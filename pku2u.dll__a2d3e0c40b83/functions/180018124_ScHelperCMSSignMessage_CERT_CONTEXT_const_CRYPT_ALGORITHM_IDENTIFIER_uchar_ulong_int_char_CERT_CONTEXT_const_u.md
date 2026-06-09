# ScHelperCMSSignMessage(_CERT_CONTEXT const *,_CRYPT_ALGORITHM_IDENTIFIER *,uchar *,ulong,int,char *,_CERT_CONTEXT const * *,ulong,uchar * *,ulong *)

- ea: `0x180018124`
- end: `0x180018480`
- name: `?ScHelperCMSSignMessage@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAEKHPEADPEAPEBU1@KPEAPEAEPEAK@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, struct _CRYPT_ALGORITHM_IDENTIFIER *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, int, LPSTR pszInnerContentObjID, const struct _CERT_CONTEXT **, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180017df0`

## callees

- `0x180018124`
- `0x180018c80`
- `0x1800210f0`
- `0x180021a54`
- `0x180044f20`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800181f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001825d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800181f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001825d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018200`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018432`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001824d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001824d`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800181e2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800181e2`
- `CRYPT32!CryptMsgUpdate` at `0x1800183fa`
- `CRYPT32!CryptMsgUpdate` at `0x1800183fa`
- `CRYPT32!CryptMsgClose` at `0x18001823f`
- `CRYPT32!CryptMsgClose` at `0x18001823f`
- `CRYPT32!CryptMsgGetParam` at `0x18001841f`
- `CRYPT32!CryptMsgGetParam` at `0x180018458`
- `CRYPT32!CryptMsgGetParam` at `0x18001841f`
- `CRYPT32!CryptMsgGetParam` at `0x180018458`
- `CRYPT32!CryptMsgOpenToEncode` at `0x1800183da`
- `CRYPT32!CryptMsgOpenToEncode` at `0x1800183da`

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
  unsigned __int8 *v13; // r14
  __int128 v14; // xmm0
  BYTE *v15; // xmm1_8
  DWORD LastError; // eax
  unsigned int v17; // esi
  DWORD v18; // ebx
  DWORD *p_pcbData; // rbx
  unsigned __int64 v21; // rdi
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  DWORD *v26; // rax
  unsigned int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // rdx
  const struct _CERT_CONTEXT *v30; // rax
  HCRYPTMSG v31; // rax
  DWORD v32; // eax
  __int64 v33; // [rsp+0h] [rbp-30h] BYREF
  BOOL *pfCallerFreeProvOrNCryptKey; // [rsp+28h] [rbp-8h]
  DWORD pcbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp+4h]
  __int128 v37; // [rsp+38h] [rbp+8h] BYREF
  __int128 pvMsgEncodeInfo; // [rsp+48h] [rbp+18h] BYREF
  __int128 v39; // [rsp+58h] [rbp+28h]
  __int128 v40; // [rsp+68h] [rbp+38h]
  BYTE *pbData; // [rsp+78h] [rbp+48h]
  int v42; // [rsp+90h] [rbp+60h] BYREF
  PCERT_INFO pCertInfo; // [rsp+98h] [rbp+68h]
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+A0h] [rbp+70h] BYREF
  DWORD pdwKeySpec; // [rsp+A8h] [rbp+78h] BYREF
  __int128 v46; // [rsp+B0h] [rbp+80h]
  BYTE *v47; // [rsp+C0h] [rbp+90h]

  pbData = a3;
  cbData = a4;
  v12 = 0;
  pvMsgEncodeInfo = 0;
  v39 = 0;
  v40 = 0;
  memset_0(&v42, 0, 0x60u);
  v13 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  v37 = 0;
  pcbData = 0;
  *a9 = 0;
  *a10 = 0;
  v14 = *(_OWORD *)&a2->pszObjId;
  pCertInfo = pCert->pCertInfo;
  v15 = a2->Parameters.pbData;
  v42 = 96;
  v46 = v14;
  v47 = v15;
  if ( CryptAcquireCertificatePrivateKey(
         pCert,
         0x20041u,
         0,
         &phCryptProvOrNCryptKey,
         &pdwKeySpec,
         pfCallerFreeProvOrNCryptKey) )
  {
    *(_QWORD *)&pvMsgEncodeInfo = 0x100000030LL;
    v17 = 1;
    *((_QWORD *)&pvMsgEncodeInfo + 1) = &v42;
    if ( a8 )
    {
      p_pcbData = 0;
      v21 = 16LL * a8;
      if ( !v21
        || v21 > g_ulMaxStackAllocSize
        || v21 + g_ulAdditionalProbeSize + 8 < v21
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_43;
      }
      v22 = v21 + 23;
      if ( v21 + 23 <= v21 + 8 )
        v22 = 0xFFFFFFFFFFFFFF0LL;
      v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
      v24 = alloca(v23);
      v25 = alloca(v23);
      p_pcbData = &pcbData;
      if ( &v33 == (__int64 *)-48LL || (pcbData = 1801679955, (p_pcbData = (DWORD *)&v37) == 0) )
      {
LABEL_43:
        if ( v21 + 8 >= v21 )
        {
          v26 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbData = v26;
          if ( v26 )
          {
            *v26 = 1885431112;
            p_pcbData = v26 + 2;
          }
        }
      }
      *((_QWORD *)&v39 + 1) = p_pcbData;
      if ( !p_pcbData )
        goto LABEL_3;
      v27 = 0;
      v28 = 0;
      while ( 1 )
      {
        v29 = 2 * v28;
        ++v27;
        *(_QWORD *)&p_pcbData[2 * v29 + 2] = a7[v28]->pbCertEncoded;
        v30 = a7[v28++];
        *(_DWORD *)(*((_QWORD *)&v39 + 1) + 8 * v29) = v30->cbCertEncoded;
        if ( v27 >= a8 )
          break;
        p_pcbData = (DWORD *)*((_QWORD *)&v39 + 1);
      }
      LODWORD(v39) = a8;
    }
    else
    {
      LODWORD(v37) = pCert->cbCertEncoded;
      *((_QWORD *)&v37 + 1) = pCert->pbCertEncoded;
      *((_QWORD *)&v39 + 1) = &v37;
      LODWORD(v39) = 1;
    }
    v31 = CryptMsgOpenToEncode(0x10001u, 0x40u, 2u, &pvMsgEncodeInfo, pszInnerContentObjID, 0);
    v12 = v31;
    if ( v31 )
    {
      if ( CryptMsgUpdate(v31, pbData, cbData, 1) )
      {
        if ( CryptMsgGetParam(v12, 3u, 0, 0, &pcbData) )
        {
          v13 = (unsigned __int8 *)LocalAlloc(0x40u, pcbData);
          if ( v13 )
          {
            if ( CryptMsgGetParam(v12, 3u, 0, v13, &pcbData) )
            {
              v18 = 0;
              v32 = pcbData;
              *a9 = v13;
              v13 = 0;
              *a10 = v32;
              goto LABEL_4;
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    SetLastError(LastError);
  }
LABEL_3:
  v17 = 0;
  v18 = GetLastError();
LABEL_4:
  if ( *((_QWORD *)&v39 + 1)
    && *((__int128 **)&v39 + 1) != &v37
    && *(_DWORD *)(*((_QWORD *)&v39 + 1) - 8LL) == 1885431112 )
  {
    ((void (*)(void))g_pfnFree)();
  }
  if ( v12 )
    CryptMsgClose(v12);
  if ( v13 )
    LocalFree(v13);
  if ( !v17 && v18 )
    SetLastError(v18);
  return v17;
}

```

## disassembly

```asm
0x180018124  push    rbp
0x180018126  push    rbx
0x180018127  push    rsi
0x180018128  push    rdi
0x180018129  push    r12
0x18001812b  push    r13
0x18001812d  push    r14
0x18001812f  push    r15
0x180018131  sub     rsp, 108h
0x180018138  lea     rbp, [rsp+30h]
0x18001813d  mov     rax, cs:__security_cookie
0x180018144  xor     rax, rbp
0x180018147  mov     [rbp+110h+var_50], rax
0x18001814e  xorps   xmm0, xmm0
0x180018151  mov     [rbp+110h+pbData], r8
0x180018155  mov     rbx, rdx
0x180018158  mov     [rbp+110h+cbData], r9d
0x18001815c  mov     rdi, rcx
0x18001815f  xor     r15d, r15d
0x180018162  xor     edx, edx; Val
0x180018164  lea     rcx, [rbp+110h+var_B0]; void *
0x180018168  movups  [rbp+110h+pvMsgEncodeInfo], xmm0
0x18001816c  lea     esi, [r15+60h]
0x180018170  mov     r8d, esi; Size
0x180018173  movups  [rbp+110h+var_E8], xmm0
0x180018177  movups  [rbp+110h+var_D8], xmm0
0x18001817b  call    memset_0
0x180018180  mov     rax, [rbp+110h+arg_48]
0x180018187  lea     r9, [rbp+110h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18001818b  mov     r13, [rbp+110h+arg_40]
0x180018192  xor     r14d, r14d
0x180018195  xorps   xmm0, xmm0
0x180018198  mov     [rsp+140h+pfCallerFreeProvOrNCryptKey], r14; pfCallerFreeProvOrNCryptKey
0x18001819d  movups  [rbp+110h+var_108], xmm0
0x1800181a1  xor     r8d, r8d; pvParameters
0x1800181a4  mov     [rbp+110h+pcbData], r15d
0x1800181a8  mov     [r13+0], r14
0x1800181ac  mov     edx, 20041h; dwFlags
0x1800181b1  mov     [rax], r14d
0x1800181b4  mov     rcx, rdi; pCert
0x1800181b7  mov     rax, [rdi+18h]
0x1800181bb  movups  xmm0, xmmword ptr [rbx]
0x1800181be  mov     [rbp+110h+var_A8], rax
0x1800181c2  lea     rax, [rbp+110h+var_98]
0x1800181c6  movsd   xmm1, qword ptr [rbx+10h]
0x1800181cb  mov     [rsp+140h+pdwKeySpec], rax; pdwKeySpec
0x1800181d0  mov     [rbp+110h+var_B0], esi
0x1800181d3  movaps  [rbp+110h+var_90], xmm0
0x1800181da  movsd   [rbp+110h+var_80], xmm1
0x1800181e2  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800181e8  test    eax, eax
0x1800181ea  jnz     loc_180018288
0x1800181f0  call    cs:__imp_GetLastError
0x1800181f6  mov     ecx, eax; dwErrCode
0x1800181f8  call    cs:__imp_SetLastError
0x1800181fe  xor     esi, esi
0x180018200  call    cs:__imp_GetLastError
0x180018206  mov     ebx, eax
0x180018208  mov     rcx, qword ptr [rbp+110h+var_E8+8]
0x18001820c  test    rcx, rcx
0x18001820f  jz      short loc_180018237
0x180018211  lea     rax, [rbp+110h+var_108]
0x180018215  cmp     rcx, rax
0x180018218  jz      short loc_180018237
0x18001821a  test    rcx, rcx
0x18001821d  jz      short loc_180018237
0x18001821f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180018223  cmp     dword ptr [rcx], 70616548h
0x180018229  jnz     short loc_180018237
0x18001822b  mov     rax, cs:g_pfnFree
0x180018232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018237  test    r15, r15
0x18001823a  jz      short loc_180018245
0x18001823c  mov     rcx, r15; hCryptMsg
0x18001823f  call    cs:__imp_CryptMsgClose
0x180018245  test    r14, r14
0x180018248  jz      short loc_180018253
0x18001824a  mov     rcx, r14; hMem
0x18001824d  call    cs:__imp_LocalFree
0x180018253  test    esi, esi
0x180018255  jnz     short loc_180018263
0x180018257  test    ebx, ebx
0x180018259  jz      short loc_180018263
0x18001825b  mov     ecx, ebx; dwErrCode
0x18001825d  call    cs:__imp_SetLastError
0x180018263  mov     eax, esi
0x180018265  mov     rcx, [rbp+110h+var_50]
0x18001826c  xor     rcx, rbp; StackCookie
0x18001826f  call    __security_check_cookie
0x180018274  lea     rsp, [rbp+0D8h]
0x18001827b  pop     r15
0x18001827d  pop     r14
0x18001827f  pop     r13
0x180018281  pop     r12
0x180018283  pop     rdi
0x180018284  pop     rsi
0x180018285  pop     rbx
0x180018286  pop     rbp
0x180018287  retn
0x180018288  mov     r12d, [rbp+110h+arg_38]
0x18001828f  lea     rax, [rbp+110h+var_B0]
0x180018293  mov     dword ptr [rbp+110h+pvMsgEncodeInfo], 30h ; '0'
0x18001829a  mov     esi, 1
0x18001829f  mov     dword ptr [rbp+110h+pvMsgEncodeInfo+4], esi
0x1800182a2  mov     qword ptr [rbp+110h+pvMsgEncodeInfo+8], rax
0x1800182a6  test    r12d, r12d
0x1800182a9  jz      loc_18001839C
0x1800182af  mov     edi, r12d
0x1800182b2  xor     ebx, ebx
0x1800182b4  shl     rdi, 4
0x1800182b8  test    rdi, rdi
0x1800182bb  jz      short loc_18001831E
0x1800182bd  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800182c4  ja      short loc_18001831E
0x1800182c6  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800182cd  add     rcx, 8
0x1800182d1  add     rcx, rdi
0x1800182d4  cmp     rcx, rdi
0x1800182d7  jb      short loc_18001831E
0x1800182d9  call    VerifyStackAvailable
0x1800182de  test    eax, eax
0x1800182e0  jz      short loc_18001831E
0x1800182e2  lea     rax, [rdi+8]
0x1800182e6  lea     rcx, [rax+0Fh]
0x1800182ea  cmp     rcx, rax
0x1800182ed  ja      short loc_1800182F9
0x1800182ef  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800182f9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800182fd  mov     rax, rcx
0x180018300  call    _alloca_probe
0x180018305  sub     rsp, rcx
0x180018308  lea     rbx, [rsp+140h+pcbData]
0x18001830d  test    rbx, rbx
0x180018310  jz      short loc_18001831E
0x180018312  mov     dword ptr [rbx], 6B637453h
0x180018318  add     rbx, 8
0x18001831c  jnz     short loc_180018345
0x18001831e  lea     rcx, [rdi+8]
0x180018322  cmp     rcx, rdi
0x180018325  jb      short loc_180018345
0x180018327  mov     rax, cs:g_pfnAllocate
0x18001832e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018333  mov     rbx, rax
0x180018336  test    rax, rax
0x180018339  jz      short loc_180018345
0x18001833b  mov     dword ptr [rax], 70616548h
0x180018341  add     rbx, 8
0x180018345  mov     qword ptr [rbp+110h+var_E8+8], rbx
0x180018349  test    rbx, rbx
0x18001834c  jz      loc_1800181FE
0x180018352  mov     r10, [rbp+110h+arg_30]
0x180018359  xor     r9d, r9d
0x18001835c  test    r12d, r12d
0x18001835f  jz      short loc_180018396
0x180018361  xor     r8d, r8d
0x180018364  mov     rax, [r10+r8*8]
0x180018368  mov     rdx, r8
0x18001836b  add     rdx, rdx
0x18001836e  add     r9d, esi
0x180018371  mov     rcx, [rax+8]
0x180018375  mov     [rbx+rdx*8+8], rcx
0x18001837a  mov     rax, [r10+r8*8]
0x18001837e  add     r8, rsi
0x180018381  mov     ecx, [rax+10h]
0x180018384  mov     rax, qword ptr [rbp+110h+var_E8+8]
0x180018388  mov     [rax+rdx*8], ecx
0x18001838b  cmp     r9d, r12d
0x18001838e  jnb     short loc_180018396
0x180018390  mov     rbx, qword ptr [rbp+110h+var_E8+8]
0x180018394  jmp     short loc_180018364
0x180018396  mov     dword ptr [rbp+110h+var_E8], r12d
0x18001839a  jmp     short loc_1800183B5
0x18001839c  mov     eax, [rdi+10h]
0x18001839f  mov     dword ptr [rbp+110h+var_108], eax
0x1800183a2  mov     rax, [rdi+8]
0x1800183a6  mov     qword ptr [rbp+110h+var_108+8], rax
0x1800183aa  lea     rax, [rbp+110h+var_108]
0x1800183ae  mov     qword ptr [rbp+110h+var_E8+8], rax
0x1800183b2  mov     dword ptr [rbp+110h+var_E8], esi
0x1800183b5  mov     rax, [rbp+110h+pszInnerContentObjID]
0x1800183bc  lea     r9, [rbp+110h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x1800183c0  mov     ebx, 40h ; '@'
0x1800183c5  mov     [rsp+140h+pfCallerFreeProvOrNCryptKey], r14; pStreamInfo
0x1800183ca  mov     edx, ebx; dwFlags
0x1800183cc  mov     [rsp+140h+pdwKeySpec], rax; pszInnerContentObjID
0x1800183d1  mov     ecx, 10001h; dwMsgEncodingType
0x1800183d6  lea     r8d, [rbx-3Eh]; dwMsgType
0x1800183da  call    cs:__imp_CryptMsgOpenToEncode
0x1800183e0  mov     r15, rax
0x1800183e3  test    rax, rax
0x1800183e6  jz      loc_1800181FE
0x1800183ec  mov     r8d, [rbp+110h+cbData]; cbData
0x1800183f0  mov     r9d, esi; fFinal
0x1800183f3  mov     rdx, [rbp+110h+pbData]; pbData
0x1800183f7  mov     rcx, rax; hCryptMsg
0x1800183fa  call    cs:__imp_CryptMsgUpdate
0x180018400  test    eax, eax
0x180018402  jz      loc_1800181FE
0x180018408  lea     rax, [rbp+110h+pcbData]
0x18001840c  xor     r9d, r9d; pvData
0x18001840f  lea     edi, [rbx-3Dh]
0x180018412  mov     [rsp+140h+pdwKeySpec], rax; pcbData
0x180018417  mov     edx, edi; dwParamType
0x180018419  xor     r8d, r8d; dwIndex
0x18001841c  mov     rcx, r15; hCryptMsg
0x18001841f  call    cs:__imp_CryptMsgGetParam
0x180018425  test    eax, eax
0x180018427  jz      loc_1800181FE
0x18001842d  mov     edx, [rbp+110h+pcbData]; uBytes
0x180018430  mov     ecx, ebx; uFlags
0x180018432  call    cs:__imp_LocalAlloc
0x180018438  mov     r14, rax
0x18001843b  test    rax, rax
0x18001843e  jz      loc_1800181FE
0x180018444  lea     rax, [rbp+110h+pcbData]
0x180018448  mov     r9, r14; pvData
0x18001844b  xor     r8d, r8d; dwIndex
0x18001844e  mov     [rsp+140h+pdwKeySpec], rax; pcbData
0x180018453  mov     edx, edi; dwParamType
0x180018455  mov     rcx, r15; hCryptMsg
0x180018458  call    cs:__imp_CryptMsgGetParam
0x18001845e  test    eax, eax
0x180018460  jz      loc_1800181FE
0x180018466  mov     rcx, [rbp+110h+arg_48]
0x18001846d  xor     ebx, ebx
0x18001846f  mov     eax, [rbp+110h+pcbData]
0x180018472  mov     [r13+0], r14
0x180018476  xor     r14d, r14d
0x180018479  mov     [rcx], eax
0x18001847b  jmp     loc_180018208
```
