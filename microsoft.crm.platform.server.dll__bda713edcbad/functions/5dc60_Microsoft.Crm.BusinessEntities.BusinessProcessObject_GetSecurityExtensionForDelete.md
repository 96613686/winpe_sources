# Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetSecurityExtensionForDelete

- ea: `0x5dc60`
- end: `0x5dc95`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetSecurityExtensionForDelete`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8c1d0`

## callees

- `0x5d540`
- `0x5dba0`
- `0x5dc60`
- `0x84b20`
- `0x84b90`

## string_xrefs

- `0x5dc6b`: `ActivityPartyServicebaseFactory`
- `0x5dc83`: `The security extension returned does not implement the IDeleteSecurityExtension interface`

## pseudocode

```c

```

## disassembly

```asm
0x5dc60  call     class Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory Microsoft.Crm.BusinessEntities.CrmBaseSecurityExtensionFactory::get_Instance()
0x5dc65  ldarg.0
0x5dc66  call     instance string Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x5dc6b  ldstr    aActivitypartys// "ActivityPartyServicebaseFactory"
0x5dc70  call     object Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string typeName)
0x5dc75  callvirt instance class Microsoft.Crm.BusinessEntities.ICrmExtension Microsoft.Crm.BusinessEntities.ICrmSecurityExtensionFactory::Get(string platformName, object activityPartyServicebaseFactory)
0x5dc7a  isinst   Microsoft.Crm.BusinessEntities.IDeleteSecurityExtension
0x5dc7f  stloc.0
0x5dc80  ldloc.0
0x5dc81  brtrue.s loc_5DC93
0x5dc83  ldstr    aTheSecurityExt// "The security extension returned does no"...
0x5dc88  ldc.i4   0x80040216
0x5dc8d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5dc92  throw
0x5dc93  ldloc.0
0x5dc94  ret
```
