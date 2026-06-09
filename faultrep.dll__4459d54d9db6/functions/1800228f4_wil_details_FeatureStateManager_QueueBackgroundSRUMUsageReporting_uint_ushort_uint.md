# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800228f4`
- end: `0x180022a8f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800243e0`

## callees

- `0x1800033e2`
- `0x180003474`
- `0x1800228f4`
- `0x1800247fc`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002298b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800229b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002298b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800229b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022944`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022944`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022a7b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022a25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022a25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022a2e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022a2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800229f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800229f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a69`

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
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
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
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800228f4  push    rbx
0x1800228f6  push    rbp
0x1800228f7  push    rsi
0x1800228f8  push    rdi
0x1800228f9  push    r14
0x1800228fb  push    r15
0x1800228fd  sub     rsp, 38h
0x180022901  mov     ebp, r9d
0x180022904  movzx   ebx, r8w
0x180022908  mov     r14d, edx
0x18002290b  mov     rdi, rcx
0x18002290e  cmp     byte ptr [rcx], 0
0x180022911  jz      loc_180022A82
0x180022917  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002291e  jnz     loc_180022A82
0x180022924  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002292b  test    rax, rax
0x18002292e  jz      short loc_18002293D
0x180022930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022935  test    al, al
0x180022937  jnz     loc_180022A82
0x18002293d  lea     rsi, [rdi+28h]
0x180022941  mov     rcx, rsi; SRWLock
0x180022944  call    cs:__imp_AcquireSRWLockExclusive
0x18002294a  xor     eax, eax
0x18002294c  mov     word ptr [rsp+68h+var_48+6], ax
0x180022951  mov     dword ptr [rsp+68h+var_48], r14d
0x180022956  mov     word ptr [rsp+68h+var_48+4], bx
0x18002295b  lea     rbx, [rdi+0E8h]
0x180022962  lea     edx, [rax+0Ch]; unsigned __int64
0x180022965  mov     rcx, rbx; this
0x180022968  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002296d  test    al, al
0x18002296f  jz      short loc_1800229CB
0x180022971  mov     rcx, [rbx+8]; void *
0x180022975  mov     rax, [rbx+10h]
0x180022979  sub     rax, rcx
0x18002297c  cmp     rcx, [rbx+10h]
0x180022980  sbb     r8, r8
0x180022983  and     r8, rax; Size
0x180022986  test    rcx, rcx
0x180022989  jnz     short loc_180022999
0x18002298b  call    cs:__imp__o__errno
0x180022991  mov     dword ptr [rax], 16h
0x180022997  jmp     short loc_1800229C1
0x180022999  cmp     r8, 0Ch
0x18002299d  jb      short loc_1800229AE
0x18002299f  movsd   xmm0, [rsp+68h+var_48]
0x1800229a5  movsd   qword ptr [rcx], xmm0
0x1800229a9  mov     [rcx+8], ebp
0x1800229ac  jmp     short loc_1800229C6
0x1800229ae  xor     edx, edx; Val
0x1800229b0  call    memset_0
0x1800229b5  call    cs:__imp__o__errno
0x1800229bb  mov     dword ptr [rax], 22h ; '"'
0x1800229c1  call    _invalid_parameter_noinfo
0x1800229c6  add     qword ptr [rbx+8], 0Ch
0x1800229cb  cmp     byte ptr [rdi+40h], 0
0x1800229cf  jnz     loc_180022A73
0x1800229d5  cmp     qword ptr [rdi+38h], 0
0x1800229da  jnz     short loc_180022A49
0x1800229dc  call    cs:__imp_GetLastError
0x1800229e2  mov     r14d, eax
0x1800229e5  xor     r8d, r8d; pcbe
0x1800229e8  mov     rdx, rdi; pv
0x1800229eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800229f2  call    cs:__imp_CreateThreadpoolTimer
0x1800229f8  mov     r15, rax
0x1800229fb  mov     rbp, [rdi+38h]
0x1800229ff  test    rbp, rbp
0x180022a02  jz      short loc_180022A3C
0x180022a04  call    cs:__imp_GetLastError
0x180022a0a  mov     ebx, eax
0x180022a0c  xor     r9d, r9d; msWindowLength
0x180022a0f  xor     r8d, r8d; msPeriod
0x180022a12  xor     edx, edx; pftDueTime
0x180022a14  mov     rcx, rbp; pti
0x180022a17  call    cs:__imp_SetThreadpoolTimer
0x180022a1d  mov     edx, 1; fCancelPendingCallbacks
0x180022a22  mov     rcx, rbp; pti
0x180022a25  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022a2b  mov     rcx, rbp; pti
0x180022a2e  call    cs:__imp_CloseThreadpoolTimer
0x180022a34  mov     ecx, ebx; dwErrCode
0x180022a36  call    cs:__imp_SetLastError
0x180022a3c  mov     [rdi+38h], r15
0x180022a40  mov     ecx, r14d; dwErrCode
0x180022a43  call    cs:__imp_SetLastError
0x180022a49  mov     rcx, [rdi+38h]; pti
0x180022a4d  test    rcx, rcx
0x180022a50  jz      short loc_180022A73
0x180022a52  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180022a5b  mov     r9d, 4E2h; msWindowLength
0x180022a61  xor     r8d, r8d; msPeriod
0x180022a64  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180022a69  call    cs:__imp_SetThreadpoolTimer
0x180022a6f  mov     byte ptr [rdi+40h], 1
0x180022a73  test    rsi, rsi
0x180022a76  jz      short loc_180022A82
0x180022a78  mov     rcx, rsi; SRWLock
0x180022a7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180022a81  nop
0x180022a82  add     rsp, 38h
0x180022a86  pop     r15
0x180022a88  pop     r14
0x180022a8a  pop     rdi
0x180022a8b  pop     rsi
0x180022a8c  pop     rbp
0x180022a8d  pop     rbx
0x180022a8e  retn
```
