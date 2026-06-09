# FreeKeyIsoPerfCounterInstance

- ea: `0x18000a89c`
- end: `0x18000a8e2`
- name: `FreeKeyIsoPerfCounterInstance`
- size: `70`
- prototype: `void __fastcall(PPERF_COUNTERSET_INSTANCE InstanceBlock)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a5c0`

## callees

- `0x180003cf0`
- `0x18000a89c`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18000a8b8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18000a8b8`

## string_xrefs

- `0x18000a8c8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\perfcounters.c`

## pseudocode

```c
void __fastcall FreeKeyIsoPerfCounterInstance(PPERF_COUNTERSET_INSTANCE InstanceBlock)
{
  ULONG v1; // eax

  if ( dword_180025A30 && InstanceBlock )
  {
    v1 = PerfDeleteInstance(KeyIsoPerfCounterProvider, InstanceBlock);
    if ( v1 )
      DebugTraceError(
        v1,
        (int)"error",
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\perfcounters.c",
        121);
  }
}

```

## disassembly

```asm
0x18000a89c  sub     rsp, 28h
0x18000a8a0  cmp     cs:dword_180025A30, 0
0x18000a8a7  jz      short loc_18000A8DD
0x18000a8a9  test    rcx, rcx
0x18000a8ac  jz      short loc_18000A8DD
0x18000a8ae  mov     rdx, rcx; InstanceBlock
0x18000a8b1  mov     rcx, cs:KeyIsoPerfCounterProvider; Provider
0x18000a8b8  call    cs:__imp_PerfDeleteInstance
0x18000a8be  test    eax, eax
0x18000a8c0  jz      short loc_18000A8DD
0x18000a8c2  mov     r9d, 79h ; 'y'
0x18000a8c8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a8cf  lea     rdx, aError; "error"
0x18000a8d6  mov     ecx, eax
0x18000a8d8  call    DebugTraceError
0x18000a8dd  add     rsp, 28h
0x18000a8e1  retn
```
