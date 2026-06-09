# Microsoft.Crm.Application.Commands.ApplicationCommand::UpdateUserSettingsLanguage

- ea: `0x32bb0`
- end: `0x32c69`
- name: `Microsoft.Crm.Application.Commands.ApplicationCommand::UpdateUserSettingsLanguage`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x32b50`
- `0x32b80`

## callees

- `0x30130`
- `0x32bb0`
- `0x47940`
- `0x59690`
- `0x5be40`
- `0x5c6f0`
- `0x6a810`

## string_xrefs

- `0x32bdd`: `UserSettings.{0} {1} is invalid and is being updated to {2}.`
- `0x32c27`: `UserSettings.{0} {1} is invalid and failed updated to {2}: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x32bb0  ldstr    aUsersettings// "usersettings"
0x32bb5  ldarg.3
0x32bb6  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x32bbb  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x32bc0  stloc.0
0x32bc1  ldloc.0
0x32bc2  ldstr    aSystemuserid// "systemuserid"
0x32bc7  ldarg.3
0x32bc8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserId()
0x32bcd  box      [mscorlib]System.Guid
0x32bd2  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x32bd7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x32bdc  ldc.i4.0
0x32bdd  ldstr    aUsersettings01// "UserSettings.{0} {1} is invalid and is "...
0x32be2  ldc.i4.3
0x32be3  newarr   [mscorlib]System.Object
0x32be8  dup
0x32be9  ldc.i4.0
0x32bea  ldarg.0
0x32beb  stelem.ref
0x32bec  dup
0x32bed  ldc.i4.1
0x32bee  ldarg.1
0x32bef  box      [mscorlib]System.Int32
0x32bf4  stelem.ref
0x32bf5  dup
0x32bf6  ldc.i4.2
0x32bf7  ldarg.2
0x32bf8  box      [mscorlib]System.Int32
0x32bfd  stelem.ref
0x32bfe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32c03  ldloc.0
0x32c04  ldarg.0
0x32c05  ldarg.2
0x32c06  box      [mscorlib]System.Int32
0x32c0b  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x32c10  newobj   instance void Microsoft.Crm.Application.Security.WrpcValidationBypass::.ctor()
0x32c15  stloc.1
0x32c16  ldloc.0
0x32c17  ldarg.3
0x32c18  call     void Microsoft.Crm.Application.Platform.DataSource::Update(class Microsoft.Crm.Application.Platform.EntityProxy entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x32c1d  leave.s  loc_32C68
0x32c1f  stloc.2
0x32c20  ldloc.2
0x32c21  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x32c26  ldc.i4.0
0x32c27  ldstr    aUsersettings01_0// "UserSettings.{0} {1} is invalid and fai"...
0x32c2c  ldc.i4.4
0x32c2d  newarr   [mscorlib]System.Object
0x32c32  dup
0x32c33  ldc.i4.0
0x32c34  ldarg.0
0x32c35  stelem.ref
0x32c36  dup
0x32c37  ldc.i4.1
0x32c38  ldarg.1
0x32c39  box      [mscorlib]System.Int32
0x32c3e  stelem.ref
0x32c3f  dup
0x32c40  ldc.i4.2
0x32c41  ldarg.2
0x32c42  box      [mscorlib]System.Int32
0x32c47  stelem.ref
0x32c48  dup
0x32c49  ldc.i4.3
0x32c4a  ldloc.2
0x32c4b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x32c50  stelem.ref
0x32c51  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32c56  ldarg.s  4
0x32c58  brfalse.s loc_32C5C
0x32c5a  rethrow
0x32c5c  leave.s  loc_32C68
0x32c5e  ldloc.1
0x32c5f  brfalse.s loc_32C67
0x32c61  ldloc.1
0x32c62  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32c67  endfinally
0x32c68  ret
```
