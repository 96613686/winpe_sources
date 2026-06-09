# WorkbookCellWriteList(x,x,x,x,x)

- ea: `0x1001c090`
- end: `0x1001c2a6`
- name: `_WorkbookCellWriteList@20`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x10032705`

## callees

- `0x1000a1f0`
- `0x10018430`
- `0x10018550`
- `0x1001bd50`
- `0x1001bf00`
- `0x1001c090`
- `0x1001c2b0`
- `0x10020e70`

## pseudocode

```c
int __fastcall WorkbookCellWriteList(_DWORD *a1, DispatchDriver *a2, int a3, int a4, int a5)
{
  int v5; // esi
  int result; // eax
  void *v8; // ecx
  _DWORD *v9; // edi
  int v10; // ecx
  _DWORD *v11; // ecx
  int v12; // eax
  int v13; // eax
  _DWORD *v14; // edx
  unsigned __int16 v15; // di
  int v16; // ecx
  _DWORD *v17; // edx
  int v18; // ecx
  int v19; // edi
  _DWORD *i; // eax
  void *v21; // eax
  unsigned __int16 v22; // dx
  void *v23; // eax
  _WORD *v24; // eax
  unsigned __int16 v25; // cx
  int v26; // eax
  int v27; // [esp+14h] [ebp-14h]
  int v29; // [esp+1Ch] [ebp-Ch]
  unsigned __int16 v30; // [esp+20h] [ebp-8h]
  unsigned __int16 v31; // [esp+24h] [ebp-4h]

  v5 = a4;
  if ( !a4 )
    return -1003;
  if ( a1[3] )
  {
    v8 = (void *)XLOLECellWriteList((int)a1, a2, a3, (int *)a4);
    return TranslateEXErrorToJETError(v8);
  }
  v9 = (_DWORD *)a1[201];
  LOWORD(v27) = a3 + *(_WORD *)a2;
  HIWORD(v27) = HIWORD(a3);
  result = CheckForNeededXFRecords(v9, a4);
  if ( result )
    return result;
  v10 = a4;
  do
  {
    *(_BYTE *)(v10 + 4) += *((_BYTE *)a2 + 2);
    v10 = *(_DWORD *)v10;
  }
  while ( v10 );
  if ( a5 == 1 )
  {
    result = DetermineCellFormats(v27, a4);
    if ( result )
      return result;
  }
  v11 = (_DWORD *)a4;
  do
  {
    v12 = v11[3];
    switch ( v12 )
    {
      case -1:
        v13 = v9[15];
        break;
      case -2:
        v13 = v9[16];
        break;
      case -3:
        v13 = v9[17];
        break;
      default:
        goto LABEL_19;
    }
    v11[3] = v13;
LABEL_19:
    v14 = v11;
    v11 = (_DWORD *)*v11;
  }
  while ( v11 );
  v15 = v27;
  v30 = *(unsigned __int8 *)(a4 + 4);
  v31 = *((unsigned __int8 *)v14 + 4);
  v16 = a1[2];
  v17 = *(_DWORD **)(v16 + 48);
  if ( v17[5] )
  {
    v18 = *(_DWORD *)(v16 + 44);
    v19 = 0;
    v29 = v18;
    for ( i = *(_DWORD **)(v18 + 64); i; ++v19 )
    {
      if ( i == v17 )
        break;
      i = (_DWORD *)*i;
    }
    *(_DWORD *)(v18 + 44) = 1;
    v21 = (void *)ExcelMIWriteCellList(v27, a4);
    v22 = v27;
    v8 = v21;
    if ( !v21 && *(_DWORD *)(v29 + 48) && (unsigned __int16)v27 <= 0x3FFFu )
    {
      v23 = (void *)ExcelMIWriteCellList(v27, a4);
      v22 = v27;
      v8 = v23;
    }
    v15 = v27;
  }
  else
  {
    if ( a5 == 1 )
      v26 = EXInsertRecord(a4);
    else
      v26 = EXUpdateRecord(v16, (unsigned __int16)v27, a4);
    v22 = v27;
    v8 = (void *)v26;
  }
  do
  {
    *(_BYTE *)(v5 + 4) -= *((_BYTE *)a2 + 2);
    v5 = *(_DWORD *)v5;
  }
  while ( v5 );
  if ( v8 )
    return TranslateEXErrorToJETError(v8);
  v24 = (_WORD *)a1[199];
  v25 = v24[2];
  if ( v25 == 0xFFFF )
  {
    v24[3] = v30;
    v24[2] = v15;
    v24[5] = v31;
    goto LABEL_44;
  }
  if ( v30 < v24[3] )
    v24[3] = v30;
  if ( v31 > v24[5] )
    v24[5] = v31;
  if ( v15 < v25 )
    v24[2] = v15;
  if ( v22 > v24[4] )
LABEL_44:
    v24[4] = v22;
  a1[202] = 1;
  return 0;
}

```

## disassembly

```asm
0x1001c090  mov     edi, edi
0x1001c092  push    ebp
0x1001c093  mov     ebp, esp
0x1001c095  and     esp, 0FFFFFFF8h
0x1001c098  sub     esp, 1Ch
0x1001c09b  push    ebx
0x1001c09c  push    esi
0x1001c09d  mov     esi, [ebp+arg_4]
0x1001c0a0  mov     eax, ecx
0x1001c0a2  mov     [esp+24h+var_10], eax
0x1001c0a6  mov     ebx, edx
0x1001c0a8  push    edi
0x1001c0a9  test    esi, esi
0x1001c0ab  jnz     short loc_1001C0BB
0x1001c0ad  mov     eax, 0FFFFFC15h
0x1001c0b2  pop     edi
0x1001c0b3  pop     esi
0x1001c0b4  pop     ebx
0x1001c0b5  mov     esp, ebp
0x1001c0b7  pop     ebp
0x1001c0b8  retn    0Ch
0x1001c0bb  cmp     dword ptr [eax+0Ch], 0
0x1001c0bf  jz      short loc_1001C0DA
0x1001c0c1  push    esi
0x1001c0c2  push    [ebp+arg_0]
0x1001c0c5  call    _XLOLECellWriteList@16; XLOLECellWriteList(x,x,x,x)
0x1001c0ca  mov     ecx, eax
0x1001c0cc  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001c0d1  pop     edi
0x1001c0d2  pop     esi
0x1001c0d3  pop     ebx
0x1001c0d4  mov     esp, ebp
0x1001c0d6  pop     ebp
0x1001c0d7  retn    0Ch
0x1001c0da  mov     edi, [eax+324h]
0x1001c0e0  mov     edx, esi
0x1001c0e2  mov     ax, [ebx]
0x1001c0e5  mov     ecx, edi
0x1001c0e7  add     ax, word ptr [ebp+arg_0]
0x1001c0eb  mov     word ptr [esp+28h+var_14], ax
0x1001c0f0  mov     ax, word ptr [ebp+arg_0+2]
0x1001c0f4  mov     word ptr [esp+28h+var_14+2], ax
0x1001c0f9  call    CheckForNeededXFRecords
0x1001c0fe  test    eax, eax
0x1001c100  jnz     loc_1001C29D
0x1001c106  mov     ecx, esi
0x1001c108  mov     al, [ebx+2]
0x1001c10b  add     [ecx+4], al
0x1001c10e  mov     ecx, [ecx]
0x1001c110  test    ecx, ecx
0x1001c112  jnz     short loc_1001C108
0x1001c114  cmp     [ebp+arg_8], 1
0x1001c118  jnz     short loc_1001C132
0x1001c11a  mov     edx, [esp+28h+var_10]
0x1001c11e  mov     ecx, edi
0x1001c120  push    esi
0x1001c121  push    [esp+2Ch+var_14]
0x1001c125  call    DetermineCellFormats
0x1001c12a  test    eax, eax
0x1001c12c  jnz     loc_1001C29D
0x1001c132  mov     ecx, esi
0x1001c134  mov     eax, [ecx+0Ch]
0x1001c137  cmp     eax, 0FFFFFFFFh
0x1001c13a  jnz     short loc_1001C141
0x1001c13c  mov     eax, [edi+3Ch]
0x1001c13f  jmp     short loc_1001C153
0x1001c141  cmp     eax, 0FFFFFFFEh
0x1001c144  jnz     short loc_1001C14B
0x1001c146  mov     eax, [edi+40h]
0x1001c149  jmp     short loc_1001C153
0x1001c14b  cmp     eax, 0FFFFFFFDh
0x1001c14e  jnz     short loc_1001C156
0x1001c150  mov     eax, [edi+44h]
0x1001c153  mov     [ecx+0Ch], eax
0x1001c156  mov     edx, ecx
0x1001c158  mov     ecx, [ecx]
0x1001c15a  test    ecx, ecx
0x1001c15c  jnz     short loc_1001C134
0x1001c15e  movzx   eax, byte ptr [esi+4]
0x1001c162  movzx   edi, word ptr [esp+28h+var_14]
0x1001c167  mov     [esp+28h+var_8], eax
0x1001c16b  movzx   eax, byte ptr [edx+4]
0x1001c16f  movzx   ecx, di
0x1001c172  mov     [esp+28h+var_18], ecx
0x1001c176  mov     [esp+28h+var_4], eax
0x1001c17a  movzx   eax, cx
0x1001c17d  mov     ecx, [esp+28h+var_10]
0x1001c181  mov     [esp+28h+var_14], edi
0x1001c185  mov     ecx, [ecx+8]
0x1001c188  mov     edx, [ecx+30h]
0x1001c18b  cmp     dword ptr [edx+14h], 0
0x1001c18f  jz      loc_1001C243
0x1001c195  mov     ecx, [ecx+2Ch]
0x1001c198  xor     edi, edi
0x1001c19a  mov     [esp+28h+var_C], ecx
0x1001c19e  mov     eax, [ecx+40h]
0x1001c1a1  test    eax, eax
0x1001c1a3  jz      short loc_1001C1B0
0x1001c1a5  cmp     eax, edx
0x1001c1a7  jz      short loc_1001C1B0
0x1001c1a9  mov     eax, [eax]
0x1001c1ab  inc     edi
0x1001c1ac  test    eax, eax
0x1001c1ae  jnz     short loc_1001C1A5
0x1001c1b0  mov     edx, [esp+28h+var_18]
0x1001c1b4  movzx   eax, dx
0x1001c1b7  mov     edx, edi
0x1001c1b9  push    esi
0x1001c1ba  mov     dword ptr [ecx+2Ch], 1
0x1001c1c1  mov     ecx, [ecx+28h]
0x1001c1c4  push    eax
0x1001c1c5  call    _ExcelMIWriteCellList@16; ExcelMIWriteCellList(x,x,x,x)
0x1001c1ca  mov     edx, [esp+28h+var_18]
0x1001c1ce  mov     ecx, eax
0x1001c1d0  test    ecx, ecx
0x1001c1d2  jnz     short loc_1001C1FD
0x1001c1d4  mov     eax, [esp+28h+var_C]
0x1001c1d8  cmp     [eax+30h], ecx
0x1001c1db  jz      short loc_1001C1FD
0x1001c1dd  movzx   eax, dx
0x1001c1e0  cmp     eax, 3FFFh
0x1001c1e5  ja      short loc_1001C1FD
0x1001c1e7  push    esi
0x1001c1e8  push    eax
0x1001c1e9  mov     eax, [esp+30h+var_C]
0x1001c1ed  mov     edx, edi
0x1001c1ef  mov     ecx, [eax+34h]
0x1001c1f2  call    _ExcelMIWriteCellList@16; ExcelMIWriteCellList(x,x,x,x)
0x1001c1f7  mov     edx, [esp+28h+var_18]
0x1001c1fb  mov     ecx, eax
0x1001c1fd  mov     edi, [esp+28h+var_14]
0x1001c201  mov     al, [ebx+2]
0x1001c204  sub     [esi+4], al
0x1001c207  mov     esi, [esi]
0x1001c209  test    esi, esi
0x1001c20b  jnz     short loc_1001C201
0x1001c20d  test    ecx, ecx
0x1001c20f  jnz     loc_1001C0CC
0x1001c215  mov     ebx, [esp+28h+var_10]
0x1001c219  mov     esi, 0FFFFh
0x1001c21e  mov     eax, [ebx+31Ch]
0x1001c224  movzx   ecx, word ptr [eax+4]
0x1001c228  cmp     cx, si
0x1001c22b  mov     esi, [esp+28h+var_8]
0x1001c22f  jnz     short loc_1001C266
0x1001c231  mov     [eax+6], si
0x1001c235  mov     esi, [esp+28h+var_4]
0x1001c239  mov     [eax+4], di
0x1001c23d  mov     [eax+0Ah], si
0x1001c241  jmp     short loc_1001C28D
0x1001c243  cmp     [ebp+arg_8], 1
0x1001c247  mov     edx, eax
0x1001c249  push    esi
0x1001c24a  jnz     short loc_1001C259
0x1001c24c  call    EXInsertRecord
0x1001c251  mov     edx, [esp+28h+var_18]
0x1001c255  mov     ecx, eax
0x1001c257  jmp     short loc_1001C201
0x1001c259  call    EXUpdateRecord
0x1001c25e  mov     edx, [esp+28h+var_18]
0x1001c262  mov     ecx, eax
0x1001c264  jmp     short loc_1001C201
0x1001c266  cmp     si, [eax+6]
0x1001c26a  jnb     short loc_1001C270
0x1001c26c  mov     [eax+6], si
0x1001c270  mov     esi, [esp+28h+var_4]
0x1001c274  cmp     si, [eax+0Ah]
0x1001c278  jbe     short loc_1001C27E
0x1001c27a  mov     [eax+0Ah], si
0x1001c27e  cmp     di, cx
0x1001c281  jnb     short loc_1001C287
0x1001c283  mov     [eax+4], di
0x1001c287  cmp     dx, [eax+8]
0x1001c28b  jbe     short loc_1001C291
0x1001c28d  mov     [eax+8], dx
0x1001c291  mov     dword ptr [ebx+328h], 1
0x1001c29b  xor     eax, eax
0x1001c29d  pop     edi
0x1001c29e  pop     esi
0x1001c29f  pop     ebx
0x1001c2a0  mov     esp, ebp
0x1001c2a2  pop     ebp
0x1001c2a3  retn    0Ch
```
