# ObjectContextGetNextUpdateUrl(char const *,void *,_CERT_CONTEXT const *,ushort *,_CRYPT_URL_ARRAY * *,ulong *,ulong *)

- ea: `0x18001254c`
- end: `0x1800127c0`
- name: `?ObjectContextGetNextUpdateUrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@PEAGPEAPEAU_CRYPT_URL_ARRAY@@PEAK5@Z`
- size: `628`
- prototype: `__int64 __fastcall(const char *, void *, const struct _CERT_CONTEXT *, unsigned __int16 *, struct _CRYPT_URL_ARRAY **, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007cc0`
- `0x180008f80`
- `0x18001e1b8`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x18001254c`
- `0x180016500`
- `0x180017d7c`
- `0x180026546`

## import_xrefs

- `msvcrt!printf` at `0x1800126bf`
- `msvcrt!printf` at `0x1800126bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800127b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b0`
- `CRYPT32!CryptMsgGetParam` at `0x1800125d4`
- `CRYPT32!CryptMsgGetParam` at `0x180012609`
- `CRYPT32!CryptMsgGetParam` at `0x18001263d`
- `CRYPT32!CryptMsgGetParam` at `0x1800125d4`
- `CRYPT32!CryptMsgGetParam` at `0x180012609`
- `CRYPT32!CryptMsgGetParam` at `0x18001263d`

## pseudocode

```c
__int64 __fastcall ObjectContextGetNextUpdateUrl(
        const char *a1,
        void *a2,
        const struct _CERT_CONTEXT *a3,
        unsigned __int16 *a4,
        struct _CRYPT_URL_ARRAY **a5,
        unsigned int *a6,
        unsigned int *a7)
{
  DWORD v9; // ecx
  void *v11; // rcx
  BOOL v12; // esi
  DWORD i; // edi
  const void **v14; // rbx
  PCERT_INFO pCertInfo; // r14
  unsigned int v16; // eax
  unsigned int v17; // r12d
  DWORD LastError; // eax
  unsigned int ObjectUrl; // ebx
  struct _CRYPT_URL_ARRAY *v20; // rdi
  __int64 v21; // r8
  unsigned int *v22; // rcx
  DWORD v23; // eax
  DWORD pvData; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-1Ch] BYREF
  __int128 pvPara; // [rsp+48h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pcbUrlArray; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 *v29; // [rsp+B8h] [rbp+58h]

  v29 = a4;
  pcbUrlArray = 0;
  v25 = 0;
  pvData = 0;
  pvPara = 0;
  if ( a1 != (const char *)3 )
  {
    v9 = -2147024809;
LABEL_3:
    SetLastError(v9);
    return 0;
  }
  v11 = (void *)*((_QWORD *)a2 + 5);
  pcbData = 4;
  if ( !CryptMsgGetParam(v11, 5u, 0, &pvData, &pcbData) )
    return 0;
  v12 = 0;
  for ( i = 0; i < pvData; ++i )
  {
    if ( v12 )
      goto LABEL_22;
    if ( !CryptMsgGetParam(*((HCRYPTMSG *)a2 + 5), 7u, i, 0, &pcbData) )
    {
      LastError = GetLastError();
      printf("GetLastError() = %lx\n", LastError);
      return 0;
    }
    v14 = (const void **)operator new(pcbData);
    if ( !v14 )
    {
      v9 = -2147024882;
      goto LABEL_3;
    }
    if ( !CryptMsgGetParam(*((HCRYPTMSG *)a2 + 5), 7u, i, v14, &pcbData) )
    {
      operator delete(v14);
      return 0;
    }
    pCertInfo = a3->pCertInfo;
    v16 = *((_DWORD *)v14 + 12);
    if ( pCertInfo->Issuer.cbData == v16 )
    {
      v17 = *((_DWORD *)v14 + 2);
      if ( pCertInfo->SerialNumber.cbData == v17 && !memcmp_0(pCertInfo->Issuer.pbData, v14[7], v16) )
        v12 = memcmp_0(pCertInfo->SerialNumber.pbData, v14[2], v17) == 0;
    }
    operator delete(v14);
  }
  if ( !v12 )
  {
    v9 = -2146885628;
    goto LABEL_3;
  }
LABEL_22:
  *((_QWORD *)&pvPara + 1) = i - 1;
  *(_QWORD *)&pvPara = a2;
  ObjectUrl = CryptGetObjectUrl((LPCSTR)4, &pvPara, 0, 0, &pcbUrlArray, 0, 0, 0);
  if ( ObjectUrl == 1 )
  {
    v20 = (struct _CRYPT_URL_ARRAY *)operator new(pcbUrlArray);
    if ( v20 )
    {
      ObjectUrl = CryptGetObjectUrl((LPCSTR)4, &pvPara, 0, v20, &pcbUrlArray, 0, 0, 0);
      if ( ObjectUrl == 1 )
      {
        GetUrlArrayIndex(v20, v29, v21, &v25);
        v22 = a6;
        v23 = pcbUrlArray;
        *a5 = v20;
        *v22 = v23;
        if ( a7 )
          *a7 = v25;
      }
      else
      {
        operator delete(v20);
      }
    }
    else
    {
      SetLastError(0x8007000E);
      return 0;
    }
  }
  return ObjectUrl;
}

```

## disassembly

```asm
0x18001254c  mov     [rsp-38h+arg_10], rbx
0x180012551  mov     [rsp-38h+arg_18], r9
0x180012556  push    rbp
0x180012557  push    rsi
0x180012558  push    rdi
0x180012559  push    r12
0x18001255b  push    r13
0x18001255d  push    r14
0x18001255f  push    r15
0x180012561  mov     rbp, rsp
0x180012564  sub     rsp, 60h
0x180012568  mov     [rbp+pcbUrlArray], 0
0x18001256f  xorps   xmm0, xmm0
0x180012572  mov     [rbp+var_1C], 0
0x180012579  mov     r13, r8
0x18001257c  mov     [rbp+pvData], 0
0x180012583  mov     r15, rdx
0x180012586  movups  [rbp+pvPara], xmm0
0x18001258a  cmp     rcx, 3
0x18001258e  jz      short loc_1800125B5
0x180012590  mov     ecx, 80070057h; dwErrCode
0x180012595  call    cs:__imp_SetLastError
0x18001259b  xor     eax, eax
0x18001259d  mov     rbx, [rsp+60h+arg_10]
0x1800125a5  add     rsp, 60h
0x1800125a9  pop     r15
0x1800125ab  pop     r14
0x1800125ad  pop     r13
0x1800125af  pop     r12
0x1800125b1  pop     rdi
0x1800125b2  pop     rsi
0x1800125b3  pop     rbp
0x1800125b4  retn
0x1800125b5  mov     rcx, [r15+28h]; hCryptMsg
0x1800125b9  lea     rax, [rbp+arg_0]
0x1800125bd  xor     r8d, r8d; dwIndex
0x1800125c0  mov     [rbp+arg_0], 4
0x1800125c7  lea     r9, [rbp+pvData]; pvData
0x1800125cb  mov     [rsp+60h+pcbData], rax; pcbData
0x1800125d0  lea     edx, [r8+5]; dwParamType
0x1800125d4  call    cs:__imp_CryptMsgGetParam
0x1800125da  test    eax, eax
0x1800125dc  jz      short loc_18001259B
0x1800125de  xor     esi, esi
0x1800125e0  xor     edi, edi
0x1800125e2  cmp     edi, [rbp+pvData]
0x1800125e5  jnb     loc_1800126CA
0x1800125eb  test    esi, esi
0x1800125ed  jnz     loc_1800126D8
0x1800125f3  mov     rcx, [r15+28h]; hCryptMsg
0x1800125f7  lea     rax, [rbp+arg_0]
0x1800125fb  xor     r9d, r9d; pvData
0x1800125fe  mov     [rsp+60h+pcbData], rax; pcbData
0x180012603  mov     r8d, edi; dwIndex
0x180012606  lea     edx, [rsi+7]; dwParamType
0x180012609  call    cs:__imp_CryptMsgGetParam
0x18001260f  test    eax, eax
0x180012611  jz      loc_1800126B0
0x180012617  mov     ecx, [rbp+arg_0]; uBytes
0x18001261a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001261f  mov     rbx, rax
0x180012622  test    rax, rax
0x180012625  jz      short loc_1800126A6
0x180012627  mov     rcx, [r15+28h]; hCryptMsg
0x18001262b  lea     rax, [rbp+arg_0]
0x18001262f  mov     r9, rbx; pvData
0x180012632  mov     [rsp+60h+pcbData], rax; pcbData
0x180012637  mov     r8d, edi; dwIndex
0x18001263a  lea     edx, [rsi+7]; dwParamType
0x18001263d  call    cs:__imp_CryptMsgGetParam
0x180012643  test    eax, eax
0x180012645  jz      short loc_180012699
0x180012647  mov     r14, [r13+18h]
0x18001264b  mov     eax, [rbx+30h]
0x18001264e  cmp     [r14+30h], eax
0x180012652  jnz     short loc_18001268A
0x180012654  mov     r12d, [rbx+8]
0x180012658  cmp     [r14+8], r12d
0x18001265c  jnz     short loc_18001268A
0x18001265e  mov     rdx, [rbx+38h]; Buf2
0x180012662  mov     r8d, eax; Size
0x180012665  mov     rcx, [r14+38h]; Buf1
0x180012669  call    memcmp_0
0x18001266e  test    eax, eax
0x180012670  jnz     short loc_18001268A
0x180012672  mov     rdx, [rbx+10h]; Buf2
0x180012676  mov     r8d, r12d; Size
0x180012679  mov     rcx, [r14+10h]; Buf1
0x18001267d  call    memcmp_0
0x180012682  test    eax, eax
0x180012684  lea     eax, [rsi+1]
0x180012687  cmovz   esi, eax
0x18001268a  mov     rcx, rbx; hMem
0x18001268d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012692  inc     edi
0x180012694  jmp     loc_1800125E2
0x180012699  mov     rcx, rbx; hMem
0x18001269c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126a1  jmp     loc_18001259B
0x1800126a6  mov     ecx, 8007000Eh
0x1800126ab  jmp     loc_180012595
0x1800126b0  call    cs:__imp_GetLastError
0x1800126b6  mov     edx, eax
0x1800126b8  lea     rcx, Format; "GetLastError() = %lx\n"
0x1800126bf  call    cs:__imp_printf
0x1800126c5  jmp     loc_18001259B
0x1800126ca  test    esi, esi
0x1800126cc  jnz     short loc_1800126D8
0x1800126ce  mov     ecx, 80092004h
0x1800126d3  jmp     loc_180012595
0x1800126d8  lea     ecx, [rdi-1]
0x1800126db  mov     [rsp+60h+pvReserved], 0; pvReserved
0x1800126e4  xor     r9d, r9d; pUrlArray
0x1800126e7  mov     qword ptr [rbp+pvPara+8], rcx
0x1800126eb  mov     [rsp+60h+pcbUrlInfo], 0; pcbUrlInfo
0x1800126f4  lea     rax, [rbp+pcbUrlArray]
0x1800126f8  mov     [rsp+60h+pUrlInfo], 0; pUrlInfo
0x180012701  lea     rdx, [rbp+pvPara]; pvPara
0x180012705  xor     r8d, r8d; dwFlags
0x180012708  mov     qword ptr [rbp+pvPara], r15
0x18001270c  lea     ecx, [r9+4]; pszUrlOid
0x180012710  mov     [rsp+60h+pcbData], rax; pcbUrlArray
0x180012715  call    CryptGetObjectUrl
0x18001271a  mov     esi, 1
0x18001271f  mov     ebx, eax
0x180012721  cmp     eax, esi
0x180012723  jnz     loc_1800127B9
0x180012729  mov     ecx, [rbp+pcbUrlArray]; uBytes
0x18001272c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012731  mov     rdi, rax
0x180012734  test    rax, rax
0x180012737  jz      short loc_1800127AC
0x180012739  mov     [rsp+60h+pvReserved], 0; pvReserved
0x180012742  lea     rax, [rbp+pcbUrlArray]
0x180012746  mov     [rsp+60h+pcbUrlInfo], 0; pcbUrlInfo
0x18001274f  lea     rdx, [rbp+pvPara]; pvPara
0x180012753  mov     [rsp+60h+pUrlInfo], 0; pUrlInfo
0x18001275c  lea     ecx, [rsi+3]; pszUrlOid
0x18001275f  mov     r9, rdi; pUrlArray
0x180012762  mov     [rsp+60h+pcbData], rax; pcbUrlArray
0x180012767  xor     r8d, r8d; dwFlags
0x18001276a  call    CryptGetObjectUrl
0x18001276f  mov     ebx, eax
0x180012771  mov     rcx, rdi; hMem
0x180012774  cmp     eax, esi
0x180012776  jnz     short loc_1800127A5
0x180012778  mov     rdx, [rbp+arg_18]
0x18001277c  lea     r9, [rbp+var_1C]
0x180012780  call    GetUrlArrayIndex
0x180012785  mov     rcx, [rbp+arg_28]
0x180012789  mov     r9, [rbp+arg_20]
0x18001278d  mov     eax, [rbp+pcbUrlArray]
0x180012790  mov     [r9], rdi
0x180012793  mov     [rcx], eax
0x180012795  mov     rcx, [rbp+arg_30]
0x180012799  test    rcx, rcx
0x18001279c  jz      short loc_1800127B9
0x18001279e  mov     eax, [rbp+var_1C]
0x1800127a1  mov     [rcx], eax
0x1800127a3  jmp     short loc_1800127B9
0x1800127a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800127aa  jmp     short loc_1800127B9
0x1800127ac  mov     ecx, 8007000Eh; dwErrCode
0x1800127b1  call    cs:__imp_SetLastError
0x1800127b7  xor     ebx, ebx
0x1800127b9  mov     eax, ebx
0x1800127bb  jmp     loc_18001259D
```
