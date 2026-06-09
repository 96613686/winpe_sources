# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008cd0`
- end: `0x180008e78`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `424`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000b7e0`

## callees

- `0x180002102`
- `0x180002132`
- `0x1800021f4`
- `0x180008cd0`
- `0x18000f49c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008de7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e26`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180008e08`
- `api-ms-win-core-threadpool-l1-1-0!WaitForThreadpoolTimerCallbacks` at `0x180008e08`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180008e11`
- `api-ms-win-core-threadpool-l1-1-0!CloseThreadpoolTimer` at `0x180008e11`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180008dfa`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180008e52`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180008dfa`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolTimer` at `0x180008e52`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x180008dd5`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolTimer` at `0x180008dd5`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+28h] [rbp-50h]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv) )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)o__errno_0(v10) = 34;
    }
    else
    {
      *(_DWORD *)o__errno_0(0) = 22;
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
0x180008cd0  push    rbx
0x180008cd2  push    rbp
0x180008cd3  push    rsi
0x180008cd4  push    rdi
0x180008cd5  push    r14
0x180008cd7  push    r15
0x180008cd9  sub     rsp, 48h
0x180008cdd  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x180008ce6  mov     ebp, r9d
0x180008ce9  movzx   ebx, r8w
0x180008ced  mov     r14d, edx
0x180008cf0  mov     rdi, rcx
0x180008cf3  cmp     byte ptr [rcx], 0
0x180008cf6  jz      loc_180008E6B
0x180008cfc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008d03  jnz     loc_180008E6B
0x180008d09  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008d10  test    rax, rax
0x180008d13  jz      short loc_180008D22
0x180008d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1a  test    al, al
0x180008d1c  jnz     loc_180008E6B
0x180008d22  lea     rsi, [rdi+28h]
0x180008d26  mov     rcx, rsi; SRWLock
0x180008d29  call    cs:__imp_AcquireSRWLockExclusive
0x180008d2f  xor     eax, eax
0x180008d31  mov     word ptr [rsp+78h+var_50+6], ax
0x180008d36  mov     dword ptr [rsp+78h+var_50], r14d
0x180008d3b  mov     word ptr [rsp+78h+var_50+4], bx
0x180008d40  lea     rbx, [rdi+0E8h]
0x180008d47  lea     edx, [rax+0Ch]; unsigned __int64
0x180008d4a  mov     rcx, rbx; this
0x180008d4d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008d52  test    al, al
0x180008d54  jz      short loc_180008DAE
0x180008d56  mov     rcx, [rbx+8]; void *
0x180008d5a  mov     rax, [rbx+10h]
0x180008d5e  sub     rax, rcx
0x180008d61  cmp     rcx, [rbx+10h]
0x180008d65  sbb     r8, r8
0x180008d68  and     r8, rax; Size
0x180008d6b  test    rcx, rcx
0x180008d6e  jnz     short loc_180008D7D
0x180008d70  call    _o__errno_0
0x180008d75  mov     dword ptr [rax], 16h
0x180008d7b  jmp     short loc_180008DA4
0x180008d7d  cmp     r8, 0Ch
0x180008d81  jb      short loc_180008D92
0x180008d83  movsd   xmm0, [rsp+78h+var_50]
0x180008d89  movsd   qword ptr [rcx], xmm0
0x180008d8d  mov     [rcx+8], ebp
0x180008d90  jmp     short loc_180008DA9
0x180008d92  xor     edx, edx; Val
0x180008d94  call    memset_0
0x180008d99  call    _o__errno_0
0x180008d9e  mov     dword ptr [rax], 22h ; '"'
0x180008da4  call    _invalid_parameter_noinfo
0x180008da9  add     qword ptr [rbx+8], 0Ch
0x180008dae  cmp     byte ptr [rdi+40h], 0
0x180008db2  jnz     loc_180008E5C
0x180008db8  cmp     qword ptr [rdi+38h], 0
0x180008dbd  jnz     short loc_180008E2C
0x180008dbf  call    cs:__imp_GetLastError
0x180008dc5  mov     r14d, eax
0x180008dc8  xor     r8d, r8d; pcbe
0x180008dcb  mov     rdx, rdi; pv
0x180008dce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008dd5  call    cs:__imp_CreateThreadpoolTimer
0x180008ddb  mov     r15, rax
0x180008dde  mov     rbp, [rdi+38h]
0x180008de2  test    rbp, rbp
0x180008de5  jz      short loc_180008E1F
0x180008de7  call    cs:__imp_GetLastError
0x180008ded  mov     ebx, eax
0x180008def  xor     r9d, r9d; msWindowLength
0x180008df2  xor     r8d, r8d; msPeriod
0x180008df5  xor     edx, edx; pftDueTime
0x180008df7  mov     rcx, rbp; pti
0x180008dfa  call    cs:__imp_SetThreadpoolTimer
0x180008e00  mov     edx, 1; fCancelPendingCallbacks
0x180008e05  mov     rcx, rbp; pti
0x180008e08  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008e0e  mov     rcx, rbp; pti
0x180008e11  call    cs:__imp_CloseThreadpoolTimer
0x180008e17  mov     ecx, ebx; dwErrCode
0x180008e19  call    cs:__imp_SetLastError
0x180008e1f  mov     [rdi+38h], r15
0x180008e23  mov     ecx, r14d; dwErrCode
0x180008e26  call    cs:__imp_SetLastError
0x180008e2c  mov     rcx, [rdi+38h]; pti
0x180008e30  test    rcx, rcx
0x180008e33  jz      short loc_180008E5C
0x180008e35  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008e41  mov     r9d, 4E2h; msWindowLength
0x180008e47  xor     r8d, r8d; msPeriod
0x180008e4a  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180008e52  call    cs:__imp_SetThreadpoolTimer
0x180008e58  mov     byte ptr [rdi+40h], 1
0x180008e5c  test    rsi, rsi
0x180008e5f  jz      short loc_180008E6B
0x180008e61  mov     rcx, rsi; SRWLock
0x180008e64  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e6a  nop
0x180008e6b  add     rsp, 48h
0x180008e6f  pop     r15
0x180008e71  pop     r14
0x180008e73  pop     rdi
0x180008e74  pop     rsi
0x180008e75  pop     rbp
0x180008e76  pop     rbx
0x180008e77  retn
```
