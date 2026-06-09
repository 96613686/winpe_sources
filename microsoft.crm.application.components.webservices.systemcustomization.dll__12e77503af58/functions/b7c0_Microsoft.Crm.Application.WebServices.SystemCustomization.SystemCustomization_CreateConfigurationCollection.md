# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateConfigurationCollection

- ea: `0xb7c0`
- end: `0xb7e8`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateConfigurationCollection`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb620`

## callees

- `0xb7c0`

## pseudocode

```c

```

## disassembly

```asm
0xb7c0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfigurationCollection::.ctor()
0xb7c5  stloc.0
0xb7c6  ldarg.1
0xb7c7  stloc.1
0xb7c8  ldc.i4.0
0xb7c9  stloc.2
0xb7ca  br.s     loc_B7E0
0xb7cc  ldloc.1
0xb7cd  ldloc.2
0xb7ce  ldelem.ref
0xb7cf  stloc.3
0xb7d0  ldloc.0
0xb7d1  ldloc.3
0xb7d2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfiguration::.ctor(string)
0xb7d7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.QuickFindConfiguration>::Add(var<u1>)
0xb7dc  ldloc.2
0xb7dd  ldc.i4.1
0xb7de  add
0xb7df  stloc.2
0xb7e0  ldloc.2
0xb7e1  ldloc.1
0xb7e2  ldlen
0xb7e3  conv.i4
0xb7e4  blt.s    loc_B7CC
0xb7e6  ldloc.0
0xb7e7  ret
```
