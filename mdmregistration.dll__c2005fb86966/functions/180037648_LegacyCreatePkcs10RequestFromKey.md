# LegacyCreatePkcs10RequestFromKey

- ea: `0x180037648`
- end: `0x180037b0f`
- name: `LegacyCreatePkcs10RequestFromKey`
- size: `1223`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x1800141b0`
- `0x180031628`
- `0x180033aa0`
- `0x180033bb8`
- `0x180037648`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037824`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037993`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037824`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037ac8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003780d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003797c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ab4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003780d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003797c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a00`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180037966`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800379de`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x180037966`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800379de`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800377eb`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18003785f`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800377eb`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x18003785f`

## string_xrefs

- `0x180037734`: `LegacyCreatePkcs10RequestFromKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LegacyCreatePkcs10RequestFromKey(
        HKEY a1,
        const char *a2,
        unsigned int a3,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a4,
        CHAR *a5,
        struct _CERT_PUBLIC_KEY_INFO **a6,
        DWORD *a7,
        BYTE **a8,
        DWORD *pcbEncoded)
{
  struct _CERT_PUBLIC_KEY_INFO *v12; // rdi
  int v13; // ecx
  DWORD v14; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v16; // ebx
  HANDLE v17; // rax
  BYTE *pbEncoded; // rax
  signed int LastError; // eax
  void *v20; // rbx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  HANDLE v24; // rax
  BYTE *v25; // rbx
  HANDLE v26; // rax
  unsigned int v27; // ebx
  int v29; // [rsp+58h] [rbp-B0h] BYREF
  DWORD pcbInfo; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned int v31; // [rsp+60h] [rbp-A8h] BYREF
  int v32; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  _QWORD lpMem[3]; // [rsp+70h] [rbp-98h] BYREF
  const char *v35; // [rsp+88h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-78h]
  const char *v37; // [rsp+A0h] [rbp-68h]
  HKEY v38; // [rsp+A8h] [rbp-60h]
  CHAR *v39; // [rsp+B0h] [rbp-58h]
  DWORD *v40; // [rsp+B8h] [rbp-50h]
  _CERT_EXTENSIONS v41; // [rsp+C0h] [rbp-48h] BYREF
  const char *v42; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v43; // [rsp+D8h] [rbp-30h]
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v45[3]; // [rsp+100h] [rbp-8h] BYREF
  _DWORD pvStructInfo[4]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v47; // [rsp+128h] [rbp+20h]
  __int128 v48; // [rsp+130h] [rbp+28h]
  __int128 v49; // [rsp+140h] [rbp+38h]
  __int128 v50; // [rsp+150h] [rbp+48h]
  int v51; // [rsp+160h] [rbp+58h]
  const char **v52; // [rsp+168h] [rbp+60h]
  __int128 v53; // [rsp+178h] [rbp+70h]
  __int128 v54; // [rsp+188h] [rbp+80h]
  char v55[80]; // [rsp+198h] [rbp+90h] BYREF

  LODWORD(v33) = a3;
  v38 = a1;
  v39 = a5;
  v40 = a7;
  v29 = 0;
  v53 = 0;
  memset(lpMem, 0, sizeof(lpMem));
  v12 = 0;
  pcbInfo = 0;
  memset_0(pvStructInfo, 0, 0x58u);
  v32 = 0;
  memset(&pSignatureAlgorithm, 0, sizeof(pSignatureAlgorithm));
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v54 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  memset_0(v55, 0, 0x41u);
  v31 = 65;
  v45[0] = "LegacyCreatePkcs10RequestFromKey";
  v45[1] = &v29;
  if ( !a8 || !pcbEncoded || !a6 )
  {
    v29 = -2147467261;
    goto LABEL_21;
  }
  *pcbEncoded = 0;
  *a8 = 0;
  v29 = CreateCertificateName(0, v38, a2, a3, v55, &v31);
  if ( v29 >= 0 )
  {
    v29 = EncodeNameAttr(v13, (unsigned int)v55, v31 - 1, (unsigned int)lpMem, (__int64)&v32);
    if ( v29 >= 0 )
    {
      if ( !CryptExportPublicKeyInfo(a4, 0, 0x10001u, 0, &pcbInfo) || !pcbInfo )
        goto LABEL_18;
      v14 = pcbInfo;
      ProcessHeap = GetProcessHeap();
      v12 = (struct _CERT_PUBLIC_KEY_INFO *)HeapAlloc(ProcessHeap, 8u, v14);
      if ( !v12 )
      {
LABEL_10:
        v29 = -2147024882;
        goto LABEL_21;
      }
      if ( !CryptExportPublicKeyInfo(a4, 0, 0x10001u, v12, &pcbInfo) || !pcbInfo )
        goto LABEL_18;
      pvStructInfo[0] = 0;
      pvStructInfo[2] = v32;
      pvStructInfo[3] = DWORD1(v53);
      v47 = lpMem[0];
      v48 = *(_OWORD *)&v12->Algorithm.pszObjId;
      v49 = *(_OWORD *)&v12->Algorithm.Parameters.pbData;
      v50 = *(_OWORD *)&v12->PublicKey.pbData;
      v51 = 0;
      v52 = 0;
      LODWORD(v36) = 0;
      v35 = "1.3.6.1.4.1.311.66.1.0";
      *((_QWORD *)&v36 + 1) = __PAIR64__(DWORD1(v54), v33);
      v37 = a2;
      v41.cExtension = 1;
      v41.rgExtension = (PCERT_EXTENSION)&v35;
      v29 = EncodeExtensions(&v41, (DWORD *)&lpMem[1]);
      if ( v29 < 0 )
        goto LABEL_21;
      LODWORD(v43) = 1;
      v42 = "1.2.840.113549.1.9.14";
      *((_QWORD *)&v43 + 1) = &lpMem[1];
      v51 = 1;
      v52 = &v42;
      pSignatureAlgorithm.pszObjId = v39;
      pSignatureAlgorithm.Parameters = 0;
      if ( !CryptSignAndEncodeCertificate(
              a4,
              0,
              0x10001u,
              (LPCSTR)4,
              pvStructInfo,
              &pSignatureAlgorithm,
              0,
              0,
              pcbEncoded) )
        goto LABEL_18;
      v16 = *pcbEncoded;
      v17 = GetProcessHeap();
      pbEncoded = (BYTE *)HeapAlloc(v17, 8u, v16);
      *a8 = pbEncoded;
      if ( !pbEncoded )
        goto LABEL_10;
      if ( CryptSignAndEncodeCertificate(
             a4,
             0,
             0x10001u,
             (LPCSTR)4,
             pvStructInfo,
             &pSignatureAlgorithm,
             0,
             pbEncoded,
             pcbEncoded) )
      {
        *a6 = v12;
        v12 = 0;
        *v40 = pcbInfo;
      }
      else
      {
LABEL_18:
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v29 = LastError;
      }
    }
  }
LABEL_21:
  v20 = (void *)lpMem[2];
  if ( lpMem[2] )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v20);
  }
  lpMem[2] = 0;
  v22 = (void *)lpMem[0];
  if ( lpMem[0] )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  if ( v12 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v12);
  }
  if ( v29 < 0 )
  {
    if ( a8 )
    {
      *pcbEncoded = 0;
      v25 = *a8;
      if ( *a8 )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v25);
      }
    }
  }
  v27 = v29;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v45);
  return v27;
}

```

## disassembly

```asm
0x180037648  mov     rax, rsp
0x18003764b  push    rbp
0x18003764c  push    rbx
0x18003764d  push    rsi
0x18003764e  push    rdi
0x18003764f  push    r12
0x180037651  push    r13
0x180037653  push    r14
0x180037655  push    r15
0x180037657  lea     rbp, [rax-148h]
0x18003765e  sub     rsp, 208h
0x180037665  movaps  xmmword ptr [rax-58h], xmm6
0x180037669  mov     rax, cs:__security_cookie
0x180037670  xor     rax, rsp
0x180037673  mov     [rbp+140h+var_60], rax
0x18003767a  mov     r15, r9
0x18003767d  mov     ebx, r8d
0x180037680  mov     dword ptr [rsp+240h+var_1E0], ebx
0x180037684  mov     r13, rdx
0x180037687  mov     [rbp+140h+var_1A0], rcx
0x18003768b  mov     rax, [rbp+140h+arg_20]
0x180037692  mov     [rbp+140h+var_198], rax
0x180037696  mov     r12, [rbp+140h+arg_28]
0x18003769d  mov     rax, [rbp+140h+arg_30]
0x1800376a4  mov     [rbp+140h+var_190], rax
0x1800376a8  mov     r14, [rbp+140h+arg_38]
0x1800376af  mov     rsi, [rbp+140h+pcbEncoded]
0x1800376b6  xor     eax, eax
0x1800376b8  mov     [rsp+240h+var_1F0], eax
0x1800376bc  xorps   xmm0, xmm0
0x1800376bf  movups  [rbp+140h+var_D0], xmm0
0x1800376c3  xorps   xmm6, xmm6
0x1800376c6  mov     qword ptr [rsp+240h+lpMem], rax
0x1800376cb  mov     edi, eax
0x1800376cd  mov     [rsp+240h+var_1EC], eax
0x1800376d1  xor     edx, edx; Val
0x1800376d3  lea     r8d, [rax+58h]; Size
0x1800376d7  lea     rcx, [rbp+140h+pvStructInfo]; void *
0x1800376db  call    memset_0
0x1800376e0  xor     ecx, ecx
0x1800376e2  mov     [rsp+240h+var_1E4], ecx
0x1800376e6  xorps   xmm0, xmm0
0x1800376e9  xor     eax, eax
0x1800376eb  movups  xmmword ptr [rbp+140h+var_160.pszObjId], xmm0
0x1800376ef  mov     [rbp+140h+var_160.Parameters.pbData], rax
0x1800376f3  mov     [rbp+140h+var_1C0], rcx
0x1800376f7  movups  [rbp+140h+var_1B8], xmm0
0x1800376fb  mov     [rbp+140h+var_1A8], rax
0x1800376ff  movups  [rbp+140h+var_C0], xmm0
0x180037706  xorps   xmm1, xmm1
0x180037709  movups  xmmword ptr [rbp+140h+var_188.cExtension], xmm1
0x18003770d  movups  xmmword ptr [rsp+240h+lpMem+8], xmm0
0x180037712  mov     [rbp+140h+var_178], rcx
0x180037716  movups  [rbp+140h+var_170], xmm1
0x18003771a  xor     edx, edx; Val
0x18003771c  lea     r8d, [rdi+41h]; Size
0x180037720  lea     rcx, [rbp+140h+var_B0]; void *
0x180037727  call    memset_0
0x18003772c  mov     [rsp+240h+var_1E8], 41h ; 'A'
0x180037734  lea     rax, aLegacycreatepk_0; "LegacyCreatePkcs10RequestFromKey"
0x18003773b  mov     [rbp+140h+var_148], rax
0x18003773f  lea     rax, [rsp+240h+var_1F0]
0x180037744  mov     [rbp+140h+var_140], rax
0x180037748  test    r14, r14
0x18003774b  jnz     short loc_18003775A
0x18003774d  mov     [rsp+240h+var_1F0], 80004003h
0x180037755  jmp     loc_180037A1C
0x18003775a  test    rsi, rsi
0x18003775d  jz      short loc_18003774D
0x18003775f  test    r12, r12
0x180037762  jz      short loc_18003774D
0x180037764  mov     dword ptr [rsi], 0
0x18003776a  mov     qword ptr [r14], 0
0x180037771  lea     rax, [rsp+240h+var_1E8]
0x180037776  mov     [rsp+240h+pSignatureAlgorithm], rax; unsigned int *
0x18003777b  lea     rax, [rbp+140h+var_B0]
0x180037782  mov     [rsp+240h+pcbInfo], rax; char *
0x180037787  mov     r9d, ebx; unsigned int
0x18003778a  mov     r8, r13; unsigned __int8 *
0x18003778d  mov     rdx, [rbp+140h+var_1A0]; HKEY
0x180037791  xor     ecx, ecx; bool
0x180037793  call    ?CreateCertificateName@@YAJ_NPEAUHKEY__@@PEBEKPEADPEAK@Z; CreateCertificateName(bool,HKEY__ *,uchar const *,ulong,char *,ulong *)
0x180037798  mov     [rsp+240h+var_1F0], eax
0x18003779c  test    eax, eax
0x18003779e  js      loc_180037A1C
0x1800377a4  mov     r8d, [rsp+240h+var_1E8]
0x1800377a9  dec     r8d
0x1800377ac  lea     rax, [rsp+240h+var_1E4]
0x1800377b1  mov     [rsp+240h+pcbInfo], rax
0x1800377b6  lea     r9, [rsp+240h+lpMem]
0x1800377bb  lea     rdx, [rbp+140h+var_B0]
0x1800377c2  call    EncodeNameAttr
0x1800377c7  mov     [rsp+240h+var_1F0], eax
0x1800377cb  test    eax, eax
0x1800377cd  js      loc_180037A1C
0x1800377d3  lea     rax, [rsp+240h+var_1EC]
0x1800377d8  mov     [rsp+240h+pcbInfo], rax; pcbInfo
0x1800377dd  xor     r9d, r9d; pInfo
0x1800377e0  xor     edx, edx; dwKeySpec
0x1800377e2  mov     r8d, 10001h; dwCertEncodingType
0x1800377e8  mov     rcx, r15; hCryptProvOrNCryptKey
0x1800377eb  call    cs:__imp_CryptExportPublicKeyInfo
0x1800377f2  nop     dword ptr [rax+rax+00h]
0x1800377f7  test    eax, eax
0x1800377f9  jz      loc_180037A00
0x1800377ff  mov     eax, [rsp+240h+var_1EC]
0x180037803  test    eax, eax
0x180037805  jz      loc_180037A00
0x18003780b  mov     ebx, eax
0x18003780d  call    cs:__imp_GetProcessHeap
0x180037814  nop     dword ptr [rax+rax+00h]
0x180037819  mov     rcx, rax; hHeap
0x18003781c  mov     r8d, ebx; dwBytes
0x18003781f  mov     edx, 8; dwFlags
0x180037824  call    cs:__imp_HeapAlloc
0x18003782b  nop     dword ptr [rax+rax+00h]
0x180037830  mov     rdi, rax
0x180037833  xor     ebx, ebx
0x180037835  test    rax, rax
0x180037838  jnz     short loc_180037847
0x18003783a  mov     [rsp+240h+var_1F0], 8007000Eh
0x180037842  jmp     loc_180037A1C
0x180037847  lea     rax, [rsp+240h+var_1EC]
0x18003784c  mov     [rsp+240h+pcbInfo], rax; pcbInfo
0x180037851  mov     r9, rdi; pInfo
0x180037854  xor     edx, edx; dwKeySpec
0x180037856  mov     r8d, 10001h; dwCertEncodingType
0x18003785c  mov     rcx, r15; hCryptProvOrNCryptKey
0x18003785f  call    cs:__imp_CryptExportPublicKeyInfo
0x180037866  nop     dword ptr [rax+rax+00h]
0x18003786b  test    eax, eax
0x18003786d  jz      loc_180037A00
0x180037873  cmp     [rsp+240h+var_1EC], ebx
0x180037877  jz      loc_180037A00
0x18003787d  mov     [rbp+140h+pvStructInfo], ebx
0x180037880  mov     eax, [rsp+240h+var_1E4]
0x180037884  mov     [rbp+140h+var_128], eax
0x180037887  mov     eax, dword ptr [rbp+140h+var_D0+4]
0x18003788a  mov     [rbp+140h+var_124], eax
0x18003788d  mov     rax, qword ptr [rsp+240h+lpMem]
0x180037892  mov     [rbp+140h+var_120], rax
0x180037896  movups  xmm0, xmmword ptr [rdi]
0x180037899  movups  [rbp+140h+var_118], xmm0
0x18003789d  movups  xmm1, xmmword ptr [rdi+10h]
0x1800378a1  movups  [rbp+140h+var_108], xmm1
0x1800378a5  movups  xmm0, xmmword ptr [rdi+20h]
0x1800378a9  movups  [rbp+140h+var_F8], xmm0
0x1800378ad  mov     [rbp+140h+var_E8], ebx
0x1800378b0  mov     [rbp+140h+var_E0], rbx
0x1800378b4  mov     dword ptr [rbp+140h+var_1B8], ebx
0x1800378b7  lea     rax, a1361413116610_0; "1.3.6.1.4.1.311.66.1.0"
0x1800378be  mov     [rbp+140h+var_1C0], rax
0x1800378c2  mov     eax, dword ptr [rsp+240h+var_1E0]
0x1800378c6  mov     dword ptr [rbp+140h+var_1B8+8], eax
0x1800378c9  mov     eax, dword ptr [rbp+140h+var_C0+4]
0x1800378cf  mov     dword ptr [rbp+140h+var_1B8+0Ch], eax
0x1800378d2  mov     [rbp+140h+var_1A8], r13
0x1800378d6  mov     r13d, 1
0x1800378dc  mov     [rbp+140h+var_188.cExtension], r13d
0x1800378e0  lea     rax, [rbp+140h+var_1C0]
0x1800378e4  mov     [rbp+140h+var_188.rgExtension], rax
0x1800378e8  lea     rdx, [rsp+240h+lpMem+8]; pcbEncoded
0x1800378ed  lea     rcx, [rbp+140h+var_188]; pvStructInfo
0x1800378f1  call    ?EncodeExtensions@@YAJPEAU_CERT_EXTENSIONS@@PEAU_CRYPTOAPI_BLOB@@@Z; EncodeExtensions(_CERT_EXTENSIONS *,_CRYPTOAPI_BLOB *)
0x1800378f6  mov     [rsp+240h+var_1F0], eax
0x1800378fa  test    eax, eax
0x1800378fc  js      loc_180037A1C
0x180037902  mov     dword ptr [rbp+140h+var_170], r13d
0x180037906  lea     rax, a12840113549191; "1.2.840.113549.1.9.14"
0x18003790d  mov     [rbp+140h+var_178], rax
0x180037911  lea     rax, [rsp+240h+lpMem+8]
0x180037916  mov     qword ptr [rbp+140h+var_170+8], rax
0x18003791a  mov     [rbp+140h+var_E8], r13d
0x18003791e  lea     rax, [rbp+140h+var_178]
0x180037922  mov     [rbp+140h+var_E0], rax
0x180037926  mov     rax, [rbp+140h+var_198]
0x18003792a  mov     [rbp+140h+var_160.pszObjId], rax
0x18003792e  movdqu  xmmword ptr [rbp+140h+var_160.Parameters.cbData], xmm6
0x180037933  mov     [rsp+40h], rsi; pcbEncoded
0x180037938  mov     [rsp+240h+pbEncoded], rbx; pbEncoded
0x18003793d  mov     [rsp+240h+pvHashAuxInfo], rbx; pvHashAuxInfo
0x180037942  lea     rax, [rbp+140h+var_160]
0x180037946  mov     [rsp+240h+pSignatureAlgorithm], rax; pSignatureAlgorithm
0x18003794b  lea     rax, [rbp+140h+pvStructInfo]
0x18003794f  mov     [rsp+240h+pcbInfo], rax; pvStructInfo
0x180037954  lea     r9d, [r13+3]; lpszStructType
0x180037958  mov     r13d, 10001h
0x18003795e  mov     r8d, r13d; dwCertEncodingType
0x180037961  xor     edx, edx; dwKeySpec
0x180037963  mov     rcx, r15; hCryptProvOrNCryptKey
0x180037966  call    cs:__imp_CryptSignAndEncodeCertificate
0x18003796d  nop     dword ptr [rax+rax+00h]
0x180037972  test    eax, eax
0x180037974  jz      loc_180037A00
0x18003797a  mov     ebx, [rsi]
0x18003797c  call    cs:__imp_GetProcessHeap
0x180037983  nop     dword ptr [rax+rax+00h]
0x180037988  mov     rcx, rax; hHeap
0x18003798b  mov     r8d, ebx; dwBytes
0x18003798e  mov     edx, 8; dwFlags
0x180037993  call    cs:__imp_HeapAlloc
0x18003799a  nop     dword ptr [rax+rax+00h]
0x18003799f  mov     [r14], rax
0x1800379a2  test    rax, rax
0x1800379a5  jz      loc_18003783A
0x1800379ab  mov     [rsp+40h], rsi; pcbEncoded
0x1800379b0  mov     [rsp+240h+pbEncoded], rax; pbEncoded
0x1800379b5  mov     [rsp+240h+pvHashAuxInfo], 0; pvHashAuxInfo
0x1800379be  lea     rax, [rbp+140h+var_160]
0x1800379c2  mov     [rsp+240h+pSignatureAlgorithm], rax; pSignatureAlgorithm
0x1800379c7  lea     rax, [rbp+140h+pvStructInfo]
0x1800379cb  mov     [rsp+240h+pcbInfo], rax; pvStructInfo
0x1800379d0  mov     r9d, 4; lpszStructType
0x1800379d6  mov     r8d, r13d; dwCertEncodingType
0x1800379d9  xor     edx, edx; dwKeySpec
0x1800379db  mov     rcx, r15; hCryptProvOrNCryptKey
0x1800379de  call    cs:__imp_CryptSignAndEncodeCertificate
0x1800379e5  nop     dword ptr [rax+rax+00h]
0x1800379ea  test    eax, eax
0x1800379ec  jz      short loc_180037A00
0x1800379ee  mov     [r12], rdi
0x1800379f2  xor     edi, edi
0x1800379f4  mov     eax, [rsp+240h+var_1EC]
0x1800379f8  mov     rcx, [rbp+140h+var_190]
0x1800379fc  mov     [rcx], eax
0x1800379fe  jmp     short loc_180037A1C
0x180037a00  call    cs:__imp_GetLastError
0x180037a07  nop     dword ptr [rax+rax+00h]
0x180037a0c  test    eax, eax
0x180037a0e  jle     short loc_180037A18
0x180037a10  movzx   eax, ax
0x180037a13  or      eax, 80070000h
0x180037a18  mov     [rsp+240h+var_1F0], eax
0x180037a1c  mov     rbx, qword ptr [rsp+240h+lpMem+10h]
0x180037a21  xor     r15d, r15d
0x180037a24  test    rbx, rbx
0x180037a27  jz      short loc_180037A49
0x180037a29  call    cs:__imp_GetProcessHeap
0x180037a30  nop     dword ptr [rax+rax+00h]
0x180037a35  mov     rcx, rax; hHeap
0x180037a38  mov     r8, rbx; lpMem
0x180037a3b  xor     edx, edx; dwFlags
0x180037a3d  call    cs:__imp_HeapFree
0x180037a44  nop     dword ptr [rax+rax+00h]
0x180037a49  mov     qword ptr [rsp+240h+lpMem+10h], r15
0x180037a4e  mov     rbx, qword ptr [rsp+240h+lpMem]
0x180037a53  test    rbx, rbx
0x180037a56  jz      short loc_180037A78
0x180037a58  call    cs:__imp_GetProcessHeap
0x180037a5f  nop     dword ptr [rax+rax+00h]
0x180037a64  mov     rcx, rax; hHeap
0x180037a67  mov     r8, rbx; lpMem
0x180037a6a  xor     edx, edx; dwFlags
0x180037a6c  call    cs:__imp_HeapFree
0x180037a73  nop     dword ptr [rax+rax+00h]
0x180037a78  test    rdi, rdi
0x180037a7b  jz      short loc_180037A9D
0x180037a7d  call    cs:__imp_GetProcessHeap
0x180037a84  nop     dword ptr [rax+rax+00h]
0x180037a89  mov     rcx, rax; hHeap
0x180037a8c  mov     r8, rdi; lpMem
0x180037a8f  xor     edx, edx; dwFlags
0x180037a91  call    cs:__imp_HeapFree
0x180037a98  nop     dword ptr [rax+rax+00h]
0x180037a9d  cmp     [rsp+240h+var_1F0], r15d
0x180037aa2  jge     short loc_180037AD4
0x180037aa4  test    r14, r14
0x180037aa7  jz      short loc_180037AD4
0x180037aa9  mov     [rsi], r15d
0x180037aac  mov     rbx, [r14]
0x180037aaf  test    rbx, rbx
0x180037ab2  jz      short loc_180037AD4
0x180037ab4  call    cs:__imp_GetProcessHeap
0x180037abb  nop     dword ptr [rax+rax+00h]
0x180037ac0  mov     rcx, rax; hHeap
0x180037ac3  mov     r8, rbx; lpMem
0x180037ac6  xor     edx, edx; dwFlags
0x180037ac8  call    cs:__imp_HeapFree
0x180037acf  nop     dword ptr [rax+rax+00h]
0x180037ad4  mov     ebx, [rsp+240h+var_1F0]
0x180037ad8  lea     rcx, [rbp+140h+var_148]; this
0x180037adc  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180037ae1  mov     eax, ebx
0x180037ae3  mov     rcx, [rbp+140h+var_60]
0x180037aea  xor     rcx, rsp; StackCookie
0x180037aed  call    __security_check_cookie
0x180037af2  movaps  xmm6, [rsp+240h+var_58+8]
0x180037afa  add     rsp, 208h
0x180037b01  pop     r15
0x180037b03  pop     r14
0x180037b05  pop     r13
0x180037b07  pop     r12
0x180037b09  pop     rdi
0x180037b0a  pop     rsi
0x180037b0b  pop     rbx
0x180037b0c  pop     rbp
0x180037b0d  retn
```
