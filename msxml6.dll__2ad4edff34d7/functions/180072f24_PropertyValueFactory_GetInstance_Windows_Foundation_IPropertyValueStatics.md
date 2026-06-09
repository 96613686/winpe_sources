# PropertyValueFactory::GetInstance(Windows::Foundation::IPropertyValueStatics * *)

- ea: `0x180072f24`
- end: `0x180073044`
- name: `?GetInstance@PropertyValueFactory@@QEAAJPEAPEAUIPropertyValueStatics@Foundation@Windows@@@Z`
- size: `288`
- prototype: `HRESULT __fastcall(PropertyValueFactory *this, Windows::Foundation::IPropertyValueStatics **propertyfactory)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072e38`

## callees

- `0x180072f24`
- `0x1800730a4`
- `0x1800731cc`
- `0x180092c9c`
- `0x1800cada0`
- `0x18014d280`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007301e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007301e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072f6d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072f9e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072f9e`

## pseudocode

```c
HRESULT __fastcall PropertyValueFactory::GetInstance(
        PropertyValueFactory *this,
        Windows::Foundation::IPropertyValueStatics **propertyfactory)
{
  volatile unsigned int dwGitCookie; // ecx
  HSTRING__ *hstring; // rbx
  int ActivationFactory; // eax
  Windows::Foundation::IPropertyValueStatics *v7; // rcx
  int v8; // ebx
  unsigned int cookie; // [rsp+20h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> ptr; // [rsp+28h] [rbp-38h] BYREF
  Windows::Internal::StringReference clsid; // [rsp+38h] [rbp-28h] BYREF

  *propertyfactory = 0;
  dwGitCookie = this->_dwGitCookie;
  cookie = dwGitCookie;
  if ( dwGitCookie )
    return GetInterfaceFromGlobal(dwGitCookie, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, (void **)propertyfactory);
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Foundation_PropertyValue,
         0x20u,
         &clsid._header,
         &clsid._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  hstring = clsid._hstring;
  ptr.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&ptr);
  ActivationFactory = RoGetActivationFactory(hstring, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &ptr);
  v7 = ptr.ptr_;
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    if ( ptr.ptr_ )
    {
      ptr.ptr_ = 0;
      v7->Release(v7);
    }
    return v8;
  }
  else
  {
    if ( RegisterInterfaceInGlobal(ptr.ptr_, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &cookie) >= 0 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this, cookie, 0) )
        RevokeInterfaceFromGlobal(cookie);
    }
    *propertyfactory = ptr.ptr_;
    return 0;
  }
}

```

## disassembly

```asm
0x180072f24  mov     [rsp-18h+arg_10], rbx
0x180072f29  push    rbp
0x180072f2a  push    rsi
0x180072f2b  push    rdi
0x180072f2c  mov     rbp, rsp
0x180072f2f  sub     rsp, 60h
0x180072f33  mov     rax, cs:__security_cookie
0x180072f3a  xor     rax, rsp
0x180072f3d  mov     [rbp+var_8], rax
0x180072f41  mov     rsi, this
0x180072f44  mov     qword ptr [propertyfactory], 0
0x180072f4b  mov     ecx, [this]; cookie
0x180072f4d  mov     rdi, propertyfactory
0x180072f50  mov     [rbp+cookie], ecx
0x180072f53  test    ecx, ecx
0x180072f55  jnz     loc_180073033
0x180072f5b  lea     edx, [this+20h]; length
0x180072f5e  lea     this, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; sourceString
0x180072f65  lea     r9, [rbp+clsid]; string
0x180072f69  lea     r8, [rbp+clsid._header]; hstringHeader
0x180072f6d  call    cs:__imp_WindowsCreateStringReference
0x180072f73  test    eax, eax
0x180072f75  js      loc_18007300F
0x180072f7b  mov     rbx, [rbp+clsid._hstring]
0x180072f7f  lea     this, [rbp+ptr]; this
0x180072f83  mov     [rbp+ptr.ptr_], 0
0x180072f8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072f90  lea     r8, [rbp+ptr]
0x180072f94  mov     this, rbx
0x180072f97  lea     propertyfactory, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180072f9e  call    cs:__imp_RoGetActivationFactory
0x180072fa4  mov     this, [rbp+ptr.ptr_]; ptr
0x180072fa8  mov     ebx, eax
0x180072faa  test    eax, eax
0x180072fac  js      short loc_180072FF2
0x180072fae  lea     r8, [rbp+cookie]; pcookie
0x180072fb2  lea     propertyfactory, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x180072fb9  call    ?RegisterInterfaceInGlobal@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x180072fbe  test    eax, eax
0x180072fc0  js      short loc_180072FCD
0x180072fc2  mov     ecx, [rbp+cookie]
0x180072fc5  xor     eax, eax
0x180072fc7  lock cmpxchg [rsi], ecx
0x180072fcb  jnz     short loc_180073029
0x180072fcd  mov     rax, [rbp+ptr.ptr_]
0x180072fd1  mov     [rdi], rax
0x180072fd4  xor     eax, eax
0x180072fd6  mov     this, [rbp+var_8]
0x180072fda  xor     this, rsp; StackCookie
0x180072fdd  call    __security_check_cookie
0x180072fe2  mov     rbx, [rsp+60h+arg_10]
0x180072fea  add     rsp, 60h
0x180072fee  pop     rdi
0x180072fef  pop     rsi
0x180072ff0  pop     rbp
0x180072ff1  retn
0x180072ff2  test    this, this
0x180072ff5  jz      short loc_18007300B
0x180072ff7  mov     [rbp+ptr.ptr_], 0
0x180072fff  mov     propertyfactory, [this]
0x180073002  mov     rax, [propertyfactory+10h]
0x180073006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007300b  mov     eax, ebx
0x18007300d  jmp     short loc_180072FD6
0x18007300f  xor     r9d, r9d; lpArguments
0x180073012  xor     r8d, r8d; nNumberOfArguments
0x180073015  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007301a  lea     edx, [r9+1]; dwExceptionFlags
0x18007301e  call    cs:__imp_RaiseException
0x180073024  jmp     loc_180072F7B
0x180073029  mov     ecx, [rbp+cookie]; cookie
0x18007302c  call    ?RevokeInterfaceFromGlobal@@YAJK@Z; RevokeInterfaceFromGlobal(ulong)
0x180073031  jmp     short loc_180072FCD
0x180073033  mov     r8, rdi; ppv
0x180073036  lea     propertyfactory, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x18007303d  call    ?GetInterfaceFromGlobal@@YAJKAEBU_GUID@@PEAPEAX@Z; GetInterfaceFromGlobal(ulong,_GUID const &,void * *)
0x180073042  jmp     short loc_180072FD6
```
