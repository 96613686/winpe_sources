# ObjectContextGetRawUrlData

- ea: `0x180014df0`
- end: `0x180015370`
- name: `ObjectContextGetRawUrlData`
- size: `1408`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, char *Str1, void *, __int64)`
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180013bc0`
- `0x180013c80`
- `0x1800141e0`
- `0x180014750`
- `0x180015bb8`
- `0x180025740`
- `0x180025a50`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x180014df0`
- `0x180015380`
- `0x180016f80`
- `0x180026552`
- `0x180026576`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001514a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001515c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001516f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015325`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001514a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001515c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001516f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015325`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015330`
- `CRYPT32!CertFindExtension` at `0x180014fc1`
- `CRYPT32!CertFindExtension` at `0x180014fc1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001511b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001511b`
- `CRYPT32!CryptDecodeObject` at `0x180014ffd`
- `CRYPT32!CryptDecodeObject` at `0x180015051`
- `CRYPT32!CryptDecodeObject` at `0x180014ffd`
- `CRYPT32!CryptDecodeObject` at `0x180015051`
- `CRYPT32!CertGetCRLContextProperty` at `0x1800152d7`
- `CRYPT32!CertGetCRLContextProperty` at `0x1800152d7`
- `CRYPT32!CertGetCTLContextProperty` at `0x1800152b4`
- `CRYPT32!CertGetCTLContextProperty` at `0x1800152b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015017`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015017`

## pseudocode

```c
__int64 __fastcall ObjectContextGetRawUrlData(
        char *a1,
        const CERT_CONTEXT *a2,
        unsigned int a3,
        char a4,
        char *Str1,
        void *a6,
        unsigned int *a7)
{
  void *v7; // r11
  unsigned int *v8; // r14
  char *v9; // r10
  const char *v10; // rcx
  unsigned int v11; // r13d
  PCCERT_CONTEXT v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int CertificateContextProperty; // esi
  int v18; // edi
  unsigned int v19; // r12d
  unsigned int v20; // r14d
  const char *v21; // rsi
  DWORD v22; // r14d
  PCERT_INFO pCertInfo; // rax
  DWORD cExtension; // edx
  CERT_EXTENSION *rgExtension; // r8
  PCERT_EXTENSION Extension; // rax
  HLOCAL pvStructInfo; // r14
  BYTE *v29; // rax
  PCERT_INFO v30; // rax
  struct _CRYPT_ATTRIBUTE *v31; // rax
  __int64 v32; // rcx
  PCERT_INFO v33; // rax
  DWORD cbEncoded[2]; // [rsp+40h] [rbp-A1h] BYREF
  BYTE *pbEncoded; // [rsp+48h] [rbp-99h]
  SIZE_T uBytes; // [rsp+50h] [rbp-91h] BYREF
  int v37; // [rsp+58h] [rbp-89h]
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-81h]
  unsigned int v39; // [rsp+68h] [rbp-79h]
  LPCSTR lpszStructType; // [rsp+70h] [rbp-71h]
  HLOCAL hMem; // [rsp+78h] [rbp-69h]
  char *v42; // [rsp+80h] [rbp-61h]
  unsigned int *v43; // [rsp+88h] [rbp-59h]
  void *v44; // [rsp+90h] [rbp-51h]
  int Src; // [rsp+A0h] [rbp-41h] BYREF
  _QWORD v46[7]; // [rsp+A8h] [rbp-39h]

  v7 = a6;
  v8 = a7;
  v9 = a1;
  v42 = a1;
  v10 = Str1;
  v11 = 1;
  v39 = a3;
  v12 = a2;
  lpszStructType = Str1;
  pCertContext = a2;
  v44 = a6;
  v43 = a7;
  *(_QWORD *)cbEncoded = 0;
  pbEncoded = 0;
  uBytes = 0;
  v13 = a4 & 1;
  if ( (a4 & 1) != 0 )
  {
    Src = 1;
    v46[0] = 0;
  }
  if ( (a4 & 2) != 0 )
  {
    v14 = 2LL * (a4 & 1);
    ++v13;
    LODWORD(v46[v14]) = 2;
    v46[v14] = 0;
  }
  if ( (a4 & 4) != 0 )
  {
    v15 = 2LL * v13++;
    LODWORD(v46[v15]) = 4;
    v46[v15] = 0;
  }
  if ( (a4 & 8) != 0 )
  {
    v16 = 2LL * v13++;
    LODWORD(v46[v16]) = 8;
    v46[v16] = 0;
  }
  if ( *a7 < v13 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  CertificateContextProperty = 1;
  v18 = 0;
  v19 = 0;
  v37 = 0;
  hMem = 0;
  if ( !v13 )
    goto LABEL_37;
  do
  {
    v20 = v46[2 * v19];
    if ( v20 == 1 )
    {
      if ( (unsigned __int64)v10 <= 0xFFFF )
        goto LABEL_26;
      if ( !strcmp_0(v10, "1.3.6.1.4.1.311.10.9.1") )
      {
        v22 = 23;
      }
      else
      {
        v21 = lpszStructType;
        if ( !strcmp_0(lpszStructType, "1.3.6.1.4.1.311.10.2") )
        {
          v22 = 10;
        }
        else if ( !strcmp_0(v21, "1.3.6.1.5.5.7.1.1") )
        {
          v22 = 68;
        }
        else if ( !strcmp_0(v21, "1.3.6.1.4.1.311.10.11.85") )
        {
          v22 = 85;
        }
        else
        {
          if ( strcmp_0(v21, "1.3.6.1.5.5.7.1.11") )
            goto LABEL_26;
          v22 = 80;
        }
      }
      if ( v42 == (char *)1 )
      {
        CertificateContextProperty = CertGetCertificateContextProperty(pCertContext, v22, 0, cbEncoded);
      }
      else if ( v42 == (char *)3 )
      {
        CertificateContextProperty = CertGetCTLContextProperty((PCCTL_CONTEXT)pCertContext, v22, 0, cbEncoded);
      }
      else if ( v42 == (char *)2 )
      {
        CertificateContextProperty = CertGetCRLContextProperty((PCCRL_CONTEXT)pCertContext, v22, 0, cbEncoded);
      }
      else
      {
        SetLastError(0x80070057);
        CertificateContextProperty = 0;
      }
      if ( CertificateContextProperty != 1 )
        goto LABEL_16;
      v29 = (BYTE *)operator new(cbEncoded[0]);
      pbEncoded = v29;
      if ( !v29 )
      {
LABEL_45:
        CertificateContextProperty = 0;
        SetLastError(0x8007000E);
        ++v18;
        goto LABEL_31;
      }
      v37 = 1;
      CertificateContextProperty = ObjectContextGetProperty(v42, (void *)pCertContext, v22, v29, cbEncoded);
LABEL_15:
      if ( CertificateContextProperty != 1 )
        goto LABEL_16;
      goto LABEL_27;
    }
    if ( LODWORD(v46[2 * v19]) == 2 )
    {
      if ( v9 == (char *)1 )
      {
        pCertInfo = v12->pCertInfo;
        cExtension = pCertInfo->cExtension;
        rgExtension = pCertInfo->rgExtension;
      }
      else if ( v9 == (char *)3 )
      {
        v33 = v12->pCertInfo;
        cExtension = (DWORD)v33->SubjectPublicKeyInfo.Algorithm.Parameters.pbData;
        rgExtension = *(CERT_EXTENSION **)&v33->SubjectPublicKeyInfo.PublicKey.cbData;
      }
      else
      {
        if ( v9 != (char *)2 )
          goto LABEL_26;
        v30 = v12->pCertInfo;
        cExtension = v30->Subject.cbData;
        rgExtension = (CERT_EXTENSION *)v30->Subject.pbData;
      }
      Extension = CertFindExtension(v10, cExtension, rgExtension);
      if ( !Extension )
        goto LABEL_26;
      cbEncoded[0] = Extension->Value.cbData;
      pbEncoded = Extension->Value.pbData;
      goto LABEL_27;
    }
    if ( LODWORD(v46[2 * v19]) != 4 && LODWORD(v46[2 * v19]) != 8 )
      goto LABEL_15;
    CertificateContextProperty = ObjectContextGetAttribute(
                                   v9,
                                   (void *)pCertContext,
                                   v39,
                                   v20,
                                   v10,
                                   0,
                                   (unsigned int *)&uBytes);
    if ( CertificateContextProperty != 1 )
      goto LABEL_15;
    v31 = (struct _CRYPT_ATTRIBUTE *)operator new((unsigned int)uBytes);
    hMem = v31;
    if ( !v31 )
      goto LABEL_45;
    CertificateContextProperty = ObjectContextGetAttribute(
                                   v42,
                                   (void *)pCertContext,
                                   v39,
                                   v20,
                                   lpszStructType,
                                   v31,
                                   (unsigned int *)&uBytes);
    if ( CertificateContextProperty != 1 )
      goto LABEL_15;
    v32 = *((_QWORD *)hMem + 2);
    cbEncoded[0] = *(_DWORD *)v32;
    pbEncoded = *(BYTE **)(v32 + 8);
LABEL_27:
    CertificateContextProperty = CryptDecodeObject(
                                   1u,
                                   lpszStructType,
                                   pbEncoded,
                                   cbEncoded[0],
                                   0,
                                   0,
                                   (DWORD *)&uBytes + 1);
    if ( CertificateContextProperty != 1 )
      goto LABEL_16;
    pvStructInfo = LocalAlloc(0x40u, HIDWORD(uBytes));
    if ( !pvStructInfo )
    {
      SetLastError(0x8007000E);
      SetLastError(8u);
LABEL_26:
      CertificateContextProperty = 0;
LABEL_16:
      ++v18;
      goto LABEL_31;
    }
    CertificateContextProperty = CryptDecodeObject(
                                   1u,
                                   lpszStructType,
                                   pbEncoded,
                                   cbEncoded[0],
                                   0,
                                   pvStructInfo,
                                   (DWORD *)&uBytes + 1);
    if ( CertificateContextProperty != 1 )
    {
      operator delete(pvStructInfo);
      goto LABEL_16;
    }
    v46[2 * v19] = pvStructInfo;
LABEL_31:
    if ( v37 == 1 )
    {
      operator delete(pbEncoded);
      v37 = 0;
    }
    if ( hMem )
    {
      operator delete(hMem);
      hMem = 0;
    }
    v10 = lpszStructType;
    ++v19;
    v9 = v42;
    v12 = pCertContext;
  }
  while ( v19 < v13 );
  v8 = v43;
  v7 = v44;
LABEL_37:
  if ( v18 == v13 )
  {
    SetLastError(0x80092004);
    return 0;
  }
  else
  {
    memcpy_0(v7, &Src, 16LL * v13);
    *v8 = v13;
  }
  return v11;
}

```

## disassembly

```asm
0x180014df0  push    rbp
0x180014df2  push    rbx
0x180014df3  push    r13
0x180014df5  push    r14
0x180014df7  push    r15
0x180014df9  lea     rbp, [rsp-1Fh]
0x180014dfe  sub     rsp, 100h
0x180014e05  mov     rax, cs:__security_cookie
0x180014e0c  xor     rax, rsp
0x180014e0f  mov     [rbp+3Fh+var_40], rax
0x180014e13  mov     r11, [rbp+3Fh+arg_28]
0x180014e17  xor     r15d, r15d
0x180014e1a  mov     r14, [rbp+3Fh+arg_30]
0x180014e1e  mov     r10, rcx
0x180014e21  mov     [rbp+3Fh+var_A0], rcx
0x180014e25  mov     ebx, r9d
0x180014e28  mov     rcx, [rbp+3Fh+Str1]; Str1
0x180014e2c  mov     r13d, 1
0x180014e32  mov     [rbp+3Fh+var_B8], r8d
0x180014e36  mov     r8, rdx
0x180014e39  mov     [rbp+3Fh+lpszStructType], rcx
0x180014e3d  mov     [rsp+120h+pCertContext], rdx
0x180014e42  mov     [rbp+3Fh+var_90], r11
0x180014e46  mov     [rbp+3Fh+var_98], r14
0x180014e4a  mov     qword ptr [rsp+120h+cbEncoded], r15
0x180014e4f  mov     [rsp+120h+pbEncoded], r15
0x180014e54  mov     dword ptr [rsp+120h+uBytes+4], r15d
0x180014e59  mov     dword ptr [rsp+120h+uBytes], r15d
0x180014e5e  and     ebx, r13d
0x180014e61  jz      short loc_180014E6B
0x180014e63  mov     [rbp+3Fh+Src], r13d
0x180014e67  mov     [rbp+3Fh+var_78], r15
0x180014e6b  test    r9b, 2
0x180014e6f  jz      short loc_180014E85
0x180014e71  mov     eax, ebx
0x180014e73  add     rax, rax
0x180014e76  inc     ebx
0x180014e78  mov     [rbp+rax*8+3Fh+Src], 2
0x180014e80  mov     [rbp+rax*8+3Fh+var_78], r15
0x180014e85  test    r9b, 4
0x180014e89  jz      short loc_180014E9F
0x180014e8b  mov     eax, ebx
0x180014e8d  add     rax, rax
0x180014e90  inc     ebx
0x180014e92  mov     [rbp+rax*8+3Fh+Src], 4
0x180014e9a  mov     [rbp+rax*8+3Fh+var_78], r15
0x180014e9f  test    r9b, 8
0x180014ea3  jz      short loc_180014EB9
0x180014ea5  mov     eax, ebx
0x180014ea7  add     rax, rax
0x180014eaa  inc     ebx
0x180014eac  mov     [rbp+rax*8+3Fh+Src], 8
0x180014eb4  mov     [rbp+rax*8+3Fh+var_78], r15
0x180014eb9  cmp     [r14], ebx
0x180014ebc  jb      loc_18001516A
0x180014ec2  mov     [rsp+120h+arg_0], rsi
0x180014eca  mov     esi, r13d
0x180014ecd  mov     [rsp+120h+var_28], rdi
0x180014ed5  mov     edi, r15d
0x180014ed8  mov     [rsp+120h+var_30], r12
0x180014ee0  mov     r12d, r15d
0x180014ee3  mov     [rsp+120h+var_C8], r15d
0x180014ee8  mov     [rbp+3Fh+hMem], r15
0x180014eec  test    ebx, ebx
0x180014eee  jz      loc_1800150A3
0x180014ef4  mov     r15d, r12d
0x180014ef7  add     r15, r15
0x180014efa  mov     r14d, [rbp+r15*8+3Fh+Src]
0x180014eff  mov     eax, r14d
0x180014f02  sub     eax, r13d
0x180014f05  jz      short loc_180014F32
0x180014f07  sub     eax, r13d
0x180014f0a  jz      loc_180014FA7
0x180014f10  sub     eax, 2
0x180014f13  jz      loc_1800151C2
0x180014f19  cmp     eax, 4
0x180014f1c  jz      loc_1800151C2
0x180014f22  cmp     esi, r13d
0x180014f25  jz      loc_180014FD7
0x180014f2b  inc     edi
0x180014f2d  jmp     loc_180015067
0x180014f32  cmp     rcx, 0FFFFh
0x180014f39  jbe     loc_180014FD0
0x180014f3f  lea     rdx, a1361413111091; "1.3.6.1.4.1.311.10.9.1"
0x180014f46  call    strcmp_0
0x180014f4b  test    eax, eax
0x180014f4d  jz      loc_180015288
0x180014f53  mov     rsi, [rbp+3Fh+lpszStructType]
0x180014f57  lea     rdx, a136141311102; "1.3.6.1.4.1.311.10.2"
0x180014f5e  mov     rcx, rsi; Str1
0x180014f61  call    strcmp_0
0x180014f66  test    eax, eax
0x180014f68  jz      loc_180015293
0x180014f6e  lea     rdx, a136155711; "1.3.6.1.5.5.7.1.1"
0x180014f75  mov     rcx, rsi; Str1
0x180014f78  call    strcmp_0
0x180014f7d  test    eax, eax
0x180014f7f  jz      loc_1800150F8
0x180014f85  lea     rdx, a13614131110118; "1.3.6.1.4.1.311.10.11.85"
0x180014f8c  mov     rcx, rsi; Str1
0x180014f8f  call    strcmp_0
0x180014f94  test    eax, eax
0x180014f96  jnz     loc_1800151A0
0x180014f9c  mov     r14d, 55h ; 'U'
0x180014fa2  jmp     loc_1800150FE
0x180014fa7  cmp     r10, r13
0x180014faa  jnz     loc_18001517C
0x180014fb0  mov     rax, [r8+18h]
0x180014fb4  mov     edx, [rax+0C0h]; cExtensions
0x180014fba  mov     r8, [rax+0C8h]; rgExtensions
0x180014fc1  call    cs:__imp_CertFindExtension
0x180014fc7  test    rax, rax
0x180014fca  jnz     loc_180015273
0x180014fd0  xor     esi, esi
0x180014fd2  jmp     loc_180014F2B
0x180014fd7  mov     r9d, [rsp+120h+cbEncoded]; cbEncoded
0x180014fdc  lea     rax, [rsp+120h+uBytes+4]
0x180014fe1  mov     r8, [rsp+120h+pbEncoded]; pbEncoded
0x180014fe6  mov     ecx, r13d; dwCertEncodingType
0x180014fe9  mov     rdx, [rbp+3Fh+lpszStructType]; lpszStructType
0x180014fed  mov     [rsp+120h+pcbStructInfo], rax; pcbStructInfo
0x180014ff2  xor     eax, eax
0x180014ff4  mov     [rsp+120h+pvStructInfo], rax; pvStructInfo
0x180014ff9  mov     [rsp+120h+dwFlags], eax; dwFlags
0x180014ffd  call    cs:__imp_CryptDecodeObject
0x180015003  mov     esi, eax
0x180015005  cmp     eax, r13d
0x180015008  jnz     loc_180014F2B
0x18001500e  mov     edx, dword ptr [rsp+120h+uBytes+4]; uBytes
0x180015012  mov     ecx, 40h ; '@'; uFlags
0x180015017  call    cs:__imp_LocalAlloc
0x18001501d  mov     r14, rax
0x180015020  test    rax, rax
0x180015023  jz      loc_180015320
0x180015029  mov     r9d, [rsp+120h+cbEncoded]; cbEncoded
0x18001502e  lea     rax, [rsp+120h+uBytes+4]
0x180015033  mov     r8, [rsp+120h+pbEncoded]; pbEncoded
0x180015038  mov     ecx, r13d; dwCertEncodingType
0x18001503b  mov     rdx, [rbp+3Fh+lpszStructType]; lpszStructType
0x18001503f  mov     [rsp+120h+pcbStructInfo], rax; pcbStructInfo
0x180015044  mov     [rsp+120h+pvStructInfo], r14; pvStructInfo
0x180015049  mov     [rsp+120h+dwFlags], 0; dwFlags
0x180015051  call    cs:__imp_CryptDecodeObject
0x180015057  mov     esi, eax
0x180015059  cmp     eax, r13d
0x18001505c  jnz     loc_18001533B
0x180015062  mov     [rbp+r15*8+3Fh+var_78], r14
0x180015067  cmp     [rsp+120h+var_C8], r13d
0x18001506c  jz      loc_180015348
0x180015072  mov     rdx, [rbp+3Fh+hMem]
0x180015076  test    rdx, rdx
0x180015079  jnz     loc_18001535D
0x18001507f  mov     rcx, [rbp+3Fh+lpszStructType]
0x180015083  inc     r12d
0x180015086  mov     r10, [rbp+3Fh+var_A0]
0x18001508a  mov     r8, [rsp+120h+pCertContext]
0x18001508f  cmp     r12d, ebx
0x180015092  jb      loc_180014EF4
0x180015098  mov     r14, [rbp+3Fh+var_98]
0x18001509c  xor     r15d, r15d
0x18001509f  mov     r11, [rbp+3Fh+var_90]
0x1800150a3  mov     r12, [rsp+120h+var_30]
0x1800150ab  cmp     edi, ebx
0x1800150ad  mov     rdi, [rsp+120h+var_28]
0x1800150b5  mov     rsi, [rsp+120h+arg_0]
0x1800150bd  jz      loc_180015157
0x1800150c3  mov     r8d, ebx
0x1800150c6  lea     rdx, [rbp+3Fh+Src]; Src
0x1800150ca  shl     r8, 4; Size
0x1800150ce  mov     rcx, r11; void *
0x1800150d1  call    memcpy_0
0x1800150d6  mov     [r14], ebx
0x1800150d9  mov     eax, r13d
0x1800150dc  mov     rcx, [rbp+3Fh+var_40]
0x1800150e0  xor     rcx, rsp; StackCookie
0x1800150e3  call    __security_check_cookie
0x1800150e8  add     rsp, 100h
0x1800150ef  pop     r15
0x1800150f1  pop     r14
0x1800150f3  pop     r13
0x1800150f5  pop     rbx
0x1800150f6  pop     rbp
0x1800150f7  retn
0x1800150f8  mov     r14d, 44h ; 'D'
0x1800150fe  mov     rax, [rbp+3Fh+var_A0]
0x180015102  cmp     rax, r13
0x180015105  jnz     loc_18001529E
0x18001510b  mov     rcx, [rsp+120h+pCertContext]; pCertContext
0x180015110  lea     r9, [rsp+120h+cbEncoded]; pcbData
0x180015115  xor     r8d, r8d; pvData
0x180015118  mov     edx, r14d; dwPropId
0x18001511b  call    cs:__imp_CertGetCertificateContextProperty
0x180015121  mov     esi, eax
0x180015123  cmp     esi, r13d
0x180015126  jnz     loc_180014F2B
0x18001512c  mov     ecx, [rsp+120h+cbEncoded]; uBytes
0x180015130  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015135  mov     [rsp+120h+pbEncoded], rax
0x18001513a  test    rax, rax
0x18001513d  jnz     loc_1800152F6
0x180015143  mov     ecx, 8007000Eh; dwErrCode
0x180015148  xor     esi, esi
0x18001514a  call    cs:__imp_SetLastError
0x180015150  inc     edi
0x180015152  jmp     loc_180015067
0x180015157  mov     ecx, 80092004h; dwErrCode
0x18001515c  call    cs:__imp_SetLastError
0x180015162  mov     r13d, r15d
0x180015165  jmp     loc_1800150D9
0x18001516a  mov     ecx, 80070057h; dwErrCode
0x18001516f  call    cs:__imp_SetLastError
0x180015175  xor     eax, eax
0x180015177  jmp     loc_1800150DC
0x18001517c  cmp     r10, 3
0x180015180  jz      loc_180015263
0x180015186  cmp     r10, 2
0x18001518a  jnz     loc_180014FD0
0x180015190  mov     rax, [r8+18h]
0x180015194  mov     edx, [rax+50h]
0x180015197  mov     r8, [rax+58h]
0x18001519b  jmp     loc_180014FC1
0x1800151a0  lea     rdx, a1361557111; "1.3.6.1.5.5.7.1.11"
0x1800151a7  mov     rcx, rsi; Str1
0x1800151aa  call    strcmp_0
0x1800151af  test    eax, eax
0x1800151b1  jnz     loc_180014FD0
0x1800151b7  mov     r14d, 50h ; 'P'
0x1800151bd  jmp     loc_1800150FE
0x1800151c2  mov     r8d, [rbp+3Fh+var_B8]; unsigned int
0x1800151c6  lea     rax, [rsp+120h+uBytes]
0x1800151cb  mov     rdx, [rsp+120h+pCertContext]; void *
0x1800151d0  mov     r9d, r14d; unsigned int
0x1800151d3  mov     [rsp+120h+pcbStructInfo], rax; unsigned int *
0x1800151d8  mov     [rsp+120h+pvStructInfo], 0; struct _CRYPT_ATTRIBUTE *
0x1800151e1  mov     qword ptr [rsp+120h+dwFlags], rcx; char *
0x1800151e6  mov     rcx, r10; char *
0x1800151e9  call    ?ObjectContextGetAttribute@@YAHPEBDPEAXKK0PEAU_CRYPT_ATTRIBUTE@@PEAK@Z; ObjectContextGetAttribute(char const *,void *,ulong,ulong,char const *,_CRYPT_ATTRIBUTE *,ulong *)
0x1800151ee  mov     esi, eax
0x1800151f0  cmp     eax, r13d
0x1800151f3  jnz     loc_180014F22
0x1800151f9  mov     ecx, dword ptr [rsp+120h+uBytes]; uBytes
0x1800151fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015202  mov     [rbp+3Fh+hMem], rax
0x180015206  test    rax, rax
0x180015209  jz      loc_180015143
0x18001520f  mov     r8d, [rbp+3Fh+var_B8]; unsigned int
0x180015213  lea     rcx, [rsp+120h+uBytes]
0x180015218  mov     rdx, [rsp+120h+pCertContext]; void *
0x18001521d  mov     r9d, r14d; unsigned int
0x180015220  mov     [rsp+120h+pcbStructInfo], rcx; unsigned int *
0x180015225  mov     rcx, [rbp+3Fh+lpszStructType]
0x180015229  mov     [rsp+120h+pvStructInfo], rax; struct _CRYPT_ATTRIBUTE *
0x18001522e  mov     qword ptr [rsp+120h+dwFlags], rcx; char *
0x180015233  mov     rcx, [rbp+3Fh+var_A0]; char *
0x180015237  call    ?ObjectContextGetAttribute@@YAHPEBDPEAXKK0PEAU_CRYPT_ATTRIBUTE@@PEAK@Z; ObjectContextGetAttribute(char const *,void *,ulong,ulong,char const *,_CRYPT_ATTRIBUTE *,ulong *)
0x18001523c  mov     esi, eax
0x18001523e  cmp     eax, r13d
0x180015241  jnz     loc_180014F22
0x180015247  mov     rcx, [rbp+3Fh+hMem]
0x18001524b  mov     rcx, [rcx+10h]
0x18001524f  mov     eax, [rcx]
0x180015251  mov     [rsp+120h+cbEncoded], eax
0x180015255  mov     rax, [rcx+8]
0x180015259  mov     [rsp+120h+pbEncoded], rax
0x18001525e  jmp     loc_180014FD7
0x180015263  mov     rax, [r8+18h]
0x180015267  mov     edx, [rax+70h]
0x18001526a  mov     r8, [rax+78h]
0x18001526e  jmp     loc_180014FC1
0x180015273  mov     ecx, [rax+10h]
0x180015276  mov     [rsp+120h+cbEncoded], ecx
0x18001527a  mov     rax, [rax+18h]
0x18001527e  mov     [rsp+120h+pbEncoded], rax
0x180015283  jmp     loc_180014FD7
0x180015288  mov     r14d, 17h
0x18001528e  jmp     loc_1800150FE
0x180015293  mov     r14d, 0Ah
0x180015299  jmp     loc_1800150FE
0x18001529e  cmp     rax, 3
0x1800152a2  jnz     short loc_1800152C1
0x1800152a4  mov     rcx, [rsp+120h+pCertContext]; pCtlContext
0x1800152a9  lea     r9, [rsp+120h+cbEncoded]; pcbData
0x1800152ae  xor     r8d, r8d; pvData
0x1800152b1  mov     edx, r14d; dwPropId
0x1800152b4  call    cs:__imp_CertGetCTLContextProperty
0x1800152ba  mov     esi, eax
0x1800152bc  jmp     loc_180015123
0x1800152c1  cmp     rax, 2
0x1800152c5  jnz     short loc_1800152E4
0x1800152c7  mov     rcx, [rsp+120h+pCertContext]; pCrlContext
0x1800152cc  lea     r9, [rsp+120h+cbEncoded]; pcbData
0x1800152d1  xor     r8d, r8d; pvData
0x1800152d4  mov     edx, r14d; dwPropId
0x1800152d7  call    cs:__imp_CertGetCRLContextProperty
0x1800152dd  mov     esi, eax
0x1800152df  jmp     loc_180015123
0x1800152e4  mov     ecx, 80070057h; dwErrCode
0x1800152e9  call    cs:__imp_SetLastError
0x1800152ef  xor     esi, esi
0x1800152f1  jmp     loc_180015123
  ... truncated ...
```
