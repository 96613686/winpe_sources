# Microsoft.Crm.Workflow.ClientActivities.SetMessage::Execute

- ea: `0x1ab50`
- end: `0x1abbb`
- name: `Microsoft.Crm.Workflow.ClientActivities.SetMessage::Execute`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x19d20`
- `0x1ab50`

## string_xrefs

- `0x1ab7a`: `recommendation`

## pseudocode

```c

```

## disassembly

```asm
0x1ab50  ldarg.0
0x1ab51  ldfld    class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::_level
0x1ab56  brfalse.s loc_1ABA8
0x1ab58  ldarg.0
0x1ab59  ldfld    class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::_level
0x1ab5e  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1ab63  brfalse.s loc_1ABA8
0x1ab65  ldarg.0
0x1ab66  ldfld    class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::_level
0x1ab6b  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1ab70  callvirt instance string [mscorlib]System.Object::ToString()
0x1ab75  callvirt instance string [mscorlib]System.String::ToLower()
0x1ab7a  ldstr    aRecommendation// "recommendation"
0x1ab7f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1ab84  brtrue.s loc_1ABA7
0x1ab86  ldarg.0
0x1ab87  ldfld    class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetMessage::_level
0x1ab8c  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1ab91  callvirt instance string [mscorlib]System.Object::ToString()
0x1ab96  callvirt instance string [mscorlib]System.String::ToLower()
0x1ab9b  ldstr    aWarning// "warning"
0x1aba0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1aba5  brfalse.s loc_1ABA8
0x1aba7  ret
0x1aba8  ldarg.1
0x1aba9  callvirt T0x2B000013
0x1abae  castclass Microsoft.Crm.Workflow.Services.SetMessageService
0x1abb3  ldarg.1
0x1abb4  ldarg.0
0x1abb5  callvirt instance void Microsoft.Crm.Workflow.Services.SetMessageService::Execute(class [System.Activities]System.Activities.ActivityContext executionContext, class Microsoft.Crm.Workflow.ClientActivities.SetMessage setMessage)
0x1abba  ret
```
