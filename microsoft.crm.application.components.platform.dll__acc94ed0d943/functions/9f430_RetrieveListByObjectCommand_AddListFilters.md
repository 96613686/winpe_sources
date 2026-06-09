# RetrieveListByObjectCommand::AddListFilters

- ea: `0x9f430`
- end: `0x9f4f9`
- name: `RetrieveListByObjectCommand::AddListFilters`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x17b0`

## callees

- `0x3a980`
- `0x59710`
- `0x5be20`
- `0x9caf0`
- `0x9cb20`
- `0x9f430`
- `0x9f500`

## string_xrefs

- `0x9f467`: `createdfromcode`
- `0x9f4b6`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x9f430  ldstr    aList// "list"
0x9f435  callvirt instance string [mscorlib]System.Object::ToString()
0x9f43a  ldarg.0
0x9f43b  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f440  ldstr    aOid// "oId"
0x9f445  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9f44a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9f44f  ldc.i4.3
0x9f450  newarr   [mscorlib]System.String
0x9f455  dup
0x9f456  ldc.i4.0
0x9f457  ldstr    aQuery// "query"
0x9f45c  stelem.ref
0x9f45d  dup
0x9f45e  ldc.i4.1
0x9f45f  ldstr    aType// "type"
0x9f464  stelem.ref
0x9f465  dup
0x9f466  ldc.i4.2
0x9f467  ldstr    aCreatedfromcod// "createdfromcode"
0x9f46c  stelem.ref
0x9f46d  ldarg.0
0x9f46e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext ApiCommand::get_OrganizationContext()
0x9f473  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9f478  stloc.0
0x9f479  ldnull
0x9f47a  stloc.1
0x9f47b  ldloc.0
0x9f47c  ldstr    aType// "type"
0x9f481  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f486  unbox.any [mscorlib]System.Boolean
0x9f48b  brfalse.s loc_9F4F7
0x9f48d  ldloc.0
0x9f48e  ldstr    aQuery// "query"
0x9f493  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f498  castclass [mscorlib]System.String
0x9f49d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9f4a2  brtrue.s loc_9F4F7
0x9f4a4  ldloc.0
0x9f4a5  ldstr    aQuery// "query"
0x9f4aa  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f4af  castclass [mscorlib]System.String
0x9f4b4  stloc.2
0x9f4b5  ldloc.0
0x9f4b6  ldstr    aCreatedfromcod// "createdfromcode"
0x9f4bb  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f4c0  unbox.any [mscorlib]System.Int32
0x9f4c5  stloc.3
0x9f4c6  ldarg.0
0x9f4c7  ldloc.2
0x9f4c8  ldloc.3
0x9f4c9  call     instance string RetrieveListByObjectCommand::GetListQuickFindXml(string listFetchXml, int32 entityTypeCode)
0x9f4ce  stloc.1
0x9f4cf  ldc.i4.0
0x9f4d0  stloc.s  4
0x9f4d2  ldarg.0
0x9f4d3  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f4d8  ldstr    aQuickfind// "quickFind"
0x9f4dd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9f4e2  ldloca.s 4
0x9f4e4  ldloc.1
0x9f4e5  ldloc.3
0x9f4e6  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9f4eb  ldarg.0
0x9f4ec  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext ApiCommand::get_OrganizationContext()
0x9f4f1  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.QuickFindUtil::ProcessQuickFindSearchCriteria(string, bool&, string, int32, class [mscorlib]System.Globalization.CultureInfo, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9f4f6  stloc.1
0x9f4f7  ldloc.1
0x9f4f8  ret
```
