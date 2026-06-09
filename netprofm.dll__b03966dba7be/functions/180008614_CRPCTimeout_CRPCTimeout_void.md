# CRPCTimeout::~CRPCTimeout(void)

- ea: `0x180008614`
- end: `0x180008655`
- name: `??1CRPCTimeout@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CRPCTimeout *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800412d2`

## callees

- `0x180008614`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008641`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008641`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000862c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18000862c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRPCTimeout::~CRPCTimeout(CRPCTimeout *this)
{
  void *v2; // rdx

  if ( *((int *)this + 2) >= 0 )
  {
    *((_DWORD *)this + 2) = -2147467259;
    CoDisableCallCancellation(0);
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x180008614  push    rbx
0x180008616  sub     rsp, 20h
0x18000861a  cmp     dword ptr [rcx+8], 0
0x18000861e  mov     rbx, rcx
0x180008621  jl      short loc_18000864F
0x180008623  mov     dword ptr [rcx+8], 80004005h
0x18000862a  xor     ecx, ecx; pReserved
0x18000862c  call    cs:__imp_CoDisableCallCancellation
0x180008632  mov     rdx, [rbx+10h]; Timer
0x180008636  test    rdx, rdx
0x180008639  jz      short loc_18000864F
0x18000863b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000863f  xor     ecx, ecx; TimerQueue
0x180008641  call    cs:__imp_DeleteTimerQueueTimer
0x180008647  mov     qword ptr [rbx+10h], 0
0x18000864f  add     rsp, 20h
0x180008653  pop     rbx
0x180008654  retn
```
