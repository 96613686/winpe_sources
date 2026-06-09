# CCAPIStm::HandleEnveloped(void)

- ea: `0x18005ab90`
- end: `0x18005afa5`
- name: `?HandleEnveloped@CCAPIStm@@AEAAJXZ`
- size: `1045`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005ca70`

## callees

- `0x1800247c8`
- `0x18002c4b0`
- `0x18005a6a0`
- `0x18005ab90`
- `0x1800cc9ba`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrGetMsgParam` at `0x18005ad87`
- `MSOERT2!HrGetMsgParam` at `0x18005ad87`
- `MSOERT2!PVGetMsgParam` at `0x18005abfd`
- `MSOERT2!PVGetMsgParam` at `0x18005abfd`
- `ADVAPI32!CryptReleaseContext` at `0x18005aec0`
- `ADVAPI32!CryptReleaseContext` at `0x18005aec0`
- `ADVAPI32!CryptSetProvParam` at `0x18005ae80`
- `ADVAPI32!CryptSetProvParam` at `0x18005ae80`
- `CRYPT32!CryptMsgControl` at `0x18005ae97`
- `CRYPT32!CryptMsgControl` at `0x18005ae97`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ad3e`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ad5c`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ad3e`
- `CRYPT32!CertAddStoreToCollection` at `0x18005ad5c`
- `CRYPT32!CryptMsgGetParam` at `0x18005ac47`
- `CRYPT32!CryptMsgGetParam` at `0x18005acb9`
- `CRYPT32!CryptMsgGetParam` at `0x18005ac47`
- `CRYPT32!CryptMsgGetParam` at `0x18005acb9`
- `CRYPT32!CertOpenStore` at `0x18005ac70`
- `CRYPT32!CertOpenStore` at `0x18005acdf`
- `CRYPT32!CertOpenStore` at `0x18005ad10`
- `CRYPT32!CertOpenStore` at `0x18005ac70`
- `CRYPT32!CertOpenStore` at `0x18005acdf`
- `CRYPT32!CertOpenStore` at `0x18005ad10`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005acfe`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005acfe`
- `CRYPT32!CertFreeCertificateContext` at `0x18005af3d`
- `CRYPT32!CertFreeCertificateContext` at `0x18005af3d`
- `CRYPT32!CertCloseStore` at `0x18005af4d`
- `CRYPT32!CertCloseStore` at `0x18005af5d`
- `CRYPT32!CertCloseStore` at `0x18005af4d`
- `CRYPT32!CertCloseStore` at `0x18005af5d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005aed1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005aed1`
- `CRYPT32!CertDuplicateStore` at `0x18005ac86`
- `CRYPT32!CertDuplicateStore` at `0x18005ac86`

## pseudocode

```c
__int64 __fastcall CCAPIStm::HandleEnveloped(CCAPIStm *this)
{
  void *v3; // r15
  void *v4; // rcx
  HCERTSTORE v5; // rax
  void *v6; // rcx
  HCERTSTORE v7; // rax
  HCERTSTORE hCertStore; // rsi
  unsigned int j; // ebx
  int v10; // r12d
  unsigned int i; // r14d
  HWND v12; // rdx
  CCAPIStm *v13; // rcx
  int MsgParam; // ebx
  unsigned int v15; // r8d
  int v16; // eax
  const BYTE *v17; // r8
  PCCERT_CONTEXT v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // r8d
  struct _CMSG_CMS_RECIPIENT_INFO *v21; // [rsp+50h] [rbp-39h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-31h] BYREF
  _BYTE pvCtrlPara[8]; // [rsp+60h] [rbp-29h] BYREF
  HCRYPTPROV hProv; // [rsp+68h] [rbp-21h]
  DWORD dwCtrlType; // [rsp+F0h] [rbp+67h] BYREF
  DWORD pcbData; // [rsp+F8h] [rbp+6Fh] BYREF
  int pvData; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v28; // [rsp+108h] [rbp+7Fh] BYREF

  pcbData = 0;
  pvData = 0;
  v28 = 0;
  dwCtrlType = 0;
  pCertContext = 0;
  v21 = 0;
  memset_0(pvCtrlPara, 0, 0x40u);
  if ( (*((_BYTE *)this + 128) & 4) != 0 )
    return 2148323062LL;
  v3 = 0;
  v21 = (struct _CMSG_CMS_RECIPIENT_INFO *)PVGetMsgParam(*((_QWORD *)this + 3), 15, 0);
  if ( !v21 )
    goto LABEL_45;
  ((void (__fastcall *)(LPMALLOC, struct _CMSG_CMS_RECIPIENT_INFO *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v21);
  v4 = (void *)*((_QWORD *)this + 3);
  v21 = 0;
  pcbData = 4;
  if ( !CryptMsgGetParam(v4, 0xBu, 0, &pvData, &pcbData) )
    goto LABEL_45;
  if ( pvData )
  {
    v5 = CertOpenStore((LPCSTR)1, 1u, *((_QWORD *)this + 4), 0, *((const void **)this + 3));
    v3 = v5;
    if ( v5 )
    {
      *((_DWORD *)this + 16) |= 0x20000u;
      *(_QWORD *)(*((_QWORD *)this + 12) + 96LL) = CertDuplicateStore(v5);
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)this + 12) + 96LL) = 0;
    }
  }
  v6 = (void *)*((_QWORD *)this + 3);
  pcbData = 4;
  if ( CryptMsgGetParam(v6, 0x21u, 0, &v28, &pcbData) )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v7 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0);
      hCertStore = v7;
      if ( !v7 || !CertAddCertificateContextToStore(v7, *((PCCERT_CONTEXT *)this + 7), 4u, 0) )
        goto LABEL_46;
LABEL_19:
      v10 = 0;
      while ( 2 )
      {
        for ( i = 0; i < v28; ++i )
        {
          MsgParam = HrGetMsgParam(*((_QWORD *)this + 3), 36, i, &v21, 0);
          if ( MsgParam < 0 )
            goto LABEL_47;
          v16 = v10
              ? (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct _CMSG_CMS_RECIPIENT_INFO *, DWORD *, _BYTE *, PCCERT_CONTEXT *))(**((_QWORD **)this + 14) + 24LL))(
                  *((_QWORD *)this + 14),
                  *((_QWORD *)this + 15),
                  0,
                  i,
                  v21,
                  &dwCtrlType,
                  pvCtrlPara,
                  &pCertContext)
              : CCAPIStm::FindKeyFor(
                  v13,
                  v12,
                  v15,
                  i,
                  v21,
                  hCertStore,
                  &dwCtrlType,
                  (union tagCMS_CTRL_DECRYPT_INFO *)pvCtrlPara,
                  &pCertContext);
          MsgParam = v16;
          if ( v16 < 0 )
            goto LABEL_47;
          if ( !v16 )
          {
            v17 = (const BYTE *)*((_QWORD *)this + 17);
            if ( v17 && (dwCtrlType == 2 || dwCtrlType - 16 <= 1) )
              CryptSetProvParam(hProv, 0x15u, v17, 0);
            if ( CryptMsgControl(*((HCRYPTMSG *)this + 3), 0x8000u, dwCtrlType, pvCtrlPara) )
            {
              if ( pCertContext )
              {
                v18 = CertDuplicateCertificateContext(pCertContext);
                v19 = *((_QWORD *)this + 12);
                *(_QWORD *)(v19 + 128) = v18;
                if ( CertVerifyTimeValidityWithDelta((struct _FILETIME *)v19, pCertContext->pCertInfo, v20) )
                  *(_DWORD *)(*((_QWORD *)this + 12) + 104LL) |= 0x2000u;
              }
              MsgParam = 0;
            }
            else
            {
              MsgParam = HrGetLastError();
              if ( dwCtrlType == 2 || dwCtrlType - 16 <= 1 )
                CryptReleaseContext(hProv, 0);
            }
            goto LABEL_47;
          }
          ((void (__fastcall *)(LPMALLOC, struct _CMSG_CMS_RECIPIENT_INFO *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v21);
          v21 = 0;
        }
        if ( !v10 && *((_QWORD *)this + 14) )
        {
          v10 = 1;
          continue;
        }
        break;
      }
      MsgParam = -2147212268;
      *(_DWORD *)(*((_QWORD *)this + 12) + 104LL) = 4096;
      goto LABEL_47;
    }
    hCertStore = CertOpenStore((LPCSTR)0xB, 1u, 0, 0, 0);
    if ( hCertStore )
    {
      for ( j = 0; j < *((_DWORD *)this + 17); ++j )
        CertAddStoreToCollection(hCertStore, *(HCERTSTORE *)(*((_QWORD *)this + 9) + 8LL * j), 0, 0);
      if ( v3 )
        CertAddStoreToCollection(hCertStore, v3, 0, 0);
      goto LABEL_19;
    }
  }
  else
  {
LABEL_45:
    hCertStore = 0;
  }
LABEL_46:
  MsgParam = HrGetLastError();
LABEL_47:
  if ( v21 )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  CertFreeCertificateContext(pCertContext);
  if ( v3 )
    CertCloseStore(v3, 0);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( MsgParam < 0 && MsgParam != -2147212268 && MsgParam != -2147023673 && MsgParam != -2146889712 )
  {
    MsgParam = -2147212267;
    *(_DWORD *)(*((_QWORD *)this + 12) + 104LL) = 0x1000000;
  }
  return (unsigned int)MsgParam;
}

```

## disassembly

```asm
0x18005ab90  push    rbp
0x18005ab92  push    rbx
0x18005ab93  push    rsi
0x18005ab94  push    rdi
0x18005ab95  push    r12
0x18005ab97  push    r13
0x18005ab99  push    r14
0x18005ab9b  push    r15
0x18005ab9d  lea     rbp, [rsp-1Fh]
0x18005aba2  sub     rsp, 0A8h
0x18005aba9  xor     r13d, r13d
0x18005abac  mov     rdi, rcx
0x18005abaf  xor     edx, edx; Val
0x18005abb1  mov     [rbp+57h+arg_8], r13d
0x18005abb5  lea     rcx, [rbp+57h+pvCtrlPara]; void *
0x18005abb9  mov     [rbp+57h+pvData], r13d
0x18005abbd  mov     [rbp+57h+arg_18], r13d
0x18005abc1  lea     r8d, [r13+40h]; Size
0x18005abc5  mov     [rbp+57h+dwCtrlType], r13d
0x18005abc9  mov     [rbp+57h+pCertContext], r13
0x18005abcd  mov     [rbp+57h+var_90], r13
0x18005abd1  call    memset_0
0x18005abd6  lea     ebx, [r13+4]
0x18005abda  test    [rdi+80h], bl
0x18005abe0  jz      short loc_18005ABEC
0x18005abe2  mov     eax, 800CCEF6h
0x18005abe7  jmp     loc_18005AF91
0x18005abec  mov     rcx, [rdi+18h]
0x18005abf0  xor     r9d, r9d
0x18005abf3  xor     r8d, r8d
0x18005abf6  mov     r15, r13
0x18005abf9  lea     edx, [r9+0Fh]
0x18005abfd  call    cs:__imp_PVGetMsgParam
0x18005ac03  mov     [rbp+57h+var_90], rax
0x18005ac07  mov     rdx, rax
0x18005ac0a  test    rax, rax
0x18005ac0d  jz      loc_18005AF13
0x18005ac13  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005ac1a  mov     rax, [rcx]
0x18005ac1d  mov     rax, [rax+28h]
0x18005ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac26  mov     rcx, [rdi+18h]; hCryptMsg
0x18005ac2a  lea     rax, [rbp+57h+arg_8]
0x18005ac2e  xor     r8d, r8d; dwIndex
0x18005ac31  mov     [rbp+57h+var_90], r13
0x18005ac35  lea     r9, [rbp+57h+pvData]; pvData
0x18005ac39  mov     [rbp+57h+arg_8], ebx
0x18005ac3c  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18005ac41  lea     esi, [r8+0Bh]
0x18005ac45  mov     edx, esi; dwParamType
0x18005ac47  call    cs:__imp_CryptMsgGetParam
0x18005ac4d  test    eax, eax
0x18005ac4f  jz      loc_18005AF13
0x18005ac55  cmp     [rbp+57h+pvData], r13d
0x18005ac59  jbe     short loc_18005AC9E
0x18005ac5b  mov     rax, [rdi+18h]
0x18005ac5f  lea     edx, [rsi-0Ah]; dwEncodingType
0x18005ac62  mov     r8, [rdi+20h]; hCryptProv
0x18005ac66  mov     ecx, edx; lpszStoreProvider
0x18005ac68  xor     r9d, r9d; dwFlags
0x18005ac6b  mov     [rsp+0E0h+pcbData], rax; pvPara
0x18005ac70  call    cs:__imp_CertOpenStore
0x18005ac76  mov     r15, rax
0x18005ac79  test    rax, rax
0x18005ac7c  jz      short loc_18005AC96
0x18005ac7e  bts     dword ptr [rdi+40h], 11h
0x18005ac83  mov     rcx, rax; hCertStore
0x18005ac86  call    cs:__imp_CertDuplicateStore
0x18005ac8c  mov     rcx, [rdi+60h]
0x18005ac90  mov     [rcx+60h], rax
0x18005ac94  jmp     short loc_18005AC9E
0x18005ac96  mov     rax, [rdi+60h]
0x18005ac9a  mov     [rax+60h], r13
0x18005ac9e  mov     rcx, [rdi+18h]; hCryptMsg
0x18005aca2  lea     rax, [rbp+57h+arg_8]
0x18005aca6  xor     r8d, r8d; dwIndex
0x18005aca9  mov     [rbp+57h+arg_8], ebx
0x18005acac  lea     r9, [rbp+57h+arg_18]; pvData
0x18005acb0  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18005acb5  lea     edx, [r8+21h]; dwParamType
0x18005acb9  call    cs:__imp_CryptMsgGetParam
0x18005acbf  test    eax, eax
0x18005acc1  jz      loc_18005AF13
0x18005acc7  xor     r9d, r9d; dwFlags
0x18005acca  mov     [rsp+0E0h+pcbData], r13; pvPara
0x18005accf  xor     r8d, r8d; hCryptProv
0x18005acd2  lea     edx, [r9+1]; dwEncodingType
0x18005acd6  cmp     [rdi+38h], r13
0x18005acda  jz      short loc_18005AD0D
0x18005acdc  lea     ecx, [rdx+1]; lpszStoreProvider
0x18005acdf  call    cs:__imp_CertOpenStore
0x18005ace5  mov     rsi, rax
0x18005ace8  test    rax, rax
0x18005aceb  jz      loc_18005AF16
0x18005acf1  mov     rdx, [rdi+38h]; pCertContext
0x18005acf5  xor     r9d, r9d; ppStoreContext
0x18005acf8  mov     r8d, ebx; dwAddDisposition
0x18005acfb  mov     rcx, rax; hCertStore
0x18005acfe  call    cs:__imp_CertAddCertificateContextToStore
0x18005ad04  test    eax, eax
0x18005ad06  jnz     short loc_18005AD62
0x18005ad08  jmp     loc_18005AF16
0x18005ad0d  mov     rcx, rsi; lpszStoreProvider
0x18005ad10  call    cs:__imp_CertOpenStore
0x18005ad16  mov     rsi, rax
0x18005ad19  test    rax, rax
0x18005ad1c  jz      loc_18005AF16
0x18005ad22  mov     ebx, r13d
0x18005ad25  cmp     [rdi+44h], r13d
0x18005ad29  jbe     short loc_18005AD4B
0x18005ad2b  mov     rdx, [rdi+48h]
0x18005ad2f  xor     r9d, r9d; dwPriority
0x18005ad32  mov     eax, ebx
0x18005ad34  xor     r8d, r8d; dwUpdateFlags
0x18005ad37  mov     rcx, rsi; hCollectionStore
0x18005ad3a  mov     rdx, [rdx+rax*8]; hSiblingStore
0x18005ad3e  call    cs:__imp_CertAddStoreToCollection
0x18005ad44  inc     ebx
0x18005ad46  cmp     ebx, [rdi+44h]
0x18005ad49  jb      short loc_18005AD2B
0x18005ad4b  test    r15, r15
0x18005ad4e  jz      short loc_18005AD62
0x18005ad50  xor     r9d, r9d; dwPriority
0x18005ad53  xor     r8d, r8d; dwUpdateFlags
0x18005ad56  mov     rdx, r15; hSiblingStore
0x18005ad59  mov     rcx, rsi; hCollectionStore
0x18005ad5c  call    cs:__imp_CertAddStoreToCollection
0x18005ad62  mov     r12d, r13d
0x18005ad65  mov     r14d, r13d
0x18005ad68  cmp     r14d, [rbp+57h+arg_18]
0x18005ad6c  jnb     loc_18005AE39
0x18005ad72  mov     rcx, [rdi+18h]
0x18005ad76  lea     r9, [rbp+57h+var_90]
0x18005ad7a  mov     r8d, r14d
0x18005ad7d  mov     [rsp+0E0h+pcbData], r13
0x18005ad82  mov     edx, 24h ; '$'
0x18005ad87  call    cs:__imp_HrGetMsgParam
0x18005ad8d  mov     ebx, eax
0x18005ad8f  test    eax, eax
0x18005ad91  js      loc_18005AF1D
0x18005ad97  mov     r9d, r14d; unsigned int
0x18005ad9a  test    r12d, r12d
0x18005ad9d  jz      short loc_18005ADDC
0x18005ad9f  mov     rcx, [rdi+70h]
0x18005ada3  lea     rdx, [rbp+57h+pCertContext]
0x18005ada7  mov     [rsp+0E0h+var_A8], rdx
0x18005adac  xor     r8d, r8d
0x18005adaf  lea     rdx, [rbp+57h+pvCtrlPara]
0x18005adb3  mov     [rsp+0E0h+var_B0], rdx
0x18005adb8  lea     rdx, [rbp+57h+dwCtrlType]
0x18005adbc  mov     rax, [rcx]
0x18005adbf  mov     [rsp+0E0h+hCertStore], rdx
0x18005adc4  mov     rdx, [rbp+57h+var_90]
0x18005adc8  mov     [rsp+0E0h+pcbData], rdx
0x18005adcd  mov     rdx, [rdi+78h]
0x18005add1  mov     rax, [rax+18h]
0x18005add5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adda  jmp     short loc_18005AE0A
0x18005addc  lea     rax, [rbp+57h+pCertContext]
0x18005ade0  mov     [rsp+0E0h+var_A0], rax; struct _CERT_CONTEXT **
0x18005ade5  lea     rax, [rbp+57h+pvCtrlPara]
0x18005ade9  mov     [rsp+0E0h+var_A8], rax; union tagCMS_CTRL_DECRYPT_INFO *
0x18005adee  lea     rax, [rbp+57h+dwCtrlType]
0x18005adf2  mov     [rsp+0E0h+var_B0], rax; unsigned int *
0x18005adf7  mov     rax, [rbp+57h+var_90]
0x18005adfb  mov     [rsp+0E0h+hCertStore], rsi; hCertStore
0x18005ae00  mov     [rsp+0E0h+pcbData], rax; struct _CMSG_CMS_RECIPIENT_INFO *
0x18005ae05  call    ?FindKeyFor@CCAPIStm@@AEAAJPEAUHWND__@@KKPEBU_CMSG_CMS_RECIPIENT_INFO@@PEAXPEAKPEATtagCMS_CTRL_DECRYPT_INFO@@PEAPEBU_CERT_CONTEXT@@@Z; CCAPIStm::FindKeyFor(HWND__ *,ulong,ulong,_CMSG_CMS_RECIPIENT_INFO const *,void *,ulong *,tagCMS_CTRL_DECRYPT_INFO *,_CERT_CONTEXT const * *)
0x18005ae0a  mov     ebx, eax
0x18005ae0c  test    eax, eax
0x18005ae0e  js      loc_18005AF1D
0x18005ae14  jz      short loc_18005AE57
0x18005ae16  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005ae1d  mov     rdx, [rbp+57h+var_90]
0x18005ae21  mov     rax, [rcx]
0x18005ae24  mov     rax, [rax+28h]
0x18005ae28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae2d  inc     r14d
0x18005ae30  mov     [rbp+57h+var_90], r13
0x18005ae34  jmp     loc_18005AD68
0x18005ae39  test    r12d, r12d
0x18005ae3c  jnz     loc_18005AF01
0x18005ae42  cmp     [rdi+70h], r13
0x18005ae46  jz      loc_18005AF01
0x18005ae4c  mov     r12d, 1
0x18005ae52  jmp     loc_18005AD65
0x18005ae57  mov     r8, [rdi+88h]; pbData
0x18005ae5e  test    r8, r8
0x18005ae61  jz      short loc_18005AE86
0x18005ae63  mov     eax, [rbp+57h+dwCtrlType]
0x18005ae66  sub     eax, 2
0x18005ae69  jz      short loc_18005AE75
0x18005ae6b  sub     eax, 0Eh
0x18005ae6e  jz      short loc_18005AE75
0x18005ae70  cmp     eax, 1
0x18005ae73  jnz     short loc_18005AE86
0x18005ae75  mov     rcx, [rbp+57h+hProv]; hProv
0x18005ae79  xor     r9d, r9d; dwFlags
0x18005ae7c  lea     edx, [r9+15h]; dwParam
0x18005ae80  call    cs:__imp_CryptSetProvParam
0x18005ae86  mov     r8d, [rbp+57h+dwCtrlType]; dwCtrlType
0x18005ae8a  lea     r9, [rbp+57h+pvCtrlPara]; pvCtrlPara
0x18005ae8e  mov     rcx, [rdi+18h]; hCryptMsg
0x18005ae92  mov     edx, 8000h; dwFlags
0x18005ae97  call    cs:__imp_CryptMsgControl
0x18005ae9d  test    eax, eax
0x18005ae9f  jnz     short loc_18005AEC8
0x18005aea1  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005aea6  mov     ebx, eax
0x18005aea8  mov     eax, [rbp+57h+dwCtrlType]
0x18005aeab  sub     eax, 2
0x18005aeae  jz      short loc_18005AEBA
0x18005aeb0  sub     eax, 0Eh
0x18005aeb3  jz      short loc_18005AEBA
0x18005aeb5  cmp     eax, 1
0x18005aeb8  jnz     short loc_18005AF1D
0x18005aeba  mov     rcx, [rbp+57h+hProv]; hProv
0x18005aebe  xor     edx, edx; dwFlags
0x18005aec0  call    cs:__imp_CryptReleaseContext
0x18005aec6  jmp     short loc_18005AF1D
0x18005aec8  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x18005aecc  test    rcx, rcx
0x18005aecf  jz      short loc_18005AEFC
0x18005aed1  call    cs:__imp_CertDuplicateCertificateContext
0x18005aed7  mov     rcx, [rdi+60h]; struct _FILETIME *
0x18005aedb  mov     [rcx+80h], rax
0x18005aee2  mov     rdx, [rbp+57h+pCertContext]
0x18005aee6  mov     rdx, [rdx+18h]; struct _CERT_INFO *
0x18005aeea  call    ?CertVerifyTimeValidityWithDelta@@YAJPEAU_FILETIME@@PEAU_CERT_INFO@@K@Z; CertVerifyTimeValidityWithDelta(_FILETIME *,_CERT_INFO *,ulong)
0x18005aeef  test    eax, eax
0x18005aef1  jz      short loc_18005AEFC
0x18005aef3  mov     rax, [rdi+60h]
0x18005aef7  bts     dword ptr [rax+68h], 0Dh
0x18005aefc  mov     ebx, r13d
0x18005aeff  jmp     short loc_18005AF1D
0x18005af01  mov     rax, [rdi+60h]
0x18005af05  mov     ebx, 80042414h
0x18005af0a  mov     dword ptr [rax+68h], 1000h
0x18005af11  jmp     short loc_18005AF1D
0x18005af13  mov     rsi, r13
0x18005af16  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005af1b  mov     ebx, eax
0x18005af1d  mov     rdx, [rbp+57h+var_90]
0x18005af21  test    rdx, rdx
0x18005af24  jz      short loc_18005AF39
0x18005af26  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005af2d  mov     rax, [rcx]
0x18005af30  mov     rax, [rax+28h]
0x18005af34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af39  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x18005af3d  call    cs:__imp_CertFreeCertificateContext
0x18005af43  test    r15, r15
0x18005af46  jz      short loc_18005AF53
0x18005af48  xor     edx, edx; dwFlags
0x18005af4a  mov     rcx, r15; hCertStore
0x18005af4d  call    cs:__imp_CertCloseStore
0x18005af53  test    rsi, rsi
0x18005af56  jz      short loc_18005AF63
0x18005af58  xor     edx, edx; dwFlags
0x18005af5a  mov     rcx, rsi; hCertStore
0x18005af5d  call    cs:__imp_CertCloseStore
0x18005af63  test    ebx, ebx
0x18005af65  jns     short loc_18005AF8F
0x18005af67  cmp     ebx, 80042414h
0x18005af6d  jz      short loc_18005AF8F
0x18005af6f  cmp     ebx, 800704C7h
0x18005af75  jz      short loc_18005AF8F
0x18005af77  cmp     ebx, 80091010h
0x18005af7d  jz      short loc_18005AF8F
0x18005af7f  mov     rax, [rdi+60h]
0x18005af83  mov     ebx, 80042415h
0x18005af88  mov     dword ptr [rax+68h], 1000000h
0x18005af8f  mov     eax, ebx
0x18005af91  add     rsp, 0A8h
0x18005af98  pop     r15
0x18005af9a  pop     r14
0x18005af9c  pop     r13
0x18005af9e  pop     r12
0x18005afa0  pop     rdi
0x18005afa1  pop     rsi
0x18005afa2  pop     rbx
0x18005afa3  pop     rbp
0x18005afa4  retn
```
