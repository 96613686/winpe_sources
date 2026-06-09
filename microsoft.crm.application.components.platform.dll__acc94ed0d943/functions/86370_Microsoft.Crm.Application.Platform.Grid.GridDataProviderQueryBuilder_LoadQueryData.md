# Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::LoadQueryData

- ea: `0x86370`
- end: `0x865ff`
- name: `Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::LoadQueryData`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x86360`

## callees

- `0x1550`
- `0x16b0`
- `0x16d0`
- `0x49e0`
- `0x4a30`
- `0x5880`
- `0x58c0`
- `0x58d0`
- `0x115b0`
- `0x59710`
- `0x5be20`
- `0x6a0d0`
- `0x6a2e0`
- `0x6a330`
- `0x84dd0`
- `0x84e00`
- `0x84e20`
- `0x85170`
- `0x856a0`
- `0x85700`
- `0x86370`
- `0x86600`
- `0x868c0`
- `0x86f80`
- `0x87190`

## string_xrefs

- `0x86555`: `layoutXml`
- `0x8656c`: `layoutXml`
- `0x8658a`: `fetchXmlForFilters`
- `0x865a3`: `fetchXmlForFilters`

## pseudocode

```c

```

## disassembly

```asm
0x86370  ldnull
0x86371  stloc.0
0x86372  ldarg.0
0x86373  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86378  ldstr    aSuppressfetch// "suppressfetch"
0x8637d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86382  brfalse.s loc_863A3
0x86384  ldarg.0
0x86385  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x8638a  ldstr    aSuppressfetch// "suppressfetch"
0x8638f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86394  ldstr    a1// "1"
0x86399  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8639e  brfalse  loc_865FD
0x863a3  ldarg.0
0x863a4  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x863a9  ldstr    aViewid// "viewid"
0x863ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x863b3  ldnull
0x863b4  cgt.un
0x863b6  ldstr    aViewIdIsNotSet// "View ID is not set in the Grid Paramete"...
0x863bb  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x863c0  ldarg.0
0x863c1  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x863c6  ldstr    aViewtype// "viewtype"
0x863cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x863d0  ldnull
0x863d1  cgt.un
0x863d3  ldstr    aViewtypeIsNotS// "ViewType is not set in the Grid Paramet"...
0x863d8  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x863dd  ldarg.0
0x863de  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x863e3  ldstr    aOtype// "oType"
0x863e8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x863ed  ldarg.0
0x863ee  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x863f3  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x863f8  stloc.1
0x863f9  ldloc.1
0x863fa  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x863ff  ldc.i4   0x10CC
0x86404  bne.un   loc_86525
0x86409  ldarg.0
0x8640a  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x8640f  ldstr    aOid// "oId"
0x86414  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x86419  stloc.s  4
0x8641b  ldloc.1
0x8641c  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x86421  ldloc.s  4
0x86423  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x86428  ldc.i4.4
0x86429  newarr   [mscorlib]System.String
0x8642e  dup
0x8642f  ldc.i4.0
0x86430  ldstr    aListid// "listid"
0x86435  stelem.ref
0x86436  dup
0x86437  ldc.i4.1
0x86438  ldstr    aType// "type"
0x8643d  stelem.ref
0x8643e  dup
0x8643f  ldc.i4.2
0x86440  ldstr    aQuery// "query"
0x86445  stelem.ref
0x86446  dup
0x86447  ldc.i4.3
0x86448  ldstr    aMembertype// "membertype"
0x8644d  stelem.ref
0x8644e  ldarg.0
0x8644f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x86454  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x86459  stloc.s  5
0x8645b  ldloc.s  5
0x8645d  ldstr    aType// "type"
0x86462  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x86467  unbox.any [mscorlib]System.Boolean
0x8646c  brfalse  loc_86525
0x86471  ldloc.s  5
0x86473  ldstr    aQuery// "query"
0x86478  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x8647d  castclass [mscorlib]System.String
0x86482  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86487  brtrue   loc_86525
0x8648c  ldarg.0
0x8648d  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86492  ldstr    aOtc// "otc"
0x86497  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8649c  ldarg.0
0x8649d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x864a2  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x864a7  ldstr    a1039// "1039"
0x864ac  stloc.s  6
0x864ae  ldarg.0
0x864af  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x864b4  ldstr    aViewtype// "viewtype"
0x864b9  ldloc.s  6
0x864bb  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x864c0  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x864c5  stloc.s  7
0x864c7  ldloc.s  7
0x864c9  ldc.i4.1
0x864ca  sub
0x864cb  switch   loc_864E2, loc_864F9, loc_86525, loc_86510
0x864e0  br.s     loc_86525
0x864e2  ldarg.0
0x864e3  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x864e8  ldstr    aViewid// "viewid"
0x864ed  ldstr    a38a21ffb4e3240// "{38A21FFB-4E32-4038-BEB9-03172A0DD034}"
0x864f2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x864f7  br.s     loc_86525
0x864f9  ldarg.0
0x864fa  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x864ff  ldstr    aViewid// "viewid"
0x86504  ldstr    a58fb20ffD5be40// "{58FB20FF-D5BE-406F-908E-C777E9DEDF5F}"
0x86509  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x8650e  br.s     loc_86525
0x86510  ldarg.0
0x86511  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86516  ldstr    aViewid// "viewid"
0x8651b  ldstr    aFc71d0307a824b// "{FC71D030-7A82-4B51-BDE8-29B24B7ABF9D}"
0x86520  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x86525  ldarg.0
0x86526  callvirt instance class Microsoft.Crm.View Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_CurrentView()
0x8652b  stloc.2
0x8652c  ldloc.2
0x8652d  ldarg.0
0x8652e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x86533  newobj   instance void Microsoft.Crm.QueryBuilder::.ctor(class Microsoft.Crm.View view, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x86538  stloc.3
0x86539  ldarg.0
0x8653a  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x8653f  ldstr    aViewtitle// "viewTitle"
0x86544  ldloc.2
0x86545  callvirt instance string Microsoft.Crm.View::get_Title()
0x8654a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x8654f  ldarg.0
0x86550  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x86555  ldstr    aLayoutxml_0// "layoutXml"
0x8655a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8655f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86564  brfalse.s loc_8657C
0x86566  ldarg.0
0x86567  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x8656c  ldstr    aLayoutxml_0// "layoutXml"
0x86571  ldloc.2
0x86572  callvirt instance string Microsoft.Crm.View::get_HeaderXml()
0x86577  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x8657c  ldloc.2
0x8657d  callvirt instance string Microsoft.Crm.View::get_FetchXml()
0x86582  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86587  brtrue.s loc_865A2
0x86589  ldarg.0
0x8658a  ldstr    aFetchxmlforfil// "fetchXmlForFilters"
0x8658f  ldloc.2
0x86590  callvirt instance string Microsoft.Crm.View::get_FetchXml()
0x86595  call     string Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::SanitizeFetchXmlFilterNodes(string fetchXmlValue)
0x8659a  ldc.i4.1
0x8659b  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddParameter(string name, string value, valuetype Microsoft.Crm.Application.Platform.Grid.GridParamRequirementLevel requiredLevel)
0x865a0  br.s     loc_865B3
0x865a2  ldarg.0
0x865a3  ldstr    aFetchxmlforfil// "fetchXmlForFilters"
0x865a8  ldsfld   string [mscorlib]System.String::Empty
0x865ad  ldc.i4.1
0x865ae  call     instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddParameter(string name, string value, valuetype Microsoft.Crm.Application.Platform.Grid.GridParamRequirementLevel requiredLevel)
0x865b3  ldarg.0
0x865b4  ldloc.3
0x865b5  ldloc.2
0x865b6  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::SetupQueryBuilder(class Microsoft.Crm.QueryBuilder queryBuilder, class Microsoft.Crm.View view)
0x865bb  brfalse.s loc_865FD
0x865bd  ldloc.3
0x865be  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x865c3  ldarg.0
0x865c4  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x865c9  callvirt instance void Microsoft.Crm.ApplicationQuery::AddParameters(class [System]System.Collections.Specialized.NameValueCollection parameters)
0x865ce  ldloc.3
0x865cf  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x865d4  ldarg.0
0x865d5  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_RequirementLevels()
0x865da  callvirt instance void Microsoft.Crm.ApplicationQuery::AddRequirementLevels(class [System]System.Collections.Specialized.NameValueCollection parameters)
0x865df  ldarg.0
0x865e0  ldloc.3
0x865e1  callvirt instance object Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::GetData(class Microsoft.Crm.QueryBuilder queryBuilder)
0x865e6  stloc.0
0x865e7  ldarg.0
0x865e8  call     instance class Microsoft.Crm.Application.Platform.Grid.GridData Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0x865ed  ldloc.3
0x865ee  callvirt instance class Microsoft.Crm.ApplicationQuery Microsoft.Crm.QueryBuilder::get_Query()
0x865f3  callvirt instance bool Microsoft.Crm.ApplicationQuery::get_RetrieveHierarchyInformation()
0x865f8  callvirt instance void Microsoft.Crm.Application.Platform.Grid.GridData::set_IsHierarchyAware(bool value)
0x865fd  ldloc.0
0x865fe  ret
```
