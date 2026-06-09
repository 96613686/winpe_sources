# Microsoft.Crm.Entities.CommunicationActivity::GetMappingItem

- ea: `0x360`
- end: `0x39d`
- name: `Microsoft.Crm.Entities.CommunicationActivity::GetMappingItem`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x340`
- `0x350`

## callees

- `0x100`
- `0x360`
- `0xd80`

## pseudocode

```c

```

## disassembly

```asm
0x360  ldarg.0
0x361  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x366  ldarg.1
0x367  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(valuetype Microsoft.Crm.Entities.ParticipationType type)
0x36c  stloc.0
0x36d  ldloc.0
0x36e  brtrue.s loc_39B
0x370  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x375  ldstr    aNoParticipatio_0// "No ParticipationType '{0}'"
0x37a  ldc.i4.1
0x37b  newarr   [mscorlib]System.Object
0x380  dup
0x381  ldc.i4.0
0x382  ldarga.s 1
0x384  constrained. Microsoft.Crm.Entities.ParticipationType
0x38a  callvirt instance string [mscorlib]System.Object::ToString()
0x38f  stelem.ref
0x390  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x395  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x39a  throw
0x39b  ldloc.0
0x39c  ret
```
