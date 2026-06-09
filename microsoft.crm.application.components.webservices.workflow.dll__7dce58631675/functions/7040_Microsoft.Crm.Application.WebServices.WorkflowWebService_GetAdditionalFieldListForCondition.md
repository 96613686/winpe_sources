# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAdditionalFieldListForCondition

- ea: `0x7040`
- end: `0x71a8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAdditionalFieldListForCondition`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7040`

## pseudocode

```c

```

## disassembly

```asm
0x7040  ldc.i4.s 0xA
0x7042  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x7047  stloc.0
0x7048  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x704d  stloc.1
0x704e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7053  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7058  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x705d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7062  ldarg.1
0x7063  ldc.i4.1
0x7064  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7069  stloc.2
0x706a  ldloc.2
0x706b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x7070  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x7075  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x707a  stloc.s  4
0x707c  br.s     loc_70D9
0x707e  ldloc.s  4
0x7080  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7085  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x708a  stloc.s  5
0x708c  ldloc.s  5
0x708e  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.AdvanceFindUtility::IsAttributeValidForAdvancedFind(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x7093  brtrue.s loc_70D9
0x7095  ldloc.s  5
0x7097  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x709c  ldc.i4   0x8000000
0x70a1  and
0x70a2  ldc.i4   0x8000000
0x70a7  bne.un.s loc_70D9
0x70a9  ldloc.s  5
0x70ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x70b0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x70b5  ldc.i4.s 0x11
0x70b7  beq.s    loc_70D9
0x70b9  ldarg.0
0x70ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_CurrentResourceManager()
0x70bf  ldloc.2
0x70c0  ldloc.s  5
0x70c2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x70c7  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x70cc  ldloc.0
0x70cd  ldloc.1
0x70ce  ldnull
0x70cf  call     void [Microsoft.Crm.Application.Components.WebServices.AdvancedFind]Microsoft.Crm.Application.WebServices.AdvancedFind::AppendFieldXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, int32, class [mscorlib]System.Collections.ArrayList, class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>)
0x70d4  leave.s  loc_70D9
0x70d6  pop
0x70d7  leave.s  loc_70D9
0x70d9  ldloc.s  4
0x70db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x70e0  brtrue.s loc_707E
0x70e2  leave.s  loc_70F9
0x70e4  ldloc.s  4
0x70e6  isinst   [mscorlib]System.IDisposable
0x70eb  stloc.s  6
0x70ed  ldloc.s  6
0x70ef  brfalse.s loc_70F8
0x70f1  ldloc.s  6
0x70f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70f8  endfinally
0x70f9  ldloc.0
0x70fa  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x70ff  stloc.3
0x7100  ldloc.1
0x7101  ldstr    aLookupicons// "<lookupicons>"
0x7106  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x710b  pop
0x710c  ldloc.0
0x710d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7112  stloc.s  4
0x7114  br.s     loc_7164
0x7116  ldloc.s  4
0x7118  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x711d  unbox.any [mscorlib]System.Int32
0x7122  stloc.s  7
0x7124  ldloc.3
0x7125  ldc.i4.1
0x7126  sub
0x7127  stloc.3
0x7128  ldloc.1
0x7129  ldloc.s  7
0x712b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x7130  pop
0x7131  ldloc.1
0x7132  ldc.i4.s 0x3A
0x7134  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x7139  pop
0x713a  ldloc.1
0x713b  ldloc.s  7
0x713d  ldc.i4.0
0x713e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7143  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7148  callvirt instance string [mscorlib]System.Object::ToString()
0x714d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x7152  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7157  pop
0x7158  ldloc.3
0x7159  brfalse.s loc_7164
0x715b  ldloc.1
0x715c  ldc.i4.s 0x3A
0x715e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x7163  pop
0x7164  ldloc.s  4
0x7166  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x716b  brtrue.s loc_7116
0x716d  leave.s  loc_7184
0x716f  ldloc.s  4
0x7171  isinst   [mscorlib]System.IDisposable
0x7176  stloc.s  6
0x7178  ldloc.s  6
0x717a  brfalse.s loc_7183
0x717c  ldloc.s  6
0x717e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7183  endfinally
0x7184  ldloc.1
0x7185  ldstr    aLookupicons_0// "</lookupicons>"
0x718a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x718f  pop
0x7190  ldloc.1
0x7191  callvirt instance string [mscorlib]System.Object::ToString()
0x7196  stloc.s  8
0x7198  leave.s  loc_71A5
0x719a  stloc.s  9
0x719c  ldarg.0
0x719d  ldloc.s  9
0x719f  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x71a4  throw
0x71a5  ldloc.s  8
0x71a7  ret
```
