# SnmpExtensionTrap

- ea: `0x180001b50`
- end: `0x180001b53`
- name: `SnmpExtensionTrap`
- size: `3`
- prototype: `BOOL __stdcall(AsnObjectIdentifier *pEnterpriseOid, AsnInteger32 *pGenericTrapId, AsnInteger32 *pSpecificTrapId, AsnTimeticks *pTimeStamp, SnmpVarBindList *pVarBindList)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
BOOL __stdcall SnmpExtensionTrap(
        AsnObjectIdentifier *pEnterpriseOid,
        AsnInteger32 *pGenericTrapId,
        AsnInteger32 *pSpecificTrapId,
        AsnTimeticks *pTimeStamp,
        SnmpVarBindList *pVarBindList)
{
  return 0;
}

```

## disassembly

```asm
0x180001b50  xor     eax, eax
0x180001b52  retn
```
