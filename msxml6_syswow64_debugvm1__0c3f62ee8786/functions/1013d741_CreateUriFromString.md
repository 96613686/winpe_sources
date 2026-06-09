# CreateUriFromString

- ea: `0x1013d741`
- end: `0x1013d800`
- name: `CreateUriFromString`
- size: `191`
- prototype: `HRESULT __userpurge@<eax>(const wchar_t *url@<ecx>, Windows::Foundation::IUriRuntimeClass **ppUri@<edx>)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1013d810`

## callees

- `0x10067bc0`
- `0x1006b510`
- `0x10073a99`
- `0x1013d741`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1013d783`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1013d783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d7a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d7a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1013d7c2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1013d7c2`

## string_xrefs

- `0x1013d764`: `Windows.Foundation.Uri`

## pseudocode

```c
HRESULT __fastcall CreateUriFromString(const wchar_t *url, Windows::Foundation::IUriRuntimeClass **ppUri)
{
  HSTRING__ *hstring; // esi
  int ActivationFactory; // esi
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> spUriFac; // [esp+10h] [ebp-38h] BYREF
  Windows::Internal::StringReference hstrURL; // [esp+14h] [ebp-34h] BYREF
  Windows::Internal::StringReference hstrActivableId; // [esp+2Ch] [ebp-1Ch] BYREF

  *ppUri = 0;
  spUriFac.ptr_ = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Uri",
         0x16u,
         &hstrActivableId._header,
         &hstrActivableId._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(url, wcslen(url), &hstrURL._header, &hstrURL._hstring);
  hstring = hstrActivableId._hstring;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(&spUriFac);
  ActivationFactory = RoGetActivationFactory(hstring, &_GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &spUriFac);
  if ( ActivationFactory >= 0 )
    ActivationFactory = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::IUriRuntimeClassFactory *, HSTRING__ *, Windows::Foundation::IUriRuntimeClass **), Windows::Foundation::IUriRuntimeClassFactory *, HSTRING__ *, Windows::Foundation::IUriRuntimeClass **))spUriFac.ptr_->CreateUri)(
                          spUriFac.ptr_->CreateUri,
                          spUriFac.ptr_,
                          hstrURL._hstring,
                          ppUri);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(&spUriFac);
  return ActivationFactory;
}

```

## disassembly

```asm
0x1013d741  mov     edi, edi
0x1013d743  push    ebp
0x1013d744  mov     ebp, esp
0x1013d746  sub     esp, 3Ch
0x1013d749  mov     eax, ___security_cookie
0x1013d74e  xor     eax, ebp
0x1013d750  mov     [ebp+var_4], eax
0x1013d753  push    ebx
0x1013d754  push    esi
0x1013d755  push    edi
0x1013d756  lea     eax, [ebp+hstrActivableId]
0x1013d759  mov     edi, ppUri
0x1013d75b  push    eax; string
0x1013d75c  lea     eax, [ebp+hstrActivableId._header]
0x1013d75f  xor     ebx, ebx
0x1013d761  push    eax; hstringHeader
0x1013d762  push    16h; length
0x1013d764  push    offset ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1013d769  mov     esi, url
0x1013d76b  mov     [edi], ebx
0x1013d76d  mov     [ebp+spUriFac.ptr_], ebx
0x1013d770  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d776  test    eax, eax
0x1013d778  jns     short loc_1013D789
0x1013d77a  push    ebx; lpArguments
0x1013d77b  push    ebx; nNumberOfArguments
0x1013d77c  push    1; dwExceptionFlags
0x1013d77e  push    0C000000Dh; dwExceptionCode
0x1013d783  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x1013d789  mov     url, esi
0x1013d78b  lea     ppUri, [url+2]
0x1013d78e  mov     ax, [url]
0x1013d791  add     url, 2
0x1013d794  cmp     ax, bx
0x1013d797  jnz     short loc_1013D78E
0x1013d799  lea     eax, [ebp+hstrURL]
0x1013d79c  sub     url, ppUri
0x1013d79e  push    eax; string
0x1013d79f  lea     eax, [ebp+hstrURL._header]
0x1013d7a2  sar     url, 1
0x1013d7a4  push    eax; hstringHeader
0x1013d7a5  push    url; length
0x1013d7a6  push    esi; sourceString
0x1013d7a7  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d7ad  mov     esi, [ebp+hstrActivableId._hstring]
0x1013d7b0  lea     url, [ebp+spUriFac]; this
0x1013d7b3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d7b8  lea     eax, [ebp+spUriFac]
0x1013d7bb  push    eax
0x1013d7bc  push    offset __GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1013d7c1  push    esi
0x1013d7c2  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x1013d7c8  mov     esi, eax
0x1013d7ca  test    esi, esi
0x1013d7cc  js      short loc_1013D7E7
0x1013d7ce  mov     url, [ebp+spUriFac.ptr_]
0x1013d7d1  push    edi
0x1013d7d2  push    [ebp+hstrURL._hstring]
0x1013d7d5  mov     eax, [url]
0x1013d7d7  push    url
0x1013d7d8  mov     esi, [eax+18h]
0x1013d7db  mov     url, esi; this
0x1013d7dd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013d7e3  call    esi
0x1013d7e5  mov     esi, eax
0x1013d7e7  lea     url, [ebp+spUriFac]; this
0x1013d7ea  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d7ef  mov     url, [ebp+var_4]
0x1013d7f2  mov     eax, esi
0x1013d7f4  pop     edi
0x1013d7f5  pop     esi
0x1013d7f6  xor     url, ebp; cookie
0x1013d7f8  pop     ebx
0x1013d7f9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1013d7fe  leave
0x1013d7ff  retn
```
