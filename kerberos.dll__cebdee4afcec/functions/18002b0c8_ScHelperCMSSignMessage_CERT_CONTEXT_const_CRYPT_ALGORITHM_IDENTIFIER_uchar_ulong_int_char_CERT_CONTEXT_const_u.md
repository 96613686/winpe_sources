# ScHelperCMSSignMessage(_CERT_CONTEXT const *,_CRYPT_ALGORITHM_IDENTIFIER *,uchar *,ulong,int,char *,_CERT_CONTEXT const * *,ulong,uchar * *,ulong *)

- ea: `0x18002b0c8`
- end: `0x18002b435`
- name: `?ScHelperCMSSignMessage@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAEKHPEADPEAPEBU1@KPEAPEAEPEAK@Z`
- size: `877`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, struct _CRYPT_ALGORITHM_IDENTIFIER *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, int, LPSTR, const struct _CERT_CONTEXT **, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18002af90`

## callees

- `0x180007e80`
- `0x18002b0c8`
- `0x18002b43c`
- `0x180070680`
- `0x18007108c`
- `0x1800f1ea0`
- `0x1800f1f00`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b212`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b1ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b3e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b3e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b202`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b202`
- `CRYPT32!CryptMsgClose` at `0x18002b1f4`
- `CRYPT32!CryptMsgClose` at `0x18002b1f4`
- `CRYPT32!CryptMsgUpdate` at `0x18002b3b1`
- `CRYPT32!CryptMsgUpdate` at `0x18002b3b1`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18002b391`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18002b391`
- `CRYPT32!CryptMsgGetParam` at `0x18002b3d3`
- `CRYPT32!CryptMsgGetParam` at `0x18002b40c`
- `CRYPT32!CryptMsgGetParam` at `0x18002b3d3`
- `CRYPT32!CryptMsgGetParam` at `0x18002b40c`

## pseudocode

```c
__int64 __fastcall ScHelperCMSSignMessage(
        PCCERT_CONTEXT pCert,
        struct _CRYPT_ALGORITHM_IDENTIFIER *a2,
        unsigned __int8 *a3,
        DWORD a4,
        int a5,
        LPSTR pszInnerContentObjID,
        const struct _CERT_CONTEXT **a7,
        unsigned int a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  void *v12; // r15
  const char *pszObjId; // rcx
  unsigned __int8 *v14; // r14
  __int128 v15; // xmm0
  BYTE *v16; // xmm1_8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // esi
  DWORD LastError; // ebx
  DWORD *p_pcbData; // rbx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  DWORD *v30; // rax
  unsigned int v31; // r9d
  __int64 v32; // r8
  __int64 v33; // rdx
  const struct _CERT_CONTEXT *v34; // rax
  HCRYPTMSG v35; // rax
  DWORD v36; // eax
  __int64 v37; // [rsp+0h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD dwErrCode; // [rsp+34h] [rbp+4h] BYREF
  DWORD cbData; // [rsp+38h] [rbp+8h] BYREF
  __int128 v41; // [rsp+40h] [rbp+10h] BYREF
  __int128 pvMsgEncodeInfo; // [rsp+50h] [rbp+20h] BYREF
  __int128 v43; // [rsp+60h] [rbp+30h]
  __int128 v44; // [rsp+70h] [rbp+40h]
  BYTE *pbData; // [rsp+80h] [rbp+50h]
  int v46; // [rsp+90h] [rbp+60h] BYREF
  PCERT_INFO pCertInfo; // [rsp+98h] [rbp+68h]
  __int128 v48; // [rsp+B0h] [rbp+80h]
  BYTE *v49; // [rsp+C0h] [rbp+90h]

  pbData = a3;
  cbData = a4;
  v12 = 0;
  pvMsgEncodeInfo = 0;
  v43 = 0;
  v44 = 0;
  memset_0(&v46, 0, 0x60u);
  pszObjId = a2->pszObjId;
  dwErrCode = 0;
  pcbData = 0;
  v41 = 0;
  v14 = 0;
  strncmp_0(pszObjId, "1.3.14.3.2.26", 0xEu);
  v15 = *(_OWORD *)&a2->pszObjId;
  v16 = a2->Parameters.pbData;
  v46 = 96;
  *a9 = 0;
  v48 = v15;
  v49 = v16;
  *a10 = 0;
  pCertInfo = pCert->pCertInfo;
  if ( (int)ScHelperCryptAcquireCertificatePrivateKey(pCert, (__int64)&dwErrCode) >= 0 )
  {
    *(_QWORD *)&pvMsgEncodeInfo = 0x100000030LL;
    v20 = 1;
    *((_QWORD *)&pvMsgEncodeInfo + 1) = &v46;
    if ( a8 )
    {
      p_pcbData = 0;
      v24 = 16LL * a8;
      if ( !v24 )
        goto LABEL_43;
      if ( v24 > g_ulMaxStackAllocSize )
        goto LABEL_43;
      v25 = v24 + g_ulAdditionalProbeSize + 8;
      if ( v25 < v24 || !(unsigned int)VerifyStackAvailable(v25, v17, v18, v19) )
        goto LABEL_43;
      v26 = v24 + 23;
      if ( v24 + 23 <= v24 + 8 )
        v26 = 0xFFFFFFFFFFFFFF0LL;
      v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
      v28 = alloca(v27);
      v29 = alloca(v27);
      p_pcbData = &pcbData;
      if ( &v37 == (__int64 *)-48LL || (pcbData = 1801679955, (p_pcbData = &cbData) == 0) )
      {
LABEL_43:
        if ( v24 + 8 >= v24 )
        {
          v30 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbData = v30;
          if ( v30 )
          {
            *v30 = 1885431112;
            p_pcbData = v30 + 2;
          }
        }
      }
      *((_QWORD *)&v43 + 1) = p_pcbData;
      if ( !p_pcbData )
        goto LABEL_3;
      v31 = 0;
      v32 = 0;
      while ( 1 )
      {
        v33 = 2 * v32;
        ++v31;
        *(_QWORD *)&p_pcbData[2 * v33 + 2] = a7[v32]->pbCertEncoded;
        v34 = a7[v32++];
        *(_DWORD *)(*((_QWORD *)&v43 + 1) + 8 * v33) = v34->cbCertEncoded;
        if ( v31 >= a8 )
          break;
        p_pcbData = (DWORD *)*((_QWORD *)&v43 + 1);
      }
      LODWORD(v43) = a8;
    }
    else
    {
      LODWORD(v41) = pCert->cbCertEncoded;
      *((_QWORD *)&v41 + 1) = pCert->pbCertEncoded;
      *((_QWORD *)&v43 + 1) = &v41;
      LODWORD(v43) = 1;
    }
    v35 = CryptMsgOpenToEncode(0x10001u, 0x40u, 2u, &pvMsgEncodeInfo, pszInnerContentObjID, 0);
    v12 = v35;
    if ( v35 )
    {
      if ( CryptMsgUpdate(v35, pbData, cbData, 1) )
      {
        if ( CryptMsgGetParam(v12, 2u, 0, 0, &pcbData) )
        {
          v14 = (unsigned __int8 *)LocalAlloc(0x40u, pcbData);
          if ( v14 )
          {
            if ( CryptMsgGetParam(v12, 2u, 0, v14, &pcbData) )
            {
              v36 = pcbData;
              *a9 = v14;
              v14 = 0;
              *a10 = v36;
              LastError = dwErrCode;
              goto LABEL_4;
            }
          }
        }
      }
    }
  }
  else
  {
    SetLastError(dwErrCode);
  }
LABEL_3:
  v20 = 0;
  LastError = GetLastError();
LABEL_4:
  if ( *((_QWORD *)&v43 + 1)
    && *((__int128 **)&v43 + 1) != &v41
    && *(_DWORD *)(*((_QWORD *)&v43 + 1) - 8LL) == 1885431112 )
  {
    ((void (*)(void))g_pfnFree)();
  }
  if ( v12 )
    CryptMsgClose(v12);
  if ( v14 )
    LocalFree(v14);
  if ( !v20 && LastError )
    SetLastError(LastError);
  return v20;
}

```

## disassembly

```asm
0x18002b0c8  push    rbp
0x18002b0ca  push    rbx
0x18002b0cb  push    rsi
0x18002b0cc  push    rdi
0x18002b0cd  push    r12
0x18002b0cf  push    r13
0x18002b0d1  push    r14
0x18002b0d3  push    r15
0x18002b0d5  sub     rsp, 108h
0x18002b0dc  lea     rbp, [rsp+30h]
0x18002b0e1  mov     rax, cs:__security_cookie
0x18002b0e8  xor     rax, rbp
0x18002b0eb  mov     [rbp+110h+var_50], rax
0x18002b0f2  xorps   xmm0, xmm0
0x18002b0f5  mov     [rbp+110h+pbData], r8
0x18002b0f9  mov     rbx, rdx
0x18002b0fc  mov     [rbp+110h+cbData], r9d
0x18002b100  mov     rdi, rcx
0x18002b103  xor     r15d, r15d
0x18002b106  xor     edx, edx; Val
0x18002b108  lea     rcx, [rbp+110h+var_B0]; void *
0x18002b10c  movups  [rbp+110h+pvMsgEncodeInfo], xmm0
0x18002b110  lea     esi, [r15+60h]
0x18002b114  mov     r8d, esi; Size
0x18002b117  movups  [rbp+110h+var_E0], xmm0
0x18002b11b  movups  [rbp+110h+var_D0], xmm0
0x18002b11f  call    memset_0
0x18002b124  mov     rcx, [rbx]; Str1
0x18002b127  lea     r8d, [r15+0Eh]; MaxCount
0x18002b12b  xorps   xmm0, xmm0
0x18002b12e  mov     [rbp+110h+dwErrCode], r15d
0x18002b132  lea     rdx, a13143226; "1.3.14.3.2.26"
0x18002b139  mov     [rbp+110h+pcbData], r15d
0x18002b13d  movups  [rbp+110h+var_100], xmm0
0x18002b141  xor     r14d, r14d
0x18002b144  call    strncmp_0
0x18002b149  movups  xmm0, xmmword ptr [rbx]
0x18002b14c  lea     r9, [rbp+110h+var_98]
0x18002b150  mov     r13, [rbp+110h+arg_40]
0x18002b157  movsd   xmm1, qword ptr [rbx+10h]
0x18002b15c  lea     r8, [rbp+110h+var_A0]
0x18002b160  mov     ecx, eax
0x18002b162  mov     [rbp+110h+var_B0], esi
0x18002b165  mov     rax, [rbp+110h+arg_48]
0x18002b16c  xor     edx, edx
0x18002b16e  test    ecx, ecx
0x18002b170  mov     [r13+0], r14
0x18002b174  mov     rcx, rdi; pCert
0x18002b177  movaps  [rbp+110h+var_90], xmm0
0x18002b17e  setnz   dl
0x18002b181  movsd   [rbp+110h+var_80], xmm1
0x18002b189  mov     [rax], r14d
0x18002b18c  mov     rax, [rdi+18h]
0x18002b190  mov     [rbp+110h+var_A8], rax
0x18002b194  lea     rax, [rbp+110h+dwErrCode]
0x18002b198  mov     [rsp+140h+pszInnerContentObjID], rax; __int64
0x18002b19d  call    ScHelperCryptAcquireCertificatePrivateKey
0x18002b1a2  test    eax, eax
0x18002b1a4  jns     loc_18002B23D
0x18002b1aa  mov     ecx, [rbp+110h+dwErrCode]; dwErrCode
0x18002b1ad  call    cs:__imp_SetLastError
0x18002b1b3  xor     esi, esi
0x18002b1b5  call    cs:__imp_GetLastError
0x18002b1bb  mov     ebx, eax
0x18002b1bd  mov     rcx, qword ptr [rbp+110h+var_E0+8]
0x18002b1c1  test    rcx, rcx
0x18002b1c4  jz      short loc_18002B1EC
0x18002b1c6  lea     rax, [rbp+110h+var_100]
0x18002b1ca  cmp     rcx, rax
0x18002b1cd  jz      short loc_18002B1EC
0x18002b1cf  test    rcx, rcx
0x18002b1d2  jz      short loc_18002B1EC
0x18002b1d4  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18002b1d8  cmp     dword ptr [rcx], 70616548h
0x18002b1de  jnz     short loc_18002B1EC
0x18002b1e0  mov     rax, cs:g_pfnFree
0x18002b1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1ec  test    r15, r15
0x18002b1ef  jz      short loc_18002B1FA
0x18002b1f1  mov     rcx, r15; hCryptMsg
0x18002b1f4  call    cs:__imp_CryptMsgClose
0x18002b1fa  test    r14, r14
0x18002b1fd  jz      short loc_18002B208
0x18002b1ff  mov     rcx, r14; hMem
0x18002b202  call    cs:__imp_LocalFree
0x18002b208  test    esi, esi
0x18002b20a  jnz     short loc_18002B218
0x18002b20c  test    ebx, ebx
0x18002b20e  jz      short loc_18002B218
0x18002b210  mov     ecx, ebx; dwErrCode
0x18002b212  call    cs:__imp_SetLastError
0x18002b218  mov     eax, esi
0x18002b21a  mov     rcx, [rbp+110h+var_50]
0x18002b221  xor     rcx, rbp; StackCookie
0x18002b224  call    __security_check_cookie
0x18002b229  lea     rsp, [rbp+0D8h]
0x18002b230  pop     r15
0x18002b232  pop     r14
0x18002b234  pop     r13
0x18002b236  pop     r12
0x18002b238  pop     rdi
0x18002b239  pop     rsi
0x18002b23a  pop     rbx
0x18002b23b  pop     rbp
0x18002b23c  retn
0x18002b23d  mov     r12d, [rbp+110h+arg_38]
0x18002b244  lea     rax, [rbp+110h+var_B0]
0x18002b248  mov     dword ptr [rbp+110h+pvMsgEncodeInfo], 30h ; '0'
0x18002b24f  mov     esi, 1
0x18002b254  mov     dword ptr [rbp+110h+pvMsgEncodeInfo+4], esi
0x18002b257  mov     qword ptr [rbp+110h+pvMsgEncodeInfo+8], rax
0x18002b25b  test    r12d, r12d
0x18002b25e  jz      loc_18002B351
0x18002b264  mov     edi, r12d
0x18002b267  xor     ebx, ebx
0x18002b269  shl     rdi, 4
0x18002b26d  test    rdi, rdi
0x18002b270  jz      short loc_18002B2D3
0x18002b272  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002b279  ja      short loc_18002B2D3
0x18002b27b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b282  add     rcx, 8
0x18002b286  add     rcx, rdi
0x18002b289  cmp     rcx, rdi
0x18002b28c  jb      short loc_18002B2D3
0x18002b28e  call    VerifyStackAvailable
0x18002b293  test    eax, eax
0x18002b295  jz      short loc_18002B2D3
0x18002b297  lea     rax, [rdi+8]
0x18002b29b  lea     rcx, [rax+0Fh]
0x18002b29f  cmp     rcx, rax
0x18002b2a2  ja      short loc_18002B2AE
0x18002b2a4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002b2ae  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b2b2  mov     rax, rcx
0x18002b2b5  call    _alloca_probe
0x18002b2ba  sub     rsp, rcx
0x18002b2bd  lea     rbx, [rsp+140h+pcbData]
0x18002b2c2  test    rbx, rbx
0x18002b2c5  jz      short loc_18002B2D3
0x18002b2c7  mov     dword ptr [rbx], 6B637453h
0x18002b2cd  add     rbx, 8
0x18002b2d1  jnz     short loc_18002B2FA
0x18002b2d3  lea     rcx, [rdi+8]
0x18002b2d7  cmp     rcx, rdi
0x18002b2da  jb      short loc_18002B2FA
0x18002b2dc  mov     rax, cs:g_pfnAllocate
0x18002b2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2e8  mov     rbx, rax
0x18002b2eb  test    rax, rax
0x18002b2ee  jz      short loc_18002B2FA
0x18002b2f0  mov     dword ptr [rax], 70616548h
0x18002b2f6  add     rbx, 8
0x18002b2fa  mov     qword ptr [rbp+110h+var_E0+8], rbx
0x18002b2fe  test    rbx, rbx
0x18002b301  jz      loc_18002B1B3
0x18002b307  mov     r10, [rbp+110h+arg_30]
0x18002b30e  xor     r9d, r9d
0x18002b311  test    r12d, r12d
0x18002b314  jz      short loc_18002B34B
0x18002b316  xor     r8d, r8d
0x18002b319  mov     rax, [r10+r8*8]
0x18002b31d  mov     rdx, r8
0x18002b320  add     rdx, rdx
0x18002b323  add     r9d, esi
0x18002b326  mov     rcx, [rax+8]
0x18002b32a  mov     [rbx+rdx*8+8], rcx
0x18002b32f  mov     rax, [r10+r8*8]
0x18002b333  add     r8, rsi
0x18002b336  mov     ecx, [rax+10h]
0x18002b339  mov     rax, qword ptr [rbp+110h+var_E0+8]
0x18002b33d  mov     [rax+rdx*8], ecx
0x18002b340  cmp     r9d, r12d
0x18002b343  jnb     short loc_18002B34B
0x18002b345  mov     rbx, qword ptr [rbp+110h+var_E0+8]
0x18002b349  jmp     short loc_18002B319
0x18002b34b  mov     dword ptr [rbp+110h+var_E0], r12d
0x18002b34f  jmp     short loc_18002B36A
0x18002b351  mov     eax, [rdi+10h]
0x18002b354  mov     dword ptr [rbp+110h+var_100], eax
0x18002b357  mov     rax, [rdi+8]
0x18002b35b  mov     qword ptr [rbp+110h+var_100+8], rax
0x18002b35f  lea     rax, [rbp+110h+var_100]
0x18002b363  mov     qword ptr [rbp+110h+var_E0+8], rax
0x18002b367  mov     dword ptr [rbp+110h+var_E0], esi
0x18002b36a  mov     rax, [rbp+110h+arg_28]
0x18002b371  lea     r9, [rbp+110h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x18002b375  mov     ebx, 2
0x18002b37a  mov     [rsp+140h+pStreamInfo], r14; pStreamInfo
0x18002b37f  mov     r8d, ebx; dwMsgType
0x18002b382  mov     [rsp+140h+pszInnerContentObjID], rax; pszInnerContentObjID
0x18002b387  mov     ecx, 10001h; dwMsgEncodingType
0x18002b38c  lea     edi, [rbx+3Eh]
0x18002b38f  mov     edx, edi; dwFlags
0x18002b391  call    cs:__imp_CryptMsgOpenToEncode
0x18002b397  mov     r15, rax
0x18002b39a  test    rax, rax
0x18002b39d  jz      loc_18002B1B3
0x18002b3a3  mov     r8d, [rbp+110h+cbData]; cbData
0x18002b3a7  mov     r9d, esi; fFinal
0x18002b3aa  mov     rdx, [rbp+110h+pbData]; pbData
0x18002b3ae  mov     rcx, rax; hCryptMsg
0x18002b3b1  call    cs:__imp_CryptMsgUpdate
0x18002b3b7  test    eax, eax
0x18002b3b9  jz      loc_18002B1B3
0x18002b3bf  lea     rax, [rbp+110h+pcbData]
0x18002b3c3  xor     r9d, r9d; pvData
0x18002b3c6  xor     r8d, r8d; dwIndex
0x18002b3c9  mov     [rsp+140h+pszInnerContentObjID], rax; pcbData
0x18002b3ce  mov     edx, ebx; dwParamType
0x18002b3d0  mov     rcx, r15; hCryptMsg
0x18002b3d3  call    cs:__imp_CryptMsgGetParam
0x18002b3d9  test    eax, eax
0x18002b3db  jz      loc_18002B1B3
0x18002b3e1  mov     edx, [rbp+110h+pcbData]; uBytes
0x18002b3e4  mov     ecx, edi; uFlags
0x18002b3e6  call    cs:__imp_LocalAlloc
0x18002b3ec  mov     r14, rax
0x18002b3ef  test    rax, rax
0x18002b3f2  jz      loc_18002B1B3
0x18002b3f8  lea     rax, [rbp+110h+pcbData]
0x18002b3fc  mov     r9, r14; pvData
0x18002b3ff  xor     r8d, r8d; dwIndex
0x18002b402  mov     [rsp+140h+pszInnerContentObjID], rax; pcbData
0x18002b407  mov     edx, ebx; dwParamType
0x18002b409  mov     rcx, r15; hCryptMsg
0x18002b40c  call    cs:__imp_CryptMsgGetParam
0x18002b412  test    eax, eax
0x18002b414  jz      loc_18002B1B3
0x18002b41a  mov     rcx, [rbp+110h+arg_48]
0x18002b421  mov     eax, [rbp+110h+pcbData]
0x18002b424  mov     [r13+0], r14
0x18002b428  xor     r14d, r14d
0x18002b42b  mov     [rcx], eax
0x18002b42d  mov     ebx, [rbp+110h+dwErrCode]
0x18002b430  jmp     loc_18002B1BD
```
