# Pku2uGetCertFromCred(_PKU2U_SECONDARY_CREDENTIAL *,_GUID const *,_UNICODE_STRING *)

- ea: `0x180020238`
- end: `0x180020956`
- name: `?Pku2uGetCertFromCred@@YAJPEAU_PKU2U_SECONDARY_CREDENTIAL@@PEBU_GUID@@PEAU_UNICODE_STRING@@@Z`
- size: `1822`
- prototype: `__int64 __fastcall(struct _PKU2U_SECONDARY_CREDENTIAL *, const struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x1800139e0`
- `0x180014ba0`
- `0x180014fe0`
- `0x180015fa0`
- `0x1800178d0`
- `0x180020238`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x18002e7a4`
- `0x18003b1f8`
- `0x180044cac`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002062a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002062a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002056f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002056f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208ce`
- `ntdll!RtlFreeUnicodeString` at `0x180020930`
- `ntdll!RtlFreeUnicodeString` at `0x18002093a`
- `ntdll!RtlFreeUnicodeString` at `0x180020930`
- `ntdll!RtlFreeUnicodeString` at `0x18002093a`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800208b0`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800208b0`
- `CRYPT32!CertOpenStore` at `0x180020503`
- `CRYPT32!CertOpenStore` at `0x180020503`
- `CRYPT32!CertFindCertificateInStore` at `0x180020534`
- `CRYPT32!CertFindCertificateInStore` at `0x180020534`
- `CRYPT32!CertFreeCertificateContext` at `0x1800208dd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800208ec`
- `CRYPT32!CertFreeCertificateContext` at `0x1800208dd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800208ec`
- `CRYPT32!CertCloseStore` at `0x18002057e`
- `CRYPT32!CertCloseStore` at `0x1800208fc`
- `CRYPT32!CertCloseStore` at `0x18002057e`
- `CRYPT32!CertCloseStore` at `0x1800208fc`
- `ext-ms-win-security-certpoleng-l1-1-0!PstAcquirePrivateKey` at `0x180020813`
- `ext-ms-win-security-certpoleng-l1-1-0!PstAcquirePrivateKey` at `0x180020813`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetNameIdentifierForCertificate` at `0x180020861`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstGetNameIdentifierForCertificate` at `0x180020861`

## pseudocode

```c
__int64 __fastcall Pku2uGetCertFromCred(
        struct _PKU2U_SECONDARY_CREDENTIAL *a1,
        const struct _GUID *a2,
        struct _UNICODE_STRING *a3)
{
  __int64 v4; // rdi
  void *v5; // r15
  unsigned __int16 v6; // r12
  __int64 v7; // rsi
  __int64 v8; // rbx
  unsigned int v9; // edx
  unsigned int v10; // ecx
  __int64 i; // r8
  __int16 v12; // cx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // ebx
  void *v22; // rcx
  int NameIdentifierForCertificate; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  HCERTSTORE v26; // rax
  HANDLE v27; // rbx
  DWORD LastError; // eax
  __int64 v29; // rdx
  void *v30; // rcx
  int v31; // eax
  __int64 v32; // r8
  int v33; // ebx
  PCCERT_CONTEXT v34; // rcx
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+30h] [rbp-39h] BYREF
  void *pvFindPara; // [rsp+38h] [rbp-31h] BYREF
  int v38[4]; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING v39; // [rsp+50h] [rbp-19h] BYREF
  int v40[4]; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp+7h] BYREF
  HANDLE hObject; // [rsp+D0h] [rbp+67h] BYREF
  WINBOOL IsMember; // [rsp+D8h] [rbp+6Fh] BYREF
  int v44; // [rsp+DCh] [rbp+73h]
  int v45; // [rsp+E0h] [rbp+77h] BYREF
  int v46; // [rsp+E4h] [rbp+7Bh]
  PCCERT_CONTEXT pCert; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = HIDWORD(a3);
  v44 = HIDWORD(a2);
  pCert = 0;
  pvFindPara = 0;
  hObject = 0;
  v4 = 0;
  v45 = 0;
  v5 = 0;
  IsMember = 0;
  v6 = 0;
  AuthData = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  UnicodeString = 0;
  if ( !a1 || !*((_DWORD *)a1 + 21) || *((_DWORD *)a1 + 8) || (v7 = *((_QWORD *)a1 + 3)) == 0 )
  {
    v21 = -1073741811;
    goto LABEL_95;
  }
  v8 = v7 + *(unsigned int *)(v7 + 76);
  v4 = v8 + *(unsigned int *)(v8 + 20);
  v6 = *(_WORD *)(v8 + 24);
  ((void (__fastcall *)(__int64, _QWORD, struct _UNICODE_STRING *))Pku2uGlobalLsaFunctions->LsaUnprotectMemory)(
    v4,
    v6,
    a3);
  v9 = 0;
  v10 = *(unsigned __int16 *)(v8 + 8);
  for ( i = v8 + *(unsigned int *)(v8 + 4); v9 < v10; ++v9 )
  {
    if ( *(_WORD *)(i + 2LL * v9) == 92 )
      break;
  }
  if ( v9 >= v10 )
  {
    *(_QWORD *)&v38[2] = v8 + *(unsigned int *)(v8 + 4);
    v12 = 2 * v10;
  }
  else
  {
    *(_QWORD *)&v38[2] = i + 2;
    v12 = 2 * (v10 - v9) - 2;
  }
  v13 = *(_QWORD *)(v4 + 4) - SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
  *(_OWORD *)v40 = *(_OWORD *)((char *)a1 + 104);
  LOWORD(v38[0]) = v12;
  HIWORD(v38[0]) = v12;
  if ( !v13 )
    v13 = *(_QWORD *)(v4 + 12) - *((_QWORD *)&SEC_WINNT_AUTH_DATA_TYPE_PASSWORD + 1);
  if ( !v13 )
    goto LABEL_60;
  v14 = *(_QWORD *)(v4 + 4) - SEC_WINNT_AUTH_DATA_TYPE_NGC;
  if ( !v14 )
    v14 = *(_QWORD *)(v4 + 12) + 0x75630B4BE43D7243LL;
  if ( !v14 )
    goto LABEL_60;
  v15 = *(_QWORD *)(v4 + 4) - SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT;
  if ( !v15 )
    v15 = *(_QWORD *)(v4 + 12) - *((_QWORD *)&SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT + 1);
  if ( !v15 )
  {
LABEL_60:
    if ( !Pku2uGlobalIdpExtTable )
    {
      v21 = -2146893042;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_2429819d036b3e2177922931f9f6578d_Traceguids);
      goto LABEL_95;
    }
    v21 = SspiHelperConstructAuthEx2FromStrings((int)v38, (int)v40, i, v6, (void *)v4, (__int64)&AuthData);
    if ( v21 < 0 )
      goto LABEL_95;
    v30 = *(void **)(v7 + 32);
    if ( (*(_BYTE *)(v7 + 56) & 2) != 0 )
    {
      NameIdentifierForCertificate = Pku2uImpersonateToken2(v30, &hObject, &v45);
      v21 = NameIdentifierForCertificate;
      if ( NameIdentifierForCertificate < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 55;
          goto LABEL_70;
        }
        goto LABEL_95;
      }
    }
    else
    {
      NameIdentifierForCertificate = Pku2uImpersonateToken(v30, &hObject, &v45);
      v21 = NameIdentifierForCertificate;
      if ( NameIdentifierForCertificate < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 56;
          goto LABEL_70;
        }
        goto LABEL_95;
      }
    }
    v31 = (*(__int64 (__fastcall **)(__int64, char *, PSEC_WINNT_AUTH_IDENTITY_OPAQUE, _QWORD, PCCERT_CONTEXT *))Pku2uGlobalIdpExtTable)(
            v7 + 24,
            (char *)a1 + 120,
            AuthData,
            *((unsigned int *)AuthData + 2),
            &pCert);
    v33 = v31;
    if ( v31 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v32, (unsigned int)v31);
      pCert = 0;
      if ( v33 == -1073741252 || v33 == -2146893039 || v33 == -1073741730 )
        goto LABEL_28;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_2429819d036b3e2177922931f9f6578d_Traceguids);
    }
LABEL_85:
    v17 = PstAcquirePrivateKey(pCert);
    if ( v17 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v20 = 66;
      goto LABEL_27;
    }
    Pku2uRevertImpersonation(hObject);
    v34 = pCert;
    *((_QWORD *)a1 + 20) = pCert;
    v45 = 0;
    pCert = 0;
    NameIdentifierForCertificate = IntPstGetNameIdentifierForCertificate(v34, &v39);
    v21 = NameIdentifierForCertificate;
    if ( NameIdentifierForCertificate >= 0 )
    {
      v21 = KerbDuplicateStringEx((struct _UNICODE_STRING *)((char *)a1 + 88), &v39, 1u, 0);
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = 67;
        goto LABEL_70;
      }
    }
    goto LABEL_95;
  }
  v16 = *(_QWORD *)(v4 + 4) - SEC_WINNT_AUTH_DATA_TYPE_CERT;
  if ( !v16 )
    v16 = *(_QWORD *)(v4 + 12) - *((_QWORD *)&SEC_WINNT_AUTH_DATA_TYPE_CERT + 1);
  if ( v16 )
    goto LABEL_85;
  v17 = ScHelperBuildCertContext(
          (BYTE *)(v4 + *(unsigned int *)(v4 + 20) + *(unsigned int *)(v4 + *(unsigned int *)(v4 + 20) + 4)),
          *(unsigned __int16 *)(v4 + *(unsigned int *)(v4 + 20) + 8),
          (const struct _CERT_CONTEXT **)&pvFindPara);
  if ( v17 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_28;
    v20 = 59;
LABEL_27:
    WPP_SF_Dd(v19[2], v20, v18, (unsigned int)v17);
LABEL_28:
    v21 = -2146893042;
    goto LABEL_95;
  }
  v22 = *(void **)(v7 + 32);
  if ( (*(_BYTE *)(v7 + 56) & 2) != 0 )
  {
    NameIdentifierForCertificate = Pku2uImpersonateToken2(v22, &hObject, &v45);
    v21 = NameIdentifierForCertificate;
    if ( NameIdentifierForCertificate >= 0 )
      goto LABEL_42;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v25 = 60;
LABEL_70:
      WPP_SF_d(
        v24[2],
        v25,
        &WPP_2429819d036b3e2177922931f9f6578d_Traceguids,
        (unsigned int)NameIdentifierForCertificate);
    }
  }
  else
  {
    NameIdentifierForCertificate = Pku2uImpersonateToken(v22, &hObject, &v45);
    v21 = NameIdentifierForCertificate;
    if ( NameIdentifierForCertificate >= 0 )
    {
      NameIdentifierForCertificate = Pku2uCheckTokenMembership(0, 0x12u, &IsMember);
      v21 = NameIdentifierForCertificate;
      if ( NameIdentifierForCertificate >= 0 )
      {
LABEL_42:
        while ( 1 )
        {
          v26 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, IsMember != 0 ? 180224 : 114688, L"My");
          v5 = v26;
          if ( !v26 )
            break;
          pCert = CertFindCertificateInStore(v26, 0x10001u, 0, 0xD0000u, pvFindPara, 0);
          if ( pCert )
            goto LABEL_85;
          if ( !IsMember )
          {
            v21 = -2146893042;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              LastError = GetLastError();
              v29 = 65;
LABEL_59:
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v29,
                &WPP_2429819d036b3e2177922931f9f6578d_Traceguids,
                LastError,
                -2146893042);
              goto LABEL_95;
            }
            goto LABEL_95;
          }
          v27 = hObject;
          if ( v45 )
          {
            Pku2uRevertImpersonation(hObject);
            v45 = 0;
          }
          if ( v27 )
          {
            CloseHandle(v27);
            hObject = 0;
          }
          CertCloseStore(v5, 0);
          IsMember = 0;
          v5 = 0;
          NameIdentifierForCertificate = Pku2uImpersonateToken2(*(void **)(v7 + 32), &hObject, &v45);
          v21 = NameIdentifierForCertificate;
          if ( NameIdentifierForCertificate < 0 )
          {
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v25 = 64;
              goto LABEL_70;
            }
            goto LABEL_95;
          }
        }
        v21 = -2146893042;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          v29 = 63;
          goto LABEL_59;
        }
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 62;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = 61;
        goto LABEL_70;
      }
    }
  }
LABEL_95:
  SspiFreeAuthIdentity(AuthData);
  if ( v45 )
    Pku2uRevertImpersonation(hObject);
  if ( hObject )
    CloseHandle(hObject);
  if ( pCert )
    CertFreeCertificateContext(pCert);
  if ( pvFindPara )
    CertFreeCertificateContext((PCCERT_CONTEXT)pvFindPara);
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( a1 && v4 && !*((_DWORD *)a1 + 8) )
    ((void (__fastcall *)(__int64, _QWORD))Pku2uGlobalLsaFunctions->LsaProtectMemory)(v4, v6);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v39);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180020238  mov     qword ptr [rsp-8+arg_10], r8
0x18002023d  mov     qword ptr [rsp-8+IsMember], rdx
0x180020242  push    rbp
0x180020243  push    rbx
0x180020244  push    rsi
0x180020245  push    rdi
0x180020246  push    r12
0x180020248  push    r13
0x18002024a  push    r14
0x18002024c  push    r15
0x18002024e  lea     rbp, [rsp-1Fh]
0x180020253  sub     rsp, 88h
0x18002025a  xor     r13d, r13d
0x18002025d  xorps   xmm0, xmm0
0x180020260  mov     [rbp+57h+pCert], r13
0x180020264  xorps   xmm1, xmm1
0x180020267  mov     [rbp+57h+pvFindPara], r13
0x18002026b  mov     r14, rcx
0x18002026e  mov     [rbp+57h+hObject], r13
0x180020272  mov     edi, r13d
0x180020275  mov     [rbp+57h+arg_10], r13d
0x180020279  mov     r15d, r13d
0x18002027c  mov     [rbp+57h+IsMember], r13d
0x180020280  mov     r12d, r13d
0x180020283  mov     [rbp+57h+AuthData], r13
0x180020287  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18002028b  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x18002028f  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180020293  test    rcx, rcx
0x180020296  jz      loc_1800208A7
0x18002029c  cmp     [rcx+54h], r13d
0x1800202a0  jz      loc_1800208A7
0x1800202a6  cmp     [rcx+20h], r13d
0x1800202aa  jnz     loc_1800208A7
0x1800202b0  mov     rsi, [rcx+18h]
0x1800202b4  test    rsi, rsi
0x1800202b7  jz      loc_1800208A7
0x1800202bd  mov     ebx, [rsi+4Ch]
0x1800202c0  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x1800202c7  add     rbx, rsi
0x1800202ca  mov     edi, [rbx+14h]
0x1800202cd  movzx   edx, word ptr [rbx+18h]
0x1800202d1  add     rdi, rbx
0x1800202d4  mov     rax, [rax+168h]
0x1800202db  mov     rcx, rdi
0x1800202de  movzx   r12d, dx
0x1800202e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202e7  mov     r8d, [rbx+4]
0x1800202eb  mov     edx, r13d
0x1800202ee  movzx   ecx, word ptr [rbx+8]
0x1800202f2  add     r8, rbx; int
0x1800202f5  test    ecx, ecx
0x1800202f7  jz      short loc_180020309
0x1800202f9  mov     eax, edx
0x1800202fb  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180020301  jz      short loc_180020309
0x180020303  inc     edx
0x180020305  cmp     edx, ecx
0x180020307  jb      short loc_1800202F9
0x180020309  cmp     edx, ecx
0x18002030b  jnb     short loc_180020321
0x18002030d  sub     cx, dx
0x180020310  lea     rax, [r8+2]
0x180020314  add     cx, cx
0x180020317  mov     qword ptr [rbp+57h+var_80+8], rax
0x18002031b  sub     cx, 2
0x18002031f  jmp     short loc_180020328
0x180020321  mov     qword ptr [rbp+57h+var_80+8], r8
0x180020325  add     cx, cx
0x180020328  movups  xmm0, xmmword ptr [r14+68h]
0x18002032d  mov     rax, [rdi+4]
0x180020331  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x180020338  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18002033d  mov     word ptr [rbp+57h+var_80], cx
0x180020341  mov     word ptr [rbp+57h+var_80+2], cx
0x180020345  jnz     short loc_180020352
0x180020347  mov     rax, [rdi+0Ch]
0x18002034b  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD+8
0x180020352  lea     rbx, WPP_GLOBAL_Control
0x180020359  test    rax, rax
0x18002035c  jz      loc_180020658
0x180020362  mov     rax, [rdi+4]
0x180020366  sub     rax, cs:SEC_WINNT_AUTH_DATA_TYPE_NGC
0x18002036d  jnz     short loc_18002037A
0x18002036f  mov     rax, [rdi+0Ch]
0x180020373  sub     rax, cs:qword_18004A120
0x18002037a  test    rax, rax
0x18002037d  jz      loc_180020658
0x180020383  mov     rax, [rdi+4]
0x180020387  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT
0x18002038e  jnz     short loc_18002039B
0x180020390  mov     rax, [rdi+0Ch]
0x180020394  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT+8
0x18002039b  test    rax, rax
0x18002039e  jz      loc_180020658
0x1800203a4  mov     rax, [rdi+4]
0x1800203a8  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_CERT
0x1800203af  jnz     short loc_1800203BC
0x1800203b1  mov     rax, [rdi+0Ch]
0x1800203b5  sub     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_CERT+8
0x1800203bc  test    rax, rax
0x1800203bf  jnz     loc_18002080F
0x1800203c5  mov     r8d, [rdi+14h]
0x1800203c9  add     r8, rdi
0x1800203cc  mov     ecx, [r8+4]
0x1800203d0  movzx   edx, word ptr [r8+8]; cbCertEncoded
0x1800203d5  add     rcx, r8; pbCertEncoded
0x1800203d8  lea     r8, [rbp+57h+pvFindPara]; struct _CERT_CONTEXT **
0x1800203dc  call    ?ScHelperBuildCertContext@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z; ScHelperBuildCertContext(uchar *,ulong,_CERT_CONTEXT const * *)
0x1800203e1  test    eax, eax
0x1800203e3  jns     short loc_180020412
0x1800203e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203ec  cmp     rcx, rbx
0x1800203ef  jz      short loc_180020408
0x1800203f1  test    byte ptr [rcx+1Ch], 2
0x1800203f5  jz      short loc_180020408
0x1800203f7  mov     edx, 3Bh ; ';'
0x1800203fc  mov     rcx, [rcx+10h]
0x180020400  mov     r9d, eax
0x180020403  call    WPP_SF_Dd
0x180020408  mov     ebx, 8009030Eh
0x18002040d  jmp     loc_1800208AC
0x180020412  test    byte ptr [rsi+38h], 2
0x180020416  lea     r8, [rbp+57h+arg_10]; int *
0x18002041a  mov     rcx, [rsi+20h]; TokenHandle
0x18002041e  lea     rdx, [rbp+57h+hObject]; void **
0x180020422  jz      short loc_18002045E
0x180020424  call    ?Pku2uImpersonateToken2@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken2(void *,void * *,int *)
0x180020429  mov     ebx, eax
0x18002042b  test    eax, eax
0x18002042d  jns     loc_1800204D5
0x180020433  mov     rcx, cs:WPP_GLOBAL_Control
0x18002043a  lea     rdx, WPP_GLOBAL_Control
0x180020441  cmp     rcx, rdx
0x180020444  jz      loc_1800208AC
0x18002044a  test    byte ptr [rcx+1Ch], 1
0x18002044e  jz      loc_1800208AC
0x180020454  mov     edx, 3Ch ; '<'
0x180020459  jmp     loc_18002070D
0x18002045e  call    ?Pku2uImpersonateToken@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken(void *,void * *,int *)
0x180020463  mov     ebx, eax
0x180020465  test    eax, eax
0x180020467  jns     short loc_180020494
0x180020469  mov     rcx, cs:WPP_GLOBAL_Control
0x180020470  lea     rdx, WPP_GLOBAL_Control
0x180020477  cmp     rcx, rdx
0x18002047a  jz      loc_1800208AC
0x180020480  test    byte ptr [rcx+1Ch], 1
0x180020484  jz      loc_1800208AC
0x18002048a  mov     edx, 3Dh ; '='
0x18002048f  jmp     loc_18002070D
0x180020494  lea     r8, [rbp+57h+IsMember]; IsMember
0x180020498  mov     edx, 12h; nSubAuthority0
0x18002049d  xor     ecx, ecx; TokenHandle
0x18002049f  call    ?Pku2uCheckTokenMembership@@YAJPEAXKPEAH@Z; Pku2uCheckTokenMembership(void *,ulong,int *)
0x1800204a4  mov     ebx, eax
0x1800204a6  test    eax, eax
0x1800204a8  jns     short loc_1800204D5
0x1800204aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204b1  lea     rdx, WPP_GLOBAL_Control
0x1800204b8  cmp     rcx, rdx
0x1800204bb  jz      loc_1800208AC
0x1800204c1  test    byte ptr [rcx+1Ch], 1
0x1800204c5  jz      loc_1800208AC
0x1800204cb  mov     edx, 3Eh ; '>'
0x1800204d0  jmp     loc_18002070D
0x1800204d5  mov     eax, [rbp+57h+IsMember]
0x1800204d8  mov     edx, 10001h; dwEncodingType
0x1800204dd  neg     eax
0x1800204df  lea     rax, aMy; "My"
0x1800204e6  sbb     r9d, r9d
0x1800204e9  mov     [rsp+0C0h+pvPara], rax; pvPara
0x1800204ee  xor     r8d, r8d; hCryptProv
0x1800204f1  and     r9d, 10000h
0x1800204f8  add     r9d, 1C000h; dwFlags
0x1800204ff  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180020503  call    cs:__imp_CertOpenStore
0x180020509  mov     r15, rax
0x18002050c  test    rax, rax
0x18002050f  jz      loc_180020604
0x180020515  mov     rcx, [rbp+57h+pvFindPara]
0x180020519  mov     r9d, 0D0000h; dwFindType
0x18002051f  mov     [rsp+0C0h+pPrevCertContext], r13; pPrevCertContext
0x180020524  xor     r8d, r8d; dwFindFlags
0x180020527  mov     [rsp+0C0h+pvPara], rcx; pvFindPara
0x18002052c  mov     edx, 10001h; dwCertEncodingType
0x180020531  mov     rcx, rax; hCertStore
0x180020534  call    cs:__imp_CertFindCertificateInStore
0x18002053a  mov     [rbp+57h+pCert], rax
0x18002053e  test    rax, rax
0x180020541  jnz     loc_180020808
0x180020547  cmp     [rbp+57h+IsMember], r13d
0x18002054b  jz      loc_1800205D1
0x180020551  mov     rbx, [rbp+57h+hObject]
0x180020555  cmp     [rbp+57h+arg_10], r13d
0x180020559  jz      short loc_180020567
0x18002055b  mov     rcx, rbx; Token
0x18002055e  call    ?Pku2uRevertImpersonation@@YAXPEAX@Z; Pku2uRevertImpersonation(void *)
0x180020563  mov     [rbp+57h+arg_10], r13d
0x180020567  test    rbx, rbx
0x18002056a  jz      short loc_180020579
0x18002056c  mov     rcx, rbx; hObject
0x18002056f  call    cs:__imp_CloseHandle
0x180020575  mov     [rbp+57h+hObject], r13
0x180020579  xor     edx, edx; dwFlags
0x18002057b  mov     rcx, r15; hCertStore
0x18002057e  call    cs:__imp_CertCloseStore
0x180020584  mov     [rbp+57h+IsMember], r13d
0x180020588  lea     r8, [rbp+57h+arg_10]; int *
0x18002058c  mov     rcx, [rsi+20h]; void *
0x180020590  lea     rdx, [rbp+57h+hObject]; void **
0x180020594  mov     r15, r13
0x180020597  call    ?Pku2uImpersonateToken2@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken2(void *,void * *,int *)
0x18002059c  mov     ebx, eax
0x18002059e  test    eax, eax
0x1800205a0  jns     loc_1800204D5
0x1800205a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205ad  lea     rdx, WPP_GLOBAL_Control
0x1800205b4  cmp     rcx, rdx
0x1800205b7  jz      loc_1800208AC
0x1800205bd  test    byte ptr [rcx+1Ch], 1
0x1800205c1  jz      loc_1800208AC
0x1800205c7  mov     edx, 40h ; '@'
0x1800205cc  jmp     loc_18002070D
0x1800205d1  mov     rax, cs:WPP_GLOBAL_Control
0x1800205d8  lea     rdx, WPP_GLOBAL_Control
0x1800205df  mov     ebx, 8009030Eh
0x1800205e4  cmp     rax, rdx
0x1800205e7  jz      loc_1800208AC
0x1800205ed  test    byte ptr [rax+1Ch], 2
0x1800205f1  jz      loc_1800208AC
0x1800205f7  call    cs:__imp_GetLastError
0x1800205fd  mov     edx, 41h ; 'A'
0x180020602  jmp     short loc_180020635
0x180020604  mov     rax, cs:WPP_GLOBAL_Control
0x18002060b  lea     rdx, WPP_GLOBAL_Control
0x180020612  mov     ebx, 8009030Eh
0x180020617  cmp     rax, rdx
0x18002061a  jz      loc_1800208AC
0x180020620  test    byte ptr [rax+1Ch], 2
0x180020624  jz      loc_1800208AC
0x18002062a  call    cs:__imp_GetLastError
0x180020630  mov     edx, 3Fh ; '?'
0x180020635  mov     rcx, cs:WPP_GLOBAL_Control
0x18002063c  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x180020643  mov     r9d, eax
0x180020646  mov     dword ptr [rsp+0C0h+pvPara], ebx
0x18002064a  mov     rcx, [rcx+10h]
0x18002064e  call    WPP_SF_dd
0x180020653  jmp     loc_1800208AC
0x180020658  cmp     cs:?Pku2uGlobalIdpExtTable@@3PEAU_LSA_IF_IDPROVEXT_FUNCTION_TABLE@@EA, r13; _LSA_IF_IDPROVEXT_FUNCTION_TABLE * Pku2uGlobalIdpExtTable
0x18002065f  jnz     short loc_1800206A1
0x180020661  mov     ebx, 8009030Eh
0x180020666  mov     rcx, cs:WPP_GLOBAL_Control
0x18002066d  lea     rdx, WPP_GLOBAL_Control
0x180020674  cmp     rcx, rdx
0x180020677  jz      loc_1800208AC
0x18002067d  test    byte ptr [rcx+1Ch], 4
0x180020681  jz      loc_1800208AC
0x180020687  mov     rcx, [rcx+10h]
0x18002068b  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x180020692  mov     edx, 36h ; '6'
0x180020697  call    WPP_SF_
0x18002069c  jmp     loc_1800208AC
0x1800206a1  lea     rax, [rbp+57h+AuthData]
0x1800206a5  movzx   r9d, r12w; int
0x1800206a9  mov     [rsp+0C0h+pPrevCertContext], rax; __int64
0x1800206ae  lea     rdx, [rbp+57h+var_60]; int
0x1800206b2  lea     rcx, [rbp+57h+var_80]; int
0x1800206b6  mov     [rsp+0C0h+pvPara], rdi; Src
0x1800206bb  call    SspiHelperConstructAuthEx2FromStrings
0x1800206c0  mov     ebx, eax
0x1800206c2  test    eax, eax
0x1800206c4  js      loc_1800208AC
0x1800206ca  test    byte ptr [rsi+38h], 2
0x1800206ce  lea     r8, [rbp+57h+arg_10]; int *
0x1800206d2  mov     rcx, [rsi+20h]; TokenHandle
0x1800206d6  lea     rdx, [rbp+57h+hObject]; void **
0x1800206da  jz      short loc_180020725
0x1800206dc  call    ?Pku2uImpersonateToken2@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken2(void *,void * *,int *)
0x1800206e1  mov     ebx, eax
0x1800206e3  test    eax, eax
0x1800206e5  jns     short loc_180020758
0x1800206e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206ee  lea     rdx, WPP_GLOBAL_Control
0x1800206f5  cmp     rcx, rdx
0x1800206f8  jz      loc_1800208AC
0x1800206fe  test    byte ptr [rcx+1Ch], 1
0x180020702  jz      loc_1800208AC
0x180020708  mov     edx, 37h ; '7'
0x18002070d  mov     rcx, [rcx+10h]
0x180020711  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x180020718  mov     r9d, eax
0x18002071b  call    WPP_SF_d
0x180020720  jmp     loc_1800208AC
0x180020725  call    ?Pku2uImpersonateToken@@YAJPEAXPEAPEAXPEAH@Z; Pku2uImpersonateToken(void *,void * *,int *)
0x18002072a  mov     ebx, eax
0x18002072c  test    eax, eax
0x18002072e  jns     short loc_180020758
0x180020730  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
