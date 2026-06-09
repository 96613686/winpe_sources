# CoreWebViewHostProcess::CoreWebViewHostProcess(ushort * const,CoreWebViewHostProcessCapabilityState,ushort * const,ushort * const)

- ea: `0x18001646c`
- end: `0x18001672c`
- name: `??0CoreWebViewHostProcess@@QEAA@QEAGW4CoreWebViewHostProcessCapabilityState@@00@Z`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800194bc`

## callees

- `0x180002a90`
- `0x18000f46c`
- `0x18001646c`
- `0x180016734`
- `0x180018198`
- `0x1800181c8`
- `0x180018358`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001657a`
- `OLEAUT32!__imp_SysFreeString` at `0x180016592`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663e`
- `OLEAUT32!__imp_SysFreeString` at `0x180016653`
- `OLEAUT32!__imp_SysFreeString` at `0x18001657a`
- `OLEAUT32!__imp_SysFreeString` at `0x180016592`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001663e`
- `OLEAUT32!__imp_SysFreeString` at `0x180016653`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180016687`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180016687`
- `edgeIso!__imp_?GetRACLaunchFlags@@YAKKK@Z` at `0x1800166e9`
- `edgeIso!__imp_?GetRACLaunchFlags@@YAKKK@Z` at `0x1800166e9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800166a3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800166a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CoreWebViewHostProcess::CoreWebViewHostProcess(__int64 a1, __int64 a2, int a3, __int64 a4, BSTR a5)
{
  BSTR *bstr_failfast; // rax
  char v10; // si
  BSTR v11; // rcx
  BSTR *p_bstrString; // rax
  char v13; // di
  BSTR v14; // rcx
  char v15; // di
  BSTR *v16; // rax
  char v17; // si
  BSTR v18; // rcx
  char v19; // si
  HRESULT Guid; // eax
  bool HasCapability; // al
  unsigned int RACLaunchFlags; // eax
  int v24; // [rsp+20h] [rbp-30h]
  _QWORD v25[2]; // [rsp+30h] [rbp-20h] BYREF
  char v26; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF
  int v29; // [rsp+A0h] [rbp+50h]
  BSTR v30; // [rsp+A8h] [rbp+58h] BYREF

  v29 = 0;
  *(_QWORD *)(a1 + 24) = &Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<WebRuntime::DevTools::IDebugTargetInfo *> *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(a1 + 32));
  *(_QWORD *)(a1 + 72) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `ICoreWebViewHostProcess'};
  *(_QWORD *)(a1 + 16) = &CoreWebViewHostProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>'};
  *(_QWORD *)(a1 + 24) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `ICoreWebViewHostProcessInternal'};
  *(_QWORD *)(a1 + 32) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &CoreWebViewHostProcess::`vftable';
  *(_QWORD *)(a1 + 8) = &CoreWebViewHostProcess::`vftable'{for `ICoreWebViewHostProcess'};
  *(_QWORD *)(a1 + 16) = &CoreWebViewHostProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>'};
  *(_QWORD *)(a1 + 24) = &CoreWebViewHostProcess::`vftable'{for `ICoreWebViewHostProcessInternal'};
  *(_QWORD *)(a1 + 32) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *(_DWORD *)(a1 + 80) = 0;
  if ( a2 )
  {
    bstr_failfast = (BSTR *)wil::make_bstr_failfast(&v30, a2);
    v10 = 1;
    v11 = *bstr_failfast;
  }
  else
  {
    bstr_failfast = &bstrString;
    v10 = 2;
    v11 = 0;
  }
  *(_QWORD *)(a1 + 104) = v11;
  *bstr_failfast = 0;
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    if ( bstrString )
      SysFreeString(bstrString);
  }
  if ( (v10 & 1) != 0 )
  {
    v10 &= ~1u;
    if ( v30 )
      SysFreeString(v30);
  }
  if ( a4 )
  {
    p_bstrString = (BSTR *)wil::make_bstr_failfast(&v30, a4);
    v13 = 4;
    v14 = *p_bstrString;
  }
  else
  {
    p_bstrString = &bstrString;
    v13 = 8;
    v14 = 0;
  }
  v15 = v10 | v13;
  *(_QWORD *)(a1 + 120) = v14;
  *p_bstrString = 0;
  if ( (v15 & 8) != 0 )
  {
    v15 &= ~8u;
    if ( bstrString )
      SysFreeString(bstrString);
  }
  if ( (v15 & 4) != 0 )
  {
    v15 &= ~4u;
    if ( v30 )
      SysFreeString(v30);
  }
  if ( a5 )
  {
    v16 = (BSTR *)wil::make_bstr_failfast(&bstrString, a5);
    v17 = 16;
    v18 = *v16;
  }
  else
  {
    v16 = &a5;
    v17 = 32;
    v18 = 0;
  }
  v19 = v15 | v17;
  *(_QWORD *)(a1 + 128) = v18;
  *v16 = 0;
  if ( (v19 & 0x20) != 0 )
  {
    v19 &= ~0x20u;
    if ( a5 )
      SysFreeString(a5);
  }
  if ( (v19 & 0x10) != 0 && bstrString )
    SysFreeString(bstrString);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 168), 0, 0);
  *(_QWORD *)(a1 + 208) = 0;
  *(_BYTE *)(a1 + 112) = a3 == 2;
  Guid = CoCreateGuid((GUID *)(a1 + 84));
  if ( Guid < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewhostprocess.cpp",
      (const char *)(unsigned int)Guid,
      v24);
  CoreWebViewHostProcess::CreateRACProfile((CoreWebViewHostProcess *)a1);
  HasCapability = AppTokenHasCapability(
                    L"S-1-15-3-1024-3623855041-1826999956-3747069818-3525260223-3747374510-1746272624-950601168-56556331");
  RACLaunchFlags = GetRACLaunchFlags(9u, 8 * HasCapability + 311);
  v25[0] = a1 + 144;
  v25[1] = 0;
  v26 = 1;
  BuildProcessSecurityAttributeBlob(RACLaunchFlags);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v25);
  return a1;
}

```

## disassembly

```asm
0x18001646c  mov     [rsp-38h+arg_0], rcx
0x180016471  push    rbp
0x180016472  push    rbx
0x180016473  push    rsi
0x180016474  push    rdi
0x180016475  push    r12
0x180016477  push    r14
0x180016479  push    r15
0x18001647b  mov     rbp, rsp
0x18001647e  sub     rsp, 50h
0x180016482  mov     r14, r9
0x180016485  mov     r15d, r8d
0x180016488  mov     rdi, rdx
0x18001648b  mov     rbx, rcx
0x18001648e  xor     r12d, r12d
0x180016491  mov     [rbp+arg_10], r12d
0x180016495  lea     rax, ??_7?$IAsyncOperation@PEAU?$IVectorView@PEAUIDebugTargetInfo@DevTools@WebRuntime@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<WebRuntime::DevTools::IDebugTargetInfo *> *>::`vftable'
0x18001649c  mov     [rcx+18h], rax
0x1800164a0  add     rcx, 20h ; ' '; this
0x1800164a4  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800164a9  mov     qword ptr [rbx+48h], 1
0x1800164b1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'
0x1800164b8  mov     [rbx], rax
0x1800164bb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@WRL@Microsoft@@6BICoreWebViewHostProcess@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `ICoreWebViewHostProcess'}
0x1800164c2  mov     [rbx+8], rax
0x1800164c6  lea     rax, ??_7CoreWebViewHostProcess@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CoreWebViewHostProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>'}
0x1800164cd  mov     [rbx+10h], rax
0x1800164d1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@WRL@Microsoft@@6BICoreWebViewHostProcessInternal@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `ICoreWebViewHostProcessInternal'}
0x1800164d8  mov     [rbx+18h], rax
0x1800164dc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800164e3  mov     [rbx+20h], rax
0x1800164e7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800164ee  test    rcx, rcx
0x1800164f1  jz      short loc_180016500
0x1800164f3  mov     rax, [rcx]
0x1800164f6  mov     rax, [rax+8]
0x1800164fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ff  nop
0x180016500  lea     rax, ??_7CoreWebViewHostProcess@@6B@; const CoreWebViewHostProcess::`vftable'
0x180016507  mov     [rbx], rax
0x18001650a  lea     rax, ??_7CoreWebViewHostProcess@@6BICoreWebViewHostProcess@@@; const CoreWebViewHostProcess::`vftable'{for `ICoreWebViewHostProcess'}
0x180016511  mov     [rbx+8], rax
0x180016515  lea     rax, ??_7CoreWebViewHostProcess@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CoreWebViewHostProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>'}
0x18001651c  mov     [rbx+10h], rax
0x180016520  lea     rax, ??_7CoreWebViewHostProcess@@6BICoreWebViewHostProcessInternal@@@; const CoreWebViewHostProcess::`vftable'{for `ICoreWebViewHostProcessInternal'}
0x180016527  mov     [rbx+18h], rax
0x18001652b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180016532  mov     [rbx+20h], rax
0x180016536  mov     [rbx+50h], r12d
0x18001653a  test    rdi, rdi
0x18001653d  jz      short loc_180016555
0x18001653f  mov     rdx, rdi
0x180016542  lea     rcx, [rbp+arg_18]
0x180016546  call    ?make_bstr_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_failfast(ushort const *)
0x18001654b  mov     esi, 1
0x180016550  mov     rcx, [rax]
0x180016553  jmp     short loc_180016561
0x180016555  lea     rax, [rbp+bstrString]
0x180016559  mov     esi, 2
0x18001655e  mov     rcx, r12
0x180016561  mov     [rbx+68h], rcx
0x180016565  mov     [rax], r12
0x180016568  test    sil, 2
0x18001656c  jz      short loc_180016580
0x18001656e  and     esi, 0FFFFFFFDh
0x180016571  mov     rcx, [rbp+bstrString]; bstrString
0x180016575  test    rcx, rcx
0x180016578  jz      short loc_180016580
0x18001657a  call    cs:__imp_SysFreeString
0x180016580  test    sil, 1
0x180016584  jz      short loc_180016598
0x180016586  and     esi, 0FFFFFFFEh
0x180016589  mov     rcx, [rbp+arg_18]; bstrString
0x18001658d  test    rcx, rcx
0x180016590  jz      short loc_180016598
0x180016592  call    cs:__imp_SysFreeString
0x180016598  test    r14, r14
0x18001659b  jz      short loc_1800165B3
0x18001659d  mov     rdx, r14
0x1800165a0  lea     rcx, [rbp+arg_18]
0x1800165a4  call    ?make_bstr_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_failfast(ushort const *)
0x1800165a9  mov     edi, 4
0x1800165ae  mov     rcx, [rax]
0x1800165b1  jmp     short loc_1800165BF
0x1800165b3  lea     rax, [rbp+bstrString]
0x1800165b7  mov     edi, 8
0x1800165bc  mov     rcx, r12
0x1800165bf  or      edi, esi
0x1800165c1  mov     [rbx+78h], rcx
0x1800165c5  mov     [rax], r12
0x1800165c8  test    dil, 8
0x1800165cc  jz      short loc_1800165E0
0x1800165ce  and     edi, 0FFFFFFF7h
0x1800165d1  mov     rcx, [rbp+bstrString]; bstrString
0x1800165d5  test    rcx, rcx
0x1800165d8  jz      short loc_1800165E0
0x1800165da  call    cs:__imp_SysFreeString
0x1800165e0  test    dil, 4
0x1800165e4  jz      short loc_1800165F8
0x1800165e6  and     edi, 0FFFFFFFBh
0x1800165e9  mov     rcx, [rbp+arg_18]; bstrString
0x1800165ed  test    rcx, rcx
0x1800165f0  jz      short loc_1800165F8
0x1800165f2  call    cs:__imp_SysFreeString
0x1800165f8  mov     rdx, [rbp+arg_20]
0x1800165fc  test    rdx, rdx
0x1800165ff  jz      short loc_180016614
0x180016601  lea     rcx, [rbp+bstrString]
0x180016605  call    ?make_bstr_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_failfast(ushort const *)
0x18001660a  mov     esi, 10h
0x18001660f  mov     rcx, [rax]
0x180016612  jmp     short loc_180016620
0x180016614  lea     rax, [rbp+arg_20]
0x180016618  mov     esi, 20h ; ' '
0x18001661d  mov     rcx, r12
0x180016620  or      esi, edi
0x180016622  mov     [rbx+80h], rcx
0x180016629  mov     [rax], r12
0x18001662c  test    sil, 20h
0x180016630  jz      short loc_180016644
0x180016632  and     esi, 0FFFFFFDFh
0x180016635  mov     rcx, [rbp+arg_20]; bstrString
0x180016639  test    rcx, rcx
0x18001663c  jz      short loc_180016644
0x18001663e  call    cs:__imp_SysFreeString
0x180016644  test    sil, 10h
0x180016648  jz      short loc_180016659
0x18001664a  mov     rcx, [rbp+bstrString]; bstrString
0x18001664e  test    rcx, rcx
0x180016651  jz      short loc_180016659
0x180016653  call    cs:__imp_SysFreeString
0x180016659  mov     [rbx+88h], r12
0x180016660  lea     rdi, [rbx+90h]
0x180016667  mov     [rdi], r12
0x18001666a  lea     rsi, [rbx+98h]
0x180016671  mov     [rsi], r12d
0x180016674  mov     [rbx+0A0h], r12
0x18001667b  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180016682  xor     r8d, r8d; Flags
0x180016685  xor     edx, edx; dwSpinCount
0x180016687  call    cs:__imp_InitializeCriticalSectionEx
0x18001668d  nop
0x18001668e  mov     [rbx+0D0h], r12
0x180016695  cmp     r15d, 2
0x180016699  setz    al
0x18001669c  mov     [rbx+70h], al
0x18001669f  lea     rcx, [rbx+54h]; pguid
0x1800166a3  call    cs:__imp_CoCreateGuid
0x1800166a9  mov     rcx, [rbp+38h]; this
0x1800166ad  test    eax, eax
0x1800166af  jns     short loc_1800166C6
0x1800166b1  mov     r9d, eax; char *
0x1800166b4  lea     r8, aOnecoreuapInet_39; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800166bb  mov     edx, 3Bh ; ';'; void *
0x1800166c0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800166c6  mov     rcx, rbx; this
0x1800166c9  call    ?CreateRACProfile@CoreWebViewHostProcess@@AEAAXXZ; CoreWebViewHostProcess::CreateRACProfile(void)
0x1800166ce  lea     rcx, aS1153102436238; "S-1-15-3-1024-3623855041-1826999956-374"...
0x1800166d5  call    AppTokenHasCapability
0x1800166da  movzx   edx, al
0x1800166dd  lea     edx, ds:137h[rdx*8]
0x1800166e4  mov     ecx, 9
0x1800166e9  call    cs:__imp_?GetRACLaunchFlags@@YAKKK@Z; GetRACLaunchFlags(ulong,ulong)
0x1800166ef  mov     [rbp+var_20], rdi
0x1800166f3  mov     [rbp+var_18], r12
0x1800166f7  mov     [rbp+var_10], 1
0x1800166fb  mov     [rsp+50h+var_28], rsi
0x180016700  lea     rcx, [rbp+var_18]
0x180016704  mov     [rsp+50h+var_30], rcx
0x180016709  mov     ecx, eax
0x18001670b  call    ?BuildProcessSecurityAttributeBlob@@YAXW4RestrictedAppContainerLaunchFlags@Core@ApplicationModel@Windows@@K_N1PEAPEAEPEAK@Z; BuildProcessSecurityAttributeBlob(Windows::ApplicationModel::Core::RestrictedAppContainerLaunchFlags,ulong,bool,bool,uchar * *,ulong *)
0x180016710  lea     rcx, [rbp+var_20]
0x180016714  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016719  nop
0x18001671a  mov     rax, rbx
0x18001671d  add     rsp, 50h
0x180016721  pop     r15
0x180016723  pop     r14
0x180016725  pop     r12
0x180016727  pop     rdi
0x180016728  pop     rsi
0x180016729  pop     rbx
0x18001672a  pop     rbp
0x18001672b  retn
```
