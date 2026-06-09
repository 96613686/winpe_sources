# CngRsa32Compat_MD5Init

- ea: `0x140012548`
- end: `0x1400125d4`
- name: `CngRsa32Compat_MD5Init`
- size: `140`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14003edd4`

## callees

- `0x140012548`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001256f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001256f`
- `ksecdd!BCryptCreateHash` at `0x1400125ad`
- `ksecdd!BCryptCreateHash` at `0x1400125ad`

## pseudocode

```c
BCRYPT_ALG_HANDLE __fastcall CngRsa32Compat_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  BCRYPT_ALG_HANDLE result; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 1u) < 0 )
    __fastfail(7u);
  if ( BCryptCreateHash(phAlgorithm, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  result = phAlgorithm;
  phHash[1] = phAlgorithm;
  return result;
}

```

## disassembly

```asm
0x140012548  push    rbx
0x14001254a  sub     rsp, 40h
0x14001254e  mov     rbx, rcx
0x140012551  mov     [rsp+48h+phAlgorithm], 0
0x14001255a  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x14001255f  mov     r9d, 1; dwFlags
0x140012565  xor     r8d, r8d; pszImplementation
0x140012568  lea     rdx, pszAlgId; "MD5"
0x14001256f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140012576  nop     dword ptr [rax+rax+00h]
0x14001257b  test    eax, eax
0x14001257d  jns     short loc_140012586
0x14001257f  mov     ecx, 7
0x140012584  int     29h; Win8: RtlFailFast(ecx)
0x140012586  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x14001258b  xor     r9d, r9d; cbHashObject
0x14001258e  mov     [rsp+48h+dwFlags], 0; dwFlags
0x140012596  xor     r8d, r8d; pbHashObject
0x140012599  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1400125a1  mov     rdx, rbx; phHash
0x1400125a4  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1400125ad  call    cs:__imp_BCryptCreateHash
0x1400125b4  nop     dword ptr [rax+rax+00h]
0x1400125b9  test    eax, eax
0x1400125bb  jns     short loc_1400125C4
0x1400125bd  mov     ecx, 7
0x1400125c2  int     29h; Win8: RtlFailFast(ecx)
0x1400125c4  mov     rax, [rsp+48h+phAlgorithm]
0x1400125c9  mov     [rbx+8], rax
0x1400125cd  add     rsp, 40h
0x1400125d1  pop     rbx
0x1400125d2  retn
```
