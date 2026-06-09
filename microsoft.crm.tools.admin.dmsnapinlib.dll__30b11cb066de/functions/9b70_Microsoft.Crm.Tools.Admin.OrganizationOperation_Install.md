# Microsoft.Crm.Tools.Admin.OrganizationOperation::Install

- ea: `0x9b70`
- end: `0x9d2b`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::Install`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x121d0`
- `0x168d0`

## callees

- `0x47e0`
- `0x4820`
- `0x8e30`
- `0x9870`
- `0x98b0`
- `0x9950`
- `0x9b70`
- `0x9f10`
- `0xa070`
- `0x19660`

## string_xrefs

- `0x9c2c`: `Failed to retrieve MetadataCacheConfigContext.`
- `0x9ca4`: `Exception occurred during`
- `0x9ccb`: `SetOrganizationState In Config`
- `0x9d11`: `Exception occurred during the finally block of`

## pseudocode

```c

```

## disassembly

```asm
0x9b70  newobj   instance void <>c__DisplayClass56_0::.ctor()
0x9b75  stloc.0
0x9b76  ldloc.0
0x9b77  ldarg.0
0x9b78  stfld    class Microsoft.Crm.Tools.Admin.OrganizationOperation <>c__DisplayClass56_0::<>4__this
0x9b7d  ldc.i4.2
0x9b7e  stloc.1
0x9b7f  ldnull
0x9b80  stloc.2
0x9b81  ldc.i4.0
0x9b82  stloc.3
0x9b83  ldc.i4.3
0x9b84  ldarg.0
0x9b85  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x9b8a  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x9b8f  beq.s    loc_9B9F
0x9b91  ldc.i4.4
0x9b92  ldarg.0
0x9b93  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x9b98  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x9b9d  bne.un.s loc_9BC0
0x9b9f  ldc.i4.1
0x9ba0  stloc.3
0x9ba1  ldarg.0
0x9ba2  ldc.i4.2
0x9ba3  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState> Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrganizationState(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState newState)
0x9ba8  stloc.s  4
0x9baa  ldloca.s 4
0x9bac  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_HasValue()
0x9bb1  brtrue.s loc_9BB6
0x9bb3  ldc.i4.2
0x9bb4  br.s     loc_9BBD
0x9bb6  ldloca.s 4
0x9bb8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_Value()
0x9bbd  stloc.1
0x9bbe  br.s     loc_9BD0
0x9bc0  ldc.i4.5
0x9bc1  ldarg.0
0x9bc2  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x9bc7  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x9bcc  bne.un.s loc_9BD0
0x9bce  ldc.i4.1
0x9bcf  stloc.3
0x9bd0  ldloc.0
0x9bd1  ldc.i4.1
0x9bd2  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState <>c__DisplayClass56_0::postOperationState
0x9bd7  ldarg.0
0x9bd8  call     instance bool Microsoft.Crm.Tools.Admin.OrganizationOperation::get_RestorePreviousStateOnCompletion()
0x9bdd  brfalse.s loc_9BE8
0x9bdf  ldloc.0
0x9be0  ldloc.1
0x9be1  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState <>c__DisplayClass56_0::postOperationState
0x9be6  br.s     loc_9BFC
0x9be8  ldarg.0
0x9be9  ldfld    bool Microsoft.Crm.Tools.Admin.OrganizationOperation::_callerSpecifiedPostOperationOrganizationState
0x9bee  brfalse.s loc_9BFC
0x9bf0  ldloc.0
0x9bf1  ldarg.0
0x9bf2  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Tools.Admin.OrganizationOperation::_postOperationStateSpecifiedByCaller
0x9bf7  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState <>c__DisplayClass56_0::postOperationState
0x9bfc  nop
0x9bfd  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x9c02  stloc.s  5
0x9c04  ldloc.s  5
0x9c06  ldnull
0x9c07  cgt.un
0x9c09  ldstr    aFailedToRetrie// "Failed to retrieve current identity."
0x9c0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9c13  ldarg.0
0x9c14  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationId()
0x9c19  ldloc.s  5
0x9c1b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x9c20  newobj   instance void Microsoft.Crm.Tools.Admin.MetadataCacheConfigContext::.ctor(valuetype [mscorlib]System.Guid organizationId, string systemUserDomainName)
0x9c25  stloc.s  6
0x9c27  ldloc.s  6
0x9c29  ldnull
0x9c2a  cgt.un
0x9c2c  ldstr    aFailedToRetrie_0// "Failed to retrieve MetadataCacheConfigC"...
0x9c31  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9c36  ldc.i4.1
0x9c37  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0x9c3c  ldc.i4.2
0x9c3d  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheLoadOption)
0x9c42  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x9c47  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x9c4c  ldarg.0
0x9c4d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationId()
0x9c52  ldloc.3
0x9c53  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SetMetadataCacheConfigForUpdates::.ctor(valuetype [mscorlib]System.Guid, bool)
0x9c58  stloc.s  7
0x9c5a  ldarg.0
0x9c5b  ldarg.1
0x9c5c  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x9c61  leave.s  loc_9C6F
0x9c63  ldloc.s  7
0x9c65  brfalse.s loc_9C6E
0x9c67  ldloc.s  7
0x9c69  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c6e  endfinally
0x9c6f  leave.s  loc_9C7E
0x9c71  stloc.s  8
0x9c73  ldloc.s  6
0x9c75  ldloc.s  8
0x9c77  callvirt instance void Microsoft.Crm.Tools.Admin.MetadataCacheConfigContext::set_Exception(class [mscorlib]System.Exception value)
0x9c7c  rethrow
0x9c7e  leave.s  loc_9C8C
0x9c80  ldloc.s  6
0x9c82  brfalse.s loc_9C8B
0x9c84  ldloc.s  6
0x9c86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c8b  endfinally
0x9c8c  leave.s  loc_9C9A
0x9c8e  ldloc.s  5
0x9c90  brfalse.s loc_9C99
0x9c92  ldloc.s  5
0x9c94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c99  endfinally
0x9c9a  leave    loc_9D2A
0x9c9f  stloc.s  9
0x9ca1  ldloc.s  9
0x9ca3  stloc.2
0x9ca4  ldstr    aExceptionOccur// "Exception occurred during"
0x9ca9  stloc.s  0xA
0x9cab  ldarg.0
0x9cac  ldloc.s  9
0x9cae  ldloc.s  0xA
0x9cb0  call     instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HandleExceptionInInstall(class [mscorlib]System.Exception ex, string message)
0x9cb5  ldloc.0
0x9cb6  ldc.i4.3
0x9cb7  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState <>c__DisplayClass56_0::postOperationState
0x9cbc  rethrow
0x9cbe  nop
0x9cbf  ldloc.0
0x9cc0  ldftn    instance string <>c__DisplayClass56_0::<Install>b__0()
0x9cc6  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x9ccb  ldstr    aSetorganizatio// "SetOrganizationState In Config"
0x9cd0  ldarg.0
0x9cd1  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x9cd6  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x9cdb  call     instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x9ce0  call     T0x2B000008
0x9ce5  pop
0x9ce6  ldarg.0
0x9ce7  ldftn    instance string Microsoft.Crm.Tools.Admin.OrganizationOperation::<Install>b__56_1()
0x9ced  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x9cf2  ldstr    aSetorganizatio_0// "SetOrganizationState In Org"
0x9cf7  ldarg.0
0x9cf8  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x9cfd  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x9d02  call     instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x9d07  call     T0x2B000008
0x9d0c  pop
0x9d0d  leave.s  loc_9D29
0x9d0f  stloc.s  0xB
0x9d11  ldstr    aExceptionOccur_0// "Exception occurred during the finally b"...
0x9d16  stloc.s  0xC
0x9d18  ldarg.0
0x9d19  ldloc.s  0xB
0x9d1b  ldloc.s  0xC
0x9d1d  call     instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HandleExceptionInInstall(class [mscorlib]System.Exception ex, string message)
0x9d22  ldloc.2
0x9d23  brtrue.s loc_9D27
0x9d25  rethrow
0x9d27  leave.s  loc_9D29
0x9d29  endfinally
0x9d2a  ret
```
