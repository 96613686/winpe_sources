# Microsoft.Crm.Application.Components.Platform.Utility.NotificationsGeneratorReflectionUtility::ServiceNotificationsGenerator

- ea: `0x99280`
- end: `0x992b4`
- name: `Microsoft.Crm.Application.Components.Platform.Utility.NotificationsGeneratorReflectionUtility::ServiceNotificationsGenerator`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x805b0`

## string_xrefs

- `0x99280`: `Microsoft.Crm.Service.Application.Components.Platform`
- `0x9928a`: `Microsoft.Crm.Service.Application.Platform.ServiceNotificationsGeneratorFactory`

## pseudocode

```c

```

## disassembly

```asm
0x99280  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Compo"...
0x99285  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x9928a  ldstr    aMicrosoftCrmSe_8// "Microsoft.Crm.Service.Application.Platf"...
0x9928f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x99294  ldstr    aGetentitynotif// "GetEntityNotificationsGenerator"
0x99299  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x9929e  ldnull
0x9929f  ldc.i4.1
0x992a0  newarr   [mscorlib]System.Object
0x992a5  dup
0x992a6  ldc.i4.0
0x992a7  ldarg.0
0x992a8  stelem.ref
0x992a9  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x992ae  castclass Microsoft.Crm.Application.Platform.Notifications.Entities.EntityNotificationsGenerator
0x992b3  ret
```
