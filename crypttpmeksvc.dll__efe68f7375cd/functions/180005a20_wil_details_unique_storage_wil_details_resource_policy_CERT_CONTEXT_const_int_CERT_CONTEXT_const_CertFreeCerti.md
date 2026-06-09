# wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)

- ea: `0x180005a20`
- end: `0x180005a78`
- name: `?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z`
- size: `88`
- prototype: `void __fastcall(const CERT_CONTEXT **, const CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002310`
- `0x180005998`

## callees

- `0x180005a20`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180005a4d`
- `CRYPT32!CertFreeCertificateContext` at `0x180005a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a55`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
        const CERT_CONTEXT **a1,
        const CERT_CONTEXT *a2)
{
  const CERT_CONTEXT *v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CertFreeCertificateContext(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x180005a20  mov     [rsp+arg_8], rbx
0x180005a25  mov     [rsp+arg_10], rbp
0x180005a2a  push    rsi
0x180005a2b  sub     rsp, 20h
0x180005a2f  mov     rbp, [rcx]
0x180005a32  mov     rsi, rdx
0x180005a35  mov     rbx, rcx
0x180005a38  test    rbp, rbp
0x180005a3b  jz      short loc_180005A65
0x180005a3d  mov     [rsp+28h+arg_0], rdi
0x180005a42  call    cs:__imp_GetLastError
0x180005a48  mov     rcx, rbp; pCertContext
0x180005a4b  mov     edi, eax
0x180005a4d  call    cs:__imp_CertFreeCertificateContext
0x180005a53  mov     ecx, edi; dwErrCode
0x180005a55  call    cs:__imp_SetLastError
0x180005a5b  mov     rdi, [rsp+28h+arg_0]
0x180005a60  mov     [rbx], rsi
0x180005a63  jmp     short loc_180005A68
0x180005a65  mov     [rcx], rsi
0x180005a68  mov     rbx, [rsp+28h+arg_8]
0x180005a6d  mov     rbp, [rsp+28h+arg_10]
0x180005a72  add     rsp, 20h
0x180005a76  pop     rsi
0x180005a77  retn
```
