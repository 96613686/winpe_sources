# KerbCheckUserNameForCert(_LUID *,uchar,_UNICODE_STRING *,_UNICODE_STRING *,_CERT_CONTEXT const * *)

- ea: `0x1800638a0`
- end: `0x180063c6b`
- name: `?KerbCheckUserNameForCert@@YAJPEAU_LUID@@EPEAU_UNICODE_STRING@@1PEAPEBU_CERT_CONTEXT@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(struct _LUID *, char, struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _CERT_CONTEXT **)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025680`
- `0x18005b210`
- `0x1800974f0`
- `0x1800adccc`

## callees

- `0x1800068d0`
- `0x180007e80`
- `0x18000b300`
- `0x1800638a0`
- `0x180070680`
- `0x1800744cf`
- `0x18008b70c`
- `0x180092ec0`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063bc2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180063b3f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180063b3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063c1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063c1c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180063bfe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180063bfe`
- `ntdll!RtlInitUnicodeString` at `0x180063a48`
- `ntdll!RtlInitUnicodeString` at `0x180063a48`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180063c0d`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180063c0d`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180063a5a`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180063a5a`
- `CRYPT32!CertFindCertificateInStore` at `0x180063bab`
- `CRYPT32!CertFindCertificateInStore` at `0x180063bab`
- `CRYPT32!CertCloseStore` at `0x180063bf8`
- `CRYPT32!CertCloseStore` at `0x180063bf8`
- `CRYPT32!CertOpenStore` at `0x180063abc`
- `CRYPT32!CertOpenStore` at `0x180063abc`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180063a02`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180063a02`

## string_xrefs

- `0x180063b16`: `Unable to get the client token handle.\n`
- `0x180063b4d`: `Unable to impersonate the client token handle.\n`
- `0x180063ace`: `Failed to open the user cert store even though a cert cred was found.\n`

## pseudocode

```c
__int64 __fastcall KerbCheckUserNameForCert(
        struct _LUID *a1,
        char a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        const struct _CERT_CONTEXT **a5)
{
  __int64 Length; // rax
  unsigned __int64 v11; // rbx
  PVOID *p_Credential; // rdi
  WCHAR *p_SourceString; // rsi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  _DWORD *v18; // rax
  int v19; // ebx
  HCERTSTORE v20; // rsi
  PCCERT_CONTEXT CertificateInStore; // rax
  DWORD LastError; // eax
  __int64 v23; // [rsp+0h] [rbp-30h] BYREF
  int v24; // [rsp+30h] [rbp+0h] BYREF
  _CRED_MARSHAL_TYPE CredType; // [rsp+34h] [rbp+4h] BYREF
  PVOID Credential; // [rsp+38h] [rbp+8h] BYREF
  HANDLE Token; // [rsp+40h] [rbp+10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp+18h] BYREF
  const struct _CERT_CONTEXT **v29; // [rsp+58h] [rbp+28h]
  __int128 pvFindPara; // [rsp+60h] [rbp+30h] BYREF
  struct _UNICODE_STRING v31; // [rsp+70h] [rbp+40h] BYREF
  WCHAR SourceString; // [rsp+90h] [rbp+60h] BYREF

  v29 = a5;
  CredType = 0;
  *a5 = 0;
  Length = a3->Length;
  Credential = 0;
  Token = 0;
  v24 = 0;
  pvFindPara = 0;
  DestinationString = 0;
  v31 = 0;
  if ( !(_WORD)Length )
    return 0;
  v11 = Length + 2;
  p_Credential = 0;
  if ( (unsigned __int64)(Length + 2) > 0x404 )
  {
    if ( v11 > g_ulMaxStackAllocSize || v11 + g_ulAdditionalProbeSize + 8 < v11 || !(unsigned int)VerifyStackAvailable() )
      goto LABEL_52;
    v14 = v11 + 23;
    if ( v11 + 23 <= v11 + 8 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    p_Credential = (PVOID *)&v24;
    if ( &v23 == (__int64 *)-48LL || (v24 = 1801679955, (p_Credential = &Credential) == 0) )
    {
LABEL_52:
      if ( v11 + 8 >= v11 )
      {
        v18 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_Credential = (PVOID *)v18;
        if ( v18 )
        {
          *v18 = 1885431112;
          p_Credential = (PVOID *)(v18 + 2);
        }
      }
    }
    if ( !p_Credential )
    {
      v19 = -1073741670;
      goto LABEL_42;
    }
    p_SourceString = (WCHAR *)p_Credential;
  }
  else
  {
    p_SourceString = &SourceString;
  }
  memcpy_0(p_SourceString, a3->Buffer, a3->Length);
  p_SourceString[(unsigned __int64)a3->Length >> 1] = 0;
  if ( a4->Length )
  {
    v19 = 0;
    RtlInitUnicodeString(&DestinationString, p_SourceString);
  }
  else
  {
    v19 = CredParseUserNameWithType(p_SourceString, &DestinationString, &v31, &v24);
    if ( v19 < 0 )
      goto LABEL_42;
    if ( v24 != 3 )
    {
      v19 = 0;
      goto LABEL_42;
    }
    KerbFreeString(a4);
    v19 = KerbDuplicateStringEx(a4, &v31);
    if ( v19 < 0 )
      goto LABEL_42;
  }
  if ( CredUnmarshalCredentialW(DestinationString.Buffer, &CredType, &Credential) )
  {
    if ( CredType == CertCredential )
    {
      if ( a1 )
      {
        v19 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a1, &Token);
        if ( v19 < 0 )
        {
          KerbTracerT::Log(1, "KerbCheckUserNameForCert", 646, "Unable to get the client token handle.\n");
          goto LABEL_42;
        }
        if ( !SetThreadToken(0, Token) )
        {
          KerbTracerT::Log(1, "KerbCheckUserNameForCert", 652, "Unable to impersonate the client token handle.\n");
          v19 = -1073741555;
          goto LABEL_42;
        }
      }
      else
      {
        if ( !a2 )
          goto LABEL_42;
        v19 = LsaFunctions->ImpersonateClient();
        if ( v19 < 0 )
          goto LABEL_42;
      }
      v20 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
      if ( v20 )
      {
        *((_QWORD *)&pvFindPara + 1) = (char *)Credential + 4;
        LODWORD(pvFindPara) = 20;
        CertificateInStore = CertFindCertificateInStore(v20, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
        *v29 = CertificateInStore;
        if ( !CertificateInStore )
        {
          v19 = -2146893042;
          LastError = GetLastError();
          KerbTracerT::Log(
            1,
            "KerbCheckUserNameForCert",
            695,
            "KerbCheckUserNameForCert failed to find cert in store even though a cert cred was found: %#x\n",
            LastError);
          KerbReportCertificateStoreError(&DestinationString);
        }
        CertCloseStore(v20, 0);
      }
      else
      {
        v19 = -2146893042;
        KerbTracerT::Log(
          1,
          "KerbCheckUserNameForCert",
          673,
          "Failed to open the user cert store even though a cert cred was found.\n");
      }
      RevertToSelf();
      goto LABEL_42;
    }
    v19 = 0;
  }
  else
  {
    v19 = 0;
  }
LABEL_42:
  if ( Credential )
    CredFree(Credential);
  if ( Token )
    CloseHandle(Token);
  if ( p_Credential )
  {
    if ( *((_DWORD *)p_Credential - 2) == 1885431112 )
      ((void (__fastcall *)(PVOID *))g_pfnFree)(p_Credential - 1);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800638a0  push    rbp
0x1800638a2  push    rsi
0x1800638a3  push    rdi
0x1800638a4  push    r12
0x1800638a6  push    r13
0x1800638a8  push    r14
0x1800638aa  push    r15
0x1800638ac  sub     rsp, 4B0h
0x1800638b3  lea     rbp, [rsp+30h]
0x1800638b8  mov     [rbp+4B0h+arg_8], rbx
0x1800638bf  mov     rax, cs:__security_cookie
0x1800638c6  xor     rax, rbp
0x1800638c9  mov     [rbp+4B0h+var_40], rax
0x1800638d0  mov     rax, [rbp+4B0h+arg_20]
0x1800638d7  xorps   xmm0, xmm0
0x1800638da  mov     r12, rcx
0x1800638dd  mov     [rbp+4B0h+var_488], rax
0x1800638e1  xor     ecx, ecx
0x1800638e3  xorps   xmm1, xmm1
0x1800638e6  mov     r14, r9
0x1800638e9  mov     [rbp+4B0h+CredType], ecx
0x1800638ec  mov     [rax], rcx
0x1800638ef  mov     r15, r8
0x1800638f2  movzx   eax, word ptr [r8]
0x1800638f6  movzx   r13d, dl
0x1800638fa  mov     [rbp+4B0h+Credential], rcx
0x1800638fe  mov     [rbp+4B0h+Token], rcx
0x180063902  mov     [rbp+4B0h+var_4B0], ecx
0x180063905  movups  [rbp+4B0h+pvFindPara], xmm0
0x180063909  movups  xmmword ptr [rbp+4B0h+DestinationString.Length], xmm0
0x18006390d  movups  xmmword ptr [rbp+4B0h+var_470.Length], xmm1
0x180063911  test    ax, ax
0x180063914  jnz     short loc_18006391D
0x180063916  xor     eax, eax
0x180063918  jmp     loc_180063C42
0x18006391d  lea     rbx, [rax+2]
0x180063921  mov     rdi, rcx
0x180063924  cmp     rbx, 404h
0x18006392b  ja      short loc_180063936
0x18006392d  lea     rsi, [rbp+4B0h+SourceString]
0x180063931  jmp     loc_1800639D0
0x180063936  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18006393d  ja      short loc_180063997
0x18006393f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180063946  add     rcx, 8
0x18006394a  add     rcx, rbx
0x18006394d  cmp     rcx, rbx
0x180063950  jb      short loc_180063997
0x180063952  call    VerifyStackAvailable
0x180063957  test    eax, eax
0x180063959  jz      short loc_180063997
0x18006395b  lea     rax, [rbx+8]
0x18006395f  lea     rcx, [rax+0Fh]
0x180063963  cmp     rcx, rax
0x180063966  ja      short loc_180063972
0x180063968  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180063972  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180063976  mov     rax, rcx
0x180063979  call    _alloca_probe
0x18006397e  sub     rsp, rcx
0x180063981  lea     rdi, [rsp+4E0h+var_4B0]
0x180063986  test    rdi, rdi
0x180063989  jz      short loc_180063997
0x18006398b  mov     dword ptr [rdi], 6B637453h
0x180063991  add     rdi, 8
0x180063995  jnz     short loc_1800639BE
0x180063997  lea     rcx, [rbx+8]
0x18006399b  cmp     rcx, rbx
0x18006399e  jb      short loc_1800639BE
0x1800639a0  mov     rax, cs:g_pfnAllocate
0x1800639a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639ac  mov     rdi, rax
0x1800639af  test    rax, rax
0x1800639b2  jz      short loc_1800639BE
0x1800639b4  mov     dword ptr [rax], 70616548h
0x1800639ba  add     rdi, 8
0x1800639be  test    rdi, rdi
0x1800639c1  jnz     short loc_1800639CD
0x1800639c3  mov     ebx, 0C000009Ah
0x1800639c8  jmp     loc_180063C04
0x1800639cd  mov     rsi, rdi
0x1800639d0  movzx   r8d, word ptr [r15]; Size
0x1800639d4  mov     rcx, rsi; void *
0x1800639d7  mov     rdx, [r15+8]; Src
0x1800639db  call    memcpy_0
0x1800639e0  movzx   ecx, word ptr [r15]
0x1800639e4  xor     eax, eax
0x1800639e6  shr     rcx, 1
0x1800639e9  mov     [rsi+rcx*2], ax
0x1800639ed  cmp     [r14], ax
0x1800639f1  jnz     short loc_180063A3F
0x1800639f3  lea     r9, [rbp+4B0h+var_4B0]
0x1800639f7  mov     rcx, rsi
0x1800639fa  lea     r8, [rbp+4B0h+var_470]
0x1800639fe  lea     rdx, [rbp+4B0h+DestinationString]
0x180063a02  call    cs:__imp_CredParseUserNameWithType
0x180063a08  mov     ebx, eax
0x180063a0a  test    eax, eax
0x180063a0c  js      loc_180063C04
0x180063a12  cmp     [rbp+4B0h+var_4B0], 3
0x180063a16  jz      short loc_180063A1F
0x180063a18  xor     ebx, ebx
0x180063a1a  jmp     loc_180063C04
0x180063a1f  mov     rcx, r14
0x180063a22  call    KerbFreeString
0x180063a27  lea     rdx, [rbp+4B0h+var_470]; struct _UNICODE_STRING *
0x180063a2b  mov     rcx, r14; struct _UNICODE_STRING *
0x180063a2e  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180063a33  mov     ebx, eax
0x180063a35  test    eax, eax
0x180063a37  js      loc_180063C04
0x180063a3d  jmp     short loc_180063A4E
0x180063a3f  xor     ebx, ebx
0x180063a41  lea     rcx, [rbp+4B0h+DestinationString]; DestinationString
0x180063a45  mov     rdx, rsi; SourceString
0x180063a48  call    cs:__imp_RtlInitUnicodeString
0x180063a4e  mov     rcx, [rbp+4B0h+DestinationString.Buffer]; MarshaledCredential
0x180063a52  lea     r8, [rbp+4B0h+Credential]; Credential
0x180063a56  lea     rdx, [rbp+4B0h+CredType]; CredType
0x180063a5a  call    cs:__imp_CredUnmarshalCredentialW
0x180063a60  test    eax, eax
0x180063a62  jnz     short loc_180063A6B
0x180063a64  xor     ebx, ebx
0x180063a66  jmp     loc_180063C04
0x180063a6b  cmp     [rbp+4B0h+CredType], 1
0x180063a6f  jz      short loc_180063A78
0x180063a71  xor     ebx, ebx
0x180063a73  jmp     loc_180063C04
0x180063a78  test    r12, r12
0x180063a7b  jnz     short loc_180063AF6
0x180063a7d  test    r13b, r13b
0x180063a80  jz      loc_180063C04
0x180063a86  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180063a8d  mov     rax, [rax+58h]
0x180063a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a96  mov     ebx, eax
0x180063a98  test    eax, eax
0x180063a9a  js      loc_180063C04
0x180063aa0  lea     rax, aMy_0; "MY"
0x180063aa7  mov     r9d, 10000h; dwFlags
0x180063aad  xor     r8d, r8d; hCryptProv
0x180063ab0  mov     [rsp+4E0h+pvPara], rax; pvPara
0x180063ab5  xor     edx, edx; dwEncodingType
0x180063ab7  mov     ecx, 0Ah; lpszStoreProvider
0x180063abc  call    cs:__imp_CertOpenStore
0x180063ac2  mov     rsi, rax
0x180063ac5  test    rax, rax
0x180063ac8  jnz     loc_180063B75
0x180063ace  lea     r9, aFailedToOpenTh; "Failed to open the user cert store even"...
0x180063ad5  mov     r8d, 2A1h
0x180063adb  lea     rdx, aKerbcheckusern_0; "KerbCheckUserNameForCert"
0x180063ae2  mov     ecx, 1
0x180063ae7  mov     ebx, 8009030Eh
0x180063aec  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180063af1  jmp     loc_180063BFE
0x180063af6  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180063afd  lea     rdx, [rbp+4B0h+Token]
0x180063b01  mov     rcx, r12
0x180063b04  mov     rax, [rax+170h]
0x180063b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b10  mov     ebx, eax
0x180063b12  test    eax, eax
0x180063b14  jns     short loc_180063B39
0x180063b16  lea     r9, aUnableToGetThe; "Unable to get the client token handle."...
0x180063b1d  mov     r8d, 286h
0x180063b23  lea     rdx, aKerbcheckusern_0; "KerbCheckUserNameForCert"
0x180063b2a  mov     ecx, 1
0x180063b2f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180063b34  jmp     loc_180063C04
0x180063b39  mov     rdx, [rbp+4B0h+Token]; Token
0x180063b3d  xor     ecx, ecx; Thread
0x180063b3f  call    cs:__imp_SetThreadToken
0x180063b45  test    eax, eax
0x180063b47  jnz     loc_180063AA0
0x180063b4d  lea     r9, aUnableToImpers_3; "Unable to impersonate the client token "...
0x180063b54  mov     r8d, 28Ch
0x180063b5a  lea     rdx, aKerbcheckusern_0; "KerbCheckUserNameForCert"
0x180063b61  mov     ecx, 1
0x180063b66  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180063b6b  mov     ebx, 0C000010Dh
0x180063b70  jmp     loc_180063C04
0x180063b75  mov     rax, [rbp+4B0h+Credential]
0x180063b79  mov     r9d, 10000h; dwFindType
0x180063b7f  add     rax, 4
0x180063b83  mov     [rsp+4E0h+pPrevCertContext], 0; pPrevCertContext
0x180063b8c  mov     qword ptr [rbp+4B0h+pvFindPara+8], rax
0x180063b90  xor     r8d, r8d; dwFindFlags
0x180063b93  lea     rax, [rbp+4B0h+pvFindPara]
0x180063b97  mov     dword ptr [rbp+4B0h+pvFindPara], 14h
0x180063b9e  mov     edx, 10001h; dwCertEncodingType
0x180063ba3  mov     [rsp+4E0h+pvPara], rax; pvFindPara
0x180063ba8  mov     rcx, rsi; hCertStore
0x180063bab  call    cs:__imp_CertFindCertificateInStore
0x180063bb1  mov     rcx, [rbp+4B0h+var_488]
0x180063bb5  mov     [rcx], rax
0x180063bb8  test    rax, rax
0x180063bbb  jnz     short loc_180063BF3
0x180063bbd  mov     ebx, 8009030Eh
0x180063bc2  call    cs:__imp_GetLastError
0x180063bc8  lea     r9, aKerbcheckusern; "KerbCheckUserNameForCert failed to find"...
0x180063bcf  mov     r8d, 2B7h
0x180063bd5  lea     rdx, aKerbcheckusern_0; "KerbCheckUserNameForCert"
0x180063bdc  mov     dword ptr [rsp+4E0h+pvPara], eax
0x180063be0  mov     ecx, 1
0x180063be5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180063bea  lea     rcx, [rbp+4B0h+DestinationString]; struct _UNICODE_STRING *
0x180063bee  call    ?KerbReportCertificateStoreError@@YAXPEAU_UNICODE_STRING@@@Z; KerbReportCertificateStoreError(_UNICODE_STRING *)
0x180063bf3  xor     edx, edx; dwFlags
0x180063bf5  mov     rcx, rsi; hCertStore
0x180063bf8  call    cs:__imp_CertCloseStore
0x180063bfe  call    cs:__imp_RevertToSelf
0x180063c04  mov     rcx, [rbp+4B0h+Credential]; Buffer
0x180063c08  test    rcx, rcx
0x180063c0b  jz      short loc_180063C13
0x180063c0d  call    cs:__imp_CredFree
0x180063c13  mov     rcx, [rbp+4B0h+Token]; hObject
0x180063c17  test    rcx, rcx
0x180063c1a  jz      short loc_180063C22
0x180063c1c  call    cs:__imp_CloseHandle
0x180063c22  test    rdi, rdi
0x180063c25  jz      short loc_180063C40
0x180063c27  cmp     dword ptr [rdi-8], 70616548h
0x180063c2e  lea     rcx, [rdi-8]
0x180063c32  jnz     short loc_180063C40
0x180063c34  mov     rax, cs:g_pfnFree
0x180063c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c40  mov     eax, ebx
0x180063c42  mov     rcx, [rbp+4B0h+var_40]
0x180063c49  xor     rcx, rbp; StackCookie
0x180063c4c  call    __security_check_cookie
0x180063c51  mov     rbx, [rbp+4B0h+arg_8]
0x180063c58  lea     rsp, [rbp+480h]
0x180063c5f  pop     r15
0x180063c61  pop     r14
0x180063c63  pop     r13
0x180063c65  pop     r12
0x180063c67  pop     rdi
0x180063c68  pop     rsi
0x180063c69  pop     rbp
0x180063c6a  retn
```
