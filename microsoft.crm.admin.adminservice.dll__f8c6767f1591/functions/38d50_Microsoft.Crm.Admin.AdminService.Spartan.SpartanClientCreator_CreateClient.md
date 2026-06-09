# Microsoft.Crm.Admin.AdminService.Spartan.SpartanClientCreator::CreateClient

- ea: `0x38d50`
- end: `0x38e32`
- name: `Microsoft.Crm.Admin.AdminService.Spartan.SpartanClientCreator::CreateClient`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x394b0`

## callees

- `0x38d50`

## string_xrefs

- `0x38d6c`: `SpartanServicePrincipal`
- `0x38dcb`: `CreateClient`
- `0x38dd0`: `D:\a\1\s\src\CrmLive\Admin\Spartan\SpartanService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x38d50  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x38d55  stloc.0
0x38d56  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x38d5b  ldstr    aSpartankeyvaul// "SpartanKeyVaultUrl"
0x38d60  ldc.i4.1
0x38d61  callvirt T0x2B000014
0x38d66  stloc.1
0x38d67  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x38d6c  ldstr    aSpartanservice// "SpartanServicePrincipal"
0x38d71  ldc.i4.1
0x38d72  callvirt T0x2B000014
0x38d77  stloc.2
0x38d78  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x38d7d  ldstr    aSpartanenviron// "SpartanEnvironment"
0x38d82  ldc.i4.1
0x38d83  callvirt T0x2B000014
0x38d88  stloc.3
0x38d89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x38d8e  stloc.s  4
0x38d90  ldloc.s  4
0x38d92  ldstr    aType// "Type"
0x38d97  ldc.i4.s 0x11
0x38d99  box      [mscorlib]System.Int32
0x38d9e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x38da3  ldloc.0
0x38da4  ldstr    aAzureapplicati// "AzureApplication"
0x38da9  ldc.i4.3
0x38daa  newarr   [mscorlib]System.String
0x38daf  dup
0x38db0  ldc.i4.0
0x38db1  ldstr    aClientid// "ClientId"
0x38db6  stelem.ref
0x38db7  dup
0x38db8  ldc.i4.1
0x38db9  ldstr    aDomain// "Domain"
0x38dbe  stelem.ref
0x38dbf  dup
0x38dc0  ldc.i4.2
0x38dc1  ldstr    aSecretkey// "SecretKey"
0x38dc6  stelem.ref
0x38dc7  ldloc.s  4
0x38dc9  ldc.i4.s 0x39
0x38dcb  ldstr    aCreateclient// "CreateClient"
0x38dd0  ldstr    aDA1SSrcCrmlive_65// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Spart"...
0x38dd5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x38dda  dup
0x38ddb  brtrue.s loc_38DE8
0x38ddd  ldstr    aNoValidAzureap// "No valid AzureApplication with type Crm"...
0x38de2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x38de7  throw
0x38de8  dup
0x38de9  ldstr    aClientid// "ClientId"
0x38dee  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x38df3  callvirt instance string [mscorlib]System.Object::ToString()
0x38df8  stloc.s  5
0x38dfa  ldstr    aSecretkey// "SecretKey"
0x38dff  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x38e04  castclass [mscorlib]System.Security.SecureString
0x38e09  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x38e0e  stloc.s  6
0x38e10  ldloc.2
0x38e11  ldloc.3
0x38e12  ldloc.s  5
0x38e14  ldloc.s  6
0x38e16  ldloc.1
0x38e17  newobj   instance void [Spartan.Common.Azure]Microsoft.Dynamics.DataServices.Spartan.Common.Azure.AccessCredential::.ctor(string, string, string)
0x38e1c  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.SpartanClient::.ctor(string, string, class [Spartan.Common.Azure]Microsoft.Dynamics.DataServices.Spartan.Common.Azure.AccessCredential)
0x38e21  stloc.s  7
0x38e23  leave.s  loc_38E2F
0x38e25  ldloc.0
0x38e26  brfalse.s loc_38E2E
0x38e28  ldloc.0
0x38e29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38e2e  endfinally
0x38e2f  ldloc.s  7
0x38e31  ret
```
