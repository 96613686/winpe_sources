# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14001552c`
- end: `0x1400156b4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400171f0`

## callees

- `0x14001552c`
- `0x140017744`
- `0x140018350`
- `0x140019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015694`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015694`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001558a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001558a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001563e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001563e`
- `KERNEL32!CloseThreadpoolTimer` at `0x140015647`
- `KERNEL32!CloseThreadpoolTimer` at `0x140015647`
- `KERNEL32!GetLastError` at `0x1400155f5`
- `KERNEL32!GetLastError` at `0x14001561d`
- `KERNEL32!GetLastError` at `0x1400155f5`
- `KERNEL32!GetLastError` at `0x14001561d`
- `KERNEL32!SetThreadpoolTimer` at `0x140015630`
- `KERNEL32!SetThreadpoolTimer` at `0x140015682`
- `KERNEL32!SetThreadpoolTimer` at `0x140015630`
- `KERNEL32!SetThreadpoolTimer` at `0x140015682`
- `KERNEL32!CreateThreadpoolTimer` at `0x14001560b`
- `KERNEL32!CreateThreadpoolTimer` at `0x14001560b`
- `KERNEL32!SetLastError` at `0x14001564f`
- `KERNEL32!SetLastError` at `0x14001565c`
- `KERNEL32!SetLastError` at `0x14001564f`
- `KERNEL32!SetLastError` at `0x14001565c`
- `msvcrt!memcpy_s` at `0x1400155da`
- `msvcrt!memcpy_s` at `0x1400155da`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x14001552c  push    rbx
0x14001552e  push    rbp
0x14001552f  push    rsi
0x140015530  push    rdi
0x140015531  push    r14
0x140015533  push    r15
0x140015535  sub     rsp, 48h
0x140015539  mov     rax, cs:__security_cookie
0x140015540  xor     rax, rsp
0x140015543  mov     [rsp+78h+var_40], rax
0x140015548  cmp     byte ptr [rcx], 0
0x14001554b  mov     r14d, r9d
0x14001554e  movzx   ebp, r8w
0x140015552  mov     ebx, edx
0x140015554  mov     rdi, rcx
0x140015557  jz      loc_14001569A
0x14001555d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140015564  jnz     loc_14001569A
0x14001556a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140015571  test    rax, rax
0x140015574  jz      short loc_140015583
0x140015576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001557b  test    al, al
0x14001557d  jnz     loc_14001569A
0x140015583  lea     rsi, [rdi+28h]
0x140015587  mov     rcx, rsi; SRWLock
0x14001558a  call    cs:__imp_AcquireSRWLockExclusive
0x140015590  xor     eax, eax
0x140015592  mov     [rsp+78h+Source], ebx
0x140015596  mov     [rsp+78h+var_4C], bp
0x14001559b  lea     rbx, [rdi+0E8h]
0x1400155a2  mov     rcx, rbx; this
0x1400155a5  mov     [rsp+78h+var_4A], ax
0x1400155aa  mov     [rsp+78h+var_48], r14d
0x1400155af  lea     ebp, [rax+0Ch]
0x1400155b2  mov     edx, ebp; unsigned __int64
0x1400155b4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400155b9  test    al, al
0x1400155bb  jz      short loc_1400155E4
0x1400155bd  mov     rcx, [rbx+8]; Destination
0x1400155c1  lea     r8, [rsp+78h+Source]; Source
0x1400155c6  mov     rax, [rbx+10h]
0x1400155ca  mov     r9d, ebp; SourceSize
0x1400155cd  sub     rax, rcx
0x1400155d0  cmp     rcx, [rbx+10h]
0x1400155d4  sbb     rdx, rdx
0x1400155d7  and     rdx, rax; DestinationSize
0x1400155da  call    cs:__imp_memcpy_s
0x1400155e0  add     [rbx+8], rbp
0x1400155e4  cmp     byte ptr [rdi+40h], 0
0x1400155e8  jnz     loc_14001568C
0x1400155ee  cmp     qword ptr [rdi+38h], 0
0x1400155f3  jnz     short loc_140015662
0x1400155f5  call    cs:__imp_GetLastError
0x1400155fb  xor     r8d, r8d; pcbe
0x1400155fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140015605  mov     rdx, rdi; pv
0x140015608  mov     r14d, eax
0x14001560b  call    cs:__imp_CreateThreadpoolTimer
0x140015611  mov     rbp, [rdi+38h]
0x140015615  mov     r15, rax
0x140015618  test    rbp, rbp
0x14001561b  jz      short loc_140015655
0x14001561d  call    cs:__imp_GetLastError
0x140015623  xor     r9d, r9d; msWindowLength
0x140015626  xor     r8d, r8d; msPeriod
0x140015629  xor     edx, edx; pftDueTime
0x14001562b  mov     rcx, rbp; pti
0x14001562e  mov     ebx, eax
0x140015630  call    cs:__imp_SetThreadpoolTimer
0x140015636  mov     edx, 1; fCancelPendingCallbacks
0x14001563b  mov     rcx, rbp; pti
0x14001563e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015644  mov     rcx, rbp; pti
0x140015647  call    cs:__imp_CloseThreadpoolTimer
0x14001564d  mov     ecx, ebx; dwErrCode
0x14001564f  call    cs:__imp_SetLastError
0x140015655  mov     ecx, r14d; dwErrCode
0x140015658  mov     [rdi+38h], r15
0x14001565c  call    cs:__imp_SetLastError
0x140015662  mov     rcx, [rdi+38h]; pti
0x140015666  test    rcx, rcx
0x140015669  jz      short loc_14001568C
0x14001566b  mov     r9d, 4E2h; msWindowLength
0x140015671  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14001567a  xor     r8d, r8d; msPeriod
0x14001567d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x140015682  call    cs:__imp_SetThreadpoolTimer
0x140015688  mov     byte ptr [rdi+40h], 1
0x14001568c  test    rsi, rsi
0x14001568f  jz      short loc_14001569A
0x140015691  mov     rcx, rsi; SRWLock
0x140015694  call    cs:__imp_ReleaseSRWLockExclusive
0x14001569a  mov     rcx, [rsp+78h+var_40]
0x14001569f  xor     rcx, rsp; StackCookie
0x1400156a2  call    __security_check_cookie
0x1400156a7  add     rsp, 48h
0x1400156ab  pop     r15
0x1400156ad  pop     r14
0x1400156af  pop     rdi
0x1400156b0  pop     rsi
0x1400156b1  pop     rbp
0x1400156b2  pop     rbx
0x1400156b3  retn
```
