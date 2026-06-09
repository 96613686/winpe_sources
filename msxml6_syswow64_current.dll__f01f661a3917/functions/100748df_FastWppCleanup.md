# FastWppCleanup()

- ea: `0x100748df`
- end: `0x10074923`
- name: `_FastWppCleanup@0`
- size: `68`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1005b380`

## callees

- `0x1006c354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10074912`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10074912`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x100748eb`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x100748eb`

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
0x100748df  push    dword ptr ?FastWppRegHandle@@3_KA+4; unsigned __int64 FastWppRegHandle
0x100748e5  push    dword ptr ?FastWppRegHandle@@3_KA; RegHandle
0x100748eb  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x100748f1  push    30h ; '0'; Size
0x100748f3  xorps   xmm0, xmm0
0x100748f6  push    0; Val
0x100748f8  push    offset _g_rgFastWppLevelEnabledFlags; void *
0x100748fd  movlpd  ?FastWppRegHandle@@3_KA, xmm0; unsigned __int64 FastWppRegHandle
0x10074905  call    _memset
0x1007490a  add     esp, 0Ch
0x1007490d  push    offset ?FastWppCallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10074912  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10074918  mov     ?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 0; _FAST_WPP_STATE volatile FastWppInitState
0x10074922  retn
```
