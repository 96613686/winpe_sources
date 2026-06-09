# OpenTable(x,x,x,x,x,x,x)

- ea: `0x10011060`
- end: `0x10011303`
- name: `_OpenTable@28`
- size: `675`
- prototype: `int __stdcall(int, int, int, STRSAFE_LPCWSTR pszSrc, int, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x10011870`
- `0x100130e0`

## callees

- `0x1000a350`
- `0x1000bf60`
- `0x1000ff00`
- `0x10010000`
- `0x10010020`
- `0x100108e0`
- `0x10011060`
- `0x10013c80`
- `0x100140b0`
- `0x10014270`
- `0x10014690`
- `0x10016910`
- `0x1001eb10`
- `0x1001f1b0`
- `0x1001f240`
- `0x1001f830`

## pseudocode

```c
int __stdcall OpenTable(int a1, int a2, _DWORD *a3, STRSAFE_LPCWSTR pszSrc, int a5, int a6, int a7)
{
  int v7; // ebp
  int result; // eax
  int v9; // ebx
  int v10; // esi
  int v11; // ecx
  int **v12; // eax
  int **v13; // edx
  int v14; // eax
  int v15; // eax
  int v16; // edi
  DWORD v17; // eax
  int v18; // eax
  int v19; // [esp+10h] [ebp-8h]
  int v20; // [esp+14h] [ebp-4h] BYREF
  int v21; // [esp+20h] [ebp+8h]
  char pszSrca; // [esp+28h] [ebp+10h]

  v7 = *(_DWORD *)(a2 + 4);
  v19 = 0;
  result = LocateTableInDatabase(a2, pszSrc, (int)&v20, 1);
  if ( result )
    return result;
  v9 = a5;
  v10 = v20;
  if ( (a5 & 4) == 0 && a7 && *(_DWORD *)(v7 + 8) == 2 && *(int *)(v20 + 864) > 0 )
    return -1001;
  v11 = a2;
  *(_DWORD *)(v20 + 904) = *(_DWORD *)(v7 + 8);
  if ( (*(_BYTE *)(a2 + 892) & 1) != 0 || *(_DWORD *)(v10 + 896) == 1 && *(_DWORD *)(v10 + 900) )
    v9 = a5 | 4;
  if ( a6 )
    goto LABEL_25;
  v12 = *(int ***)(v10 + 868);
  if ( !v12 )
  {
LABEL_15:
    if ( AnyCursorHasOption(v10, 1) == 1 )
    {
      if ( v9 != 4 )
      {
LABEL_17:
        ErrorSetExtendedInfoSz2(-8154, pszSrc, 1);
        return -1304;
      }
    }
    else if ( v13 )
    {
      if ( (v9 & 2) != 0 )
        goto LABEL_17;
      if ( (v9 & 1) != 0 )
      {
        while ( ((_BYTE)v13[5] & 4) != 0 )
        {
          v13 = (int **)*v13;
          if ( !v13 )
            goto LABEL_24;
        }
        goto LABEL_17;
      }
    }
LABEL_24:
    v11 = a2;
LABEL_25:
    v14 = v9;
    pszSrca = v9;
    if ( (*(_BYTE *)(v11 + 892) & 2) != 0 )
    {
      v14 = v9 | 3;
      pszSrca = v9 | 3;
    }
    if ( !*(_DWORD *)(v10 + 8) )
    {
      result = EngineOpenTable((_DWORD *)v11, (_DWORD *)v10, v14);
      if ( result )
        return result;
      *(_BYTE *)(v10 + 876) = (pszSrca & 4) != 0 || !TextFileIsWritable(*(_DWORD *)(v10 + 8));
      v19 = 1;
    }
    v15 = ISAMDBAddCursor(a2, v10);
    v16 = v15;
    if ( v15 )
    {
      if ( !ReadBufferAllocate(v15) )
      {
        *(_BYTE *)(v16 + 28) = (v9 & 4) != 0 || !TextFileIsWritable(*(_DWORD *)(v10 + 8));
        *(_BYTE *)(v16 + 29) = TextMove(*(_DWORD *)(v10 + 8), 0) != 0 ? 0 : 2;
        TextGetBookmark(*(_DWORD *)(v10 + 8), v16 + 32);
        *(_DWORD *)(v16 + 64) = 1;
        *(_DWORD *)(v16 + 20) = v9;
        *(_DWORD *)(v10 + 872) = v16;
        if ( (v9 & 0x80000) != 0 )
          *(_DWORD *)(v16 + 24) = 1;
        v17 = CurrentTaskHandle();
        v18 = ISAMDBFindTask(v17);
        v21 = (*(int (__stdcall **)(_DWORD, _DWORD *, _DWORD, int *))(*(_DWORD *)(v18 + 28) + 36))(
                *(_DWORD *)(a1 + 12),
                a3,
                *(_DWORD *)(v16 + 12),
                &TableEntryPoints);
        if ( v21 )
        {
          if ( v19 == 1 )
            EngineCloseTable(v7, v10);
          ISAMDBDeleteCursor(v10, v16);
          if ( !*(_DWORD *)(v10 + 868) )
            ISAMDBDeleteTable(v7, v10);
          return v21;
        }
        else
        {
          *(_DWORD *)(v16 + 16) = *a3;
          return 0;
        }
      }
      if ( v19 == 1 )
      {
        EngineCloseTable(v7, v10);
        ISAMDBDeleteTable(v7, v10);
      }
    }
    else if ( v19 == 1 )
    {
      if ( *(_DWORD *)(v10 + 8) )
        TextCloseFile(*(_DWORD *)(v10 + 8));
      ISAMDBDeleteTable(v7, v10);
      return -1011;
    }
    return -1011;
  }
  while ( ((_BYTE)v12[5] & 2) == 0 )
  {
    v12 = (int **)*v12;
    if ( !v12 )
      goto LABEL_15;
  }
  ErrorSetExtendedInfoSz2(-8153, pszSrc, 1);
  return -1302;
}

```

## disassembly

```asm
0x10011060  sub     esp, 8
0x10011063  mov     eax, [esp+8+arg_4]
0x10011067  lea     ecx, [esp+8+var_4]
0x1001106b  push    ebp
0x1001106c  push    edi
0x1001106d  mov     edi, [esp+10h+pszSrc]
0x10011071  mov     ebp, [eax+4]
0x10011074  push    1; int
0x10011076  push    ecx; int
0x10011077  push    edi; STRSAFE_LPCWSTR
0x10011078  push    eax; int
0x10011079  mov     [esp+20h+var_8], 0
0x10011081  call    _LocateTableInDatabase@16; LocateTableInDatabase(x,x,x,x)
0x10011086  test    eax, eax
0x10011088  jnz     loc_100112FB
0x1001108e  push    ebx
0x1001108f  mov     ebx, [esp+14h+arg_10]
0x10011093  push    esi
0x10011094  mov     esi, [esp+18h+var_4]
0x10011098  test    bl, 4
0x1001109b  jnz     short loc_100110C0
0x1001109d  cmp     [esp+18h+arg_18], eax
0x100110a1  jz      short loc_100110C0
0x100110a3  cmp     dword ptr [ebp+8], 2
0x100110a7  jnz     short loc_100110C0
0x100110a9  cmp     [esi+360h], eax
0x100110af  jle     short loc_100110C0
0x100110b1  pop     esi
0x100110b2  pop     ebx
0x100110b3  pop     edi
0x100110b4  mov     eax, 0FFFFFC17h
0x100110b9  pop     ebp
0x100110ba  add     esp, 8
0x100110bd  retn    1Ch
0x100110c0  mov     ecx, [esp+18h+arg_4]
0x100110c4  mov     eax, [ebp+8]
0x100110c7  mov     [esi+388h], eax
0x100110cd  test    byte ptr [ecx+37Ch], 1
0x100110d4  jnz     short loc_100110E8
0x100110d6  cmp     dword ptr [esi+380h], 1
0x100110dd  jnz     short loc_100110EB
0x100110df  cmp     dword ptr [esi+384h], 0
0x100110e6  jz      short loc_100110EB
0x100110e8  or      ebx, 4
0x100110eb  cmp     [esp+18h+arg_14], 0
0x100110f0  jnz     loc_10011176
0x100110f6  mov     edx, [esi+364h]
0x100110fc  mov     eax, edx
0x100110fe  test    eax, eax
0x10011100  jz      short loc_1001110E
0x10011102  test    byte ptr [eax+14h], 2
0x10011106  jnz     short loc_1001113C
0x10011108  mov     eax, [eax]
0x1001110a  test    eax, eax
0x1001110c  jnz     short loc_10011102
0x1001110e  push    1
0x10011110  push    esi
0x10011111  call    AnyCursorHasOption
0x10011116  cmp     eax, 1
0x10011119  jnz     short loc_10011158
0x1001111b  cmp     ebx, 4
0x1001111e  jz      short loc_10011172
0x10011120  push    1; int
0x10011122  push    edi; pszSrc
0x10011123  push    0FFFFE026h; int
0x10011128  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x1001112d  pop     esi
0x1001112e  pop     ebx
0x1001112f  pop     edi
0x10011130  mov     eax, 0FFFFFAE8h
0x10011135  pop     ebp
0x10011136  add     esp, 8
0x10011139  retn    1Ch
0x1001113c  push    1; int
0x1001113e  push    edi; pszSrc
0x1001113f  push    0FFFFE027h; int
0x10011144  call    _ErrorSetExtendedInfoSz2@12; ErrorSetExtendedInfoSz2(x,x,x)
0x10011149  pop     esi
0x1001114a  pop     ebx
0x1001114b  pop     edi
0x1001114c  mov     eax, 0FFFFFAEAh
0x10011151  pop     ebp
0x10011152  add     esp, 8
0x10011155  retn    1Ch
0x10011158  test    edx, edx
0x1001115a  jz      short loc_10011172
0x1001115c  test    bl, 2
0x1001115f  jnz     short loc_10011120
0x10011161  test    bl, 1
0x10011164  jz      short loc_10011172
0x10011166  test    byte ptr [edx+14h], 4
0x1001116a  jz      short loc_10011120
0x1001116c  mov     edx, [edx]
0x1001116e  test    edx, edx
0x10011170  jnz     short loc_10011166
0x10011172  mov     ecx, [esp+18h+arg_4]
0x10011176  test    byte ptr [ecx+37Ch], 2
0x1001117d  mov     eax, ebx
0x1001117f  mov     [esp+18h+pszSrc], eax
0x10011183  jz      short loc_1001118C
0x10011185  or      eax, 3
0x10011188  mov     [esp+18h+pszSrc], eax
0x1001118c  cmp     dword ptr [esi+8], 0
0x10011190  jnz     short loc_100111CD
0x10011192  push    eax
0x10011193  push    esi
0x10011194  push    ecx
0x10011195  call    _EngineOpenTable@12; EngineOpenTable(x,x,x)
0x1001119a  test    eax, eax
0x1001119c  jnz     loc_100112F9
0x100111a2  test    byte ptr [esp+18h+pszSrc], 4
0x100111a7  jnz     short loc_100111BE
0x100111a9  push    dword ptr [esi+8]
0x100111ac  call    _TextFileIsWritable@4; TextFileIsWritable(x)
0x100111b1  test    eax, eax
0x100111b3  jz      short loc_100111BE
0x100111b5  mov     byte ptr [esi+36Ch], 0
0x100111bc  jmp     short loc_100111C5
0x100111be  mov     byte ptr [esi+36Ch], 1
0x100111c5  mov     [esp+18h+var_8], 1
0x100111cd  push    esi
0x100111ce  push    [esp+1Ch+arg_4]
0x100111d2  call    _ISAMDBAddCursor@8; ISAMDBAddCursor(x,x)
0x100111d7  mov     edi, eax
0x100111d9  test    edi, edi
0x100111db  jnz     short loc_10011207
0x100111dd  cmp     [esp+18h+var_8], 1
0x100111e2  jnz     short loc_10011226
0x100111e4  mov     eax, [esi+8]
0x100111e7  test    eax, eax
0x100111e9  jz      short loc_100111F1
0x100111eb  push    eax
0x100111ec  call    _TextCloseFile@4; TextCloseFile(x)
0x100111f1  push    esi
0x100111f2  push    ebp
0x100111f3  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100111f8  pop     esi
0x100111f9  pop     ebx
0x100111fa  pop     edi
0x100111fb  mov     eax, 0FFFFFC0Dh
0x10011200  pop     ebp
0x10011201  add     esp, 8
0x10011204  retn    1Ch
0x10011207  push    edi
0x10011208  call    _ReadBufferAllocate@4; ReadBufferAllocate(x)
0x1001120d  test    eax, eax
0x1001120f  jz      short loc_10011235
0x10011211  cmp     [esp+18h+var_8], 1
0x10011216  jnz     short loc_10011226
0x10011218  push    esi
0x10011219  push    ebp
0x1001121a  call    EngineCloseTable
0x1001121f  push    esi
0x10011220  push    ebp
0x10011221  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x10011226  pop     esi
0x10011227  pop     ebx
0x10011228  pop     edi
0x10011229  mov     eax, 0FFFFFC0Dh
0x1001122e  pop     ebp
0x1001122f  add     esp, 8
0x10011232  retn    1Ch
0x10011235  test    bl, 4
0x10011238  jnz     short loc_1001124C
0x1001123a  push    dword ptr [esi+8]
0x1001123d  call    _TextFileIsWritable@4; TextFileIsWritable(x)
0x10011242  test    eax, eax
0x10011244  jz      short loc_1001124C
0x10011246  mov     byte ptr [edi+1Ch], 0
0x1001124a  jmp     short loc_10011250
0x1001124c  mov     byte ptr [edi+1Ch], 1
0x10011250  push    0
0x10011252  push    dword ptr [esi+8]
0x10011255  call    _TextMove@8; TextMove(x,x)
0x1001125a  neg     eax
0x1001125c  sbb     al, al
0x1001125e  and     al, 0FEh
0x10011260  add     al, 2
0x10011262  mov     [edi+1Dh], al
0x10011265  lea     eax, [edi+20h]
0x10011268  push    eax
0x10011269  push    dword ptr [esi+8]
0x1001126c  call    _TextGetBookmark@8; TextGetBookmark(x,x)
0x10011271  mov     dword ptr [edi+40h], 1
0x10011278  mov     [edi+14h], ebx
0x1001127b  mov     [esi+368h], edi
0x10011281  test    ebx, 80000h
0x10011287  jz      short loc_10011290
0x10011289  mov     dword ptr [edi+18h], 1
0x10011290  call    _CurrentTaskHandle@0; CurrentTaskHandle()
0x10011295  push    eax
0x10011296  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x1001129b  mov     ebx, [esp+18h+arg_8]
0x1001129f  push    offset _TableEntryPoints
0x100112a4  push    dword ptr [edi+0Ch]
0x100112a7  mov     ecx, [eax+1Ch]
0x100112aa  mov     eax, [esp+20h+arg_0]
0x100112ae  push    ebx
0x100112af  push    dword ptr [eax+0Ch]
0x100112b2  mov     eax, [ecx+24h]
0x100112b5  call    eax
0x100112b7  mov     [esp+18h+arg_4], eax
0x100112bb  test    eax, eax
0x100112bd  jz      short loc_100112F2
0x100112bf  cmp     [esp+18h+var_8], 1
0x100112c4  jnz     short loc_100112CD
0x100112c6  push    esi
0x100112c7  push    ebp
0x100112c8  call    EngineCloseTable
0x100112cd  push    edi
0x100112ce  push    esi
0x100112cf  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x100112d4  cmp     dword ptr [esi+364h], 0
0x100112db  jnz     short loc_100112E4
0x100112dd  push    esi
0x100112de  push    ebp
0x100112df  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100112e4  mov     eax, [esp+18h+arg_4]
0x100112e8  pop     esi
0x100112e9  pop     ebx
0x100112ea  pop     edi
0x100112eb  pop     ebp
0x100112ec  add     esp, 8
0x100112ef  retn    1Ch
0x100112f2  mov     eax, [ebx]
0x100112f4  mov     [edi+10h], eax
0x100112f7  xor     eax, eax
0x100112f9  pop     esi
0x100112fa  pop     ebx
0x100112fb  pop     edi
0x100112fc  pop     ebp
0x100112fd  add     esp, 8
0x10011300  retn    1Ch
```
