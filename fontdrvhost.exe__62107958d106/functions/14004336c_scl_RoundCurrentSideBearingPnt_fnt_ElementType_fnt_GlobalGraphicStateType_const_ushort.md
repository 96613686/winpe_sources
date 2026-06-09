# scl_RoundCurrentSideBearingPnt(fnt_ElementType *,fnt_GlobalGraphicStateType const *,ushort)

- ea: `0x14004336c`
- end: `0x14004350a`
- name: `?scl_RoundCurrentSideBearingPnt@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@G@Z`
- size: `414`
- prototype: `void __fastcall(struct fnt_ElementType *, const struct fnt_GlobalGraphicStateType *, unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140042d40`

## callees

- `0x14004336c`

## pseudocode

```c
void __fastcall scl_RoundCurrentSideBearingPnt(
        struct fnt_ElementType *a1,
        const struct fnt_GlobalGraphicStateType *a2,
        __int16 a3)
{
  __int64 v4; // rdi
  unsigned int v6; // ebp
  __int16 v7; // r10
  __int64 v8; // r9
  __int64 v9; // r14
  unsigned __int64 v10; // r8
  __int64 v11; // r10
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // ecx
  unsigned int v17; // ecx
  __int16 v18; // dx
  __int64 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r10
  __int16 v25; // r9

  v4 = a3;
  v6 = (unsigned int)a3 >> 31;
  v7 = *(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * *((__int16 *)a1 + 40) - 2);
  v8 = (unsigned __int16)(v7 + 2);
  v9 = (unsigned __int16)(v7 + 1);
  v10 = *((int *)a2 + 97)
      * (__int64)(__int16)(*(_WORD *)(*((_QWORD *)a1 + 4) + 4 * v8) - *(_WORD *)(*((_QWORD *)a1 + 4) + 4 * v9));
  v11 = (int)v4 / 2;
  v12 = v10 >> 63;
  v13 = v10 + v11;
  v14 = v10 - v11;
  if ( v6 == (_DWORD)v12 )
    v14 = v13;
  if ( (_WORD)v4 )
    v15 = v14 / v4;
  else
    LODWORD(v15) = (v14 < 0) + 0x7FFFFFFF;
  v16 = ((int)v15 + 512) >> 10;
  if ( (*((_BYTE *)a2 + 448) & 5) == 1 )
    v17 = (v16 + 2) & 0xFFFFFFFC;
  else
    v17 = (v16 + 32) & 0xFFFFFFC0;
  *(_DWORD *)(*(_QWORD *)a1 + 4 * v8) = *(_DWORD *)(*(_QWORD *)a1 + 4 * v9) + v17;
  v18 = *(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * *((__int16 *)a1 + 40) - 2);
  v19 = (unsigned __int16)(v18 + 3);
  v20 = *((int *)a2 + 98)
      * (__int64)(__int16)(*(_WORD *)(*((_QWORD *)a1 + 5) + 4LL * (unsigned __int16)(v18 + 4))
                         - *(_WORD *)(*((_QWORD *)a1 + 5) + 4 * v19));
  v21 = v20 >> 63;
  v22 = v20 + v11;
  v23 = v20 - v11;
  if ( v6 == (_DWORD)v21 )
    v23 = v22;
  if ( (_WORD)v4 )
    v24 = v23 / v4;
  else
    LODWORD(v24) = (v23 < 0) + 0x7FFFFFFF;
  *(_DWORD *)(*((_QWORD *)a1 + 1) + 4 * v19) = (*(_DWORD *)(*((_QWORD *)a1 + 1) + 4 * v19) + 32) & 0xFFFFFFC0;
  v25 = *(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * *((__int16 *)a1 + 40) - 2);
  *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL * (unsigned __int16)(v25 + 4)) = (*(_DWORD *)(*((_QWORD *)a1 + 1)
                                                                                    + 4LL * (unsigned __int16)(v25 + 3))
                                                                        + 32
                                                                        + (((int)v24 + 512) >> 10))
                                                                       & 0xFFFFFFC0;
}

```

## disassembly

```asm
0x14004336c  push    rbx
0x14004336e  push    rbp
0x14004336f  push    rsi
0x140043370  push    rdi
0x140043371  push    r14
0x140043373  push    r15
0x140043375  mov     rax, [rcx+40h]
0x140043379  mov     rbx, rcx
0x14004337c  movsx   r9, word ptr [rcx+50h]
0x140043381  mov     r15d, 2
0x140043387  movsx   rdi, r8w
0x14004338b  mov     rsi, rdx
0x14004338e  mov     r8, [rcx+20h]
0x140043392  mov     ebp, edi
0x140043394  shr     ebp, 1Fh
0x140043397  movzx   r10d, word ptr [rax+r9*2-2]
0x14004339d  lea     eax, [r15+r10]
0x1400433a1  inc     r10w
0x1400433a5  movzx   r9d, ax
0x1400433a9  mov     eax, edi
0x1400433ab  movzx   r14d, r10w
0x1400433af  movzx   ecx, word ptr [r8+r9*4]
0x1400433b4  sub     cx, [r8+r14*4]
0x1400433b9  movsx   r8, cx
0x1400433bd  movsxd  rcx, dword ptr [rdx+184h]
0x1400433c4  cdq
0x1400433c5  imul    r8, rcx
0x1400433c9  idiv    r15d
0x1400433cc  mov     rcx, r8
0x1400433cf  mov     r15d, 7FFFFFFFh
0x1400433d5  movsxd  r10, eax
0x1400433d8  shr     rcx, 3Fh
0x1400433dc  lea     rax, [r8+r10]
0x1400433e0  sub     r8, r10
0x1400433e3  cmp     ebp, ecx
0x1400433e5  cmovz   r8, rax
0x1400433e9  xor     r11d, r11d
0x1400433ec  test    di, di
0x1400433ef  jz      loc_1400434E7
0x1400433f5  mov     rax, r8
0x1400433f8  cqo
0x1400433fa  idiv    rdi
0x1400433fd  lea     ecx, [rax+200h]
0x140043403  mov     al, [rsi+1C0h]
0x140043409  and     al, 5
0x14004340b  sar     ecx, 0Ah
0x14004340e  cmp     al, 1
0x140043410  jz      loc_1400434DC
0x140043416  add     ecx, 20h ; ' '
0x140043419  and     ecx, 0FFFFFFC0h
0x14004341c  mov     rdx, [rbx]
0x14004341f  add     ecx, [rdx+r14*4]
0x140043423  mov     [rdx+r9*4], ecx
0x140043427  movsx   rcx, word ptr [rbx+50h]
0x14004342c  mov     rax, [rbx+40h]
0x140043430  mov     r8, [rbx+28h]
0x140043434  movzx   edx, word ptr [rax+rcx*2-2]
0x140043439  lea     eax, [rdx+3]
0x14004343c  add     dx, 4
0x140043440  movzx   r9d, ax
0x140043444  movzx   eax, dx
0x140043447  movzx   ecx, word ptr [r8+rax*4]
0x14004344c  sub     cx, [r8+r9*4]
0x140043451  movsxd  rax, dword ptr [rsi+188h]
0x140043458  movsx   rdx, cx
0x14004345c  imul    rdx, rax
0x140043460  mov     rcx, rdx
0x140043463  shr     rcx, 3Fh
0x140043467  lea     rax, [rdx+r10]
0x14004346b  sub     rdx, r10
0x14004346e  cmp     ebp, ecx
0x140043470  cmovz   rdx, rax
0x140043474  test    di, di
0x140043477  jz      short loc_1400434F8
0x140043479  mov     rax, rdx
0x14004347c  cqo
0x14004347e  idiv    rdi
0x140043481  mov     r10, rax
0x140043484  mov     rdx, [rbx+8]
0x140043488  mov     ecx, [rdx+r9*4]
0x14004348c  add     ecx, 20h ; ' '
0x14004348f  and     ecx, 0FFFFFFC0h
0x140043492  mov     [rdx+r9*4], ecx
0x140043496  movsx   rdx, word ptr [rbx+50h]
0x14004349b  mov     rcx, [rbx+40h]
0x14004349f  mov     r8, [rbx+8]
0x1400434a3  movzx   r9d, word ptr [rcx+rdx*2-2]
0x1400434a9  lea     edx, [r10+200h]
0x1400434b0  sar     edx, 0Ah
0x1400434b3  lea     eax, [r9+3]
0x1400434b7  movzx   eax, ax
0x1400434ba  mov     eax, [r8+rax*4]
0x1400434be  add     eax, 20h ; ' '
0x1400434c1  add     edx, eax
0x1400434c3  and     edx, 0FFFFFFC0h
0x1400434c6  add     r9w, 4
0x1400434cb  movzx   eax, r9w
0x1400434cf  mov     [r8+rax*4], edx
0x1400434d3  pop     r15
0x1400434d5  pop     r14
0x1400434d7  pop     rdi
0x1400434d8  pop     rsi
0x1400434d9  pop     rbp
0x1400434da  pop     rbx
0x1400434db  retn
0x1400434dc  add     ecx, 2
0x1400434df  and     ecx, 0FFFFFFFCh
0x1400434e2  jmp     loc_14004341C
0x1400434e7  test    r8, r8
0x1400434ea  mov     rax, r11
0x1400434ed  sets    al
0x1400434f0  add     rax, r15
0x1400434f3  jmp     loc_1400433FD
0x1400434f8  test    rdx, rdx
0x1400434fb  mov     r10, r11
0x1400434fe  sets    r10b
0x140043502  add     r10, r15
0x140043505  jmp     loc_140043484
```
