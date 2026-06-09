# Pkcs7SignRequest

- ea: `0x18002d9d0`
- end: `0x18002dd8e`
- name: `Pkcs7SignRequest`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x1800140d0`
- `0x180014148`
- `0x18001aec8`
- `0x18001decc`
- `0x1800206a8`
- `0x18002d9d0`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18003b068`
- `0x1800719b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc99`
- `CRYPT32!CertCloseStore` at `0x18002dd33`
- `CRYPT32!CertCloseStore` at `0x18002dd33`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd21`
- `CRYPT32!CertFreeCertificateContext` at `0x18002dd21`
- `CRYPT32!CryptMsgCalculateEncodedLength` at `0x18002dba0`
- `CRYPT32!CryptMsgCalculateEncodedLength` at `0x18002dba0`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18002dc52`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18002dc52`
- `CRYPT32!CryptMsgUpdate` at `0x18002dc8f`
- `CRYPT32!CryptMsgUpdate` at `0x18002dc8f`
- `CRYPT32!CryptMsgGetParam` at `0x18002dcd6`
- `CRYPT32!CryptMsgGetParam` at `0x18002dcd6`
- `CRYPT32!CryptMsgClose` at `0x18002dd4f`
- `CRYPT32!CryptMsgClose` at `0x18002dd4f`
- `ncrypt!NCryptFreeObject` at `0x18002dd41`
- `ncrypt!NCryptFreeObject` at `0x18002dd41`

## string_xrefs

- `0x18002dc76`: `CryptMsgOpenToEncode`
- `0x18002dcaf`: `CryptMsgUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Pkcs7SignRequest(
        BYTE *a1,
        DWORD a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7,
        DWORD *a8)
{
  void *v9; // rdi
  void *v10; // rsi
  PCCERT_CONTEXT v11; // r13
  NCRYPT_HANDLE v12; // r12
  const unsigned __int16 *v13; // rbx
  DWORD v14; // eax
  signed int LastError; // eax
  __int64 v16; // r8
  HCRYPTMSG v17; // rax
  signed int v18; // eax
  signed int v19; // eax
  bool v20; // zf
  DWORD v21; // eax
  CEnrollmentLogger *Logger; // rax
  __int64 v23; // rdx
  unsigned int v24; // ebx
  int CertBasedOnContainer; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-CCh] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-C8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pvMsgEncodeInfo; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  BYTE *pbData; // [rsp+80h] [rbp-80h]
  _QWORD v35[3]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h]
  _BYTE v38[24]; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int128 v40; // [rsp+E0h] [rbp-20h]
  __int128 v41; // [rsp+F0h] [rbp-10h]
  _OWORD v42[3]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v43[6]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v44; // [rsp+190h] [rbp+90h] BYREF

  pbData = a1;
  CertBasedOnContainer = 0;
  hCertStore = 0;
  pCertContext = 0;
  v9 = 0;
  pcbData = 0;
  v10 = 0;
  DWORD1(v44) = 0;
  pvMsgEncodeInfo = 0;
  v32 = 0;
  v33 = 0;
  hObject = 0;
  v35[0] = "Pkcs7SignRequest";
  v35[1] = &CertBasedOnContainer;
  *a8 = 0;
  *a7 = 0;
  CertBasedOnContainer = FindCertBasedOnContainer(
                           a3,
                           L"Microsoft Software Key Storage Provider",
                           a6,
                           &hCertStore,
                           &pCertContext,
                           &hObject);
  v11 = pCertContext;
  v12 = hObject;
  if ( CertBasedOnContainer < 0 )
  {
    v13 = L"FindCertBasedOnContainer";
    goto LABEL_23;
  }
  memset(&v42[1], 0, 24);
  memset_0(&v36, 0, 0x60u);
  LODWORD(v36) = 96;
  *((_QWORD *)&v36 + 1) = v11->pCertInfo;
  *(_QWORD *)&v37 = v12;
  DWORD2(v37) = 0;
  *(_QWORD *)v38 = a5;
  *(_OWORD *)&v38[8] = *(_OWORD *)((char *)&v42[1] + 8);
  v39 = 0;
  v43[0] = v36;
  v43[1] = v37;
  v43[2] = *(_OWORD *)v38;
  v43[3] = *(unsigned __int64 *)&v42[2];
  v43[4] = v40;
  v43[5] = v41;
  LODWORD(v44) = v11->cbCertEncoded;
  *((_QWORD *)&v44 + 1) = v11->pbCertEncoded;
  v42[0] = v44;
  *(_QWORD *)&v32 = 1;
  v33 = 0u;
  *(_QWORD *)&pvMsgEncodeInfo = 0x100000030LL;
  *((_QWORD *)&pvMsgEncodeInfo + 1) = v43;
  *((_QWORD *)&v32 + 1) = v42;
  v14 = CryptMsgCalculateEncodedLength(0x10000u, 0, 2u, &pvMsgEncodeInfo, 0, a2);
  pcbData = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CertBasedOnContainer = LastError;
    v13 = L"CryptMsgCalculateEncodedLength";
    if ( LastError == -2146893802 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, PrivateKeyNotFoundEvent, v16, 1, &v44);
    goto LABEL_23;
  }
  v9 = SafeHeapAlloc(v14);
  if ( v9 )
  {
    v17 = CryptMsgOpenToEncode(0x10000u, 0, 2u, &pvMsgEncodeInfo, 0, 0);
    v10 = v17;
    if ( v17 )
    {
      if ( CryptMsgUpdate(v17, pbData, a2, 1) )
      {
        v13 = &wszURI;
        v20 = !CryptMsgGetParam(v10, 2u, 0, v9, &pcbData);
        v21 = pcbData;
        if ( v20 )
        {
          *a7 = 0;
        }
        else
        {
          *a7 = v9;
          v9 = 0;
        }
        *a8 = v21;
      }
      else
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        CertBasedOnContainer = v19;
        v13 = L"CryptMsgUpdate";
      }
    }
    else
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      CertBasedOnContainer = v18;
      v13 = L"CryptMsgOpenToEncode";
    }
LABEL_23:
    if ( CertBasedOnContainer >= 0 )
      goto LABEL_25;
    goto LABEL_24;
  }
  CertBasedOnContainer = -2147024882;
  v13 = L"SafeHeapAlloc(cbSignedBlob)";
LABEL_24:
  Logger = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogEnrollCertificateRenewPKCS7SignFailed(Logger, v13, CertBasedOnContainer);
LABEL_25:
  SafeHeapFree(v9);
  if ( v11 )
    CertFreeCertificateContext(v11);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v12 )
    NCryptFreeObject(v12);
  if ( v10 )
    CryptMsgClose(v10);
  v24 = CertBasedOnContainer;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v35, v23);
  return v24;
}

```

## disassembly

```asm
0x18002d9d0  mov     [rsp-8+arg_18], rbx
0x18002d9d5  push    rbp
0x18002d9d6  push    rsi
0x18002d9d7  push    rdi
0x18002d9d8  push    r12
0x18002d9da  push    r13
0x18002d9dc  push    r14
0x18002d9de  push    r15
0x18002d9e0  lea     rbp, [rsp-0B0h]
0x18002d9e8  sub     rsp, 1B0h
0x18002d9ef  mov     rax, cs:__security_cookie
0x18002d9f6  xor     rax, rsp
0x18002d9f9  mov     [rbp+0E0h+var_40], rax
0x18002da00  mov     rax, r8
0x18002da03  mov     ebx, edx
0x18002da05  mov     [rbp+0E0h+pbData], rcx
0x18002da09  mov     r14, [rbp+0E0h+arg_30]
0x18002da10  mov     r15, [rbp+0E0h+arg_38]
0x18002da17  xor     edx, edx
0x18002da19  mov     [rsp+1E0h+var_1B0], edx
0x18002da1d  mov     [rsp+1E0h+hCertStore], rdx
0x18002da22  mov     [rsp+1E0h+pCertContext], rdx
0x18002da27  mov     edi, edx
0x18002da29  mov     [rsp+1E0h+pcbData], edx
0x18002da2d  mov     esi, edx
0x18002da2f  mov     dword ptr [rbp+0E0h+var_50+4], edx
0x18002da35  xorps   xmm0, xmm0
0x18002da38  movups  [rsp+1E0h+pvMsgEncodeInfo], xmm0
0x18002da3d  movups  [rsp+1E0h+var_180], xmm0
0x18002da42  movups  [rsp+1E0h+var_170], xmm0
0x18002da47  mov     [rsp+1E0h+hObject], rdx
0x18002da4c  lea     rcx, aPkcs7signreque; "Pkcs7SignRequest"
0x18002da53  mov     [rbp+0E0h+var_158], rcx
0x18002da57  lea     rcx, [rsp+1E0h+var_1B0]
0x18002da5c  mov     [rbp+0E0h+var_150], rcx
0x18002da60  mov     [r15], edx
0x18002da63  mov     [r14], rdx
0x18002da66  lea     rcx, [rsp+1E0h+hObject]
0x18002da6b  mov     qword ptr [rsp+1E0h+cbData], rcx; unsigned __int64 *
0x18002da70  lea     rcx, [rsp+1E0h+pCertContext]
0x18002da75  mov     [rsp+1E0h+pszInnerContentObjID], rcx; struct _CERT_CONTEXT **
0x18002da7a  lea     r9, [rsp+1E0h+hCertStore]; void **
0x18002da7f  mov     r8d, [rbp+0E0h+arg_28]; unsigned int
0x18002da86  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18002da8d  mov     rcx, rax; unsigned __int16 *
0x18002da90  call    ?FindCertBasedOnContainer@@YAJPEBG0KPEAPEAXPEAPEBU_CERT_CONTEXT@@PEA_K@Z; FindCertBasedOnContainer(ushort const *,ushort const *,ulong,void * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x18002da95  mov     [rsp+1E0h+var_1B0], eax
0x18002da99  mov     r13, [rsp+1E0h+pCertContext]
0x18002da9e  mov     r12, [rsp+1E0h+hObject]
0x18002daa3  test    eax, eax
0x18002daa5  jns     short loc_18002DAB3
0x18002daa7  lea     rbx, aFindcertbasedo_1; "FindCertBasedOnContainer"
0x18002daae  jmp     loc_18002DCF5
0x18002dab3  xorps   xmm0, xmm0
0x18002dab6  xor     eax, eax
0x18002dab8  movups  [rbp+0E0h+var_D0], xmm0
0x18002dabc  mov     [rbp+0E0h+var_C0], rax
0x18002dac0  xor     edx, edx; Val
0x18002dac2  lea     r8d, [rax+60h]; Size
0x18002dac6  lea     rcx, [rbp+0E0h+var_140]; void *
0x18002daca  call    memset_0
0x18002dacf  mov     dword ptr [rbp+0E0h+var_140], 60h ; '`'
0x18002dad6  mov     rax, [r13+18h]
0x18002dada  mov     qword ptr [rbp+0E0h+var_140+8], rax
0x18002dade  mov     qword ptr [rbp+0E0h+var_130], r12
0x18002dae2  xor     ecx, ecx
0x18002dae4  mov     dword ptr [rbp+0E0h+var_130+8], ecx
0x18002dae7  mov     rax, [rbp+0E0h+arg_20]
0x18002daee  mov     qword ptr [rbp+0E0h+var_120], rax
0x18002daf2  movups  xmm0, [rbp+0E0h+var_D0+8]
0x18002daf6  movdqu  xmmword ptr [rbp+0E0h+var_120+8], xmm0
0x18002dafb  mov     [rbp+0E0h+var_108], rcx
0x18002daff  movaps  xmm1, [rbp+0E0h+var_140]
0x18002db03  movaps  [rbp+0E0h+var_B0], xmm1
0x18002db07  movaps  xmm0, [rbp+0E0h+var_130]
0x18002db0b  movaps  [rbp+0E0h+var_A0], xmm0
0x18002db0f  movaps  xmm1, xmmword ptr [rbp+0E0h+var_120]
0x18002db13  movaps  [rbp+0E0h+var_90], xmm1
0x18002db17  movaps  xmm0, xmmword ptr [rbp-30h]
0x18002db1b  movaps  [rbp+0E0h+var_80], xmm0
0x18002db1f  movaps  xmm1, [rbp+0E0h+var_100]
0x18002db23  movaps  [rbp+0E0h+var_70], xmm1
0x18002db27  movaps  xmm0, [rbp+0E0h+var_F0]
0x18002db2b  movaps  [rbp+0E0h+var_60], xmm0
0x18002db32  mov     eax, [r13+10h]
0x18002db36  mov     dword ptr [rbp+0E0h+var_50], eax
0x18002db3c  mov     rax, [r13+8]
0x18002db40  mov     qword ptr [rbp+0E0h+var_50+8], rax
0x18002db47  movaps  xmm0, [rbp+0E0h+var_50]
0x18002db4e  movdqa  [rbp+0E0h+var_E0], xmm0
0x18002db53  mov     qword ptr [rsp+1E0h+var_180], 1
0x18002db5c  mov     qword ptr [rsp+1E0h+var_170], rcx
0x18002db61  mov     dword ptr [rsp+1E0h+pvMsgEncodeInfo], 30h ; '0'
0x18002db69  lea     edx, [rcx+1]
0x18002db6c  mov     dword ptr [rsp+1E0h+pvMsgEncodeInfo+4], edx
0x18002db70  lea     rax, [rbp+0E0h+var_B0]
0x18002db74  mov     qword ptr [rsp+1E0h+pvMsgEncodeInfo+8], rax
0x18002db79  lea     rax, [rbp+0E0h+var_E0]
0x18002db7d  mov     qword ptr [rsp+1E0h+var_180+8], rax
0x18002db82  mov     qword ptr [rsp+1E0h+var_170+8], rcx
0x18002db87  mov     [rsp+1E0h+cbData], ebx; cbData
0x18002db8b  mov     [rsp+1E0h+pszInnerContentObjID], rcx; pszInnerContentObjID
0x18002db90  lea     r9, [rsp+1E0h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x18002db95  xor     edx, edx; dwFlags
0x18002db97  mov     ecx, 10000h; dwMsgEncodingType
0x18002db9c  lea     r8d, [rdx+2]; dwMsgType
0x18002dba0  call    cs:__imp_CryptMsgCalculateEncodedLength
0x18002dba6  mov     [rsp+1E0h+pcbData], eax
0x18002dbaa  test    eax, eax
0x18002dbac  jnz     short loc_18002DC0D
0x18002dbae  call    cs:__imp_GetLastError
0x18002dbb4  test    eax, eax
0x18002dbb6  jle     short loc_18002DBC0
0x18002dbb8  movzx   eax, ax
0x18002dbbb  or      eax, 80070000h
0x18002dbc0  mov     [rsp+1E0h+var_1B0], eax
0x18002dbc4  lea     rbx, aCryptmsgcalcul_0; "CryptMsgCalculateEncodedLength"
0x18002dbcb  cmp     eax, 80090016h
0x18002dbd0  jnz     loc_18002DCF5
0x18002dbd6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002dbdd  jz      loc_18002DCF5
0x18002dbe3  lea     rax, [rbp+0E0h+var_50]
0x18002dbea  mov     [rsp+1E0h+pszInnerContentObjID], rax
0x18002dbef  mov     r9d, 1
0x18002dbf5  lea     rdx, PrivateKeyNotFoundEvent
0x18002dbfc  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002dc03  call    McGenEventWrite_EventWriteTransfer
0x18002dc08  jmp     loc_18002DCF5
0x18002dc0d  mov     ecx, eax; unsigned __int64
0x18002dc0f  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18002dc14  mov     rdi, rax
0x18002dc17  test    rax, rax
0x18002dc1a  jnz     short loc_18002DC30
0x18002dc1c  mov     [rsp+1E0h+var_1B0], 8007000Eh
0x18002dc24  lea     rbx, aSafeheapallocC_0; "SafeHeapAlloc(cbSignedBlob)"
0x18002dc2b  jmp     loc_18002DCFC
0x18002dc30  mov     qword ptr [rsp+1E0h+cbData], 0; pStreamInfo
0x18002dc39  mov     [rsp+1E0h+pszInnerContentObjID], 0; pszInnerContentObjID
0x18002dc42  lea     r9, [rsp+1E0h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x18002dc47  xor     edx, edx; dwFlags
0x18002dc49  mov     ecx, 10000h; dwMsgEncodingType
0x18002dc4e  lea     r8d, [rdx+2]; dwMsgType
0x18002dc52  call    cs:__imp_CryptMsgOpenToEncode
0x18002dc58  mov     rsi, rax
0x18002dc5b  test    rax, rax
0x18002dc5e  jnz     short loc_18002DC7F
0x18002dc60  call    cs:__imp_GetLastError
0x18002dc66  test    eax, eax
0x18002dc68  jle     short loc_18002DC72
0x18002dc6a  movzx   eax, ax
0x18002dc6d  or      eax, 80070000h
0x18002dc72  mov     [rsp+1E0h+var_1B0], eax
0x18002dc76  lea     rbx, aCryptmsgopento_0; "CryptMsgOpenToEncode"
0x18002dc7d  jmp     short loc_18002DCF5
0x18002dc7f  mov     r9d, 1; fFinal
0x18002dc85  mov     r8d, ebx; cbData
0x18002dc88  mov     rdx, [rbp+0E0h+pbData]; pbData
0x18002dc8c  mov     rcx, rsi; hCryptMsg
0x18002dc8f  call    cs:__imp_CryptMsgUpdate
0x18002dc95  test    eax, eax
0x18002dc97  jnz     short loc_18002DCB8
0x18002dc99  call    cs:__imp_GetLastError
0x18002dc9f  test    eax, eax
0x18002dca1  jle     short loc_18002DCAB
0x18002dca3  movzx   eax, ax
0x18002dca6  or      eax, 80070000h
0x18002dcab  mov     [rsp+1E0h+var_1B0], eax
0x18002dcaf  lea     rbx, aCryptmsgupdate_0; "CryptMsgUpdate"
0x18002dcb6  jmp     short loc_18002DCF5
0x18002dcb8  lea     rbx, wszURI
0x18002dcbf  lea     rax, [rsp+1E0h+pcbData]
0x18002dcc4  mov     [rsp+1E0h+pszInnerContentObjID], rax; pcbData
0x18002dcc9  mov     r9, rdi; pvData
0x18002dccc  xor     r8d, r8d; dwIndex
0x18002dccf  lea     edx, [r8+2]; dwParamType
0x18002dcd3  mov     rcx, rsi; hCryptMsg
0x18002dcd6  call    cs:__imp_CryptMsgGetParam
0x18002dcdc  test    eax, eax
0x18002dcde  mov     eax, [rsp+1E0h+pcbData]
0x18002dce2  jz      short loc_18002DCEB
0x18002dce4  mov     [r14], rdi
0x18002dce7  xor     edi, edi
0x18002dce9  jmp     short loc_18002DCF2
0x18002dceb  mov     qword ptr [r14], 0
0x18002dcf2  mov     [r15], eax
0x18002dcf5  cmp     [rsp+1E0h+var_1B0], 0
0x18002dcfa  jge     short loc_18002DD11
0x18002dcfc  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002dd01  mov     r8d, [rsp+1E0h+var_1B0]; int
0x18002dd06  mov     rdx, rbx; unsigned __int16 *
0x18002dd09  mov     rcx, rax; this
0x18002dd0c  call    ?LogEnrollCertificateRenewPKCS7SignFailed@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogEnrollCertificateRenewPKCS7SignFailed(ushort const *,long)
0x18002dd11  mov     rcx, rdi; void *
0x18002dd14  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18002dd19  test    r13, r13
0x18002dd1c  jz      short loc_18002DD27
0x18002dd1e  mov     rcx, r13; pCertContext
0x18002dd21  call    cs:__imp_CertFreeCertificateContext
0x18002dd27  mov     rcx, [rsp+1E0h+hCertStore]; hCertStore
0x18002dd2c  test    rcx, rcx
0x18002dd2f  jz      short loc_18002DD39
0x18002dd31  xor     edx, edx; dwFlags
0x18002dd33  call    cs:__imp_CertCloseStore
0x18002dd39  test    r12, r12
0x18002dd3c  jz      short loc_18002DD47
0x18002dd3e  mov     rcx, r12; hObject
0x18002dd41  call    cs:__imp_NCryptFreeObject
0x18002dd47  test    rsi, rsi
0x18002dd4a  jz      short loc_18002DD55
0x18002dd4c  mov     rcx, rsi; hCryptMsg
0x18002dd4f  call    cs:__imp_CryptMsgClose
0x18002dd55  mov     ebx, [rsp+1E0h+var_1B0]
0x18002dd59  lea     rcx, [rbp+0E0h+var_158]; this
0x18002dd5d  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002dd62  mov     eax, ebx
0x18002dd64  mov     rcx, [rbp+0E0h+var_40]
0x18002dd6b  xor     rcx, rsp; StackCookie
0x18002dd6e  call    __security_check_cookie
0x18002dd73  mov     rbx, [rsp+1E0h+arg_18]
0x18002dd7b  add     rsp, 1B0h
0x18002dd82  pop     r15
0x18002dd84  pop     r14
0x18002dd86  pop     r13
0x18002dd88  pop     r12
0x18002dd8a  pop     rdi
0x18002dd8b  pop     rsi
0x18002dd8c  pop     rbp
0x18002dd8d  retn
```
