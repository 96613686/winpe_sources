# CertifyGroupIdentity(_DRM_CRYPTO_VERSION_PARAMETERS const *,uint,ushort *,ushort *,ushort *,void *,long (*)(_DRM_STATUS_MSG,long,void *,void *),void *,ushort * *,ushort * *,ushort * *)

- ea: `0x18002c390`
- end: `0x18002c750`
- name: `?CertifyGroupIdentity@@YAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@IPEAG11PEAXP6AJW4_DRM_STATUS_MSG@@J22@Z2PEAPEAG55@Z`
- size: `960`
- prototype: `__int64 __usercall@<rax>(const struct _DRM_CRYPTO_VERSION_PARAMETERS *@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, wchar_t *String1, HANDLE hHandle, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), void *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18002cb38`

## callees

- `0x180001284`
- `0x1800046c8`
- `0x18002c390`
- `0x18002c758`
- `0x18002c7ec`
- `0x18002d178`
- `0x180036b9c`
- `0x1800472d4`
- `0x180047678`
- `0x1800476f0`
- `0x180049250`
- `0x18004a92c`
- `0x18004aa40`
- `0x18004b218`
- `0x18005bd8a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c42a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c4d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c517`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c6ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c42a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c4d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c517`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c6ca`

## string_xrefs

- `0x18002c592`: `System.UnauthorizedAccessException`
- `0x18002c662`: `Microsoft.RightsManagementServices.Online.Exceptions.CrossTenantCertificationDisabledException`
- `0x18002c644`: `Microsoft.DigitalRightsManagement.Certification.TemporaryDrmacException`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CertifyGroupIdentity(
        const struct _DRM_CRYPTO_VERSION_PARAMETERS *a1,
        char a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        wchar_t *String1,
        HANDLE hHandle,
        int (*a7)(enum _DRM_STATUS_MSG, int, void *, void *),
        void *a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10,
        unsigned __int16 **a11)
{
  unsigned __int16 *v14; // r15
  unsigned __int16 *v15; // r12
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r10
  int CertificationRequest; // ebx
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // edx
  unsigned __int16 *v25; // r8
  unsigned __int16 *v26; // r9
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v30; // [rsp+60h] [rbp-A0h] BYREF
  void *Block[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[8]; // [rsp+80h] [rbp-80h] BYREF
  int (*v33)(enum _DRM_STATUS_MSG, int, void *, void *); // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  void *v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+A8h] [rbp-58h]
  HANDLE v37; // [rsp+D0h] [rbp-30h]
  int v38; // [rsp+110h] [rbp+10h]

  Block[1] = (void *)-2LL;
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v32);
  v14 = 0;
  v30 = 0;
  v15 = 0;
  v29 = 0;
  v28 = 0;
  Block[0] = 0;
  v33 = a7;
  v34 = 1;
  v35 = a8;
  v37 = hHandle;
  CertificationRequest = CHttpBase::SetServerInfo((CHttpBase *)v32, v17, 0, v16);
  if ( CertificationRequest < 0 )
    goto LABEL_47;
  if ( !WaitForSingleObject(hHandle, 0) )
  {
    CertificationRequest = -2147168447;
    goto LABEL_47;
  }
  GetPersistedLicenseEx(1, v19, 0, 0, 0, &v28, 0, Block);
  v20 = v38;
  if ( v28 )
    v20 = 1;
  v38 = v20;
  if ( !wcscmp_0(String1, L"PassportAuthProvider") )
  {
    v36 = 32;
  }
  else if ( !wcscmp_0(String1, L"WindowsAuthProvider") )
  {
    if ( (a2 & 4) != 0 )
    {
      v36 = 8;
    }
    else
    {
      v21 = v36;
      if ( (a2 & 0x10) != 0 )
        v21 = 16;
      v36 = v21;
    }
  }
  if ( !WaitForSingleObject(hHandle, 0) )
    goto LABEL_15;
  CertificationRequest = GenerateCertificationRequest(a1, (struct CDRMSoapRequest *)v32, a2 & 0xFE, a4, String1);
  if ( CertificationRequest >= 0 )
  {
    if ( WaitForSingleObject(hHandle, 0) )
    {
      v22 = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v32, 0, 0);
      CertificationRequest = v22;
      if ( v22 == -2147168300 )
      {
        CDRMSoapRequest::GetFaultCode((CDRMSoapRequest *)v32, &v30);
        CDRMSoapRequest::GetFaultString((CDRMSoapRequest *)v32, &v29);
        v15 = v29;
        v14 = v30;
        _RTLTRACE("[msdrm]: CertifyGroupIdentity  FaultCode = %S , FaultString = %S ", v30, v29);
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Cryptography.UnsupportedCryptographicSetException") )
        {
          CertificationRequest = -2147168492;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType((CDRMSoapRequest *)v32, L"System.UnauthorizedAccessException")
          || CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Certification.MismatchedIdentificationEmailAddressException") )
        {
          CertificationRequest = -2147168445;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Core.VerifyEmailAddressFailedException") )
        {
          CertificationRequest = -2147168437;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Activation.EmailAddressNotVerified") )
        {
          CertificationRequest = -2147168422;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Utilities.ADEntrySearchFailedException") )
        {
          CertificationRequest = -2147168419;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Core.VerifyMachineCertificateChainFailedException")
          || CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Licensing.BlackBoxIsInvalidException") )
        {
          CertificationRequest = -2147168451;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.DigitalRightsManagement.Certification.TemporaryDrmacException") )
        {
          CertificationRequest = -2147168417;
          goto LABEL_45;
        }
        if ( CDRMSoapRequest::IsExceptionType(
               (CDRMSoapRequest *)v32,
               L"Microsoft.RightsManagementServices.Online.Exceptions.CrossTenantCertificationDisabledException") )
        {
          DisplayIppOnlineError((const unsigned __int16 *)0x1776, a2 & 0x10);
          CertificationRequest = -2147168444;
          goto LABEL_45;
        }
        v23 = -2147168444;
        if ( *(_DWORD *)a1 > 0x400u )
          v23 = -2147168492;
        goto LABEL_44;
      }
      if ( v22 < 0 )
      {
        _RTLTRACE("[msdrm]: FAILED : %x ", v22);
        goto LABEL_45;
      }
      if ( WaitForSingleObject(hHandle, 0) )
      {
        v23 = ProcessCertificationResponse((struct CDRMSoapRequest *)v32, v24, v25, v26, a1, hHandle, a9, a10, a11);
LABEL_44:
        CertificationRequest = v23;
        goto LABEL_45;
      }
    }
LABEL_15:
    CertificationRequest = -2147168447;
  }
LABEL_45:
  if ( Block[0] )
    operator delete(Block[0]);
LABEL_47:
  operator delete(v14);
  operator delete(v15);
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v32);
  return (unsigned int)CertificationRequest;
}

```

## disassembly

```asm
0x18002c390  push    rbp
0x18002c392  push    rbx
0x18002c393  push    rsi
0x18002c394  push    rdi
0x18002c395  push    r12
0x18002c397  push    r13
0x18002c399  push    r14
0x18002c39b  push    r15
0x18002c39d  lea     rbp, [rsp-98h]
0x18002c3a5  sub     rsp, 198h
0x18002c3ac  mov     [rsp+1D0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18002c3b5  mov     r13, r9
0x18002c3b8  mov     r10, r8
0x18002c3bb  mov     esi, edx
0x18002c3bd  mov     r14, rcx
0x18002c3c0  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c3c4  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x18002c3c9  nop
0x18002c3ca  xor     r15d, r15d
0x18002c3cd  mov     [rsp+1D0h+var_170], r15
0x18002c3d2  xor     r12d, r12d
0x18002c3d5  mov     [rsp+1D0h+var_178], r12
0x18002c3da  mov     [rsp+1D0h+var_180], r12d
0x18002c3df  mov     [rsp+1D0h+Block], r12
0x18002c3e4  mov     rax, [rbp+0D0h+arg_30]
0x18002c3eb  mov     [rbp+0D0h+var_148], rax
0x18002c3ef  mov     [rbp+0D0h+var_140], 1
0x18002c3f6  mov     rax, [rbp+0D0h+arg_38]
0x18002c3fd  mov     [rbp+0D0h+var_138], rax
0x18002c401  mov     rdi, [rbp+0D0h+hHandle]
0x18002c408  mov     [rbp+0D0h+var_100], rdi
0x18002c40c  xor     r8d, r8d; unsigned int
0x18002c40f  mov     rdx, r10; unsigned __int16 *
0x18002c412  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c416  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x18002c41b  mov     ebx, eax
0x18002c41d  test    eax, eax
0x18002c41f  js      loc_18002C720
0x18002c425  xor     edx, edx; dwMilliseconds
0x18002c427  mov     rcx, rdi; hHandle
0x18002c42a  call    cs:__imp_WaitForSingleObject
0x18002c430  xor     ebx, ebx
0x18002c432  test    eax, eax
0x18002c434  jnz     short loc_18002C440
0x18002c436  mov     ebx, 8004CF41h
0x18002c43b  jmp     loc_18002C720
0x18002c440  lea     rax, [rsp+1D0h+Block]
0x18002c445  mov     [rsp+1D0h+var_198], rax
0x18002c44a  mov     [rsp+1D0h+var_1A0], rbx
0x18002c44f  lea     rax, [rsp+1D0h+var_180]
0x18002c454  mov     [rsp+1D0h+var_1A8], rax
0x18002c459  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x18002c45d  xor     r9d, r9d
0x18002c460  xor     r8d, r8d
0x18002c463  lea     ecx, [r9+1]
0x18002c467  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18002c46c  mov     eax, [rbp+0D0h+var_C0]
0x18002c46f  cmp     [rsp+1D0h+var_180], ebx
0x18002c473  mov     ecx, 1
0x18002c478  cmova   eax, ecx
0x18002c47b  mov     [rbp+0D0h+var_C0], eax
0x18002c47e  lea     rdx, aPassportauthpr; "PassportAuthProvider"
0x18002c485  mov     rbx, [rbp+0D0h+String1]
0x18002c48c  mov     rcx, rbx; String1
0x18002c48f  call    wcscmp_0
0x18002c494  test    eax, eax
0x18002c496  jnz     short loc_18002C4A1
0x18002c498  mov     [rbp+0D0h+var_128], 20h ; ' '
0x18002c49f  jmp     short loc_18002C4D4
0x18002c4a1  lea     rdx, aWindowsauthpro; "WindowsAuthProvider"
0x18002c4a8  mov     rcx, rbx; String1
0x18002c4ab  call    wcscmp_0
0x18002c4b0  test    eax, eax
0x18002c4b2  jnz     short loc_18002C4D4
0x18002c4b4  test    sil, 4
0x18002c4b8  jz      short loc_18002C4C3
0x18002c4ba  mov     [rbp+0D0h+var_128], 8
0x18002c4c1  jmp     short loc_18002C4D4
0x18002c4c3  mov     ecx, 10h
0x18002c4c8  test    cl, sil
0x18002c4cb  mov     eax, [rbp+0D0h+var_128]
0x18002c4ce  cmovnz  eax, ecx
0x18002c4d1  mov     [rbp+0D0h+var_128], eax
0x18002c4d4  xor     edx, edx; dwMilliseconds
0x18002c4d6  mov     rcx, rdi; hHandle
0x18002c4d9  call    cs:__imp_WaitForSingleObject
0x18002c4df  test    eax, eax
0x18002c4e1  jnz     short loc_18002C4ED
0x18002c4e3  mov     ebx, 8004CF41h
0x18002c4e8  jmp     loc_18002C711
0x18002c4ed  mov     r8d, esi
0x18002c4f0  and     r8d, 0FFFFFFFEh; unsigned int
0x18002c4f4  mov     [rsp+1D0h+var_1B0], rbx; unsigned __int16 *
0x18002c4f9  mov     r9, r13; unsigned __int16 *
0x18002c4fc  lea     rdx, [rbp+0D0h+var_150]; struct CDRMSoapRequest *
0x18002c500  mov     rcx, r14; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x18002c503  call    ?GenerateCertificationRequest@@YAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@PEAVCDRMSoapRequest@@IPEAG2@Z; GenerateCertificationRequest(_DRM_CRYPTO_VERSION_PARAMETERS const *,CDRMSoapRequest *,uint,ushort *,ushort *)
0x18002c508  mov     ebx, eax
0x18002c50a  test    eax, eax
0x18002c50c  js      loc_18002C711
0x18002c512  xor     edx, edx; dwMilliseconds
0x18002c514  mov     rcx, rdi; hHandle
0x18002c517  call    cs:__imp_WaitForSingleObject
0x18002c51d  test    eax, eax
0x18002c51f  jz      short loc_18002C4E3
0x18002c521  xor     r8d, r8d; unsigned int
0x18002c524  xor     edx, edx; unsigned __int8 *
0x18002c526  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c52a  call    ?DispatchRequest@CDRMSoapRequest@@UEAAJPEAEI@Z; CDRMSoapRequest::DispatchRequest(uchar *,uint)
0x18002c52f  mov     ebx, eax
0x18002c531  cmp     eax, 8004CFD4h
0x18002c536  jnz     loc_18002C6B1
0x18002c53c  lea     rdx, [rsp+1D0h+var_170]; unsigned __int16 **
0x18002c541  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c545  call    ?GetFaultCode@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultCode(ushort * *)
0x18002c54a  lea     rdx, [rsp+1D0h+var_178]; unsigned __int16 **
0x18002c54f  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c553  call    ?GetFaultString@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultString(ushort * *)
0x18002c558  mov     r12, [rsp+1D0h+var_178]
0x18002c55d  mov     r8, r12
0x18002c560  mov     r15, [rsp+1D0h+var_170]
0x18002c565  mov     rdx, r15
0x18002c568  lea     rcx, aMsdrmCertifygr; "[msdrm]: CertifyGroupIdentity  FaultCod"...
0x18002c56f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002c574  lea     rdx, ?g_wszACT_UnsupportedCryptoException@@3QBGB; "Microsoft.DigitalRightsManagement.Crypt"...
0x18002c57b  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c57f  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c584  test    eax, eax
0x18002c586  jz      short loc_18002C592
0x18002c588  mov     ebx, 8004CF14h
0x18002c58d  jmp     loc_18002C711
0x18002c592  lea     rdx, ?g_wszACT_UnauthAccessException@@3QBGB; "System.UnauthorizedAccessException"
0x18002c599  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c59d  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c5a2  test    eax, eax
0x18002c5a4  jnz     loc_18002C6AA
0x18002c5aa  lea     rdx, ?g_wszACT_MismatchedEmailException@@3QBGB; "Microsoft.DigitalRightsManagement.Certi"...
0x18002c5b1  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c5b5  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c5ba  test    eax, eax
0x18002c5bc  jnz     loc_18002C6AA
0x18002c5c2  lea     rdx, ?g_wszACT_EmailException@@3QBGB; "Microsoft.DigitalRightsManagement.Core."...
0x18002c5c9  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c5cd  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c5d2  test    eax, eax
0x18002c5d4  jz      short loc_18002C5E0
0x18002c5d6  mov     ebx, 8004CF4Bh
0x18002c5db  jmp     loc_18002C711
0x18002c5e0  lea     rdx, ?g_wszACT_EmailNotVerified@@3QBGB; "Microsoft.DigitalRightsManagement.Activ"...
0x18002c5e7  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c5eb  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c5f0  test    eax, eax
0x18002c5f2  jz      short loc_18002C5FE
0x18002c5f4  mov     ebx, 8004CF5Ah
0x18002c5f9  jmp     loc_18002C711
0x18002c5fe  lea     rdx, ?g_wszACT_ActiveDirException@@3QBGB; "Microsoft.DigitalRightsManagement.Utili"...
0x18002c605  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c609  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c60e  test    eax, eax
0x18002c610  jz      short loc_18002C61C
0x18002c612  mov     ebx, 8004CF5Dh
0x18002c617  jmp     loc_18002C711
0x18002c61c  lea     rdx, ?g_wszACT_MachineCertException@@3QBGB; "Microsoft.DigitalRightsManagement.Core."...
0x18002c623  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c627  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c62c  test    eax, eax
0x18002c62e  jnz     short loc_18002C6A3
0x18002c630  lea     rdx, ?g_wszACT_BlackboxIsInvalidExclusion@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x18002c637  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c63b  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c640  test    eax, eax
0x18002c642  jnz     short loc_18002C6A3
0x18002c644  lea     rdx, ?g_wszACT_TemporaryDrmacException@@3QBGB; "Microsoft.DigitalRightsManagement.Certi"...
0x18002c64b  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c64f  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c654  test    eax, eax
0x18002c656  jz      short loc_18002C662
0x18002c658  mov     ebx, 8004CF5Fh
0x18002c65d  jmp     loc_18002C711
0x18002c662  lea     rdx, ?g_wszACT_CrossTenantCertificationDisabledException@@3QBGB; "Microsoft.RightsManagementServices.Onli"...
0x18002c669  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c66d  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18002c672  test    eax, eax
0x18002c674  jz      short loc_18002C68F
0x18002c676  and     esi, 10h
0x18002c679  mov     edx, esi; int
0x18002c67b  mov     ecx, 1776h; unsigned __int16 *
0x18002c680  call    ?DisplayIppOnlineError@@YAXPEBGH@Z; DisplayIppOnlineError(ushort const *,int)
0x18002c685  mov     ebx, 8004CF44h
0x18002c68a  jmp     loc_18002C711
0x18002c68f  mov     eax, 8004CF44h
0x18002c694  lea     ebx, [rax-30h]
0x18002c697  cmp     dword ptr [r14], 400h
0x18002c69e  cmova   eax, ebx
0x18002c6a1  jmp     short loc_18002C70F
0x18002c6a3  mov     ebx, 8004CF3Dh
0x18002c6a8  jmp     short loc_18002C711
0x18002c6aa  mov     ebx, 8004CF43h
0x18002c6af  jmp     short loc_18002C711
0x18002c6b1  test    eax, eax
0x18002c6b3  jns     short loc_18002C6C5
0x18002c6b5  mov     edx, eax
0x18002c6b7  lea     rcx, aMsdrmFailedX; "[msdrm]: FAILED : %x "
0x18002c6be  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002c6c3  jmp     short loc_18002C711
0x18002c6c5  xor     edx, edx; dwMilliseconds
0x18002c6c7  mov     rcx, rdi; hHandle
0x18002c6ca  call    cs:__imp_WaitForSingleObject
0x18002c6d0  test    eax, eax
0x18002c6d2  jz      loc_18002C4E3
0x18002c6d8  mov     rax, [rbp+0D0h+arg_50]
0x18002c6df  mov     [rsp+1D0h+var_190], rax; unsigned __int16 **
0x18002c6e4  mov     rax, [rbp+0D0h+arg_48]
0x18002c6eb  mov     [rsp+1D0h+var_198], rax; unsigned __int16 **
0x18002c6f0  mov     rax, [rbp+0D0h+arg_40]
0x18002c6f7  mov     [rsp+1D0h+var_1A0], rax; unsigned __int16 **
0x18002c6fc  mov     [rsp+1D0h+var_1A8], rdi; hHandle
0x18002c701  mov     [rsp+1D0h+var_1B0], r14; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x18002c706  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c70a  call    ?ProcessCertificationResponse@@YAJPEAVCDRMSoapRequest@@IPEAG1PEBU_DRM_CRYPTO_VERSION_PARAMETERS@@PEAXPEAPEAG44@Z; ProcessCertificationResponse(CDRMSoapRequest *,uint,ushort *,ushort *,_DRM_CRYPTO_VERSION_PARAMETERS const *,void *,ushort * *,ushort * *,ushort * *)
0x18002c70f  mov     ebx, eax
0x18002c711  mov     rcx, [rsp+1D0h+Block]; Block
0x18002c716  test    rcx, rcx
0x18002c719  jz      short loc_18002C720
0x18002c71b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c720  mov     rcx, r15; Block
0x18002c723  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c728  mov     rcx, r12; Block
0x18002c72b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c730  nop
0x18002c731  lea     rcx, [rbp+0D0h+var_150]; this
0x18002c735  call    ??1CDRMSoapRequest@@UEAA@XZ; CDRMSoapRequest::~CDRMSoapRequest(void)
0x18002c73a  mov     eax, ebx
0x18002c73c  add     rsp, 198h
0x18002c743  pop     r15
0x18002c745  pop     r14
0x18002c747  pop     r13
0x18002c749  pop     r12
0x18002c74b  pop     rdi
0x18002c74c  pop     rsi
0x18002c74d  pop     rbx
0x18002c74e  pop     rbp
0x18002c74f  retn
```
