# Microsoft.Crm.Application.Security.WrpcContextExtensions::GenerateTokenJson

- ea: `0x133e0`
- end: `0x13461`
- name: `Microsoft.Crm.Application.Security.WrpcContextExtensions::GenerateTokenJson`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x133e0`
- `0x13cc0`

## string_xrefs

- `0x13414`: `Token`

## pseudocode

```c

```

## disassembly

```asm
0x133e0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x133e5  stloc.0
0x133e6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::.ctor()
0x133eb  stloc.1
0x133ec  ldc.i4.0
0x133ed  stloc.2
0x133ee  br.s     loc_1344F
0x133f0  ldarg.1
0x133f1  ldloc.2
0x133f2  ldelem.ref
0x133f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x133f8  stloc.3
0x133f9  ldloc.3
0x133fa  callvirt instance string [mscorlib]System.Object::ToString()
0x133ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13404  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x13409  stloc.s  4
0x1340b  ldloc.1
0x1340c  ldloc.s  4
0x1340e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x13413  dup
0x13414  ldstr    aToken_0// "Token"
0x13419  ldarg.0
0x1341a  ldloc.3
0x1341b  ldloc.0
0x1341c  callvirt instance string Microsoft.Crm.Application.Security.WrpcContext::GenerateToken(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x13421  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13426  dup
0x13427  ldstr    aTimestamp_0// "Timestamp"
0x1342c  ldloca.s 0
0x1342e  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x13433  stloc.s  5
0x13435  ldloca.s 5
0x13437  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1343c  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x13441  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13446  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::set_Item(var<u1>, !!T0)
0x1344b  ldloc.2
0x1344c  ldc.i4.1
0x1344d  add
0x1344e  stloc.2
0x1344f  ldloc.2
0x13450  ldarg.1
0x13451  ldlen
0x13452  conv.i4
0x13453  blt.s    loc_133F0
0x13455  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x1345a  ldloc.1
0x1345b  call     instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x13460  ret
```
