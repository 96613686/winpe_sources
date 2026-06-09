# CopyRoiTwoPlane(tagRECT const &,ParameterBase const *)

- ea: `0x180075c50`
- end: `0x180075dbb`
- name: `?CopyRoiTwoPlane@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180075c50`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180075cf5`
- `MFPlat!MFCopyImage` at `0x180075da3`
- `MFPlat!MFCopyImage` at `0x180075cf5`
- `MFPlat!MFCopyImage` at `0x180075da3`

## pseudocode

```c
__int64 __fastcall CopyRoiTwoPlane(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  LONG v3; // r13d
  int v4; // r8d
  int v5; // r9d
  int v6; // eax
  DWORD dwLines; // r14d
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // r12
  DWORD dwWidthInBytes; // esi
  int v11; // ecx
  __int64 v13; // [rsp+30h] [rbp-48h]
  LONG v14; // [rsp+80h] [rbp+8h]
  int v15; // [rsp+88h] [rbp+10h]
  LONG top; // [rsp+90h] [rbp+18h]
  __int64 v17; // [rsp+98h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 6);
  v4 = *((_DWORD *)a2 + 24);
  v5 = *((_DWORD *)a2 + 26);
  v6 = *((_DWORD *)a2 + 25);
  dwLines = *((_DWORD *)a2 + 28) - v5;
  v15 = v5;
  v8 = (unsigned __int64)(unsigned int)(v4 * v6) >> 3;
  v9 = (unsigned __int64)(unsigned int)(a1->left * v4) >> 3;
  dwWidthInBytes = (unsigned int)(v4 * (*((_DWORD *)a2 + 27) - v6)) >> 3;
  v17 = *((_QWORD *)a2 + 2);
  v13 = *(_QWORD *)a2;
  v14 = *((_DWORD *)a2 + 2);
  top = a1->top;
  if ( !MFCopyImage(
          (BYTE *)(*(_QWORD *)a2 + v9 + v14 * top),
          v14,
          (const BYTE *)(v17 + v8 + v3 * v5),
          v3,
          dwWidthInBytes,
          dwLines) )
  {
    v11 = *((_DWORD *)a2 + 21);
    if ( v11 > 0 && *((int *)a2 + 22) > 0 )
      MFCopyImage(
        (BYTE *)(v13 + v9 + v14 / v11 * (top / *((_DWORD *)a2 + 22)) + *((_DWORD *)a2 + 3) * v14),
        v14 / v11,
        (const BYTE *)(v17 + v8 + v3 / v11 * (v15 / *((_DWORD *)a2 + 22)) + *((_DWORD *)a2 + 7) * v3),
        v3 / v11,
        dwWidthInBytes / v11,
        dwLines / *((_DWORD *)a2 + 22));
  }
  return 0;
}

```

## disassembly

```asm
0x180075c50  push    rbx
0x180075c52  push    rsi
0x180075c53  push    rdi
0x180075c54  push    r12
0x180075c56  push    r13
0x180075c58  push    r14
0x180075c5a  push    r15
0x180075c5c  sub     rsp, 40h
0x180075c60  mov     ebx, [rcx+4]
0x180075c63  mov     rdi, rdx
0x180075c66  mov     r13d, [rdx+18h]
0x180075c6a  mov     r10, [rdx+10h]
0x180075c6e  mov     r11, [rdx]
0x180075c71  mov     r8d, [rdi+60h]
0x180075c75  mov     r9d, [rdi+68h]
0x180075c79  mov     eax, [rdi+64h]
0x180075c7c  mov     edx, [rdx+8]; lDestStride
0x180075c7f  mov     esi, [rdi+6Ch]
0x180075c82  mov     r14d, [rdi+70h]
0x180075c86  sub     esi, eax
0x180075c88  imul    eax, r8d
0x180075c8c  sub     r14d, r9d
0x180075c8f  imul    esi, r8d
0x180075c93  imul    r8d, [rcx]
0x180075c97  mov     [rsp+78h+arg_8], r9d
0x180075c9f  mov     [rsp+78h+dwLines], r14d; dwLines
0x180075ca4  mov     r15d, eax
0x180075ca7  mov     eax, r9d
0x180075caa  imul    eax, r13d
0x180075cae  mov     r9d, r13d; lSrcStride
0x180075cb1  mov     r12d, r8d
0x180075cb4  shr     r15, 3
0x180075cb8  shr     r12, 3
0x180075cbc  shr     esi, 3
0x180075cbf  movsxd  r8, eax
0x180075cc2  mov     eax, ebx
0x180075cc4  imul    eax, edx
0x180075cc7  add     r8, r15
0x180075cca  add     r8, r10; pSrc
0x180075ccd  mov     [rsp+78h+arg_18], r10
0x180075cd5  mov     [rsp+78h+var_48], r11
0x180075cda  mov     [rsp+78h+arg_0], edx
0x180075ce1  mov     [rsp+78h+arg_10], ebx
0x180075ce8  movsxd  rcx, eax
0x180075ceb  add     rcx, r12
0x180075cee  mov     [rsp+78h+dwWidthInBytes], esi; dwWidthInBytes
0x180075cf2  add     rcx, r11; pDest
0x180075cf5  call    cs:__imp_MFCopyImage
0x180075cfb  test    eax, eax
0x180075cfd  jnz     loc_180075DA9
0x180075d03  mov     ecx, [rdi+54h]
0x180075d06  test    ecx, ecx
0x180075d08  jle     loc_180075DA9
0x180075d0e  cmp     [rdi+58h], eax
0x180075d11  jle     loc_180075DA9
0x180075d17  mov     eax, r13d
0x180075d1a  imul    r13d, [rdi+1Ch]
0x180075d1f  cdq
0x180075d20  idiv    ecx
0x180075d22  movsxd  r8, r13d
0x180075d25  mov     ebx, eax
0x180075d27  mov     eax, [rsp+78h+arg_0]
0x180075d2e  cdq
0x180075d2f  idiv    ecx
0x180075d31  xor     edx, edx
0x180075d33  mov     r11d, eax
0x180075d36  mov     eax, r14d
0x180075d39  div     dword ptr [rdi+58h]
0x180075d3c  xor     edx, edx
0x180075d3e  mov     r10d, eax
0x180075d41  mov     eax, esi
0x180075d43  div     ecx
0x180075d45  mov     [rsp+78h+dwLines], r10d; dwLines
0x180075d4a  mov     r9d, eax
0x180075d4d  mov     eax, [rsp+78h+arg_8]
0x180075d54  cdq
0x180075d55  mov     [rsp+78h+dwWidthInBytes], r9d; dwWidthInBytes
0x180075d5a  idiv    dword ptr [rdi+58h]
0x180075d5d  mov     r9d, ebx; lSrcStride
0x180075d60  imul    eax, ebx
0x180075d63  movsxd  rcx, eax
0x180075d66  mov     eax, [rsp+78h+arg_10]
0x180075d6d  add     rcx, r15
0x180075d70  cdq
0x180075d71  add     r8, rcx
0x180075d74  idiv    dword ptr [rdi+58h]
0x180075d77  add     r8, [rsp+78h+arg_18]; pSrc
0x180075d7f  imul    eax, r11d
0x180075d83  movsxd  rdx, eax
0x180075d86  mov     eax, [rsp+78h+arg_0]
0x180075d8d  imul    eax, [rdi+0Ch]
0x180075d91  movsxd  rcx, eax
0x180075d94  lea     rax, [r12+rdx]
0x180075d98  add     rcx, rax
0x180075d9b  mov     edx, r11d; lDestStride
0x180075d9e  add     rcx, [rsp+78h+var_48]; pDest
0x180075da3  call    cs:__imp_MFCopyImage
0x180075da9  xor     eax, eax
0x180075dab  add     rsp, 40h
0x180075daf  pop     r15
0x180075db1  pop     r14
0x180075db3  pop     r13
0x180075db5  pop     r12
0x180075db7  pop     rdi
0x180075db8  pop     rsi
0x180075db9  pop     rbx
0x180075dba  retn
```
