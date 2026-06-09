# PropertyValueFactory::GetInstance(Windows::Foundation::IPropertyValueStatics * *)

- ea: `0x100aa0f2`
- end: `0x100aa1c9`
- name: `?GetInstance@PropertyValueFactory@@QAEJPAPAUIPropertyValueStatics@Foundation@Windows@@@Z`
- size: `215`
- prototype: `HRESULT __thiscall(PropertyValueFactory *this, Windows::Foundation::IPropertyValueStatics **propertyfactory)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100aaa1a`

## callees

- `0x1006b470`
- `0x10073ac9`
- `0x100aa0f2`
- `0x10128923`
- `0x10128b89`
- `0x10128c4b`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100aa13f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100aa13f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100aa12c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100aa12c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100aa15d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100aa15d`

## pseudocode

```c
HRESULT __thiscall PropertyValueFactory::GetInstance(
        PropertyValueFactory *this,
        Windows::Foundation::IPropertyValueStatics **propertyfactory)
{
  volatile unsigned int dwGitCookie; // ecx
  HSTRING__ *hstring; // esi
  int ActivationFactory; // esi
  Windows::Foundation::IPropertyValueStatics *v6; // eax
  unsigned int cookie; // [esp+Ch] [ebp-24h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> ptr; // [esp+10h] [ebp-20h] BYREF
  Windows::Internal::StringReference clsid; // [esp+14h] [ebp-1Ch] BYREF

  *propertyfactory = 0;
  dwGitCookie = this->_dwGitCookie;
  cookie = dwGitCookie;
  if ( dwGitCookie )
    return GetInterfaceFromGlobal(dwGitCookie, &_GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, (void **)propertyfactory);
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &clsid._header, &clsid._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ptr.ptr_ = 0;
  hstring = clsid._hstring;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&ptr);
  ActivationFactory = RoGetActivationFactory(hstring, &_GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &ptr);
  if ( ActivationFactory >= 0 )
  {
    if ( RegisterInterfaceInGlobal(ptr.ptr_, &_GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &cookie) >= 0 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this, cookie, 0) )
        RevokeInterfaceFromGlobal(cookie);
    }
    v6 = ptr.ptr_;
    ActivationFactory = 0;
    ptr.ptr_ = 0;
    *propertyfactory = v6;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&ptr);
  return ActivationFactory;
}

```

## disassembly

```asm
0x100aa0f2  mov     edi, edi
0x100aa0f4  push    ebp
0x100aa0f5  mov     ebp, esp
0x100aa0f7  sub     esp, 24h
0x100aa0fa  mov     eax, ___security_cookie
0x100aa0ff  xor     eax, ebp
0x100aa101  mov     [ebp+var_4], eax
0x100aa104  push    ebx
0x100aa105  push    esi
0x100aa106  push    edi
0x100aa107  mov     edi, [ebp+propertyfactory]
0x100aa10a  mov     ebx, this
0x100aa10c  xor     esi, esi
0x100aa10e  mov     [edi], esi
0x100aa110  mov     this, [ebx]; cookie
0x100aa112  mov     [ebp+cookie], this
0x100aa115  test    this, this
0x100aa117  jnz     loc_100AA1AD
0x100aa11d  lea     eax, [ebp+clsid]
0x100aa120  push    eax; string
0x100aa121  lea     eax, [ebp+clsid._header]
0x100aa124  push    eax; hstringHeader
0x100aa125  push    20h ; ' '; length
0x100aa127  push    offset ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x100aa12c  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100aa132  test    eax, eax
0x100aa134  jns     short loc_100AA145
0x100aa136  push    esi; lpArguments
0x100aa137  push    esi; nNumberOfArguments
0x100aa138  push    1; dwExceptionFlags
0x100aa13a  push    0C000000Dh; dwExceptionCode
0x100aa13f  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100aa145  mov     [ebp+ptr.ptr_], esi
0x100aa148  lea     this, [ebp+ptr]; this
0x100aa14b  mov     esi, [ebp+clsid._hstring]
0x100aa14e  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100aa153  lea     eax, [ebp+ptr]
0x100aa156  push    eax
0x100aa157  push    offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x100aa15c  push    esi
0x100aa15d  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x100aa163  mov     esi, eax
0x100aa165  test    esi, esi
0x100aa167  js      short loc_100AA1A1
0x100aa169  mov     this, [ebp+ptr.ptr_]; ptr
0x100aa16c  lea     eax, [ebp+cookie]
0x100aa16f  push    eax; pcookie
0x100aa170  mov     edx, offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x100aa175  call    ?RegisterInterfaceInGlobal@@YGJPAUIUnknown@@ABU_GUID@@PAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x100aa17a  test    eax, eax
0x100aa17c  js      short loc_100AA193
0x100aa17e  mov     this, [ebp+cookie]
0x100aa181  xor     eax, eax
0x100aa183  lock cmpxchg [ebx], this
0x100aa187  test    eax, eax
0x100aa189  jz      short loc_100AA193
0x100aa18b  mov     this, [ebp+cookie]; cookie
0x100aa18e  call    ?RevokeInterfaceFromGlobal@@YGJK@Z; RevokeInterfaceFromGlobal(ulong)
0x100aa193  mov     eax, [ebp+ptr.ptr_]
0x100aa196  xor     esi, esi
0x100aa198  mov     [ebp+ptr.ptr_], 0
0x100aa19f  mov     [edi], eax
0x100aa1a1  lea     this, [ebp+ptr]; this
0x100aa1a4  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100aa1a9  mov     eax, esi
0x100aa1ab  jmp     short loc_100AA1B8
0x100aa1ad  push    edi; ppv
0x100aa1ae  mov     edx, offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x100aa1b3  call    ?GetInterfaceFromGlobal@@YGJKABU_GUID@@PAPAX@Z; GetInterfaceFromGlobal(ulong,_GUID const &,void * *)
0x100aa1b8  mov     this, [ebp+var_4]
0x100aa1bb  pop     edi
0x100aa1bc  pop     esi
0x100aa1bd  xor     this, ebp; cookie
0x100aa1bf  pop     ebx
0x100aa1c0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100aa1c5  leave
0x100aa1c6  retn    4
```
