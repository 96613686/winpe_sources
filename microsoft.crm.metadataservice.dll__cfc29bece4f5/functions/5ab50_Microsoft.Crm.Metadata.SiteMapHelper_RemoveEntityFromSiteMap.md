# Microsoft.Crm.Metadata.SiteMapHelper::RemoveEntityFromSiteMap

- ea: `0x5ab50`
- end: `0x5acdd`
- name: `Microsoft.Crm.Metadata.SiteMapHelper::RemoveEntityFromSiteMap`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x31b10`
- `0x32900`

## callees

- `0x5ab50`
- `0x5ace0`
- `0x5b050`

## string_xrefs

- `0x5ab84`: `sitemapxml`
- `0x5ac24`: `/SiteMap/Area/Group/SubArea/Privilege[@Entity = '{0}']`

## pseudocode

```c

```

## disassembly

```asm
0x5ab50  ldarg.0
0x5ab51  ldstr    aEntityname// "entityName"
0x5ab56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5ab5b  ldarg.1
0x5ab5c  ldstr    aContext// "context"
0x5ab61  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5ab66  ldarg.1
0x5ab67  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Metadata.SiteMapHelper::RetriveUnpublishedSitemaps(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5ab6c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5ab71  stloc.0
0x5ab72  br       loc_5ACBB
0x5ab77  ldloc.0
0x5ab78  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5ab7d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5ab82  stloc.1
0x5ab83  ldloc.1
0x5ab84  ldstr    aSitemapxml// "sitemapxml"
0x5ab89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ab8e  castclass [mscorlib]System.String
0x5ab93  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5ab98  stloc.2
0x5ab99  ldc.i4.0
0x5ab9a  stloc.3
0x5ab9b  ldloc.2
0x5ab9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5aba1  ldstr    aSitemapAreaGro// "/SiteMap/Area/Group/SubArea[@Entity = '"...
0x5aba6  ldc.i4.1
0x5aba7  newarr   [mscorlib]System.Object
0x5abac  dup
0x5abad  ldc.i4.0
0x5abae  ldarg.0
0x5abaf  stelem.ref
0x5abb0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5abb5  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5abba  stloc.s  4
0x5abbc  ldloc.s  4
0x5abbe  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5abc3  ldc.i4.0
0x5abc4  ble.s    loc_5AC10
0x5abc6  ldloc.s  4
0x5abc8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5abcd  stloc.s  5
0x5abcf  br.s     loc_5ABEE
0x5abd1  ldloc.s  5
0x5abd3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5abd8  castclass [System.Xml]System.Xml.XmlNode
0x5abdd  stloc.s  6
0x5abdf  ldloc.s  6
0x5abe1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x5abe6  ldloc.s  6
0x5abe8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x5abed  pop
0x5abee  ldloc.s  5
0x5abf0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5abf5  brtrue.s loc_5ABD1
0x5abf7  leave.s  loc_5AC0E
0x5abf9  ldloc.s  5
0x5abfb  isinst   [mscorlib]System.IDisposable
0x5ac00  stloc.s  7
0x5ac02  ldloc.s  7
0x5ac04  brfalse.s loc_5AC0D
0x5ac06  ldloc.s  7
0x5ac08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ac0d  endfinally
0x5ac0e  ldc.i4.1
0x5ac0f  stloc.3
0x5ac10  leave.s  loc_5AC1E
0x5ac12  ldloc.s  4
0x5ac14  brfalse.s loc_5AC1D
0x5ac16  ldloc.s  4
0x5ac18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ac1d  endfinally
0x5ac1e  ldloc.2
0x5ac1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ac24  ldstr    aSitemapAreaGro_0// "/SiteMap/Area/Group/SubArea/Privilege[@"...
0x5ac29  ldc.i4.1
0x5ac2a  newarr   [mscorlib]System.Object
0x5ac2f  dup
0x5ac30  ldc.i4.0
0x5ac31  ldarg.0
0x5ac32  stelem.ref
0x5ac33  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ac38  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5ac3d  stloc.s  8
0x5ac3f  ldloc.s  8
0x5ac41  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5ac46  ldc.i4.0
0x5ac47  ble.s    loc_5AC93
0x5ac49  ldloc.s  8
0x5ac4b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5ac50  stloc.s  5
0x5ac52  br.s     loc_5AC71
0x5ac54  ldloc.s  5
0x5ac56  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5ac5b  castclass [System.Xml]System.Xml.XmlNode
0x5ac60  stloc.s  9
0x5ac62  ldloc.s  9
0x5ac64  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x5ac69  ldloc.s  9
0x5ac6b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x5ac70  pop
0x5ac71  ldloc.s  5
0x5ac73  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5ac78  brtrue.s loc_5AC54
0x5ac7a  leave.s  loc_5AC91
0x5ac7c  ldloc.s  5
0x5ac7e  isinst   [mscorlib]System.IDisposable
0x5ac83  stloc.s  7
0x5ac85  ldloc.s  7
0x5ac87  brfalse.s loc_5AC90
0x5ac89  ldloc.s  7
0x5ac8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ac90  endfinally
0x5ac91  ldc.i4.1
0x5ac92  stloc.3
0x5ac93  leave.s  loc_5ACA1
0x5ac95  ldloc.s  8
0x5ac97  brfalse.s loc_5ACA0
0x5ac99  ldloc.s  8
0x5ac9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5aca0  endfinally
0x5aca1  ldloc.3
0x5aca2  brfalse.s loc_5ACBB
0x5aca4  ldloc.2
0x5aca5  ldarg.1
0x5aca6  ldloc.1
0x5aca7  ldstr    aSitemapid// "sitemapid"
0x5acac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5acb1  unbox.any [mscorlib]System.Guid
0x5acb6  call     void Microsoft.Crm.Metadata.SiteMapHelper::UpdateSiteMapAndDependencies(class [System.Xml]System.Xml.XmlDocument siteMapXml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid siteMapId)
0x5acbb  ldloc.0
0x5acbc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5acc1  brtrue   loc_5AB77
0x5acc6  leave.s  loc_5ACDC
0x5acc8  ldloc.0
0x5acc9  isinst   [mscorlib]System.IDisposable
0x5acce  stloc.s  7
0x5acd0  ldloc.s  7
0x5acd2  brfalse.s loc_5ACDB
0x5acd4  ldloc.s  7
0x5acd6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5acdb  endfinally
0x5acdc  ret
```
