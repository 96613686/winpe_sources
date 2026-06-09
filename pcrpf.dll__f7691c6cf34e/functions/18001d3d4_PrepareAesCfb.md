# PrepareAesCfb

- ea: `0x18001d3d4`
- end: `0x18001d522`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d530`
- `0x18001d700`

## callees

- `0x18001d3d4`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x18001d482`
- `bcrypt!BCryptSetProperty` at `0x18001d4b1`
- `bcrypt!BCryptSetProperty` at `0x18001d482`
- `bcrypt!BCryptSetProperty` at `0x18001d4b1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d41b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d41b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d506`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001d506`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001d450`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001d450`
- `bcrypt!BCryptDestroyKey` at `0x18001d4ef`
- `bcrypt!BCryptDestroyKey` at `0x18001d4ef`

## pseudocode

```c
__int64 __fastcall PrepareAesCfb(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_ALG_HANDLE *a3, BCRYPT_KEY_HANDLE *a4)
{
  NTSTATUS v8; // ebx
  BCRYPT_ALG_HANDLE v9; // rcx
  BCRYPT_KEY_HANDLE v10; // rax
  UCHAR pbInput[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  *(_DWORD *)pbInput = 16;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0
    || (v8 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"MessageBlockLength", pbInput, 4u, 0), v8 < 0) )
  {
    v9 = phAlgorithm;
    v10 = phKey;
  }
  else
  {
    v9 = 0;
    *a3 = phAlgorithm;
    *a4 = phKey;
    v10 = 0;
    phKey = 0;
    phAlgorithm = 0;
  }
  if ( v10 )
  {
    BCryptDestroyKey(v10);
    v9 = phAlgorithm;
  }
  if ( v9 )
    BCryptCloseAlgorithmProvider(v9, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d3d4  push    rbp
0x18001d3d6  push    rbx
0x18001d3d7  push    rsi
0x18001d3d8  push    rdi
0x18001d3d9  push    r14
0x18001d3db  push    r15
0x18001d3dd  mov     rbp, rsp
0x18001d3e0  sub     rsp, 68h
0x18001d3e4  mov     r14, r9
0x18001d3e7  mov     [rbp+phAlgorithm], 0
0x18001d3ef  mov     r15, r8
0x18001d3f2  mov     [rbp+phKey], 0
0x18001d3fa  mov     edi, edx
0x18001d3fc  mov     dword ptr [rbp+pbInput], 10h
0x18001d403  mov     rsi, rcx
0x18001d406  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18001d40d  xor     r9d, r9d; dwFlags
0x18001d410  lea     rdx, pszAlgId; "AES"
0x18001d417  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18001d41b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001d422  nop     dword ptr [rax+rax+00h]
0x18001d427  mov     ebx, eax
0x18001d429  test    eax, eax
0x18001d42b  js      loc_18001D4DF
0x18001d431  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001d435  lea     rdx, [rbp+phKey]; phKey
0x18001d439  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001d441  xor     r9d, r9d; cbKeyObject
0x18001d444  mov     [rsp+68h+cbSecret], edi; cbSecret
0x18001d448  xor     r8d, r8d; pbKeyObject
0x18001d44b  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x18001d450  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001d457  nop     dword ptr [rax+rax+00h]
0x18001d45c  mov     ebx, eax
0x18001d45e  test    eax, eax
0x18001d460  js      short loc_18001D4DF
0x18001d462  mov     rcx, [rbp+phKey]; hObject
0x18001d466  lea     r8, pbInput; "ChainingModeCFB"
0x18001d46d  mov     r9d, 20h ; ' '; cbInput
0x18001d473  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18001d47b  lea     rdx, pszProperty; "ChainingMode"
0x18001d482  call    cs:__imp_BCryptSetProperty
0x18001d489  nop     dword ptr [rax+rax+00h]
0x18001d48e  mov     ebx, eax
0x18001d490  test    eax, eax
0x18001d492  js      short loc_18001D4DF
0x18001d494  mov     rcx, [rbp+phKey]; hObject
0x18001d498  lea     r8, [rbp+pbInput]; pbInput
0x18001d49c  mov     r9d, 4; cbInput
0x18001d4a2  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18001d4aa  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18001d4b1  call    cs:__imp_BCryptSetProperty
0x18001d4b8  nop     dword ptr [rax+rax+00h]
0x18001d4bd  mov     ebx, eax
0x18001d4bf  test    eax, eax
0x18001d4c1  js      short loc_18001D4DF
0x18001d4c3  mov     rax, [rbp+phAlgorithm]
0x18001d4c7  xor     ecx, ecx
0x18001d4c9  mov     [r15], rax
0x18001d4cc  mov     rax, [rbp+phKey]
0x18001d4d0  mov     [r14], rax
0x18001d4d3  xor     eax, eax
0x18001d4d5  mov     [rbp+phKey], rax
0x18001d4d9  mov     [rbp+phAlgorithm], rcx
0x18001d4dd  jmp     short loc_18001D4E7
0x18001d4df  mov     rcx, [rbp+phAlgorithm]
0x18001d4e3  mov     rax, [rbp+phKey]
0x18001d4e7  test    rax, rax
0x18001d4ea  jz      short loc_18001D4FF
0x18001d4ec  mov     rcx, rax; hKey
0x18001d4ef  call    cs:__imp_BCryptDestroyKey
0x18001d4f6  nop     dword ptr [rax+rax+00h]
0x18001d4fb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001d4ff  test    rcx, rcx
0x18001d502  jz      short loc_18001D512
0x18001d504  xor     edx, edx; dwFlags
0x18001d506  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001d50d  nop     dword ptr [rax+rax+00h]
0x18001d512  mov     eax, ebx
0x18001d514  add     rsp, 68h
0x18001d518  pop     r15
0x18001d51a  pop     r14
0x18001d51c  pop     rdi
0x18001d51d  pop     rsi
0x18001d51e  pop     rbx
0x18001d51f  pop     rbp
0x18001d520  retn
```
