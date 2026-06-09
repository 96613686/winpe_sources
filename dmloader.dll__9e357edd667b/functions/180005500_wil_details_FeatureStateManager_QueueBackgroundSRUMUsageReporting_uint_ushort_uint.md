# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005500`
- end: `0x18000569a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007340`

## callees

- `0x180001eae`
- `0x180001ef0`
- `0x180005500`
- `0x1800078bc`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005597`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005597`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800055c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005550`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005550`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005610`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005642`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000564f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005642`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000564f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800055fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800055fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005623`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005675`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005623`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005675`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000563a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000563a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005631`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005631`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rbp
  PTP_TIMER v14; // r15
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v17) = a3;
  LODWORD(v17) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v17;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      v14 = ThreadpoolTimer;
      if ( v13 )
      {
        v15 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v15);
      }
      pv[7].Ptr = v14;
      SetLastError(LastError);
    }
    v16 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v16 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v16, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180005500  push    rbx
0x180005502  push    rbp
0x180005503  push    rsi
0x180005504  push    rdi
0x180005505  push    r14
0x180005507  push    r15
0x180005509  sub     rsp, 38h
0x18000550d  cmp     byte ptr [rcx], 0
0x180005510  mov     ebp, r9d
0x180005513  movzx   ebx, r8w
0x180005517  mov     r14d, edx
0x18000551a  mov     rdi, rcx
0x18000551d  jz      loc_18000568D
0x180005523  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000552a  jnz     loc_18000568D
0x180005530  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005537  test    rax, rax
0x18000553a  jz      short loc_180005549
0x18000553c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005541  test    al, al
0x180005543  jnz     loc_18000568D
0x180005549  lea     rsi, [rdi+28h]
0x18000554d  mov     rcx, rsi; SRWLock
0x180005550  call    cs:__imp_AcquireSRWLockExclusive
0x180005556  xor     eax, eax
0x180005558  mov     word ptr [rsp+68h+var_48+4], bx
0x18000555d  lea     rbx, [rdi+0E8h]
0x180005564  mov     word ptr [rsp+68h+var_48+6], ax
0x180005569  mov     rcx, rbx; this
0x18000556c  mov     dword ptr [rsp+68h+var_48], r14d
0x180005571  lea     edx, [rax+0Ch]; unsigned __int64
0x180005574  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005579  test    al, al
0x18000557b  jz      short loc_1800055D7
0x18000557d  mov     rcx, [rbx+8]; void *
0x180005581  mov     rax, [rbx+10h]
0x180005585  sub     rax, rcx
0x180005588  cmp     rcx, [rbx+10h]
0x18000558c  sbb     r8, r8
0x18000558f  and     r8, rax; Size
0x180005592  test    rcx, rcx
0x180005595  jnz     short loc_1800055A5
0x180005597  call    cs:__imp__o__errno
0x18000559d  mov     dword ptr [rax], 16h
0x1800055a3  jmp     short loc_1800055CD
0x1800055a5  cmp     r8, 0Ch
0x1800055a9  jb      short loc_1800055BA
0x1800055ab  movsd   xmm0, [rsp+68h+var_48]
0x1800055b1  movsd   qword ptr [rcx], xmm0
0x1800055b5  mov     [rcx+8], ebp
0x1800055b8  jmp     short loc_1800055D2
0x1800055ba  xor     edx, edx; Val
0x1800055bc  call    memset_0
0x1800055c1  call    cs:__imp__o__errno
0x1800055c7  mov     dword ptr [rax], 22h ; '"'
0x1800055cd  call    _invalid_parameter_noinfo
0x1800055d2  add     qword ptr [rbx+8], 0Ch
0x1800055d7  cmp     byte ptr [rdi+40h], 0
0x1800055db  jnz     loc_18000567F
0x1800055e1  cmp     qword ptr [rdi+38h], 0
0x1800055e6  jnz     short loc_180005655
0x1800055e8  call    cs:__imp_GetLastError
0x1800055ee  xor     r8d, r8d; pcbe
0x1800055f1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800055f8  mov     rdx, rdi; pv
0x1800055fb  mov     r14d, eax
0x1800055fe  call    cs:__imp_CreateThreadpoolTimer
0x180005604  mov     rbp, [rdi+38h]
0x180005608  mov     r15, rax
0x18000560b  test    rbp, rbp
0x18000560e  jz      short loc_180005648
0x180005610  call    cs:__imp_GetLastError
0x180005616  xor     r9d, r9d; msWindowLength
0x180005619  xor     r8d, r8d; msPeriod
0x18000561c  xor     edx, edx; pftDueTime
0x18000561e  mov     rcx, rbp; pti
0x180005621  mov     ebx, eax
0x180005623  call    cs:__imp_SetThreadpoolTimer
0x180005629  mov     edx, 1; fCancelPendingCallbacks
0x18000562e  mov     rcx, rbp; pti
0x180005631  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005637  mov     rcx, rbp; pti
0x18000563a  call    cs:__imp_CloseThreadpoolTimer
0x180005640  mov     ecx, ebx; dwErrCode
0x180005642  call    cs:__imp_SetLastError
0x180005648  mov     ecx, r14d; dwErrCode
0x18000564b  mov     [rdi+38h], r15
0x18000564f  call    cs:__imp_SetLastError
0x180005655  mov     rcx, [rdi+38h]; pti
0x180005659  test    rcx, rcx
0x18000565c  jz      short loc_18000567F
0x18000565e  mov     r9d, 4E2h; msWindowLength
0x180005664  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000566d  xor     r8d, r8d; msPeriod
0x180005670  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180005675  call    cs:__imp_SetThreadpoolTimer
0x18000567b  mov     byte ptr [rdi+40h], 1
0x18000567f  test    rsi, rsi
0x180005682  jz      short loc_18000568D
0x180005684  mov     rcx, rsi; SRWLock
0x180005687  call    cs:__imp_ReleaseSRWLockExclusive
0x18000568d  add     rsp, 38h
0x180005691  pop     r15
0x180005693  pop     r14
0x180005695  pop     rdi
0x180005696  pop     rsi
0x180005697  pop     rbp
0x180005698  pop     rbx
0x180005699  retn
```
