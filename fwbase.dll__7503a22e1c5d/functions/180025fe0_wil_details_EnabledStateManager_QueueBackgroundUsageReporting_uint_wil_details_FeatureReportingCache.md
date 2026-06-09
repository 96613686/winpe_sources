# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180025fe0`
- end: `0x18002617e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `414`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180027860`

## callees

- `0x18001e1d0`
- `0x18001eae6`
- `0x18001eb54`
- `0x180025fe0`
- `0x180029710`
- `0x180029820`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800260a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800260d0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800260a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800260d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002603f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002603f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026159`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002611b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002611b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026107`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026107`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026147`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026147`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // r9
  size_t v9; // r8
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( !*(_DWORD *)pv
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (char *)-8LL )
        ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 32), 0x10u) )
    {
LABEL_19:
      if ( !pv[24] )
      {
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v12 = (struct _TP_TIMER *)*((_QWORD *)pv + 2);
        if ( v12 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v12, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
      goto LABEL_24;
    }
    v8 = *((_QWORD *)pv + 5);
    v9 = 0;
    if ( v8 < *((_QWORD *)pv + 6) )
      v9 = *((_QWORD *)pv + 6) - v8;
    if ( v8 )
    {
      if ( v9 >= 0x10 )
      {
        *(_DWORD *)v8 = a2;
        *(_DWORD *)(v8 + 4) = 0;
        *(_QWORD *)(v8 + 8) = a3;
LABEL_18:
        *((_QWORD *)pv + 5) += 16LL;
        goto LABEL_19;
      }
      memset_0(*((void **)pv + 5), 0, v9);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v9) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x180025fe0  mov     [rsp+arg_18], rbx
0x180025fe5  push    rbp
0x180025fe6  push    rsi
0x180025fe7  push    rdi
0x180025fe8  push    r14
0x180025fea  push    r15
0x180025fec  sub     rsp, 30h
0x180025ff0  mov     rax, cs:__security_cookie
0x180025ff7  xor     rax, rsp
0x180025ffa  mov     [rsp+58h+var_30], rax
0x180025fff  mov     rbp, r8
0x180026002  mov     r14d, edx
0x180026005  mov     rdi, rcx
0x180026008  mov     eax, [rcx]
0x18002600a  test    eax, eax
0x18002600c  jz      loc_180026160
0x180026012  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180026019  jnz     loc_180026160
0x18002601f  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180026026  test    rax, rax
0x180026029  jz      short loc_180026038
0x18002602b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026030  test    al, al
0x180026032  jnz     loc_180026160
0x180026038  lea     rsi, [rdi+8]
0x18002603c  mov     rcx, rsi; SRWLock
0x18002603f  call    cs:__imp_AcquireSRWLockExclusive
0x180026045  mov     eax, [rdi]
0x180026047  test    eax, eax
0x180026049  jz      loc_180026151
0x18002604f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180026056  jnz     loc_180026151
0x18002605c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180026063  test    rax, rax
0x180026066  jz      short loc_180026075
0x180026068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002606d  test    al, al
0x18002606f  jnz     loc_180026151
0x180026075  xor     r15d, r15d
0x180026078  mov     edx, 10h; unsigned __int64
0x18002607d  lea     rcx, [rdi+20h]; this
0x180026081  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180026086  test    al, al
0x180026088  jz      short loc_1800260E6
0x18002608a  mov     r9, [rdi+28h]
0x18002608e  mov     rax, [rdi+30h]
0x180026092  sub     rax, r9
0x180026095  xor     r8d, r8d
0x180026098  cmp     r9, [rdi+30h]
0x18002609c  cmovb   r8, rax; Size
0x1800260a0  test    r9, r9
0x1800260a3  jnz     short loc_1800260B3
0x1800260a5  call    cs:__imp__o__errno
0x1800260ab  mov     dword ptr [rax], 16h
0x1800260b1  jmp     short loc_1800260DC
0x1800260b3  cmp     r8, 10h
0x1800260b7  jb      short loc_1800260C6
0x1800260b9  mov     [r9], r14d
0x1800260bc  mov     [r9+4], r15d
0x1800260c0  mov     [r9+8], rbp
0x1800260c4  jmp     short loc_1800260E1
0x1800260c6  xor     edx, edx; Val
0x1800260c8  mov     rcx, r9; void *
0x1800260cb  call    memset_0
0x1800260d0  call    cs:__imp__o__errno
0x1800260d6  mov     dword ptr [rax], 22h ; '"'
0x1800260dc  call    _invalid_parameter_noinfo
0x1800260e1  add     qword ptr [rdi+28h], 10h
0x1800260e6  cmp     [rdi+18h], r15b
0x1800260ea  jnz     short loc_180026151
0x1800260ec  cmp     [rdi+10h], r15
0x1800260f0  jnz     short loc_180026121
0x1800260f2  call    cs:__imp_GetLastError
0x1800260f8  mov     ebx, eax
0x1800260fa  xor     r8d, r8d; pcbe
0x1800260fd  mov     rdx, rdi; pv
0x180026100  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180026107  call    cs:__imp_CreateThreadpoolTimer
0x18002610d  mov     rdx, rax
0x180026110  lea     rcx, [rdi+10h]
0x180026114  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026119  mov     ecx, ebx; dwErrCode
0x18002611b  call    cs:__imp_SetLastError
0x180026121  mov     rcx, [rdi+10h]; pti
0x180026125  test    rcx, rcx
0x180026128  jz      short loc_180026151
0x18002612a  mov     rax, 0FFFFFFFF4D2FA200h
0x180026134  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180026139  mov     r9d, 124F8h; msWindowLength
0x18002613f  xor     r8d, r8d; msPeriod
0x180026142  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180026147  call    cs:__imp_SetThreadpoolTimer
0x18002614d  mov     byte ptr [rdi+18h], 1
0x180026151  test    rsi, rsi
0x180026154  jz      short loc_180026160
0x180026156  mov     rcx, rsi; SRWLock
0x180026159  call    cs:__imp_ReleaseSRWLockExclusive
0x18002615f  nop
0x180026160  mov     rcx, [rsp+58h+var_30]
0x180026165  xor     rcx, rsp; StackCookie
0x180026168  call    __security_check_cookie
0x18002616d  mov     rbx, [rsp+58h+arg_18]
0x180026172  add     rsp, 30h
0x180026176  pop     r15
0x180026178  pop     r14
0x18002617a  pop     rdi
0x18002617b  pop     rsi
0x18002617c  pop     rbp
0x18002617d  retn
```
