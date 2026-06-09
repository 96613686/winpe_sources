# FastWppCleanup()

- ea: `0x1007490f`
- end: `0x10074953`
- name: `_FastWppCleanup@0`
- size: `68`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1005b2f0`

## callees

- `0x1006c2c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10074942`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10074942`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1007491b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1007491b`

## pseudocode

```c
void __stdcall FastWppCleanup()
{
  EventUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  memset(g_rgFastWppLevelEnabledFlags, 0, sizeof(g_rgFastWppLevelEnabledFlags));
  DeleteCriticalSection(&FastWppCallbackLock);
  FastWppInitState = FastWppStateUninitialized;
}

```

## disassembly

```asm
0x1007490f  push    dword ptr ?FastWppRegHandle@@3_KA+4; unsigned __int64 FastWppRegHandle
0x10074915  push    dword ptr ?FastWppRegHandle@@3_KA; RegHandle
0x1007491b  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x10074921  push    30h ; '0'; Size
0x10074923  xorps   xmm0, xmm0
0x10074926  push    0; Val
0x10074928  push    offset _g_rgFastWppLevelEnabledFlags; void *
0x1007492d  movlpd  ?FastWppRegHandle@@3_KA, xmm0; unsigned __int64 FastWppRegHandle
0x10074935  call    _memset
0x1007493a  add     esp, 0Ch
0x1007493d  push    offset ?FastWppCallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10074942  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10074948  mov     ?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 0; _FAST_WPP_STATE volatile FastWppInitState
0x10074952  retn
```
