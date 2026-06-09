# MVarTable::GetTagCachedDelta(sfnt_mvar_tag)

- ea: `0x140050290`
- end: `0x14005046d`
- name: `?GetTagCachedDelta@MVarTable@@QEBAFW4sfnt_mvar_tag@@@Z`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001b68`
- `0x140002a68`

## callees

- `0x140050290`

## pseudocode

```c
__int64 __fastcall MVarTable::GetTagCachedDelta(unsigned __int16 *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // edx

  if ( a2 <= 1935833199 )
  {
    if ( a2 == 1935833199 )
      return a1[25];
    if ( a2 > 1735618616 )
    {
      v11 = a2 - 1735618617;
      if ( !v11 )
        return a1[44];
      v12 = v11 - 15598378;
      if ( !v12 )
        return a1[7];
      v13 = v12 - 129278;
      if ( !v13 )
        return a1[10];
      v14 = v13 - 3;
      if ( !v14 )
        return a1[11];
      v15 = v14 - 770;
      if ( !v15 )
        return a1[17];
      v16 = v15 - 776;
      if ( !v16 )
        return a1[16];
      v17 = v16 - 5;
      if ( !v17 )
        return a1[15];
      v18 = v17 - 65776;
      if ( !v18 )
        return a1[8];
      if ( v18 == 521229 )
        return a1[9];
    }
    else
    {
      if ( a2 == 1735618616 )
        return a1[43];
      v3 = a2 - 1668311156;
      if ( !v3 )
        return a1[22];
      v4 = v3 - 67307452;
      if ( !v4 )
        return a1[35];
      v5 = v4 - 1;
      if ( !v5 )
        return a1[36];
      v6 = v5 - 1;
      if ( !v6 )
        return a1[37];
      v7 = v6 - 1;
      if ( !v7 )
        return a1[38];
      v8 = v7 - 1;
      if ( !v8 )
        return a1[39];
      v9 = v8 - 1;
      if ( !v9 )
        return a1[40];
      v10 = v9 - 1;
      if ( !v10 )
        return a1[41];
      if ( v10 == 1 )
        return a1[42];
    }
    return 0;
  }
  if ( a2 <= 1970168943 )
  {
    if ( a2 == 1970168943 )
      return a1[34];
    v19 = a2 - 1935833203;
    if ( !v19 )
      return a1[23];
    v20 = v19 - 252;
    if ( !v20 )
      return a1[26];
    v21 = v20 - 4;
    if ( !v21 )
      return a1[24];
    v22 = v21 - 917244;
    if ( !v22 )
      return a1[29];
    v23 = v22 - 4;
    if ( !v23 )
      return a1[27];
    v24 = v23 - 252;
    if ( !v24 )
      return a1[30];
    v25 = v24 - 4;
    if ( !v25 )
      return a1[28];
    v26 = v25 - 260348;
    if ( !v26 )
      return a1[32];
    if ( v26 == 4 )
      return a1[31];
    return 0;
  }
  v27 = a2 - 1970168947;
  if ( !v27 )
    return a1[33];
  v28 = v27 - 15929072;
  if ( !v28 )
    return a1[12];
  v29 = v28 - 130051;
  if ( !v29 )
    return a1[20];
  v30 = v29 - 776;
  if ( !v30 )
    return a1[19];
  v31 = v30 - 5;
  if ( !v31 )
    return a1[18];
  v32 = v31 - 65776;
  if ( !v32 )
    return a1[13];
  v33 = v32 - 521229;
  if ( v33 )
  {
    if ( v33 == 33292292 )
      return a1[21];
    return 0;
  }
  return a1[14];
}

```

## disassembly

```asm
0x140050290  mov     eax, 7362786Fh
0x140050295  cmp     edx, eax
0x140050297  jg      loc_14005038F
0x14005029d  jz      loc_14005038A
0x1400502a3  mov     eax, 67737038h
0x1400502a8  cmp     edx, eax
0x1400502aa  jg      short loc_140050317
0x1400502ac  jnz     short loc_1400502B3
0x1400502ae  movzx   eax, word ptr [rcx+56h]
0x1400502b2  retn
0x1400502b3  sub     edx, 63706874h
0x1400502b9  jz      short loc_140050312
0x1400502bb  sub     edx, 40307BCh
0x1400502c1  jnz     short loc_1400502C8
0x1400502c3  movzx   eax, word ptr [rcx+46h]
0x1400502c7  retn
0x1400502c8  sub     edx, 1
0x1400502cb  jnz     short loc_1400502D2
0x1400502cd  movzx   eax, word ptr [rcx+48h]
0x1400502d1  retn
0x1400502d2  sub     edx, 1
0x1400502d5  jz      short loc_14005030D
0x1400502d7  sub     edx, 1
0x1400502da  jz      short loc_140050308
0x1400502dc  sub     edx, 1
0x1400502df  jz      short loc_140050303
0x1400502e1  sub     edx, 1
0x1400502e4  jz      short loc_1400502FE
0x1400502e6  sub     edx, 1
0x1400502e9  jz      short loc_1400502F9
0x1400502eb  cmp     edx, 1
0x1400502ee  jnz     loc_140050447
0x1400502f4  movzx   eax, word ptr [rcx+54h]
0x1400502f8  retn
0x1400502f9  movzx   eax, word ptr [rcx+52h]
0x1400502fd  retn
0x1400502fe  movzx   eax, word ptr [rcx+50h]
0x140050302  retn
0x140050303  movzx   eax, word ptr [rcx+4Eh]
0x140050307  retn
0x140050308  movzx   eax, word ptr [rcx+4Ch]
0x14005030c  retn
0x14005030d  movzx   eax, word ptr [rcx+4Ah]
0x140050311  retn
0x140050312  movzx   eax, word ptr [rcx+2Ch]
0x140050316  retn
0x140050317  sub     edx, 67737039h
0x14005031d  jz      short loc_140050385
0x14005031f  sub     edx, 0EE032Ah
0x140050325  jz      short loc_140050380
0x140050327  sub     edx, 1F8FEh
0x14005032d  jz      short loc_14005037B
0x14005032f  sub     edx, 3
0x140050332  jz      short loc_140050376
0x140050334  sub     edx, 302h
0x14005033a  jz      short loc_140050371
0x14005033c  sub     edx, 308h
0x140050342  jz      short loc_14005036C
0x140050344  sub     edx, 5
0x140050347  jz      short loc_140050367
0x140050349  sub     edx, 100F0h
0x14005034f  jz      short loc_140050362
0x140050351  cmp     edx, 7F40Dh
0x140050357  jnz     loc_140050447
0x14005035d  movzx   eax, word ptr [rcx+12h]
0x140050361  retn
0x140050362  movzx   eax, word ptr [rcx+10h]
0x140050366  retn
0x140050367  movzx   eax, word ptr [rcx+1Eh]
0x14005036b  retn
0x14005036c  movzx   eax, word ptr [rcx+20h]
0x140050370  retn
0x140050371  movzx   eax, word ptr [rcx+22h]
0x140050375  retn
0x140050376  movzx   eax, word ptr [rcx+16h]
0x14005037a  retn
0x14005037b  movzx   eax, word ptr [rcx+14h]
0x14005037f  retn
0x140050380  movzx   eax, word ptr [rcx+0Eh]
0x140050384  retn
0x140050385  movzx   eax, word ptr [rcx+58h]
0x140050389  retn
0x14005038a  movzx   eax, word ptr [rcx+32h]
0x14005038e  retn
0x14005038f  mov     eax, 756E646Fh
0x140050394  cmp     edx, eax
0x140050396  jg      short loc_140050405
0x140050398  jz      short loc_140050400
0x14005039a  sub     edx, 73627873h
0x1400503a0  jz      short loc_1400503FB
0x1400503a2  mov     eax, 0FCh
0x1400503a7  sub     edx, eax
0x1400503a9  jz      short loc_1400503F6
0x1400503ab  sub     edx, 4
0x1400503ae  jz      short loc_1400503F1
0x1400503b0  sub     edx, 0DFEFCh
0x1400503b6  jz      short loc_1400503EC
0x1400503b8  sub     edx, 4
0x1400503bb  jz      short loc_1400503E7
0x1400503bd  sub     edx, eax
0x1400503bf  jz      short loc_1400503E2
0x1400503c1  sub     edx, 4
0x1400503c4  jz      short loc_1400503DD
0x1400503c6  sub     edx, 3F8FCh
0x1400503cc  jz      short loc_1400503D8
0x1400503ce  cmp     edx, 4
0x1400503d1  jnz     short loc_140050447
0x1400503d3  movzx   eax, word ptr [rcx+3Eh]
0x1400503d7  retn
0x1400503d8  movzx   eax, word ptr [rcx+40h]
0x1400503dc  retn
0x1400503dd  movzx   eax, word ptr [rcx+38h]
0x1400503e1  retn
0x1400503e2  movzx   eax, word ptr [rcx+3Ch]
0x1400503e6  retn
0x1400503e7  movzx   eax, word ptr [rcx+36h]
0x1400503eb  retn
0x1400503ec  movzx   eax, word ptr [rcx+3Ah]
0x1400503f0  retn
0x1400503f1  movzx   eax, word ptr [rcx+30h]
0x1400503f5  retn
0x1400503f6  movzx   eax, word ptr [rcx+34h]
0x1400503fa  retn
0x1400503fb  movzx   eax, word ptr [rcx+2Eh]
0x1400503ff  retn
0x140050400  movzx   eax, word ptr [rcx+44h]
0x140050404  retn
0x140050405  sub     edx, 756E6473h
0x14005040b  jz      short loc_140050468
0x14005040d  sub     edx, 0F30EF0h
0x140050413  jz      short loc_140050463
0x140050415  sub     edx, 1FC03h
0x14005041b  jz      short loc_14005045E
0x14005041d  sub     edx, 308h
0x140050423  jz      short loc_140050459
0x140050425  sub     edx, 5
0x140050428  jz      short loc_140050454
0x14005042a  sub     edx, 100F0h
0x140050430  jz      short loc_14005044F
0x140050432  sub     edx, 7F40Dh
0x140050438  jz      short loc_14005044A
0x14005043a  cmp     edx, 1FC0004h
0x140050440  jnz     short loc_140050447
0x140050442  movzx   eax, word ptr [rcx+2Ah]
0x140050446  retn
0x140050447  xor     eax, eax
0x140050449  retn
0x14005044a  movzx   eax, word ptr [rcx+1Ch]
0x14005044e  retn
0x14005044f  movzx   eax, word ptr [rcx+1Ah]
0x140050453  retn
0x140050454  movzx   eax, word ptr [rcx+24h]
0x140050458  retn
0x140050459  movzx   eax, word ptr [rcx+26h]
0x14005045d  retn
0x14005045e  movzx   eax, word ptr [rcx+28h]
0x140050462  retn
0x140050463  movzx   eax, word ptr [rcx+18h]
0x140050467  retn
0x140050468  movzx   eax, word ptr [rcx+42h]
0x14005046c  retn
```
