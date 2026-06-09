# UnpackFrame0

- ea: `0x1800037cc`
- end: `0x180003a41`
- name: `UnpackFrame0`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f60`

## callees

- `0x1800037cc`

## pseudocode

```c
__int64 __fastcall UnpackFrame0(
        unsigned __int8 *a1,
        _WORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned __int8 v7; // r10
  unsigned __int8 v11; // r9
  unsigned __int8 v13; // r8
  unsigned int v14; // esi
  unsigned __int8 v15; // dl
  __int16 v16; // ax
  unsigned __int8 v17; // dl
  __int64 v18; // r11
  int v19; // r10d
  __int64 v20; // r9
  unsigned __int8 v21; // r8
  __int16 v22; // dx
  unsigned __int8 v23; // al
  unsigned __int8 v24; // r8
  unsigned __int8 v25; // r8
  unsigned __int8 v26; // al
  __int16 v27; // cx
  __int64 result; // rax

  v7 = *a1;
  v11 = a1[2];
  v13 = a1[3];
  v14 = 0;
  a2[1] = *a1 & 0x3F;
  v15 = a1[1] >> 4;
  a2[2] = (v7 >> 6) | (4 * (a1[1] & 0xF));
  v16 = v15;
  v17 = a1[4];
  a2[3] = v16 | (16 * (v11 & 1));
  a2[4] = (v11 >> 1) & 0x1F;
  a2[5] = (v11 >> 6) | (4 * (v13 & 3));
  a2[6] = (v13 >> 2) & 0xF;
  a2[8] = (v17 >> 1) & 7;
  a2[7] = (v13 >> 6) | (4 * (v17 & 1));
  v18 = 0;
  do
  {
    v19 = 7 * v14;
    v20 = 26 * v18;
    v21 = a1[7 * v14 + 5];
    v22 = (16 * (a1[v19 + 5] & 7)) | (a1[v19 + 4] >> 4);
    *(_WORD *)(a4 + 2 * v18) = (v21 >> 3) & 3;
    *(_WORD *)(a3 + 2 * v18) = v22;
    *(_WORD *)(a5 + 2 * v18) = (v21 >> 5) & 3;
    v23 = a1[7 * v14 + 6];
    *(_WORD *)(v20 + a7) = v23 >> 5;
    *(_WORD *)(a6 + 2 * v18) = (v21 >> 7) | (2 * (v23 & 0x1F));
    LOBYTE(v22) = a1[7 * v14 + 7];
    *(_WORD *)(v20 + a7 + 2) = v22 & 7;
    *(_WORD *)(v20 + a7 + 4) = ((unsigned __int8)v22 >> 3) & 7;
    v24 = a1[7 * v14 + 8];
    *(_WORD *)(v20 + a7 + 6) = ((unsigned __int8)v22 >> 6) | (4 * (v24 & 1));
    *(_WORD *)(v20 + a7 + 8) = (v24 >> 1) & 7;
    *(_WORD *)(v20 + a7 + 10) = (v24 >> 4) & 7;
    LOBYTE(v22) = a1[7 * v14 + 9];
    *(_WORD *)(v20 + a7 + 12) = (v24 >> 7) | (2 * (v22 & 3));
    ++v14;
    *(_WORD *)(v20 + a7 + 14) = ((unsigned __int8)v22 >> 2) & 7;
    ++v18;
    *(_WORD *)(v20 + a7 + 16) = (unsigned __int8)v22 >> 5;
    v25 = a1[v19 + 10];
    *(_WORD *)(v20 + a7 + 18) = v25 & 7;
    *(_WORD *)(v20 + a7 + 20) = (v25 >> 3) & 7;
    v26 = a1[v19 + 11];
    v27 = (v25 >> 6) | (4 * (v26 & 1));
    result = (v26 >> 1) & 7;
    *(_WORD *)(v20 + a7 + 24) = result;
    *(_WORD *)(v20 + a7 + 22) = v27;
  }
  while ( v14 < 4 );
  return result;
}

```

## disassembly

```asm
0x1800037cc  push    rbx
0x1800037ce  push    rbp
0x1800037cf  push    rsi
0x1800037d0  push    rdi
0x1800037d1  push    r12
0x1800037d3  push    r14
0x1800037d5  push    r15
0x1800037d7  mov     r10b, [rcx]
0x1800037da  mov     rbx, rcx
0x1800037dd  mov     rdi, [rsp+38h+arg_30]
0x1800037e2  mov     r11, rdx
0x1800037e5  mov     r12, [rsp+38h+arg_28]
0x1800037ea  mov     al, r10b
0x1800037ed  mov     rbp, [rsp+38h+arg_20]
0x1800037f2  and     al, 3Fh
0x1800037f4  movzx   eax, al
0x1800037f7  mov     r14, r9
0x1800037fa  mov     r9b, [rbx+2]
0x1800037fe  mov     r15, r8
0x180003801  mov     r8b, [rbx+3]
0x180003805  xor     esi, esi
0x180003807  mov     [rdx+2], ax
0x18000380b  mov     dl, [rcx+1]
0x18000380e  mov     al, dl
0x180003810  shr     r10b, 6
0x180003814  and     al, 0Fh
0x180003816  shr     dl, 4
0x180003819  movzx   ecx, al
0x18000381c  shl     cx, 2
0x180003820  movzx   eax, r10b
0x180003824  or      cx, ax
0x180003827  mov     al, r9b
0x18000382a  and     al, 1
0x18000382c  mov     [r11+4], cx
0x180003831  movzx   ecx, al
0x180003834  shl     cx, 4
0x180003838  movzx   eax, dl
0x18000383b  mov     dl, [rbx+4]
0x18000383e  or      cx, ax
0x180003841  mov     [r11+6], cx
0x180003846  mov     al, r9b
0x180003849  shr     al, 1
0x18000384b  and     al, 1Fh
0x18000384d  shr     r9b, 6
0x180003851  movzx   eax, al
0x180003854  mov     [r11+8], ax
0x180003859  mov     al, r8b
0x18000385c  and     al, 3
0x18000385e  movzx   ecx, al
0x180003861  shl     cx, 2
0x180003865  movzx   eax, r9b
0x180003869  or      cx, ax
0x18000386c  mov     al, r8b
0x18000386f  shr     al, 2
0x180003872  and     al, 0Fh
0x180003874  mov     [r11+0Ah], cx
0x180003879  movzx   eax, al
0x18000387c  mov     [r11+0Ch], ax
0x180003881  mov     al, dl
0x180003883  and     al, 1
0x180003885  shr     r8b, 6
0x180003889  movzx   ecx, al
0x18000388c  shr     dl, 1
0x18000388e  shl     cx, 2
0x180003892  and     dl, 7
0x180003895  movzx   eax, r8b
0x180003899  or      cx, ax
0x18000389c  movzx   eax, dl
0x18000389f  mov     [r11+10h], ax
0x1800038a4  mov     [r11+0Eh], cx
0x1800038a9  xor     r11d, r11d
0x1800038ac  imul    r10d, esi, 7
0x1800038b0  imul    r9, r11, 1Ah
0x1800038b4  lea     eax, [r10+5]
0x1800038b8  mov     r8b, [rax+rbx]
0x1800038bc  lea     eax, [r10+4]
0x1800038c0  mov     al, [rax+rbx]
0x1800038c3  shr     al, 4
0x1800038c6  movzx   edx, al
0x1800038c9  mov     al, r8b
0x1800038cc  and     al, 7
0x1800038ce  movzx   ecx, al
0x1800038d1  mov     al, r8b
0x1800038d4  shr     al, 3
0x1800038d7  and     al, 3
0x1800038d9  shl     cx, 4
0x1800038dd  movzx   eax, al
0x1800038e0  or      dx, cx
0x1800038e3  mov     [r14+r11*2], ax
0x1800038e8  mov     al, r8b
0x1800038eb  shr     al, 5
0x1800038ee  and     al, 3
0x1800038f0  mov     [r15+r11*2], dx
0x1800038f5  movzx   eax, al
0x1800038f8  mov     [rbp+r11*2+0], ax
0x1800038fe  lea     eax, [r10+6]
0x180003902  shr     r8b, 7
0x180003906  mov     dl, [rax+rbx]
0x180003909  mov     al, dl
0x18000390b  shr     dl, 5
0x18000390e  and     al, 1Fh
0x180003910  movzx   ecx, al
0x180003913  add     cx, cx
0x180003916  movzx   eax, r8b
0x18000391a  or      cx, ax
0x18000391d  movzx   eax, dl
0x180003920  mov     [r9+rdi], ax
0x180003925  lea     eax, [r10+7]
0x180003929  mov     [r12+r11*2], cx
0x18000392e  mov     dl, [rax+rbx]
0x180003931  mov     al, dl
0x180003933  and     al, 7
0x180003935  movzx   eax, al
0x180003938  mov     [r9+rdi+2], ax
0x18000393e  mov     al, dl
0x180003940  shr     al, 3
0x180003943  and     al, 7
0x180003945  shr     dl, 6
0x180003948  movzx   eax, al
0x18000394b  mov     [r9+rdi+4], ax
0x180003951  lea     eax, [r10+8]
0x180003955  mov     r8b, [rax+rbx]
0x180003959  mov     al, r8b
0x18000395c  and     al, 1
0x18000395e  movzx   ecx, al
0x180003961  shl     cx, 2
0x180003965  movzx   eax, dl
0x180003968  or      cx, ax
0x18000396b  mov     al, r8b
0x18000396e  shr     al, 1
0x180003970  and     al, 7
0x180003972  mov     [r9+rdi+6], cx
0x180003978  movzx   eax, al
0x18000397b  mov     [r9+rdi+8], ax
0x180003981  mov     al, r8b
0x180003984  shr     al, 4
0x180003987  and     al, 7
0x180003989  shr     r8b, 7
0x18000398d  movzx   eax, al
0x180003990  mov     [r9+rdi+0Ah], ax
0x180003996  lea     eax, [r10+9]
0x18000399a  mov     dl, [rax+rbx]
0x18000399d  mov     al, dl
0x18000399f  and     al, 3
0x1800039a1  movzx   ecx, al
0x1800039a4  add     cx, cx
0x1800039a7  movzx   eax, r8b
0x1800039ab  or      cx, ax
0x1800039ae  mov     al, dl
0x1800039b0  shr     al, 2
0x1800039b3  and     al, 7
0x1800039b5  mov     [r9+rdi+0Ch], cx
0x1800039bb  movzx   eax, al
0x1800039be  inc     esi
0x1800039c0  mov     [r9+rdi+0Eh], ax
0x1800039c6  inc     r11
0x1800039c9  shr     dl, 5
0x1800039cc  movzx   eax, dl
0x1800039cf  mov     [r9+rdi+10h], ax
0x1800039d5  lea     eax, [r10+0Ah]
0x1800039d9  mov     r8b, [rax+rbx]
0x1800039dd  mov     al, r8b
0x1800039e0  and     al, 7
0x1800039e2  movzx   eax, al
0x1800039e5  mov     [r9+rdi+12h], ax
0x1800039eb  mov     al, r8b
0x1800039ee  shr     al, 3
0x1800039f1  and     al, 7
0x1800039f3  shr     r8b, 6
0x1800039f7  movzx   eax, al
0x1800039fa  mov     [r9+rdi+14h], ax
0x180003a00  lea     eax, [r10+0Bh]
0x180003a04  mov     dl, [rax+rbx]
0x180003a07  mov     al, dl
0x180003a09  shr     dl, 1
0x180003a0b  and     al, 1
0x180003a0d  and     dl, 7
0x180003a10  movzx   ecx, al
0x180003a13  shl     cx, 2
0x180003a17  movzx   eax, r8b
0x180003a1b  or      cx, ax
0x180003a1e  movzx   eax, dl
0x180003a21  mov     [r9+rdi+18h], ax
0x180003a27  mov     [r9+rdi+16h], cx
0x180003a2d  cmp     esi, 4
0x180003a30  jb      loc_1800038AC
0x180003a36  pop     r15
0x180003a38  pop     r14
0x180003a3a  pop     r12
0x180003a3c  pop     rdi
0x180003a3d  pop     rsi
0x180003a3e  pop     rbp
0x180003a3f  pop     rbx
0x180003a40  retn
```
