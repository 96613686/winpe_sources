# WorkThreadManager::CThread::CheckForDeadlock(void)

- ea: `0x180031730`
- end: `0x180031792`
- name: `?CheckForDeadlock@CThread@WorkThreadManager@@QEAAXXZ`
- size: `98`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180032b10`

## callees

- `0x180031730`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031753`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180031753`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031786`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031786`

## pseudocode

```c
void __fastcall WorkThreadManager::CThread::CheckForDeadlock(_BYTE *pv)
{
  struct _TP_TIMER *v2; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pv[89] = 1;
  v2 = (struct _TP_TIMER *)*((_QWORD *)pv + 12);
  if ( v2
    || (ThreadpoolTimer = CreateThreadpoolTimer(WorkThreadManager::CThread::s_CheckForDeadlockTimerCallback, pv, 0),
        *((_QWORD *)pv + 12) = ThreadpoolTimer,
        (v2 = ThreadpoolTimer) != 0) )
  {
    pftDueTime = (struct _FILETIME)-5000000LL;
    SetThreadpoolTimer(v2, &pftDueTime, 0, 0xFAu);
  }
}

```

## disassembly

```asm
0x180031730  push    rbx
0x180031732  sub     rsp, 20h
0x180031736  mov     rbx, rcx
0x180031739  mov     byte ptr [rcx+59h], 1
0x18003173d  mov     rcx, [rcx+60h]
0x180031741  test    rcx, rcx
0x180031744  jnz     short loc_180031765
0x180031746  xor     r8d, r8d; pcbe
0x180031749  lea     rcx, ?s_CheckForDeadlockTimerCallback@CThread@WorkThreadManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180031750  mov     rdx, rbx; pv
0x180031753  call    cs:__imp_CreateThreadpoolTimer
0x180031759  mov     [rbx+60h], rax
0x18003175d  mov     rcx, rax; pti
0x180031760  test    rax, rax
0x180031763  jz      short loc_18003178C
0x180031765  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFB3B4C0h
0x18003176e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180031773  mov     rax, qword ptr [rsp+28h+pftDueTime.dwLowDateTime]
0x180031778  mov     r9d, 0FAh; msWindowLength
0x18003177e  xor     r8d, r8d; msPeriod
0x180031781  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180031786  call    cs:__imp_SetThreadpoolTimer
0x18003178c  add     rsp, 20h
0x180031790  pop     rbx
0x180031791  retn
```
