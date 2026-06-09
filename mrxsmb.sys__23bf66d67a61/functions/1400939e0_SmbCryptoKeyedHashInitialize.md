# SmbCryptoKeyedHashInitialize

- ea: `0x1400939e0`
- end: `0x140093af5`
- name: `SmbCryptoKeyedHashInitialize`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140086620`
- `0x1400939e0`

## import_xrefs

- `ksecdd!BCryptGetProperty` at `0x140093a62`
- `ksecdd!BCryptGetProperty` at `0x140093aa2`
- `ksecdd!BCryptGetProperty` at `0x140093a62`
- `ksecdd!BCryptGetProperty` at `0x140093aa2`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140093a26`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140093a26`

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
0x1400939e0  push    rbx
0x1400939e2  push    rbp
0x1400939e3  push    rsi
0x1400939e4  push    rdi
0x1400939e5  push    r12
0x1400939e7  push    r14
0x1400939e9  sub     rsp, 38h
0x1400939ed  xor     ebx, ebx
0x1400939ef  lea     r12, cs:140000000h
0x1400939f6  mov     [rsp+68h+arg_0], ebx
0x1400939fa  mov     r14d, ebx
0x1400939fd  lea     rbp, [rbx+rbx*2]
0x140093a01  add     r14, r14
0x140093a04  lea     rsi, rva qword_1400709D0[r12]
0x140093a0c  lea     rsi, [rsi+rbp*8]
0x140093a10  xor     r8d, r8d; pszImplementation
0x140093a13  mov     rcx, rsi; phAlgorithm
0x140093a16  mov     r9d, ds:rva dword_140061EF8[r12+r14*8]; dwFlags
0x140093a1e  mov     rdx, ds:rva Smb2HashAlgorithmDescriptors[r12+r14*8]; pszAlgId
0x140093a26  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140093a2d  nop     dword ptr [rax+rax+00h]
0x140093a32  mov     edi, eax
0x140093a34  test    eax, eax
0x140093a36  js      loc_140093AE0
0x140093a3c  mov     rcx, [rsi]; hObject
0x140093a3f  lea     rax, [rsp+68h+arg_0]
0x140093a44  lea     r8, [rsi+8]; pbOutput
0x140093a48  mov     [rsp+68h+dwFlags], 0; dwFlags
0x140093a50  mov     r9d, 4; cbOutput
0x140093a56  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140093a5b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140093a62  call    cs:__imp_BCryptGetProperty
0x140093a69  nop     dword ptr [rax+rax+00h]
0x140093a6e  mov     edi, eax
0x140093a70  test    eax, eax
0x140093a72  js      short loc_140093AE0
0x140093a74  mov     rcx, [rsi]; hObject
0x140093a77  lea     rax, [rsp+68h+arg_0]
0x140093a7c  lea     r8, rva dword_1400709DC[r12]
0x140093a84  mov     [rsp+68h+dwFlags], 0; dwFlags
0x140093a8c  lea     r8, [r8+rbp*8]; pbOutput
0x140093a90  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140093a95  mov     r9d, 4; cbOutput
0x140093a9b  lea     rdx, aObjectlength; "ObjectLength"
0x140093aa2  call    cs:__imp_BCryptGetProperty
0x140093aa9  nop     dword ptr [rax+rax+00h]
0x140093aae  mov     edi, eax
0x140093ab0  test    eax, eax
0x140093ab2  js      short loc_140093AE0
0x140093ab4  cmp     rva dword_1400709D8[r12+rbp*8], 20h ; ' '
0x140093abd  movzx   eax, ds:rva word_140061EFC[r12+r14*8]
0x140093ac6  mov     rva word_1400709E0[r12+rbp*8], ax
0x140093acf  jbe     short loc_140093AD3
0x140093ad1  int     2Ch; Windows NT - assertion failure
0x140093ad3  inc     ebx
0x140093ad5  cmp     ebx, 3
0x140093ad8  jb      loc_1400939FA
0x140093ade  jmp     short loc_140093AE5
0x140093ae0  call    SmbCryptoKeyedHashUninitialize
0x140093ae5  mov     eax, edi
0x140093ae7  add     rsp, 38h
0x140093aeb  pop     r14
0x140093aed  pop     r12
0x140093aef  pop     rdi
0x140093af0  pop     rsi
0x140093af1  pop     rbp
0x140093af2  pop     rbx
0x140093af3  retn
```
