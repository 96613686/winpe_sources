# DevAuthGetRunningHash

- ea: `0x1800027dc`
- end: `0x180002881`
- name: `DevAuthGetRunningHash`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e04`
- `0x180002444`
- `0x180003e20`
- `0x180004368`

## callees

- `0x1800027dc`
- `0x180003320`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180002869`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002869`
- `cng!BCryptFinishHash` at `0x180002835`
- `cng!BCryptFinishHash` at `0x180002835`
- `cng!BCryptDestroyHash` at `0x180002853`
- `cng!BCryptDestroyHash` at `0x180002853`
- `cng!BCryptDuplicateHash` at `0x180002816`
- `cng!BCryptDuplicateHash` at `0x180002816`

## pseudocode

```c
_BOOL8 __fastcall DevAuthGetRunningHash(__int64 a1, UCHAR *a2)
{
  BOOL v3; // edi
  size_t v4; // rcx
  UCHAR *v6; // rax
  UCHAR *v7; // rbx
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v4 = *(unsigned int *)(a1 + 24);
  phNewHash = 0;
  v6 = (UCHAR *)DevAuthAlloc(v4);
  v7 = v6;
  if ( v6 && BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a1 + 8), &phNewHash, v6, *(_DWORD *)(a1 + 24), 0) >= 0 )
    v3 = BCryptFinishHash(phNewHash, a2, 0x20u, 0) >= 0;
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return v3;
}

```

## disassembly

```asm
0x1800027dc  push    rbx
0x1800027de  push    rbp
0x1800027df  push    rsi
0x1800027e0  push    rdi
0x1800027e1  sub     rsp, 38h
0x1800027e5  mov     rsi, rcx
0x1800027e8  xor     edi, edi
0x1800027ea  mov     ecx, [rcx+18h]; Size
0x1800027ed  mov     rbp, rdx
0x1800027f0  mov     [rsp+58h+phNewHash], rdi
0x1800027f5  call    DevAuthAlloc
0x1800027fa  mov     rbx, rax
0x1800027fd  test    rax, rax
0x180002800  jz      short loc_180002849
0x180002802  mov     r9d, [rsi+18h]; cbHashObject
0x180002806  lea     rdx, [rsp+58h+phNewHash]; phNewHash
0x18000280b  mov     rcx, [rsi+8]; hHash
0x18000280f  mov     r8, rax; pbHashObject
0x180002812  mov     [rsp+58h+dwFlags], edi; dwFlags
0x180002816  call    cs:__imp_BCryptDuplicateHash
0x18000281d  nop     dword ptr [rax+rax+00h]
0x180002822  test    eax, eax
0x180002824  js      short loc_180002849
0x180002826  mov     rcx, [rsp+58h+phNewHash]; hHash
0x18000282b  lea     r8d, [rdi+20h]; cbOutput
0x18000282f  xor     r9d, r9d; dwFlags
0x180002832  mov     rdx, rbp; pbOutput
0x180002835  call    cs:__imp_BCryptFinishHash
0x18000283c  nop     dword ptr [rax+rax+00h]
0x180002841  test    eax, eax
0x180002843  lea     ecx, [rdi+1]
0x180002846  cmovns  edi, ecx
0x180002849  mov     rcx, [rsp+58h+phNewHash]; hHash
0x18000284e  test    rcx, rcx
0x180002851  jz      short loc_18000285F
0x180002853  call    cs:__imp_BCryptDestroyHash
0x18000285a  nop     dword ptr [rax+rax+00h]
0x18000285f  test    rbx, rbx
0x180002862  jz      short loc_180002875
0x180002864  xor     edx, edx; Tag
0x180002866  mov     rcx, rbx; P
0x180002869  call    cs:__imp_ExFreePoolWithTag
0x180002870  nop     dword ptr [rax+rax+00h]
0x180002875  mov     eax, edi
0x180002877  add     rsp, 38h
0x18000287b  pop     rdi
0x18000287c  pop     rsi
0x18000287d  pop     rbp
0x18000287e  pop     rbx
0x18000287f  retn
```
