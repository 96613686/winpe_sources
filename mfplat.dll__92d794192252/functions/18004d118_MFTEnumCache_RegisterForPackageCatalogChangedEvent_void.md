# MFTEnumCache::RegisterForPackageCatalogChangedEvent(void)

- ea: `0x18004d118`
- end: `0x18004d38d`
- name: `?RegisterForPackageCatalogChangedEvent@MFTEnumCache@@SAJXZ`
- size: `629`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d100`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004d118`
- `0x18004e77c`
- `0x1801211c0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d226`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d267`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004d1ab`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004d1ab`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18004d13d`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18004d13d`

## string_xrefs

- `0x18004d1e8`: `MFTEnumCache::RegisterForPackageCatalogChangedEvent`
- `0x18004d361`: `MFTEnumCache::RegisterForPackageCatalogChangedEvent`

## pseudocode

```c
__int64 MFTEnumCache::RegisterForPackageCatalogChangedEvent(void)
{
  unsigned int v0; // esi
  __int64 v1; // rcx
  __int64 v2; // rcx
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  MFTEnumCache *v10; // rdx
  __int64 *v11; // rdi
  __int64 v12; // r14
  CallStackTracing *v13; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackScopeTrace v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+78h] [rbp+48h] BYREF

  v0 = 0;
  v17 = 0;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  if ( (int)GetMediaExtensionCommunicationFactory(&v17) >= 0 )
  {
    v4 = v17;
    v5 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    CurrentProcess = GetCurrentProcess();
    ProcessId = GetProcessId(CurrentProcess);
    if ( v5(v4, ProcessId, &v16) >= 0 )
    {
      v8 = operator new(0x48u, &std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>(v8);
        *v9 = off_1801B5FF0;
        v9[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      }
      CallStackScopeTrace::CallStackScopeTrace(&v15, "MFTEnumCache::RegisterForPackageCatalogChangedEvent", 3499);
      if ( v9 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, v9, &v18);
        EnterCriticalSection(&g_MFTCacheLock);
        v10 = g_pMFTEnumCache;
        if ( !g_pMFTEnumCache || (v11 = (__int64 *)((char *)g_pMFTEnumCache + 80), *((_QWORD *)g_pMFTEnumCache + 10)) )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 56LL))(v16, v18);
        }
        else
        {
          v12 = v16;
          v16 = 0;
          if ( *v11 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)*v11 + 16LL))(*v11);
            v10 = g_pMFTEnumCache;
          }
          *v11 = v12;
          *((_QWORD *)v10 + 9) = v18;
        }
        LeaveCriticalSection(&g_MFTCacheLock);
        CallStackScopeTrace::~CallStackScopeTrace(&v15);
        (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      }
      else
      {
        v13 = CallStackTracing::s_wpInstance;
        v0 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v13->m_fEnabled )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v13);
          if ( ThreadRelativeContext->m_result != -2147024882 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "MFTEnumCache::RegisterForPackageCatalogChangedEvent",
              3499,
              -2147024882);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
            0,
            -2147024882);
        CallStackScopeTrace::~CallStackScopeTrace(&v15);
      }
    }
  }
  v1 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
  v2 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18004d118  push    rbp
0x18004d11a  push    rbx
0x18004d11b  push    rsi
0x18004d11c  push    rdi
0x18004d11d  push    r14
0x18004d11f  mov     rbp, rsp
0x18004d122  sub     rsp, 30h
0x18004d126  xor     esi, esi
0x18004d128  lea     rcx, [rbp+arg_10]
0x18004d12c  mov     [rbp+arg_10], rsi
0x18004d130  mov     [rbp+arg_8], rsi
0x18004d134  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d139  lea     rcx, [rbp+arg_10]
0x18004d13d  call    cs:__imp_GetMediaExtensionCommunicationFactory
0x18004d143  test    eax, eax
0x18004d145  jns     short loc_18004D18E
0x18004d147  mov     rcx, [rbp+arg_8]
0x18004d14b  test    rcx, rcx
0x18004d14e  jz      short loc_18004D164
0x18004d150  mov     [rbp+arg_8], 0
0x18004d158  mov     rax, [rcx]
0x18004d15b  mov     rax, [rax+10h]
0x18004d15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d164  mov     rcx, [rbp+arg_10]
0x18004d168  test    rcx, rcx
0x18004d16b  jz      short loc_18004D181
0x18004d16d  mov     [rbp+arg_10], 0
0x18004d175  mov     rdx, [rcx]
0x18004d178  mov     rax, [rdx+10h]
0x18004d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d181  mov     eax, esi
0x18004d183  add     rsp, 30h
0x18004d187  pop     r14
0x18004d189  pop     rdi
0x18004d18a  pop     rsi
0x18004d18b  pop     rbx
0x18004d18c  pop     rbp
0x18004d18d  retn
0x18004d18e  mov     rdi, [rbp+arg_10]
0x18004d192  lea     rcx, [rbp+arg_8]
0x18004d196  mov     rax, [rdi]
0x18004d199  mov     rbx, [rax+58h]
0x18004d19d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004d1a2  call    cs:__imp_GetCurrentProcess
0x18004d1a8  mov     rcx, rax; Process
0x18004d1ab  call    cs:__imp_GetProcessId
0x18004d1b1  lea     r8, [rbp+arg_8]
0x18004d1b5  mov     rcx, rdi
0x18004d1b8  mov     edx, eax
0x18004d1ba  mov     rax, rbx
0x18004d1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1c2  test    eax, eax
0x18004d1c4  js      short loc_18004D147
0x18004d1c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004d1cd  mov     ecx, 48h ; 'H'; unsigned __int64
0x18004d1d2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004d1d7  mov     rbx, rax
0x18004d1da  test    rax, rax
0x18004d1dd  jnz     loc_18004D28A
0x18004d1e3  mov     edi, 0DABh
0x18004d1e8  lea     rdx, aMftenumcacheRe; "MFTEnumCache::RegisterForPackageCatalog"...
0x18004d1ef  mov     r8d, edi; int
0x18004d1f2  lea     rcx, [rbp+arg_0]; this
0x18004d1f6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d1fb  test    rbx, rbx
0x18004d1fe  jz      loc_18004D2C2
0x18004d204  mov     rcx, [rbp+arg_8]
0x18004d208  lea     r8, [rbp+arg_18]
0x18004d20c  mov     [rbp+arg_18], rsi
0x18004d210  mov     rdx, rbx
0x18004d213  mov     rax, [rcx]
0x18004d216  mov     rax, [rax+30h]
0x18004d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d21f  lea     rcx, ?g_MFTCacheLock@@3VCMFCSLock@@A; lpCriticalSection
0x18004d226  call    cs:__imp_EnterCriticalSection
0x18004d22c  mov     rdx, cs:?g_pMFTEnumCache@@3PEAUMFTEnumCache@@EA; MFTEnumCache * g_pMFTEnumCache
0x18004d233  test    rdx, rdx
0x18004d236  jz      short loc_18004D2AC
0x18004d238  lea     rdi, [rdx+50h]
0x18004d23c  cmp     [rdi], rsi
0x18004d23f  jnz     short loc_18004D2AC
0x18004d241  mov     r14, [rbp+arg_8]
0x18004d245  mov     [rbp+arg_8], rsi
0x18004d249  mov     rcx, [rdi]
0x18004d24c  test    rcx, rcx
0x18004d24f  jnz     loc_18004D375
0x18004d255  mov     [rdi], r14
0x18004d258  mov     rax, [rbp+arg_18]
0x18004d25c  mov     [rdx+48h], rax
0x18004d260  lea     rcx, ?g_MFTCacheLock@@3VCMFCSLock@@A; lpCriticalSection
0x18004d267  call    cs:__imp_LeaveCriticalSection
0x18004d26d  lea     rcx, [rbp+arg_0]; this
0x18004d271  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d276  mov     rax, [rbx]
0x18004d279  mov     rcx, rbx
0x18004d27c  mov     rax, [rax+10h]
0x18004d280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d285  jmp     loc_18004D147
0x18004d28a  mov     rcx, rbx
0x18004d28d  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVMediaExtensionBroker@MediaExtensionAppServices@Media@Windows@@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>(void)
0x18004d292  lea     rax, off_1801B5FF0
0x18004d299  mov     [rbx], rax
0x18004d29c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVMediaExtensionBroker@MediaExtensionAppServices@Media@Windows@@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::Media::MediaExtensionAppServices::MediaExtensionBroker *,IInspectable *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004d2a3  mov     [rbx+8], rax
0x18004d2a7  jmp     loc_18004D1E3
0x18004d2ac  mov     rcx, [rbp+arg_8]
0x18004d2b0  mov     rdx, [rbp+arg_18]
0x18004d2b4  mov     rax, [rcx]
0x18004d2b7  mov     rax, [rax+38h]
0x18004d2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2c0  jmp     short loc_18004D260
0x18004d2c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2c9  mov     esi, 8007000Eh
0x18004d2ce  test    rcx, rcx
0x18004d2d1  jnz     short loc_18004D308
0x18004d2d3  mov     rax, cs:stru_1801FC290.__vftable
0x18004d2da  lea     rcx, stru_1801FC290
0x18004d2e1  mov     edx, 7F0h
0x18004d2e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2ed  mov     rax, [rax+8]
0x18004d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2f6  test    eax, eax
0x18004d2f8  jnz     short loc_18004D348
0x18004d2fa  lea     rcx, stru_1801F8A30; this
0x18004d301  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d308  cmp     byte ptr [rcx+8], 0
0x18004d30c  jnz     short loc_18004D351
0x18004d30e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d315  jb      short loc_18004D33A
0x18004d317  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d31e  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x18004d325  mov     edx, 57h ; 'W'
0x18004d32a  mov     [rsp+30h+var_10], esi
0x18004d32e  xor     r9d, r9d
0x18004d331  mov     rcx, [rcx+10h]
0x18004d335  call    WPP_SF_qD
0x18004d33a  lea     rcx, [rbp+arg_0]; this
0x18004d33e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d343  jmp     loc_18004D147
0x18004d348  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d34f  jmp     short loc_18004D308
0x18004d351  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d356  cmp     [rax+7CCh], esi
0x18004d35c  jz      short loc_18004D30E
0x18004d35e  mov     r9d, esi; int
0x18004d361  lea     rdx, aMftenumcacheRe; "MFTEnumCache::RegisterForPackageCatalog"...
0x18004d368  mov     r8d, edi; int
0x18004d36b  mov     rcx, rax; this
0x18004d36e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d373  jmp     short loc_18004D30E
0x18004d375  mov     rax, [rcx]
0x18004d378  mov     rax, [rax+10h]
0x18004d37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d381  mov     rdx, cs:?g_pMFTEnumCache@@3PEAUMFTEnumCache@@EA; MFTEnumCache * g_pMFTEnumCache
0x18004d388  jmp     loc_18004D255
```
