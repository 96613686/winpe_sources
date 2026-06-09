# Projection::ProjectionWriter::GetPromiseMaker(void)

- ea: `0x18024aee0`
- end: `0x18024b115`
- name: `?GetPromiseMaker@ProjectionWriter@Projection@@AEAAPEAVJavascriptFunction@Js@@XZ`
- size: `565`
- prototype: `struct Js::JavascriptFunction *__fastcall(Projection::ProjectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1801bd7b8`

## callees

- `0x180016010`
- `0x1800160fc`
- `0x18001ba34`
- `0x18002e9dc`
- `0x18003dd0c`
- `0x18003dd74`
- `0x18006ab10`
- `0x1800709f8`
- `0x1800f0480`
- `0x18015d94c`
- `0x18024aee0`
- `0x180341dd0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18024b050`
- `msvcrt!wcscpy_s` at `0x18024b050`
- `KERNEL32!GetUserDefaultLCID` at `0x18024afe7`
- `KERNEL32!GetUserDefaultLCID` at `0x18024afe7`
- `OLEAUT32!__imp_SysFreeString` at `0x18024b059`
- `OLEAUT32!__imp_SysFreeString` at `0x18024b059`
- `OLEAUT32!__imp_SysStringLen` at `0x18024b022`
- `OLEAUT32!__imp_SysStringLen` at `0x18024b022`

## string_xrefs

- `0x18024af65`: `// Copyright (c) Microsoft Corporation.\n// All rights reserved.\nfunction AsyncBehaviorError(message, asyncOpType, asyncOpSource, asyncOpCausalityId) {\n    this.name = 'AsyncBehaviorError';\n    this.message = (message || '');\n    this.asyncOpType = asyncOpType;\n    this.asyncOpSource = asyncOpSource;\n    this.asyncOpCausalityId = asyncOpCausalityId;\n}\nAsyncBehaviorError.prototype = Object.create(Error.prototype);\nAsyncBehaviorError.prototype.constructor = AsyncBehaviorError;\n\nfunction`

## pseudocode

```c

```
