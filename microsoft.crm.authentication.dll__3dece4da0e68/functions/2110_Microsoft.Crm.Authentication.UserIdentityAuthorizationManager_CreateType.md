# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::CreateType

- ea: `0x2110`
- end: `0x2194`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::CreateType`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x20f0`
- `0x52d0`

## callees

- `0x2110`

## pseudocode

```c

```

## disassembly

```asm
0x2110  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2115  ldarg.0
0x2116  ldc.i4.1
0x2117  newarr   [mscorlib]System.Object
0x211c  dup
0x211d  ldc.i4.0
0x211e  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::get_FullVersion()
0x2123  stelem.ref
0x2124  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2129  starg.s  0
0x212b  ldarg.0
0x212c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x2131  stloc.0
0x2132  ldloc.0
0x2133  ldnull
0x2134  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2139  brfalse.s loc_215B
0x213b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2140  ldstr    a0DoesnTExist// "'{0}' doesn't exist."
0x2145  ldc.i4.1
0x2146  newarr   [mscorlib]System.Object
0x214b  dup
0x214c  ldc.i4.0
0x214d  ldarg.0
0x214e  stelem.ref
0x214f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2154  ldarg.0
0x2155  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x215a  throw
0x215b  ldarg.1
0x215c  ldloc.0
0x215d  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2162  brtrue.s loc_218D
0x2164  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2169  ldstr    a0DoesnTImpleme// "'{0}' doesn't implement '{1}'."
0x216e  ldc.i4.2
0x216f  newarr   [mscorlib]System.Object
0x2174  dup
0x2175  ldc.i4.0
0x2176  ldarg.0
0x2177  stelem.ref
0x2178  dup
0x2179  ldc.i4.1
0x217a  ldarg.1
0x217b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2180  stelem.ref
0x2181  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2186  ldarg.0
0x2187  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x218c  throw
0x218d  ldloc.0
0x218e  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x2193  ret
```
