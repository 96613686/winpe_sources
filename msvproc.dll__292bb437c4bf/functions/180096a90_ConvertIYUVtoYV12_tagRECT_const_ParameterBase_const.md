# ConvertIYUVtoYV12(tagRECT const &,ParameterBase const *)

- ea: `0x180096a90`
- end: `0x180096c2e`
- name: `?ConvertIYUVtoYV12@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180096a90`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180096b1a`
- `MFPlat!MFCopyImage` at `0x180096bd2`
- `MFPlat!MFCopyImage` at `0x180096c0e`
- `MFPlat!MFCopyImage` at `0x180096b1a`
- `MFPlat!MFCopyImage` at `0x180096bd2`
- `MFPlat!MFCopyImage` at `0x180096c0e`

## pseudocode

```c
__int64 __fastcall ConvertIYUVtoYV12(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  signed int v2; // ebx
  LONG v3; // r15d
  signed int v4; // ebp
  signed int v5; // edi
  LONG v6; // r14d
  __int64 v7; // r13
  signed int v8; // esi
  int v9; // r12d
  __int64 v10; // rdi
  int v11; // r8d
  LONG v12; // ebx
  __int64 v13; // r15
  __int64 v14; // r14
  DWORD dwLines; // ebp
  DWORD dwWidthInBytes; // esi
  __int64 v17; // r13
  __int64 v18; // kr00_8
  int v20; // [rsp+70h] [rbp+8h]
  __int64 v21; // [rsp+70h] [rbp+8h]
  int lSrcStride; // [rsp+78h] [rbp+10h]
  __int64 v23; // [rsp+80h] [rbp+18h]

  v2 = a1->top & 0xFFFFFFFE;
  v3 = *((_DWORD *)a2 + 6);
  v4 = a1->bottom & 0xFFFFFFFE;
  v5 = a1->left & 0xFFFFFFFE;
  v7 = *((_QWORD *)a2 + 2);
  v8 = a1->right & 0xFFFFFFFE;
  v9 = *((_DWORD *)a2 + 3);
  v20 = *((_DWORD *)a2 + 7);
  v23 = *(_QWORD *)a2;
  v6 = *((_DWORD *)a2 + 2);
  if ( !MFCopyImage(
          (BYTE *)(*(_QWORD *)a2 + v5 + (__int64)(v6 * v2)),
          v6,
          (const BYTE *)(v7 + v5 + (__int64)(v3 * v2)),
          v3,
          v8 - v5,
          v4 - v2) )
  {
    lSrcStride = v3 / 2;
    v10 = v5 / 2;
    v11 = v2 / 2;
    v12 = v6 / 2;
    v13 = v7 + v3 * v20;
    v14 = v23 + v6 * v9;
    dwLines = v4 / 2 - v11;
    dwWidthInBytes = v8 / 2 - v10;
    v17 = lSrcStride * v11;
    v18 = v20;
    v21 = v11 * v12;
    if ( !MFCopyImage(
            (BYTE *)(v14 + v10 + v21),
            v12,
            (const BYTE *)(v13 + v10 + v17 + (int)(lSrcStride * (v18 / 2))),
            lSrcStride,
            dwWidthInBytes,
            dwLines) )
      MFCopyImage(
        (BYTE *)(v14 + v10 + v21 + v12 * (v9 / 2)),
        v12,
        (const BYTE *)(v13 + v10 + v17),
        lSrcStride,
        dwWidthInBytes,
        dwLines);
  }
  return 0;
}

```

## disassembly

```asm
0x180096a90  mov     [rsp+arg_18], rbx
0x180096a95  push    rbp
0x180096a96  push    rsi
0x180096a97  push    rdi
0x180096a98  push    r12
0x180096a9a  push    r13
0x180096a9c  push    r14
0x180096a9e  push    r15
0x180096aa0  sub     rsp, 30h
0x180096aa4  mov     ebx, [rcx+4]
0x180096aa7  mov     eax, [rdx+1Ch]
0x180096aaa  and     ebx, 0FFFFFFFEh
0x180096aad  mov     r15d, [rdx+18h]
0x180096ab1  mov     ebp, [rcx+0Ch]
0x180096ab4  mov     esi, [rcx+8]
0x180096ab7  and     ebp, 0FFFFFFFEh
0x180096aba  mov     edi, [rcx]
0x180096abc  mov     r10d, ebp
0x180096abf  mov     r11, [rdx]
0x180096ac2  and     edi, 0FFFFFFFEh
0x180096ac5  mov     r14d, [rdx+8]
0x180096ac9  sub     r10d, ebx
0x180096acc  mov     r13, [rdx+10h]
0x180096ad0  and     esi, 0FFFFFFFEh
0x180096ad3  mov     r12d, [rdx+0Ch]
0x180096ad7  mov     r9d, esi
0x180096ada  mov     dword ptr [rsp+68h+arg_0], eax
0x180096ade  sub     r9d, edi
0x180096ae1  movsxd  rdx, edi
0x180096ae4  mov     eax, ebx
0x180096ae6  imul    eax, r15d
0x180096aea  mov     [rsp+68h+dwLines], r10d; dwLines
0x180096aef  mov     [rsp+68h+dwWidthInBytes], r9d; dwWidthInBytes
0x180096af4  mov     r9d, r15d; lSrcStride
0x180096af7  mov     [rsp+68h+arg_10], r11
0x180096aff  movsxd  r8, eax
0x180096b02  mov     eax, ebx
0x180096b04  add     r8, rdx
0x180096b07  imul    eax, r14d
0x180096b0b  add     r8, r13; pSrc
0x180096b0e  movsxd  rcx, eax
0x180096b11  add     rcx, rdx
0x180096b14  mov     edx, r14d; lDestStride
0x180096b17  add     rcx, r11; pDest
0x180096b1a  call    cs:__imp_MFCopyImage
0x180096b20  test    eax, eax
0x180096b22  jnz     loc_180096C14
0x180096b28  mov     r10d, dword ptr [rsp+68h+arg_0]
0x180096b2d  mov     r11d, 2
0x180096b33  mov     eax, r15d
0x180096b36  cdq
0x180096b37  idiv    r11d
0x180096b3a  mov     r9d, eax; lSrcStride
0x180096b3d  mov     [rsp+68h+lSrcStride], eax
0x180096b41  mov     eax, edi
0x180096b43  cdq
0x180096b44  idiv    r11d
0x180096b47  movsxd  rcx, eax
0x180096b4a  mov     eax, ebx
0x180096b4c  cdq
0x180096b4d  mov     rdi, rcx
0x180096b50  idiv    r11d
0x180096b53  mov     r8d, eax
0x180096b56  mov     eax, r14d
0x180096b59  cdq
0x180096b5a  idiv    r11d
0x180096b5d  mov     ebx, eax
0x180096b5f  mov     eax, r10d
0x180096b62  imul    eax, r15d
0x180096b66  movsxd  r15, eax
0x180096b69  mov     eax, r12d
0x180096b6c  imul    eax, r14d
0x180096b70  add     r15, r13
0x180096b73  movsxd  r14, eax
0x180096b76  mov     eax, ebp
0x180096b78  add     r14, [rsp+68h+arg_10]
0x180096b80  cdq
0x180096b81  idiv    r11d
0x180096b84  mov     ebp, eax
0x180096b86  mov     eax, esi
0x180096b88  cdq
0x180096b89  sub     ebp, r8d
0x180096b8c  idiv    r11d
0x180096b8f  mov     [rsp+68h+dwLines], ebp; dwLines
0x180096b93  mov     esi, eax
0x180096b95  mov     eax, r8d
0x180096b98  imul    eax, r9d
0x180096b9c  sub     esi, ecx
0x180096b9e  mov     [rsp+68h+dwWidthInBytes], esi; dwWidthInBytes
0x180096ba2  movsxd  r13, eax
0x180096ba5  mov     eax, ebx
0x180096ba7  imul    eax, r8d
0x180096bab  movsxd  rcx, eax
0x180096bae  mov     eax, r10d
0x180096bb1  cdq
0x180096bb2  mov     [rsp+68h+arg_0], rcx
0x180096bb7  idiv    r11d
0x180096bba  add     rcx, rdi
0x180096bbd  mov     edx, ebx; lDestStride
0x180096bbf  imul    eax, r9d
0x180096bc3  add     rcx, r14; pDest
0x180096bc6  movsxd  r8, eax
0x180096bc9  add     r8, r13
0x180096bcc  add     r8, rdi
0x180096bcf  add     r8, r15; pSrc
0x180096bd2  call    cs:__imp_MFCopyImage
0x180096bd8  test    eax, eax
0x180096bda  jnz     short loc_180096C14
0x180096bdc  mov     r9d, [rsp+68h+lSrcStride]; lSrcStride
0x180096be1  lea     r8, [rdi+r13]
0x180096be5  mov     eax, r12d
0x180096be8  mov     [rsp+68h+dwLines], ebp; dwLines
0x180096bec  cdq
0x180096bed  mov     [rsp+68h+dwWidthInBytes], esi; dwWidthInBytes
0x180096bf1  mov     ecx, 2
0x180096bf6  add     r8, r15; pSrc
0x180096bf9  idiv    ecx
0x180096bfb  mov     edx, ebx; lDestStride
0x180096bfd  imul    eax, ebx
0x180096c00  movsxd  rcx, eax
0x180096c03  add     rcx, [rsp+68h+arg_0]
0x180096c08  add     rcx, rdi
0x180096c0b  add     rcx, r14; pDest
0x180096c0e  call    cs:__imp_MFCopyImage
0x180096c14  mov     rbx, [rsp+68h+arg_18]
0x180096c1c  xor     eax, eax
0x180096c1e  add     rsp, 30h
0x180096c22  pop     r15
0x180096c24  pop     r14
0x180096c26  pop     r13
0x180096c28  pop     r12
0x180096c2a  pop     rdi
0x180096c2b  pop     rsi
0x180096c2c  pop     rbp
0x180096c2d  retn
```
