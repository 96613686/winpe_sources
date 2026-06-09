# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::GetLastUpdateTimeFromConfigurationString

- ea: `0x9940`
- end: `0x9997`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::GetLastUpdateTimeFromConfigurationString`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x9300`

## callees

- `0x9860`
- `0x9940`

## string_xrefs

- `0x9952`: `LastUpdateTime`
- `0x995f`: `LastUpdateTime`
- `0x9972`: `LastUpdateTime`

## pseudocode

```c

```

## disassembly

```asm
0x9940  ldarg.0
0x9941  ldarg.1
0x9942  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeMailboxToCrmOrgBinder::GetExchangeMailboxConfigurationDictionaryFromString(string configurationString)
0x9947  stloc.0
0x9948  ldloc.0
0x9949  brtrue.s loc_9951
0x994b  ldsfld   string [mscorlib]System.String::Empty
0x9950  ret
0x9951  ldloc.0
0x9952  ldstr    aLastupdatetime// "LastUpdateTime"
0x9957  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x995c  brfalse.s loc_996B
0x995e  ldloc.0
0x995f  ldstr    aLastupdatetime// "LastUpdateTime"
0x9964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9969  brtrue.s loc_9971
0x996b  ldsfld   string [mscorlib]System.String::Empty
0x9970  ret
0x9971  ldloc.0
0x9972  ldstr    aLastupdatetime// "LastUpdateTime"
0x9977  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x997c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x9981  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x9986  stloc.1
0x9987  ldloca.s 1
0x9989  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x998e  stloc.2
0x998f  ldloca.s 2
0x9991  call     instance string [mscorlib]System.DateTime::ToString()
0x9996  ret
```
