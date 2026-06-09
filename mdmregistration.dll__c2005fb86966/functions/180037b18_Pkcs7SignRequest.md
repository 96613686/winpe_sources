# Pkcs7SignRequest

- ea: `0x180037b18`
- end: `0x180037f55`
- name: `Pkcs7SignRequest`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x180012f70`
- `0x1800141b0`
- `0x18001be08`
- `0x180037b18`
- `0x180041410`
- `0x180043124`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037d76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037d76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037ebb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037ebb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037d5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037d5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e1e`
- `CRYPT32!CertFreeCertificateContext` at `0x180037ecf`
- `CRYPT32!CertFreeCertificateContext` at `0x180037ecf`
- `CRYPT32!CryptMsgClose` at `0x180037f0f`
- `CRYPT32!CryptMsgClose` at `0x180037f0f`
- `CRYPT32!CryptMsgGetParam` at `0x180037e61`
- `CRYPT32!CryptMsgGetParam` at `0x180037e61`
- `CRYPT32!CryptMsgUpdate` at `0x180037e0e`
- `CRYPT32!CryptMsgUpdate` at `0x180037e0e`
- `CRYPT32!CryptMsgOpenToEncode` at `0x180037dc0`
- `CRYPT32!CryptMsgOpenToEncode` at `0x180037dc0`
- `CRYPT32!CryptMsgCalculateEncodedLength` at `0x180037ce4`
- `CRYPT32!CryptMsgCalculateEncodedLength` at `0x180037ce4`
- `CRYPT32!CertCloseStore` at `0x180037ee7`
- `CRYPT32!CertCloseStore` at `0x180037ee7`
- `ncrypt!NCryptFreeObject` at `0x180037efb`
- `ncrypt!NCryptFreeObject` at `0x180037efb`

## string_xrefs

- `0x180037e3a`: `CryptMsgUpdate`
- `0x180037df0`: `CryptMsgOpenToEncode`

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
  DWORD v17; // ebx
  HANDLE ProcessHeap; // rax
  HCRYPTMSG v19; // rax
  signed int v20; // eax
  signed int v21; // eax
  bool v22; // zf
  DWORD v23; // eax
  CEnrollmentLogger *Logger; // rax
  HANDLE v25; // rax
  unsigned int v26; // ebx
  int CertBasedOnContainer; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v30; // [rsp+38h] [rbp-C8h]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-C0h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pvMsgEncodeInfo; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+78h] [rbp-88h]
  BYTE *pbData; // [rsp+88h] [rbp-78h]
  _QWORD v38[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v40; // [rsp+B0h] [rbp-50h]
  _BYTE v41[24]; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int128 v43; // [rsp+E0h] [rbp-20h]
  __int128 v44; // [rsp+F0h] [rbp-10h]
  _OWORD v45[3]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v46[6]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v47; // [rsp+190h] [rbp+90h] BYREF

  v30 = a2;
  pbData = a1;
  CertBasedOnContainer = 0;
  hCertStore = 0;
  pCertContext = 0;
  v9 = 0;
  pcbData = 0;
  v10 = 0;
  DWORD1(v47) = 0;
  pvMsgEncodeInfo = 0;
  v35 = 0;
  v36 = 0;
  hObject = 0;
  v38[0] = "Pkcs7SignRequest";
  v38[1] = &CertBasedOnContainer;
  *a8 = 0;
  *a7 = 0;
  CertBasedOnContainer = FindCertBasedOnContainer(a3, 0, a6, &hCertStore, &pCertContext, &hObject);
  v11 = pCertContext;
  v12 = hObject;
  if ( CertBasedOnContainer < 0 )
  {
    v13 = L"FindCertBasedOnContainer";
    goto LABEL_23;
  }
  memset(&v45[1], 0, 24);
  memset_0(&v39, 0, 0x60u);
  LODWORD(v39) = 96;
  *((_QWORD *)&v39 + 1) = v11->pCertInfo;
  *(_QWORD *)&v40 = v12;
  DWORD2(v40) = 0;
  *(_QWORD *)v41 = a5;
  *(_OWORD *)&v41[8] = *(_OWORD *)((char *)&v45[1] + 8);
  v42 = 0;
  v46[0] = v39;
  v46[1] = v40;
  v46[2] = *(_OWORD *)v41;
  v46[3] = *(unsigned __int64 *)&v45[2];
  v46[4] = v43;
  v46[5] = v44;
  LODWORD(v47) = v11->cbCertEncoded;
  *((_QWORD *)&v47 + 1) = v11->pbCertEncoded;
  v45[0] = v47;
  *(_QWORD *)&v35 = 1;
  v36 = 0u;
  *(_QWORD *)&pvMsgEncodeInfo = 0x100000030LL;
  *((_QWORD *)&pvMsgEncodeInfo + 1) = v46;
  *((_QWORD *)&v35 + 1) = v45;
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
      McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, PrivateKeyNotFoundEvent, v16, 1, &v47);
    goto LABEL_23;
  }
  v17 = v14;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v17);
  if ( v9 )
  {
    v19 = CryptMsgOpenToEncode(0x10000u, 0, 2u, &pvMsgEncodeInfo, 0, 0);
    v10 = v19;
    if ( v19 )
    {
      if ( CryptMsgUpdate(v19, pbData, v30, 1) )
      {
        v13 = &String2;
        v22 = !CryptMsgGetParam(v10, 2u, 0, v9, &pcbData);
        v23 = pcbData;
        if ( v22 )
        {
          *a7 = 0;
        }
        else
        {
          *a7 = v9;
          v9 = 0;
        }
        *a8 = v23;
      }
      else
      {
        v21 = GetLastError();
        if ( v21 > 0 )
          v21 = (unsigned __int16)v21 | 0x80070000;
        CertBasedOnContainer = v21;
        v13 = L"CryptMsgUpdate";
      }
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      CertBasedOnContainer = v20;
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
  if ( v9 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v9);
  }
  if ( v11 )
    CertFreeCertificateContext(v11);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v12 )
    NCryptFreeObject(v12);
  if ( v10 )
    CryptMsgClose(v10);
  v26 = CertBasedOnContainer;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v38);
  return v26;
}

```

## disassembly

```asm
0x180037b18  mov     [rsp-8+arg_18], rbx
0x180037b1d  push    rbp
0x180037b1e  push    rsi
0x180037b1f  push    rdi
0x180037b20  push    r12
0x180037b22  push    r13
0x180037b24  push    r14
0x180037b26  push    r15
0x180037b28  lea     rbp, [rsp-0B0h]
0x180037b30  sub     rsp, 1B0h
0x180037b37  mov     rax, cs:__security_cookie
0x180037b3e  xor     rax, rsp
0x180037b41  mov     [rbp+0E0h+var_40], rax
0x180037b48  mov     rax, r8
0x180037b4b  mov     ebx, edx
0x180037b4d  mov     [rsp+1E0h+var_1A8], edx
0x180037b51  mov     [rbp+0E0h+pbData], rcx
0x180037b55  mov     r14, [rbp+0E0h+arg_30]
0x180037b5c  mov     r15, [rbp+0E0h+arg_38]
0x180037b63  xor     edx, edx; unsigned __int16 *
0x180037b65  mov     [rsp+1E0h+var_1B0], edx
0x180037b69  mov     [rsp+1E0h+hCertStore], rdx
0x180037b6e  mov     [rsp+1E0h+pCertContext], rdx
0x180037b73  mov     edi, edx
0x180037b75  mov     [rsp+1E0h+pcbData], edx
0x180037b79  mov     esi, edx
0x180037b7b  mov     dword ptr [rbp+0E0h+var_50+4], edx
0x180037b81  xorps   xmm0, xmm0
0x180037b84  movups  [rsp+1E0h+pvMsgEncodeInfo], xmm0
0x180037b89  movups  [rsp+1E0h+var_178], xmm0
0x180037b8e  movups  [rsp+1E0h+var_168], xmm0
0x180037b93  mov     [rsp+1E0h+hObject], rdx
0x180037b98  lea     rcx, aPkcs7signreque; "Pkcs7SignRequest"
0x180037b9f  mov     [rbp+0E0h+var_150], rcx
0x180037ba3  lea     rcx, [rsp+1E0h+var_1B0]
0x180037ba8  mov     [rbp+0E0h+var_148], rcx
0x180037bac  mov     [r15], edx
0x180037baf  mov     [r14], rdx
0x180037bb2  lea     rcx, [rsp+1E0h+hObject]
0x180037bb7  mov     qword ptr [rsp+1E0h+cbData], rcx; unsigned __int64 *
0x180037bbc  lea     rcx, [rsp+1E0h+pCertContext]
0x180037bc1  mov     [rsp+1E0h+pszInnerContentObjID], rcx; struct _CERT_CONTEXT **
0x180037bc6  lea     r9, [rsp+1E0h+hCertStore]; void **
0x180037bcb  mov     r8d, [rbp+0E0h+arg_28]; unsigned int
0x180037bd2  mov     rcx, rax; unsigned __int16 *
0x180037bd5  call    ?FindCertBasedOnContainer@@YAJPEBG0KPEAPEAXPEAPEBU_CERT_CONTEXT@@PEA_K@Z; FindCertBasedOnContainer(ushort const *,ushort const *,ulong,void * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x180037bda  mov     [rsp+1E0h+var_1B0], eax
0x180037bde  mov     r13, [rsp+1E0h+pCertContext]
0x180037be3  mov     r12, [rsp+1E0h+hObject]
0x180037be8  test    eax, eax
0x180037bea  jns     short loc_180037BF8
0x180037bec  lea     rbx, aFindcertbasedo_1; "FindCertBasedOnContainer"
0x180037bf3  jmp     loc_180037E86
0x180037bf8  xorps   xmm0, xmm0
0x180037bfb  xor     eax, eax
0x180037bfd  movups  [rbp+0E0h+var_D0], xmm0
0x180037c01  mov     [rbp+0E0h+var_C0], rax
0x180037c05  xor     edx, edx; Val
0x180037c07  lea     r8d, [rax+60h]; Size
0x180037c0b  lea     rcx, [rbp+0E0h+var_140]; void *
0x180037c0f  call    memset_0
0x180037c14  mov     dword ptr [rbp+0E0h+var_140], 60h ; '`'
0x180037c1b  mov     rax, [r13+18h]
0x180037c1f  mov     qword ptr [rbp+0E0h+var_140+8], rax
0x180037c23  mov     qword ptr [rbp+0E0h+var_130], r12
0x180037c27  xor     ecx, ecx
0x180037c29  mov     dword ptr [rbp+0E0h+var_130+8], ecx
0x180037c2c  mov     rax, [rbp+0E0h+arg_20]
0x180037c33  mov     qword ptr [rbp+0E0h+var_120], rax
0x180037c37  movups  xmm0, [rbp+0E0h+var_D0+8]
0x180037c3b  movdqu  xmmword ptr [rbp+0E0h+var_120+8], xmm0
0x180037c40  mov     [rbp+0E0h+var_108], rcx
0x180037c44  movaps  xmm1, [rbp+0E0h+var_140]
0x180037c48  movaps  [rbp+0E0h+var_B0], xmm1
0x180037c4c  movaps  xmm0, [rbp+0E0h+var_130]
0x180037c50  movaps  [rbp+0E0h+var_A0], xmm0
0x180037c54  movaps  xmm1, xmmword ptr [rbp+0E0h+var_120]
0x180037c58  movaps  [rbp+0E0h+var_90], xmm1
0x180037c5c  movaps  xmm0, xmmword ptr [rbp-30h]
0x180037c60  movaps  [rbp+0E0h+var_80], xmm0
0x180037c64  movaps  xmm1, [rbp+0E0h+var_100]
0x180037c68  movaps  [rbp+0E0h+var_70], xmm1
0x180037c6c  movaps  xmm0, [rbp+0E0h+var_F0]
0x180037c70  movaps  [rbp+0E0h+var_60], xmm0
0x180037c77  mov     eax, [r13+10h]
0x180037c7b  mov     dword ptr [rbp+0E0h+var_50], eax
0x180037c81  mov     rax, [r13+8]
0x180037c85  mov     qword ptr [rbp+0E0h+var_50+8], rax
0x180037c8c  movaps  xmm0, [rbp+0E0h+var_50]
0x180037c93  movdqa  [rbp+0E0h+var_E0], xmm0
0x180037c98  mov     qword ptr [rsp+1E0h+var_178], 1
0x180037ca1  mov     qword ptr [rsp+1E0h+var_168], rcx
0x180037ca6  mov     dword ptr [rsp+1E0h+pvMsgEncodeInfo], 30h ; '0'
0x180037cae  lea     edx, [rcx+1]
0x180037cb1  mov     dword ptr [rsp+1E0h+pvMsgEncodeInfo+4], edx
0x180037cb5  lea     rax, [rbp+0E0h+var_B0]
0x180037cb9  mov     qword ptr [rsp+1E0h+pvMsgEncodeInfo+8], rax
0x180037cbe  lea     rax, [rbp+0E0h+var_E0]
0x180037cc2  mov     qword ptr [rsp+1E0h+var_178+8], rax
0x180037cc7  mov     qword ptr [rbp+0E0h+var_168+8], rcx
0x180037ccb  mov     [rsp+1E0h+cbData], ebx; cbData
0x180037ccf  mov     [rsp+1E0h+pszInnerContentObjID], rcx; pszInnerContentObjID
0x180037cd4  lea     r9, [rsp+1E0h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x180037cd9  xor     edx, edx; dwFlags
0x180037cdb  mov     ecx, 10000h; dwMsgEncodingType
0x180037ce0  lea     r8d, [rdx+2]; dwMsgType
0x180037ce4  call    cs:__imp_CryptMsgCalculateEncodedLength
0x180037ceb  nop     dword ptr [rax+rax+00h]
0x180037cf0  mov     [rsp+1E0h+pcbData], eax
0x180037cf4  test    eax, eax
0x180037cf6  jnz     short loc_180037D5D
0x180037cf8  call    cs:__imp_GetLastError
0x180037cff  nop     dword ptr [rax+rax+00h]
0x180037d04  test    eax, eax
0x180037d06  jle     short loc_180037D10
0x180037d08  movzx   eax, ax
0x180037d0b  or      eax, 80070000h
0x180037d10  mov     [rsp+1E0h+var_1B0], eax
0x180037d14  lea     rbx, aCryptmsgcalcul_0; "CryptMsgCalculateEncodedLength"
0x180037d1b  cmp     eax, 80090016h
0x180037d20  jnz     loc_180037E86
0x180037d26  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x180037d2d  jz      loc_180037E86
0x180037d33  lea     rax, [rbp+0E0h+var_50]
0x180037d3a  mov     [rsp+1E0h+pszInnerContentObjID], rax
0x180037d3f  mov     r9d, 1
0x180037d45  lea     rdx, PrivateKeyNotFoundEvent
0x180037d4c  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180037d53  call    McGenEventWrite_EventWriteTransfer
0x180037d58  jmp     loc_180037E86
0x180037d5d  mov     ebx, eax
0x180037d5f  call    cs:__imp_GetProcessHeap
0x180037d66  nop     dword ptr [rax+rax+00h]
0x180037d6b  mov     rcx, rax; hHeap
0x180037d6e  mov     r8d, ebx; dwBytes
0x180037d71  mov     edx, 8; dwFlags
0x180037d76  call    cs:__imp_HeapAlloc
0x180037d7d  nop     dword ptr [rax+rax+00h]
0x180037d82  mov     rdi, rax
0x180037d85  test    rax, rax
0x180037d88  jnz     short loc_180037D9E
0x180037d8a  mov     [rsp+1E0h+var_1B0], 8007000Eh
0x180037d92  lea     rbx, aSafeheapallocC_0; "SafeHeapAlloc(cbSignedBlob)"
0x180037d99  jmp     loc_180037E8D
0x180037d9e  mov     qword ptr [rsp+1E0h+cbData], 0; pStreamInfo
0x180037da7  mov     [rsp+1E0h+pszInnerContentObjID], 0; pszInnerContentObjID
0x180037db0  lea     r9, [rsp+1E0h+pvMsgEncodeInfo]; pvMsgEncodeInfo
0x180037db5  xor     edx, edx; dwFlags
0x180037db7  mov     ecx, 10000h; dwMsgEncodingType
0x180037dbc  lea     r8d, [rdx+2]; dwMsgType
0x180037dc0  call    cs:__imp_CryptMsgOpenToEncode
0x180037dc7  nop     dword ptr [rax+rax+00h]
0x180037dcc  mov     rsi, rax
0x180037dcf  test    rax, rax
0x180037dd2  jnz     short loc_180037DFC
0x180037dd4  call    cs:__imp_GetLastError
0x180037ddb  nop     dword ptr [rax+rax+00h]
0x180037de0  test    eax, eax
0x180037de2  jle     short loc_180037DEC
0x180037de4  movzx   eax, ax
0x180037de7  or      eax, 80070000h
0x180037dec  mov     [rsp+1E0h+var_1B0], eax
0x180037df0  lea     rbx, aCryptmsgopento_0; "CryptMsgOpenToEncode"
0x180037df7  jmp     loc_180037E86
0x180037dfc  mov     r9d, 1; fFinal
0x180037e02  mov     r8d, [rsp+1E0h+var_1A8]; cbData
0x180037e07  mov     rdx, [rbp+0E0h+pbData]; pbData
0x180037e0b  mov     rcx, rsi; hCryptMsg
0x180037e0e  call    cs:__imp_CryptMsgUpdate
0x180037e15  nop     dword ptr [rax+rax+00h]
0x180037e1a  test    eax, eax
0x180037e1c  jnz     short loc_180037E43
0x180037e1e  call    cs:__imp_GetLastError
0x180037e25  nop     dword ptr [rax+rax+00h]
0x180037e2a  test    eax, eax
0x180037e2c  jle     short loc_180037E36
0x180037e2e  movzx   eax, ax
0x180037e31  or      eax, 80070000h
0x180037e36  mov     [rsp+1E0h+var_1B0], eax
0x180037e3a  lea     rbx, aCryptmsgupdate_0; "CryptMsgUpdate"
0x180037e41  jmp     short loc_180037E86
0x180037e43  lea     rbx, String2
0x180037e4a  lea     rax, [rsp+1E0h+pcbData]
0x180037e4f  mov     [rsp+1E0h+pszInnerContentObjID], rax; pcbData
0x180037e54  mov     r9, rdi; pvData
0x180037e57  xor     r8d, r8d; dwIndex
0x180037e5a  lea     edx, [r8+2]; dwParamType
0x180037e5e  mov     rcx, rsi; hCryptMsg
0x180037e61  call    cs:__imp_CryptMsgGetParam
0x180037e68  nop     dword ptr [rax+rax+00h]
0x180037e6d  test    eax, eax
0x180037e6f  mov     eax, [rsp+1E0h+pcbData]
0x180037e73  jz      short loc_180037E7C
0x180037e75  mov     [r14], rdi
0x180037e78  xor     edi, edi
0x180037e7a  jmp     short loc_180037E83
0x180037e7c  mov     qword ptr [r14], 0
0x180037e83  mov     [r15], eax
0x180037e86  cmp     [rsp+1E0h+var_1B0], 0
0x180037e8b  jge     short loc_180037EA2
0x180037e8d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180037e92  mov     r8d, [rsp+1E0h+var_1B0]; int
0x180037e97  mov     rdx, rbx; unsigned __int16 *
0x180037e9a  mov     rcx, rax; this
0x180037e9d  call    ?LogEnrollCertificateRenewPKCS7SignFailed@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogEnrollCertificateRenewPKCS7SignFailed(ushort const *,long)
0x180037ea2  test    rdi, rdi
0x180037ea5  jz      short loc_180037EC7
0x180037ea7  call    cs:__imp_GetProcessHeap
0x180037eae  nop     dword ptr [rax+rax+00h]
0x180037eb3  mov     rcx, rax; hHeap
0x180037eb6  mov     r8, rdi; lpMem
0x180037eb9  xor     edx, edx; dwFlags
0x180037ebb  call    cs:__imp_HeapFree
0x180037ec2  nop     dword ptr [rax+rax+00h]
0x180037ec7  test    r13, r13
0x180037eca  jz      short loc_180037EDB
0x180037ecc  mov     rcx, r13; pCertContext
0x180037ecf  call    cs:__imp_CertFreeCertificateContext
0x180037ed6  nop     dword ptr [rax+rax+00h]
0x180037edb  mov     rcx, [rsp+1E0h+hCertStore]; hCertStore
0x180037ee0  test    rcx, rcx
0x180037ee3  jz      short loc_180037EF3
0x180037ee5  xor     edx, edx; dwFlags
0x180037ee7  call    cs:__imp_CertCloseStore
0x180037eee  nop     dword ptr [rax+rax+00h]
0x180037ef3  test    r12, r12
0x180037ef6  jz      short loc_180037F07
0x180037ef8  mov     rcx, r12; hObject
0x180037efb  call    cs:__imp_NCryptFreeObject
0x180037f02  nop     dword ptr [rax+rax+00h]
0x180037f07  test    rsi, rsi
0x180037f0a  jz      short loc_180037F1B
0x180037f0c  mov     rcx, rsi; hCryptMsg
0x180037f0f  call    cs:__imp_CryptMsgClose
0x180037f16  nop     dword ptr [rax+rax+00h]
0x180037f1b  mov     ebx, [rsp+1E0h+var_1B0]
0x180037f1f  lea     rcx, [rbp+0E0h+var_150]; this
0x180037f23  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180037f28  mov     eax, ebx
0x180037f2a  mov     rcx, [rbp+0E0h+var_40]
0x180037f31  xor     rcx, rsp; StackCookie
0x180037f34  call    __security_check_cookie
0x180037f39  mov     rbx, [rsp+1E0h+arg_18]
0x180037f41  add     rsp, 1B0h
0x180037f48  pop     r15
0x180037f4a  pop     r14
0x180037f4c  pop     r13
0x180037f4e  pop     r12
0x180037f50  pop     rdi
0x180037f51  pop     rsi
0x180037f52  pop     rbp
0x180037f53  retn
```
