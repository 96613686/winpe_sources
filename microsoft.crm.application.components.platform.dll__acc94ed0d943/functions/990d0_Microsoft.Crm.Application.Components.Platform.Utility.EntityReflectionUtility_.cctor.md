# Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::.cctor

- ea: `0x990d0`
- end: `0x991bb`
- name: `Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::.cctor`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9913c`: `Microsoft.Crm.Service.Application.Components.Platform`
- `0x990d0`: `Microsoft.Crm.Common.Application.Platform`
- `0x99172`: `Microsoft.Crm.Common.Application.Platform`
- `0x990da`: `Microsoft.Crm.Common.Application.Platform.CommonEntityFactory`
- `0x990e4`: `CreateEntity`
- `0x9911a`: `CreateEntity`
- `0x99150`: `CreateEntity`
- `0x99146`: `Microsoft.Crm.Service.Application.Platform.ServiceEntityfactory`

## pseudocode

```c

```

## disassembly

```asm
0x990d0  ldstr    aMicrosoftCrmCo_3// "Microsoft.Crm.Common.Application.Platfo"...
0x990d5  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x990da  ldstr    aMicrosoftCrmCo_4// "Microsoft.Crm.Common.Application.Platfo"...
0x990df  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x990e4  ldstr    aCreateentity// "CreateEntity"
0x990e9  ldc.i4.1
0x990ea  newarr   [mscorlib]System.Type
0x990ef  dup
0x990f0  ldc.i4.0
0x990f1  ldtoken  Microsoft.Crm.Application.Platform.EntityType
0x990f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x990fb  stelem.ref
0x990fc  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x99101  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::commonCreateEntity
0x99106  ldstr    aMicrosoftCrmMa// "Microsoft.Crm.Marketing.Application.Pla"...
0x9910b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x99110  ldstr    aMicrosoftCrmMa_0// "Microsoft.Crm.Marketing.Application.Pla"...
0x99115  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x9911a  ldstr    aCreateentity// "CreateEntity"
0x9911f  ldc.i4.1
0x99120  newarr   [mscorlib]System.Type
0x99125  dup
0x99126  ldc.i4.0
0x99127  ldtoken  Microsoft.Crm.Application.Platform.EntityType
0x9912c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99131  stelem.ref
0x99132  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x99137  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::marketingCreateEntity
0x9913c  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Compo"...
0x99141  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x99146  ldstr    aMicrosoftCrmSe_7// "Microsoft.Crm.Service.Application.Platf"...
0x9914b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x99150  ldstr    aCreateentity// "CreateEntity"
0x99155  ldc.i4.1
0x99156  newarr   [mscorlib]System.Type
0x9915b  dup
0x9915c  ldc.i4.0
0x9915d  ldtoken  Microsoft.Crm.Application.Platform.EntityType
0x99162  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99167  stelem.ref
0x99168  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x9916d  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::serviceCreateEntity
0x99172  ldstr    aMicrosoftCrmCo_3// "Microsoft.Crm.Common.Application.Platfo"...
0x99177  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x9917c  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0x99181  ldsfld   class <>c <>c::<>9
0x99186  ldftn    instance bool <>c::<.cctor>b__4_0(class [mscorlib]System.Type t)
0x9918c  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::.ctor(object, native int)
0x99191  call     T0x2B0000B0
0x99196  ldsfld   class <>c <>c::<>9
0x9919b  ldftn    instance object <>c::<.cctor>b__4_1(class [mscorlib]System.Type t)
0x991a1  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, object>::.ctor(object, native int)
0x991a6  call     T0x2B0000B1
0x991ab  call     T0x2B0000B2
0x991b0  castclass IDecoratror
0x991b5  stsfld   class IDecoratror Microsoft.Crm.Application.Components.Platform.Utility.EntityReflectionUtility::queryDecorator
0x991ba  ret
```
