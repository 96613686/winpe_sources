# CalculateHash(ushort const *,uchar *,ulong,uchar *,ulong)

- ea: `0x18000e9b0`
- end: `0x18000eae4`
- name: `?CalculateHash@@YAJPEBGPEAEK1K@Z`
- size: `308`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e9b0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ea10`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ea10`
- `bcrypt!BCryptCreateHash` at `0x18000ea44`
- `bcrypt!BCryptCreateHash` at `0x18000ea44`
- `bcrypt!BCryptFinishHash` at `0x18000ea8a`
- `bcrypt!BCryptFinishHash` at `0x18000ea8a`
- `bcrypt!BCryptHashData` at `0x18000ea67`
- `bcrypt!BCryptHashData` at `0x18000ea67`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000eaa4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000eaa4`
- `bcrypt!BCryptDestroyHash` at `0x18000eabd`
- `bcrypt!BCryptDestroyHash` at `0x18000eabd`

## pseudocode

```c
__int64 __fastcall CalculateHash(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)
{
  ULONG v8; // r14d
  NTSTATUS v9; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+98h] [rbp+10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  if ( pbInput && cbInput && pbOutput && (v8 = cbOutput) != 0 )
  {
    v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0);
    if ( v9 >= 0 )
    {
      v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
      if ( v9 >= 0 )
      {
        v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v9 >= 0 )
          v9 = BCryptFinishHash(phHash, pbOutput, v8, 0);
      }
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( phHash )
      BCryptDestroyHash(phHash);
  }
  else
  {
    v9 = -1073741811;
  }
  return v9 | 0x10000000u;
}

```

## disassembly

```asm
0x18000e9b0  push    rbx
0x18000e9b2  push    rbp
0x18000e9b3  push    rsi
0x18000e9b4  push    rdi
0x18000e9b5  push    r14
0x18000e9b7  push    r15
0x18000e9b9  sub     rsp, 58h
0x18000e9bd  xor     r15d, r15d
0x18000e9c0  mov     rsi, r9
0x18000e9c3  mov     [rsp+88h+phAlgorithm], r15
0x18000e9c8  mov     ebp, r8d
0x18000e9cb  mov     [rsp+88h+phHash], r15
0x18000e9d3  mov     rdi, rdx
0x18000e9d6  test    rdx, rdx
0x18000e9d9  jz      loc_18000EADD
0x18000e9df  test    r8d, r8d
0x18000e9e2  jz      loc_18000EADD
0x18000e9e8  test    r9, r9
0x18000e9eb  jz      loc_18000EADD
0x18000e9f1  mov     r14d, [rsp+88h+cbOutput]
0x18000e9f9  test    r14d, r14d
0x18000e9fc  jz      loc_18000EADD
0x18000ea02  mov     rdx, rcx; pszAlgId
0x18000ea05  xor     r9d, r9d; dwFlags
0x18000ea08  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x18000ea0d  xor     r8d, r8d; pszImplementation
0x18000ea10  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ea17  nop     dword ptr [rax+rax+00h]
0x18000ea1c  mov     ebx, eax
0x18000ea1e  test    eax, eax
0x18000ea20  js      short loc_18000EA98
0x18000ea22  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18000ea27  lea     rdx, [rsp+88h+phHash]; phHash
0x18000ea2f  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18000ea34  xor     r9d, r9d; cbHashObject
0x18000ea37  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18000ea3c  xor     r8d, r8d; pbHashObject
0x18000ea3f  mov     [rsp+88h+pbSecret], r15; pbSecret
0x18000ea44  call    cs:__imp_BCryptCreateHash
0x18000ea4b  nop     dword ptr [rax+rax+00h]
0x18000ea50  mov     ebx, eax
0x18000ea52  test    eax, eax
0x18000ea54  js      short loc_18000EA98
0x18000ea56  mov     rcx, [rsp+88h+phHash]; hHash
0x18000ea5e  xor     r9d, r9d; dwFlags
0x18000ea61  mov     r8d, ebp; cbInput
0x18000ea64  mov     rdx, rdi; pbInput
0x18000ea67  call    cs:__imp_BCryptHashData
0x18000ea6e  nop     dword ptr [rax+rax+00h]
0x18000ea73  mov     ebx, eax
0x18000ea75  test    eax, eax
0x18000ea77  js      short loc_18000EA98
0x18000ea79  mov     rcx, [rsp+88h+phHash]; hHash
0x18000ea81  xor     r9d, r9d; dwFlags
0x18000ea84  mov     r8d, r14d; cbOutput
0x18000ea87  mov     rdx, rsi; pbOutput
0x18000ea8a  call    cs:__imp_BCryptFinishHash
0x18000ea91  nop     dword ptr [rax+rax+00h]
0x18000ea96  mov     ebx, eax
0x18000ea98  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18000ea9d  test    rcx, rcx
0x18000eaa0  jz      short loc_18000EAB0
0x18000eaa2  xor     edx, edx; dwFlags
0x18000eaa4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000eaab  nop     dword ptr [rax+rax+00h]
0x18000eab0  mov     rcx, [rsp+88h+phHash]; hHash
0x18000eab8  test    rcx, rcx
0x18000eabb  jz      short loc_18000EAC9
0x18000eabd  call    cs:__imp_BCryptDestroyHash
0x18000eac4  nop     dword ptr [rax+rax+00h]
0x18000eac9  bts     ebx, 1Ch
0x18000eacd  mov     eax, ebx
0x18000eacf  add     rsp, 58h
0x18000ead3  pop     r15
0x18000ead5  pop     r14
0x18000ead7  pop     rdi
0x18000ead8  pop     rsi
0x18000ead9  pop     rbp
0x18000eada  pop     rbx
0x18000eadb  retn
0x18000eadd  mov     ebx, 0C000000Dh
0x18000eae2  jmp     short loc_18000EAC9
```
