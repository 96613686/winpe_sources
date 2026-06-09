# SyncDataCollection::Create

- ea: `0x15c00`
- end: `0x15c26`
- name: `SyncDataCollection::Create`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x62c0`

## callees

- `0x15c00`
- `0x15c80`
- `0x15dc0`

## pseudocode

```c

```

## disassembly

```asm
0x15c00  ldnull
0x15c01  stloc.0
0x15c02  ldarg.0
0x15c03  brfalse.s loc_15C1E
0x15c05  ldarg.1
0x15c06  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15c0b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15c10  brfalse.s loc_15C1E
0x15c12  ldarg.0
0x15c13  ldarg.1
0x15c14  ldarg.2
0x15c15  ldarg.3
0x15c16  newobj   instance void SyncDataCollectionResourceBooking::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService exchangeService, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid businessUnitId, int64 lastSyncVersionNumber)
0x15c1b  stloc.0
0x15c1c  br.s     loc_15C24
0x15c1e  newobj   instance void SyncDataCollectionNull::.ctor()
0x15c23  stloc.0
0x15c24  ldloc.0
0x15c25  ret
```
