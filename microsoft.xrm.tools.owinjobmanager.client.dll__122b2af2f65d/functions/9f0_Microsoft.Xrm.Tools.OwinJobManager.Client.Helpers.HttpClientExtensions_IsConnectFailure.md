# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::IsConnectFailure

- ea: `0x9f0`
- end: `0xa13`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::IsConnectFailure`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x240`
- `0x480`

## callees

- `0x9f0`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldarg.0
0x9f1  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x9f6  isinst   [System]System.Net.WebException
0x9fb  brfalse.s loc_A11
0x9fd  ldarg.0
0x9fe  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xa03  castclass [System]System.Net.WebException
0xa08  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0xa0d  ldc.i4.2
0xa0e  ceq
0xa10  ret
0xa11  ldc.i4.0
0xa12  ret
```
