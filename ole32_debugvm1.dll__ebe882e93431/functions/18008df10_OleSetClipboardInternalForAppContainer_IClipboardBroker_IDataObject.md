# OleSetClipboardInternalForAppContainer(IClipboardBroker *,IDataObject *)

- ea: `0x18008df10`
- end: `0x18008e0e4`
- name: `?OleSetClipboardInternalForAppContainer@@YAJPEAUIClipboardBroker@@PEAUIDataObject@@@Z`
- size: `468`
- prototype: `HRESULT __fastcall(IClipboardBroker *clipboardBroker, IDataObject *dataObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008bf20`

## callees

- `0x18000a0e8`
- `0x180039768`
- `0x1800405b8`
- `0x180040640`
- `0x18008df10`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008e06b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008e06b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008df7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008df7b`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x18008dfeb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x18008dfeb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18008df35`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18008df35`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18008e077`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18008e077`

## string_xrefs

- `0x18008dfbe`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18008e015`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18008e04f`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18008e09d`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall OleSetClipboardInternalForAppContainer(IClipboardBroker *clipboardBroker, IDataObject *dataObject)
{
  int v2; // esi
  IServiceHostBrokerProvider *ptr; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  HRESULT v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // eax
  DWORD CurrentProcessId; // eax
  HRESULT v9; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > uniqueAppId; // [rsp+30h] [rbp-10h] BYREF
  void *retaddr; // [rsp+58h] [rbp+18h]
  Microsoft::WRL::ComPtr<IClipboardProtectionServices> clipboardServer; // [rsp+60h] [rbp+20h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+70h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<IServiceHostBrokerProvider> brokerProvider; // [rsp+78h] [rbp+38h] BYREF

  v2 = ((__int64 (__fastcall *)(IClipboardBroker *, IDataObject *))clipboardBroker->lpVtbl[1].QueryInterface)(
         clipboardBroker,
         dataObject);
  if ( v2 >= 0 && (unsigned int)EdpGetIsManaged() )
  {
    brokerProvider.ptr_ = 0;
    clipboardServer.ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&brokerProvider);
    if ( CoCreateInstance(
           &GUID_3480a401_bde9_4407_bc02_798a866ac051,
           0,
           0x404u,
           &GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf,
           (LPVOID *)&brokerProvider.ptr_) >= 0 )
    {
      ptr = brokerProvider.ptr_;
      QueryInterface = brokerProvider.ptr_->lpVtbl[1].QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&clipboardServer);
      v5 = ((__int64 (__fastcall *)(IServiceHostBrokerProvider *, SID *, GUID *, Microsoft::WRL::ComPtr<IClipboardProtectionServices> *))QueryInterface)(
             ptr,
             &SID_ClipboardServer,
             &GUID_fed95700_f716_4950_bcac_8e2e1ca1b307,
             &clipboardServer);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, 0xD94u, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v5);
    }
    if ( clipboardServer.ptr_ )
    {
      edpContext.m_ptr = 0;
      if ( (int)EdpGetContextForWindow(0, &edpContext) >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(IClipboardProtectionServices *, wchar_t *))clipboardServer.ptr_->lpVtbl[2].Release)(
               clipboardServer.ptr_,
               edpContext.m_ptr->enterpriseIdForUIEnforcement);
        if ( v6 < 0 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0xD9Cu, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v6);
        if ( (edpContext.m_ptr->contextStates & 3) != 0 )
        {
          v7 = ((__int64 (__fastcall *)(IClipboardProtectionServices *, __int64))clipboardServer.ptr_->lpVtbl[3].AddRef)(
                 clipboardServer.ptr_,
                 1);
          if ( v7 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, 0xDA0u, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v7);
        }
      }
      uniqueAppId.m_ptr = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( (int)EdpGetAppLockerUniqueAppIdentifier(CurrentProcessId, &uniqueAppId) >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(IClipboardProtectionServices *, wchar_t *))clipboardServer.ptr_->lpVtbl[3].QueryInterface)(
               clipboardServer.ptr_,
               uniqueAppId.m_ptr);
        if ( v9 < 0 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0xDA7u, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v9);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&uniqueAppId);
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&edpContext);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&clipboardServer);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&brokerProvider);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008df10  mov     [rsp-18h+arg_8], rbx
0x18008df15  push    rbp
0x18008df16  push    rsi
0x18008df17  push    rdi
0x18008df18  mov     rbp, rsp
0x18008df1b  sub     rsp, 40h
0x18008df1f  mov     rax, [clipboardBroker]
0x18008df22  mov     rax, [rax+18h]
0x18008df26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df2b  mov     esi, eax
0x18008df2d  test    eax, eax
0x18008df2f  js      loc_18008E0D5
0x18008df35  call    cs:__imp_EdpGetIsManaged
0x18008df3b  test    eax, eax
0x18008df3d  jz      loc_18008E0D5
0x18008df43  lea     clipboardBroker, [rbp+brokerProvider]; this
0x18008df47  mov     [rbp+brokerProvider.ptr_], 0
0x18008df4f  mov     [rbp+clipboardServer.ptr_], 0
0x18008df57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008df5c  lea     rax, [rbp+brokerProvider]
0x18008df60  xor     edx, edx; pUnkOuter
0x18008df62  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x18008df69  mov     [rsp+40h+ppv], rax; ppv
0x18008df6e  mov     r8d, 404h; dwClsContext
0x18008df74  lea     clipboardBroker, _GUID_3480a401_bde9_4407_bc02_798a866ac051; rclsid
0x18008df7b  call    cs:__imp_CoCreateInstance
0x18008df81  test    eax, eax
0x18008df83  js      short loc_18008DFD2
0x18008df85  mov     rdi, [rbp+brokerProvider.ptr_]
0x18008df89  lea     clipboardBroker, [rbp+clipboardServer]; this
0x18008df8d  mov     rax, [rdi]
0x18008df90  mov     rbx, [rax+18h]
0x18008df94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008df99  lea     r9, [rbp+clipboardServer]
0x18008df9d  mov     clipboardBroker, rdi
0x18008dfa0  lea     r8, _GUID_fed95700_f716_4950_bcac_8e2e1ca1b307
0x18008dfa7  mov     rax, rbx
0x18008dfaa  lea     dataObject, SID_ClipboardServer
0x18008dfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfb6  test    eax, eax
0x18008dfb8  jns     short loc_18008DFD2
0x18008dfba  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x18008dfbe  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18008dfc5  mov     r9d, eax; hr
0x18008dfc8  mov     edx, 0D94h; lineNumber
0x18008dfcd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008dfd2  cmp     [rbp+clipboardServer.ptr_], 0
0x18008dfd7  jz      loc_18008E0C3
0x18008dfdd  lea     dataObject, [rbp+edpContext]
0x18008dfe1  mov     [rbp+edpContext.m_ptr], 0
0x18008dfe9  xor     ecx, ecx
0x18008dfeb  call    cs:__imp_EdpGetContextForWindow
0x18008dff1  test    eax, eax
0x18008dff3  js      short loc_18008E063
0x18008dff5  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x18008dff9  mov     dataObject, [rbp+edpContext.m_ptr]
0x18008dffd  mov     rax, [clipboardBroker]
0x18008e000  mov     dataObject, [dataObject+8]
0x18008e004  mov     rax, [rax+40h]
0x18008e008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e00d  test    eax, eax
0x18008e00f  jns     short loc_18008E029
0x18008e011  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x18008e015  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18008e01c  mov     r9d, eax; hr
0x18008e01f  mov     edx, 0D9Ch; lineNumber
0x18008e024  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e029  mov     rax, [rbp+edpContext.m_ptr]
0x18008e02d  test    byte ptr [rax], 3
0x18008e030  jz      short loc_18008E063
0x18008e032  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x18008e036  mov     edx, 1
0x18008e03b  mov     rax, [clipboardBroker]
0x18008e03e  mov     rax, [rax+50h]
0x18008e042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e047  test    eax, eax
0x18008e049  jns     short loc_18008E063
0x18008e04b  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x18008e04f  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18008e056  mov     r9d, eax; hr
0x18008e059  mov     edx, 0DA0h; lineNumber
0x18008e05e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e063  mov     [rbp+uniqueAppId.m_ptr], 0
0x18008e06b  call    cs:__imp_GetCurrentProcessId
0x18008e071  mov     ecx, eax
0x18008e073  lea     dataObject, [rbp+uniqueAppId]
0x18008e077  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x18008e07d  test    eax, eax
0x18008e07f  js      short loc_18008E0B1
0x18008e081  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x18008e085  mov     dataObject, [rbp+uniqueAppId.m_ptr]
0x18008e089  mov     rax, [clipboardBroker]
0x18008e08c  mov     rax, [rax+48h]
0x18008e090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e095  test    eax, eax
0x18008e097  jns     short loc_18008E0B1
0x18008e099  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x18008e09d  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18008e0a4  mov     r9d, eax; hr
0x18008e0a7  mov     edx, 0DA7h; lineNumber
0x18008e0ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e0b1  lea     clipboardBroker, [rbp+uniqueAppId]; this
0x18008e0b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008e0ba  lea     clipboardBroker, [rbp+edpContext]; this
0x18008e0be  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x18008e0c3  lea     clipboardBroker, [rbp+clipboardServer]; this
0x18008e0c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e0cc  lea     clipboardBroker, [rbp+brokerProvider]; this
0x18008e0d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008e0d5  mov     rbx, [rsp+40h+arg_8]
0x18008e0da  mov     eax, esi
0x18008e0dc  add     rsp, 40h
0x18008e0e0  pop     rdi
0x18008e0e1  pop     rsi
0x18008e0e2  pop     rbp
0x18008e0e3  retn
```
