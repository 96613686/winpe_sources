# ExcelCloseFile(x,x)

- ea: `0x10011730`
- end: `0x10011a65`
- name: `_ExcelCloseFile@8`
- size: `821`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001abf0`
- `0x1001b2f0`

## callees

- `0x10007670`
- `0x1000d760`
- `0x10011730`
- `0x10011dd0`
- `0x10025ab7`
- `0x10025b48`
- `0x10025cb3`
- `0x10025df5`
- `0x10026030`
- `0x100260bc`
- `0x1002eb45`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10011828`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10011970`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10011828`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10011970`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100119ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100119ae`

## pseudocode

```c
int __fastcall ExcelCloseFile(_DWORD *a1, int a2)
{
  int result; // eax
  int v5; // esi
  bool v6; // zf
  _DWORD *v7; // ebx
  int v8; // ebx
  int v9; // eax
  LONG v10; // edx
  void (__thiscall *v11)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD); // ecx
  int v12; // ecx
  int v13; // esi
  int v14; // ebx
  int i; // eax
  _DWORD *v16; // ecx
  _DWORD *v17; // esi
  int v18; // ebx
  int v19; // eax
  LONG v20; // edx
  void (__thiscall *v21)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD); // ecx
  void (__thiscall *v22)(_DWORD, _DWORD, _DWORD *, _DWORD *); // ecx
  int v23; // esi
  int v24; // ebx
  _DWORD *v25; // ecx
  _DWORD *v26; // ecx
  int v27; // [esp+34h] [ebp-18h]
  int v28; // [esp+34h] [ebp-18h]
  int v30; // [esp+38h] [ebp-14h]
  _DWORD *v31[3]; // [esp+3Ch] [ebp-10h] BYREF
  DWORD NumberOfBytesWritten; // [esp+48h] [ebp-4h] BYREF

  v27 = 0;
  if ( (int)a1[1] >= 5 && a1[10] )
  {
    result = ((int (*)(void))ExcelMISave)();
    if ( a2 && (result == -8 || result == -9) )
      return result;
    if ( a1[12] )
    {
      BFCloseStream(a1[5]);
      BFOpenStream(2);
      v5 = ExcelMISave(a1, a1[13]);
      BFCloseStream(a1[5]);
      BFOpenStream(2);
      if ( a2 )
      {
        if ( v5 == -8 || v5 == -9 )
          return v5;
      }
    }
    v6 = a1[11] == 1;
    v7 = (_DWORD *)a1[10];
    NumberOfBytesWritten = a1[13];
    v31[0] = v7;
    if ( v6 )
    {
      v8 = a1[5];
      v28 = 0;
      if ( *(_DWORD *)(v8 + 92) != 1 || (v9 = WriteFileBlock(v8), (v28 = v9) == 0) )
      {
        if ( *(_DWORD *)(v8 + 24) == 1 )
        {
          v10 = *(_DWORD *)(v8 + 88);
          if ( *(_DWORD *)(v8 + 12) )
          {
            v11 = *(void (__thiscall **)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD))(**(_DWORD **)(v8 + 32) + 20);
            v11(v11, *(_DWORD *)(v8 + 32), v10, v10 >> 31, 0, 0);
          }
          else
          {
            SetFilePointer(*(HANDLE *)(v8 + 20), v10, 0, 0);
          }
          OSWriteFile(0);
        }
        if ( *(_DWORD *)(v8 + 12) == 1
          && (v12 = *(_DWORD *)(v8 + 28)) != 0
          && (*(_BYTE *)(v8 + 16) & 2) != 0
          && *(_DWORD *)(v8 + 24) == 1 )
        {
          v9 = (*(int (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v12 + 36))(
                 *(_DWORD *)(*(_DWORD *)v12 + 36),
                 v12,
                 0);
          if ( v9 )
          {
            if ( v9 == -2147286928 )
              v9 = -12;
            else
              v9 = 4 * (v9 == -2147287036) - 5;
          }
        }
        else
        {
          v9 = v28;
        }
      }
      v13 = a2;
      v14 = dword_10001970[abs32(v9)];
      if ( v14 == -10 )
        v14 = -10;
      v27 = v14;
      if ( v14 && a2 )
      {
LABEL_37:
        if ( v14 == -8 || v14 == -9 )
          return v14;
        goto LABEL_40;
      }
    }
    else
    {
      v13 = a2;
      v14 = 0;
      v27 = 0;
    }
    FreeWorkbook(v31[0]);
    if ( NumberOfBytesWritten )
      FreeWorkbook((_DWORD *)NumberOfBytesWritten);
    if ( v13 )
      goto LABEL_37;
  }
LABEL_40:
  for ( i = a1[17]; i; i = a1[17] )
    ExcelCloseSheet(i);
  v16 = (_DWORD *)a1[16];
  if ( v16 )
  {
    do
    {
      v17 = (_DWORD *)*v16;
      MemFree(v16);
      v16 = v17;
    }
    while ( v17 );
  }
  v18 = a1[5];
  if ( *(_DWORD *)(v18 + 92) == 1 )
    v19 = WriteFileBlock(a1[5]);
  else
    v19 = 0;
  v30 = v19;
  if ( *(_DWORD *)(v18 + 24) == 1 )
  {
    v20 = *(_DWORD *)(v18 + 88);
    if ( *(_DWORD *)(v18 + 12) )
    {
      v21 = *(void (__thiscall **)(_DWORD, _DWORD, LONG, LONG, _DWORD, _DWORD))(**(_DWORD **)(v18 + 32) + 20);
      v21(v21, *(_DWORD *)(v18 + 32), v20, v20 >> 31, 0, 0);
    }
    else
    {
      SetFilePointer(*(HANDLE *)(v18 + 20), v20, 0, 0);
    }
    v6 = *(_DWORD *)(v18 + 12) == 0;
    *(_DWORD *)(v18 + 24) = 1;
    if ( v6 )
    {
      WriteFile(*(HANDLE *)(v18 + 20), *(LPCVOID *)(v18 + 4), 0, &NumberOfBytesWritten, 0);
    }
    else
    {
      (*(void (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD **))(**(_DWORD **)(v18 + 32) + 20))(
        *(_DWORD *)(**(_DWORD **)(v18 + 32) + 20),
        *(_DWORD *)(v18 + 32),
        0,
        0,
        1,
        v31);
      v22 = *(void (__thiscall **)(_DWORD, _DWORD, _DWORD *, _DWORD *))(**(_DWORD **)(v18 + 32) + 24);
      v22(v22, *(_DWORD *)(v18 + 32), v31[0], v31[1]);
    }
  }
  v23 = OSCloseFile(v18);
  MemFree(*(_DWORD **)(v18 + 4));
  MemFree((_DWORD *)v18);
  v24 = v30;
  if ( v30 || (v24 = v23) != 0 )
  {
    v24 = dword_10001970[abs32(v24)];
    if ( v24 == -10 )
      v24 = -10;
  }
  TextStorageDestroy(a1[4]);
  v25 = (_DWORD *)a1[18];
  if ( v25 )
    MemFree(v25);
  v26 = (_DWORD *)a1[20];
  if ( v26 )
    MemFree(v26);
  MemFree(a1);
  result = v27;
  if ( !v27 )
    return v24;
  return result;
}

```

## disassembly

```asm
0x10011730  mov     edi, edi
0x10011732  push    ebp
0x10011733  mov     ebp, esp
0x10011735  and     esp, 0FFFFFFF8h
0x10011738  sub     esp, 1Ch
0x1001173b  push    ebx
0x1001173c  push    esi
0x1001173d  push    edi
0x1001173e  mov     edi, ecx
0x10011740  mov     [esp+28h+var_18], 0
0x10011748  mov     ebx, edx
0x1001174a  mov     [esp+28h+var_14], ebx
0x1001174e  cmp     dword ptr [edi+4], 5
0x10011752  jl      loc_10011910
0x10011758  mov     edx, [edi+28h]
0x1001175b  test    edx, edx
0x1001175d  jz      loc_10011910
0x10011763  call    _ExcelMISave@8; ExcelMISave(x,x)
0x10011768  test    ebx, ebx
0x1001176a  jz      short loc_1001177E
0x1001176c  cmp     eax, 0FFFFFFF8h
0x1001176f  jz      loc_10011A5E
0x10011775  cmp     eax, 0FFFFFFF7h
0x10011778  jz      loc_10011A5E
0x1001177e  cmp     dword ptr [edi+30h], 0
0x10011782  jz      short loc_100117D5
0x10011784  mov     ecx, [edi+14h]
0x10011787  call    _BFCloseStream@4; BFCloseStream(x)
0x1001178c  mov     ecx, [edi+14h]
0x1001178f  mov     edx, offset aBook; "Book"
0x10011794  push    2
0x10011796  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x1001179b  mov     edx, [edi+34h]
0x1001179e  mov     ecx, edi
0x100117a0  call    _ExcelMISave@8; ExcelMISave(x,x)
0x100117a5  mov     ecx, [edi+14h]
0x100117a8  mov     esi, eax
0x100117aa  call    _BFCloseStream@4; BFCloseStream(x)
0x100117af  mov     ecx, [edi+14h]
0x100117b2  mov     edx, offset aWorkbook; "Workbook"
0x100117b7  push    2
0x100117b9  call    _BFOpenStream@12; BFOpenStream(x,x,x)
0x100117be  test    ebx, ebx
0x100117c0  jz      short loc_100117D5
0x100117c2  cmp     esi, 0FFFFFFF8h
0x100117c5  jz      short loc_100117CC
0x100117c7  cmp     esi, 0FFFFFFF7h
0x100117ca  jnz     short loc_100117D5
0x100117cc  mov     eax, esi
0x100117ce  pop     edi
0x100117cf  pop     esi
0x100117d0  pop     ebx
0x100117d1  mov     esp, ebp
0x100117d3  pop     ebp
0x100117d4  retn
0x100117d5  cmp     dword ptr [edi+2Ch], 1
0x100117d9  mov     eax, [edi+34h]
0x100117dc  mov     ebx, [edi+28h]
0x100117df  mov     [esp+28h+NumberOfBytesWritten], eax
0x100117e3  mov     [esp+28h+var_10], ebx
0x100117e7  jnz     loc_100118D7
0x100117ed  mov     ebx, [edi+14h]
0x100117f0  mov     [esp+28h+var_18], 0
0x100117f8  cmp     dword ptr [ebx+5Ch], 1
0x100117fc  jnz     short loc_10011811
0x100117fe  mov     ecx, ebx
0x10011800  call    WriteFileBlock
0x10011805  mov     [esp+28h+var_18], eax
0x10011809  test    eax, eax
0x1001180b  jnz     loc_100118AE
0x10011811  cmp     dword ptr [ebx+18h], 1
0x10011815  jnz     short loc_10011856
0x10011817  cmp     dword ptr [ebx+0Ch], 0
0x1001181b  mov     edx, [ebx+58h]
0x1001181e  push    0; dwMoveMethod
0x10011820  push    0; lpDistanceToMoveHigh
0x10011822  jnz     short loc_10011830
0x10011824  push    edx; lDistanceToMove
0x10011825  push    dword ptr [ebx+14h]; hFile
0x10011828  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1001182e  jmp     short loc_1001184A
0x10011830  mov     eax, [ebx+20h]
0x10011833  mov     ecx, edx
0x10011835  sar     ecx, 1Fh
0x10011838  push    ecx
0x10011839  push    edx
0x1001183a  mov     esi, [eax]
0x1001183c  push    eax
0x1001183d  mov     esi, [esi+14h]
0x10011840  mov     ecx, esi
0x10011842  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011848  call    esi
0x1001184a  mov     edx, [ebx+4]
0x1001184d  mov     ecx, ebx
0x1001184f  push    0; nNumberOfBytesToWrite
0x10011851  call    OSWriteFile
0x10011856  cmp     dword ptr [ebx+0Ch], 1
0x1001185a  jnz     short loc_100118AA
0x1001185c  mov     ecx, [ebx+1Ch]
0x1001185f  test    ecx, ecx
0x10011861  jz      short loc_100118AA
0x10011863  test    byte ptr [ebx+10h], 2
0x10011867  jz      short loc_100118AA
0x10011869  cmp     dword ptr [ebx+18h], 1
0x1001186d  jnz     short loc_100118AA
0x1001186f  mov     eax, [ecx]
0x10011871  push    0
0x10011873  push    ecx
0x10011874  mov     esi, [eax+24h]
0x10011877  mov     ecx, esi
0x10011879  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001187f  call    esi
0x10011881  mov     ecx, eax
0x10011883  test    ecx, ecx
0x10011885  jz      short loc_100118AE
0x10011887  cmp     ecx, 80030070h
0x1001188d  jnz     short loc_10011896
0x1001188f  mov     eax, 0FFFFFFF4h
0x10011894  jmp     short loc_100118AE
0x10011896  xor     eax, eax
0x10011898  cmp     ecx, 80030004h
0x1001189e  setz    al
0x100118a1  lea     eax, ds:0FFFFFFFBh[eax*4]
0x100118a8  jmp     short loc_100118AE
0x100118aa  mov     eax, [esp+28h+var_18]
0x100118ae  mov     esi, [esp+28h+var_14]
0x100118b2  cdq
0x100118b3  xor     eax, edx
0x100118b5  sub     eax, edx
0x100118b7  mov     ebx, ds:dword_10001970[eax*4]
0x100118be  cmp     ebx, 0FFFFFFF6h
0x100118c1  mov     eax, 0FFFFFFF6h
0x100118c6  cmovz   ebx, eax
0x100118c9  mov     [esp+28h+var_18], ebx
0x100118cd  test    ebx, ebx
0x100118cf  jz      short loc_100118E1
0x100118d1  test    esi, esi
0x100118d3  jnz     short loc_100118FD
0x100118d5  jmp     short loc_100118E1
0x100118d7  mov     esi, [esp+28h+var_14]
0x100118db  xor     ebx, ebx
0x100118dd  mov     [esp+28h+var_18], ebx
0x100118e1  mov     ecx, [esp+28h+var_10]
0x100118e5  call    FreeWorkbook
0x100118ea  mov     eax, [esp+28h+NumberOfBytesWritten]
0x100118ee  test    eax, eax
0x100118f0  jz      short loc_100118F9
0x100118f2  mov     ecx, eax
0x100118f4  call    FreeWorkbook
0x100118f9  test    esi, esi
0x100118fb  jz      short loc_10011910
0x100118fd  cmp     ebx, 0FFFFFFF8h
0x10011900  jz      short loc_10011907
0x10011902  cmp     ebx, 0FFFFFFF7h
0x10011905  jnz     short loc_10011910
0x10011907  mov     eax, ebx
0x10011909  pop     edi
0x1001190a  pop     esi
0x1001190b  pop     ebx
0x1001190c  mov     esp, ebp
0x1001190e  pop     ebp
0x1001190f  retn
0x10011910  mov     eax, [edi+44h]
0x10011913  test    eax, eax
0x10011915  jz      short loc_10011925
0x10011917  mov     ecx, eax
0x10011919  call    _ExcelCloseSheet@4; ExcelCloseSheet(x)
0x1001191e  mov     eax, [edi+44h]
0x10011921  test    eax, eax
0x10011923  jnz     short loc_10011917
0x10011925  mov     ecx, [edi+40h]
0x10011928  test    ecx, ecx
0x1001192a  jz      short loc_1001193D
0x1001192c  nop     dword ptr [eax+00h]
0x10011930  mov     esi, [ecx]
0x10011932  call    _MemFree@4; MemFree(x)
0x10011937  mov     ecx, esi
0x10011939  test    esi, esi
0x1001193b  jnz     short loc_10011930
0x1001193d  mov     ebx, [edi+14h]
0x10011940  cmp     dword ptr [ebx+5Ch], 1
0x10011944  jnz     short loc_1001194F
0x10011946  mov     ecx, ebx
0x10011948  call    WriteFileBlock
0x1001194d  jmp     short loc_10011951
0x1001194f  xor     eax, eax
0x10011951  cmp     dword ptr [ebx+18h], 1
0x10011955  mov     [esp+28h+var_14], eax
0x10011959  jnz     loc_100119EF
0x1001195f  cmp     dword ptr [ebx+0Ch], 0
0x10011963  mov     edx, [ebx+58h]
0x10011966  push    0; dwMoveMethod
0x10011968  push    0; lpDistanceToMoveHigh
0x1001196a  jnz     short loc_10011978
0x1001196c  push    edx; lDistanceToMove
0x1001196d  push    dword ptr [ebx+14h]; hFile
0x10011970  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10011976  jmp     short loc_10011992
0x10011978  mov     eax, [ebx+20h]
0x1001197b  mov     ecx, edx
0x1001197d  sar     ecx, 1Fh
0x10011980  push    ecx
0x10011981  push    edx
0x10011982  mov     esi, [eax]
0x10011984  push    eax
0x10011985  mov     esi, [esi+14h]
0x10011988  mov     ecx, esi
0x1001198a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10011990  call    esi
0x10011992  cmp     dword ptr [ebx+0Ch], 0
0x10011996  mov     dword ptr [ebx+18h], 1
0x1001199d  jnz     short loc_100119B6
0x1001199f  push    0; lpOverlapped
0x100119a1  lea     eax, [esp+2Ch+NumberOfBytesWritten]
0x100119a5  push    eax; lpNumberOfBytesWritten
0x100119a6  push    0; nNumberOfBytesToWrite
0x100119a8  push    dword ptr [ebx+4]; lpBuffer
0x100119ab  push    dword ptr [ebx+14h]; hFile
0x100119ae  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x100119b4  jmp     short loc_100119EF
0x100119b6  mov     ecx, [ebx+20h]
0x100119b9  lea     eax, [esp+28h+var_10]
0x100119bd  push    eax
0x100119be  push    1
0x100119c0  xor     eax, eax
0x100119c2  mov     esi, [ecx]
0x100119c4  push    eax
0x100119c5  push    eax
0x100119c6  push    ecx
0x100119c7  mov     esi, [esi+14h]
0x100119ca  mov     ecx, esi
0x100119cc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100119d2  call    esi
0x100119d4  mov     eax, [ebx+20h]
0x100119d7  push    [esp+28h+var_C]
0x100119db  push    [esp+2Ch+var_10]
0x100119df  mov     esi, [eax]
0x100119e1  push    eax
0x100119e2  mov     esi, [esi+18h]
0x100119e5  mov     ecx, esi
0x100119e7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100119ed  call    esi
0x100119ef  mov     ecx, ebx
0x100119f1  call    OSCloseFile
0x100119f6  mov     ecx, [ebx+4]
0x100119f9  mov     esi, eax
0x100119fb  call    _MemFree@4; MemFree(x)
0x10011a00  mov     ecx, ebx
0x10011a02  call    _MemFree@4; MemFree(x)
0x10011a07  mov     ebx, [esp+28h+var_14]
0x10011a0b  test    ebx, ebx
0x10011a0d  jnz     short loc_10011A15
0x10011a0f  mov     ebx, esi
0x10011a11  test    ebx, ebx
0x10011a13  jz      short loc_10011A2E
0x10011a15  mov     eax, ebx
0x10011a17  cdq
0x10011a18  xor     eax, edx
0x10011a1a  sub     eax, edx
0x10011a1c  mov     ebx, ds:dword_10001970[eax*4]
0x10011a23  cmp     ebx, 0FFFFFFF6h
0x10011a26  mov     eax, 0FFFFFFF6h
0x10011a2b  cmovz   ebx, eax
0x10011a2e  mov     ecx, [edi+10h]
0x10011a31  call    _TextStorageDestroy@4; TextStorageDestroy(x)
0x10011a36  mov     ecx, [edi+48h]
0x10011a39  test    ecx, ecx
0x10011a3b  jz      short loc_10011A42
0x10011a3d  call    _MemFree@4; MemFree(x)
0x10011a42  mov     ecx, [edi+50h]
0x10011a45  test    ecx, ecx
0x10011a47  jz      short loc_10011A4E
0x10011a49  call    _MemFree@4; MemFree(x)
0x10011a4e  mov     ecx, edi
0x10011a50  call    _MemFree@4; MemFree(x)
0x10011a55  mov     eax, [esp+28h+var_18]
0x10011a59  test    eax, eax
0x10011a5b  cmovz   eax, ebx
0x10011a5e  pop     edi
0x10011a5f  pop     esi
0x10011a60  pop     ebx
0x10011a61  mov     esp, ebp
0x10011a63  pop     ebp
0x10011a64  retn
```
