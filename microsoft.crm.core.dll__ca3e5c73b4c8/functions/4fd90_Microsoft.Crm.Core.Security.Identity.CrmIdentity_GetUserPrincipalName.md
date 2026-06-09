# Microsoft.Crm.Core.Security.Identity.CrmIdentity::GetUserPrincipalName

- ea: `0x4fd90`
- end: `0x4ff4c`
- name: `Microsoft.Crm.Core.Security.Identity.CrmIdentity::GetUserPrincipalName`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x50040`

## callees

- `0x4640`
- `0x4890`
- `0x4fd90`

## string_xrefs

- `0x4fe05`: `@Live.com`
- `0x4fe72`: `@MicrosoftOnline.com`
- `0x4fec7`: `@MicrosoftOnline.com`

## pseudocode

```c

```

## disassembly

```asm
0x4fd90  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4fd95  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.LocatorService::GetSku()
0x4fd9a  ldc.i4.2
0x4fd9b  bne.un   loc_4FF0E
0x4fda0  ldarg.0
0x4fda1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4fda6  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_0
0x4fdab  dup
0x4fdac  brtrue.s loc_4FDC5
0x4fdae  pop
0x4fdaf  ldsfld   class <>c <>c::<>9
0x4fdb4  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_0(class [mscorlib]System.Security.Claims.Claim claim)
0x4fdba  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4fdbf  dup
0x4fdc0  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_0
0x4fdc5  call     T0x2B000001
0x4fdca  stloc.0
0x4fdcb  ldloc.0
0x4fdcc  brfalse.s loc_4FE29
0x4fdce  ldarg.0
0x4fdcf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4fdd4  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_4
0x4fdd9  dup
0x4fdda  brtrue.s loc_4FDF3
0x4fddc  pop
0x4fddd  ldsfld   class <>c <>c::<>9
0x4fde2  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_4(class [mscorlib]System.Security.Claims.Claim claim)
0x4fde8  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4fded  dup
0x4fdee  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_4
0x4fdf3  call     T0x2B000001
0x4fdf8  stloc.s  4
0x4fdfa  ldloc.s  4
0x4fdfc  brfalse.s loc_4FE29
0x4fdfe  ldloc.s  4
0x4fe00  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4fe05  ldstr    aLiveCom// "@Live.com"
0x4fe0a  ldc.i4.1
0x4fe0b  newarr   [mscorlib]System.Char
0x4fe10  dup
0x4fe11  ldc.i4.0
0x4fe12  ldc.i4.s 0x40
0x4fe14  stelem.i2
0x4fe15  call     instance string [mscorlib]System.String::Trim(char[])
0x4fe1a  ldc.i4.5
0x4fe1b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4fe20  brtrue.s loc_4FE29
0x4fe22  ldloc.0
0x4fe23  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4fe28  ret
0x4fe29  ldarg.0
0x4fe2a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4fe2f  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_1
0x4fe34  dup
0x4fe35  brtrue.s loc_4FE4E
0x4fe37  pop
0x4fe38  ldsfld   class <>c <>c::<>9
0x4fe3d  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_1(class [mscorlib]System.Security.Claims.Claim claim)
0x4fe43  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4fe48  dup
0x4fe49  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_1
0x4fe4e  call     T0x2B000001
0x4fe53  stloc.1
0x4fe54  ldloc.1
0x4fe55  brfalse.s loc_4FE7E
0x4fe57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fe5c  ldstr    a01_2// "{0}{1}"
0x4fe61  ldc.i4.2
0x4fe62  newarr   [mscorlib]System.Object
0x4fe67  dup
0x4fe68  ldc.i4.0
0x4fe69  ldloc.1
0x4fe6a  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4fe6f  stelem.ref
0x4fe70  dup
0x4fe71  ldc.i4.1
0x4fe72  ldstr    aMicrosoftonlin// "@MicrosoftOnline.com"
0x4fe77  stelem.ref
0x4fe78  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4fe7d  ret
0x4fe7e  ldarg.0
0x4fe7f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4fe84  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_2
0x4fe89  dup
0x4fe8a  brtrue.s loc_4FEA3
0x4fe8c  pop
0x4fe8d  ldsfld   class <>c <>c::<>9
0x4fe92  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_2(class [mscorlib]System.Security.Claims.Claim claim)
0x4fe98  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4fe9d  dup
0x4fe9e  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_2
0x4fea3  call     T0x2B000001
0x4fea8  stloc.2
0x4fea9  ldloc.2
0x4feaa  brfalse.s loc_4FED3
0x4feac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4feb1  ldstr    a01_2// "{0}{1}"
0x4feb6  ldc.i4.2
0x4feb7  newarr   [mscorlib]System.Object
0x4febc  dup
0x4febd  ldc.i4.0
0x4febe  ldloc.2
0x4febf  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4fec4  stelem.ref
0x4fec5  dup
0x4fec6  ldc.i4.1
0x4fec7  ldstr    aMicrosoftonlin// "@MicrosoftOnline.com"
0x4fecc  stelem.ref
0x4fecd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4fed2  ret
0x4fed3  ldarg.0
0x4fed4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4fed9  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_3
0x4fede  dup
0x4fedf  brtrue.s loc_4FEF8
0x4fee1  pop
0x4fee2  ldsfld   class <>c <>c::<>9
0x4fee7  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_3(class [mscorlib]System.Security.Claims.Claim claim)
0x4feed  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4fef2  dup
0x4fef3  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_3
0x4fef8  call     T0x2B000001
0x4fefd  stloc.3
0x4fefe  ldloc.3
0x4feff  brtrue.s loc_4FF07
0x4ff01  ldsfld   string [mscorlib]System.String::Empty
0x4ff06  ret
0x4ff07  ldloc.3
0x4ff08  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4ff0d  ret
0x4ff0e  ldarg.0
0x4ff0f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x4ff14  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_5
0x4ff19  dup
0x4ff1a  brtrue.s loc_4FF33
0x4ff1c  pop
0x4ff1d  ldsfld   class <>c <>c::<>9
0x4ff22  ldftn    instance bool <>c::<GetUserPrincipalName>b__58_5(class [mscorlib]System.Security.Claims.Claim claim)
0x4ff28  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x4ff2d  dup
0x4ff2e  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__58_5
0x4ff33  call     T0x2B000001
0x4ff38  stloc.s  5
0x4ff3a  ldloc.s  5
0x4ff3c  brtrue.s loc_4FF44
0x4ff3e  ldsfld   string [mscorlib]System.String::Empty
0x4ff43  ret
0x4ff44  ldloc.s  5
0x4ff46  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x4ff4b  ret
```
