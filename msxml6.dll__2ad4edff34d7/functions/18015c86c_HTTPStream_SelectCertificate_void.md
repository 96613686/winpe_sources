# HTTPStream::SelectCertificate(void)

- ea: `0x18015c86c`
- end: `0x18015c9bd`
- name: `?SelectCertificate@HTTPStream@@IEAAJXZ`
- size: `337`
- prototype: `HRESULT __fastcall(HTTPStream *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18015c9d0`

## callees

- `0x18015c86c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015c980`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18015c89d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18015c89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015c887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015c887`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18015c976`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18015c976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015c99a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015c99a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18015c8a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18015c8a7`
- `WINHTTP!WinHttpSetOption` at `0x18015c945`
- `WINHTTP!WinHttpSetOption` at `0x18015c945`
- `CRYPT32!CertFindCertificateInStore` at `0x18015c926`
- `CRYPT32!CertFindCertificateInStore` at `0x18015c926`
- `CRYPT32!CertFreeCertificateContext` at `0x18015c951`
- `CRYPT32!CertFreeCertificateContext` at `0x18015c951`
- `CRYPT32!CertCloseStore` at `0x18015c95c`
- `CRYPT32!CertCloseStore` at `0x18015c95c`
- `CRYPT32!CertOpenStore` at `0x18015c900`
- `CRYPT32!CertOpenStore` at `0x18015c900`

## pseudocode

```c
__int64 __fastcall HTTPStream::SelectCertificate(HTTPStream *this)
{
  BOOL v1; // r14d
  char v3; // bp
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  HCERTSTORE v7; // rax
  void *v8; // rdi
  PCCERT_CONTEXT CertificateInStore; // rax
  const _CERT_CONTEXT *v10; // rsi
  void *v11; // rcx
  signed int v12; // eax
  void *hThreadToken; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  hThreadToken = 0;
  v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &hThreadToken) )
  {
    if ( !RevertToSelf() )
    {
      v3 = 1;
      goto LABEL_4;
    }
  }
  else
  {
    hThreadToken = 0;
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
    CertificateInStore = CertFindCertificateInStore(v7, 0x10001u, 0, 0, 0, 0);
    v10 = CertificateInStore;
    if ( CertificateInStore )
    {
      v1 = WinHttpSetOption(this->_hHTTP, 0x2Fu, (LPVOID)CertificateInStore, 0x28u);
      CertFreeCertificateContext(v10);
    }
    CertCloseStore(v8, 0);
  }
LABEL_11:
  v11 = hThreadToken;
  if ( hThreadToken )
  {
    if ( !v3 )
    {
      if ( !SetThreadToken(0, hThreadToken) )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
      v11 = hThreadToken;
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
0x18015c86c  push    rbx
0x18015c86e  push    rbp
0x18015c86f  push    rsi
0x18015c870  push    rdi
0x18015c871  push    r14
0x18015c873  push    r15
0x18015c875  sub     rsp, 38h
0x18015c879  xor     r14d, r14d
0x18015c87c  mov     r15, this
0x18015c87f  mov     [rsp+68h+hThreadToken], r14
0x18015c884  xor     bpl, bpl
0x18015c887  call    cs:__imp_GetCurrentThread
0x18015c88d  lea     r9, [rsp+68h+hThreadToken]; TokenHandle
0x18015c892  xor     r8d, r8d; OpenAsSelf
0x18015c895  mov     this, rax; ThreadHandle
0x18015c898  mov     edx, 2000Ch; DesiredAccess
0x18015c89d  call    cs:__imp_OpenThreadToken
0x18015c8a3  test    eax, eax
0x18015c8a5  jz      short loc_18015C8D2
0x18015c8a7  call    cs:__imp_RevertToSelf
0x18015c8ad  test    eax, eax
0x18015c8af  jnz     short loc_18015C8E4
0x18015c8b1  mov     bpl, 1
0x18015c8b4  call    cs:__imp_GetLastError
0x18015c8ba  mov     ebx, eax
0x18015c8bc  test    eax, eax
0x18015c8be  jle     loc_18015C962
0x18015c8c4  movzx   ebx, ax
0x18015c8c7  or      ebx, 80070000h
0x18015c8cd  jmp     loc_18015C962
0x18015c8d2  mov     [rsp+68h+hThreadToken], r14
0x18015c8d7  call    cs:__imp_GetLastError
0x18015c8dd  cmp     eax, 3F0h
0x18015c8e2  jnz     short loc_18015C8B4
0x18015c8e4  lea     rax, aMy; "MY"
0x18015c8eb  xor     ebx, ebx
0x18015c8ed  mov     r9d, 1C000h; dwFlags
0x18015c8f3  mov     [rsp+68h+pvPara], rax; pvPara
0x18015c8f8  xor     r8d, r8d; hCryptProv
0x18015c8fb  xor     edx, edx; dwEncodingType
0x18015c8fd  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18015c900  call    cs:__imp_CertOpenStore
0x18015c906  mov     rdi, rax
0x18015c909  test    rax, rax
0x18015c90c  jz      short loc_18015C962
0x18015c90e  mov     [rsp+68h+pPrevCertContext], rbx; pPrevCertContext
0x18015c913  xor     r9d, r9d; dwFindType
0x18015c916  xor     r8d, r8d; dwFindFlags
0x18015c919  mov     [rsp+68h+pvPara], rbx; pvFindPara
0x18015c91e  mov     edx, 10001h; dwCertEncodingType
0x18015c923  mov     this, rax; hCertStore
0x18015c926  call    cs:__imp_CertFindCertificateInStore
0x18015c92c  mov     rsi, rax
0x18015c92f  test    rax, rax
0x18015c932  jz      short loc_18015C957
0x18015c934  mov     this, [r15+0B0h]; hInternet
0x18015c93b  lea     r9d, [rbx+28h]; dwBufferLength
0x18015c93f  mov     r8, rax; lpBuffer
0x18015c942  lea     edx, [rbx+2Fh]; dwOption
0x18015c945  call    cs:__imp_WinHttpSetOption
0x18015c94b  mov     r14d, eax
0x18015c94e  mov     this, rsi; pCertContext
0x18015c951  call    cs:__imp_CertFreeCertificateContext
0x18015c957  xor     edx, edx; dwFlags
0x18015c959  mov     this, rdi; hCertStore
0x18015c95c  call    cs:__imp_CertCloseStore
0x18015c962  mov     this, [rsp+68h+hThreadToken]
0x18015c967  test    this, this
0x18015c96a  jz      short loc_18015C9A0
0x18015c96c  test    bpl, bpl
0x18015c96f  jnz     short loc_18015C99A
0x18015c971  mov     rdx, this; Token
0x18015c974  xor     ecx, ecx; Thread
0x18015c976  call    cs:__imp_SetThreadToken
0x18015c97c  test    eax, eax
0x18015c97e  jnz     short loc_18015C995
0x18015c980  call    cs:__imp_GetLastError
0x18015c986  mov     ebx, eax
0x18015c988  test    eax, eax
0x18015c98a  jle     short loc_18015C995
0x18015c98c  movzx   ebx, ax
0x18015c98f  or      ebx, 80070000h
0x18015c995  mov     this, [rsp+68h+hThreadToken]; hObject
0x18015c99a  call    cs:__imp_CloseHandle
0x18015c9a0  test    ebx, ebx
0x18015c9a2  jns     short loc_18015C9A8
0x18015c9a4  mov     eax, ebx
0x18015c9a6  jmp     short loc_18015C9B0
0x18015c9a8  xor     eax, eax
0x18015c9aa  test    r14d, r14d
0x18015c9ad  setz    al
0x18015c9b0  add     rsp, 38h
0x18015c9b4  pop     r15
0x18015c9b6  pop     r14
0x18015c9b8  pop     rdi
0x18015c9b9  pop     rsi
0x18015c9ba  pop     rbp
0x18015c9bb  pop     rbx
0x18015c9bc  retn
```
