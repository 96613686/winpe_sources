# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::ExportRuleDefinition

- ea: `0x72860`
- end: `0x72a1d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::ExportRuleDefinition`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x727e0`

## callees

- `0x391e0`
- `0x39930`
- `0x39940`
- `0x3b380`
- `0x72860`
- `0x72a20`
- `0x72a40`
- `0x72aa0`
- `0x72b40`
- `0x72bd0`

## string_xrefs

- `0x72912`: `ChannelAccessProfileRuleId`
- `0x72900`: `channelaccessprofileruleid`
- `0x7288c`: `ChannelAccessProfileRule`
- `0x72945`: `ChannelAccessProfileRuleItem`

## pseudocode

```c

```

## disassembly

```asm
0x72860  ldnull
0x72861  stloc.0
0x72862  ldarg.0
0x72863  ldarg.0
0x72864  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::_profileRules
0x72869  ldarg.0
0x7286a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::_context
0x7286f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveProfileRules(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> profileRuleIds, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72874  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x72879  stloc.1
0x7287a  br       loc_729FB
0x7287f  ldloc.1
0x72880  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x72885  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x7288a  stloc.2
0x7288b  ldarg.1
0x7288c  ldstr    aChannelaccessp_16// "ChannelAccessProfileRule"
0x72891  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x72896  stloc.3
0x72897  ldloc.2
0x72898  ldstr    aSolutionid// "solutionid"
0x7289d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x728a2  unbox.any [mscorlib]System.Guid
0x728a7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x728ac  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x728b1  ldloc.2
0x728b2  ldstr    aIsmanaged// "ismanaged"
0x728b7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x728bc  unbox.any [mscorlib]System.Boolean
0x728c1  stloc.s  4
0x728c3  brfalse.s loc_728DC
0x728c5  ldarg.0
0x728c6  ldstr    aProfileruleatt// "ProfileRuleAttributes"
0x728cb  ldarg.1
0x728cc  ldloc.3
0x728cd  ldloc.2
0x728ce  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x728d3  ldloc.s  4
0x728d5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x728da  br.s     loc_728FF
0x728dc  ldarg.0
0x728dd  ldstr    aProfileruleatt_0// "ProfileRuleAttribute"
0x728e2  ldarg.1
0x728e3  ldloc.3
0x728e4  ldloc.2
0x728e5  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x728ea  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x728ef  ldloc.3
0x728f0  ldstr    aUnmodified// "unmodified"
0x728f5  ldstr    a1// "1"
0x728fa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x728ff  ldloc.2
0x72900  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72905  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7290a  unbox.any [mscorlib]System.Guid
0x7290f  stloc.s  5
0x72911  ldloc.3
0x72912  ldstr    aChannelaccessp_2// "ChannelAccessProfileRuleId"
0x72917  ldloca.s 5
0x72919  constrained. [mscorlib]System.Guid
0x7291f  callvirt instance string [mscorlib]System.Object::ToString()
0x72924  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x72929  ldloc.3
0x7292a  ldstr    aName_1// "Name"
0x7292f  ldloc.2
0x72930  ldstr    aName// "name"
0x72935  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7293a  castclass [mscorlib]System.String
0x7293f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x72944  ldarg.0
0x72945  ldstr    aChannelaccessp_18// "ChannelAccessProfileRuleItem"
0x7294a  ldloc.s  5
0x7294c  ldarg.0
0x7294d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::_context
0x72952  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveRuleItems(string entityName, valuetype [mscorlib]System.Guid profileRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72957  stloc.0
0x72958  ldarg.0
0x72959  ldarg.1
0x7295a  ldloc.3
0x7295b  ldloc.s  5
0x7295d  ldloc.2
0x7295e  ldstr    aName// "name"
0x72963  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x72968  castclass [mscorlib]System.String
0x7296d  ldloc.0
0x7296e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::ExportProfileRuleItems(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode profileruleNode, valuetype [mscorlib]System.Guid profileRuleId, string profileRuleName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection profileRuleCollection)
0x72973  ldloc.2
0x72974  ldstr    aWorkflowid_0// "workflowid"
0x72979  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x7297e  brtrue.s loc_729B6
0x72980  ldloc.2
0x72981  ldstr    aWorkflowid_0// "workflowid"
0x72986  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7298b  unbox.any [mscorlib]System.Guid
0x72990  stloc.s  6
0x72992  ldloca.s 6
0x72994  constrained. [mscorlib]System.Guid
0x7299a  callvirt instance string [mscorlib]System.Object::ToString()
0x7299f  ldarg.0
0x729a0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::_context
0x729a5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveWorkflow(string WorkflowId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x729aa  stloc.s  7
0x729ac  ldarg.0
0x729ad  ldarg.1
0x729ae  ldloc.3
0x729af  ldloc.s  7
0x729b1  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::ExportWorkflow(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode ProfileRuleNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity workflowEntity)
0x729b6  ldarg.2
0x729b7  ldloc.3
0x729b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x729bd  pop
0x729be  ldarg.0
0x729bf  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::_tracer
0x729c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x729c9  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileRuleExportSuccessMessage
0x729ce  ldc.i4.2
0x729cf  newarr   [mscorlib]System.Object
0x729d4  dup
0x729d5  ldc.i4.0
0x729d6  ldloc.2
0x729d7  ldstr    aName// "name"
0x729dc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x729e1  castclass [mscorlib]System.String
0x729e6  stelem.ref
0x729e7  dup
0x729e8  ldc.i4.1
0x729e9  ldloc.s  5
0x729eb  box      [mscorlib]System.Guid
0x729f0  stelem.ref
0x729f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x729f6  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x729fb  ldloc.1
0x729fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x72a01  brtrue   loc_7287F
0x72a06  leave.s  loc_72A1C
0x72a08  ldloc.1
0x72a09  isinst   [mscorlib]System.IDisposable
0x72a0e  stloc.s  8
0x72a10  ldloc.s  8
0x72a12  brfalse.s loc_72A1B
0x72a14  ldloc.s  8
0x72a16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72a1b  endfinally
0x72a1c  ret
```
