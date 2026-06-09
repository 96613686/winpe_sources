# NOTIFICATION_THREAD::SetPollPeriod(ulong)

- ea: `0x1800512b4`
- end: `0x18005134b`
- name: `?SetPollPeriod@NOTIFICATION_THREAD@@QEAAJK@Z`
- size: `151`
- prototype: `__int64 __fastcall(PVOID pv, DWORD msPeriod)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180050a34`

## callees

- `0x1800512b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051333`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051333`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800512cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800512cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005132a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005132a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800512ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800512ea`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_THREAD::SetPollPeriod(RTL_SRWLOCK *pv, DWORD msPeriod)
{
  RTL_SRWLOCK *v2; // rdi
  struct _TP_TIMER *Ptr; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v2 = pv + 1;
  AcquireSRWLockExclusive(pv + 1);
  Ptr = (struct _TP_TIMER *)pv->Ptr;
  if ( pv->Ptr || (Ptr = CreateThreadpoolTimer(NOTIFICATION_THREAD::ProcessPollingList, pv, 0), (pv->Ptr = Ptr) != 0) )
  {
    pftDueTime.dwHighDateTime = -1;
    v7 = 0;
    pftDueTime.dwLowDateTime = -1;
    SetThreadpoolTimer(Ptr, &pftDueTime, msPeriod, 0);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  ReleaseSRWLockExclusive(v2);
  return v7;
}

```

## disassembly

```asm
0x1800512b4  mov     [rsp+arg_8], rbx
0x1800512b9  mov     [rsp+arg_10], rsi
0x1800512be  push    rdi
0x1800512bf  sub     rsp, 20h
0x1800512c3  lea     rdi, [rcx+8]
0x1800512c7  mov     rbx, rcx
0x1800512ca  mov     rcx, rdi; SRWLock
0x1800512cd  mov     esi, edx
0x1800512cf  call    cs:__imp_AcquireSRWLockExclusive
0x1800512d5  mov     rax, [rbx]
0x1800512d8  test    rax, rax
0x1800512db  jnz     short loc_18005130F
0x1800512dd  xor     r8d, r8d; pcbe
0x1800512e0  lea     rcx, ?ProcessPollingList@NOTIFICATION_THREAD@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800512e7  mov     rdx, rbx; pv
0x1800512ea  call    cs:__imp_CreateThreadpoolTimer
0x1800512f0  mov     [rbx], rax
0x1800512f3  test    rax, rax
0x1800512f6  jnz     short loc_18005130F
0x1800512f8  call    cs:__imp_GetLastError
0x1800512fe  mov     ebx, eax
0x180051300  test    eax, eax
0x180051302  jle     short loc_180051330
0x180051304  movzx   ebx, ax
0x180051307  or      ebx, 80070000h
0x18005130d  jmp     short loc_180051330
0x18005130f  or      ecx, 0FFFFFFFFh
0x180051312  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180051317  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x18005131b  xor     ebx, ebx
0x18005131d  mov     [rsp+28h+pftDueTime.dwLowDateTime], ecx
0x180051321  xor     r9d, r9d; msWindowLength
0x180051324  mov     rcx, rax; pti
0x180051327  mov     r8d, esi; msPeriod
0x18005132a  call    cs:__imp_SetThreadpoolTimer
0x180051330  mov     rcx, rdi; SRWLock
0x180051333  call    cs:__imp_ReleaseSRWLockExclusive
0x180051339  mov     rsi, [rsp+28h+arg_10]
0x18005133e  mov     eax, ebx
0x180051340  mov     rbx, [rsp+28h+arg_8]
0x180051345  add     rsp, 20h
0x180051349  pop     rdi
0x18005134a  retn
```
