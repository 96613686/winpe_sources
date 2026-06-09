# DavGetCertStoreFromIssuerList

- ea: `0x18000c264`
- end: `0x18000c4fa`
- name: `DavGetCertStoreFromIssuerList`
- size: `662`
- prototype: `__int64 __fastcall(int, unsigned __int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007ad0`

## callees

- `0x18000c264`
- `0x180010a14`
- `0x180010be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c40b`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000c2d0`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000c2d0`
- `CRYPT32!CertCloseStore` at `0x18000c49c`
- `CRYPT32!CertCloseStore` at `0x18000c4ba`
- `CRYPT32!CertCloseStore` at `0x18000c49c`
- `CRYPT32!CertCloseStore` at `0x18000c4ba`
- `CRYPT32!CertFreeCertificateChain` at `0x18000c447`
- `CRYPT32!CertFreeCertificateChain` at `0x18000c447`
- `CRYPT32!CertOpenStore` at `0x18000c336`
- `CRYPT32!CertOpenStore` at `0x18000c336`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000c3fd`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000c3fd`
- `CRYPT32!CertFindChainInStore` at `0x18000c3d3`
- `CRYPT32!CertFindChainInStore` at `0x18000c3d3`

## pseudocode

```c
__int64 __fastcall DavGetCertStoreFromIssuerList(int a1, unsigned __int64 a2, _QWORD *a3, unsigned int *a4)
{
  HCERTSTORE v7; // r15
  HCERTSTORE v8; // rdi
  DWORD v9; // eax
  DWORD v10; // ebx
  _QWORD *v11; // rcx
  DWORD v12; // eax
  unsigned int v13; // esi
  const CERT_CHAIN_CONTEXT *pPrevChainContext; // r14
  PCCERT_CHAIN_CONTEXT ChainInStore; // rax
  DWORD LastError; // eax
  __int128 pvFindPara; // [rsp+30h] [rbp-48h] BYREF
  __int128 v19; // [rsp+40h] [rbp-38h]
  __int128 v20; // [rsp+50h] [rbp-28h]
  __int64 v21; // [rsp+60h] [rbp-18h]

  pvFindPara = 0;
  LODWORD(v21) = 0;
  v19 = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
  v7 = CertOpenSystemStoreW(0, L"MY");
  if ( v7 )
  {
    v8 = CertOpenStore((LPCSTR)2, 0, 0, 0x1000u, 0);
    if ( v8 )
    {
      v13 = 0;
      pPrevChainContext = 0;
      *(_QWORD *)&pvFindPara = 56;
      v21 = 0;
      v20 = a2;
      v19 = 0;
      *((_QWORD *)&pvFindPara + 1) = "1.3.6.1.5.5.7.3.2";
      DWORD2(v19) = a1;
      while ( 1 )
      {
        ChainInStore = CertFindChainInStore(v7, 1u, 0, 1u, &pvFindPara, pPrevChainContext);
        pPrevChainContext = ChainInStore;
        if ( !ChainInStore )
          break;
        if ( !CertAddCertificateContextToStore(v8, (*(*ChainInStore->rgpChain)->rgpElement)->pCertContext, 3u, 0) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              372,
              WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
              LastError);
          CertFreeCertificateChain(pPrevChainContext);
          goto LABEL_23;
        }
        ++v13;
      }
      v10 = 0;
      *a3 = v8;
      *a4 = v13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 373, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v13);
    }
    else
    {
      v12 = GetLastError();
      v10 = v12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 371, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v12);
    }
LABEL_23:
    CertCloseStore(v7, 1u);
    goto LABEL_24;
  }
  v8 = 0;
  v9 = GetLastError();
  v10 = v9;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 370, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v9);
LABEL_24:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v10 && v8 )
  {
    CertCloseStore(v8, 1u);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
    WPP_SF_(v11[2], 374, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
  return v10;
}

```

## disassembly

```asm
0x18000c264  mov     [rsp-40h+arg_10], r8
0x18000c269  push    rbp
0x18000c26a  push    rbx
0x18000c26b  push    rsi
0x18000c26c  push    rdi
0x18000c26d  push    r12
0x18000c26f  push    r13
0x18000c271  push    r14
0x18000c273  push    r15
0x18000c275  mov     rbp, rsp
0x18000c278  sub     rsp, 78h
0x18000c27c  xorps   xmm0, xmm0
0x18000c27f  xor     eax, eax
0x18000c281  movups  [rbp+pvFindPara], xmm0
0x18000c285  mov     dword ptr [rbp+var_18], eax
0x18000c288  mov     r13, r9
0x18000c28b  movups  [rbp+var_38], xmm0
0x18000c28f  mov     rbx, rdx
0x18000c292  mov     r12d, ecx
0x18000c295  movups  [rbp+var_28], xmm0
0x18000c299  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2a0  lea     rsi, WPP_GLOBAL_Control
0x18000c2a7  cmp     rcx, rsi
0x18000c2aa  jz      short loc_18000C2C7
0x18000c2ac  test    byte ptr [rcx+1Ch], 2
0x18000c2b0  jz      short loc_18000C2C7
0x18000c2b2  mov     rcx, [rcx+10h]
0x18000c2b6  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c2bd  mov     edx, 171h
0x18000c2c2  call    WPP_SF_
0x18000c2c7  lea     rdx, szSubsystemProtocol; "MY"
0x18000c2ce  xor     ecx, ecx; hProv
0x18000c2d0  call    cs:__imp_CertOpenSystemStoreW
0x18000c2d6  mov     r15, rax
0x18000c2d9  test    rax, rax
0x18000c2dc  jnz     short loc_18000C31F
0x18000c2de  xor     edi, edi
0x18000c2e0  call    cs:__imp_GetLastError
0x18000c2e6  mov     ebx, eax
0x18000c2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ef  cmp     rcx, rsi
0x18000c2f2  jz      loc_18000C4A9
0x18000c2f8  test    byte ptr [rcx+1Ch], 1
0x18000c2fc  jz      loc_18000C4A9
0x18000c302  mov     rcx, [rcx+10h]
0x18000c306  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c30d  mov     edx, 172h
0x18000c312  mov     r9d, eax
0x18000c315  call    WPP_SF_d
0x18000c31a  jmp     loc_18000C4A2
0x18000c31f  xor     edx, edx; dwEncodingType
0x18000c321  mov     [rsp+78h+pvPara], 0; pvPara
0x18000c32a  mov     r9d, 1000h; dwFlags
0x18000c330  xor     r8d, r8d; hCryptProv
0x18000c333  lea     ecx, [rdx+2]; lpszStoreProvider
0x18000c336  call    cs:__imp_CertOpenStore
0x18000c33c  mov     rdi, rax
0x18000c33f  test    rax, rax
0x18000c342  jnz     short loc_18000C383
0x18000c344  call    cs:__imp_GetLastError
0x18000c34a  mov     ebx, eax
0x18000c34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c353  cmp     rcx, rsi
0x18000c356  jz      loc_18000C494
0x18000c35c  test    byte ptr [rcx+1Ch], 1
0x18000c360  jz      loc_18000C494
0x18000c366  mov     rcx, [rcx+10h]
0x18000c36a  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c371  mov     edx, 173h
0x18000c376  mov     r9d, eax
0x18000c379  call    WPP_SF_d
0x18000c37e  jmp     loc_18000C494
0x18000c383  xorps   xmm0, xmm0
0x18000c386  xor     esi, esi
0x18000c388  movups  [rbp+pvFindPara], xmm0
0x18000c38c  xor     r14d, r14d
0x18000c38f  mov     dword ptr [rbp+pvFindPara], 38h ; '8'
0x18000c396  xor     eax, eax
0x18000c398  mov     [rbp+var_18], rax
0x18000c39c  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x18000c3a3  movups  [rbp+var_28], xmm0
0x18000c3a7  mov     qword ptr [rbp+var_28], rbx
0x18000c3ab  lea     ebx, [rsi+1]
0x18000c3ae  movups  [rbp+var_38], xmm0
0x18000c3b2  mov     qword ptr [rbp+pvFindPara+8], rax
0x18000c3b6  mov     dword ptr [rbp+var_38+8], r12d
0x18000c3ba  lea     rax, [rbp+pvFindPara]
0x18000c3be  mov     [rsp+78h+pPrevChainContext], r14; pPrevChainContext
0x18000c3c3  mov     r9d, ebx; dwFindType
0x18000c3c6  mov     [rsp+78h+pvPara], rax; pvFindPara
0x18000c3cb  xor     r8d, r8d; dwFindFlags
0x18000c3ce  mov     edx, ebx; dwCertEncodingType
0x18000c3d0  mov     rcx, r15; hCertStore
0x18000c3d3  call    cs:__imp_CertFindChainInStore
0x18000c3d9  mov     r14, rax
0x18000c3dc  test    rax, rax
0x18000c3df  jz      short loc_18000C44F
0x18000c3e1  mov     rcx, [rax+10h]
0x18000c3e5  xor     r9d, r9d; ppStoreContext
0x18000c3e8  mov     rdx, [rcx]
0x18000c3eb  lea     r8d, [r9+3]; dwAddDisposition
0x18000c3ef  mov     rcx, [rdx+10h]
0x18000c3f3  mov     rdx, [rcx]
0x18000c3f6  mov     rcx, rdi; hCertStore
0x18000c3f9  mov     rdx, [rdx+8]; pCertContext
0x18000c3fd  call    cs:__imp_CertAddCertificateContextToStore
0x18000c403  test    eax, eax
0x18000c405  jz      short loc_18000C40B
0x18000c407  add     esi, ebx
0x18000c409  jmp     short loc_18000C3BA
0x18000c40b  call    cs:__imp_GetLastError
0x18000c411  mov     ebx, eax
0x18000c413  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c41a  lea     rsi, WPP_GLOBAL_Control
0x18000c421  cmp     rcx, rsi
0x18000c424  jz      short loc_18000C444
0x18000c426  test    byte ptr [rcx+1Ch], 1
0x18000c42a  jz      short loc_18000C444
0x18000c42c  mov     rcx, [rcx+10h]
0x18000c430  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c437  mov     edx, 174h
0x18000c43c  mov     r9d, eax
0x18000c43f  call    WPP_SF_d
0x18000c444  mov     rcx, r14; pChainContext
0x18000c447  call    cs:__imp_CertFreeCertificateChain
0x18000c44d  jmp     short loc_18000C494
0x18000c44f  mov     rax, [rbp+arg_10]
0x18000c453  xor     ebx, ebx
0x18000c455  mov     [rax], rdi
0x18000c458  mov     [r13+0], esi
0x18000c45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c463  lea     rax, WPP_GLOBAL_Control
0x18000c46a  cmp     rcx, rax
0x18000c46d  jz      short loc_18000C48D
0x18000c46f  test    byte ptr [rcx+1Ch], 2
0x18000c473  jz      short loc_18000C48D
0x18000c475  mov     rcx, [rcx+10h]
0x18000c479  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c480  mov     edx, 175h
0x18000c485  mov     r9d, esi
0x18000c488  call    WPP_SF_d
0x18000c48d  lea     rsi, WPP_GLOBAL_Control
0x18000c494  mov     edx, 1; dwFlags
0x18000c499  mov     rcx, r15; hCertStore
0x18000c49c  call    cs:__imp_CertCloseStore
0x18000c4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4a9  test    ebx, ebx
0x18000c4ab  jz      short loc_18000C4C7
0x18000c4ad  test    rdi, rdi
0x18000c4b0  jz      short loc_18000C4C7
0x18000c4b2  mov     edx, 1; dwFlags
0x18000c4b7  mov     rcx, rdi; hCertStore
0x18000c4ba  call    cs:__imp_CertCloseStore
0x18000c4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4c7  cmp     rcx, rsi
0x18000c4ca  jz      short loc_18000C4E7
0x18000c4cc  test    byte ptr [rcx+1Ch], 2
0x18000c4d0  jz      short loc_18000C4E7
0x18000c4d2  mov     rcx, [rcx+10h]
0x18000c4d6  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c4dd  mov     edx, 176h
0x18000c4e2  call    WPP_SF_
0x18000c4e7  mov     eax, ebx
0x18000c4e9  add     rsp, 78h
0x18000c4ed  pop     r15
0x18000c4ef  pop     r14
0x18000c4f1  pop     r13
0x18000c4f3  pop     r12
0x18000c4f5  pop     rdi
0x18000c4f6  pop     rsi
0x18000c4f7  pop     rbx
0x18000c4f8  pop     rbp
0x18000c4f9  retn
```
