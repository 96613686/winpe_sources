# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140009124`
- end: `0x1400092bf`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000c7c0`

## callees

- `0x140002b82`
- `0x140002c2c`
- `0x140009124`
- `0x14000d04c`
- `0x140011010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140009266`
- `KERNEL32!SetLastError` at `0x140009273`
- `KERNEL32!SetLastError` at `0x140009266`
- `KERNEL32!SetLastError` at `0x140009273`
- `KERNEL32!SetThreadpoolTimer` at `0x140009247`
- `KERNEL32!SetThreadpoolTimer` at `0x140009299`
- `KERNEL32!SetThreadpoolTimer` at `0x140009247`
- `KERNEL32!SetThreadpoolTimer` at `0x140009299`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009255`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140009255`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000925e`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000925e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009174`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009174`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009222`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009222`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400092ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400092ab`
- `KERNEL32!GetLastError` at `0x14000920c`
- `KERNEL32!GetLastError` at `0x140009234`
- `KERNEL32!GetLastError` at `0x14000920c`
- `KERNEL32!GetLastError` at `0x140009234`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400091bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400091e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400091bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400091e5`

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
0x140009124  push    rbx
0x140009126  push    rbp
0x140009127  push    rsi
0x140009128  push    rdi
0x140009129  push    r14
0x14000912b  push    r15
0x14000912d  sub     rsp, 38h
0x140009131  mov     ebp, r9d
0x140009134  movzx   ebx, r8w
0x140009138  mov     r14d, edx
0x14000913b  mov     rdi, rcx
0x14000913e  cmp     byte ptr [rcx], 0
0x140009141  jz      loc_1400092B2
0x140009147  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000914e  jnz     loc_1400092B2
0x140009154  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000915b  test    rax, rax
0x14000915e  jz      short loc_14000916D
0x140009160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009165  test    al, al
0x140009167  jnz     loc_1400092B2
0x14000916d  lea     rsi, [rdi+28h]
0x140009171  mov     rcx, rsi; SRWLock
0x140009174  call    cs:__imp_AcquireSRWLockExclusive
0x14000917a  xor     eax, eax
0x14000917c  mov     word ptr [rsp+68h+var_48+6], ax
0x140009181  mov     dword ptr [rsp+68h+var_48], r14d
0x140009186  mov     word ptr [rsp+68h+var_48+4], bx
0x14000918b  lea     rbx, [rdi+0E8h]
0x140009192  lea     edx, [rax+0Ch]; unsigned __int64
0x140009195  mov     rcx, rbx; this
0x140009198  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000919d  test    al, al
0x14000919f  jz      short loc_1400091FB
0x1400091a1  mov     rcx, [rbx+8]; void *
0x1400091a5  mov     rax, [rbx+10h]
0x1400091a9  sub     rax, rcx
0x1400091ac  cmp     rcx, [rbx+10h]
0x1400091b0  sbb     r8, r8
0x1400091b3  and     r8, rax; Size
0x1400091b6  test    rcx, rcx
0x1400091b9  jnz     short loc_1400091C9
0x1400091bb  call    cs:__imp__o__errno
0x1400091c1  mov     dword ptr [rax], 16h
0x1400091c7  jmp     short loc_1400091F1
0x1400091c9  cmp     r8, 0Ch
0x1400091cd  jb      short loc_1400091DE
0x1400091cf  movsd   xmm0, [rsp+68h+var_48]
0x1400091d5  movsd   qword ptr [rcx], xmm0
0x1400091d9  mov     [rcx+8], ebp
0x1400091dc  jmp     short loc_1400091F6
0x1400091de  xor     edx, edx; Val
0x1400091e0  call    memset_0
0x1400091e5  call    cs:__imp__o__errno
0x1400091eb  mov     dword ptr [rax], 22h ; '"'
0x1400091f1  call    _invalid_parameter_noinfo
0x1400091f6  add     qword ptr [rbx+8], 0Ch
0x1400091fb  cmp     byte ptr [rdi+40h], 0
0x1400091ff  jnz     loc_1400092A3
0x140009205  cmp     qword ptr [rdi+38h], 0
0x14000920a  jnz     short loc_140009279
0x14000920c  call    cs:__imp_GetLastError
0x140009212  mov     r14d, eax
0x140009215  xor     r8d, r8d; pcbe
0x140009218  mov     rdx, rdi; pv
0x14000921b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009222  call    cs:__imp_CreateThreadpoolTimer
0x140009228  mov     r15, rax
0x14000922b  mov     rbp, [rdi+38h]
0x14000922f  test    rbp, rbp
0x140009232  jz      short loc_14000926C
0x140009234  call    cs:__imp_GetLastError
0x14000923a  mov     ebx, eax
0x14000923c  xor     r9d, r9d; msWindowLength
0x14000923f  xor     r8d, r8d; msPeriod
0x140009242  xor     edx, edx; pftDueTime
0x140009244  mov     rcx, rbp; pti
0x140009247  call    cs:__imp_SetThreadpoolTimer
0x14000924d  mov     edx, 1; fCancelPendingCallbacks
0x140009252  mov     rcx, rbp; pti
0x140009255  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000925b  mov     rcx, rbp; pti
0x14000925e  call    cs:__imp_CloseThreadpoolTimer
0x140009264  mov     ecx, ebx; dwErrCode
0x140009266  call    cs:__imp_SetLastError
0x14000926c  mov     [rdi+38h], r15
0x140009270  mov     ecx, r14d; dwErrCode
0x140009273  call    cs:__imp_SetLastError
0x140009279  mov     rcx, [rdi+38h]; pti
0x14000927d  test    rcx, rcx
0x140009280  jz      short loc_1400092A3
0x140009282  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000928b  mov     r9d, 4E2h; msWindowLength
0x140009291  xor     r8d, r8d; msPeriod
0x140009294  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140009299  call    cs:__imp_SetThreadpoolTimer
0x14000929f  mov     byte ptr [rdi+40h], 1
0x1400092a3  test    rsi, rsi
0x1400092a6  jz      short loc_1400092B2
0x1400092a8  mov     rcx, rsi; SRWLock
0x1400092ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1400092b1  nop
0x1400092b2  add     rsp, 38h
0x1400092b6  pop     r15
0x1400092b8  pop     r14
0x1400092ba  pop     rdi
0x1400092bb  pop     rsi
0x1400092bc  pop     rbp
0x1400092bd  pop     rbx
0x1400092be  retn
```
