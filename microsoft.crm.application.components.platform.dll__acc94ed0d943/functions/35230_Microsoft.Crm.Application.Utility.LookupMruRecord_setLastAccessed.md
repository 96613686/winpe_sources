# Microsoft.Crm.Application.Utility.LookupMruRecord::setLastAccessed

- ea: `0x35230`
- end: `0x3528c`
- name: `Microsoft.Crm.Application.Utility.LookupMruRecord::setLastAccessed`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x352c0`

## callees

- `0x115b0`
- `0x35230`

## string_xrefs

- `0x35231`: `LastAccessed`
- `0x35266`: `invalid last-accessed`
- `0x3527a`: `invalid last-accessed`

## pseudocode

```c

```

## disassembly

```asm
0x35230  ldarg.1
0x35231  ldstr    aLastaccessed// "LastAccessed"
0x35236  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3523b  stloc.0
0x3523c  ldloc.0
0x3523d  brfalse.s loc_35279
0x3523f  ldloc.0
0x35240  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x35245  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3524a  brtrue.s loc_35279
0x3524c  ldarg.0
0x3524d  ldloc.0
0x3524e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x35253  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35258  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x3525d  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Utility.LookupMruRecord::_lastAccessed
0x35262  leave.s  loc_3528B
0x35264  pop
0x35265  ldc.i4.1
0x35266  ldstr    aInvalidLastAcc// "invalid last-accessed"
0x3526b  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x35270  ldarg.0
0x35271  ldc.i4.1
0x35272  stfld    bool Microsoft.Crm.Application.Utility.LookupMruRecord::_invalid
0x35277  leave.s  loc_3528B
0x35279  ldc.i4.1
0x3527a  ldstr    aInvalidLastAcc// "invalid last-accessed"
0x3527f  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x35284  ldarg.0
0x35285  ldc.i4.1
0x35286  stfld    bool Microsoft.Crm.Application.Utility.LookupMruRecord::_invalid
0x3528b  ret
```
