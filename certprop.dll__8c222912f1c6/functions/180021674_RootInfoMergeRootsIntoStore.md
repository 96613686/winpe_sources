# RootInfoMergeRootsIntoStore

- ea: `0x180021674`
- end: `0x180021840`
- name: `RootInfoMergeRootsIntoStore`
- size: `460`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800103f0`

## callees

- `0x18002139c`
- `0x1800214a8`
- `0x180021674`
- `0x180021848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800217ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800216c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800216c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800216af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800216af`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021811`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021820`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800216d1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800216d1`
- `CRYPT32!CertFindCertificateInStore` at `0x180021715`
- `CRYPT32!CertFindCertificateInStore` at `0x180021715`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800216e4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800216e4`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800217c9`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800217c9`
- `CRYPT32!CertFreeCertificateContext` at `0x180021752`
- `CRYPT32!CertFreeCertificateContext` at `0x1800217e8`
- `CRYPT32!CertFreeCertificateContext` at `0x180021752`
- `CRYPT32!CertFreeCertificateContext` at `0x1800217e8`

## pseudocode

```c
__int64 __fastcall RootInfoMergeRootsIntoStore(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  DWORD LastError; // ebx
  void *v8; // rdi
  const CERT_CONTEXT *v11; // rsi
  BOOL v12; // r14d
  HANDLE CurrentThread; // rax
  PCCERT_CONTEXT v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  const CERT_CONTEXT *CertificateInStore; // r15
  int v18; // edx
  int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int *pvFindPara; // [rsp+20h] [rbp-20h]
  void *TokenHandle; // [rsp+80h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+48h] BYREF

  LastError = 0;
  v8 = 0;
  lpMem = 0;
  a7 = 0;
  TokenHandle = 0;
  v11 = 0;
  v12 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    v12 = RevertToSelf();
  while ( 1 )
  {
    v14 = CertEnumCertificatesInStore(a3, v11);
    v11 = v14;
    if ( !v14 )
      break;
    CertificateInStore = CertFindCertificateInStore(a4, 0x10001u, 0, 0xD0000u, v14, 0);
    if ( CertificateInStore )
    {
      pvFindPara = &a7;
      LastError = RootInfoGet(v16, v15, CertificateInStore, &lpMem);
      CertFreeCertificateContext(CertificateInStore);
      if ( LastError )
        goto LABEL_12;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != -2146885628 )
        goto LABEL_13;
    }
    LastError = RootInfoCreateNew(v19, v18, a5, a6, (_DWORD)pvFindPara, (__int64)&lpMem, (__int64)&a7);
    if ( LastError )
    {
LABEL_12:
      v8 = lpMem;
LABEL_13:
      CertFreeCertificateContext(v11);
      if ( v8 )
        HeapFree(g_hHeap, 0, v8);
      break;
    }
    v8 = lpMem;
    LastError = RootInfoSet(v21, v20, v11, lpMem, a7);
    if ( LastError )
      goto LABEL_13;
    HeapFree(g_hHeap, 0, v8);
    v8 = 0;
    lpMem = 0;
    a7 = 0;
    if ( !CertAddCertificateContextToStore(a4, v11, 3u, 0) )
    {
      LastError = GetLastError();
      goto LABEL_13;
    }
  }
  if ( v12 )
    SetThreadToken(0, TokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180021674  mov     [rsp-38h+arg_10], rbx
0x180021679  mov     [rsp-38h+lpMem], rdx
0x18002167e  mov     [rsp-38h+TokenHandle], rcx
0x180021683  push    rbp
0x180021684  push    rsi
0x180021685  push    rdi
0x180021686  push    r12
0x180021688  push    r13
0x18002168a  push    r14
0x18002168c  push    r15
0x18002168e  mov     rbp, rsp
0x180021691  sub     rsp, 40h
0x180021695  xor     ebx, ebx
0x180021697  xor     edi, edi
0x180021699  mov     [rbp+lpMem], rdi
0x18002169d  mov     r12, r9
0x1800216a0  mov     [rbp+arg_30], ebx
0x1800216a3  mov     r13, r8
0x1800216a6  mov     [rbp+TokenHandle], rbx
0x1800216aa  xor     esi, esi
0x1800216ac  xor     r14d, r14d
0x1800216af  call    cs:__imp_GetCurrentThread
0x1800216b5  lea     r15d, [rbx+1]
0x1800216b9  mov     rcx, rax; ThreadHandle
0x1800216bc  mov     r8d, r15d; OpenAsSelf
0x1800216bf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800216c3  lea     edx, [rbx+4]; DesiredAccess
0x1800216c6  call    cs:__imp_OpenThreadToken
0x1800216cc  cmp     eax, r15d
0x1800216cf  jnz     short loc_1800216DE
0x1800216d1  call    cs:__imp_RevertToSelf
0x1800216d7  cmp     eax, r15d
0x1800216da  cmovz   r14d, r15d
0x1800216de  mov     rdx, rsi; pPrevCertContext
0x1800216e1  mov     rcx, r13; hCertStore
0x1800216e4  call    cs:__imp_CertEnumCertificatesInStore
0x1800216ea  mov     rsi, rax
0x1800216ed  test    rax, rax
0x1800216f0  jz      loc_180021805
0x1800216f6  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x1800216ff  mov     r9d, 0D0000h; dwFindType
0x180021705  xor     r8d, r8d; dwFindFlags
0x180021708  mov     [rsp+40h+pvFindPara], rax; pvFindPara
0x18002170d  mov     edx, 10001h; dwCertEncodingType
0x180021712  mov     rcx, r12; hCertStore
0x180021715  call    cs:__imp_CertFindCertificateInStore
0x18002171b  mov     r15, rax
0x18002171e  test    rax, rax
0x180021721  jnz     short loc_180021738
0x180021723  call    cs:__imp_GetLastError
0x180021729  mov     ebx, eax
0x18002172b  cmp     eax, 80092004h
0x180021730  jnz     loc_1800217E5
0x180021736  jmp     short loc_180021760
0x180021738  lea     rax, [rbp+arg_30]
0x18002173c  mov     r8, r15
0x18002173f  lea     r9, [rbp+lpMem]
0x180021743  mov     [rsp+40h+pvFindPara], rax
0x180021748  call    RootInfoGet
0x18002174d  mov     rcx, r15; pCertContext
0x180021750  mov     ebx, eax
0x180021752  call    cs:__imp_CertFreeCertificateContext
0x180021758  test    ebx, ebx
0x18002175a  jnz     loc_1800217E1
0x180021760  mov     r9, [rbp+arg_28]
0x180021764  lea     rax, [rbp+arg_30]
0x180021768  mov     r8, [rbp+arg_20]
0x18002176c  mov     [rsp+40h+var_10], rax
0x180021771  lea     rax, [rbp+lpMem]
0x180021775  mov     [rsp+40h+pPrevCertContext], rax
0x18002177a  call    RootInfoCreateNew
0x18002177f  mov     ebx, eax
0x180021781  test    eax, eax
0x180021783  jnz     short loc_1800217E1
0x180021785  mov     eax, [rbp+arg_30]
0x180021788  mov     r8, rsi
0x18002178b  mov     rdi, [rbp+lpMem]
0x18002178f  mov     r9, rdi
0x180021792  mov     dword ptr [rsp+40h+pvFindPara], eax
0x180021796  call    RootInfoSet
0x18002179b  mov     ebx, eax
0x18002179d  test    eax, eax
0x18002179f  jnz     short loc_1800217E5
0x1800217a1  mov     rcx, cs:g_hHeap; hHeap
0x1800217a8  mov     r8, rdi; lpMem
0x1800217ab  xor     edx, edx; dwFlags
0x1800217ad  call    cs:__imp_HeapFree
0x1800217b3  xor     edi, edi
0x1800217b5  lea     r8d, [rbx+3]; dwAddDisposition
0x1800217b9  xor     r9d, r9d; ppStoreContext
0x1800217bc  mov     [rbp+lpMem], rdi
0x1800217c0  mov     rdx, rsi; pCertContext
0x1800217c3  mov     [rbp+arg_30], edi
0x1800217c6  mov     rcx, r12; hCertStore
0x1800217c9  call    cs:__imp_CertAddCertificateContextToStore
0x1800217cf  test    eax, eax
0x1800217d1  jnz     loc_1800216DE
0x1800217d7  call    cs:__imp_GetLastError
0x1800217dd  mov     ebx, eax
0x1800217df  jmp     short loc_1800217E5
0x1800217e1  mov     rdi, [rbp+lpMem]
0x1800217e5  mov     rcx, rsi; pCertContext
0x1800217e8  call    cs:__imp_CertFreeCertificateContext
0x1800217ee  test    rdi, rdi
0x1800217f1  jz      short loc_180021805
0x1800217f3  mov     rcx, cs:g_hHeap; hHeap
0x1800217fa  mov     r8, rdi; lpMem
0x1800217fd  xor     edx, edx; dwFlags
0x1800217ff  call    cs:__imp_HeapFree
0x180021805  cmp     r14d, 1
0x180021809  jnz     short loc_180021817
0x18002180b  mov     rdx, [rbp+TokenHandle]; Token
0x18002180f  xor     ecx, ecx; Thread
0x180021811  call    cs:__imp_SetThreadToken
0x180021817  mov     rcx, [rbp+TokenHandle]; hObject
0x18002181b  test    rcx, rcx
0x18002181e  jz      short loc_180021826
0x180021820  call    cs:__imp_CloseHandle
0x180021826  mov     eax, ebx
0x180021828  mov     rbx, [rsp+40h+arg_10]
0x180021830  add     rsp, 40h
0x180021834  pop     r15
0x180021836  pop     r14
0x180021838  pop     r13
0x18002183a  pop     r12
0x18002183c  pop     rdi
0x18002183d  pop     rsi
0x18002183e  pop     rbp
0x18002183f  retn
```
