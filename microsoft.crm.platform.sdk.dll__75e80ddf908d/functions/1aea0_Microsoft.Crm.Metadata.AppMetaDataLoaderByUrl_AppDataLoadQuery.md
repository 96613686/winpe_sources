# Microsoft.Crm.Metadata.AppMetaDataLoaderByUrl::AppDataLoadQuery

- ea: `0x1aea0`
- end: `0x1af43`
- name: `Microsoft.Crm.Metadata.AppMetaDataLoaderByUrl::AppDataLoadQuery`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1aea0`
- `0x1af50`

## string_xrefs

- `0x1aeb3`: `SELECT a.ClientType, a.AppModuleId, a.Name, a.FormFactor, a.AppModuleIdUnique, a.Url, a.UniqueName, b.AppModuleComponentId, b.ObjectId, b.ComponentType, b.AppModuleIdUnique`
- `0x1aecb`: `, w.WebResourceId as welcomePageId, w.Name as welcomePageName, w.DisplayName as welcomePageDisplayName, w.WebResourceType as welcomePageType`
- `0x1aed7`: ` from AppModuleBase a LEFT JOIN AppModuleComponentBase b ON a.AppModuleIdUnique = b.AppModuleIdUnique`
- `0x1aeef`: ` LEFT JOIN WebResourceBase w ON a.WelcomePageId = w.WebResourceId`
- `0x1aefb`: ` WHERE a.Url = @url AND a.ComponentState = 0 AND a.OverwriteTime = 0`

## pseudocode

```c

```

## disassembly

```asm
0x1aea0  ldarg.1
0x1aea1  ldstr    aConnection// "connection"
0x1aea6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1aeab  ldnull
0x1aeac  stloc.0
0x1aead  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1aeb2  dup
0x1aeb3  ldstr    aSelectAClientt// "SELECT a.ClientType, a.AppModuleId, a.N"...
0x1aeb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aebd  pop
0x1aebe  dup
0x1aebf  ldstr    aIWebresourceid// ", i.WebResourceId as iconWebresourceId,"...
0x1aec4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aec9  pop
0x1aeca  dup
0x1aecb  ldstr    aWWebresourceid// ", w.WebResourceId as welcomePageId, w.N"...
0x1aed0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aed5  pop
0x1aed6  dup
0x1aed7  ldstr    aFromAppmoduleb// " from AppModuleBase a LEFT JOIN AppModu"...
0x1aedc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aee1  pop
0x1aee2  dup
0x1aee3  ldstr    aLeftJoinWebres// " LEFT JOIN WebResourceBase i ON a.WebRe"...
0x1aee8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aeed  pop
0x1aeee  dup
0x1aeef  ldstr    aLeftJoinWebres_0// " LEFT JOIN WebResourceBase w ON a.Welco"...
0x1aef4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1aef9  pop
0x1aefa  dup
0x1aefb  ldstr    aWhereAUrlUrlAn// " WHERE a.Url = @url AND a.ComponentStat"...
0x1af00  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1af05  pop
0x1af06  callvirt instance string [mscorlib]System.Object::ToString()
0x1af0b  stloc.1
0x1af0c  ldarg.1
0x1af0d  ldloc.1
0x1af0e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1af13  stloc.0
0x1af14  ldloc.0
0x1af15  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1af1a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1af1f  ldstr    aUrl// "@url"
0x1af24  ldarg.0
0x1af25  ldarg.2
0x1af26  call     instance string Microsoft.Crm.Metadata.AppMetaDataLoaderByUrl::GetAppUrl(string appModuleIdKey)
0x1af2b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1af30  pop
0x1af31  ldloc.0
0x1af32  stloc.2
0x1af33  leave.s  loc_1AF41
0x1af35  pop
0x1af36  ldloc.0
0x1af37  brfalse.s loc_1AF3F
0x1af39  ldloc.0
0x1af3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1af3f  rethrow
0x1af41  ldloc.2
0x1af42  ret
```
