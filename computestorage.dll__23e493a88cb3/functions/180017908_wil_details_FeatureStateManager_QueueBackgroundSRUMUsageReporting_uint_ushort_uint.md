# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180017908`
- end: `0x180017a70`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `360`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800198c0`

## callees

- `0x180002690`
- `0x180015be8`
- `0x180017908`
- `0x180019e24`
- `0x180019f1c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017a4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017a4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017964`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800179ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800179ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a32`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        DWORD a2,
        unsigned __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  __int64 Source; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h]

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    LODWORD(Source) = a2;
    HIDWORD(Source) = a3;
    v13 = a4;
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
        Source = -50000000;
        SetThreadpoolTimer(v11, (PFILETIME)&Source, 0, 0x4E2u);
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
0x180017908  push    rbx
0x18001790a  push    rbp
0x18001790b  push    rsi
0x18001790c  push    rdi
0x18001790d  push    r14
0x18001790f  sub     rsp, 40h
0x180017913  mov     rax, cs:__security_cookie
0x18001791a  xor     rax, rsp
0x18001791d  mov     [rsp+68h+var_38], rax
0x180017922  mov     r14d, r9d
0x180017925  movzx   esi, r8w
0x180017929  mov     ebx, edx
0x18001792b  mov     rdi, rcx
0x18001792e  cmp     byte ptr [rcx], 0
0x180017931  jz      loc_180017A57
0x180017937  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001793e  jnz     loc_180017A57
0x180017944  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001794b  test    rax, rax
0x18001794e  jz      short loc_18001795D
0x180017950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017955  test    al, al
0x180017957  jnz     loc_180017A57
0x18001795d  lea     rbp, [rdi+28h]
0x180017961  mov     rcx, rbp; SRWLock
0x180017964  call    cs:__imp_AcquireSRWLockExclusive
0x18001796b  nop     dword ptr [rax+rax+00h]
0x180017970  xor     eax, eax
0x180017972  mov     word ptr [rsp+68h+Source+6], ax
0x180017977  mov     dword ptr [rsp+68h+Source], ebx
0x18001797b  mov     word ptr [rsp+68h+Source+4], si
0x180017980  mov     [rsp+68h+var_40], r14d
0x180017985  lea     rbx, [rdi+0E8h]
0x18001798c  lea     esi, [rax+0Ch]
0x18001798f  mov     edx, esi; unsigned __int64
0x180017991  mov     rcx, rbx; this
0x180017994  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180017999  test    al, al
0x18001799b  jz      short loc_1800179C3
0x18001799d  mov     rcx, [rbx+8]; Destination
0x1800179a1  mov     rax, [rbx+10h]
0x1800179a5  sub     rax, rcx
0x1800179a8  cmp     rcx, [rbx+10h]
0x1800179ac  sbb     rdx, rdx
0x1800179af  and     rdx, rax; DestinationSize
0x1800179b2  mov     r9d, esi; SourceSize
0x1800179b5  lea     r8, [rsp+68h+Source]; Source
0x1800179ba  call    memcpy_s
0x1800179bf  add     [rbx+8], rsi
0x1800179c3  cmp     byte ptr [rdi+40h], 0
0x1800179c7  jnz     short loc_180017A42
0x1800179c9  lea     rsi, [rdi+38h]
0x1800179cd  cmp     qword ptr [rsi], 0
0x1800179d1  jnz     short loc_180017A13
0x1800179d3  call    cs:__imp_GetLastError
0x1800179da  nop     dword ptr [rax+rax+00h]
0x1800179df  mov     ebx, eax
0x1800179e1  xor     r8d, r8d; pcbe
0x1800179e4  mov     rdx, rdi; pv
0x1800179e7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800179ee  call    cs:__imp_CreateThreadpoolTimer
0x1800179f5  nop     dword ptr [rax+rax+00h]
0x1800179fa  mov     rdx, rax
0x1800179fd  mov     rcx, rsi
0x180017a00  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017a05  mov     ecx, ebx; dwErrCode
0x180017a07  call    cs:__imp_SetLastError
0x180017a0e  nop     dword ptr [rax+rax+00h]
0x180017a13  mov     rcx, [rsi]; pti
0x180017a16  test    rcx, rcx
0x180017a19  jz      short loc_180017A42
0x180017a1b  mov     [rsp+68h+Source], 0FFFFFFFFFD050F80h
0x180017a24  mov     r9d, 4E2h; msWindowLength
0x180017a2a  xor     r8d, r8d; msPeriod
0x180017a2d  lea     rdx, [rsp+68h+Source]; pftDueTime
0x180017a32  call    cs:__imp_SetThreadpoolTimer
0x180017a39  nop     dword ptr [rax+rax+00h]
0x180017a3e  mov     byte ptr [rdi+40h], 1
0x180017a42  test    rbp, rbp
0x180017a45  jz      short loc_180017A57
0x180017a47  mov     rcx, rbp; SRWLock
0x180017a4a  call    cs:__imp_ReleaseSRWLockExclusive
0x180017a51  nop     dword ptr [rax+rax+00h]
0x180017a56  nop
0x180017a57  mov     rcx, [rsp+68h+var_38]
0x180017a5c  xor     rcx, rsp; StackCookie
0x180017a5f  call    __security_check_cookie
0x180017a64  add     rsp, 40h
0x180017a68  pop     r14
0x180017a6a  pop     rdi
0x180017a6b  pop     rsi
0x180017a6c  pop     rbp
0x180017a6d  pop     rbx
0x180017a6e  retn
```
