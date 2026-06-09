# HTTPStream::SelectCertificate(void)

- ea: `0x1800f47d8`
- end: `0x1800f4929`
- name: `?SelectCertificate@HTTPStream@@IEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(HTTPStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f4950`

## callees

- `0x1800f47d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f48ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f48ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f4809`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f4809`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800f48e2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800f48e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f47f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f47f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4906`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4906`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f4813`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f4813`
- `WINHTTP!WinHttpSetOption` at `0x1800f48b1`
- `WINHTTP!WinHttpSetOption` at `0x1800f48b1`
- `CRYPT32!CertCloseStore` at `0x1800f48c8`
- `CRYPT32!CertCloseStore` at `0x1800f48c8`
- `CRYPT32!CertFreeCertificateContext` at `0x1800f48bd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800f48bd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800f4892`
- `CRYPT32!CertFindCertificateInStore` at `0x1800f4892`
- `CRYPT32!CertOpenStore` at `0x1800f486c`
- `CRYPT32!CertOpenStore` at `0x1800f486c`

## pseudocode

```c
__int64 __fastcall HTTPStream::SelectCertificate(HINTERNET *this)
{
  BOOL v1; // r14d
  char v3; // bp
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  HCERTSTORE v7; // rax
  void *v8; // rdi
  CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v10; // rsi
  void *v11; // rcx
  signed int v12; // eax
  void *TokenHandle; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) )
  {
    if ( !RevertToSelf() )
    {
      v3 = 1;
      goto LABEL_4;
    }
  }
  else
  {
    TokenHandle = 0;
    if ( GetLastError() != 1008 )
    {
LABEL_4:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_11;
    }
  }
  v6 = 0;
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x1C000u, L"MY");
  v8 = v7;
  if ( v7 )
  {
    CertificateInStore = (CERT_CONTEXT *)CertFindCertificateInStore(v7, 0x10001u, 0, 0, 0, 0);
    v10 = CertificateInStore;
    if ( CertificateInStore )
    {
      v1 = WinHttpSetOption(this[22], 0x2Fu, CertificateInStore, 0x28u);
      CertFreeCertificateContext(v10);
    }
    CertCloseStore(v8, 0);
  }
LABEL_11:
  v11 = TokenHandle;
  if ( TokenHandle )
  {
    if ( !v3 )
    {
      if ( !SetThreadToken(0, TokenHandle) )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
      v11 = TokenHandle;
    }
    CloseHandle(v11);
  }
  if ( v6 >= 0 )
    return !v1;
  else
    return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f47d8  push    rbx
0x1800f47da  push    rbp
0x1800f47db  push    rsi
0x1800f47dc  push    rdi
0x1800f47dd  push    r14
0x1800f47df  push    r15
0x1800f47e1  sub     rsp, 38h
0x1800f47e5  xor     r14d, r14d
0x1800f47e8  mov     r15, rcx
0x1800f47eb  mov     [rsp+68h+TokenHandle], r14
0x1800f47f0  xor     bpl, bpl
0x1800f47f3  call    cs:__imp_GetCurrentThread
0x1800f47f9  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800f47fe  xor     r8d, r8d; OpenAsSelf
0x1800f4801  mov     rcx, rax; ThreadHandle
0x1800f4804  mov     edx, 2000Ch; DesiredAccess
0x1800f4809  call    cs:__imp_OpenThreadToken
0x1800f480f  test    eax, eax
0x1800f4811  jz      short loc_1800F483E
0x1800f4813  call    cs:__imp_RevertToSelf
0x1800f4819  test    eax, eax
0x1800f481b  jnz     short loc_1800F4850
0x1800f481d  mov     bpl, 1
0x1800f4820  call    cs:__imp_GetLastError
0x1800f4826  mov     ebx, eax
0x1800f4828  test    eax, eax
0x1800f482a  jle     loc_1800F48CE
0x1800f4830  movzx   ebx, ax
0x1800f4833  or      ebx, 80070000h
0x1800f4839  jmp     loc_1800F48CE
0x1800f483e  mov     [rsp+68h+TokenHandle], r14
0x1800f4843  call    cs:__imp_GetLastError
0x1800f4849  cmp     eax, 3F0h
0x1800f484e  jnz     short loc_1800F4820
0x1800f4850  lea     rax, aMy; "MY"
0x1800f4857  xor     ebx, ebx
0x1800f4859  mov     r9d, 1C000h; dwFlags
0x1800f485f  mov     [rsp+68h+pvPara], rax; pvPara
0x1800f4864  xor     r8d, r8d; hCryptProv
0x1800f4867  xor     edx, edx; dwEncodingType
0x1800f4869  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x1800f486c  call    cs:__imp_CertOpenStore
0x1800f4872  mov     rdi, rax
0x1800f4875  test    rax, rax
0x1800f4878  jz      short loc_1800F48CE
0x1800f487a  mov     [rsp+68h+pPrevCertContext], rbx; pPrevCertContext
0x1800f487f  xor     r9d, r9d; dwFindType
0x1800f4882  xor     r8d, r8d; dwFindFlags
0x1800f4885  mov     [rsp+68h+pvPara], rbx; pvFindPara
0x1800f488a  mov     edx, 10001h; dwCertEncodingType
0x1800f488f  mov     rcx, rax; hCertStore
0x1800f4892  call    cs:__imp_CertFindCertificateInStore
0x1800f4898  mov     rsi, rax
0x1800f489b  test    rax, rax
0x1800f489e  jz      short loc_1800F48C3
0x1800f48a0  mov     rcx, [r15+0B0h]; hInternet
0x1800f48a7  lea     r9d, [rbx+28h]; dwBufferLength
0x1800f48ab  mov     r8, rax; lpBuffer
0x1800f48ae  lea     edx, [rbx+2Fh]; dwOption
0x1800f48b1  call    cs:__imp_WinHttpSetOption
0x1800f48b7  mov     r14d, eax
0x1800f48ba  mov     rcx, rsi; pCertContext
0x1800f48bd  call    cs:__imp_CertFreeCertificateContext
0x1800f48c3  xor     edx, edx; dwFlags
0x1800f48c5  mov     rcx, rdi; hCertStore
0x1800f48c8  call    cs:__imp_CertCloseStore
0x1800f48ce  mov     rcx, [rsp+68h+TokenHandle]
0x1800f48d3  test    rcx, rcx
0x1800f48d6  jz      short loc_1800F490C
0x1800f48d8  test    bpl, bpl
0x1800f48db  jnz     short loc_1800F4906
0x1800f48dd  mov     rdx, rcx; Token
0x1800f48e0  xor     ecx, ecx; Thread
0x1800f48e2  call    cs:__imp_SetThreadToken
0x1800f48e8  test    eax, eax
0x1800f48ea  jnz     short loc_1800F4901
0x1800f48ec  call    cs:__imp_GetLastError
0x1800f48f2  mov     ebx, eax
0x1800f48f4  test    eax, eax
0x1800f48f6  jle     short loc_1800F4901
0x1800f48f8  movzx   ebx, ax
0x1800f48fb  or      ebx, 80070000h
0x1800f4901  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800f4906  call    cs:__imp_CloseHandle
0x1800f490c  test    ebx, ebx
0x1800f490e  jns     short loc_1800F4914
0x1800f4910  mov     eax, ebx
0x1800f4912  jmp     short loc_1800F491C
0x1800f4914  xor     eax, eax
0x1800f4916  test    r14d, r14d
0x1800f4919  setz    al
0x1800f491c  add     rsp, 38h
0x1800f4920  pop     r15
0x1800f4922  pop     r14
0x1800f4924  pop     rdi
0x1800f4925  pop     rsi
0x1800f4926  pop     rbp
0x1800f4927  pop     rbx
0x1800f4928  retn
```
