# UlpComputeSecureHash

- ea: `0x1c004a54c`
- end: `0x1c004a6d7`
- name: `UlpComputeSecureHash`
- size: `395`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1c01374ac`

## callees

- `0x1c001a4b0`
- `0x1c004a54c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c004a5e8`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c004a5e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004a6aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004a6aa`
- `ksecdd!BCryptDestroyHash` at `0x1c004a67f`
- `ksecdd!BCryptDestroyHash` at `0x1c004a67f`
- `ksecdd!BCryptFinishHash` at `0x1c004a667`
- `ksecdd!BCryptFinishHash` at `0x1c004a667`
- `ksecdd!BCryptHashData` at `0x1c004a643`
- `ksecdd!BCryptHashData` at `0x1c004a643`
- `ksecdd!BCryptCreateHash` at `0x1c004a623`
- `ksecdd!BCryptCreateHash` at `0x1c004a623`
- `ksecdd!BCryptGetProperty` at `0x1c004a5ac`
- `ksecdd!BCryptGetProperty` at `0x1c004a5ac`

## pseudocode

```c
__int64 __fastcall UlpComputeSecureHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput)
{
  UCHAR *PoolWithTagPriority; // rbx
  NTSTATUS Property; // esi
  ULONG v11; // r9d
  UCHAR pbOutputa[4]; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult[4]; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR pbHashObject[256]; // [rsp+60h] [rbp-A0h] BYREF

  phHash = 0;
  pcbResult[0] = 0;
  PoolWithTagPriority = 0;
  *(_DWORD *)pbOutputa = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutputa, 4u, pcbResult, 0);
  if ( Property >= 0 )
  {
    v11 = *(_DWORD *)pbOutputa;
    if ( *(_DWORD *)pbOutputa > 0x100u )
    {
      PoolWithTagPriority = (UCHAR *)ExAllocatePoolWithTagPriority(
                                       (POOL_TYPE)512,
                                       *(unsigned int *)pbOutputa,
                                       0x51586C55u,
                                       LowPoolPriority);
      if ( !PoolWithTagPriority )
      {
        Property = -1073741670;
        goto LABEL_10;
      }
      v11 = *(_DWORD *)pbOutputa;
    }
    else
    {
      PoolWithTagPriority = pbHashObject;
    }
    Property = BCryptCreateHash(hAlgorithm, &phHash, PoolWithTagPriority, v11, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( Property >= 0 )
        Property = BCryptFinishHash(phHash, pbOutput, cbOutput, 0);
    }
  }
LABEL_10:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( PoolWithTagPriority )
  {
    memset(PoolWithTagPriority, 0, *(unsigned int *)pbOutputa);
    if ( PoolWithTagPriority != pbHashObject )
      ExFreePoolWithTag(PoolWithTagPriority, 0);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1c004a54c  push    rbp
0x1c004a54e  push    rbx
0x1c004a54f  push    rsi
0x1c004a550  push    rdi
0x1c004a551  push    r12
0x1c004a553  push    r14
0x1c004a555  push    r15
0x1c004a557  lea     rbp, [rsp-70h]
0x1c004a55c  sub     rsp, 170h
0x1c004a563  mov     rax, cs:__security_cookie
0x1c004a56a  xor     rax, rsp
0x1c004a56d  mov     [rbp+0A0h+var_40], rax
0x1c004a571  and     [rsp+1A0h+phHash], 0
0x1c004a577  lea     rax, [rsp+1A0h+var_150]
0x1c004a57c  and     [rsp+1A0h+var_150], 0
0x1c004a581  xor     ebx, ebx
0x1c004a583  and     [rsp+1A0h+var_178], ebx
0x1c004a587  mov     r14, r9
0x1c004a58a  and     dword ptr [rsp+1A0h+pbOutput], ebx
0x1c004a58e  mov     r12d, r8d
0x1c004a591  mov     r15, rdx
0x1c004a594  mov     [rsp+1A0h+pcbResult], rax; pbSecret
0x1c004a599  lea     r9d, [rbx+4]; cbOutput
0x1c004a59d  mov     rdi, rcx
0x1c004a5a0  lea     r8, [rsp+1A0h+pbOutput]; pbOutput
0x1c004a5a5  lea     rdx, pszProperty; "ObjectLength"
0x1c004a5ac  call    cs:__imp_BCryptGetProperty
0x1c004a5b3  nop     dword ptr [rax+rax+00h]
0x1c004a5b8  mov     esi, eax
0x1c004a5ba  test    eax, eax
0x1c004a5bc  js      loc_1C004A675
0x1c004a5c2  mov     r9d, dword ptr [rsp+1A0h+pbOutput]
0x1c004a5c7  cmp     r9d, 100h
0x1c004a5ce  ja      short loc_1C004A5D7
0x1c004a5d0  lea     rbx, [rsp+1A0h+pbHashObject]
0x1c004a5d5  jmp     short loc_1C004A608
0x1c004a5d7  mov     rdx, r9; NumberOfBytes
0x1c004a5da  mov     ecx, 200h; PoolType
0x1c004a5df  xor     r9d, r9d; Priority
0x1c004a5e2  mov     r8d, 51586C55h; Tag
0x1c004a5e8  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c004a5ef  nop     dword ptr [rax+rax+00h]
0x1c004a5f4  mov     rbx, rax
0x1c004a5f7  test    rax, rax
0x1c004a5fa  jnz     short loc_1C004A603
0x1c004a5fc  mov     esi, 0C000009Ah
0x1c004a601  jmp     short loc_1C004A675
0x1c004a603  mov     r9d, dword ptr [rsp+1A0h+pbOutput]; cbHashObject
0x1c004a608  and     [rsp+1A0h+var_170], 0
0x1c004a60d  lea     rdx, [rsp+1A0h+phHash]; phHash
0x1c004a612  and     [rsp+1A0h+var_178], 0
0x1c004a617  mov     r8, rbx; pbHashObject
0x1c004a61a  and     [rsp+1A0h+pcbResult], 0
0x1c004a620  mov     rcx, rdi; hAlgorithm
0x1c004a623  call    cs:__imp_BCryptCreateHash
0x1c004a62a  nop     dword ptr [rax+rax+00h]
0x1c004a62f  mov     esi, eax
0x1c004a631  test    eax, eax
0x1c004a633  js      short loc_1C004A675
0x1c004a635  mov     rcx, [rsp+1A0h+phHash]; hHash
0x1c004a63a  xor     r9d, r9d; dwFlags
0x1c004a63d  mov     r8d, r12d; cbInput
0x1c004a640  mov     rdx, r15; pbInput
0x1c004a643  call    cs:__imp_BCryptHashData
0x1c004a64a  nop     dword ptr [rax+rax+00h]
0x1c004a64f  mov     esi, eax
0x1c004a651  test    eax, eax
0x1c004a653  js      short loc_1C004A675
0x1c004a655  mov     r8d, [rbp+0A0h+cbOutput]; cbOutput
0x1c004a65c  xor     r9d, r9d; dwFlags
0x1c004a65f  mov     rcx, [rsp+1A0h+phHash]; hHash
0x1c004a664  mov     rdx, r14; pbOutput
0x1c004a667  call    cs:__imp_BCryptFinishHash
0x1c004a66e  nop     dword ptr [rax+rax+00h]
0x1c004a673  mov     esi, eax
0x1c004a675  mov     rcx, [rsp+1A0h+phHash]; hHash
0x1c004a67a  test    rcx, rcx
0x1c004a67d  jz      short loc_1C004A68B
0x1c004a67f  call    cs:__imp_BCryptDestroyHash
0x1c004a686  nop     dword ptr [rax+rax+00h]
0x1c004a68b  test    rbx, rbx
0x1c004a68e  jz      short loc_1C004A6B6
0x1c004a690  mov     ecx, dword ptr [rsp+1A0h+pbOutput]
0x1c004a694  xor     eax, eax
0x1c004a696  mov     rdi, rbx
0x1c004a699  rep stosb
0x1c004a69b  lea     rax, [rsp+1A0h+pbHashObject]
0x1c004a6a0  cmp     rbx, rax
0x1c004a6a3  jz      short loc_1C004A6B6
0x1c004a6a5  xor     edx, edx; Tag
0x1c004a6a7  mov     rcx, rbx; P
0x1c004a6aa  call    cs:__imp_ExFreePoolWithTag
0x1c004a6b1  nop     dword ptr [rax+rax+00h]
0x1c004a6b6  mov     eax, esi
0x1c004a6b8  mov     rcx, [rbp+0A0h+var_40]
0x1c004a6bc  xor     rcx, rsp; StackCookie
0x1c004a6bf  call    __security_check_cookie
0x1c004a6c4  add     rsp, 170h
0x1c004a6cb  pop     r15
0x1c004a6cd  pop     r14
0x1c004a6cf  pop     r12
0x1c004a6d1  pop     rdi
0x1c004a6d2  pop     rsi
0x1c004a6d3  pop     rbx
0x1c004a6d4  pop     rbp
0x1c004a6d5  retn
```
