# Microsoft.Crm.Application.Forms.AppForm::UpdateUrlForChildEntites

- ea: `0x27b60`
- end: `0x27ef9`
- name: `Microsoft.Crm.Application.Forms.AppForm::UpdateUrlForChildEntites`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x27220`

## callees

- `0x26ba0`
- `0x27b60`

## string_xrefs

- `0x27c18`: `_CreateFromId`
- `0x27c3d`: `_CreateFromId`
- `0x27c52`: `_CreateFromId`
- `0x27c84`: `_CreateFromId`
- `0x27cc8`: `_CreateFromId`
- `0x27cea`: `_CreateFromId`
- `0x27dc1`: `_CreateFromId`
- `0x27e0e`: `_CreateFromId`
- `0x27dd3`: `_CreateFromType`
- `0x27dfb`: `_CreateFromType=`

## pseudocode

```c

```

## disassembly

```asm
0x27b60  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x27b65  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x27b6a  stloc.0
0x27b6b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x27b70  stloc.1
0x27b71  ldarg.0
0x27b72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27b77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x27b7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x27b81  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x27b86  stloc.3
0x27b87  ldloc.3
0x27b88  ldc.i4   0x42F
0x27b8d  bgt.s    loc_27BBF
0x27b8f  ldloc.3
0x27b90  ldc.i4   0x3F5
0x27b95  bgt.s    loc_27BAB
0x27b97  ldloc.3
0x27b98  ldc.i4   0x3F3
0x27b9d  beq.s    loc_27C17
0x27b9f  ldloc.3
0x27ba0  ldc.i4   0x3F5
0x27ba5  beq      loc_27C3C
0x27baa  ret
0x27bab  ldloc.3
0x27bac  ldc.i4   0x41F
0x27bb1  beq      loc_27CE9
0x27bb6  ldloc.3
0x27bb7  ldc.i4   0x42F
0x27bbc  beq.s    loc_27BF2
0x27bbe  ret
0x27bbf  ldloc.3
0x27bc0  ldc.i4   0x43D
0x27bc5  bgt.s    loc_27BDE
0x27bc7  ldloc.3
0x27bc8  ldc.i4   0x43B
0x27bcd  beq      loc_27CB5
0x27bd2  ldloc.3
0x27bd3  ldc.i4   0x43D
0x27bd8  beq      loc_27CC7
0x27bdd  ret
0x27bde  ldloc.3
0x27bdf  ldc.i4   0x441
0x27be4  beq.s    loc_27C51
0x27be6  ldloc.3
0x27be7  ldc.i4   0x443
0x27bec  beq      loc_27C83
0x27bf1  ret
0x27bf2  ldloc.1
0x27bf3  ldstr    aObjecttypecode// "objecttypecode"
0x27bf8  ldstr    aObjecttypecode// "objecttypecode"
0x27bfd  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c02  ldloc.1
0x27c03  ldstr    aParentid_0// "parentid"
0x27c08  ldstr    aParentid_0// "parentid"
0x27c0d  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c12  br       loc_27CF9
0x27c17  ldloc.1
0x27c18  ldstr    aCreatefromid// "_CreateFromId"
0x27c1d  ldstr    aContractid// "contractid"
0x27c22  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c27  ldloc.1
0x27c28  ldstr    aContractid// "contractid"
0x27c2d  ldstr    aContractid// "contractid"
0x27c32  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c37  br       loc_27CF9
0x27c3c  ldloc.1
0x27c3d  ldstr    aCreatefromid// "_CreateFromId"
0x27c42  ldstr    aDiscounttypeid// "discounttypeid"
0x27c47  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c4c  br       loc_27CF9
0x27c51  ldloc.1
0x27c52  ldstr    aCreatefromid// "_CreateFromId"
0x27c57  ldstr    aSalesorderid// "salesorderid"
0x27c5c  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c61  ldloc.1
0x27c62  ldstr    aLocked// "locked"
0x27c67  ldstr    aSalesorderispr// "salesorderispricelocked"
0x27c6c  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c71  ldloc.1
0x27c72  ldstr    aIsproductoverr// "isproductoverridden"
0x27c77  ldstr    aIsproductoverr// "isproductoverridden"
0x27c7c  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c81  br.s     loc_27CF9
0x27c83  ldloc.1
0x27c84  ldstr    aCreatefromid// "_CreateFromId"
0x27c89  ldstr    aInvoiceid// "invoiceid"
0x27c8e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27c93  ldloc.1
0x27c94  ldstr    aLocked// "locked"
0x27c99  ldstr    aInvoiceisprice// "invoiceispricelocked"
0x27c9e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27ca3  ldloc.1
0x27ca4  ldstr    aIsproductoverr// "isproductoverridden"
0x27ca9  ldstr    aIsproductoverr// "isproductoverridden"
0x27cae  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27cb3  br.s     loc_27CF9
0x27cb5  ldloc.1
0x27cb6  ldstr    aOpportunityid// "opportunityid"
0x27cbb  ldstr    aOpportunityid// "opportunityid"
0x27cc0  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27cc5  br.s     loc_27CF9
0x27cc7  ldloc.1
0x27cc8  ldstr    aCreatefromid// "_CreateFromId"
0x27ccd  ldstr    aQuoteid// "quoteid"
0x27cd2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27cd7  ldloc.1
0x27cd8  ldstr    aIsproductoverr// "isproductoverridden"
0x27cdd  ldstr    aIsproductoverr// "isproductoverridden"
0x27ce2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27ce7  br.s     loc_27CF9
0x27ce9  ldloc.1
0x27cea  ldstr    aCreatefromid// "_CreateFromId"
0x27cef  ldstr    aUomscheduleid// "uomscheduleid"
0x27cf4  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x27cf9  ldc.i4   0x80
0x27cfe  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x27d03  stloc.2
0x27d04  ldloc.2
0x27d05  ldstr    aColumnset_0// "<columnset>"
0x27d0a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27d0f  pop
0x27d10  ldloc.1
0x27d11  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0x27d16  stloc.s  4
0x27d18  br.s     loc_27D3B
0x27d1a  ldloc.s  4
0x27d1c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x27d21  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x27d26  stloc.s  5
0x27d28  ldloc.2
0x27d29  ldstr    aColumn0Column// "<column>{0}</column>"
0x27d2e  ldloca.s 5
0x27d30  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x27d35  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x27d3a  pop
0x27d3b  ldloc.s  4
0x27d3d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27d42  brtrue.s loc_27D1A
0x27d44  leave.s  loc_27D5B
0x27d46  ldloc.s  4
0x27d48  isinst   [mscorlib]System.IDisposable
0x27d4d  stloc.s  6
0x27d4f  ldloc.s  6
0x27d51  brfalse.s loc_27D5A
0x27d53  ldloc.s  6
0x27d55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27d5a  endfinally
0x27d5b  ldloc.2
0x27d5c  ldstr    aColumnset// "</columnset>"
0x27d61  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27d66  pop
0x27d67  ldarg.0
0x27d68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27d6d  ldloc.2
0x27d6e  callvirt instance string [mscorlib]System.Object::ToString()
0x27d73  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x27d78  ldarg.0
0x27d79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27d7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x27d83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x27d88  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x27d8d  stloc.3
0x27d8e  ldloc.3
0x27d8f  ldc.i4   0x441
0x27d94  beq.s    loc_27D9E
0x27d96  ldloc.3
0x27d97  ldc.i4   0x443
0x27d9c  bne.un.s loc_27DC0
0x27d9e  ldarg.0
0x27d9f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27da4  ldstr    aIsproductoverr// "isproductoverridden"
0x27da9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x27dae  unbox.any [mscorlib]System.Boolean
0x27db3  brfalse.s loc_27DC0
0x27db5  ldloc.1
0x27db6  ldstr    aLocked// "locked"
0x27dbb  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x27dc0  ldloc.1
0x27dc1  ldstr    aCreatefromid// "_CreateFromId"
0x27dc6  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x27dcb  brfalse.s loc_27E3F
0x27dcd  ldloc.0
0x27dce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x27dd3  ldstr    aCreatefromtype// "_CreateFromType"
0x27dd8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x27ddd  brtrue.s loc_27E3F
0x27ddf  ldarg.1
0x27de0  ldarg.1
0x27de1  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x27de6  brfalse.s loc_27DEF
0x27de8  ldstr    asc_12008E// "&"
0x27ded  br.s     loc_27DF4
0x27def  ldstr    asc_113718// "?"
0x27df4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27df9  pop
0x27dfa  ldarg.1
0x27dfb  ldstr    aCreatefromtype_0// "_CreateFromType="
0x27e00  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27e05  pop
0x27e06  ldarg.1
0x27e07  ldarg.0
0x27e08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27e0d  ldloc.1
0x27e0e  ldstr    aCreatefromid// "_CreateFromId"
0x27e13  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x27e18  castclass [mscorlib]System.String
0x27e1d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x27e22  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x27e27  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x27e2c  stloc.3
0x27e2d  ldloca.s 3
0x27e2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27e34  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x27e39  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27e3e  pop
0x27e3f  ldloc.1
0x27e40  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0x27e45  stloc.s  4
0x27e47  br       loc_27ED5
0x27e4c  ldloc.s  4
0x27e4e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x27e53  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x27e58  stloc.s  7
0x27e5a  ldloc.0
0x27e5b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x27e60  ldloca.s 7
0x27e62  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x27e67  castclass [mscorlib]System.String
0x27e6c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x27e71  brtrue.s loc_27ED5
0x27e73  ldarg.1
0x27e74  ldarg.1
0x27e75  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x27e7a  brfalse.s loc_27E83
0x27e7c  ldstr    asc_12008E// "&"
0x27e81  br.s     loc_27E88
0x27e83  ldstr    asc_113718// "?"
0x27e88  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27e8d  pop
0x27e8e  ldarg.1
0x27e8f  ldloca.s 7
0x27e91  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x27e96  castclass [mscorlib]System.String
0x27e9b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x27ea0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27ea5  pop
0x27ea6  ldarg.1
0x27ea7  ldstr    asc_1200B4// "="
0x27eac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27eb1  pop
0x27eb2  ldarg.1
0x27eb3  ldarg.0
0x27eb4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x27eb9  ldloca.s 7
0x27ebb  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x27ec0  castclass [mscorlib]System.String
0x27ec5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string)
0x27eca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x27ecf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x27ed4  pop
0x27ed5  ldloc.s  4
0x27ed7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27edc  brtrue   loc_27E4C
0x27ee1  leave.s  loc_27EF8
0x27ee3  ldloc.s  4
0x27ee5  isinst   [mscorlib]System.IDisposable
0x27eea  stloc.s  6
0x27eec  ldloc.s  6
0x27eee  brfalse.s loc_27EF7
0x27ef0  ldloc.s  6
0x27ef2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27ef7  endfinally
0x27ef8  ret
```
