# WorkbookSheetOpen(x,x,x,x)

- ea: `0x1001b4b0`
- end: `0x1001b5d0`
- name: `_WorkbookSheetOpen@16`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10027e33`
- `0x1002db68`

## callees

- `0x10011a70`
- `0x10011dd0`
- `0x10012270`
- `0x1001b4b0`
- `0x1001c2b0`
- `0x1001f420`
- `0x1002580a`
- `0x10025ab7`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001b4de`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001b4de`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001b4e5`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001b4e5`

## pseudocode

```c
int __fastcall WorkbookSheetOpen(_DWORD *a1, int a2, int a3, _DWORD *a4)
{
  _DWORD *v4; // esi
  int v5; // eax
  LCID UserDefaultLCID; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // edi
  int v10; // esi
  int **v11; // esi
  int v12; // ebx
  int *v13; // ecx
  int v14; // [esp-8h] [ebp-20h]

  v4 = (_DWORD *)a1[20];
  v5 = a2;
  if ( !v4 )
    return -1305;
  while ( 1 )
  {
    v14 = v5;
    UserDefaultLCID = GetUserDefaultLCID();
    if ( DBCompareStringW(UserDefaultLCID, 196609, (char *)v4 + 14, -1, v14, -1) == 2 )
      break;
    v4 = (_DWORD *)*v4;
    v5 = a2;
    if ( !v4 )
      return -1305;
  }
  v8 = (_DWORD *)MemAllocate(812);
  v9 = v8;
  if ( !v8 )
    return -1011;
  *v8 = 1;
  v8[1] = a1[1];
  v8[201] = a1;
  v8[199] = v4;
  if ( a1[3] )
  {
    v10 = XLOLESheetAttach(a1, v8);
    if ( v10 )
    {
      MemFree(v9);
      return TranslateEXErrorToJETError(v10);
    }
    v9[4] = -1;
    goto LABEL_11;
  }
  v11 = (int **)(v8 + 2);
  v12 = ExcelOpenSheet(a1, v8 + 2);
  if ( !v12 )
  {
    v13 = *v11;
    dword_1003A9C4 = (int)v9;
    v12 = ExcelScanFile(v13, dword_100383F0, 0);
    if ( v12 >= 0 )
    {
LABEL_11:
      *a4 = v9;
      return 0;
    }
    ExcelCloseSheet(*v11);
  }
  MemFree(v9);
  return TranslateEXErrorToJETError(v12);
}

```

## disassembly

```asm
0x1001b4b0  mov     edi, edi
0x1001b4b2  push    ebp
0x1001b4b3  mov     ebp, esp
0x1001b4b5  sub     esp, 0Ch
0x1001b4b8  push    ebx
0x1001b4b9  push    esi
0x1001b4ba  mov     esi, [ecx+50h]
0x1001b4bd  mov     eax, edx
0x1001b4bf  mov     [ebp+var_4], eax
0x1001b4c2  mov     [ebp+var_8], ecx
0x1001b4c5  push    edi
0x1001b4c6  test    esi, esi
0x1001b4c8  jz      short loc_1001B4F9
0x1001b4ca  nop     word ptr [eax+eax+00h]
0x1001b4d0  push    0FFFFFFFFh
0x1001b4d2  push    eax
0x1001b4d3  push    0FFFFFFFFh
0x1001b4d5  lea     ebx, [esi+0Eh]
0x1001b4d8  push    ebx
0x1001b4d9  push    30001h
0x1001b4de  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001b4e4  push    eax
0x1001b4e5  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001b4eb  sub     eax, 2
0x1001b4ee  jz      short loc_1001B507
0x1001b4f0  mov     esi, [esi]
0x1001b4f2  mov     eax, [ebp+var_4]
0x1001b4f5  test    esi, esi
0x1001b4f7  jnz     short loc_1001B4D0
0x1001b4f9  mov     eax, 0FFFFFAE7h
0x1001b4fe  pop     edi
0x1001b4ff  pop     esi
0x1001b500  pop     ebx
0x1001b501  mov     esp, ebp
0x1001b503  pop     ebp
0x1001b504  retn    8
0x1001b507  mov     ecx, 32Ch
0x1001b50c  call    _MemAllocate@4; MemAllocate(x)
0x1001b511  mov     edi, eax
0x1001b513  test    edi, edi
0x1001b515  jnz     short loc_1001B525
0x1001b517  mov     eax, 0FFFFFC0Dh
0x1001b51c  pop     edi
0x1001b51d  pop     esi
0x1001b51e  pop     ebx
0x1001b51f  mov     esp, ebp
0x1001b521  pop     ebp
0x1001b522  retn    8
0x1001b525  mov     ecx, [ebp+var_8]
0x1001b528  mov     dword ptr [edi], 1
0x1001b52e  mov     eax, [ecx+4]
0x1001b531  mov     [edi+4], eax
0x1001b534  mov     [edi+324h], ecx
0x1001b53a  mov     [edi+31Ch], esi
0x1001b540  cmp     dword ptr [ecx+0Ch], 0
0x1001b544  jz      short loc_1001B584
0x1001b546  mov     edx, [ebp+var_4]
0x1001b549  push    edi
0x1001b54a  push    ecx
0x1001b54b  call    _XLOLESheetAttach@16; XLOLESheetAttach(x,x,x,x)
0x1001b550  mov     esi, eax
0x1001b552  test    esi, esi
0x1001b554  jz      short loc_1001B56D
0x1001b556  mov     ecx, edi
0x1001b558  call    _MemFree@4; MemFree(x)
0x1001b55d  mov     ecx, esi
0x1001b55f  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001b564  pop     edi
0x1001b565  pop     esi
0x1001b566  pop     ebx
0x1001b567  mov     esp, ebp
0x1001b569  pop     ebp
0x1001b56a  retn    8
0x1001b56d  mov     dword ptr [edi+10h], 0FFFFFFFFh
0x1001b574  mov     eax, [ebp+arg_4]
0x1001b577  mov     [eax], edi
0x1001b579  xor     eax, eax
0x1001b57b  pop     edi
0x1001b57c  pop     esi
0x1001b57d  pop     ebx
0x1001b57e  mov     esp, ebp
0x1001b580  pop     ebp
0x1001b581  retn    8
0x1001b584  lea     esi, [edi+8]
0x1001b587  mov     edx, ebx
0x1001b589  push    esi
0x1001b58a  push    ecx
0x1001b58b  mov     ecx, [ecx+8]
0x1001b58e  call    _ExcelOpenSheet@16; ExcelOpenSheet(x,x,x,x)
0x1001b593  mov     ebx, eax
0x1001b595  test    ebx, ebx
0x1001b597  jnz     short loc_1001B5B9
0x1001b599  mov     ecx, [esi]
0x1001b59b  mov     edx, offset dword_100383F0
0x1001b5a0  push    eax
0x1001b5a1  mov     dword_1003A9C4, edi
0x1001b5a7  call    _ExcelScanFile@12; ExcelScanFile(x,x,x)
0x1001b5ac  mov     ebx, eax
0x1001b5ae  test    ebx, ebx
0x1001b5b0  jns     short loc_1001B574
0x1001b5b2  mov     ecx, [esi]
0x1001b5b4  call    _ExcelCloseSheet@4; ExcelCloseSheet(x)
0x1001b5b9  mov     ecx, edi
0x1001b5bb  call    _MemFree@4; MemFree(x)
0x1001b5c0  mov     ecx, ebx
0x1001b5c2  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001b5c7  pop     edi
0x1001b5c8  pop     esi
0x1001b5c9  pop     ebx
0x1001b5ca  mov     esp, ebp
0x1001b5cc  pop     ebp
0x1001b5cd  retn    8
```
