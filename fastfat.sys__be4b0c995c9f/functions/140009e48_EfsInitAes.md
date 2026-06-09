# EfsInitAes

- ea: `0x140009e48`
- end: `0x140009fa4`
- name: `EfsInitAes`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004da14`

## callees

- `0x140009e48`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x140009eca`
- `ksecdd!BCryptSetProperty` at `0x140009eca`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009e94`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009e94`
- `ksecdd!BCryptGetProperty` at `0x140009f0d`
- `ksecdd!BCryptGetProperty` at `0x140009f4c`
- `ksecdd!BCryptGetProperty` at `0x140009f0d`
- `ksecdd!BCryptGetProperty` at `0x140009f4c`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140009f82`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140009f82`

## pseudocode

```c
__int64 __fastcall EfsInitAes(BCRYPT_ALG_HANDLE *a1, _DWORD *a2, _DWORD *a3)
{
  NTSTATUS Property; // ebx
  BCRYPT_ALG_HANDLE v7; // rcx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-10h] BYREF
  UCHAR v10[4]; // [rsp+34h] [rbp-Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+78h] [rbp+38h] BYREF

  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_DWORD *)v10 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property < 0
    || (Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0), Property < 0)
    || (pcbResult = 4,
        Property = BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0),
        Property < 0)
    || (pcbResult = 4, Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v10, 4u, &pcbResult, 0), Property < 0) )
  {
    v7 = phAlgorithm;
  }
  else
  {
    v7 = 0;
    *a1 = phAlgorithm;
    *a2 = *(_DWORD *)pbOutput;
    *a3 = *(_DWORD *)v10;
    phAlgorithm = 0;
  }
  if ( v7 )
    BCryptCloseAlgorithmProvider(v7, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140009e48  mov     [rsp-18h+arg_0], rbx
0x140009e4d  mov     [rsp-18h+arg_8], rsi
0x140009e52  push    rbp
0x140009e53  push    rdi
0x140009e54  push    r14
0x140009e56  mov     rbp, rsp
0x140009e59  sub     rsp, 40h
0x140009e5d  mov     rdi, r8
0x140009e60  mov     [rbp+phAlgorithm], 0
0x140009e68  mov     rsi, rdx
0x140009e6b  mov     dword ptr [rbp+pbOutput], 0
0x140009e72  mov     r14, rcx
0x140009e75  mov     [rbp+pcbResult], 0
0x140009e7c  xor     r8d, r8d; pszImplementation
0x140009e7f  mov     dword ptr [rbp+var_C], 0
0x140009e86  lea     rdx, aAes; "AES"
0x140009e8d  xor     r9d, r9d; dwFlags
0x140009e90  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140009e94  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140009e9b  nop     dword ptr [rax+rax+00h]
0x140009ea0  mov     ebx, eax
0x140009ea2  test    eax, eax
0x140009ea4  js      loc_140009F77
0x140009eaa  mov     rcx, [rbp+phAlgorithm]; hObject
0x140009eae  lea     r8, pbInput; "ChainingModeCBC"
0x140009eb5  mov     r9d, 20h ; ' '; cbInput
0x140009ebb  mov     [rsp+40h+dwFlags], 0; dwFlags
0x140009ec3  lea     rdx, aChainingmode; "ChainingMode"
0x140009eca  call    cs:__imp_BCryptSetProperty
0x140009ed1  nop     dword ptr [rax+rax+00h]
0x140009ed6  mov     ebx, eax
0x140009ed8  test    eax, eax
0x140009eda  js      loc_140009F77
0x140009ee0  mov     rcx, [rbp+phAlgorithm]; hObject
0x140009ee4  lea     rax, [rbp+pcbResult]
0x140009ee8  mov     [rsp+40h+var_18], 0; dwFlags
0x140009ef0  lea     r8, [rbp+pbOutput]; pbOutput
0x140009ef4  mov     r9d, 4; cbOutput
0x140009efa  mov     qword ptr [rsp+40h+dwFlags], rax; pcbResult
0x140009eff  lea     rdx, aBlocklength; "BlockLength"
0x140009f06  mov     [rbp+pcbResult], 4
0x140009f0d  call    cs:__imp_BCryptGetProperty
0x140009f14  nop     dword ptr [rax+rax+00h]
0x140009f19  mov     ebx, eax
0x140009f1b  test    eax, eax
0x140009f1d  js      short loc_140009F77
0x140009f1f  mov     rcx, [rbp+phAlgorithm]; hObject
0x140009f23  lea     rax, [rbp+pcbResult]
0x140009f27  mov     [rsp+40h+var_18], 0; dwFlags
0x140009f2f  lea     r8, [rbp+var_C]; pbOutput
0x140009f33  mov     r9d, 4; cbOutput
0x140009f39  mov     qword ptr [rsp+40h+dwFlags], rax; pcbResult
0x140009f3e  lea     rdx, aObjectlength; "ObjectLength"
0x140009f45  mov     [rbp+pcbResult], 4
0x140009f4c  call    cs:__imp_BCryptGetProperty
0x140009f53  nop     dword ptr [rax+rax+00h]
0x140009f58  mov     ebx, eax
0x140009f5a  test    eax, eax
0x140009f5c  js      short loc_140009F77
0x140009f5e  mov     rax, [rbp+phAlgorithm]
0x140009f62  xor     ecx, ecx
0x140009f64  mov     [r14], rax
0x140009f67  mov     eax, dword ptr [rbp+pbOutput]
0x140009f6a  mov     [rsi], eax
0x140009f6c  mov     eax, dword ptr [rbp+var_C]
0x140009f6f  mov     [rdi], eax
0x140009f71  mov     [rbp+phAlgorithm], rcx
0x140009f75  jmp     short loc_140009F7B
0x140009f77  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140009f7b  test    rcx, rcx
0x140009f7e  jz      short loc_140009F8E
0x140009f80  xor     edx, edx; dwFlags
0x140009f82  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140009f89  nop     dword ptr [rax+rax+00h]
0x140009f8e  mov     rsi, [rsp+40h+arg_8]
0x140009f93  mov     eax, ebx
0x140009f95  mov     rbx, [rsp+40h+arg_0]
0x140009f9a  add     rsp, 40h
0x140009f9e  pop     r14
0x140009fa0  pop     rdi
0x140009fa1  pop     rbp
0x140009fa2  retn
```
