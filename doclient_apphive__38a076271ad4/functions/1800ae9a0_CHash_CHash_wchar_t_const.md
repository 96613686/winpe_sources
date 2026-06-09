# CHash::CHash(wchar_t const *)

- ea: `0x1800ae9a0`
- end: `0x1800aeaa9`
- name: `??0CHash@@QEAA@PEB_W@Z`
- size: `265`
- prototype: `CHash *__fastcall(BCRYPT_HASH_HANDLE *phHash, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002123c`
- `0x18007f57c`
- `0x1800aa3b0`

## callees

- `0x1800ae9a0`
- `0x1800aede8`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aea02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aea15`
- `bcrypt!BCryptDestroyHash` at `0x1800aea0d`
- `bcrypt!BCryptDestroyHash` at `0x1800aea0d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800aea64`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800aea64`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800ae9e7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800ae9e7`
- `bcrypt!BCryptCreateHash` at `0x1800aea49`
- `bcrypt!BCryptCreateHash` at `0x1800aea49`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BCRYPT_HASH_HANDLE *__fastcall CHash::CHash(BCRYPT_HASH_HANDLE *phHash, const wchar_t *a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // r8d
  BCRYPT_HASH_HANDLE v5; // rsi
  DWORD LastError; // ebx
  NTSTATUS Hash; // eax
  unsigned int v8; // r8d
  int pbSecret; // [rsp+20h] [rbp-48h]
  int pbSecreta; // [rsp+20h] [rbp-48h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *phHash = 0;
  phHash[1] = 0;
  hAlgorithm = 0;
  v3 = BCryptOpenAlgorithmProvider(&hAlgorithm, a2, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xD, v4, (const char *)(unsigned int)v3, pbSecret);
  v5 = *phHash;
  if ( *phHash )
  {
    LastError = GetLastError();
    BCryptDestroyHash(v5);
    SetLastError(LastError);
  }
  *phHash = 0;
  Hash = BCryptCreateHash(hAlgorithm, phHash, 0, 0, 0, 0, 0x20u);
  if ( Hash < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xE, v8, (const char *)(unsigned int)Hash, pbSecreta);
  if ( hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return phHash;
}

```

## disassembly

```asm
0x1800ae9a0  mov     r11, rsp
0x1800ae9a3  mov     [r11+18h], rbx
0x1800ae9a7  mov     [r11+20h], rsi
0x1800ae9ab  push    rdi
0x1800ae9ac  sub     rsp, 60h
0x1800ae9b0  mov     rax, cs:__security_cookie
0x1800ae9b7  xor     rax, rsp
0x1800ae9ba  mov     [rsp+68h+var_18], rax
0x1800ae9bf  mov     rdi, rcx
0x1800ae9c2  mov     [r11-28h], rcx
0x1800ae9c6  mov     qword ptr [rcx], 0
0x1800ae9cd  mov     qword ptr [rcx+8], 0
0x1800ae9d5  mov     qword ptr [r11-20h], 0
0x1800ae9dd  xor     r9d, r9d; dwFlags
0x1800ae9e0  xor     r8d, r8d; pszImplementation
0x1800ae9e3  lea     rcx, [r11-20h]; phAlgorithm
0x1800ae9e7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800ae9ed  mov     rcx, [rsp+68h]; this
0x1800ae9f2  test    eax, eax
0x1800ae9f4  js      loc_1800AEA9B
0x1800ae9fa  mov     rsi, [rdi]
0x1800ae9fd  test    rsi, rsi
0x1800aea00  jz      short loc_1800AEA1B
0x1800aea02  call    cs:__imp_GetLastError
0x1800aea08  mov     ebx, eax
0x1800aea0a  mov     rcx, rsi; hHash
0x1800aea0d  call    cs:__imp_BCryptDestroyHash
0x1800aea13  mov     ecx, ebx; dwErrCode
0x1800aea15  call    cs:__imp_SetLastError
0x1800aea1b  mov     qword ptr [rdi], 0
0x1800aea22  mov     [rsp+68h+dwFlags], 20h ; ' '; dwFlags
0x1800aea2a  mov     [rsp+68h+cbSecret], 0; cbSecret
0x1800aea32  mov     [rsp+68h+pbSecret], 0; int
0x1800aea3b  xor     r9d, r9d; cbHashObject
0x1800aea3e  xor     r8d, r8d; pbHashObject
0x1800aea41  mov     rdx, rdi; phHash
0x1800aea44  mov     rcx, [rsp+68h+hAlgorithm]; hAlgorithm
0x1800aea49  call    cs:__imp_BCryptCreateHash
0x1800aea4f  mov     rcx, [rsp+68h]; this
0x1800aea54  test    eax, eax
0x1800aea56  js      short loc_1800AEA8D
0x1800aea58  mov     rcx, [rsp+68h+hAlgorithm]; hAlgorithm
0x1800aea5d  test    rcx, rcx
0x1800aea60  jz      short loc_1800AEA6B
0x1800aea62  xor     edx, edx; dwFlags
0x1800aea64  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800aea6a  nop
0x1800aea6b  mov     rax, rdi
0x1800aea6e  mov     rcx, [rsp+68h+var_18]
0x1800aea73  xor     rcx, rsp; StackCookie
0x1800aea76  call    __security_check_cookie
0x1800aea7b  lea     r11, [rsp+68h+var_8]
0x1800aea80  mov     rbx, [r11+20h]
0x1800aea84  mov     rsi, [r11+28h]
0x1800aea88  mov     rsp, r11
0x1800aea8b  pop     rdi
0x1800aea8c  retn
0x1800aea8d  mov     r9d, eax; char *
0x1800aea90  mov     edx, 0Eh; void *
0x1800aea95  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800aea9b  mov     r9d, eax; char *
0x1800aea9e  mov     edx, 0Dh; void *
0x1800aeaa3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
