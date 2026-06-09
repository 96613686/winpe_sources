# InitCmsRecipientEncodeInfo

- ea: `0x1800aed78`
- end: `0x1800af409`
- name: `InitCmsRecipientEncodeInfo`
- size: `1681`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800aecc0`
- `0x1800cc41c`

## callees

- `0x180009da0`
- `0x180028d60`
- `0x18004d730`
- `0x1800600e0`
- `0x1800aed78`
- `0x1800bf63c`
- `0x180111238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af3e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af3e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aeede`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aef0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aef42`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aefd5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af104`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af1fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af22b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aeede`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aef0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aef42`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800aefd5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af104`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af1fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800af22b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af042`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af079`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af0b0`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af042`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af079`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800af0b0`

## string_xrefs

- `0x1800aeeec`: `Composite-ML-KEM`

## pseudocode

```c
char *__fastcall InitCmsRecipientEncodeInfo(__int64 a1, unsigned int a2, PCCERT_CONTEXT *a3, char a4)
{
  __int64 v4; // rsi
  PCCERT_CONTEXT *v5; // r13
  char *v6; // rbp
  DWORD v7; // ecx
  SIZE_T v8; // rcx
  int v9; // r12d
  unsigned int v10; // ebx
  char *v11; // rax
  char *v12; // r14
  __int64 v13; // rbx
  int v14; // r15d
  PCCRYPT_OID_INFO OIDInfo; // rax
  PCCRYPT_OID_INFO v16; // r12
  DWORD dwValue; // r13d
  const wchar_t *v18; // rcx
  WCHAR *v19; // rdi
  PCCRYPT_OID_INFO v20; // rax
  PCCRYPT_OID_INFO v21; // rdi
  DWORD v22; // r15d
  char *v23; // r12
  const char *v24; // rax
  BYTE *pbData; // rax
  const char *v26; // rdx
  char *v27; // r13
  _QWORD *v28; // rdi
  _QWORD *v29; // r15
  char *v30; // rcx
  PCERT_INFO v31; // rdx
  CERT_NAME_BLOB *v32; // rax
  int v34; // [rsp+30h] [rbp-88h]
  PCERT_INFO pCertInfo; // [rsp+38h] [rbp-80h]
  char *v36; // [rsp+40h] [rbp-78h]
  char *v37; // [rsp+48h] [rbp-70h]
  _QWORD *v38; // [rsp+50h] [rbp-68h]
  _QWORD *v39; // [rsp+58h] [rbp-60h]
  char *pvData; // [rsp+60h] [rbp-58h]
  PCNZWCH lpString1; // [rsp+68h] [rbp-50h] BYREF
  int v43; // [rsp+C8h] [rbp+10h]
  PCCERT_CONTEXT *v44; // [rsp+D0h] [rbp+18h]
  int v45; // [rsp+D8h] [rbp+20h]

  v44 = a3;
  v4 = a2;
  v5 = a3;
  if ( a2 > 0xFFFFF )
  {
    v6 = 0;
    v7 = 534;
    goto LABEL_63;
  }
  v8 = a2 << 9;
  v9 = a4 & 4;
  v45 = v9;
  if ( (a4 & 4) != 0 )
    v8 = 532 * a2;
  v10 = v8;
  v11 = (char *)PkiAlloc(v8);
  v6 = v11;
  if ( v11 )
  {
    pvData = 0;
    memset_0(v11, 0, v10);
    v36 = v6;
    v12 = &v6[16 * v4];
    v13 = (__int64)&v12[160 * v4 + 112 * v4];
    v37 = &v12[112 * v4];
    v38 = (_QWORD *)(v13 + (v4 << 7));
    v39 = &v38[v4];
    if ( v9 )
      pvData = (char *)&v38[11 * v4 + v4];
    if ( (_DWORD)v4 )
    {
      while ( 1 )
      {
        v14 = 0;
        v43 = 0;
        v34 = 0;
        pCertInfo = (*v5)->pCertInfo;
        OIDInfo = CryptFindOIDInfo(0x40000001u, pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId, 0x40000003u);
        v16 = OIDInfo;
        if ( OIDInfo )
        {
          dwValue = OIDInfo->dwValue;
          if ( dwValue == -3 )
          {
            v18 = *(const wchar_t **)&OIDInfo[1].cbSize;
            lpString1 = 0;
            if ( (unsigned int)I_CryptExtractFromParameterSetAlgorithmName(v18, (HLOCAL *)&lpString1, 0) )
            {
              v19 = (WCHAR *)lpString1;
              if ( CompareStringW(0x409u, 1u, lpString1, -1, L"ML-KEM", -1) == 2
                || CompareStringW(0x409u, 1u, v19, -1, L"Composite-ML-KEM", -1) == 2 )
              {
                v43 = 1;
                if ( CompareStringW(0x409u, 1u, *(PCNZWCH *)&v16[1].cbSize, -1, L"ML-KEM:512", -1) == 2 )
                  v14 = 1;
                v34 = v14;
              }
              PkiDefaultCryptFree(v19);
            }
          }
        }
        else
        {
          dwValue = 0;
        }
        v20 = CryptFindOIDInfo(1u, *(void **)(a1 + 16), 0x40000002u);
        v21 = v20;
        v22 = v20 ? v20->dwValue : 0;
        if ( dwValue - 43521 <= 1 )
          break;
        if ( v16 && CompareStringW(0x409u, 1u, *(PCNZWCH *)&v16[1].cbSize, -1, L"CryptOIDInfoECCParameters", -1) == 2 )
        {
          v23 = v36;
          *(_DWORD *)v36 = 2;
          *((_QWORD *)v36 + 1) = v13;
          *(_QWORD *)(v13 + 8) = "1.3.133.16.840.63.0.2";
          *(_QWORD *)(v13 + 40) = "2.16.840.1.101.3.4.1.45";
          *(_DWORD *)v13 = 128;
          if ( v22 - 26114 > 1 )
          {
            if ( CompareStringA(0x409u, 1u, v21->pszOID, -1, "2.16.840.1.101.3.4.1.2", -1) == 2 )
            {
              v24 = "2.16.840.1.101.3.4.1.5";
              goto LABEL_51;
            }
            if ( CompareStringA(0x409u, 1u, v21->pszOID, -1, "2.16.840.1.101.3.4.1.22", -1) == 2 )
            {
              v24 = "2.16.840.1.101.3.4.1.25";
              goto LABEL_51;
            }
            if ( CompareStringA(0x409u, 1u, v21->pszOID, -1, "2.16.840.1.101.3.4.1.42", -1) == 2 )
            {
              v24 = "2.16.840.1.101.3.4.1.45";
              goto LABEL_51;
            }
          }
          goto LABEL_54;
        }
        if ( !v43 )
        {
          *(_DWORD *)v36 = 1;
          *((_QWORD *)v36 + 1) = v12;
          *(_DWORD *)v12 = 112;
          if ( v21
            && CompareStringW(0x409u, 1u, *(PCNZWCH *)&v21[1].cbSize, -1, L"AES", -1) == 2
            && v16
            && CompareStringW(0x409u, 1u, *(PCNZWCH *)&v16[1].cbSize, -1, L"RSA", -1) == 2 )
          {
            v31 = pCertInfo;
            *((_QWORD *)v12 + 1) = "1.2.840.113549.1.1.7";
          }
          else
          {
            v31 = pCertInfo;
            *(_OWORD *)(v12 + 8) = *(_OWORD *)&pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId;
            *((_QWORD *)v12 + 3) = pCertInfo->SubjectPublicKeyInfo.Algorithm.Parameters.pbData;
          }
          v28 = v39;
          v30 = v12 + 72;
          v29 = v38;
          v23 = v36;
          *((_OWORD *)v12 + 3) = *(_OWORD *)&v31->SubjectPublicKeyInfo.PublicKey.cbData;
          *((_QWORD *)v12 + 8) = *(_QWORD *)&v31->SubjectPublicKeyInfo.PublicKey.cUnusedBits;
          goto LABEL_55;
        }
        if ( !v21
          || CompareStringW(0x409u, 1u, *(PCNZWCH *)&v21[1].cbSize, -1, L"AES", -1) != 2
          || (v21->ExtraInfo.cbData & 0xFFFFFFFC) < 4 )
        {
LABEL_62:
          v7 = -2147024809;
LABEL_63:
          SetLastError(v7);
          goto LABEL_64;
        }
        pbData = v21->ExtraInfo.pbData;
        if ( *(_DWORD *)pbData == 128 )
        {
          if ( !v34 )
            goto LABEL_62;
          v26 = "2.16.840.1.101.3.4.1.5";
        }
        else
        {
          if ( *(_DWORD *)pbData != 256 )
            goto LABEL_62;
          v26 = "2.16.840.1.101.3.4.1.45";
        }
        v27 = v37;
        v23 = v36;
        v28 = v39;
        v29 = v38;
        v30 = v37 + 8;
        *(_DWORD *)v36 = 4;
        *((_QWORD *)v36 + 1) = v37;
        *(_DWORD *)v37 = 160;
        *((_OWORD *)v37 + 3) = *(_OWORD *)&pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
        *((_QWORD *)v37 + 8) = *(_QWORD *)&pCertInfo->SubjectPublicKeyInfo.PublicKey.cUnusedBits;
        *((_QWORD *)v37 + 9) = pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId;
        *((_QWORD *)v37 + 15) = v26;
        v31 = pCertInfo;
        *((_QWORD *)v37 + 12) = "1.2.840.113549.1.9.16.3.28";
LABEL_56:
        v32 = (CERT_NAME_BLOB *)(v30 + 8);
        if ( v45 )
        {
          *((_QWORD *)v30 + 2) = pvData;
          *(_DWORD *)v30 = 2;
          v32->cbData = 20;
          if ( !CertGetCertificateContextProperty(*v44, 0x14u, pvData, (DWORD *)v30 + 2) )
            goto LABEL_64;
          pvData += 20;
        }
        else
        {
          *(_DWORD *)v30 = 1;
          *v32 = v31->Issuer;
          *(CRYPT_INTEGER_BLOB *)(v30 + 24) = v31->SerialNumber;
        }
        v37 = v27 + 160;
        v5 = v44 + 1;
        v36 = v23 + 16;
        v12 += 112;
        v38 = v29 + 1;
        v13 += 128;
        v39 = v28 + 11;
        ++v44;
        LODWORD(v4) = v4 - 1;
        if ( !(_DWORD)v4 )
          return v6;
      }
      v23 = v36;
      *(_DWORD *)v36 = 2;
      *((_QWORD *)v36 + 1) = v13;
      *(_DWORD *)v13 = 128;
      *(_QWORD *)(v13 + 8) = "1.2.840.113549.1.9.16.3.5";
      if ( v22 == 26115 )
      {
        v24 = "1.2.840.113549.1.9.16.3.6";
LABEL_51:
        *(_QWORD *)(v13 + 40) = v24;
      }
      else
      {
        *(_QWORD *)(v13 + 40) = "1.2.840.113549.1.9.16.3.7";
        if ( v22 == 26114 )
          *(_QWORD *)(v13 + 64) = *(_QWORD *)(a1 + 40);
      }
LABEL_54:
      v28 = v39;
      v29 = v38;
      v31 = pCertInfo;
      *(_DWORD *)(v13 + 84) = 1;
      *(_DWORD *)(v13 + 112) = 1;
      v30 = (char *)(v39 + 4);
      *(_QWORD *)(v13 + 120) = v38;
      *(_QWORD *)(v13 + 88) = &pCertInfo->SubjectPublicKeyInfo;
      *v38 = v39;
      *(_DWORD *)v39 = 88;
      *(_OWORD *)(v39 + 1) = *(_OWORD *)&pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
      v39[3] = *(_QWORD *)&pCertInfo->SubjectPublicKeyInfo.PublicKey.cUnusedBits;
LABEL_55:
      v27 = v37;
      goto LABEL_56;
    }
  }
  else
  {
LABEL_64:
    PkiDefaultCryptFree(v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800aed78  mov     [rsp+arg_10], r8
0x1800aed7d  mov     [rsp+arg_0], rcx
0x1800aed82  push    rbx
0x1800aed83  push    rbp
0x1800aed84  push    rsi
0x1800aed85  push    rdi
0x1800aed86  push    r12
0x1800aed88  push    r13
0x1800aed8a  push    r14
0x1800aed8c  push    r15
0x1800aed8e  sub     rsp, 78h
0x1800aed92  mov     esi, edx
0x1800aed94  mov     r12d, r9d
0x1800aed97  mov     r13, r8
0x1800aed9a  cmp     edx, 0FFFFFh
0x1800aeda0  jbe     short loc_1800AEDAE
0x1800aeda2  xor     ebp, ebp
0x1800aeda4  mov     ecx, 216h
0x1800aeda9  jmp     loc_1800AF3E5
0x1800aedae  mov     ecx, esi
0x1800aedb0  shl     ecx, 9
0x1800aedb3  and     r12d, 4
0x1800aedb7  mov     [rsp+0B8h+arg_18], r12d
0x1800aedbf  jz      short loc_1800AEDC7
0x1800aedc1  lea     eax, [rsi+rsi*4]
0x1800aedc4  lea     ecx, [rcx+rax*4]; uBytes
0x1800aedc7  mov     ebx, ecx
0x1800aedc9  call    PkiAlloc
0x1800aedce  mov     rbp, rax
0x1800aedd1  test    rax, rax
0x1800aedd4  jz      loc_1800AF3EB
0x1800aedda  mov     [rsp+0B8h+pvData], 0
0x1800aede3  mov     r8d, ebx; Size
0x1800aede6  xor     edx, edx; Val
0x1800aede8  mov     rcx, rax; void *
0x1800aedeb  call    memset_0
0x1800aedf0  imul    rax, rsi, 70h ; 'p'
0x1800aedf4  mov     r14, rsi
0x1800aedf7  mov     [rsp+0B8h+var_78], rbp
0x1800aedfc  shl     r14, 4
0x1800aee00  lea     rbx, [rsi+rsi*4]
0x1800aee04  add     r14, rbp
0x1800aee07  shl     rbx, 5
0x1800aee0b  add     rax, r14
0x1800aee0e  mov     r15, rsi
0x1800aee11  add     rbx, rax
0x1800aee14  shl     r15, 7
0x1800aee18  add     r15, rbx
0x1800aee1b  mov     [rsp+0B8h+var_70], rax
0x1800aee20  mov     [rsp+0B8h+var_68], r15
0x1800aee25  mov     rcx, rsi
0x1800aee28  lea     rdi, [r15+rsi*8]
0x1800aee2c  mov     [rsp+0B8h+var_60], rdi
0x1800aee31  test    r12d, r12d
0x1800aee34  jz      short loc_1800AEE42
0x1800aee36  imul    r12, rcx, 58h ; 'X'
0x1800aee3a  add     r12, rdi
0x1800aee3d  mov     [rsp+0B8h+pvData], r12
0x1800aee42  test    esi, esi
0x1800aee44  jz      loc_1800AF3F5
0x1800aee4a  mov     rax, [r13+0]
0x1800aee4e  mov     r8d, 40000003h; dwGroupId
0x1800aee54  xor     r15d, r15d
0x1800aee57  mov     [rsp+0B8h+arg_8], 0
0x1800aee62  mov     [rsp+0B8h+var_88], r15d
0x1800aee67  mov     rax, [rax+18h]
0x1800aee6b  lea     ecx, [r8-2]; dwKeyType
0x1800aee6f  mov     [rsp+0B8h+var_80], rax
0x1800aee74  mov     rdx, [rax+60h]; pvKey
0x1800aee78  call    CryptFindOIDInfo
0x1800aee7d  mov     r12, rax
0x1800aee80  test    rax, rax
0x1800aee83  jz      loc_1800AEF63
0x1800aee89  mov     r13d, [rax+1Ch]
0x1800aee8d  cmp     r13d, 0FFFFFFFDh
0x1800aee91  jnz     loc_1800AEF66
0x1800aee97  mov     rcx, [rax+30h]
0x1800aee9b  lea     rdx, [rsp+0B8h+lpString1]
0x1800aeea0  xor     r8d, r8d
0x1800aeea3  mov     [rsp+0B8h+lpString1], r15
0x1800aeea8  call    I_CryptExtractFromParameterSetAlgorithmName
0x1800aeead  test    eax, eax
0x1800aeeaf  jz      loc_1800AEF66
0x1800aeeb5  mov     rdi, [rsp+0B8h+lpString1]
0x1800aeeba  lea     rax, aMlKem; "ML-KEM"
0x1800aeec1  mov     r8, rdi; lpString1
0x1800aeec4  mov     [rsp+0B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800aeecc  or      r9d, 0FFFFFFFFh; cchCount1
0x1800aeed0  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800aeed5  lea     edx, [r15+1]; dwCmpFlags
0x1800aeed9  mov     ecx, 409h; Locale
0x1800aeede  call    cs:__imp_CompareStringW
0x1800aeee4  cmp     eax, 2
0x1800aeee7  jz      short loc_1800AEF15
0x1800aeee9  or      ecx, 0FFFFFFFFh
0x1800aeeec  lea     rax, aCompositeMlKem_4; "Composite-ML-KEM"
0x1800aeef3  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x1800aeef7  mov     r9d, ecx; cchCount1
0x1800aeefa  mov     r8, rdi; lpString1
0x1800aeefd  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800aef02  lea     edx, [rcx+2]; dwCmpFlags
0x1800aef05  mov     ecx, 409h; Locale
0x1800aef0a  call    cs:__imp_CompareStringW
0x1800aef10  cmp     eax, 2
0x1800aef13  jnz     short loc_1800AEF59
0x1800aef15  mov     r8, [r12+30h]; lpString1
0x1800aef1a  lea     rax, aMlKem512; "ML-KEM:512"
0x1800aef21  mov     ecx, 1
0x1800aef26  or      r9d, 0FFFFFFFFh; cchCount1
0x1800aef2a  mov     [rsp+0B8h+arg_8], ecx
0x1800aef31  mov     edx, ecx; dwCmpFlags
0x1800aef33  mov     [rsp+0B8h+cchCount2], r9d; cchCount2
0x1800aef38  mov     ecx, 409h; Locale
0x1800aef3d  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800aef42  call    cs:__imp_CompareStringW
0x1800aef48  cmp     eax, 2
0x1800aef4b  mov     eax, 1
0x1800aef50  cmovz   r15d, eax
0x1800aef54  mov     [rsp+0B8h+var_88], r15d
0x1800aef59  mov     rcx, rdi; hMem
0x1800aef5c  call    PkiDefaultCryptFree
0x1800aef61  jmp     short loc_1800AEF66
0x1800aef63  xor     r13d, r13d
0x1800aef66  mov     rax, [rsp+0B8h+arg_0]
0x1800aef6e  mov     r8d, 40000002h; dwGroupId
0x1800aef74  mov     ecx, 1; dwKeyType
0x1800aef79  mov     rdx, [rax+10h]; pvKey
0x1800aef7d  call    CryptFindOIDInfo
0x1800aef82  mov     rdi, rax
0x1800aef85  test    rax, rax
0x1800aef88  jz      short loc_1800AEF90
0x1800aef8a  mov     r15d, [rax+1Ch]
0x1800aef8e  jmp     short loc_1800AEF93
0x1800aef90  xor     r15d, r15d
0x1800aef93  lea     eax, [r13-0AA01h]
0x1800aef9a  mov     r13d, 1
0x1800aefa0  cmp     eax, r13d
0x1800aefa3  jbe     loc_1800AF290
0x1800aefa9  test    r12, r12
0x1800aefac  jz      loc_1800AF0CB
0x1800aefb2  mov     r8, [r12+30h]; lpString1
0x1800aefb7  lea     rax, String2; "CryptOIDInfoECCParameters"
0x1800aefbe  or      ecx, 0FFFFFFFFh
0x1800aefc1  mov     edx, r13d; dwCmpFlags
0x1800aefc4  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x1800aefc8  mov     r9d, ecx; cchCount1
0x1800aefcb  mov     ecx, 409h; Locale
0x1800aefd0  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800aefd5  call    cs:__imp_CompareStringW
0x1800aefdb  cmp     eax, 2
0x1800aefde  jnz     loc_1800AF0CB
0x1800aefe4  mov     r12, [rsp+0B8h+var_78]
0x1800aefe9  mov     [r12], eax
0x1800aefed  lea     rax, a13133168406302; "1.3.133.16.840.63.0.2"
0x1800aeff4  mov     [r12+8], rbx
0x1800aeff9  mov     [rbx+8], rax
0x1800aeffd  lea     rax, a21684011013414_2; "2.16.840.1.101.3.4.1.45"
0x1800af004  mov     [rbx+28h], rax
0x1800af008  lea     eax, [r15-6602h]
0x1800af00f  mov     dword ptr [rbx], 80h
0x1800af015  cmp     eax, r13d
0x1800af018  jbe     loc_1800AF2ED
0x1800af01e  mov     r8, [rdi+8]; lpString1
0x1800af022  lea     rax, a21684011013412; "2.16.840.1.101.3.4.1.2"
0x1800af029  or      r15d, 0FFFFFFFFh
0x1800af02d  mov     edx, r13d; dwCmpFlags
0x1800af030  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800af035  mov     r9d, r15d; cchCount1
0x1800af038  mov     ecx, 409h; Locale
0x1800af03d  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800af042  call    cs:__imp_CompareStringA
0x1800af048  cmp     eax, 2
0x1800af04b  jnz     short loc_1800AF059
0x1800af04d  lea     rax, a21684011013415; "2.16.840.1.101.3.4.1.5"
0x1800af054  jmp     loc_1800AF2C3
0x1800af059  mov     r8, [rdi+8]; lpString1
0x1800af05d  lea     rax, a21684011013412_0; "2.16.840.1.101.3.4.1.22"
0x1800af064  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800af069  mov     r9d, r15d; cchCount1
0x1800af06c  mov     edx, r13d; dwCmpFlags
0x1800af06f  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800af074  mov     ecx, 409h; Locale
0x1800af079  call    cs:__imp_CompareStringA
0x1800af07f  cmp     eax, 2
0x1800af082  jnz     short loc_1800AF090
0x1800af084  lea     rax, a21684011013412_2; "2.16.840.1.101.3.4.1.25"
0x1800af08b  jmp     loc_1800AF2C3
0x1800af090  mov     r8, [rdi+8]; lpString1
0x1800af094  lea     rax, a21684011013414_1; "2.16.840.1.101.3.4.1.42"
0x1800af09b  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800af0a0  mov     r9d, r15d; cchCount1
0x1800af0a3  mov     edx, r13d; dwCmpFlags
0x1800af0a6  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800af0ab  mov     ecx, 409h; Locale
0x1800af0b0  call    cs:__imp_CompareStringA
0x1800af0b6  cmp     eax, 2
0x1800af0b9  jnz     loc_1800AF2ED
0x1800af0bf  lea     rax, a21684011013414_2; "2.16.840.1.101.3.4.1.45"
0x1800af0c6  jmp     loc_1800AF2C3
0x1800af0cb  cmp     [rsp+0B8h+arg_8], 0
0x1800af0d3  jz      loc_1800AF1BF
0x1800af0d9  test    rdi, rdi
0x1800af0dc  jz      loc_1800AF3E0
0x1800af0e2  mov     r8, [rdi+30h]; lpString1
0x1800af0e6  lea     rcx, aAes; "AES"
0x1800af0ed  or      eax, 0FFFFFFFFh
0x1800af0f0  mov     edx, r13d; dwCmpFlags
0x1800af0f3  mov     [rsp+0B8h+cchCount2], eax; cchCount2
0x1800af0f7  mov     r9d, eax; cchCount1
0x1800af0fa  mov     [rsp+0B8h+lpString2], rcx; lpString2
0x1800af0ff  mov     ecx, 409h; Locale
0x1800af104  call    cs:__imp_CompareStringW
0x1800af10a  cmp     eax, 2
0x1800af10d  jnz     loc_1800AF3E0
0x1800af113  mov     eax, [rdi+20h]
0x1800af116  and     eax, 0FFFFFFFCh
0x1800af119  cmp     eax, 4
0x1800af11c  jb      loc_1800AF3E0
0x1800af122  mov     rax, [rdi+28h]
0x1800af126  cmp     dword ptr [rax], 80h
0x1800af12c  jnz     short loc_1800AF142
0x1800af12e  cmp     [rsp+0B8h+var_88], 0
0x1800af133  jz      loc_1800AF3E0
0x1800af139  lea     rdx, a21684011013415; "2.16.840.1.101.3.4.1.5"
0x1800af140  jmp     short loc_1800AF155
0x1800af142  cmp     dword ptr [rax], 100h
0x1800af148  jnz     loc_1800AF3E0
0x1800af14e  lea     rdx, a21684011013414_2; "2.16.840.1.101.3.4.1.45"
0x1800af155  mov     r13, [rsp+0B8h+var_70]
0x1800af15a  mov     rax, [rsp+0B8h+var_80]
0x1800af15f  mov     r12, [rsp+0B8h+var_78]
0x1800af164  mov     rdi, [rsp+0B8h+var_60]
0x1800af169  mov     r15, [rsp+0B8h+var_68]
0x1800af16e  lea     rcx, [r13+8]
0x1800af172  mov     dword ptr [r12], 4
0x1800af17a  mov     [r12+8], r13
0x1800af17f  mov     dword ptr [r13+0], 0A0h
0x1800af187  movups  xmm0, xmmword ptr [rax+78h]
0x1800af18b  movups  xmmword ptr [r13+30h], xmm0
0x1800af190  movsd   xmm1, qword ptr [rax+88h]
0x1800af198  movsd   qword ptr [r13+40h], xmm1
0x1800af19e  mov     rax, [rax+60h]
0x1800af1a2  mov     [r13+48h], rax
0x1800af1a6  lea     rax, a12840113549191_1; "1.2.840.113549.1.9.16.3.28"
0x1800af1ad  mov     [r13+78h], rdx
0x1800af1b1  mov     rdx, [rsp+0B8h+var_80]
0x1800af1b6  mov     [r13+60h], rax
0x1800af1ba  jmp     loc_1800AF334
0x1800af1bf  mov     rax, [rsp+0B8h+var_78]
0x1800af1c4  mov     [rax], r13d
0x1800af1c7  mov     [rax+8], r14
0x1800af1cb  mov     dword ptr [r14], 70h ; 'p'
0x1800af1d2  test    rdi, rdi
0x1800af1d5  jz      short loc_1800AF248
0x1800af1d7  mov     r8, [rdi+30h]; lpString1
0x1800af1db  lea     rax, aAes; "AES"
0x1800af1e2  or      r15d, 0FFFFFFFFh
0x1800af1e6  mov     edi, 409h
0x1800af1eb  mov     ecx, edi; Locale
0x1800af1ed  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800af1f2  mov     r9d, r15d; cchCount1
0x1800af1f5  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800af1fa  mov     edx, r13d; dwCmpFlags
0x1800af1fd  call    cs:__imp_CompareStringW
0x1800af203  cmp     eax, 2
0x1800af206  jnz     short loc_1800AF248
0x1800af208  test    r12, r12
0x1800af20b  jz      short loc_1800AF248
0x1800af20d  mov     r8, [r12+30h]; lpString1
0x1800af212  lea     rax, aRsa; "RSA"
0x1800af219  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800af21e  mov     r9d, r15d; cchCount1
0x1800af221  mov     edx, r13d; dwCmpFlags
0x1800af224  mov     [rsp+0B8h+lpString2], rax; lpString2
0x1800af229  mov     ecx, edi; Locale
0x1800af22b  call    cs:__imp_CompareStringW
0x1800af231  cmp     eax, 2
0x1800af234  jnz     short loc_1800AF248
0x1800af236  mov     rdx, [rsp+0B8h+var_80]
0x1800af23b  lea     rax, a12840113549117; "1.2.840.113549.1.1.7"
0x1800af242  mov     [r14+8], rax
0x1800af246  jmp     short loc_1800AF261
0x1800af248  mov     rdx, [rsp+0B8h+var_80]
0x1800af24d  movups  xmm0, xmmword ptr [rdx+60h]
0x1800af251  movups  xmmword ptr [r14+8], xmm0
0x1800af256  movsd   xmm1, qword ptr [rdx+70h]
0x1800af25b  movsd   qword ptr [r14+18h], xmm1
0x1800af261  movups  xmm0, xmmword ptr [rdx+78h]
0x1800af265  mov     rdi, [rsp+0B8h+var_60]
0x1800af26a  lea     rcx, [r14+48h]
0x1800af26e  mov     r15, [rsp+0B8h+var_68]
0x1800af273  mov     r12, [rsp+0B8h+var_78]
0x1800af278  movups  xmmword ptr [r14+30h], xmm0
0x1800af27d  movsd   xmm1, qword ptr [rdx+88h]
0x1800af285  movsd   qword ptr [r14+40h], xmm1
0x1800af28b  jmp     loc_1800AF32F
0x1800af290  mov     r12, [rsp+0B8h+var_78]
0x1800af295  lea     rax, a12840113549191_9; "1.2.840.113549.1.9.16.3.5"
0x1800af29c  mov     dword ptr [r12], 2
0x1800af2a4  mov     [r12+8], rbx
  ... truncated ...
```
