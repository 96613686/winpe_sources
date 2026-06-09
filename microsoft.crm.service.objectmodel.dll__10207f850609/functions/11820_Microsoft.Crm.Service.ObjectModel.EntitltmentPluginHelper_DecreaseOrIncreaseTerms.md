# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms

- ea: `0x11820`
- end: `0x1188c`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms`
- size: `108`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10900`
- `0x10bc0`
- `0x11310`
- `0x11350`

## callees

- `0x11820`

## pseudocode

```c

```

## disassembly

```asm
0x11820  ldarg.0
0x11821  ldarg.3
0x11822  ldarg.1
0x11823  brtrue.s loc_1183E
0x11825  ldarg.0
0x11826  ldarg.3
0x11827  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1182c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11831  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(object, class [mscorlib]System.IFormatProvider)
0x11836  ldarg.2
0x11837  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x1183c  br.s     loc_11855
0x1183e  ldarg.0
0x1183f  ldarg.3
0x11840  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11845  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1184a  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(object, class [mscorlib]System.IFormatProvider)
0x1184f  ldarg.2
0x11850  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x11855  box      [mscorlib]System.Decimal
0x1185a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1185f  ldarg.0
0x11860  ldstr    aStatecode// "statecode"
0x11865  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x1186a  ldarg.s  4
0x1186c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11871  stloc.0
0x11872  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x11877  ldarg.0
0x11878  ldarg.s  4
0x1187a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1187f  leave.s  loc_1188B
0x11881  ldloc.0
0x11882  brfalse.s loc_1188A
0x11884  ldloc.0
0x11885  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1188a  endfinally
0x1188b  ret
```
