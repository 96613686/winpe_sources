# ReSetSequencePointers(DIRECTCOLORCONVFRM *,long,long,long,long)

- ea: `0x180011650`
- end: `0x180011d78`
- name: `?ReSetSequencePointers@@YAXPEAUDIRECTCOLORCONVFRM@@JJJJ@Z`
- size: `1832`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *, int, int, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006260`
- `0x180013490`
- `0x180014e50`

## callees

- `0x18000a6d0`
- `0x18000a71c`
- `0x180011650`

## pseudocode

```c
void __fastcall ReSetSequencePointers(struct DIRECTCOLORCONVFRM *a1, int a2, int a3, int a4, int a5)
{
  __int64 v5; // rsi
  int v7; // r9d
  __int64 v9; // r13
  int v10; // eax
  int v11; // r15d
  int v12; // r8d
  int v13; // r11d
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // eax
  int v18; // ebp
  int v19; // r10d
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // eax
  int v24; // r11d
  int v25; // r8d
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  int v29; // r11d
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r10d
  int v34; // ecx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // r10d
  int v39; // eax
  int v40; // eax
  int v41; // ecx
  int v42; // r10d
  int v43; // ecx
  int v44; // ecx
  int v45; // eax
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // eax
  int v50; // r10d
  int v51; // r8d
  int v52; // edx
  int v53; // edx
  int v54; // r8d
  int v55; // ecx
  unsigned int v56; // r9d
  unsigned int v57; // r10d
  unsigned __int64 v58; // rdx
  unsigned int v59; // r8d
  int v60; // ecx
  int v61; // eax
  void *v62; // rcx
  int v63; // ecx
  void *v64; // rax
  int v65; // ecx
  int v66; // r8d
  int v67; // ecx
  int v68; // eax
  int v69; // ecx
  int v70; // ecx
  int v71; // eax
  int v72; // ecx
  int v73; // r8d
  int v74; // eax
  int v75; // ecx
  int v76; // r8d

  v5 = *(_QWORD *)a1;
  *((_DWORD *)a1 + 3822) = a2;
  v7 = a3;
  if ( *(_DWORD *)(v5 + 16) > 3u )
  {
    v7 = -a3;
    if ( a3 > 0 )
      v7 = a3;
  }
  v9 = *((_QWORD *)a1 + 1);
  v10 = a5;
  *((_DWORD *)a1 + 3823) = v7;
  *((_DWORD *)a1 + 3824) = a4;
  if ( *(_DWORD *)(v9 + 16) > 3u )
  {
    v10 = -a5;
    if ( a5 > 0 )
      v10 = a5;
  }
  v11 = *((_DWORD *)a1 + 3834);
  *((_DWORD *)a1 + 3825) = v10;
  if ( v11 )
  {
    *((_DWORD *)a1 + 3637) = 1;
    v12 = v11;
    v13 = 1;
  }
  else
  {
    v13 = *((_DWORD *)a1 + 3637);
    v12 = v13 * ((int)((a2 * *(unsigned __int16 *)(v5 + 14) + 31) & 0xFFFFFFE0) / 8);
  }
  *((_DWORD *)a1 + 3652) = v12;
  *((_DWORD *)a1 + 3653) = 2 * v12;
  if ( v13 == 1 )
  {
    v14 = 0;
  }
  else
  {
    v15 = -v7;
    if ( v7 > 0 )
      v15 = v7;
    v16 = v15 - 1;
    v17 = -v12;
    if ( v12 > 0 )
      v17 = v12;
    v14 = v17 * v16;
  }
  v18 = *((_DWORD *)a1 + 3826);
  v19 = *((_DWORD *)a1 + 3827);
  *((_DWORD *)a1 + 31) = v14;
  *((_DWORD *)a1 + 3654) = v19 * v12 + v18 * *(unsigned __int16 *)(v5 + 14) / 8;
  if ( *((_DWORD *)a1 + 3820) )
  {
    if ( v13 == 1 )
    {
      v20 = *((_DWORD *)a1 + 3817) * v12 + *((_DWORD *)a1 + 3816) * *(unsigned __int16 *)(v5 + 14) / 8;
    }
    else
    {
      v21 = -v7;
      if ( v7 > 0 )
        v21 = v7;
      v22 = ~*((_DWORD *)a1 + 3817) + v21;
      v23 = -v12;
      if ( v12 > 0 )
        v23 = v12;
      v20 = *((_DWORD *)a1 + 3816) * *(unsigned __int16 *)(v5 + 14) / 8 + v23 * v22;
    }
    *((_DWORD *)a1 + 31) = v20;
  }
  v24 = a2;
  if ( v11 )
    v24 = v11;
  if ( *(_DWORD *)(v5 + 16) != 808596553 )
  {
    switch ( *(_DWORD *)(v5 + 16) )
    {
      case 0x31313450:
        v44 = *((_DWORD *)a1 + 3832);
        if ( !v44 )
          v44 = v24 / 4;
        *((_DWORD *)a1 + 3836) = v44;
        *((_DWORD *)a1 + 33) = v24 * v7;
        v45 = v7 * (v44 + v24);
        v26 = v19 * v44;
        *((_DWORD *)a1 + 34) = v45;
        *((_DWORD *)a1 + 3655) = v18 + a2 * v19;
        v27 = v18 / 4;
        goto LABEL_39;
      case 0x3131564E:
        v43 = *((_DWORD *)a1 + 3832);
        *((_DWORD *)a1 + 34) = 0;
        *((_DWORD *)a1 + 3657) = 0;
        if ( !v43 )
          v43 = v24 / 2;
        *((_DWORD *)a1 + 3836) = v43;
        *((_DWORD *)a1 + 3655) = v18 + a2 * v19;
        *((_DWORD *)a1 + 33) = v24 * v7;
        v28 = v18 / 2 + v19 * v43;
        goto LABEL_41;
      case 0x3231564E:
        *((_DWORD *)a1 + 34) = 0;
        v41 = -v7;
        *((_DWORD *)a1 + 3657) = 0;
        *((_DWORD *)a1 + 3836) = v24;
        if ( v7 > 0 )
          v41 = v7;
        v42 = a2 * v19;
        *((_DWORD *)a1 + 33) = v24 * v41;
        *((_DWORD *)a1 + 3655) = v42 + v18;
        *((_DWORD *)a1 + 3656) = v18 + v42 / 2;
        goto LABEL_42;
      case 0x32315659:
        v39 = -v7;
        if ( v7 > 0 )
          v39 = v7;
        v40 = v24 * v39;
        *((_DWORD *)a1 + 34) = v40;
        *((_DWORD *)a1 + 33) = (unsigned int)(5 * v40) >> 2;
        break;
      case 0x32323450:
        v36 = -v7;
        if ( v7 > 0 )
          v36 = v7;
        v37 = v24 * v36;
        *((_DWORD *)a1 + 33) = v37;
        *((_DWORD *)a1 + 34) = (unsigned int)(3 * v37) >> 1;
        break;
      case 0x39555659:
        v32 = -v7;
        if ( v7 > 0 )
          v32 = v7;
        v33 = a2 * v19;
        v34 = v24 * v32;
        *((_DWORD *)a1 + 34) = v34;
        *((_DWORD *)a1 + 33) = (unsigned int)(17 * v34) >> 4;
        *((_DWORD *)a1 + 3655) = v33 + v18;
        v28 = v18 / 4 + v33 / 16;
        v35 = v24 / 4;
LABEL_48:
        *((_DWORD *)a1 + 3836) = v35;
        goto LABEL_40;
      case 0x56555949:
        goto LABEL_36;
      default:
        goto LABEL_43;
    }
    v38 = a2 * v19;
    *((_DWORD *)a1 + 3655) = v38 + v18;
    v28 = v18 / 2 + v38 / 4;
    v35 = v24 / 2;
    goto LABEL_48;
  }
LABEL_36:
  v25 = *((_DWORD *)a1 + 3832);
  if ( !v25 )
    v25 = v24 / 2;
  *((_DWORD *)a1 + 3836) = v25;
  *((_DWORD *)a1 + 33) = v24 * v7;
  *((_DWORD *)a1 + 34) = v24 * v7 + v7 * v25 / 2;
  *((_DWORD *)a1 + 3655) = v18 + a2 * v19;
  v26 = v25 * (v19 / 2);
  v27 = v18 / 2;
LABEL_39:
  v28 = v27 + v26;
LABEL_40:
  *((_DWORD *)a1 + 3657) = v28;
LABEL_41:
  *((_DWORD *)a1 + 3656) = v28;
LABEL_42:
  *((_DWORD *)a1 + 32) = 0;
LABEL_43:
  v29 = *((_DWORD *)a1 + 3835);
  if ( v29 )
  {
    *((_DWORD *)a1 + 3638) = 1;
    v30 = 1;
    v31 = v29;
  }
  else
  {
    v30 = *((_DWORD *)a1 + 3638);
    v31 = v30 * ((int)((a4 * *(unsigned __int16 *)(v9 + 14) + 31) & 0xFFFFFFE0) / 8);
  }
  *((_DWORD *)a1 + 3643) = v31;
  *((_DWORD *)a1 + 3644) = 2 * v31;
  if ( v30 == 1 )
  {
    v46 = 0;
  }
  else
  {
    v47 = -*((_DWORD *)a1 + 3825);
    if ( *((int *)a1 + 3825) > 0 )
      v47 = *((_DWORD *)a1 + 3825);
    v48 = v47 - 1;
    v49 = -v31;
    if ( v31 > 0 )
      v49 = v31;
    v46 = v49 * v48;
  }
  v50 = *((_DWORD *)a1 + 3828);
  v51 = *((_DWORD *)a1 + 3829);
  *((_DWORD *)a1 + 35) = v46;
  *((_DWORD *)a1 + 3645) = v51 * v31 + v50 * *(unsigned __int16 *)(v9 + 14) / 8;
  if ( v29 )
    a4 = v29;
  if ( *(_DWORD *)(v9 + 16) == 808596553 )
    goto LABEL_81;
  if ( *(_DWORD *)(v9 + 16) == 825316942 )
  {
    v74 = *((_DWORD *)a1 + 3825);
    v75 = -v74;
    *((_DWORD *)a1 + 37) = 0;
    *((_DWORD *)a1 + 3648) = 0;
    if ( v74 > 0 )
      v75 = v74;
    v76 = *((_DWORD *)a1 + 3824) * v51;
    *((_DWORD *)a1 + 36) = a4 * v75;
    *((_DWORD *)a1 + 3646) = v76 + v50;
    v55 = v50 / 2 + v76 / 2;
    goto LABEL_85;
  }
  if ( *(_DWORD *)(v9 + 16) != 842094158 )
  {
    if ( *(_DWORD *)(v9 + 16) == 842094169 )
    {
      v69 = -*((_DWORD *)a1 + 3825);
      if ( *((int *)a1 + 3825) > 0 )
        v69 = *((_DWORD *)a1 + 3825);
      v70 = a4 * v69;
      *((_DWORD *)a1 + 37) = v70;
      *((_DWORD *)a1 + 36) = (unsigned int)(5 * v70) >> 2;
      goto LABEL_84;
    }
    if ( *(_DWORD *)(v9 + 16) == 842150992 )
    {
      v65 = -*((_DWORD *)a1 + 3825);
      if ( *((int *)a1 + 3825) > 0 )
        v65 = *((_DWORD *)a1 + 3825);
      v66 = *((_DWORD *)a1 + 3824) * v51;
      v67 = a4 * v65;
      *((_DWORD *)a1 + 36) = v67;
      *((_DWORD *)a1 + 3646) = v66 + v50;
      v68 = (v66 + v50) / 2;
      *((_DWORD *)a1 + 37) = (unsigned int)(3 * v67) >> 1;
      *((_DWORD *)a1 + 3647) = v68;
      *((_DWORD *)a1 + 3648) = v68;
      goto LABEL_86;
    }
    if ( *(_DWORD *)(v9 + 16) != 1448433993 )
      goto LABEL_87;
LABEL_81:
    v52 = -*((_DWORD *)a1 + 3825);
    if ( *((int *)a1 + 3825) > 0 )
      v52 = *((_DWORD *)a1 + 3825);
    v53 = a4 * v52;
    *((_DWORD *)a1 + 36) = v53;
    *((_DWORD *)a1 + 37) = (unsigned int)(5 * v53) >> 2;
LABEL_84:
    v54 = *((_DWORD *)a1 + 3824) * v51;
    *((_DWORD *)a1 + 3646) = v54 + v50;
    v55 = v50 / 2 + v54 / 4;
    *((_DWORD *)a1 + 3648) = v55;
LABEL_85:
    *((_DWORD *)a1 + 3647) = v55;
LABEL_86:
    *((_DWORD *)a1 + 3837) = a4 / 2;
    goto LABEL_87;
  }
  v71 = *((_DWORD *)a1 + 3825);
  v72 = -v71;
  *((_DWORD *)a1 + 37) = 0;
  *((_DWORD *)a1 + 3648) = 0;
  if ( v71 > 0 )
    v72 = v71;
  *((_DWORD *)a1 + 3837) = a4;
  v73 = *((_DWORD *)a1 + 3824) * v51;
  *((_DWORD *)a1 + 36) = a4 * v72;
  *((_DWORD *)a1 + 3646) = v73 + v50;
  *((_DWORD *)a1 + 3647) = v50 + v73 / 2;
LABEL_87:
  v56 = *((_DWORD *)a1 + 3641);
  HIDWORD(v58) = 0;
  v57 = *((_DWORD *)a1 + 3660);
  LODWORD(v58) = v56 % v57;
  v59 = (v56 / v57) & 0xFFFFFFFE;
  *((_DWORD *)a1 + 38) = v59;
  if ( ((v56 / v57) & 2) != 0 )
  {
    v59 -= 2;
    *((_DWORD *)a1 + 38) = v59;
  }
  if ( v57 == 1 )
  {
    *((_DWORD *)a1 + 38) = v56;
    v59 = v56;
  }
  v60 = v56;
  if ( v57 != 2 )
    v60 = 2 * v59;
  *((_DWORD *)a1 + 39) = v60;
  if ( v57 == 4 )
    v56 = 3 * v59;
  *((_DWORD *)a1 + 40) = v56;
  if ( *((_DWORD *)a1 + 3838) && *(_DWORD *)(v9 + 16) <= 3u )
  {
    v61 = -(*((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643));
    if ( *((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643) > 0 )
      v61 = *((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643);
    if ( v61 > *((_DWORD *)a1 + 30) )
    {
      v62 = (void *)*((_QWORD *)a1 + 14);
      if ( v62 )
      {
        operator delete(v62, v58);
        *((_QWORD *)a1 + 14) = 0;
      }
      v63 = -(*((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643));
      if ( *((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643) > 0 )
        v63 = *((_DWORD *)a1 + 3825) * *((_DWORD *)a1 + 3643);
      *((_DWORD *)a1 + 30) = v63;
      v64 = operator new[](v63);
      *((_QWORD *)a1 + 14) = v64;
      if ( !v64 )
        *((_DWORD *)a1 + 30) = 0;
    }
  }
}

```

## disassembly

```asm
0x180011650  push    rbx
0x180011652  push    rbp
0x180011653  push    rsi
0x180011654  push    rdi
0x180011655  push    r12
0x180011657  push    r13
0x180011659  push    r14
0x18001165b  push    r15
0x18001165d  sub     rsp, 28h
0x180011661  mov     rsi, [rcx]
0x180011664  mov     edi, r9d
0x180011667  mov     [rcx+3BB8h], edx
0x18001166d  mov     r9d, r8d
0x180011670  mov     r14d, edx
0x180011673  mov     rbx, rcx
0x180011676  cmp     dword ptr [rsi+10h], 3
0x18001167a  jbe     short loc_180011683
0x18001167c  neg     r9d
0x18001167f  cmovs   r9d, r8d
0x180011683  mov     r13, [rcx+8]
0x180011687  mov     eax, [rsp+68h+arg_20]
0x18001168e  mov     [rcx+3BBCh], r9d
0x180011695  mov     [rcx+3BC0h], edi
0x18001169b  cmp     dword ptr [r13+10h], 3
0x1800116a0  jbe     short loc_1800116AC
0x1800116a2  neg     eax
0x1800116a4  cmovs   eax, [rsp+68h+arg_20]
0x1800116ac  mov     r15d, [rcx+3BE8h]
0x1800116b3  xor     r12d, r12d
0x1800116b6  mov     [rcx+3BC4h], eax
0x1800116bc  mov     ecx, 8
0x1800116c1  lea     r10d, [rcx-7]
0x1800116c5  test    r15d, r15d
0x1800116c8  jz      short loc_1800116D9
0x1800116ca  mov     [rbx+38D4h], r10d
0x1800116d1  mov     r8d, r15d
0x1800116d4  mov     r11d, r10d
0x1800116d7  jmp     short loc_1800116F8
0x1800116d9  movzx   eax, word ptr [rsi+0Eh]
0x1800116dd  mov     r11d, [rbx+38D4h]
0x1800116e4  imul    eax, r14d
0x1800116e8  add     eax, 1Fh
0x1800116eb  and     eax, 0FFFFFFE0h
0x1800116ee  cdq
0x1800116ef  idiv    ecx
0x1800116f1  mov     r8d, eax
0x1800116f4  imul    r8d, r11d
0x1800116f8  mov     [rbx+3910h], r8d
0x1800116ff  lea     ecx, [r8+r8]
0x180011703  mov     [rbx+3914h], ecx
0x180011709  cmp     r11d, r10d
0x18001170c  jnz     short loc_180011713
0x18001170e  mov     ecx, r12d
0x180011711  jmp     short loc_18001172B
0x180011713  mov     ecx, r9d
0x180011716  mov     eax, r8d
0x180011719  neg     ecx
0x18001171b  cmovs   ecx, r9d
0x18001171f  sub     ecx, r10d
0x180011722  neg     eax
0x180011724  cmovs   eax, r8d
0x180011728  imul    ecx, eax
0x18001172b  mov     ebp, [rbx+3BC8h]
0x180011731  mov     r10d, [rbx+3BCCh]
0x180011738  mov     [rbx+7Ch], ecx
0x18001173b  mov     ecx, 8
0x180011740  movzx   eax, word ptr [rsi+0Eh]
0x180011744  imul    eax, ebp
0x180011747  cdq
0x180011748  idiv    ecx
0x18001174a  mov     ecx, r8d
0x18001174d  imul    ecx, r10d
0x180011751  add     eax, ecx
0x180011753  mov     [rbx+3918h], eax
0x180011759  cmp     [rbx+3BB0h], r12d
0x180011760  jz      short loc_1800117C1
0x180011762  cmp     r11d, 1
0x180011766  jnz     short loc_180011788
0x180011768  movzx   eax, word ptr [rsi+0Eh]
0x18001176c  lea     ecx, [r11+7]
0x180011770  imul    eax, [rbx+3BA0h]
0x180011777  cdq
0x180011778  idiv    ecx
0x18001177a  imul    r8d, [rbx+3BA4h]
0x180011782  lea     ecx, [r8+rax]
0x180011786  jmp     short loc_1800117BE
0x180011788  mov     eax, [rbx+3BA4h]
0x18001178e  mov     ecx, r9d
0x180011791  not     eax
0x180011793  neg     ecx
0x180011795  cmovs   ecx, r9d
0x180011799  add     ecx, eax
0x18001179b  mov     eax, r8d
0x18001179e  neg     eax
0x1800117a0  cmovs   eax, r8d
0x1800117a4  mov     r8d, 8
0x1800117aa  imul    ecx, eax
0x1800117ad  movzx   eax, word ptr [rsi+0Eh]
0x1800117b1  imul    eax, [rbx+3BA0h]
0x1800117b8  cdq
0x1800117b9  idiv    r8d
0x1800117bc  add     ecx, eax
0x1800117be  mov     [rbx+7Ch], ecx
0x1800117c1  mov     ecx, [rsi+10h]
0x1800117c4  test    r15d, r15d
0x1800117c7  mov     esi, 2
0x1800117cc  mov     r11d, r14d
0x1800117cf  cmovnz  r11d, r15d
0x1800117d3  lea     r15d, [rsi+2]
0x1800117d7  sub     ecx, 30323449h
0x1800117dd  jz      short loc_18001182C
0x1800117df  sub     ecx, 0FF0007h
0x1800117e5  jz      loc_180011A17
0x1800117eb  sub     ecx, 21FEh
0x1800117f1  jz      loc_1800119C8
0x1800117f7  sub     ecx, 1000000h
0x1800117fd  jz      loc_18001197F
0x180011803  sub     ecx, 0Bh
0x180011806  jz      loc_18001195E
0x18001180c  sub     ecx, 0DDF7h
0x180011812  jz      loc_18001191A
0x180011818  sub     ecx, 7232209h
0x18001181e  jz      loc_1800118C6
0x180011824  cmp     ecx, 1D0002F0h
0x18001182a  jnz     short loc_18001189B
0x18001182c  mov     r8d, [rbx+3BE0h]
0x180011833  mov     eax, r11d
0x180011836  cdq
0x180011837  mov     ecx, r9d
0x18001183a  idiv    esi
0x18001183c  test    r8d, r8d
0x18001183f  cmovz   r8d, eax
0x180011843  imul    ecx, r11d
0x180011847  mov     eax, r8d
0x18001184a  mov     [rbx+3BF0h], r8d
0x180011851  imul    eax, r9d
0x180011855  mov     [rbx+84h], ecx
0x18001185b  cdq
0x18001185c  idiv    esi
0x18001185e  add     eax, ecx
0x180011860  mov     [rbx+88h], eax
0x180011866  mov     eax, r10d
0x180011869  imul    eax, r14d
0x18001186d  add     eax, ebp
0x18001186f  mov     [rbx+391Ch], eax
0x180011875  mov     eax, r10d
0x180011878  cdq
0x180011879  idiv    esi
0x18001187b  mov     ecx, eax
0x18001187d  mov     eax, ebp
0x18001187f  cdq
0x180011880  imul    ecx, r8d
0x180011884  idiv    esi
0x180011886  add     ecx, eax
0x180011888  mov     [rbx+3924h], ecx
0x18001188e  mov     [rbx+3920h], ecx
0x180011894  mov     [rbx+80h], r12d
0x18001189b  mov     r11d, [rbx+3BECh]
0x1800118a2  mov     ebp, 8
0x1800118a7  test    r11d, r11d
0x1800118aa  jz      loc_180011A68
0x1800118b0  mov     dword ptr [rbx+38D8h], 1
0x1800118ba  lea     r8d, [rbp-7]
0x1800118be  mov     r9d, r11d
0x1800118c1  jmp     loc_180011A87
0x1800118c6  mov     ecx, r9d
0x1800118c9  neg     ecx
0x1800118cb  cmovs   ecx, r9d
0x1800118cf  imul    r10d, r14d
0x1800118d3  imul    ecx, r11d
0x1800118d7  mov     eax, r10d
0x1800118da  cdq
0x1800118db  mov     [rbx+88h], ecx
0x1800118e1  imul    ecx, 11h
0x1800118e4  shr     ecx, 4
0x1800118e7  mov     [rbx+84h], ecx
0x1800118ed  lea     ecx, [r10+rbp]
0x1800118f1  mov     [rbx+391Ch], ecx
0x1800118f7  mov     ecx, 10h
0x1800118fc  idiv    ecx
0x1800118fe  mov     ecx, eax
0x180011900  mov     eax, ebp
0x180011902  cdq
0x180011903  idiv    r15d
0x180011906  add     ecx, eax
0x180011908  mov     eax, r11d
0x18001190b  cdq
0x18001190c  idiv    r15d
0x18001190f  mov     [rbx+3BF0h], eax
0x180011915  jmp     loc_180011888
0x18001191a  mov     eax, r9d
0x18001191d  neg     eax
0x18001191f  cmovs   eax, r9d
0x180011923  imul    eax, r11d
0x180011927  mov     [rbx+84h], eax
0x18001192d  lea     eax, [rax+rax*2]
0x180011930  shr     eax, 1
0x180011932  mov     [rbx+88h], eax
0x180011938  imul    r10d, r14d
0x18001193c  lea     eax, [r10+rbp]
0x180011940  mov     [rbx+391Ch], eax
0x180011946  mov     eax, r10d
0x180011949  cdq
0x18001194a  idiv    r15d
0x18001194d  mov     ecx, eax
0x18001194f  mov     eax, ebp
0x180011951  cdq
0x180011952  idiv    esi
0x180011954  add     ecx, eax
0x180011956  mov     eax, r11d
0x180011959  cdq
0x18001195a  idiv    esi
0x18001195c  jmp     short loc_18001190F
0x18001195e  mov     eax, r9d
0x180011961  neg     eax
0x180011963  cmovs   eax, r9d
0x180011967  imul    eax, r11d
0x18001196b  mov     [rbx+88h], eax
0x180011971  lea     eax, [rax+rax*4]
0x180011974  shr     eax, 2
0x180011977  mov     [rbx+84h], eax
0x18001197d  jmp     short loc_180011938
0x18001197f  mov     ecx, r9d
0x180011982  mov     [rbx+88h], r12d
0x180011989  neg     ecx
0x18001198b  mov     [rbx+3924h], r12d
0x180011992  mov     [rbx+3BF0h], r11d
0x180011999  cmovs   ecx, r9d
0x18001199d  imul    r10d, r14d
0x1800119a1  imul    ecx, r11d
0x1800119a5  mov     eax, r10d
0x1800119a8  cdq
0x1800119a9  mov     [rbx+84h], ecx
0x1800119af  idiv    esi
0x1800119b1  lea     ecx, [r10+rbp]
0x1800119b5  add     eax, ebp
0x1800119b7  mov     [rbx+391Ch], ecx
0x1800119bd  mov     [rbx+3920h], eax
0x1800119c3  jmp     loc_180011894
0x1800119c8  mov     ecx, [rbx+3BE0h]
0x1800119ce  mov     eax, r11d
0x1800119d1  cdq
0x1800119d2  mov     [rbx+88h], r12d
0x1800119d9  idiv    esi
0x1800119db  test    ecx, ecx
0x1800119dd  mov     [rbx+3924h], r12d
0x1800119e4  cmovz   ecx, eax
0x1800119e7  mov     eax, r10d
0x1800119ea  imul    eax, r14d
0x1800119ee  mov     [rbx+3BF0h], ecx
0x1800119f4  imul    r9d, r11d
0x1800119f8  imul    ecx, r10d
0x1800119fc  add     eax, ebp
0x1800119fe  mov     [rbx+391Ch], eax
0x180011a04  mov     eax, ebp
0x180011a06  cdq
0x180011a07  mov     [rbx+84h], r9d
0x180011a0e  idiv    esi
0x180011a10  add     ecx, eax
0x180011a12  jmp     loc_18001188E
0x180011a17  mov     ecx, [rbx+3BE0h]
0x180011a1d  mov     eax, r11d
0x180011a20  cdq
0x180011a21  idiv    r15d
0x180011a24  test    ecx, ecx
0x180011a26  cmovz   ecx, eax
0x180011a29  mov     eax, r9d
0x180011a2c  imul    eax, r11d
0x180011a30  mov     [rbx+3BF0h], ecx
0x180011a36  mov     [rbx+84h], eax
0x180011a3c  lea     eax, [rcx+r11]
0x180011a40  imul    eax, r9d
0x180011a44  imul    ecx, r10d
0x180011a48  mov     [rbx+88h], eax
0x180011a4e  mov     eax, r10d
0x180011a51  imul    eax, r14d
0x180011a55  add     eax, ebp
0x180011a57  mov     [rbx+391Ch], eax
0x180011a5d  mov     eax, ebp
0x180011a5f  cdq
0x180011a60  idiv    r15d
0x180011a63  jmp     loc_180011886
0x180011a68  movzx   eax, word ptr [r13+0Eh]
0x180011a6d  mov     r8d, [rbx+38D8h]
0x180011a74  imul    eax, edi
0x180011a77  add     eax, 1Fh
0x180011a7a  and     eax, 0FFFFFFE0h
0x180011a7d  cdq
0x180011a7e  idiv    ebp
0x180011a80  mov     r9d, eax
0x180011a83  imul    r9d, r8d
0x180011a87  mov     [rbx+38ECh], r9d
0x180011a8e  lea     ecx, [r9+r9]
0x180011a92  mov     [rbx+38F0h], ecx
0x180011a98  cmp     r8d, 1
0x180011a9c  jnz     short loc_180011AA3
0x180011a9e  mov     ecx, r12d
0x180011aa1  jmp     short loc_180011ABE
0x180011aa3  mov     eax, [rbx+3BC4h]
0x180011aa9  mov     ecx, eax
  ... truncated ...
```
