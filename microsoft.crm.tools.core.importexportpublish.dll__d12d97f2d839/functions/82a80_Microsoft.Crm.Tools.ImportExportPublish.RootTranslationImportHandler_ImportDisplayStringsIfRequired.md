# Microsoft.Crm.Tools.ImportExportPublish.RootTranslationImportHandler::ImportDisplayStringsIfRequired

- ea: `0x82a80`
- end: `0x82dca`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootTranslationImportHandler::ImportDisplayStringsIfRequired`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x829c0`

## callees

- `0x63df0`
- `0x809c0`
- `0x809e0`
- `0x80a30`
- `0x80a50`
- `0x82a80`
- `0x82dd0`
- `0x8b320`
- `0x8ba70`
- `0x8c1f0`

## string_xrefs

- `0x82a9c`: `Translations xml is invalid. No row found in worksheet {0}.`
- `0x82b33`: `Translations xml is invalid. Number of cells inr row {0} do not match the number of cells in row 1 in worksheet {1}.`
- `0x82b96`: `Translations xml is invalid. DisplayStringKey in row number {0} in worksheet {1} is non-customizable.`
- `0x82c30`: `Translations xml is invalid. The file contains NULL Value for base language display string in row number {0} in worksheet {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x82a80  ldarg.1
0x82a81  ldstr    aDisplayStrings// "Display Strings"
0x82a86  ldc.i4.0
0x82a87  ldc.i4.0
0x82a88  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::ReadRowNodes(class [System.Xml]System.Xml.XmlDocument xdoc, string worksheetName, [opt] int32 pageSize, [opt] int32 startRow)
0x82a8d  stloc.0
0x82a8e  ldloc.0
0x82a8f  brtrue.s loc_82ADB
0x82a91  ldarg.0
0x82a92  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x82a97  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82a9c  ldstr    aTranslationsXm_1// "Translations xml is invalid. No row fou"...
0x82aa1  ldc.i4.1
0x82aa2  newarr   [mscorlib]System.Object
0x82aa7  dup
0x82aa8  ldc.i4.0
0x82aa9  ldstr    aDisplayStrings// "Display Strings"
0x82aae  stelem.ref
0x82aaf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82ab4  ldc.i4   0x80044249
0x82ab9  ldc.i4.0
0x82aba  newarr   [mscorlib]System.Object
0x82abf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82ac4  ldc.i4.1
0x82ac5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x82aca  ldc.i4   0x80044249
0x82acf  ldc.i4.0
0x82ad0  newarr   [mscorlib]System.Object
0x82ad5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82ada  throw
0x82adb  ldarg.0
0x82adc  ldstr    aDisplayStrings// "Display Strings"
0x82ae1  call     instance void Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::set_ErrorOnSheet(string value)
0x82ae6  ldc.i4.0
0x82ae7  stloc.1
0x82ae8  ldloc.0
0x82ae9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x82aee  stloc.2
0x82aef  br       loc_82D9E
0x82af4  ldloc.2
0x82af5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x82afa  castclass [System.Xml]System.Xml.XmlNode
0x82aff  stloc.3
0x82b00  ldloc.1
0x82b01  ldc.i4.1
0x82b02  add
0x82b03  stloc.1
0x82b04  ldc.i4.1
0x82b05  ldloc.1
0x82b06  beq      loc_82D9E
0x82b0b  ldarg.0
0x82b0c  ldloc.1
0x82b0d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::set_ErrorOnRow(int32 value)
0x82b12  ldloc.3
0x82b13  call     string[] Microsoft.Crm.Tools.ImportExportPublish.TranslationsHelper::GetCellValuesFromRow(class [System.Xml]System.Xml.XmlNode row)
0x82b18  stloc.s  4
0x82b1a  ldloc.s  4
0x82b1c  ldlen
0x82b1d  conv.i4
0x82b1e  ldarg.3
0x82b1f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Count()
0x82b24  ldc.i4.2
0x82b25  add
0x82b26  beq.s    loc_82B7B
0x82b28  ldarg.0
0x82b29  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x82b2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82b33  ldstr    aTranslationsXm_8// "Translations xml is invalid. Number of "...
0x82b38  ldc.i4.2
0x82b39  newarr   [mscorlib]System.Object
0x82b3e  dup
0x82b3f  ldc.i4.0
0x82b40  ldloc.1
0x82b41  box      [mscorlib]System.Int32
0x82b46  stelem.ref
0x82b47  dup
0x82b48  ldc.i4.1
0x82b49  ldstr    aDisplayStrings// "Display Strings"
0x82b4e  stelem.ref
0x82b4f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82b54  ldc.i4   0x80044249
0x82b59  ldc.i4.0
0x82b5a  newarr   [mscorlib]System.Object
0x82b5f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82b64  ldc.i4.1
0x82b65  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x82b6a  ldc.i4   0x80044249
0x82b6f  ldc.i4.0
0x82b70  newarr   [mscorlib]System.Object
0x82b75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82b7a  throw
0x82b7b  ldloc.s  4
0x82b7d  ldc.i4.1
0x82b7e  ldelem.ref
0x82b7f  stloc.s  5
0x82b81  ldarg.2
0x82b82  ldloc.s  5
0x82b84  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Tools.ImportExportPublish.DisplayStringInfo>::ContainsKey(var<u1>)
0x82b89  brtrue.s loc_82BF8
0x82b8b  ldarg.0
0x82b8c  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x82b91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82b96  ldstr    aTranslationsXm_9// "Translations xml is invalid. DisplayStr"...
0x82b9b  ldc.i4.2
0x82b9c  newarr   [mscorlib]System.Object
0x82ba1  dup
0x82ba2  ldc.i4.0
0x82ba3  ldloc.1
0x82ba4  box      [mscorlib]System.Int32
0x82ba9  stelem.ref
0x82baa  dup
0x82bab  ldc.i4.1
0x82bac  ldstr    aDisplayStrings// "Display Strings"
0x82bb1  stelem.ref
0x82bb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82bb7  ldc.i4   0x80044249
0x82bbc  ldc.i4.0
0x82bbd  newarr   [mscorlib]System.Object
0x82bc2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82bc7  ldc.i4.1
0x82bc8  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x82bcd  ldc.i4   0x80044247
0x82bd2  ldc.i4.3
0x82bd3  newarr   [mscorlib]System.Object
0x82bd8  dup
0x82bd9  ldc.i4.0
0x82bda  ldstr    aDisplayStrings// "Display Strings"
0x82bdf  stelem.ref
0x82be0  dup
0x82be1  ldc.i4.1
0x82be2  ldloc.1
0x82be3  box      [mscorlib]System.Int32
0x82be8  stelem.ref
0x82be9  dup
0x82bea  ldc.i4.2
0x82beb  ldc.i4.1
0x82bec  box      [mscorlib]System.Int32
0x82bf1  stelem.ref
0x82bf2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82bf7  throw
0x82bf8  ldc.i4.2
0x82bf9  stloc.s  6
0x82bfb  br       loc_82D93
0x82c00  ldarg.3
0x82c01  ldloc.s  6
0x82c03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x82c08  stloc.s  7
0x82c0a  ldloc.s  7
0x82c0c  ldarg.0
0x82c0d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Cache()
0x82c12  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x82c17  bne.un.s loc_82C95
0x82c19  ldloc.s  4
0x82c1b  ldloc.s  6
0x82c1d  ldelem.ref
0x82c1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x82c23  brfalse.s loc_82C95
0x82c25  ldarg.0
0x82c26  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.TranslationImportHandlerBase::get_Tracer()
0x82c2b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82c30  ldstr    aTranslationsXm_10// "Translations xml is invalid. The file c"...
0x82c35  ldc.i4.2
0x82c36  newarr   [mscorlib]System.Object
0x82c3b  dup
0x82c3c  ldc.i4.0
0x82c3d  ldloc.1
0x82c3e  box      [mscorlib]System.Int32
0x82c43  stelem.ref
0x82c44  dup
0x82c45  ldc.i4.1
0x82c46  ldstr    aDisplayStrings// "Display Strings"
0x82c4b  stelem.ref
0x82c4c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82c51  ldc.i4   0x80044249
0x82c56  ldc.i4.0
0x82c57  newarr   [mscorlib]System.Object
0x82c5c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82c61  ldc.i4.1
0x82c62  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x82c67  ldc.i4   0x80044246
0x82c6c  ldc.i4.3
0x82c6d  newarr   [mscorlib]System.Object
0x82c72  dup
0x82c73  ldc.i4.0
0x82c74  ldstr    aDisplayStrings// "Display Strings"
0x82c79  stelem.ref
0x82c7a  dup
0x82c7b  ldc.i4.1
0x82c7c  ldloc.1
0x82c7d  box      [mscorlib]System.Int32
0x82c82  stelem.ref
0x82c83  dup
0x82c84  ldc.i4.2
0x82c85  ldloc.s  6
0x82c87  ldc.i4.1
0x82c88  add
0x82c89  box      [mscorlib]System.Int32
0x82c8e  stelem.ref
0x82c8f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x82c94  throw
0x82c95  ldarg.s  5
0x82c97  ldloc.s  7
0x82c99  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::Contains(var<u1>)
0x82c9e  brtrue.s loc_82CA9
0x82ca0  ldloc.s  7
0x82ca2  ldarg.s  4
0x82ca4  bne.un   loc_82D8D
0x82ca9  ldsfld   string [mscorlib]System.String::Empty
0x82cae  stloc.s  8
0x82cb0  ldarg.2
0x82cb1  ldloc.s  5
0x82cb3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Tools.ImportExportPublish.DisplayStringInfo>::get_Item(void)
0x82cb8  stloc.s  0xB
0x82cba  ldloca.s 0xB
0x82cbc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Tools.ImportExportPublish.DisplayStringInfo::get_Label()
0x82cc1  ldloc.s  7
0x82cc3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0x82cc8  brfalse.s loc_82CE4
0x82cca  ldarg.2
0x82ccb  ldloc.s  5
0x82ccd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Tools.ImportExportPublish.DisplayStringInfo>::get_Item(void)
0x82cd2  stloc.s  0xB
0x82cd4  ldloca.s 0xB
0x82cd6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Tools.ImportExportPublish.DisplayStringInfo::get_Label()
0x82cdb  ldloc.s  7
0x82cdd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x82ce2  stloc.s  8
0x82ce4  ldsfld   string [mscorlib]System.String::Empty
0x82ce9  stloc.s  9
0x82ceb  ldloc.s  8
0x82ced  brfalse.s loc_82D28
0x82cef  ldloc.s  8
0x82cf1  ldstr    asc_10963A// "\r"
0x82cf6  ldstr    asc_9A18C// ""
0x82cfb  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d00  stloc.s  9
0x82d02  ldloc.s  9
0x82d04  ldstr    asc_9B37C// "\n"
0x82d09  ldstr    asc_9A18C// ""
0x82d0e  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d13  stloc.s  9
0x82d15  ldloc.s  9
0x82d17  ldstr    asc_10963E// "\t"
0x82d1c  ldstr    asc_9A18C// ""
0x82d21  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d26  stloc.s  9
0x82d28  ldsfld   string [mscorlib]System.String::Empty
0x82d2d  stloc.s  0xA
0x82d2f  ldloc.s  4
0x82d31  ldloc.s  6
0x82d33  ldelem.ref
0x82d34  brfalse.s loc_82D72
0x82d36  ldloc.s  4
0x82d38  ldloc.s  6
0x82d3a  ldelem.ref
0x82d3b  ldstr    asc_10963A// "\r"
0x82d40  ldstr    asc_9A18C// ""
0x82d45  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d4a  stloc.s  0xA
0x82d4c  ldloc.s  0xA
0x82d4e  ldstr    asc_9B37C// "\n"
0x82d53  ldstr    asc_9A18C// ""
0x82d58  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d5d  stloc.s  0xA
0x82d5f  ldloc.s  0xA
0x82d61  ldstr    asc_10963E// "\t"
0x82d66  ldstr    asc_9A18C// ""
0x82d6b  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x82d70  stloc.s  0xA
0x82d72  ldloc.s  9
0x82d74  ldloc.s  0xA
0x82d76  ldc.i4.4
0x82d77  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x82d7c  brfalse.s loc_82D8D
0x82d7e  ldarg.0
0x82d7f  ldloc.s  5
0x82d81  ldloc.s  4
0x82d83  ldloc.s  6
0x82d85  ldelem.ref
0x82d86  ldloc.s  7
0x82d88  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootTranslationImportHandler::UpdateDisplayString(string displayStringKey, string displayStringValue, int32 languageCode)
0x82d8d  ldloc.s  6
0x82d8f  ldc.i4.1
0x82d90  add
0x82d91  stloc.s  6
0x82d93  ldloc.s  6
0x82d95  ldloc.s  4
0x82d97  ldlen
0x82d98  conv.i4
0x82d99  blt      loc_82C00
0x82d9e  ldloc.2
0x82d9f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x82da4  brtrue   loc_82AF4
0x82da9  leave.s  loc_82DC9
0x82dab  ldloc.2
0x82dac  isinst   [mscorlib]System.IDisposable
0x82db1  stloc.s  0xC
0x82db3  ldloc.s  0xC
0x82db5  brfalse.s loc_82DBE
0x82db7  ldloc.s  0xC
  ... truncated ...
```
