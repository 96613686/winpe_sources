# Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::GetWorkflowProperties

- ea: `0x94310`
- end: `0x94740`
- name: `Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::GetWorkflowProperties`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x94160`

## callees

- `0x94310`
- `0x94850`

## string_xrefs

- `0x9444c`: `TriggerOnUpdateAttributeList`
- `0x94451`: `triggeronupdateattributelist`
- `0x94470`: `TriggerOnCreate`
- `0x94475`: `triggeroncreate`
- `0x94494`: `TriggerOnDelete`
- `0x94499`: `triggerondelete`
- `0x944b8`: `AsyncAutodelete`
- `0x944bd`: `asyncautodelete`
- `0x94548`: `CreateStage`
- `0x9454d`: `createstage`
- `0x9456c`: `UpdateStage`
- `0x94571`: `updatestage`
- `0x94590`: `DeleteStage`
- `0x94595`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x94310  ldarg.0
0x94311  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94316  brtrue   loc_94739
0x9431b  ldarg.0
0x9431c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::.ctor()
0x94321  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94326  ldarg.0
0x94327  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9432c  ldstr    aType// "Type"
0x94331  ldstr    aType_0// "type"
0x94336  ldtoken  [mscorlib]System.Int32
0x9433b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94340  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94345  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9434a  ldarg.0
0x9434b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94350  ldstr    aSubprocess// "Subprocess"
0x94355  ldstr    aSubprocess_0// "subprocess"
0x9435a  ldtoken  [mscorlib]System.Boolean
0x9435f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94364  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94369  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9436e  ldarg.0
0x9436f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94374  ldstr    aCategory_0// "Category"
0x94379  ldstr    aCategory// "category"
0x9437e  ldtoken  [mscorlib]System.Int32
0x94383  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94388  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9438d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94392  ldarg.0
0x94393  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94398  ldstr    aBusinessproces// "BusinessProcessType"
0x9439d  ldstr    aBusinessproces_0// "businessprocesstype"
0x943a2  ldtoken  [mscorlib]System.Int32
0x943a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x943ac  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x943b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x943b6  ldarg.0
0x943b7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x943bc  ldstr    aMode// "Mode"
0x943c1  ldstr    aMode_0// "mode"
0x943c6  ldtoken  [mscorlib]System.Int32
0x943cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x943d0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x943d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x943da  ldarg.0
0x943db  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x943e0  ldstr    aLanguagecode_0// "LanguageCode"
0x943e5  ldstr    aLanguagecode// "languagecode"
0x943ea  ldtoken  [mscorlib]System.Int32
0x943ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x943f4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x943f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x943fe  ldarg.0
0x943ff  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94404  ldstr    aScope// "Scope"
0x94409  ldstr    aScope_0// "scope"
0x9440e  ldtoken  [mscorlib]System.Int32
0x94413  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94418  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9441d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94422  ldarg.0
0x94423  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94428  ldstr    aOndemand// "OnDemand"
0x9442d  ldstr    aOndemand_0// "ondemand"
0x94432  ldtoken  [mscorlib]System.Boolean
0x94437  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9443c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94441  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94446  ldarg.0
0x94447  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9444c  ldstr    aTriggeronupdat// "TriggerOnUpdateAttributeList"
0x94451  ldstr    aTriggeronupdat_0// "triggeronupdateattributelist"
0x94456  ldtoken  [mscorlib]System.String
0x9445b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94460  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94465  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9446a  ldarg.0
0x9446b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94470  ldstr    aTriggeroncreat// "TriggerOnCreate"
0x94475  ldstr    aTriggeroncreat_0// "triggeroncreate"
0x9447a  ldtoken  [mscorlib]System.Boolean
0x9447f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94484  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94489  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9448e  ldarg.0
0x9448f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94494  ldstr    aTriggerondelet// "TriggerOnDelete"
0x94499  ldstr    aTriggerondelet_0// "triggerondelete"
0x9449e  ldtoken  [mscorlib]System.Boolean
0x944a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x944a8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x944ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x944b2  ldarg.0
0x944b3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x944b8  ldstr    aAsyncautodelet// "AsyncAutodelete"
0x944bd  ldstr    aAsyncautodelet_0// "asyncautodelete"
0x944c2  ldtoken  [mscorlib]System.Boolean
0x944c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x944cc  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x944d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x944d6  ldarg.0
0x944d7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x944dc  ldstr    aSyncworkflowlo// "SyncWorkflowLogOnFailure"
0x944e1  ldstr    aSyncworkflowlo_0// "syncworkflowlogonfailure"
0x944e6  ldtoken  [mscorlib]System.Boolean
0x944eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x944f0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x944f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x944fa  ldarg.0
0x944fb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94500  ldstr    aStatecode_0// "StateCode"
0x94505  ldstr    aStatecode// "statecode"
0x9450a  ldtoken  [mscorlib]System.Int32
0x9450f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94514  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94519  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9451e  ldarg.0
0x9451f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94524  ldstr    aStatuscode_0// "StatusCode"
0x94529  ldstr    aStatuscode// "statuscode"
0x9452e  ldtoken  [mscorlib]System.Int32
0x94533  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94538  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9453d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94542  ldarg.0
0x94543  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94548  ldstr    aCreatestage// "CreateStage"
0x9454d  ldstr    aCreatestage_0// "createstage"
0x94552  ldtoken  [mscorlib]System.Int32
0x94557  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9455c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94561  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94566  ldarg.0
0x94567  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9456c  ldstr    aUpdatestage// "UpdateStage"
0x94571  ldstr    aUpdatestage_0// "updatestage"
0x94576  ldtoken  [mscorlib]System.Int32
0x9457b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94580  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94585  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9458a  ldarg.0
0x9458b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94590  ldstr    aDeletestage// "DeleteStage"
0x94595  ldstr    aDeletestage_0// "deletestage"
0x9459a  ldtoken  [mscorlib]System.Int32
0x9459f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x945a4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x945a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x945ae  ldarg.0
0x945af  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x945b4  ldstr    aRank// "Rank"
0x945b9  ldstr    aRank_0// "rank"
0x945be  ldtoken  [mscorlib]System.Int32
0x945c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x945c8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x945cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x945d2  ldarg.0
0x945d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x945d8  ldstr    aProcessorder// "processorder"
0x945dd  ldstr    aProcessorder// "processorder"
0x945e2  ldtoken  [mscorlib]System.Int32
0x945e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x945ec  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x945f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x945f6  ldarg.0
0x945f7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x945fc  ldstr    aProcessroleass// "processroleassignment"
0x94601  ldstr    aProcessroleass// "processroleassignment"
0x94606  ldtoken  [mscorlib]System.String
0x9460b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94610  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94615  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9461a  ldarg.0
0x9461b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94620  ldstr    aRunas// "RunAs"
0x94625  ldstr    aRunas_0// "runas"
0x9462a  ldtoken  [mscorlib]System.Int32
0x9462f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94634  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94639  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x9463e  ldarg.0
0x9463f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94644  ldstr    aUniquename_0// "UniqueName"
0x94649  ldstr    aUniquename// "uniquename"
0x9464e  ldtoken  [mscorlib]System.String
0x94653  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x94658  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9465d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94662  ldarg.0
0x94663  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x94668  ldstr    aIstransacted// "IsTransacted"
0x9466d  ldstr    aIstransacted_0// "istransacted"
0x94672  ldtoken  [mscorlib]System.Boolean
0x94677  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9467c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94681  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94686  ldarg.0
0x94687  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9468c  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x94691  ldstr    aIntroducedvers// "introducedversion"
0x94696  ldtoken  [mscorlib]System.String
0x9469b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x946a0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x946a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x946aa  ldarg.0
0x946ab  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x946b0  ldstr    aIscustomizable_0// "IsCustomizable"
0x946b5  ldstr    aIscustomizable// "iscustomizable"
0x946ba  ldtoken  [mscorlib]System.Boolean
0x946bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x946c4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x946c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x946ce  ldarg.0
0x946cf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x946d4  ldstr    aFormid_0// "FormId"
0x946d9  ldstr    aFormid// "formid"
0x946de  ldtoken  [mscorlib]System.Guid
0x946e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x946e8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x946ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x946f2  ldarg.1
0x946f3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x946f8  ldstr    aWorkflow// "Workflow"
0x946fd  ldc.i4.0
0x946fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x94703  stloc.0
0x94704  ldloc.0
0x94705  brfalse.s loc_94739
0x94707  ldloc.0
0x94708  ldstr    aRendererobject_0// "rendererobjecttypecode"
0x9470d  ldc.i4.1
0x9470e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x94713  brfalse.s loc_94739
0x94715  ldarg.0
0x94716  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9471b  ldstr    aRendererobject// "RendererObjectTypeCode"
0x94720  ldstr    aRendererobject_0// "rendererobjecttypecode"
0x94725  ldtoken  [mscorlib]System.Int32
0x9472a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9472f  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x94734  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap>::Add(var<u1>)
0x94739  ldarg.0
0x9473a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.WorkflowPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.WorkflowConvertor::_workflowProperties
0x9473f  ret
```
