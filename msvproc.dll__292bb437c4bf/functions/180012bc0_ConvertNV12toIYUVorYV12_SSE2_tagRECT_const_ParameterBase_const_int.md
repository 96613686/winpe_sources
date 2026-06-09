# ConvertNV12toIYUVorYV12_SSE2(tagRECT const &,ParameterBase const *,int)

- ea: `0x180012bc0`
- end: `0x180012d45`
- name: `?ConvertNV12toIYUVorYV12_SSE2@@YAJAEBUtagRECT@@PEBUParameterBase@@H@Z`
- size: `389`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012bc0`
- `0x180012d50`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180012cba`
- `MFPlat!MFCopyImage` at `0x180012cba`

## pseudocode

```c
__int64 __fastcall ConvertNV12toIYUVorYV12_SSE2(const struct tagRECT *a1, const struct ParameterBase *a2, int a3)
{
  LONG v3; // r12d
  int v4; // r14d
  __int64 v5; // rbp
  signed int v6; // r15d
  signed int v7; // edi
  signed int v8; // r10d
  signed int v9; // r11d
  __int64 v10; // rbx
  int v11; // r13d
  int v12; // eax
  int v13; // esi
  __int64 v15; // [rsp+40h] [rbp-58h]
  int v16; // [rsp+A8h] [rbp+10h]

  v3 = *((_DWORD *)a2 + 2);
  v4 = *((_DWORD *)a2 + 3);
  v5 = *((int *)a2 + 6);
  v6 = a1->left & 0xFFFFFFFE;
  v7 = a1->right & 0xFFFFFFFE;
  v8 = a1->top & 0xFFFFFFFE;
  v15 = *((_QWORD *)a2 + 2);
  v9 = a1->bottom & 0xFFFFFFFE;
  v10 = v3 * v4 + *(_QWORD *)a2;
  v11 = v8 / 2;
  v16 = v9 / 2;
  v12 = v3 / 2 * (v4 / 2);
  if ( a3 )
  {
    v13 = v10 + v12;
  }
  else
  {
    v13 = v3 * v4 + *(_DWORD *)a2;
    v10 += v12;
  }
  MFCopyImage(
    (BYTE *)(*(_QWORD *)a2 + v6 + (__int64)(v3 * v8)),
    v3,
    (const BYTE *)(v15 + v6 + (__int64)((int)v5 * v8)),
    v5,
    v7 - v6,
    v9 - v8);
  DeInterleave_SSE2(
    v7 / 2 - v6 / 2,
    v16 - v11,
    v5 * v11 + v15 + v5 * v4 + 2 * (v6 / 2),
    v6 / 2 + v11 * (v3 / 2) + v13,
    v6 / 2 + (__int64)(v11 * (v3 / 2)) + v10,
    v5,
    v3 / 2);
  return 0;
}

```

## disassembly

```asm
0x180012bc0  push    rbx
0x180012bc2  push    rbp
0x180012bc3  push    rsi
0x180012bc4  push    rdi
0x180012bc5  push    r12
0x180012bc7  push    r13
0x180012bc9  push    r14
0x180012bcb  push    r15
0x180012bcd  sub     rsp, 58h
0x180012bd1  mov     rax, [rdx+10h]
0x180012bd5  mov     r12d, [rdx+8]
0x180012bd9  mov     r14d, [rdx+0Ch]
0x180012bdd  mov     rbx, [rdx]
0x180012be0  movsxd  rbp, dword ptr [rdx+18h]
0x180012be4  mov     r15d, [rcx]
0x180012be7  mov     edi, [rcx+8]
0x180012bea  and     r15d, 0FFFFFFFEh
0x180012bee  mov     r10d, [rcx+4]
0x180012bf2  and     edi, 0FFFFFFFEh
0x180012bf5  mov     r11d, [rcx+0Ch]
0x180012bf9  and     r10d, 0FFFFFFFEh
0x180012bfd  mov     [rsp+98h+var_58], rax
0x180012c02  and     r11d, 0FFFFFFFEh
0x180012c06  mov     eax, r15d
0x180012c09  mov     [rsp+98h+var_50], rbx
0x180012c0e  cdq
0x180012c0f  mov     ecx, r14d
0x180012c12  sub     eax, edx
0x180012c14  imul    ecx, r12d
0x180012c18  sar     eax, 1
0x180012c1a  mov     [rsp+98h+arg_10], eax
0x180012c21  mov     eax, edi
0x180012c23  cdq
0x180012c24  sub     eax, edx
0x180012c26  sar     eax, 1
0x180012c28  mov     [rsp+98h+arg_18], eax
0x180012c2f  mov     eax, r10d
0x180012c32  cdq
0x180012c33  movsxd  rcx, ecx
0x180012c36  sub     eax, edx
0x180012c38  add     rbx, rcx
0x180012c3b  sar     eax, 1
0x180012c3d  mov     r13d, eax
0x180012c40  mov     eax, r11d
0x180012c43  cdq
0x180012c44  sub     eax, edx
0x180012c46  sar     eax, 1
0x180012c48  mov     [rsp+98h+arg_8], eax
0x180012c4f  mov     eax, r12d
0x180012c52  cdq
0x180012c53  sub     eax, edx
0x180012c55  sar     eax, 1
0x180012c57  mov     r9d, eax
0x180012c5a  mov     [rsp+98h+arg_0], eax
0x180012c61  mov     eax, r14d
0x180012c64  cdq
0x180012c65  sub     eax, edx
0x180012c67  sar     eax, 1
0x180012c69  imul    eax, r9d
0x180012c6d  movsxd  rdx, eax
0x180012c70  add     rdx, rbx
0x180012c73  test    r8d, r8d
0x180012c76  jnz     loc_180012D3D
0x180012c7c  mov     rsi, rbx
0x180012c7f  mov     rbx, rdx
0x180012c82  movsxd  r9, r15d
0x180012c85  mov     eax, r10d
0x180012c88  sub     r11d, r10d
0x180012c8b  imul    eax, ebp
0x180012c8e  imul    r10d, r12d
0x180012c92  sub     edi, r15d
0x180012c95  mov     [rsp+98h+dwLines], r11d; dwLines
0x180012c9a  mov     edx, r12d; lDestStride
0x180012c9d  mov     [rsp+98h+dwWidthInBytes], edi; dwWidthInBytes
0x180012ca1  movsxd  r8, eax
0x180012ca4  add     r8, r9
0x180012ca7  movsxd  rcx, r10d
0x180012caa  add     r8, [rsp+98h+var_58]; pSrc
0x180012caf  add     rcx, r9
0x180012cb2  add     rcx, [rsp+98h+var_50]; pDest
0x180012cb7  mov     r9d, ebp; lSrcStride
0x180012cba  call    cs:__imp_MFCopyImage
0x180012cc0  movsxd  rdx, [rsp+98h+arg_0]
0x180012cc8  movsxd  r12, [rsp+98h+arg_10]
0x180012cd0  mov     eax, edx
0x180012cd2  imul    eax, r13d
0x180012cd6  mov     r11, rdx
0x180012cd9  mov     edx, [rsp+98h+arg_8]
0x180012ce0  mov     [rsp+98h+var_68], r11
0x180012ce5  sub     edx, r13d
0x180012ce8  imul    r14d, ebp
0x180012cec  mov     qword ptr [rsp+98h+dwLines], rbp
0x180012cf1  movsxd  rcx, eax
0x180012cf4  mov     eax, r13d
0x180012cf7  imul    eax, ebp
0x180012cfa  add     rcx, r12
0x180012cfd  add     rbx, rcx
0x180012d00  mov     qword ptr [rsp+98h+dwWidthInBytes], rbx
0x180012d05  lea     r9, [rcx+rsi]
0x180012d09  mov     ecx, [rsp+98h+arg_18]
0x180012d10  movsxd  r8, eax
0x180012d13  sub     ecx, r12d
0x180012d16  movsxd  rax, r14d
0x180012d19  add     rax, [rsp+98h+var_58]
0x180012d1e  add     rax, r8
0x180012d21  lea     r8, [rax+r12*2]
0x180012d25  call    DeInterleave_SSE2
0x180012d2a  xor     eax, eax
0x180012d2c  add     rsp, 58h
0x180012d30  pop     r15
0x180012d32  pop     r14
0x180012d34  pop     r13
0x180012d36  pop     r12
0x180012d38  pop     rdi
0x180012d39  pop     rsi
0x180012d3a  pop     rbp
0x180012d3b  pop     rbx
0x180012d3c  retn
0x180012d3d  mov     rsi, rdx
0x180012d40  jmp     loc_180012C82
```
