# Microsoft.Crm.MetadataService.AccessTeamHelper::VerifyAccessTeamLimits

- ea: `0x65e30`
- end: `0x65e65`
- name: `Microsoft.Crm.MetadataService.AccessTeamHelper::VerifyAccessTeamLimits`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x65dc0`

## callees

- `0x65e30`

## string_xrefs

- `0x65e35`: `MaxEntitiesEnabledForAutoCreatedAccessTeams`
- `0x65e41`: `SELECT COUNT(*) FROM EntityView WHERE AutoCreateAccessTeams=1`

## pseudocode

```c

```

## disassembly

```asm
0x65e30  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x65e35  ldstr    aMaxentitiesena// "MaxEntitiesEnabledForAutoCreatedAccessT"...
0x65e3a  callvirt T0x2B000062
0x65e3f  stloc.0
0x65e40  ldarg.1
0x65e41  ldstr    aSelectCountFro// "SELECT COUNT(*) FROM EntityView WHERE A"...
0x65e46  call     object [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.SqlHelper::ExecuteScalar(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper, string)
0x65e4b  unbox.any [mscorlib]System.Int32
0x65e50  ldloc.0
0x65e51  blt.s    loc_65E64
0x65e53  ldc.i4   0x80048332
0x65e58  ldc.i4.0
0x65e59  newarr   [mscorlib]System.Object
0x65e5e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x65e63  throw
0x65e64  ret
```
