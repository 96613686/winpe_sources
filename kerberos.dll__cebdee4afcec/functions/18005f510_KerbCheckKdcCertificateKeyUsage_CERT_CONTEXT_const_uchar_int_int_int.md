# KerbCheckKdcCertificateKeyUsage(_CERT_CONTEXT const *,uchar,int *,int *,int *)

- ea: `0x18005f510`
- end: `0x18005f7f6`
- name: `?KerbCheckKdcCertificateKeyUsage@@YAJPEBU_CERT_CONTEXT@@EPEAH11@Z`
- size: `742`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, char, int *, int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f044`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18005f510`
- `0x180065c48`
- `0x18008b2f4`
- `0x18008b70c`
- `0x1800935dc`
- `0x1800b4000`
- `0x1800f1ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f65d`
- `CRYPT32!CertFindExtension` at `0x18005f597`
- `CRYPT32!CertFindExtension` at `0x18005f597`
- `CRYPT32!CryptDecodeObject` at `0x18005f5d3`
- `CRYPT32!CryptDecodeObject` at `0x18005f64e`
- `CRYPT32!CryptDecodeObject` at `0x18005f5d3`
- `CRYPT32!CryptDecodeObject` at `0x18005f64e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbCheckKdcCertificateKeyUsage(const struct _CERT_CONTEXT *a1, char a2, int *a3, int *a4, int *a5)
{
  int *v5; // r13
  char v6; // r14
  PCERT_INFO pCertInfo; // rdx
  int *v9; // rbx
  unsigned int v10; // ebx
  _QWORD *pvStructInfo; // rsi
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v13; // rbp
  DWORD LastError; // eax
  DWORD v15; // eax
  int v16; // r15d
  int v17; // eax
  __int64 v18; // rbp
  __int64 v19; // rbx
  const char *v20; // r14
  int v21; // eax
  int v22; // ecx
  _QWORD *CorrelationId; // rax
  __int64 v24; // rcx
  _BYTE v26[104]; // [rsp+40h] [rbp-68h] BYREF
  DWORD pcbStructInfo; // [rsp+B0h] [rbp+8h] BYREF
  char v28; // [rsp+B8h] [rbp+10h]
  int *v29; // [rsp+C0h] [rbp+18h]
  int v30; // [rsp+C8h] [rbp+20h]

  v29 = a3;
  v28 = a2;
  v5 = a5;
  v6 = 0;
  pCertInfo = a1->pCertInfo;
  v30 = 0;
  v9 = a3;
  pcbStructInfo = 0;
  *a5 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !pCertInfo )
  {
    KerbTracerT::Log(1, "KerbCheckKdcCertificateKeyUsage", 1439, "no cert info\n");
    return (unsigned int)-1073741811;
  }
  pvStructInfo = 0;
  Extension = CertFindExtension("2.5.29.37", pCertInfo->cExtension, pCertInfo->rgExtension);
  v13 = Extension;
  if ( Extension )
  {
    if ( !CryptDecodeObject(1u, (LPCSTR)0x24, Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo) )
    {
      v10 = -1073741670;
      LastError = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbCheckKdcCertificateKeyUsage",
        1464,
        "CryptDecodeObject get size failed with %#x\n",
        LastError);
      return v10;
    }
    pvStructInfo = MIDL_user_allocate(pcbStructInfo);
    if ( !pvStructInfo )
      return (unsigned int)-1073741801;
    if ( !CryptDecodeObject(1u, (LPCSTR)0x24, v13->Value.pbData, v13->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
    {
      v10 = -1073741670;
      v15 = GetLastError();
      KerbTracerT::Log(1, "KerbCheckKdcCertificateKeyUsage", 1485, "CryptDecodeObject decode failed with %#x\n", v15);
LABEL_36:
      KerbFree(pvStructInfo);
      return v10;
    }
    v16 = 0;
    if ( *(_DWORD *)pvStructInfo )
    {
      v17 = *v9;
      v18 = 0;
      v19 = pvStructInfo[1];
      LODWORD(a5) = v17;
      do
      {
        v20 = *(const char **)(v19 + 8 * v18);
        if ( !strcmp_0("1.3.6.1.5.2.3.5", v20) )
        {
          v21 = 1;
          LODWORD(a5) = 1;
        }
        else
        {
          if ( !strcmp_0("1.3.6.1.4.1.311.20.2.2", v20) )
          {
            *a4 = 1;
          }
          else if ( !strcmp_0("1.3.6.1.5.5.7.3.1", v20) )
          {
            *v5 = 1;
          }
          else if ( !strcmp_0("2.5.29.37.0", v20) )
          {
            v16 = 1;
          }
          v21 = (int)a5;
        }
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < *(_DWORD *)pvStructInfo );
      v9 = v29;
      v6 = v30;
      *v29 = v21;
    }
    if ( !*v9 && !*a4 && !*v5 && !v16 )
    {
      KerbTracerT::Log(1, "KerbCheckKdcCertificateKeyUsage", 1529, "KDC certificate is restricted with usage\n");
      v10 = -1073741024;
      goto LABEL_36;
    }
  }
  if ( !v28 || *v9 )
  {
    v10 = 0;
  }
  else
  {
    KerbTracerT::Log(1, "KerbCheckKdcCertificateKeyUsage", 1537, "KDC certificate no required kdc eku\n");
    v10 = -1073741024;
    KerbReportKdcCertValidationMissingKdcEku(v22);
    if ( (Microsoft_Windows_Security_KerberosEnableBits & 2) != 0 )
    {
      CorrelationId = (_QWORD *)KerbTracerT::GetCorrelationId(v26);
      v6 = 1;
      McTemplateU0qz_EtwEventWriteTransfer(v24, KdcCertValidationMissingKdcEku, 3221226272LL, *CorrelationId);
    }
    if ( (v6 & 1) != 0 )
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v26);
  }
  if ( pvStructInfo )
    goto LABEL_36;
  return v10;
}

```

## disassembly

```asm
0x18005f510  mov     rax, rsp
0x18005f513  mov     [rax+18h], r8
0x18005f517  mov     [rax+10h], dl
0x18005f51a  push    rbx
0x18005f51b  push    rbp
0x18005f51c  push    rsi
0x18005f51d  push    rdi
0x18005f51e  push    r12
0x18005f520  push    r13
0x18005f522  push    r14
0x18005f524  push    r15
0x18005f526  sub     rsp, 68h
0x18005f52a  mov     r13, [rsp+0A8h+arg_20]
0x18005f532  xor     r14d, r14d
0x18005f535  mov     rdx, [rcx+18h]
0x18005f539  mov     r12, r9
0x18005f53c  mov     [rsp+0A8h+arg_18], r14d
0x18005f544  mov     rbx, r8
0x18005f547  mov     [rax+8], r14d
0x18005f54b  mov     [r13+0], r14d
0x18005f54f  mov     [r8], r14d
0x18005f552  mov     [r9], r14d
0x18005f555  test    rdx, rdx
0x18005f558  jnz     short loc_18005F581
0x18005f55a  lea     r9, aNoCertInfo; "no cert info\n"
0x18005f561  mov     r8d, 59Fh
0x18005f567  lea     rdx, aKerbcheckkdcce; "KerbCheckKdcCertificateKeyUsage"
0x18005f56e  lea     ecx, [r14+1]
0x18005f572  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f577  mov     ebx, 0C000000Dh
0x18005f57c  jmp     loc_18005F7E3
0x18005f581  mov     r8, [rdx+0C8h]; rgExtensions
0x18005f588  lea     rcx, pszObjId; "2.5.29.37"
0x18005f58f  mov     edx, [rdx+0C0h]; cExtensions
0x18005f595  xor     esi, esi
0x18005f597  call    cs:__imp_CertFindExtension
0x18005f59d  lea     edi, [rsi+1]
0x18005f5a0  mov     rbp, rax
0x18005f5a3  test    rax, rax
0x18005f5a6  jz      loc_18005F764
0x18005f5ac  mov     r9d, [rbp+10h]; cbEncoded
0x18005f5b0  lea     rax, [rsp+0A8h+arg_0]
0x18005f5b8  mov     r8, [rbp+18h]; pbEncoded
0x18005f5bc  lea     r15d, [rsi+24h]
0x18005f5c0  mov     [rsp+0A8h+pcbStructInfo], rax; pcbStructInfo
0x18005f5c5  mov     edx, r15d; lpszStructType
0x18005f5c8  mov     [rsp+0A8h+pvStructInfo], rsi; pvStructInfo
0x18005f5cd  mov     ecx, edi; dwCertEncodingType
0x18005f5cf  mov     [rsp+0A8h+dwFlags], esi; dwFlags
0x18005f5d3  call    cs:__imp_CryptDecodeObject
0x18005f5d9  test    eax, eax
0x18005f5db  jnz     short loc_18005F60C
0x18005f5dd  mov     ebx, 0C000009Ah
0x18005f5e2  call    cs:__imp_GetLastError
0x18005f5e8  lea     r9, aCryptdecodeobj_2; "CryptDecodeObject get size failed with "...
0x18005f5ef  mov     r8d, 5B8h
0x18005f5f5  lea     rdx, aKerbcheckkdcce; "KerbCheckKdcCertificateKeyUsage"
0x18005f5fc  mov     [rsp+0A8h+dwFlags], eax
0x18005f600  mov     ecx, edi
0x18005f602  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f607  jmp     loc_18005F7E3
0x18005f60c  mov     ecx, [rsp+0A8h+arg_0]; size
0x18005f613  call    MIDL_user_allocate
0x18005f618  mov     rsi, rax
0x18005f61b  test    rax, rax
0x18005f61e  jnz     short loc_18005F62A
0x18005f620  mov     ebx, 0C0000017h
0x18005f625  jmp     loc_18005F7E3
0x18005f62a  mov     r9d, [rbp+10h]; cbEncoded
0x18005f62e  lea     rax, [rsp+0A8h+arg_0]
0x18005f636  mov     r8, [rbp+18h]; pbEncoded
0x18005f63a  mov     rdx, r15; lpszStructType
0x18005f63d  mov     [rsp+0A8h+pcbStructInfo], rax; pcbStructInfo
0x18005f642  mov     ecx, edi; dwCertEncodingType
0x18005f644  mov     [rsp+0A8h+pvStructInfo], rsi; pvStructInfo
0x18005f649  mov     [rsp+0A8h+dwFlags], r14d; dwFlags
0x18005f64e  call    cs:__imp_CryptDecodeObject
0x18005f654  test    eax, eax
0x18005f656  jnz     short loc_18005F687
0x18005f658  mov     ebx, 0C000009Ah
0x18005f65d  call    cs:__imp_GetLastError
0x18005f663  lea     r9, aCryptdecodeobj_3; "CryptDecodeObject decode failed with %#"...
0x18005f66a  mov     r8d, 5CDh
0x18005f670  lea     rdx, aKerbcheckkdcce; "KerbCheckKdcCertificateKeyUsage"
0x18005f677  mov     [rsp+0A8h+dwFlags], eax
0x18005f67b  mov     ecx, edi
0x18005f67d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f682  jmp     loc_18005F7DB
0x18005f687  xor     r15d, r15d
0x18005f68a  cmp     [rsi], r14d
0x18005f68d  jbe     loc_18005F72A
0x18005f693  mov     eax, [rbx]
0x18005f695  xor     ebp, ebp
0x18005f697  mov     rbx, [rsi+8]
0x18005f69b  mov     dword ptr [rsp+0A8h+arg_20], eax
0x18005f6a2  mov     r14, [rbx+rbp*8]
0x18005f6a6  lea     rcx, a13615235; "1.3.6.1.5.2.3.5"
0x18005f6ad  mov     rdx, r14; Str2
0x18005f6b0  call    strcmp_0
0x18005f6b5  test    eax, eax
0x18005f6b7  jnz     short loc_18005F6C4
0x18005f6b9  mov     eax, edi
0x18005f6bb  mov     dword ptr [rsp+0A8h+arg_20], eax
0x18005f6c2  jmp     short loc_18005F712
0x18005f6c4  mov     rdx, r14; Str2
0x18005f6c7  lea     rcx, a1361413112022; "1.3.6.1.4.1.311.20.2.2"
0x18005f6ce  call    strcmp_0
0x18005f6d3  test    eax, eax
0x18005f6d5  jnz     short loc_18005F6DD
0x18005f6d7  mov     [r12], edi
0x18005f6db  jmp     short loc_18005F70B
0x18005f6dd  mov     rdx, r14; Str2
0x18005f6e0  lea     rcx, a136155731; "1.3.6.1.5.5.7.3.1"
0x18005f6e7  call    strcmp_0
0x18005f6ec  test    eax, eax
0x18005f6ee  jnz     short loc_18005F6F6
0x18005f6f0  mov     [r13+0], edi
0x18005f6f4  jmp     short loc_18005F70B
0x18005f6f6  mov     rdx, r14; Str2
0x18005f6f9  lea     rcx, a2529370; "2.5.29.37.0"
0x18005f700  call    strcmp_0
0x18005f705  test    eax, eax
0x18005f707  cmovz   r15d, edi
0x18005f70b  mov     eax, dword ptr [rsp+0A8h+arg_20]
0x18005f712  add     ebp, edi
0x18005f714  cmp     ebp, [rsi]
0x18005f716  jb      short loc_18005F6A2
0x18005f718  mov     rbx, [rsp+0A8h+arg_10]
0x18005f720  mov     r14d, [rsp+0A8h+arg_18]
0x18005f728  mov     [rbx], eax
0x18005f72a  cmp     dword ptr [rbx], 0
0x18005f72d  jnz     short loc_18005F764
0x18005f72f  cmp     dword ptr [r12], 0
0x18005f734  jnz     short loc_18005F764
0x18005f736  cmp     dword ptr [r13+0], 0
0x18005f73b  jnz     short loc_18005F764
0x18005f73d  test    r15d, r15d
0x18005f740  jnz     short loc_18005F764
0x18005f742  lea     r9, aKdcCertificate; "KDC certificate is restricted with usag"...
0x18005f749  mov     r8d, 5F9h
0x18005f74f  lea     rdx, aKerbcheckkdcce; "KerbCheckKdcCertificateKeyUsage"
0x18005f756  mov     ecx, edi
0x18005f758  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f75d  mov     ebx, 0C0000320h
0x18005f762  jmp     short loc_18005F7DB
0x18005f764  cmp     [rsp+0A8h+arg_8], 0
0x18005f76c  jz      short loc_18005F7D4
0x18005f76e  cmp     dword ptr [rbx], 0
0x18005f771  jnz     short loc_18005F7D4
0x18005f773  lea     r9, aKdcCertificate_1; "KDC certificate no required kdc eku\n"
0x18005f77a  mov     r8d, 601h
0x18005f780  lea     rdx, aKerbcheckkdcce; "KerbCheckKdcCertificateKeyUsage"
0x18005f787  mov     ecx, edi
0x18005f789  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f78e  mov     ebx, 0C0000320h
0x18005f793  call    ?KerbReportKdcCertValidationMissingKdcEku@@YAXJ@Z; KerbReportKdcCertValidationMissingKdcEku(long)
0x18005f798  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 2
0x18005f79f  jz      short loc_18005F7C3
0x18005f7a1  lea     rcx, [rsp+0A8h+var_68]
0x18005f7a6  call    ?GetCorrelationId@KerbTracerT@@SA?BV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; KerbTracerT::GetCorrelationId(void)
0x18005f7ab  mov     r8d, 0C0000320h
0x18005f7b1  lea     rdx, KdcCertValidationMissingKdcEku
0x18005f7b8  mov     r14d, edi
0x18005f7bb  mov     r9, [rax]
0x18005f7be  call    McTemplateU0qz_EtwEventWriteTransfer
0x18005f7c3  test    dil, r14b
0x18005f7c6  jz      short loc_18005F7D6
0x18005f7c8  lea     rcx, [rsp+0A8h+var_68]
0x18005f7cd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005f7d2  jmp     short loc_18005F7D6
0x18005f7d4  xor     ebx, ebx
0x18005f7d6  test    rsi, rsi
0x18005f7d9  jz      short loc_18005F7E3
0x18005f7db  mov     rcx, rsi
0x18005f7de  call    KerbFree
0x18005f7e3  mov     eax, ebx
0x18005f7e5  add     rsp, 68h
0x18005f7e9  pop     r15
0x18005f7eb  pop     r14
0x18005f7ed  pop     r13
0x18005f7ef  pop     r12
0x18005f7f1  pop     rdi
0x18005f7f2  pop     rsi
0x18005f7f3  pop     rbp
0x18005f7f4  pop     rbx
0x18005f7f5  retn
```
