# UL_RESPONSE_CACHE::Terminate(void)

- ea: `0x1800052dc`
- end: `0x18000530c`
- name: `?Terminate@UL_RESPONSE_CACHE@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(UL_RESPONSE_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800039d0`
- `0x1800072b0`

## callees

- `0x1800052dc`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800052f8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800052f8`

## pseudocode

```c
void __fastcall UL_RESPONSE_CACHE::Terminate(UL_RESPONSE_CACHE *this)
{
  _QWORD *v1; // rbx
  void *v2; // rdx

  v1 = g_pUlCache;
  v2 = (void *)*((_QWORD *)g_pUlCache + 9);
  if ( v2 )
  {
    DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v1[9] = 0;
  }
}

```

## disassembly

```asm
0x1800052dc  push    rbx
0x1800052de  sub     rsp, 20h
0x1800052e2  mov     rbx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x1800052e9  mov     rdx, [rbx+48h]; Timer
0x1800052ed  test    rdx, rdx
0x1800052f0  jz      short loc_180005306
0x1800052f2  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800052f6  xor     ecx, ecx; TimerQueue
0x1800052f8  call    cs:__imp_DeleteTimerQueueTimer
0x1800052fe  mov     qword ptr [rbx+48h], 0
0x180005306  add     rsp, 20h
0x18000530a  pop     rbx
0x18000530b  retn
```
