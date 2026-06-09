# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800075b0`
- end: `0x18000774a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009e70`

## callees

- `0x180002b1a`
- `0x180002b60`
- `0x1800075b0`
- `0x18000a570`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007647`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007671`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007647`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007671`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800076ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800076ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800076d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007725`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800076ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800076ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800076e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800076e1`

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
0x1800075b0  push    rbx
0x1800075b2  push    rbp
0x1800075b3  push    rsi
0x1800075b4  push    rdi
0x1800075b5  push    r14
0x1800075b7  push    r15
0x1800075b9  sub     rsp, 38h
0x1800075bd  cmp     byte ptr [rcx], 0
0x1800075c0  mov     ebp, r9d
0x1800075c3  movzx   ebx, r8w
0x1800075c7  mov     r14d, edx
0x1800075ca  mov     rdi, rcx
0x1800075cd  jz      loc_18000773D
0x1800075d3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800075da  jnz     loc_18000773D
0x1800075e0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800075e7  test    rax, rax
0x1800075ea  jz      short loc_1800075F9
0x1800075ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f1  test    al, al
0x1800075f3  jnz     loc_18000773D
0x1800075f9  lea     rsi, [rdi+28h]
0x1800075fd  mov     rcx, rsi; SRWLock
0x180007600  call    cs:__imp_AcquireSRWLockExclusive
0x180007606  xor     eax, eax
0x180007608  mov     word ptr [rsp+68h+var_48+4], bx
0x18000760d  lea     rbx, [rdi+0E8h]
0x180007614  mov     word ptr [rsp+68h+var_48+6], ax
0x180007619  mov     rcx, rbx; this
0x18000761c  mov     dword ptr [rsp+68h+var_48], r14d
0x180007621  lea     edx, [rax+0Ch]; unsigned __int64
0x180007624  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007629  test    al, al
0x18000762b  jz      short loc_180007687
0x18000762d  mov     rcx, [rbx+8]; void *
0x180007631  mov     rax, [rbx+10h]
0x180007635  sub     rax, rcx
0x180007638  cmp     rcx, [rbx+10h]
0x18000763c  sbb     r8, r8
0x18000763f  and     r8, rax; Size
0x180007642  test    rcx, rcx
0x180007645  jnz     short loc_180007655
0x180007647  call    cs:__imp__o__errno
0x18000764d  mov     dword ptr [rax], 16h
0x180007653  jmp     short loc_18000767D
0x180007655  cmp     r8, 0Ch
0x180007659  jb      short loc_18000766A
0x18000765b  movsd   xmm0, [rsp+68h+var_48]
0x180007661  movsd   qword ptr [rcx], xmm0
0x180007665  mov     [rcx+8], ebp
0x180007668  jmp     short loc_180007682
0x18000766a  xor     edx, edx; Val
0x18000766c  call    memset_0
0x180007671  call    cs:__imp__o__errno
0x180007677  mov     dword ptr [rax], 22h ; '"'
0x18000767d  call    _invalid_parameter_noinfo
0x180007682  add     qword ptr [rbx+8], 0Ch
0x180007687  cmp     byte ptr [rdi+40h], 0
0x18000768b  jnz     loc_18000772F
0x180007691  cmp     qword ptr [rdi+38h], 0
0x180007696  jnz     short loc_180007705
0x180007698  call    cs:__imp_GetLastError
0x18000769e  xor     r8d, r8d; pcbe
0x1800076a1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800076a8  mov     rdx, rdi; pv
0x1800076ab  mov     r14d, eax
0x1800076ae  call    cs:__imp_CreateThreadpoolTimer
0x1800076b4  mov     rbp, [rdi+38h]
0x1800076b8  mov     r15, rax
0x1800076bb  test    rbp, rbp
0x1800076be  jz      short loc_1800076F8
0x1800076c0  call    cs:__imp_GetLastError
0x1800076c6  xor     r9d, r9d; msWindowLength
0x1800076c9  xor     r8d, r8d; msPeriod
0x1800076cc  xor     edx, edx; pftDueTime
0x1800076ce  mov     rcx, rbp; pti
0x1800076d1  mov     ebx, eax
0x1800076d3  call    cs:__imp_SetThreadpoolTimer
0x1800076d9  mov     edx, 1; fCancelPendingCallbacks
0x1800076de  mov     rcx, rbp; pti
0x1800076e1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800076e7  mov     rcx, rbp; pti
0x1800076ea  call    cs:__imp_CloseThreadpoolTimer
0x1800076f0  mov     ecx, ebx; dwErrCode
0x1800076f2  call    cs:__imp_SetLastError
0x1800076f8  mov     ecx, r14d; dwErrCode
0x1800076fb  mov     [rdi+38h], r15
0x1800076ff  call    cs:__imp_SetLastError
0x180007705  mov     rcx, [rdi+38h]; pti
0x180007709  test    rcx, rcx
0x18000770c  jz      short loc_18000772F
0x18000770e  mov     r9d, 4E2h; msWindowLength
0x180007714  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000771d  xor     r8d, r8d; msPeriod
0x180007720  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180007725  call    cs:__imp_SetThreadpoolTimer
0x18000772b  mov     byte ptr [rdi+40h], 1
0x18000772f  test    rsi, rsi
0x180007732  jz      short loc_18000773D
0x180007734  mov     rcx, rsi; SRWLock
0x180007737  call    cs:__imp_ReleaseSRWLockExclusive
0x18000773d  add     rsp, 38h
0x180007741  pop     r15
0x180007743  pop     r14
0x180007745  pop     rdi
0x180007746  pop     rsi
0x180007747  pop     rbp
0x180007748  pop     rbx
0x180007749  retn
```
