# Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfo_0

- ea: `0x172e0`
- end: `0x172f6`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfo_0`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x172e0`
- `0x17360`

## string_xrefs

- `0x172e3`: `featureNames`

## pseudocode

```c

```

## disassembly

```asm
0x172e0  ldarg.1
0x172e1  brtrue.s loc_172EE
0x172e3  ldstr    aFeaturenames// "featureNames"
0x172e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x172ed  throw
0x172ee  ldarg.0
0x172ef  ldarg.1
0x172f0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.CA.IFeatureInfo> Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> features)
0x172f5  ret
```
