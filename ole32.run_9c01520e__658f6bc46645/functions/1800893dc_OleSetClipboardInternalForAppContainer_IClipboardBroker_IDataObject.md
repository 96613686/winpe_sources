# OleSetClipboardInternalForAppContainer(IClipboardBroker *,IDataObject *)

- ea: `0x1800893dc`
- end: `0x1800895c3`
- name: `?OleSetClipboardInternalForAppContainer@@YAJPEAUIClipboardBroker@@PEAUIDataObject@@@Z`
- size: `487`
- prototype: `HRESULT __fastcall(IClipboardBroker *clipboardBroker, IDataObject *dataObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180087194`

## callees

- `0x1800085a8`
- `0x18003d730`
- `0x18008798c`
- `0x1800879ac`
- `0x1800893dc`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008953d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008953d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180089447`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180089447`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x1800894ba`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x1800894ba`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180089401`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180089401`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18008954f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18008954f`

## string_xrefs

- `0x180089490`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x1800894ea`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180089524`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18008957b`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall OleSetClipboardInternalForAppContainer(IClipboardBroker *clipboardBroker, IDataObject *dataObject)
{
  int v2; // esi
  IServiceHostBrokerProvider *ptr; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
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
0x1800893dc  mov     [rsp-18h+arg_8], rbx
0x1800893e1  push    rbp
0x1800893e2  push    rsi
0x1800893e3  push    rdi
0x1800893e4  mov     rbp, rsp
0x1800893e7  sub     rsp, 40h
0x1800893eb  mov     rax, [clipboardBroker]
0x1800893ee  mov     rax, [rax+18h]
0x1800893f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893f7  mov     esi, eax
0x1800893f9  test    eax, eax
0x1800893fb  js      loc_1800895B3
0x180089401  call    cs:__imp_EdpGetIsManaged
0x180089408  nop     dword ptr [rax+rax+00h]
0x18008940d  test    eax, eax
0x18008940f  jz      loc_1800895B3
0x180089415  and     [rbp+brokerProvider.ptr_], 0
0x18008941a  lea     clipboardBroker, [rbp+brokerProvider]; this
0x18008941e  and     [rbp+clipboardServer.ptr_], 0
0x180089423  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089428  lea     rax, [rbp+brokerProvider]
0x18008942c  xor     edx, edx; pUnkOuter
0x18008942e  lea     r9, _GUID_0f4accb1_d8f9_4011_ba37_2557925a78cf; riid
0x180089435  mov     [rsp+40h+ppv], rax; ppv
0x18008943a  mov     r8d, 404h; dwClsContext
0x180089440  lea     clipboardBroker, _GUID_3480a401_bde9_4407_bc02_798a866ac051; rclsid
0x180089447  call    cs:__imp_CoCreateInstance
0x18008944e  nop     dword ptr [rax+rax+00h]
0x180089453  test    eax, eax
0x180089455  js      short loc_1800894A4
0x180089457  mov     rbx, [rbp+brokerProvider.ptr_]
0x18008945b  lea     clipboardBroker, [rbp+clipboardServer]; this
0x18008945f  mov     rax, [rbx]
0x180089462  mov     rdi, [rax+18h]
0x180089466  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008946b  lea     r9, [rbp+clipboardServer]
0x18008946f  mov     clipboardBroker, rbx
0x180089472  lea     r8, _GUID_fed95700_f716_4950_bcac_8e2e1ca1b307
0x180089479  mov     rax, rdi
0x18008947c  lea     dataObject, SID_ClipboardServer
0x180089483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089488  test    eax, eax
0x18008948a  jns     short loc_1800894A4
0x18008948c  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x180089490  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089497  mov     r9d, eax; hr
0x18008949a  mov     edx, 0D94h; lineNumber
0x18008949f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800894a4  cmp     [rbp+clipboardServer.ptr_], 0
0x1800894a9  jz      loc_1800895A1
0x1800894af  and     [rbp+edpContext.m_ptr], 0
0x1800894b4  lea     dataObject, [rbp+edpContext]
0x1800894b8  xor     ecx, ecx
0x1800894ba  call    cs:__imp_EdpGetContextForWindow
0x1800894c1  nop     dword ptr [rax+rax+00h]
0x1800894c6  test    eax, eax
0x1800894c8  js      short loc_180089538
0x1800894ca  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x1800894ce  mov     dataObject, [rbp+edpContext.m_ptr]
0x1800894d2  mov     rax, [clipboardBroker]
0x1800894d5  mov     dataObject, [dataObject+8]
0x1800894d9  mov     rax, [rax+40h]
0x1800894dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894e2  test    eax, eax
0x1800894e4  jns     short loc_1800894FE
0x1800894e6  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x1800894ea  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800894f1  mov     r9d, eax; hr
0x1800894f4  mov     edx, 0D9Ch; lineNumber
0x1800894f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800894fe  mov     rax, [rbp+edpContext.m_ptr]
0x180089502  test    byte ptr [rax], 3
0x180089505  jz      short loc_180089538
0x180089507  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x18008950b  mov     edx, 1
0x180089510  mov     rax, [clipboardBroker]
0x180089513  mov     rax, [rax+50h]
0x180089517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008951c  test    eax, eax
0x18008951e  jns     short loc_180089538
0x180089520  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x180089524  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18008952b  mov     r9d, eax; hr
0x18008952e  mov     edx, 0DA0h; lineNumber
0x180089533  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180089538  and     [rbp+uniqueAppId.m_ptr], 0
0x18008953d  call    cs:__imp_GetCurrentProcessId
0x180089544  nop     dword ptr [rax+rax+00h]
0x180089549  mov     ecx, eax
0x18008954b  lea     dataObject, [rbp+uniqueAppId]
0x18008954f  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x180089556  nop     dword ptr [rax+rax+00h]
0x18008955b  test    eax, eax
0x18008955d  js      short loc_18008958F
0x18008955f  mov     clipboardBroker, [rbp+clipboardServer.ptr_]
0x180089563  mov     dataObject, [rbp+uniqueAppId.m_ptr]
0x180089567  mov     rax, [clipboardBroker]
0x18008956a  mov     rax, [rax+48h]
0x18008956e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089573  test    eax, eax
0x180089575  jns     short loc_18008958F
0x180089577  mov     clipboardBroker, [rbp+18h]; callerReturnAddress
0x18008957b  lea     r8, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180089582  mov     r9d, eax; hr
0x180089585  mov     edx, 0DA7h; lineNumber
0x18008958a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008958f  lea     clipboardBroker, [rbp+uniqueAppId]; this
0x180089593  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089598  lea     clipboardBroker, [rbp+edpContext]; this
0x18008959c  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x1800895a1  lea     clipboardBroker, [rbp+clipboardServer]; this
0x1800895a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800895aa  lea     clipboardBroker, [rbp+brokerProvider]; this
0x1800895ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800895b3  mov     rbx, [rsp+40h+arg_8]
0x1800895b8  mov     eax, esi
0x1800895ba  add     rsp, 40h
0x1800895be  pop     rdi
0x1800895bf  pop     rsi
0x1800895c0  pop     rbp
0x1800895c1  retn
```
