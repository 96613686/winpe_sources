# Microsoft.Crm.Tools.Admin.OrganizationManifestService::GetOrganizationIdFromManifest

- ea: `0xbb10`
- end: `0xbcb6`
- name: `Microsoft.Crm.Tools.Admin.OrganizationManifestService::GetOrganizationIdFromManifest`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbb10`
- `0xbcc0`

## string_xrefs

- `0xbb17`: `manifestPath`
- `0xbb39`: `Manifest file '{0}' could not be located.`
- `0xbb77`: `OrganizationManifest/TableRows/Organization/Id`
- `0xbbe7`: `OrganizationManifest/TableRows/Organization/Id`
- `0xbb99`: `OrganizationManifest/TableRows/Organization/UniqueName`
- `0xbc22`: `OrganizationManifest/TableRows/Organization/UniqueName`
- `0xbbda`: `'{0}' element is not present in the Manifest file '{1}'.`
- `0xbc15`: `'{0}' element is not present in the Manifest file '{1}'.`
- `0xbc51`: `'{0}' Organization is not present in the Manifest file '{1}'.`
- `0xbc8a`: `Invalid OrganizationId '{0}' present in the Manifest file '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0xbb10  ldsfld   string [mscorlib]System.String::Empty
0xbb15  pop
0xbb16  ldarg.1
0xbb17  ldstr    aManifestpath// "manifestPath"
0xbb1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xbb21  ldarg.2
0xbb22  ldstr    aOrguniquename// "orgUniqueName"
0xbb27  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xbb2c  ldarg.1
0xbb2d  call     bool [mscorlib]System.IO.File::Exists(string)
0xbb32  brtrue.s loc_BB5F
0xbb34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb39  ldstr    aManifestFile0C// "Manifest file '{0}' could not be locate"...
0xbb3e  ldc.i4.1
0xbb3f  newarr   [mscorlib]System.Object
0xbb44  dup
0xbb45  ldc.i4.0
0xbb46  ldarg.1
0xbb47  stelem.ref
0xbb48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbb4d  dup
0xbb4e  ldc.i4.3
0xbb4f  call     void Microsoft.Crm.Tools.Admin.OrganizationManifestService::Trace(string message, valuetype [System]System.Diagnostics.TraceLevel level)
0xbb54  ldc.i4   0x80048533
0xbb59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbb5e  throw
0xbb5f  ldnull
0xbb60  stloc.0
0xbb61  ldnull
0xbb62  stloc.1
0xbb63  ldarg.1
0xbb64  ldc.i4.3
0xbb65  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode)
0xbb6a  stloc.3
0xbb6b  ldloc.3
0xbb6c  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [mscorlib]System.IO.Stream)
0xbb71  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathDocument::CreateNavigator()
0xbb76  dup
0xbb77  ldstr    aOrganizationma// "OrganizationManifest/TableRows/Organiza"...
0xbb7c  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0xbb81  stloc.s  4
0xbb83  ldloc.s  4
0xbb85  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0xbb8a  brfalse.s loc_BB99
0xbb8c  ldloc.s  4
0xbb8e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xbb93  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xbb98  stloc.0
0xbb99  ldstr    aOrganizationma_0// "OrganizationManifest/TableRows/Organiza"...
0xbb9e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0xbba3  stloc.s  5
0xbba5  ldloc.s  5
0xbba7  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0xbbac  brfalse.s loc_BBBB
0xbbae  ldloc.s  5
0xbbb0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xbbb5  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xbbba  stloc.1
0xbbbb  ldloc.3
0xbbbc  callvirt instance void [mscorlib]System.IO.Stream::Close()
0xbbc1  leave.s  loc_BBCD
0xbbc3  ldloc.3
0xbbc4  brfalse.s loc_BBCC
0xbbc6  ldloc.3
0xbbc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbbcc  endfinally
0xbbcd  ldloc.0
0xbbce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbbd3  brfalse.s loc_BC08
0xbbd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbbda  ldstr    a0ElementIsNotP// "'{0}' element is not present in the Man"...
0xbbdf  ldc.i4.2
0xbbe0  newarr   [mscorlib]System.Object
0xbbe5  dup
0xbbe6  ldc.i4.0
0xbbe7  ldstr    aOrganizationma// "OrganizationManifest/TableRows/Organiza"...
0xbbec  stelem.ref
0xbbed  dup
0xbbee  ldc.i4.1
0xbbef  ldarg.1
0xbbf0  stelem.ref
0xbbf1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbbf6  dup
0xbbf7  ldc.i4.3
0xbbf8  call     void Microsoft.Crm.Tools.Admin.OrganizationManifestService::Trace(string message, valuetype [System]System.Diagnostics.TraceLevel level)
0xbbfd  ldc.i4   0x80048534
0xbc02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbc07  throw
0xbc08  ldloc.1
0xbc09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbc0e  brfalse.s loc_BC43
0xbc10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc15  ldstr    a0ElementIsNotP// "'{0}' element is not present in the Man"...
0xbc1a  ldc.i4.2
0xbc1b  newarr   [mscorlib]System.Object
0xbc20  dup
0xbc21  ldc.i4.0
0xbc22  ldstr    aOrganizationma_0// "OrganizationManifest/TableRows/Organiza"...
0xbc27  stelem.ref
0xbc28  dup
0xbc29  ldc.i4.1
0xbc2a  ldarg.1
0xbc2b  stelem.ref
0xbc2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbc31  dup
0xbc32  ldc.i4.3
0xbc33  call     void Microsoft.Crm.Tools.Admin.OrganizationManifestService::Trace(string message, valuetype [System]System.Diagnostics.TraceLevel level)
0xbc38  ldc.i4   0x80048534
0xbc3d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbc42  throw
0xbc43  ldarg.2
0xbc44  ldloc.1
0xbc45  callvirt instance bool [mscorlib]System.String::Equals(string)
0xbc4a  brtrue.s loc_BC7B
0xbc4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc51  ldstr    a0OrganizationI// "'{0}' Organization is not present in th"...
0xbc56  ldc.i4.2
0xbc57  newarr   [mscorlib]System.Object
0xbc5c  dup
0xbc5d  ldc.i4.0
0xbc5e  ldarg.2
0xbc5f  stelem.ref
0xbc60  dup
0xbc61  ldc.i4.1
0xbc62  ldarg.1
0xbc63  stelem.ref
0xbc64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbc69  dup
0xbc6a  ldc.i4.3
0xbc6b  call     void Microsoft.Crm.Tools.Admin.OrganizationManifestService::Trace(string message, valuetype [System]System.Diagnostics.TraceLevel level)
0xbc70  ldc.i4   0x80048534
0xbc75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbc7a  throw
0xbc7b  ldloc.0
0xbc7c  ldloca.s 2
0xbc7e  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xbc83  brtrue.s loc_BCB4
0xbc85  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc8a  ldstr    aInvalidOrganiz// "Invalid OrganizationId '{0}' present in"...
0xbc8f  ldc.i4.2
0xbc90  newarr   [mscorlib]System.Object
0xbc95  dup
0xbc96  ldc.i4.0
0xbc97  ldarg.2
0xbc98  stelem.ref
0xbc99  dup
0xbc9a  ldc.i4.1
0xbc9b  ldarg.1
0xbc9c  stelem.ref
0xbc9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbca2  dup
0xbca3  ldc.i4.3
0xbca4  call     void Microsoft.Crm.Tools.Admin.OrganizationManifestService::Trace(string message, valuetype [System]System.Diagnostics.TraceLevel level)
0xbca9  ldc.i4   0x80048534
0xbcae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xbcb3  throw
0xbcb4  ldloc.2
0xbcb5  ret
```
