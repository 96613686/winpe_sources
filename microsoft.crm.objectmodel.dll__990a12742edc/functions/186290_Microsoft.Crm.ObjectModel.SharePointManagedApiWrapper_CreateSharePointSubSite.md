# Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::CreateSharePointSubSite

- ea: `0x186290`
- end: `0x186aaf`
- name: `Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::CreateSharePointSubSite`
- size: `2079`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x17c930`
- `0x182f80`
- `0x1839f0`
- `0x185ba0`
- `0x186290`
- `0x186ea0`
- `0x186eb0`

## string_xrefs

- `0x186428`: `template`
- `0x1864d5`: `SharePoint version not supported. Exception occured while accessing SharePoint: {0}`
- `0x186563`: `ServerException occured while accessing SharePoint: {0}`
- `0x18664d`: `Exception occured while accessing SharePoint: Sharepoint Request GUID {0} `
- `0x18667e`: `Exception occured while accessing SharePoint: {0} `
- `0x18695d`: `WebException occured while accessing SharePoint. Web status code returned: {0}. Web exception: {1}`
- `0x1869c4`: `Unknown exception occured while accessing SharePoint: {0}`
- `0x186377`: `<exception>Faild to create sub site {0}, under site {1}. {2}</exception>`

## pseudocode

```c

```

## disassembly

```asm
0x186290  ldarg.2
0x186291  newarr   [mscorlib]System.Boolean
0x186296  stloc.0
0x186297  ldarg.3
0x186298  ldsfld   string [mscorlib]System.String::Empty
0x18629d  stind.ref
0x18629e  ldarg.3
0x18629f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1862a4  ldstr    aSites// "<sites>"
0x1862a9  ldc.i4.0
0x1862aa  newarr   [mscorlib]System.Object
0x1862af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1862b4  stind.ref
0x1862b5  ldc.i4.0
0x1862b6  stloc.1
0x1862b7  ldarg.1
0x1862b8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Keys()
0x1862bd  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [mscorlib]System.Collections.ArrayList>::GetEnumerator()
0x1862c2  stloc.3
0x1862c3  br       loc_186A62
0x1862c8  ldloca.s 3
0x1862ca  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [mscorlib]System.Collections.ArrayList>::get_Current()
0x1862cf  stloc.s  4
0x1862d1  ldarg.3
0x1862d2  ldarg.3
0x1862d3  ldind.ref
0x1862d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1862d9  ldstr    aSite// "<site>"
0x1862de  ldc.i4.0
0x1862df  newarr   [mscorlib]System.Object
0x1862e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1862e9  call     string [mscorlib]System.String::Concat(string, string)
0x1862ee  stind.ref
0x1862ef  ldarg.3
0x1862f0  ldarg.3
0x1862f1  ldind.ref
0x1862f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1862f7  ldstr    aUrl0Url// "<url>{0}</url>"
0x1862fc  ldc.i4.1
0x1862fd  newarr   [mscorlib]System.Object
0x186302  dup
0x186303  ldc.i4.0
0x186304  ldloc.s  4
0x186306  stelem.ref
0x186307  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18630c  call     string [mscorlib]System.String::Concat(string, string)
0x186311  stind.ref
0x186312  ldloc.s  4
0x186314  newobj   instance void [System]System.Uri::.ctor(string)
0x186319  callvirt instance string [System]System.Uri::get_Scheme()
0x18631e  ldsfld   string [System]System.Uri::UriSchemeHttps
0x186323  ldc.i4.3
0x186324  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x186329  brtrue   loc_1863EA
0x18632e  ldstr    aAllowhttpshare// "AllowHTTPSharePointSites"
0x186333  ldc.i4.0
0x186334  box      [mscorlib]System.Int32
0x186339  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x18633e  call     bool [mscorlib]System.Convert::ToBoolean(object)
0x186343  brtrue   loc_1863EA
0x186348  ldarg.1
0x186349  ldloc.s  4
0x18634b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Item(void)
0x186350  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x186355  stloc.s  5
0x186357  br.s     loc_1863C7
0x186359  ldloc.s  5
0x18635b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x186360  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x186365  stloc.s  6
0x186367  ldloc.0
0x186368  ldloc.1
0x186369  dup
0x18636a  ldc.i4.1
0x18636b  add
0x18636c  stloc.1
0x18636d  ldc.i4.0
0x18636e  stelem.i1
0x18636f  ldarg.3
0x186370  ldarg.3
0x186371  ldind.ref
0x186372  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x186377  ldstr    aExceptionFaild// "<exception>Faild to create sub site {0}"...
0x18637c  ldc.i4.3
0x18637d  newarr   [mscorlib]System.Object
0x186382  dup
0x186383  ldc.i4.0
0x186384  ldloc.s  6
0x186386  ldstr    aTitle_0// "title"
0x18638b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x186390  stelem.ref
0x186391  dup
0x186392  ldc.i4.1
0x186393  ldloc.s  4
0x186395  stelem.ref
0x186396  dup
0x186397  ldc.i4.2
0x186398  ldstr    aServerBasedInt// "Server-based integration is only suppor"...
0x18639d  stelem.ref
0x18639e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1863a3  call     string [mscorlib]System.String::Concat(string, string)
0x1863a8  stind.ref
0x1863a9  ldarg.3
0x1863aa  ldarg.3
0x1863ab  ldind.ref
0x1863ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1863b1  ldstr    aSite_0// "</site>"
0x1863b6  ldc.i4.0
0x1863b7  newarr   [mscorlib]System.Object
0x1863bc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1863c1  call     string [mscorlib]System.String::Concat(string, string)
0x1863c6  stind.ref
0x1863c7  ldloc.s  5
0x1863c9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1863ce  brtrue.s loc_186359
0x1863d0  leave    loc_186A62
0x1863d5  ldloc.s  5
0x1863d7  isinst   [mscorlib]System.IDisposable
0x1863dc  stloc.s  7
0x1863de  ldloc.s  7
0x1863e0  brfalse.s loc_1863E9
0x1863e2  ldloc.s  7
0x1863e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1863e9  endfinally
0x1863ea  ldarg.0
0x1863eb  ldloc.s  4
0x1863ed  newobj   instance void [System]System.Uri::.ctor(string)
0x1863f2  ldc.i4.1
0x1863f3  call     instance void Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::SetClientContext(class [System]System.Uri sharePointSite, [opt] bool addClaims)
0x1863f8  ldarg.1
0x1863f9  ldloc.s  4
0x1863fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Item(void)
0x186400  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x186405  stloc.s  5
0x186407  br       loc_186A3F
0x18640c  ldloc.s  5
0x18640e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x186413  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x186418  stloc.s  8
0x18641a  ldc.i4.0
0x18641b  stloc.s  9
0x18641d  newobj   instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::.ctor()
0x186422  stloc.s  0xA
0x186424  ldloc.s  0xA
0x186426  ldloc.s  8
0x186428  ldstr    aTemplate// "template"
0x18642d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x186432  callvirt instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::set_WebTemplate(string)
0x186437  ldloc.s  0xA
0x186439  ldloc.s  8
0x18643b  ldstr    aDescription// "description"
0x186440  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x186445  callvirt instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::set_Description(string)
0x18644a  ldloc.s  0xA
0x18644c  ldloc.s  8
0x18644e  ldstr    aTitle_0// "title"
0x186453  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x186458  callvirt instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::set_Title(string)
0x18645d  ldloc.s  0xA
0x18645f  ldloc.s  8
0x186461  ldstr    aSubsite// "subsite"
0x186466  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x18646b  callvirt instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::set_Url(string)
0x186470  ldloc.s  0xA
0x186472  ldc.i4   0x409
0x186477  callvirt instance void [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation::set_Language(int32)
0x18647c  ldarg.0
0x18647d  ldfld    class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.ClientContext Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::_clientContext
0x186482  callvirt instance class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.Web [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.ClientContext::get_Web()
0x186487  callvirt instance class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCollection [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.Web::get_Webs()
0x18648c  ldloc.s  0xA
0x18648e  callvirt instance class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.Web [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCollection::Add(class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.WebCreationInformation)
0x186493  pop
0x186494  ldarg.0
0x186495  ldarg.0
0x186496  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::userContext
0x18649b  call     instance void Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::UpdateSemaphores(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1864a0  ldarg.0
0x1864a1  ldc.i4.4
0x1864a2  call     instance void Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::SharePointAsyncExecute(valuetype Microsoft.Crm.ObjectModel.CSOMCallType callType)
0x1864a7  ldloc.0
0x1864a8  ldloc.1
0x1864a9  dup
0x1864aa  ldc.i4.1
0x1864ab  add
0x1864ac  stloc.1
0x1864ad  ldc.i4.1
0x1864ae  stelem.i1
0x1864af  leave    loc_186A21
0x1864b4  stloc.s  0xB
0x1864b6  ldloc.s  0xB
0x1864b8  callvirt instance int32 [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException::get_ServerErrorCode()
0x1864bd  ldc.i4.m1
0x1864be  bne.un   loc_186559
0x1864c3  ldloc.0
0x1864c4  ldloc.1
0x1864c5  dup
0x1864c6  ldc.i4.1
0x1864c7  add
0x1864c8  stloc.1
0x1864c9  ldc.i4.0
0x1864ca  stelem.i1
0x1864cb  ldloc.s  0xB
0x1864cd  ldarg.0
0x1864ce  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::_organisationId
0x1864d3  ldc.i4.s 0x11
0x1864d5  ldstr    aSharepointVers// "SharePoint version not supported. Excep"...
0x1864da  ldc.i4.1
0x1864db  newarr   [mscorlib]System.Object
0x1864e0  dup
0x1864e1  ldc.i4.0
0x1864e2  ldloc.s  0xB
0x1864e4  call     string Microsoft.Crm.ObjectModel.SharePointErrorHandler::GetSPErrorDetails(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x1864e9  ldloc.s  0xB
0x1864eb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1864f0  call     string [mscorlib]System.String::Concat(string, string)
0x1864f5  stelem.ref
0x1864f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1864fb  ldloc.s  0xB
0x1864fd  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x186502  brtrue.s loc_18650D
0x186504  ldloc.s  0xB
0x186506  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18650b  br.s     loc_186525
0x18650d  ldloc.s  0xB
0x18650f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x186514  ldloc.s  0xB
0x186516  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x18651b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x186520  call     string [mscorlib]System.String::Concat(string, string)
0x186525  stloc.s  0xC
0x186527  ldarg.3
0x186528  ldarg.3
0x186529  ldind.ref
0x18652a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18652f  ldstr    aException0Exce// "<exception>{0}</exception><errorcode>{1"...
0x186534  ldc.i4.2
0x186535  newarr   [mscorlib]System.Object
0x18653a  dup
0x18653b  ldc.i4.0
0x18653c  ldloc.s  0xC
0x18653e  stelem.ref
0x18653f  dup
0x186540  ldc.i4.1
0x186541  ldc.i4   0x800608B6
0x186546  box      [mscorlib]System.Int32
0x18654b  stelem.ref
0x18654c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x186551  call     string [mscorlib]System.String::Concat(string, string)
0x186556  stind.ref
0x186557  br.s     loc_1865B9
0x186559  ldloc.s  0xB
0x18655b  ldarg.0
0x18655c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.SharePointManagedApiWrapper::_organisationId
0x186561  ldc.i4.s 0x11
0x186563  ldstr    aServerexceptio// "ServerException occured while accessing"...
0x186568  ldc.i4.1
0x186569  newarr   [mscorlib]System.Object
0x18656e  dup
0x18656f  ldc.i4.0
0x186570  ldloc.s  0xB
0x186572  call     string Microsoft.Crm.ObjectModel.SharePointErrorHandler::GetSPErrorDetails(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x186577  ldloc.s  0xB
0x186579  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x18657e  call     string [mscorlib]System.String::Concat(string, string)
0x186583  stelem.ref
0x186584  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x186589  ldloc.0
0x18658a  ldloc.1
0x18658b  dup
0x18658c  ldc.i4.1
0x18658d  add
0x18658e  stloc.1
0x18658f  ldc.i4.0
0x186590  stelem.i1
0x186591  ldarg.3
0x186592  ldarg.3
0x186593  ldind.ref
0x186594  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x186599  ldstr    aException0Exce_0// "<exception>{0}</exception>"
0x18659e  ldc.i4.1
0x18659f  newarr   [mscorlib]System.Object
0x1865a4  dup
0x1865a5  ldc.i4.0
0x1865a6  ldloc.s  0xB
0x1865a8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1865ad  stelem.ref
0x1865ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1865b3  call     string [mscorlib]System.String::Concat(string, string)
0x1865b8  stind.ref
0x1865b9  leave    loc_186A21
0x1865be  stloc.s  0xD
0x1865c0  ldloc.0
0x1865c1  ldloc.1
0x1865c2  dup
0x1865c3  ldc.i4.1
0x1865c4  add
0x1865c5  stloc.1
0x1865c6  ldc.i4.0
0x1865c7  stelem.i1
  ... truncated ...
```
