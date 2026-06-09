# PackFrame1

- ea: `0x1800035f4`
- end: `0x1800037c5`
- name: `PackFrame1`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005350`

## callees

- `0x1800035f4`

## pseudocode

```c
char __fastcall PackFrame1(_BYTE *a1, _BYTE *a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  char v9; // dl
  int v10; // edi
  char v12; // al
  char v13; // cl
  char v14; // al
  char v15; // cl
  char v16; // al
  char v17; // cl
  char v18; // al
  __int64 v19; // r10
  int v20; // esi
  __int64 v21; // r9
  char v22; // al
  char v23; // dl
  char v24; // cl
  char v25; // al
  char v26; // cl
  char v27; // al
  char v28; // cl
  char v29; // al
  char v30; // dl
  char v31; // cl
  char result; // al
  char v33; // cl

  v9 = a2[2];
  v10 = 0;
  a1[32] |= 16 * v9;
  v12 = a2[8];
  a1[33] = (4 * a2[4]) | (v9 >> 4) & 3;
  v13 = (32 * v12) | a2[6] & 0x1F;
  v14 = a2[12];
  a1[34] = v13;
  v15 = ((char)a2[8] >> 3) & 3 | (4 * ((16 * v14) | a2[10] & 0xF));
  v16 = a2[16];
  a1[35] = v15;
  v17 = (8 * v16) | a2[14] & 7;
  v18 = (char)a2[12] >> 2;
  v19 = 0;
  a1[36] = v18 & 3 | (4 * v17);
  v20 = 0;
  do
  {
    v21 = v20;
    v22 = 4 * *(_BYTE *)(a6 + 2 * v19);
    a1[v20 + 37] = (*(_BYTE *)(a4 + 2 * v19) << 7) | *(_BYTE *)(a3 + 2 * v19) & 0x7F;
    v23 = *(_BYTE *)(26 * v19 + a7 + 18) & 7;
    v24 = (*(char *)(a4 + 2 * v19) >> 1) & 1 | (2 * (v22 | *(_BYTE *)(a5 + 2 * v19) & 3));
    v25 = 8 * *(_BYTE *)(26 * v19 + a7 + 4);
    a1[v20 + 38] = v24;
    v26 = (*(char *)(a6 + 2 * v19) >> 5) & 1
        | (2 * (*(_BYTE *)(26 * v19 + a7) & 7 | (8 * (v25 | *(_BYTE *)(26 * v19 + a7 + 2) & 7))));
    v27 = 8 * *(_BYTE *)(26 * v19 + a7 + 8);
    a1[v20 + 39] = v26;
    v28 = (*(char *)(26 * v19 + a7 + 4) >> 1) & 3 | (4 * (v27 | *(_BYTE *)(26 * v19 + a7 + 6) & 7));
    v29 = 8 * *(_BYTE *)(26 * v19 + a7 + 14);
    a1[v20 + 40] = v28;
    v30 = (8 * *(_BYTE *)(26 * v19 + a7 + 20)) | v23;
    a1[v20 + 41] = *(_BYTE *)(26 * v19 + a7 + 10) & 7 | (8 * (v29 | *(_BYTE *)(26 * v19 + a7 + 12) & 7));
    v31 = *(_BYTE *)(26 * v19 + a7 + 22) & 7;
    a1[7 * v10 + 42] = (*(char *)(26 * v19 + a7 + 14) >> 2) & 1 | (2 * (*(_BYTE *)(26 * v19 + a7 + 16) & 7 | (8 * v30)));
    result = (*(char *)(26 * v19 + a7 + 20) >> 1) & 3;
    ++v10;
    v33 = result | (4 * ((8 * *(_BYTE *)(26 * v19++ + a7 + 24)) | v31));
    v20 += 7;
    a1[v21 + 43] = v33;
  }
  while ( v10 < 4 );
  return result;
}

```

## disassembly

```asm
0x1800035f4  push    rbx
0x1800035f6  push    rbp
0x1800035f7  push    rsi
0x1800035f8  push    rdi
0x1800035f9  push    r12
0x1800035fb  push    r14
0x1800035fd  push    r15
0x1800035ff  mov     al, [rdx+2]
0x180003602  mov     r11, rcx
0x180003605  mov     r15, [rsp+38h+arg_28]
0x18000360a  mov     r10, rdx
0x18000360d  mov     dl, [rdx+2]
0x180003610  xor     edi, edi
0x180003612  mov     rbp, [rsp+38h+arg_20]
0x180003617  mov     r14, r9
0x18000361a  mov     rbx, [rsp+38h+arg_30]
0x18000361f  mov     r12, r8
0x180003622  shl     al, 4
0x180003625  or      [rcx+20h], al
0x180003628  mov     al, [r10+4]
0x18000362c  shl     al, 2
0x18000362f  sar     dl, 4
0x180003632  and     dl, 3
0x180003635  or      dl, al
0x180003637  mov     al, [r10+8]
0x18000363b  mov     [rcx+21h], dl
0x18000363e  mov     cl, [r10+6]
0x180003642  and     cl, 1Fh
0x180003645  shl     al, 5
0x180003648  or      cl, al
0x18000364a  mov     al, [r10+0Ch]
0x18000364e  mov     [r11+22h], cl
0x180003652  mov     cl, [r10+0Ah]
0x180003656  shl     al, 4
0x180003659  and     cl, 0Fh
0x18000365c  or      cl, al
0x18000365e  mov     al, [r10+8]
0x180003662  sar     al, 3
0x180003665  and     al, 3
0x180003667  shl     cl, 2
0x18000366a  or      cl, al
0x18000366c  mov     al, [r10+10h]
0x180003670  mov     [r11+23h], cl
0x180003674  mov     cl, [r10+0Eh]
0x180003678  shl     al, 3
0x18000367b  and     cl, 7
0x18000367e  or      cl, al
0x180003680  mov     al, [r10+0Ch]
0x180003684  sar     al, 2
0x180003687  xor     r10d, r10d
0x18000368a  and     al, 3
0x18000368c  shl     cl, 2
0x18000368f  or      cl, al
0x180003691  mov     [r11+24h], cl
0x180003695  xor     esi, esi
0x180003697  mov     al, [r14+r10*2]
0x18000369b  shl     al, 7
0x18000369e  mov     cl, [r12+r10*2]
0x1800036a2  and     cl, 7Fh
0x1800036a5  movsxd  r9, esi
0x1800036a8  or      cl, al
0x1800036aa  mov     al, [r15+r10*2]
0x1800036ae  shl     al, 2
0x1800036b1  imul    r8, r10, 1Ah
0x1800036b5  mov     [r9+r11+25h], cl
0x1800036ba  mov     cl, [rbp+r10*2+0]
0x1800036bf  and     cl, 3
0x1800036c2  or      cl, al
0x1800036c4  mov     al, [r14+r10*2]
0x1800036c8  mov     dl, [r8+rbx+12h]
0x1800036cd  add     cl, cl
0x1800036cf  sar     al, 1
0x1800036d1  and     dl, 7
0x1800036d4  and     al, 1
0x1800036d6  or      cl, al
0x1800036d8  mov     al, [r8+rbx+4]
0x1800036dd  shl     al, 3
0x1800036e0  mov     [r9+r11+26h], cl
0x1800036e5  mov     cl, [r8+rbx+2]
0x1800036ea  and     cl, 7
0x1800036ed  or      cl, al
0x1800036ef  mov     al, [r8+rbx]
0x1800036f3  and     al, 7
0x1800036f5  shl     cl, 3
0x1800036f8  or      cl, al
0x1800036fa  mov     al, [r15+r10*2]
0x1800036fe  sar     al, 5
0x180003701  add     cl, cl
0x180003703  and     al, 1
0x180003705  or      cl, al
0x180003707  mov     al, [r8+rbx+8]
0x18000370c  shl     al, 3
0x18000370f  mov     [r9+r11+27h], cl
0x180003714  mov     cl, [r8+rbx+6]
0x180003719  and     cl, 7
0x18000371c  or      cl, al
0x18000371e  mov     al, [r8+rbx+4]
0x180003723  sar     al, 1
0x180003725  and     al, 3
0x180003727  shl     cl, 2
0x18000372a  or      cl, al
0x18000372c  mov     al, [r8+rbx+0Eh]
0x180003731  shl     al, 3
0x180003734  mov     [r9+r11+28h], cl
0x180003739  mov     cl, [r8+rbx+0Ch]
0x18000373e  and     cl, 7
0x180003741  or      cl, al
0x180003743  mov     al, [r8+rbx+0Ah]
0x180003748  and     al, 7
0x18000374a  shl     cl, 3
0x18000374d  or      cl, al
0x18000374f  mov     al, [r8+rbx+14h]
0x180003754  shl     al, 3
0x180003757  or      dl, al
0x180003759  mov     [r9+r11+29h], cl
0x18000375e  mov     al, [r8+rbx+10h]
0x180003763  mov     cl, [r8+rbx+16h]
0x180003768  and     al, 7
0x18000376a  shl     dl, 3
0x18000376d  and     cl, 7
0x180003770  or      dl, al
0x180003772  mov     al, [r8+rbx+0Eh]
0x180003777  sar     al, 2
0x18000377a  add     dl, dl
0x18000377c  and     al, 1
0x18000377e  or      dl, al
0x180003780  lea     eax, [rdi+6]
0x180003783  imul    eax, 7
0x180003786  cdqe
0x180003788  mov     [rax+r11], dl
0x18000378c  mov     al, [r8+rbx+18h]
0x180003791  shl     al, 3
0x180003794  or      cl, al
0x180003796  mov     al, [r8+rbx+14h]
0x18000379b  shl     cl, 2
0x18000379e  sar     al, 1
0x1800037a0  and     al, 3
0x1800037a2  inc     edi
0x1800037a4  or      cl, al
0x1800037a6  inc     r10
0x1800037a9  add     esi, 7
0x1800037ac  mov     [r9+r11+2Bh], cl
0x1800037b1  cmp     edi, 4
0x1800037b4  jl      loc_180003697
0x1800037ba  pop     r15
0x1800037bc  pop     r14
0x1800037be  pop     r12
0x1800037c0  pop     rdi
0x1800037c1  pop     rsi
0x1800037c2  pop     rbp
0x1800037c3  pop     rbx
0x1800037c4  retn
```
