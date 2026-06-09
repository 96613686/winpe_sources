# SnmpExtensionInit

- ea: `0x180001a10`
- end: `0x180001a34`
- name: `SnmpExtensionInit`
- size: `36`
- prototype: `BOOL __stdcall(DWORD dwUptimeReference, HANDLE *phSubagentTrapEvent, AsnObjectIdentifier *pFirstSupportedRegion)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
BOOL __stdcall SnmpExtensionInit(
        DWORD dwUptimeReference,
        HANDLE *phSubagentTrapEvent,
        AsnObjectIdentifier *pFirstSupportedRegion)
{
  BOOL result; // eax

  *pFirstSupportedRegion = pOidSrc;
  result = 1;
  *phSubagentTrapEvent = 0;
  return result;
}

```

## disassembly

```asm
0x180001a10  movsd   xmm0, qword ptr cs:pOidSrc.idLength
0x180001a18  movsd   qword ptr [r8], xmm0
0x180001a1d  mov     eax, dword ptr cs:pOidSrc.ids+4
0x180001a23  mov     [r8+8], eax
0x180001a27  mov     eax, 1
0x180001a2c  mov     qword ptr [rdx], 0
0x180001a33  retn
```
