# Microsoft.Crm.ObjectModel.PluginAssemblyServiceInternal`1::LoadCrmPluginAssemblyMetadata

- ea: `0x1390b0`
- end: `0x1393b2`
- name: `Microsoft.Crm.ObjectModel.PluginAssemblyServiceInternal`1::LoadCrmPluginAssemblyMetadata`
- size: `770`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1390b0`

## string_xrefs

- `0x139234`: `publickeytoken`
- `0x139241`: `publickeytoken`
- `0x1390c1`: `Crm plugin assembly info : `
- `0x139140`: `Cannot load plugin assembly: SourceTypeAttribute is not specified. PluginInfo => {0}`
- `0x139153`: `PluginInfo => {0}`
- `0x139336`: `PluginInfo => {0}`
- `0x1392d0`: `{0}, Version={1}, Culture={2}, PublicKeyToken={3}`
- `0x13931d`: `Cannot load plugin assembly: Unknown SourceType: {0}, PluginInfo => {1}`
- `0x13935f`: `Failed to load plugin assembly with exception {0}. PluginInfo => {1}`
- `0x13937b`: `Exception {0}, PluginInfo => {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1390b0  ldarg.1
0x1390b1  brtrue.s loc_1390BA
0x1390b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1390b8  br.s     loc_1390C0
0x1390ba  ldarg.1
0x1390bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1390c0  stloc.0
0x1390c1  ldstr    aCrmPluginAssem// "Crm plugin assembly info : "
0x1390c6  stloc.1
0x1390c7  ldarg.0
0x1390c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x1390cd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1390d2  stloc.s  4
0x1390d4  br.s     loc_139113
0x1390d6  ldloc.s  4
0x1390d8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1390dd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo
0x1390e2  stloc.s  5
0x1390e4  ldloc.1
0x1390e5  ldstr    a01_21// "{0} = {1}, "
0x1390ea  ldloc.s  5
0x1390ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Name()
0x1390f1  ldloc.s  5
0x1390f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1390f8  brtrue.s loc_139101
0x1390fa  ldstr    aNull_0// "NULL"
0x1390ff  br.s     loc_139108
0x139101  ldloc.s  5
0x139103  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x139108  call     string [mscorlib]System.String::Format(string, object, object)
0x13910d  call     string [mscorlib]System.String::Concat(string, string)
0x139112  stloc.1
0x139113  ldloc.s  4
0x139115  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13911a  brtrue.s loc_1390D6
0x13911c  leave.s  loc_139133
0x13911e  ldloc.s  4
0x139120  isinst   [mscorlib]System.IDisposable
0x139125  stloc.s  6
0x139127  ldloc.s  6
0x139129  brfalse.s loc_139132
0x13912b  ldloc.s  6
0x13912d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139132  endfinally
0x139133  ldarg.0
0x139134  ldstr    aSourcetype// "sourcetype"
0x139139  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x13913e  brfalse.s loc_139178
0x139140  ldstr    aCannotLoadPlug// "Cannot load plugin assembly: SourceType"...
0x139145  ldloc.1
0x139146  call     string [mscorlib]System.String::Format(string, object)
0x13914b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x139150  ldloc.0
0x139151  ldc.i4.s 0x1A
0x139153  ldstr    aPlugininfo0// "PluginInfo => {0}"
0x139158  ldc.i4.1
0x139159  newarr   [mscorlib]System.Object
0x13915e  dup
0x13915f  ldc.i4.0
0x139160  ldloc.1
0x139161  stelem.ref
0x139162  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139167  ldc.i4   0x80044191
0x13916c  ldc.i4.0
0x13916d  newarr   [mscorlib]System.Object
0x139172  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x139177  throw
0x139178  ldarg.0
0x139179  ldstr    aSourcetype// "sourcetype"
0x13917e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x139183  unbox.any [mscorlib]System.Int32
0x139188  stloc.2
0x139189  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor()
0x13918e  stloc.3
0x13918f  ldloc.2
0x139190  switch   loc_1391AA, loc_1391DE, loc_139233, loc_139314
0x1391a5  br       loc_13931D
0x1391aa  ldarg.0
0x1391ab  ldstr    aContent// "content"
0x1391b0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1391b5  brtrue.s loc_1391C9
0x1391b7  ldarg.0
0x1391b8  ldstr    aContent// "content"
0x1391bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1391c2  castclass [mscorlib]System.String
0x1391c7  br.s     loc_1391CE
0x1391c9  ldsfld   string [mscorlib]System.String::Empty
0x1391ce  stloc.s  7
0x1391d0  ldloc.3
0x1391d1  ldloc.s  7
0x1391d3  ldarg.2
0x1391d4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::LoadMetadataFromAssemblyContent(string, bool)
0x1391d9  br       loc_13935B
0x1391de  ldarg.0
0x1391df  ldstr    aPath// "path"
0x1391e4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1391e9  brtrue.s loc_1391FD
0x1391eb  ldarg.0
0x1391ec  ldstr    aPath// "path"
0x1391f1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1391f6  castclass [mscorlib]System.String
0x1391fb  br.s     loc_139202
0x1391fd  ldsfld   string [mscorlib]System.String::Empty
0x139202  stloc.s  8
0x139204  call     string [Microsoft.Crm]Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_AssemblyFolder()
0x139209  ldloc.s  8
0x13920b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x139210  stloc.s  9
0x139212  ldloc.1
0x139213  ldstr    aLocation0// "Location = {0}"
0x139218  ldloc.s  9
0x13921a  call     string [mscorlib]System.String::Format(string, object)
0x13921f  call     string [mscorlib]System.String::Concat(string, string)
0x139224  stloc.1
0x139225  ldloc.3
0x139226  ldloc.s  9
0x139228  ldarg.2
0x139229  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::LoadMetadataFromAssemblyFile(string, bool)
0x13922e  br       loc_13935B
0x139233  ldarg.0
0x139234  ldstr    aPublickeytoken// "publickeytoken"
0x139239  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x13923e  brtrue.s loc_139252
0x139240  ldarg.0
0x139241  ldstr    aPublickeytoken// "publickeytoken"
0x139246  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x13924b  castclass [mscorlib]System.String
0x139250  br.s     loc_139257
0x139252  ldsfld   string [mscorlib]System.String::Empty
0x139257  stloc.s  0xA
0x139259  ldarg.0
0x13925a  ldstr    aName// "name"
0x13925f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x139264  brtrue.s loc_139278
0x139266  ldarg.0
0x139267  ldstr    aName// "name"
0x13926c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x139271  castclass [mscorlib]System.String
0x139276  br.s     loc_13927D
0x139278  ldsfld   string [mscorlib]System.String::Empty
0x13927d  stloc.s  0xB
0x13927f  ldarg.0
0x139280  ldstr    aCulture// "culture"
0x139285  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x13928a  brtrue.s loc_13929E
0x13928c  ldarg.0
0x13928d  ldstr    aCulture// "culture"
0x139292  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x139297  castclass [mscorlib]System.String
0x13929c  br.s     loc_1392A3
0x13929e  ldsfld   string [mscorlib]System.String::Empty
0x1392a3  stloc.s  0xC
0x1392a5  ldarg.0
0x1392a6  ldstr    aVersion// "version"
0x1392ab  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1392b0  brtrue.s loc_1392C4
0x1392b2  ldarg.0
0x1392b3  ldstr    aVersion// "version"
0x1392b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1392bd  castclass [mscorlib]System.String
0x1392c2  br.s     loc_1392C9
0x1392c4  ldsfld   string [mscorlib]System.String::Empty
0x1392c9  stloc.s  0xD
0x1392cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1392d0  ldstr    a0Version1Cultu// "{0}, Version={1}, Culture={2}, PublicKe"...
0x1392d5  ldc.i4.4
0x1392d6  newarr   [mscorlib]System.Object
0x1392db  dup
0x1392dc  ldc.i4.0
0x1392dd  ldloc.s  0xB
0x1392df  stelem.ref
0x1392e0  dup
0x1392e1  ldc.i4.1
0x1392e2  ldloc.s  0xD
0x1392e4  stelem.ref
0x1392e5  dup
0x1392e6  ldc.i4.2
0x1392e7  ldloc.s  0xC
0x1392e9  stelem.ref
0x1392ea  dup
0x1392eb  ldc.i4.3
0x1392ec  ldloc.s  0xA
0x1392ee  stelem.ref
0x1392ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1392f4  stloc.s  0xE
0x1392f6  ldloc.1
0x1392f7  ldstr    aFullname0// "FullName = {0}"
0x1392fc  ldloc.s  0xE
0x1392fe  call     string [mscorlib]System.String::Format(string, object)
0x139303  call     string [mscorlib]System.String::Concat(string, string)
0x139308  stloc.1
0x139309  ldloc.3
0x13930a  ldloc.s  0xE
0x13930c  ldarg.2
0x13930d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::LoadMetadataFromAssemblyName(string, bool)
0x139312  br.s     loc_13935B
0x139314  ldarg.0
0x139315  call     class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata class Microsoft.Crm.ObjectModel.PluginAssemblyServiceInternal`1<var<u1>>::ValidateWebAndGenerateAssemblyMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x13931a  stloc.3
0x13931b  br.s     loc_13935B
0x13931d  ldstr    aCannotLoadPlug_0// "Cannot load plugin assembly: Unknown So"...
0x139322  ldloc.2
0x139323  box      [mscorlib]System.Int32
0x139328  ldloc.1
0x139329  call     string [mscorlib]System.String::Format(string, object, object)
0x13932e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x139333  ldloc.0
0x139334  ldc.i4.s 0x1A
0x139336  ldstr    aPlugininfo0// "PluginInfo => {0}"
0x13933b  ldc.i4.1
0x13933c  newarr   [mscorlib]System.Object
0x139341  dup
0x139342  ldc.i4.0
0x139343  ldloc.1
0x139344  stelem.ref
0x139345  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13934a  ldc.i4   0x80044191
0x13934f  ldc.i4.0
0x139350  newarr   [mscorlib]System.Object
0x139355  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x13935a  throw
0x13935b  leave.s  loc_1393AA
0x13935d  stloc.s  0xF
0x13935f  ldstr    aFailedToLoadPl// "Failed to load plugin assembly with exc"...
0x139364  ldloc.s  0xF
0x139366  callvirt instance string [mscorlib]System.Object::ToString()
0x13936b  ldloc.1
0x13936c  call     string [mscorlib]System.String::Format(string, object, object)
0x139371  ldloc.s  0xF
0x139373  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x139378  ldloc.0
0x139379  ldc.i4.s 0x1A
0x13937b  ldstr    aException0Plug// "Exception {0}, PluginInfo => {1}"
0x139380  ldc.i4.2
0x139381  newarr   [mscorlib]System.Object
0x139386  dup
0x139387  ldc.i4.0
0x139388  ldloc.s  0xF
0x13938a  callvirt instance string [mscorlib]System.Object::ToString()
0x13938f  stelem.ref
0x139390  dup
0x139391  ldc.i4.1
0x139392  ldloc.1
0x139393  stelem.ref
0x139394  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139399  ldc.i4   0x80044191
0x13939e  ldc.i4.0
0x13939f  newarr   [mscorlib]System.Object
0x1393a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1393a9  throw
0x1393aa  ldloc.3
0x1393ab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::OnlyPluginTypes()
0x1393b0  ldloc.3
0x1393b1  ret
```
