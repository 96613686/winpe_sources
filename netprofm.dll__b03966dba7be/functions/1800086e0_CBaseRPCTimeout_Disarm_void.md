# CBaseRPCTimeout::Disarm(void)

- ea: `0x1800086e0`
- end: `0x180008724`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c2bc`
- `0x180021bcc`
- `0x180026c04`

## callees

- `0x1800086e0`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008710`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008710`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800086f8`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800086f8`

## pseudocode

```c
void __fastcall CBaseRPCTimeout::Disarm(CBaseRPCTimeout *this)
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
0x1800086e0  push    rbx
0x1800086e2  sub     rsp, 20h
0x1800086e6  cmp     dword ptr [rcx+8], 0
0x1800086ea  mov     rbx, rcx
0x1800086ed  jl      short loc_18000871E
0x1800086ef  mov     dword ptr [rcx+8], 80004005h
0x1800086f6  xor     ecx, ecx; pReserved
0x1800086f8  call    cs:__imp_CoDisableCallCancellation
0x1800086fe  mov     rdx, [rbx+10h]; Timer
0x180008702  test    rdx, rdx
0x180008705  jz      short loc_18000871E
0x180008707  xor     ecx, ecx; TimerQueue
0x180008709  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180008710  call    cs:__imp_DeleteTimerQueueTimer
0x180008716  mov     qword ptr [rbx+10h], 0
0x18000871e  add     rsp, 20h
0x180008722  pop     rbx
0x180008723  retn
```
