# s_SSRecoverImportRecoveryKey

- ea: `0x180038a00`
- end: `0x180038d31`
- name: `s_SSRecoverImportRecoveryKey`
- size: `817`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007f10`
- `0x18001c9c0`
- `0x18001d810`
- `0x180036dc0`
- `0x180037a5c`
- `0x180038094`
- `0x180038a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038c60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180038b10`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180038b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038cfa`
- `ntdll!RtlInitUnicodeString` at `0x180038b60`
- `ntdll!RtlInitUnicodeString` at `0x180038b73`
- `ntdll!RtlInitUnicodeString` at `0x180038b86`
- `ntdll!RtlInitUnicodeString` at `0x180038b60`
- `ntdll!RtlInitUnicodeString` at `0x180038b73`
- `ntdll!RtlInitUnicodeString` at `0x180038b86`
- `CRYPT32!CertCreateCertificateContext` at `0x180038bbe`
- `CRYPT32!CertCreateCertificateContext` at `0x180038bbe`
- `CRYPT32!CertFreeCertificateContext` at `0x180038cbb`
- `CRYPT32!CertFreeCertificateContext` at `0x180038cbb`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180038c50`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180038c50`
- `CRYPT32!CertCloseStore` at `0x180038cac`
- `CRYPT32!CertCloseStore` at `0x180038cac`
- `CRYPT32!CertOpenStore` at `0x180038c04`
- `CRYPT32!CertOpenStore` at `0x180038c04`

## string_xrefs

- `0x180038c2a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180038c92`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180038cde`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall s_SSRecoverImportRecoveryKey(
        __int64 a1,
        const WCHAR *a2,
        unsigned int a3,
        const WCHAR *a4,
        unsigned int a5,
        BYTE *pbCertEncoded,
        DWORD cbCertEncoded)
{
  unsigned __int64 v8; // rbx
  __int64 v10; // rax
  int LastError; // eax
  __int64 v13; // r9
  DWORD v14; // ebx
  __int64 v15; // rcx
  PCCERT_CONTEXT CertificateContext; // rdi
  HCERTSTORE v17; // rax
  void *v18; // rsi
  DWORD v19; // eax
  __int64 v20; // r9
  DWORD nSize; // [rsp+30h] [rbp-51h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-41h] BYREF
  struct _UNICODE_STRING v24; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING v25; // [rsp+60h] [rbp-21h] BYREF
  WCHAR Buffer[16]; // [rsp+70h] [rbp-11h] BYREF

  hObject = 0;
  nSize = 0;
  DestinationString = 0;
  v8 = a3;
  v24 = 0;
  v25 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  if ( !a2 || (unsigned int)v8 < 2 || !a4 || a5 < 2 || !pbCertEncoded || !cbCertEncoded )
  {
    v13 = 1008;
    goto LABEL_37;
  }
  if ( a2[(v8 >> 1) - 1] || a4[((unsigned __int64)a5 >> 1) - 1] )
  {
    v13 = 1017;
LABEL_37:
    v15 = 87;
    v14 = 87;
    goto LABEL_38;
  }
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( !(_DWORD)v10 )
    return 87;
  nSize = 16;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    LastError = GetLastError();
    v13 = 1040;
LABEL_18:
    v14 = LastError;
LABEL_19:
    v15 = (unsigned int)LastError;
LABEL_38:
    DebugTraceError(v15, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v13);
    goto LABEL_39;
  }
  LastError = VerifyCredentials(a2, Buffer, a4);
  v14 = LastError;
  if ( LastError )
  {
    v13 = 1050;
    goto LABEL_19;
  }
  RtlInitUnicodeString(&DestinationString, Buffer);
  RtlInitUnicodeString(&v24, a2);
  RtlInitUnicodeString(&v25, a4);
  LastError = PRCreateLocalToken(&v24, &DestinationString, &hObject);
  v14 = LastError;
  if ( LastError < 0 )
  {
    v13 = 1070;
    goto LABEL_19;
  }
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    v13 = 1085;
    goto LABEL_18;
  }
  v17 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"Recovery");
  v18 = v17;
  if ( v17 )
  {
    if ( CertAddCertificateContextToStore(v17, CertificateContext, 3u, 0) )
    {
      v19 = EncryptRecoveryPassword((__int64)hObject, CertificateContext, &v25);
      v14 = v19;
      if ( !v19 )
      {
LABEL_33:
        CertCloseStore(v18, 0);
        goto LABEL_34;
      }
      v20 = 1121;
    }
    else
    {
      v19 = GetLastError();
      v14 = v19;
      v20 = 1110;
    }
    DebugTraceError(v19, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v20);
    goto LABEL_33;
  }
  v14 = GetLastError();
  DebugTraceError(v14, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1100);
LABEL_34:
  CertFreeCertificateContext(CertificateContext);
LABEL_39:
  if ( hObject )
    CloseHandle(hObject);
  return v14;
}

```

## disassembly

```asm
0x180038a00  mov     [rsp-8+arg_0], rbx
0x180038a05  mov     [rsp-8+arg_10], rsi
0x180038a0a  push    rbp
0x180038a0b  push    rdi
0x180038a0c  push    r12
0x180038a0e  push    r14
0x180038a10  push    r15
0x180038a12  lea     rbp, [rsp-1Fh]
0x180038a17  sub     rsp, 0A0h
0x180038a1e  mov     rax, cs:__security_cookie
0x180038a25  xor     rax, rsp
0x180038a28  mov     [rbp+3Fh+var_30], rax
0x180038a2c  mov     r14, [rbp+3Fh+pbCertEncoded]
0x180038a30  xor     r12d, r12d
0x180038a33  mov     r15d, [rbp+3Fh+cbCertEncoded]
0x180038a37  xorps   xmm0, xmm0
0x180038a3a  xorps   xmm1, xmm1
0x180038a3d  mov     [rbp+3Fh+hObject], r12
0x180038a41  mov     [rbp+3Fh+nSize], r12d
0x180038a45  mov     rsi, r9
0x180038a48  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180038a4c  mov     ebx, r8d
0x180038a4f  mov     rdi, rdx
0x180038a52  movups  xmmword ptr [rbp+3Fh+var_70.Length], xmm1
0x180038a56  movups  xmmword ptr [rbp+3Fh+var_60.Length], xmm0
0x180038a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a61  lea     rax, WPP_GLOBAL_Control
0x180038a68  cmp     rcx, rax
0x180038a6b  jz      short loc_180038A88
0x180038a6d  test    byte ptr [rcx+1Ch], 4
0x180038a71  jz      short loc_180038A88
0x180038a73  mov     rcx, [rcx+10h]
0x180038a77  lea     edx, [r12+14h]
0x180038a7c  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180038a83  call    WPP_SF_
0x180038a88  test    rdi, rdi
0x180038a8b  jz      loc_180038CD1
0x180038a91  cmp     ebx, 2
0x180038a94  jb      loc_180038CD1
0x180038a9a  test    rsi, rsi
0x180038a9d  jz      loc_180038CD1
0x180038aa3  cmp     [rbp+3Fh+arg_20], 2
0x180038aa7  jb      loc_180038CD1
0x180038aad  test    r14, r14
0x180038ab0  jz      loc_180038CD1
0x180038ab6  test    r15d, r15d
0x180038ab9  jz      loc_180038CD1
0x180038abf  mov     rax, rbx
0x180038ac2  shr     rax, 1
0x180038ac5  cmp     [rdi+rax*2-2], r12w
0x180038acb  jnz     loc_180038CC9
0x180038ad1  mov     eax, [rbp+3Fh+arg_20]
0x180038ad4  shr     rax, 1
0x180038ad7  cmp     [rsi+rax*2-2], r12w
0x180038add  jnz     loc_180038CC9
0x180038ae3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038ae7  inc     rax
0x180038aea  cmp     [rdi+rax*2], r12w
0x180038aef  jnz     short loc_180038AE7
0x180038af1  test    eax, eax
0x180038af3  jnz     short loc_180038AFF
0x180038af5  mov     eax, 57h ; 'W'
0x180038afa  jmp     loc_180038D08
0x180038aff  lea     r8, [rbp+3Fh+nSize]; nSize
0x180038b03  mov     [rbp+3Fh+nSize], 10h
0x180038b0a  lea     rdx, [rbp+3Fh+Buffer]; lpBuffer
0x180038b0e  xor     ecx, ecx; NameType
0x180038b10  call    cs:__imp_GetComputerNameExW
0x180038b17  nop     dword ptr [rax+rax+00h]
0x180038b1c  test    eax, eax
0x180038b1e  jnz     short loc_180038B3B
0x180038b20  call    cs:__imp_GetLastError
0x180038b27  nop     dword ptr [rax+rax+00h]
0x180038b2c  mov     r9d, 410h
0x180038b32  mov     ebx, eax
0x180038b34  mov     ecx, eax
0x180038b36  jmp     loc_180038CDE
0x180038b3b  mov     r8, rsi; LPCWSTR
0x180038b3e  lea     rdx, [rbp+3Fh+Buffer]; LPCWSTR
0x180038b42  mov     rcx, rdi; lpString
0x180038b45  call    ?VerifyCredentials@@YAKPEAG00@Z; VerifyCredentials(ushort *,ushort *,ushort *)
0x180038b4a  mov     ebx, eax
0x180038b4c  test    eax, eax
0x180038b4e  jz      short loc_180038B58
0x180038b50  mov     r9d, 41Ah
0x180038b56  jmp     short loc_180038B34
0x180038b58  lea     rdx, [rbp+3Fh+Buffer]; SourceString
0x180038b5c  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180038b60  call    cs:__imp_RtlInitUnicodeString
0x180038b67  nop     dword ptr [rax+rax+00h]
0x180038b6c  mov     rdx, rdi; SourceString
0x180038b6f  lea     rcx, [rbp+3Fh+var_70]; DestinationString
0x180038b73  call    cs:__imp_RtlInitUnicodeString
0x180038b7a  nop     dword ptr [rax+rax+00h]
0x180038b7f  mov     rdx, rsi; SourceString
0x180038b82  lea     rcx, [rbp+3Fh+var_60]; DestinationString
0x180038b86  call    cs:__imp_RtlInitUnicodeString
0x180038b8d  nop     dword ptr [rax+rax+00h]
0x180038b92  lea     r8, [rbp+3Fh+hObject]; void **
0x180038b96  lea     rdx, [rbp+3Fh+DestinationString]; struct _UNICODE_STRING *
0x180038b9a  lea     rcx, [rbp+3Fh+var_70]; struct _UNICODE_STRING *
0x180038b9e  call    ?PRCreateLocalToken@@YAKPEAU_UNICODE_STRING@@0PEAPEAX@Z; PRCreateLocalToken(_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x180038ba3  mov     ebx, eax
0x180038ba5  test    eax, eax
0x180038ba7  jns     short loc_180038BB1
0x180038ba9  mov     r9d, 42Eh
0x180038baf  jmp     short loc_180038B34
0x180038bb1  mov     ebx, 1
0x180038bb6  mov     r8d, r15d; cbCertEncoded
0x180038bb9  mov     ecx, ebx; dwCertEncodingType
0x180038bbb  mov     rdx, r14; pbCertEncoded
0x180038bbe  call    cs:__imp_CertCreateCertificateContext
0x180038bc5  nop     dword ptr [rax+rax+00h]
0x180038bca  mov     rdi, rax
0x180038bcd  test    rax, rax
0x180038bd0  jnz     short loc_180038BE9
0x180038bd2  call    cs:__imp_GetLastError
0x180038bd9  nop     dword ptr [rax+rax+00h]
0x180038bde  mov     r9d, 43Dh
0x180038be4  jmp     loc_180038B32
0x180038be9  xor     r8d, r8d; hCryptProv
0x180038bec  lea     rax, aRecovery_0; "Recovery"
0x180038bf3  mov     r9d, 20000h; dwFlags
0x180038bf9  mov     [rsp+0C0h+pvPara], rax; pvPara
0x180038bfe  mov     edx, ebx; dwEncodingType
0x180038c00  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180038c04  call    cs:__imp_CertOpenStore
0x180038c0b  nop     dword ptr [rax+rax+00h]
0x180038c10  mov     rsi, rax
0x180038c13  test    rax, rax
0x180038c16  jnz     short loc_180038C43
0x180038c18  call    cs:__imp_GetLastError
0x180038c1f  nop     dword ptr [rax+rax+00h]
0x180038c24  mov     r9d, 44Ch
0x180038c2a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038c31  mov     ecx, eax
0x180038c33  lea     rdx, aDwerror; "dwError"
0x180038c3a  mov     ebx, eax
0x180038c3c  call    DebugTraceError
0x180038c41  jmp     short loc_180038CB8
0x180038c43  xor     r9d, r9d; ppStoreContext
0x180038c46  mov     rdx, rdi; pCertContext
0x180038c49  mov     rcx, rsi; hCertStore
0x180038c4c  lea     r8d, [r9+3]; dwAddDisposition
0x180038c50  call    cs:__imp_CertAddCertificateContextToStore
0x180038c57  nop     dword ptr [rax+rax+00h]
0x180038c5c  test    eax, eax
0x180038c5e  jnz     short loc_180038C76
0x180038c60  call    cs:__imp_GetLastError
0x180038c67  nop     dword ptr [rax+rax+00h]
0x180038c6c  mov     ebx, eax
0x180038c6e  mov     r9d, 456h
0x180038c74  jmp     short loc_180038C92
0x180038c76  mov     rcx, [rbp+3Fh+hObject]; void *
0x180038c7a  lea     r8, [rbp+3Fh+var_60]; struct _UNICODE_STRING *
0x180038c7e  mov     rdx, rdi; struct _CERT_CONTEXT *
0x180038c81  call    ?EncryptRecoveryPassword@@YAKPEAXPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z; EncryptRecoveryPassword(void *,_CERT_CONTEXT const *,_UNICODE_STRING *)
0x180038c86  mov     ebx, eax
0x180038c88  test    eax, eax
0x180038c8a  jz      short loc_180038CA7
0x180038c8c  mov     r9d, 461h
0x180038c92  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038c99  mov     ecx, eax
0x180038c9b  lea     rdx, aDwerror; "dwError"
0x180038ca2  call    DebugTraceError
0x180038ca7  xor     edx, edx; dwFlags
0x180038ca9  mov     rcx, rsi; hCertStore
0x180038cac  call    cs:__imp_CertCloseStore
0x180038cb3  nop     dword ptr [rax+rax+00h]
0x180038cb8  mov     rcx, rdi; pCertContext
0x180038cbb  call    cs:__imp_CertFreeCertificateContext
0x180038cc2  nop     dword ptr [rax+rax+00h]
0x180038cc7  jmp     short loc_180038CF1
0x180038cc9  mov     r9d, 3F9h
0x180038ccf  jmp     short loc_180038CD7
0x180038cd1  mov     r9d, 3F0h
0x180038cd7  mov     ecx, 57h ; 'W'
0x180038cdc  mov     ebx, ecx
0x180038cde  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038ce5  lea     rdx, aDwerror; "dwError"
0x180038cec  call    DebugTraceError
0x180038cf1  mov     rcx, [rbp+3Fh+hObject]; hObject
0x180038cf5  test    rcx, rcx
0x180038cf8  jz      short loc_180038D06
0x180038cfa  call    cs:__imp_CloseHandle
0x180038d01  nop     dword ptr [rax+rax+00h]
0x180038d06  mov     eax, ebx
0x180038d08  mov     rcx, [rbp+3Fh+var_30]
0x180038d0c  xor     rcx, rsp; StackCookie
0x180038d0f  call    __security_check_cookie
0x180038d14  lea     r11, [rsp+0C0h+var_20]
0x180038d1c  mov     rbx, [r11+30h]
0x180038d20  mov     rsi, [r11+40h]
0x180038d24  mov     rsp, r11
0x180038d27  pop     r15
0x180038d29  pop     r14
0x180038d2b  pop     r12
0x180038d2d  pop     rdi
0x180038d2e  pop     rbp
0x180038d2f  retn
```
