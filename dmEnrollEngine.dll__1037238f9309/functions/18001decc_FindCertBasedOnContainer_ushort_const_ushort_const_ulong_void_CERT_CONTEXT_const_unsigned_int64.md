# FindCertBasedOnContainer(ushort const *,ushort const *,ulong,void * *,_CERT_CONTEXT const * *,unsigned __int64 *)

- ea: `0x18001decc`
- end: `0x18001e15b`
- name: `?FindCertBasedOnContainer@@YAJPEBG0KPEAPEAXPEAPEBU_CERT_CONTEXT@@PEA_K@Z`
- size: `655`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, void **@<r9>, const struct _CERT_CONTEXT **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002d9d0`
- `0x18004ea54`

## callees

- `0x1800140d0`
- `0x180014148`
- `0x18001aec8`
- `0x18001decc`
- `0x1800206a8`
- `0x180044d64`
- `0x18007181c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e03d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e03d`
- `CRYPT32!CertCloseStore` at `0x18001e12f`
- `CRYPT32!CertCloseStore` at `0x18001e12f`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e11f`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e11f`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001dfc0`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001e033`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001dfc0`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001e033`
- `ncrypt!NCryptFreeObject` at `0x18001e102`
- `ncrypt!NCryptFreeObject` at `0x18001e111`
- `ncrypt!NCryptFreeObject` at `0x18001e102`
- `ncrypt!NCryptFreeObject` at `0x18001e111`
- `ncrypt!NCryptOpenKey` at `0x18001df74`
- `ncrypt!NCryptOpenKey` at `0x18001df74`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001df49`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001df49`

## string_xrefs

- `0x18001df81`: `NCryptOpenKey`
- `0x18001df56`: `NCryptOpenStorageProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindCertBasedOnContainer(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char a3,
        void **a4,
        const struct _CERT_CONTEXT **a5,
        unsigned __int64 *a6)
{
  void *v9; // rsi
  const CERT_CONTEXT *v10; // r14
  DWORD dwFlags; // ebx
  struct _CERT_PUBLIC_KEY_INFO *pInfo; // rdi
  const unsigned __int16 *v13; // rbx
  signed int LastError; // eax
  CEnrollmentLogger *Logger; // rax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-30h] BYREF
  void *v20; // [rsp+48h] [rbp-28h] BYREF
  const struct _CERT_CONTEXT *v21; // [rsp+50h] [rbp-20h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD pcbInfo; // [rsp+B0h] [rbp+40h] BYREF
  int CertBasedOnContainerHelper; // [rsp+C0h] [rbp+50h] BYREF

  CertBasedOnContainerHelper = 0;
  v9 = 0;
  v20 = 0;
  v10 = 0;
  v21 = 0;
  phProvider = 0;
  phKey = 0;
  dwFlags = 8 * (a3 & 4 | 8);
  pcbInfo = 0;
  pInfo = 0;
  v23[0] = "FindCertBasedOnContainer";
  v23[1] = &CertBasedOnContainerHelper;
  if ( !a1 )
  {
    v13 = &wszURI;
    CertBasedOnContainerHelper = -2147024809;
LABEL_22:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollCertificateFindCertBasedOnContainerFailed(
      Logger,
      v13,
      a1,
      a2,
      CertBasedOnContainerHelper);
    goto LABEL_24;
  }
  CertBasedOnContainerHelper = NCryptOpenStorageProvider(&phProvider, a2, 0);
  if ( CertBasedOnContainerHelper < 0 )
  {
    v13 = L"NCryptOpenStorageProvider";
    goto LABEL_22;
  }
  CertBasedOnContainerHelper = NCryptOpenKey(phProvider, &phKey, a1, 0, dwFlags);
  if ( CertBasedOnContainerHelper < 0 )
  {
    v13 = L"NCryptOpenKey";
    goto LABEL_22;
  }
  if ( !CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, 0, &pcbInfo) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"CryptExportPublicKeyInfoEx 1st call";
    goto LABEL_17;
  }
  pInfo = (struct _CERT_PUBLIC_KEY_INFO *)SafeHeapAlloc(pcbInfo);
  if ( !pInfo )
  {
    CertBasedOnContainerHelper = -2147024882;
    v13 = L"SafeHeapAlloc(cbCertPubKey)";
    goto LABEL_22;
  }
  if ( !CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, pInfo, &pcbInfo) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"CryptExportPublicKeyInfoEx 2nd call";
LABEL_17:
    CertBasedOnContainerHelper = LastError;
    if ( LastError >= 0 )
      goto LABEL_24;
    goto LABEL_22;
  }
  CertBasedOnContainerHelper = FindCertBasedOnContainerHelper(0x20000, pInfo, &v20, &v21);
  if ( CertBasedOnContainerHelper < 0 )
  {
    CertBasedOnContainerHelper = FindCertBasedOnContainerHelper(0x10000, pInfo, &v20, &v21);
    if ( CertBasedOnContainerHelper < 0 )
    {
      v13 = L"FindCertBasedOnContainerHelper with CERT_SYSTEM_STORE_CURRENT_USER after call with CERT_SYSTEM_STORE_LOCAL_MACHINE";
      v9 = v20;
      v10 = v21;
      goto LABEL_22;
    }
  }
  *a4 = v20;
  v9 = 0;
  *a5 = v21;
  v10 = 0;
  *a6 = phKey;
  phKey = 0;
LABEL_24:
  SafeHeapFree(pInfo);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( v10 )
    CertFreeCertificateContext(v10);
  if ( v9 )
    CertCloseStore(v9, 0);
  v17 = CertBasedOnContainerHelper;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v23, v16);
  return v17;
}

```

## disassembly

```asm
0x18001decc  mov     [rsp-38h+arg_8], rbx
0x18001ded1  push    rbp
0x18001ded2  push    rsi
0x18001ded3  push    rdi
0x18001ded4  push    r12
0x18001ded6  push    r13
0x18001ded8  push    r14
0x18001deda  push    r15
0x18001dedc  mov     rbp, rsp
0x18001dedf  sub     rsp, 70h
0x18001dee3  mov     r15, r9
0x18001dee6  mov     ebx, r8d
0x18001dee9  mov     r13, rdx
0x18001deec  mov     r12, rcx
0x18001deef  xor     ecx, ecx
0x18001def1  mov     [rbp+arg_10], ecx
0x18001def4  mov     esi, ecx
0x18001def6  mov     [rbp+var_28], rcx
0x18001defa  mov     r14d, ecx
0x18001defd  mov     [rbp+var_20], rcx
0x18001df01  mov     [rbp+phProvider], rcx
0x18001df05  mov     [rbp+phKey], rcx
0x18001df09  and     ebx, 4
0x18001df0c  or      ebx, 8
0x18001df0f  shl     ebx, 3
0x18001df12  mov     [rbp+arg_0], ecx
0x18001df15  mov     edi, ecx
0x18001df17  lea     rax, aFindcertbasedo_0; "FindCertBasedOnContainer"
0x18001df1e  mov     [rbp+var_10], rax
0x18001df22  lea     rax, [rbp+arg_10]
0x18001df26  mov     [rbp+var_8], rax
0x18001df2a  test    r12, r12
0x18001df2d  jnz     short loc_18001DF42
0x18001df2f  lea     rbx, wszURI
0x18001df36  mov     [rbp+arg_10], 80070057h
0x18001df3d  jmp     loc_18001E0AC
0x18001df42  xor     r8d, r8d; dwFlags
0x18001df45  lea     rcx, [rbp+phProvider]; phProvider
0x18001df49  call    cs:__imp_NCryptOpenStorageProvider
0x18001df4f  mov     [rbp+arg_10], eax
0x18001df52  test    eax, eax
0x18001df54  jns     short loc_18001DF62
0x18001df56  lea     rbx, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x18001df5d  jmp     loc_18001E0AC
0x18001df62  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18001df66  xor     r9d, r9d; dwLegacyKeySpec
0x18001df69  mov     r8, r12; pszKeyName
0x18001df6c  lea     rdx, [rbp+phKey]; phKey
0x18001df70  mov     rcx, [rbp+phProvider]; hProvider
0x18001df74  call    cs:__imp_NCryptOpenKey
0x18001df7a  mov     [rbp+arg_10], eax
0x18001df7d  test    eax, eax
0x18001df7f  jns     short loc_18001DF8D
0x18001df81  lea     rbx, aNcryptopenkey_0; "NCryptOpenKey"
0x18001df88  jmp     loc_18001E0AC
0x18001df8d  lea     rax, [rbp+arg_0]
0x18001df91  mov     [rsp+70h+pcbInfo], rax; pcbInfo
0x18001df96  mov     [rsp+70h+pInfo], 0; pInfo
0x18001df9f  mov     [rsp+70h+pvAuxInfo], 0; pvAuxInfo
0x18001dfa8  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18001dfb0  xor     r9d, r9d; pszPublicKeyObjId
0x18001dfb3  lea     ebx, [r9+1]
0x18001dfb7  mov     r8d, ebx; dwCertEncodingType
0x18001dfba  xor     edx, edx; dwKeySpec
0x18001dfbc  mov     rcx, [rbp+phKey]; hCryptProvOrNCryptKey
0x18001dfc0  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001dfc6  test    eax, eax
0x18001dfc8  jnz     short loc_18001DFE5
0x18001dfca  call    cs:__imp_GetLastError
0x18001dfd0  test    eax, eax
0x18001dfd2  jle     short loc_18001DFDC
0x18001dfd4  movzx   eax, ax
0x18001dfd7  or      eax, 80070000h
0x18001dfdc  lea     rbx, aCryptexportpub_2; "CryptExportPublicKeyInfoEx 1st call"
0x18001dfe3  jmp     short loc_18001E056
0x18001dfe5  mov     ecx, [rbp+arg_0]; unsigned __int64
0x18001dfe8  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18001dfed  mov     rdi, rax
0x18001dff0  test    rax, rax
0x18001dff3  jnz     short loc_18001E008
0x18001dff5  mov     [rbp+arg_10], 8007000Eh
0x18001dffc  lea     rbx, aSafeheapallocC; "SafeHeapAlloc(cbCertPubKey)"
0x18001e003  jmp     loc_18001E0AC
0x18001e008  lea     rax, [rbp+arg_0]
0x18001e00c  mov     [rsp+70h+pcbInfo], rax; pcbInfo
0x18001e011  mov     [rsp+70h+pInfo], rdi; pInfo
0x18001e016  mov     [rsp+70h+pvAuxInfo], 0; pvAuxInfo
0x18001e01f  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18001e027  xor     r9d, r9d; pszPublicKeyObjId
0x18001e02a  mov     r8d, ebx; dwCertEncodingType
0x18001e02d  xor     edx, edx; dwKeySpec
0x18001e02f  mov     rcx, [rbp+phKey]; hCryptProvOrNCryptKey
0x18001e033  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001e039  test    eax, eax
0x18001e03b  jnz     short loc_18001E065
0x18001e03d  call    cs:__imp_GetLastError
0x18001e043  test    eax, eax
0x18001e045  jle     short loc_18001E04F
0x18001e047  movzx   eax, ax
0x18001e04a  or      eax, 80070000h
0x18001e04f  lea     rbx, aCryptexportpub_1; "CryptExportPublicKeyInfoEx 2nd call"
0x18001e056  mov     ecx, eax
0x18001e058  mov     [rbp+arg_10], eax
0x18001e05b  test    eax, eax
0x18001e05d  jns     loc_18001E0F1
0x18001e063  jmp     short loc_18001E0AC
0x18001e065  lea     r9, [rbp+var_20]
0x18001e069  lea     r8, [rbp+var_28]
0x18001e06d  mov     rdx, rdi
0x18001e070  mov     ecx, 20000h
0x18001e075  call    FindCertBasedOnContainerHelper
0x18001e07a  mov     [rbp+arg_10], eax
0x18001e07d  test    eax, eax
0x18001e07f  jns     short loc_18001E0CB
0x18001e081  lea     r9, [rbp+var_20]
0x18001e085  lea     r8, [rbp+var_28]
0x18001e089  mov     rdx, rdi
0x18001e08c  mov     ecx, 10000h
0x18001e091  call    FindCertBasedOnContainerHelper
0x18001e096  mov     [rbp+arg_10], eax
0x18001e099  test    eax, eax
0x18001e09b  jns     short loc_18001E0CB
0x18001e09d  lea     rbx, aFindcertbasedo; "FindCertBasedOnContainerHelper with CER"...
0x18001e0a4  mov     rsi, [rbp+var_28]
0x18001e0a8  mov     r14, [rbp+var_20]
0x18001e0ac  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001e0b1  mov     ecx, [rbp+arg_10]
0x18001e0b4  mov     [rsp+70h+dwFlags], ecx; int
0x18001e0b8  mov     r9, r13; unsigned __int16 *
0x18001e0bb  mov     r8, r12; unsigned __int16 *
0x18001e0be  mov     rdx, rbx; unsigned __int16 *
0x18001e0c1  mov     rcx, rax; this
0x18001e0c4  call    ?LogEnrollCertificateFindCertBasedOnContainerFailed@CEnrollmentLogger@@QEAAXPEBG00J@Z; CEnrollmentLogger::LogEnrollCertificateFindCertBasedOnContainerFailed(ushort const *,ushort const *,ushort const *,long)
0x18001e0c9  jmp     short loc_18001E0F1
0x18001e0cb  mov     rax, [rbp+var_28]
0x18001e0cf  mov     [r15], rax
0x18001e0d2  xor     esi, esi
0x18001e0d4  mov     rcx, [rbp+arg_20]
0x18001e0d8  mov     rax, [rbp+var_20]
0x18001e0dc  mov     [rcx], rax
0x18001e0df  xor     r14d, r14d
0x18001e0e2  mov     rcx, [rbp+arg_28]
0x18001e0e6  mov     rax, [rbp+phKey]
0x18001e0ea  mov     [rcx], rax
0x18001e0ed  mov     [rbp+phKey], rsi
0x18001e0f1  mov     rcx, rdi; void *
0x18001e0f4  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18001e0f9  mov     rcx, [rbp+phKey]; hObject
0x18001e0fd  test    rcx, rcx
0x18001e100  jz      short loc_18001E108
0x18001e102  call    cs:__imp_NCryptFreeObject
0x18001e108  mov     rcx, [rbp+phProvider]; hObject
0x18001e10c  test    rcx, rcx
0x18001e10f  jz      short loc_18001E117
0x18001e111  call    cs:__imp_NCryptFreeObject
0x18001e117  test    r14, r14
0x18001e11a  jz      short loc_18001E125
0x18001e11c  mov     rcx, r14; pCertContext
0x18001e11f  call    cs:__imp_CertFreeCertificateContext
0x18001e125  test    rsi, rsi
0x18001e128  jz      short loc_18001E135
0x18001e12a  xor     edx, edx; dwFlags
0x18001e12c  mov     rcx, rsi; hCertStore
0x18001e12f  call    cs:__imp_CertCloseStore
0x18001e135  mov     ebx, [rbp+arg_10]
0x18001e138  lea     rcx, [rbp+var_10]; this
0x18001e13c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001e141  mov     eax, ebx
0x18001e143  mov     rbx, [rsp+70h+arg_8]
0x18001e14b  add     rsp, 70h
0x18001e14f  pop     r15
0x18001e151  pop     r14
0x18001e153  pop     r13
0x18001e155  pop     r12
0x18001e157  pop     rdi
0x18001e158  pop     rsi
0x18001e159  pop     rbp
0x18001e15a  retn
```
