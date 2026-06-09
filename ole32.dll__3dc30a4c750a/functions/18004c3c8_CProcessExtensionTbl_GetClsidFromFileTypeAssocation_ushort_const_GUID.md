# CProcessExtensionTbl::GetClsidFromFileTypeAssocation(ushort const *,_GUID *)

- ea: `0x18004c3c8`
- end: `0x18004c57d`
- name: `?GetClsidFromFileTypeAssocation@CProcessExtensionTbl@@AEAAJPEBGPEAU_GUID@@@Z`
- size: `437`
- prototype: `HRESULT __fastcall(CProcessExtensionTbl *this, const wchar_t *pwszExt, _GUID *pclsid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800660a4`

## callees

- `0x18000a0e8`
- `0x1800185ec`
- `0x18003ffb4`
- `0x18004c3c8`
- `0x18004c584`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004c42a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004c42a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18004c532`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18004c532`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c468`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c54e`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18004c409`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18004c409`

## string_xrefs

- `0x18004c478`: `com\ole32\com\class\pexttbl.cxx`
- `0x18004c49e`: `com\ole32\com\class\pexttbl.cxx`
- `0x18004c504`: `com\ole32\com\class\pexttbl.cxx`

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
  IApplicationAssociationRegistration *ptr; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
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
  if ( ReservedForOle[10] )
    goto LABEL_7;
  v6 = CoInitializeEx(0, 2u);
  if ( v6 < 0 )
  {
LABEL_10:
    wil::details::in1diag3::Return_Hr(retaddr, 0x10Eu, "com\\ole32\\com\\class\\pexttbl.cxx", v6);
    goto LABEL_20;
  }
  LOBYTE(coInitWrapper) = 1;
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
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x112u, "com\\ole32\\com\\class\\pexttbl.cxx", Instance);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&appAssociations);
    goto LABEL_20;
  }
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
  if ( v10 < 0 )
  {
    v11 = 277;
    goto LABEL_13;
  }
  v10 = CLSIDFromProgID(progIdForExt.m_ptr, pclsid);
  v6 = v10;
  if ( v10 < 0 )
  {
    v11 = 279;
LABEL_13:
    wil::details::in1diag3::Return_Hr(retaddr, v11, "com\\ole32\\com\\class\\pexttbl.cxx", v10);
    if ( progIdForExt.m_ptr )
      CoTaskMemFree(progIdForExt.m_ptr);
    goto LABEL_9;
  }
  if ( progIdForExt.m_ptr )
    CoTaskMemFree(progIdForExt.m_ptr);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&appAssociations);
  v6 = 0;
LABEL_20:
  CoInitializeIfNecessaryRAII::~CoInitializeIfNecessaryRAII((CoInitializeIfNecessaryRAII *)&coInitWrapper);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004c3c8  mov     [rsp-18h+arg_8], rbx
0x18004c3cd  mov     [rsp-18h+arg_10], rsi
0x18004c3d2  mov     qword ptr [rsp-18h+coInitWrapper._isCoInitialized], rcx
0x18004c3d7  push    rbp
0x18004c3d8  push    rdi
0x18004c3d9  push    r14
0x18004c3db  mov     rbp, rsp
0x18004c3de  sub     rsp, 40h
0x18004c3e2  mov     rax, gs:30h
0x18004c3eb  mov     rsi, pclsid
0x18004c3ee  mov     r14, pwszExt
0x18004c3f1  mov     [rbp+coInitWrapper._isCoInitialized], 0
0x18004c3f5  mov     rax, [rax+1758h]
0x18004c3fc  mov     [rbp+var_8], rax
0x18004c400  test    rax, rax
0x18004c403  jnz     short loc_18004C41D
0x18004c405  lea     rcx, [rbp+var_8]
0x18004c409  call    cs:__imp_InternalTlsAllocData
0x18004c40f  mov     ebx, eax
0x18004c411  test    eax, eax
0x18004c413  js      loc_18004C49A
0x18004c419  mov     rax, [rbp+var_8]
0x18004c41d  cmp     dword ptr [rax+28h], 0
0x18004c421  jnz     short loc_18004C43A
0x18004c423  mov     edx, 2; dwCoInit
0x18004c428  xor     ecx, ecx; pvReserved
0x18004c42a  call    cs:__imp_CoInitializeEx
0x18004c430  mov     ebx, eax
0x18004c432  test    eax, eax
0x18004c434  js      short loc_18004C49A
0x18004c436  mov     [rbp+coInitWrapper._isCoInitialized], 1
0x18004c43a  lea     rcx, [rbp+appAssociations]; this
0x18004c43e  mov     [rbp+appAssociations.ptr_], 0
0x18004c446  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c44b  xor     edx, edx; pUnkOuter
0x18004c44d  lea     rax, [rbp+appAssociations]
0x18004c451  lea     r9, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x18004c458  mov     [rsp+40h+ppv], rax; ppv
0x18004c45d  lea     rcx, CLSID_ApplicationAssociationRegistration; rclsid
0x18004c464  lea     r8d, [pwszExt+1]; dwClsContext
0x18004c468  call    cs:__imp_CoCreateInstance
0x18004c46e  mov     ebx, eax
0x18004c470  test    eax, eax
0x18004c472  jns     short loc_18004C4B7
0x18004c474  mov     rcx, [rbp+18h]; callerReturnAddress
0x18004c478  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x18004c47f  mov     r9d, eax; hr
0x18004c482  mov     edx, 112h; lineNumber
0x18004c487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c48c  lea     rcx, [rbp+appAssociations]; this
0x18004c490  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c495  jmp     loc_18004C55F
0x18004c49a  mov     rcx, [rbp+18h]; callerReturnAddress
0x18004c49e  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x18004c4a5  mov     r9d, ebx; hr
0x18004c4a8  mov     edx, 10Eh; lineNumber
0x18004c4ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c4b2  jmp     loc_18004C55F
0x18004c4b7  mov     rdi, [rbp+appAssociations.ptr_]
0x18004c4bb  lea     rcx, [rbp+progIdForExt]; this
0x18004c4bf  mov     [rbp+progIdForExt.m_ptr], 0
0x18004c4c7  xor     edx, edx; ptr
0x18004c4c9  mov     rax, [rdi]
0x18004c4cc  mov     rbx, [rax+18h]
0x18004c4d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004c4d5  lea     rax, [rbp+progIdForExt]
0x18004c4d9  mov     r9d, 1
0x18004c4df  mov     [rsp+40h+ppv], rax
0x18004c4e4  xor     r8d, r8d
0x18004c4e7  mov     rax, rbx
0x18004c4ea  mov     pwszExt, r14
0x18004c4ed  mov     rcx, rdi
0x18004c4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4f5  mov     ebx, eax
0x18004c4f7  test    eax, eax
0x18004c4f9  jns     short loc_18004C52B
0x18004c4fb  mov     edx, 115h; lineNumber
0x18004c500  mov     rcx, [rbp+18h]; callerReturnAddress
0x18004c504  lea     pclsid, aComOle32ComCla_1; "com\\ole32\\com\\class\\pexttbl.cxx"
0x18004c50b  mov     r9d, eax; hr
0x18004c50e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c513  mov     rcx, [rbp+progIdForExt.m_ptr]; pv
0x18004c517  test    rcx, rcx
0x18004c51a  jz      loc_18004C48C
0x18004c520  call    cs:__imp_CoTaskMemFree
0x18004c526  jmp     loc_18004C48C
0x18004c52b  mov     rcx, [rbp+progIdForExt.m_ptr]; lpszProgID
0x18004c52f  mov     pwszExt, rsi; lpclsid
0x18004c532  call    cs:__imp_CLSIDFromProgID
0x18004c538  mov     ebx, eax
0x18004c53a  test    eax, eax
0x18004c53c  jns     short loc_18004C545
0x18004c53e  mov     edx, 117h
0x18004c543  jmp     short loc_18004C500
0x18004c545  mov     rcx, [rbp+progIdForExt.m_ptr]; pv
0x18004c549  test    rcx, rcx
0x18004c54c  jz      short loc_18004C554
0x18004c54e  call    cs:__imp_CoTaskMemFree
0x18004c554  lea     rcx, [rbp+appAssociations]; this
0x18004c558  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c55d  xor     ebx, ebx
0x18004c55f  lea     rcx, [rbp+coInitWrapper]; this
0x18004c563  call    ??1CoInitializeIfNecessaryRAII@@QEAA@XZ; CoInitializeIfNecessaryRAII::~CoInitializeIfNecessaryRAII(void)
0x18004c568  mov     rsi, [rsp+40h+arg_10]
0x18004c56d  mov     eax, ebx
0x18004c56f  mov     rbx, [rsp+40h+arg_8]
0x18004c574  add     rsp, 40h
0x18004c578  pop     r14
0x18004c57a  pop     rdi
0x18004c57b  pop     rbp
0x18004c57c  retn
```
