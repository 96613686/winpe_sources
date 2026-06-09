# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateQueryStep

- ea: `0x2340`
- end: `0x24f9`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateQueryStep`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x2340`
- `0x2500`
- `0x8b90`
- `0x8f00`

## string_xrefs

- `0x24d0`: `Invalid XML`

## pseudocode

```c

```

## disassembly

```asm
0x2340  ldarg.0
0x2341  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2346  ldarg.3
0x2347  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x234c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2351  stloc.0
0x2352  ldloc.0
0x2353  ldarg.1
0x2354  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x2359  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x235e  stloc.1
0x235f  ldarg.0
0x2360  ldloc.0
0x2361  ldarg.s  4
0x2363  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x2368  ldarg.2
0x2369  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x236e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x2373  ldstr    aQueryactivity// "queryactivity"
0x2378  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x237d  stloc.2
0x237e  ldloc.2
0x237f  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x2384  brfalse  loc_24E0
0x2389  ldloc.2
0x238a  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x238f  stloc.3
0x2390  ldloc.3
0x2391  ldstr    aSteplabel// "steplabel"
0x2396  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x239b  stloc.s  4
0x239d  ldloc.3
0x239e  ldstr    aOriginalfetch// "originalFetch"
0x23a3  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x23a8  stloc.s  5
0x23aa  ldloc.3
0x23ab  ldstr    aOriginallayout// "originalLayout"
0x23b0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x23b5  stloc.s  6
0x23b7  ldloc.s  4
0x23b9  brfalse  loc_24D0
0x23be  ldloc.s  5
0x23c0  brfalse  loc_24D0
0x23c5  ldloc.1
0x23c6  ldloc.s  4
0x23c8  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x23cd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x23d2  ldloc.3
0x23d3  ldstr    aModifiedfetch// "modifiedFetch"
0x23d8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x23dd  stloc.s  7
0x23df  ldloc.3
0x23e0  ldstr    aConditions// "conditions"
0x23e5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x23ea  stloc.s  8
0x23ec  ldloc.s  7
0x23ee  brfalse.s loc_2402
0x23f0  ldloc.s  8
0x23f2  brfalse.s loc_2402
0x23f4  ldarg.0
0x23f5  ldloc.1
0x23f6  ldloc.0
0x23f7  ldloc.s  7
0x23f9  ldloc.s  8
0x23fb  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateQueryforAdvacedMode(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep queryStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [System.Xml]System.Xml.XPath.XPathNavigator advancedModeNode, class [System.Xml]System.Xml.XPath.XPathNavigator conditionsNode)
0x2400  br.s     loc_2426
0x2402  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2407  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x240c  stloc.s  0xB
0x240e  ldloc.1
0x240f  ldloc.s  0xB
0x2411  ldloc.0
0x2412  ldc.i4.s 0xE
0x2414  ldloc.s  5
0x2416  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x241b  ldc.i4.0
0x241c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.PropertyExpressionBuilder::CreateExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, bool)
0x2421  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2426  ldloc.1
0x2427  ldloc.s  5
0x2429  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x242e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_OriginalFetchXml(string)
0x2433  ldloc.s  6
0x2435  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x243a  brfalse.s loc_2449
0x243c  ldloc.1
0x243d  ldloc.s  6
0x243f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2444  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_OriginalLayoutXml(string)
0x2449  ldloc.s  5
0x244b  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x2450  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2455  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::FromFetch(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x245a  stloc.s  9
0x245c  ldsfld   string [mscorlib]System.String::Empty
0x2461  stloc.s  0xA
0x2463  ldloc.s  9
0x2465  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x246a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x246f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression>::GetEnumerator()
0x2474  stloc.s  0xC
0x2476  br.s     loc_249B
0x2478  ldloca.s 0xC
0x247a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression>::get_Current()
0x247f  stloc.s  0xD
0x2481  ldloc.s  0xA
0x2483  ldloc.s  0xD
0x2485  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression::get_Attribute()
0x248a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x248f  ldstr    asc_AB88// ";"
0x2494  call     string [mscorlib]System.String::Concat(string, string, string)
0x2499  stloc.s  0xA
0x249b  ldloca.s 0xC
0x249d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression>::MoveNext()
0x24a2  brtrue.s loc_2478
0x24a4  leave.s  loc_24B4
0x24a6  ldloca.s 0xC
0x24a8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.AttributeExpression>
0x24ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24b3  endfinally
0x24b4  ldloc.1
0x24b5  ldloc.s  0xA
0x24b7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_AttributeList(string)
0x24bc  ldloc.1
0x24bd  ldloc.s  9
0x24bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x24c4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x24c9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_EntityName(string)
0x24ce  br.s     loc_24E0
0x24d0  ldstr    aInvalidXml// "Invalid XML"
0x24d5  ldc.i4   0x80004005
0x24da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24df  throw
0x24e0  ldarg.0
0x24e1  ldloc.0
0x24e2  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x24e7  stloc.s  0xE
0x24e9  leave.s  loc_24F6
0x24eb  stloc.s  0xF
0x24ed  ldarg.0
0x24ee  ldloc.s  0xF
0x24f0  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x24f5  throw
0x24f6  ldloc.s  0xE
0x24f8  ret
```
