# FastWppCleanup

- ea: `0x1800d42ac`
- end: `0x1800d42fc`
- name: `FastWppCleanup`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b3600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d42e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d42e7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800d42b7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800d42b7`

## pseudocode

```c
void FastWppCleanup()
{
  EventUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  *(_OWORD *)&g_rgFastWppLevelEnabledFlags[0].ullFlags = 0;
  xmmword_1801F6C10 = 0;
  xmmword_1801F6C20 = 0;
  DeleteCriticalSection(&FastWppCallbackLock);
  FastWppInitState = FastWppStateUninitialized;
}

```

## disassembly

```asm
0x1800d42ac  sub     rsp, 28h
0x1800d42b0  mov     rcx, cs:?FastWppRegHandle@@3_KA; RegHandle
0x1800d42b7  call    cs:__imp_EventUnregister
0x1800d42bd  xorps   xmm0, xmm0
0x1800d42c0  mov     cs:?FastWppRegHandle@@3_KA, 0; unsigned __int64 FastWppRegHandle
0x1800d42cb  lea     rcx, ?FastWppCallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d42d2  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x1800d42d9  movups  cs:xmmword_1801F6C10, xmm0
0x1800d42e0  movups  cs:xmmword_1801F6C20, xmm0
0x1800d42e7  call    cs:__imp_DeleteCriticalSection
0x1800d42ed  mov     cs:?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 0; _FAST_WPP_STATE volatile FastWppInitState
0x1800d42f7  add     rsp, 28h
0x1800d42fb  retn
```
