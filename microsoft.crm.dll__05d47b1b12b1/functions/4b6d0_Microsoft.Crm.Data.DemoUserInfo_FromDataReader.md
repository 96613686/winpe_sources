# Microsoft.Crm.Data.DemoUserInfo::FromDataReader

- ea: `0x4b6d0`
- end: `0x4b767`
- name: `Microsoft.Crm.Data.DemoUserInfo::FromDataReader`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x50b50`

## callees

- `0x4b640`
- `0x4b660`
- `0x4b670`
- `0x4b680`
- `0x4b6a0`
- `0x4b6c0`
- `0x4b6d0`
- `0x4b770`

## string_xrefs

- `0x4b6ee`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x4b6d0  newobj   instance void Microsoft.Crm.Data.DemoUserInfo::.ctor()
0x4b6d5  stloc.0
0x4b6d6  ldloc.0
0x4b6d7  ldarg.0
0x4b6d8  ldstr    aSystemuserid// "SystemUserId"
0x4b6dd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4b6e2  unbox.any [mscorlib]System.Guid
0x4b6e7  callvirt instance void Microsoft.Crm.Data.DemoUserInfo::set_SystemUserId(valuetype [mscorlib]System.Guid value)
0x4b6ec  ldloc.0
0x4b6ed  ldarg.0
0x4b6ee  ldstr    aCreatedon// "CreatedOn"
0x4b6f3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4b6f8  unbox.any [mscorlib]System.DateTime
0x4b6fd  callvirt instance void Microsoft.Crm.Data.DemoUserInfo::set_CreatedOn(valuetype [mscorlib]System.DateTime value)
0x4b702  ldloc.0
0x4b703  ldarg.0
0x4b704  ldstr    aDomainname// "DomainName"
0x4b709  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4b70e  castclass [mscorlib]System.String
0x4b713  callvirt instance void Microsoft.Crm.Data.DemoUserInfo::set_DomainName(string value)
0x4b718  ldloc.0
0x4b719  callvirt instance string Microsoft.Crm.Data.DemoUserInfo::get_DomainName()
0x4b71e  ldc.i4.1
0x4b71f  newarr   [mscorlib]System.Char
0x4b724  dup
0x4b725  ldc.i4.0
0x4b726  ldc.i4.s 0x40
0x4b728  stelem.i2
0x4b729  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4b72e  ldc.i4.0
0x4b72f  ldelem.ref
0x4b730  ldc.i4.1
0x4b731  newarr   [mscorlib]System.Char
0x4b736  dup
0x4b737  ldc.i4.0
0x4b738  ldc.i4.s 0x5F
0x4b73a  stelem.i2
0x4b73b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4b740  stloc.1
0x4b741  ldloc.1
0x4b742  ldlen
0x4b743  conv.i4
0x4b744  ldc.i4.2
0x4b745  beq.s    loc_4B749
0x4b747  ldnull
0x4b748  ret
0x4b749  ldloc.0
0x4b74a  ldloc.1
0x4b74b  ldc.i4.0
0x4b74c  ldelem.ref
0x4b74d  callvirt instance void Microsoft.Crm.Data.DemoUserInfo::set_Scenario(string value)
0x4b752  ldloc.0
0x4b753  ldloc.1
0x4b754  ldc.i4.1
0x4b755  ldelem.ref
0x4b756  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b75b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x4b760  callvirt instance void Microsoft.Crm.Data.DemoUserInfo::set_Number(int32 value)
0x4b765  ldloc.0
0x4b766  ret
```
