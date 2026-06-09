# ServiceMain

- ea: `0x180007920`
- end: `0x180007b85`
- name: `ServiceMain`
- size: `613`
- prototype: `void __fastcall(__int64, _WORD **, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001770`
- `0x180001794`
- `0x1800021f0`
- `0x180003d0c`
- `0x180003e30`
- `0x180004274`
- `0x180007260`
- `0x180007394`
- `0x1800077a0`
- `0x180007878`
- `0x180007920`
- `0x1800084bc`
- `0x180009300`
- `0x18000a068`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800079e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800079e7`

## string_xrefs

- `0x180007b25`: `Service name should always be passed by SCM.`
- `0x180007a53`: `AttestationPlugin`
- `0x180007a72`: `servercommon\base\securehostingservice\common\service\dll\hgclientservice.cpp`
- `0x180007a0a`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`
- `0x1800079fa`: `Failed to begin initialization of the configuration.`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, _WORD **a2, __int64 a3)
{
  int v4; // edi
  char v5; // al
  _WORD *v6; // rbx
  BOOL inited; // eax
  int v8; // eax
  void *v9; // rdi
  __int64 v10; // r8
  const char *v11; // r9
  const struct wil::FailureInfo *v12; // rdx
  wil *v13; // rcx
  unsigned int v14; // eax
  unsigned __int8 v15; // dl
  __int64 v16; // r8
  unsigned int v17; // edi
  __int64 v18; // rcx
  Microsoft::HostGuardian::Client::HgService *v19; // rbx
  int v20; // [rsp+20h] [rbp-178h]
  const char *v21; // [rsp+28h] [rbp-170h]
  LPVOID Context; // [rsp+30h] [rbp-168h] BYREF
  Microsoft::HostGuardian::Client::HgService *v23; // [rsp+38h] [rbp-160h]
  WCHAR ServiceName[8]; // [rsp+40h] [rbp-158h] BYREF
  __int64 v25; // [rsp+50h] [rbp-148h]
  __int64 v26; // [rsp+58h] [rbp-140h]
  _BYTE *v27; // [rsp+60h] [rbp-138h]
  _BYTE v28[40]; // [rsp+68h] [rbp-130h] BYREF
  _BYTE v29[160]; // [rsp+90h] [rbp-108h] BYREF
  __int128 v30; // [rsp+130h] [rbp-68h] BYREF
  __int64 v31; // [rsp+140h] [rbp-58h]
  __int64 v32; // [rsp+148h] [rbp-50h]
  _QWORD v33[4]; // [rsp+150h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v4 = a1;
  v5 = Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a1, ServiceLaunch, a3, 1, v33);
    v5 = Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  }
  if ( wil::details::g_pfnLoggingCallback
    && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != lambda_94f5badb7431ffd0bfcb652c1cc96464_::_lambda_invoker_cdecl_ )
  {
    memset_0(v29, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v29, v12);
  }
  wil::details::g_pfnLoggingCallback = (__int64)lambda_94f5badb7431ffd0bfcb652c1cc96464_::_lambda_invoker_cdecl_;
  if ( v4 && a2 && (v6 = *a2) != 0 && *v6 )
  {
    v23 = 0;
    Context = 0;
    inited = InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)InitializeConfigurationOnce, 0, &Context);
    try
    {
      wil::details::in1diag3::Throw_GetLastErrorIfMsg(
        retaddr,
        (void *)0x36,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
        (const char *)!inited,
        (bool)"Failed to begin initialization of the configuration.",
        v21);
      v30 = 0;
      v31 = 0;
      v32 = 7;
      LOWORD(v30) = 0;
      v8 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int128 *))(*(_QWORD *)Context + 8LL))(
             Context,
             L"AttestationPlugin",
             &v30);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\dll\\hgclientservice.cpp",
          (const char *)(unsigned int)v8,
          v20);
      v9 = operator new(0xC8u);
      Context = v9;
      v27 = v28;
      std::wstring::wstring(v28, &v30);
      *(_OWORD *)ServiceName = 0;
      v25 = 0;
      v26 = 0;
      v10 = -1;
      do
        ++v10;
      while ( v6[v10] );
      std::wstring::_Construct<1,wchar_t const *>(ServiceName, v6, v10);
      v23 = (Microsoft::HostGuardian::Client::HgService *)Microsoft::HostGuardian::Client::HgService::HgService(
                                                            v9,
                                                            ServiceName);
      Microsoft::HostGuardian::Client::HgService::Start(v23);
      std::wstring::~wstring(&v30);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x53,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\dll\\hgclientservice.cpp",
        v11);
      v14 = wil::ResultFromCaughtException(v13);
      v17 = v14;
      v18 = (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 8) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits,
          ServiceDebugError,
          L"ServiceMain failed",
          v14);
        v18 = (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
      }
      v19 = v23;
      if ( v23 )
      {
        if ( (v18 & 2) != 0 )
        {
          v33[2] = L"Stopping the service.";
          v33[3] = 44;
          McGenEventWrite_EventWriteTransfer(v18, ServiceDebugInformational, v16, 2, v33);
        }
        Microsoft::HostGuardian::Client::HgService::Stop(v19, v15, v17);
        Microsoft::HostGuardian::Client::HgService::~HgService(v19);
        operator delete(v19);
      }
    }
  }
  else if ( (v5 & 8) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(
      lambda_94f5badb7431ffd0bfcb652c1cc96464_::_lambda_invoker_cdecl_,
      ServiceDebugError,
      L"Service name should always be passed by SCM.",
      87);
  }
}

```

## disassembly

```asm
0x180007920  mov     r11, rsp
0x180007923  mov     [r11+8], rbx
0x180007927  mov     [r11+18h], rsi
0x18000792b  push    rdi
0x18000792c  push    r14
0x18000792e  push    r15
0x180007930  sub     rsp, 180h
0x180007937  mov     rax, cs:__security_cookie
0x18000793e  xor     rax, rsp
0x180007941  mov     [rsp+198h+var_28], rax
0x180007949  mov     rbx, rdx
0x18000794c  mov     edi, ecx
0x18000794e  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x180007954  test    al, 1
0x180007956  jz      short loc_180007979
0x180007958  lea     rax, [r11-48h]
0x18000795c  mov     qword ptr [rsp+198h+var_178], rax
0x180007961  mov     r9d, 1
0x180007967  lea     rdx, ServiceLaunch
0x18000796e  call    McGenEventWrite_EventWriteTransfer
0x180007973  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x180007979  mov     rdx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007980  xor     r15d, r15d
0x180007983  lea     rcx, _lambda_94f5badb7431ffd0bfcb652c1cc96464____lambda_invoker_cdecl_
0x18000798a  test    rdx, rdx
0x18000798d  jz      short loc_180007998
0x18000798f  cmp     rdx, rcx
0x180007992  jnz     loc_180007B62
0x180007998  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18000799f  cmp     edi, 1
0x1800079a2  jb      loc_180007B1B
0x1800079a8  test    rbx, rbx
0x1800079ab  jz      loc_180007B1B
0x1800079b1  mov     rbx, [rbx]
0x1800079b4  test    rbx, rbx
0x1800079b7  jz      loc_180007B1B
0x1800079bd  cmp     r15w, [rbx]
0x1800079c1  jz      loc_180007B1B
0x1800079c7  mov     [rsp+198h+var_160], r15
0x1800079cc  mov     [rsp+198h+Context], r15
0x1800079d1  lea     r9, [rsp+198h+Context]; Context
0x1800079d6  xor     r8d, r8d; Parameter
0x1800079d9  lea     rdx, ?InitializeConfigurationOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800079e0  lea     rcx, InitOnce; InitOnce
0x1800079e7  call    cs:__imp_InitOnceExecuteOnce
0x1800079ed  test    eax, eax
0x1800079ef  setz    al
0x1800079f2  mov     rcx, [rsp+198h]; this
0x1800079fa  lea     rdx, aFailedToBeginI; "Failed to begin initialization of the c"...
0x180007a01  mov     qword ptr [rsp+198h+var_178], rdx; int
0x180007a06  movzx   r9d, al; char *
0x180007a0a  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x180007a11  mov     edx, 36h ; '6'; void *
0x180007a16  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180007a1b  mov     rcx, [rsp+198h+Context]
0x180007a20  xorps   xmm0, xmm0
0x180007a23  movups  [rsp+198h+var_68], xmm0
0x180007a2b  mov     [rsp+198h+var_58], r15
0x180007a33  mov     [rsp+198h+var_50], 7
0x180007a3f  mov     word ptr [rsp+198h+var_68], r15w
0x180007a48  mov     rax, [rcx]
0x180007a4b  lea     r8, [rsp+198h+var_68]
0x180007a53  lea     rdx, aAttestationplu; "AttestationPlugin"
0x180007a5a  mov     rax, [rax+8]
0x180007a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a63  mov     rcx, [rsp+198h]; this
0x180007a6b  test    eax, eax
0x180007a6d  jns     short loc_180007A83
0x180007a6f  mov     r9d, eax; char *
0x180007a72  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180007a79  mov     edx, 4Ah ; 'J'; void *
0x180007a7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a83  mov     ecx, 0C8h; Size
0x180007a88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a8d  mov     rdi, rax
0x180007a90  mov     [rsp+198h+Context], rax
0x180007a95  lea     rax, [rsp+198h+var_130]
0x180007a9a  mov     [rsp+198h+var_138], rax
0x180007a9f  lea     rdx, [rsp+198h+var_68]
0x180007aa7  lea     rcx, [rsp+198h+var_130]
0x180007aac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007ab1  mov     rsi, rax
0x180007ab4  mov     r14, cs:?g_serviceHostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_serviceHostSharedGlobals
0x180007abb  xorps   xmm0, xmm0
0x180007abe  movups  xmmword ptr [rsp+198h+ServiceName], xmm0
0x180007ac3  mov     [rsp+198h+var_148], r15
0x180007ac8  mov     [rsp+198h+var_140], r15
0x180007acd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007ad1  inc     r8
0x180007ad4  cmp     [rbx+r8*2], r15w
0x180007ad9  jnz     short loc_180007AD1
0x180007adb  mov     rdx, rbx
0x180007ade  lea     rcx, [rsp+198h+ServiceName]
0x180007ae3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007ae8  nop
0x180007ae9  mov     r9, rsi
0x180007aec  mov     r8, r14
0x180007aef  lea     rdx, [rsp+198h+ServiceName]; lpServiceName
0x180007af4  mov     rcx, rdi; lpContext
0x180007af7  call    ??0HgService@Client@HostGuardian@Microsoft@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_SVCHOST_GLOBAL_DATA@@0@Z; Microsoft::HostGuardian::Client::HgService::HgService(std::wstring,_SVCHOST_GLOBAL_DATA *,std::wstring)
0x180007afc  nop
0x180007afd  mov     [rsp+198h+var_160], rax
0x180007b02  mov     rcx, rax; this
0x180007b05  call    ?Start@HgService@Client@HostGuardian@Microsoft@@QEAAXXZ; Microsoft::HostGuardian::Client::HgService::Start(void)
0x180007b0a  nop
0x180007b0b  lea     rcx, [rsp+198h+var_68]
0x180007b13  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007b18  nop
0x180007b19  jmp     short loc_180007B39
0x180007b1b  test    al, 8
0x180007b1d  jz      short loc_180007B39
0x180007b1f  mov     r9d, 57h ; 'W'
0x180007b25  lea     r8, aServiceNameSho; "Service name should always be passed by"...
0x180007b2c  lea     rdx, ServiceDebugError
0x180007b33  call    McTemplateU0zq_EventWriteTransfer
0x180007b38  nop
0x180007b39  mov     rcx, [rsp+198h+var_28]
0x180007b41  xor     rcx, rsp; StackCookie
0x180007b44  call    __security_check_cookie
0x180007b49  lea     r11, [rsp+198h+var_18]
0x180007b51  mov     rbx, [r11+20h]
0x180007b55  mov     rsi, [r11+30h]
0x180007b59  mov     rsp, r11
0x180007b5c  pop     r15
0x180007b5e  pop     r14
0x180007b60  pop     rdi
0x180007b61  retn
0x180007b62  xor     edx, edx; Val
0x180007b64  mov     r8d, 98h; Size
0x180007b6a  lea     rcx, [rsp+198h+var_108]; void *
0x180007b72  call    memset_0
0x180007b77  lea     rcx, [rsp+198h+var_108]; this
0x180007b7f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
