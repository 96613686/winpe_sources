# DevAuthSignHash

- ea: `0x180002b38`
- end: `0x180002c3c`
- name: `DevAuthSignHash`
- size: `260`
- prototype: `_BOOL8 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR, __int64, PUCHAR pbOutput)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e04`
- `0x1800036a0`
- `0x1800037ac`

## callees

- `0x180002b38`

## import_xrefs

- `cng!BCryptDestroyKey` at `0x180002c0b`
- `cng!BCryptDestroyKey` at `0x180002c0b`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002b74`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002b74`
- `cng!BCryptSignHash` at `0x180002bee`
- `cng!BCryptSignHash` at `0x180002bee`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002c22`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002c22`
- `cng!BCryptImportKeyPair` at `0x180002ba2`
- `cng!BCryptImportKeyPair` at `0x180002ba2`

## pseudocode

```c
_BOOL8 __fastcall DevAuthSignHash(PUCHAR pbInput, ULONG cbInput, PUCHAR a3, __int64 a4, PUCHAR pbOutput)
{
  BOOL v5; // ebx
  const WCHAR *pPaddingInfo; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+90h] [rbp+40h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+48h] BYREF

  v5 = 0;
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  pPaddingInfo = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", 0, 0) >= 0
    && BCryptImportKeyPair(phAlgorithm, 0, L"RSAPRIVATEBLOB", &phKey, pbInput, cbInput, 0) >= 0 )
  {
    pPaddingInfo = L"SHA256";
    v5 = BCryptSignHash(phKey, &pPaddingInfo, a3, 0x20u, pbOutput, 0x100u, &pcbResult, 2u) >= 0;
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v5;
}

```

## disassembly

```asm
0x180002b38  mov     [rsp-28h+pcbResult], r9d
0x180002b3d  push    rbp
0x180002b3e  push    rbx
0x180002b3f  push    rsi
0x180002b40  push    rdi
0x180002b41  push    r14
0x180002b43  mov     rbp, rsp
0x180002b46  sub     rsp, 50h
0x180002b4a  xor     ebx, ebx
0x180002b4c  mov     r14, r8
0x180002b4f  mov     edi, edx
0x180002b51  mov     [rbp+phAlgorithm], rbx
0x180002b55  mov     rsi, rcx
0x180002b58  mov     [rbp+phKey], rbx
0x180002b5c  xor     r8d, r8d; pszImplementation
0x180002b5f  mov     [rbp+pcbResult], ebx
0x180002b62  lea     rdx, aRsa; "RSA"
0x180002b69  mov     [rbp+pPaddingInfo], rbx
0x180002b6d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180002b71  xor     r9d, r9d; dwFlags
0x180002b74  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180002b7b  nop     dword ptr [rax+rax+00h]
0x180002b80  test    eax, eax
0x180002b82  js      short loc_180002C02
0x180002b84  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002b88  lea     r9, [rbp+phKey]; phKey
0x180002b8c  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x180002b90  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180002b97  mov     [rsp+50h+cbInput], edi; cbInput
0x180002b9b  xor     edx, edx; hImportKey
0x180002b9d  mov     [rsp+50h+pbInput], rsi; pbInput
0x180002ba2  call    cs:__imp_BCryptImportKeyPair
0x180002ba9  nop     dword ptr [rax+rax+00h]
0x180002bae  test    eax, eax
0x180002bb0  js      short loc_180002C02
0x180002bb2  mov     rcx, [rbp+phKey]; hKey
0x180002bb6  lea     rax, pszAlgId; "SHA256"
0x180002bbd  mov     [rbp+pPaddingInfo], rax
0x180002bc1  lea     r9d, [rbx+20h]; cbInput
0x180002bc5  mov     [rsp+50h+var_18], 2; dwFlags
0x180002bcd  lea     rax, [rbp+pcbResult]
0x180002bd1  mov     qword ptr [rsp+50h+dwFlags], rax; pcbResult
0x180002bd6  lea     rdx, [rbp+pPaddingInfo]; pPaddingInfo
0x180002bda  mov     rax, [rbp+pbOutput]
0x180002bde  mov     r8, r14; pbInput
0x180002be1  mov     [rsp+50h+cbInput], 100h; cbOutput
0x180002be9  mov     [rsp+50h+pbInput], rax; pbOutput
0x180002bee  call    cs:__imp_BCryptSignHash
0x180002bf5  nop     dword ptr [rax+rax+00h]
0x180002bfa  test    eax, eax
0x180002bfc  lea     ecx, [rbx+1]
0x180002bff  cmovns  ebx, ecx
0x180002c02  mov     rcx, [rbp+phKey]; hKey
0x180002c06  test    rcx, rcx
0x180002c09  jz      short loc_180002C17
0x180002c0b  call    cs:__imp_BCryptDestroyKey
0x180002c12  nop     dword ptr [rax+rax+00h]
0x180002c17  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002c1b  test    rcx, rcx
0x180002c1e  jz      short loc_180002C2E
0x180002c20  xor     edx, edx; dwFlags
0x180002c22  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002c29  nop     dword ptr [rax+rax+00h]
0x180002c2e  mov     eax, ebx
0x180002c30  add     rsp, 50h
0x180002c34  pop     r14
0x180002c36  pop     rdi
0x180002c37  pop     rsi
0x180002c38  pop     rbx
0x180002c39  pop     rbp
0x180002c3a  retn
```
