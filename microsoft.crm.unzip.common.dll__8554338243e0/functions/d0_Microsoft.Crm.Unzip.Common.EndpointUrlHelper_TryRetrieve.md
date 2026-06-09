# Microsoft.Crm.Unzip.Common.EndpointUrlHelper::TryRetrieve

- ea: `0xd0`
- end: `0xf8`
- name: `Microsoft.Crm.Unzip.Common.EndpointUrlHelper::TryRetrieve`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb0`

## callees

- `0x90`
- `0xd0`

## pseudocode

```c

```

## disassembly

```asm
0xd0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xd5  ldstr    aImportunzipser// "ImportUnzipServerWithPort"
0xda  callvirt T0x2B000001
0xdf  stloc.0
0xe0  ldloc.0
0xe1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe6  brfalse.s loc_EE
0xe8  ldstr    aLocalhost8500// "localhost:8500"
0xed  stloc.0
0xee  ldarg.0
0xef  ldloc.0
0xf0  call     class [System]System.Uri Microsoft.Crm.Unzip.Common.EndpointUrlHelper::BuildUrl(string server)
0xf5  stind.ref
0xf6  ldc.i4.1
0xf7  ret
```
