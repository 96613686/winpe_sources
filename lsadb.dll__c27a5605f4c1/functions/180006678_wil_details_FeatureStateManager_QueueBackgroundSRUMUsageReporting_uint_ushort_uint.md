# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006678`
- end: `0x180006812`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008730`

## callees

- `0x180001f56`
- `0x180001fb8`
- `0x180006678`
- `0x180008d0c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000670f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006739`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000670f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800067ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800067ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006776`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000679b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800067ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000679b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800067ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800067a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800067a9`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v16; // rbp
  PTP_TIMER v17; // r15
  DWORD v18; // ebx
  struct _TP_TIMER *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v20) = a3;
  LODWORD(v20) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v20;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      v17 = ThreadpoolTimer;
      if ( v16 )
      {
        v18 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v18);
      }
      pv[7].Ptr = v17;
      SetLastError(LastError);
    }
    v19 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v19 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180006678  push    rbx
0x18000667a  push    rbp
0x18000667b  push    rsi
0x18000667c  push    rdi
0x18000667d  push    r14
0x18000667f  push    r15
0x180006681  sub     rsp, 38h
0x180006685  cmp     byte ptr [rcx], 0
0x180006688  mov     ebp, r9d
0x18000668b  movzx   ebx, r8w
0x18000668f  mov     r14d, edx
0x180006692  mov     rdi, rcx
0x180006695  jz      loc_180006805
0x18000669b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800066a2  jnz     loc_180006805
0x1800066a8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800066af  test    rax, rax
0x1800066b2  jz      short loc_1800066C1
0x1800066b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b9  test    al, al
0x1800066bb  jnz     loc_180006805
0x1800066c1  lea     rsi, [rdi+28h]
0x1800066c5  mov     rcx, rsi; SRWLock
0x1800066c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800066ce  xor     eax, eax
0x1800066d0  mov     word ptr [rsp+68h+var_48+4], bx
0x1800066d5  lea     rbx, [rdi+0E8h]
0x1800066dc  mov     word ptr [rsp+68h+var_48+6], ax
0x1800066e1  mov     rcx, rbx; this
0x1800066e4  mov     dword ptr [rsp+68h+var_48], r14d
0x1800066e9  lea     edx, [rax+0Ch]; unsigned __int64
0x1800066ec  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800066f1  test    al, al
0x1800066f3  jz      short loc_18000674F
0x1800066f5  mov     rcx, [rbx+8]; void *
0x1800066f9  mov     rax, [rbx+10h]
0x1800066fd  sub     rax, rcx
0x180006700  cmp     rcx, [rbx+10h]
0x180006704  sbb     r8, r8
0x180006707  and     r8, rax; Size
0x18000670a  test    rcx, rcx
0x18000670d  jnz     short loc_18000671D
0x18000670f  call    cs:__imp__o__errno
0x180006715  mov     dword ptr [rax], 16h
0x18000671b  jmp     short loc_180006745
0x18000671d  cmp     r8, 0Ch
0x180006721  jb      short loc_180006732
0x180006723  movsd   xmm0, [rsp+68h+var_48]
0x180006729  movsd   qword ptr [rcx], xmm0
0x18000672d  mov     [rcx+8], ebp
0x180006730  jmp     short loc_18000674A
0x180006732  xor     edx, edx; Val
0x180006734  call    memset_0
0x180006739  call    cs:__imp__o__errno
0x18000673f  mov     dword ptr [rax], 22h ; '"'
0x180006745  call    _invalid_parameter_noinfo
0x18000674a  add     qword ptr [rbx+8], 0Ch
0x18000674f  cmp     byte ptr [rdi+40h], 0
0x180006753  jnz     loc_1800067F7
0x180006759  cmp     qword ptr [rdi+38h], 0
0x18000675e  jnz     short loc_1800067CD
0x180006760  call    cs:__imp_GetLastError
0x180006766  xor     r8d, r8d; pcbe
0x180006769  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006770  mov     rdx, rdi; pv
0x180006773  mov     r14d, eax
0x180006776  call    cs:__imp_CreateThreadpoolTimer
0x18000677c  mov     rbp, [rdi+38h]
0x180006780  mov     r15, rax
0x180006783  test    rbp, rbp
0x180006786  jz      short loc_1800067C0
0x180006788  call    cs:__imp_GetLastError
0x18000678e  xor     r9d, r9d; msWindowLength
0x180006791  xor     r8d, r8d; msPeriod
0x180006794  xor     edx, edx; pftDueTime
0x180006796  mov     rcx, rbp; pti
0x180006799  mov     ebx, eax
0x18000679b  call    cs:__imp_SetThreadpoolTimer
0x1800067a1  mov     edx, 1; fCancelPendingCallbacks
0x1800067a6  mov     rcx, rbp; pti
0x1800067a9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800067af  mov     rcx, rbp; pti
0x1800067b2  call    cs:__imp_CloseThreadpoolTimer
0x1800067b8  mov     ecx, ebx; dwErrCode
0x1800067ba  call    cs:__imp_SetLastError
0x1800067c0  mov     ecx, r14d; dwErrCode
0x1800067c3  mov     [rdi+38h], r15
0x1800067c7  call    cs:__imp_SetLastError
0x1800067cd  mov     rcx, [rdi+38h]; pti
0x1800067d1  test    rcx, rcx
0x1800067d4  jz      short loc_1800067F7
0x1800067d6  mov     r9d, 4E2h; msWindowLength
0x1800067dc  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800067e5  xor     r8d, r8d; msPeriod
0x1800067e8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800067ed  call    cs:__imp_SetThreadpoolTimer
0x1800067f3  mov     byte ptr [rdi+40h], 1
0x1800067f7  test    rsi, rsi
0x1800067fa  jz      short loc_180006805
0x1800067fc  mov     rcx, rsi; SRWLock
0x1800067ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180006805  add     rsp, 38h
0x180006809  pop     r15
0x18000680b  pop     r14
0x18000680d  pop     rdi
0x18000680e  pop     rsi
0x18000680f  pop     rbp
0x180006810  pop     rbx
0x180006811  retn
```
