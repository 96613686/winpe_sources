# PropertyValueFactory::GetInstance(Windows::Foundation::IPropertyValueStatics * *)

- ea: `0x100a9fe2`
- end: `0x100aa0b9`
- name: `?GetInstance@PropertyValueFactory@@QAEJPAPAUIPropertyValueStatics@Foundation@Windows@@@Z`
- size: `215`
- prototype: `HRESULT __thiscall(PropertyValueFactory *this, Windows::Foundation::IPropertyValueStatics **propertyfactory)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100aa90a`

## callees

- `0x1006b510`
- `0x10073a99`
- `0x100a9fe2`
- `0x10128813`
- `0x10128a79`
- `0x10128b3b`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100aa02f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100aa02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100aa01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100aa01c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100aa04d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x100aa04d`

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
0x100a9fe2  mov     edi, edi
0x100a9fe4  push    ebp
0x100a9fe5  mov     ebp, esp
0x100a9fe7  sub     esp, 24h
0x100a9fea  mov     eax, ___security_cookie
0x100a9fef  xor     eax, ebp
0x100a9ff1  mov     [ebp+var_4], eax
0x100a9ff4  push    ebx
0x100a9ff5  push    esi
0x100a9ff6  push    edi
0x100a9ff7  mov     edi, [ebp+propertyfactory]
0x100a9ffa  mov     ebx, this
0x100a9ffc  xor     esi, esi
0x100a9ffe  mov     [edi], esi
0x100aa000  mov     this, [ebx]; cookie
0x100aa002  mov     [ebp+cookie], this
0x100aa005  test    this, this
0x100aa007  jnz     loc_100AA09D
0x100aa00d  lea     eax, [ebp+clsid]
0x100aa010  push    eax; string
0x100aa011  lea     eax, [ebp+clsid._header]
0x100aa014  push    eax; hstringHeader
0x100aa015  push    20h ; ' '; length
0x100aa017  push    offset ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x100aa01c  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100aa022  test    eax, eax
0x100aa024  jns     short loc_100AA035
0x100aa026  push    esi; lpArguments
0x100aa027  push    esi; nNumberOfArguments
0x100aa028  push    1; dwExceptionFlags
0x100aa02a  push    0C000000Dh; dwExceptionCode
0x100aa02f  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100aa035  mov     [ebp+ptr.ptr_], esi
0x100aa038  lea     this, [ebp+ptr]; this
0x100aa03b  mov     esi, [ebp+clsid._hstring]
0x100aa03e  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100aa043  lea     eax, [ebp+ptr]
0x100aa046  push    eax
0x100aa047  push    offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x100aa04c  push    esi
0x100aa04d  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x100aa053  mov     esi, eax
0x100aa055  test    esi, esi
0x100aa057  js      short loc_100AA091
0x100aa059  mov     this, [ebp+ptr.ptr_]; ptr
0x100aa05c  lea     eax, [ebp+cookie]
0x100aa05f  push    eax; pcookie
0x100aa060  mov     edx, offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x100aa065  call    ?RegisterInterfaceInGlobal@@YGJPAUIUnknown@@ABU_GUID@@PAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x100aa06a  test    eax, eax
0x100aa06c  js      short loc_100AA083
0x100aa06e  mov     this, [ebp+cookie]
0x100aa071  xor     eax, eax
0x100aa073  lock cmpxchg [ebx], this
0x100aa077  test    eax, eax
0x100aa079  jz      short loc_100AA083
0x100aa07b  mov     this, [ebp+cookie]; cookie
0x100aa07e  call    ?RevokeInterfaceFromGlobal@@YGJK@Z; RevokeInterfaceFromGlobal(ulong)
0x100aa083  mov     eax, [ebp+ptr.ptr_]
0x100aa086  xor     esi, esi
0x100aa088  mov     [ebp+ptr.ptr_], 0
0x100aa08f  mov     [edi], eax
0x100aa091  lea     this, [ebp+ptr]; this
0x100aa094  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100aa099  mov     eax, esi
0x100aa09b  jmp     short loc_100AA0A8
0x100aa09d  push    edi; ppv
0x100aa09e  mov     edx, offset __GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858; iid
0x100aa0a3  call    ?GetInterfaceFromGlobal@@YGJKABU_GUID@@PAPAX@Z; GetInterfaceFromGlobal(ulong,_GUID const &,void * *)
0x100aa0a8  mov     this, [ebp+var_4]
0x100aa0ab  pop     edi
0x100aa0ac  pop     esi
0x100aa0ad  xor     this, ebp; cookie
0x100aa0af  pop     ebx
0x100aa0b0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100aa0b5  leave
0x100aa0b6  retn    4
```
