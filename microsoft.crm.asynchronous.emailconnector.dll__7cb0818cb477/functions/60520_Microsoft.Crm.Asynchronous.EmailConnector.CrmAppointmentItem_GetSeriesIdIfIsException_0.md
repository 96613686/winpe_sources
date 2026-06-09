# Microsoft.Crm.Asynchronous.EmailConnector.CrmAppointmentItem::GetSeriesIdIfIsException_0

- ea: `0x60520`
- end: `0x605b9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmAppointmentItem::GetSeriesIdIfIsException_0`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5bda0`
- `0x60510`

## callees

- `0x58a20`
- `0x60520`

## string_xrefs

- `0x60589`: `seriesid`
- `0x605a2`: `seriesid`

## pseudocode

```c

```

## disassembly

```asm
0x60520  ldsfld   string [mscorlib]System.String::Empty
0x60525  stloc.0
0x60526  ldarg.0
0x60527  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x6052c  ldstr    aInstancetypeco// "instancetypecode"
0x60531  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x60536  brtrue.s loc_6053F
0x60538  ldsfld   string [mscorlib]System.String::Empty
0x6053d  br.s     loc_60566
0x6053f  ldarg.0
0x60540  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x60545  ldstr    aInstancetypeco// "instancetypecode"
0x6054a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6054f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x60554  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x60559  stloc.2
0x6055a  ldloca.s 2
0x6055c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x60561  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x60566  stloc.1
0x60567  ldloc.1
0x60568  ldstr    a3// "3"
0x6056d  ldc.i4.5
0x6056e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x60573  brfalse.s loc_60583
0x60575  ldloc.1
0x60576  ldstr    a4// "4"
0x6057b  ldc.i4.5
0x6057c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x60581  brtrue.s loc_605B7
0x60583  ldarg.0
0x60584  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x60589  ldstr    aSeriesid// "seriesid"
0x6058e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x60593  brtrue.s loc_6059C
0x60595  ldsfld   string [mscorlib]System.String::Empty
0x6059a  br.s     loc_605B6
0x6059c  ldarg.0
0x6059d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x605a2  ldstr    aSeriesid// "seriesid"
0x605a7  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x605ac  unbox.any [mscorlib]System.Guid
0x605b1  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x605b6  stloc.0
0x605b7  ldloc.0
0x605b8  ret
```
