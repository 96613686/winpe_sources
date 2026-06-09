# CreateUriFromString

- ea: `0x18015f828`
- end: `0x18015f956`
- name: `CreateUriFromString`
- size: `302`
- prototype: `HRESULT __fastcall(const wchar_t *url, Windows::Foundation::IUriRuntimeClass **ppUri)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18015f960`

## callees

- `0x18006f2d4`
- `0x1800719e4`
- `0x1800cc6c0`
- `0x18015f828`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f887`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f8bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f887`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f8d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015f900`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18015f900`

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
0x18015f828  mov     [rsp-18h+arg_10], rbx
0x18015f82d  push    rbp
0x18015f82e  push    rsi
0x18015f82f  push    rdi
0x18015f830  mov     rbp, rsp
0x18015f833  sub     rsp, 80h
0x18015f83a  mov     rax, cs:__security_cookie
0x18015f841  xor     rax, rsp
0x18015f844  mov     [rbp+var_10], rax
0x18015f848  xor     esi, esi
0x18015f84a  lea     r9, [rbp+hstrActivableId]; string
0x18015f84e  mov     rdi, ppUri
0x18015f851  mov     [ppUri], rsi
0x18015f854  mov     rbx, url
0x18015f857  mov     [rbp+spUriFac.ptr_], rsi
0x18015f85b  lea     r8, [rbp+hstrActivableId._header]; hstringHeader
0x18015f85f  lea     edx, [rsi+16h]; length
0x18015f862  lea     url, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; sourceString
0x18015f869  call    cs:__imp_WindowsCreateStringReference
0x18015f870  nop     dword ptr [rax+rax+00h]
0x18015f875  test    eax, eax
0x18015f877  jns     short loc_18015F893
0x18015f879  xor     r9d, r9d; lpArguments
0x18015f87c  lea     edx, [rsi+1]; dwExceptionFlags
0x18015f87f  xor     r8d, r8d; nNumberOfArguments
0x18015f882  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015f887  call    cs:__imp_RaiseException
0x18015f88e  nop     dword ptr [rax+rax+00h]
0x18015f893  mov     [rbp+puResult], esi
0x18015f896  or      url, 0FFFFFFFFFFFFFFFFh
0x18015f89a  inc     url; ullOperand
0x18015f89d  cmp     [rbx+url*2], si
0x18015f8a1  jnz     short loc_18015F89A
0x18015f8a3  lea     ppUri, [rbp+puResult]; puResult
0x18015f8a7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18015f8ac  test    eax, eax
0x18015f8ae  jns     short loc_18015F8CB
0x18015f8b0  xor     r9d, r9d; lpArguments
0x18015f8b3  xor     r8d, r8d; nNumberOfArguments
0x18015f8b6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015f8bb  lea     edx, [r9+1]; dwExceptionFlags
0x18015f8bf  call    cs:__imp_RaiseException
0x18015f8c6  nop     dword ptr [rax+rax+00h]
0x18015f8cb  mov     edx, [rbp+puResult]; length
0x18015f8ce  lea     r9, [rbp+hstrURL]; string
0x18015f8d2  lea     r8, [rbp+hstrURL._header]; hstringHeader
0x18015f8d6  mov     url, rbx; sourceString
0x18015f8d9  call    cs:__imp_WindowsCreateStringReference
0x18015f8e0  nop     dword ptr [rax+rax+00h]
0x18015f8e5  mov     rbx, [rbp+hstrActivableId._hstring]
0x18015f8e9  lea     url, [rbp+spUriFac]; this
0x18015f8ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f8f2  lea     r8, [rbp+spUriFac]
0x18015f8f6  mov     url, rbx
0x18015f8f9  lea     ppUri, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18015f900  call    cs:__imp_RoGetActivationFactory
0x18015f907  nop     dword ptr [rax+rax+00h]
0x18015f90c  mov     ebx, eax
0x18015f90e  test    eax, eax
0x18015f910  js      short loc_18015F92B
0x18015f912  mov     url, [rbp+spUriFac.ptr_]
0x18015f916  mov     r8, rdi
0x18015f919  mov     ppUri, [rbp+hstrURL._hstring]
0x18015f91d  mov     rax, [url]
0x18015f920  mov     rax, [rax+30h]
0x18015f924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f929  mov     ebx, eax
0x18015f92b  lea     url, [rbp+spUriFac]; this
0x18015f92f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f934  mov     eax, ebx
0x18015f936  mov     url, [rbp+var_10]
0x18015f93a  xor     url, rsp; StackCookie
0x18015f93d  call    __security_check_cookie
0x18015f942  mov     rbx, [rsp+80h+arg_10]
0x18015f94a  add     rsp, 80h
0x18015f951  pop     rdi
0x18015f952  pop     rsi
0x18015f953  pop     rbp
0x18015f954  retn
```
