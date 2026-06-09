# UpdateRecord(x,x,x)

- ea: `0x10032705`
- end: `0x1003284d`
- name: `_UpdateRecord@12`
- size: `328`
- prototype: `int __fastcall(int, int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x10029aad`
- `0x1002c79f`
- `0x1002cbc4`
- `0x1002db68`

## callees

- `0x1001c090`
- `0x1002ec67`
- `0x10031ef2`
- `0x10031fd9`
- `0x10032705`

## pseudocode

```c
int __fastcall UpdateRecord(int a1, int a2, int a3)
{
  int v3; // eax
  char *v4; // ebx
  char *v5; // esi
  char *v7; // edi
  _DWORD *v8; // ecx
  _DWORD *v9; // edx
  const unsigned __int16 *v10; // edx
  unsigned int v11; // ecx
  _DWORD *v12; // eax
  int v13; // eax
  int v14; // edi
  char *v15; // esi
  char *v17; // [esp+14h] [ebp-Ch]
  int v18; // [esp+14h] [ebp-Ch]
  _DWORD *v19; // [esp+18h] [ebp-8h]

  v3 = a1;
  v4 = 0;
  v5 = *(char **)(a1 + 40);
  v19 = 0;
  if ( !v5 )
    return 0;
  if ( a2 == 1 )
  {
    v7 = *(char **)(a1 + 40);
    goto LABEL_17;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  do
  {
    v17 = *(char **)v5;
    if ( (*((_WORD *)v5 + 4) & 0x400) != 0 )
    {
      if ( v8 )
        *v8 = v5;
      else
        v7 = v5;
      v8 = v5;
    }
    else
    {
      if ( v9 )
        *v9 = v5;
      else
        v4 = v5;
      v9 = v5;
    }
    *(_DWORD *)v5 = 0;
    v5 = v17;
  }
  while ( v17 );
  v18 = 0;
  v5 = v7;
  v3 = a1;
  v19 = v8;
  if ( v7 )
  {
    do
    {
LABEL_17:
      if ( v7[8] < 0 )
      {
        v10 = *(const unsigned __int16 **)(AssociatedColumnMemo(v3, (unsigned __int8)v7[4]) + 12);
        v11 = wcslen(v10);
        v12 = *(_DWORD **)(*(_DWORD *)(*(_DWORD *)(a1 + 4) + 4) + 12);
        if ( !v12[3] )
          v12 = (_DWORD *)v12[2];
        v13 = TextStoragePut(v12[4], v10, v11, 1);
        *((_DWORD *)v7 + 6) = v13;
        if ( v13 == -1 )
          return -1011;
        v3 = a1;
      }
      v7 = *(char **)v7;
    }
    while ( v7 );
    v14 = WorkbookCellWriteList(a3, v5, (a2 != 1) + 1);
    v18 = v14;
    if ( a2 == 1 )
      return v14;
    v3 = a1;
  }
  else
  {
    v14 = 0;
  }
  *(_DWORD *)(v3 + 40) = v5;
  *(_DWORD *)(v3 + 44) = v19;
  if ( v4 )
  {
    do
    {
      v15 = *(char **)v4;
      *(_DWORD *)v4 = 0;
      AddCopyCell(v3, v4);
      v3 = a1;
      v4 = v15;
    }
    while ( v15 );
    return v18;
  }
  return v14;
}

```

## disassembly

```asm
0x10032705  mov     edi, edi
0x10032707  push    ebp
0x10032708  mov     ebp, esp
0x1003270a  sub     esp, 14h
0x1003270d  mov     eax, ecx
0x1003270f  mov     [ebp+var_10], edx
0x10032712  push    ebx
0x10032713  push    esi
0x10032714  xor     ebx, ebx
0x10032716  mov     [ebp+var_4], eax
0x10032719  mov     esi, [eax+28h]
0x1003271c  mov     [ebp+var_14], ebx
0x1003271f  mov     [ebp+var_8], ebx
0x10032722  push    edi
0x10032723  test    esi, esi
0x10032725  jnz     short loc_1003272E
0x10032727  xor     eax, eax
0x10032729  jmp     loc_10032846
0x1003272e  cmp     edx, 1
0x10032731  jnz     short loc_10032737
0x10032733  mov     edi, esi
0x10032735  jmp     short loc_10032785
0x10032737  mov     edi, ebx
0x10032739  mov     ecx, ebx
0x1003273b  xor     edx, edx
0x1003273d  mov     eax, [esi]
0x1003273f  mov     [ebp+var_C], eax
0x10032742  mov     eax, 400h
0x10032747  test    [esi+8], ax
0x1003274b  jz      short loc_1003275B
0x1003274d  test    ecx, ecx
0x1003274f  jnz     short loc_10032755
0x10032751  mov     edi, esi
0x10032753  jmp     short loc_10032757
0x10032755  mov     [ecx], esi
0x10032757  mov     ecx, esi
0x10032759  jmp     short loc_10032767
0x1003275b  test    edx, edx
0x1003275d  jnz     short loc_10032763
0x1003275f  mov     ebx, esi
0x10032761  jmp     short loc_10032765
0x10032763  mov     [edx], esi
0x10032765  mov     edx, esi
0x10032767  xor     eax, eax
0x10032769  mov     [esi], eax
0x1003276b  mov     esi, [ebp+var_C]
0x1003276e  cmp     esi, eax
0x10032770  jnz     short loc_1003273D
0x10032772  mov     [ebp+var_C], eax
0x10032775  mov     esi, edi
0x10032777  mov     eax, [ebp+var_4]
0x1003277a  mov     [ebp+var_8], ecx
0x1003277d  test    edi, edi
0x1003277f  jz      loc_10032817
0x10032785  test    byte ptr [edi+8], 80h
0x10032789  jz      short loc_100327DD
0x1003278b  movzx   edx, byte ptr [edi+4]
0x1003278f  mov     ecx, eax
0x10032791  call    _AssociatedColumnMemo@8; AssociatedColumnMemo(x,x)
0x10032796  mov     edx, [eax+0Ch]
0x10032799  mov     ecx, edx
0x1003279b  lea     eax, [ecx+2]
0x1003279e  mov     [ebp+var_C], eax
0x100327a1  mov     ax, [ecx]
0x100327a4  add     ecx, 2
0x100327a7  cmp     ax, word ptr [ebp+var_14]
0x100327ab  jnz     short loc_100327A1
0x100327ad  mov     eax, [ebp+var_4]
0x100327b0  sub     ecx, [ebp+var_C]
0x100327b3  sar     ecx, 1
0x100327b5  mov     eax, [eax+4]
0x100327b8  mov     eax, [eax+4]
0x100327bb  mov     eax, [eax+0Ch]
0x100327be  cmp     dword ptr [eax+0Ch], 0
0x100327c2  jnz     short loc_100327C7
0x100327c4  mov     eax, [eax+8]
0x100327c7  push    1
0x100327c9  push    ecx
0x100327ca  mov     ecx, [eax+10h]
0x100327cd  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x100327d2  mov     [edi+18h], eax
0x100327d5  cmp     eax, 0FFFFFFFFh
0x100327d8  jz      short loc_10032810
0x100327da  mov     eax, [ebp+var_4]
0x100327dd  mov     edi, [edi]
0x100327df  test    edi, edi
0x100327e1  jnz     short loc_10032785
0x100327e3  mov     ecx, [eax+4]
0x100327e6  xor     eax, eax
0x100327e8  cmp     [ebp+var_10], 1
0x100327ec  setnz   al
0x100327ef  mov     edx, [ecx+10h]
0x100327f2  inc     eax
0x100327f3  mov     ecx, [ecx+0Ch]
0x100327f6  push    eax
0x100327f7  push    esi
0x100327f8  push    [ebp+arg_0]
0x100327fb  call    _WorkbookCellWriteList@20; WorkbookCellWriteList(x,x,x,x,x)
0x10032800  cmp     [ebp+var_10], 1
0x10032804  mov     edi, eax
0x10032806  mov     [ebp+var_C], edi
0x10032809  jz      short loc_10032844
0x1003280b  mov     eax, [ebp+var_4]
0x1003280e  jmp     short loc_1003281A
0x10032810  mov     eax, 0FFFFFC0Dh
0x10032815  jmp     short loc_10032846
0x10032817  mov     edi, [ebp+var_C]
0x1003281a  mov     ecx, [ebp+var_8]
0x1003281d  mov     [eax+28h], esi
0x10032820  mov     [eax+2Ch], ecx
0x10032823  test    ebx, ebx
0x10032825  jz      short loc_10032844
0x10032827  mov     esi, [ebx]
0x10032829  mov     edx, ebx
0x1003282b  mov     ecx, eax
0x1003282d  mov     dword ptr [ebx], 0
0x10032833  call    AddCopyCell
0x10032838  mov     eax, [ebp+var_4]
0x1003283b  mov     ebx, esi
0x1003283d  test    esi, esi
0x1003283f  jnz     short loc_10032827
0x10032841  mov     edi, [ebp+var_C]
0x10032844  mov     eax, edi
0x10032846  pop     edi
0x10032847  pop     esi
0x10032848  pop     ebx
0x10032849  leave
0x1003284a  retn    4
```
