# Microsoft.Crm.Metadata.AppMetaDataLoaderById::AppDataLoadQuery

- ea: `0x1adb0`
- end: `0x1ae7d`
- name: `Microsoft.Crm.Metadata.AppMetaDataLoaderById::AppDataLoadQuery`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1adb0`

## string_xrefs

- `0x1adc4`: `SELECT a.ClientType, a.AppModuleId, a.Name, a.FormFactor, a.AppModuleIdUnique, a.Url, a.UniqueName, b.AppModuleComponentId, b.ObjectId, b.ComponentType, b.AppModuleIdUnique`
- `0x1addc`: `, w.WebResourceId as welcomePageId, w.Name as welcomePageName, w.DisplayName as welcomePageDisplayName, w.WebResourceType as welcomePageType`
- `0x1ade8`: ` from AppModuleBase a LEFT JOIN AppModuleComponentBase b ON a.AppModuleIdUnique = b.AppModuleIdUnique`
- `0x1ae00`: ` LEFT JOIN WebResourceBase w ON a.WelcomePageId = w.WebResourceId`
- `0x1ae0c`: ` WHERE a.ComponentState = 0 AND a.OverwriteTime = 0`

## pseudocode

```c

```

## disassembly

```asm
0x1adb0  ldarg.1
0x1adb1  ldstr    aConnection// "connection"
0x1adb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1adbb  ldnull
0x1adbc  stloc.0
0x1adbd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1adc2  stloc.1
0x1adc3  ldloc.1
0x1adc4  ldstr    aSelectAClientt// "SELECT a.ClientType, a.AppModuleId, a.N"...
0x1adc9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1adce  pop
0x1adcf  ldloc.1
0x1add0  ldstr    aIWebresourceid// ", i.WebResourceId as iconWebresourceId,"...
0x1add5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1adda  pop
0x1addb  ldloc.1
0x1addc  ldstr    aWWebresourceid// ", w.WebResourceId as welcomePageId, w.N"...
0x1ade1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ade6  pop
0x1ade7  ldloc.1
0x1ade8  ldstr    aFromAppmoduleb// " from AppModuleBase a LEFT JOIN AppModu"...
0x1aded  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1adf2  pop
0x1adf3  ldloc.1
0x1adf4  ldstr    aLeftJoinWebres// " LEFT JOIN WebResourceBase i ON a.WebRe"...
0x1adf9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1adfe  pop
0x1adff  ldloc.1
0x1ae00  ldstr    aLeftJoinWebres_0// " LEFT JOIN WebResourceBase w ON a.Welco"...
0x1ae05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ae0a  pop
0x1ae0b  ldloc.1
0x1ae0c  ldstr    aWhereAComponen// " WHERE a.ComponentState = 0 AND a.Overw"...
0x1ae11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ae16  pop
0x1ae17  ldarg.2
0x1ae18  brfalse.s loc_1AE27
0x1ae1a  ldarg.2
0x1ae1b  ldstr    asc_B967C// ""
0x1ae20  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1ae25  brfalse.s loc_1AE36
0x1ae27  ldarg.1
0x1ae28  ldloc.1
0x1ae29  callvirt instance string [mscorlib]System.Object::ToString()
0x1ae2e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1ae33  stloc.0
0x1ae34  br.s     loc_1AE6B
0x1ae36  ldloc.1
0x1ae37  ldstr    aAndAAppmodulei// " AND a.AppModuleId = @appModuleId"
0x1ae3c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ae41  pop
0x1ae42  ldarg.1
0x1ae43  ldloc.1
0x1ae44  callvirt instance string [mscorlib]System.Object::ToString()
0x1ae49  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1ae4e  stloc.0
0x1ae4f  ldloc.0
0x1ae50  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1ae55  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1ae5a  ldstr    aAppmoduleid// "@appModuleId"
0x1ae5f  ldarg.2
0x1ae60  callvirt instance string [mscorlib]System.Object::ToString()
0x1ae65  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ae6a  pop
0x1ae6b  ldloc.0
0x1ae6c  stloc.2
0x1ae6d  leave.s  loc_1AE7B
0x1ae6f  pop
0x1ae70  ldloc.0
0x1ae71  brfalse.s loc_1AE79
0x1ae73  ldloc.0
0x1ae74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ae79  rethrow
0x1ae7b  ldloc.2
0x1ae7c  ret
```
