# CMachineEnroller::DeleteCertWithContainerName(ushort const *,ushort const *,ulong)

- ea: `0x18004ea54`
- end: `0x18004eb64`
- name: `?DeleteCertWithContainerName@CMachineEnroller@@CAJPEBG0K@Z`
- size: `272`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004f260`

## callees

- `0x1800140d0`
- `0x18001decc`
- `0x18004ea54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ead8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ead8`
- `CRYPT32!CertCloseStore` at `0x18004eb32`
- `CRYPT32!CertCloseStore` at `0x18004eb32`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18004eace`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18004eace`
- `CRYPT32!CertFreeCertificateContext` at `0x18004eb21`
- `CRYPT32!CertFreeCertificateContext` at `0x18004eb21`
- `ncrypt!NCryptFreeObject` at `0x18004eb40`
- `ncrypt!NCryptFreeObject` at `0x18004eb40`
- `ncrypt!NCryptDeleteKey` at `0x18004eafe`
- `ncrypt!NCryptDeleteKey` at `0x18004eafe`

## string_xrefs

- `0x18004ea85`: `CMachineEnroller::DeleteCertWithContainerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMachineEnroller::DeleteCertWithContainerName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char a3)
{
  const CERT_CONTEXT *v3; // rdi
  signed int LastError; // eax
  NCRYPT_KEY_HANDLE v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-20h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-10h] BYREF
  int CertBasedOnContainer; // [rsp+60h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+78h] [rbp+28h] BYREF

  CertBasedOnContainer = 0;
  hCertStore = 0;
  pCertContext = 0;
  hKey = 0;
  v11[0] = "CMachineEnroller::DeleteCertWithContainerName";
  v11[1] = &CertBasedOnContainer;
  if ( !a1 )
  {
    CertBasedOnContainer = -2147024809;
    goto LABEL_18;
  }
  CertBasedOnContainer = FindCertBasedOnContainer(a1, a2, a3, &hCertStore, &pCertContext, &hKey);
  v3 = pCertContext;
  if ( CertDeleteCertificateFromStore(pCertContext) )
  {
    v3 = 0;
    v5 = hKey;
    v6 = NCryptDeleteKey(hKey, 0);
    if ( v6 )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      CertBasedOnContainer = v6;
      goto LABEL_14;
    }
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CertBasedOnContainer = LastError;
    v5 = hKey;
  }
  if ( v3 )
    CertFreeCertificateContext(v3);
LABEL_14:
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v5 )
    NCryptFreeObject(v5);
LABEL_18:
  v7 = CertBasedOnContainer;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v11, (__int64)a2);
  return v7;
}

```

## disassembly

```asm
0x18004ea54  mov     [rsp-8+arg_8], rbx
0x18004ea59  mov     [rsp-8+arg_10], rdi
0x18004ea5e  push    rbp
0x18004ea5f  mov     rbp, rsp
0x18004ea62  sub     rsp, 50h
0x18004ea66  mov     [rbp+arg_0], 0
0x18004ea6d  mov     [rbp+hCertStore], 0
0x18004ea75  mov     [rbp+pCertContext], 0
0x18004ea7d  mov     [rbp+hKey], 0
0x18004ea85  lea     rax, aCmachineenroll_16; "CMachineEnroller::DeleteCertWithContain"...
0x18004ea8c  mov     [rbp+var_10], rax
0x18004ea90  lea     rax, [rbp+arg_0]
0x18004ea94  mov     [rbp+var_8], rax
0x18004ea98  test    rcx, rcx
0x18004ea9b  jnz     short loc_18004EAA9
0x18004ea9d  mov     [rbp+arg_0], 80070057h
0x18004eaa4  jmp     loc_18004EB46
0x18004eaa9  lea     rax, [rbp+hKey]
0x18004eaad  mov     [rsp+50h+var_28], rax; unsigned __int64 *
0x18004eab2  lea     rax, [rbp+pCertContext]
0x18004eab6  mov     [rsp+50h+var_30], rax; struct _CERT_CONTEXT **
0x18004eabb  lea     r9, [rbp+hCertStore]; void **
0x18004eabf  call    ?FindCertBasedOnContainer@@YAJPEBG0KPEAPEAXPEAPEBU_CERT_CONTEXT@@PEA_K@Z; FindCertBasedOnContainer(ushort const *,ushort const *,ulong,void * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x18004eac4  mov     [rbp+arg_0], eax
0x18004eac7  mov     rdi, [rbp+pCertContext]
0x18004eacb  mov     rcx, rdi; pCertContext
0x18004eace  call    cs:__imp_CertDeleteCertificateFromStore
0x18004ead4  test    eax, eax
0x18004ead6  jnz     short loc_18004EAF3
0x18004ead8  call    cs:__imp_GetLastError
0x18004eade  test    eax, eax
0x18004eae0  jle     short loc_18004EAEA
0x18004eae2  movzx   eax, ax
0x18004eae5  or      eax, 80070000h
0x18004eaea  mov     [rbp+arg_0], eax
0x18004eaed  mov     rbx, [rbp+hKey]
0x18004eaf1  jmp     short loc_18004EB19
0x18004eaf3  xor     edi, edi
0x18004eaf5  xor     edx, edx; dwFlags
0x18004eaf7  mov     rbx, [rbp+hKey]
0x18004eafb  mov     rcx, rbx; hKey
0x18004eafe  call    cs:__imp_NCryptDeleteKey
0x18004eb04  test    eax, eax
0x18004eb06  jz      short loc_18004EB17
0x18004eb08  jle     short loc_18004EB12
0x18004eb0a  movzx   eax, ax
0x18004eb0d  or      eax, 80070000h
0x18004eb12  mov     [rbp+arg_0], eax
0x18004eb15  jmp     short loc_18004EB27
0x18004eb17  xor     ebx, ebx
0x18004eb19  test    rdi, rdi
0x18004eb1c  jz      short loc_18004EB27
0x18004eb1e  mov     rcx, rdi; pCertContext
0x18004eb21  call    cs:__imp_CertFreeCertificateContext
0x18004eb27  mov     rcx, [rbp+hCertStore]; hCertStore
0x18004eb2b  test    rcx, rcx
0x18004eb2e  jz      short loc_18004EB38
0x18004eb30  xor     edx, edx; dwFlags
0x18004eb32  call    cs:__imp_CertCloseStore
0x18004eb38  test    rbx, rbx
0x18004eb3b  jz      short loc_18004EB46
0x18004eb3d  mov     rcx, rbx; hObject
0x18004eb40  call    cs:__imp_NCryptFreeObject
0x18004eb46  mov     ebx, [rbp+arg_0]
0x18004eb49  lea     rcx, [rbp+var_10]; this
0x18004eb4d  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004eb52  mov     eax, ebx
0x18004eb54  mov     rbx, [rsp+50h+arg_8]
0x18004eb59  mov     rdi, [rsp+50h+arg_10]
0x18004eb5e  add     rsp, 50h
0x18004eb62  pop     rbp
0x18004eb63  retn
```
