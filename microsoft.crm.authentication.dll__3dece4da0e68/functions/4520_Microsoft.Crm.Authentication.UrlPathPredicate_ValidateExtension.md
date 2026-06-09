# Microsoft.Crm.Authentication.UrlPathPredicate::ValidateExtension

- ea: `0x4520`
- end: `0x45a4`
- name: `Microsoft.Crm.Authentication.UrlPathPredicate::ValidateExtension`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x44c0`

## callees

- `0x4520`

## string_xrefs

- `0x4535`: `extension`
- `0x4551`: `Configuration parameter "{0}" cannot be null or empty.`
- `0x457c`: `The extension "{0}" is invalid. Extensions must begin with a period.`

## pseudocode

```c

```

## disassembly

```asm
0x4520  ldarga.s 1
0x4522  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x4527  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x452c  brtrue.s loc_459E
0x452e  ldarga.s 1
0x4530  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x4535  ldstr    aExtension// "extension"
0x453a  ldc.i4.5
0x453b  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4540  brfalse.s loc_459E
0x4542  ldarga.s 1
0x4544  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x4549  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x454e  ldc.i4.0
0x454f  ceq
0x4551  ldstr    aConfigurationP// "Configuration parameter \"{0}\" cannot "...
0x4556  ldc.i4.1
0x4557  newarr   [mscorlib]System.Object
0x455c  dup
0x455d  ldc.i4.0
0x455e  ldarga.s 1
0x4560  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x4565  stelem.ref
0x4566  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x456b  ldarga.s 1
0x456d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x4572  ldc.i4.0
0x4573  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4578  ldc.i4.s 0x2E
0x457a  ceq
0x457c  ldstr    aTheExtension0I// "The extension \"{0}\" is invalid. Exten"...
0x4581  ldc.i4.1
0x4582  newarr   [mscorlib]System.Object
0x4587  dup
0x4588  ldc.i4.0
0x4589  ldarga.s 1
0x458b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x4590  stelem.ref
0x4591  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x4596  ldarga.s 1
0x4598  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x459d  ret
0x459e  ldsfld   string [mscorlib]System.String::Empty
0x45a3  ret
```
