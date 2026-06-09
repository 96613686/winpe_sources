# Ssl::ImportCertificate(void * *,std::vector<uchar,std::allocator<uchar>> const &,_CERT_CONTEXT const * &)

- ea: `0x10042d708`
- end: `0x10042d8af`
- name: `?ImportCertificate@Ssl@@CAKPEAPEAXAEBV?$vector@EV?$allocator@E@std@@@std@@AEAPEBU_CERT_CONTEXT@@@Z`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10042d8b8`
- `0x10042f68c`

## callees

- `0x10042b1cc`
- `0x10042d708`
- `0x100545d84`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042d820`
- `KERNEL32!GetLastError` at `0x10042d820`
- `CRYPT32!CertOpenStore` at `0x10042d7ed`
- `CRYPT32!CertOpenStore` at `0x10042d7ed`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10042d816`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x10042d816`
- `VCRUNTIME140!strstr` at `0x10042d7a1`
- `VCRUNTIME140!strstr` at `0x10042d7a1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10042d862`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10042d862`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Ssl::ImportCertificate(_QWORD *a1, __int64 a2, PCCERT_CONTEXT *a3)
{
  DWORD LastError; // ebx
  LPCSTR v7; // rdi
  __int64 v8; // rbx
  DWORD v9; // ebx
  HCERTSTORE v10; // rax
  __int64 v12; // [rsp+88h] [rbp+28h] BYREF

  v12 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7BC8[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v12,
      off_1005E7BC8[0],
      0);
  if ( strstr(*(const char **)a2, "-----BEGIN") )
  {
    LastError = Ssl::ConvertBase64StringToBinaryBlob(*(LPCSTR *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
    if ( LastError )
      goto LABEL_13;
    v7 = 0;
    LODWORD(v8) = 0;
  }
  else
  {
    v7 = *(LPCSTR *)a2;
    v8 = *(_QWORD *)(a2 + 8);
  }
  v9 = v8 - (_DWORD)v7;
  v10 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *a1 = v10;
  if ( v10 && CertAddEncodedCertificateToStore(v10, 0x10001u, (const BYTE *)v7, v9, 3u, a3) )
    LastError = 0;
  else
    LastError = GetLastError();
LABEL_13:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v12);
  return LastError;
}

```

## disassembly

```asm
0x10042d708  mov     r11, rsp
0x10042d70b  push    rbp
0x10042d70c  push    rdi
0x10042d70d  push    r14
0x10042d70f  mov     rbp, rsp
0x10042d712  sub     rsp, 60h
0x10042d716  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x10042d71e  mov     [r11+8], rbx
0x10042d722  mov     [r11+18h], rsi
0x10042d726  mov     r14, r8
0x10042d729  mov     rbx, rdx
0x10042d72c  mov     rsi, rcx
0x10042d72f  or      [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x10042d734  mov     eax, cs:_bidGblFlags
0x10042d73a  mov     ecx, 20004h
0x10042d73f  and     eax, ecx
0x10042d741  cmp     eax, ecx
0x10042d743  jnz     short loc_10042D788
0x10042d745  mov     rax, cs:off_1005E7BC8; "<Ssl::ImportCertificate|API|SNI> \n"
0x10042d74c  test    rax, rax
0x10042d74f  jz      short loc_10042D788
0x10042d751  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10042d759  jz      short loc_10042D788
0x10042d75b  mov     rax, cs:off_1005D39F0
0x10042d762  and     qword ptr [r11-50h], 0
0x10042d767  mov     rcx, cs:off_1005E7BC8; "<Ssl::ImportCertificate|API|SNI> \n"
0x10042d76e  mov     [r11-58h], rcx
0x10042d772  lea     r9, [rbp+arg_8]
0x10042d776  xor     r8d, r8d
0x10042d779  xor     edx, edx
0x10042d77b  mov     rcx, cs:_bidID
0x10042d782  call    cs:__guard_dispatch_icall_fptr
0x10042d788  and     [rbp+pbCertEncoded], 0
0x10042d78d  and     [rbp+pbCertEncoded+8], 0
0x10042d792  and     [rbp+var_8], 0
0x10042d797  lea     rdx, SubStr; "-----BEGIN"
0x10042d79e  mov     rcx, [rbx]; Str
0x10042d7a1  call    cs:__imp_strstr
0x10042d7a7  test    rax, rax
0x10042d7aa  jz      short loc_10042D7D2
0x10042d7ac  mov     rdx, [rbx+8]
0x10042d7b0  sub     rdx, [rbx]; cchString
0x10042d7b3  lea     r9, [rbp+pbCertEncoded]
0x10042d7b7  mov     r8b, 1
0x10042d7ba  mov     rcx, [rbx]; pszString
0x10042d7bd  call    ?ConvertBase64StringToBinaryBlob@Ssl@@CAKPEBEK_NAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Ssl::ConvertBase64StringToBinaryBlob(uchar const *,ulong,bool,std::vector<uchar> &)
0x10042d7c2  mov     ebx, eax
0x10042d7c4  test    eax, eax
0x10042d7c6  jnz     short loc_10042D82C
0x10042d7c8  mov     rdi, [rbp+pbCertEncoded]
0x10042d7cc  mov     rbx, [rbp+pbCertEncoded+8]
0x10042d7d0  jmp     short loc_10042D7D9
0x10042d7d2  mov     rdi, [rbx]
0x10042d7d5  mov     rbx, [rbx+8]
0x10042d7d9  sub     rbx, rdi
0x10042d7dc  and     qword ptr [rsp+60h+dwAddDisposition], 0
0x10042d7e2  xor     r9d, r9d; dwFlags
0x10042d7e5  xor     r8d, r8d; hCryptProv
0x10042d7e8  xor     edx, edx; dwEncodingType
0x10042d7ea  lea     ecx, [rdx+2]; lpszStoreProvider
0x10042d7ed  call    cs:__imp_CertOpenStore
0x10042d7f3  mov     [rsi], rax
0x10042d7f6  test    rax, rax
0x10042d7f9  jz      short loc_10042D820
0x10042d7fb  mov     [rsp+60h+ppCertContext], r14; ppCertContext
0x10042d800  mov     [rsp+60h+dwAddDisposition], 3; dwAddDisposition
0x10042d808  mov     r9d, ebx; cbCertEncoded
0x10042d80b  mov     r8, rdi; pbCertEncoded
0x10042d80e  mov     edx, 10001h; dwCertEncodingType
0x10042d813  mov     rcx, rax; hCertStore
0x10042d816  call    cs:__imp_CertAddEncodedCertificateToStore
0x10042d81c  test    eax, eax
0x10042d81e  jnz     short loc_10042D82A
0x10042d820  call    cs:__imp_GetLastError
0x10042d826  mov     ebx, eax
0x10042d828  jmp     short loc_10042D82C
0x10042d82a  xor     ebx, ebx
0x10042d82c  mov     rdx, [rbp+pbCertEncoded]
0x10042d830  test    rdx, rdx
0x10042d833  jz      short loc_10042D88F
0x10042d835  mov     rax, [rbp+var_8]
0x10042d839  sub     rax, rdx
0x10042d83c  mov     rcx, rdx
0x10042d83f  cmp     rax, 1000h
0x10042d845  jb      short loc_10042D869
0x10042d847  test    cl, 1Fh
0x10042d84a  jnz     short loc_10042D862
0x10042d84c  mov     rdx, [rdx-8]
0x10042d850  cmp     rdx, rcx
0x10042d853  jnb     short loc_10042D862
0x10042d855  sub     rcx, rdx
0x10042d858  sub     rcx, 8
0x10042d85c  cmp     rcx, 1Fh
0x10042d860  jbe     short loc_10042D869
0x10042d862  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x10042d869  test    rdx, rdx
0x10042d86c  jz      short loc_10042D882
0x10042d86e  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10042d875  mov     rax, [rcx]
0x10042d878  mov     rax, [rax+68h]
0x10042d87c  call    cs:__guard_dispatch_icall_fptr
0x10042d882  xorps   xmm0, xmm0
0x10042d885  movdqu  xmmword ptr [rbp+pbCertEncoded], xmm0
0x10042d88a  and     [rbp+var_8], 0
0x10042d88f  lea     rcx, [rbp+arg_8]; this
0x10042d893  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042d898  mov     eax, ebx
0x10042d89a  lea     r11, [rsp+60h+var_s0]
0x10042d89f  mov     rbx, [r11+20h]
0x10042d8a3  mov     rsi, [r11+30h]
0x10042d8a7  mov     rsp, r11
0x10042d8aa  pop     r14
0x10042d8ac  pop     rdi
0x10042d8ad  pop     rbp
0x10042d8ae  retn
```
