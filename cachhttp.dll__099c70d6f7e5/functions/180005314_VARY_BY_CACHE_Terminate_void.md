# VARY_BY_CACHE::Terminate(void)

- ea: `0x180005314`
- end: `0x180005344`
- name: `?Terminate@VARY_BY_CACHE@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(VARY_BY_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800039d0`
- `0x1800072b0`

## callees

- `0x180005314`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180005330`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180005330`

## pseudocode

```c
void __fastcall VARY_BY_CACHE::Terminate(VARY_BY_CACHE *this)
{
  _QWORD *v1; // rbx
  void *v2; // rdx

  v1 = g_pVaryByCache;
  v2 = (void *)*((_QWORD *)g_pVaryByCache + 5);
  if ( v2 )
  {
    DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v1[5] = 0;
  }
}

```

## disassembly

```asm
0x180005314  push    rbx
0x180005316  sub     rsp, 20h
0x18000531a  mov     rbx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x180005321  mov     rdx, [rbx+28h]; Timer
0x180005325  test    rdx, rdx
0x180005328  jz      short loc_18000533E
0x18000532a  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000532e  xor     ecx, ecx; TimerQueue
0x180005330  call    cs:__imp_DeleteTimerQueueTimer
0x180005336  mov     qword ptr [rbx+28h], 0
0x18000533e  add     rsp, 20h
0x180005342  pop     rbx
0x180005343  retn
```
