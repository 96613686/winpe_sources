# Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GetDocumentObjectsFromGraphQueryResult

- ea: `0x12f890`
- end: `0x12fb38`
- name: `Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GetDocumentObjectsFromGraphQueryResult`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x12ec60`

## callees

- `0x12f890`
- `0x12fb40`
- `0x12fce0`
- `0x12fda0`
- `0x12fde0`
- `0x12feb0`
- `0x12ff40`
- `0x12ff80`
- `0x12ffc0`
- `0x130020`
- `0x130060`
- `0x1300a0`
- `0x1300e0`
- `0x130120`
- `0x130180`

## string_xrefs

- `0x12f91c`: `File path not found for OfficeGraphDocument, hence ignoring. User: {0}, document-id: {1}`
- `0x12f97b`: `FILEEXTENSION`
- `0x12fa97`: `FILEEXTENSION`
- `0x12f99c`: `SECONDARYFILEEXTENSION`
- `0x12faa3`: `SECONDARYFILEEXTENSION`
- `0x12fabb`: `CREATED`
- `0x12fae7`: `Error in processing graph query Json result for OfficeGraphDocument. User: {0}, document-id: {1}, exception: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x12f890  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.IDocumentObject>::.ctor()
0x12f895  stloc.0
0x12f896  ldarg.0
0x12f897  call     bool Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GraphQueryJsonHasResults(class Microsoft.Crm.ObjectModel.GraphQueryJsonResult graphQueryJsonResult)
0x12f89c  brfalse  loc_12FB31
0x12f8a1  ldarg.0
0x12f8a2  callvirt instance class Microsoft.Crm.ObjectModel.QueryReultsContainer Microsoft.Crm.ObjectModel.GraphQueryJsonResult::get_d()
0x12f8a7  callvirt instance class Microsoft.Crm.ObjectModel.QueryReults Microsoft.Crm.ObjectModel.QueryReultsContainer::get_query()
0x12f8ac  callvirt instance class Microsoft.Crm.ObjectModel.PrimaryQueryResult Microsoft.Crm.ObjectModel.QueryReults::get_PrimaryQueryResult()
0x12f8b1  callvirt instance class Microsoft.Crm.ObjectModel.RelevantResults Microsoft.Crm.ObjectModel.PrimaryQueryResult::get_RelevantResults()
0x12f8b6  callvirt instance class Microsoft.Crm.ObjectModel.Table Microsoft.Crm.ObjectModel.RelevantResults::get_Table()
0x12f8bb  callvirt instance class Microsoft.Crm.ObjectModel.Rows Microsoft.Crm.ObjectModel.Table::get_Rows()
0x12f8c0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DocumentObject> Microsoft.Crm.ObjectModel.Rows::get_results()
0x12f8c5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DocumentObject>::GetEnumerator()
0x12f8ca  stloc.1
0x12f8cb  br       loc_12FB15
0x12f8d0  ldloca.s 1
0x12f8d2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.DocumentObject>::get_Current()
0x12f8d7  stloc.2
0x12f8d8  ldsfld   string [mscorlib]System.String::Empty
0x12f8dd  stloc.3
0x12f8de  ldloc.2
0x12f8df  callvirt instance class Microsoft.Crm.ObjectModel.Cells Microsoft.Crm.ObjectModel.DocumentObject::get_Cells()
0x12f8e4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.Cells::get_Properties()
0x12f8e9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GetDocumentPropertiesFromGraphQuery(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> documentPropertiesFromGraphQuery)
0x12f8ee  stloc.s  4
0x12f8f0  ldloc.s  4
0x12f8f2  ldstr    aDocid// "DOCID"
0x12f8f7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f8fc  stloc.3
0x12f8fd  ldloc.s  4
0x12f8ff  ldstr    aPath_0// "PATH"
0x12f904  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f909  stloc.s  5
0x12f90b  ldloc.s  5
0x12f90d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12f912  brfalse.s loc_12F943
0x12f914  ldarg.2
0x12f915  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12f91a  ldc.i4.s 0x11
0x12f91c  ldstr    aFilePathNotFou// "File path not found for OfficeGraphDocu"...
0x12f921  ldc.i4.2
0x12f922  newarr   [mscorlib]System.Object
0x12f927  dup
0x12f928  ldc.i4.0
0x12f929  ldarg.2
0x12f92a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x12f92f  box      [mscorlib]System.Guid
0x12f934  stelem.ref
0x12f935  dup
0x12f936  ldc.i4.1
0x12f937  ldloc.3
0x12f938  stelem.ref
0x12f939  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12f93e  leave    loc_12FB15
0x12f943  ldloc.s  5
0x12f945  ldc.i4.0
0x12f946  ldloc.s  5
0x12f948  ldc.i4.s 0x2F
0x12f94a  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x12f94f  ldc.i4.1
0x12f950  add
0x12f951  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x12f956  stloc.s  6
0x12f958  ldloc.s  4
0x12f95a  ldstr    aFiletype_1// "FILETYPE"
0x12f95f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f964  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f969  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x12f96e  stloc.s  7
0x12f970  ldloc.s  7
0x12f972  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12f977  brfalse.s loc_12F991
0x12f979  ldloc.s  4
0x12f97b  ldstr    aFileextension// "FILEEXTENSION"
0x12f980  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f985  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f98a  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x12f98f  stloc.s  7
0x12f991  ldloc.s  7
0x12f993  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12f998  brfalse.s loc_12F9B2
0x12f99a  ldloc.s  4
0x12f99c  ldstr    aSecondaryfilee// "SECONDARYFILEEXTENSION"
0x12f9a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f9a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12f9ab  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x12f9b0  stloc.s  7
0x12f9b2  ldloc.s  7
0x12f9b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12f9b9  brfalse.s loc_12F9EA
0x12f9bb  ldarg.2
0x12f9bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12f9c1  ldc.i4.s 0x11
0x12f9c3  ldstr    aFiletypeCouldn// "Filetype couldn't be determined for Off"...
0x12f9c8  ldc.i4.2
0x12f9c9  newarr   [mscorlib]System.Object
0x12f9ce  dup
0x12f9cf  ldc.i4.0
0x12f9d0  ldarg.2
0x12f9d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x12f9d6  box      [mscorlib]System.Guid
0x12f9db  stelem.ref
0x12f9dc  dup
0x12f9dd  ldc.i4.1
0x12f9de  ldloc.3
0x12f9df  stelem.ref
0x12f9e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12f9e5  leave    loc_12FB15
0x12f9ea  ldloc.0
0x12f9eb  ldloc.s  4
0x12f9ed  ldstr    aRank_0// "RANK"
0x12f9f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12f9f7  call     float64 [mscorlib]System.Convert::ToDouble(string)
0x12f9fc  ldloc.s  4
0x12f9fe  ldstr    aDocid// "DOCID"
0x12fa03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa08  ldarg.1
0x12fa09  ldloc.s  4
0x12fa0b  ldstr    aUniqueid_1// "UNIQUEID"
0x12fa10  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa15  ldloc.s  4
0x12fa17  ldstr    aSiteid// "SITEID"
0x12fa1c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa21  ldloc.s  4
0x12fa23  ldstr    aWebid// "WEBID"
0x12fa28  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa2d  ldloc.s  4
0x12fa2f  ldstr    aViewcountlifet// "VIEWCOUNTLIFETIME"
0x12fa34  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa39  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x12fa3e  ldloc.s  4
0x12fa40  ldstr    aTitle_1// "TITLE"
0x12fa45  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa4a  newobj   instance void Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::.ctor()
0x12fa4f  ldloc.s  6
0x12fa51  ldloc.s  4
0x12fa53  ldstr    aSitetitle_1// "SITETITLE"
0x12fa58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa5d  ldarg.2
0x12fa5e  call     instance string Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GenerateSiteTitle(string siteUrl, string siteTitle, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12fa63  ldloc.s  4
0x12fa65  ldstr    aServerredirect// "SERVERREDIRECTEDURL"
0x12fa6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa6f  ldloc.s  4
0x12fa71  ldstr    aSpweburl// "SPWEBURL"
0x12fa76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa7b  ldloc.s  4
0x12fa7d  ldstr    aPath_0// "PATH"
0x12fa82  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa87  ldloc.s  4
0x12fa89  ldstr    aLastmodifiedti// "LASTMODIFIEDTIME"
0x12fa8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fa93  ldloc.s  7
0x12fa95  ldloc.s  4
0x12fa97  ldstr    aFileextension// "FILEEXTENSION"
0x12fa9c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12faa1  ldloc.s  4
0x12faa3  ldstr    aSecondaryfilee// "SECONDARYFILEEXTENSION"
0x12faa8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12faad  ldloc.s  4
0x12faaf  ldstr    aAuthor_0// "AUTHOR"
0x12fab4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fab9  ldloc.s  4
0x12fabb  ldstr    aCreated// "CREATED"
0x12fac0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fac5  ldloc.s  4
0x12fac7  ldstr    aDocumentprevie// "DOCUMENTPREVIEWMETADATA"
0x12facc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12fad1  newobj   instance void Microsoft.Crm.ObjectModel.SharePointGraphQueryDocument::.ctor(float64 rank, string documentid, string sharepointSiteUrl, string DocumentUniqueId, string SiteID, string WebID, int32 viewcount, string title, string sitetitle, string readurl, string siteurl, string weblocationurl, string documentlastmodifiedon, string filetype, string fileExtension, string secondaryFileExtension, string authornames, string createdTime, string documentpreviewmetadata)
0x12fad6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.IDocumentObject>::Add(var<u1>)
0x12fadb  leave.s  loc_12FB15
0x12fadd  stloc.s  8
0x12fadf  ldarg.2
0x12fae0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12fae5  ldc.i4.s 0x11
0x12fae7  ldstr    aErrorInProcess_0// "Error in processing graph query Json re"...
0x12faec  ldc.i4.3
0x12faed  newarr   [mscorlib]System.Object
0x12faf2  dup
0x12faf3  ldc.i4.0
0x12faf4  ldarg.2
0x12faf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x12fafa  box      [mscorlib]System.Guid
0x12faff  stelem.ref
0x12fb00  dup
0x12fb01  ldc.i4.1
0x12fb02  ldloc.3
0x12fb03  stelem.ref
0x12fb04  dup
0x12fb05  ldc.i4.2
0x12fb06  ldloc.s  8
0x12fb08  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12fb0d  stelem.ref
0x12fb0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12fb13  leave.s  loc_12FB15
0x12fb15  ldloca.s 1
0x12fb17  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.DocumentObject>::MoveNext()
0x12fb1c  brtrue   loc_12F8D0
0x12fb21  leave.s  loc_12FB31
0x12fb23  ldloca.s 1
0x12fb25  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.ObjectModel.DocumentObject>
0x12fb2b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12fb30  endfinally
0x12fb31  ldloc.0
0x12fb32  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.IDocumentObject>::ToArray()
0x12fb37  ret
```
