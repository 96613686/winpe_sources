# Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::.ctor

- ea: `0x17820`
- end: `0x17869`
- name: `Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::.ctor`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x17870`
- `0x179c0`

## string_xrefs

- `0x17849`: `link cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0x17820  ldarg.0
0x17821  call     instance void [mscorlib]System.Object::.ctor()
0x17826  ldarg.1
0x17827  ldnull
0x17828  cgt.un
0x1782a  ldstr    aEdmentitynameC// "edmEntityName cannot be null"
0x1782f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17834  ldarg.2
0x17835  ldnull
0x17836  cgt.un
0x17838  ldstr    aEdmentitykeyCa// "edmEntityKey cannot be null"
0x1783d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17842  ldarg.3
0x17843  ldnull
0x17844  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x17849  ldstr    aLinkCannotBeNu// "link cannot be null"
0x1784e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17853  ldarg.0
0x17854  ldarg.1
0x17855  stfld    string Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::_edmEntityCollectionName
0x1785a  ldarg.0
0x1785b  ldarg.2
0x1785c  stfld    string Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::_edmEntityKey
0x17861  ldarg.0
0x17862  ldarg.3
0x17863  stfld    class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::_link
0x17868  ret
```
