# ExcelOpenSheet(x,x,x,x)

- ea: `0x10011a70`
- end: `0x10011dc2`
- name: `_ExcelOpenSheet@16`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1001b4b0`

## callees

- `0x1000daa0`
- `0x1000dcc0`
- `0x1000df70`
- `0x1000f470`
- `0x1000fdf0`
- `0x10011a70`
- `0x1002580a`
- `0x10025ab7`
- `0x10025f86`

## pseudocode

```c
int __fastcall ExcelOpenSheet(int a1, const unsigned __int16 *a2, int a3, _DWORD *a4)
{
  int v6; // esi
  int v7; // eax
  int result; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // ecx
  _DWORD *v11; // edx
  int v12; // eax
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int RecordHeader; // ebx
  int v17; // ecx
  __int16 *v18; // ecx
  _DWORD *v19; // ecx
  _BYTE v20[4]; // [esp+10h] [ebp-20h] BYREF
  _BYTE v21[4]; // [esp+14h] [ebp-1Ch] BYREF
  _BYTE v22[4]; // [esp+18h] [ebp-18h] BYREF
  _DWORD *v23; // [esp+1Ch] [ebp-14h]
  int v24; // [esp+20h] [ebp-10h] BYREF
  int v25; // [esp+24h] [ebp-Ch] BYREF
  _DWORD *v26; // [esp+28h] [ebp-8h]
  __int16 v27[2]; // [esp+2Ch] [ebp-4h] BYREF

  v6 = *(_DWORD *)(a1 + 64);
  if ( !v6 )
    return -22;
  while ( 1 )
  {
    v7 = wcscmp((const unsigned __int16 *)(v6 + 56), a2);
    if ( v7 )
      v7 = v7 < 0 ? -1 : 1;
    if ( !v7 )
      break;
    v6 = *(_DWORD *)v6;
    if ( !v6 )
      return -22;
  }
  v9 = (_DWORD *)MemAllocate(52);
  v10 = v9;
  v26 = v9;
  if ( !v9 )
    return -2;
  *v9 = 1;
  v11 = (_DWORD *)(v6 + 36);
  v9[1] = *(_DWORD *)(a1 + 4);
  v9[2] = *(_DWORD *)(a1 + 8);
  v9[3] = *(_DWORD *)(a1 + 12);
  v9[4] = *(_DWORD *)(a1 + 16);
  v9[5] = *(_DWORD *)(a1 + 20);
  v9[9] = *(_DWORD *)(a1 + 36);
  v9[10] = *(_DWORD *)(a1 + 68);
  v9[11] = a1;
  v9[12] = v6;
  *(_DWORD *)(a1 + 68) = v9;
  v12 = *(_DWORD *)(v6 + 36);
  v23 = (_DWORD *)(v6 + 36);
  if ( v12 )
  {
    *v11 = v12 + 1;
    *a4 = v10;
    return 0;
  }
  *v11 = 1;
  v13 = a1;
  if ( *(_DWORD *)a1 == 1 )
    v13 = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(v13 + 104) = 0;
  *(_WORD *)(v13 + 96) = 0x4000;
  v14 = *(_DWORD *)(a1 + 40);
  v15 = *(_DWORD *)(v6 + 4);
  if ( v14 )
  {
    if ( !v15 )
      v15 = *(_DWORD *)(v14 + 4);
    *(_DWORD *)(v14 + 8) = v15;
  }
  else
  {
    BFSetFilePosition(*(int **)(a1 + 20), 0, *(_DWORD *)(v6 + 4));
  }
  if ( ExcelReadRecordHeader(a1, v27) )
  {
    RecordHeader = -10;
LABEL_57:
    v18 = *(__int16 **)(v6 + 40);
    *v23 = 0;
    if ( v18 )
      ExcelFreeCellIndex(v18);
    v19 = v26;
    *(_DWORD *)(v6 + 40) = 0;
    *(_DWORD *)(v6 + 48) = 0;
    *(_DWORD *)(a1 + 68) = *(_DWORD *)(*(_DWORD *)(a1 + 68) + 40);
    MemFree(v19);
    return RecordHeader;
  }
  result = ExcelReadTotalRecord(a1, v27, &v25);
  if ( result )
    return result;
  ParseBOFRecord(v25, v20, &v24, v21, v22);
  if ( v24 == 32 || v24 == 6 )
    return -24;
  RecordHeader = ExcelReadRecordHeader(a1, v27);
  if ( RecordHeader )
    goto LABEL_57;
  while ( 1 )
  {
    switch ( v27[0] )
    {
      case 47:
        RecordHeader = -12;
        goto LABEL_57;
      case 94:
        *(_DWORD *)(v6 + 48) = 1;
        goto LABEL_47;
      case 523:
        RecordHeader = LoadCellIndex(a1, v6, v27);
        if ( RecordHeader )
          goto LABEL_57;
        goto LABEL_50;
    }
    if ( v27[0] == 10
      || v27[0] == 516
      || v27[0] == 638
      || v27[0] == 515
      || v27[0] == 189
      || v27[0] == 190
      || v27[0] == 513
      || v27[0] == 517
      || v27[0] == 214
      || v27[0] == 253
      || v27[0] == 518
      || v27[0] == 1030
      || v27[0] == 6
      || v27[0] == 519
      || v27[0] == 545
      || v27[0] == 1212 )
    {
      break;
    }
LABEL_47:
    v17 = *(_DWORD *)(a1 + 40);
    if ( v17 )
      *(_DWORD *)(v17 + 8) = **(_DWORD **)(v17 + 8);
    else
      BFSetFilePosition(*(int **)(a1 + 20), 1, v27[1]);
LABEL_50:
    RecordHeader = ExcelReadRecordHeader(a1, v27);
    if ( RecordHeader )
      goto LABEL_57;
  }
  if ( !*(_DWORD *)(v6 + 40) && !*(_DWORD *)(a1 + 40) )
  {
    RecordHeader = -11;
    goto LABEL_57;
  }
  *a4 = v26;
  return 0;
}

```

## disassembly

```asm
0x10011a70  mov     edi, edi
0x10011a72  push    ebp
0x10011a73  mov     ebp, esp
0x10011a75  sub     esp, 24h
0x10011a78  push    ebx
0x10011a79  push    esi
0x10011a7a  push    edi
0x10011a7b  mov     edi, ecx
0x10011a7d  mov     ebx, edx
0x10011a7f  mov     esi, [edi+40h]
0x10011a82  test    esi, esi
0x10011a84  jz      short loc_10011AC5
0x10011a86  mov     eax, ebx
0x10011a88  lea     ecx, [esi+38h]
0x10011a8b  nop     dword ptr [eax+eax+00h]
0x10011a90  mov     dx, [ecx]
0x10011a93  cmp     dx, [eax]
0x10011a96  jnz     short loc_10011AB6
0x10011a98  test    dx, dx
0x10011a9b  jz      short loc_10011AB2
0x10011a9d  mov     dx, [ecx+2]
0x10011aa1  cmp     dx, [eax+2]
0x10011aa5  jnz     short loc_10011AB6
0x10011aa7  add     ecx, 4
0x10011aaa  add     eax, 4
0x10011aad  test    dx, dx
0x10011ab0  jnz     short loc_10011A90
0x10011ab2  xor     eax, eax
0x10011ab4  jmp     short loc_10011ABB
0x10011ab6  sbb     eax, eax
0x10011ab8  or      eax, 1
0x10011abb  test    eax, eax
0x10011abd  jz      short loc_10011AD3
0x10011abf  mov     esi, [esi]
0x10011ac1  test    esi, esi
0x10011ac3  jnz     short loc_10011A86
0x10011ac5  mov     eax, 0FFFFFFEAh
0x10011aca  pop     edi
0x10011acb  pop     esi
0x10011acc  pop     ebx
0x10011acd  mov     esp, ebp
0x10011acf  pop     ebp
0x10011ad0  retn    8
0x10011ad3  mov     ecx, 34h ; '4'
0x10011ad8  call    _MemAllocate@4; MemAllocate(x)
0x10011add  mov     ecx, eax
0x10011adf  mov     [ebp+var_8], ecx
0x10011ae2  test    ecx, ecx
0x10011ae4  jnz     short loc_10011AF2
0x10011ae6  lea     eax, [ecx-2]
0x10011ae9  pop     edi
0x10011aea  pop     esi
0x10011aeb  pop     ebx
0x10011aec  mov     esp, ebp
0x10011aee  pop     ebp
0x10011aef  retn    8
0x10011af2  mov     dword ptr [ecx], 1
0x10011af8  lea     edx, [esi+24h]
0x10011afb  mov     eax, [edi+4]
0x10011afe  mov     [ecx+4], eax
0x10011b01  mov     eax, [edi+8]
0x10011b04  mov     [ecx+8], eax
0x10011b07  mov     eax, [edi+0Ch]
0x10011b0a  mov     [ecx+0Ch], eax
0x10011b0d  mov     eax, [edi+10h]
0x10011b10  mov     [ecx+10h], eax
0x10011b13  mov     eax, [edi+14h]
0x10011b16  mov     [ecx+14h], eax
0x10011b19  mov     eax, [edi+24h]
0x10011b1c  mov     [ecx+24h], eax
0x10011b1f  mov     eax, [edi+44h]
0x10011b22  mov     [ecx+28h], eax
0x10011b25  mov     [ecx+2Ch], edi
0x10011b28  mov     [ecx+30h], esi
0x10011b2b  mov     [edi+44h], ecx
0x10011b2e  mov     eax, [edx]
0x10011b30  mov     [ebp+var_14], edx
0x10011b33  test    eax, eax
0x10011b35  jz      short loc_10011B4A
0x10011b37  inc     eax
0x10011b38  mov     [edx], eax
0x10011b3a  mov     eax, [ebp+arg_4]
0x10011b3d  mov     [eax], ecx
0x10011b3f  xor     eax, eax
0x10011b41  pop     edi
0x10011b42  pop     esi
0x10011b43  pop     ebx
0x10011b44  mov     esp, ebp
0x10011b46  pop     ebp
0x10011b47  retn    8
0x10011b4a  mov     dword ptr [edx], 1
0x10011b50  mov     eax, edi
0x10011b52  cmp     dword ptr [edi], 1
0x10011b55  jnz     short loc_10011B5A
0x10011b57  mov     eax, [edi+2Ch]
0x10011b5a  mov     ecx, 4000h
0x10011b5f  mov     dword ptr [eax+68h], 0
0x10011b66  mov     [eax+60h], cx
0x10011b6a  mov     ecx, [edi+28h]
0x10011b6d  mov     eax, [esi+4]
0x10011b70  test    ecx, ecx
0x10011b72  jz      short loc_10011B80
0x10011b74  test    eax, eax
0x10011b76  jnz     short loc_10011B7B
0x10011b78  mov     eax, [ecx+4]
0x10011b7b  mov     [ecx+8], eax
0x10011b7e  jmp     short loc_10011B8B
0x10011b80  mov     ecx, [edi+14h]
0x10011b83  xor     edx, edx
0x10011b85  push    eax
0x10011b86  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10011b8b  lea     edx, [ebp+var_4]
0x10011b8e  mov     ecx, edi
0x10011b90  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10011b95  test    eax, eax
0x10011b97  jz      short loc_10011BA3
0x10011b99  mov     ebx, 0FFFFFFF6h
0x10011b9e  jmp     loc_10011D75
0x10011ba3  lea     eax, [ebp+var_C]
0x10011ba6  mov     ecx, edi
0x10011ba8  push    eax
0x10011ba9  lea     edx, [ebp+var_4]
0x10011bac  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x10011bb1  test    eax, eax
0x10011bb3  jnz     loc_10011ACA
0x10011bb9  movsx   edx, word ptr [ebp+var_4]
0x10011bbd  lea     eax, [ebp+var_18]
0x10011bc0  push    eax
0x10011bc1  lea     eax, [ebp+var_1C]
0x10011bc4  mov     ecx, edi
0x10011bc6  push    eax
0x10011bc7  lea     eax, [ebp+var_10]
0x10011bca  push    eax
0x10011bcb  lea     eax, [ebp+var_20]
0x10011bce  push    eax
0x10011bcf  push    [ebp+var_C]
0x10011bd2  call    ParseBOFRecord
0x10011bd7  mov     eax, [ebp+var_10]
0x10011bda  cmp     eax, 20h ; ' '
0x10011bdd  jz      loc_10011DB4
0x10011be3  cmp     eax, 6
0x10011be6  jz      loc_10011DB4
0x10011bec  lea     edx, [ebp+var_4]
0x10011bef  mov     ecx, edi
0x10011bf1  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10011bf6  mov     ebx, eax
0x10011bf8  test    ebx, ebx
0x10011bfa  jnz     loc_10011D75
0x10011c00  mov     ecx, 20Bh
0x10011c05  lea     edx, [ecx-7]
0x10011c08  nop     dword ptr [eax+eax+00000000h]
0x10011c10  mov     eax, [ebp+var_4]
0x10011c13  cmp     ax, 2Fh ; '/'
0x10011c17  jz      loc_10011D70
0x10011c1d  cmp     ax, 5Eh ; '^'
0x10011c21  jnz     short loc_10011C2F
0x10011c23  mov     dword ptr [esi+30h], 1
0x10011c2a  jmp     loc_10011D07
0x10011c2f  cmp     ax, cx
0x10011c32  jnz     short loc_10011C50
0x10011c34  lea     eax, [ebp+var_4]
0x10011c37  mov     edx, esi
0x10011c39  push    eax
0x10011c3a  mov     ecx, edi
0x10011c3c  call    LoadCellIndex
0x10011c41  mov     ebx, eax
0x10011c43  test    ebx, ebx
0x10011c45  jnz     loc_10011D75
0x10011c4b  jmp     loc_10011D2A
0x10011c50  cmp     ax, 0Ah
0x10011c54  jz      loc_10011D48
0x10011c5a  cmp     ax, dx
0x10011c5d  jz      loc_10011D48
0x10011c63  mov     ecx, 27Eh
0x10011c68  cmp     ax, cx
0x10011c6b  jz      loc_10011D48
0x10011c71  mov     ecx, 203h
0x10011c76  cmp     ax, cx
0x10011c79  jz      loc_10011D48
0x10011c7f  mov     ecx, 0BDh
0x10011c84  cmp     ax, cx
0x10011c87  jz      loc_10011D48
0x10011c8d  mov     ecx, 0BEh
0x10011c92  cmp     ax, cx
0x10011c95  jz      loc_10011D48
0x10011c9b  mov     ecx, 201h
0x10011ca0  cmp     ax, cx
0x10011ca3  jz      loc_10011D48
0x10011ca9  mov     ecx, 205h
0x10011cae  cmp     ax, cx
0x10011cb1  jz      loc_10011D48
0x10011cb7  mov     ecx, 0D6h
0x10011cbc  cmp     ax, cx
0x10011cbf  jz      loc_10011D48
0x10011cc5  mov     ecx, 0FDh
0x10011cca  cmp     ax, cx
0x10011ccd  jz      short loc_10011D48
0x10011ccf  mov     ecx, 206h
0x10011cd4  cmp     ax, cx
0x10011cd7  jz      short loc_10011D48
0x10011cd9  mov     ecx, 406h
0x10011cde  cmp     ax, cx
0x10011ce1  jz      short loc_10011D48
0x10011ce3  cmp     ax, 6
0x10011ce7  jz      short loc_10011D48
0x10011ce9  mov     ecx, 207h
0x10011cee  cmp     ax, cx
0x10011cf1  jz      short loc_10011D48
0x10011cf3  mov     ecx, 221h
0x10011cf8  cmp     ax, cx
0x10011cfb  jz      short loc_10011D48
0x10011cfd  mov     ecx, 4BCh
0x10011d02  cmp     ax, cx
0x10011d05  jz      short loc_10011D48
0x10011d07  mov     ecx, [edi+28h]
0x10011d0a  test    ecx, ecx
0x10011d0c  jz      short loc_10011D18
0x10011d0e  mov     eax, [ecx+8]
0x10011d11  mov     eax, [eax]
0x10011d13  mov     [ecx+8], eax
0x10011d16  jmp     short loc_10011D2A
0x10011d18  movsx   eax, word ptr [ebp+var_4+2]
0x10011d1c  mov     edx, 1
0x10011d21  mov     ecx, [edi+14h]
0x10011d24  push    eax
0x10011d25  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10011d2a  lea     edx, [ebp+var_4]
0x10011d2d  mov     ecx, edi
0x10011d2f  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10011d34  mov     ecx, 20Bh
0x10011d39  mov     ebx, eax
0x10011d3b  lea     edx, [ecx-7]
0x10011d3e  test    ebx, ebx
0x10011d40  jz      loc_10011C10
0x10011d46  jmp     short loc_10011D75
0x10011d48  test    ebx, ebx
0x10011d4a  jnz     short loc_10011D75
0x10011d4c  cmp     [esi+28h], ebx
0x10011d4f  jnz     short loc_10011D5D
0x10011d51  cmp     [edi+28h], ebx
0x10011d54  jnz     short loc_10011D5D
0x10011d56  mov     ebx, 0FFFFFFF5h
0x10011d5b  jmp     short loc_10011D75
0x10011d5d  mov     eax, [ebp+arg_4]
0x10011d60  mov     ecx, [ebp+var_8]
0x10011d63  mov     [eax], ecx
0x10011d65  xor     eax, eax
0x10011d67  pop     edi
0x10011d68  pop     esi
0x10011d69  pop     ebx
0x10011d6a  mov     esp, ebp
0x10011d6c  pop     ebp
0x10011d6d  retn    8
0x10011d70  mov     ebx, 0FFFFFFF4h
0x10011d75  mov     eax, [ebp+var_14]
0x10011d78  mov     ecx, [esi+28h]
0x10011d7b  mov     dword ptr [eax], 0
0x10011d81  test    ecx, ecx
0x10011d83  jz      short loc_10011D8A
0x10011d85  call    _ExcelFreeCellIndex@4; ExcelFreeCellIndex(x)
0x10011d8a  mov     ecx, [ebp+var_8]
0x10011d8d  mov     dword ptr [esi+28h], 0
0x10011d94  mov     dword ptr [esi+30h], 0
0x10011d9b  mov     eax, [edi+44h]
0x10011d9e  mov     eax, [eax+28h]
0x10011da1  mov     [edi+44h], eax
0x10011da4  call    _MemFree@4; MemFree(x)
0x10011da9  mov     eax, ebx
0x10011dab  pop     edi
0x10011dac  pop     esi
0x10011dad  pop     ebx
0x10011dae  mov     esp, ebp
0x10011db0  pop     ebp
0x10011db1  retn    8
0x10011db4  pop     edi
0x10011db5  pop     esi
0x10011db6  mov     eax, 0FFFFFFE8h
0x10011dbb  pop     ebx
0x10011dbc  mov     esp, ebp
0x10011dbe  pop     ebp
0x10011dbf  retn    8
```
