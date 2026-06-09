# Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::GetIssuerEndpoint

- ea: `0x17960`
- end: `0x179ce`
- name: `Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::GetIssuerEndpoint`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15600`
- `0x16bb0`
- `0x16c30`
- `0x16cc0`

## callees

- `0x17810`
- `0x17960`

## string_xrefs

- `0x179ad`: `The authentication endpoint {0} was not found on the configured Secure Token Service!`

## pseudocode

```c

```

## disassembly

```asm
0x17960  ldarg.1
0x17961  brtrue.s loc_17965
0x17963  ldnull
0x17964  ret
0x17965  ldarg.0
0x17966  call     instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::GetEnumerator()
0x1796b  stloc.0
0x1796c  br.s     loc_1798F
0x1796e  ldloca.s 0
0x17970  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::get_Current()
0x17975  stloc.1
0x17976  ldloca.s 1
0x17978  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::get_Value()
0x1797d  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_CredentialType()
0x17982  ldarg.1
0x17983  bne.un.s loc_1798F
0x17985  ldloca.s 1
0x17987  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::get_Value()
0x1798c  stloc.2
0x1798d  leave.s  loc_179CC
0x1798f  ldloca.s 0
0x17991  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::MoveNext()
0x17996  brtrue.s loc_1796E
0x17998  leave.s  loc_179A8
0x1799a  ldloca.s 0
0x1799c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>
0x179a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x179a7  endfinally
0x179a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x179ad  ldstr    aTheAuthenticat// "The authentication endpoint {0} was not"...
0x179b2  ldc.i4.1
0x179b3  newarr   [mscorlib]System.Object
0x179b8  dup
0x179b9  ldc.i4.0
0x179ba  ldarg.1
0x179bb  box      Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x179c0  stelem.ref
0x179c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x179c6  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x179cb  throw
0x179cc  ldloc.2
0x179cd  ret
```
