# Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::TrySetExecutingUserProperties

- ea: `0x15640`
- end: `0x157ce`
- name: `Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::TrySetExecutingUserProperties`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x153e0`

## callees

- `0x15640`
- `0x15930`

## string_xrefs

- `0x1568e`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationImportSolution\PackageDeployerExecutableWrapper.cs`
- `0x156b8`: `Property for executing user account name has been read correctly, but data is missing.`
- `0x156e9`: `Property for executing user account password has been read correctly, but data is missing.`

## pseudocode

```c

```

## disassembly

```asm
0x15640  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x15645  stloc.0
0x15646  ldstr    asc_361CC// ""
0x1564b  stloc.1
0x1564c  ldc.i4.2
0x1564d  newarr   [mscorlib]System.String
0x15652  dup
0x15653  ldc.i4.0
0x15654  ldstr    aApplicationid// "ApplicationId"
0x15659  stelem.ref
0x1565a  dup
0x1565b  ldc.i4.1
0x1565c  ldstr    aApplicationsec// "ApplicationSecret"
0x15661  stelem.ref
0x15662  stloc.3
0x15663  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x15668  stloc.s  4
0x1566a  ldloc.s  4
0x1566c  ldstr    aName// "Name"
0x15671  ldstr    aPdaccount// "PDAccount"
0x15676  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1567b  ldloc.0
0x1567c  ldstr    aExternalkey// "ExternalKey"
0x15681  ldloc.3
0x15682  ldloc.s  4
0x15684  ldc.i4   0x9E
0x15689  ldstr    aTrysetexecutin// "TrySetExecutingUserProperties"
0x1568e  ldstr    aDDbsShDccm2110_29// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x15693  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x15698  stloc.s  5
0x1569a  ldloc.s  5
0x1569c  brfalse.s loc_156FB
0x1569e  ldloc.s  5
0x156a0  ldstr    aApplicationid// "ApplicationId"
0x156a5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x156aa  castclass [mscorlib]System.String
0x156af  stloc.1
0x156b0  ldloc.1
0x156b1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x156b6  brfalse.s loc_156CA
0x156b8  ldstr    aPropertyForExe// "Property for executing user account nam"...
0x156bd  call     void Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::LogWarning(string message)
0x156c2  ldc.i4.0
0x156c3  stloc.s  7
0x156c5  leave    loc_157CB
0x156ca  ldloc.s  5
0x156cc  ldstr    aApplicationsec// "ApplicationSecret"
0x156d1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x156d6  castclass [mscorlib]System.Security.SecureString
0x156db  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x156e0  stloc.2
0x156e1  ldloc.2
0x156e2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x156e7  brfalse.s loc_1570D
0x156e9  ldstr    aPropertyForExe_0// "Property for executing user account pas"...
0x156ee  call     void Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::LogWarning(string message)
0x156f3  ldc.i4.0
0x156f4  stloc.s  7
0x156f6  leave    loc_157CB
0x156fb  ldstr    aCouldNotRetrie// "Could not retrieve properties for PDAcc"...
0x15700  call     void Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::LogWarning(string message)
0x15705  ldc.i4.0
0x15706  stloc.s  7
0x15708  leave    loc_157CB
0x1570d  ldloc.1
0x1570e  ldsfld   char [mscorlib]System.IO.Path::AltDirectorySeparatorChar
0x15713  call     bool [Microsoft.Crm.Core]Microsoft.Crm.IEnumerableExtensions::Contains(string, char)
0x15718  brfalse.s loc_1575C
0x1571a  ldloc.1
0x1571b  ldc.i4.1
0x1571c  newarr   [mscorlib]System.Char
0x15721  dup
0x15722  ldc.i4.0
0x15723  ldsfld   char [mscorlib]System.IO.Path::AltDirectorySeparatorChar
0x15728  stelem.i2
0x15729  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1572e  stloc.s  8
0x15730  ldloc.s  8
0x15732  ldlen
0x15733  conv.i4
0x15734  ldc.i4.2
0x15735  bne.un.s loc_15763
0x15737  ldarg.0
0x15738  ldloc.s  8
0x1573a  call     T0x2B00007B
0x1573f  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Domain(string)
0x15744  ldarg.0
0x15745  ldloc.s  8
0x15747  call     T0x2B00007C
0x1574c  dup
0x1574d  brtrue.s loc_15755
0x1574f  pop
0x15750  ldsfld   string [mscorlib]System.String::Empty
0x15755  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UserName(string)
0x1575a  br.s     loc_15763
0x1575c  ldarg.0
0x1575d  ldloc.1
0x1575e  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UserName(string)
0x15763  newobj   instance void [mscorlib]System.Security.SecureString::.ctor()
0x15768  stloc.s  6
0x1576a  ldloc.2
0x1576b  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0x15770  stloc.s  9
0x15772  ldc.i4.0
0x15773  stloc.s  0xA
0x15775  br.s     loc_1578D
0x15777  ldloc.s  9
0x15779  ldloc.s  0xA
0x1577b  ldelem.u2
0x1577c  stloc.s  0xB
0x1577e  ldloc.s  6
0x15780  ldloc.s  0xB
0x15782  callvirt instance void [mscorlib]System.Security.SecureString::AppendChar(char)
0x15787  ldloc.s  0xA
0x15789  ldc.i4.1
0x1578a  add
0x1578b  stloc.s  0xA
0x1578d  ldloc.s  0xA
0x1578f  ldloc.s  9
0x15791  ldlen
0x15792  conv.i4
0x15793  blt.s    loc_15777
0x15795  ldarg.0
0x15796  ldloc.s  6
0x15798  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Password(class [mscorlib]System.Security.SecureString)
0x1579d  ldc.i4.1
0x1579e  stloc.s  7
0x157a0  leave.s  loc_157CB
0x157a2  ldloc.0
0x157a3  brfalse.s loc_157AB
0x157a5  ldloc.0
0x157a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x157ab  endfinally
0x157ac  stloc.s  0xC
0x157ae  ldstr    aExecutionOf// "Execution of '"
0x157b3  ldarg.0
0x157b4  callvirt instance string [System]System.Diagnostics.ProcessStartInfo::get_FileName()
0x157b9  ldstr    aIsTerminatedEx// "'is terminated. Exception occured while"...
0x157be  call     string [mscorlib]System.String::Concat(string, string, string)
0x157c3  ldloc.s  0xC
0x157c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x157ca  throw
0x157cb  ldloc.s  7
0x157cd  ret
```
