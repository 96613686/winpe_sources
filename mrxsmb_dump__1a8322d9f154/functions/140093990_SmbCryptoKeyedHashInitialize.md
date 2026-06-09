# SmbCryptoKeyedHashInitialize

- ea: `0x140093990`
- end: `0x140093aa5`
- name: `SmbCryptoKeyedHashInitialize`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400865d0`
- `0x140093990`

## import_xrefs

- `ksecdd!BCryptGetProperty` at `0x140093a12`
- `ksecdd!BCryptGetProperty` at `0x140093a52`
- `ksecdd!BCryptGetProperty` at `0x140093a12`
- `ksecdd!BCryptGetProperty` at `0x140093a52`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400939d6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400939d6`

## pseudocode

```c
__int64 SmbCryptoKeyedHashInitialize()
{
  __int64 v0; // rbx
  __int64 *v1; // rsi
  NTSTATUS Property; // edi
  bool v3; // cc
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF

  v0 = 0;
  pcbResult = 0;
  while ( 1 )
  {
    v1 = &qword_1400709D0[3 * v0];
    Property = BCryptOpenAlgorithmProvider(
                 (BCRYPT_ALG_HANDLE *)v1,
                 (&Smb2HashAlgorithmDescriptors)[2 * (unsigned int)v0],
                 0,
                 dword_140061EF8[4 * (unsigned int)v0]);
    if ( Property < 0 )
      break;
    Property = BCryptGetProperty((BCRYPT_HANDLE)*v1, L"HashDigestLength", (PUCHAR)v1 + 8, 4u, &pcbResult, 0);
    if ( Property < 0 )
      break;
    Property = BCryptGetProperty(
                 (BCRYPT_HANDLE)*v1,
                 L"ObjectLength",
                 (PUCHAR)&dword_1400709DC[6 * v0],
                 4u,
                 &pcbResult,
                 0);
    if ( Property < 0 )
      break;
    v3 = (unsigned int)dword_1400709D8[6 * v0] <= 0x20;
    word_1400709E0[12 * v0] = word_140061EFC[8 * (unsigned int)v0];
    if ( !v3 )
      __int2c();
    v0 = (unsigned int)(v0 + 1);
    if ( (unsigned int)v0 >= 3 )
      return (unsigned int)Property;
  }
  SmbCryptoKeyedHashUninitialize();
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140093990  push    rbx
0x140093992  push    rbp
0x140093993  push    rsi
0x140093994  push    rdi
0x140093995  push    r12
0x140093997  push    r14
0x140093999  sub     rsp, 38h
0x14009399d  xor     ebx, ebx
0x14009399f  lea     r12, cs:140000000h
0x1400939a6  mov     [rsp+68h+arg_0], ebx
0x1400939aa  mov     r14d, ebx
0x1400939ad  lea     rbp, [rbx+rbx*2]
0x1400939b1  add     r14, r14
0x1400939b4  lea     rsi, rva qword_1400709D0[r12]
0x1400939bc  lea     rsi, [rsi+rbp*8]
0x1400939c0  xor     r8d, r8d; pszImplementation
0x1400939c3  mov     rcx, rsi; phAlgorithm
0x1400939c6  mov     r9d, ds:rva dword_140061EF8[r12+r14*8]; dwFlags
0x1400939ce  mov     rdx, ds:rva Smb2HashAlgorithmDescriptors[r12+r14*8]; pszAlgId
0x1400939d6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400939dd  nop     dword ptr [rax+rax+00h]
0x1400939e2  mov     edi, eax
0x1400939e4  test    eax, eax
0x1400939e6  js      loc_140093A90
0x1400939ec  mov     rcx, [rsi]; hObject
0x1400939ef  lea     rax, [rsp+68h+arg_0]
0x1400939f4  lea     r8, [rsi+8]; pbOutput
0x1400939f8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x140093a00  mov     r9d, 4; cbOutput
0x140093a06  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140093a0b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140093a12  call    cs:__imp_BCryptGetProperty
0x140093a19  nop     dword ptr [rax+rax+00h]
0x140093a1e  mov     edi, eax
0x140093a20  test    eax, eax
0x140093a22  js      short loc_140093A90
0x140093a24  mov     rcx, [rsi]; hObject
0x140093a27  lea     rax, [rsp+68h+arg_0]
0x140093a2c  lea     r8, rva dword_1400709DC[r12]
0x140093a34  mov     [rsp+68h+dwFlags], 0; dwFlags
0x140093a3c  lea     r8, [r8+rbp*8]; pbOutput
0x140093a40  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140093a45  mov     r9d, 4; cbOutput
0x140093a4b  lea     rdx, aObjectlength; "ObjectLength"
0x140093a52  call    cs:__imp_BCryptGetProperty
0x140093a59  nop     dword ptr [rax+rax+00h]
0x140093a5e  mov     edi, eax
0x140093a60  test    eax, eax
0x140093a62  js      short loc_140093A90
0x140093a64  cmp     rva dword_1400709D8[r12+rbp*8], 20h ; ' '
0x140093a6d  movzx   eax, ds:rva word_140061EFC[r12+r14*8]
0x140093a76  mov     rva word_1400709E0[r12+rbp*8], ax
0x140093a7f  jbe     short loc_140093A83
0x140093a81  int     2Ch; Windows NT - assertion failure
0x140093a83  inc     ebx
0x140093a85  cmp     ebx, 3
0x140093a88  jb      loc_1400939AA
0x140093a8e  jmp     short loc_140093A95
0x140093a90  call    SmbCryptoKeyedHashUninitialize
0x140093a95  mov     eax, edi
0x140093a97  add     rsp, 38h
0x140093a9b  pop     r14
0x140093a9d  pop     r12
0x140093a9f  pop     rdi
0x140093aa0  pop     rsi
0x140093aa1  pop     rbp
0x140093aa2  pop     rbx
0x140093aa3  retn
```
