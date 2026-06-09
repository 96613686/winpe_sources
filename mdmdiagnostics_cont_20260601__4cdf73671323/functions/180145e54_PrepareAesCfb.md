# PrepareAesCfb

- ea: `0x180145e54`
- end: `0x180145f7d`
- name: `PrepareAesCfb`
- size: `297`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180145f90`
- `0x180146150`

## callees

- `0x180145e54`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180145ef6`
- `bcrypt!BCryptSetProperty` at `0x180145f1f`
- `bcrypt!BCryptSetProperty` at `0x180145ef6`
- `bcrypt!BCryptSetProperty` at `0x180145f1f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180145e9b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180145e9b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180145eca`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180145eca`
- `bcrypt!BCryptDestroyKey` at `0x180145f57`
- `bcrypt!BCryptDestroyKey` at `0x180145f57`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180145f68`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180145f68`

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
0x180145e54  push    rbp
0x180145e56  push    rbx
0x180145e57  push    rsi
0x180145e58  push    rdi
0x180145e59  push    r14
0x180145e5b  push    r15
0x180145e5d  mov     rbp, rsp
0x180145e60  sub     rsp, 68h
0x180145e64  mov     r14, r9
0x180145e67  mov     [rbp+phAlgorithm], 0
0x180145e6f  mov     r15, r8
0x180145e72  mov     [rbp+phKey], 0
0x180145e7a  mov     edi, edx
0x180145e7c  mov     dword ptr [rbp+pbInput], 10h
0x180145e83  mov     rsi, rcx
0x180145e86  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180145e8d  xor     r9d, r9d; dwFlags
0x180145e90  lea     rdx, aAes; "AES"
0x180145e97  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180145e9b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180145ea1  mov     ebx, eax
0x180145ea3  test    eax, eax
0x180145ea5  js      loc_180145F47
0x180145eab  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180145eaf  lea     rdx, [rbp+phKey]; phKey
0x180145eb3  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180145ebb  xor     r9d, r9d; cbKeyObject
0x180145ebe  mov     [rsp+68h+cbSecret], edi; cbSecret
0x180145ec2  xor     r8d, r8d; pbKeyObject
0x180145ec5  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x180145eca  call    cs:__imp_BCryptGenerateSymmetricKey
0x180145ed0  mov     ebx, eax
0x180145ed2  test    eax, eax
0x180145ed4  js      short loc_180145F47
0x180145ed6  mov     rcx, [rbp+phKey]; hObject
0x180145eda  lea     r8, pbInput; "ChainingModeCFB"
0x180145ee1  mov     r9d, 20h ; ' '; cbInput
0x180145ee7  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x180145eef  lea     rdx, aChainingmode; "ChainingMode"
0x180145ef6  call    cs:__imp_BCryptSetProperty
0x180145efc  mov     ebx, eax
0x180145efe  test    eax, eax
0x180145f00  js      short loc_180145F47
0x180145f02  mov     rcx, [rbp+phKey]; hObject
0x180145f06  lea     r8, [rbp+pbInput]; pbInput
0x180145f0a  mov     r9d, 4; cbInput
0x180145f10  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x180145f18  lea     rdx, aMessageblockle; "MessageBlockLength"
0x180145f1f  call    cs:__imp_BCryptSetProperty
0x180145f25  mov     ebx, eax
0x180145f27  test    eax, eax
0x180145f29  js      short loc_180145F47
0x180145f2b  mov     rax, [rbp+phAlgorithm]
0x180145f2f  xor     ecx, ecx
0x180145f31  mov     [r15], rax
0x180145f34  mov     rax, [rbp+phKey]
0x180145f38  mov     [r14], rax
0x180145f3b  xor     eax, eax
0x180145f3d  mov     [rbp+phKey], rax
0x180145f41  mov     [rbp+phAlgorithm], rcx
0x180145f45  jmp     short loc_180145F4F
0x180145f47  mov     rcx, [rbp+phAlgorithm]
0x180145f4b  mov     rax, [rbp+phKey]
0x180145f4f  test    rax, rax
0x180145f52  jz      short loc_180145F61
0x180145f54  mov     rcx, rax; hKey
0x180145f57  call    cs:__imp_BCryptDestroyKey
0x180145f5d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180145f61  test    rcx, rcx
0x180145f64  jz      short loc_180145F6E
0x180145f66  xor     edx, edx; dwFlags
0x180145f68  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180145f6e  mov     eax, ebx
0x180145f70  add     rsp, 68h
0x180145f74  pop     r15
0x180145f76  pop     r14
0x180145f78  pop     rdi
0x180145f79  pop     rsi
0x180145f7a  pop     rbx
0x180145f7b  pop     rbp
0x180145f7c  retn
```
