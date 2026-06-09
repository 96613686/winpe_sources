# Microsoft.Crm.WebServices.ExportXmlService::BlockExportOfPatchedSolution

- ea: `0xdaf0`
- end: `0xdb26`
- name: `Microsoft.Crm.WebServices.ExportXmlService::BlockExportOfPatchedSolution`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xd8b0`
- `0xda20`

## callees

- `0xdaf0`

## pseudocode

```c

```

## disassembly

```asm
0xdaf0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionService::.ctor()
0xdaf5  ldarg.1
0xdaf6  ldarg.2
0xdaf7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrievePatches(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xdafc  stloc.0
0xdafd  ldloc.0
0xdafe  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xdb03  ldc.i4.0
0xdb04  ble.s    loc_DB25
0xdb06  ldc.i4   0x80048538
0xdb0b  ldc.i4.1
0xdb0c  newarr   [mscorlib]System.Object
0xdb11  dup
0xdb12  ldc.i4.0
0xdb13  ldstr    asc_1485C// ", "
0xdb18  ldloc.0
0xdb19  call     T0x2B000002
0xdb1e  stelem.ref
0xdb1f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xdb24  throw
0xdb25  ret
```
