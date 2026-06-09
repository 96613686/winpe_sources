# EngineOpenTable

- ea: `0x10028701`
- end: `0x10028e7f`
- name: `EngineOpenTable`
- size: `1918`
- prototype: `int __fastcall(int, int)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x10029068`
- `0x10029b60`

## callees

- `0x100073e0`
- `0x10018b80`
- `0x1001a630`
- `0x1001bb70`
- `0x1001bc80`
- `0x1001ce30`
- `0x1001d5b0`
- `0x100243dc`
- `0x10025775`
- `0x1002580a`
- `0x10025ab7`
- `0x1002838d`
- `0x100283fc`
- `0x10028538`
- `0x1002865c`
- `0x10028701`
- `0x1002ad0e`
- `0x1002ae70`
- `0x1002eb9b`
- `0x10035510`
- `0x10036678`

## pseudocode

```c
int __fastcall EngineOpenTable(int a1, int a2)
{
  int v3; // edi
  int v4; // eax
  int v5; // ecx
  int result; // eax
  int v7; // eax
  int *v8; // esi
  int v9; // ebx
  int v10; // eax
  int v11; // ecx
  bool v12; // zf
  int v13; // ebx
  int v14; // esi
  int v15; // eax
  const wchar_t *v16; // eax
  int v17; // ecx
  int v18; // eax
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // cx
  unsigned int v21; // esi
  __int16 v22; // dx
  __int16 v23; // ax
  __int16 v24; // cx
  int v25; // eax
  int v26; // ecx
  int v27; // ebx
  bool v28; // cc
  int v29; // eax
  int v30; // edx
  _DWORD *v31; // ebx
  _DWORD *i; // edi
  _DWORD *v33; // ecx
  _DWORD *v34; // esi
  int **v35; // ecx
  int v36; // edi
  int *v37; // esi
  unsigned __int16 *v38; // ecx
  int v39; // edi
  int v40; // esi
  int v41; // ecx
  int v42; // eax
  _DWORD *v43; // eax
  int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  UINT v51; // ecx
  int j; // eax
  _DWORD **v53; // esi
  _DWORD *v54; // ebx
  int v55; // edi
  char *v56; // esi
  int v57; // ecx
  char *v58; // ecx
  __int16 v59; // ax
  char *v60; // edx
  int v61; // ecx
  __int16 v62; // ax
  int v63; // edx
  int v64; // [esp-4h] [ebp-5ACh]
  __int16 v66; // [esp+18h] [ebp-590h]
  int v67; // [esp+1Ch] [ebp-58Ch]
  int v68; // [esp+20h] [ebp-588h] BYREF
  int v69; // [esp+24h] [ebp-584h]
  int v70; // [esp+28h] [ebp-580h]
  _DWORD *v71; // [esp+2Ch] [ebp-57Ch]
  int v72; // [esp+30h] [ebp-578h]
  UINT v73; // [esp+34h] [ebp-574h] BYREF
  int v74; // [esp+38h] [ebp-570h]
  int v75; // [esp+3Ch] [ebp-56Ch]
  _BYTE v76[16]; // [esp+40h] [ebp-568h] BYREF
  wchar_t Destination[512]; // [esp+70h] [ebp-538h] BYREF
  WCHAR v78[68]; // [esp+470h] [ebp-138h] BYREF
  __int16 v79; // [esp+4F8h] [ebp-B0h]
  char v80; // [esp+584h] [ebp-24h] BYREF
  __int16 v81; // [esp+586h] [ebp-22h] BYREF

  v3 = a2;
  v71 = *(_DWORD **)(a1 + 4);
  ISAMDBDeleteColumns(a2);
  v4 = *(unsigned __int16 *)(v3 + 96);
  v69 = *(unsigned __int16 *)(v3 + 102) - *(unsigned __int16 *)(v3 + 98) + 1;
  v74 = *(unsigned __int16 *)(v3 + 100) - v4;
  v5 = *(_DWORD *)(v3 + 16);
  v68 = v74 + 1;
  if ( v5 )
  {
    MemFree(v5);
    *(_DWORD *)(v3 + 16) = 0;
  }
  result = WorkbookRangeCreate(*(_DWORD *)(v3 + 96), *(_DWORD *)(v3 + 100));
  if ( result < 0 )
    return result;
  v7 = TableCacheFind(v71[14], v3 + 104);
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 8) == *(_DWORD *)(v3 + 44) )
    {
      v8 = *(int **)(v7 + 4);
      v9 = 0;
      while ( v8 )
      {
        v10 = ISAMDBAddColumn(
                v8[1],
                v8[2],
                *((_BYTE *)v8 + 17),
                *((_BYTE *)v8 + 16),
                *(_DWORD *)(*(_DWORD *)(v3 + 4) + 68));
        if ( !v10 )
          return -1011;
        *(_WORD *)(v10 + 28) = v9++;
        *(_DWORD *)(v10 + 32) = v8[3];
        v8 = (int *)*v8;
      }
      return 0;
    }
    TableCacheRemove(v71, v3);
  }
  v11 = 1;
  if ( !*(_DWORD *)(v3 + 92) || (v12 = *(_DWORD *)(a1 + 56) == 1, v13 = 1, v12) )
    v13 = 0;
  v14 = 0;
  v15 = v69;
  if ( v69 > 0 )
  {
    while ( 1 )
    {
      HIWORD(v72) = v14;
      LOWORD(v72) = 0;
      v79 = 0;
      if ( *(_DWORD *)(v3 + 44) != 1 )
        goto LABEL_22;
      result = WorkbookCellRead(v72, v76, 7);
      if ( result < 0 )
        return result;
      if ( result
        || (v76[0] & 0x10) == 0
        || (v16 = (const wchar_t *)TextStorageGet(),
            wcsncpy(Destination, v16, 0x41u),
            WorkbookCodePage(v71[3], &v73),
            MakeValidJetName(Destination, v78, 65, v73),
            WCSNCPY2(v78, 65),
            !v79) )
      {
LABEL_22:
        v79 = 70;
        ITOW(64, v11);
      }
      v17 = 10;
      v75 = 10;
      if ( !v13 )
        goto LABEL_29;
      result = FixColumnTypeFromNote(v72);
      if ( result )
        return result;
      v17 = v75;
      if ( v75 == 10 || v75 == 12 || v75 == 11 )
LABEL_29:
        v18 = ISAMDBAddColumn(v17, 32, 2, 28, *(_DWORD *)(*(_DWORD *)(v3 + 4) + 68));
      else
        v18 = ISAMDBAddColumn(v75, 33, 2, 28, *(_DWORD *)(*(_DWORD *)(v3 + 4) + 68));
      if ( !v18 )
        return -1011;
      *(_WORD *)(v18 + 28) = v14++;
      v15 = v69;
      if ( v14 >= v69 )
        break;
      v11 = 1;
    }
  }
  if ( v13 )
    goto LABEL_112;
  v70 = MemAllocate(36 * v15);
  if ( !v70 )
    return -1011;
  if ( *(_DWORD *)(v3 + 44) == 1 )
  {
    v66 = 1;
    v19 = v68 - 1;
    if ( ISAMDefaults < v74 )
      v19 = ISAMDefaults;
    v20 = v19;
    if ( v19 == 0xFFFF )
      v20 = 0;
    v21 = 1;
  }
  else
  {
    v22 = v68;
    v66 = 0;
    if ( ISAMDefaults < v68 )
      v22 = ISAMDefaults;
    if ( v22 )
      v20 = v22 - 1;
    else
      v20 = 0;
    v21 = 0;
  }
  LOWORD(v67) = v20;
  v68 = v20;
  if ( v21 <= v20 )
  {
    do
    {
      v75 = *(_DWORD *)(v3 + 40);
      v23 = 0;
      v24 = v21;
      v73 = 0;
      v74 = (unsigned __int16)v21;
      do
      {
        HIWORD(v72) = v23;
        LOWORD(v72) = v24;
        v25 = WorkbookCellRead(v72, v76, 6);
        v27 = v25;
        if ( v25 < 0 )
        {
          for ( i = *(_DWORD **)(v3 + 40); i; i = (_DWORD *)*i )
          {
            v33 = (_DWORD *)i[9];
            if ( v33 )
            {
              do
              {
                v34 = (_DWORD *)*v33;
                MemFree(v33);
                v33 = v34;
              }
              while ( v34 );
            }
          }
          MemFree(v70);
          return v27;
        }
        if ( !v25 )
        {
          HIWORD(v67) = v69 - 1;
          CountTypeAndFormat(v66, v67, v70, v26, v72, v76);
        }
        v75 = *(_DWORD *)v75;
        v23 = v73 + 1;
        v28 = (int)++v73 <= (unsigned __int16)(v69 - 1);
        v24 = v74;
      }
      while ( v28 );
      ++v21;
    }
    while ( (int)v21 <= v68 );
  }
  v29 = v70;
  v30 = 0;
  v31 = *(_DWORD **)(v3 + 40);
  v75 = v70;
  v73 = 0;
  if ( v69 <= 0 )
    goto LABEL_111;
  while ( 1 )
  {
    v35 = (int **)v31[9];
    v74 = 0;
    v31[8] = 0;
    if ( v35 )
    {
      v36 = 0;
      do
      {
        if ( v36 < *((__int16 *)v35 + 4) )
        {
          v31[8] = v35[1];
          v36 = *((__int16 *)v35 + 4);
        }
        v37 = *v35;
        MemFree(v35);
        v35 = (int **)v37;
      }
      while ( v37 );
      v30 = 0;
    }
    v38 = (unsigned __int16 *)v75;
    v39 = 0;
    v40 = 0;
    v74 = *(unsigned __int16 *)(v75 + 24);
    *(_WORD *)(v75 + 24) = 0;
    do
    {
      v41 = *v38;
      v42 = v40 + 1;
      if ( !(_WORD)v41 )
        v42 = v40;
      v40 = v42;
      if ( v39 < v41 )
      {
        v39 = v41;
        v31[4] = v30;
      }
      v38 = (unsigned __int16 *)(v75 + 2);
      ++v30;
      v75 += 2;
    }
    while ( v30 < 18 );
    v3 = a2;
    if ( v42 )
    {
      if ( v42 > 1 && *(_DWORD *)(a2 + 84) == 1 && dword_1003C2DC == 1 )
      {
        v43 = v31 + 4;
        v31[4] = 10;
        goto LABEL_86;
      }
    }
    else
    {
      WorkbookFormatType(0, &v68);
      if ( v68 == 1 || v68 == 2 || v68 == 3 )
      {
        v31[4] = 8;
      }
      else if ( v68 == 4 )
      {
        v31[4] = 7;
      }
      else
      {
        v31[4] = v68 == 5 ? 5 : 10;
      }
    }
    v43 = v31 + 4;
    v44 = v31[4];
    if ( v44 == 10 && (_WORD)v74 )
    {
      *v43 = 12;
LABEL_86:
      v64 = 32;
      goto LABEL_87;
    }
    v43 = v31 + 4;
    if ( v44 == 10 || v44 == 12 )
      goto LABEL_86;
    v64 = 33;
LABEL_87:
    v31[2] = v64;
    v45 = *v43 - 1;
    if ( v45 )
    {
      v46 = v45 - 4;
      if ( v46 && (v47 = v46 - 2) != 0 && (v48 = v47 - 1) != 0 )
      {
        v49 = v48 - 2;
        if ( v49 )
        {
          if ( v49 != 2 )
            goto LABEL_109;
          v50 = *((unsigned __int16 *)&dword_1003C31A + v71[4]);
        }
        else
        {
          v50 = *((unsigned __int16 *)&dword_1003C31A + v71[4]);
          if ( (unsigned __int16)v50 >= 0xFFu )
            v50 = 255;
        }
        v31[5] = 2 * v50;
      }
      else
      {
        v31[5] = 8;
      }
    }
    else
    {
      v31[5] = 1;
    }
LABEL_109:
    v31 = (_DWORD *)*v31;
    if ( (int)++v73 >= v69 )
      break;
    v30 = 0;
  }
  v29 = v70;
LABEL_111:
  MemFree(v29);
LABEL_112:
  v51 = 0;
  for ( j = 1; ; ++j )
  {
    v70 = j;
    if ( j != 1 && v51 != 1 )
      break;
    if ( j > *(_DWORD *)(v3 + 36) )
      break;
    v53 = *(_DWORD ***)(v3 + 40);
    v51 = 0;
    v75 = (int)v53;
    v73 = 0;
    if ( v53 )
    {
      do
      {
        v54 = *v53;
        v55 = 1;
        if ( *v53 )
        {
          v74 = (int)v53 + 42;
          v56 = (char *)v53 + 42;
          do
          {
            if ( DBlstrcmpi(v56, (char *)v54 + 42) )
            {
              v51 = v73;
            }
            else
            {
              ITOW(16, v57);
              v58 = (char *)v54 + 42;
              do
              {
                v59 = *(_WORD *)v58;
                v58 += 2;
              }
              while ( v59 );
              v60 = &v80;
              v61 = (v58 - (char *)(v54 + 11)) >> 1;
              v74 = (int)&v81;
              do
              {
                v62 = *(_WORD *)v60;
                v60 += 2;
              }
              while ( v62 );
              v63 = (int)&v60[-v74] >> 1;
              if ( v63 + v61 > 64 )
                *((_WORD *)v54 + 64 - v63 + 21) = 0;
              WCSCAT2(65);
              ++v55;
              v51 = 1;
              v73 = 1;
            }
            v54 = (_DWORD *)*v54;
          }
          while ( v54 );
          v53 = (_DWORD **)v75;
        }
        v53 = (_DWORD **)*v53;
        v75 = (int)v53;
      }
      while ( v53 );
      v3 = a2;
      j = v70;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10028701  mov     edi, edi
0x10028703  push    ebp
0x10028704  mov     ebp, esp
0x10028706  sub     esp, 59Ch
0x1002870c  mov     eax, ___security_cookie
0x10028711  xor     eax, ebp
0x10028713  mov     [ebp+var_4], eax
0x10028716  push    ebx
0x10028717  mov     ebx, ecx
0x10028719  push    esi
0x1002871a  push    edi
0x1002871b  mov     edi, edx
0x1002871d  mov     eax, [ebx+4]
0x10028720  mov     ecx, edi
0x10028722  mov     [ebp+var_598], edi
0x10028728  mov     [ebp+var_57C], eax
0x1002872e  call    _ISAMDBDeleteColumns@4; ISAMDBDeleteColumns(x)
0x10028733  movzx   eax, word ptr [edi+62h]
0x10028737  lea     esi, [edi+10h]
0x1002873a  movzx   ecx, word ptr [edi+66h]
0x1002873e  sub     ecx, eax
0x10028740  mov     [ebp+var_594], 0
0x1002874a  movzx   eax, word ptr [edi+60h]
0x1002874e  inc     ecx
0x1002874f  mov     [ebp+var_584], ecx
0x10028755  movzx   ecx, word ptr [edi+64h]
0x10028759  sub     ecx, eax
0x1002875b  mov     [ebp+var_570], ecx
0x10028761  lea     eax, [ecx+1]
0x10028764  mov     ecx, [esi]
0x10028766  mov     [ebp+var_588], eax
0x1002876c  test    ecx, ecx
0x1002876e  jz      short loc_1002877B
0x10028770  call    _MemFree@4; MemFree(x)
0x10028775  mov     dword ptr [esi], 0
0x1002877b  push    dword ptr [edi+64h]
0x1002877e  mov     ecx, [edi+0Ch]
0x10028781  mov     edx, esi
0x10028783  push    dword ptr [edi+60h]
0x10028786  call    _WorkbookRangeCreate@16; WorkbookRangeCreate(x,x,x,x)
0x1002878b  test    eax, eax
0x1002878d  js      short loc_100287EE
0x1002878f  mov     esi, [ebp+var_57C]
0x10028795  lea     edx, [edi+68h]
0x10028798  mov     ecx, [esi+38h]
0x1002879b  call    _TableCacheFind@8; TableCacheFind(x,x)
0x100287a0  test    eax, eax
0x100287a2  jz      short loc_10028806
0x100287a4  mov     ecx, [eax+8]
0x100287a7  cmp     ecx, [edi+2Ch]
0x100287aa  jnz     short loc_100287FD
0x100287ac  mov     esi, [eax+4]
0x100287af  xor     ebx, ebx
0x100287b1  jmp     short loc_100287E8
0x100287b3  mov     eax, [edi+4]
0x100287b6  lea     edx, [esi+12h]
0x100287b9  mov     ecx, edi
0x100287bb  push    dword ptr [eax+44h]
0x100287be  movzx   eax, byte ptr [esi+10h]
0x100287c2  push    eax
0x100287c3  movzx   eax, byte ptr [esi+11h]
0x100287c7  push    eax
0x100287c8  push    dword ptr [esi+8]
0x100287cb  push    dword ptr [esi+4]
0x100287ce  call    _ISAMDBAddColumn@28; ISAMDBAddColumn(x,x,x,x,x,x,x)
0x100287d3  test    eax, eax
0x100287d5  jz      loc_10028993
0x100287db  mov     [eax+1Ch], bx
0x100287df  inc     ebx
0x100287e0  mov     ecx, [esi+0Ch]
0x100287e3  mov     [eax+20h], ecx
0x100287e6  mov     esi, [esi]
0x100287e8  test    esi, esi
0x100287ea  jnz     short loc_100287B3
0x100287ec  xor     eax, eax
0x100287ee  mov     ecx, [ebp+var_4]
0x100287f1  pop     edi
0x100287f2  pop     esi
0x100287f3  xor     ecx, ebp; StackCookie
0x100287f5  pop     ebx
0x100287f6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100287fb  leave
0x100287fc  retn
0x100287fd  mov     edx, edi
0x100287ff  mov     ecx, esi
0x10028801  call    _TableCacheRemove@8; TableCacheRemove(x,x)
0x10028806  xor     ecx, ecx
0x10028808  xor     eax, eax
0x1002880a  inc     ecx
0x1002880b  cmp     [edi+5Ch], eax
0x1002880e  jz      short loc_10028817
0x10028810  cmp     [ebx+38h], ecx
0x10028813  mov     ebx, ecx
0x10028815  jnz     short loc_10028819
0x10028817  mov     ebx, eax
0x10028819  mov     esi, eax
0x1002881b  mov     eax, [ebp+var_584]
0x10028821  test    eax, eax
0x10028823  jle     loc_10028979
0x10028829  xor     eax, eax
0x1002882b  mov     word ptr [ebp+var_578+2], si
0x10028832  mov     word ptr [ebp+var_578], ax
0x10028839  mov     [ebp+var_B0], ax
0x10028840  cmp     [edi+2Ch], ecx
0x10028843  jnz     loc_100288E6
0x10028849  mov     edx, [edi+10h]
0x1002884c  lea     eax, [ebp+var_568]
0x10028852  mov     ecx, [edi+0Ch]
0x10028855  push    7
0x10028857  push    eax
0x10028858  push    [ebp+var_578]
0x1002885e  call    _WorkbookCellRead@20; WorkbookCellRead(x,x,x,x,x)
0x10028863  test    eax, eax
0x10028865  js      short loc_100287EE
0x10028867  jnz     short loc_100288E6
0x10028869  test    [ebp+var_568], 10h
0x10028870  jz      short loc_100288E6
0x10028872  mov     eax, [ebp+var_57C]
0x10028878  mov     edx, [ebp+var_558]
0x1002887e  mov     eax, [eax+0Ch]
0x10028881  call    _TextStorageGet@8; TextStorageGet(x,x)
0x10028886  push    41h ; 'A'; Count
0x10028888  push    eax; Source
0x10028889  lea     eax, [ebp+Destination]
0x1002888f  push    eax; Destination
0x10028890  call    _wcsncpy
0x10028895  mov     eax, [ebp+var_57C]
0x1002889b  lea     edx, [ebp+var_574]
0x100288a1  add     esp, 0Ch
0x100288a4  mov     ecx, [eax+0Ch]
0x100288a7  call    _WorkbookCodePage@8; WorkbookCodePage(x,x)
0x100288ac  push    [ebp+var_574]
0x100288b2  lea     edx, [ebp+var_138]
0x100288b8  push    41h ; 'A'
0x100288ba  lea     ecx, [ebp+Destination]
0x100288c0  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x100288c5  push    41h ; 'A'
0x100288c7  lea     eax, [ebp+var_138]
0x100288cd  push    eax
0x100288ce  push    41h ; 'A'
0x100288d0  pop     edx
0x100288d1  lea     ecx, [ebp+var_B0]
0x100288d7  call    _WCSNCPY2@16; WCSNCPY2(x,x,x,x)
0x100288dc  cmp     [ebp+var_B0], 0
0x100288e4  jnz     short loc_10028901
0x100288e6  push    46h ; 'F'
0x100288e8  pop     eax
0x100288e9  push    ecx
0x100288ea  push    40h ; '@'
0x100288ec  lea     ecx, [esi+1]
0x100288ef  mov     [ebp+var_B0], ax
0x100288f6  lea     edx, [ebp+var_AE]
0x100288fc  call    _ITOW@16; ITOW(x,x,x,x)
0x10028901  push    0Ah
0x10028903  pop     ecx
0x10028904  mov     [ebp+var_56C], ecx
0x1002890a  test    ebx, ebx
0x1002890c  jz      short loc_10028942
0x1002890e  push    [ebp+var_578]
0x10028914  lea     edx, [ebp+var_56C]
0x1002891a  mov     ecx, edi
0x1002891c  call    FixColumnTypeFromNote
0x10028921  test    eax, eax
0x10028923  jnz     loc_100287EE
0x10028929  mov     ecx, [ebp+var_56C]
0x1002892f  cmp     ecx, 0Ah
0x10028932  jz      short loc_10028942
0x10028934  cmp     ecx, 0Ch
0x10028937  jz      short loc_10028942
0x10028939  cmp     ecx, 0Bh
0x1002893c  jz      short loc_10028942
0x1002893e  push    21h ; '!'
0x10028940  jmp     short loc_10028944
0x10028942  push    20h ; ' '
0x10028944  mov     eax, [edi+4]
0x10028947  pop     edx
0x10028948  push    dword ptr [eax+44h]
0x1002894b  push    1Ch
0x1002894d  push    2
0x1002894f  push    edx
0x10028950  push    ecx
0x10028951  lea     edx, [ebp+var_B0]
0x10028957  mov     ecx, edi
0x10028959  call    _ISAMDBAddColumn@28; ISAMDBAddColumn(x,x,x,x,x,x,x)
0x1002895e  test    eax, eax
0x10028960  jz      short loc_10028993
0x10028962  mov     [eax+1Ch], si
0x10028966  inc     esi
0x10028967  mov     eax, [ebp+var_584]
0x1002896d  cmp     esi, eax
0x1002896f  jge     short loc_10028979
0x10028971  xor     ecx, ecx
0x10028973  inc     ecx
0x10028974  jmp     loc_10028829
0x10028979  test    ebx, ebx
0x1002897b  jnz     loc_10028D6C
0x10028981  imul    ecx, eax, 24h ; '$'
0x10028984  call    _MemAllocate@4; MemAllocate(x)
0x10028989  mov     [ebp+var_580], eax
0x1002898f  test    eax, eax
0x10028991  jnz     short loc_1002899D
0x10028993  mov     eax, 0FFFFFC0Dh
0x10028998  jmp     loc_100287EE
0x1002899d  mov     ebx, [ebp+var_584]
0x100289a3  xor     ecx, ecx
0x100289a5  mov     esi, [ebp+var_588]
0x100289ab  xor     eax, eax
0x100289ad  dec     ebx
0x100289ae  mov     word ptr [ebp+var_590+2], ax
0x100289b5  inc     ecx
0x100289b6  mov     word ptr [ebp+var_58C+2], bx
0x100289bd  movzx   eax, si
0x100289c0  cmp     [edi+2Ch], ecx
0x100289c3  jnz     short loc_100289F3
0x100289c5  dec     eax
0x100289c6  mov     word ptr [ebp+var_590], cx
0x100289cd  movzx   edx, ax
0x100289d0  mov     eax, _ISAMDefaults
0x100289d5  cmp     eax, [ebp+var_570]
0x100289db  movzx   ecx, ax
0x100289de  cmovl   edx, ecx
0x100289e1  movzx   eax, dx
0x100289e4  mov     ecx, eax
0x100289e6  inc     eax
0x100289e7  test    ax, ax
0x100289ea  jnz     short loc_100289EE
0x100289ec  xor     ecx, ecx
0x100289ee  xor     esi, esi
0x100289f0  inc     esi
0x100289f1  jmp     short loc_10028A1C
0x100289f3  xor     ecx, ecx
0x100289f5  mov     edx, eax
0x100289f7  mov     eax, _ISAMDefaults
0x100289fc  cmp     eax, esi
0x100289fe  mov     word ptr [ebp+var_590], cx
0x10028a05  movzx   ecx, ax
0x10028a08  cmovl   edx, ecx
0x10028a0b  movzx   eax, dx
0x10028a0e  test    ax, ax
0x10028a11  jz      short loc_10028A18
0x10028a13  lea     ecx, [eax-1]
0x10028a16  jmp     short loc_10028A1A
0x10028a18  xor     ecx, ecx
0x10028a1a  xor     esi, esi
0x10028a1c  movzx   eax, cx
0x10028a1f  mov     word ptr [ebp+var_58C], cx
0x10028a26  mov     [ebp+var_588], eax
0x10028a2c  cmp     esi, eax
0x10028a2e  ja      loc_10028AF3
0x10028a34  mov     eax, [edi+28h]
0x10028a37  mov     [ebp+var_56C], eax
0x10028a3d  xor     eax, eax
0x10028a3f  movzx   ecx, si
0x10028a42  mov     [ebp+var_574], eax
0x10028a48  mov     [ebp+var_570], ecx
0x10028a4e  mov     edx, [edi+10h]
0x10028a51  mov     word ptr [ebp+var_578+2], ax
0x10028a58  lea     eax, [ebp+var_568]
0x10028a5e  push    6
0x10028a60  mov     word ptr [ebp+var_578], cx
0x10028a67  mov     ecx, [edi+0Ch]
0x10028a6a  push    eax
0x10028a6b  push    [ebp+var_578]
0x10028a71  call    _WorkbookCellRead@20; WorkbookCellRead(x,x,x,x,x)
0x10028a76  mov     ebx, eax
0x10028a78  test    ebx, ebx
0x10028a7a  js      loc_10028B18
0x10028a80  jnz     short loc_10028AB3
0x10028a82  mov     edx, [ebp+var_56C]
0x10028a88  lea     eax, [ebp+var_568]
0x10028a8e  push    eax
0x10028a8f  push    [ebp+var_578]
0x10028a95  push    ecx
0x10028a96  push    [ebp+var_580]
0x10028a9c  mov     ecx, [ebp+var_57C]
0x10028aa2  push    [ebp+var_58C]
0x10028aa8  push    [ebp+var_590]
0x10028aae  call    CountTypeAndFormat
0x10028ab3  mov     eax, [ebp+var_56C]
0x10028ab9  mov     ebx, [ebp+var_584]
0x10028abf  dec     ebx
0x10028ac0  movzx   ecx, bx
0x10028ac3  mov     eax, [eax]
0x10028ac5  mov     [ebp+var_56C], eax
0x10028acb  mov     eax, [ebp+var_574]
0x10028ad1  inc     eax
0x10028ad2  cmp     eax, ecx
0x10028ad4  mov     [ebp+var_574], eax
0x10028ada  mov     ecx, [ebp+var_570]
0x10028ae0  jle     loc_10028A4E
0x10028ae6  inc     esi
0x10028ae7  cmp     esi, [ebp+var_588]
0x10028aed  jle     loc_10028A34
0x10028af3  mov     eax, [ebp+var_580]
0x10028af9  xor     edx, edx
0x10028afb  mov     ebx, [edi+28h]
0x10028afe  mov     [ebp+var_56C], eax
0x10028b04  mov     [ebp+var_574], edx
0x10028b0a  cmp     [ebp+var_584], edx
0x10028b10  jle     loc_10028D65
  ... truncated ...
```
