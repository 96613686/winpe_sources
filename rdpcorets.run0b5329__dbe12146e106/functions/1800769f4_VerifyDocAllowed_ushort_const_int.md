# VerifyDocAllowed(ushort const *,int *)

- ea: `0x1800769f4`
- end: `0x180076c34`
- name: `?VerifyDocAllowed@@YAJPEBGPEAH@Z`
- size: `576`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180076d08`

## callees

- `0x180032110`
- `0x180033da0`
- `0x1800769f4`
- `0x180076c3c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076beb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076beb`
- `RDPBASE!TRC_TraceBufferW` at `0x180076b4f`
- `RDPBASE!TRC_TraceBufferW` at `0x180076bdb`
- `RDPBASE!TRC_TraceBufferW` at `0x180076b4f`
- `RDPBASE!TRC_TraceBufferW` at `0x180076bdb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180076a5f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180076a5f`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180076a40`
- `api-ms-win-core-url-l1-1-0!UrlIsW` at `0x180076a40`
- `SHELL32!SHCreateAssociationRegistration` at `0x180076a87`
- `SHELL32!SHCreateAssociationRegistration` at `0x180076a87`
- `SHLWAPI!AssocQueryStringW` at `0x180076b0e`
- `SHLWAPI!AssocQueryStringW` at `0x180076b0e`

## string_xrefs

- `0x180076a9d`: `SHCreateAssociationRegistration failed: 0x%x`
- `0x180076b9d`: `PathFindExtension could not find a valid extension on the doc: %s`
- `0x180076b94`: `VerifyRealAppAllowedFromRegistry hr[0x%x]`

## pseudocode

```c
__int64 __fastcall VerifyDocAllowed(LPCWSTR pszPath, int *a2)
{
  const wchar_t *v4; // rax
  __int64 v5; // r8
  LPWSTR ExtensionW; // rax
  LPWSTR v7; // rdi
  HRESULT v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  HRESULT v13; // [rsp+38h] [rbp-C8h]
  int v14; // [rsp+38h] [rbp-C8h]
  int v15; // [rsp+38h] [rbp-C8h]
  LPCWSTR pszAssoc; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchOut; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcchOut = 260;
  *a2 = 0;
  ppv = 0;
  pszAssoc = 0;
  if ( UrlIsW(pszPath, URLIS_URL) )
  {
    v4 = L"%s is a URL, not a document";
    v5 = 456;
LABEL_15:
    v9 = -2147024809;
    TRC_TraceBufferW(
      3,
      4096,
      v5,
      L"VerifyDocAllowed",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      v4,
      pszPath);
    goto LABEL_16;
  }
  ExtensionW = PathFindExtensionW(pszPath);
  v7 = ExtensionW;
  if ( !ExtensionW || !*ExtensionW )
  {
    v4 = L"PathFindExtension could not find a valid extension on the doc: %s";
    v5 = 464;
    goto LABEL_15;
  }
  v8 = SHCreateAssociationRegistration(&GUID_4e530b0a_e611_4c77_a3ac_9031d022281b, &ppv);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, LPWSTR, _QWORD, _QWORD, LPCWSTR *))(*(_QWORD *)ppv + 24LL))(
            ppv,
            v7,
            0,
            0,
            &pszAssoc);
    v9 = v10;
    if ( v10 >= 0 )
    {
      if ( AssocQueryStringW(0x430u, ASSOCSTR_EXECUTABLE, pszAssoc, 0, String2, &pcchOut) >= 0 )
      {
        v9 = VerifyRealAppAllowedFromLRPC(String2, 0, 0, a2);
        if ( v9 < 0 )
        {
          v11 = VerifyRealAppAllowedFromRegistry(String2, 0, 0, a2);
          v9 = v11;
          if ( v11 < 0 )
          {
            v15 = v11;
            TRC_TraceBufferW(
              3,
              4096,
              508,
              L"VerifyDocAllowed",
              L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
              0,
              L"VerifyRealAppAllowedFromRegistry hr[0x%x]",
              v15);
          }
        }
      }
      else
      {
        v9 = 0;
        TRC_TraceBufferW(
          3,
          4096,
          497,
          L"VerifyDocAllowed",
          L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
          0,
          L"AssocQueryString failed.  Not an error");
      }
    }
    else
    {
      v14 = v10;
      TRC_TraceBufferW(
        3,
        4096,
        480,
        L"VerifyDocAllowed",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"IApplicationAssociationRegistration::QueryCurrentDefault failed: 0x%x",
        v14);
    }
  }
  else
  {
    v13 = v8;
    TRC_TraceBufferW(
      3,
      4096,
      473,
      L"VerifyDocAllowed",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      L"SHCreateAssociationRegistration failed: 0x%x",
      v13);
  }
LABEL_16:
  if ( pszAssoc )
  {
    CoTaskMemFree((LPVOID)pszAssoc);
    pszAssoc = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800769f4  mov     [rsp-8+arg_10], rbx
0x1800769f9  push    rbp
0x1800769fa  push    rsi
0x1800769fb  push    rdi
0x1800769fc  push    r14
0x1800769fe  push    r15
0x180076a00  lea     rbp, [rsp-180h]
0x180076a08  sub     rsp, 280h
0x180076a0f  mov     rax, cs:__security_cookie
0x180076a16  xor     rax, rsp
0x180076a19  mov     [rbp+1A0h+var_30], rax
0x180076a20  xor     r15d, r15d
0x180076a23  mov     [rsp+2A0h+var_258], 104h
0x180076a2b  mov     [rdx], r15d
0x180076a2e  mov     r14, rdx
0x180076a31  xor     edx, edx; UrlIs
0x180076a33  mov     [rsp+2A0h+ppv], r15
0x180076a38  mov     rsi, rcx
0x180076a3b  mov     [rsp+2A0h+pszAssoc], r15
0x180076a40  call    cs:__imp_UrlIsW
0x180076a46  test    eax, eax
0x180076a48  jz      short loc_180076A5C
0x180076a4a  lea     rax, aSIsAUrlNotADoc; "%s is a URL, not a document"
0x180076a51  mov     r8d, 1C8h
0x180076a57  jmp     loc_180076BAA
0x180076a5c  mov     rcx, rsi; pszPath
0x180076a5f  call    cs:__imp_PathFindExtensionW
0x180076a65  mov     rdi, rax
0x180076a68  test    rax, rax
0x180076a6b  jz      loc_180076B9D
0x180076a71  cmp     [rax], r15w
0x180076a75  jz      loc_180076B9D
0x180076a7b  lea     rdx, [rsp+2A0h+ppv]; ppv
0x180076a80  lea     rcx, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x180076a87  call    cs:__imp_SHCreateAssociationRegistration
0x180076a8d  mov     ebx, eax
0x180076a8f  test    eax, eax
0x180076a91  jns     short loc_180076AA9
0x180076a93  mov     dword ptr [rsp+2A0h+var_268], eax
0x180076a97  mov     r8d, 1D9h
0x180076a9d  lea     rax, aShcreateassoci_0; "SHCreateAssociationRegistration failed:"...
0x180076aa4  jmp     loc_180076BB4
0x180076aa9  mov     rcx, [rsp+2A0h+ppv]
0x180076aae  lea     rdx, [rsp+2A0h+pszAssoc]
0x180076ab3  mov     [rsp+2A0h+pszOut], rdx
0x180076ab8  xor     r9d, r9d
0x180076abb  xor     r8d, r8d
0x180076abe  mov     rdx, rdi
0x180076ac1  mov     rax, [rcx]
0x180076ac4  mov     rax, [rax+18h]
0x180076ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076acd  mov     ebx, eax
0x180076acf  test    eax, eax
0x180076ad1  jns     short loc_180076AE9
0x180076ad3  mov     dword ptr [rsp+2A0h+var_268], eax
0x180076ad7  mov     r8d, 1E0h
0x180076add  lea     rax, aIapplicationas; "IApplicationAssociationRegistration::Qu"...
0x180076ae4  jmp     loc_180076BB4
0x180076ae9  mov     r8, [rsp+2A0h+pszAssoc]; pszAssoc
0x180076aee  lea     rax, [rsp+2A0h+var_258]
0x180076af3  mov     [rsp+2A0h+pcchOut], rax; pcchOut
0x180076af8  xor     r9d, r9d; pszExtra
0x180076afb  lea     rax, [rsp+2A0h+String2]
0x180076b00  mov     ecx, 430h; flags
0x180076b05  mov     [rsp+2A0h+pszOut], rax; pszOut
0x180076b0a  lea     edx, [r9+2]; str
0x180076b0e  call    cs:__imp_AssocQueryStringW
0x180076b14  test    eax, eax
0x180076b16  jns     short loc_180076B5A
0x180076b18  lea     rax, aAssocquerystri_0; "AssocQueryString failed.  Not an error"
0x180076b1f  mov     edx, 1000h
0x180076b24  mov     [rsp+2A0h+var_270], rax
0x180076b29  lea     r9, aVerifydocallow; "VerifyDocAllowed"
0x180076b30  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076b37  mov     [rsp+2A0h+pcchOut], r15
0x180076b3c  mov     ecx, 3
0x180076b41  mov     [rsp+2A0h+pszOut], rax
0x180076b46  mov     r8d, 1F1h
0x180076b4c  mov     ebx, r15d
0x180076b4f  call    cs:__imp_TRC_TraceBufferW
0x180076b55  jmp     loc_180076BE1
0x180076b5a  mov     r9, r14; int *
0x180076b5d  lea     rcx, [rsp+2A0h+String2]; unsigned __int16 *
0x180076b62  xor     r8d, r8d; int
0x180076b65  xor     edx, edx; unsigned __int16 *
0x180076b67  call    ?VerifyRealAppAllowedFromLRPC@@YAJPEBG0HPEAH@Z; VerifyRealAppAllowedFromLRPC(ushort const *,ushort const *,int,int *)
0x180076b6c  mov     ebx, eax
0x180076b6e  test    eax, eax
0x180076b70  jns     short loc_180076BE1
0x180076b72  mov     r9, r14; int *
0x180076b75  lea     rcx, [rsp+2A0h+String2]; lpString2
0x180076b7a  xor     r8d, r8d; int
0x180076b7d  xor     edx, edx; unsigned __int16 *
0x180076b7f  call    ?VerifyRealAppAllowedFromRegistry@@YAJPEBG0HPEAH@Z; VerifyRealAppAllowedFromRegistry(ushort const *,ushort const *,int,int *)
0x180076b84  mov     ebx, eax
0x180076b86  test    eax, eax
0x180076b88  jns     short loc_180076BE1
0x180076b8a  mov     dword ptr [rsp+2A0h+var_268], eax
0x180076b8e  mov     r8d, 1FCh
0x180076b94  lea     rax, aVerifyrealappa_1; "VerifyRealAppAllowedFromRegistry hr[0x%"...
0x180076b9b  jmp     short loc_180076BB4
0x180076b9d  lea     rax, aPathfindextens; "PathFindExtension could not find a vali"...
0x180076ba4  mov     r8d, 1D0h
0x180076baa  mov     [rsp+2A0h+var_268], rsi
0x180076baf  mov     ebx, 80070057h
0x180076bb4  mov     [rsp+2A0h+var_270], rax
0x180076bb9  lea     r9, aVerifydocallow; "VerifyDocAllowed"
0x180076bc0  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x180076bc7  mov     [rsp+2A0h+pcchOut], r15
0x180076bcc  mov     edx, 1000h
0x180076bd1  mov     [rsp+2A0h+pszOut], rax
0x180076bd6  mov     ecx, 3
0x180076bdb  call    cs:__imp_TRC_TraceBufferW
0x180076be1  mov     rcx, [rsp+2A0h+pszAssoc]; pv
0x180076be6  test    rcx, rcx
0x180076be9  jz      short loc_180076BF6
0x180076beb  call    cs:__imp_CoTaskMemFree
0x180076bf1  mov     [rsp+2A0h+pszAssoc], r15
0x180076bf6  mov     rcx, [rsp+2A0h+ppv]
0x180076bfb  test    rcx, rcx
0x180076bfe  jz      short loc_180076C0C
0x180076c00  mov     rax, [rcx]
0x180076c03  mov     rax, [rax+10h]
0x180076c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c0c  mov     eax, ebx
0x180076c0e  mov     rcx, [rbp+1A0h+var_30]
0x180076c15  xor     rcx, rsp; StackCookie
0x180076c18  call    __security_check_cookie
0x180076c1d  mov     rbx, [rsp+2A0h+arg_10]
0x180076c25  add     rsp, 280h
0x180076c2c  pop     r15
0x180076c2e  pop     r14
0x180076c30  pop     rdi
0x180076c31  pop     rsi
0x180076c32  pop     rbp
0x180076c33  retn
```
