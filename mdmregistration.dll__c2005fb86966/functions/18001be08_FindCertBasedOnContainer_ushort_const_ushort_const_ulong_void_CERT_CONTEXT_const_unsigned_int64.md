# FindCertBasedOnContainer(ushort const *,ushort const *,ulong,void * *,_CERT_CONTEXT const * *,unsigned __int64 *)

- ea: `0x18001be08`
- end: `0x18001c105`
- name: `?FindCertBasedOnContainer@@YAJPEBG0KPEAPEAXPEAPEBU_CERT_CONTEXT@@PEA_K@Z`
- size: `765`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, void **@<r9>, const struct _CERT_CONTEXT **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180037b18`

## callees

- `0x1800141b0`
- `0x18001be08`
- `0x18001c10c`
- `0x180041410`
- `0x180042ed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bf58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bf58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c087`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c087`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c073`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfbb`
- `CRYPT32!CertFreeCertificateContext` at `0x18001c0c5`
- `CRYPT32!CertFreeCertificateContext` at `0x18001c0c5`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001bf0a`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001bfab`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001bf0a`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x18001bfab`
- `CRYPT32!CertCloseStore` at `0x18001c0db`
- `CRYPT32!CertCloseStore` at `0x18001c0db`
- `ncrypt!NCryptFreeObject` at `0x18001c09c`
- `ncrypt!NCryptFreeObject` at `0x18001c0b1`
- `ncrypt!NCryptFreeObject` at `0x18001c09c`
- `ncrypt!NCryptFreeObject` at `0x18001c0b1`
- `ncrypt!NCryptOpenKey` at `0x18001bebb`
- `ncrypt!NCryptOpenKey` at `0x18001bebb`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001be8a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001be8a`

## string_xrefs

- `0x18001be9d`: `NCryptOpenStorageProvider`
- `0x18001bece`: `NCryptOpenKey`

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
  void *v8; // rsi
  const CERT_CONTEXT *v9; // r14
  DWORD dwFlags; // ebx
  struct _CERT_PUBLIC_KEY_INFO *pInfo; // rdi
  const unsigned __int16 *v12; // rbx
  signed int LastError; // eax
  DWORD v14; // ebx
  HANDLE ProcessHeap; // rax
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v17; // r9
  HANDLE v18; // rax
  unsigned int v19; // ebx
  void *v21; // [rsp+40h] [rbp-30h] BYREF
  const struct _CERT_CONTEXT *v22; // [rsp+48h] [rbp-28h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+58h] [rbp-18h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+B0h] [rbp+40h] BYREF
  DWORD pcbInfo; // [rsp+B8h] [rbp+48h] BYREF
  int v27; // [rsp+BCh] [rbp+4Ch]
  int CertBasedOnContainerHelper; // [rsp+C0h] [rbp+50h] BYREF

  v27 = HIDWORD(a2);
  CertBasedOnContainerHelper = 0;
  v8 = 0;
  v21 = 0;
  v9 = 0;
  v22 = 0;
  phProvider = 0;
  phKey = 0;
  dwFlags = 8 * (a3 & 4 | 8);
  pcbInfo = 0;
  pInfo = 0;
  v24[0] = "FindCertBasedOnContainer";
  v24[1] = &CertBasedOnContainerHelper;
  if ( !a1 )
  {
    v12 = &String2;
    CertBasedOnContainerHelper = -2147024809;
LABEL_22:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollCertificateFindCertBasedOnContainerFailed(
      Logger,
      v12,
      a1,
      v17,
      CertBasedOnContainerHelper);
LABEL_23:
    if ( !pInfo )
      goto LABEL_27;
    goto LABEL_26;
  }
  CertBasedOnContainerHelper = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( CertBasedOnContainerHelper < 0 )
  {
    v12 = L"NCryptOpenStorageProvider";
    goto LABEL_22;
  }
  CertBasedOnContainerHelper = NCryptOpenKey(phProvider, &phKey, a1, 0, dwFlags);
  if ( CertBasedOnContainerHelper < 0 )
  {
    v12 = L"NCryptOpenKey";
    goto LABEL_22;
  }
  if ( !CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, 0, &pcbInfo) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"CryptExportPublicKeyInfoEx 1st call";
    goto LABEL_17;
  }
  v14 = pcbInfo;
  ProcessHeap = GetProcessHeap();
  pInfo = (struct _CERT_PUBLIC_KEY_INFO *)HeapAlloc(ProcessHeap, 8u, v14);
  if ( !pInfo )
  {
    CertBasedOnContainerHelper = -2147024882;
    v12 = L"SafeHeapAlloc(cbCertPubKey)";
    goto LABEL_22;
  }
  if ( !CryptExportPublicKeyInfoEx(phKey, 0, 1u, 0, 0, 0, pInfo, &pcbInfo) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"CryptExportPublicKeyInfoEx 2nd call";
LABEL_17:
    CertBasedOnContainerHelper = LastError;
    if ( LastError >= 0 )
      goto LABEL_23;
    goto LABEL_22;
  }
  CertBasedOnContainerHelper = FindCertBasedOnContainerHelper(0x20000, pInfo, &v21, &v22);
  if ( CertBasedOnContainerHelper < 0 )
  {
    CertBasedOnContainerHelper = FindCertBasedOnContainerHelper(0x10000, pInfo, &v21, &v22);
    if ( CertBasedOnContainerHelper < 0 )
    {
      v12 = L"FindCertBasedOnContainerHelper with CERT_SYSTEM_STORE_CURRENT_USER after call with CERT_SYSTEM_STORE_LOCAL_MACHINE";
      v8 = v21;
      v9 = v22;
      goto LABEL_22;
    }
  }
  *a4 = v21;
  v8 = 0;
  *a5 = v22;
  v9 = 0;
  *a6 = phKey;
  phKey = 0;
LABEL_26:
  v18 = GetProcessHeap();
  HeapFree(v18, 0, pInfo);
LABEL_27:
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( v9 )
    CertFreeCertificateContext(v9);
  if ( v8 )
    CertCloseStore(v8, 0);
  v19 = CertBasedOnContainerHelper;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v24);
  return v19;
}

```

## disassembly

```asm
0x18001be08  mov     qword ptr [rsp-38h+arg_8], rdx
0x18001be0d  push    rbp
0x18001be0e  push    rbx
0x18001be0f  push    rsi
0x18001be10  push    rdi
0x18001be11  push    r12
0x18001be13  push    r14
0x18001be15  push    r15
0x18001be17  mov     rbp, rsp
0x18001be1a  sub     rsp, 70h
0x18001be1e  mov     r15, r9
0x18001be21  mov     ebx, r8d
0x18001be24  mov     r12, rcx
0x18001be27  mov     [rbp+arg_10], 0
0x18001be2e  xor     esi, esi
0x18001be30  mov     [rbp+var_30], rsi
0x18001be34  xor     r14d, r14d
0x18001be37  mov     [rbp+var_28], r14
0x18001be3b  mov     [rbp+phProvider], rsi
0x18001be3f  mov     [rbp+phKey], rsi
0x18001be43  and     ebx, 4
0x18001be46  or      ebx, 8
0x18001be49  shl     ebx, 3
0x18001be4c  mov     [rbp+arg_8], esi
0x18001be4f  xor     edi, edi
0x18001be51  lea     rax, aFindcertbasedo_0; "FindCertBasedOnContainer"
0x18001be58  mov     [rbp+var_18], rax
0x18001be5c  lea     rax, [rbp+arg_10]
0x18001be60  mov     [rbp+var_10], rax
0x18001be64  test    rcx, rcx
0x18001be67  jnz     short loc_18001BE7C
0x18001be69  lea     rbx, String2
0x18001be70  mov     [rbp+arg_10], 80070057h
0x18001be77  jmp     loc_18001C02C
0x18001be7c  xor     r8d, r8d; dwFlags
0x18001be7f  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18001be86  lea     rcx, [rbp+phProvider]; phProvider
0x18001be8a  call    cs:__imp_NCryptOpenStorageProvider
0x18001be91  nop     dword ptr [rax+rax+00h]
0x18001be96  mov     [rbp+arg_10], eax
0x18001be99  test    eax, eax
0x18001be9b  jns     short loc_18001BEA9
0x18001be9d  lea     rbx, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x18001bea4  jmp     loc_18001C02C
0x18001bea9  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x18001bead  xor     r9d, r9d; dwLegacyKeySpec
0x18001beb0  mov     r8, r12; pszKeyName
0x18001beb3  lea     rdx, [rbp+phKey]; phKey
0x18001beb7  mov     rcx, [rbp+phProvider]; hProvider
0x18001bebb  call    cs:__imp_NCryptOpenKey
0x18001bec2  nop     dword ptr [rax+rax+00h]
0x18001bec7  mov     [rbp+arg_10], eax
0x18001beca  test    eax, eax
0x18001becc  jns     short loc_18001BEDA
0x18001bece  lea     rbx, aNcryptopenkey_0; "NCryptOpenKey"
0x18001bed5  jmp     loc_18001C02C
0x18001beda  lea     rax, [rbp+arg_8]
0x18001bede  mov     [rsp+70h+pcbInfo], rax; pcbInfo
0x18001bee3  mov     [rsp+70h+pInfo], 0; pInfo
0x18001beec  mov     [rsp+70h+pvAuxInfo], 0; pvAuxInfo
0x18001bef5  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18001befd  xor     r9d, r9d; pszPublicKeyObjId
0x18001bf00  xor     edx, edx; dwKeySpec
0x18001bf02  lea     r8d, [r9+1]; dwCertEncodingType
0x18001bf06  mov     rcx, [rbp+phKey]; hCryptProvOrNCryptKey
0x18001bf0a  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001bf11  nop     dword ptr [rax+rax+00h]
0x18001bf16  test    eax, eax
0x18001bf18  jnz     short loc_18001BF3E
0x18001bf1a  call    cs:__imp_GetLastError
0x18001bf21  nop     dword ptr [rax+rax+00h]
0x18001bf26  test    eax, eax
0x18001bf28  jle     short loc_18001BF32
0x18001bf2a  movzx   eax, ax
0x18001bf2d  or      eax, 80070000h
0x18001bf32  lea     rbx, aCryptexportpub_2; "CryptExportPublicKeyInfoEx 1st call"
0x18001bf39  jmp     loc_18001BFDA
0x18001bf3e  mov     ebx, [rbp+arg_8]
0x18001bf41  call    cs:__imp_GetProcessHeap
0x18001bf48  nop     dword ptr [rax+rax+00h]
0x18001bf4d  mov     rcx, rax; hHeap
0x18001bf50  mov     r8d, ebx; dwBytes
0x18001bf53  mov     edx, 8; dwFlags
0x18001bf58  call    cs:__imp_HeapAlloc
0x18001bf5f  nop     dword ptr [rax+rax+00h]
0x18001bf64  mov     rdi, rax
0x18001bf67  test    rax, rax
0x18001bf6a  jnz     short loc_18001BF7F
0x18001bf6c  mov     [rbp+arg_10], 8007000Eh
0x18001bf73  lea     rbx, aSafeheapallocC; "SafeHeapAlloc(cbCertPubKey)"
0x18001bf7a  jmp     loc_18001C02C
0x18001bf7f  lea     rax, [rbp+arg_8]
0x18001bf83  mov     [rsp+70h+pcbInfo], rax; pcbInfo
0x18001bf88  mov     [rsp+70h+pInfo], rdi; pInfo
0x18001bf8d  mov     [rsp+70h+pvAuxInfo], 0; pvAuxInfo
0x18001bf96  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18001bf9e  xor     r9d, r9d; pszPublicKeyObjId
0x18001bfa1  xor     edx, edx; dwKeySpec
0x18001bfa3  lea     r8d, [r9+1]; dwCertEncodingType
0x18001bfa7  mov     rcx, [rbp+phKey]; hCryptProvOrNCryptKey
0x18001bfab  call    cs:__imp_CryptExportPublicKeyInfoEx
0x18001bfb2  nop     dword ptr [rax+rax+00h]
0x18001bfb7  test    eax, eax
0x18001bfb9  jnz     short loc_18001BFE5
0x18001bfbb  call    cs:__imp_GetLastError
0x18001bfc2  nop     dword ptr [rax+rax+00h]
0x18001bfc7  test    eax, eax
0x18001bfc9  jle     short loc_18001BFD3
0x18001bfcb  movzx   eax, ax
0x18001bfce  or      eax, 80070000h
0x18001bfd3  lea     rbx, aCryptexportpub_1; "CryptExportPublicKeyInfoEx 2nd call"
0x18001bfda  mov     ecx, eax
0x18001bfdc  mov     [rbp+arg_10], eax
0x18001bfdf  test    eax, eax
0x18001bfe1  jns     short loc_18001C046
0x18001bfe3  jmp     short loc_18001C02C
0x18001bfe5  lea     r9, [rbp+var_28]
0x18001bfe9  lea     r8, [rbp+var_30]
0x18001bfed  mov     rdx, rdi
0x18001bff0  mov     ecx, 20000h
0x18001bff5  call    FindCertBasedOnContainerHelper
0x18001bffa  mov     [rbp+arg_10], eax
0x18001bffd  test    eax, eax
0x18001bfff  jns     short loc_18001C04D
0x18001c001  lea     r9, [rbp+var_28]
0x18001c005  lea     r8, [rbp+var_30]
0x18001c009  mov     rdx, rdi
0x18001c00c  mov     ecx, 10000h
0x18001c011  call    FindCertBasedOnContainerHelper
0x18001c016  mov     [rbp+arg_10], eax
0x18001c019  test    eax, eax
0x18001c01b  jns     short loc_18001C04D
0x18001c01d  lea     rbx, aFindcertbasedo; "FindCertBasedOnContainerHelper with CER"...
0x18001c024  mov     rsi, [rbp+var_30]
0x18001c028  mov     r14, [rbp+var_28]
0x18001c02c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c031  mov     ecx, [rbp+arg_10]
0x18001c034  mov     [rsp+70h+dwFlags], ecx; int
0x18001c038  mov     r8, r12; unsigned __int16 *
0x18001c03b  mov     rdx, rbx; unsigned __int16 *
0x18001c03e  mov     rcx, rax; this
0x18001c041  call    ?LogEnrollCertificateFindCertBasedOnContainerFailed@CEnrollmentLogger@@QEAAXPEBG00J@Z; CEnrollmentLogger::LogEnrollCertificateFindCertBasedOnContainerFailed(ushort const *,ushort const *,ushort const *,long)
0x18001c046  test    rdi, rdi
0x18001c049  jz      short loc_18001C093
0x18001c04b  jmp     short loc_18001C073
0x18001c04d  mov     rax, [rbp+var_30]
0x18001c051  mov     [r15], rax
0x18001c054  xor     esi, esi
0x18001c056  mov     rcx, [rbp+var_28]
0x18001c05a  mov     rax, [rbp+arg_20]
0x18001c05e  mov     [rax], rcx
0x18001c061  xor     r14d, r14d
0x18001c064  mov     rcx, [rbp+arg_28]
0x18001c068  mov     rax, [rbp+phKey]
0x18001c06c  mov     [rcx], rax
0x18001c06f  mov     [rbp+phKey], rsi
0x18001c073  call    cs:__imp_GetProcessHeap
0x18001c07a  nop     dword ptr [rax+rax+00h]
0x18001c07f  mov     rcx, rax; hHeap
0x18001c082  mov     r8, rdi; lpMem
0x18001c085  xor     edx, edx; dwFlags
0x18001c087  call    cs:__imp_HeapFree
0x18001c08e  nop     dword ptr [rax+rax+00h]
0x18001c093  mov     rcx, [rbp+phKey]; hObject
0x18001c097  test    rcx, rcx
0x18001c09a  jz      short loc_18001C0A8
0x18001c09c  call    cs:__imp_NCryptFreeObject
0x18001c0a3  nop     dword ptr [rax+rax+00h]
0x18001c0a8  mov     rcx, [rbp+phProvider]; hObject
0x18001c0ac  test    rcx, rcx
0x18001c0af  jz      short loc_18001C0BD
0x18001c0b1  call    cs:__imp_NCryptFreeObject
0x18001c0b8  nop     dword ptr [rax+rax+00h]
0x18001c0bd  test    r14, r14
0x18001c0c0  jz      short loc_18001C0D1
0x18001c0c2  mov     rcx, r14; pCertContext
0x18001c0c5  call    cs:__imp_CertFreeCertificateContext
0x18001c0cc  nop     dword ptr [rax+rax+00h]
0x18001c0d1  test    rsi, rsi
0x18001c0d4  jz      short loc_18001C0E7
0x18001c0d6  xor     edx, edx; dwFlags
0x18001c0d8  mov     rcx, rsi; hCertStore
0x18001c0db  call    cs:__imp_CertCloseStore
0x18001c0e2  nop     dword ptr [rax+rax+00h]
0x18001c0e7  mov     ebx, [rbp+arg_10]
0x18001c0ea  lea     rcx, [rbp+var_18]; this
0x18001c0ee  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001c0f3  mov     eax, ebx
0x18001c0f5  add     rsp, 70h
0x18001c0f9  pop     r15
0x18001c0fb  pop     r14
0x18001c0fd  pop     r12
0x18001c0ff  pop     rdi
0x18001c100  pop     rsi
0x18001c101  pop     rbx
0x18001c102  pop     rbp
0x18001c103  retn
```
