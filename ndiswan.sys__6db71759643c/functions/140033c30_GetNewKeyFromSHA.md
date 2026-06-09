# GetNewKeyFromSHA

- ea: `0x140033c30`
- end: `0x140033dae`
- name: `GetNewKeyFromSHA`
- size: `382`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140024728`
- `0x1400247c4`
- `0x140032340`
- `0x1400330a0`

## callees

- `0x140009120`
- `0x1400161f0`
- `0x140016400`
- `0x140033c30`

## import_xrefs

- `cng!BCryptFinishHash` at `0x140033d1f`
- `cng!BCryptFinishHash` at `0x140033d1f`
- `cng!BCryptDestroyHash` at `0x140033d32`
- `cng!BCryptDestroyHash` at `0x140033d32`
- `cng!BCryptHashData` at `0x140033c7a`
- `cng!BCryptHashData` at `0x140033ca5`
- `cng!BCryptHashData` at `0x140033ccb`
- `cng!BCryptHashData` at `0x140033cf6`
- `cng!BCryptHashData` at `0x140033c7a`
- `cng!BCryptHashData` at `0x140033ca5`
- `cng!BCryptHashData` at `0x140033ccb`
- `cng!BCryptHashData` at `0x140033cf6`

## pseudocode

```c
void *__fastcall GetNewKeyFromSHA(__int64 a1)
{
  BCRYPT_HASH_HANDLE *v2; // rcx
  BCRYPT_HASH_HANDLE *v3; // rdi
  UCHAR pbOutput[16]; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  v2 = *(BCRYPT_HASH_HANDLE **)(a1 + 40);
  *(_OWORD *)pbOutput = 0;
  v6 = 0;
  CngRsa32Compat_SHAInit_Ex(v2);
  if ( BCryptHashData(**(BCRYPT_HASH_HANDLE **)(a1 + 40), (PUCHAR)(a1 + 4), *(_DWORD *)(a1 + 36), 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(**(BCRYPT_HASH_HANDLE **)(a1 + 40), &SHApad1, 0x28u, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(**(BCRYPT_HASH_HANDLE **)(a1 + 40), (PUCHAR)(a1 + 20), *(_DWORD *)(a1 + 36), 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(**(BCRYPT_HASH_HANDLE **)(a1 + 40), &SHApad2, 0x28u, 0) < 0 )
    __fastfail(7u);
  v3 = *(BCRYPT_HASH_HANDLE **)(a1 + 40);
  if ( BCryptFinishHash(*v3, pbOutput, 0x14u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(*v3);
  *v3 = 0;
  return memmove((void *)(a1 + 20), pbOutput, *(unsigned int *)(a1 + 36));
}

```

## disassembly

```asm
0x140033c30  mov     [rsp+arg_8], rbx
0x140033c35  mov     [rsp+arg_10], rsi
0x140033c3a  push    rdi
0x140033c3b  sub     rsp, 40h
0x140033c3f  mov     rax, cs:__security_cookie
0x140033c46  xor     rax, rsp
0x140033c49  mov     [rsp+48h+var_10], rax
0x140033c4e  mov     rbx, rcx
0x140033c51  xorps   xmm0, xmm0
0x140033c54  mov     rcx, [rcx+28h]; phHash
0x140033c58  xor     eax, eax
0x140033c5a  movups  xmmword ptr [rsp+48h+pbOutput], xmm0
0x140033c5f  mov     [rsp+48h+var_18], eax
0x140033c63  call    CngRsa32Compat_SHAInit_Ex
0x140033c68  mov     rcx, [rbx+28h]
0x140033c6c  lea     rdx, [rbx+4]; pbInput
0x140033c70  mov     r8d, [rbx+24h]; cbInput
0x140033c74  xor     r9d, r9d; dwFlags
0x140033c77  mov     rcx, [rcx]; hHash
0x140033c7a  call    cs:__imp_BCryptHashData
0x140033c81  nop     dword ptr [rax+rax+00h]
0x140033c86  test    eax, eax
0x140033c88  js      loc_140033D75
0x140033c8e  mov     rcx, [rbx+28h]
0x140033c92  lea     rdx, SHApad1; pbInput
0x140033c99  xor     r9d, r9d; dwFlags
0x140033c9c  mov     r8d, 28h ; '('; cbInput
0x140033ca2  mov     rcx, [rcx]; hHash
0x140033ca5  call    cs:__imp_BCryptHashData
0x140033cac  nop     dword ptr [rax+rax+00h]
0x140033cb1  test    eax, eax
0x140033cb3  js      loc_140033D81
0x140033cb9  mov     rcx, [rbx+28h]
0x140033cbd  lea     rdx, [rbx+14h]; pbInput
0x140033cc1  mov     r8d, [rbx+24h]; cbInput
0x140033cc5  xor     r9d, r9d; dwFlags
0x140033cc8  mov     rcx, [rcx]; hHash
0x140033ccb  call    cs:__imp_BCryptHashData
0x140033cd2  nop     dword ptr [rax+rax+00h]
0x140033cd7  test    eax, eax
0x140033cd9  js      loc_140033D8D
0x140033cdf  mov     rcx, [rbx+28h]
0x140033ce3  lea     rdx, SHApad2; pbInput
0x140033cea  xor     r9d, r9d; dwFlags
0x140033ced  mov     r8d, 28h ; '('; cbInput
0x140033cf3  mov     rcx, [rcx]; hHash
0x140033cf6  call    cs:__imp_BCryptHashData
0x140033cfd  nop     dword ptr [rax+rax+00h]
0x140033d02  test    eax, eax
0x140033d04  js      loc_140033D99
0x140033d0a  mov     rdi, [rbx+28h]
0x140033d0e  lea     rdx, [rsp+48h+pbOutput]; pbOutput
0x140033d13  xor     r9d, r9d; dwFlags
0x140033d16  mov     r8d, 14h; cbOutput
0x140033d1c  mov     rcx, [rdi]; hHash
0x140033d1f  call    cs:__imp_BCryptFinishHash
0x140033d26  nop     dword ptr [rax+rax+00h]
0x140033d2b  test    eax, eax
0x140033d2d  js      short loc_140033DA5
0x140033d2f  mov     rcx, [rdi]; hHash
0x140033d32  call    cs:__imp_BCryptDestroyHash
0x140033d39  nop     dword ptr [rax+rax+00h]
0x140033d3e  mov     qword ptr [rdi], 0
0x140033d45  lea     rdx, [rsp+48h+pbOutput]; Src
0x140033d4a  mov     r8d, [rbx+24h]; Size
0x140033d4e  lea     rcx, [rbx+14h]; void *
0x140033d52  call    memmove
0x140033d57  mov     rcx, [rsp+48h+var_10]
0x140033d5c  xor     rcx, rsp; StackCookie
0x140033d5f  call    __security_check_cookie
0x140033d64  mov     rbx, [rsp+48h+arg_8]
0x140033d69  mov     rsi, [rsp+48h+arg_10]
0x140033d6e  add     rsp, 40h
0x140033d72  pop     rdi
0x140033d73  retn
0x140033d75  mov     ecx, 7
0x140033d7a  int     29h; Win8: RtlFailFast(ecx)
0x140033d7c  jmp     loc_140033C8E
0x140033d81  mov     ecx, 7
0x140033d86  int     29h; Win8: RtlFailFast(ecx)
0x140033d88  jmp     loc_140033CB9
0x140033d8d  mov     ecx, 7
0x140033d92  int     29h; Win8: RtlFailFast(ecx)
0x140033d94  jmp     loc_140033CDF
0x140033d99  mov     ecx, 7
0x140033d9e  int     29h; Win8: RtlFailFast(ecx)
0x140033da0  jmp     loc_140033D0A
0x140033da5  mov     ecx, 7
0x140033daa  int     29h; Win8: RtlFailFast(ecx)
0x140033dac  jmp     short loc_140033D2F
```
