# CalculateHash(ushort const *,uchar *,ulong,uchar *,ulong)

- ea: `0x18000d7b0`
- end: `0x18000d8bf`
- name: `?CalculateHash@@YAJPEBGPEAEK1K@Z`
- size: `271`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d7b0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000d810`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000d810`
- `bcrypt!BCryptCreateHash` at `0x18000d83e`
- `bcrypt!BCryptCreateHash` at `0x18000d83e`
- `bcrypt!BCryptFinishHash` at `0x18000d878`
- `bcrypt!BCryptFinishHash` at `0x18000d878`
- `bcrypt!BCryptHashData` at `0x18000d85b`
- `bcrypt!BCryptHashData` at `0x18000d85b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d88c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d88c`
- `bcrypt!BCryptDestroyHash` at `0x18000d89f`
- `bcrypt!BCryptDestroyHash` at `0x18000d89f`

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
0x18000d7b0  push    rbx
0x18000d7b2  push    rbp
0x18000d7b3  push    rsi
0x18000d7b4  push    rdi
0x18000d7b5  push    r14
0x18000d7b7  push    r15
0x18000d7b9  sub     rsp, 58h
0x18000d7bd  xor     r15d, r15d
0x18000d7c0  mov     rsi, r9
0x18000d7c3  mov     [rsp+88h+phAlgorithm], r15
0x18000d7c8  mov     ebp, r8d
0x18000d7cb  mov     [rsp+88h+phHash], r15
0x18000d7d3  mov     rdi, rdx
0x18000d7d6  test    rdx, rdx
0x18000d7d9  jz      loc_18000D8B8
0x18000d7df  test    r8d, r8d
0x18000d7e2  jz      loc_18000D8B8
0x18000d7e8  test    r9, r9
0x18000d7eb  jz      loc_18000D8B8
0x18000d7f1  mov     r14d, [rsp+88h+cbOutput]
0x18000d7f9  test    r14d, r14d
0x18000d7fc  jz      loc_18000D8B8
0x18000d802  mov     rdx, rcx; pszAlgId
0x18000d805  xor     r9d, r9d; dwFlags
0x18000d808  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x18000d80d  xor     r8d, r8d; pszImplementation
0x18000d810  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000d816  mov     ebx, eax
0x18000d818  test    eax, eax
0x18000d81a  js      short loc_18000D880
0x18000d81c  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18000d821  lea     rdx, [rsp+88h+phHash]; phHash
0x18000d829  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18000d82e  xor     r9d, r9d; cbHashObject
0x18000d831  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18000d836  xor     r8d, r8d; pbHashObject
0x18000d839  mov     [rsp+88h+pbSecret], r15; pbSecret
0x18000d83e  call    cs:__imp_BCryptCreateHash
0x18000d844  mov     ebx, eax
0x18000d846  test    eax, eax
0x18000d848  js      short loc_18000D880
0x18000d84a  mov     rcx, [rsp+88h+phHash]; hHash
0x18000d852  xor     r9d, r9d; dwFlags
0x18000d855  mov     r8d, ebp; cbInput
0x18000d858  mov     rdx, rdi; pbInput
0x18000d85b  call    cs:__imp_BCryptHashData
0x18000d861  mov     ebx, eax
0x18000d863  test    eax, eax
0x18000d865  js      short loc_18000D880
0x18000d867  mov     rcx, [rsp+88h+phHash]; hHash
0x18000d86f  xor     r9d, r9d; dwFlags
0x18000d872  mov     r8d, r14d; cbOutput
0x18000d875  mov     rdx, rsi; pbOutput
0x18000d878  call    cs:__imp_BCryptFinishHash
0x18000d87e  mov     ebx, eax
0x18000d880  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18000d885  test    rcx, rcx
0x18000d888  jz      short loc_18000D892
0x18000d88a  xor     edx, edx; dwFlags
0x18000d88c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000d892  mov     rcx, [rsp+88h+phHash]; hHash
0x18000d89a  test    rcx, rcx
0x18000d89d  jz      short loc_18000D8A5
0x18000d89f  call    cs:__imp_BCryptDestroyHash
0x18000d8a5  bts     ebx, 1Ch
0x18000d8a9  mov     eax, ebx
0x18000d8ab  add     rsp, 58h
0x18000d8af  pop     r15
0x18000d8b1  pop     r14
0x18000d8b3  pop     rdi
0x18000d8b4  pop     rsi
0x18000d8b5  pop     rbp
0x18000d8b6  pop     rbx
0x18000d8b7  retn
0x18000d8b8  mov     ebx, 0C000000Dh
0x18000d8bd  jmp     short loc_18000D8A5
```
