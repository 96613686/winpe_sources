# GetLocalizedNames

- ea: `0x1001cb30`
- end: `0x1001cff0`
- name: `GetLocalizedNames`
- size: `1216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1001c680`

## callees

- `0x1001cb30`
- `0x1002b070`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1001cb91`
- `KERNEL32!GetProcAddress` at `0x1001cb91`
- `KERNEL32!FreeLibrary` at `0x1001cb46`
- `KERNEL32!FreeLibrary` at `0x1001ccc6`
- `KERNEL32!FreeLibrary` at `0x1001cb46`
- `KERNEL32!FreeLibrary` at `0x1001ccc6`

## string_xrefs

- `0x1001cb35`: `MSJINT40.DLL`

## pseudocode

```c
int __stdcall GetLocalizedNames(int a1)
{
  HMODULE LibraryW; // eax
  HMODULE v2; // ebp
  _WORD *v3; // edi
  _WORD *v4; // ecx
  int v5; // edx
  __int16 v6; // ax
  FARPROC CchLszOfId2; // eax
  void (__stdcall *v8)(int, int, int); // ebx
  _WORD *v9; // esi
  _WORD *v11; // esi
  _WORD *v13; // esi
  _WORD *v15; // esi
  _WORD *v17; // esi
  int v19; // esi
  const unsigned __int16 *i; // edi
  int result; // eax
  int v22; // edx
  _WORD *v23; // ecx
  __int16 v24; // ax
  int v25; // edx
  _WORD *v26; // ecx
  __int16 v27; // ax
  int v28; // edx
  _WORD *v29; // ecx
  __int16 v30; // ax
  int v31; // edx
  _WORD *v32; // ecx
  __int16 v33; // ax
  int v34; // edx
  _WORD *v35; // ecx
  __int16 v36; // ax
  int v37; // edx
  _WORD *v38; // ecx
  __int16 v39; // ax
  int v40; // edx
  _WORD *v41; // ecx
  __int16 v42; // ax
  int v43; // edx
  _WORD *v44; // ecx
  __int16 v45; // ax
  int v46; // edx
  _WORD *v47; // ecx
  __int16 v48; // ax
  int v49; // edx
  _WORD *v50; // ecx
  __int16 v51; // ax
  int v52; // edx
  _WORD *v53; // ecx
  __int16 v54; // ax
  int v55; // edx
  _WORD *v56; // ecx
  __int16 v57; // ax

  LibraryW = (HMODULE)JetLoadLibraryW(L"MSJINT40.DLL");
  v2 = LibraryW;
  if ( !LibraryW )
  {
    FreeLibrary(0);
LABEL_3:
    v3 = (_WORD *)a1;
    goto LABEL_4;
  }
  CchLszOfId2 = GetProcAddress(LibraryW, "CchLszOfId2");
  v8 = (void (__stdcall *)(int, int, int))CchLszOfId2;
  if ( !CchLszOfId2 )
    goto LABEL_3;
  v3 = (_WORD *)a1;
  v9 = (_WORD *)(a1 + 158);
  ((void (__stdcall *)(int, int, int))CchLszOfId2)(10060, a1 + 158, 130);
  while ( *v9++ )
    ;
  if ( ((int)v9 - a1 - 160) >> 1 )
  {
    v11 = (_WORD *)(a1 + 288);
    v8(10061, a1 + 288, 130);
    while ( *v11++ )
      ;
    if ( ((int)v11 - a1 - 290) >> 1 )
    {
      v13 = (_WORD *)(a1 + 418);
      v8(10062, a1 + 418, 130);
      while ( *v13++ )
        ;
      if ( ((int)v13 - a1 - 420) >> 1 )
      {
        v15 = (_WORD *)(a1 + 548);
        v8(10063, a1 + 548, 130);
        while ( *v15++ )
          ;
        if ( ((int)v15 - a1 - 550) >> 1 )
        {
          v17 = (_WORD *)(a1 + 678);
          v8(10064, a1 + 678, 130);
          while ( *v17++ )
            ;
          if ( ((int)v17 - a1 - 680) >> 1 )
          {
            v19 = 0;
            for ( i = (const unsigned __int16 *)(a1 + 808); ; i += 65 )
            {
              v8(v19 + 10065, (int)i, 130);
              if ( !wcslen(i) )
                break;
              if ( ++v19 > 7 )
              {
                FreeLibrary(v2);
                return 0;
              }
            }
            goto LABEL_3;
          }
        }
      }
    }
  }
LABEL_4:
  v4 = v3 + 79;
  v5 = 65;
  while ( v5 != -2147483581 )
  {
    v6 = *(_WORD *)((char *)v4 + (char *)L"ImportErrors" - (char *)(v3 + 79));
    if ( !v6 )
      break;
    *v4++ = v6;
    if ( !--v5 )
    {
      --v4;
      break;
    }
  }
  *v4 = 0;
  v22 = 65;
  v23 = v3 + 144;
  while ( v22 != -2147483581 )
  {
    v24 = *(_WORD *)((char *)v23 + (char *)L"ExportErrors" - (char *)(v3 + 144));
    if ( !v24 )
      break;
    *v23++ = v24;
    if ( !--v22 )
    {
      --v23;
      break;
    }
  }
  *v23 = 0;
  v25 = 65;
  v26 = v3 + 209;
  while ( v25 != -2147483581 )
  {
    v27 = *(_WORD *)((char *)v26 + (char *)L"Error" - (char *)(v3 + 209));
    if ( !v27 )
      break;
    *v26++ = v27;
    if ( !--v25 )
    {
      --v26;
      break;
    }
  }
  *v26 = 0;
  v28 = 65;
  v29 = v3 + 274;
  while ( v28 != -2147483581 )
  {
    v30 = *(_WORD *)((char *)v29 + (char *)L"Field" - (char *)(v3 + 274));
    if ( !v30 )
      break;
    *v29++ = v30;
    if ( !--v28 )
    {
      --v29;
      break;
    }
  }
  *v29 = 0;
  v31 = 65;
  v32 = v3 + 339;
  while ( v31 != -2147483581 )
  {
    v33 = *(_WORD *)((char *)v32 + (char *)L"Row" - (char *)(v3 + 339));
    if ( !v33 )
      break;
    *v32++ = v33;
    if ( !--v31 )
    {
      --v32;
      break;
    }
  }
  *v32 = 0;
  v34 = 65;
  v35 = v3 + 404;
  while ( v34 != -2147483581 )
  {
    v36 = *(_WORD *)((char *)v35 + (char *)L"Unparsable Record" - (char *)(v3 + 404));
    if ( !v36 )
      break;
    *v35++ = v36;
    if ( !--v34 )
    {
      --v35;
      break;
    }
  }
  *v35 = 0;
  v37 = 65;
  v38 = v3 + 469;
  while ( v37 != -2147483581 )
  {
    v39 = *(_WORD *)((char *)v38 + (char *)L"Type Conversion Failure" - (char *)(v3 + 469));
    if ( !v39 )
      break;
    *v38++ = v39;
    if ( !--v37 )
    {
      --v38;
      break;
    }
  }
  *v38 = 0;
  v40 = 65;
  v41 = v3 + 534;
  while ( v40 != -2147483581 )
  {
    v42 = *(_WORD *)((char *)v41 + (char *)L"Row Truncation" - (char *)(v3 + 534));
    if ( !v42 )
      break;
    *v41++ = v42;
    if ( !--v40 )
    {
      --v41;
      break;
    }
  }
  *v41 = 0;
  v43 = 65;
  v44 = v3 + 599;
  while ( v43 != -2147483581 )
  {
    v45 = *(_WORD *)((char *)v44 + (char *)L"Field Truncation" - (char *)(v3 + 599));
    if ( !v45 )
      break;
    *v44++ = v45;
    if ( !--v43 )
    {
      --v44;
      break;
    }
  }
  *v44 = 0;
  v46 = 65;
  v47 = v3 + 664;
  while ( v46 != -2147483581 )
  {
    v48 = *(_WORD *)((char *)v47 + (char *)L"Date Out Of Range" - (char *)(v3 + 664));
    if ( !v48 )
      break;
    *v47++ = v48;
    if ( !--v46 )
    {
      --v47;
      break;
    }
  }
  *v47 = 0;
  v49 = 65;
  v50 = v3 + 729;
  while ( v49 != -2147483581 )
  {
    v51 = *(_WORD *)((char *)v50 + (char *)L"Rows dropped due to worksheet row limit" - (char *)(v3 + 729));
    if ( !v51 )
      break;
    *v50++ = v51;
    if ( !--v49 )
    {
      --v50;
      break;
    }
  }
  *v50 = 0;
  v52 = 65;
  v53 = v3 + 794;
  while ( v52 != -2147483581 )
  {
    v54 = *(_WORD *)((char *)v53 + (char *)L"Validation rule violation" - (char *)(v3 + 794));
    if ( !v54 )
      break;
    *v53++ = v54;
    if ( !--v52 )
    {
      --v53;
      break;
    }
  }
  *v53 = 0;
  v55 = 65;
  v56 = v3 + 859;
  while ( v55 != -2147483581 )
  {
    v57 = *(_WORD *)((char *)v56 + (char *)L"Null value in an auto-number field" - (char *)(v3 + 859));
    if ( !v57 )
      break;
    *v56++ = v57;
    if ( !--v55 )
    {
      result = 0;
      *(v56 - 1) = 0;
      return result;
    }
  }
  result = 0;
  *v56 = 0;
  return result;
}

```

## disassembly

```asm
0x1001cb30  push    ecx
0x1001cb31  push    ebx
0x1001cb32  push    ebp
0x1001cb33  push    esi
0x1001cb34  push    edi
0x1001cb35  push    offset aMsjint40Dll; "MSJINT40.DLL"
0x1001cb3a  call    _JetLoadLibraryW@4; JetLoadLibraryW(x)
0x1001cb3f  mov     ebp, eax
0x1001cb41  test    ebp, ebp
0x1001cb43  jnz     short loc_1001CB8B
0x1001cb45  push    eax; hLibModule
0x1001cb46  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001cb4c  mov     edi, [esp+14h+arg_0]
0x1001cb50  lea     ecx, [edi+9Eh]
0x1001cb56  mov     esi, offset aImporterrors; "ImportErrors"
0x1001cb5b  mov     edx, 41h ; 'A'
0x1001cb60  sub     esi, ecx
0x1001cb62  lea     eax, [edx+7FFFFFBDh]
0x1001cb68  test    eax, eax
0x1001cb6a  jz      loc_1001CCD6
0x1001cb70  movzx   eax, word ptr [esi+ecx]
0x1001cb74  test    ax, ax
0x1001cb77  jz      loc_1001CCD6
0x1001cb7d  mov     [ecx], ax
0x1001cb80  add     ecx, 2
0x1001cb83  dec     edx
0x1001cb84  jnz     short loc_1001CB62
0x1001cb86  jmp     loc_1001CCDA
0x1001cb8b  push    offset aCchlszofid2; "CchLszOfId2"
0x1001cb90  push    ebp; hModule
0x1001cb91  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1001cb97  mov     ebx, eax
0x1001cb99  test    ebx, ebx
0x1001cb9b  jz      short loc_1001CB4C
0x1001cb9d  mov     edi, [esp+14h+arg_0]
0x1001cba1  push    82h
0x1001cba6  lea     esi, [edi+9Eh]
0x1001cbac  push    esi
0x1001cbad  push    274Ch
0x1001cbb2  call    ebx
0x1001cbb4  lea     ecx, [esi+2]
0x1001cbb7  mov     ax, [esi]
0x1001cbba  add     esi, 2
0x1001cbbd  test    ax, ax
0x1001cbc0  jnz     short loc_1001CBB7
0x1001cbc2  sub     esi, ecx
0x1001cbc4  sar     esi, 1
0x1001cbc6  jz      short loc_1001CB50
0x1001cbc8  push    82h
0x1001cbcd  lea     esi, [edi+120h]
0x1001cbd3  push    esi
0x1001cbd4  push    274Dh
0x1001cbd9  call    ebx
0x1001cbdb  lea     ecx, [esi+2]
0x1001cbde  mov     edi, edi
0x1001cbe0  mov     ax, [esi]
0x1001cbe3  add     esi, 2
0x1001cbe6  test    ax, ax
0x1001cbe9  jnz     short loc_1001CBE0
0x1001cbeb  sub     esi, ecx
0x1001cbed  sar     esi, 1
0x1001cbef  jz      loc_1001CB50
0x1001cbf5  push    82h
0x1001cbfa  lea     esi, [edi+1A2h]
0x1001cc00  push    esi
0x1001cc01  push    274Eh
0x1001cc06  call    ebx
0x1001cc08  lea     ecx, [esi+2]
0x1001cc0b  jmp     short loc_1001CC10
0x1001cc10  mov     ax, [esi]
0x1001cc13  add     esi, 2
0x1001cc16  test    ax, ax
0x1001cc19  jnz     short loc_1001CC10
0x1001cc1b  sub     esi, ecx
0x1001cc1d  sar     esi, 1
0x1001cc1f  jz      loc_1001CB50
0x1001cc25  push    82h
0x1001cc2a  lea     esi, [edi+224h]
0x1001cc30  push    esi
0x1001cc31  push    274Fh
0x1001cc36  call    ebx
0x1001cc38  lea     ecx, [esi+2]
0x1001cc3b  jmp     short loc_1001CC40
0x1001cc40  mov     ax, [esi]
0x1001cc43  add     esi, 2
0x1001cc46  test    ax, ax
0x1001cc49  jnz     short loc_1001CC40
0x1001cc4b  sub     esi, ecx
0x1001cc4d  sar     esi, 1
0x1001cc4f  jz      loc_1001CB50
0x1001cc55  push    82h
0x1001cc5a  lea     esi, [edi+2A6h]
0x1001cc60  push    esi
0x1001cc61  push    2750h
0x1001cc66  call    ebx
0x1001cc68  lea     ecx, [esi+2]
0x1001cc6b  jmp     short loc_1001CC70
0x1001cc70  mov     ax, [esi]
0x1001cc73  add     esi, 2
0x1001cc76  test    ax, ax
0x1001cc79  jnz     short loc_1001CC70
0x1001cc7b  sub     esi, ecx
0x1001cc7d  sar     esi, 1
0x1001cc7f  jz      loc_1001CB50
0x1001cc85  xor     esi, esi
0x1001cc87  add     edi, 328h
0x1001cc8d  lea     ecx, [ecx+0]
0x1001cc90  push    82h
0x1001cc95  push    edi
0x1001cc96  lea     eax, [esi+2751h]
0x1001cc9c  push    eax
0x1001cc9d  call    ebx
0x1001cc9f  mov     ecx, edi
0x1001cca1  lea     edx, [ecx+2]
0x1001cca4  mov     ax, [ecx]
0x1001cca7  add     ecx, 2
0x1001ccaa  test    ax, ax
0x1001ccad  jnz     short loc_1001CCA4
0x1001ccaf  sub     ecx, edx
0x1001ccb1  sar     ecx, 1
0x1001ccb3  jz      loc_1001CB4C
0x1001ccb9  inc     esi
0x1001ccba  add     edi, 82h
0x1001ccc0  cmp     esi, 7
0x1001ccc3  jle     short loc_1001CC90
0x1001ccc5  push    ebp; hLibModule
0x1001ccc6  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001cccc  pop     edi
0x1001cccd  pop     esi
0x1001ccce  pop     ebp
0x1001cccf  xor     eax, eax
0x1001ccd1  pop     ebx
0x1001ccd2  pop     ecx
0x1001ccd3  retn    4
0x1001ccd6  test    edx, edx
0x1001ccd8  jnz     short loc_1001CCDD
0x1001ccda  sub     ecx, 2
0x1001ccdd  xor     eax, eax
0x1001ccdf  mov     esi, offset aExporterrors; "ExportErrors"
0x1001cce4  mov     [ecx], ax
0x1001cce7  mov     edx, 41h ; 'A'
0x1001ccec  lea     ecx, [edi+120h]
0x1001ccf2  sub     esi, ecx
0x1001ccf4  lea     eax, [edx+7FFFFFBDh]
0x1001ccfa  test    eax, eax
0x1001ccfc  jz      short loc_1001CD12
0x1001ccfe  movzx   eax, word ptr [esi+ecx]
0x1001cd02  test    ax, ax
0x1001cd05  jz      short loc_1001CD12
0x1001cd07  mov     [ecx], ax
0x1001cd0a  add     ecx, 2
0x1001cd0d  dec     edx
0x1001cd0e  jnz     short loc_1001CCF4
0x1001cd10  jmp     short loc_1001CD16
0x1001cd12  test    edx, edx
0x1001cd14  jnz     short loc_1001CD19
0x1001cd16  sub     ecx, 2
0x1001cd19  xor     eax, eax
0x1001cd1b  mov     esi, offset aError; "Error"
0x1001cd20  mov     [ecx], ax
0x1001cd23  mov     edx, 41h ; 'A'
0x1001cd28  lea     ecx, [edi+1A2h]
0x1001cd2e  sub     esi, ecx
0x1001cd30  lea     eax, [edx+7FFFFFBDh]
0x1001cd36  test    eax, eax
0x1001cd38  jz      short loc_1001CD4E
0x1001cd3a  movzx   eax, word ptr [esi+ecx]
0x1001cd3e  test    ax, ax
0x1001cd41  jz      short loc_1001CD4E
0x1001cd43  mov     [ecx], ax
0x1001cd46  add     ecx, 2
0x1001cd49  dec     edx
0x1001cd4a  jnz     short loc_1001CD30
0x1001cd4c  jmp     short loc_1001CD52
0x1001cd4e  test    edx, edx
0x1001cd50  jnz     short loc_1001CD55
0x1001cd52  sub     ecx, 2
0x1001cd55  xor     eax, eax
0x1001cd57  mov     esi, offset aField; "Field"
0x1001cd5c  mov     [ecx], ax
0x1001cd5f  mov     edx, 41h ; 'A'
0x1001cd64  lea     ecx, [edi+224h]
0x1001cd6a  sub     esi, ecx
0x1001cd6c  lea     esp, [esp+0]
0x1001cd70  lea     eax, [edx+7FFFFFBDh]
0x1001cd76  test    eax, eax
0x1001cd78  jz      short loc_1001CD8E
0x1001cd7a  movzx   eax, word ptr [esi+ecx]
0x1001cd7e  test    ax, ax
0x1001cd81  jz      short loc_1001CD8E
0x1001cd83  mov     [ecx], ax
0x1001cd86  add     ecx, 2
0x1001cd89  dec     edx
0x1001cd8a  jnz     short loc_1001CD70
0x1001cd8c  jmp     short loc_1001CD92
0x1001cd8e  test    edx, edx
0x1001cd90  jnz     short loc_1001CD95
0x1001cd92  sub     ecx, 2
0x1001cd95  xor     eax, eax
0x1001cd97  mov     esi, offset aRow; "Row"
0x1001cd9c  mov     [ecx], ax
0x1001cd9f  mov     edx, 41h ; 'A'
0x1001cda4  lea     ecx, [edi+2A6h]
0x1001cdaa  sub     esi, ecx
0x1001cdac  lea     esp, [esp+0]
0x1001cdb0  lea     eax, [edx+7FFFFFBDh]
0x1001cdb6  test    eax, eax
0x1001cdb8  jz      short loc_1001CDCE
0x1001cdba  movzx   eax, word ptr [esi+ecx]
0x1001cdbe  test    ax, ax
0x1001cdc1  jz      short loc_1001CDCE
0x1001cdc3  mov     [ecx], ax
0x1001cdc6  add     ecx, 2
0x1001cdc9  dec     edx
0x1001cdca  jnz     short loc_1001CDB0
0x1001cdcc  jmp     short loc_1001CDD2
0x1001cdce  test    edx, edx
0x1001cdd0  jnz     short loc_1001CDD5
0x1001cdd2  sub     ecx, 2
0x1001cdd5  xor     eax, eax
0x1001cdd7  mov     esi, offset aUnparsableReco; "Unparsable Record"
0x1001cddc  mov     [ecx], ax
0x1001cddf  mov     edx, 41h ; 'A'
0x1001cde4  lea     ecx, [edi+328h]
0x1001cdea  sub     esi, ecx
0x1001cdec  lea     esp, [esp+0]
0x1001cdf0  lea     eax, [edx+7FFFFFBDh]
0x1001cdf6  test    eax, eax
0x1001cdf8  jz      short loc_1001CE0E
0x1001cdfa  movzx   eax, word ptr [esi+ecx]
0x1001cdfe  test    ax, ax
0x1001ce01  jz      short loc_1001CE0E
0x1001ce03  mov     [ecx], ax
0x1001ce06  add     ecx, 2
0x1001ce09  dec     edx
0x1001ce0a  jnz     short loc_1001CDF0
0x1001ce0c  jmp     short loc_1001CE12
0x1001ce0e  test    edx, edx
0x1001ce10  jnz     short loc_1001CE15
0x1001ce12  sub     ecx, 2
0x1001ce15  xor     eax, eax
0x1001ce17  mov     esi, offset aTypeConversion; "Type Conversion Failure"
0x1001ce1c  mov     [ecx], ax
0x1001ce1f  mov     edx, 41h ; 'A'
0x1001ce24  lea     ecx, [edi+3AAh]
0x1001ce2a  sub     esi, ecx
0x1001ce2c  lea     esp, [esp+0]
0x1001ce30  lea     eax, [edx+7FFFFFBDh]
0x1001ce36  test    eax, eax
0x1001ce38  jz      short loc_1001CE4E
0x1001ce3a  movzx   eax, word ptr [esi+ecx]
0x1001ce3e  test    ax, ax
0x1001ce41  jz      short loc_1001CE4E
0x1001ce43  mov     [ecx], ax
0x1001ce46  add     ecx, 2
0x1001ce49  dec     edx
0x1001ce4a  jnz     short loc_1001CE30
0x1001ce4c  jmp     short loc_1001CE52
0x1001ce4e  test    edx, edx
0x1001ce50  jnz     short loc_1001CE55
0x1001ce52  sub     ecx, 2
0x1001ce55  xor     eax, eax
0x1001ce57  mov     esi, offset aRowTruncation; "Row Truncation"
0x1001ce5c  mov     [ecx], ax
0x1001ce5f  mov     edx, 41h ; 'A'
0x1001ce64  lea     ecx, [edi+42Ch]
0x1001ce6a  sub     esi, ecx
0x1001ce6c  lea     esp, [esp+0]
0x1001ce70  lea     eax, [edx+7FFFFFBDh]
0x1001ce76  test    eax, eax
0x1001ce78  jz      short loc_1001CE8E
0x1001ce7a  movzx   eax, word ptr [esi+ecx]
0x1001ce7e  test    ax, ax
0x1001ce81  jz      short loc_1001CE8E
0x1001ce83  mov     [ecx], ax
0x1001ce86  add     ecx, 2
0x1001ce89  dec     edx
0x1001ce8a  jnz     short loc_1001CE70
0x1001ce8c  jmp     short loc_1001CE92
0x1001ce8e  test    edx, edx
0x1001ce90  jnz     short loc_1001CE95
0x1001ce92  sub     ecx, 2
0x1001ce95  xor     eax, eax
0x1001ce97  mov     esi, offset aFieldTruncatio; "Field Truncation"
0x1001ce9c  mov     [ecx], ax
0x1001ce9f  mov     edx, 41h ; 'A'
0x1001cea4  lea     ecx, [edi+4AEh]
0x1001ceaa  sub     esi, ecx
0x1001ceac  lea     esp, [esp+0]
0x1001ceb0  lea     eax, [edx+7FFFFFBDh]
0x1001ceb6  test    eax, eax
0x1001ceb8  jz      short loc_1001CECE
0x1001ceba  movzx   eax, word ptr [esi+ecx]
0x1001cebe  test    ax, ax
0x1001cec1  jz      short loc_1001CECE
0x1001cec3  mov     [ecx], ax
0x1001cec6  add     ecx, 2
0x1001cec9  dec     edx
0x1001ceca  jnz     short loc_1001CEB0
0x1001cecc  jmp     short loc_1001CED2
  ... truncated ...
```
