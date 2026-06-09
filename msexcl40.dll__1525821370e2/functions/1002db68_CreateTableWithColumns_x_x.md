# CreateTableWithColumns(x,x)

- ea: `0x1002db68`
- end: `0x1002df5a`
- name: `_CreateTableWithColumns@8`
- size: `1010`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10029590`
- `0x10029730`
- `0x1002a530`
- `0x1002cd40`
- `0x1002d380`
- `0x1002e5d0`

## callees

- `0x10006400`
- `0x10016680`
- `0x1001b4b0`
- `0x1001b5e0`
- `0x1001b900`
- `0x1001bb70`
- `0x1001c2b0`
- `0x1001e2b0`
- `0x1002580a`
- `0x10025ab7`
- `0x1002db02`
- `0x1002db68`
- `0x10031f44`
- `0x10031fb7`
- `0x100321bc`
- `0x10032387`
- `0x10032705`
- `0x10035510`

## string_xrefs

- `0x1002de8c`: `[Microsoft JET Created Table]`

## pseudocode

```c
int __fastcall CreateTableWithColumns(_DWORD *a1, int a2)
{
  _DWORD *v2; // esi
  int *v3; // ebx
  int v4; // eax
  int v5; // ecx
  int v6; // ecx
  int updated; // edi
  _DWORD *v9; // eax
  _DWORD *v10; // ecx
  _DWORD *v11; // edi
  int v12; // ecx
  _DWORD *v13; // ecx
  _WORD *v14; // edx
  unsigned __int16 v15; // ax
  unsigned __int16 v16; // cx
  _DWORD *v17; // ecx
  int v18; // ebx
  int v19; // eax
  int v20; // edi
  int v21; // edx
  __int16 *v22; // ecx
  __int16 v23; // ax
  int v24; // edx
  int *v25; // edi
  int v26; // eax
  unsigned int v27; // edi
  _WORD *v28; // eax
  _WORD *v29; // ebx
  wchar_t *v30; // edi
  int v31; // ebx
  wchar_t *v32; // edi
  size_t v33; // ebx
  _DWORD *v34; // esi
  __int16 v35; // ax
  void *v36; // eax
  _DWORD *v37; // ebx
  int v38; // [esp+10h] [ebp-68h] BYREF
  int v39; // [esp+14h] [ebp-64h] BYREF
  int v40; // [esp+18h] [ebp-60h]
  _DWORD *v41; // [esp+1Ch] [ebp-5Ch] BYREF
  int v42; // [esp+20h] [ebp-58h]
  int v43; // [esp+24h] [ebp-54h]
  int v44; // [esp+28h] [ebp-50h]
  _DWORD *v45; // [esp+2Ch] [ebp-4Ch]
  _WORD v46[34]; // [esp+30h] [ebp-48h] BYREF

  v2 = a1;
  v38 = a2;
  v45 = a1;
  v43 = 0;
  if ( !a1[9] || a1[20] )
    return -1312;
  v3 = (int *)a1[1];
  v4 = a1[17];
  v42 = v4;
  v5 = v3[3];
  if ( *(_DWORD *)(v5 + 4) == 3 || *(_DWORD *)(v5 + 4) == 4 )
  {
    v13 = v2 + 3;
    if ( !v2[3] )
    {
      v2[2] = v3[7];
      updated = WorkbookSheetOpen((_DWORD *)v3[3], v3[7] + 14, (int)(v2 + 3), v2 + 3);
      if ( updated < 0 )
        goto LABEL_8;
      v4 = v42;
      v13 = v2 + 3;
    }
    if ( !v4 )
    {
LABEL_21:
      WorkbookCurrentDimensions(*v13, v2[2] + 4);
      v14 = (_WORD *)v2[2];
      if ( v14[2] || v14[4] || v14[3] || v14[5] )
      {
        *((_WORD *)v2 + 49) = dword_1003C2EA;
        *((_WORD *)v2 + 51) = *((_WORD *)v2 + 18) - 1;
        v16 = v14[4] + dword_1003C2D8 + 1;
        *((_WORD *)v2 + 48) = v16;
        if ( v16 > *((_WORD *)&dword_1003C2FA + v3[4]) )
        {
          updated = -5037;
          goto LABEL_8;
        }
        v15 = v16;
      }
      else
      {
        *((_WORD *)v2 + 49) = dword_1003C2EA;
        *((_WORD *)v2 + 51) = *((_WORD *)v2 + 18) - 1;
        v15 = *((_WORD *)&dword_1003C2EE + v3[4] + 1);
        *((_WORD *)v2 + 48) = v15;
      }
      goto LABEL_30;
    }
  }
  else if ( !v4 )
  {
    WorkbookMakeValidSheetName(v5, (const unsigned __int16 *)v2 + 52, (int)v46, v5, v3[3]);
    v41 = (_DWORD *)MemAllocate(528);
    if ( !v41 )
    {
LABEL_7:
      updated = -1011;
LABEL_8:
      v2[16] = 0;
      v2[14] = 0;
      return updated;
    }
    updated = WorkbookSheetAppend((_DWORD *)v3[3], v46, v6);
    if ( updated )
    {
      MemFree(v41);
      goto LABEL_8;
    }
    v9 = (_DWORD *)v3[7];
    if ( v9 )
    {
      do
      {
        v10 = v9;
        v9 = (_DWORD *)*v9;
      }
      while ( v9 );
      v11 = v41;
      *v10 = v41;
    }
    else
    {
      v11 = v41;
      v3[7] = (int)v41;
    }
    *((_BYTE *)v11 + 12) = 1;
    WCSCPY2((_WORD *)v11 + 7, v46, 0x100u);
    v2[2] = v11;
    updated = WorkbookSheetOpen((_DWORD *)v3[3], (int)v46, v12, &v39);
    if ( updated < 0 )
      goto LABEL_8;
    v13 = v2 + 3;
    v2[3] = v39;
    goto LABEL_21;
  }
  *((_WORD *)v2 + 51) = *((_WORD *)v2 + 18) + *((_WORD *)v2 + 49) - 1;
  v15 = *((_WORD *)v2 + 48);
LABEL_30:
  *((_WORD *)v2 + 50) = v15;
  v17 = (_DWORD *)v2[4];
  if ( v17 )
  {
    MemFree(v17);
    v2[4] = 0;
  }
  updated = WorkbookRangeCreate(v2[24], v2[25]);
  if ( updated < 0 )
    goto LABEL_8;
  v18 = v38;
  v19 = 0;
  *(_DWORD *)(v38 + 30) = 0;
  v20 = v2[10];
  while ( 1 )
  {
    v39 = v20;
    if ( !v20 )
      break;
    *(_WORD *)(v20 + 28) = v19;
    v40 = v19 + 1;
    if ( !v42 || CellStatus(&v38, &v41, 6) == 1 )
    {
      v21 = -1;
      v38 = -1;
    }
    else
    {
      v21 = v38;
    }
    v22 = (__int16 *)(v20 + 42);
    v44 = v20 + 44;
    do
      v23 = *v22++;
    while ( v23 != (_WORD)v43 );
    updated = CopyPutAlpha(v18, v20, v21, (char *)(v20 + 42), 2 * (((int)v22 - v44) >> 1));
    if ( updated )
    {
      CopyBufferClear(v18);
      goto LABEL_8;
    }
    v25 = (int *)v39;
    LOWORD(v24) = *(_WORD *)(v39 + 28);
    v26 = CopyBufferCellForCol(*(_DWORD *)(v18 + 40), v24);
    *(_WORD *)(v26 + 8) |= 0x400u;
    v20 = *v25;
    v19 = v40;
  }
  updated = UpdateRecord(v18, v42 == 0, *(_DWORD *)(v18 + 30));
  CopyBufferClear(v18);
  if ( updated )
    goto LABEL_8;
  v2[14] = 0;
  v2[11] = 1;
  v2[16] = 1;
  v40 = 2 * v2[9] + 33;
  v27 = v40;
  v28 = (_WORD *)MemAllocate(2 * v40);
  v29 = v28;
  v38 = (int)v28;
  if ( !v28 )
    goto LABEL_7;
  WCSCPY2(v28, L"[Microsoft JET Created Table]", v27);
  v30 = v29 + 29;
  v31 = v40 - 29;
  StringCchPrintfW(v30, v40 - 29, L"%03d", v2[9]);
  v32 = v30 + 3;
  v33 = v31 - 3;
  if ( v2[10] )
  {
    v34 = (_DWORD *)v2[10];
    do
    {
      StringCchPrintfW(v32, v33, L"%02d", v34[4]);
      v34 = (_DWORD *)*v34;
      v32 += 2;
      v33 -= 2;
    }
    while ( v34 );
    v2 = v45;
  }
  v35 = *((_WORD *)v2 + 48);
  if ( *(_DWORD *)(v2[3] + 12) )
  {
    v36 = 0;
    v37 = (_DWORD *)v38;
  }
  else
  {
    v37 = (_DWORD *)v38;
    HIWORD(v39) = *((_WORD *)v2 + 49);
    LOWORD(v39) = v35;
    v36 = (void *)ExcelAddNote(v39);
  }
  updated = TranslateEXErrorToJETError(v36);
  MemFree(v37);
  if ( updated < 0 )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x1002db68  mov     edi, edi
0x1002db6a  push    ebp
0x1002db6b  mov     ebp, esp
0x1002db6d  and     esp, 0FFFFFFF8h
0x1002db70  sub     esp, 6Ch
0x1002db73  mov     eax, ___security_cookie
0x1002db78  xor     eax, esp
0x1002db7a  mov     [esp+6Ch+var_4], eax
0x1002db7e  push    ebx
0x1002db7f  push    esi
0x1002db80  mov     esi, ecx
0x1002db82  mov     [esp+74h+var_68], edx
0x1002db86  xor     edx, edx
0x1002db88  mov     [esp+74h+var_4C], esi
0x1002db8c  push    edi
0x1002db8d  mov     [esp+78h+var_54], edx
0x1002db91  cmp     [esi+24h], edx
0x1002db94  jz      loc_1002DF43
0x1002db9a  cmp     [esi+50h], edx
0x1002db9d  jnz     loc_1002DF43
0x1002dba3  mov     ebx, [esi+4]
0x1002dba6  mov     eax, [esi+44h]
0x1002dba9  mov     [esp+78h+var_58], eax
0x1002dbad  mov     ecx, [ebx+0Ch]
0x1002dbb0  cmp     dword ptr [ecx+4], 3
0x1002dbb4  jz      loc_1002DC78
0x1002dbba  cmp     dword ptr [ecx+4], 4
0x1002dbbe  jz      loc_1002DC78
0x1002dbc4  test    eax, eax
0x1002dbc6  jnz     loc_1002DD42
0x1002dbcc  push    ecx
0x1002dbcd  push    ecx
0x1002dbce  lea     eax, [esp+80h+var_48]
0x1002dbd2  push    eax
0x1002dbd3  lea     edx, [esi+68h]
0x1002dbd6  call    _WorkbookMakeValidSheetName@20; WorkbookMakeValidSheetName(x,x,x,x,x)
0x1002dbdb  mov     ecx, 210h
0x1002dbe0  call    _MemAllocate@4; MemAllocate(x)
0x1002dbe5  mov     [esp+78h+var_5C], eax
0x1002dbe9  test    eax, eax
0x1002dbeb  jnz     short loc_1002DC01
0x1002dbed  mov     edi, 0FFFFFC0Dh
0x1002dbf2  xor     eax, eax
0x1002dbf4  mov     [esi+40h], eax
0x1002dbf7  mov     [esi+38h], eax
0x1002dbfa  mov     eax, edi
0x1002dbfc  jmp     loc_1002DF48
0x1002dc01  push    ecx
0x1002dc02  mov     ecx, [ebx+0Ch]
0x1002dc05  lea     edx, [esp+7Ch+var_48]
0x1002dc09  call    _WorkbookSheetAppend@12; WorkbookSheetAppend(x,x,x)
0x1002dc0e  mov     edi, eax
0x1002dc10  test    edi, edi
0x1002dc12  jz      short loc_1002DC1F
0x1002dc14  mov     ecx, [esp+78h+var_5C]
0x1002dc18  call    _MemFree@4; MemFree(x)
0x1002dc1d  jmp     short loc_1002DBF2
0x1002dc1f  mov     eax, [ebx+1Ch]
0x1002dc22  test    eax, eax
0x1002dc24  jz      short loc_1002DC36
0x1002dc26  lea     ecx, [eax]
0x1002dc28  mov     eax, [eax]
0x1002dc2a  test    eax, eax
0x1002dc2c  jnz     short loc_1002DC26
0x1002dc2e  mov     edi, [esp+78h+var_5C]
0x1002dc32  mov     [ecx], edi
0x1002dc34  jmp     short loc_1002DC3D
0x1002dc36  mov     edi, [esp+78h+var_5C]
0x1002dc3a  mov     [ebx+1Ch], edi
0x1002dc3d  push    100h
0x1002dc42  lea     ecx, [edi+0Eh]
0x1002dc45  mov     byte ptr [edi+0Ch], 1
0x1002dc49  lea     edx, [esp+7Ch+var_48]
0x1002dc4d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002dc52  lea     eax, [esp+78h+var_64]
0x1002dc56  mov     [esi+8], edi
0x1002dc59  push    eax
0x1002dc5a  push    ecx
0x1002dc5b  mov     ecx, [ebx+0Ch]
0x1002dc5e  lea     edx, [esp+80h+var_48]
0x1002dc62  call    _WorkbookSheetOpen@16; WorkbookSheetOpen(x,x,x,x)
0x1002dc67  mov     edi, eax
0x1002dc69  test    edi, edi
0x1002dc6b  js      short loc_1002DBF2
0x1002dc6d  mov     eax, [esp+78h+var_64]
0x1002dc71  lea     ecx, [esi+0Ch]
0x1002dc74  mov     [ecx], eax
0x1002dc76  jmp     short loc_1002DCAE
0x1002dc78  lea     ecx, [esi+0Ch]
0x1002dc7b  cmp     [ecx], edx
0x1002dc7d  jnz     short loc_1002DCA6
0x1002dc7f  mov     eax, [ebx+1Ch]
0x1002dc82  mov     [esi+8], eax
0x1002dc85  mov     edx, [ebx+1Ch]
0x1002dc88  push    ecx
0x1002dc89  push    ecx
0x1002dc8a  mov     ecx, [ebx+0Ch]
0x1002dc8d  add     edx, 0Eh
0x1002dc90  call    _WorkbookSheetOpen@16; WorkbookSheetOpen(x,x,x,x)
0x1002dc95  mov     edi, eax
0x1002dc97  test    edi, edi
0x1002dc99  js      loc_1002DBF2
0x1002dc9f  mov     eax, [esp+78h+var_58]
0x1002dca3  lea     ecx, [esi+0Ch]
0x1002dca6  test    eax, eax
0x1002dca8  jnz     loc_1002DD42
0x1002dcae  mov     edx, [esi+8]
0x1002dcb1  mov     ecx, [ecx]
0x1002dcb3  add     edx, 4
0x1002dcb6  call    _WorkbookCurrentDimensions@8; WorkbookCurrentDimensions(x,x)
0x1002dcbb  mov     edx, [esi+8]
0x1002dcbe  xor     eax, eax
0x1002dcc0  cmp     [edx+4], ax
0x1002dcc4  jnz     short loc_1002DCFD
0x1002dcc6  cmp     [edx+8], ax
0x1002dcca  jnz     short loc_1002DCFD
0x1002dccc  cmp     [edx+6], ax
0x1002dcd0  jnz     short loc_1002DCFD
0x1002dcd2  cmp     [edx+0Ah], ax
0x1002dcd6  jnz     short loc_1002DCFD
0x1002dcd8  mov     ax, word ptr dword_1003C2EA
0x1002dcde  mov     [esi+62h], ax
0x1002dce2  mov     ax, [esi+24h]
0x1002dce6  dec     ax
0x1002dce8  mov     [esi+66h], ax
0x1002dcec  mov     eax, [ebx+10h]
0x1002dcef  movzx   eax, word ptr (dword_1003C2EE+2)[eax*2]
0x1002dcf7  mov     [esi+60h], ax
0x1002dcfb  jmp     short loc_1002DD3D
0x1002dcfd  mov     ax, word ptr dword_1003C2EA
0x1002dd03  mov     [esi+62h], ax
0x1002dd07  mov     ax, [esi+24h]
0x1002dd0b  dec     ax
0x1002dd0d  mov     [esi+66h], ax
0x1002dd11  mov     ecx, dword_1003C2D8
0x1002dd17  inc     cx
0x1002dd19  add     cx, [edx+8]
0x1002dd1d  movzx   edx, cx
0x1002dd20  mov     [esi+60h], dx
0x1002dd24  mov     eax, [ebx+10h]
0x1002dd27  cmp     cx, word ptr dword_1003C2FA[eax*2]
0x1002dd2f  jbe     short loc_1002DD3B
0x1002dd31  mov     edi, 0FFFFEC53h
0x1002dd36  jmp     loc_1002DBF2
0x1002dd3b  mov     eax, edx
0x1002dd3d  movzx   eax, ax
0x1002dd40  jmp     short loc_1002DD54
0x1002dd42  mov     ax, [esi+62h]
0x1002dd46  dec     ax
0x1002dd48  add     ax, [esi+24h]
0x1002dd4c  mov     [esi+66h], ax
0x1002dd50  movzx   eax, word ptr [esi+60h]
0x1002dd54  push    64h ; 'd'
0x1002dd56  mov     ecx, esi
0x1002dd58  lea     edi, [esi+10h]
0x1002dd5b  pop     edx
0x1002dd5c  mov     [ecx+edx], ax
0x1002dd60  mov     ecx, [edi]
0x1002dd62  test    ecx, ecx
0x1002dd64  jz      short loc_1002DD71
0x1002dd66  call    _MemFree@4; MemFree(x)
0x1002dd6b  mov     dword ptr [edi], 0
0x1002dd71  push    dword ptr [esi+64h]
0x1002dd74  mov     ecx, [esi+0Ch]
0x1002dd77  mov     edx, edi
0x1002dd79  push    dword ptr [esi+60h]
0x1002dd7c  call    _WorkbookRangeCreate@16; WorkbookRangeCreate(x,x,x,x)
0x1002dd81  mov     edi, eax
0x1002dd83  test    edi, edi
0x1002dd85  js      loc_1002DBF2
0x1002dd8b  mov     ebx, [esp+78h+var_68]
0x1002dd8f  xor     eax, eax
0x1002dd91  mov     [ebx+1Eh], eax
0x1002dd94  mov     edi, [esi+28h]
0x1002dd97  jmp     loc_1002DE2B
0x1002dd9c  mov     [edi+1Ch], ax
0x1002dda0  inc     eax
0x1002dda1  cmp     [esp+78h+var_58], 0
0x1002dda6  mov     [esp+78h+var_60], eax
0x1002ddaa  jz      short loc_1002DDCC
0x1002ddac  push    6
0x1002ddae  lea     eax, [esp+7Ch+var_5C]
0x1002ddb2  mov     edx, edi
0x1002ddb4  push    eax
0x1002ddb5  lea     eax, [esp+80h+var_68]
0x1002ddb9  mov     ecx, ebx
0x1002ddbb  push    eax
0x1002ddbc  call    _CellStatus@20; CellStatus(x,x,x,x,x)
0x1002ddc1  cmp     eax, 1
0x1002ddc4  jz      short loc_1002DDCC
0x1002ddc6  mov     edx, [esp+78h+var_68]
0x1002ddca  jmp     short loc_1002DDD3
0x1002ddcc  or      edx, 0FFFFFFFFh
0x1002ddcf  mov     [esp+78h+var_68], edx
0x1002ddd3  lea     ecx, [edi+2Ah]
0x1002ddd6  lea     eax, [ecx+2]
0x1002ddd9  mov     [esp+78h+var_50], eax
0x1002dddd  mov     ax, [ecx]
0x1002dde0  add     ecx, 2
0x1002dde3  cmp     ax, word ptr [esp+78h+var_54]
0x1002dde8  jnz     short loc_1002DDDD
0x1002ddea  sub     ecx, [esp+78h+var_50]
0x1002ddee  sar     ecx, 1
0x1002ddf0  lea     eax, [ecx+ecx]
0x1002ddf3  mov     ecx, ebx
0x1002ddf5  push    eax
0x1002ddf6  lea     eax, [edi+2Ah]
0x1002ddf9  push    eax
0x1002ddfa  push    edx
0x1002ddfb  mov     edx, edi
0x1002ddfd  call    _CopyPutAlpha@20; CopyPutAlpha(x,x,x,x,x)
0x1002de02  mov     edi, eax
0x1002de04  test    edi, edi
0x1002de06  jnz     loc_1002DEFF
0x1002de0c  mov     edi, [esp+78h+var_64]
0x1002de10  mov     ecx, [ebx+28h]
0x1002de13  mov     dx, [edi+1Ch]
0x1002de17  call    _CopyBufferCellForCol@8; CopyBufferCellForCol(x,x)
0x1002de1c  mov     ecx, 400h
0x1002de21  or      [eax+8], cx
0x1002de25  mov     edi, [edi]
0x1002de27  mov     eax, [esp+78h+var_60]
0x1002de2b  mov     [esp+78h+var_64], edi
0x1002de2f  test    edi, edi
0x1002de31  jnz     loc_1002DD9C
0x1002de37  push    dword ptr [ebx+1Eh]
0x1002de3a  xor     edx, edx
0x1002de3c  mov     ecx, ebx
0x1002de3e  cmp     [esp+7Ch+var_58], edx
0x1002de42  jnz     short loc_1002DE45
0x1002de44  inc     edx
0x1002de45  call    _UpdateRecord@12; UpdateRecord(x,x,x)
0x1002de4a  mov     ecx, ebx
0x1002de4c  mov     edi, eax
0x1002de4e  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002de53  test    edi, edi
0x1002de55  jnz     loc_1002DBF2
0x1002de5b  xor     eax, eax
0x1002de5d  mov     [esi+38h], edi
0x1002de60  inc     eax
0x1002de61  mov     [esi+2Ch], eax
0x1002de64  mov     [esi+40h], eax
0x1002de67  mov     eax, [esi+24h]
0x1002de6a  lea     edi, ds:21h[eax*2]
0x1002de71  lea     ecx, [edi+edi]
0x1002de74  mov     [esp+78h+var_60], edi
0x1002de78  call    _MemAllocate@4; MemAllocate(x)
0x1002de7d  mov     ebx, eax
0x1002de7f  mov     [esp+78h+var_68], ebx
0x1002de83  test    ebx, ebx
0x1002de85  jz      loc_1002DBED
0x1002de8b  push    edi
0x1002de8c  mov     edx, offset aMicrosoftJetCr; "[Microsoft JET Created Table]"
0x1002de91  mov     ecx, ebx
0x1002de93  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002de98  push    dword ptr [esi+24h]
0x1002de9b  lea     edi, [ebx+3Ah]
0x1002de9e  mov     ebx, [esp+7Ch+var_60]
0x1002dea2  push    offset a03d; "%03d"
0x1002dea7  add     ebx, 0FFFFFFE3h
0x1002deaa  push    ebx; cchDest
0x1002deab  push    edi; pszDest
0x1002deac  call    _StringCchPrintfW
0x1002deb1  mov     eax, [esi+28h]
0x1002deb4  add     esp, 10h
0x1002deb7  add     edi, 6
0x1002deba  sub     ebx, 3
0x1002debd  test    eax, eax
0x1002debf  jz      short loc_1002DEE5
0x1002dec1  mov     esi, eax
0x1002dec3  push    dword ptr [esi+10h]
0x1002dec6  push    offset a02d; "%02d"
0x1002decb  push    ebx; cchDest
0x1002decc  push    edi; pszDest
0x1002decd  call    _StringCchPrintfW
0x1002ded2  mov     esi, [esi]
0x1002ded4  add     esp, 10h
0x1002ded7  add     edi, 4
0x1002deda  sub     ebx, 2
0x1002dedd  test    esi, esi
0x1002dedf  jnz     short loc_1002DEC3
0x1002dee1  mov     esi, [esp+78h+var_4C]
0x1002dee5  mov     ecx, [esi+0Ch]
0x1002dee8  xor     ebx, ebx
0x1002deea  movzx   eax, word ptr [esi+60h]
0x1002deee  movzx   edx, word ptr [esi+62h]
0x1002def2  cmp     [ecx+0Ch], ebx
0x1002def5  jz      short loc_1002DF0B
0x1002def7  mov     eax, ebx
0x1002def9  mov     ebx, [esp+78h+var_68]
0x1002defd  jmp     short loc_1002DF27
0x1002deff  mov     ecx, ebx
0x1002df01  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002df06  jmp     loc_1002DBF2
0x1002df0b  mov     ebx, [esp+78h+var_68]
0x1002df0f  mov     ecx, [ecx+8]
0x1002df12  mov     word ptr [esp+78h+var_64+2], dx
0x1002df17  mov     edx, ebx
0x1002df19  mov     word ptr [esp+78h+var_64], ax
0x1002df1e  push    [esp+78h+var_64]
  ... truncated ...
```
