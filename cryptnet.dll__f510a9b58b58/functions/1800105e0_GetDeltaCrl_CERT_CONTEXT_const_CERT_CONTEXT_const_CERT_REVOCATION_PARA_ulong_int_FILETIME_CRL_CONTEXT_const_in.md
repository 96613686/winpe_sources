# GetDeltaCrl(_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,ulong,int,_FILETIME *,_CRL_CONTEXT const * *,int *,_CRL_CONTEXT const * *,ulong *)

- ea: `0x1800105e0`
- end: `0x180010af0`
- name: `?GetDeltaCrl@@YAHPEBU_CERT_CONTEXT@@0PEAU_CERT_REVOCATION_PARA@@KHPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH3PEAK@Z`
- size: `1296`
- prototype: `__int64 __fastcall(struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *, struct _CERT_REVOCATION_PARA *, unsigned int, int, struct _FILETIME *, const CRL_CONTEXT **pcbStructInfo, int *, const struct _CRL_CONTEXT **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f140`

## callees

- `0x18000a990`
- `0x18000fb70`
- `0x180010510`
- `0x1800105e0`
- `0x180010ba0`
- `0x180017d34`
- `0x1800262c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ac0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089f`
- `CRYPT32!CertFindExtension` at `0x180010657`
- `CRYPT32!CertFindExtension` at `0x1800106df`
- `CRYPT32!CertFindExtension` at `0x180010702`
- `CRYPT32!CertFindExtension` at `0x180010817`
- `CRYPT32!CertFindExtension` at `0x180010840`
- `CRYPT32!CertFindExtension` at `0x180010657`
- `CRYPT32!CertFindExtension` at `0x1800106df`
- `CRYPT32!CertFindExtension` at `0x180010702`
- `CRYPT32!CertFindExtension` at `0x180010817`
- `CRYPT32!CertFindExtension` at `0x180010840`
- `CRYPT32!CertFreeCRLContext` at `0x180010a69`
- `CRYPT32!CertFreeCRLContext` at `0x180010acb`
- `CRYPT32!CertFreeCRLContext` at `0x180010a69`
- `CRYPT32!CertFreeCRLContext` at `0x180010acb`
- `CRYPT32!CryptDecodeObject` at `0x180010887`
- `CRYPT32!CryptDecodeObject` at `0x18001098e`
- `CRYPT32!CryptDecodeObject` at `0x180010887`
- `CRYPT32!CryptDecodeObject` at `0x18001098e`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800108e9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180010942`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800108e9`
- `CRYPT32!CryptDecodeObjectEx` at `0x180010942`

## pseudocode

```c
__int64 __fastcall GetDeltaCrl(
        struct _CERT_CONTEXT *a1,
        const struct _CERT_CONTEXT *a2,
        struct _CERT_REVOCATION_PARA *a3,
        unsigned int a4,
        int a5,
        struct _FILETIME *a6,
        const CRL_CONTEXT **pcbStructInfo,
        int *a8,
        const struct _CRL_CONTEXT **a9,
        unsigned int *a10)
{
  _QWORD *v11; // rdi
  const CRL_CONTEXT *v14; // rbx
  PCRL_INFO pCrlInfo; // rdx
  const struct _CRL_CONTEXT *v17; // rcx
  __int64 v19; // rax
  struct _CERT_CONTEXT *v20; // rcx
  int TimeValidCrl; // eax
  int *v22; // r13
  void *v23; // rdx
  const char *v24; // rcx
  BOOL v25; // eax
  int v26; // ecx
  void *p_ThisUpdate; // rax
  DWORD cbSize; // eax
  unsigned int v29; // eax
  bool v30; // zf
  int v31; // [rsp+68h] [rbp-79h] BYREF
  PCCRL_CONTEXT pCrlContext; // [rsp+70h] [rbp-71h] BYREF
  void *Extension; // [rsp+78h] [rbp-69h]
  LPVOID ppvObject; // [rsp+80h] [rbp-61h] BYREF
  int v35; // [rsp+88h] [rbp-59h] BYREF
  int pvStructInfo; // [rsp+8Ch] [rbp-55h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-51h] BYREF
  HLOCAL v38; // [rsp+98h] [rbp-49h] BYREF
  DWORD v39; // [rsp+A0h] [rbp-41h] BYREF
  DWORD v40; // [rsp+A4h] [rbp-3Dh] BYREF
  __int128 v41; // [rsp+A8h] [rbp-39h] BYREF
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO pExtraInfo; // [rsp+B8h] [rbp-29h] BYREF

  v11 = pcbStructInfo;
  v14 = *pcbStructInfo;
  v41 = 0;
  pCrlContext = 0;
  pvStructInfo = 0;
  v35 = 0;
  LODWORD(pcbStructInfo) = 0;
  v40 = 0;
  v39 = 0;
  hMem = 0;
  v38 = 0;
  pCrlInfo = v14->pCrlInfo;
  v31 = 0;
  if ( CertFindExtension("1.3.6.1.5.5.7.48.1.1", pCrlInfo->cExtension, pCrlInfo->rgExtension) )
    goto LABEL_2;
  if ( CertFindExtension("2.5.29.46", v14->pCrlInfo->cExtension, v14->pCrlInfo->rgExtension) )
  {
    v19 = 5;
    *(_QWORD *)&v41 = a1;
    *((_QWORD *)&v41 + 1) = v14;
    v20 = (struct _CERT_CONTEXT *)&v41;
  }
  else
  {
    if ( !CertFindExtension("2.5.29.46", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension) )
    {
LABEL_2:
      v17 = pCrlContext;
      goto LABEL_3;
    }
    v19 = 4;
    v20 = a1;
  }
  Extension = v20;
  ppvObject = (LPVOID)v19;
  TimeValidCrl = GetTimeValidCrl((const char *)v19, v20, a1, a2, a3, 1, a4, 2, a6, (LPVOID *)&pCrlContext, &v31);
  v22 = a8;
  if ( TimeValidCrl )
  {
    *a8 = 1;
    goto LABEL_18;
  }
  v23 = Extension;
  v24 = (const char *)ppvObject;
  *a8 = 0;
  if ( (unsigned int)GetTimeValidCrl(v24, v23, a1, a2, a3, 1, a4, 3, a6, (LPVOID *)&pCrlContext, &v31) )
  {
LABEL_18:
    if ( (unsigned int)HasUnsupportedCrlCriticalExtension(pCrlContext)
      || (ppvObject = CertFindExtension("2.5.29.20", v14->pCrlInfo->cExtension, v14->pCrlInfo->rgExtension)) == 0
      || (Extension = CertFindExtension(
                        "2.5.29.27",
                        pCrlContext->pCrlInfo->cExtension,
                        pCrlContext->pCrlInfo->rgExtension)) == 0 )
    {
      SetLastError(0x80092012);
      goto LABEL_14;
    }
    LODWORD(pcbStructInfo) = 4;
    v25 = CryptDecodeObject(
            v14->dwCertEncodingType,
            (LPCSTR)0x1B,
            *((const BYTE **)ppvObject + 3),
            *((_DWORD *)ppvObject + 4),
            0,
            &pvStructInfo,
            (DWORD *)&pcbStructInfo);
    v31 = 0x7FFFFFFF;
    if ( !v25 )
    {
      if ( GetLastError() != -2146881276
        || !CryptDecodeObjectEx(
              v14->dwCertEncodingType,
              (LPCSTR)0x1C,
              *((const BYTE **)ppvObject + 3),
              *((_DWORD *)ppvObject + 4),
              0x8005u,
              &PkiDecodePara,
              &hMem,
              &v39) )
      {
        goto LABEL_14;
      }
      pvStructInfo = 0x7FFFFFFF;
    }
    if ( hMem )
    {
      if ( !CryptDecodeObjectEx(
              pCrlContext->dwCertEncodingType,
              (LPCSTR)0x1C,
              *((const BYTE **)Extension + 3),
              *((_DWORD *)Extension + 4),
              0x8005u,
              &PkiDecodePara,
              &v38,
              &v40) )
        goto LABEL_14;
      v26 = 0x7FFFFFFF;
      v35 = 0x7FFFFFFF;
    }
    else
    {
      LODWORD(pcbStructInfo) = 4;
      if ( !CryptDecodeObject(
              pCrlContext->dwCertEncodingType,
              (LPCSTR)0x1B,
              *((const BYTE **)Extension + 3),
              *((_DWORD *)Extension + 4),
              0,
              &v35,
              (DWORD *)&pcbStructInfo) )
        goto LABEL_14;
      v26 = v35;
      v31 = v35;
    }
    p_ThisUpdate = &pCrlContext->pCrlInfo->ThisUpdate;
    Extension = p_ThisUpdate;
    if ( hMem )
    {
      if ( (unsigned int)I_CertCompareIntegerBlob(hMem, v38) != -1 )
        goto LABEL_39;
      v26 = v31;
    }
    else if ( pvStructInfo >= v26 )
    {
      goto LABEL_40;
    }
    if ( a5 )
      goto LABEL_42;
    if ( (a4 & 2) != 0 )
      goto LABEL_42;
    pExtraInfo.pftCacheResync = (LPFILETIME)a3[1].hCrlStore;
    pExtraInfo.pChainPara = (PCERT_REVOCATION_CHAIN_PARA)a3[1].pftTimeToUse;
    pExtraInfo.pDeltaCrlIndicator = (PCRYPT_INTEGER_BLOB)v38;
    cbSize = a3[1].cbSize;
    pExtraInfo.iDeltaCrlIndicator = v26;
    ppvObject = 0;
    *(_OWORD *)&pExtraInfo.pLastSyncTime = 0;
    pExtraInfo.cbSize = 48;
    if ( !CryptGetTimeValidObject((LPCSTR)3, a1, a2, 0, 0x80000204, cbSize, &ppvObject, 0, &pExtraInfo) )
    {
LABEL_42:
      p_ThisUpdate = &v14->pCrlInfo->ThisUpdate;
      *v22 = 0;
LABEL_40:
      v29 = I_CryptSubtractFileTimes(*(_QWORD *)&a3[1].cCertStore, p_ThisUpdate);
      v30 = *(&a3[1].cbSize + 1) == 0;
      *a10 = v29;
      if ( !v30 )
        *v22 = LODWORD(a3[1].pIssuerCert) >= v29;
      goto LABEL_2;
    }
    CertFreeCRLContext(v14);
    *v11 = ppvObject;
LABEL_39:
    p_ThisUpdate = Extension;
    goto LABEL_40;
  }
LABEL_14:
  v17 = pCrlContext;
  if ( pCrlContext )
  {
    CertFreeCRLContext(pCrlContext);
    v17 = 0;
    pCrlContext = 0;
  }
  *v22 = 0;
LABEL_3:
  *a9 = v17;
  if ( hMem )
    operator delete(hMem);
  if ( v38 )
    operator delete(v38);
  return 1;
}

```

## disassembly

```asm
0x1800105e0  mov     rax, rsp
0x1800105e3  push    rbp
0x1800105e4  lea     rbp, [rax-2Fh]
0x1800105e8  sub     rsp, 100h
0x1800105ef  mov     [rax+8], rbx
0x1800105f3  xorps   xmm0, xmm0
0x1800105f6  mov     [rax+10h], rsi
0x1800105fa  mov     rsi, rcx
0x1800105fd  mov     [rax+18h], rdi
0x180010601  lea     rcx, Str2; "1.3.6.1.5.5.7.48.1.1"
0x180010608  mov     rdi, [rbp+27h+arg_30]
0x18001060c  mov     [rax-10h], r12
0x180010610  mov     r12, rdx
0x180010613  mov     [rax-18h], r13
0x180010617  mov     [rax-20h], r14
0x18001061b  mov     r14, r8
0x18001061e  mov     rbx, [rdi]
0x180010621  movups  [rbp+27h+var_60], xmm0
0x180010625  mov     [rax-28h], r15
0x180010629  xor     eax, eax
0x18001062b  mov     [rbp+27h+pCrlContext], rax
0x18001062f  mov     r15d, r9d
0x180010632  mov     [rbp+27h+var_7C], eax
0x180010635  mov     [rbp+27h+var_80], eax
0x180010638  mov     dword ptr [rbp+27h+arg_30], eax
0x18001063b  mov     [rbp+27h+var_64], eax
0x18001063e  mov     [rbp+27h+var_68], eax
0x180010641  mov     [rbp+27h+hMem], rax
0x180010645  mov     [rbp+27h+var_70], rax
0x180010649  mov     rdx, [rbx+18h]
0x18001064d  mov     [rbp+27h+var_A0], eax
0x180010650  mov     r8, [rdx+58h]; rgExtensions
0x180010654  mov     edx, [rdx+50h]; cExtensions
0x180010657  call    cs:__imp_CertFindExtension
0x18001065d  test    rax, rax
0x180010660  jz      short loc_1800106CD
0x180010662  mov     rcx, [rbp+27h+pCrlContext]
0x180010666  mov     rax, [rbp+27h+arg_40]
0x18001066a  mov     r15, [rsp+100h+var_20]
0x180010672  mov     r14, [rsp+100h+var_18]
0x18001067a  mov     r13, [rsp+100h+var_10]
0x180010682  mov     r12, [rsp+0F8h]
0x18001068a  mov     rdi, [rsp+100h+arg_10]
0x180010692  mov     rsi, [rsp+100h+arg_8]
0x18001069a  mov     rbx, [rsp+100h+arg_0]
0x1800106a2  mov     [rax], rcx
0x1800106a5  mov     rcx, [rbp+27h+hMem]; hMem
0x1800106a9  test    rcx, rcx
0x1800106ac  jnz     loc_180010ADC
0x1800106b2  mov     rcx, [rbp+27h+var_70]; hMem
0x1800106b6  test    rcx, rcx
0x1800106b9  jnz     loc_180010AE6
0x1800106bf  mov     eax, 1
0x1800106c4  add     rsp, 100h
0x1800106cb  pop     rbp
0x1800106cc  retn
0x1800106cd  mov     rdx, [rbx+18h]
0x1800106d1  lea     rcx, a252946; "2.5.29.46"
0x1800106d8  mov     r8, [rdx+58h]; rgExtensions
0x1800106dc  mov     edx, [rdx+50h]; cExtensions
0x1800106df  call    cs:__imp_CertFindExtension
0x1800106e5  test    rax, rax
0x1800106e8  jnz     short loc_18001071B
0x1800106ea  mov     rdx, [rsi+18h]
0x1800106ee  lea     rcx, a252946; "2.5.29.46"
0x1800106f5  mov     r8, [rdx+0C8h]; rgExtensions
0x1800106fc  mov     edx, [rdx+0C0h]; cExtensions
0x180010702  call    cs:__imp_CertFindExtension
0x180010708  test    rax, rax
0x18001070b  jz      loc_180010662
0x180010711  mov     eax, 4
0x180010716  mov     rcx, rsi
0x180010719  jmp     short loc_18001072C
0x18001071b  mov     eax, 5
0x180010720  mov     qword ptr [rbp+27h+var_60], rsi
0x180010724  mov     qword ptr [rbp+27h+var_60+8], rbx
0x180010728  lea     rcx, [rbp+27h+var_60]
0x18001072c  lea     rdx, [rbp+27h+var_A0]
0x180010730  mov     [rbp+27h+var_90], rcx
0x180010734  mov     [rsp+50h], rdx; int *
0x180010739  mov     r9, r12; struct _CERT_CONTEXT *
0x18001073c  lea     rdx, [rbp+27h+pCrlContext]
0x180010740  mov     [rbp+27h+ppvObject], rax
0x180010744  mov     [rsp+100h+var_B8], rdx; struct _CRL_CONTEXT **
0x180010749  mov     r8, rsi; struct _CERT_CONTEXT *
0x18001074c  mov     rdx, [rbp+27h+arg_28]
0x180010750  mov     [rsp+100h+pExtraInfo], rdx; struct _FILETIME *
0x180010755  mov     rdx, rcx; void *
0x180010758  mov     dword ptr [rsp+100h+pCredentials], 2; unsigned int
0x180010760  mov     rcx, rax; char *
0x180010763  mov     dword ptr [rsp+100h+pcbStructInfo], r15d; unsigned int
0x180010768  mov     dword ptr [rsp+100h+pvStructInfo], 1; int
0x180010770  mov     qword ptr [rsp+100h+dwFlags], r14; struct _CERT_REVOCATION_PARA *
0x180010775  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x18001077a  mov     r13, [rbp+27h+arg_38]
0x18001077e  test    eax, eax
0x180010780  jnz     short loc_1800107EC
0x180010782  mov     rdx, [rbp+27h+var_90]; void *
0x180010786  mov     r9, r12; struct _CERT_CONTEXT *
0x180010789  mov     rcx, [rbp+27h+ppvObject]; char *
0x18001078d  mov     r8, rsi; struct _CERT_CONTEXT *
0x180010790  mov     [r13+0], eax
0x180010794  lea     rax, [rbp+27h+var_A0]
0x180010798  mov     [rsp+50h], rax; int *
0x18001079d  lea     rax, [rbp+27h+pCrlContext]
0x1800107a1  mov     [rsp+100h+var_B8], rax; struct _CRL_CONTEXT **
0x1800107a6  mov     rax, [rbp+27h+arg_28]
0x1800107aa  mov     [rsp+100h+pExtraInfo], rax; struct _FILETIME *
0x1800107af  mov     dword ptr [rsp+100h+pCredentials], 3; unsigned int
0x1800107b7  mov     dword ptr [rsp+100h+pcbStructInfo], r15d; unsigned int
0x1800107bc  mov     dword ptr [rsp+100h+pvStructInfo], 1; int
0x1800107c4  mov     qword ptr [rsp+100h+dwFlags], r14; struct _CERT_REVOCATION_PARA *
0x1800107c9  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x1800107ce  test    eax, eax
0x1800107d0  jnz     short loc_1800107F4
0x1800107d2  mov     rcx, [rbp+27h+pCrlContext]; pCrlContext
0x1800107d6  test    rcx, rcx
0x1800107d9  jnz     loc_180010ACB
0x1800107df  mov     dword ptr [r13+0], 0
0x1800107e7  jmp     loc_180010666
0x1800107ec  mov     dword ptr [r13+0], 1
0x1800107f4  mov     rcx, [rbp+27h+pCrlContext]; struct _CRL_CONTEXT *
0x1800107f8  call    ?HasUnsupportedCrlCriticalExtension@@YAHPEBU_CRL_CONTEXT@@@Z; HasUnsupportedCrlCriticalExtension(_CRL_CONTEXT const *)
0x1800107fd  test    eax, eax
0x1800107ff  jnz     loc_180010ABB
0x180010805  mov     rdx, [rbx+18h]
0x180010809  lea     rcx, a252920; "2.5.29.20"
0x180010810  mov     r8, [rdx+58h]; rgExtensions
0x180010814  mov     edx, [rdx+50h]; cExtensions
0x180010817  call    cs:__imp_CertFindExtension
0x18001081d  mov     [rbp+27h+ppvObject], rax
0x180010821  test    rax, rax
0x180010824  jz      loc_180010ABB
0x18001082a  mov     rax, [rbp+27h+pCrlContext]
0x18001082e  lea     rcx, a252927; "2.5.29.27"
0x180010835  mov     rdx, [rax+18h]
0x180010839  mov     r8, [rdx+58h]; rgExtensions
0x18001083d  mov     edx, [rdx+50h]; cExtensions
0x180010840  call    cs:__imp_CertFindExtension
0x180010846  mov     [rbp+27h+var_90], rax
0x18001084a  test    rax, rax
0x18001084d  jz      loc_180010ABB
0x180010853  mov     r8, [rbp+27h+ppvObject]
0x180010857  lea     rax, [rbp+27h+arg_30]
0x18001085b  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x180010860  mov     edx, 1Bh; lpszStructType
0x180010865  mov     dword ptr [rbp+27h+arg_30], 4
0x18001086c  lea     rax, [rbp+27h+var_7C]
0x180010870  mov     ecx, [rbx]; dwCertEncodingType
0x180010872  mov     r9d, [r8+10h]; cbEncoded
0x180010876  mov     r8, [r8+18h]; pbEncoded
0x18001087a  mov     [rsp+100h+pvStructInfo], rax; pvStructInfo
0x18001087f  mov     [rsp+100h+dwFlags], 0; dwFlags
0x180010887  call    cs:__imp_CryptDecodeObject
0x18001088d  lea     rcx, PkiDecodePara
0x180010894  mov     [rbp+27h+var_A0], 7FFFFFFFh
0x18001089b  test    eax, eax
0x18001089d  jnz     short loc_180010905
0x18001089f  call    cs:__imp_GetLastError
0x1800108a5  cmp     eax, 80093104h
0x1800108aa  jnz     loc_1800107D2
0x1800108b0  mov     ecx, [rbx]; dwCertEncodingType
0x1800108b2  lea     rax, [rbp+27h+var_68]
0x1800108b6  mov     [rsp+100h+pCredentials], rax; pcbStructInfo
0x1800108bb  mov     edx, 1Ch; lpszStructType
0x1800108c0  lea     rax, [rbp+27h+hMem]
0x1800108c4  mov     [rsp+100h+pcbStructInfo], rax; pvStructInfo
0x1800108c9  lea     rax, PkiDecodePara
0x1800108d0  mov     [rsp+100h+pvStructInfo], rax; pDecodePara
0x1800108d5  mov     rax, [rbp+27h+ppvObject]
0x1800108d9  mov     [rsp+100h+dwFlags], 8005h; dwFlags
0x1800108e1  mov     r9d, [rax+10h]; cbEncoded
0x1800108e5  mov     r8, [rax+18h]; pbEncoded
0x1800108e9  call    cs:__imp_CryptDecodeObjectEx
0x1800108ef  test    eax, eax
0x1800108f1  jz      loc_1800107D2
0x1800108f7  mov     [rbp+27h+var_7C], 7FFFFFFFh
0x1800108fe  lea     rcx, PkiDecodePara
0x180010905  cmp     [rbp+27h+hMem], 0
0x18001090a  mov     r8, [rbp+27h+var_90]
0x18001090e  jz      short loc_18001095A
0x180010910  mov     r9d, [r8+10h]; cbEncoded
0x180010914  lea     rax, [rbp+27h+var_64]
0x180010918  mov     r8, [r8+18h]; pbEncoded
0x18001091c  mov     edx, 1Ch; lpszStructType
0x180010921  mov     [rsp+100h+pCredentials], rax; pcbStructInfo
0x180010926  lea     rax, [rbp+27h+var_70]
0x18001092a  mov     [rsp+100h+pcbStructInfo], rax; pvStructInfo
0x18001092f  mov     [rsp+100h+pvStructInfo], rcx; pDecodePara
0x180010934  mov     rcx, [rbp+27h+pCrlContext]
0x180010938  mov     [rsp+100h+dwFlags], 8005h; dwFlags
0x180010940  mov     ecx, [rcx]; dwCertEncodingType
0x180010942  call    cs:__imp_CryptDecodeObjectEx
0x180010948  test    eax, eax
0x18001094a  jz      loc_1800107D2
0x180010950  mov     ecx, 7FFFFFFFh
0x180010955  mov     [rbp+27h+var_80], ecx
0x180010958  jmp     short loc_1800109A2
0x18001095a  mov     rcx, [rbp+27h+pCrlContext]
0x18001095e  lea     rax, [rbp+27h+arg_30]
0x180010962  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x180010967  mov     edx, 1Bh; lpszStructType
0x18001096c  mov     dword ptr [rbp+27h+arg_30], 4
0x180010973  lea     rax, [rbp+27h+var_80]
0x180010977  mov     r9d, [r8+10h]; cbEncoded
0x18001097b  mov     ecx, [rcx]; dwCertEncodingType
0x18001097d  mov     r8, [r8+18h]; pbEncoded
0x180010981  mov     [rsp+100h+pvStructInfo], rax; pvStructInfo
0x180010986  mov     [rsp+100h+dwFlags], 0; dwFlags
0x18001098e  call    cs:__imp_CryptDecodeObject
0x180010994  test    eax, eax
0x180010996  jz      loc_1800107D2
0x18001099c  mov     ecx, [rbp+27h+var_80]
0x18001099f  mov     [rbp+27h+var_A0], ecx
0x1800109a2  mov     rax, [rbp+27h+pCrlContext]
0x1800109a6  mov     r8, [rbp+27h+hMem]
0x1800109aa  mov     rax, [rax+18h]
0x1800109ae  add     rax, 30h ; '0'
0x1800109b2  mov     [rbp+27h+var_90], rax
0x1800109b6  test    r8, r8
0x1800109b9  jnz     short loc_1800109C6
0x1800109bb  cmp     [rbp+27h+var_7C], ecx
0x1800109be  jge     loc_180010A7A
0x1800109c4  jmp     short loc_1800109DE
0x1800109c6  mov     rdx, [rbp+27h+var_70]
0x1800109ca  mov     rcx, r8
0x1800109cd  call    I_CertCompareIntegerBlob
0x1800109d2  cmp     eax, 0FFFFFFFFh
0x1800109d5  jnz     loc_180010A76
0x1800109db  mov     ecx, [rbp+27h+var_A0]
0x1800109de  cmp     [rbp+27h+arg_20], 0
0x1800109e2  jnz     loc_180010AA9
0x1800109e8  test    r15b, 2
0x1800109ec  jnz     loc_180010AA9
0x1800109f2  mov     rax, [r14+50h]
0x1800109f6  xorps   xmm0, xmm0
0x1800109f9  mov     [rbp+27h+var_50.pftCacheResync], rax
0x1800109fd  xor     r9d, r9d; pftValidFor
0x180010a00  mov     rax, [r14+58h]
0x180010a04  mov     r8, r12; pIssuer
0x180010a07  mov     [rbp+27h+var_50.pChainPara], rax
0x180010a0b  mov     rdx, rsi; pvPara
0x180010a0e  mov     rax, [rbp+27h+var_70]
0x180010a12  mov     [rbp+27h+var_50.pDeltaCrlIndicator], rax
0x180010a16  lea     rax, [rbp+27h+var_50]
0x180010a1a  mov     [rsp+100h+pExtraInfo], rax; pExtraInfo
0x180010a1f  lea     rax, [rbp+27h+ppvObject]
0x180010a23  mov     [rsp+100h+pCredentials], 0; pCredentials
0x180010a2c  mov     [rsp+100h+pcbStructInfo], rax; ppvObject
0x180010a31  mov     eax, [r14+30h]
0x180010a35  mov     [rbp+27h+var_50.iDeltaCrlIndicator], ecx
0x180010a38  mov     ecx, 3; pszTimeValidOid
0x180010a3d  mov     dword ptr [rsp+100h+pvStructInfo], eax; dwTimeout
0x180010a41  mov     [rsp+100h+dwFlags], 80000204h; dwFlags
0x180010a49  mov     [rbp+27h+ppvObject], 0
0x180010a51  movdqu  xmmword ptr [rbp+27h+var_50.pLastSyncTime], xmm0
0x180010a56  mov     [rbp+27h+var_50.cbSize], 30h ; '0'
0x180010a5d  call    CryptGetTimeValidObject
0x180010a62  test    eax, eax
0x180010a64  jz      short loc_180010AA9
0x180010a66  mov     rcx, rbx; pCrlContext
0x180010a69  call    cs:__imp_CertFreeCRLContext
0x180010a6f  mov     rax, [rbp+27h+ppvObject]
0x180010a73  mov     [rdi], rax
0x180010a76  mov     rax, [rbp+27h+var_90]
0x180010a7a  mov     rcx, [r14+40h]
0x180010a7e  mov     rdx, rax
0x180010a81  call    I_CryptSubtractFileTimes
0x180010a86  cmp     dword ptr [r14+34h], 0
0x180010a8b  mov     rcx, [rbp+27h+arg_48]
0x180010a8f  mov     [rcx], eax
0x180010a91  jz      loc_180010662
0x180010a97  xor     ecx, ecx
0x180010a99  cmp     [r14+38h], eax
0x180010a9d  setnb   cl
0x180010aa0  mov     [r13+0], ecx
0x180010aa4  jmp     loc_180010662
0x180010aa9  mov     rax, [rbx+18h]
0x180010aad  add     rax, 30h ; '0'
0x180010ab1  mov     dword ptr [r13+0], 0
0x180010ab9  jmp     short loc_180010A7A
0x180010abb  mov     ecx, 80092012h; dwErrCode
0x180010ac0  call    cs:__imp_SetLastError
0x180010ac6  jmp     loc_1800107D2
0x180010acb  call    cs:__imp_CertFreeCRLContext
0x180010ad1  xor     ecx, ecx
0x180010ad3  mov     [rbp+27h+pCrlContext], rcx
0x180010ad7  jmp     loc_1800107DF
0x180010adc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010ae1  jmp     loc_1800106B2
0x180010ae6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010aeb  jmp     loc_1800106BF
```
