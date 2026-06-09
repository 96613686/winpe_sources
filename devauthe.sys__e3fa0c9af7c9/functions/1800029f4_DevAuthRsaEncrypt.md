# DevAuthRsaEncrypt

- ea: `0x1800029f4`
- end: `0x180002b30`
- name: `DevAuthRsaEncrypt`
- size: `316`
- prototype: `_BOOL8 __fastcall(void *Src, __int64, UCHAR *, __int64, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002348`

## callees

- `0x1800029f4`
- `0x180002d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180002aec`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002aec`
- `cng!BCryptEncrypt` at `0x180002ace`
- `cng!BCryptEncrypt` at `0x180002ace`
- `cng!BCryptDestroyKey` at `0x180002b01`
- `cng!BCryptDestroyKey` at `0x180002b01`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002a33`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002a33`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002b18`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002b18`
- `cng!BCryptImportKeyPair` at `0x180002a85`
- `cng!BCryptImportKeyPair` at `0x180002a85`

## pseudocode

```c
_BOOL8 __fastcall DevAuthRsaEncrypt(void *Src, __int64 a2, UCHAR *a3, __int64 a4, PUCHAR pbOutput)
{
  BOOL v5; // edi
  int v8; // eax
  PUCHAR v9; // rbx
  PUCHAR pbInput[3]; // [rsp+50h] [rbp-18h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp+28h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+A0h] [rbp+38h] BYREF
  ULONG cbInput; // [rsp+A8h] [rbp+40h] BYREF

  v5 = 0;
  phAlgorithm = 0;
  phKey = 0;
  pbInput[0] = 0;
  cbInput = 0;
  pcbResult = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", 0, 0) >= 0 )
  {
    v8 = CreateCngPublicKeyBlob(Src, 0x100u, (__int64 *)pbInput, &cbInput);
    v9 = pbInput[0];
    if ( v8 && BCryptImportKeyPair(phAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, pbInput[0], cbInput, 0) >= 0 )
      v5 = BCryptEncrypt(phKey, a3, 0x30u, 0, 0, 0, pbOutput, 0x100u, &pcbResult, 2u) >= 0;
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
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
0x1800029f4  mov     [rsp-20h+arg_18], r9d
0x1800029f9  mov     [rsp-20h+arg_8], edx
0x1800029fd  push    rbp
0x1800029fe  push    rbx
0x1800029ff  push    rsi
0x180002a00  push    rdi
0x180002a01  mov     rbp, rsp
0x180002a04  sub     rsp, 68h
0x180002a08  xor     edi, edi
0x180002a0a  lea     rdx, aRsa; "RSA"
0x180002a11  mov     rsi, r8
0x180002a14  mov     [rbp+phAlgorithm], rdi
0x180002a18  mov     rbx, rcx
0x180002a1b  mov     [rbp+phKey], rdi
0x180002a1f  xor     r8d, r8d; pszImplementation
0x180002a22  mov     [rbp+var_18], rdi
0x180002a26  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180002a2a  mov     [rbp+arg_18], edi
0x180002a2d  xor     r9d, r9d; dwFlags
0x180002a30  mov     [rbp+arg_8], edi
0x180002a33  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180002a3a  nop     dword ptr [rax+rax+00h]
0x180002a3f  test    eax, eax
0x180002a41  js      loc_180002AF8
0x180002a47  lea     r9, [rbp+arg_18]
0x180002a4b  mov     edx, 100h; Size
0x180002a50  lea     r8, [rbp+var_18]
0x180002a54  mov     rcx, rbx; Src
0x180002a57  call    _CreateCngPublicKeyBlob
0x180002a5c  mov     rbx, [rbp+var_18]
0x180002a60  test    eax, eax
0x180002a62  jz      short loc_180002AE2
0x180002a64  mov     eax, [rbp+arg_18]
0x180002a67  lea     r9, [rbp+phKey]; phKey
0x180002a6b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002a6f  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180002a76  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180002a7a  xor     edx, edx; hImportKey
0x180002a7c  mov     [rsp+68h+cbInput], eax; cbInput
0x180002a80  mov     [rsp+68h+pbInput], rbx; pbInput
0x180002a85  call    cs:__imp_BCryptImportKeyPair
0x180002a8c  nop     dword ptr [rax+rax+00h]
0x180002a91  test    eax, eax
0x180002a93  js      short loc_180002AE2
0x180002a95  mov     rcx, [rbp+phKey]; hKey
0x180002a99  lea     rax, [rbp+arg_8]
0x180002a9d  mov     [rsp+68h+var_20], 2; dwFlags
0x180002aa5  lea     r8d, [rdi+30h]; cbInput
0x180002aa9  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180002aae  xor     r9d, r9d; pPaddingInfo
0x180002ab1  mov     rax, [rbp+pbOutput]
0x180002ab5  mov     rdx, rsi; pbInput
0x180002ab8  mov     [rsp+68h+cbOutput], 100h; cbOutput
0x180002ac0  mov     qword ptr [rsp+68h+dwFlags], rax; pbOutput
0x180002ac5  mov     [rsp+68h+cbInput], edi; cbIV
0x180002ac9  mov     [rsp+68h+pbInput], rdi; pbIV
0x180002ace  call    cs:__imp_BCryptEncrypt
0x180002ad5  nop     dword ptr [rax+rax+00h]
0x180002ada  test    eax, eax
0x180002adc  lea     ecx, [rdi+1]
0x180002adf  cmovns  edi, ecx
0x180002ae2  test    rbx, rbx
0x180002ae5  jz      short loc_180002AF8
0x180002ae7  xor     edx, edx; Tag
0x180002ae9  mov     rcx, rbx; P
0x180002aec  call    cs:__imp_ExFreePoolWithTag
0x180002af3  nop     dword ptr [rax+rax+00h]
0x180002af8  mov     rcx, [rbp+phKey]; hKey
0x180002afc  test    rcx, rcx
0x180002aff  jz      short loc_180002B0D
0x180002b01  call    cs:__imp_BCryptDestroyKey
0x180002b08  nop     dword ptr [rax+rax+00h]
0x180002b0d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002b11  test    rcx, rcx
0x180002b14  jz      short loc_180002B24
0x180002b16  xor     edx, edx; dwFlags
0x180002b18  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002b1f  nop     dword ptr [rax+rax+00h]
0x180002b24  mov     eax, edi
0x180002b26  add     rsp, 68h
0x180002b2a  pop     rdi
0x180002b2b  pop     rsi
0x180002b2c  pop     rbx
0x180002b2d  pop     rbp
0x180002b2e  retn
```
