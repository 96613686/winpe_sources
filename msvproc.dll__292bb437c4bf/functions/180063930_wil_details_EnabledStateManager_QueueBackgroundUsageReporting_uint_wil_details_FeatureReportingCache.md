# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180063930`
- end: `0x180063bd0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `672`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180063f30`

## callees

- `0x1800432c0`
- `0x180054d8a`
- `0x180054ee4`
- `0x180058480`
- `0x180063930`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063ae1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063ae1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063980`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063980`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063bbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063a6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063a6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063a5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063a5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063a27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063a87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063a27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063a87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180063b51`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180063b51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180063b5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180063b5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180063b1e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180063b1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063b43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063b9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063b43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063b9b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  int v4; // ebx
  __int64 v6; // rcx
  DWORD dwLowDateTime; // r10d
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  DWORD LastError; // ebp
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r8
  char *v14; // rax
  char *v15; // rbx
  PVOID Ptr; // r8
  rsize_t v17; // r15
  PVOID v18; // r12
  HANDLE ProcessHeap; // rax
  _DWORD *v20; // r9
  size_t v21; // r8
  DWORD v22; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v24; // rbp
  PTP_TIMER v25; // r15
  DWORD v26; // ebx
  struct _TP_TIMER *v27; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF
  int v29; // [rsp+68h] [rbp+10h]

  v29 = a2;
  v4 = a2;
  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_35:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    dwLowDateTime = 0;
    v8 = (char *)pv[5].Ptr - (char *)pv[4].Ptr + 16;
    v9 = (char *)pv[6].Ptr - (char *)pv[4].Ptr;
    pftDueTime = 0;
    if ( v8 >= v9 )
    {
      v10 = 16;
      if ( 2 * v9 > 0x10 )
        v10 = 2 * v9;
      if ( v9 < v10 )
      {
        LastError = GetLastError();
        v12 = (v10 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v14 = (char *)wil::details::ProcessHeapAlloc(0, v12, v13);
        v15 = v14;
        if ( !v14 )
        {
          SetLastError(LastError);
          goto LABEL_28;
        }
        Ptr = pv[4].Ptr;
        v17 = (char *)pv[5].Ptr - (char *)Ptr;
        memcpy_s(v14, v12, Ptr, v17);
        v18 = pv[7].Ptr;
        pv[7].Ptr = v15;
        if ( v18 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v18);
        }
        pv[4].Ptr = v15;
        pv[5].Ptr = &v15[v17];
        pv[6].Ptr = &v15[v12];
        SetLastError(LastError);
        dwLowDateTime = pftDueTime.dwLowDateTime;
      }
      v4 = v29;
    }
    v20 = pv[5].Ptr;
    v21 = 0;
    if ( v20 < pv[6].Ptr )
      v21 = (char *)pv[6].Ptr - (char *)v20;
    if ( v20 )
    {
      if ( v21 >= 0x10 )
      {
        *v20 = v4;
        v20[1] = dwLowDateTime;
        *((_QWORD *)v20 + 1) = a3;
LABEL_27:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
LABEL_28:
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            v22 = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            v24 = (struct _TP_TIMER *)pv[2].Ptr;
            v25 = ThreadpoolTimer;
            if ( v24 )
            {
              v26 = GetLastError();
              SetThreadpoolTimer(v24, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(v24, 1);
              CloseThreadpoolTimer(v24);
              SetLastError(v26);
            }
            pv[2].Ptr = v25;
            SetLastError(v22);
          }
          v27 = (struct _TP_TIMER *)pv[2].Ptr;
          if ( v27 )
          {
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v27, &pftDueTime, 0, 0x124F8u);
            LOBYTE(pv[3].Ptr) = 1;
          }
        }
        goto LABEL_35;
      }
      memset_0(pv[5].Ptr, 0, v21);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v6, v9, v21) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x180063930  mov     [rsp+arg_8], edx
0x180063934  push    rbx
0x180063935  push    rdi
0x180063936  push    r13
0x180063938  sub     rsp, 40h
0x18006393c  mov     eax, [rcx]
0x18006393e  mov     r13, r8
0x180063941  mov     ebx, edx
0x180063943  mov     rdi, rcx
0x180063946  test    eax, eax
0x180063948  jz      loc_180063BC7
0x18006394e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180063955  jnz     loc_180063BC7
0x18006395b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180063962  test    rax, rax
0x180063965  jz      short loc_180063974
0x180063967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006396c  test    al, al
0x18006396e  jnz     loc_180063BC7
0x180063974  mov     [rsp+58h+var_20], rsi
0x180063979  lea     rsi, [rdi+8]
0x18006397d  mov     rcx, rsi; SRWLock
0x180063980  call    cs:__imp_AcquireSRWLockExclusive
0x180063986  mov     eax, [rdi]
0x180063988  test    eax, eax
0x18006398a  jz      loc_180063BB4
0x180063990  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180063997  jnz     loc_180063BB4
0x18006399d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800639a4  test    rax, rax
0x1800639a7  jz      short loc_1800639B6
0x1800639a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639ae  test    al, al
0x1800639b0  jnz     loc_180063BB4
0x1800639b6  mov     rax, [rdi+28h]
0x1800639ba  xor     r10d, r10d
0x1800639bd  sub     rax, [rdi+20h]
0x1800639c1  mov     rdx, [rdi+30h]
0x1800639c5  add     rax, 10h
0x1800639c9  sub     rdx, [rdi+20h]
0x1800639cd  mov     [rsp+58h+arg_10], rbp
0x1800639d2  mov     [rsp+58h+var_30], r14
0x1800639d7  mov     [rsp+58h+var_38], r15
0x1800639dc  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], r10
0x1800639e1  cmp     rax, rdx
0x1800639e4  jb      loc_180063A9B
0x1800639ea  lea     rax, [rdx+rdx]
0x1800639ee  mov     ebx, 10h
0x1800639f3  cmp     rax, rbx
0x1800639f6  cmova   rbx, rax
0x1800639fa  cmp     rdx, rbx
0x1800639fd  jnb     loc_180063A97
0x180063a03  call    cs:__imp_GetLastError
0x180063a09  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180063a0d  xor     ecx, ecx; dwFlags
0x180063a0f  mov     ebp, eax
0x180063a11  lea     r14, [rbx+40h]
0x180063a15  mov     rdx, r14; dwBytes
0x180063a18  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180063a1d  mov     rbx, rax
0x180063a20  test    rax, rax
0x180063a23  jnz     short loc_180063A32
0x180063a25  mov     ecx, ebp; dwErrCode
0x180063a27  call    cs:__imp_SetLastError
0x180063a2d  jmp     loc_180063AF7
0x180063a32  mov     r8, [rdi+20h]; Source
0x180063a36  mov     rdx, r14; DestinationSize
0x180063a39  mov     r15, [rdi+28h]
0x180063a3d  mov     rcx, rbx; Destination
0x180063a40  sub     r15, r8
0x180063a43  mov     [rsp+58h+var_28], r12
0x180063a48  mov     r9, r15; SourceSize
0x180063a4b  call    memcpy_s
0x180063a50  mov     r12, [rdi+38h]
0x180063a54  mov     [rdi+38h], rbx
0x180063a58  test    r12, r12
0x180063a5b  jz      short loc_180063A71
0x180063a5d  call    cs:__imp_GetProcessHeap
0x180063a63  mov     r8, r12; lpMem
0x180063a66  xor     edx, edx; dwFlags
0x180063a68  mov     rcx, rax; hHeap
0x180063a6b  call    cs:__imp_HeapFree
0x180063a71  lea     rax, [r15+rbx]
0x180063a75  mov     [rdi+20h], rbx
0x180063a79  mov     [rdi+28h], rax
0x180063a7d  mov     ecx, ebp; dwErrCode
0x180063a7f  lea     rax, [r14+rbx]
0x180063a83  mov     [rdi+30h], rax
0x180063a87  call    cs:__imp_SetLastError
0x180063a8d  mov     r10, qword ptr [rsp+58h+pftDueTime.dwLowDateTime]
0x180063a92  mov     r12, [rsp+58h+var_28]
0x180063a97  mov     ebx, [rsp+58h+arg_8]
0x180063a9b  mov     r9, [rdi+28h]
0x180063a9f  xor     r8d, r8d
0x180063aa2  mov     rax, [rdi+30h]
0x180063aa6  sub     rax, r9
0x180063aa9  cmp     r9, [rdi+30h]
0x180063aad  cmovb   r8, rax; Size
0x180063ab1  test    r9, r9
0x180063ab4  jnz     short loc_180063AC4
0x180063ab6  call    cs:__imp__o__errno
0x180063abc  mov     dword ptr [rax], 16h
0x180063ac2  jmp     short loc_180063AED
0x180063ac4  cmp     r8, 10h
0x180063ac8  jb      short loc_180063AD7
0x180063aca  mov     [r9], ebx
0x180063acd  mov     [r9+4], r10d
0x180063ad1  mov     [r9+8], r13
0x180063ad5  jmp     short loc_180063AF2
0x180063ad7  xor     edx, edx; Val
0x180063ad9  mov     rcx, r9; void *
0x180063adc  call    memset_0
0x180063ae1  call    cs:__imp__o__errno
0x180063ae7  mov     dword ptr [rax], 22h ; '"'
0x180063aed  call    _invalid_parameter_noinfo
0x180063af2  add     qword ptr [rdi+28h], 10h
0x180063af7  cmp     byte ptr [rdi+18h], 0
0x180063afb  jnz     loc_180063BA5
0x180063b01  cmp     qword ptr [rdi+10h], 0
0x180063b06  jnz     short loc_180063B75
0x180063b08  call    cs:__imp_GetLastError
0x180063b0e  xor     r8d, r8d; pcbe
0x180063b11  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180063b18  mov     rdx, rdi; pv
0x180063b1b  mov     r14d, eax
0x180063b1e  call    cs:__imp_CreateThreadpoolTimer
0x180063b24  mov     rbp, [rdi+10h]
0x180063b28  mov     r15, rax
0x180063b2b  test    rbp, rbp
0x180063b2e  jz      short loc_180063B68
0x180063b30  call    cs:__imp_GetLastError
0x180063b36  xor     r9d, r9d; msWindowLength
0x180063b39  xor     r8d, r8d; msPeriod
0x180063b3c  xor     edx, edx; pftDueTime
0x180063b3e  mov     rcx, rbp; pti
0x180063b41  mov     ebx, eax
0x180063b43  call    cs:__imp_SetThreadpoolTimer
0x180063b49  mov     edx, 1; fCancelPendingCallbacks
0x180063b4e  mov     rcx, rbp; pti
0x180063b51  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180063b57  mov     rcx, rbp; pti
0x180063b5a  call    cs:__imp_CloseThreadpoolTimer
0x180063b60  mov     ecx, ebx; dwErrCode
0x180063b62  call    cs:__imp_SetLastError
0x180063b68  mov     ecx, r14d; dwErrCode
0x180063b6b  mov     [rdi+10h], r15
0x180063b6f  call    cs:__imp_SetLastError
0x180063b75  mov     rcx, [rdi+10h]; pti
0x180063b79  test    rcx, rcx
0x180063b7c  jz      short loc_180063BA5
0x180063b7e  mov     rax, 0FFFFFFFF4D2FA200h
0x180063b88  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180063b8d  mov     r9d, 124F8h; msWindowLength
0x180063b93  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180063b98  xor     r8d, r8d; msPeriod
0x180063b9b  call    cs:__imp_SetThreadpoolTimer
0x180063ba1  mov     byte ptr [rdi+18h], 1
0x180063ba5  mov     r15, [rsp+58h+var_38]
0x180063baa  mov     r14, [rsp+58h+var_30]
0x180063baf  mov     rbp, [rsp+58h+arg_10]
0x180063bb4  test    rsi, rsi
0x180063bb7  jz      short loc_180063BC2
0x180063bb9  mov     rcx, rsi; SRWLock
0x180063bbc  call    cs:__imp_ReleaseSRWLockExclusive
0x180063bc2  mov     rsi, [rsp+58h+var_20]
0x180063bc7  add     rsp, 40h
0x180063bcb  pop     r13
0x180063bcd  pop     rdi
0x180063bce  pop     rbx
0x180063bcf  retn
```
