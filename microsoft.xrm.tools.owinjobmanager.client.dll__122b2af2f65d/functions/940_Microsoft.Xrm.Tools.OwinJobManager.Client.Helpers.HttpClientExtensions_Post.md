# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Post

- ea: `0x940`
- end: `0x968`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Post`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8a0`
- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x940  ldarg.0
0x941  ldarg.1
0x942  ldarg.2
0x943  call     T0x2B00000A
0x948  stloc.0
0x949  ldloc.0
0x94a  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x94f  call     string Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::ReadAsString(class [System.Net.Http]System.Net.Http.HttpContent content)
0x954  call     T0x2B00000B
0x959  stloc.1
0x95a  leave.s  loc_966
0x95c  ldloc.0
0x95d  brfalse.s loc_965
0x95f  ldloc.0
0x960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x965  endfinally
0x966  ldloc.1
0x967  ret
```
