# CreateUriFromString

- ea: `0x18015bfec`
- end: `0x18015c0fb`
- name: `CreateUriFromString`
- size: `271`
- prototype: `__int64 __fastcall(const wchar_t *url, Windows::Foundation::IUriRuntimeClass **ppUri)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18015c110`

## callees

- `0x180071640`
- `0x1800730a4`
- `0x1800cada0`
- `0x18015bfec`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015c045`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015c077`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015c045`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015c077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015c02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015c08b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015c02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015c08b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015c0ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015c0ac`

## pseudocode

```c
__int64 __fastcall CreateUriFromString(const wchar_t *url, Windows::Foundation::IUriRuntimeClass **ppUri)
{
  unsigned __int64 v4; // rcx
  HSTRING__ *hstring; // rbx
  int ActivationFactory; // ebx
  unsigned int puResult; // [rsp+20h] [rbp-60h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> spUriFac; // [rsp+28h] [rbp-58h] BYREF
  Windows::Internal::StringReference hstrActivableId; // [rsp+30h] [rbp-50h] BYREF
  Windows::Internal::StringReference hstrURL; // [rsp+50h] [rbp-30h] BYREF

  *ppUri = 0;
  spUriFac.ptr_ = 0;
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Foundation_Uri,
         0x16u,
         &hstrActivableId._header,
         &hstrActivableId._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  puResult = 0;
  v4 = -1;
  do
    ++v4;
  while ( url[v4] );
  if ( ULongLongToUInt(v4, &puResult) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(url, puResult, &hstrURL._header, &hstrURL._hstring);
  hstring = hstrActivableId._hstring;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&spUriFac);
  ActivationFactory = RoGetActivationFactory(hstring, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &spUriFac);
  if ( ActivationFactory >= 0 )
    ActivationFactory = spUriFac.ptr_->CreateUri(spUriFac.ptr_, hstrURL._hstring, ppUri);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&spUriFac);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18015bfec  mov     [rsp-18h+arg_10], rbx
0x18015bff1  push    rbp
0x18015bff2  push    rsi
0x18015bff3  push    rdi
0x18015bff4  mov     rbp, rsp
0x18015bff7  sub     rsp, 80h
0x18015bffe  mov     rax, cs:__security_cookie
0x18015c005  xor     rax, rsp
0x18015c008  mov     [rbp+var_10], rax
0x18015c00c  xor     esi, esi
0x18015c00e  lea     r9, [rbp+hstrActivableId]; string
0x18015c012  mov     rdi, ppUri
0x18015c015  mov     [ppUri], rsi
0x18015c018  mov     rbx, url
0x18015c01b  mov     [rbp+spUriFac.ptr_], rsi
0x18015c01f  lea     r8, [rbp+hstrActivableId._header]; hstringHeader
0x18015c023  lea     edx, [rsi+16h]; length
0x18015c026  lea     url, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; sourceString
0x18015c02d  call    cs:__imp_WindowsCreateStringReference
0x18015c033  test    eax, eax
0x18015c035  jns     short loc_18015C04B
0x18015c037  xor     r9d, r9d; lpArguments
0x18015c03a  lea     edx, [rsi+1]; dwExceptionFlags
0x18015c03d  xor     r8d, r8d; nNumberOfArguments
0x18015c040  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015c045  call    cs:__imp_RaiseException
0x18015c04b  mov     [rbp+puResult], esi
0x18015c04e  or      url, 0FFFFFFFFFFFFFFFFh
0x18015c052  inc     url; ullOperand
0x18015c055  cmp     [rbx+url*2], si
0x18015c059  jnz     short loc_18015C052
0x18015c05b  lea     ppUri, [rbp+puResult]; puResult
0x18015c05f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18015c064  test    eax, eax
0x18015c066  jns     short loc_18015C07D
0x18015c068  xor     r9d, r9d; lpArguments
0x18015c06b  xor     r8d, r8d; nNumberOfArguments
0x18015c06e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015c073  lea     edx, [r9+1]; dwExceptionFlags
0x18015c077  call    cs:__imp_RaiseException
0x18015c07d  mov     edx, [rbp+puResult]; length
0x18015c080  lea     r9, [rbp+hstrURL]; string
0x18015c084  lea     r8, [rbp+hstrURL._header]; hstringHeader
0x18015c088  mov     url, rbx; sourceString
0x18015c08b  call    cs:__imp_WindowsCreateStringReference
0x18015c091  mov     rbx, [rbp+hstrActivableId._hstring]
0x18015c095  lea     url, [rbp+spUriFac]; this
0x18015c099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015c09e  lea     r8, [rbp+spUriFac]
0x18015c0a2  mov     url, rbx
0x18015c0a5  lea     ppUri, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18015c0ac  call    cs:__imp_RoGetActivationFactory
0x18015c0b2  mov     ebx, eax
0x18015c0b4  test    eax, eax
0x18015c0b6  js      short loc_18015C0D1
0x18015c0b8  mov     url, [rbp+spUriFac.ptr_]
0x18015c0bc  mov     r8, rdi
0x18015c0bf  mov     ppUri, [rbp+hstrURL._hstring]
0x18015c0c3  mov     rax, [url]
0x18015c0c6  mov     rax, [rax+30h]
0x18015c0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c0cf  mov     ebx, eax
0x18015c0d1  lea     url, [rbp+spUriFac]; this
0x18015c0d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015c0da  mov     eax, ebx
0x18015c0dc  mov     url, [rbp+var_10]
0x18015c0e0  xor     url, rsp; StackCookie
0x18015c0e3  call    __security_check_cookie
0x18015c0e8  mov     rbx, [rsp+80h+arg_10]
0x18015c0f0  add     rsp, 80h
0x18015c0f7  pop     rdi
0x18015c0f8  pop     rsi
0x18015c0f9  pop     rbp
0x18015c0fa  retn
```
