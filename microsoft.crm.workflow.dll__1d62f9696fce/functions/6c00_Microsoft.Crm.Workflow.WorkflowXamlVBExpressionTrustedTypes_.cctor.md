# Microsoft.Crm.Workflow.WorkflowXamlVBExpressionTrustedTypes::.cctor

- ea: `0x6c00`
- end: `0x722c`
- name: `Microsoft.Crm.Workflow.WorkflowXamlVBExpressionTrustedTypes::.cctor`
- size: `1580`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x6d90`: `Microsoft.Xrm.Sdk.Workflow.Activities.CreateEntity`
- `0x6dd8`: `Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate`
- `0x6e20`: `Microsoft.Xrm.Sdk.Workflow.Activities.UpdateEntity`
- `0x6e68`: `Microsoft.Crm.Workflow.Activities.Composite`
- `0x70c0`: `Microsoft.Xrm.Sdk.InvalidPluginExecutionException`
- `0x71a4`: `System.Windows.Markup.NullExtension`

## pseudocode

```c

```

## disassembly

```asm
0x6c00  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x6c05  dup
0x6c06  ldstr    aMscorlib// "mscorlib"
0x6c0b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c10  pop
0x6c11  dup
0x6c12  ldstr    aSystemActiviti// "System.Activities"
0x6c17  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c1c  pop
0x6c1d  dup
0x6c1e  ldstr    aSystemXaml// "System.Xaml"
0x6c23  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c28  pop
0x6c29  dup
0x6c2a  ldstr    aMicrosoftXrmSd// "Microsoft.Xrm.Sdk.Workflow"
0x6c2f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c34  pop
0x6c35  dup
0x6c36  ldstr    aMicrosoftCrm// "Microsoft.Crm"
0x6c3b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c40  pop
0x6c41  dup
0x6c42  ldstr    aMicrosoftCrmWo// "Microsoft.Crm.Workflow"
0x6c47  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c4c  pop
0x6c4d  dup
0x6c4e  ldstr    aMicrosoftXrmSd_0// "Microsoft.Xrm.Sdk"
0x6c53  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c58  pop
0x6c59  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Workflow.WorkflowXamlVBExpressionTrustedTypes::AllowedAssemblies
0x6c5e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x6c63  dup
0x6c64  ldstr    aSystemBoolean// "System.Boolean"
0x6c69  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c6e  pop
0x6c6f  dup
0x6c70  ldstr    aSystemByte// "System.Byte"
0x6c75  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c7a  pop
0x6c7b  dup
0x6c7c  ldstr    aSystemChar// "System.Char"
0x6c81  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c86  pop
0x6c87  dup
0x6c88  ldstr    aSystemDatetime// "System.DateTime"
0x6c8d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c92  pop
0x6c93  dup
0x6c94  ldstr    aSystemDatetime_0// "System.DateTime.MinValue"
0x6c99  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6c9e  pop
0x6c9f  dup
0x6ca0  ldstr    aSystemDatetime_1// "System.DateTime.MaxValue"
0x6ca5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6caa  pop
0x6cab  dup
0x6cac  ldstr    aSystemDouble// "System.Double"
0x6cb1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cb6  pop
0x6cb7  dup
0x6cb8  ldstr    aSystemDecimal// "System.Decimal"
0x6cbd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cc2  pop
0x6cc3  dup
0x6cc4  ldstr    aSystemGuid// "System.Guid"
0x6cc9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cce  pop
0x6ccf  dup
0x6cd0  ldstr    aSystemInt16// "System.Int16"
0x6cd5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cda  pop
0x6cdb  dup
0x6cdc  ldstr    aSystemInt32// "System.Int32"
0x6ce1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ce6  pop
0x6ce7  dup
0x6ce8  ldstr    aSystemInt64// "System.Int64"
0x6ced  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cf2  pop
0x6cf3  dup
0x6cf4  ldstr    aSystemObject// "System.Object"
0x6cf9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6cfe  pop
0x6cff  dup
0x6d00  ldstr    aSystemString// "System.String"
0x6d05  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d0a  pop
0x6d0b  dup
0x6d0c  ldstr    aSystemType// "System.Type"
0x6d11  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d16  pop
0x6d17  dup
0x6d18  ldstr    aDatetimeUtcnow// "DateTime.UtcNow"
0x6d1d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d22  pop
0x6d23  dup
0x6d24  ldstr    aDatetimeMaxval// "DateTime.MaxValue"
0x6d29  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d2e  pop
0x6d2f  dup
0x6d30  ldstr    aDatetimeMinval// "DateTime.MinValue"
0x6d35  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d3a  pop
0x6d3b  dup
0x6d3c  ldstr    aMicrosoftXrmSd_1// "Microsoft.Xrm.Sdk.Workflow.ArgumentRequ"...
0x6d41  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d46  pop
0x6d47  dup
0x6d48  ldstr    aMicrosoftXrmSd_2// "Microsoft.Xrm.Sdk.Workflow.ArgumentTarg"...
0x6d4d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d52  pop
0x6d53  dup
0x6d54  ldstr    aMicrosoftXrmSd_3// "Microsoft.Xrm.Sdk.Workflow.ArgumentDesc"...
0x6d59  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d5e  pop
0x6d5f  dup
0x6d60  ldstr    aMicrosoftXrmSd_4// "Microsoft.Xrm.Sdk.Workflow.ArgumentDire"...
0x6d65  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d6a  pop
0x6d6b  dup
0x6d6c  ldstr    aMicrosoftXrmSd_5// "Microsoft.Xrm.Sdk.Workflow.ArgumentEnti"...
0x6d71  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d76  pop
0x6d77  dup
0x6d78  ldstr    aMicrosoftXrmSd_6// "Microsoft.Xrm.Sdk.Workflow.Activities.A"...
0x6d7d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d82  pop
0x6d83  dup
0x6d84  ldstr    aMicrosoftXrmSd_7// "Microsoft.Xrm.Sdk.Workflow.Activities.A"...
0x6d89  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d8e  pop
0x6d8f  dup
0x6d90  ldstr    aMicrosoftXrmSd_8// "Microsoft.Xrm.Sdk.Workflow.Activities.C"...
0x6d95  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6d9a  pop
0x6d9b  dup
0x6d9c  ldstr    aMicrosoftXrmSd_9// "Microsoft.Xrm.Sdk.Workflow.Activities.G"...
0x6da1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6da6  pop
0x6da7  dup
0x6da8  ldstr    aMicrosoftXrmSd_10// "Microsoft.Xrm.Sdk.Workflow.Activities.G"...
0x6dad  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6db2  pop
0x6db3  dup
0x6db4  ldstr    aMicrosoftXrmSd_11// "Microsoft.Xrm.Sdk.Workflow.Activities.R"...
0x6db9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6dbe  pop
0x6dbf  dup
0x6dc0  ldstr    aMicrosoftXrmSd_12// "Microsoft.Xrm.Sdk.Workflow.Activities.R"...
0x6dc5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6dca  pop
0x6dcb  dup
0x6dcc  ldstr    aMicrosoftXrmSd_13// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6dd1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6dd6  pop
0x6dd7  dup
0x6dd8  ldstr    aMicrosoftXrmSd_14// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6ddd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6de2  pop
0x6de3  dup
0x6de4  ldstr    aMicrosoftXrmSd_15// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6de9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6dee  pop
0x6def  dup
0x6df0  ldstr    aMicrosoftXrmSd_16// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6df5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6dfa  pop
0x6dfb  dup
0x6dfc  ldstr    aMicrosoftXrmSd_17// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6e01  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e06  pop
0x6e07  dup
0x6e08  ldstr    aMicrosoftXrmSd_18// "Microsoft.Xrm.Sdk.Workflow.Activities.S"...
0x6e0d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e12  pop
0x6e13  dup
0x6e14  ldstr    aMicrosoftXrmSd_19// "Microsoft.Xrm.Sdk.Workflow.Activities.P"...
0x6e19  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e1e  pop
0x6e1f  dup
0x6e20  ldstr    aMicrosoftXrmSd_20// "Microsoft.Xrm.Sdk.Workflow.Activities.U"...
0x6e25  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e2a  pop
0x6e2b  dup
0x6e2c  ldstr    aMicrosoftXrmSd_21// "Microsoft.Xrm.Sdk.Workflow.Activities.W"...
0x6e31  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e36  pop
0x6e37  dup
0x6e38  ldstr    aMicrosoftXrmSd_22// "Microsoft.Xrm.Sdk.Workflow.Activities.W"...
0x6e3d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e42  pop
0x6e43  dup
0x6e44  ldstr    aMicrosoftCrm// "Microsoft.Crm"
0x6e49  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e4e  pop
0x6e4f  dup
0x6e50  ldstr    aMicrosoftCrmWo// "Microsoft.Crm.Workflow"
0x6e55  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e5a  pop
0x6e5b  dup
0x6e5c  ldstr    aMicrosoftCrmWo_0// "Microsoft.Crm.Workflow.Activities.Start"...
0x6e61  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e66  pop
0x6e67  dup
0x6e68  ldstr    aMicrosoftCrmWo_1// "Microsoft.Crm.Workflow.Activities.Compo"...
0x6e6d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e72  pop
0x6e73  dup
0x6e74  ldstr    aMicrosoftCrmWo_2// "Microsoft.Crm.Workflow.Activities.Condi"...
0x6e79  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e7e  pop
0x6e7f  dup
0x6e80  ldstr    aMicrosoftCrmWo_3// "Microsoft.Crm.Workflow.Activities.Condi"...
0x6e85  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e8a  pop
0x6e8b  dup
0x6e8c  ldstr    aMicrosoftCrmWo_4// "Microsoft.Crm.Workflow.Activities.Conve"...
0x6e91  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6e96  pop
0x6e97  dup
0x6e98  ldstr    aMicrosoftCrmWo_5// "Microsoft.Crm.Workflow.Activities.Evalu"...
0x6e9d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ea2  pop
0x6ea3  dup
0x6ea4  ldstr    aMicrosoftCrmWo_6// "Microsoft.Crm.Workflow.Activities.Evalu"...
0x6ea9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6eae  pop
0x6eaf  dup
0x6eb0  ldstr    aMicrosoftCrmWo_7// "Microsoft.Crm.Workflow.Activities.Evalu"...
0x6eb5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6eba  pop
0x6ebb  dup
0x6ebc  ldstr    aMicrosoftCrmWo_8// "Microsoft.Crm.Workflow.Activities.Inter"...
0x6ec1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ec6  pop
0x6ec7  dup
0x6ec8  ldstr    aMicrosoftCrmWo_9// "Microsoft.Crm.Workflow.Activities.Inter"...
0x6ecd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ed2  pop
0x6ed3  dup
0x6ed4  ldstr    aMicrosoftCrmWo_10// "Microsoft.Crm.Workflow.Activities.Invok"...
0x6ed9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ede  pop
0x6edf  dup
0x6ee0  ldstr    aMicrosoftCrmWo_11// "Microsoft.Crm.Workflow.Activities.Query"...
0x6ee5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6eea  pop
0x6eeb  dup
0x6eec  ldstr    aMicrosoftCrmWo_12// "Microsoft.Crm.Workflow.ClientActivities"...
0x6ef1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6ef6  pop
0x6ef7  dup
0x6ef8  ldstr    aMicrosoftCrmWo_13// "Microsoft.Crm.Workflow.ClientActivities"...
0x6efd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f02  pop
0x6f03  dup
0x6f04  ldstr    aMicrosoftCrmWo_14// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f09  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f0e  pop
0x6f0f  dup
0x6f10  ldstr    aMicrosoftCrmWo_15// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f15  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f1a  pop
0x6f1b  dup
0x6f1c  ldstr    aMicrosoftCrmWo_16// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f21  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f26  pop
0x6f27  dup
0x6f28  ldstr    aMicrosoftCrmWo_17// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f2d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f32  pop
0x6f33  dup
0x6f34  ldstr    aMicrosoftCrmWo_18// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f39  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f3e  pop
0x6f3f  dup
0x6f40  ldstr    aMicrosoftCrmWo_19// "Microsoft.Crm.Workflow.ClientActivities"...
0x6f45  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f4a  pop
0x6f4b  dup
0x6f4c  ldstr    aMicrosoftCrmWo_20// "Microsoft.Crm.Workflow.InteractionActiv"...
0x6f51  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f56  pop
0x6f57  dup
0x6f58  ldstr    aMicrosoftXrmSd_23// "Microsoft.Xrm.Sdk.Workflow.WorkflowProp"...
0x6f5d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f62  pop
0x6f63  dup
0x6f64  ldstr    aMicrosoftXrmSd_24// "Microsoft.Xrm.Sdk.Workflow.WorkflowProp"...
0x6f69  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f6e  pop
0x6f6f  dup
0x6f70  ldstr    aMicrosoftXrmSd_25// "Microsoft.Xrm.Sdk.Workflow.WorkflowProp"...
0x6f75  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f7a  pop
0x6f7b  dup
0x6f7c  ldstr    aMicrosoftXrmSd_26// "Microsoft.Xrm.Sdk.Workflow.WorkflowProp"...
0x6f81  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x6f86  pop
0x6f87  dup
  ... truncated ...
```
