# Microsoft.Crm.Metadata.AppMetaDataLoaderByUName::AppDataLoadQuery

- ea: `0x1afb0`
- end: `0x1b053`
- name: `Microsoft.Crm.Metadata.AppMetaDataLoaderByUName::AppDataLoadQuery`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1afb0`
- `0x1b060`

## string_xrefs

- `0x1afc3`: `SELECT a.ClientType, a.AppModuleId, a.Name, a.FormFactor, a.AppModuleIdUnique, a.Url, a.UniqueName, b.AppModuleComponentId, b.ObjectId, b.ComponentType, b.AppModuleIdUnique`
- `0x1afdb`: `, w.WebResourceId as welcomePageId, w.Name as welcomePageName, w.DisplayName as welcomePageDisplayName, w.WebResourceType as welcomePageType`
- `0x1afe7`: ` from AppModuleBase a LEFT JOIN AppModuleComponentBase b ON a.AppModuleIdUnique = b.AppModuleIdUnique`
- `0x1afff`: ` LEFT JOIN WebResourceBase w ON a.WelcomePageId = w.WebResourceId`
- `0x1b00b`: ` WHERE a.UniqueName = @uniqueName AND a.ComponentState = 0 AND a.OverwriteTime = 0`

## pseudocode

```c

```

## disassembly

```asm
0x1afb0  ldarg.1
0x1afb1  ldstr    aConnection// "connection"
0x1afb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1afbb  ldnull
0x1afbc  stloc.0
0x1afbd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1afc2  dup
0x1afc3  ldstr    aSelectAClientt// "SELECT a.ClientType, a.AppModuleId, a.N"...
0x1afc8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1afcd  pop
0x1afce  dup
0x1afcf  ldstr    aIWebresourceid// ", i.WebResourceId as iconWebresourceId,"...
0x1afd4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1afd9  pop
0x1afda  dup
0x1afdb  ldstr    aWWebresourceid// ", w.WebResourceId as welcomePageId, w.N"...
0x1afe0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1afe5  pop
0x1afe6  dup
0x1afe7  ldstr    aFromAppmoduleb// " from AppModuleBase a LEFT JOIN AppModu"...
0x1afec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aff1  pop
0x1aff2  dup
0x1aff3  ldstr    aLeftJoinWebres// " LEFT JOIN WebResourceBase i ON a.WebRe"...
0x1aff8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1affd  pop
0x1affe  dup
0x1afff  ldstr    aLeftJoinWebres_0// " LEFT JOIN WebResourceBase w ON a.Welco"...
0x1b004  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b009  pop
0x1b00a  dup
0x1b00b  ldstr    aWhereAUniquena// " WHERE a.UniqueName = @uniqueName AND a"...
0x1b010  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b015  pop
0x1b016  callvirt instance string [mscorlib]System.Object::ToString()
0x1b01b  stloc.1
0x1b01c  ldarg.1
0x1b01d  ldloc.1
0x1b01e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1b023  stloc.0
0x1b024  ldloc.0
0x1b025  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1b02a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1b02f  ldstr    aUniquename// "@uniqueName"
0x1b034  ldarg.0
0x1b035  ldarg.2
0x1b036  call     instance string Microsoft.Crm.Metadata.AppMetaDataLoaderByUName::GetAppUrl(string appModuleIdKey)
0x1b03b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1b040  pop
0x1b041  ldloc.0
0x1b042  stloc.2
0x1b043  leave.s  loc_1B051
0x1b045  pop
0x1b046  ldloc.0
0x1b047  brfalse.s loc_1B04F
0x1b049  ldloc.0
0x1b04a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b04f  rethrow
0x1b051  ldloc.2
0x1b052  ret
```
