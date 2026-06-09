# ExcelReadCell(x,x,x)

- ea: `0x10013490`
- end: `0x10013ae3`
- name: `_ExcelReadCell@12`
- size: `1619`
- prototype: `int __fastcall(int, __int16 *, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x10017b00`
- `0x10018550`
- `0x1001bc80`
- `0x1001bd50`

## callees

- `0x10009aa0`
- `0x1000dc30`
- `0x1000dcc0`
- `0x1000df70`
- `0x1000e440`
- `0x1000eec0`
- `0x1000fa90`
- `0x1000fb30`
- `0x1000fbf0`
- `0x1000fd50`
- `0x10013490`
- `0x1002580a`
- `0x10025ab7`
- `0x10025f86`
- `0x1002ec67`
- `0x1003669c`

## pseudocode

```c
int __fastcall ExcelReadCell(int a1, __int16 *a2, int a3)
{
  int v5; // esi
  int result; // eax
  int *v7; // esi
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // esi
  int v14; // edx
  int v15; // esi
  __int16 v16; // si
  int v17; // esi
  int v18; // ecx
  int v19; // edx
  unsigned __int16 v20; // dx
  int v21; // esi
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  int v25; // ecx
  double v26; // xmm0_8
  _DWORD *v27; // eax
  unsigned int String; // eax
  WCHAR *v29; // esi
  int v30; // ecx
  const CHAR *v31; // esi
  __int16 v32; // cx
  __int16 v33; // cx
  bool v34; // zf
  __int16 v35; // cx
  int v36; // eax
  void *v37; // eax
  int v38; // eax
  int v39; // ebx
  _DWORD *v40; // ecx
  int v41; // eax
  size_t Size[4]; // [esp+Ch] [ebp-68h] BYREF
  void *Src; // [esp+1Ch] [ebp-58h]
  double v44; // [esp+20h] [ebp-54h] BYREF
  int v45; // [esp+2Ch] [ebp-48h] BYREF
  __int64 v46; // [esp+30h] [ebp-44h] BYREF
  int v47; // [esp+3Ch] [ebp-38h]
  int v48; // [esp+40h] [ebp-34h]
  int v49; // [esp+44h] [ebp-30h]
  int v50; // [esp+48h] [ebp-2Ch]
  int v51; // [esp+4Ch] [ebp-28h]
  int v52; // [esp+50h] [ebp-24h]
  int v53; // [esp+54h] [ebp-20h]
  int v54; // [esp+58h] [ebp-1Ch]
  int v55; // [esp+5Ch] [ebp-18h] BYREF
  int v56; // [esp+60h] [ebp-14h] BYREF
  int v57; // [esp+64h] [ebp-10h] BYREF
  int v58; // [esp+68h] [ebp-Ch]
  int v59; // [esp+6Ch] [ebp-8h] BYREF

  v58 = a1;
  v5 = *(_DWORD *)(a1 + 48);
  if ( *(_DWORD *)(*(_DWORD *)(a1 + 44) + 40) )
    return ExcelMIReadCell(a3, a2);
  *a2 = 0;
  v7 = *(int **)(v5 + 40);
  if ( !v7 )
    return -11;
  v8 = *(_DWORD *)(a1 + 44);
  if ( *(_DWORD *)(v8 + 104) == *(_DWORD *)(a1 + 48)
    && (_WORD)a3 == *(_WORD *)(v8 + 96)
    && HIWORD(a3) >= *(_WORD *)(v8 + 98) )
  {
    v9 = *(_DWORD *)(v8 + 100);
  }
  else
  {
    v10 = *v7;
    if ( (unsigned __int16)a3 < *v7 )
      return 2;
    if ( (unsigned __int16)a3 >= v7[1] )
      return 2;
    v55 = 32;
    v11 = ((unsigned __int16)a3 - v10) / 32;
    v12 = ((unsigned __int16)a3 - v10) % 32;
    v13 = v7[v11 + 4];
    if ( !v13 )
      return 2;
    v14 = 5 * v12;
    if ( *(_DWORD *)(v13 + 4 * v14 + 20) == -1 )
      return 2;
    v55 = HIWORD(a3);
    if ( HIWORD(a3) < *(__int16 *)(v13 + 4 * v14 + 8) || v55 >= *(__int16 *)(v13 + 4 * v14 + 10) )
      return 2;
    v9 = *(_DWORD *)(v13 + 4 * v14 + 20) + *(_DWORD *)(v8 + 60);
  }
  v15 = v58;
  BFSetFilePosition(*(int **)(v58 + 20), 0, v9);
  *(_DWORD *)(*(_DWORD *)(v58 + 44) + 88) = *(_DWORD *)(*(_DWORD *)(v58 + 20) + 8)
                                          + *(_DWORD *)(*(_DWORD *)(v58 + 20) + 84)
                                          - *(_DWORD *)(*(_DWORD *)(v58 + 20) + 4);
  if ( ExcelReadRecordHeader(*(_DWORD *)(v15 + 44), &v56) )
    return -10;
  v54 = 516;
  v53 = 638;
  v52 = 515;
  v51 = 189;
  v50 = 190;
  v49 = 513;
  v48 = 517;
  v47 = 214;
  HIDWORD(v46) = 253;
  v45 = 518;
  HIDWORD(v44) = 1030;
  while ( 1 )
  {
    v16 = v56;
    v55 = 0;
    if ( (_WORD)v56 != (_WORD)v54
      && (_WORD)v56 != (_WORD)v53
      && (_WORD)v56 != (_WORD)v52
      && (_WORD)v56 != (_WORD)v51
      && (_WORD)v56 != (_WORD)v50
      && (_WORD)v56 != (_WORD)v49
      && (_WORD)v56 != (_WORD)v48
      && (_WORD)v56 != (_WORD)v47
      && (_WORD)v56 != WORD2(v46)
      && (_WORD)v56 != (_WORD)v45
      && (_WORD)v56 != WORD2(v44)
      && (_WORD)v56 != 6 )
    {
      if ( (_WORD)v56 == 519 )
        goto LABEL_44;
      if ( (_WORD)v56 != 545 && (_WORD)v56 != 1212 )
        return 2;
    }
    if ( (_WORD)v56 == 519 || (_WORD)v56 == 545 || (_WORD)v56 == 1212 )
      goto LABEL_44;
    result = PeekAtRowCol((char *)&v57 + 2);
    if ( result )
      return result;
    if ( (unsigned __int16)v57 > (unsigned __int16)a3 || (_WORD)v57 == (_WORD)a3 && HIWORD(v57) > HIWORD(a3) )
      return 2;
    if ( v16 != 189 && v16 != 190 )
      break;
    v19 = ExcelReadTotalRecord(*(_DWORD *)(v58 + 44), &v56, &v55);
    v59 = v19;
    if ( v19 )
      return v19;
    v20 = HIWORD(v57);
    if ( HIWORD(a3) >= HIWORD(v57) )
    {
      v21 = v55;
      if ( HIWORD(a3) <= *(__int16 *)(SHIWORD(v56) + v55 - 2) )
      {
        *a2 |= 0x4000u;
        goto LABEL_50;
      }
    }
LABEL_54:
    *(_DWORD *)(*(_DWORD *)(v58 + 44) + 88) = *(_DWORD *)(*(_DWORD *)(v58 + 20) + 8)
                                            + *(_DWORD *)(*(_DWORD *)(v58 + 20) + 84)
                                            - *(_DWORD *)(*(_DWORD *)(v58 + 20) + 4);
    if ( ExcelReadRecordHeader(*(_DWORD *)(v58 + 44), &v56) )
      return -10;
  }
  if ( v57 != a3 )
  {
LABEL_44:
    v17 = *(_DWORD *)(v58 + 44);
    v18 = *(_DWORD *)(v17 + 40);
    if ( v18 )
      *(_DWORD *)(v18 + 8) = **(_DWORD **)(v18 + 8);
    else
      BFSetFilePosition(*(int **)(v17 + 20), 1, SHIWORD(v56));
    goto LABEL_54;
  }
  v23 = ExcelReadTotalRecord(*(_DWORD *)(v58 + 44), &v56, &v55);
  v19 = v23;
  v59 = v23;
  if ( !v23 )
  {
    v21 = v55;
    v20 = HIWORD(v57);
    *((_DWORD *)a2 + 1) = *(__int16 *)(v55 + 4);
LABEL_50:
    v22 = v56;
    HIDWORD(v44) = (__int16)v56;
    if ( (__int16)v56 <= 513 )
    {
      if ( (__int16)v56 != 513 )
      {
        switch ( (__int16)v56 )
        {
          case 6:
            goto LABEL_94;
          case 189:
            *a2 |= 0x2002u;
            v24 = 3 * (__int16)(HIWORD(a3) - *(_WORD *)(v21 + 2));
            *((_DWORD *)a2 + 1) = *(__int16 *)(v21 + 6 * (__int16)(HIWORD(a3) - *(_WORD *)(v21 + 2)) + 4);
            v25 = *(_DWORD *)(v21 + 2 * v24 + 6);
            if ( (v25 & 3) == 2 )
            {
              *((_DWORD *)a2 + 2) = v25;
              *((double *)a2 + 2) = (double)(v25 >> 2);
            }
            else
            {
              if ( (v25 & 2) != 0 )
              {
                v26 = (double)(v25 >> 2);
              }
              else
              {
                LODWORD(v44) = 0;
                HIDWORD(v44) = v25 & 0xFFFFFFFC;
                v26 = v44;
              }
              if ( (v25 & 1) != 0 )
                v26 = v26 / 100.0;
              *((_DWORD *)a2 + 2) = v25;
              *((double *)a2 + 2) = v26;
            }
            goto LABEL_99;
          case 190:
            *a2 |= 1u;
            *((_DWORD *)a2 + 1) = *(__int16 *)(v21 + 2 * (HIWORD(a3) - v20) + 4);
            goto LABEL_99;
          case 214:
          case 253:
            goto LABEL_72;
          default:
            goto LABEL_99;
        }
      }
      *a2 |= 1u;
      goto LABEL_99;
    }
    if ( (__int16)v56 > 638 )
    {
      if ( (__int16)v56 != 1030 )
        goto LABEL_99;
LABEL_94:
      *a2 |= 0x100u;
      v19 = ParseFormulaRecord(v22, &v57, &v56, Size, 0, &v59);
      if ( !v19 )
      {
        v37 = (void *)MemAllocate(Size[0]);
        v55 = (int)v37;
        if ( v37 )
        {
          memcpy(v37, Src, Size[0]);
          Size[1] = (unsigned __int16)v59;
          v38 = v55;
          *(_OWORD *)(a2 + 12) = *(_OWORD *)Size;
          *((_DWORD *)a2 + 10) = v38;
          v59 = FormulaCurrentValue(a2, 3);
          if ( v59 )
          {
            MemFree(v55);
            *((_DWORD *)a2 + 6) = 0;
            *((_DWORD *)a2 + 10) = 0;
          }
          goto LABEL_99;
        }
        v19 = -2;
      }
    }
    else if ( (__int16)v56 == 638 )
    {
      *a2 |= 0x2002u;
      v36 = ParseRKRecord(&v56, (char *)&v44 + 4, &v46, &v45);
      v34 = HIDWORD(v44) == 0;
      v19 = v59;
      *((_DWORD *)a2 + 2) = v36;
      if ( v34 )
        *((_QWORD *)a2 + 2) = v46;
      else
        *((double *)a2 + 2) = (double)v45;
    }
    else
    {
      switch ( (__int16)v56 )
      {
        case 515:
          *a2 |= 2u;
          *((_QWORD *)a2 + 2) = *(_QWORD *)(v21 + 6);
          break;
        case 516:
LABEL_72:
          v56 = 0;
          v27 = *(_DWORD **)(v58 + 44);
          v55 = (int)v27;
          if ( *v27 == 1 )
          {
            v27 = (_DWORD *)v27[11];
            v55 = (int)v27;
          }
          v57 = 0;
          if ( HIDWORD(v44) == 253 )
          {
            if ( !v27[18] || GetStringPoolEntry(&v45, (char *)&v44 + 4, &v56) )
              goto LABEL_83;
            String = HIDWORD(v44);
            v29 = (WCHAR *)v45;
          }
          else
          {
            v30 = *(__int16 *)(v21 + 6);
            v31 = (const CHAR *)(v21 + 8);
            if ( !v30 || !*v31 )
              goto LABEL_83;
            String = ExcelExtractString(v27[1], v27[6], (__m128i *)&ExcelRecordTextBuffer, 512, v31, v30);
            v29 = &ExcelRecordTextBuffer;
          }
          v57 = TextStoragePut(*(_DWORD *)(v55 + 16), String >> 1, 1);
          if ( v56 )
            MemFree(v29);
LABEL_83:
          v32 = *a2;
          if ( v57 )
          {
            v33 = v32 | 0x10;
            *((_DWORD *)a2 + 4) = v57;
          }
          else
          {
            v33 = v32 | 1;
          }
          *a2 = v33;
          break;
        case 517:
          ParseBoolerrRecord(&v56, &v55, (char *)&v44 + 4);
          v34 = HIDWORD(v44) == 1;
          v35 = *a2;
          *((_DWORD *)a2 + 4) = v55;
          if ( v34 )
            *a2 = v35 | 4;
          else
            *a2 = v35 | 8;
          break;
        case 518:
          goto LABEL_94;
        default:
          break;
      }
LABEL_99:
      v19 = v59;
    }
    v39 = v58;
    v40 = *(_DWORD **)(v58 + 44);
    v41 = v40[22];
    v40[24] = a3;
    v40[25] = v41;
    v40[26] = *(_DWORD *)(v39 + 48);
  }
  return v19;
}

```

## disassembly

```asm
0x10013490  mov     edi, edi
0x10013492  push    ebp
0x10013493  mov     ebp, esp
0x10013495  sub     esp, 68h
0x10013498  push    ebx
0x10013499  mov     ebx, edx
0x1001349b  mov     edx, ecx
0x1001349d  push    esi
0x1001349e  push    edi
0x1001349f  mov     [ebp+var_C], edx
0x100134a2  mov     eax, [edx+2Ch]
0x100134a5  mov     esi, [edx+30h]
0x100134a8  mov     ecx, [eax+28h]
0x100134ab  test    ecx, ecx
0x100134ad  jz      short loc_100134C4
0x100134af  mov     edx, [esi+14h]
0x100134b2  push    ebx; void *
0x100134b3  push    [ebp+arg_0]; int
0x100134b6  call    _ExcelMIReadCell@16; ExcelMIReadCell(x,x,x,x)
0x100134bb  pop     edi
0x100134bc  pop     esi
0x100134bd  pop     ebx
0x100134be  mov     esp, ebp
0x100134c0  pop     ebp
0x100134c1  retn    4
0x100134c4  xor     eax, eax
0x100134c6  mov     [ebx], ax
0x100134c9  mov     esi, [esi+28h]
0x100134cc  test    esi, esi
0x100134ce  jnz     short loc_100134DC
0x100134d0  lea     eax, [esi-0Bh]
0x100134d3  pop     edi
0x100134d4  pop     esi
0x100134d5  pop     ebx
0x100134d6  mov     esp, ebp
0x100134d8  pop     ebp
0x100134d9  retn    4
0x100134dc  mov     ecx, [edx+2Ch]
0x100134df  mov     edi, [ebp+arg_0]
0x100134e2  mov     eax, [ecx+68h]
0x100134e5  cmp     eax, [edx+30h]
0x100134e8  mov     ax, word ptr [ebp+arg_0+2]
0x100134ec  jnz     short loc_100134FF
0x100134ee  cmp     di, [ecx+60h]
0x100134f2  jnz     short loc_100134FF
0x100134f4  cmp     ax, [ecx+62h]
0x100134f8  jb      short loc_100134FF
0x100134fa  mov     eax, [ecx+64h]
0x100134fd  jmp     short loc_10013566
0x100134ff  mov     edx, [esi]
0x10013501  movzx   eax, di
0x10013504  cmp     eax, edx
0x10013506  jl      loc_10013AD5
0x1001350c  cmp     eax, [esi+4]
0x1001350f  jge     loc_10013AD5
0x10013515  sub     eax, edx
0x10013517  mov     [ebp+var_18], 20h ; ' '
0x1001351e  cdq
0x1001351f  idiv    [ebp+var_18]
0x10013522  mov     esi, [esi+eax*4+10h]
0x10013526  test    esi, esi
0x10013528  jz      loc_10013AD5
0x1001352e  lea     edx, [edx+edx*4]
0x10013531  cmp     dword ptr [esi+edx*4+14h], 0FFFFFFFFh
0x10013536  jz      loc_10013AD5
0x1001353c  movzx   eax, word ptr [ebp+arg_0+2]
0x10013540  mov     [ebp+var_18], eax
0x10013543  movsx   eax, word ptr [esi+edx*4+8]
0x10013548  cmp     [ebp+var_18], eax
0x1001354b  jl      loc_10013AD5
0x10013551  movsx   eax, word ptr [esi+edx*4+0Ah]
0x10013556  cmp     [ebp+var_18], eax
0x10013559  jge     loc_10013AD5
0x1001355f  mov     eax, [ecx+3Ch]
0x10013562  add     eax, [esi+edx*4+14h]
0x10013566  mov     esi, [ebp+var_C]
0x10013569  xor     edx, edx
0x1001356b  push    eax
0x1001356c  mov     ecx, [esi+14h]
0x1001356f  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10013574  mov     eax, [esi+14h]
0x10013577  lea     edx, [ebp+var_14]
0x1001357a  mov     ecx, [eax+54h]
0x1001357d  sub     ecx, [eax+4]
0x10013580  add     ecx, [eax+8]
0x10013583  mov     eax, [esi+2Ch]
0x10013586  mov     [eax+58h], ecx
0x10013589  mov     ecx, [esi+2Ch]
0x1001358c  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10013591  test    eax, eax
0x10013593  jnz     loc_1001379D
0x10013599  mov     [ebp+var_1C], 204h
0x100135a0  mov     [ebp+var_20], 27Eh
0x100135a7  mov     [ebp+var_24], 203h
0x100135ae  mov     [ebp+var_28], 0BDh
0x100135b5  mov     [ebp+var_2C], 0BEh
0x100135bc  mov     [ebp+var_30], 201h
0x100135c3  mov     [ebp+var_34], 205h
0x100135ca  mov     [ebp+var_38], 0D6h
0x100135d1  mov     dword ptr [ebp+var_44+4], 0FDh
0x100135d8  mov     [ebp+var_48], 206h
0x100135df  mov     dword ptr [ebp+var_54+4], 406h
0x100135e6  mov     esi, [ebp+var_14]
0x100135e9  mov     ecx, 221h
0x100135ee  mov     edx, 4BCh
0x100135f3  mov     [ebp+var_18], 0
0x100135fa  lea     eax, [ecx-1Ah]
0x100135fd  cmp     si, word ptr [ebp+var_1C]
0x10013601  jz      short loc_10013658
0x10013603  cmp     si, word ptr [ebp+var_20]
0x10013607  jz      short loc_10013658
0x10013609  cmp     si, word ptr [ebp+var_24]
0x1001360d  jz      short loc_10013658
0x1001360f  cmp     si, word ptr [ebp+var_28]
0x10013613  jz      short loc_10013658
0x10013615  cmp     si, word ptr [ebp+var_2C]
0x10013619  jz      short loc_10013658
0x1001361b  cmp     si, word ptr [ebp+var_30]
0x1001361f  jz      short loc_10013658
0x10013621  cmp     si, word ptr [ebp+var_34]
0x10013625  jz      short loc_10013658
0x10013627  cmp     si, word ptr [ebp+var_38]
0x1001362b  jz      short loc_10013658
0x1001362d  cmp     si, word ptr [ebp+var_44+4]
0x10013631  jz      short loc_10013658
0x10013633  cmp     si, word ptr [ebp+var_48]
0x10013637  jz      short loc_10013658
0x10013639  cmp     si, word ptr [ebp+var_54+4]
0x1001363d  jz      short loc_10013658
0x1001363f  cmp     si, 6
0x10013643  jz      short loc_10013658
0x10013645  cmp     si, ax
0x10013648  jz      short loc_100136C0
0x1001364a  cmp     si, cx
0x1001364d  jz      short loc_10013658
0x1001364f  cmp     si, dx
0x10013652  jnz     loc_10013AD5
0x10013658  cmp     si, ax
0x1001365b  jz      short loc_100136C0
0x1001365d  cmp     si, cx
0x10013660  jz      short loc_100136C0
0x10013662  cmp     si, dx
0x10013665  jz      short loc_100136C0
0x10013667  mov     ecx, [ebp+var_C]
0x1001366a  lea     eax, [ebp+var_10+2]
0x1001366d  push    eax
0x1001366e  lea     edx, [ebp+var_10]
0x10013671  mov     ecx, [ecx+2Ch]
0x10013674  call    PeekAtRowCol
0x10013679  test    eax, eax
0x1001367b  jnz     loc_10013ADA
0x10013681  mov     eax, [ebp+var_10]
0x10013684  cmp     ax, di
0x10013687  ja      loc_10013AD5
0x1001368d  mov     cx, word ptr [ebp+var_10+2]
0x10013691  jnz     short loc_1001369D
0x10013693  cmp     cx, word ptr [ebp+arg_0+2]
0x10013697  ja      loc_10013AD5
0x1001369d  mov     edx, 0BDh
0x100136a2  cmp     si, dx
0x100136a5  jz      short loc_100136DE
0x100136a7  mov     edx, 0BEh
0x100136ac  cmp     si, dx
0x100136af  jz      short loc_100136DE
0x100136b1  cmp     cx, word ptr [ebp+arg_0+2]
0x100136b5  jnz     short loc_100136C0
0x100136b7  cmp     ax, di
0x100136ba  jz      loc_100137AB
0x100136c0  mov     eax, [ebp+var_C]
0x100136c3  mov     esi, [eax+2Ch]
0x100136c6  mov     ecx, [esi+28h]
0x100136c9  test    ecx, ecx
0x100136cb  jz      loc_1001375D
0x100136d1  mov     eax, [ecx+8]
0x100136d4  mov     eax, [eax]
0x100136d6  mov     [ecx+8], eax
0x100136d9  jmp     loc_1001376F
0x100136de  lea     eax, [ebp+var_18]
0x100136e1  push    eax
0x100136e2  mov     eax, [ebp+var_C]
0x100136e5  lea     edx, [ebp+var_14]
0x100136e8  mov     ecx, [eax+2Ch]
0x100136eb  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100136f0  mov     edx, eax
0x100136f2  mov     [ebp+var_8], edx
0x100136f5  test    edx, edx
0x100136f7  jnz     loc_10013ACA
0x100136fd  mov     dx, word ptr [ebp+var_10+2]
0x10013701  mov     ax, word ptr [ebp+arg_0+2]
0x10013705  cmp     ax, dx
0x10013708  jb      short loc_1001376F
0x1001370a  movsx   ecx, word ptr [ebp+var_14+2]
0x1001370e  mov     esi, [ebp+var_18]
0x10013711  movzx   eax, ax
0x10013714  movsx   ecx, word ptr [ecx+esi-2]
0x10013719  cmp     eax, ecx
0x1001371b  jg      short loc_1001376F
0x1001371d  mov     eax, 4000h
0x10013722  or      [ebx], ax
0x10013725  mov     eax, [ebp+var_14]
0x10013728  movsx   ecx, ax
0x1001372b  mov     dword ptr [ebp+var_54+4], ecx
0x1001372e  cmp     ecx, 201h
0x10013734  jg      loc_10013880
0x1001373a  jz      loc_10013877
0x10013740  sub     ecx, 6; switch 248 cases
0x10013743  cmp     ecx, 0F7h
0x10013749  ja      def_10013756; jumptable 10013756 default case, cases 7-188,191-213,215-252
0x1001374f  movzx   ecx, ds:byte_10013AF8[ecx]
0x10013756  jmp     ds:jpt_10013756[ecx*4]; switch jump
0x1001375d  movsx   eax, word ptr [ebp+var_14+2]
0x10013761  mov     edx, 1
0x10013766  mov     ecx, [esi+14h]
0x10013769  push    eax
0x1001376a  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1001376f  mov     eax, [ebp+var_C]
0x10013772  lea     edx, [ebp+var_14]
0x10013775  mov     eax, [eax+14h]
0x10013778  mov     ecx, [eax+54h]
0x1001377b  sub     ecx, [eax+4]
0x1001377e  add     ecx, [eax+8]
0x10013781  mov     eax, [ebp+var_C]
0x10013784  mov     eax, [eax+2Ch]
0x10013787  mov     [eax+58h], ecx
0x1001378a  mov     eax, [ebp+var_C]
0x1001378d  mov     ecx, [eax+2Ch]
0x10013790  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10013795  test    eax, eax
0x10013797  jz      loc_100135E6
0x1001379d  mov     eax, 0FFFFFFF6h
0x100137a2  pop     edi
0x100137a3  pop     esi
0x100137a4  pop     ebx
0x100137a5  mov     esp, ebp
0x100137a7  pop     ebp
0x100137a8  retn    4
0x100137ab  lea     eax, [ebp+var_18]
0x100137ae  push    eax
0x100137af  mov     eax, [ebp+var_C]
0x100137b2  lea     edx, [ebp+var_14]
0x100137b5  mov     ecx, [eax+2Ch]
0x100137b8  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100137bd  mov     edx, eax
0x100137bf  mov     [ebp+var_8], eax
0x100137c2  test    edx, edx
0x100137c4  jnz     loc_10013ACA
0x100137ca  mov     esi, [ebp+var_18]
0x100137cd  mov     dx, word ptr [ebp+var_10+2]
0x100137d1  movsx   eax, word ptr [esi+4]
0x100137d5  mov     [ebx+4], eax
0x100137d8  jmp     loc_10013725
0x100137dd  mov     eax, 2002h; jumptable 10013756 case 189
0x100137e2  or      [ebx], ax
0x100137e5  mov     ax, word ptr [ebp+arg_0+2]
0x100137e9  sub     ax, [esi+2]
0x100137ed  cwde
0x100137ee  lea     ecx, [eax+eax*2]
0x100137f1  movsx   eax, word ptr [esi+ecx*2+4]
0x100137f6  mov     [ebx+4], eax
0x100137f9  mov     ecx, [esi+ecx*2+6]
0x100137fd  mov     eax, ecx
0x100137ff  and     al, 3
0x10013801  cmp     al, 2
0x10013803  mov     eax, ecx
0x10013805  jnz     short loc_1001381F
0x10013807  sar     eax, 2
0x1001380a  mov     [ebx+8], ecx
0x1001380d  movd    xmm0, eax
0x10013811  cvtdq2pd xmm0, xmm0
0x10013815  movsd   qword ptr [ebx+10h], xmm0
0x1001381a  jmp     def_10013756; jumptable 10013756 default case, cases 7-188,191-213,215-252
0x1001381f  test    cl, 2
0x10013822  jz      short loc_10013831
0x10013824  sar     eax, 2
0x10013827  movd    xmm0, eax
0x1001382b  cvtdq2pd xmm0, xmm0
0x1001382f  jmp     short loc_10013843
0x10013831  and     eax, 0FFFFFFFCh
0x10013834  mov     dword ptr [ebp+var_54], 0
0x1001383b  mov     dword ptr [ebp+var_54+4], eax
0x1001383e  movsd   xmm0, [ebp+var_54]
0x10013843  test    cl, 1
0x10013846  jz      short loc_10013850
0x10013848  divsd   xmm0, ds:__real@4059000000000000
0x10013850  mov     [ebx+8], ecx
0x10013853  movsd   qword ptr [ebx+10h], xmm0
0x10013858  jmp     def_10013756; jumptable 10013756 default case, cases 7-188,191-213,215-252
0x1001385d  or      word ptr [ebx], 1; jumptable 10013756 case 190
0x10013861  movzx   ecx, word ptr [ebp+arg_0+2]
0x10013865  movzx   eax, dx
0x10013868  sub     ecx, eax
0x1001386a  movsx   eax, word ptr [esi+ecx*2+4]
0x1001386f  mov     [ebx+4], eax
0x10013872  jmp     def_10013756; jumptable 10013756 default case, cases 7-188,191-213,215-252
0x10013877  or      word ptr [ebx], 1
0x1001387b  jmp     def_10013756; jumptable 10013756 default case, cases 7-188,191-213,215-252
0x10013880  cmp     ecx, 27Eh
0x10013886  jg      loc_10013A16
0x1001388c  jz      loc_100139C6
0x10013892  sub     ecx, 203h; switch 4 cases
  ... truncated ...
```
