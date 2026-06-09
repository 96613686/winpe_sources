# WBTCloseTable(x,x)

- ea: `0x10029730`
- end: `0x10029a21`
- name: `_WBTCloseTable@8`
- size: `753`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x100279f0`
- `0x1002b3b3`
- `0x1002bee0`

## callees

- `0x10016060`
- `0x1001b770`
- `0x1001bbd0`
- `0x1001bc20`
- `0x1001c2b0`
- `0x1001d870`
- `0x10025ab7`
- `0x100279f0`
- `0x10028429`
- `0x10029648`
- `0x100296d0`
- `0x10029730`
- `0x1002a7de`
- `0x1002ab35`
- `0x1002ac5e`
- `0x1002acaf`
- `0x1002db68`
- `0x10031f44`
- `0x10034bca`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100297ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100297ab`

## pseudocode

```c
int __stdcall WBTCloseTable(int a1, int a2)
{
  int v2; // eax
  int v3; // esi
  int v5; // edi
  int TableWithColumns; // ecx
  int v7; // eax
  int v8; // eax
  _DWORD *i; // ebx
  DWORD CurrentProcessId; // eax
  int v11; // eax
  _DWORD *v12; // eax
  int v13; // esi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // esi
  int v19; // edx
  _DWORD *v20; // ecx
  _DWORD *v21; // ecx
  int v22; // esi
  int v23; // ecx
  _DWORD *v24; // ecx
  _DWORD *v25; // ecx
  _DWORD *v26; // eax
  _DWORD *j; // esi
  int v28; // [esp-4h] [ebp-24h]
  int v29; // [esp+10h] [ebp-10h]
  int v30; // [esp+14h] [ebp-Ch]
  int v31; // [esp+1Ch] [ebp-4h]

  v2 = ISAMDBFindCursor(a1, a2);
  v3 = v2;
  v30 = v2;
  if ( !v2 )
    return -1310;
  v5 = *(_DWORD *)(v2 + 4);
  v29 = 0;
  if ( *(_DWORD *)(v5 + 56) == 1 )
  {
    TableWithColumns = CreateTableWithColumns(v5, v2);
    v29 = TableWithColumns;
    if ( TableWithColumns )
    {
      v7 = 0;
      *(_DWORD *)(v5 + 64) = 0;
      if ( TableWithColumns != -1312 )
        v7 = TableWithColumns;
      v29 = v7;
    }
  }
  CopyBufferClear(v3);
  v8 = *(_DWORD *)(v3 + 8);
  i = *(_DWORD **)(v8 + 4);
  v31 = *(_DWORD *)(v8 + 8);
  CurrentProcessId = GetCurrentProcessId();
  v11 = ISAMDBFindTask(CurrentProcessId);
  (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)(v11 + 28) + 68))(
    *(_DWORD *)(*(_DWORD *)(v11 + 28) + 68),
    *(_DWORD *)(v3 + 16));
  ISAMDBDeleteCursor(v5, v30);
  if ( *(_DWORD *)(v5 + 20) )
    return v29;
  TableCacheAdd(i, v5);
  if ( i[8] == 1 && *(_DWORD *)(v5 + 84) <= 1u )
    ExceptionsTableClose(*(JET_SESID **)(v5 + 88));
  if ( *(_DWORD *)(v5 + 64) != 1 )
    goto LABEL_27;
  v12 = (_DWORD *)i[7];
  v13 = 0;
  while ( v12 && v12 != *(_DWORD **)(v5 + 8) )
  {
    v12 = (_DWORD *)*v12;
    ++v13;
  }
  v14 = *(_DWORD *)(v5 + 48);
  if ( v14 || *(_DWORD *)(v5 + 52) )
  {
    if ( *(_DWORD *)(v5 + 76) == 1 && !v14 )
    {
      WorkbookRangeRange(v5 + 96);
      v18 = WorkbookNameUpdate(
              *(_DWORD *)(v5 + 12),
              (wchar_t *)(v5 + 104),
              v23,
              0,
              *(_DWORD *)(v5 + 96),
              *(_DWORD *)(v5 + 100));
      WorkbookRangeDelete(*(_DWORD *)(v5 + 12), *(_DWORD *)(v5 + 16));
      *(_DWORD *)(v5 + 16) = 0;
      goto LABEL_26;
    }
LABEL_27:
    v19 = *(_DWORD *)(v5 + 16);
    if ( v19 )
    {
      WorkbookRangeDelete(*(_DWORD *)(v5 + 12), v19);
      *(_DWORD *)(v5 + 16) = 0;
    }
    v20 = *(_DWORD **)(v5 + 92);
    if ( v20 )
      MemFree(v20);
    if ( *(_DWORD *)(v5 + 68) == 1 && (*(_DWORD *)(v5 + 48) == 1 || *(_DWORD *)(v5 + 52) == 1) )
      AddToDeletedTableList(i, v5);
    v21 = *(_DWORD **)(v5 + 12);
    if ( v21 && v21 != (_DWORD *)i[3] )
      WorkbookSheetClose(v21);
    if ( *(_DWORD *)(v5 + 76) != 1 || *(_DWORD *)(v5 + 20) )
    {
LABEL_58:
      ISAMDBDeleteTable(i, v5);
    }
    else
    {
      v22 = i[1];
      WBDBCloseDatabase(*(_DWORD *)(v31 + 12), *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(v5 + 4) + 44) + 12), 0);
      for ( i = *(_DWORD **)(v22 + 8); i; i = (_DWORD *)*i )
      {
        for ( j = (_DWORD *)i[12]; j; j = (_DWORD *)*j )
        {
          if ( j == (_DWORD *)v5 )
            goto LABEL_58;
        }
      }
    }
    return v29;
  }
  v28 = v5 + 96;
  if ( *(_DWORD *)(v5 + 60) == 1 )
  {
    WorkbookRangeRange(v28);
    if ( *(_DWORD *)(*(_DWORD *)(v5 + 12) + 12) )
      v15 = 0;
    else
      v15 = ExcelAddName(
              (LPCWCH)(v5 + 104),
              v13,
              HIWORD(*(_DWORD *)(v5 + 96)),
              *(_DWORD *)(v5 + 96),
              *(_DWORD *)(v5 + 100));
    v16 = TranslateEXErrorToJETError(v15);
  }
  else
  {
    WorkbookRangeRange(v28);
    *(_DWORD *)(v5 + 68) = 0;
    RemoveFromDeletedTableList(i, v5);
    v16 = WorkbookNameUpdate(
            *(_DWORD *)(v5 + 12),
            (wchar_t *)(v5 + 104),
            v17,
            1,
            *(_DWORD *)(v5 + 96),
            *(_DWORD *)(v5 + 100));
  }
  v18 = v16;
LABEL_26:
  if ( !v18 )
    goto LABEL_27;
  v24 = *(_DWORD **)(v5 + 92);
  if ( v24 )
    MemFree(v24);
  v25 = *(_DWORD **)(v5 + 12);
  v26 = v25;
  if ( v25 && v25 != (_DWORD *)i[3] )
  {
    WorkbookSheetClose(v25);
    *(_DWORD *)(v5 + 12) = 0;
    v26 = 0;
  }
  WorkbookRangeDelete(v26, *(_DWORD *)(v5 + 16));
  *(_DWORD *)(v5 + 16) = 0;
  ISAMDBDeleteTable(i, v5);
  return v18;
}

```

## disassembly

```asm
0x10029730  mov     edi, edi
0x10029732  push    ebp
0x10029733  mov     ebp, esp
0x10029735  and     esp, 0FFFFFFF8h
0x10029738  sub     esp, 14h
0x1002973b  mov     edx, [ebp+arg_4]
0x1002973e  mov     ecx, [ebp+arg_0]
0x10029741  push    ebx
0x10029742  push    esi
0x10029743  push    edi
0x10029744  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x10029749  mov     esi, eax
0x1002974b  mov     [esp+20h+var_C], esi
0x1002974f  test    esi, esi
0x10029751  jnz     short loc_1002975D
0x10029753  mov     eax, 0FFFFFAE2h
0x10029758  jmp     loc_10029A18
0x1002975d  mov     edi, [esi+4]
0x10029760  mov     [esp+20h+var_10], 0
0x10029768  cmp     dword ptr [edi+38h], 1
0x1002976c  jnz     short loc_10029797
0x1002976e  mov     edx, esi
0x10029770  mov     ecx, edi
0x10029772  call    _CreateTableWithColumns@8; CreateTableWithColumns(x,x)
0x10029777  mov     ecx, eax
0x10029779  mov     [esp+20h+var_10], ecx
0x1002977d  test    ecx, ecx
0x1002977f  jz      short loc_10029797
0x10029781  xor     eax, eax
0x10029783  mov     dword ptr [edi+40h], 0
0x1002978a  cmp     ecx, 0FFFFFAE0h
0x10029790  cmovnz  eax, ecx
0x10029793  mov     [esp+20h+var_10], eax
0x10029797  mov     ecx, esi
0x10029799  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002979e  mov     eax, [esi+8]
0x100297a1  mov     ebx, [eax+4]
0x100297a4  mov     eax, [eax+8]
0x100297a7  mov     [esp+20h+var_4], eax
0x100297ab  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x100297b1  mov     ecx, eax
0x100297b3  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x100297b8  push    dword ptr [esi+10h]
0x100297bb  mov     eax, [eax+1Ch]
0x100297be  mov     esi, [eax+44h]
0x100297c1  mov     ecx, esi
0x100297c3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100297c9  call    esi
0x100297cb  mov     edx, [esp+20h+var_C]
0x100297cf  mov     ecx, edi
0x100297d1  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x100297d6  cmp     dword ptr [edi+14h], 0
0x100297da  jnz     loc_10029A14
0x100297e0  mov     edx, edi
0x100297e2  mov     ecx, ebx
0x100297e4  call    TableCacheAdd
0x100297e9  cmp     dword ptr [ebx+20h], 1
0x100297ed  jnz     short loc_10029803
0x100297ef  cmp     dword ptr [edi+54h], 1
0x100297f3  jz      short loc_100297FB
0x100297f5  cmp     dword ptr [edi+54h], 0
0x100297f9  jnz     short loc_10029803
0x100297fb  mov     ecx, [edi+58h]
0x100297fe  call    _ExceptionsTableClose@4; ExceptionsTableClose(x)
0x10029803  cmp     dword ptr [edi+40h], 1
0x10029807  jnz     loc_100298CE
0x1002980d  mov     eax, [ebx+1Ch]
0x10029810  xor     esi, esi
0x10029812  jmp     short loc_1002981C
0x10029814  cmp     eax, [edi+8]
0x10029817  jz      short loc_10029820
0x10029819  mov     eax, [eax]
0x1002981b  inc     esi
0x1002981c  test    eax, eax
0x1002981e  jnz     short loc_10029814
0x10029820  mov     eax, [edi+30h]
0x10029823  test    eax, eax
0x10029825  jnz     loc_10029952
0x1002982b  cmp     [edi+34h], eax
0x1002982e  jnz     loc_10029952
0x10029834  cmp     dword ptr [edi+3Ch], 1
0x10029838  lea     eax, [edi+60h]
0x1002983b  mov     edx, [edi+10h]
0x1002983e  mov     ecx, [edi+0Ch]
0x10029841  push    eax
0x10029842  jnz     short loc_1002989B
0x10029844  call    _WorkbookRangeRange@12; WorkbookRangeRange(x,x,x)
0x10029849  mov     edx, [edi+0Ch]
0x1002984c  mov     ecx, [edi+60h]
0x1002984f  mov     eax, [edi+64h]
0x10029852  cmp     dword ptr [edx+0Ch], 0
0x10029856  jz      short loc_1002985C
0x10029858  xor     eax, eax
0x1002985a  jmp     short loc_10029892
0x1002985c  mov     word ptr [esp+20h+var_8], ax
0x10029861  mov     word ptr [esp+20h+var_C], cx
0x10029866  shr     eax, 10h
0x10029869  shr     ecx, 10h
0x1002986c  mov     word ptr [esp+20h+var_8+2], ax
0x10029871  lea     eax, [edi+68h]
0x10029874  push    [esp+20h+var_8]; int
0x10029878  mov     word ptr [esp+24h+var_C+2], cx
0x1002987d  push    [esp+24h+var_C]; int
0x10029881  push    ecx; int
0x10029882  mov     ecx, [edx+324h]
0x10029888  push    esi; int
0x10029889  push    eax; lpWideCharStr
0x1002988a  mov     ecx, [ecx+8]
0x1002988d  call    _ExcelAddName@28; ExcelAddName(x,x,x,x,x,x,x)
0x10029892  mov     ecx, eax
0x10029894  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x10029899  jmp     short loc_100298C4
0x1002989b  call    _WorkbookRangeRange@12; WorkbookRangeRange(x,x,x)
0x100298a0  mov     edx, edi
0x100298a2  mov     dword ptr [edi+44h], 0
0x100298a9  mov     ecx, ebx
0x100298ab  call    RemoveFromDeletedTableList
0x100298b0  push    dword ptr [edi+64h]
0x100298b3  lea     edx, [edi+68h]
0x100298b6  push    dword ptr [edi+60h]
0x100298b9  push    1
0x100298bb  push    ecx
0x100298bc  mov     ecx, [edi+0Ch]
0x100298bf  call    _WorkbookNameUpdate@24; WorkbookNameUpdate(x,x,x,x,x,x)
0x100298c4  mov     esi, eax
0x100298c6  test    esi, esi
0x100298c8  jnz     loc_1002999F
0x100298ce  mov     edx, [edi+10h]
0x100298d1  test    edx, edx
0x100298d3  jz      short loc_100298E4
0x100298d5  mov     ecx, [edi+0Ch]
0x100298d8  call    _WorkbookRangeDelete@8; WorkbookRangeDelete(x,x)
0x100298dd  mov     dword ptr [edi+10h], 0
0x100298e4  mov     ecx, [edi+5Ch]
0x100298e7  test    ecx, ecx
0x100298e9  jz      short loc_100298F0
0x100298eb  call    _MemFree@4; MemFree(x)
0x100298f0  cmp     dword ptr [edi+44h], 1
0x100298f4  jnz     short loc_1002990B
0x100298f6  cmp     dword ptr [edi+30h], 1
0x100298fa  jz      short loc_10029902
0x100298fc  cmp     dword ptr [edi+34h], 1
0x10029900  jnz     short loc_1002990B
0x10029902  mov     edx, edi
0x10029904  mov     ecx, ebx
0x10029906  call    AddToDeletedTableList
0x1002990b  mov     ecx, [edi+0Ch]
0x1002990e  test    ecx, ecx
0x10029910  jz      short loc_1002991C
0x10029912  cmp     ecx, [ebx+0Ch]
0x10029915  jz      short loc_1002991C
0x10029917  call    _WorkbookSheetClose@4; WorkbookSheetClose(x)
0x1002991c  cmp     dword ptr [edi+4Ch], 1
0x10029920  jnz     loc_10029A0B
0x10029926  cmp     dword ptr [edi+14h], 0
0x1002992a  jnz     loc_10029A0B
0x10029930  mov     eax, [edi+4]
0x10029933  mov     esi, [ebx+4]
0x10029936  push    0
0x10029938  mov     eax, [eax+2Ch]
0x1002993b  push    dword ptr [eax+0Ch]
0x1002993e  mov     eax, [esp+28h+var_4]
0x10029942  push    dword ptr [eax+0Ch]
0x10029945  call    _WBDBCloseDatabase@12; WBDBCloseDatabase(x,x,x)
0x1002994a  mov     ebx, [esi+8]
0x1002994d  jmp     loc_10029A05
0x10029952  cmp     dword ptr [edi+4Ch], 1
0x10029956  jnz     loc_100298CE
0x1002995c  test    eax, eax
0x1002995e  jnz     loc_100298CE
0x10029964  mov     edx, [edi+10h]
0x10029967  lea     esi, [edi+60h]
0x1002996a  mov     ecx, [edi+0Ch]
0x1002996d  push    esi
0x1002996e  call    _WorkbookRangeRange@12; WorkbookRangeRange(x,x,x)
0x10029973  push    dword ptr [esi+4]
0x10029976  lea     edx, [edi+68h]
0x10029979  push    dword ptr [esi]
0x1002997b  push    0
0x1002997d  push    ecx
0x1002997e  mov     ecx, [edi+0Ch]
0x10029981  call    _WorkbookNameUpdate@24; WorkbookNameUpdate(x,x,x,x,x,x)
0x10029986  mov     edx, [edi+10h]
0x10029989  mov     esi, eax
0x1002998b  mov     ecx, [edi+0Ch]
0x1002998e  call    _WorkbookRangeDelete@8; WorkbookRangeDelete(x,x)
0x10029993  mov     dword ptr [edi+10h], 0
0x1002999a  jmp     loc_100298C6
0x1002999f  mov     ecx, [edi+5Ch]
0x100299a2  test    ecx, ecx
0x100299a4  jz      short loc_100299AB
0x100299a6  call    _MemFree@4; MemFree(x)
0x100299ab  mov     ecx, [edi+0Ch]
0x100299ae  mov     eax, ecx
0x100299b0  test    ecx, ecx
0x100299b2  jz      short loc_100299C7
0x100299b4  cmp     ecx, [ebx+0Ch]
0x100299b7  jz      short loc_100299C7
0x100299b9  call    _WorkbookSheetClose@4; WorkbookSheetClose(x)
0x100299be  mov     dword ptr [edi+0Ch], 0
0x100299c5  xor     eax, eax
0x100299c7  mov     edx, [edi+10h]
0x100299ca  mov     ecx, eax
0x100299cc  call    _WorkbookRangeDelete@8; WorkbookRangeDelete(x,x)
0x100299d1  mov     edx, edi
0x100299d3  mov     dword ptr [edi+10h], 0
0x100299da  mov     ecx, ebx
0x100299dc  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100299e1  mov     eax, esi
0x100299e3  jmp     short loc_10029A18
0x100299e5  mov     esi, [ebx+30h]
0x100299e8  jmp     short loc_100299F0
0x100299ea  cmp     esi, edi
0x100299ec  jz      short loc_100299F6
0x100299ee  mov     esi, [esi]
0x100299f0  test    esi, esi
0x100299f2  jnz     short loc_100299EA
0x100299f4  jmp     short loc_10029A03
0x100299f6  mov     edx, edi
0x100299f8  mov     ecx, ebx
0x100299fa  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x100299ff  test    esi, esi
0x10029a01  jnz     short loc_10029A14
0x10029a03  mov     ebx, [ebx]
0x10029a05  test    ebx, ebx
0x10029a07  jnz     short loc_100299E5
0x10029a09  jmp     short loc_10029A14
0x10029a0b  mov     edx, edi
0x10029a0d  mov     ecx, ebx
0x10029a0f  call    _ISAMDBDeleteTable@8; ISAMDBDeleteTable(x,x)
0x10029a14  mov     eax, [esp+20h+var_10]
0x10029a18  pop     edi
0x10029a19  pop     esi
0x10029a1a  pop     ebx
0x10029a1b  mov     esp, ebp
0x10029a1d  pop     ebp
0x10029a1e  retn    8
```
