# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadOrgSettings

- ea: `0x5c800`
- end: `0x5c88a`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadOrgSettings`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5c6f0`

## callees

- `0x4c330`
- `0x51f10`
- `0x523d0`
- `0x52860`
- `0x5c800`

## string_xrefs

- `0x5c848`: `The fillable description created for the organization should be OrganizationDescription inheriting object`
- `0x5c86d`: `MetadataXml cannot have more than one /metadata/organization xml nodes.`

## pseudocode

```c

```

## disassembly

```asm
0x5c800  ldstr    aLoadorgsetting// "LoadOrgSettings"
0x5c805  ldarg.2
0x5c806  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5c80b  dup
0x5c80c  starg.s  2
0x5c80e  stloc.0
0x5c80f  ldarg.3
0x5c810  ldstr    aMetadataOrgani// "/metadata/organization"
0x5c815  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5c81a  stloc.1
0x5c81b  ldloc.1
0x5c81c  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5c821  brfalse.s loc_5C865
0x5c823  ldloc.1
0x5c824  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5c829  castclass [System.Xml]System.Xml.IHasXmlNode
0x5c82e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.IHasXmlNode::GetNode()
0x5c833  stloc.2
0x5c834  ldarg.0
0x5c835  ldstr    aOrganization// "Organization"
0x5c83a  callvirt instance class Microsoft.Crm.Metadata.IFillableMetadataDescription Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFillableDescription(string name)
0x5c83f  isinst   Microsoft.Crm.Metadata.OrganizationDescription
0x5c844  stloc.3
0x5c845  ldloc.3
0x5c846  brtrue.s loc_5C858
0x5c848  ldstr    aTheFillableDes// "The fillable description created for th"...
0x5c84d  ldc.i4   0x80040216
0x5c852  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5c857  throw
0x5c858  ldarg.1
0x5c859  ldloc.2
0x5c85a  ldloc.3
0x5c85b  newobj   instance void Microsoft.Crm.Metadata.Organization::.ctor(class [System.Xml]System.Xml.XmlNode node, class Microsoft.Crm.Metadata.OrganizationDescription descriptionToUse)
0x5c860  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::set_OrganizationSettings(class Microsoft.Crm.Metadata.Organization value)
0x5c865  ldloc.1
0x5c866  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5c86b  brfalse.s loc_5C87D
0x5c86d  ldstr    aMetadataxmlCan// "MetadataXml cannot have more than one /"...
0x5c872  ldc.i4   0x8004023A
0x5c877  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5c87c  throw
0x5c87d  leave.s  loc_5C889
0x5c87f  ldloc.0
0x5c880  brfalse.s loc_5C888
0x5c882  ldloc.0
0x5c883  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c888  endfinally
0x5c889  ret
```
