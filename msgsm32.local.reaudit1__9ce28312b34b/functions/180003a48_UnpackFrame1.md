# UnpackFrame1

- ea: `0x180003a48`
- end: `0x180003cbd`
- name: `UnpackFrame1`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f60`

## callees

- `0x180003a48`

## pseudocode

```c
__int64 __fastcall UnpackFrame1(_BYTE *a1, _WORD *a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  unsigned __int8 v10; // al
  unsigned int v12; // ebp
  __int16 v13; // r8
  unsigned __int8 v14; // al
  unsigned __int8 v15; // dl
  __int64 v16; // rsi
  __int64 v17; // r10
  int v18; // r11d
  unsigned __int8 v19; // al
  unsigned __int8 v20; // r8
  unsigned __int8 v21; // r9
  __int16 v22; // cx
  unsigned __int8 v23; // dl
  unsigned __int8 v24; // dl
  unsigned __int8 v25; // r8
  __int16 v26; // cx
  unsigned __int8 v27; // dl
  __int64 result; // rax

  v10 = a1[33];
  v12 = 0;
  v13 = (a1[32] >> 4) | (16 * (v10 & 3));
  a2[2] = v10 >> 2;
  a2[1] = v13;
  LOBYTE(v13) = a1[35];
  v14 = a1[34];
  a2[3] = v14 & 0x1F;
  v15 = a1[36];
  a2[4] = (v14 >> 5) | (8 * (v13 & 3));
  a2[5] = ((unsigned __int8)v13 >> 2) & 0xF;
  v16 = 0;
  a2[7] = (v15 >> 2) & 7;
  a2[8] = v15 >> 5;
  a2[6] = ((unsigned __int8)v13 >> 6) | (4 * (v15 & 3));
  do
  {
    v17 = 26 * v16;
    v18 = 7 * v12;
    v19 = a1[7 * v12 + 37];
    *(_WORD *)(a3 + 2 * v16) = v19 & 0x7F;
    v20 = a1[7 * v12 + 38];
    *(_WORD *)(a4 + 2 * v16) = (v19 >> 7) | (2 * (v20 & 1));
    *(_WORD *)(a5 + 2 * v16) = (v20 >> 1) & 3;
    v21 = a1[7 * v12 + 39];
    *(_WORD *)(a6 + 2 * v16) = (v20 >> 3) | (32 * (v21 & 1));
    *(_WORD *)(v17 + a7) = (v21 >> 1) & 7;
    *(_WORD *)(v17 + a7 + 2) = (v21 >> 4) & 7;
    v22 = (v21 >> 7) | (2 * (a1[7 * v12 + 40] & 3));
    v23 = a1[7 * v12 + 40] >> 5;
    *(_WORD *)(v17 + a7 + 6) = (a1[7 * v12 + 40] >> 2) & 7;
    *(_WORD *)(v17 + a7 + 8) = v23;
    *(_WORD *)(v17 + a7 + 4) = v22;
    v24 = a1[7 * v12 + 41];
    *(_WORD *)(v17 + a7 + 10) = v24 & 7;
    *(_WORD *)(v17 + a7 + 12) = (v24 >> 3) & 7;
    v25 = a1[7 * v12++ + 42];
    *(_WORD *)(v17 + a7 + 14) = (v24 >> 6) | (4 * (v25 & 1));
    ++v16;
    *(_WORD *)(v17 + a7 + 16) = (v25 >> 1) & 7;
    *(_WORD *)(v17 + a7 + 18) = (v25 >> 4) & 7;
    v26 = (v25 >> 7) | (2 * (a1[v18 + 43] & 3));
    v27 = a1[v18 + 43] >> 5;
    *(_WORD *)(v17 + a7 + 22) = (a1[v18 + 43] >> 2) & 7;
    result = v27;
    *(_WORD *)(v17 + a7 + 24) = v27;
    *(_WORD *)(v17 + a7 + 20) = v26;
  }
  while ( v12 < 4 );
  return result;
}

```

## disassembly

```asm
0x180003a48  push    rbx
0x180003a4a  push    rbp
0x180003a4b  push    rsi
0x180003a4c  push    rdi
0x180003a4d  push    r12
0x180003a4f  push    r13
0x180003a51  push    r14
0x180003a53  push    r15
0x180003a55  mov     r10b, [rcx+21h]
0x180003a59  mov     rbx, rcx
0x180003a5c  mov     rdi, [rsp+40h+arg_30]
0x180003a61  mov     r11, rdx
0x180003a64  mov     r12, [rsp+40h+arg_28]
0x180003a69  mov     r15, r8
0x180003a6c  mov     r13, [rsp+40h+arg_20]
0x180003a71  mov     al, r10b
0x180003a74  shr     r10b, 2
0x180003a78  mov     r14, r9
0x180003a7b  mov     r9b, 3
0x180003a7e  xor     ebp, ebp
0x180003a80  and     al, r9b
0x180003a83  movzx   r8d, al
0x180003a87  mov     al, [rcx+20h]
0x180003a8a  shr     al, 4
0x180003a8d  movzx   ecx, al
0x180003a90  shl     r8w, 4
0x180003a95  or      r8w, cx
0x180003a99  movzx   eax, r10b
0x180003a9d  mov     [rdx+4], ax
0x180003aa1  mov     [rdx+2], r8w
0x180003aa6  mov     r8b, [rbx+23h]
0x180003aaa  mov     dl, [rbx+22h]
0x180003aad  mov     al, dl
0x180003aaf  shr     dl, 5
0x180003ab2  and     al, 1Fh
0x180003ab4  movzx   eax, al
0x180003ab7  mov     [r11+6], ax
0x180003abc  mov     al, r8b
0x180003abf  and     al, r9b
0x180003ac2  movzx   ecx, al
0x180003ac5  shl     cx, 3
0x180003ac9  movzx   eax, dl
0x180003acc  mov     dl, [rbx+24h]
0x180003acf  or      cx, ax
0x180003ad2  mov     al, r8b
0x180003ad5  mov     [r11+8], cx
0x180003ada  shr     al, 2
0x180003add  and     al, 0Fh
0x180003adf  shr     r8b, 6
0x180003ae3  movzx   eax, al
0x180003ae6  mov     [r11+0Ah], ax
0x180003aeb  mov     al, dl
0x180003aed  and     al, r9b
0x180003af0  movzx   ecx, al
0x180003af3  movzx   eax, r8b
0x180003af7  shl     cx, 2
0x180003afb  or      cx, ax
0x180003afe  mov     al, dl
0x180003b00  shr     al, 2
0x180003b03  and     al, 7
0x180003b05  shr     dl, 5
0x180003b08  movzx   eax, al
0x180003b0b  xor     esi, esi
0x180003b0d  mov     [r11+0Eh], ax
0x180003b12  movzx   eax, dl
0x180003b15  mov     [r11+10h], ax
0x180003b1a  mov     [r11+0Ch], cx
0x180003b1f  imul    r10, rsi, 1Ah
0x180003b23  imul    r11d, ebp, 7
0x180003b27  lea     eax, [r11+25h]
0x180003b2b  mov     dl, [rax+rbx]
0x180003b2e  mov     al, dl
0x180003b30  shr     dl, 7
0x180003b33  and     al, 7Fh
0x180003b35  movzx   eax, al
0x180003b38  mov     [r15+rsi*2], ax
0x180003b3d  lea     eax, [r11+26h]
0x180003b41  mov     r8b, [rax+rbx]
0x180003b45  mov     al, r8b
0x180003b48  and     al, 1
0x180003b4a  movzx   ecx, al
0x180003b4d  add     cx, cx
0x180003b50  movzx   eax, dl
0x180003b53  or      cx, ax
0x180003b56  mov     al, r8b
0x180003b59  shr     al, 1
0x180003b5b  and     al, r9b
0x180003b5e  mov     [r14+rsi*2], cx
0x180003b63  movzx   eax, al
0x180003b66  mov     [r13+rsi*2+0], ax
0x180003b6c  lea     eax, [r11+27h]
0x180003b70  shr     r8b, 3
0x180003b74  mov     r9b, [rax+rbx]
0x180003b78  mov     al, r9b
0x180003b7b  and     al, 1
0x180003b7d  movzx   ecx, al
0x180003b80  shl     cx, 5
0x180003b84  movzx   eax, r8b
0x180003b88  mov     r8b, 7
0x180003b8b  or      cx, ax
0x180003b8e  mov     al, r9b
0x180003b91  shr     al, 1
0x180003b93  and     al, r8b
0x180003b96  mov     [r12+rsi*2], cx
0x180003b9b  movzx   eax, al
0x180003b9e  mov     [r10+rdi], ax
0x180003ba3  mov     al, r9b
0x180003ba6  shr     al, 4
0x180003ba9  and     al, r8b
0x180003bac  shr     r9b, 7
0x180003bb0  movzx   eax, al
0x180003bb3  mov     [r10+rdi+2], ax
0x180003bb9  lea     eax, [r11+28h]
0x180003bbd  mov     dl, [rax+rbx]
0x180003bc0  mov     al, dl
0x180003bc2  and     al, 3
0x180003bc4  movzx   ecx, al
0x180003bc7  add     cx, cx
0x180003bca  movzx   eax, r9b
0x180003bce  or      cx, ax
0x180003bd1  mov     al, dl
0x180003bd3  shr     al, 2
0x180003bd6  and     al, r8b
0x180003bd9  shr     dl, 5
0x180003bdc  movzx   eax, al
0x180003bdf  mov     [r10+rdi+6], ax
0x180003be5  movzx   eax, dl
0x180003be8  mov     [r10+rdi+8], ax
0x180003bee  lea     eax, [r11+29h]
0x180003bf2  mov     [r10+rdi+4], cx
0x180003bf8  mov     dl, [rax+rbx]
0x180003bfb  mov     al, dl
0x180003bfd  and     al, r8b
0x180003c00  movzx   eax, al
0x180003c03  mov     [r10+rdi+0Ah], ax
0x180003c09  mov     al, dl
0x180003c0b  shr     al, 3
0x180003c0e  and     al, r8b
0x180003c11  movzx   eax, al
0x180003c14  mov     [r10+rdi+0Ch], ax
0x180003c1a  lea     eax, [rbp+6]
0x180003c1d  imul    ecx, eax, 7
0x180003c20  mov     r8b, [rcx+rbx]
0x180003c24  mov     al, r8b
0x180003c27  and     al, 1
0x180003c29  movzx   ecx, al
0x180003c2c  shl     cx, 2
0x180003c30  shr     dl, 6
0x180003c33  movzx   eax, dl
0x180003c36  mov     r9b, 3
0x180003c39  or      cx, ax
0x180003c3c  inc     ebp
0x180003c3e  mov     al, r8b
0x180003c41  mov     [r10+rdi+0Eh], cx
0x180003c47  shr     al, 1
0x180003c49  inc     rsi
0x180003c4c  and     al, 7
0x180003c4e  movzx   eax, al
0x180003c51  mov     [r10+rdi+10h], ax
0x180003c57  mov     al, r8b
0x180003c5a  shr     al, 4
0x180003c5d  and     al, 7
0x180003c5f  shr     r8b, 7
0x180003c63  movzx   eax, al
0x180003c66  mov     [r10+rdi+12h], ax
0x180003c6c  lea     eax, [r11+2Bh]
0x180003c70  mov     dl, [rax+rbx]
0x180003c73  mov     al, dl
0x180003c75  and     al, r9b
0x180003c78  movzx   ecx, al
0x180003c7b  movzx   eax, r8b
0x180003c7f  add     cx, cx
0x180003c82  or      cx, ax
0x180003c85  mov     al, dl
0x180003c87  shr     al, 2
0x180003c8a  and     al, 7
0x180003c8c  shr     dl, 5
0x180003c8f  movzx   eax, al
0x180003c92  mov     [r10+rdi+16h], ax
0x180003c98  movzx   eax, dl
0x180003c9b  mov     [r10+rdi+18h], ax
0x180003ca1  mov     [r10+rdi+14h], cx
0x180003ca7  cmp     ebp, 4
0x180003caa  jb      loc_180003B1F
0x180003cb0  pop     r15
0x180003cb2  pop     r14
0x180003cb4  pop     r13
0x180003cb6  pop     r12
0x180003cb8  pop     rdi
0x180003cb9  pop     rsi
0x180003cba  pop     rbp
0x180003cbb  pop     rbx
0x180003cbc  retn
```
