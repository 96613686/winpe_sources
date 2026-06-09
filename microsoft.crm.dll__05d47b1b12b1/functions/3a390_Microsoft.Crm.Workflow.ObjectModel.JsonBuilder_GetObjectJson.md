# Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson

- ea: `0x3a390`
- end: `0x3a3b1`
- name: `Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson`
- size: `33`
- prototype: ``
- caller_count: `43`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x29260`
- `0x29c80`
- `0x29fc0`
- `0x2a320`
- `0x2a730`
- `0x2af40`
- `0x2b340`
- `0x2b7e0`
- `0x2cd10`
- `0x2d260`
- `0x2d800`
- `0x2ddd0`
- `0x2e1f0`
- `0x2ec80`
- `0x2f350`
- `0x2f930`
- `0x2ff00`
- `0x30be0`
- `0x30f80`
- `0x31490`
- `0x31860`
- `0x31b40`
- `0x33740`
- `0x33930`
- `0x34260`
- `0x34550`
- `0x34940`
- `0x35540`
- `0x35850`
- `0x35ae0`
- `0x361c0`
- `0x379b0`
- `0x381a0`
- `0x386d0`
- `0x3b3f0`
- `0x3b9e0`
- `0x3c500`
- `0x3cc60`
- `0x3d260`
- `0x3d4e0`
- `0x3e4a0`
- `0x3eea0`
- `0x3fcb0`

## callees

- `0x3a370`
- `0x3a390`

## pseudocode

```c

```

## disassembly

```asm
0x3a390  ldarg.2
0x3a391  brtrue.s loc_3A39A
0x3a393  ldstr    asc_66456// ""
0x3a398  br.s     loc_3A39F
0x3a39a  ldstr    asc_6B1E0// ","
0x3a39f  ldarg.0
0x3a3a0  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetQuotedString(string propertyName)
0x3a3a5  ldstr    asc_7440A// ":"
0x3a3aa  ldarg.1
0x3a3ab  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3a3b0  ret
```
