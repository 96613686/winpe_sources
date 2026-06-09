# CProcessExtensionTbl::GetClsidFromFileTypeAssocation(ushort const *,_GUID *)

- ea: `0x180058d64`
- end: `0x180058f1c`
- name: `?GetClsidFromFileTypeAssocation@CProcessExtensionTbl@@AEAAJPEBGPEAU_GUID@@@Z`
- size: `440`
- prototype: `HRESULT __fastcall(CProcessExtensionTbl *this, const wchar_t *pwszExt, _GUID *pclsid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058bb4`

## callees

- `0x1800085a8`
- `0x18001217c`
- `0x18002a618`
- `0x180042ffc`
- `0x1800587d4`
- `0x180058d64`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180058dcc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180058dcc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180058ed0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180058ed0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058e0d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058e0d`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180058da5`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180058da5`

## string_xrefs

- `0x180058e23`: `com\ole32\com\class\pexttbl.cxx`
- `0x180058e49`: `com\ole32\com\class\pexttbl.cxx`
- `0x180058eac`: `com\ole32\com\class\pexttbl.cxx`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CProcessExtensionTbl::GetClsidFromFileTypeAssocation(
        CProcessExtensionTbl *this,
        const wchar_t *pwszExt,
        _GUID *pclsid)
{
  _DWORD *ReservedForOle; // rax
  int v6; // ebx
  int Instance; // eax
  IApplicationAssociationRegistration *ptr; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v10; // eax
  unsigned int v11; // edx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > progIdForExt; // [rsp+30h] [rbp-10h] BYREF
  _DWORD *v14; // [rsp+38h] [rbp-8h] BYREF
  void *retaddr; // [rsp+58h] [rbp+18h]
  CProcessExtensionTbl *coInitWrapper; // [rsp+60h] [rbp+20h] OVERLAPPED BYREF
  Microsoft::WRL::ComPtr<IApplicationAssociationRegistration> appAssociations; // [rsp+78h] [rbp+38h] BYREF

  coInitWrapper = this;
  LOBYTE(coInitWrapper) = 0;
  ReservedForOle = NtCurrentTeb()->ReservedForOle;
  v14 = ReservedForOle;
  if ( !ReservedForOle )
  {
    v6 = InternalTlsAllocData(&v14);
    if ( v6 < 0 )
      goto LABEL_10;
    ReservedForOle = v14;
  }
  if ( !ReservedForOle[10] )
  {
    v6 = CoInitializeEx(0, 2u);
    if ( v6 >= 0 )
    {
      LOBYTE(coInitWrapper) = 1;
      goto LABEL_7;
    }
LABEL_10:
    wil::details::in1diag3::Return_Hr(retaddr, 0x10Eu, "com\\ole32\\com\\class\\pexttbl.cxx", v6);
    goto LABEL_17;
  }
LABEL_7:
  appAssociations.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&appAssociations);
  Instance = CoCreateInstance(
               &CLSID_ApplicationAssociationRegistration,
               0,
               1u,
               &GUID_4e530b0a_e611_4c77_a3ac_9031d022281b,
               (LPVOID *)&appAssociations.ptr_);
  v6 = Instance;
  if ( Instance >= 0 )
  {
    ptr = appAssociations.ptr_;
    progIdForExt.m_ptr = 0;
    QueryInterface = appAssociations.ptr_->lpVtbl[1].QueryInterface;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &progIdForExt,
      0);
    v10 = ((__int64 (__fastcall *)(IApplicationAssociationRegistration *, const wchar_t *, _QWORD, __int64, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *))QueryInterface)(
            ptr,
            pwszExt,
            0,
            1,
            &progIdForExt);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v10 = CLSIDFromProgID(progIdForExt.m_ptr, pclsid);
      v6 = v10;
      if ( v10 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&progIdForExt);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&appAssociations);
        v6 = 0;
        goto LABEL_17;
      }
      v11 = 279;
    }
    else
    {
      v11 = 277;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v11, "com\\ole32\\com\\class\\pexttbl.cxx", v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&progIdForExt);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x112u, "com\\ole32\\com\\class\\pexttbl.cxx", Instance);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&appAssociations);
LABEL_17:
  CoInitializeIfNecessaryRAII::~CoInitializeIfNecessaryRAII((CoInitializeIfNecessaryRAII *)&coInitWrapper);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180058d64  mov     [rsp-18h+arg_8], rbx
0x180058d69  mov     [rsp-18h+arg_10], rsi
0x180058d6e  mov     qword ptr [rsp-18h+coInitWrapper._isCoInitialized], rcx
0x180058d73  push    rbp
0x180058d74  push    rdi
0x180058d75  push    r14
0x180058d77  mov     rbp, rsp
0x180058d7a  sub     rsp, 40h
0x180058d7e  mov     rax, gs:30h
0x180058d87  mov     rsi, pclsid
0x180058d8a  mov     r14, pwszExt
0x180058d8d  mov     [rbp+coInitWrapper._isCoInitialized], 0
0x180058d91  mov     rax, [rax+1758h]
0x180058d98  mov     [rbp+var_8], rax
0x180058d9c  test    rax, rax
0x180058d9f  jnz     short loc_180058DBF
0x180058da1  lea     rcx, [rbp+var_8]
0x180058da5  call    cs:__imp_InternalTlsAllocData
0x180058dac  nop     dword ptr [rax+rax+00h]
0x180058db1  mov     ebx, eax
0x180058db3  test    eax, eax
0x180058db5  js      loc_180058E45
0x180058dbb  mov     rax, [rbp+var_8]
0x180058dbf  cmp     dword ptr [rax+28h], 0
0x180058dc3  jnz     short loc_180058DE2
0x180058dc5  mov     edx, 2; dwCoInit
0x180058dca  xor     ecx, ecx; pvReserved
0x180058dcc  call    cs:__imp_CoInitializeEx
0x180058dd3  nop     dword ptr [rax+rax+00h]
0x180058dd8  mov     ebx, eax
0x180058dda  test    eax, eax
0x180058ddc  js      short loc_180058E45
0x180058dde  mov     [rbp+coInitWrapper._isCoInitialized], 1
0x180058de2  and     [rbp+appAssociations.ptr_], 0
0x180058de7  lea     rcx, [rbp+appAssociations]; this
0x180058deb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058df0  xor     edx, edx; pUnkOuter
0x180058df2  lea     rax, [rbp+appAssociations]
0x180058df6  lea     r9, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x180058dfd  mov     [rsp+40h+ppv], rax; ppv
0x180058e02  lea     rcx, CLSID_ApplicationAssociationRegistration; rclsid
0x180058e09  lea     r8d, [pwszExt+1]; dwClsContext
0x180058e0d  call    cs:__imp_CoCreateInstance
0x180058e14  nop     dword ptr [rax+rax+00h]
0x180058e19  mov     ebx, eax
0x180058e1b  test    eax, eax
0x180058e1d  jns     short loc_180058E62
0x180058e1f  mov     rcx, [rbp+18h]; callerReturnAddress
0x180058e23  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x180058e2a  mov     r9d, eax; hr
0x180058e2d  mov     edx, 112h; lineNumber
0x180058e32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e37  lea     rcx, [rbp+appAssociations]; this
0x180058e3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058e40  jmp     loc_180058EFD
0x180058e45  mov     rcx, [rbp+18h]; callerReturnAddress
0x180058e49  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x180058e50  mov     r9d, ebx; hr
0x180058e53  mov     edx, 10Eh; lineNumber
0x180058e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e5d  jmp     loc_180058EFD
0x180058e62  mov     rbx, [rbp+appAssociations.ptr_]
0x180058e66  lea     rcx, [rbp+progIdForExt]; this
0x180058e6a  and     [rbp+progIdForExt.m_ptr], 0
0x180058e6f  xor     edx, edx; ptr
0x180058e71  mov     rax, [rbx]
0x180058e74  mov     rdi, [rax+18h]
0x180058e78  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058e7d  lea     rax, [rbp+progIdForExt]
0x180058e81  mov     r9d, 1
0x180058e87  mov     [rsp+40h+ppv], rax
0x180058e8c  xor     r8d, r8d
0x180058e8f  mov     rax, rdi
0x180058e92  mov     pwszExt, r14
0x180058e95  mov     rcx, rbx
0x180058e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e9d  mov     ebx, eax
0x180058e9f  test    eax, eax
0x180058ea1  jns     short loc_180058EC9
0x180058ea3  mov     edx, 115h; lineNumber
0x180058ea8  mov     rcx, [rbp+18h]; callerReturnAddress
0x180058eac  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x180058eb3  mov     r9d, eax; hr
0x180058eb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058ebb  lea     rcx, [rbp+progIdForExt]; this
0x180058ebf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058ec4  jmp     loc_180058E37
0x180058ec9  mov     rcx, [rbp+progIdForExt.m_ptr]; lpszProgID
0x180058ecd  mov     pwszExt, rsi; lpclsid
0x180058ed0  call    cs:__imp_CLSIDFromProgID
0x180058ed7  nop     dword ptr [rax+rax+00h]
0x180058edc  mov     ebx, eax
0x180058ede  test    eax, eax
0x180058ee0  jns     short loc_180058EE9
0x180058ee2  mov     edx, 117h
0x180058ee7  jmp     short loc_180058EA8
0x180058ee9  lea     rcx, [rbp+progIdForExt]; this
0x180058eed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058ef2  lea     rcx, [rbp+appAssociations]; this
0x180058ef6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180058efb  xor     ebx, ebx
0x180058efd  lea     rcx, [rbp+coInitWrapper]; this
0x180058f01  call    ??1CoInitializeIfNecessaryRAII@@QEAA@XZ; CoInitializeIfNecessaryRAII::~CoInitializeIfNecessaryRAII(void)
0x180058f06  mov     rsi, [rsp+40h+arg_10]
0x180058f0b  mov     eax, ebx
0x180058f0d  mov     rbx, [rsp+40h+arg_8]
0x180058f12  add     rsp, 40h
0x180058f16  pop     r14
0x180058f18  pop     rdi
0x180058f19  pop     rbp
0x180058f1a  retn
```
