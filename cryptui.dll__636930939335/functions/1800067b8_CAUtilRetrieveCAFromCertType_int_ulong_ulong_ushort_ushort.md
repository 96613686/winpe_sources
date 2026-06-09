# CAUtilRetrieveCAFromCertType(int,ulong,ulong *,ushort * * *,ushort * * *)

- ea: `0x1800067b8`
- end: `0x180006cb6`
- name: `?CAUtilRetrieveCAFromCertType@@YAHHKPEAKPEAPEAPEAG1@Z`
- size: `1278`
- prototype: `__int64 __fastcall(int, unsigned int, unsigned int *, unsigned __int16 ***, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002c0f0`

## callees

- `0x1800059ec`
- `0x180006688`
- `0x1800067b8`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000689b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000698e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000689b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000698e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c9b`
- `CRYPT32!CertNameToStrW` at `0x18000696f`
- `CRYPT32!CertNameToStrW` at `0x1800069ce`
- `CRYPT32!CertNameToStrW` at `0x18000696f`
- `CRYPT32!CertNameToStrW` at `0x1800069ce`
- `CRYPT32!CertFreeCertificateContext` at `0x180006a17`
- `CRYPT32!CertFreeCertificateContext` at `0x180006c8b`
- `CRYPT32!CertFreeCertificateContext` at `0x180006a17`
- `CRYPT32!CertFreeCertificateContext` at `0x180006c8b`
- `certca!__imp_CAEnumFirstCA` at `0x180006836`
- `certca!__imp_CAEnumFirstCA` at `0x180006836`
- `certca!__imp_CAEnumNextCA` at `0x180006b17`
- `certca!__imp_CAEnumNextCA` at `0x180006b17`
- `certca!__imp_CACountCAs` at `0x180006862`
- `certca!__imp_CACountCAs` at `0x180006862`
- `certca!__imp_CACloseCA` at `0x180006b26`
- `certca!__imp_CACloseCA` at `0x180006c49`
- `certca!__imp_CACloseCA` at `0x180006c59`
- `certca!__imp_CACloseCA` at `0x180006b26`
- `certca!__imp_CACloseCA` at `0x180006c49`
- `certca!__imp_CACloseCA` at `0x180006c59`
- `certca!__imp_CAGetCAProperty` at `0x180006a35`
- `certca!__imp_CAGetCAProperty` at `0x180006aa4`
- `certca!__imp_CAGetCAProperty` at `0x180006a35`
- `certca!__imp_CAGetCAProperty` at `0x180006aa4`
- `certca!__imp_CAFreeCAProperty` at `0x180006a88`
- `certca!__imp_CAFreeCAProperty` at `0x180006af2`
- `certca!__imp_CAFreeCAProperty` at `0x180006c24`
- `certca!__imp_CAFreeCAProperty` at `0x180006c39`
- `certca!__imp_CAFreeCAProperty` at `0x180006a88`
- `certca!__imp_CAFreeCAProperty` at `0x180006af2`
- `certca!__imp_CAFreeCAProperty` at `0x180006c24`
- `certca!__imp_CAFreeCAProperty` at `0x180006c39`
- `certca!__imp_CAGetCACertificate` at `0x180006930`
- `certca!__imp_CAGetCACertificate` at `0x180006930`

## pseudocode

```c
__int64 __fastcall CAUtilRetrieveCAFromCertType(
        __int64 a1,
        char a2,
        unsigned int *a3,
        HLOCAL *a4,
        unsigned __int16 ***a5)
{
  unsigned __int16 ***v6; // rdi
  __int64 v7; // r15
  DWORD v8; // eax
  DWORD v9; // ecx
  unsigned int v10; // eax
  int v11; // eax
  unsigned __int16 **v12; // rax
  unsigned __int16 **v13; // rax
  unsigned int v14; // r12d
  unsigned int v15; // eax
  unsigned int v16; // r14d
  DWORD v17; // eax
  HLOCAL v18; // rbx
  unsigned __int16 *v19; // rax
  __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rax
  void *v23; // rdi
  int v24; // ebx
  unsigned int i; // ebx
  unsigned __int16 *v26; // rcx
  unsigned int j; // ebx
  unsigned __int16 *v28; // rcx
  void *v30; // [rsp+38h] [rbp-80h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-70h]
  unsigned int v33; // [rsp+4Ch] [rbp-6Ch]
  unsigned __int16 **v34; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int16 **v35; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v36; // [rsp+60h] [rbp-58h]
  void *v37; // [rsp+68h] [rbp-50h]
  HLOCAL hMem; // [rsp+70h] [rbp-48h]
  __int64 v39; // [rsp+78h] [rbp-40h]
  DWORD csz; // [rsp+C0h] [rbp+8h]

  v30 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  pCertContext = 0;
  if ( !a3 || !a4 || (v6 = a5) == 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  LODWORD(v7) = 0;
  v33 = 0;
  hMem = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v8 = CAEnumFirstCA(0, 8 * (a2 & 4u), &v30);
  if ( v8 )
  {
    v9 = v8;
    goto LABEL_42;
  }
  if ( !v30 )
  {
    v9 = 8333;
    goto LABEL_42;
  }
  v10 = CACountCAs();
  v7 = v10;
  v33 = v10;
  if ( v10 )
  {
    v12 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * v10);
    *a4 = v12;
    if ( !v12 || (memset_0(v12, 0, 8 * v7), v13 = (unsigned __int16 **)LocalAlloc(0x40u, 8 * v7), (*a5 = v13) == 0) )
    {
LABEL_21:
      v9 = -2147024882;
      goto LABEL_42;
    }
    memset_0(v13, 0, 8 * v7);
    v14 = 0;
    v36 = 0;
    v15 = 0;
    v16 = 1;
    while ( 1 )
    {
      v32 = v15;
      if ( v15 >= (unsigned int)v7 )
        break;
      if ( (unsigned int)CAUtilCheckCAPermission(v30) )
      {
        if ( (a2 & 2) != 0 )
        {
          v11 = CAGetCACertificate(v30, &pCertContext);
          if ( v11 )
            goto LABEL_41;
          if ( !pCertContext )
          {
            v11 = -2147467259;
            goto LABEL_41;
          }
          v17 = CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Subject, 3u, 0, 0);
          csz = v17;
          if ( !v17 )
            goto LABEL_44;
          v18 = LocalAlloc(0x40u, 2LL * v17);
          hMem = v18;
          if ( !v18 )
            goto LABEL_21;
          if ( !CertNameToStrW(
                  pCertContext->dwCertEncodingType,
                  &pCertContext->pCertInfo->Subject,
                  3u,
                  (LPWSTR)v18,
                  csz) )
            goto LABEL_44;
          v19 = LocalAllocAndCopyWStr((unsigned __int16 *)v18);
          v39 = 8LL * v14;
          (*v6)[(unsigned __int64)v39 / 8] = v19;
          if ( !v19 )
            goto LABEL_44;
          LocalFree(v18);
          hMem = 0;
          CertFreeCertificateContext(pCertContext);
          pCertContext = 0;
          v20 = v39;
        }
        else
        {
          v11 = CAGetCAProperty(v30, L"cn", &v34);
          if ( v11 )
            goto LABEL_41;
          if ( !v34 )
          {
            v11 = -2147467259;
            goto LABEL_41;
          }
          v21 = LocalAllocAndCopyWStr(*v34);
          v20 = 8LL * v14;
          *(unsigned __int16 **)((char *)*v6 + v20) = v21;
          if ( !v21 )
            goto LABEL_44;
          CAFreeCAProperty(v30, v34);
          v34 = 0;
        }
        v11 = CAGetCAProperty(v30, L"dNSHostName", &v35);
        if ( v11 )
          goto LABEL_41;
        if ( !v35 )
        {
          v11 = -2147467259;
          goto LABEL_41;
        }
        v22 = LocalAllocAndCopyWStr(*v35);
        *(_QWORD *)((char *)*a4 + v20) = v22;
        if ( !v22 )
          goto LABEL_44;
        CAFreeCAProperty(v30, v35);
        v35 = 0;
        v36 = ++v14;
      }
      v23 = v30;
      v37 = v30;
      v24 = CAEnumNextCA(v30, &v30);
      CACloseCA(v23);
      v37 = 0;
      if ( v24 || !v30 )
        break;
      v15 = v32 + 1;
      v6 = a5;
    }
    *a3 = v14;
    if ( v14 )
      goto LABEL_57;
    v11 = -2147467259;
  }
  else
  {
    v11 = -2147467259;
  }
LABEL_41:
  v9 = v11;
LABEL_42:
  SetLastError(v9);
LABEL_44:
  if ( *a4 )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v26 = (unsigned __int16 *)*((_QWORD *)*a4 + i);
      if ( v26 )
        LocalFree(v26);
    }
    LocalFree(*a4);
    *a4 = 0;
  }
  if ( *a5 )
  {
    for ( j = 0; j < (unsigned int)v7; ++j )
    {
      v28 = (*a5)[j];
      if ( v28 )
        LocalFree(v28);
    }
    LocalFree(*a5);
    *a5 = 0;
  }
  v16 = 0;
LABEL_57:
  if ( v34 )
    CAFreeCAProperty(v30, v34);
  if ( v35 )
    CAFreeCAProperty(v30, v35);
  if ( v37 )
    CACloseCA(v37);
  if ( v30 )
    CACloseCA(v30);
  if ( hMem )
    LocalFree(hMem);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  return v16;
}

```

## disassembly

```asm
0x1800067b8  mov     rax, rsp
0x1800067bb  mov     [rax+20h], r9
0x1800067bf  mov     [rax+18h], r8
0x1800067c3  mov     [rax+10h], edx
0x1800067c6  mov     [rax+8], ecx
0x1800067c9  push    rbx
0x1800067ca  push    rsi
0x1800067cb  push    rdi
0x1800067cc  push    r12
0x1800067ce  push    r13
0x1800067d0  push    r14
0x1800067d2  push    r15
0x1800067d4  sub     rsp, 80h
0x1800067db  mov     r13, r9
0x1800067de  xor     esi, esi
0x1800067e0  mov     [rax-80h], rsi
0x1800067e4  mov     [rax-50h], rsi
0x1800067e8  mov     [rax-68h], rsi
0x1800067ec  mov     [rax-60h], rsi
0x1800067f0  mov     [rax-78h], rsi
0x1800067f4  test    r8, r8
0x1800067f7  jz      loc_180006C96
0x1800067fd  test    r9, r9
0x180006800  jz      loc_180006C96
0x180006806  mov     rdi, [rsp+0B8h+arg_20]
0x18000680e  test    rdi, rdi
0x180006811  jz      loc_180006C96
0x180006817  mov     r15d, esi
0x18000681a  mov     [rax-6Ch], esi
0x18000681d  mov     [rax-48h], rsi
0x180006821  mov     [r8], esi
0x180006824  mov     [r9], rsi
0x180006827  mov     [rdi], rsi
0x18000682a  and     edx, 4
0x18000682d  shl     edx, 3
0x180006830  lea     r8, [rax-80h]
0x180006834  xor     ecx, ecx
0x180006836  call    cs:__imp_CAEnumFirstCA
0x18000683c  mov     [rsp+0B8h+var_88], eax
0x180006840  test    eax, eax
0x180006842  jz      short loc_180006851
0x180006844  mov     ecx, eax; dwErrCode
0x180006846  call    cs:__imp_SetLastError
0x18000684c  jmp     loc_180006B8F
0x180006851  mov     rcx, [rsp+0B8h+var_80]
0x180006856  test    rcx, rcx
0x180006859  jnz     short loc_180006862
0x18000685b  mov     ecx, 208Dh
0x180006860  jmp     short loc_180006846
0x180006862  call    cs:__imp_CACountCAs
0x180006868  mov     r15d, eax
0x18000686b  mov     [rsp+0B8h+var_6C], r15d
0x180006870  test    eax, eax
0x180006872  jnz     short loc_180006888
0x180006874  mov     eax, 80004005h
0x180006879  mov     [rsp+0B8h+var_88], eax
0x18000687d  mov     r14d, 1
0x180006883  jmp     loc_180006B69
0x180006888  mov     rbx, r15
0x18000688b  shl     rbx, 3
0x18000688f  mov     rdx, rbx; uBytes
0x180006892  mov     r14d, 40h ; '@'
0x180006898  mov     ecx, r14d; uFlags
0x18000689b  call    cs:__imp_LocalAlloc
0x1800068a1  mov     [r13+0], rax
0x1800068a5  test    rax, rax
0x1800068a8  jnz     short loc_1800068B3
0x1800068aa  lea     r14d, [rax+1]
0x1800068ae  jmp     loc_1800069A1
0x1800068b3  mov     r8, rbx; Size
0x1800068b6  xor     edx, edx; Val
0x1800068b8  mov     rcx, rax; void *
0x1800068bb  call    memset_0
0x1800068c0  mov     rdx, rbx; uBytes
0x1800068c3  mov     ecx, r14d; uFlags
0x1800068c6  call    cs:__imp_LocalAlloc
0x1800068cc  mov     [rdi], rax
0x1800068cf  test    rax, rax
0x1800068d2  jnz     short loc_1800068DD
0x1800068d4  lea     r14d, [rax+1]
0x1800068d8  jmp     loc_1800069A1
0x1800068dd  mov     r8, rbx; Size
0x1800068e0  xor     edx, edx; Val
0x1800068e2  mov     rcx, rax; void *
0x1800068e5  call    memset_0
0x1800068ea  mov     r12d, esi
0x1800068ed  mov     [rsp+0B8h+var_58], esi
0x1800068f1  mov     eax, esi
0x1800068f3  mov     r14d, 1
0x1800068f9  mov     [rsp+0B8h+var_70], eax
0x1800068fd  cmp     eax, r15d
0x180006900  jnb     loc_180006B50
0x180006906  mov     rcx, [rsp+0B8h+var_80]; void *
0x18000690b  call    ?CAUtilCheckCAPermission@@YAHPEAX@Z; CAUtilCheckCAPermission(void *)
0x180006910  test    eax, eax
0x180006912  jz      loc_180006B05
0x180006918  mov     rcx, [rsp+0B8h+var_80]
0x18000691d  test    [rsp+0B8h+arg_8], 2
0x180006925  jz      loc_180006A29
0x18000692b  lea     rdx, [rsp+0B8h+pCertContext]
0x180006930  call    cs:__imp_CAGetCACertificate
0x180006936  mov     [rsp+0B8h+var_88], eax
0x18000693a  test    eax, eax
0x18000693c  jnz     loc_180006B69
0x180006942  mov     rcx, [rsp+0B8h+pCertContext]
0x180006947  test    rcx, rcx
0x18000694a  jnz     short loc_18000695A
0x18000694c  mov     eax, 80004005h
0x180006951  mov     [rsp+0B8h+var_88], eax
0x180006955  jmp     loc_180006B69
0x18000695a  mov     rdx, [rcx+18h]
0x18000695e  add     rdx, 50h ; 'P'; pName
0x180006962  mov     [rsp+0B8h+csz], esi; csz
0x180006966  xor     r9d, r9d; psz
0x180006969  lea     r8d, [r9+3]; dwStrType
0x18000696d  mov     ecx, [rcx]; dwCertEncodingType
0x18000696f  call    cs:__imp_CertNameToStrW
0x180006975  mov     [rsp+0B8h+arg_0], eax
0x18000697c  test    eax, eax
0x18000697e  jz      loc_180006AE3
0x180006984  mov     edx, eax
0x180006986  add     rdx, rdx; uBytes
0x180006989  mov     ecx, 40h ; '@'; uFlags
0x18000698e  call    cs:__imp_LocalAlloc
0x180006994  mov     rbx, rax
0x180006997  mov     [rsp+0B8h+hMem], rax
0x18000699c  test    rax, rax
0x18000699f  jnz     short loc_1800069AB
0x1800069a1  mov     ecx, 8007000Eh
0x1800069a6  jmp     loc_180006B6B
0x1800069ab  mov     rcx, [rsp+0B8h+pCertContext]
0x1800069b0  mov     rdx, [rcx+18h]
0x1800069b4  add     rdx, 50h ; 'P'; pName
0x1800069b8  mov     eax, [rsp+0B8h+arg_0]
0x1800069bf  mov     [rsp+0B8h+csz], eax; csz
0x1800069c3  mov     r9, rbx; psz
0x1800069c6  mov     r8d, 3; dwStrType
0x1800069cc  mov     ecx, [rcx]; dwCertEncodingType
0x1800069ce  call    cs:__imp_CertNameToStrW
0x1800069d4  test    eax, eax
0x1800069d6  jz      loc_180006AE3
0x1800069dc  mov     rcx, rbx; Src
0x1800069df  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x1800069e4  mov     ecx, r12d
0x1800069e7  lea     rdx, ds:0[rcx*8]
0x1800069ef  mov     [rsp+0B8h+var_40], rdx
0x1800069f4  mov     rcx, [rdi]
0x1800069f7  mov     [rdx+rcx], rax
0x1800069fb  test    rax, rax
0x1800069fe  jz      loc_180006AE3
0x180006a04  mov     rcx, rbx; hMem
0x180006a07  call    cs:__imp_LocalFree
0x180006a0d  mov     [rsp+0B8h+hMem], rsi
0x180006a12  mov     rcx, [rsp+0B8h+pCertContext]; pCertContext
0x180006a17  call    cs:__imp_CertFreeCertificateContext
0x180006a1d  mov     [rsp+0B8h+pCertContext], rsi
0x180006a22  mov     rbx, [rsp+0B8h+var_40]
0x180006a27  jmp     short loc_180006A93
0x180006a29  lea     r8, [rsp+0B8h+var_68]
0x180006a2e  lea     rdx, aCn; "cn"
0x180006a35  call    cs:__imp_CAGetCAProperty
0x180006a3b  mov     [rsp+0B8h+var_88], eax
0x180006a3f  test    eax, eax
0x180006a41  jnz     loc_180006B69
0x180006a47  mov     rcx, [rsp+0B8h+var_68]
0x180006a4c  test    rcx, rcx
0x180006a4f  jnz     short loc_180006A5F
0x180006a51  mov     eax, 80004005h
0x180006a56  mov     [rsp+0B8h+var_88], eax
0x180006a5a  jmp     loc_180006B69
0x180006a5f  mov     rcx, [rcx]; Src
0x180006a62  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x180006a67  mov     ecx, r12d
0x180006a6a  lea     rbx, ds:0[rcx*8]
0x180006a72  mov     rcx, [rdi]
0x180006a75  mov     [rbx+rcx], rax
0x180006a79  test    rax, rax
0x180006a7c  jz      short loc_180006AE3
0x180006a7e  mov     rdx, [rsp+0B8h+var_68]
0x180006a83  mov     rcx, [rsp+0B8h+var_80]
0x180006a88  call    cs:__imp_CAFreeCAProperty
0x180006a8e  mov     [rsp+0B8h+var_68], rsi
0x180006a93  lea     r8, [rsp+0B8h+var_60]
0x180006a98  lea     rdx, aDnshostname; "dNSHostName"
0x180006a9f  mov     rcx, [rsp+0B8h+var_80]
0x180006aa4  call    cs:__imp_CAGetCAProperty
0x180006aaa  mov     [rsp+0B8h+var_88], eax
0x180006aae  test    eax, eax
0x180006ab0  jnz     loc_180006B69
0x180006ab6  mov     rcx, [rsp+0B8h+var_60]
0x180006abb  test    rcx, rcx
0x180006abe  jnz     short loc_180006ACE
0x180006ac0  mov     eax, 80004005h
0x180006ac5  mov     [rsp+0B8h+var_88], eax
0x180006ac9  jmp     loc_180006B69
0x180006ace  mov     rcx, [rcx]; Src
0x180006ad1  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x180006ad6  mov     rcx, [r13+0]
0x180006ada  mov     [rbx+rcx], rax
0x180006ade  test    rax, rax
0x180006ae1  jnz     short loc_180006AE8
0x180006ae3  jmp     loc_180006B95
0x180006ae8  mov     rdx, [rsp+0B8h+var_60]
0x180006aed  mov     rcx, [rsp+0B8h+var_80]
0x180006af2  call    cs:__imp_CAFreeCAProperty
0x180006af8  mov     [rsp+0B8h+var_60], rsi
0x180006afd  add     r12d, r14d
0x180006b00  mov     [rsp+0B8h+var_58], r12d
0x180006b05  mov     rdi, [rsp+0B8h+var_80]
0x180006b0a  mov     [rsp+0B8h+var_50], rdi
0x180006b0f  lea     rdx, [rsp+0B8h+var_80]
0x180006b14  mov     rcx, rdi
0x180006b17  call    cs:__imp_CAEnumNextCA
0x180006b1d  mov     ebx, eax
0x180006b1f  mov     [rsp+0B8h+var_88], eax
0x180006b23  mov     rcx, rdi
0x180006b26  call    cs:__imp_CACloseCA
0x180006b2c  mov     [rsp+0B8h+var_50], rsi
0x180006b31  test    ebx, ebx
0x180006b33  jnz     short loc_180006B50
0x180006b35  cmp     [rsp+0B8h+var_80], rsi
0x180006b3a  jz      short loc_180006B50
0x180006b3c  mov     eax, [rsp+0B8h+var_70]
0x180006b40  add     eax, r14d
0x180006b43  mov     rdi, [rsp+0B8h+arg_20]
0x180006b4b  jmp     loc_1800068F9
0x180006b50  mov     rax, [rsp+0B8h+arg_10]
0x180006b58  mov     [rax], r12d
0x180006b5b  test    r12d, r12d
0x180006b5e  jnz     short loc_180006B73
0x180006b60  mov     eax, 80004005h
0x180006b65  mov     [rsp+0B8h+var_88], eax
0x180006b69  mov     ecx, eax; dwErrCode
0x180006b6b  call    cs:__imp_SetLastError
0x180006b71  jmp     short loc_180006B95
0x180006b73  jmp     loc_180006C0C
0x180006b78  mov     ecx, eax; dwErrCode
0x180006b7a  call    cs:__imp_SetLastError
0x180006b80  xor     esi, esi
0x180006b82  mov     r13, [rsp+0B8h+arg_18]
0x180006b8a  mov     r15d, [rsp+0B8h+var_6C]
0x180006b8f  mov     r14d, 1
0x180006b95  cmp     [r13+0], rsi
0x180006b99  jz      short loc_180006BCD
0x180006b9b  mov     ebx, esi
0x180006b9d  test    r15d, r15d
0x180006ba0  jz      short loc_180006BBF
0x180006ba2  mov     ecx, ebx
0x180006ba4  mov     rax, [r13+0]
0x180006ba8  mov     rcx, [rax+rcx*8]; hMem
0x180006bac  test    rcx, rcx
0x180006baf  jz      short loc_180006BB7
0x180006bb1  call    cs:__imp_LocalFree
0x180006bb7  add     ebx, r14d
0x180006bba  cmp     ebx, r15d
0x180006bbd  jb      short loc_180006BA2
0x180006bbf  mov     rcx, [r13+0]; hMem
0x180006bc3  call    cs:__imp_LocalFree
0x180006bc9  mov     [r13+0], rsi
0x180006bcd  mov     rdi, [rsp+0B8h+arg_20]
0x180006bd5  cmp     [rdi], rsi
0x180006bd8  jz      short loc_180006C09
0x180006bda  mov     ebx, esi
0x180006bdc  test    r15d, r15d
0x180006bdf  jz      short loc_180006BFD
0x180006be1  mov     ecx, ebx
0x180006be3  mov     rax, [rdi]
0x180006be6  mov     rcx, [rax+rcx*8]; hMem
0x180006bea  test    rcx, rcx
0x180006bed  jz      short loc_180006BF5
0x180006bef  call    cs:__imp_LocalFree
0x180006bf5  add     ebx, r14d
0x180006bf8  cmp     ebx, r15d
0x180006bfb  jb      short loc_180006BE1
0x180006bfd  mov     rcx, [rdi]; hMem
0x180006c00  call    cs:__imp_LocalFree
0x180006c06  mov     [rdi], rsi
0x180006c09  mov     r14d, esi
0x180006c0c  mov     [rsp+0B8h+arg_0], r14d
0x180006c14  nop
0x180006c15  mov     rdx, [rsp+0B8h+var_68]
0x180006c1a  test    rdx, rdx
0x180006c1d  jz      short loc_180006C2A
0x180006c1f  mov     rcx, [rsp+0B8h+var_80]
0x180006c24  call    cs:__imp_CAFreeCAProperty
0x180006c2a  mov     rdx, [rsp+0B8h+var_60]
0x180006c2f  test    rdx, rdx
0x180006c32  jz      short loc_180006C3F
0x180006c34  mov     rcx, [rsp+0B8h+var_80]
0x180006c39  call    cs:__imp_CAFreeCAProperty
0x180006c3f  mov     rcx, [rsp+0B8h+var_50]
0x180006c44  test    rcx, rcx
0x180006c47  jz      short loc_180006C4F
0x180006c49  call    cs:__imp_CACloseCA
0x180006c4f  mov     rcx, [rsp+0B8h+var_80]
0x180006c54  test    rcx, rcx
0x180006c57  jz      short loc_180006C5F
0x180006c59  call    cs:__imp_CACloseCA
0x180006c5f  jmp     short loc_180006C71
0x180006c61  mov     ecx, eax; dwErrCode
  ... truncated ...
```
