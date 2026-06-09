# HashUserSessionKey

- ea: `0x140041b84`
- end: `0x140041c76`
- name: `HashUserSessionKey`
- size: `242`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140041c80`
- `0x140041e90`

## callees

- `0x140012834`
- `0x140041b84`

## import_xrefs

- `ksecdd!BCryptFinishHash` at `0x140041c3a`
- `ksecdd!BCryptFinishHash` at `0x140041c3a`
- `ksecdd!BCryptDestroyHash` at `0x140041c54`
- `ksecdd!BCryptDestroyHash` at `0x140041c54`
- `ksecdd!BCryptCreateHash` at `0x140041be8`
- `ksecdd!BCryptCreateHash` at `0x140041be8`
- `ksecdd!BCryptHashData` at `0x140041c16`
- `ksecdd!BCryptHashData` at `0x140041c16`

## pseudocode

```c
void __fastcall HashUserSessionKey(PUCHAR pbSecret, PUCHAR pbOutput, __int64 a3)
{
  bool v3; // zf
  void *AlgHandle; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp+18h] BYREF

  v3 = (*(_DWORD *)(a3 + 8) & 0x100) == 0;
  phHash = 0;
  if ( v3 )
  {
    AlgHandle = (void *)p_GetAlgHandle(&g_hHmacMd5Provider, pbOutput, 8);
    if ( BCryptCreateHash(AlgHandle, &phHash, 0, 0, pbSecret, 0x10u, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash, &pbInput, 0x100u, 0) < 0 )
      __fastfail(7u);
    if ( BCryptFinishHash(phHash, pbOutput, 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash);
    *(_DWORD *)(a3 + 8) |= 0x100u;
  }
}

```

## disassembly

```asm
0x140041b84  mov     [rsp+arg_0], rbx
0x140041b89  mov     [rsp+arg_8], rsi
0x140041b8e  push    rdi
0x140041b8f  sub     rsp, 40h
0x140041b93  test    dword ptr [r8+8], 100h
0x140041b9b  mov     rbx, r8
0x140041b9e  mov     rsi, rdx
0x140041ba1  mov     [rsp+48h+phHash], 0
0x140041baa  mov     rdi, rcx
0x140041bad  jnz     loc_140041C65
0x140041bb3  mov     r8d, 8
0x140041bb9  lea     rcx, g_hHmacMd5Provider
0x140041bc0  call    p_GetAlgHandle
0x140041bc5  mov     [rsp+48h+dwFlags], 0; dwFlags
0x140041bcd  lea     rdx, [rsp+48h+phHash]; phHash
0x140041bd2  mov     rcx, rax; hAlgorithm
0x140041bd5  mov     [rsp+48h+cbSecret], 10h; cbSecret
0x140041bdd  xor     r9d, r9d; cbHashObject
0x140041be0  mov     [rsp+48h+pbSecret], rdi; pbSecret
0x140041be5  xor     r8d, r8d; pbHashObject
0x140041be8  call    cs:__imp_BCryptCreateHash
0x140041bef  nop     dword ptr [rax+rax+00h]
0x140041bf4  mov     edi, 7
0x140041bf9  test    eax, eax
0x140041bfb  jns     short loc_140041C01
0x140041bfd  mov     ecx, edi
0x140041bff  int     29h; Win8: RtlFailFast(ecx)
0x140041c01  mov     rcx, [rsp+48h+phHash]; hHash
0x140041c06  lea     rdx, pbInput; pbInput
0x140041c0d  xor     r9d, r9d; dwFlags
0x140041c10  mov     r8d, 100h; cbInput
0x140041c16  call    cs:__imp_BCryptHashData
0x140041c1d  nop     dword ptr [rax+rax+00h]
0x140041c22  test    eax, eax
0x140041c24  jns     short loc_140041C2B
0x140041c26  mov     rcx, rdi
0x140041c29  int     29h; Win8: RtlFailFast(ecx)
0x140041c2b  mov     rcx, [rsp+48h+phHash]; hHash
0x140041c30  xor     r9d, r9d; dwFlags
0x140041c33  mov     rdx, rsi; pbOutput
0x140041c36  lea     r8d, [r9+10h]; cbOutput
0x140041c3a  call    cs:__imp_BCryptFinishHash
0x140041c41  nop     dword ptr [rax+rax+00h]
0x140041c46  test    eax, eax
0x140041c48  jns     short loc_140041C4F
0x140041c4a  mov     rcx, rdi
0x140041c4d  int     29h; Win8: RtlFailFast(ecx)
0x140041c4f  mov     rcx, [rsp+48h+phHash]; hHash
0x140041c54  call    cs:__imp_BCryptDestroyHash
0x140041c5b  nop     dword ptr [rax+rax+00h]
0x140041c60  bts     dword ptr [rbx+8], 8
0x140041c65  mov     rbx, [rsp+48h+arg_0]
0x140041c6a  mov     rsi, [rsp+48h+arg_8]
0x140041c6f  add     rsp, 40h
0x140041c73  pop     rdi
0x140041c74  retn
```
