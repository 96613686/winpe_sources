# ExcelOpenFile(x,x,x,x,x)

- ea: `0x10011280`
- end: `0x1001171b`
- name: `_ExcelOpenFile@20`
- size: `1179`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callers

- `0x1001ab60`

## callees

- `0x10010790`
- `0x10011010`
- `0x10011280`
- `0x10023815`
- `0x1002580a`
- `0x10025ab7`
- `0x10025bee`
- `0x10025c47`
- `0x10025cb3`
- `0x10025e72`
- `0x100265be`
- `0x10026925`
- `0x10032fa0`
- `0x100330d6`
- `0x10035510`
- `0x10035f40`

## import_xrefs

- `ole32!StgOpenStorage` at `0x1001153b`
- `ole32!StgOpenStorage` at `0x1001153b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x100115c5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x100115c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x100115d6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x100115d6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x100114a4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x100114a4`

## pseudocode

```c
int __thiscall ExcelOpenFile(LPCWSTR lpFileName, unsigned int a2, int a3, _DWORD *a4)
{
  int v5; // eax
  int result; // eax
  WCHAR *v7; // edi
  int v8; // ebx
  unsigned int v9; // eax
  WCHAR *v10; // ecx
  wchar_t *v11; // ebx
  WCHAR v12; // cx
  unsigned __int16 v13; // si
  __int16 v14; // cx
  int v15; // edi
  unsigned __int16 v16; // si
  bool v17; // zf
  int v18; // esi
  void *FirstFileW; // esi
  int v20; // eax
  int v21; // esi
  HRESULT v22; // eax
  int v23; // eax
  HGLOBAL v24; // eax
  HGLOBAL v25; // edi
  _DWORD *v26; // eax
  _DWORD *v27; // esi
  _DWORD *v28; // edi
  _DWORD *v29; // ecx
  _DWORD *v30; // eax
  unsigned int v31; // [esp+10h] [ebp-278h]
  WCHAR *pwcsName; // [esp+14h] [ebp-274h]
  int v33; // [esp+18h] [ebp-270h]
  WCHAR *v34; // [esp+1Ch] [ebp-26Ch]
  int v35; // [esp+20h] [ebp-268h]
  _DWORD *v36; // [esp+24h] [ebp-264h]
  struct _WIN32_FIND_DATAW FindFileData; // [esp+30h] [ebp-258h] BYREF

  v5 = MemAllocate(656);
  v36 = (_DWORD *)v5;
  if ( !v5 )
    return -2;
  v7 = (WCHAR *)(v5 + 132);
  *(_DWORD *)v5 = 0;
  *(_DWORD *)(v5 + 60) = 0;
  *(_DWORD *)(v5 + 56) = a2;
  *(_DWORD *)(v5 + 76) = -1;
  *(_DWORD *)(v5 + 36) = 0;
  pwcsName = (WCHAR *)(v5 + 132);
  JetGetFullPathNameW(lpFileName, 0x105u, (LPWSTR)(v5 + 132), 0);
  v8 = MemAllocate(96);
  v33 = v8;
  if ( !v8 )
    goto LABEL_62;
  v9 = 0;
  v31 = 0;
  while ( 1 )
  {
    v10 = v7;
    v35 = (unsigned __int8)byte_10038E84[8 * v9];
    v34 = v7;
    if ( !byte_10038E84[8 * v9] )
      break;
    v11 = (&off_10038E80)[2 * v9];
    do
    {
      ++v11;
      v12 = *v10;
      v13 = v12 + 32;
      if ( (unsigned __int16)(v12 - 65) > 0x19u )
        v13 = v12;
      v14 = *(v11 - 1);
      v15 = v13;
      v16 = v14 + 32;
      if ( (unsigned __int16)(v14 - 65) > 0x19u )
        v16 = *(v11 - 1);
      v10 = v34 + 1;
      v17 = v35-- == 1;
      ++v34;
    }
    while ( !v17 && (_WORD)v15 && (_WORD)v15 == v16 );
    v8 = v33;
    v9 = v31;
    if ( v15 == v16 )
      break;
    v7 = pwcsName;
    v9 = v31 + 1;
    v31 = v9;
    if ( v9 >= 0x10 )
      goto LABEL_16;
  }
  if ( v9 )
  {
    if ( v9 != 1 )
    {
LABEL_16:
      v18 = 0;
      goto LABEL_17;
    }
    v18 = 2;
  }
  else
  {
    v18 = 1;
  }
LABEL_17:
  memset(&FindFileData, 0, sizeof(FindFileData));
  if ( v18 == 1 )
  {
    *(_DWORD *)(v8 + 40) = 0;
    *(_DWORD *)(v8 + 44) = 0;
    *(_DWORD *)(v8 + 48) = 0;
    *(_DWORD *)(v8 + 52) = 0;
    *(_DWORD *)(v8 + 56) = 0;
    *(_DWORD *)(v8 + 60) = 0;
  }
  else if ( v18 == 2 )
  {
    if ( !NetFileInfo(pwcsName) )
      SplitOSTime(FindFileData.ftLastWriteTime, v8 + 48, v8 + 52, v8 + 56, v8 + 60);
  }
  else
  {
    FirstFileW = (void *)JetFindFirstFileW(pwcsName, &FindFileData);
    if ( FirstFileW != (void *)-1 )
    {
      SplitOSTime(FindFileData.ftLastWriteTime, v8 + 48, v8 + 52, v8 + 56, v8 + 60);
      FindClose(FirstFileW);
    }
  }
  if ( (a2 & 0x100) != 0 )
    *(_DWORD *)(v8 + 12) = 1;
  v17 = *(_DWORD *)(v8 + 12) == 0;
  *(_DWORD *)(v8 + 16) = (unsigned __int8)a2;
  if ( v17 )
  {
    v20 = DOSOpenFile(pwcsName, v8 + 20);
    if ( v20 )
    {
      if ( v20 == -4 )
      {
LABEL_33:
        v21 = -1;
        MemFree((_DWORD *)v8);
LABEL_63:
        v29 = v36;
LABEL_64:
        MemFree(v29);
        result = dword_10001970[abs32(v21)];
        if ( result == -10 )
          return -10;
        return result;
      }
      if ( v20 != -2 )
      {
        v21 = (v20 != -3) - 3;
        MemFree((_DWORD *)v8);
        goto LABEL_63;
      }
      goto LABEL_35;
    }
  }
  else
  {
    v22 = StgOpenStorage(pwcsName, 0, (unsigned __int8)a2 | 0x10000, 0, 0, (IStorage **)(v8 + 28));
    if ( v22 )
    {
      if ( v22 != -2147287038 && v22 != -2147287037 )
      {
        if ( v22 != -2147287036 )
        {
          if ( v22 == -2147287035 || v22 == -2147287007 || v22 == -2147287008 )
          {
            v21 = -2;
            MemFree((_DWORD *)v8);
          }
          else
          {
            v17 = v22 == -2147286960;
            v23 = -2;
            if ( v17 )
              v23 = -8;
            v21 = v23;
            MemFree((_DWORD *)v8);
          }
          goto LABEL_63;
        }
        goto LABEL_33;
      }
LABEL_35:
      v21 = -4;
      MemFree((_DWORD *)v8);
      goto LABEL_63;
    }
    *(_DWORD *)(v8 + 12) = 1;
    *(_DWORD *)(v8 + 36) = 1;
  }
  v24 = GlobalAlloc(0x2002u, 0xFDF4u);
  v25 = v24;
  if ( !v24
    || (v26 = GlobalLock(v24), (v27 = v26) == 0)
    || (v26[2] = v25, v28 = v26 + 3, v26[1] = 65000, memset(v26 + 3, 0, 0xFDE8u), *v27 = 1, v27 == (_DWORD *)-12) )
  {
    OSCloseFile(v8);
    MemFree((_DWORD *)v8);
LABEL_62:
    v21 = -6;
    goto LABEL_63;
  }
  v17 = *(_DWORD *)(v8 + 12) == 0;
  *(_DWORD *)(v8 + 4) = v28;
  *(_DWORD *)(v8 + 64) = 65000;
  *(_DWORD *)(v8 + 84) = 0;
  *(_DWORD *)(v8 + 80) = 0;
  *(_DWORD *)v8 = 0;
  *(_DWORD *)(v8 + 8) = v28;
  if ( v17 )
  {
    OSSetFilePosition(v8, 2u, 0);
    OSGetFilePosition(v8, v8 + 88);
    OSSetFilePosition(v8, 0, 0);
  }
  v36[5] = v8;
  if ( (a2 & 0x100) != 0 )
  {
    v21 = OpenWorkbookStream(v36, a2);
    if ( v21 )
    {
      BFCloseFile(v36[5]);
      v29 = v36;
      goto LABEL_64;
    }
  }
  v30 = v36;
  if ( *v36 == 1 )
    v30 = (_DWORD *)v36[11];
  v30[26] = 0;
  *((_WORD *)v30 + 48) = 0x4000;
  result = OpenSetup((int)v36, a2, 0);
  if ( !result )
  {
    *a4 = v36;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10011280  mov     edi, edi
0x10011282  push    ebp
0x10011283  mov     ebp, esp
0x10011285  and     esp, 0FFFFFFF8h
0x10011288  sub     esp, 27Ch
0x1001128e  mov     eax, ___security_cookie
0x10011293  xor     eax, esp
0x10011295  mov     [esp+27Ch+var_4], eax
0x1001129c  mov     eax, [ebp+arg_8]
0x1001129f  push    ebx
0x100112a0  push    esi
0x100112a1  mov     esi, ecx
0x100112a3  mov     [esp+284h+var_25C], eax
0x100112a7  push    edi
0x100112a8  mov     ecx, 290h
0x100112ad  call    _MemAllocate@4; MemAllocate(x)
0x100112b2  mov     [esp+288h+var_264], eax
0x100112b6  test    eax, eax
0x100112b8  jnz     short loc_100112D6
0x100112ba  mov     eax, 0FFFFFFFEh
0x100112bf  pop     edi
0x100112c0  pop     esi
0x100112c1  pop     ebx
0x100112c2  mov     ecx, [esp+27Ch+var_4]
0x100112c9  xor     ecx, esp; StackCookie
0x100112cb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100112d0  mov     esp, ebp
0x100112d2  pop     ebp
0x100112d3  retn    0Ch
0x100112d6  mov     ebx, [ebp+arg_0]
0x100112d9  lea     edi, [eax+84h]
0x100112df  push    0; lpFilePart
0x100112e1  push    edi; lpBuffer
0x100112e2  push    105h; nBufferLength
0x100112e7  push    esi; lpFileName
0x100112e8  mov     dword ptr [eax], 0
0x100112ee  mov     dword ptr [eax+3Ch], 0
0x100112f5  mov     [eax+38h], ebx
0x100112f8  mov     dword ptr [eax+4Ch], 0FFFFFFFFh
0x100112ff  mov     dword ptr [eax+24h], 0
0x10011306  mov     [esp+298h+pwcsName], edi
0x1001130a  call    _JetGetFullPathNameW@16; JetGetFullPathNameW(x,x,x,x)
0x1001130f  mov     ecx, 60h ; '`'
0x10011314  call    _MemAllocate@4; MemAllocate(x)
0x10011319  mov     ebx, eax
0x1001131b  mov     [esp+288h+var_270], ebx
0x1001131f  test    ebx, ebx
0x10011321  jz      loc_100116DD
0x10011327  xor     eax, eax
0x10011329  mov     [esp+288h+var_278], eax
0x1001132d  nop     dword ptr [eax]
0x10011330  mov     ecx, off_10038E80[eax*8]; "http:"
0x10011337  movzx   edx, byte_10038E84[eax*8]
0x1001133f  mov     [esp+288h+var_260], ecx
0x10011343  mov     ecx, edi
0x10011345  mov     [esp+288h+var_268], edx
0x10011349  mov     [esp+288h+var_26C], ecx
0x1001134d  test    edx, edx
0x1001134f  jz      loc_10011422
0x10011355  mov     ebx, [esp+288h+var_260]
0x10011359  nop     dword ptr [eax+00000000h]
0x10011360  movzx   eax, word ptr [ecx]
0x10011363  lea     ebx, [ebx+2]
0x10011366  mov     ecx, eax
0x10011368  lea     edx, [eax-41h]
0x1001136b  lea     eax, [ecx+20h]
0x1001136e  cmp     dx, 19h
0x10011372  movzx   esi, ax
0x10011375  mov     eax, ecx
0x10011377  cmova   esi, eax
0x1001137a  movzx   eax, word ptr [ebx-2]
0x1001137e  mov     ecx, eax
0x10011380  movzx   edi, si
0x10011383  lea     edx, [eax-41h]
0x10011386  lea     eax, [ecx+20h]
0x10011389  cmp     dx, 19h
0x1001138d  movzx   esi, ax
0x10011390  mov     eax, ecx
0x10011392  mov     ecx, [esp+288h+var_26C]
0x10011396  cmova   esi, eax
0x10011399  add     ecx, 2
0x1001139c  movzx   eax, si
0x1001139f  sub     [esp+288h+var_268], 1
0x100113a4  mov     [esp+288h+var_26C], ecx
0x100113a8  jz      short loc_100113B4
0x100113aa  test    di, di
0x100113ad  jz      short loc_100113B4
0x100113af  cmp     di, ax
0x100113b2  jz      short loc_10011360
0x100113b4  mov     ebx, [esp+288h+var_270]
0x100113b8  mov     ecx, edi
0x100113ba  sub     ecx, eax
0x100113bc  mov     eax, [esp+288h+var_278]
0x100113c0  jz      short loc_10011422
0x100113c2  mov     edi, [esp+288h+pwcsName]
0x100113c6  inc     eax
0x100113c7  mov     [esp+288h+var_278], eax
0x100113cb  cmp     eax, 10h
0x100113ce  jb      loc_10011330
0x100113d4  xor     esi, esi
0x100113d6  push    250h; Size
0x100113db  lea     eax, [esp+28Ch+FindFileData]
0x100113df  push    0; Val
0x100113e1  push    eax; void *
0x100113e2  call    _memset
0x100113e7  mov     edi, [esp+294h+pwcsName]
0x100113eb  add     esp, 0Ch
0x100113ee  cmp     esi, 1
0x100113f1  jnz     short loc_10011435
0x100113f3  mov     dword ptr [ebx+28h], 0
0x100113fa  mov     dword ptr [ebx+2Ch], 0
0x10011401  mov     dword ptr [ebx+30h], 0
0x10011408  mov     dword ptr [ebx+34h], 0
0x1001140f  mov     dword ptr [ebx+38h], 0
0x10011416  mov     dword ptr [ebx+3Ch], 0
0x1001141d  jmp     loc_100114AA
0x10011422  test    eax, eax
0x10011424  jnz     short loc_1001142B
0x10011426  lea     esi, [eax+1]
0x10011429  jmp     short loc_100113D6
0x1001142b  cmp     eax, 1
0x1001142e  jnz     short loc_100113D4
0x10011430  lea     esi, [eax+1]
0x10011433  jmp     short loc_100113D6
0x10011435  cmp     esi, 2
0x10011438  jnz     short loc_1001146E
0x1001143a  lea     edx, [esp+288h+FindFileData]
0x1001143e  mov     ecx, edi; FullPath
0x10011440  call    _NetFileInfo@8; NetFileInfo(x,x)
0x10011445  test    eax, eax
0x10011447  jnz     short loc_100114AA
0x10011449  lea     eax, [ebx+3Ch]
0x1001144c  push    eax; int
0x1001144d  lea     eax, [ebx+38h]
0x10011450  push    eax; int
0x10011451  lea     eax, [ebx+34h]
0x10011454  push    eax; int
0x10011455  lea     eax, [ebx+30h]
0x10011458  push    eax; int
0x10011459  push    [esp+298h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x1001145d  lea     edx, [ebx+2Ch]
0x10011460  push    [esp+29Ch+FindFileData.ftLastWriteTime.dwLowDateTime]; FileTime
0x10011464  lea     ecx, [ebx+28h]
0x10011467  call    SplitOSTime
0x1001146c  jmp     short loc_100114AA
0x1001146e  lea     eax, [esp+288h+FindFileData]
0x10011472  push    eax; lpFindFileData
0x10011473  push    edi; lpFileName
0x10011474  call    _JetFindFirstFileW@8; JetFindFirstFileW(x,x)
0x10011479  mov     esi, eax
0x1001147b  cmp     esi, 0FFFFFFFFh
0x1001147e  jz      short loc_100114AA
0x10011480  lea     eax, [ebx+3Ch]
0x10011483  push    eax; int
0x10011484  lea     eax, [ebx+38h]
0x10011487  push    eax; int
0x10011488  lea     eax, [ebx+34h]
0x1001148b  push    eax; int
0x1001148c  lea     eax, [ebx+30h]
0x1001148f  push    eax; int
0x10011490  push    [esp+298h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x10011494  lea     edx, [ebx+2Ch]
0x10011497  push    [esp+29Ch+FindFileData.ftLastWriteTime.dwLowDateTime]; FileTime
0x1001149b  lea     ecx, [ebx+28h]
0x1001149e  call    SplitOSTime
0x100114a3  push    esi; hFindFile
0x100114a4  call    ds:__imp__FindClose@4; FindClose(x)
0x100114aa  mov     ecx, [ebp+arg_0]
0x100114ad  mov     eax, ecx
0x100114af  and     eax, 100h
0x100114b4  mov     [esp+288h+var_270], eax
0x100114b8  jz      short loc_100114C1
0x100114ba  mov     dword ptr [ebx+0Ch], 1
0x100114c1  cmp     dword ptr [ebx+0Ch], 0
0x100114c5  movzx   edx, cl
0x100114c8  mov     [ebx+10h], edx
0x100114cb  jnz     short loc_10011529
0x100114cd  lea     eax, [ebx+14h]
0x100114d0  mov     ecx, edi; lpFileName
0x100114d2  push    eax; int
0x100114d3  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x100114d8  mov     ecx, eax
0x100114da  test    ecx, ecx
0x100114dc  jz      loc_100115BB
0x100114e2  cmp     ecx, 0FFFFFFFCh
0x100114e5  jnz     short loc_100114F6
0x100114e7  mov     ecx, ebx
0x100114e9  or      esi, 0FFFFFFFFh
0x100114ec  call    _MemFree@4; MemFree(x)
0x100114f1  jmp     loc_100116E2
0x100114f6  cmp     ecx, 0FFFFFFFEh
0x100114f9  jnz     short loc_1001150C
0x100114fb  mov     ecx, ebx
0x100114fd  mov     esi, 0FFFFFFFCh
0x10011502  call    _MemFree@4; MemFree(x)
0x10011507  jmp     loc_100116E2
0x1001150c  xor     eax, eax
0x1001150e  cmp     ecx, 0FFFFFFFDh
0x10011511  mov     ecx, ebx
0x10011513  setnz   al
0x10011516  add     eax, 0FFFFFFFDh
0x10011519  mov     [esp+288h+var_278], eax
0x1001151d  mov     esi, eax
0x1001151f  call    _MemFree@4; MemFree(x)
0x10011524  jmp     loc_100116E2
0x10011529  lea     eax, [ebx+1Ch]
0x1001152c  or      edx, 10000h
0x10011532  push    eax; ppstgOpen
0x10011533  push    0; reserved
0x10011535  push    0; snbExclude
0x10011537  push    edx; grfMode
0x10011538  push    0; pstgPriority
0x1001153a  push    edi; pwcsName
0x1001153b  call    ds:__imp__StgOpenStorage@24; StgOpenStorage(x,x,x,x,x,x)
0x10011541  mov     ecx, eax
0x10011543  test    ecx, ecx
0x10011545  jz      short loc_100115AD
0x10011547  cmp     ecx, 80030002h
0x1001154d  jz      short loc_100114FB
0x1001154f  cmp     ecx, 80030003h
0x10011555  jz      short loc_100114FB
0x10011557  cmp     ecx, 80030004h
0x1001155d  jz      short loc_100114E7
0x1001155f  cmp     ecx, 80030005h
0x10011565  jz      short loc_1001159C
0x10011567  cmp     ecx, 80030021h
0x1001156d  jz      short loc_1001159C
0x1001156f  cmp     ecx, 80030020h
0x10011575  jz      short loc_1001159C
0x10011577  cmp     ecx, 80030050h
0x1001157d  mov     edx, 0FFFFFFF8h
0x10011582  mov     eax, 0FFFFFFFEh
0x10011587  mov     ecx, ebx
0x10011589  cmovz   eax, edx
0x1001158c  mov     [esp+288h+var_278], eax
0x10011590  mov     esi, eax
0x10011592  call    _MemFree@4; MemFree(x)
0x10011597  jmp     loc_100116E2
0x1001159c  mov     ecx, ebx
0x1001159e  mov     esi, 0FFFFFFFEh
0x100115a3  call    _MemFree@4; MemFree(x)
0x100115a8  jmp     loc_100116E2
0x100115ad  mov     dword ptr [ebx+0Ch], 1
0x100115b4  mov     dword ptr [ebx+24h], 1
0x100115bb  push    0FDF4h; dwBytes
0x100115c0  push    2002h; uFlags
0x100115c5  call    ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x100115cb  mov     edi, eax
0x100115cd  test    edi, edi
0x100115cf  jz      loc_100116CF
0x100115d5  push    edi; hMem
0x100115d6  call    ds:__imp__GlobalLock@4; GlobalLock(x)
0x100115dc  mov     esi, eax
0x100115de  test    esi, esi
0x100115e0  jz      loc_100116CF
0x100115e6  push    0FDE8h; Size
0x100115eb  mov     [esi+8], edi
0x100115ee  lea     edi, [esi+0Ch]
0x100115f1  push    0; Val
0x100115f3  push    edi; void *
0x100115f4  mov     dword ptr [esi+4], 0FDE8h
0x100115fb  call    _memset
0x10011600  add     esp, 0Ch
0x10011603  mov     dword ptr [esi], 1
0x10011609  test    edi, edi
0x1001160b  jz      loc_100116CF
0x10011611  cmp     dword ptr [ebx+0Ch], 0
0x10011615  mov     [ebx+4], edi
0x10011618  mov     dword ptr [ebx+40h], 0FDE8h
0x1001161f  mov     dword ptr [ebx+54h], 0
0x10011626  mov     dword ptr [ebx+50h], 0
0x1001162d  mov     dword ptr [ebx], 0
0x10011633  mov     [ebx+8], edi
0x10011636  jnz     short loc_1001165B
0x10011638  push    0
0x1001163a  mov     edx, 2
0x1001163f  mov     ecx, ebx
0x10011641  call    OSSetFilePosition
0x10011646  lea     edx, [ebx+58h]
0x10011649  mov     ecx, ebx
0x1001164b  call    OSGetFilePosition
0x10011650  push    0
0x10011652  xor     edx, edx
0x10011654  mov     ecx, ebx
0x10011656  call    OSSetFilePosition
0x1001165b  cmp     [esp+288h+var_270], 0
0x10011660  mov     edi, [esp+288h+var_264]
0x10011664  mov     [edi+14h], ebx
0x10011667  mov     ebx, [ebp+arg_0]
0x1001166a  jz      short loc_10011687
0x1001166c  mov     edx, ebx
0x1001166e  mov     ecx, edi
0x10011670  call    OpenWorkbookStream
0x10011675  mov     esi, eax
0x10011677  test    esi, esi
0x10011679  jz      short loc_10011687
0x1001167b  mov     ecx, [edi+14h]
0x1001167e  call    _BFCloseFile@4; BFCloseFile(x)
0x10011683  mov     ecx, edi
0x10011685  jmp     short loc_100116E6
  ... truncated ...
```
