# Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadMetadataForMetadataAsStringFromDirectory

- ea: `0x76820`
- end: `0x769be`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadMetadataForMetadataAsStringFromDirectory`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x76800`

## callees

- `0x76820`

## string_xrefs

- `0x76821`: `metadataForMetadataXmlDirectory`
- `0x76838`: `The directory for Metadata for Metadata xml files does not exist at this location '{0}'.`
- `0x7685e`: `*.xml`
- `0x768de`: `The following Metadata for Metadata xml files should exist at this location '{0}' but they are not there: {1}.`
- `0x76909`: `The following xml files should NOT exist at this location for the Metadata for Metadata xml file'{0}', so they are ignored: {1}.`
- `0x76939`: `There are no valid Metadata for Metadata xml files at this location '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x76820  ldarg.0
0x76821  ldstr    aMetadataformet// "metadataForMetadataXmlDirectory"
0x76826  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7682b  ldarg.0
0x7682c  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x76831  brtrue.s loc_76852
0x76833  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76838  ldstr    aTheDirectoryFo// "The directory for Metadata for Metadata"...
0x7683d  ldc.i4.1
0x7683e  newarr   [mscorlib]System.Object
0x76843  dup
0x76844  ldc.i4.0
0x76845  ldarg.0
0x76846  stelem.ref
0x76847  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7684c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x76851  throw
0x76852  ldstr    aEntities_1// "<Entities>"
0x76857  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x7685c  stloc.0
0x7685d  ldarg.0
0x7685e  ldstr    aXml// "*.xml"
0x76863  call     string[] [mscorlib]System.IO.Directory::GetFiles(string, string)
0x76868  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0x7686d  dup
0x7686e  brtrue.s loc_76887
0x76870  pop
0x76871  ldsfld   class <>c <>c::<>9
0x76876  ldftn    instance string <>c::<LoadMetadataForMetadataAsStringFromDirectory>b__2_0(string t)
0x7687c  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x76881  dup
0x76882  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0x76887  call     T0x2B000007
0x7688c  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x76891  stloc.1
0x76892  ldloc.1
0x76893  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::MetadataForMetadataXmlFiles
0x76898  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x7689d  call     T0x2B0000B9
0x768a2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x768a7  stloc.2
0x768a8  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::MetadataForMetadataXmlFiles
0x768ad  ldloc.1
0x768ae  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x768b3  call     T0x2B0000B9
0x768b8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x768bd  stloc.3
0x768be  ldloc.1
0x768bf  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::MetadataForMetadataXmlFiles
0x768c4  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x768c9  call     T0x2B0000BA
0x768ce  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x768d3  stloc.s  4
0x768d5  ldc.i4.0
0x768d6  ldloc.3
0x768d7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x768dc  bge.s    loc_76900
0x768de  ldstr    aTheFollowingMe// "The following Metadata for Metadata xml"...
0x768e3  ldc.i4.2
0x768e4  newarr   [mscorlib]System.Object
0x768e9  dup
0x768ea  ldc.i4.0
0x768eb  ldarg.0
0x768ec  stelem.ref
0x768ed  dup
0x768ee  ldc.i4.1
0x768ef  ldstr    asc_B68D2// ", "
0x768f4  ldloc.3
0x768f5  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x768fa  stelem.ref
0x768fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x76900  ldc.i4.0
0x76901  ldloc.2
0x76902  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x76907  bge.s    loc_7692B
0x76909  ldstr    aTheFollowingXm// "The following xml files should NOT exis"...
0x7690e  ldc.i4.2
0x7690f  newarr   [mscorlib]System.Object
0x76914  dup
0x76915  ldc.i4.0
0x76916  ldarg.0
0x76917  stelem.ref
0x76918  dup
0x76919  ldc.i4.1
0x7691a  ldstr    asc_B68D2// ", "
0x7691f  ldloc.2
0x76920  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x76925  stelem.ref
0x76926  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x7692b  ldloc.s  4
0x7692d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x76932  brtrue.s loc_76953
0x76934  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76939  ldstr    aThereAreNoVali// "There are no valid Metadata for Metadat"...
0x7693e  ldc.i4.1
0x7693f  newarr   [mscorlib]System.Object
0x76944  dup
0x76945  ldc.i4.0
0x76946  ldarg.0
0x76947  stelem.ref
0x76948  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7694d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x76952  throw
0x76953  ldloc.s  4
0x76955  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x7695a  stloc.s  5
0x7695c  br.s     loc_76992
0x7695e  ldloca.s 5
0x76960  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x76965  stloc.s  6
0x76967  ldarg.0
0x76968  ldloc.s  6
0x7696a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7696f  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0x76974  stloc.s  7
0x76976  ldloc.0
0x76977  ldloc.s  7
0x76979  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x7697e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x76983  pop
0x76984  leave.s  loc_76992
0x76986  ldloc.s  7
0x76988  brfalse.s loc_76991
0x7698a  ldloc.s  7
0x7698c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76991  endfinally
0x76992  ldloca.s 5
0x76994  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x76999  brtrue.s loc_7695E
0x7699b  leave.s  loc_769AB
0x7699d  ldloca.s 5
0x7699f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x769a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x769aa  endfinally
0x769ab  ldloc.0
0x769ac  ldstr    aEntities_2// "</Entities>"
0x769b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x769b6  pop
0x769b7  ldloc.0
0x769b8  callvirt instance string [mscorlib]System.Object::ToString()
0x769bd  ret
```
