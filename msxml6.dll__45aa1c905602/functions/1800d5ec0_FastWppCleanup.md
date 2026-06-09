# FastWppCleanup

- ea: `0x1800d5ec0`
- end: `0x1800d5f1d`
- name: `FastWppCleanup`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b4bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5f01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5f01`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800d5ecb`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800d5ecb`

## pseudocode

```c
void FastWppCleanup()
{
  EventUnregister(FastWppRegHandle);
  FastWppRegHandle = 0;
  *(_OWORD *)&g_rgFastWppLevelEnabledFlags[0].ullFlags = 0;
  xmmword_1801FAD10 = 0;
  xmmword_1801FAD20 = 0;
  DeleteCriticalSection(&FastWppCallbackLock);
  FastWppInitState = FastWppStateUninitialized;
}

```

## disassembly

```asm
0x1800d5ec0  sub     rsp, 28h
0x1800d5ec4  mov     rcx, cs:?FastWppRegHandle@@3_KA; RegHandle
0x1800d5ecb  call    cs:__imp_EventUnregister
0x1800d5ed2  nop     dword ptr [rax+rax+00h]
0x1800d5ed7  xorps   xmm0, xmm0
0x1800d5eda  mov     cs:?FastWppRegHandle@@3_KA, 0; unsigned __int64 FastWppRegHandle
0x1800d5ee5  lea     rcx, ?FastWppCallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d5eec  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x1800d5ef3  movups  cs:xmmword_1801FAD10, xmm0
0x1800d5efa  movups  cs:xmmword_1801FAD20, xmm0
0x1800d5f01  call    cs:__imp_DeleteCriticalSection
0x1800d5f08  nop     dword ptr [rax+rax+00h]
0x1800d5f0d  mov     cs:?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 0; _FAST_WPP_STATE volatile FastWppInitState
0x1800d5f17  add     rsp, 28h
0x1800d5f1b  retn
```
