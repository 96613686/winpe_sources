# Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::ParseState

- ea: `0x17860`
- end: `0x17944`
- name: `Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::ParseState`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17770`

## callees

- `0x17860`
- `0x179f0`

## string_xrefs

- `0x178f9`: `PARTIALLY INSTALLED`
- `0x17917`: `DISABLED WITH PAYLOAD REMOVED`

## pseudocode

```c

```

## disassembly

```asm
0x17860  ldarg.1
0x17861  callvirt instance string [mscorlib]System.String::Trim()
0x17866  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1786b  starg.s  1
0x1786d  ldarg.1
0x1786e  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x17873  stloc.0
0x17874  ldloc.0
0x17875  ldc.i4   0x2EE9140D
0x1787a  bgt.un.s loc_1789C
0x1787c  ldloc.0
0x1787d  ldc.i4   0x122DD385
0x17882  beq      loc_17925
0x17887  ldloc.0
0x17888  ldc.i4   0x1F3BF5F3
0x1788d  beq.s    loc_178F8
0x1788f  ldloc.0
0x17890  ldc.i4   0x2EE9140D
0x17895  beq.s    loc_178DA
0x17897  br       loc_17942
0x1789c  ldloc.0
0x1789d  ldc.i4   0x823F0F85
0x178a2  bgt.un.s loc_178B9
0x178a4  ldloc.0
0x178a5  ldc.i4   0x42CDBAF0
0x178aa  beq.s    loc_178E9
0x178ac  ldloc.0
0x178ad  ldc.i4   0x823F0F85
0x178b2  beq.s    loc_17916
0x178b4  br       loc_17942
0x178b9  ldloc.0
0x178ba  ldc.i4   0x88C2FFFE
0x178bf  beq.s    loc_178CB
0x178c1  ldloc.0
0x178c2  ldc.i4   0xB294B31D
0x178c7  beq.s    loc_17907
0x178c9  br.s     loc_17942
0x178cb  ldarg.1
0x178cc  ldstr    aEnabled_0// "ENABLED"
0x178d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178d6  brtrue.s loc_17934
0x178d8  br.s     loc_17942
0x178da  ldarg.1
0x178db  ldstr    aEnablePending// "ENABLE PENDING"
0x178e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178e5  brtrue.s loc_17936
0x178e7  br.s     loc_17942
0x178e9  ldarg.1
0x178ea  ldstr    aDisablePending// "DISABLE PENDING"
0x178ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x178f4  brtrue.s loc_17938
0x178f6  br.s     loc_17942
0x178f8  ldarg.1
0x178f9  ldstr    aPartiallyInsta// "PARTIALLY INSTALLED"
0x178fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17903  brtrue.s loc_1793A
0x17905  br.s     loc_17942
0x17907  ldarg.1
0x17908  ldstr    aSuperseded// "SUPERSEDED"
0x1790d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17912  brtrue.s loc_1793C
0x17914  br.s     loc_17942
0x17916  ldarg.1
0x17917  ldstr    aDisabledWithPa// "DISABLED WITH PAYLOAD REMOVED"
0x1791c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17921  brtrue.s loc_1793E
0x17923  br.s     loc_17942
0x17925  ldarg.1
0x17926  ldstr    aDisabled// "DISABLED"
0x1792b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17930  brtrue.s loc_17940
0x17932  br.s     loc_17942
0x17934  ldc.i4.4
0x17935  ret
0x17936  ldc.i4.5
0x17937  ret
0x17938  ldc.i4.1
0x17939  ret
0x1793a  ldc.i4.7
0x1793b  ret
0x1793c  ldc.i4.6
0x1793d  ret
0x1793e  ldc.i4.3
0x1793f  ret
0x17940  ldc.i4.2
0x17941  ret
0x17942  ldc.i4.2
0x17943  ret
```
