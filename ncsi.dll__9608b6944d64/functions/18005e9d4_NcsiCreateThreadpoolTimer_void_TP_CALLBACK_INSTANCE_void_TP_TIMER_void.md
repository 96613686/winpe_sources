# NcsiCreateThreadpoolTimer(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *)

- ea: `0x18005e9d4`
- end: `0x18005ea3a`
- name: `?NcsiCreateThreadpoolTimer@@YAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z`
- size: `102`
- prototype: `struct _TP_TIMER *__fastcall(PTP_TIMER_CALLBACK pfnti, PVOID pv)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180050300`
- `0x18005f454`
- `0x18006d128`

## callees

- `0x18005e9d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005ea16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005ea16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ea26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ea26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e9eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e9eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ea01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ea01`

## pseudocode

```c
PTP_TIMER __fastcall NcsiCreateThreadpoolTimer(PTP_TIMER_CALLBACK pfnti, PVOID pv)
{
  PTP_TIMER ThreadpoolTimer; // rbx

  EnterCriticalSection(&stru_18009D4B8);
  if ( byte_18009DAA0 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(pfnti, pv, pcbe);
  }
  else
  {
    ThreadpoolTimer = 0;
    SetLastError(0x45Bu);
  }
  LeaveCriticalSection(&stru_18009D4B8);
  return ThreadpoolTimer;
}

```

## disassembly

```asm
0x18005e9d4  mov     [rsp+arg_10], rbx
0x18005e9d9  push    rdi
0x18005e9da  sub     rsp, 20h
0x18005e9de  mov     rbx, rcx
0x18005e9e1  mov     rdi, rdx
0x18005e9e4  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18005e9eb  call    cs:__imp_EnterCriticalSection
0x18005e9f1  cmp     cs:byte_18009DAA0, 0
0x18005e9f8  jnz     short loc_18005EA09
0x18005e9fa  xor     ebx, ebx
0x18005e9fc  mov     ecx, 45Bh; dwErrCode
0x18005ea01  call    cs:__imp_SetLastError
0x18005ea07  jmp     short loc_18005EA1F
0x18005ea09  mov     r8, cs:pcbe; pcbe
0x18005ea10  mov     rdx, rdi; pv
0x18005ea13  mov     rcx, rbx; pfnti
0x18005ea16  call    cs:__imp_CreateThreadpoolTimer
0x18005ea1c  mov     rbx, rax
0x18005ea1f  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18005ea26  call    cs:__imp_LeaveCriticalSection
0x18005ea2c  mov     rax, rbx
0x18005ea2f  mov     rbx, [rsp+28h+arg_10]
0x18005ea34  add     rsp, 20h
0x18005ea38  pop     rdi
0x18005ea39  retn
```
