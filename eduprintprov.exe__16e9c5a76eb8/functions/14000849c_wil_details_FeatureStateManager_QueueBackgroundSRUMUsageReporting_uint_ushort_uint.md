# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000849c`
- end: `0x140008637`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000a9d0`

## callees

- `0x1400030aa`
- `0x140003168`
- `0x14000849c`
- `0x14000bb1c`
- `0x140014010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008533`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000855d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008533`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000855d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400084ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400084ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400085ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000859a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000859a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400085d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400085d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400085bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008611`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400085bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008611`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400085cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400085cd`

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
0x14000849c  push    rbx
0x14000849e  push    rbp
0x14000849f  push    rsi
0x1400084a0  push    rdi
0x1400084a1  push    r14
0x1400084a3  push    r15
0x1400084a5  sub     rsp, 38h
0x1400084a9  mov     ebp, r9d
0x1400084ac  movzx   ebx, r8w
0x1400084b0  mov     r14d, edx
0x1400084b3  mov     rdi, rcx
0x1400084b6  cmp     byte ptr [rcx], 0
0x1400084b9  jz      loc_14000862A
0x1400084bf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400084c6  jnz     loc_14000862A
0x1400084cc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400084d3  test    rax, rax
0x1400084d6  jz      short loc_1400084E5
0x1400084d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084dd  test    al, al
0x1400084df  jnz     loc_14000862A
0x1400084e5  lea     rsi, [rdi+28h]
0x1400084e9  mov     rcx, rsi; SRWLock
0x1400084ec  call    cs:__imp_AcquireSRWLockExclusive
0x1400084f2  xor     eax, eax
0x1400084f4  mov     word ptr [rsp+68h+var_48+6], ax
0x1400084f9  mov     dword ptr [rsp+68h+var_48], r14d
0x1400084fe  mov     word ptr [rsp+68h+var_48+4], bx
0x140008503  lea     rbx, [rdi+0E8h]
0x14000850a  lea     edx, [rax+0Ch]; unsigned __int64
0x14000850d  mov     rcx, rbx; this
0x140008510  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008515  test    al, al
0x140008517  jz      short loc_140008573
0x140008519  mov     rcx, [rbx+8]; void *
0x14000851d  mov     rax, [rbx+10h]
0x140008521  sub     rax, rcx
0x140008524  cmp     rcx, [rbx+10h]
0x140008528  sbb     r8, r8
0x14000852b  and     r8, rax; Size
0x14000852e  test    rcx, rcx
0x140008531  jnz     short loc_140008541
0x140008533  call    cs:__imp__o__errno
0x140008539  mov     dword ptr [rax], 16h
0x14000853f  jmp     short loc_140008569
0x140008541  cmp     r8, 0Ch
0x140008545  jb      short loc_140008556
0x140008547  movsd   xmm0, [rsp+68h+var_48]
0x14000854d  movsd   qword ptr [rcx], xmm0
0x140008551  mov     [rcx+8], ebp
0x140008554  jmp     short loc_14000856E
0x140008556  xor     edx, edx; Val
0x140008558  call    memset_0
0x14000855d  call    cs:__imp__o__errno
0x140008563  mov     dword ptr [rax], 22h ; '"'
0x140008569  call    _invalid_parameter_noinfo
0x14000856e  add     qword ptr [rbx+8], 0Ch
0x140008573  cmp     byte ptr [rdi+40h], 0
0x140008577  jnz     loc_14000861B
0x14000857d  cmp     qword ptr [rdi+38h], 0
0x140008582  jnz     short loc_1400085F1
0x140008584  call    cs:__imp_GetLastError
0x14000858a  mov     r14d, eax
0x14000858d  xor     r8d, r8d; pcbe
0x140008590  mov     rdx, rdi; pv
0x140008593  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000859a  call    cs:__imp_CreateThreadpoolTimer
0x1400085a0  mov     r15, rax
0x1400085a3  mov     rbp, [rdi+38h]
0x1400085a7  test    rbp, rbp
0x1400085aa  jz      short loc_1400085E4
0x1400085ac  call    cs:__imp_GetLastError
0x1400085b2  mov     ebx, eax
0x1400085b4  xor     r9d, r9d; msWindowLength
0x1400085b7  xor     r8d, r8d; msPeriod
0x1400085ba  xor     edx, edx; pftDueTime
0x1400085bc  mov     rcx, rbp; pti
0x1400085bf  call    cs:__imp_SetThreadpoolTimer
0x1400085c5  mov     edx, 1; fCancelPendingCallbacks
0x1400085ca  mov     rcx, rbp; pti
0x1400085cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400085d3  mov     rcx, rbp; pti
0x1400085d6  call    cs:__imp_CloseThreadpoolTimer
0x1400085dc  mov     ecx, ebx; dwErrCode
0x1400085de  call    cs:__imp_SetLastError
0x1400085e4  mov     [rdi+38h], r15
0x1400085e8  mov     ecx, r14d; dwErrCode
0x1400085eb  call    cs:__imp_SetLastError
0x1400085f1  mov     rcx, [rdi+38h]; pti
0x1400085f5  test    rcx, rcx
0x1400085f8  jz      short loc_14000861B
0x1400085fa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140008603  mov     r9d, 4E2h; msWindowLength
0x140008609  xor     r8d, r8d; msPeriod
0x14000860c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140008611  call    cs:__imp_SetThreadpoolTimer
0x140008617  mov     byte ptr [rdi+40h], 1
0x14000861b  test    rsi, rsi
0x14000861e  jz      short loc_14000862A
0x140008620  mov     rcx, rsi; SRWLock
0x140008623  call    cs:__imp_ReleaseSRWLockExclusive
0x140008629  nop
0x14000862a  add     rsp, 38h
0x14000862e  pop     r15
0x140008630  pop     r14
0x140008632  pop     rdi
0x140008633  pop     rsi
0x140008634  pop     rbp
0x140008635  pop     rbx
0x140008636  retn
```
