# CalculateResponse

- ea: `0x1400184d4`
- end: `0x14001860d`
- name: `CalculateResponse`
- size: `313`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR@<r8>, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400133ac`
- `0x1400135f0`
- `0x140013820`

## callees

- `0x1400047f0`
- `0x1400184d4`

## import_xrefs

- `cng!BCryptCreateHash` at `0x140018535`
- `cng!BCryptCreateHash` at `0x140018535`
- `cng!BCryptHashData` at `0x140018558`
- `cng!BCryptHashData` at `0x140018582`
- `cng!BCryptHashData` at `0x1400185a1`
- `cng!BCryptHashData` at `0x140018558`
- `cng!BCryptHashData` at `0x140018582`
- `cng!BCryptHashData` at `0x1400185a1`
- `cng!BCryptDestroyHash` at `0x1400185e5`
- `cng!BCryptDestroyHash` at `0x1400185e5`
- `cng!BCryptFinishHash` at `0x1400185c2`
- `cng!BCryptFinishHash` at `0x1400185c2`

## pseudocode

```c
NTSTATUS __fastcall CalculateResponse(PUCHAR pbInput, ULONG cbInput, PUCHAR a3, UCHAR a4, _OWORD *a5)
{
  NTSTATUS result; // eax
  NTSTATUS v9; // ebx
  __int64 v10; // r8
  UCHAR pbInputa[8]; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-30h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-28h] BYREF

  pbInputa[0] = a4;
  phHash = 0;
  result = BCryptCreateHash(ghAlgMD5, &phHash, 0, 0, 0, 0, 0);
  if ( result >= 0 )
  {
    v9 = BCryptHashData(phHash, pbInputa, 1u, 0);
    if ( v9 >= 0 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a3[v10] );
      v9 = BCryptHashData(phHash, a3, v10, 0);
      if ( v9 >= 0 )
      {
        v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( v9 >= 0 )
        {
          v9 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
          if ( v9 >= 0 )
            *a5 = *(_OWORD *)pbOutput;
        }
      }
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400184d4  push    rbp
0x1400184d6  push    rbx
0x1400184d7  push    rsi
0x1400184d8  push    rdi
0x1400184d9  push    r14
0x1400184db  push    r15
0x1400184dd  mov     rbp, rsp
0x1400184e0  sub     rsp, 78h
0x1400184e4  mov     rax, cs:__security_cookie
0x1400184eb  xor     rax, rsp
0x1400184ee  mov     [rbp+var_18], rax
0x1400184f2  mov     rsi, [rbp+arg_20]
0x1400184f6  mov     rdi, r8
0x1400184f9  mov     r15d, edx
0x1400184fc  mov     [rbp+pbInput], r9b
0x140018500  mov     r14, rcx
0x140018503  mov     [rsp+78h+dwFlags], 0; dwFlags
0x14001850b  mov     rcx, cs:ghAlgMD5; hAlgorithm
0x140018512  lea     rdx, [rbp+phHash]; phHash
0x140018516  mov     [rsp+78h+cbSecret], 0; cbSecret
0x14001851e  xor     r9d, r9d; cbHashObject
0x140018521  xor     r8d, r8d; pbHashObject
0x140018524  mov     [rsp+78h+pbSecret], 0; pbSecret
0x14001852d  mov     [rbp+phHash], 0
0x140018535  call    cs:__imp_BCryptCreateHash
0x14001853c  nop     dword ptr [rax+rax+00h]
0x140018541  test    eax, eax
0x140018543  js      loc_1400185F3
0x140018549  mov     rcx, [rbp+phHash]; hHash
0x14001854d  lea     rdx, [rbp+pbInput]; pbInput
0x140018551  xor     r9d, r9d; dwFlags
0x140018554  lea     r8d, [r9+1]; cbInput
0x140018558  call    cs:__imp_BCryptHashData
0x14001855f  nop     dword ptr [rax+rax+00h]
0x140018564  mov     ebx, eax
0x140018566  test    eax, eax
0x140018568  js      short loc_1400185DC
0x14001856a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001856e  inc     r8; cbInput
0x140018571  cmp     byte ptr [rdi+r8], 0
0x140018576  jnz     short loc_14001856E
0x140018578  mov     rcx, [rbp+phHash]; hHash
0x14001857c  xor     r9d, r9d; dwFlags
0x14001857f  mov     rdx, rdi; pbInput
0x140018582  call    cs:__imp_BCryptHashData
0x140018589  nop     dword ptr [rax+rax+00h]
0x14001858e  mov     ebx, eax
0x140018590  test    eax, eax
0x140018592  js      short loc_1400185DC
0x140018594  mov     rcx, [rbp+phHash]; hHash
0x140018598  xor     r9d, r9d; dwFlags
0x14001859b  mov     r8d, r15d; cbInput
0x14001859e  mov     rdx, r14; pbInput
0x1400185a1  call    cs:__imp_BCryptHashData
0x1400185a8  nop     dword ptr [rax+rax+00h]
0x1400185ad  mov     ebx, eax
0x1400185af  test    eax, eax
0x1400185b1  js      short loc_1400185DC
0x1400185b3  mov     rcx, [rbp+phHash]; hHash
0x1400185b7  lea     rdx, [rbp+pbOutput]; pbOutput
0x1400185bb  xor     r9d, r9d; dwFlags
0x1400185be  lea     r8d, [r9+10h]; cbOutput
0x1400185c2  call    cs:__imp_BCryptFinishHash
0x1400185c9  nop     dword ptr [rax+rax+00h]
0x1400185ce  mov     ebx, eax
0x1400185d0  test    eax, eax
0x1400185d2  js      short loc_1400185DC
0x1400185d4  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x1400185d8  movdqu  xmmword ptr [rsi], xmm0
0x1400185dc  mov     rcx, [rbp+phHash]; hHash
0x1400185e0  test    rcx, rcx
0x1400185e3  jz      short loc_1400185F1
0x1400185e5  call    cs:__imp_BCryptDestroyHash
0x1400185ec  nop     dword ptr [rax+rax+00h]
0x1400185f1  mov     eax, ebx
0x1400185f3  mov     rcx, [rbp+var_18]
0x1400185f7  xor     rcx, rsp; StackCookie
0x1400185fa  call    __security_check_cookie
0x1400185ff  add     rsp, 78h
0x140018603  pop     r15
0x140018605  pop     r14
0x140018607  pop     rdi
0x140018608  pop     rsi
0x140018609  pop     rbx
0x14001860a  pop     rbp
0x14001860b  retn
```
