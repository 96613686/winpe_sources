# EXUpdateRecord

- ea: `0x10018550`
- end: `0x10018b6d`
- name: `EXUpdateRecord`
- size: `1565`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callers

- `0x1001c090`

## callees

- `0x10013490`
- `0x10016b00`
- `0x10016e80`
- `0x10017110`
- `0x100175a0`
- `0x10017790`
- `0x10017b00`
- `0x10017f40`
- `0x10018060`
- `0x100181b0`
- `0x100183e0`
- `0x10018430`
- `0x10018550`
- `0x1002580a`
- `0x10025ab7`
- `0x10025f86`

## pseudocode

```c
int __fastcall EXUpdateRecord(int a1, int a2, int a3)
{
  int *v3; // ebx
  unsigned __int16 v4; // si
  int result; // eax
  double *v6; // edi
  unsigned __int16 v7; // cx
  __int16 v8; // ax
  int v9; // esi
  _DWORD *v10; // eax
  int v11; // ecx
  int v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // edx
  _DWORD *v15; // ecx
  int v16; // eax
  _DWORD *v17; // eax
  int v18; // eax
  int v19; // ecx
  _DWORD **v20; // eax
  _DWORD *v21; // ecx
  int *j; // ecx
  __int16 v23; // ax
  int *v24; // ecx
  __int16 k; // dx
  _DWORD *v26; // edi
  int v27; // ebx
  _DWORD *v28; // edx
  int v29; // ecx
  int v30; // esi
  _DWORD *v31; // edi
  int v32; // eax
  int v33; // edx
  int v34; // esi
  int *v35; // ebx
  int v36; // edx
  int v37; // eax
  int v38; // edx
  int v39; // ecx
  int v40; // ecx
  __int16 v41; // si
  __int16 v42; // bx
  int v43; // ebx
  int *v44; // edi
  int v45; // edx
  int v46; // esi
  int v47; // ecx
  int *v48; // eax
  _DWORD *v49; // edi
  int *v50; // esi
  _DWORD v51[4]; // [esp+10h] [ebp-6Ch] BYREF
  double v52; // [esp+20h] [ebp-5Ch]
  int v53; // [esp+44h] [ebp-38h]
  int i; // [esp+48h] [ebp-34h]
  int v55; // [esp+4Ch] [ebp-30h]
  int v56; // [esp+50h] [ebp-2Ch]
  int v57; // [esp+54h] [ebp-28h]
  int v58; // [esp+58h] [ebp-24h]
  int v59; // [esp+5Ch] [ebp-20h]
  int v60; // [esp+60h] [ebp-1Ch]
  int v61; // [esp+64h] [ebp-18h]
  int v62; // [esp+68h] [ebp-14h]
  _DWORD *v63; // [esp+6Ch] [ebp-10h]
  int v64; // [esp+70h] [ebp-Ch]
  _WORD v65[4]; // [esp+74h] [ebp-8h] BYREF

  v3 = (int *)a3;
  v4 = a2;
  v64 = a1;
  v58 = a2;
  if ( (unsigned int)RecordCellSize() > 0xEFFF )
    return -27;
  v63 = (_DWORD *)MemAllocate(8);
  if ( !v63 )
    return -2;
  v6 = (double *)a3;
  v60 = 0;
  v59 = 0;
  if ( !a3 )
  {
LABEL_81:
    v26 = v63;
    if ( !*v63 )
    {
      ModifyListDestroy(v63);
      return 0;
    }
    v27 = v64;
    v28 = v63;
    v29 = v64;
    *(_DWORD *)(*(_DWORD *)(v64 + 48) + 44) = 1;
    v30 = ModifyListExecute(v29, v28);
    if ( v30 )
    {
      ModifyListDestroy(v26);
      return v30;
    }
    v31 = (_DWORD *)*v26;
    if ( !v31 )
    {
LABEL_102:
      v43 = 0;
      v59 = 0;
      v44 = (int *)*v63;
      if ( *v63 )
      {
        v45 = a3;
        do
        {
          v46 = v45;
          if ( v45 )
          {
            while ( *((_WORD *)v44 + 11) != *(unsigned __int8 *)(v46 + 4) )
            {
              v46 = *(_DWORD *)v46;
              if ( !v46 )
                goto LABEL_107;
            }
          }
          else
          {
LABEL_107:
            v46 = 0;
          }
          if ( (*(_WORD *)(v45 + 8) & 0x800) != 0 || !v46 )
          {
            v47 = v59;
          }
          else
          {
            v43 = dword_10001970[abs32(BFSetFilePosition(*(int **)(v64 + 20), 0, v44[2]))];
            if ( v43 == -10 )
            {
              v43 = -10;
              goto LABEL_122;
            }
            if ( v43 )
              goto LABEL_122;
            v43 = WriteCell(v46);
            if ( v43 )
              goto LABEL_122;
            v45 = a3;
            v47 = v46;
            v59 = v46;
          }
          v44 = (int *)*v44;
        }
        while ( v44 );
        if ( v47 )
        {
          LOWORD(v53) = v58;
          LOWORD(i) = v58;
          HIWORD(v53) = *(unsigned __int8 *)(v45 + 4);
          HIWORD(i) = *(unsigned __int8 *)(v47 + 4);
          UpdateDimensions(v53, i);
        }
      }
LABEL_122:
      v48 = (int *)a3;
      v49 = 0;
      if ( a3 )
      {
        do
        {
          v50 = (int *)*v48;
          if ( *((__int16 *)v48 + 4) >= 0 )
          {
            v49 = v48;
          }
          else
          {
            MemFree(v48);
            if ( v49 )
              *v49 = v50;
          }
          v48 = v50;
        }
        while ( v50 );
      }
      ModifyListDestroy(v63);
      return v43;
    }
    while ( 1 )
    {
      v32 = v31[3];
      v33 = v31[4];
      if ( v32 )
      {
        v34 = v31[5];
        if ( v33 )
        {
          if ( v33 != v32 )
            AdjustIndexRows(v31[5]);
        }
        else
        {
          v57 = v31[5];
          AdjustIndexRows(v34);
          v35 = *(int **)(*(_DWORD *)(v27 + 48) + 40);
          v36 = *v35;
          if ( (unsigned __int16)v34 >= *v35 && (unsigned __int16)v34 < v35[1] )
          {
            v37 = ((unsigned __int16)v34 - v36) / 32;
            v38 = ((unsigned __int16)v34 - v36) % 32;
            v39 = v35[v37 + 4];
            if ( v39 )
            {
              v40 = v39 + 20 * v38 + 8;
              if ( v40 )
              {
                if ( *(_DWORD *)(v40 + 12) != -1 )
                {
                  v41 = *(_WORD *)v40;
                  v42 = *(_WORD *)(v40 + 2);
                  v59 = v42;
                  if ( v41 + 1 == v42 )
                  {
                    v27 = v64;
                    if ( v41 == HIWORD(v57) )
                      *(_DWORD *)v40 = 0;
                    goto LABEL_101;
                  }
                  if ( v41 == HIWORD(v57) )
                  {
                    *(_WORD *)v40 = v41 + 1;
                  }
                  else if ( v59 == HIWORD(v57) - 1 )
                  {
                    *(_WORD *)(v40 + 2) = v42 - 1;
                  }
                }
              }
            }
          }
          v27 = v64;
        }
      }
      else
      {
        result = ReportInsertCell(v31[5], v31[2]);
        if ( result )
          return result;
      }
LABEL_101:
      v31 = (_DWORD *)*v31;
      if ( !v31 )
        goto LABEL_102;
    }
  }
  v7 = v4;
  for ( i = v4; ; v7 = i )
  {
    v8 = *((unsigned __int8 *)v6 + 4);
    LOWORD(v57) = v7;
    HIWORD(v57) = v8;
    v9 = v57;
    if ( ExcelReadCell(v64, (__int16 *)v51, v57) )
    {
      if ( ((_WORD)v6[1] & 0x800) == 0 )
      {
        result = LocateSpotForNewCell(v9);
        if ( result )
          return result;
        v56 = CellSize(v6);
        v18 = MemAllocate(24);
        v14 = (_DWORD *)v18;
        if ( !v18 )
          return -2;
        v19 = v55;
        *(_DWORD *)(v18 + 16) = v56;
        v20 = (_DWORD **)v63;
        v14[2] = v19;
        v14[3] = 0;
        v21 = *v20;
        if ( *v20 )
        {
          while ( *v21 )
            v21 = (_DWORD *)*v21;
          *v21 = v14;
        }
        else
        {
          *v20 = v14;
        }
        ++v59;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    v10 = *(_DWORD **)(v64 + 44);
    if ( *v10 == 1 )
      v10 = (_DWORD *)v10[11];
    v11 = v10[22];
    ++v60;
    v12 = v10[23];
    v62 = v11;
    v61 = v12;
    if ( (v3[2] & 0x800) != 0 )
    {
      if ( (v51[0] & 0x4000) != 0 )
      {
        result = SplitMulRecord(v63, v11, v12, v9, v65);
        if ( result )
          return result;
        v3 = (int *)a3;
        v6 = (double *)a3;
        do
        {
          if ( *((unsigned __int8 *)v6 + 4) == v65[0] )
            break;
          v6 = *(double **)v6;
        }
        while ( v6 );
        goto LABEL_68;
      }
      v16 = MemAllocate(24);
      v14 = (_DWORD *)v16;
      if ( !v16 )
        return -2;
      *(_DWORD *)(v16 + 8) = v62;
      *(_DWORD *)(v16 + 12) = v61;
      v17 = v63;
      v14[4] = 0;
      v15 = (_DWORD *)*v17;
      if ( *v17 )
      {
        while ( *v15 )
          v15 = (_DWORD *)*v15;
        goto LABEL_40;
      }
      *v17 = v14;
LABEL_66:
      v14[5] = v9;
LABEL_67:
      v6 = *(double **)v6;
      goto LABEL_68;
    }
    if ( *((_DWORD *)v6 + 3) == v51[1] )
    {
      if ( (v51[0] & 2) != 0 && ((_BYTE)v6[1] & 2) != 0 )
      {
        if ( v52 == v6[3] )
          goto LABEL_67;
      }
      else if ( (v51[0] & 0x10) != 0 && ((_BYTE)v6[1] & 0x10) != 0 )
      {
        if ( LODWORD(v52) == *((_DWORD *)v6 + 6) )
          goto LABEL_67;
      }
      else if ( (v51[0] & 4) != 0 && ((_BYTE)v6[1] & 4) != 0 )
      {
        if ( (LODWORD(v52) != 0) == (*((_DWORD *)v6 + 6) != 0) )
          goto LABEL_67;
        v11 = v62;
      }
      else if ( (v51[0] & 8) != 0 && ((_BYTE)v6[1] & 8) != 0 )
      {
        if ( LODWORD(v52) == *((_DWORD *)v6 + 6) )
          goto LABEL_67;
      }
      else if ( (v51[0] & 0x2000) != 0 && ((_WORD)v6[1] & 0x2000) != 0 )
      {
        if ( v51[2] == *((_DWORD *)v6 + 4) )
          goto LABEL_67;
      }
      else if ( (v51[0] & 1) != 0 && ((_BYTE)v6[1] & 1) != 0 )
      {
        goto LABEL_67;
      }
    }
    if ( (v51[0] & 0x4000) == 0 )
    {
      v56 = CellSize(v6);
      v13 = (_DWORD *)MemAllocate(24);
      v14 = v13;
      if ( !v13 )
        return -2;
      v13[2] = v62;
      v13[3] = v61;
      v13[4] = v56;
      v15 = (_DWORD *)*v63;
      if ( !*v63 )
      {
        *v63 = v13;
        goto LABEL_66;
      }
      while ( *v15 )
        v15 = (_DWORD *)*v15;
LABEL_40:
      *v15 = v14;
      goto LABEL_66;
    }
    result = SplitMulRecord(v63, v11, v61, v9, v65);
    if ( result )
      return result;
    v3 = (int *)a3;
    v6 = (double *)a3;
    do
    {
      if ( *((unsigned __int8 *)v6 + 4) == v65[0] )
        break;
      v6 = *(double **)v6;
    }
    while ( v6 );
LABEL_68:
    if ( !v6 )
      break;
  }
  if ( v60 || v59 <= 0 )
    goto LABEL_81;
  for ( j = v3; j; j = (int *)*j )
  {
    if ( (j[2] & 0x800) == 0 )
      break;
  }
  v23 = *((unsigned __int8 *)j + 4);
  v24 = (int *)*j;
  for ( k = v23 + 1; v24; v24 = (int *)*v24 )
  {
    if ( (v24[2] & 0x800) == 0 )
    {
      if ( *((unsigned __int8 *)v24 + 4) != k )
        goto LABEL_81;
      ++k;
    }
  }
  ModifyListDestroy(v63);
  return EXInsertRecord(v3);
}

```

## disassembly

```asm
0x10018550  mov     edi, edi
0x10018552  push    ebp
0x10018553  mov     ebp, esp
0x10018555  sub     esp, 70h
0x10018558  push    ebx
0x10018559  mov     ebx, [ebp+arg_0]
0x1001855c  mov     eax, ecx
0x1001855e  push    esi
0x1001855f  mov     esi, edx
0x10018561  mov     [ebp+var_C], eax
0x10018564  push    edi
0x10018565  mov     edx, ebx
0x10018567  mov     [ebp+var_24], esi
0x1001856a  call    RecordCellSize
0x1001856f  cmp     eax, 0EFFFh
0x10018574  jbe     short loc_10018584
0x10018576  mov     eax, 0FFFFFFE5h
0x1001857b  pop     edi
0x1001857c  pop     esi
0x1001857d  pop     ebx
0x1001857e  mov     esp, ebp
0x10018580  pop     ebp
0x10018581  retn    4
0x10018584  mov     ecx, 8
0x10018589  call    _MemAllocate@4; MemAllocate(x)
0x1001858e  mov     [ebp+var_10], eax
0x10018591  test    eax, eax
0x10018593  jz      loc_10018B5F
0x10018599  xor     eax, eax
0x1001859b  mov     edi, ebx
0x1001859d  mov     [ebp+var_1C], eax
0x100185a0  mov     [ebp+var_20], eax
0x100185a3  test    edi, edi
0x100185a5  jz      loc_10018912
0x100185ab  movzx   ecx, si
0x100185ae  mov     [ebp+var_34], ecx
0x100185b1  movzx   eax, byte ptr [edi+4]
0x100185b5  lea     edx, [ebp+var_6C]
0x100185b8  mov     word ptr [ebp+var_28], cx
0x100185bc  mov     ecx, [ebp+var_C]
0x100185bf  mov     word ptr [ebp+var_28+2], ax
0x100185c3  mov     esi, [ebp+var_28]
0x100185c6  push    esi
0x100185c7  call    _ExcelReadCell@12; ExcelReadCell(x,x,x)
0x100185cc  test    eax, eax
0x100185ce  jnz     loc_10018818
0x100185d4  mov     eax, [ebp+var_C]
0x100185d7  mov     eax, [eax+2Ch]
0x100185da  cmp     dword ptr [eax], 1
0x100185dd  jnz     short loc_100185E2
0x100185df  mov     eax, [eax+2Ch]
0x100185e2  mov     ecx, [eax+58h]
0x100185e5  mov     edx, 800h
0x100185ea  inc     [ebp+var_1C]
0x100185ed  mov     eax, [eax+5Ch]
0x100185f0  mov     [ebp+var_14], ecx
0x100185f3  mov     [ebp+var_18], eax
0x100185f6  test    [ebx+8], dx
0x100185fa  jnz     loc_10018778
0x10018600  mov     eax, [edi+0Ch]
0x10018603  mov     edx, [ebp+var_6C]
0x10018606  cmp     eax, [ebp+var_68]
0x10018609  jnz     short loc_10018669
0x1001860b  test    dl, 2
0x1001860e  jz      short loc_1001862B
0x10018610  test    byte ptr [edi+8], 2
0x10018614  jz      short loc_1001862B
0x10018616  movsd   xmm0, [ebp+var_5C]
0x1001861b  ucomisd xmm0, qword ptr [edi+18h]
0x10018620  lahf
0x10018621  test    ah, 44h
0x10018624  jp      short loc_10018669
0x10018626  jmp     loc_10018892
0x1001862b  test    dl, 10h
0x1001862e  jz      short loc_10018643
0x10018630  test    byte ptr [edi+8], 10h
0x10018634  jz      short loc_10018643
0x10018636  mov     eax, dword ptr [ebp+var_5C]
0x10018639  cmp     eax, [edi+18h]
0x1001863c  jnz     short loc_10018669
0x1001863e  jmp     loc_10018892
0x10018643  test    dl, 4
0x10018646  jz      short loc_100186BA
0x10018648  test    byte ptr [edi+8], 4
0x1001864c  jz      short loc_100186BA
0x1001864e  xor     ecx, ecx
0x10018650  cmp     [edi+18h], ecx
0x10018653  setnz   cl
0x10018656  xor     eax, eax
0x10018658  cmp     dword ptr [ebp+var_5C], eax
0x1001865b  setnz   al
0x1001865e  cmp     eax, ecx
0x10018660  jz      loc_10018892
0x10018666  mov     ecx, [ebp+var_14]
0x10018669  test    edx, 4000h
0x1001866f  jnz     loc_10018721
0x10018675  mov     eax, [ebp+var_C]
0x10018678  push    edi
0x10018679  mov     edx, [eax+18h]
0x1001867c  call    CellSize
0x10018681  mov     ecx, 18h
0x10018686  mov     [ebp+var_2C], eax
0x10018689  call    _MemAllocate@4; MemAllocate(x)
0x1001868e  mov     edx, eax
0x10018690  test    edx, edx
0x10018692  jz      loc_10018B5F
0x10018698  mov     eax, [ebp+var_14]
0x1001869b  mov     [edx+8], eax
0x1001869e  mov     eax, [ebp+var_18]
0x100186a1  mov     [edx+0Ch], eax
0x100186a4  mov     eax, [ebp+var_2C]
0x100186a7  mov     [edx+10h], eax
0x100186aa  mov     eax, [ebp+var_10]
0x100186ad  mov     ecx, [eax]
0x100186af  test    ecx, ecx
0x100186b1  jnz     short loc_10018710
0x100186b3  mov     [eax], edx
0x100186b5  jmp     loc_1001888F
0x100186ba  test    dl, 8
0x100186bd  jz      short loc_100186D2
0x100186bf  test    byte ptr [edi+8], 8
0x100186c3  jz      short loc_100186D2
0x100186c5  mov     eax, dword ptr [ebp+var_5C]
0x100186c8  cmp     eax, [edi+18h]
0x100186cb  jnz     short loc_10018669
0x100186cd  jmp     loc_10018892
0x100186d2  test    edx, 2000h
0x100186d8  jz      short loc_100186F6
0x100186da  mov     eax, 2000h
0x100186df  test    [edi+8], ax
0x100186e3  jz      short loc_100186F6
0x100186e5  mov     eax, [ebp+var_64]
0x100186e8  cmp     eax, [edi+10h]
0x100186eb  jnz     loc_10018669
0x100186f1  jmp     loc_10018892
0x100186f6  test    dl, 1
0x100186f9  jz      loc_10018669
0x100186ff  test    byte ptr [edi+8], 1
0x10018703  jz      loc_10018669
0x10018709  jmp     loc_10018892
0x10018710  mov     eax, [ecx]
0x10018712  test    eax, eax
0x10018714  jz      short loc_1001871A
0x10018716  mov     ecx, eax
0x10018718  jmp     short loc_10018710
0x1001871a  mov     [ecx], edx
0x1001871c  jmp     loc_1001888F
0x10018721  lea     eax, [ebp+var_8]
0x10018724  push    eax
0x10018725  mov     eax, [ebp+var_18]
0x10018728  lea     edx, [ebp+arg_0]
0x1001872b  push    esi
0x1001872c  mov     esi, [ebp+var_C]
0x1001872f  push    eax
0x10018730  push    ecx
0x10018731  push    [ebp+var_10]
0x10018734  mov     ecx, esi
0x10018736  call    SplitMulRecord
0x1001873b  test    eax, eax
0x1001873d  jnz     loc_10018B64
0x10018743  mov     ebx, [ebp+arg_0]
0x10018746  mov     edi, ebx
0x10018748  test    edi, edi
0x1001874a  jz      loc_100188A3
0x10018750  mov     cx, [ebp+var_8]
0x10018754  nop     dword ptr [eax+00h]
0x10018758  nop     dword ptr [eax+eax+00000000h]
0x10018760  movzx   eax, byte ptr [edi+4]
0x10018764  cmp     ax, cx
0x10018767  jz      loc_10018897
0x1001876d  mov     edi, [edi]
0x1001876f  test    edi, edi
0x10018771  jnz     short loc_10018760
0x10018773  jmp     loc_10018897
0x10018778  test    [ebp+var_6C], 4000h
0x1001877f  jnz     short loc_100187CE
0x10018781  mov     ecx, 18h
0x10018786  call    _MemAllocate@4; MemAllocate(x)
0x1001878b  mov     edx, eax
0x1001878d  test    edx, edx
0x1001878f  jz      loc_10018B5F
0x10018795  mov     eax, [ebp+var_14]
0x10018798  mov     [edx+8], eax
0x1001879b  mov     eax, [ebp+var_18]
0x1001879e  mov     [edx+0Ch], eax
0x100187a1  mov     eax, [ebp+var_10]
0x100187a4  mov     dword ptr [edx+10h], 0
0x100187ab  mov     ecx, [eax]
0x100187ad  test    ecx, ecx
0x100187af  jnz     short loc_100187C0
0x100187b1  mov     [eax], edx
0x100187b3  jmp     loc_1001888F
0x100187c0  mov     eax, [ecx]
0x100187c2  test    eax, eax
0x100187c4  jz      loc_1001871A
0x100187ca  mov     ecx, eax
0x100187cc  jmp     short loc_100187C0
0x100187ce  lea     edx, [ebp+var_8]
0x100187d1  push    edx
0x100187d2  push    esi
0x100187d3  mov     esi, [ebp+var_C]
0x100187d6  lea     edx, [ebp+arg_0]
0x100187d9  push    eax
0x100187da  push    ecx
0x100187db  push    [ebp+var_10]
0x100187de  mov     ecx, esi
0x100187e0  call    SplitMulRecord
0x100187e5  test    eax, eax
0x100187e7  jnz     loc_10018B64
0x100187ed  mov     ebx, [ebp+arg_0]
0x100187f0  mov     edi, ebx
0x100187f2  test    edi, edi
0x100187f4  jz      loc_100188A3
0x100187fa  mov     cx, [ebp+var_8]
0x100187fe  mov     edi, edi
0x10018800  movzx   eax, byte ptr [edi+4]
0x10018804  cmp     ax, cx
0x10018807  jz      loc_10018897
0x1001880d  mov     edi, [edi]
0x1001880f  test    edi, edi
0x10018811  jnz     short loc_10018800
0x10018813  jmp     loc_10018897
0x10018818  mov     eax, 800h
0x1001881d  test    [edi+8], ax
0x10018821  jnz     short loc_10018892
0x10018823  mov     ecx, [ebp+var_C]
0x10018826  lea     edx, [ebp+var_30]
0x10018829  push    esi
0x1001882a  call    LocateSpotForNewCell
0x1001882f  test    eax, eax
0x10018831  jnz     loc_10018B64
0x10018837  mov     eax, [ebp+var_C]
0x1001883a  push    edi
0x1001883b  mov     edx, [eax+18h]
0x1001883e  call    CellSize
0x10018843  mov     ecx, 18h
0x10018848  mov     [ebp+var_2C], eax
0x1001884b  call    _MemAllocate@4; MemAllocate(x)
0x10018850  mov     edx, eax
0x10018852  test    edx, edx
0x10018854  jz      loc_10018B5F
0x1001885a  mov     eax, [ebp+var_2C]
0x1001885d  mov     ecx, [ebp+var_30]
0x10018860  mov     [edx+10h], eax
0x10018863  mov     eax, [ebp+var_10]
0x10018866  mov     [edx+8], ecx
0x10018869  mov     dword ptr [edx+0Ch], 0
0x10018870  mov     ecx, [eax]
0x10018872  test    ecx, ecx
0x10018874  jnz     short loc_10018880
0x10018876  mov     [eax], edx
0x10018878  jmp     short loc_1001888C
0x10018880  mov     eax, [ecx]
0x10018882  test    eax, eax
0x10018884  jz      short loc_1001888A
0x10018886  mov     ecx, eax
0x10018888  jmp     short loc_10018880
0x1001888a  mov     [ecx], edx
0x1001888c  inc     [ebp+var_20]
0x1001888f  mov     [edx+14h], esi
0x10018892  mov     esi, [ebp+var_C]
0x10018895  mov     edi, [edi]
0x10018897  test    edi, edi
0x10018899  jz      short loc_100188A3
0x1001889b  mov     ecx, [ebp+var_34]
0x1001889e  jmp     loc_100185B1
0x100188a3  cmp     [ebp+var_1C], 0
0x100188a7  jnz     short loc_10018912
0x100188a9  mov     eax, [ebp+var_20]
0x100188ac  test    eax, eax
0x100188ae  jle     short loc_10018912
0x100188b0  mov     ecx, ebx
0x100188b2  mov     edi, 800h
0x100188b7  test    ecx, ecx
0x100188b9  jz      short loc_100188CC
0x100188bb  nop     dword ptr [eax+eax+00h]
0x100188c0  test    [ecx+8], di
0x100188c4  jz      short loc_100188CC
0x100188c6  mov     ecx, [ecx]
0x100188c8  test    ecx, ecx
0x100188ca  jnz     short loc_100188C0
0x100188cc  movzx   eax, byte ptr [ecx+4]
0x100188d0  mov     ecx, [ecx]
0x100188d2  inc     ax
0x100188d4  movzx   edx, ax
0x100188d7  test    ecx, ecx
0x100188d9  jz      short loc_100188F6
0x100188db  nop     dword ptr [eax+eax+00h]
0x100188e0  test    [ecx+8], di
0x100188e4  jnz     short loc_100188F0
0x100188e6  movzx   eax, byte ptr [ecx+4]
0x100188ea  cmp     ax, dx
0x100188ed  jnz     short loc_10018912
0x100188ef  inc     edx
0x100188f0  mov     ecx, [ecx]
0x100188f2  test    ecx, ecx
0x100188f4  jnz     short loc_100188E0
0x100188f6  mov     ecx, [ebp+var_10]
0x100188f9  call    ModifyListDestroy
0x100188fe  mov     edx, [ebp+var_24]
  ... truncated ...
```
