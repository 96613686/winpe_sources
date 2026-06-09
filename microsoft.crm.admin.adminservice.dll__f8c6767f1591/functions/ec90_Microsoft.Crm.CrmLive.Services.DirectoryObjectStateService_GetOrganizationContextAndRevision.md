# Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::GetOrganizationContextAndRevision

- ea: `0xec90`
- end: `0xed67`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::GetOrganizationContextAndRevision`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xec90`

## string_xrefs

- `0xecde`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryObjectStateService.cs`
- `0xecc8`: `DirectoryObjectRevision`
- `0xed09`: `DirectoryObjectRevision`
- `0xed16`: `DirectoryObjectRevision`
- `0xed23`: `DirectoryObjectRevision`

## pseudocode

```c

```

## disassembly

```asm
0xec90  ldarg.1
0xec91  ldstr    aOrganizationid// "organizationId"
0xec96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xec9b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xeca0  stloc.0
0xeca1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xeca6  stloc.1
0xeca7  ldloc.1
0xeca8  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xecad  ldarg.1
0xecae  box      [mscorlib]System.Guid
0xecb3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xecb8  ldc.i4.2
0xecb9  newarr   [mscorlib]System.String
0xecbe  dup
0xecbf  ldc.i4.0
0xecc0  ldstr    aContextid// "ContextId"
0xecc5  stelem.ref
0xecc6  dup
0xecc7  ldc.i4.1
0xecc8  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xeccd  stelem.ref
0xecce  stloc.2
0xeccf  ldloc.0
0xecd0  ldstr    aOrganizationli// "OrganizationLifecycle"
0xecd5  ldloc.2
0xecd6  ldloc.1
0xecd7  ldc.i4.s 0x65
0xecd9  ldstr    aGetorganizatio// "GetOrganizationContextAndRevision"
0xecde  ldstr    aDA1SSrcCrmlive_20// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xece3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xece8  stloc.3
0xece9  ldloc.3
0xecea  brfalse.s loc_ED44
0xecec  ldloc.3
0xeced  ldstr    aContextid// "ContextId"
0xecf2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xecf7  brfalse.s loc_ED44
0xecf9  ldloc.3
0xecfa  ldstr    aContextid// "ContextId"
0xecff  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xed04  ldc.i4.m1
0xed05  conv.i8
0xed06  stloc.s  4
0xed08  ldloc.3
0xed09  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xed0e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xed13  brfalse.s loc_ED34
0xed15  ldloc.3
0xed16  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xed1b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xed20  brfalse.s loc_ED34
0xed22  ldloc.3
0xed23  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0xed28  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xed2d  unbox.any [mscorlib]System.Int64
0xed32  stloc.s  4
0xed34  unbox.any [mscorlib]System.Guid
0xed39  ldloc.s  4
0xed3b  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::.ctor(var<u1>, !!T0)
0xed40  stloc.s  5
0xed42  leave.s  loc_ED64
0xed44  leave.s  loc_ED50
0xed46  ldloc.0
0xed47  brfalse.s loc_ED4F
0xed49  ldloc.0
0xed4a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xed4f  endfinally
0xed50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xed55  ldc.i8   0x8000000000000000
0xed5e  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::.ctor(var<u1>, !!T0)
0xed63  ret
0xed64  ldloc.s  5
0xed66  ret
```
