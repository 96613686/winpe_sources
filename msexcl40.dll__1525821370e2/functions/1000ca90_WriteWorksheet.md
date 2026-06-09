# WriteWorksheet

- ea: `0x1000ca90`
- end: `0x1000cf2d`
- name: `WriteWorksheet`
- size: `1181`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1000d760`

## callees

- `0x1000bfc0`
- `0x1000c670`
- `0x1000c9f0`
- `0x1000ca90`
- `0x1002611f`
- `0x10035f40`

## pseudocode

```c
int __fastcall WriteWorksheet(int a1, _DWORD *a2, int a3)
{
  int **v4; // edi
  bool v5; // zf
  int result; // eax
  int v7; // esi
  int v8; // eax
  size_t v9; // eax
  void *v10; // esi
  char *v11; // ecx
  int *v12; // edx
  signed int v13; // esi
  _WORD *v14; // edi
  int v15; // eax
  int v16; // eax
  int i; // ecx
  _DWORD *v18; // edi
  __int16 v19; // ax
  int *v20; // esi
  _WORD *v21; // esi
  int v22; // eax
  __int16 v23; // cx
  int v24; // eax
  _DWORD *v25; // esi
  __int16 v26; // ax
  int v27; // eax
  _WORD *v28; // [esp-4h] [ebp-30h]
  int **v30; // [esp+1Ch] [ebp-10h] BYREF
  char *v31; // [esp+20h] [ebp-Ch]
  int v32; // [esp+24h] [ebp-8h]
  int v33; // [esp+28h] [ebp-4h] BYREF

  v32 = a1;
  v4 = *(int ***)(a3 + 4);
  *(_DWORD *)(a3 + 36) = a2[5];
  v5 = *((_WORD *)v4 + 5) == 16;
  v30 = v4;
  if ( !v5 )
  {
    while ( 1 )
    {
      result = WriteUntilEOF(&v30);
      if ( result )
        break;
      v4 = v30;
      if ( *((_WORD *)v30 + 5) == 16 )
        goto LABEL_4;
    }
    if ( result != 1 )
      return result;
    return 0;
  }
LABEL_4:
  a2[5] += *((__int16 *)v4 + 3) + 4;
  v5 = a2[6] == 1;
  v7 = v32;
  if ( v5 )
  {
    v8 = BFWriteFile(*(_DWORD *)(v32 + 20), (char *)v4 + 4, 4u);
    if ( v8 || (v8 = BFWriteFile(*(_DWORD *)(v7 + 20), (char *)v4 + 8, *((__int16 *)v4 + 3))) != 0 )
    {
      result = dword_10001970[abs32(v8)];
      if ( result == -10 )
        result = -10;
      if ( result )
        return result;
    }
  }
  if ( *(_DWORD *)(v7 + 36) )
  {
    v9 = g_cbCurrentSize;
    v10 = pExcelRecordBuffer;
    v33 = 131166;
    if ( (int)g_cbCurrentSize > 2 )
      v9 = 2;
    memset(pExcelRecordBuffer, 0, v9);
    result = WriteRecord(&v33, v10);
    if ( result )
      return result;
  }
  v5 = *(_WORD *)(a3 + 10) == 0;
  v11 = (char *)*v4;
  v31 = v11;
  v30 = (int **)v11;
  if ( v5 )
  {
    v18 = a2;
  }
  else
  {
    v12 = *(int **)(a3 + 28);
    v13 = g_cbCurrentSize;
    v14 = pExcelRecordBuffer;
    LOWORD(v33) = 523;
    v15 = a2[9];
    if ( v12 )
    {
      if ( v15 == 5 )
      {
        if ( (int)g_cbCurrentSize >= 12 )
        {
          *(_DWORD *)pExcelRecordBuffer = 0;
          v14[2] = *((_WORD *)v12 + 2);
          v14[3] = 0;
          *((_DWORD *)v14 + 2) = 0;
          v16 = 12;
          goto LABEL_31;
        }
      }
      else if ( (int)g_cbCurrentSize >= 16 )
      {
        *(_DWORD *)pExcelRecordBuffer = 0;
        *((_DWORD *)v14 + 1) = v12[1];
        v16 = 16;
        *((_DWORD *)v14 + 2) = 0;
        *((_DWORD *)v14 + 3) = 0;
LABEL_31:
        while ( v13 >= v16 + 4 )
        {
          *(_DWORD *)((char *)v14 + v16) = v12[34];
          if ( !*v12 )
          {
            for ( i = 31; i >= 0; --i )
            {
              if ( v12[i + 2] )
                break;
            }
            if ( a2[9] == 5 )
            {
              if ( v13 < 8 )
                break;
              v14[3] = *((_WORD *)v12 + 2) + i + 1;
            }
            else
            {
              if ( v13 < 12 )
                break;
              *((_DWORD *)v14 + 2) = i + v12[1] + 1;
            }
          }
          v12 = (int *)*v12;
          v16 += 4;
          if ( !v12 )
            goto LABEL_42;
        }
      }
    }
    else
    {
      if ( v15 == 5 )
      {
        if ( (int)g_cbCurrentSize > 12 )
          v13 = 12;
        memset(pExcelRecordBuffer, 0, v13);
        LOWORD(v16) = 12;
      }
      else
      {
        if ( (int)g_cbCurrentSize > 16 )
          v13 = 16;
        memset(pExcelRecordBuffer, 0, v13);
        LOWORD(v16) = 16;
      }
LABEL_42:
      HIWORD(v33) = v16;
    }
    v28 = v14;
    v18 = a2;
    result = WriteRecord(&v33, v28);
    if ( result )
      return result;
    v11 = v31;
  }
  if ( !v11 )
    return 0;
  while ( 1 )
  {
    v19 = *((_WORD *)v11 + 2);
    if ( v19 > 1033 )
    {
      if ( v19 != 2057 )
        goto LABEL_55;
    }
    else if ( v19 != 1033 && v19 != 9 && v19 != 521 )
    {
      goto LABEL_55;
    }
    result = WriteUntilEOF(&v30);
    if ( result )
      return result;
    v11 = (char *)v30;
    v31 = (char *)v30;
LABEL_55:
    v20 = (int *)(v11 + 4);
    if ( *((_WORD *)v11 + 2) == 512 )
      break;
    v18[5] += *((__int16 *)v11 + 3) + 4;
    if ( v18[6] == 1 )
    {
      v27 = BFWriteFile(*(_DWORD *)(v32 + 20), v11 + 4, 4u);
      if ( v27 || (v27 = BFWriteFile(*(_DWORD *)(v32 + 20), v31 + 8, *((__int16 *)v20 + 1))) != 0 )
      {
        result = dword_10001970[abs32(v27)];
        if ( result == -10 )
          result = -10;
        if ( result )
          return result;
      }
      v11 = v31;
    }
LABEL_86:
    v11 = *(char **)v11;
    v31 = v11;
    v30 = (int **)v11;
    if ( !v11 )
      return 0;
  }
  v5 = v18[9] == 5;
  v21 = pExcelRecordBuffer;
  LOWORD(v33) = 512;
  v22 = *(_DWORD *)(a3 + 20);
  if ( v5 )
  {
    v23 = 10;
    HIWORD(v33) = 10;
    if ( v22 == 1 )
    {
      *(_DWORD *)((char *)pExcelRecordBuffer + 10) = 256;
      *v21 = 0;
      v21[2] = 0;
    }
    else
    {
      *(_WORD *)pExcelRecordBuffer = *(_WORD *)(a3 + 12);
      v21[1] = *(_WORD *)(a3 + 16) + 1;
      v21[2] = *(_WORD *)(a3 + 14);
      v21[3] = *(_WORD *)(a3 + 18) + 1;
    }
    v21[4] = 0;
  }
  else
  {
    v23 = 14;
    HIWORD(v33) = 14;
    if ( v22 == 1 )
    {
      *(_DWORD *)pExcelRecordBuffer = 0;
      *((_DWORD *)v21 + 1) = 0x10000;
      *((_DWORD *)v21 + 2) = 0;
    }
    else
    {
      *(_DWORD *)pExcelRecordBuffer = *(unsigned __int16 *)(a3 + 12);
      *((_DWORD *)v21 + 1) = *(unsigned __int16 *)(a3 + 16) + 1;
      v21[4] = *(_WORD *)(a3 + 14);
      v21[5] = *(_WORD *)(a3 + 18) + 1;
    }
    v21[6] = 0;
  }
  v18[5] += v23 + 4;
  if ( v18[6] == 1 )
  {
    v24 = BFWriteFile(*(_DWORD *)(v32 + 20), (char *)&v33, 4u);
    if ( v24 || (v24 = BFWriteFile(*(_DWORD *)(v32 + 20), (char *)v21, SHIWORD(v33))) != 0 )
    {
      result = dword_10001970[abs32(v24)];
      if ( result == -10 )
        result = -10;
      if ( result )
        return result;
    }
  }
  v25 = *(_DWORD **)(a3 + 28);
  v26 = -1;
  *(_DWORD *)(a3 + 12) = -1;
  if ( !v25 )
  {
LABEL_75:
    if ( *(_WORD *)(a3 + 12) == 0xFFFF )
      *(_WORD *)(a3 + 12) = 0;
    v11 = v31;
    if ( v26 == -1 )
      *(_WORD *)(a3 + 14) = 0;
    goto LABEL_86;
  }
  while ( 1 )
  {
    result = WriteCellBlock(a3, v25);
    if ( result )
      return result;
    v25 = (_DWORD *)*v25;
    if ( !v25 )
    {
      v26 = *(_WORD *)(a3 + 14);
      goto LABEL_75;
    }
  }
}

```

## disassembly

```asm
0x1000ca90  mov     edi, edi
0x1000ca92  push    ebp
0x1000ca93  mov     ebp, esp
0x1000ca95  sub     esp, 20h
0x1000ca98  push    ebx
0x1000ca99  mov     ebx, [ebp+arg_0]
0x1000ca9c  push    esi
0x1000ca9d  mov     esi, edx
0x1000ca9f  mov     [ebp+var_8], ecx
0x1000caa2  push    edi
0x1000caa3  mov     edi, [ebx+4]
0x1000caa6  mov     [ebp+var_14], esi
0x1000caa9  mov     eax, [esi+14h]
0x1000caac  mov     [ebx+24h], eax
0x1000caaf  cmp     word ptr [edi+0Ah], 10h
0x1000cab4  mov     [ebp+var_10], edi
0x1000cab7  jz      short loc_1000CAE0
0x1000cab9  nop     dword ptr [eax+00000000h]
0x1000cac0  lea     eax, [ebp+var_10]
0x1000cac3  mov     edx, esi
0x1000cac5  push    eax
0x1000cac6  call    WriteUntilEOF
0x1000cacb  test    eax, eax
0x1000cacd  jnz     loc_1000CBD4
0x1000cad3  mov     edi, [ebp+var_10]
0x1000cad6  mov     ecx, [ebp+var_8]
0x1000cad9  cmp     word ptr [edi+0Ah], 10h
0x1000cade  jnz     short loc_1000CAC0
0x1000cae0  movsx   eax, word ptr [edi+6]
0x1000cae4  add     eax, 4
0x1000cae7  add     [esi+14h], eax
0x1000caea  cmp     dword ptr [esi+18h], 1
0x1000caee  mov     esi, [ebp+var_8]
0x1000caf1  jnz     short loc_1000CB37
0x1000caf3  mov     ecx, [esi+14h]
0x1000caf6  lea     edx, [edi+4]
0x1000caf9  push    4
0x1000cafb  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000cb00  test    eax, eax
0x1000cb02  jnz     short loc_1000CB18
0x1000cb04  movsx   eax, word ptr [edi+6]
0x1000cb08  lea     edx, [edi+8]
0x1000cb0b  mov     ecx, [esi+14h]
0x1000cb0e  push    eax
0x1000cb0f  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000cb14  test    eax, eax
0x1000cb16  jz      short loc_1000CB37
0x1000cb18  cdq
0x1000cb19  mov     ecx, 0FFFFFFF6h
0x1000cb1e  xor     eax, edx
0x1000cb20  sub     eax, edx
0x1000cb22  mov     eax, ds:dword_10001970[eax*4]
0x1000cb29  cmp     eax, 0FFFFFFF6h
0x1000cb2c  cmovz   eax, ecx
0x1000cb2f  test    eax, eax
0x1000cb31  jnz     loc_1000CBDB
0x1000cb37  cmp     dword ptr [esi+24h], 0
0x1000cb3b  jz      short loc_1000CB7B
0x1000cb3d  mov     eax, _g_cbCurrentSize
0x1000cb42  mov     ecx, 2
0x1000cb47  mov     esi, _pExcelRecordBuffer
0x1000cb4d  cmp     eax, ecx
0x1000cb4f  mov     [ebp+var_4], 2005Eh
0x1000cb56  cmovg   eax, ecx
0x1000cb59  push    eax; Size
0x1000cb5a  push    0; Val
0x1000cb5c  push    esi; void *
0x1000cb5d  call    _memset
0x1000cb62  mov     edx, [ebp+var_14]
0x1000cb65  lea     eax, [ebp+var_4]
0x1000cb68  add     esp, 0Ch
0x1000cb6b  push    esi
0x1000cb6c  mov     esi, [ebp+var_8]
0x1000cb6f  mov     ecx, esi
0x1000cb71  push    eax
0x1000cb72  call    WriteRecord
0x1000cb77  test    eax, eax
0x1000cb79  jnz     short loc_1000CBDB
0x1000cb7b  cmp     word ptr [ebx+0Ah], 0
0x1000cb80  mov     ecx, [edi]
0x1000cb82  mov     [ebp+var_C], ecx
0x1000cb85  mov     [ebp+var_10], ecx
0x1000cb88  jz      loc_1000CD1A
0x1000cb8e  mov     edx, [ebx+1Ch]
0x1000cb91  mov     eax, 20Bh
0x1000cb96  mov     esi, _g_cbCurrentSize
0x1000cb9c  mov     edi, _pExcelRecordBuffer
0x1000cba2  mov     word ptr [ebp+var_4], ax
0x1000cba6  mov     eax, [ebp+var_14]
0x1000cba9  mov     eax, [eax+24h]
0x1000cbac  test    edx, edx
0x1000cbae  jnz     short loc_1000CC04
0x1000cbb0  cmp     eax, 5
0x1000cbb3  jnz     short loc_1000CBE4
0x1000cbb5  mov     eax, 0Ch
0x1000cbba  cmp     esi, eax
0x1000cbbc  cmovg   esi, eax
0x1000cbbf  push    esi; Size
0x1000cbc0  push    edx; Val
0x1000cbc1  push    edi; void *
0x1000cbc2  call    _memset
0x1000cbc7  add     esp, 0Ch
0x1000cbca  mov     eax, 0Ch
0x1000cbcf  jmp     loc_1000CCB4
0x1000cbd4  cmp     eax, 1
0x1000cbd7  jnz     short loc_1000CBDB
0x1000cbd9  xor     eax, eax
0x1000cbdb  pop     edi
0x1000cbdc  pop     esi
0x1000cbdd  pop     ebx
0x1000cbde  mov     esp, ebp
0x1000cbe0  pop     ebp
0x1000cbe1  retn    4
0x1000cbe4  mov     eax, 10h
0x1000cbe9  cmp     esi, eax
0x1000cbeb  cmovg   esi, eax
0x1000cbee  push    esi; Size
0x1000cbef  push    0; Val
0x1000cbf1  push    edi; void *
0x1000cbf2  call    _memset
0x1000cbf7  add     esp, 0Ch
0x1000cbfa  mov     eax, 10h
0x1000cbff  jmp     loc_1000CCB4
0x1000cc04  cmp     eax, 5
0x1000cc07  jnz     short loc_1000CC30
0x1000cc09  cmp     esi, 0Ch
0x1000cc0c  jl      loc_1000CCB8
0x1000cc12  mov     dword ptr [edi], 0
0x1000cc18  mov     ax, [edx+4]
0x1000cc1c  mov     [edi+4], ax
0x1000cc20  xor     eax, eax
0x1000cc22  mov     [edi+6], ax
0x1000cc26  mov     [edi+8], eax
0x1000cc29  mov     eax, 0Ch
0x1000cc2e  jmp     short loc_1000CC58
0x1000cc30  cmp     esi, 10h
0x1000cc33  jl      loc_1000CCB8
0x1000cc39  mov     dword ptr [edi], 0
0x1000cc3f  mov     eax, [edx+4]
0x1000cc42  mov     [edi+4], eax
0x1000cc45  mov     eax, 10h
0x1000cc4a  mov     dword ptr [edi+8], 0
0x1000cc51  mov     dword ptr [edi+0Ch], 0
0x1000cc58  mov     ecx, eax
0x1000cc5a  add     eax, 4
0x1000cc5d  mov     [ebp+var_18], eax
0x1000cc60  cmp     esi, eax
0x1000cc62  jl      short loc_1000CCB8
0x1000cc64  mov     eax, [edx+88h]
0x1000cc6a  mov     [edi+ecx], eax
0x1000cc6d  cmp     dword ptr [edx], 0
0x1000cc70  jnz     short loc_1000CCAB
0x1000cc72  mov     ecx, 1Fh
0x1000cc77  cmp     dword ptr [edx+ecx*4+8], 0
0x1000cc7c  jnz     short loc_1000CC83
0x1000cc7e  sub     ecx, 1
0x1000cc81  jns     short loc_1000CC77
0x1000cc83  mov     eax, [ebp+var_14]
0x1000cc86  cmp     dword ptr [eax+24h], 5
0x1000cc8a  jnz     short loc_1000CC9D
0x1000cc8c  cmp     esi, 8
0x1000cc8f  jl      short loc_1000CCB8
0x1000cc91  inc     cx
0x1000cc93  add     cx, [edx+4]
0x1000cc97  mov     [edi+6], cx
0x1000cc9b  jmp     short loc_1000CCAB
0x1000cc9d  cmp     esi, 0Ch
0x1000cca0  jl      short loc_1000CCB8
0x1000cca2  mov     eax, [edx+4]
0x1000cca5  inc     eax
0x1000cca6  add     eax, ecx
0x1000cca8  mov     [edi+8], eax
0x1000ccab  mov     edx, [edx]
0x1000ccad  mov     eax, [ebp+var_18]
0x1000ccb0  test    edx, edx
0x1000ccb2  jnz     short loc_1000CC58
0x1000ccb4  mov     word ptr [ebp+var_4+2], ax
0x1000ccb8  mov     esi, [ebp+var_8]
0x1000ccbb  lea     eax, [ebp+var_4]
0x1000ccbe  push    edi
0x1000ccbf  mov     edi, [ebp+var_14]
0x1000ccc2  mov     ecx, esi
0x1000ccc4  push    eax
0x1000ccc5  mov     edx, edi
0x1000ccc7  call    WriteRecord
0x1000cccc  test    eax, eax
0x1000ccce  jnz     loc_1000CBDB
0x1000ccd4  mov     ecx, [ebp+var_C]
0x1000ccd7  test    ecx, ecx
0x1000ccd9  jz      loc_1000CBD9
0x1000ccdf  mov     [ebp+var_18], 409h
0x1000cce6  mov     edx, 0FFFFh
0x1000cceb  mov     [ebp+var_14], 209h
0x1000ccf2  mov     [ebp+var_1C], 809h
0x1000ccf9  nop     dword ptr [eax+00000000h]
0x1000cd00  movzx   eax, word ptr [ecx+4]
0x1000cd04  cmp     ax, word ptr [ebp+var_18]
0x1000cd08  jg      short loc_1000CD1F
0x1000cd0a  jz      short loc_1000CD25
0x1000cd0c  cmp     ax, 9
0x1000cd10  jz      short loc_1000CD25
0x1000cd12  cmp     ax, word ptr [ebp+var_14]
0x1000cd16  jz      short loc_1000CD25
0x1000cd18  jmp     short loc_1000CD45
0x1000cd1a  mov     edi, [ebp+var_14]
0x1000cd1d  jmp     short loc_1000CCD7
0x1000cd1f  cmp     ax, word ptr [ebp+var_1C]
0x1000cd23  jnz     short loc_1000CD45
0x1000cd25  lea     eax, [ebp+var_10]
0x1000cd28  mov     edx, edi
0x1000cd2a  push    eax
0x1000cd2b  mov     ecx, esi
0x1000cd2d  call    WriteUntilEOF
0x1000cd32  test    eax, eax
0x1000cd34  jnz     loc_1000CBDB
0x1000cd3a  mov     ecx, [ebp+var_10]
0x1000cd3d  mov     edx, 0FFFFh
0x1000cd42  mov     [ebp+var_C], ecx
0x1000cd45  lea     esi, [ecx+4]
0x1000cd48  mov     eax, 200h
0x1000cd4d  cmp     [esi], ax
0x1000cd50  jnz     loc_1000CEAF
0x1000cd56  cmp     dword ptr [edi+24h], 5
0x1000cd5a  mov     esi, _pExcelRecordBuffer
0x1000cd60  mov     word ptr [ebp+var_4], ax
0x1000cd64  mov     eax, [ebx+14h]
0x1000cd67  jnz     short loc_1000CDB8
0x1000cd69  mov     ecx, 0Ah
0x1000cd6e  mov     word ptr [ebp+var_4+2], cx
0x1000cd72  cmp     eax, 1
0x1000cd75  jnz     short loc_1000CD8D
0x1000cd77  xor     eax, eax
0x1000cd79  mov     dword ptr [esi+0Ah], 100h
0x1000cd80  mov     [esi], ax
0x1000cd83  mov     [esi+4], ax
0x1000cd87  mov     [esi+8], ax
0x1000cd8b  jmp     short loc_1000CE00
0x1000cd8d  movzx   eax, word ptr [ebx+0Ch]
0x1000cd91  mov     [esi], ax
0x1000cd94  movzx   eax, word ptr [ebx+10h]
0x1000cd98  inc     ax
0x1000cd9a  mov     [esi+2], ax
0x1000cd9e  movzx   eax, word ptr [ebx+0Eh]
0x1000cda2  mov     [esi+4], ax
0x1000cda6  movzx   eax, word ptr [ebx+12h]
0x1000cdaa  inc     ax
0x1000cdac  mov     [esi+6], ax
0x1000cdb0  xor     eax, eax
0x1000cdb2  mov     [esi+8], ax
0x1000cdb6  jmp     short loc_1000CE00
0x1000cdb8  mov     ecx, 0Eh
0x1000cdbd  mov     word ptr [ebp+var_4+2], cx
0x1000cdc1  cmp     eax, 1
0x1000cdc4  jnz     short loc_1000CDDA
0x1000cdc6  xor     eax, eax
0x1000cdc8  mov     dword ptr [esi], 0
0x1000cdce  mov     dword ptr [esi+4], 10000h
0x1000cdd5  mov     [esi+8], eax
0x1000cdd8  jmp     short loc_1000CDFA
0x1000cdda  movzx   eax, word ptr [ebx+0Ch]
0x1000cdde  mov     [esi], eax
0x1000cde0  movzx   eax, word ptr [ebx+10h]
0x1000cde4  inc     eax
0x1000cde5  mov     [esi+4], eax
0x1000cde8  movzx   eax, word ptr [ebx+0Eh]
0x1000cdec  mov     [esi+8], ax
0x1000cdf0  movzx   eax, word ptr [ebx+12h]
0x1000cdf4  inc     ax
0x1000cdf6  mov     [esi+0Ah], ax
0x1000cdfa  xor     eax, eax
0x1000cdfc  mov     [esi+0Ch], ax
0x1000ce00  movsx   eax, cx
0x1000ce03  add     eax, 4
0x1000ce06  add     [edi+14h], eax
0x1000ce09  cmp     dword ptr [edi+18h], 1
0x1000ce0d  jnz     short loc_1000CE5D
0x1000ce0f  mov     ecx, [ebp+var_8]
0x1000ce12  lea     edx, [ebp+var_4]
0x1000ce15  push    4
0x1000ce17  mov     ecx, [ecx+14h]
0x1000ce1a  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000ce1f  test    eax, eax
0x1000ce21  jnz     short loc_1000CE39
0x1000ce23  movsx   eax, word ptr [ebp+var_4+2]
0x1000ce27  mov     edx, esi
0x1000ce29  push    eax
0x1000ce2a  mov     eax, [ebp+var_8]
0x1000ce2d  mov     ecx, [eax+14h]
0x1000ce30  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000ce35  test    eax, eax
0x1000ce37  jz      short loc_1000CE58
0x1000ce39  cdq
0x1000ce3a  mov     ecx, 0FFFFFFF6h
0x1000ce3f  xor     eax, edx
0x1000ce41  sub     eax, edx
0x1000ce43  mov     eax, ds:dword_10001970[eax*4]
0x1000ce4a  cmp     eax, 0FFFFFFF6h
0x1000ce4d  cmovz   eax, ecx
0x1000ce50  test    eax, eax
0x1000ce52  jnz     loc_1000CBDB
  ... truncated ...
```
