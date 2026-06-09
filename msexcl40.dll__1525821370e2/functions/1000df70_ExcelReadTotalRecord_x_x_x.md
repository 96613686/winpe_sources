# ExcelReadTotalRecord(x,x,x)

- ea: `0x1000df70`
- end: `0x1000e3f3`
- name: `_ExcelReadTotalRecord@12`
- size: `1155`
- prototype: `int __fastcall(int, _WORD *, _DWORD *)`
- caller_count: `12`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10007a00`
- `0x1000fbf0`
- `0x1000fdf0`
- `0x100102c0`
- `0x10010790`
- `0x10011a70`
- `0x10012270`
- `0x10013490`
- `0x10013d10`
- `0x10016240`
- `0x100163d0`
- `0x100181b0`

## callees

- `0x1000dee0`
- `0x1000df70`
- `0x1002580a`
- `0x10025986`
- `0x10025ab7`
- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x10025ed1`
- `0x10025f86`
- `0x1003669c`

## pseudocode

```c
int __fastcall ExcelReadTotalRecord(int a1, _WORD *a2, _DWORD *a3)
{
  bool v4; // zf
  __int16 *v5; // esi
  int result; // eax
  int v7; // edi
  size_t v8; // ebx
  void *v9; // esi
  int v10; // edi
  __int16 v11; // ax
  int v12; // esi
  size_t *v13; // ebx
  int *v14; // ecx
  int v15; // eax
  char *v16; // esi
  int FileBlock; // eax
  size_t v18; // edi
  const void *v19; // esi
  size_t *v20; // ebx
  size_t v21; // edx
  int v22; // ecx
  size_t v23; // esi
  size_t v24; // edi
  const void *v25; // esi
  int v26; // edx
  char *v27; // esi
  int v28; // edi
  signed int v29; // ebx
  char *v30; // eax
  char *v31; // edx
  signed int v32; // ebx
  void *v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // [esp+Ch] [ebp-28h] BYREF
  __int16 v37; // [esp+10h] [ebp-24h]
  int v38; // [esp+14h] [ebp-20h]
  char *v39; // [esp+18h] [ebp-1Ch]
  _WORD *v40; // [esp+1Ch] [ebp-18h]
  _WORD *v41; // [esp+20h] [ebp-14h]
  int v42; // [esp+24h] [ebp-10h] BYREF
  int v43; // [esp+28h] [ebp-Ch] BYREF
  int v44; // [esp+2Ch] [ebp-8h]
  int v45; // [esp+30h] [ebp-4h]

  v45 = a1;
  v40 = a2;
  v4 = *a2 == 0;
  v5 = a2 + 1;
  v41 = a2 + 1;
  if ( v4 )
  {
    if ( *v5 )
      return -10;
  }
  else
  {
    v41 = a2 + 1;
  }
  v7 = *(_DWORD *)(a1 + 40);
  if ( v7 )
  {
    v8 = *(__int16 *)(*(_DWORD *)(v7 + 8) + 6);
    if ( v8 <= g_cbCurrentSize )
    {
      v9 = pExcelRecordBuffer;
    }
    else
    {
      v9 = (void *)MemReAllocate(pExcelRecordBuffer);
      pExcelRecordBuffer = v9;
      if ( !v9 )
      {
        g_cbCurrentSize = 0;
        return -2;
      }
      g_cbCurrentSize = v8;
    }
    memcpy(v9, (const void *)(*(_DWORD *)(v7 + 8) + 8), *(__int16 *)(*(_DWORD *)(v7 + 8) + 6));
    *a3 = v9;
    *(_DWORD *)(v7 + 8) = **(_DWORD **)(v7 + 8);
    return 0;
  }
  else
  {
    v4 = *v5 == 0;
    dword_1003A77C = 0;
    if ( v4 )
    {
      *a3 = 0;
      return 0;
    }
    v10 = a1;
    result = ExcelReadBufferedRecord(a3);
    if ( !result )
    {
      v11 = *a2;
      if ( *a2 != 545
        && v11 != 28
        && v11 != 127
        && v11 != 547
        && v11 != 35
        && v11 != 93
        && v11 != 536
        && v11 != 24
        && v11 != 519
        && v11 != 518
        && v11 != 1030
        && v11 != 6
        && v11 != 438
        || *v5 < 1024 && v11 != 438 )
      {
        *(_DWORD *)(v10 + 92) = *v5 + 4;
        return 0;
      }
      v12 = *v5;
      while ( 1 )
      {
        v13 = *(size_t **)(v10 + 20);
        v44 = v12;
        v14 = (int *)v13[2];
        if ( *v13 + v13[1] - (_DWORD)v14 < 4 )
        {
          v16 = (char *)v14 + v13[21] - v13[1];
          if ( v13[23] == 1 )
          {
            FileBlock = WriteFileBlock(v13);
            if ( FileBlock < 0 )
              goto LABEL_85;
          }
          v13[20] = (size_t)v16;
          OSSetFilePosition(v13, 0, v16);
          FileBlock = ReadFileBlock(v13);
          if ( FileBlock < 0 )
            goto LABEL_85;
          v18 = *v13;
          v19 = (const void *)v13[2];
          if ( *v13 > 4 )
            v18 = 4;
          v43 = v18;
          memcpy(&v42, v19, v18);
          v13[2] = (size_t)v19 + v18;
          if ( v18 != 4 )
          {
LABEL_84:
            FileBlock = -14;
LABEL_85:
            result = dword_10001970[abs32(FileBlock)];
            if ( result == -10 )
              return -10;
            return result;
          }
          LOWORD(v15) = v42;
          v12 = v44;
          v10 = v45;
        }
        else
        {
          v15 = *v14;
          v42 = *v14;
          v13[2] = (size_t)(v14 + 1);
          v43 = 4;
        }
        if ( *v40 == 28 && (_WORD)v15 == 28 )
        {
          v20 = *(size_t **)(v10 + 20);
          v21 = v20[2];
          if ( *v20 + v20[1] - v21 < 6 )
          {
            v23 = v21 + v20[21] - v20[1];
            if ( v20[23] == 1 )
            {
              FileBlock = WriteFileBlock(*(_DWORD *)(v10 + 20));
              if ( FileBlock < 0 )
                goto LABEL_85;
            }
            v20[20] = v23;
            OSSetFilePosition(v20, 0, v23);
            FileBlock = ReadFileBlock(v20);
            if ( FileBlock < 0 )
              goto LABEL_85;
            v24 = *v20;
            v25 = (const void *)v20[2];
            if ( *v20 > 6 )
              v24 = 6;
            v43 = v24;
            memcpy(&v36, v25, v24);
            v20[2] = (size_t)v25 + v24;
            if ( v24 != 6 )
              goto LABEL_84;
            LOWORD(v22) = v37;
            v10 = v45;
          }
          else
          {
            LOWORD(v22) = *(_WORD *)(v21 + 4);
            v36 = *(_DWORD *)v21;
            v37 = v22;
            v20[2] = v21 + 6;
            v43 = 6;
          }
          if ( (v22 & 0x8000u) != 0 )
            return -10;
          if ( (_WORD)v36 != 0xFFFF )
          {
            v34 = -10;
LABEL_83:
            BFSetFilePosition(*(int **)(v10 + 20), 1, v34);
            *a3 = pExcelRecordBuffer;
            v35 = v44;
            *v41 = v44;
            *(_DWORD *)(v10 + 92) = v35 + 4;
            return 0;
          }
          v26 = v44;
          v27 = (char *)pExcelRecordBuffer;
          v22 = (__int16)v22;
          dword_1003A77C += (__int16)v22;
          v38 = (__int16)v22;
          v28 = (__int16)v22 + v44;
          if ( v28 > g_cbCurrentSize )
          {
            if ( v28 < 0 )
              goto LABEL_80;
            if ( !pExcelRecordBuffer || !v28 )
              goto LABEL_81;
            v29 = *((_DWORD *)pExcelRecordBuffer - 2);
            if ( *((_DWORD *)pExcelRecordBuffer - 3) != 1 )
              v29 -= 12;
            if ( v29 < v28 )
            {
              v30 = (char *)MemAllocate((__int16)v22 + v44);
              v39 = v30;
              if ( !v30 )
                goto LABEL_81;
              memcpy(v30, v27, v29);
              MemFree(v27);
              v27 = v39;
              v22 = v38;
              v26 = v44;
            }
            pExcelRecordBuffer = v27;
            g_cbCurrentSize = v28;
          }
          v31 = &v27[v26];
        }
        else
        {
          if ( (_WORD)v15 != 60 )
          {
            v34 = -4;
            goto LABEL_83;
          }
          v22 = SHIWORD(v42);
          v28 = SHIWORD(v42) + v12;
          v27 = (char *)pExcelRecordBuffer;
          if ( v28 > g_cbCurrentSize )
          {
            if ( v28 < 0 )
            {
LABEL_80:
              MemFree(v27);
LABEL_81:
              pExcelRecordBuffer = 0;
              return -1011;
            }
            if ( !pExcelRecordBuffer || !v28 )
              goto LABEL_81;
            v32 = *((_DWORD *)pExcelRecordBuffer - 2);
            if ( *((_DWORD *)pExcelRecordBuffer - 3) != 1 )
              v32 -= 12;
            if ( v32 < v28 )
            {
              v33 = (void *)MemAllocate(v28);
              v38 = (int)v33;
              if ( !v33 )
                goto LABEL_81;
              memcpy(v33, v27, v32);
              MemFree(v27);
              v27 = (char *)v38;
              v22 = SHIWORD(v42);
            }
            pExcelRecordBuffer = v27;
            g_cbCurrentSize = v28;
          }
          v31 = &v27[v44];
        }
        FileBlock = BFReadFile(*(size_t **)(v45 + 20), v31, v22, &v43);
        if ( FileBlock )
          goto LABEL_85;
        v12 = v28;
        v10 = v45;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000df70  mov     edi, edi
0x1000df72  push    ebp
0x1000df73  mov     ebp, esp
0x1000df75  sub     esp, 28h
0x1000df78  push    ebx
0x1000df79  mov     ebx, edx
0x1000df7b  mov     [ebp+var_4], ecx
0x1000df7e  push    esi
0x1000df7f  push    edi
0x1000df80  mov     [ebp+var_18], ebx
0x1000df83  cmp     word ptr [ebx], 0
0x1000df87  lea     esi, [ebx+2]
0x1000df8a  mov     [ebp+var_14], esi
0x1000df8d  jnz     short loc_1000DFA3
0x1000df8f  cmp     word ptr [esi], 0
0x1000df93  jz      short loc_1000DFA6
0x1000df95  mov     eax, 0FFFFFFF6h
0x1000df9a  pop     edi
0x1000df9b  pop     esi
0x1000df9c  pop     ebx
0x1000df9d  mov     esp, ebp
0x1000df9f  pop     ebp
0x1000dfa0  retn    4
0x1000dfa3  mov     [ebp+var_14], esi
0x1000dfa6  mov     edi, [ecx+28h]
0x1000dfa9  test    edi, edi
0x1000dfab  jz      short loc_1000E021
0x1000dfad  mov     eax, [edi+8]
0x1000dfb0  movsx   ebx, word ptr [eax+6]
0x1000dfb4  cmp     ebx, _g_cbCurrentSize
0x1000dfba  jbe     short loc_1000DFEE
0x1000dfbc  mov     ecx, _pExcelRecordBuffer; Src
0x1000dfc2  mov     edx, ebx
0x1000dfc4  call    _MemReAllocate@8; MemReAllocate(x,x)
0x1000dfc9  mov     esi, eax
0x1000dfcb  mov     _pExcelRecordBuffer, esi
0x1000dfd1  test    esi, esi
0x1000dfd3  jnz     short loc_1000DFE6
0x1000dfd5  mov     _g_cbCurrentSize, eax
0x1000dfda  lea     eax, [esi-2]
0x1000dfdd  pop     edi
0x1000dfde  pop     esi
0x1000dfdf  pop     ebx
0x1000dfe0  mov     esp, ebp
0x1000dfe2  pop     ebp
0x1000dfe3  retn    4
0x1000dfe6  mov     _g_cbCurrentSize, ebx
0x1000dfec  jmp     short loc_1000DFF4
0x1000dfee  mov     esi, _pExcelRecordBuffer
0x1000dff4  mov     ecx, [edi+8]
0x1000dff7  movsx   eax, word ptr [ecx+6]
0x1000dffb  push    eax; Size
0x1000dffc  lea     eax, [ecx+8]
0x1000dfff  push    eax; Src
0x1000e000  push    esi; void *
0x1000e001  call    _memcpy
0x1000e006  mov     eax, [ebp+arg_0]
0x1000e009  add     esp, 0Ch
0x1000e00c  mov     [eax], esi
0x1000e00e  mov     eax, [edi+8]
0x1000e011  mov     eax, [eax]
0x1000e013  mov     [edi+8], eax
0x1000e016  xor     eax, eax
0x1000e018  pop     edi
0x1000e019  pop     esi
0x1000e01a  pop     ebx
0x1000e01b  mov     esp, ebp
0x1000e01d  pop     ebp
0x1000e01e  retn    4
0x1000e021  cmp     word ptr [esi], 0
0x1000e025  mov     dword_1003A77C, 0
0x1000e02f  jnz     short loc_1000E045
0x1000e031  mov     eax, [ebp+arg_0]
0x1000e034  mov     dword ptr [eax], 0
0x1000e03a  xor     eax, eax
0x1000e03c  pop     edi
0x1000e03d  pop     esi
0x1000e03e  pop     ebx
0x1000e03f  mov     esp, ebp
0x1000e041  pop     ebp
0x1000e042  retn    4
0x1000e045  push    [ebp+arg_0]
0x1000e048  mov     edi, ecx
0x1000e04a  call    _ExcelReadBufferedRecord@12; ExcelReadBufferedRecord(x,x,x)
0x1000e04f  test    eax, eax
0x1000e051  jnz     loc_1000E3EA
0x1000e057  movzx   eax, word ptr [ebx]
0x1000e05a  mov     ecx, 221h
0x1000e05f  lea     ebx, [ecx-6Bh]
0x1000e062  cmp     ax, cx
0x1000e065  jz      short loc_1000E0C2
0x1000e067  cmp     ax, 1Ch
0x1000e06b  jz      short loc_1000E0C2
0x1000e06d  cmp     ax, 7Fh
0x1000e071  jz      short loc_1000E0C2
0x1000e073  mov     ecx, 223h
0x1000e078  cmp     ax, cx
0x1000e07b  jz      short loc_1000E0C2
0x1000e07d  cmp     ax, 23h ; '#'
0x1000e081  jz      short loc_1000E0C2
0x1000e083  cmp     ax, 5Dh ; ']'
0x1000e087  jz      short loc_1000E0C2
0x1000e089  mov     ecx, 218h
0x1000e08e  cmp     ax, cx
0x1000e091  jz      short loc_1000E0C2
0x1000e093  cmp     ax, 18h
0x1000e097  jz      short loc_1000E0C2
0x1000e099  mov     ecx, 207h
0x1000e09e  cmp     ax, cx
0x1000e0a1  jz      short loc_1000E0C2
0x1000e0a3  mov     ecx, 206h
0x1000e0a8  cmp     ax, cx
0x1000e0ab  jz      short loc_1000E0C2
0x1000e0ad  mov     ecx, 406h
0x1000e0b2  cmp     ax, cx
0x1000e0b5  jz      short loc_1000E0C2
0x1000e0b7  cmp     ax, 6
0x1000e0bb  jz      short loc_1000E0C2
0x1000e0bd  cmp     ax, bx
0x1000e0c0  jnz     short loc_1000E0D4
0x1000e0c2  movzx   ecx, word ptr [esi]
0x1000e0c5  mov     edx, 400h
0x1000e0ca  cmp     cx, dx
0x1000e0cd  jge     short loc_1000E0E8
0x1000e0cf  cmp     ax, bx
0x1000e0d2  jz      short loc_1000E0E8
0x1000e0d4  movsx   eax, word ptr [esi]
0x1000e0d7  add     eax, 4
0x1000e0da  mov     [edi+5Ch], eax
0x1000e0dd  xor     eax, eax
0x1000e0df  pop     edi
0x1000e0e0  pop     esi
0x1000e0e1  pop     ebx
0x1000e0e2  mov     esp, ebp
0x1000e0e4  pop     ebp
0x1000e0e5  retn    4
0x1000e0e8  movsx   esi, cx
0x1000e0eb  mov     ebx, [edi+14h]
0x1000e0ee  mov     [ebp+var_8], esi
0x1000e0f1  mov     edx, [ebx+4]
0x1000e0f4  mov     eax, edx
0x1000e0f6  mov     ecx, [ebx+8]
0x1000e0f9  sub     eax, ecx
0x1000e0fb  add     eax, [ebx]
0x1000e0fd  cmp     eax, 4
0x1000e100  jb      short loc_1000E116
0x1000e102  mov     eax, [ecx]
0x1000e104  add     ecx, 4
0x1000e107  mov     [ebp+var_10], eax
0x1000e10a  mov     [ebx+8], ecx
0x1000e10d  mov     [ebp+var_C], 4
0x1000e114  jmp     short loc_1000E187
0x1000e116  mov     esi, [ebx+54h]
0x1000e119  sub     esi, edx
0x1000e11b  add     esi, ecx
0x1000e11d  cmp     dword ptr [ebx+5Ch], 1
0x1000e121  jnz     short loc_1000E132
0x1000e123  mov     ecx, ebx
0x1000e125  call    WriteFileBlock
0x1000e12a  test    eax, eax
0x1000e12c  js      loc_1000E3D3
0x1000e132  push    esi
0x1000e133  xor     edx, edx
0x1000e135  mov     [ebx+50h], esi
0x1000e138  mov     ecx, ebx
0x1000e13a  call    OSSetFilePosition
0x1000e13f  mov     ecx, ebx
0x1000e141  call    ReadFileBlock
0x1000e146  test    eax, eax
0x1000e148  js      loc_1000E3D3
0x1000e14e  mov     edi, [ebx]
0x1000e150  mov     eax, 4
0x1000e155  mov     esi, [ebx+8]
0x1000e158  cmp     edi, 4
0x1000e15b  cmova   edi, eax
0x1000e15e  lea     eax, [ebp+var_10]
0x1000e161  push    edi; Size
0x1000e162  push    esi; Src
0x1000e163  push    eax; void *
0x1000e164  mov     [ebp+var_C], edi
0x1000e167  call    _memcpy
0x1000e16c  add     esp, 0Ch
0x1000e16f  lea     eax, [esi+edi]
0x1000e172  mov     [ebx+8], eax
0x1000e175  cmp     edi, 4
0x1000e178  jnz     loc_1000E3CE
0x1000e17e  mov     eax, [ebp+var_10]
0x1000e181  mov     esi, [ebp+var_8]
0x1000e184  mov     edi, [ebp+var_4]
0x1000e187  mov     ecx, [ebp+var_18]
0x1000e18a  cmp     word ptr [ecx], 1Ch
0x1000e18e  jnz     loc_1000E2F7
0x1000e194  cmp     ax, 1Ch
0x1000e198  jnz     loc_1000E2F7
0x1000e19e  mov     ebx, [edi+14h]
0x1000e1a1  mov     ecx, [ebx+4]
0x1000e1a4  mov     eax, ecx
0x1000e1a6  mov     edx, [ebx+8]
0x1000e1a9  sub     eax, edx
0x1000e1ab  add     eax, [ebx]
0x1000e1ad  cmp     eax, 6
0x1000e1b0  jb      short loc_1000E1CE
0x1000e1b2  mov     eax, [edx]
0x1000e1b4  mov     cx, [edx+4]
0x1000e1b8  mov     [ebp+var_28], eax
0x1000e1bb  lea     eax, [edx+6]
0x1000e1be  mov     [ebp+var_24], cx
0x1000e1c2  mov     [ebx+8], eax
0x1000e1c5  mov     [ebp+var_C], 6
0x1000e1cc  jmp     short loc_1000E23D
0x1000e1ce  mov     esi, [ebx+54h]
0x1000e1d1  sub     esi, ecx
0x1000e1d3  add     esi, edx
0x1000e1d5  cmp     dword ptr [ebx+5Ch], 1
0x1000e1d9  jnz     short loc_1000E1EA
0x1000e1db  mov     ecx, ebx
0x1000e1dd  call    WriteFileBlock
0x1000e1e2  test    eax, eax
0x1000e1e4  js      loc_1000E3D3
0x1000e1ea  push    esi
0x1000e1eb  xor     edx, edx
0x1000e1ed  mov     [ebx+50h], esi
0x1000e1f0  mov     ecx, ebx
0x1000e1f2  call    OSSetFilePosition
0x1000e1f7  mov     ecx, ebx
0x1000e1f9  call    ReadFileBlock
0x1000e1fe  test    eax, eax
0x1000e200  js      loc_1000E3D3
0x1000e206  mov     edi, [ebx]
0x1000e208  mov     eax, 6
0x1000e20d  mov     esi, [ebx+8]
0x1000e210  cmp     edi, 6
0x1000e213  cmova   edi, eax
0x1000e216  lea     eax, [ebp+var_28]
0x1000e219  push    edi; Size
0x1000e21a  push    esi; Src
0x1000e21b  push    eax; void *
0x1000e21c  mov     [ebp+var_C], edi
0x1000e21f  call    _memcpy
0x1000e224  add     esp, 0Ch
0x1000e227  lea     eax, [esi+edi]
0x1000e22a  mov     [ebx+8], eax
0x1000e22d  cmp     edi, 6
0x1000e230  jnz     loc_1000E3CE
0x1000e236  mov     cx, [ebp+var_24]
0x1000e23a  mov     edi, [ebp+var_4]
0x1000e23d  test    cx, cx
0x1000e240  js      loc_1000DF95
0x1000e246  cmp     word ptr [ebp+var_28], 0FFFFh
0x1000e24b  jnz     loc_1000E371
0x1000e251  mov     edx, [ebp+var_8]
0x1000e254  mov     esi, _pExcelRecordBuffer
0x1000e25a  movsx   ecx, cx
0x1000e25d  add     dword_1003A77C, ecx
0x1000e263  mov     [ebp+var_20], ecx
0x1000e266  lea     edi, [ecx+edx]
0x1000e269  cmp     edi, _g_cbCurrentSize
0x1000e26f  jbe     short loc_1000E2D3
0x1000e271  test    edi, edi
0x1000e273  js      loc_1000E378
0x1000e279  test    esi, esi
0x1000e27b  jz      loc_1000E37F
0x1000e281  test    edi, edi
0x1000e283  jz      loc_1000E37F
0x1000e289  mov     ebx, [esi-8]
0x1000e28c  cmp     dword ptr [esi-0Ch], 1
0x1000e290  lea     eax, [ebx-0Ch]
0x1000e293  cmovnz  ebx, eax
0x1000e296  cmp     ebx, edi
0x1000e298  jge     short loc_1000E2C7
0x1000e29a  mov     ecx, edi
0x1000e29c  call    _MemAllocate@4; MemAllocate(x)
0x1000e2a1  mov     [ebp+var_1C], eax
0x1000e2a4  test    eax, eax
0x1000e2a6  jz      loc_1000E37F
0x1000e2ac  push    ebx; Size
0x1000e2ad  push    esi; Src
0x1000e2ae  push    eax; void *
0x1000e2af  call    _memcpy
0x1000e2b4  add     esp, 0Ch
0x1000e2b7  mov     ecx, esi
0x1000e2b9  call    _MemFree@4; MemFree(x)
0x1000e2be  mov     esi, [ebp+var_1C]
0x1000e2c1  mov     ecx, [ebp+var_20]
0x1000e2c4  mov     edx, [ebp+var_8]
0x1000e2c7  mov     _pExcelRecordBuffer, esi
0x1000e2cd  mov     _g_cbCurrentSize, edi
0x1000e2d3  add     edx, esi
0x1000e2d5  lea     eax, [ebp+var_C]
0x1000e2d8  push    eax
0x1000e2d9  push    ecx
0x1000e2da  mov     ecx, [ebp+var_4]
0x1000e2dd  mov     ecx, [ecx+14h]
0x1000e2e0  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1000e2e5  test    eax, eax
0x1000e2e7  jnz     loc_1000E3D3
0x1000e2ed  mov     esi, edi
0x1000e2ef  mov     edi, [ebp+var_4]
0x1000e2f2  jmp     loc_1000E0EB
0x1000e2f7  cmp     ax, 3Ch ; '<'
  ... truncated ...
```
