# Microsoft.Crm.FiscalSettingUtil::GetPeriodSetBasedOnTemplate

- ea: `0x20030`
- end: `0x20094`
- name: `Microsoft.Crm.FiscalSettingUtil::GetPeriodSetBasedOnTemplate`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x20030`

## string_xrefs

- `0x20075`: `Unexpected template type: {0}. Expected types are: 2000, 2001, 2002, 2003, 2004`

## pseudocode

```c

```

## disassembly

```asm
0x20030  ldarg.0
0x20031  ldc.i4   0x7D0
0x20036  sub
0x20037  switch   loc_20052, loc_20058, loc_2005E, loc_20064, loc_2006A
0x20050  br.s     loc_20070
0x20052  ldsfld   int32[] Microsoft.Crm.FiscalSettingUtil::FiscalPeriodsForAnnualTemplate
0x20057  ret
0x20058  ldsfld   int32[] Microsoft.Crm.FiscalSettingUtil::FiscalPeriodsForSemiAnnualTemplate
0x2005d  ret
0x2005e  ldsfld   int32[] Microsoft.Crm.FiscalSettingUtil::FiscalPeriodsForQuarterlyTemplate
0x20063  ret
0x20064  ldsfld   int32[] Microsoft.Crm.FiscalSettingUtil::FiscalPeriodsForMonthlyTemplate
0x20069  ret
0x2006a  ldsfld   int32[] Microsoft.Crm.FiscalSettingUtil::FiscalPeriodsForFixedMonthlyTemplate
0x2006f  ret
0x20070  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20075  ldstr    aUnexpectedTemp// "Unexpected template type: {0}. Expected"...
0x2007a  ldc.i4.1
0x2007b  newarr   [mscorlib]System.Object
0x20080  dup
0x20081  ldc.i4.0
0x20082  ldarg.0
0x20083  box      [mscorlib]System.Int32
0x20088  stelem.ref
0x20089  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2008e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x20093  throw
```
