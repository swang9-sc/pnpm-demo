# pnpm-demo
This repo demonstrates the non-determinism with hoisting node_modules. It is a monorepo with 2 apps appA/appB in it. And when you do pnpm install, it is non-deterministic that which app's dependencies get hoisted.
For example, appA depends on react 16 and appB depends on react 18. The final hoisted react version would change randomly between 16 and 18 as you keep doing pnpm install.
## Steps to reproduce
1. clone the repo
2. pnpm i
3. open .modules.yaml
4. Locate the react package in the yaml (or in the .pnpm/node_modules)
5. Keep doing pnpm i until you see the change in .modules.yaml
