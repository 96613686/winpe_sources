# Microsoft.Crm.Workflow.Services.QueryDataActivityService::ExecuteQuery

- ea: `0x19020`
- end: `0x1916a`
- name: `Microsoft.Crm.Workflow.Services.QueryDataActivityService::ExecuteQuery`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8e70`
- `0x8ec0`
- `0x14770`
- `0x14780`
- `0x14930`
- `0x149c0`
- `0x19020`

## string_xrefs

- `0x19073`: `Error Parsing FetchXml for query Step.  FetchXml - {0}, Error - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x19020  ldarg.0
0x19021  ldarg.2
0x19022  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x19027  stloc.0
0x19028  ldarg.3
0x19029  ldc.i4.1
0x1902a  bge.s    loc_19050
0x1902c  ldarg.0
0x1902d  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19032  newobj   instance void Microsoft.Crm.Workflow.WorkflowUserContext::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext)
0x19037  call     instance int32 Microsoft.Crm.Workflow.WorkflowUserContext::get_UserRecordsPerPage()
0x1903c  starg.s  3
0x1903e  ldarg.3
0x1903f  ldc.i4   0x3E8
0x19044  clt
0x19046  ldstr    aForSynchronous// "For synchronous workflow query Results "...
0x1904b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x19050  ldnull
0x19051  stloc.1
0x19052  ldarg.0
0x19053  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateSdkService()
0x19058  stloc.2
0x19059  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1905e  stloc.3
0x1905f  ldarg.1
0x19060  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x19065  stloc.3
0x19066  leave.s  loc_19093
0x19068  stloc.s  7
0x1906a  ldloc.s  7
0x1906c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x19071  ldc.i4.s 0x1E
0x19073  ldstr    aErrorParsingFe// "Error Parsing FetchXml for query Step. "...
0x19078  ldc.i4.2
0x19079  newarr   [mscorlib]System.Object
0x1907e  dup
0x1907f  ldc.i4.0
0x19080  ldarg.1
0x19081  stelem.ref
0x19082  dup
0x19083  ldc.i4.1
0x19084  ldloc.s  7
0x19086  callvirt instance string [mscorlib]System.Object::ToString()
0x1908b  stelem.ref
0x1908c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19091  rethrow
0x19093  ldloc.3
0x19094  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x19099  stloc.s  4
0x1909b  ldloc.s  4
0x1909d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x190a2  ldstr    aCount// "count"
0x190a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x190ac  brfalse.s loc_190D2
0x190ae  ldloc.s  4
0x190b0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x190b5  ldstr    aCount// "count"
0x190ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x190bf  ldarga.s 3
0x190c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x190c6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x190cb  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x190d0  br.s     loc_19101
0x190d2  ldloc.3
0x190d3  ldstr    aCount// "count"
0x190d8  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x190dd  stloc.s  8
0x190df  ldloc.s  8
0x190e1  ldarga.s 3
0x190e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x190e8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x190ed  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x190f2  ldloc.s  4
0x190f4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x190f9  ldloc.s  8
0x190fb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x19100  pop
0x19101  ldloc.3
0x19102  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x19107  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x1910c  stloc.s  5
0x1910e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x19113  stloc.s  6
0x19115  ldloc.s  6
0x19117  ldloc.s  5
0x19119  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1911e  ldloc.2
0x1911f  ldloc.s  6
0x19121  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x19126  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x1912b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x19130  stloc.1
0x19131  ldarg.0
0x19132  ldloc.0
0x19133  ldc.i4.0
0x19134  ldsfld   string [mscorlib]System.String::Empty
0x19139  ldc.i4.2
0x1913a  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x1913f  leave.s  loc_19168
0x19141  stloc.s  9
0x19143  ldloc.s  9
0x19145  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1914a  ldc.i4.s 0x1E
0x1914c  ldstr    aErrorProcessin// "Error Processing QueryData Step. Error "...
0x19151  ldc.i4.1
0x19152  newarr   [mscorlib]System.Object
0x19157  dup
0x19158  ldc.i4.0
0x19159  ldloc.s  9
0x1915b  callvirt instance string [mscorlib]System.Object::ToString()
0x19160  stelem.ref
0x19161  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19166  rethrow
0x19168  ldloc.1
0x19169  ret
```
