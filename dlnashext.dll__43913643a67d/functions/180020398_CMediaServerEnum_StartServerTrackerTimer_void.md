# CMediaServerEnum::_StartServerTrackerTimer(void)

- ea: `0x180020398`
- end: `0x1800203f0`
- name: `?_StartServerTrackerTimer@CMediaServerEnum@@QEAAXXZ`
- size: `88`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e40`

## callees

- `0x180020398`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800203ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800203ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800203e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800203e4`

## pseudocode

```c
void __fastcall CMediaServerEnum::_StartServerTrackerTimer(PTP_TIMER *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_TIMER v3; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(CMediaServerEnum::_ServerTrackingDone, pv, 0);
  pv[9] = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    v3 = *pv;
    pftDueTime = (struct _FILETIME)-100000000LL;
    (*((void (__fastcall **)(PTP_TIMER *))v3 + 1))(pv);
    SetThreadpoolTimer(pv[9], &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x180020398  push    rbx
0x18002039a  sub     rsp, 20h
0x18002039e  mov     rbx, rcx
0x1800203a1  mov     rdx, rcx; pv
0x1800203a4  lea     rcx, ?_ServerTrackingDone@CMediaServerEnum@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800203ab  xor     r8d, r8d; pcbe
0x1800203ae  call    cs:__imp_CreateThreadpoolTimer
0x1800203b4  mov     [rbx+48h], rax
0x1800203b8  test    rax, rax
0x1800203bb  jz      short loc_1800203EA
0x1800203bd  mov     rax, [rbx]
0x1800203c0  mov     rcx, rbx
0x1800203c3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFA0A1F00h
0x1800203cc  mov     rax, [rax+8]
0x1800203d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203d5  mov     rcx, [rbx+48h]; pti
0x1800203d9  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800203de  xor     r9d, r9d; msWindowLength
0x1800203e1  xor     r8d, r8d; msPeriod
0x1800203e4  call    cs:__imp_SetThreadpoolTimer
0x1800203ea  add     rsp, 20h
0x1800203ee  pop     rbx
0x1800203ef  retn
```
