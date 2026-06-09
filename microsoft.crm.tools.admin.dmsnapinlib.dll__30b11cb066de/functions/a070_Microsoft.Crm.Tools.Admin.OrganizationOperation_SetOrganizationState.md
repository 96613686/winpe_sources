# Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrganizationState

- ea: `0xa070`
- end: `0xa127`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrganizationState`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9b70`
- `0xdab0`
- `0x19670`

## callees

- `0x98b0`
- `0xa070`

## string_xrefs

- `0xa0cf`: `Not setting state to {0} as it is already set to {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa070  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0xa075  stloc.0
0xa076  ldloca.s 1
0xa078  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>
0xa07e  ldloc.0
0xa07f  ldarg.0
0xa080  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationId()
0xa085  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetState(valuetype [mscorlib]System.Guid)
0xa08a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::.ctor(var<u1>)
0xa08f  stloc.1
0xa090  leave.s  loc_A0BC
0xa092  stloc.2
0xa093  ldstr    aCouldNotRetrie_0// "Could not retrieve current state for or"...
0xa098  ldc.i4.2
0xa099  newarr   [mscorlib]System.Object
0xa09e  dup
0xa09f  ldc.i4.0
0xa0a0  ldarg.0
0xa0a1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationId()
0xa0a6  box      [mscorlib]System.Guid
0xa0ab  stelem.ref
0xa0ac  dup
0xa0ad  ldc.i4.1
0xa0ae  ldloc.2
0xa0af  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa0b4  stelem.ref
0xa0b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0xa0ba  leave.s  loc_A0BC
0xa0bc  ldloca.s 1
0xa0be  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_HasValue()
0xa0c3  brfalse.s loc_A0F8
0xa0c5  ldloca.s 1
0xa0c7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_Value()
0xa0cc  ldarg.1
0xa0cd  bne.un.s loc_A0F8
0xa0cf  ldstr    aNotSettingStat// "Not setting state to {0} as it is alrea"...
0xa0d4  ldarg.1
0xa0d5  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xa0da  ldloca.s 1
0xa0dc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_Value()
0xa0e1  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xa0e6  call     string [mscorlib]System.String::Format(string, object, object)
0xa0eb  ldc.i4.0
0xa0ec  newarr   [mscorlib]System.Object
0xa0f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xa0f6  br.s     loc_A125
0xa0f8  ldstr    aSettingOrganiz// "Setting organization state.  New state "...
0xa0fd  ldc.i4.1
0xa0fe  newarr   [mscorlib]System.Object
0xa103  dup
0xa104  ldc.i4.0
0xa105  ldarga.s 1
0xa107  constrained. [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xa10d  callvirt instance string [mscorlib]System.Object::ToString()
0xa112  stelem.ref
0xa113  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xa118  ldloc.0
0xa119  ldarg.0
0xa11a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationId()
0xa11f  ldarg.1
0xa120  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetState(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState)
0xa125  ldloc.1
0xa126  ret
```
