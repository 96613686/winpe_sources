# CCertConfigPrivate::_AddRegistryConfigEntry(ushort const *,ushort const *,ushort const *,int,_CERT_CONTEXT const *,_CERT_CONTEXT const * *)

- ea: `0x18000baf4`
- end: `0x18000c07d`
- name: `?_AddRegistryConfigEntry@CCertConfigPrivate@@AEAAJPEBG00HPEBU_CERT_CONTEXT@@PEAPEBU2@@Z`
- size: `1417`
- prototype: `__int64 __fastcall(CCertConfigPrivate *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct _CERT_CONTEXT *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18000c15c`

## callees

- `0x18000a3c4`
- `0x18000b940`
- `0x18000b9cc`
- `0x18000baf4`
- `0x18000c084`
- `0x18000c5d8`
- `0x18001d5dc`
- `0x18001dcdc`
- `0x18001f314`
- `0x18001f46c`
- `0x1800200c0`
- `0x180020a6c`
- `0x180021438`
- `0x180026740`
- `0x180026a44`
- `0x180026b04`
- `0x18002746c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bde5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bde5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c000`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c00f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c02f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c00f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c02f`
- `CRYPT32!CertOpenStore` at `0x18000be8e`
- `CRYPT32!CertOpenStore` at `0x18000be8e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000bfe4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000bfe4`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c043`
- `CRYPT32!CertFreeCertificateContext` at `0x18000c043`
- `CRYPT32!CertCloseStore` at `0x18000c05a`
- `CRYPT32!CertCloseStore` at `0x18000c05a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bbff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bc0c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bc61`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bdb7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bf0f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bbff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bc0c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bc61`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bdb7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000bf0f`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000bd35`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18000bd35`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000bcfd`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18000bcfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CCertConfigPrivate::_AddRegistryConfigEntry(
        CCertConfigPrivate *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        struct _CERT_CONTEXT *a6,
        const struct _CERT_CONTEXT **a7)
{
  CCertConfigPrivate *v7; // rbx
  unsigned __int16 *v9; // r10
  unsigned __int16 *v10; // r15
  struct _CERT_CONTEXT *v11; // rsi
  int v12; // r12d
  int i; // edi
  int v14; // edx
  __int64 v15; // r14
  unsigned int IsConfigLocal; // eax
  unsigned int v17; // ebx
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  CCertConfigPrivate *v20; // r13
  __int64 v21; // rdi
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // eax
  const unsigned __int16 *v25; // r14
  int v26; // eax
  unsigned int v27; // ecx
  _WORD *v28; // rcx
  int CertRegStrValue; // eax
  int v30; // eax
  HKEY v31; // rbx
  unsigned int v32; // r14d
  unsigned int v33; // ecx
  int v34; // edx
  int v35; // r14d
  LSTATUS v36; // eax
  unsigned int v37; // eax
  void *v38; // rcx
  const unsigned __int16 *v39; // rcx
  int CARegHashCount; // eax
  unsigned int v41; // ecx
  int v42; // ebx
  HCERTSTORE v43; // rax
  unsigned int v44; // r8d
  PCERT_INFO pCertInfo; // rcx
  __int64 v46; // rcx
  _WORD *v47; // rcx
  const unsigned __int16 *v48; // r12
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned __int64 v51; // r14
  unsigned __int16 *v52; // rax
  unsigned __int16 *v53; // rbx
  void *v54; // rcx
  const struct _CERT_CONTEXT **v55; // rbx
  unsigned __int16 **lpData; // [rsp+20h] [rbp-60h]
  bool *v58; // [rsp+30h] [rbp-50h]
  int v59; // [rsp+40h] [rbp-40h]
  DWORD Type; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int16 *v61; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v63; // [rsp+58h] [rbp-28h] BYREF
  struct _CERT_CONTEXT *v64; // [rsp+60h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF
  HCERTSTORE hCertStore; // [rsp+70h] [rbp-10h]
  CCertConfigPrivate *cbData; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int16 *Src; // [rsp+C8h] [rbp+48h]
  PCNZWCH lpString1; // [rsp+D8h] [rbp+58h]

  lpString1 = a4;
  Src = a2;
  cbData = this;
  v7 = this;
  hCertStore = 0;
  v9 = a2;
  v61 = 0;
  v10 = 0;
  v64 = 0;
  v11 = 0;
  v63 = 0;
  hMem = 0;
  hKey = 0;
  if ( a7 )
    *a7 = 0;
  v12 = a5;
  for ( i = 0; ; ++i )
  {
    v14 = *((_DWORD *)v7 + 3);
    if ( i >= v14 )
    {
      v24 = CCertConfigPrivate::_ResizeCAInfo(v7, v14 + 1);
      v17 = v24;
      if ( !v24 )
      {
        v20 = cbData;
        v25 = lpString1;
        v21 = *(_QWORD *)cbData + 104LL * *((int *)cbData + 3);
        v26 = myFormConfigString(Src, lpString1, (unsigned __int16 **)(v21 + 56));
        v17 = v26;
        if ( v26 )
        {
          v27 = 56099521;
        }
        else
        {
          v26 = myDupString(v25, (unsigned __int16 **)v21);
          v17 = v26;
          if ( v26 )
          {
            v27 = 56296129;
          }
          else
          {
            v26 = mySanitizedNameToDSName(v25, (unsigned __int16 **)(v21 + 8));
            v17 = v26;
            if ( !v26 )
            {
              v59 = 0;
              *(_DWORD *)(v21 + 88) = v12 != 0 ? 20 : 12;
              goto LABEL_25;
            }
            v27 = 56623809;
          }
        }
        CSPrintErrorLineFile(v27, v26);
        goto LABEL_85;
      }
      v22 = v24;
      v23 = 55575233;
LABEL_14:
      CSPrintErrorLineFile(v23, v22);
      return v17;
    }
    Type = 0;
    v15 = 104LL * i;
    IsConfigLocal = _IsConfigLocal(*(const unsigned __int16 **)(v15 + *(_QWORD *)v7 + 56), v9, a3, 0, (int *)&Type);
    v17 = IsConfigLocal;
    if ( IsConfigLocal )
    {
      CSPrintErrorLineFile(0x105D019Au, IsConfigLocal);
      v22 = v17;
      v23 = 53740225;
      goto LABEL_14;
    }
    v7 = cbData;
    if ( Type )
    {
      if ( !v12 )
        *(_DWORD *)(v15 + *(_QWORD *)cbData + 88) |= 8u;
      if ( !(unsigned int)mylstrcmpNLSub(lpString1, *(const unsigned __int16 **)(v15 + *(_QWORD *)v7), -1, 1) )
        break;
    }
    v9 = Src;
  }
  v20 = cbData;
  v21 = v15 + *(_QWORD *)v7;
  v59 = 1;
  *(_DWORD *)(v21 + 88) |= 4u;
  if ( v12 )
    *(_DWORD *)(v21 + 88) |= 0x10u;
LABEL_25:
  v28 = *(_WORD **)(v21 + 80);
  if ( v28 && *v28 )
    goto LABEL_49;
  if ( !v12 )
  {
    CertRegStrValue = myGetCertRegStrValue(*(const unsigned __int16 **)v21, v18, v19, L"CADescription", &v61);
    if ( CertRegStrValue )
      CSPrintErrorLineFileData2(L"CADescription", 0x37F02C1u, CertRegStrValue, -2147024894);
    v10 = v61;
LABEL_43:
    if ( v10 )
    {
      v37 = mySanitizeName(v10, &v63);
      v17 = v37;
      if ( v37 )
      {
        v34 = v37;
        v33 = 62128833;
        goto LABEL_39;
      }
      v38 = *(void **)(v21 + 80);
      if ( v38 )
        LocalFree(v38);
      *(_QWORD *)(v21 + 80) = v63;
    }
LABEL_49:
    if ( !v12 )
    {
      v39 = *(const unsigned __int16 **)v21;
      LODWORD(cbData) = 0;
      CARegHashCount = myGetCARegHashCount(v39, (unsigned int)v18, (unsigned int *)&cbData);
      if ( CARegHashCount )
      {
        v41 = 63636161;
        goto LABEL_63;
      }
      v42 = (int)cbData;
      if ( (_DWORD)cbData )
      {
        LODWORD(cbData) = 0;
        v43 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"MY");
        hCertStore = v43;
        if ( !v43 )
        {
          v17 = myHLastError();
          v34 = v17;
          v33 = 64750273;
          goto LABEL_39;
        }
        myFindCACertByHashIndex(
          v43,
          *(const unsigned __int16 **)v21,
          v44,
          v42 - 1,
          (unsigned int *)&cbData,
          (const struct _CERT_CONTEXT **)&v64);
        v11 = v64;
LABEL_57:
        if ( v11 )
        {
          pCertInfo = v11->pCertInfo;
          v46 = (__int64)(v12 ? &pCertInfo->Issuer : &pCertInfo->Subject);
          CARegHashCount = ConfigLoadDNInfo(
                             *(const unsigned __int8 **)(v46 + 8),
                             *(_DWORD *)v46,
                             (struct _CERT_AUTHORITY_INFO *)v21);
          if ( CARegHashCount )
          {
            v41 = 65995457;
LABEL_63:
            CSPrintErrorLineFile(v41, CARegHashCount);
          }
        }
      }
      v47 = *(_WORD **)(v21 + 72);
      if ( !v47 || !*v47 )
      {
        v48 = lpString1;
        v49 = -1;
        v50 = -1;
        do
          ++v50;
        while ( lpString1[v50] );
        do
          ++v49;
        while ( Src[v49] );
        v51 = v49 + v50 + 6;
        v52 = (unsigned __int16 *)LocalAlloc(0, 2 * v51);
        v53 = v52;
        if ( !v52 )
        {
          v33 = 66978497;
          goto LABEL_38;
        }
        StringCchCopyW(v52, v51, Src);
        StringCchCatW(v53, v51, L"_");
        StringCchCatW(v53, v51, v48);
        StringCchCatW(v53, v51, L".crt");
        v54 = *(void **)(v21 + 72);
        if ( v54 )
          LocalFree(v54);
        *(_QWORD *)(v21 + 72) = v53;
      }
      v35 = v59;
      if ( !v59 )
        ++*((_DWORD *)v20 + 3);
      if ( v11 )
      {
        v55 = a7;
        if ( a7 )
          *v55 = CertDuplicateCertificateContext(v11);
      }
      v21 = 0;
      v17 = 0;
      goto LABEL_80;
    }
LABEL_56:
    v11 = a6;
    goto LABEL_57;
  }
  v30 = myRegOpenRelativeKey(Src, v18, (unsigned int)v19, (unsigned __int16 **)&hMem, lpData, &hKey, v58);
  if ( v30 )
  {
    CSPrintErrorLineFileData(L"CADescription", 0x38B02C1u, v30);
    goto LABEL_56;
  }
  v31 = hKey;
  LODWORD(cbData) = 0;
  Type = 0;
  if ( RegQueryValueExW(hKey, L"CADescription", 0, &Type, 0, (LPDWORD)&cbData) || Type != 1 || (unsigned int)cbData <= 2 )
    goto LABEL_56;
  v32 = (unsigned int)cbData >> 1;
  v10 = (unsigned __int16 *)LocalAlloc(0, 2LL * (((unsigned int)cbData >> 1) + 1));
  if ( !v10 )
  {
    v33 = 61014721;
LABEL_38:
    v34 = -2147024882;
    v17 = -2147024882;
    goto LABEL_39;
  }
  v36 = RegQueryValueExW(v31, L"CADescription", 0, &Type, (LPBYTE)v10, (LPDWORD)&cbData);
  v17 = v36;
  if ( !v36 )
  {
    v10[v32] = 0;
    goto LABEL_43;
  }
  v34 = v36;
  v33 = 61604545;
LABEL_39:
  CSPrintErrorLineFile(v33, v34);
  v35 = v59;
LABEL_80:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hMem )
    LocalFree(hMem);
  if ( !v35 )
  {
LABEL_85:
    if ( v21 )
      _CleanupCAInfo((struct _CERT_AUTHORITY_INFO *)v21);
  }
  if ( v10 )
    LocalFree(v10);
  if ( v11 && a6 != v11 )
    CertFreeCertificateContext(v11);
  if ( hCertStore )
    CertCloseStore(hCertStore, 2u);
  return v17;
}

```

## disassembly

```asm
0x18000baf4  mov     rax, rsp
0x18000baf7  mov     [rax+18h], rbx
0x18000bafb  mov     [rax+20h], r9
0x18000baff  mov     [rax+10h], rdx
0x18000bb03  mov     [rax+8], rcx
0x18000bb07  push    rbp
0x18000bb08  push    rsi
0x18000bb09  push    rdi
0x18000bb0a  push    r12
0x18000bb0c  push    r13
0x18000bb0e  push    r14
0x18000bb10  push    r15
0x18000bb12  mov     rbp, rsp
0x18000bb15  sub     rsp, 80h
0x18000bb1c  mov     rax, [rbp+arg_30]
0x18000bb20  mov     rbx, rcx
0x18000bb23  xor     ecx, ecx
0x18000bb25  mov     r13, r8
0x18000bb28  mov     [rbp+hCertStore], rcx
0x18000bb2c  mov     r10, rdx
0x18000bb2f  mov     [rbp+var_38], rcx
0x18000bb33  mov     r15d, ecx
0x18000bb36  mov     [rbp+var_20], rcx
0x18000bb3a  mov     esi, ecx
0x18000bb3c  mov     [rbp+var_28], rcx
0x18000bb40  mov     [rbp+hMem], rcx
0x18000bb44  mov     [rbp+hKey], rcx
0x18000bb48  test    rax, rax
0x18000bb4b  jz      short loc_18000BB50
0x18000bb4d  mov     [rax], rcx
0x18000bb50  mov     r12d, [rbp+arg_20]
0x18000bb54  mov     edi, ecx
0x18000bb56  mov     edx, [rbx+0Ch]
0x18000bb59  cmp     edi, edx
0x18000bb5b  jge     loc_18000BC17
0x18000bb61  mov     [rbp+Type], ecx
0x18000bb64  xor     r9d, r9d; unsigned __int16 **
0x18000bb67  mov     rcx, [rbx]
0x18000bb6a  mov     r8, r13; unsigned __int16 *
0x18000bb6d  movsxd  rax, edi
0x18000bb70  mov     rdx, r10; unsigned __int16 *
0x18000bb73  imul    r14, rax, 68h ; 'h'
0x18000bb77  lea     rax, [rbp+Type]
0x18000bb7b  mov     [rsp+80h+lpData], rax; int *
0x18000bb80  mov     rcx, [r14+rcx+38h]; Src
0x18000bb85  call    ?_IsConfigLocal@@YAJPEBG00PEAPEAGPEAH@Z; _IsConfigLocal(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x18000bb8a  xor     ecx, ecx
0x18000bb8c  mov     ebx, eax
0x18000bb8e  test    eax, eax
0x18000bb90  jnz     short loc_18000BBF8
0x18000bb92  mov     rbx, [rbp+cbData]
0x18000bb96  cmp     [rbp+Type], ecx
0x18000bb99  jz      short loc_18000BBC6
0x18000bb9b  test    r12d, r12d
0x18000bb9e  jnz     short loc_18000BBA9
0x18000bba0  mov     rax, [rbx]
0x18000bba3  or      dword ptr [r14+rax+58h], 8
0x18000bba9  mov     rdx, [rbx]
0x18000bbac  mov     r9b, 1; bool
0x18000bbaf  mov     rcx, [rbp+lpString1]; lpString1
0x18000bbb3  or      r8d, 0FFFFFFFFh; int
0x18000bbb7  mov     rdx, [r14+rdx]; unsigned __int16 *
0x18000bbbb  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18000bbc0  xor     ecx, ecx
0x18000bbc2  test    eax, eax
0x18000bbc4  jz      short loc_18000BBCE
0x18000bbc6  mov     r10, [rbp+Src]
0x18000bbca  inc     edi
0x18000bbcc  jmp     short loc_18000BB56
0x18000bbce  mov     rdi, [rbx]
0x18000bbd1  mov     r13, [rbp+cbData]
0x18000bbd5  add     rdi, r14
0x18000bbd8  xor     r14d, r14d
0x18000bbdb  mov     [rbp+var_40], 1
0x18000bbe2  or      dword ptr [rdi+58h], 4
0x18000bbe6  test    r12d, r12d
0x18000bbe9  jz      loc_18000BCB4
0x18000bbef  or      dword ptr [rdi+58h], 10h
0x18000bbf3  jmp     loc_18000BCB4
0x18000bbf8  mov     edx, ebx
0x18000bbfa  mov     ecx, 105D019Ah
0x18000bbff  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000bc05  mov     edx, ebx
0x18000bc07  mov     ecx, 33402C1h
0x18000bc0c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000bc12  jmp     loc_18000C060
0x18000bc17  inc     edx; int
0x18000bc19  mov     rcx, rbx; this
0x18000bc1c  call    ?_ResizeCAInfo@CCertConfigPrivate@@AEAAJJ@Z; CCertConfigPrivate::_ResizeCAInfo(long)
0x18000bc21  mov     ebx, eax
0x18000bc23  test    eax, eax
0x18000bc25  jz      short loc_18000BC30
0x18000bc27  mov     edx, eax
0x18000bc29  mov     ecx, 35002C1h
0x18000bc2e  jmp     short loc_18000BC0C
0x18000bc30  mov     r13, [rbp+cbData]
0x18000bc34  mov     r14, [rbp+lpString1]
0x18000bc38  mov     rcx, [rbp+Src]; unsigned __int16 *
0x18000bc3c  mov     rdx, r14; unsigned __int16 *
0x18000bc3f  movsxd  rax, dword ptr [r13+0Ch]
0x18000bc43  imul    rdi, rax, 68h ; 'h'
0x18000bc47  add     rdi, [r13+0]
0x18000bc4b  lea     r8, [rdi+38h]; unsigned __int16 **
0x18000bc4f  call    ?myFormConfigString@@YAJPEBG0PEAPEAG@Z; myFormConfigString(ushort const *,ushort const *,ushort * *)
0x18000bc54  mov     ebx, eax
0x18000bc56  test    eax, eax
0x18000bc58  jz      short loc_18000BC6C
0x18000bc5a  mov     ecx, 35802C1h
0x18000bc5f  mov     edx, eax
0x18000bc61  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000bc67  jmp     loc_18000C01A
0x18000bc6c  mov     rdx, rdi; unsigned __int16 **
0x18000bc6f  mov     rcx, r14; Src
0x18000bc72  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18000bc77  mov     ebx, eax
0x18000bc79  test    eax, eax
0x18000bc7b  jz      short loc_18000BC84
0x18000bc7d  mov     ecx, 35B02C1h
0x18000bc82  jmp     short loc_18000BC5F
0x18000bc84  lea     rdx, [rdi+8]; unsigned __int16 **
0x18000bc88  mov     rcx, r14; unsigned __int16 *
0x18000bc8b  call    ?mySanitizedNameToDSName@@YAJPEBGPEAPEAG@Z; mySanitizedNameToDSName(ushort const *,ushort * *)
0x18000bc90  xor     r14d, r14d
0x18000bc93  mov     ebx, eax
0x18000bc95  test    eax, eax
0x18000bc97  jz      short loc_18000BCA0
0x18000bc99  mov     ecx, 36002C1h
0x18000bc9e  jmp     short loc_18000BC5F
0x18000bca0  mov     eax, r12d
0x18000bca3  mov     [rbp+var_40], r14d
0x18000bca7  neg     eax
0x18000bca9  sbb     ecx, ecx
0x18000bcab  and     ecx, 8
0x18000bcae  add     ecx, 0Ch
0x18000bcb1  mov     [rdi+58h], ecx
0x18000bcb4  mov     rcx, [rdi+50h]
0x18000bcb8  test    rcx, rcx
0x18000bcbb  jz      short loc_18000BCC7
0x18000bcbd  cmp     r14w, [rcx]
0x18000bcc1  jnz     loc_18000BE3C
0x18000bcc7  test    r12d, r12d
0x18000bcca  jnz     short loc_18000BD0C
0x18000bccc  mov     rcx, [rdi]; unsigned __int16 *
0x18000bccf  lea     rax, [rbp+var_38]
0x18000bcd3  lea     r9, ValueName; "CADescription"
0x18000bcda  mov     [rsp+80h+lpData], rax; unsigned __int16 **
0x18000bcdf  call    ?myGetCertRegStrValue@@YAJPEBG000PEAPEAG@Z; myGetCertRegStrValue(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18000bce4  test    eax, eax
0x18000bce6  jz      short loc_18000BD03
0x18000bce8  mov     r9d, 80070002h
0x18000bcee  lea     rcx, ValueName; "CADescription"
0x18000bcf5  mov     r8d, eax
0x18000bcf8  mov     edx, 37F02C1h
0x18000bcfd  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000bd03  mov     r15, [rbp+var_38]
0x18000bd07  jmp     loc_18000BE05
0x18000bd0c  mov     rcx, [rbp+Src]; Src
0x18000bd10  lea     rax, [rbp+hKey]
0x18000bd14  lea     r9, [rbp+hMem]; unsigned __int16 **
0x18000bd18  mov     [rsp+80h+lpcbData], rax; HKEY *
0x18000bd1d  call    ?myRegOpenRelativeKey@@YAJPEBG0KPEAPEAG1PEAPEAUHKEY__@@PEA_N@Z; myRegOpenRelativeKey(ushort const *,ushort const *,ulong,ushort * *,ushort * *,HKEY__ * *,bool *)
0x18000bd22  test    eax, eax
0x18000bd24  jz      short loc_18000BD40
0x18000bd26  mov     r8d, eax
0x18000bd29  lea     rcx, ValueName; "CADescription"
0x18000bd30  mov     edx, 38B02C1h
0x18000bd35  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18000bd3b  jmp     loc_18000BEDA
0x18000bd40  mov     rbx, [rbp+hKey]
0x18000bd44  lea     rax, [rbp+cbData]
0x18000bd48  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18000bd4d  lea     r9, [rbp+Type]; lpType
0x18000bd51  mov     rcx, rbx; hKey
0x18000bd54  mov     [rsp+80h+lpData], r14; lpData
0x18000bd59  xor     r8d, r8d; lpReserved
0x18000bd5c  mov     dword ptr [rbp+cbData], r14d
0x18000bd60  lea     rdx, ValueName; "CADescription"
0x18000bd67  mov     [rbp+Type], r14d
0x18000bd6b  call    cs:__imp_RegQueryValueExW
0x18000bd71  test    eax, eax
0x18000bd73  jnz     loc_18000BEDA
0x18000bd79  cmp     [rbp+Type], 1
0x18000bd7d  jnz     loc_18000BEDA
0x18000bd83  mov     r14d, dword ptr [rbp+cbData]
0x18000bd87  cmp     r14d, 2
0x18000bd8b  jbe     loc_18000BED7
0x18000bd91  shr     r14d, 1
0x18000bd94  xor     ecx, ecx; uFlags
0x18000bd96  lea     edx, [r14+1]
0x18000bd9a  add     rdx, rdx; uBytes
0x18000bd9d  call    cs:__imp_LocalAlloc
0x18000bda3  mov     r15, rax
0x18000bda6  test    rax, rax
0x18000bda9  jnz     short loc_18000BDC6
0x18000bdab  mov     ecx, 3A302C1h
0x18000bdb0  mov     edx, 8007000Eh
0x18000bdb5  mov     ebx, edx
0x18000bdb7  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000bdbd  mov     r14d, [rbp+var_40]
0x18000bdc1  jmp     loc_18000BFF4
0x18000bdc6  lea     rax, [rbp+cbData]
0x18000bdca  xor     r8d, r8d; lpReserved
0x18000bdcd  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18000bdd2  lea     r9, [rbp+Type]; lpType
0x18000bdd6  lea     rdx, ValueName; "CADescription"
0x18000bddd  mov     [rsp+80h+lpData], r15; lpData
0x18000bde2  mov     rcx, rbx; hKey
0x18000bde5  call    cs:__imp_RegQueryValueExW
0x18000bdeb  mov     ebx, eax
0x18000bded  test    eax, eax
0x18000bdef  jz      short loc_18000BDFA
0x18000bdf1  mov     edx, eax
0x18000bdf3  mov     ecx, 3AC02C1h
0x18000bdf8  jmp     short loc_18000BDB7
0x18000bdfa  mov     ecx, r14d
0x18000bdfd  xor     r14d, r14d
0x18000be00  mov     [r15+rcx*2], r14w
0x18000be05  test    r15, r15
0x18000be08  jz      short loc_18000BE3C
0x18000be0a  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000be0e  mov     rcx, r15; unsigned __int16 *
0x18000be11  call    ?mySanitizeName@@YAJPEBGPEAPEAG@Z; mySanitizeName(ushort const *,ushort * *)
0x18000be16  mov     ebx, eax
0x18000be18  test    eax, eax
0x18000be1a  jz      short loc_18000BE25
0x18000be1c  mov     edx, eax
0x18000be1e  mov     ecx, 3B402C1h
0x18000be23  jmp     short loc_18000BDB7
0x18000be25  mov     rcx, [rdi+50h]; hMem
0x18000be29  test    rcx, rcx
0x18000be2c  jz      short loc_18000BE34
0x18000be2e  call    cs:__imp_LocalFree
0x18000be34  mov     rax, [rbp+var_28]
0x18000be38  mov     [rdi+50h], rax
0x18000be3c  test    r12d, r12d
0x18000be3f  jnz     loc_18000BEDA
0x18000be45  mov     rcx, [rdi]; unsigned __int16 *
0x18000be48  lea     r8, [rbp+cbData]; unsigned int *
0x18000be4c  mov     dword ptr [rbp+cbData], r14d
0x18000be50  call    ?myGetCARegHashCount@@YAJPEBGKPEAK@Z; myGetCARegHashCount(ushort const *,ulong,ulong *)
0x18000be55  test    eax, eax
0x18000be57  jz      short loc_18000BE63
0x18000be59  mov     ecx, 3CB02C1h
0x18000be5e  jmp     loc_18000BF0D
0x18000be63  mov     ebx, dword ptr [rbp+cbData]
0x18000be66  test    ebx, ebx
0x18000be68  jz      loc_18000BF15
0x18000be6e  xor     r8d, r8d; hCryptProv
0x18000be71  mov     dword ptr [rbp+cbData], r14d
0x18000be75  lea     rax, aMy; "MY"
0x18000be7c  mov     r9d, 28000h; dwFlags
0x18000be82  mov     [rsp+80h+lpData], rax; pvPara
0x18000be87  lea     edx, [r8+1]; dwEncodingType
0x18000be8b  lea     ecx, [rdx+9]; lpszStoreProvider
0x18000be8e  call    cs:__imp_CertOpenStore
0x18000be94  mov     [rbp+hCertStore], rax
0x18000be98  test    rax, rax
0x18000be9b  jnz     short loc_18000BEB0
0x18000be9d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18000bea2  mov     ebx, eax
0x18000bea4  mov     edx, eax
0x18000bea6  mov     ecx, 3DC02C1h
0x18000beab  jmp     loc_18000BDB7
0x18000beb0  mov     rdx, [rdi]; unsigned __int16 *
0x18000beb3  lea     rcx, [rbp+var_20]
0x18000beb7  mov     [rsp+80h+lpcbData], rcx; struct _CERT_CONTEXT **
0x18000bebc  lea     r9d, [rbx-1]; unsigned int
0x18000bec0  lea     rcx, [rbp+cbData]
0x18000bec4  mov     [rsp+80h+lpData], rcx; unsigned int *
0x18000bec9  mov     rcx, rax; void *
0x18000becc  call    ?myFindCACertByHashIndex@@YAJPEAXPEBGKKPEAKPEAPEBU_CERT_CONTEXT@@@Z; myFindCACertByHashIndex(void *,ushort const *,ulong,ulong,ulong *,_CERT_CONTEXT const * *)
0x18000bed1  mov     rsi, [rbp+var_20]
0x18000bed5  jmp     short loc_18000BEDE
0x18000bed7  xor     r14d, r14d
0x18000beda  mov     rsi, [rbp+arg_28]
0x18000bede  test    rsi, rsi
0x18000bee1  jz      short loc_18000BF15
0x18000bee3  mov     rcx, [rsi+18h]
0x18000bee7  test    r12d, r12d
0x18000beea  jnz     short loc_18000BEF2
0x18000beec  add     rcx, 50h ; 'P'
0x18000bef0  jmp     short loc_18000BEF6
0x18000bef2  add     rcx, 30h ; '0'
0x18000bef6  mov     edx, [rcx]; unsigned int
0x18000bef8  mov     r8, rdi; struct _CERT_AUTHORITY_INFO *
0x18000befb  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000beff  call    ?ConfigLoadDNInfo@@YAJPEBEKPEAU_CERT_AUTHORITY_INFO@@@Z; ConfigLoadDNInfo(uchar const *,ulong,_CERT_AUTHORITY_INFO *)
0x18000bf04  test    eax, eax
0x18000bf06  jz      short loc_18000BF15
0x18000bf08  mov     ecx, 3EF02C1h
0x18000bf0d  mov     edx, eax
0x18000bf0f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000bf15  mov     rcx, [rdi+48h]
0x18000bf19  test    rcx, rcx
0x18000bf1c  jz      short loc_18000BF28
0x18000bf1e  cmp     r14w, [rcx]
0x18000bf22  jnz     loc_18000BFC4
0x18000bf28  mov     r12, [rbp+lpString1]
0x18000bf2c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf30  mov     rax, rcx
  ... truncated ...
```
