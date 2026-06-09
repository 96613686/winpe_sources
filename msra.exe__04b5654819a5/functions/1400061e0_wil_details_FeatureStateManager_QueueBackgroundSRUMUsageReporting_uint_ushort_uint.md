# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400061e0`
- end: `0x14000634f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140008aa0`

## callees

- `0x1400061e0`
- `0x14000955c`
- `0x140009900`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400062e6`
- `KERNEL32!SetLastError` at `0x1400062e6`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400062cd`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400062cd`
- `KERNEL32!SetThreadpoolTimer` at `0x140006311`
- `KERNEL32!SetThreadpoolTimer` at `0x140006311`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000623c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000623c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006329`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006329`
- `KERNEL32!GetLastError` at `0x1400062b2`
- `KERNEL32!GetLastError` at `0x1400062b2`
- `msvcrt!memcpy_s` at `0x140006292`
- `msvcrt!memcpy_s` at `0x140006292`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF
  int Source; // [rsp+28h] [rbp-40h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-3Ch]
  __int16 v15; // [rsp+2Eh] [rbp-3Ah]
  int v16; // [rsp+30h] [rbp-38h]

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
    {
      memcpy_s(
        *((void *const *)pv + 30),
        (*((_QWORD *)pv + 31) - *((_QWORD *)pv + 30)) & -(__int64)(*((_QWORD *)pv + 30) < *((_QWORD *)pv + 31)),
        &Source,
        0xCu);
      *((_QWORD *)pv + 30) += 12LL;
    }
    if ( !pv[64] )
    {
      v8 = (struct _TP_TIMER **)(pv + 56);
      if ( !*((_QWORD *)pv + 7) )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        pv[64] = 1;
      }
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x1400061e0  push    rbx
0x1400061e2  push    rbp
0x1400061e3  push    rsi
0x1400061e4  push    rdi
0x1400061e5  push    r14
0x1400061e7  sub     rsp, 40h
0x1400061eb  mov     rax, cs:__security_cookie
0x1400061f2  xor     rax, rsp
0x1400061f5  mov     [rsp+68h+var_30], rax
0x1400061fa  mov     r14d, r9d
0x1400061fd  movzx   esi, r8w
0x140006201  mov     ebx, edx
0x140006203  mov     rdi, rcx
0x140006206  cmp     byte ptr [rcx], 0
0x140006209  jz      loc_140006336
0x14000620f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006216  jnz     loc_140006336
0x14000621c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006223  test    rax, rax
0x140006226  jz      short loc_140006235
0x140006228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000622d  test    al, al
0x14000622f  jnz     loc_140006336
0x140006235  lea     rbp, [rdi+28h]
0x140006239  mov     rcx, rbp; SRWLock
0x14000623c  call    cs:__imp_AcquireSRWLockExclusive
0x140006243  nop     dword ptr [rax+rax+00h]
0x140006248  xor     eax, eax
0x14000624a  mov     [rsp+68h+var_3A], ax
0x14000624f  mov     [rsp+68h+Source], ebx
0x140006253  mov     [rsp+68h+var_3C], si
0x140006258  mov     [rsp+68h+var_38], r14d
0x14000625d  lea     rbx, [rdi+0E8h]
0x140006264  lea     esi, [rax+0Ch]
0x140006267  mov     edx, esi; unsigned __int64
0x140006269  mov     rcx, rbx; this
0x14000626c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140006271  test    al, al
0x140006273  jz      short loc_1400062A2
0x140006275  mov     rcx, [rbx+8]; Destination
0x140006279  mov     rax, [rbx+10h]
0x14000627d  sub     rax, rcx
0x140006280  cmp     rcx, [rbx+10h]
0x140006284  sbb     rdx, rdx
0x140006287  and     rdx, rax; DestinationSize
0x14000628a  mov     r9d, esi; SourceSize
0x14000628d  lea     r8, [rsp+68h+Source]; Source
0x140006292  call    cs:__imp_memcpy_s
0x140006299  nop     dword ptr [rax+rax+00h]
0x14000629e  add     [rbx+8], rsi
0x1400062a2  cmp     byte ptr [rdi+40h], 0
0x1400062a6  jnz     short loc_140006321
0x1400062a8  lea     rsi, [rdi+38h]
0x1400062ac  cmp     qword ptr [rsi], 0
0x1400062b0  jnz     short loc_1400062F2
0x1400062b2  call    cs:__imp_GetLastError
0x1400062b9  nop     dword ptr [rax+rax+00h]
0x1400062be  mov     ebx, eax
0x1400062c0  xor     r8d, r8d; pcbe
0x1400062c3  mov     rdx, rdi; pv
0x1400062c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400062cd  call    cs:__imp_CreateThreadpoolTimer
0x1400062d4  nop     dword ptr [rax+rax+00h]
0x1400062d9  mov     rdx, rax
0x1400062dc  mov     rcx, rsi
0x1400062df  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400062e4  mov     ecx, ebx; dwErrCode
0x1400062e6  call    cs:__imp_SetLastError
0x1400062ed  nop     dword ptr [rax+rax+00h]
0x1400062f2  mov     rcx, [rsi]; pti
0x1400062f5  test    rcx, rcx
0x1400062f8  jz      short loc_140006321
0x1400062fa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140006303  mov     r9d, 4E2h; msWindowLength
0x140006309  xor     r8d, r8d; msPeriod
0x14000630c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140006311  call    cs:__imp_SetThreadpoolTimer
0x140006318  nop     dword ptr [rax+rax+00h]
0x14000631d  mov     byte ptr [rdi+40h], 1
0x140006321  test    rbp, rbp
0x140006324  jz      short loc_140006336
0x140006326  mov     rcx, rbp; SRWLock
0x140006329  call    cs:__imp_ReleaseSRWLockExclusive
0x140006330  nop     dword ptr [rax+rax+00h]
0x140006335  nop
0x140006336  mov     rcx, [rsp+68h+var_30]
0x14000633b  xor     rcx, rsp; StackCookie
0x14000633e  call    __security_check_cookie
0x140006343  add     rsp, 40h
0x140006347  pop     r14
0x140006349  pop     rdi
0x14000634a  pop     rsi
0x14000634b  pop     rbp
0x14000634c  pop     rbx
0x14000634d  retn
```
