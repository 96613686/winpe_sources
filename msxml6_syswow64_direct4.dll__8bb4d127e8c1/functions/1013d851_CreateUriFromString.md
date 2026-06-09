# CreateUriFromString

- ea: `0x1013d851`
- end: `0x1013d910`
- name: `CreateUriFromString`
- size: `191`
- prototype: `HRESULT __userpurge@<eax>(const wchar_t *url@<ecx>, Windows::Foundation::IUriRuntimeClass **ppUri@<edx>)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1013d920`

## callees

- `0x10067b20`
- `0x1006b470`
- `0x10073ac9`
- `0x1013d851`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1013d893`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1013d893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d8b7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1013d8d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1013d8d2`

## string_xrefs

- `0x1013d874`: `Windows.Foundation.Uri`

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
0x1013d851  mov     edi, edi
0x1013d853  push    ebp
0x1013d854  mov     ebp, esp
0x1013d856  sub     esp, 3Ch
0x1013d859  mov     eax, ___security_cookie
0x1013d85e  xor     eax, ebp
0x1013d860  mov     [ebp+var_4], eax
0x1013d863  push    ebx
0x1013d864  push    esi
0x1013d865  push    edi
0x1013d866  lea     eax, [ebp+hstrActivableId]
0x1013d869  mov     edi, ppUri
0x1013d86b  push    eax; string
0x1013d86c  lea     eax, [ebp+hstrActivableId._header]
0x1013d86f  xor     ebx, ebx
0x1013d871  push    eax; hstringHeader
0x1013d872  push    16h; length
0x1013d874  push    offset ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1013d879  mov     esi, url
0x1013d87b  mov     [edi], ebx
0x1013d87d  mov     [ebp+spUriFac.ptr_], ebx
0x1013d880  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d886  test    eax, eax
0x1013d888  jns     short loc_1013D899
0x1013d88a  push    ebx; lpArguments
0x1013d88b  push    ebx; nNumberOfArguments
0x1013d88c  push    1; dwExceptionFlags
0x1013d88e  push    0C000000Dh; dwExceptionCode
0x1013d893  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x1013d899  mov     url, esi
0x1013d89b  lea     ppUri, [url+2]
0x1013d89e  mov     ax, [url]
0x1013d8a1  add     url, 2
0x1013d8a4  cmp     ax, bx
0x1013d8a7  jnz     short loc_1013D89E
0x1013d8a9  lea     eax, [ebp+hstrURL]
0x1013d8ac  sub     url, ppUri
0x1013d8ae  push    eax; string
0x1013d8af  lea     eax, [ebp+hstrURL._header]
0x1013d8b2  sar     url, 1
0x1013d8b4  push    eax; hstringHeader
0x1013d8b5  push    url; length
0x1013d8b6  push    esi; sourceString
0x1013d8b7  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d8bd  mov     esi, [ebp+hstrActivableId._hstring]
0x1013d8c0  lea     url, [ebp+spUriFac]; this
0x1013d8c3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d8c8  lea     eax, [ebp+spUriFac]
0x1013d8cb  push    eax
0x1013d8cc  push    offset __GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1013d8d1  push    esi
0x1013d8d2  call    ds:__imp__RoGetActivationFactory@12; RoGetActivationFactory(x,x,x)
0x1013d8d8  mov     esi, eax
0x1013d8da  test    esi, esi
0x1013d8dc  js      short loc_1013D8F7
0x1013d8de  mov     url, [ebp+spUriFac.ptr_]
0x1013d8e1  push    edi
0x1013d8e2  push    [ebp+hstrURL._hstring]
0x1013d8e5  mov     eax, [url]
0x1013d8e7  push    url
0x1013d8e8  mov     esi, [eax+18h]
0x1013d8eb  mov     url, esi; this
0x1013d8ed  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013d8f3  call    esi
0x1013d8f5  mov     esi, eax
0x1013d8f7  lea     url, [ebp+spUriFac]; this
0x1013d8fa  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d8ff  mov     url, [ebp+var_4]
0x1013d902  mov     eax, esi
0x1013d904  pop     edi
0x1013d905  pop     esi
0x1013d906  xor     url, ebp; cookie
0x1013d908  pop     ebx
0x1013d909  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1013d90e  leave
0x1013d90f  retn
```
