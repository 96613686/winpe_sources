# Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::ValidateRequiredField

- ea: `0x196a0`
- end: `0x1981d`
- name: `Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::ValidateRequiredField`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x19660`

## callees

- `0x7390`
- `0x14770`
- `0x14ea0`
- `0x14ee0`
- `0x196a0`
- `0x19820`
- `0x19860`

## string_xrefs

- `0x196b7`: `Cannot find record to be updated`

## pseudocode

```c

```

## disassembly

```asm
0x196a0  ldarg.1
0x196a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x196a6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x196ab  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x196b0  brfalse.s loc_196D2
0x196b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x196b7  ldstr    aCannotFindReco_2// "Cannot find record to be updated"
0x196bc  ldc.i4.0
0x196bd  newarr   [mscorlib]System.Object
0x196c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x196c7  ldc.i4   0x80045031
0x196cc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x196d1  throw
0x196d2  ldarg.3
0x196d3  ldc.i4.1
0x196d4  bne.un   loc_1981C
0x196d9  ldc.i4.0
0x196da  stloc.0
0x196db  ldarg.0
0x196dc  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x196e1  brfalse.s loc_196EC
0x196e3  ldarg.0
0x196e4  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::PreImageExists()
0x196e9  stloc.0
0x196ea  br.s     loc_19703
0x196ec  ldarg.0
0x196ed  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x196f2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x196f7  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x196fc  brtrue.s loc_19701
0x196fe  ldc.i4.0
0x196ff  br.s     loc_19702
0x19701  ldc.i4.1
0x19702  stloc.0
0x19703  ldloc.0
0x19704  brtrue.s loc_19735
0x19706  ldarg.0
0x19707  ldarg.1
0x19708  ldarg.2
0x19709  call     instance object Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::GetTargetEntityPropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string propertyName)
0x1970e  brtrue.s loc_19734
0x19710  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19715  ldstr    aAttribute0Cann// "Attribute '{0}' cannot be NULL"
0x1971a  ldc.i4.1
0x1971b  newarr   [mscorlib]System.Object
0x19720  dup
0x19721  ldc.i4.0
0x19722  ldarg.2
0x19723  stelem.ref
0x19724  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19729  ldc.i4   0x80040200
0x1972e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19733  throw
0x19734  ret
0x19735  ldarg.0
0x19736  ldarg.1
0x19737  ldarg.2
0x19738  call     instance object Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::GetTargetEntityPropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string propertyName)
0x1973d  stloc.1
0x1973e  ldloc.1
0x1973f  brtrue   loc_197CC
0x19744  ldarg.0
0x19745  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x1974a  brtrue.s loc_19789
0x1974c  ldarg.0
0x1974d  ldarg.0
0x1974e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19753  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x19758  ldstr    aPrebusinessent// "PreBusinessEntity"
0x1975d  ldarg.2
0x1975e  call     instance object Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::TryGetImagePropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection entityImages, string key, string propertyName)
0x19763  brtrue.s loc_197CB
0x19765  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1976a  ldstr    aAttribute0Cann// "Attribute '{0}' cannot be NULL"
0x1976f  ldc.i4.1
0x19770  newarr   [mscorlib]System.Object
0x19775  dup
0x19776  ldc.i4.0
0x19777  ldarg.2
0x19778  stelem.ref
0x19779  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1977e  ldc.i4   0x80040200
0x19783  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19788  throw
0x19789  ldarg.0
0x1978a  ldarg.0
0x1978b  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19790  castclass Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x19795  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PreEntityImages()
0x1979a  ldstr    aPrebusinessent// "PreBusinessEntity"
0x1979f  ldarg.2
0x197a0  call     instance object Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::TryGetImagePropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection entityImages, string key, string propertyName)
0x197a5  brtrue.s loc_197CB
0x197a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x197ac  ldstr    aAttribute0Cann// "Attribute '{0}' cannot be NULL"
0x197b1  ldc.i4.1
0x197b2  newarr   [mscorlib]System.Object
0x197b7  dup
0x197b8  ldc.i4.0
0x197b9  ldarg.2
0x197ba  stelem.ref
0x197bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x197c0  ldc.i4   0x80040200
0x197c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x197ca  throw
0x197cb  ret
0x197cc  ldloc.1
0x197cd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x197d2  beq.s    loc_197F8
0x197d4  ldloc.1
0x197d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x197da  ldtoken  [mscorlib]System.String
0x197df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x197e4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x197e9  brfalse.s loc_1981C
0x197eb  ldloc.1
0x197ec  castclass [mscorlib]System.String
0x197f1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x197f6  brtrue.s loc_1981C
0x197f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x197fd  ldstr    aAttribute0Cann// "Attribute '{0}' cannot be NULL"
0x19802  ldc.i4.1
0x19803  newarr   [mscorlib]System.Object
0x19808  dup
0x19809  ldc.i4.0
0x1980a  ldarg.2
0x1980b  stelem.ref
0x1980c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19811  ldc.i4   0x80040200
0x19816  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1981b  throw
0x1981c  ret
```
