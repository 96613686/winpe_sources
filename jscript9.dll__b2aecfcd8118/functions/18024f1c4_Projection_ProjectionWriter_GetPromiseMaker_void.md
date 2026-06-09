# Projection::ProjectionWriter::GetPromiseMaker(void)

- ea: `0x18024f1c4`
- end: `0x18024f412`
- name: `?GetPromiseMaker@ProjectionWriter@Projection@@AEAAPEAVJavascriptFunction@Js@@XZ`
- size: `590`
- prototype: `struct Js::JavascriptFunction *__fastcall(Projection::ProjectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1801bfff4`

## callees

- `0x18000e108`
- `0x18000e178`
- `0x1800141fc`
- `0x18001e340`
- `0x180021bb4`
- `0x18007a2e4`
- `0x1800e58c0`
- `0x1800e59ac`
- `0x18011eb74`
- `0x18015fe58`
- `0x18024f1c4`
- `0x1803481f0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18024f340`
- `msvcrt!wcscpy_s` at `0x18024f340`
- `KERNEL32!GetUserDefaultLCID` at `0x18024f2cb`
- `KERNEL32!GetUserDefaultLCID` at `0x18024f2cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18024f34f`
- `OLEAUT32!__imp_SysFreeString` at `0x18024f34f`
- `OLEAUT32!__imp_SysStringLen` at `0x18024f30c`
- `OLEAUT32!__imp_SysStringLen` at `0x18024f30c`

## string_xrefs

- `0x18024f249`: `// Copyright (c) Microsoft Corporation.\n// All rights reserved.\nfunction AsyncBehaviorError(message, asyncOpType, asyncOpSource, asyncOpCausalityId) {\n    this.name = 'AsyncBehaviorError';\n    this.message = (message || '');\n    this.asyncOpType = asyncOpType;\n    this.asyncOpSource = asyncOpSource;\n    this.asyncOpCausalityId = asyncOpCausalityId;\n}\nAsyncBehaviorError.prototype = Object.create(Error.prototype);\nAsyncBehaviorError.prototype.constructor = AsyncBehaviorError;\n\nfunction`

## pseudocode

```c

```
