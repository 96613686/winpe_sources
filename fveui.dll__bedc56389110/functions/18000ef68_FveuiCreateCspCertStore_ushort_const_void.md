# FveuiCreateCspCertStore(ushort const *,void * *)

- ea: `0x18000ef68`
- end: `0x18000f35b`
- name: `?FveuiCreateCspCertStore@@YAJPEBGPEAPEAX@Z`
- size: `1011`
- prototype: `__int64 __fastcall(LPCWSTR szProvider, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ebc0`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000ef68`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000f0ad`
- `KERNEL32!MultiByteToWideChar` at `0x18000f0ad`
- `KERNEL32!HeapFree` at `0x18000f202`
- `KERNEL32!HeapFree` at `0x18000f250`
- `KERNEL32!HeapFree` at `0x18000f329`
- `KERNEL32!HeapFree` at `0x18000f202`
- `KERNEL32!HeapFree` at `0x18000f250`
- `KERNEL32!HeapFree` at `0x18000f329`
- `KERNEL32!HeapAlloc` at `0x18000f138`
- `KERNEL32!HeapAlloc` at `0x18000f138`
- `KERNEL32!GetProcessHeap` at `0x18000f12a`
- `KERNEL32!GetProcessHeap` at `0x18000f1f2`
- `KERNEL32!GetProcessHeap` at `0x18000f240`
- `KERNEL32!GetProcessHeap` at `0x18000f319`
- `KERNEL32!GetProcessHeap` at `0x18000f12a`
- `KERNEL32!GetProcessHeap` at `0x18000f1f2`
- `KERNEL32!GetProcessHeap` at `0x18000f240`
- `KERNEL32!GetProcessHeap` at `0x18000f319`
- `KERNEL32!GetLastError` at `0x18000f293`
- `KERNEL32!GetLastError` at `0x18000f2ab`
- `KERNEL32!GetLastError` at `0x18000f293`
- `KERNEL32!GetLastError` at `0x18000f2ab`
- `ADVAPI32!CryptGetKeyParam` at `0x18000f118`
- `ADVAPI32!CryptGetKeyParam` at `0x18000f163`
- `ADVAPI32!CryptGetKeyParam` at `0x18000f118`
- `ADVAPI32!CryptGetKeyParam` at `0x18000f163`
- `ADVAPI32!CryptGetUserKey` at `0x18000f0f4`
- `ADVAPI32!CryptGetUserKey` at `0x18000f0f4`
- `ADVAPI32!CryptGetProvParam` at `0x18000f07c`
- `ADVAPI32!CryptGetProvParam` at `0x18000f07c`
- `ADVAPI32!CryptAcquireContextW` at `0x18000f04f`
- `ADVAPI32!CryptAcquireContextW` at `0x18000f0cc`
- `ADVAPI32!CryptAcquireContextW` at `0x18000f04f`
- `ADVAPI32!CryptAcquireContextW` at `0x18000f0cc`
- `ADVAPI32!CryptDestroyKey` at `0x18000f1e0`
- `ADVAPI32!CryptDestroyKey` at `0x18000f265`
- `ADVAPI32!CryptDestroyKey` at `0x18000f2ca`
- `ADVAPI32!CryptDestroyKey` at `0x18000f1e0`
- `ADVAPI32!CryptDestroyKey` at `0x18000f265`
- `ADVAPI32!CryptDestroyKey` at `0x18000f2ca`
- `ADVAPI32!CryptReleaseContext` at `0x18000f27a`
- `ADVAPI32!CryptReleaseContext` at `0x18000f2db`
- `ADVAPI32!CryptReleaseContext` at `0x18000f2ec`
- `ADVAPI32!CryptReleaseContext` at `0x18000f27a`
- `ADVAPI32!CryptReleaseContext` at `0x18000f2db`
- `ADVAPI32!CryptReleaseContext` at `0x18000f2ec`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f1d0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f22e`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f2fc`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f1d0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f22e`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f2fc`
- `CRYPT32!CertOpenStore` at `0x18000f029`
- `CRYPT32!CertOpenStore` at `0x18000f029`
- `CRYPT32!CryptQueryObject` at `0x18000f1a7`
- `CRYPT32!CryptQueryObject` at `0x18000f1a7`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f1c1`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f1c1`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f223`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f223`
- `CRYPT32!CertCloseStore` at `0x18000f30c`
- `CRYPT32!CertCloseStore` at `0x18000f30c`

## pseudocode

```c
__int64 __fastcall FveuiCreateCspCertStore(LPCWSTR szProvider, void **a2)
{
  HCERTSTORE v4; // rsi
  DWORD i; // eax
  DWORD j; // edi
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  unsigned int v12; // ebx
  signed int LastError; // eax
  HANDLE v14; // rax
  HCRYPTKEY phUserKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pvObject[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-88h] BYREF
  DWORD pdwDataLen; // [rsp+80h] [rbp-80h] BYREF
  HCRYPTPROV hProv; // [rsp+88h] [rbp-78h] BYREF
  HCRYPTPROV phProv; // [rsp+90h] [rbp-70h] BYREF
  _QWORD pvData[5]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v24; // [rsp+C0h] [rbp-40h]
  BYTE pbData; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[271]; // [rsp+D1h] [rbp-2Fh] BYREF
  WCHAR WideCharStr; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v28[526]; // [rsp+1E2h] [rbp+E2h] BYREF

  phProv = 0;
  hProv = 0;
  phUserKey = 0;
  pbData = 0;
  memset_0(v26, 0, 0x103u);
  WideCharStr = 0;
  memset_0(v28, 0, 0x206u);
  pdwDataLen = 0;
  *(_QWORD *)pvObject = 0;
  lpMem = 0;
  pCertContext = 0;
  pvData[0] = &WideCharStr;
  pvData[1] = szProvider;
  pvData[2] = 1;
  pvData[3] = 0;
  pvData[4] = 0;
  v24 = 0;
  v4 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, 0);
  if ( !v4 || !CryptAcquireContextW(&phProv, 0, szProvider, 1u, 0x40u) )
    goto LABEL_28;
  for ( i = 1; ; i = 0 )
  {
    pdwDataLen = 260;
    if ( !CryptGetProvParam(phProv, 2u, &pbData, &pdwDataLen, i) )
      break;
    MultiByteToWideChar(0xFDE9u, 0, (LPCCH)&pbData, -1, &WideCharStr, 260);
    if ( CryptAcquireContextW(&hProv, &WideCharStr, szProvider, 1u, 0x40u) )
    {
      for ( j = 1; ; ++j )
      {
        if ( j > 2 )
        {
          CryptReleaseContext(hProv, 0);
          hProv = 0;
          break;
        }
        LODWORD(v24) = j;
        if ( CryptGetUserKey(hProv, j, &phUserKey) )
        {
          if ( !CryptGetKeyParam(phUserKey, 0x1Au, 0, pvObject, 0) )
            goto LABEL_21;
          v7 = pvObject[0];
          ProcessHeap = GetProcessHeap();
          v9 = HeapAlloc(ProcessHeap, 0, v7);
          lpMem = v9;
          if ( !v9 )
          {
            v12 = -2147024882;
            goto LABEL_30;
          }
          if ( CryptGetKeyParam(phUserKey, 0x1Au, (BYTE *)v9, pvObject, 0)
            && CryptQueryObject(2u, pvObject, 2u, 0xEu, 0, 0, 0, 0, 0, 0, (const void **)&pCertContext) )
          {
            if ( CertSetCertificateContextProperty(pCertContext, 2u, 0, pvData) )
            {
              CertAddCertificateContextToStore(v4, pCertContext, 4u, 0);
              CertFreeCertificateContext(pCertContext);
              pCertContext = 0;
              if ( lpMem )
              {
                v11 = GetProcessHeap();
                HeapFree(v11, 0, lpMem);
                lpMem = 0;
              }
              pvObject[0] = 0;
LABEL_21:
              CryptDestroyKey(phUserKey);
              phUserKey = 0;
              continue;
            }
            CertFreeCertificateContext(pCertContext);
            pCertContext = 0;
          }
          CryptDestroyKey(phUserKey);
          phUserKey = 0;
          if ( lpMem )
          {
            v10 = GetProcessHeap();
            HeapFree(v10, 0, lpMem);
            lpMem = 0;
          }
          pvObject[0] = 0;
        }
      }
    }
  }
  if ( GetLastError() == 259 )
  {
    *a2 = v4;
    v12 = 0;
    v4 = 0;
  }
  else
  {
LABEL_28:
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_30:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v4 )
    CertCloseStore(v4, 0);
  if ( lpMem )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, lpMem);
  }
  return v12;
}

```

## disassembly

```asm
0x18000ef68  mov     [rsp-8+arg_10], rbx
0x18000ef6d  push    rbp
0x18000ef6e  push    rsi
0x18000ef6f  push    rdi
0x18000ef70  push    r12
0x18000ef72  push    r13
0x18000ef74  push    r14
0x18000ef76  push    r15
0x18000ef78  lea     rbp, [rsp-300h]
0x18000ef80  sub     rsp, 400h
0x18000ef87  mov     rax, cs:__security_cookie
0x18000ef8e  xor     rax, rsp
0x18000ef91  mov     [rbp+330h+var_40], rax
0x18000ef98  xor     r12d, r12d
0x18000ef9b  mov     r15, rdx
0x18000ef9e  mov     r14, rcx
0x18000efa1  mov     [rbp+330h+phProv], r12
0x18000efa5  xor     edx, edx; Val
0x18000efa7  mov     [rbp+330h+hProv], r12
0x18000efab  lea     rcx, [rbp+330h+var_35F]; void *
0x18000efaf  mov     [rsp+430h+phUserKey], r12
0x18000efb4  mov     r8d, 103h; Size
0x18000efba  mov     [rbp+330h+pbData], r12b
0x18000efbe  call    memset_0
0x18000efc3  xor     edx, edx; Val
0x18000efc5  mov     [rbp+330h+WideCharStr], r12w
0x18000efcd  mov     r8d, 206h; Size
0x18000efd3  lea     rcx, [rbp+330h+var_24E]; void *
0x18000efda  call    memset_0
0x18000efdf  xor     edx, edx; dwEncodingType
0x18000efe1  mov     [rbp+330h+pdwDataLen], r12d
0x18000efe5  lea     rax, [rbp+330h+WideCharStr]
0x18000efec  mov     qword ptr [rsp+430h+pvObject], r12
0x18000eff1  lea     r13d, [r12+1]
0x18000eff6  mov     [rsp+430h+lpMem], r12
0x18000effb  mov     r9d, 2000h; dwFlags
0x18000f001  mov     [rsp+430h+pCertContext], r12
0x18000f006  lea     ecx, [rdx+2]; lpszStoreProvider
0x18000f009  mov     [rbp+330h+pvData], rax
0x18000f00d  xor     r8d, r8d; hCryptProv
0x18000f010  mov     [rbp+330h+var_390], r14
0x18000f014  mov     [rbp+330h+var_388], r13
0x18000f018  mov     [rbp+330h+var_380], r12
0x18000f01c  mov     [rbp+330h+var_378], r12
0x18000f020  mov     [rbp+330h+var_370], r12
0x18000f024  mov     [rsp+430h+pvPara], r12; pvPara
0x18000f029  call    cs:__imp_CertOpenStore
0x18000f02f  mov     rsi, rax
0x18000f032  test    rax, rax
0x18000f035  jz      loc_18000F2AB
0x18000f03b  mov     r9d, r13d; dwProvType
0x18000f03e  mov     dword ptr [rsp+430h+pvPara], 40h ; '@'; dwFlags
0x18000f046  mov     r8, r14; szProvider
0x18000f049  lea     rcx, [rbp+330h+phProv]; phProv
0x18000f04d  xor     edx, edx; szContainer
0x18000f04f  call    cs:__imp_CryptAcquireContextW
0x18000f055  test    eax, eax
0x18000f057  jz      loc_18000F2AB
0x18000f05d  mov     eax, r13d
0x18000f060  mov     rcx, [rbp+330h+phProv]; hProv
0x18000f064  lea     r9, [rbp+330h+pdwDataLen]; pdwDataLen
0x18000f068  lea     r8, [rbp+330h+pbData]; pbData
0x18000f06c  mov     [rbp+330h+pdwDataLen], 104h
0x18000f073  mov     edx, 2; dwParam
0x18000f078  mov     dword ptr [rsp+430h+pvPara], eax; dwFlags
0x18000f07c  call    cs:__imp_CryptGetProvParam
0x18000f082  test    eax, eax
0x18000f084  jz      loc_18000F293
0x18000f08a  lea     rax, [rbp+330h+WideCharStr]
0x18000f091  mov     [rsp+430h+cchWideChar], 104h; cchWideChar
0x18000f099  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000f09d  mov     [rsp+430h+pvPara], rax; lpWideCharStr
0x18000f0a2  lea     r8, [rbp+330h+pbData]; lpMultiByteStr
0x18000f0a6  xor     edx, edx; dwFlags
0x18000f0a8  mov     ecx, 0FDE9h; CodePage
0x18000f0ad  call    cs:__imp_MultiByteToWideChar
0x18000f0b3  mov     r9d, r13d; dwProvType
0x18000f0b6  mov     dword ptr [rsp+430h+pvPara], 40h ; '@'; dwFlags
0x18000f0be  mov     r8, r14; szProvider
0x18000f0c1  lea     rdx, [rbp+330h+WideCharStr]; szContainer
0x18000f0c8  lea     rcx, [rbp+330h+hProv]; phProv
0x18000f0cc  call    cs:__imp_CryptAcquireContextW
0x18000f0d2  test    eax, eax
0x18000f0d4  jz      loc_18000F284
0x18000f0da  mov     edi, r13d
0x18000f0dd  mov     rcx, [rbp+330h+hProv]; hProv
0x18000f0e1  cmp     edi, 2
0x18000f0e4  ja      loc_18000F278
0x18000f0ea  lea     r8, [rsp+430h+phUserKey]; phUserKey
0x18000f0ef  mov     dword ptr [rbp+330h+var_370], edi
0x18000f0f2  mov     edx, edi; dwKeySpec
0x18000f0f4  call    cs:__imp_CryptGetUserKey
0x18000f0fa  test    eax, eax
0x18000f0fc  jz      loc_18000F270
0x18000f102  mov     rcx, [rsp+430h+phUserKey]; hKey
0x18000f107  lea     r9, [rsp+430h+pvObject]; pdwDataLen
0x18000f10c  xor     r8d, r8d; pbData
0x18000f10f  mov     dword ptr [rsp+430h+pvPara], r12d; dwFlags
0x18000f114  lea     edx, [r8+1Ah]; dwParam
0x18000f118  call    cs:__imp_CryptGetKeyParam
0x18000f11e  test    eax, eax
0x18000f120  jz      loc_18000F260
0x18000f126  mov     ebx, [rsp+430h+pvObject]
0x18000f12a  call    cs:__imp_GetProcessHeap
0x18000f130  mov     r8d, ebx; dwBytes
0x18000f133  xor     edx, edx; dwFlags
0x18000f135  mov     rcx, rax; hHeap
0x18000f138  call    cs:__imp_HeapAlloc
0x18000f13e  mov     [rsp+430h+lpMem], rax
0x18000f143  test    rax, rax
0x18000f146  jz      loc_18000F28C
0x18000f14c  mov     rcx, [rsp+430h+phUserKey]; hKey
0x18000f151  lea     r9, [rsp+430h+pvObject]; pdwDataLen
0x18000f156  mov     r8, rax; pbData
0x18000f159  mov     dword ptr [rsp+430h+pvPara], r12d; dwFlags
0x18000f15e  mov     edx, 1Ah; dwParam
0x18000f163  call    cs:__imp_CryptGetKeyParam
0x18000f169  test    eax, eax
0x18000f16b  jz      short loc_18000F1DB
0x18000f16d  lea     rax, [rsp+430h+pCertContext]
0x18000f172  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x18000f178  mov     [rsp+430h+ppvContext], rax; ppvContext
0x18000f17d  lea     rdx, [rsp+430h+pvObject]; pvObject
0x18000f182  mov     [rsp+430h+phMsg], r12; phMsg
0x18000f187  mov     [rsp+430h+phCertStore], r12; phCertStore
0x18000f18c  mov     [rsp+430h+pdwFormatType], r12; pdwFormatType
0x18000f191  lea     r8d, [r9-0Ch]; dwExpectedContentTypeFlags
0x18000f195  mov     [rsp+430h+pdwContentType], r12; pdwContentType
0x18000f19a  mov     ecx, r8d; dwObjectType
0x18000f19d  mov     qword ptr [rsp+430h+cchWideChar], r12; pdwMsgAndCertEncodingType
0x18000f1a2  mov     dword ptr [rsp+430h+pvPara], r12d; dwFlags
0x18000f1a7  call    cs:__imp_CryptQueryObject
0x18000f1ad  test    eax, eax
0x18000f1af  jz      short loc_18000F1DB
0x18000f1b1  mov     rcx, [rsp+430h+pCertContext]; pCertContext
0x18000f1b6  lea     r9, [rbp+330h+pvData]; pvData
0x18000f1ba  xor     r8d, r8d; dwFlags
0x18000f1bd  lea     edx, [r8+2]; dwPropId
0x18000f1c1  call    cs:__imp_CertSetCertificateContextProperty
0x18000f1c7  test    eax, eax
0x18000f1c9  jnz     short loc_18000F214
0x18000f1cb  mov     rcx, [rsp+430h+pCertContext]; pCertContext
0x18000f1d0  call    cs:__imp_CertFreeCertificateContext
0x18000f1d6  mov     [rsp+430h+pCertContext], r12
0x18000f1db  mov     rcx, [rsp+430h+phUserKey]; hKey
0x18000f1e0  call    cs:__imp_CryptDestroyKey
0x18000f1e6  mov     [rsp+430h+phUserKey], r12
0x18000f1eb  cmp     [rsp+430h+lpMem], r12
0x18000f1f0  jz      short loc_18000F20D
0x18000f1f2  call    cs:__imp_GetProcessHeap
0x18000f1f8  mov     r8, [rsp+430h+lpMem]; lpMem
0x18000f1fd  xor     edx, edx; dwFlags
0x18000f1ff  mov     rcx, rax; hHeap
0x18000f202  call    cs:__imp_HeapFree
0x18000f208  mov     [rsp+430h+lpMem], r12
0x18000f20d  mov     [rsp+430h+pvObject], r12d
0x18000f212  jmp     short loc_18000F270
0x18000f214  mov     rdx, [rsp+430h+pCertContext]; pCertContext
0x18000f219  xor     r9d, r9d; ppStoreContext
0x18000f21c  mov     rcx, rsi; hCertStore
0x18000f21f  lea     r8d, [r9+4]; dwAddDisposition
0x18000f223  call    cs:__imp_CertAddCertificateContextToStore
0x18000f229  mov     rcx, [rsp+430h+pCertContext]; pCertContext
0x18000f22e  call    cs:__imp_CertFreeCertificateContext
0x18000f234  mov     [rsp+430h+pCertContext], r12
0x18000f239  cmp     [rsp+430h+lpMem], r12
0x18000f23e  jz      short loc_18000F25B
0x18000f240  call    cs:__imp_GetProcessHeap
0x18000f246  mov     r8, [rsp+430h+lpMem]; lpMem
0x18000f24b  xor     edx, edx; dwFlags
0x18000f24d  mov     rcx, rax; hHeap
0x18000f250  call    cs:__imp_HeapFree
0x18000f256  mov     [rsp+430h+lpMem], r12
0x18000f25b  mov     [rsp+430h+pvObject], r12d
0x18000f260  mov     rcx, [rsp+430h+phUserKey]; hKey
0x18000f265  call    cs:__imp_CryptDestroyKey
0x18000f26b  mov     [rsp+430h+phUserKey], r12
0x18000f270  add     edi, r13d
0x18000f273  jmp     loc_18000F0DD
0x18000f278  xor     edx, edx; dwFlags
0x18000f27a  call    cs:__imp_CryptReleaseContext
0x18000f280  mov     [rbp+330h+hProv], r12
0x18000f284  mov     eax, r12d
0x18000f287  jmp     loc_18000F060
0x18000f28c  mov     ebx, 8007000Eh
0x18000f291  jmp     short loc_18000F2C0
0x18000f293  call    cs:__imp_GetLastError
0x18000f299  cmp     eax, 103h
0x18000f29e  jnz     short loc_18000F2AB
0x18000f2a0  mov     [r15], rsi
0x18000f2a3  mov     ebx, r12d
0x18000f2a6  mov     rsi, r12
0x18000f2a9  jmp     short loc_18000F2C0
0x18000f2ab  call    cs:__imp_GetLastError
0x18000f2b1  mov     ebx, eax
0x18000f2b3  test    eax, eax
0x18000f2b5  jle     short loc_18000F2C0
0x18000f2b7  movzx   ebx, ax
0x18000f2ba  or      ebx, 80070000h
0x18000f2c0  mov     rcx, [rsp+430h+phUserKey]; hKey
0x18000f2c5  test    rcx, rcx
0x18000f2c8  jz      short loc_18000F2D0
0x18000f2ca  call    cs:__imp_CryptDestroyKey
0x18000f2d0  mov     rcx, [rbp+330h+hProv]; hProv
0x18000f2d4  test    rcx, rcx
0x18000f2d7  jz      short loc_18000F2E1
0x18000f2d9  xor     edx, edx; dwFlags
0x18000f2db  call    cs:__imp_CryptReleaseContext
0x18000f2e1  mov     rcx, [rbp+330h+phProv]; hProv
0x18000f2e5  test    rcx, rcx
0x18000f2e8  jz      short loc_18000F2F2
0x18000f2ea  xor     edx, edx; dwFlags
0x18000f2ec  call    cs:__imp_CryptReleaseContext
0x18000f2f2  mov     rcx, [rsp+430h+pCertContext]; pCertContext
0x18000f2f7  test    rcx, rcx
0x18000f2fa  jz      short loc_18000F302
0x18000f2fc  call    cs:__imp_CertFreeCertificateContext
0x18000f302  test    rsi, rsi
0x18000f305  jz      short loc_18000F312
0x18000f307  xor     edx, edx; dwFlags
0x18000f309  mov     rcx, rsi; hCertStore
0x18000f30c  call    cs:__imp_CertCloseStore
0x18000f312  cmp     [rsp+430h+lpMem], r12
0x18000f317  jz      short loc_18000F32F
0x18000f319  call    cs:__imp_GetProcessHeap
0x18000f31f  mov     r8, [rsp+430h+lpMem]; lpMem
0x18000f324  xor     edx, edx; dwFlags
0x18000f326  mov     rcx, rax; hHeap
0x18000f329  call    cs:__imp_HeapFree
0x18000f32f  mov     eax, ebx
0x18000f331  mov     rcx, [rbp+330h+var_40]
0x18000f338  xor     rcx, rsp; StackCookie
0x18000f33b  call    __security_check_cookie
0x18000f340  mov     rbx, [rsp+430h+arg_10]
0x18000f348  add     rsp, 400h
0x18000f34f  pop     r15
0x18000f351  pop     r14
0x18000f353  pop     r13
0x18000f355  pop     r12
0x18000f357  pop     rdi
0x18000f358  pop     rsi
0x18000f359  pop     rbp
0x18000f35a  retn
```
