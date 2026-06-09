# CertPropDeleteRootCertFromStore

- ea: `0x180017a9c`
- end: `0x180017aff`
- name: `CertPropDeleteRootCertFromStore`
- size: `99`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, HANDLE Token)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006750`
- `0x180014a30`

## callees

- `0x180017a9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ae2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017aec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017ab2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017ab2`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180017ac6`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180017ac6`

## pseudocode

```c
__int64 __fastcall CertPropDeleteRootCertFromStore(PCCERT_CONTEXT pCertContext, HANDLE Token)
{
  int v2; // edi
  DWORD LastError; // ebx

  v2 = 0;
  if ( Token )
  {
    if ( !RevertToSelf() )
      return GetLastError();
    v2 = 1;
  }
  LastError = 0;
  if ( !CertDeleteCertificateFromStore(pCertContext) )
    LastError = GetLastError();
  if ( v2 == 1 && !SetThreadToken(0, Token) )
    return GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x180017a9c  push    rbx
0x180017a9e  push    rbp
0x180017a9f  push    rsi
0x180017aa0  push    rdi
0x180017aa1  sub     rsp, 28h
0x180017aa5  xor     edi, edi
0x180017aa7  mov     rsi, rdx
0x180017aaa  mov     rbp, rcx
0x180017aad  test    rdx, rdx
0x180017ab0  jz      short loc_180017AC1
0x180017ab2  call    cs:__imp_RevertToSelf
0x180017ab8  test    eax, eax
0x180017aba  jz      short loc_180017AEC
0x180017abc  mov     edi, 1
0x180017ac1  mov     rcx, rbp; pCertContext
0x180017ac4  xor     ebx, ebx
0x180017ac6  call    cs:__imp_CertDeleteCertificateFromStore
0x180017acc  test    eax, eax
0x180017ace  jnz     short loc_180017AD8
0x180017ad0  call    cs:__imp_GetLastError
0x180017ad6  mov     ebx, eax
0x180017ad8  cmp     edi, 1
0x180017adb  jnz     short loc_180017AF4
0x180017add  mov     rdx, rsi; Token
0x180017ae0  xor     ecx, ecx; Thread
0x180017ae2  call    cs:__imp_SetThreadToken
0x180017ae8  test    eax, eax
0x180017aea  jnz     short loc_180017AF4
0x180017aec  call    cs:__imp_GetLastError
0x180017af2  mov     ebx, eax
0x180017af4  mov     eax, ebx
0x180017af6  add     rsp, 28h
0x180017afa  pop     rdi
0x180017afb  pop     rsi
0x180017afc  pop     rbp
0x180017afd  pop     rbx
0x180017afe  retn
```
