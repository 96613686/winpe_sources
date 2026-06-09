# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a9ac`
- end: `0x18000ab35`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000ca10`

## callees

- `0x18000a9ac`
- `0x18000d020`
- `0x180015cf0`
- `0x180017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aa5a`
- `msvcrt!memcpy_s` at `0x18000aa5a`
- `KERNEL32!SetLastError` at `0x18000aacf`
- `KERNEL32!SetLastError` at `0x18000aadc`
- `KERNEL32!SetLastError` at `0x18000aacf`
- `KERNEL32!SetLastError` at `0x18000aadc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000aabe`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000aabe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ab14`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ab14`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000aac7`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000aac7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aa0a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000aa0a`
- `KERNEL32!SetThreadpoolTimer` at `0x18000aab0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ab02`
- `KERNEL32!SetThreadpoolTimer` at `0x18000aab0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ab02`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000aa8b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000aa8b`
- `KERNEL32!GetLastError` at `0x18000aa75`
- `KERNEL32!GetLastError` at `0x18000aa9d`
- `KERNEL32!GetLastError` at `0x18000aa75`
- `KERNEL32!GetLastError` at `0x18000aa9d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
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
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x18000a9ac  push    rbx
0x18000a9ae  push    rbp
0x18000a9af  push    rsi
0x18000a9b0  push    rdi
0x18000a9b1  push    r14
0x18000a9b3  push    r15
0x18000a9b5  sub     rsp, 48h
0x18000a9b9  mov     rax, cs:__security_cookie
0x18000a9c0  xor     rax, rsp
0x18000a9c3  mov     [rsp+78h+var_40], rax
0x18000a9c8  mov     r14d, r9d
0x18000a9cb  movzx   ebp, r8w
0x18000a9cf  mov     ebx, edx
0x18000a9d1  mov     rdi, rcx
0x18000a9d4  cmp     byte ptr [rcx], 0
0x18000a9d7  jz      loc_18000AB1B
0x18000a9dd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a9e4  jnz     loc_18000AB1B
0x18000a9ea  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a9f1  test    rax, rax
0x18000a9f4  jz      short loc_18000AA03
0x18000a9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9fb  test    al, al
0x18000a9fd  jnz     loc_18000AB1B
0x18000aa03  lea     rsi, [rdi+28h]
0x18000aa07  mov     rcx, rsi; SRWLock
0x18000aa0a  call    cs:__imp_AcquireSRWLockExclusive
0x18000aa10  xor     eax, eax
0x18000aa12  mov     [rsp+78h+var_4A], ax
0x18000aa17  mov     [rsp+78h+Source], ebx
0x18000aa1b  mov     [rsp+78h+var_4C], bp
0x18000aa20  mov     [rsp+78h+var_48], r14d
0x18000aa25  lea     rbx, [rdi+0E8h]
0x18000aa2c  lea     ebp, [rax+0Ch]
0x18000aa2f  mov     edx, ebp; unsigned __int64
0x18000aa31  mov     rcx, rbx; this
0x18000aa34  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aa39  test    al, al
0x18000aa3b  jz      short loc_18000AA64
0x18000aa3d  mov     rcx, [rbx+8]; Destination
0x18000aa41  mov     rax, [rbx+10h]
0x18000aa45  sub     rax, rcx
0x18000aa48  cmp     rcx, [rbx+10h]
0x18000aa4c  sbb     rdx, rdx
0x18000aa4f  and     rdx, rax; DestinationSize
0x18000aa52  mov     r9d, ebp; SourceSize
0x18000aa55  lea     r8, [rsp+78h+Source]; Source
0x18000aa5a  call    cs:__imp_memcpy_s
0x18000aa60  add     [rbx+8], rbp
0x18000aa64  cmp     byte ptr [rdi+40h], 0
0x18000aa68  jnz     loc_18000AB0C
0x18000aa6e  cmp     qword ptr [rdi+38h], 0
0x18000aa73  jnz     short loc_18000AAE2
0x18000aa75  call    cs:__imp_GetLastError
0x18000aa7b  mov     r14d, eax
0x18000aa7e  xor     r8d, r8d; pcbe
0x18000aa81  mov     rdx, rdi; pv
0x18000aa84  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000aa8b  call    cs:__imp_CreateThreadpoolTimer
0x18000aa91  mov     r15, rax
0x18000aa94  mov     rbp, [rdi+38h]
0x18000aa98  test    rbp, rbp
0x18000aa9b  jz      short loc_18000AAD5
0x18000aa9d  call    cs:__imp_GetLastError
0x18000aaa3  mov     ebx, eax
0x18000aaa5  xor     r9d, r9d; msWindowLength
0x18000aaa8  xor     r8d, r8d; msPeriod
0x18000aaab  xor     edx, edx; pftDueTime
0x18000aaad  mov     rcx, rbp; pti
0x18000aab0  call    cs:__imp_SetThreadpoolTimer
0x18000aab6  mov     edx, 1; fCancelPendingCallbacks
0x18000aabb  mov     rcx, rbp; pti
0x18000aabe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aac4  mov     rcx, rbp; pti
0x18000aac7  call    cs:__imp_CloseThreadpoolTimer
0x18000aacd  mov     ecx, ebx; dwErrCode
0x18000aacf  call    cs:__imp_SetLastError
0x18000aad5  mov     [rdi+38h], r15
0x18000aad9  mov     ecx, r14d; dwErrCode
0x18000aadc  call    cs:__imp_SetLastError
0x18000aae2  mov     rcx, [rdi+38h]; pti
0x18000aae6  test    rcx, rcx
0x18000aae9  jz      short loc_18000AB0C
0x18000aaeb  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000aaf4  mov     r9d, 4E2h; msWindowLength
0x18000aafa  xor     r8d, r8d; msPeriod
0x18000aafd  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000ab02  call    cs:__imp_SetThreadpoolTimer
0x18000ab08  mov     byte ptr [rdi+40h], 1
0x18000ab0c  test    rsi, rsi
0x18000ab0f  jz      short loc_18000AB1B
0x18000ab11  mov     rcx, rsi; SRWLock
0x18000ab14  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab1a  nop
0x18000ab1b  mov     rcx, [rsp+78h+var_40]
0x18000ab20  xor     rcx, rsp; StackCookie
0x18000ab23  call    __security_check_cookie
0x18000ab28  add     rsp, 48h
0x18000ab2c  pop     r15
0x18000ab2e  pop     r14
0x18000ab30  pop     rdi
0x18000ab31  pop     rsi
0x18000ab32  pop     rbp
0x18000ab33  pop     rbx
0x18000ab34  retn
```
