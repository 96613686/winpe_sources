# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetSolutionManifests

- ea: `0x7e230`
- end: `0x7e43e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetSolutionManifests`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x66e00`
- `0x67ea0`

## callees

- `0x7e120`
- `0x7e210`
- `0x7e230`
- `0x7e8a0`

## string_xrefs

- `0x7e268`: `ImportExportXml`
- `0x7e289`: `solutionManifests`
- `0x7e294`: `solutionManifest`
- `0x7e251`: `ImportExportXml/SolutionManifest`

## pseudocode

```c

```

## disassembly

```asm
0x7e230  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7e235  stloc.0
0x7e236  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x7e23b  stloc.1
0x7e23c  ldloc.1
0x7e23d  ldc.i4.1
0x7e23e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x7e243  ldloc.0
0x7e244  ldloc.1
0x7e245  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x7e24a  stloc.2
0x7e24b  ldarg.0
0x7e24c  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7e251  ldstr    aImportexportxm_154// "ImportExportXml/SolutionManifest"
0x7e256  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7e25b  stloc.3
0x7e25c  ldloc.3
0x7e25d  brfalse  loc_7E42B
0x7e262  ldarg.0
0x7e263  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7e268  ldstr    aImportexportxm// "ImportExportXml"
0x7e26d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7e272  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7e277  ldstr    aLanguagecode// "languagecode"
0x7e27c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x7e281  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7e286  stloc.s  4
0x7e288  ldloc.2
0x7e289  ldstr    aSolutionmanife_0// "solutionManifests"
0x7e28e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7e293  ldloc.2
0x7e294  ldstr    aSolutionmanife_1// "solutionManifest"
0x7e299  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7e29e  ldloc.2
0x7e29f  ldstr    aLanguagecode// "languagecode"
0x7e2a4  ldloc.s  4
0x7e2a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e2ab  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x7e2b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7e2b5  ldarg.0
0x7e2b6  ldstr    aUniquename_0// "UniqueName"
0x7e2bb  ldloc.3
0x7e2bc  ldloc.2
0x7e2bd  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e2c2  ldarg.0
0x7e2c3  ldstr    aParentuniquena// "ParentUniqueName"
0x7e2c8  ldloc.3
0x7e2c9  ldloc.2
0x7e2ca  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e2cf  ldarg.0
0x7e2d0  ldstr    aLocalizednames_1// "LocalizedNames"
0x7e2d5  ldstr    aLocalizedname// "LocalizedName"
0x7e2da  ldloc.3
0x7e2db  ldloc.2
0x7e2dc  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteCollection(string pluralNodeName, string singularNodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e2e1  ldarg.0
0x7e2e2  ldstr    aDescriptions// "Descriptions"
0x7e2e7  ldstr    aDescription_0// "Description"
0x7e2ec  ldloc.3
0x7e2ed  ldloc.2
0x7e2ee  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteCollection(string pluralNodeName, string singularNodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e2f3  ldarg.0
0x7e2f4  ldstr    aVersion_0// "Version"
0x7e2f9  ldloc.3
0x7e2fa  ldloc.2
0x7e2fb  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e300  ldarg.0
0x7e301  ldstr    aManaged// "Managed"
0x7e306  ldloc.3
0x7e307  ldloc.2
0x7e308  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e30d  ldloc.2
0x7e30e  ldstr    aPublisher// "Publisher"
0x7e313  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7e318  ldloc.3
0x7e319  ldstr    aPublisher// "Publisher"
0x7e31e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x7e323  stloc.s  5
0x7e325  ldloc.s  5
0x7e327  brfalse  loc_7E411
0x7e32c  ldarg.0
0x7e32d  ldstr    aUniquename_0// "UniqueName"
0x7e332  ldloc.s  5
0x7e334  ldloc.2
0x7e335  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e33a  ldarg.0
0x7e33b  ldstr    aLocalizednames_1// "LocalizedNames"
0x7e340  ldstr    aLocalizedname// "LocalizedName"
0x7e345  ldloc.s  5
0x7e347  ldloc.2
0x7e348  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteCollection(string pluralNodeName, string singularNodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e34d  ldarg.0
0x7e34e  ldstr    aDescriptions// "Descriptions"
0x7e353  ldstr    aDescription_0// "Description"
0x7e358  ldloc.s  5
0x7e35a  ldloc.2
0x7e35b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteCollection(string pluralNodeName, string singularNodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e360  ldarg.0
0x7e361  ldstr    aEmailaddress_0// "EMailAddress"
0x7e366  ldloc.s  5
0x7e368  ldloc.2
0x7e369  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e36e  ldarg.0
0x7e36f  ldstr    aSupportingwebs_0// "SupportingWebsiteUrl"
0x7e374  ldloc.s  5
0x7e376  ldloc.2
0x7e377  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e37c  ldloc.2
0x7e37d  ldstr    aAddresses// "Addresses"
0x7e382  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7e387  ldloc.2
0x7e388  ldstr    aAddress// "Address"
0x7e38d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7e392  ldloc.3
0x7e393  ldstr    aPublisherAddre_7// "Publisher/Addresses/Address[AddressNumb"...
0x7e398  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7e39d  stloc.s  6
0x7e39f  ldloc.s  6
0x7e3a1  brfalse.s loc_7E405
0x7e3a3  ldarg.0
0x7e3a4  ldstr    aCity// "City"
0x7e3a9  ldloc.s  6
0x7e3ab  ldloc.2
0x7e3ac  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3b1  ldarg.0
0x7e3b2  ldstr    aCountry// "Country"
0x7e3b7  ldloc.s  6
0x7e3b9  ldloc.2
0x7e3ba  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3bf  ldarg.0
0x7e3c0  ldstr    aLine1// "Line1"
0x7e3c5  ldloc.s  6
0x7e3c7  ldloc.2
0x7e3c8  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3cd  ldarg.0
0x7e3ce  ldstr    aLine2// "Line2"
0x7e3d3  ldloc.s  6
0x7e3d5  ldloc.2
0x7e3d6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3db  ldarg.0
0x7e3dc  ldstr    aPostalcode// "PostalCode"
0x7e3e1  ldloc.s  6
0x7e3e3  ldloc.2
0x7e3e4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3e9  ldarg.0
0x7e3ea  ldstr    aStateorprovinc// "StateOrProvince"
0x7e3ef  ldloc.s  6
0x7e3f1  ldloc.2
0x7e3f2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e3f7  ldarg.0
0x7e3f8  ldstr    aTelephone1// "Telephone1"
0x7e3fd  ldloc.s  6
0x7e3ff  ldloc.2
0x7e400  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::WriteItem(string nodeName, class [System.Xml]System.Xml.XmlNode rootNode, class [System.Xml]System.Xml.XmlWriter xw)
0x7e405  ldloc.2
0x7e406  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7e40b  ldloc.2
0x7e40c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7e411  ldloc.2
0x7e412  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7e417  ldarg.0
0x7e418  ldarg.1
0x7e419  ldloc.2
0x7e41a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::CheckImportPreConditions(bool checkMissingDependencies, class [System.Xml]System.Xml.XmlWriter xw)
0x7e41f  ldloc.2
0x7e420  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7e425  ldloc.2
0x7e426  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7e42b  leave.s  loc_7E437
0x7e42d  ldloc.2
0x7e42e  brfalse.s loc_7E436
0x7e430  ldloc.2
0x7e431  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e436  endfinally
0x7e437  ldloc.0
0x7e438  callvirt instance string [mscorlib]System.Object::ToString()
0x7e43d  ret
```
