# StoreFormat

- ea: `0x100200c0`
- end: `0x10020391`
- name: `StoreFormat`
- size: `721`
- prototype: `int __fastcall(int, unsigned __int16 *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10020780`

## callees

- `0x10006400`
- `0x100200c0`
- `0x1002580a`
- `0x1002edd2`
- `0x1002ee43`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10020169`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10020169`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10020170`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10020170`

## pseudocode

```c
int __fastcall StoreFormat(int a1, unsigned __int16 *a2, _DWORD *a3)
{
  int v3; // ebx
  unsigned __int16 *v5; // esi
  int v6; // eax
  LCID UserDefaultLCID; // eax
  int v8; // esi
  char *v9; // eax
  char v10; // cl
  char v11; // cl
  unsigned __int16 *v12; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // edi
  _DWORD *v17; // ebx
  _WORD *v18; // ecx
  unsigned __int16 *v19; // eax
  int v20; // eax
  bool v21; // zf
  unsigned __int16 *v22; // esi
  _WORD *v23; // edx
  int *v26; // [esp+10h] [ebp-18h]
  int i; // [esp+18h] [ebp-10h]
  int v29; // [esp+1Ch] [ebp-Ch] BYREF
  int v30; // [esp+20h] [ebp-8h]
  unsigned __int16 *v31; // [esp+24h] [ebp-4h]

  v3 = 0;
  v5 = *(unsigned __int16 **)(a1 + 76);
  v31 = 0;
  v30 = 0;
  v26 = 0;
  for ( i = 0; v5; i = v3 )
  {
    v6 = wcscmp(v5 + 8, a2);
    if ( v6 )
      v6 = v6 < 0 ? -1 : 1;
    if ( !v6 )
      goto LABEL_19;
    v26 = (int *)v5;
    ++v3;
    v5 = *(unsigned __int16 **)v5;
  }
  if ( FMTStoreFormat(a2, &v29) )
    return -10;
  if ( ControlPanelSettings == 1 )
  {
    UserDefaultLCID = GetUserDefaultLCID();
    if ( DBCompareStringW(UserDefaultLCID, 196609, &dword_1003B8F0, -1, L"$", -1) == 2
      && word_1003B920 == 58
      && word_1003B922 == 45 )
    {
LABEL_34:
      v8 = v29;
      goto LABEL_35;
    }
  }
  v8 = v29;
  if ( v29 )
  {
    v9 = *(char **)(v29 + 8);
    if ( v9 )
    {
      v10 = *v9;
      if ( *v9 )
      {
        if ( v10 != 3 )
        {
          if ( v10 == 2 )
          {
            v11 = v9[8] & 0x70;
            if ( (v9[8] & 0xF) != 0 )
            {
              if ( !v11 )
              {
                FMTDeleteFormat(v29);
                v12 = (unsigned __int16 *)qword_1003B8D0;
                goto LABEL_25;
              }
            }
            else if ( v11 )
            {
              FMTDeleteFormat(v29);
              v12 = (unsigned __int16 *)HIDWORD(qword_1003B8D0);
              goto LABEL_25;
            }
            FMTDeleteFormat(v29);
            v12 = (unsigned __int16 *)HIDWORD(StandardFormats);
          }
          else
          {
            if ( !*((_DWORD *)v9 + 6) )
              goto LABEL_35;
            FMTDeleteFormat(v29);
            v12 = (unsigned __int16 *)StandardFormats;
          }
LABEL_25:
          v30 = 1;
          v31 = v12;
          v5 = *(unsigned __int16 **)(a1 + 76);
          if ( v5 )
          {
            while ( 1 )
            {
              v14 = wcscmp(v5 + 8, v12);
              if ( v14 )
                v14 = v14 < 0 ? -1 : 1;
              if ( !v14 )
                break;
              v5 = *(unsigned __int16 **)v5;
              if ( !v5 )
                goto LABEL_30;
            }
LABEL_19:
            *a3 = *((_DWORD *)v5 + 1);
            return 0;
          }
LABEL_30:
          if ( !FMTStoreFormat(v12, &v29) )
          {
            if ( v30 )
            {
              v15 = MemAllocate(2 * wcslen(v12) + 20);
              v16 = v15;
              if ( v15 )
              {
                v17 = (_DWORD *)(v15 + 4);
                *(_DWORD *)(v15 + 8) = v29;
                v18 = (_WORD *)(v15 + 16);
                *(_DWORD *)(v15 + 4) = i;
                v19 = v31;
                goto LABEL_40;
              }
              return -2;
            }
            goto LABEL_34;
          }
          return -10;
        }
      }
    }
  }
LABEL_35:
  v20 = MemAllocate(2 * wcslen(a2) + 20);
  v16 = v20;
  if ( !v20 )
    return -2;
  v21 = v30 == 0;
  v17 = (_DWORD *)(v20 + 4);
  v18 = (_WORD *)(v20 + 16);
  *(_DWORD *)(v20 + 8) = v8;
  *(_DWORD *)(v20 + 4) = i;
  if ( !v21 )
  {
    v19 = v31;
    goto LABEL_41;
  }
  v19 = a2;
LABEL_40:
  v31 = v19;
LABEL_41:
  v22 = v19;
  v23 = v19 + 1;
  while ( *v22++ )
    ;
  WCSCPY2(v18, v31, v22 - v23 + 1);
  if ( *(_DWORD *)(a1 + 76) )
    *v26 = v16;
  else
    *(_DWORD *)(a1 + 76) = v16;
  *a3 = *v17;
  return 0;
}

```

## disassembly

```asm
0x100200c0  mov     edi, edi
0x100200c2  push    ebp
0x100200c3  mov     ebp, esp
0x100200c5  sub     esp, 1Ch
0x100200c8  push    ebx
0x100200c9  mov     eax, ecx
0x100200cb  xor     ebx, ebx
0x100200cd  push    esi
0x100200ce  push    edi
0x100200cf  mov     edi, edx
0x100200d1  mov     [ebp+var_14], eax
0x100200d4  mov     esi, [eax+4Ch]
0x100200d7  xor     edx, edx
0x100200d9  mov     [ebp+var_1C], edi
0x100200dc  mov     [ebp+var_4], edx
0x100200df  mov     [ebp+var_8], edx
0x100200e2  mov     [ebp+var_18], edx
0x100200e5  mov     [ebp+var_10], ebx
0x100200e8  test    esi, esi
0x100200ea  jz      short loc_10020135
0x100200ec  nop     dword ptr [eax+00h]
0x100200f0  mov     ecx, edi
0x100200f2  lea     eax, [esi+10h]
0x100200f5  mov     dx, [eax]
0x100200f8  cmp     dx, [ecx]
0x100200fb  jnz     short loc_1002011B
0x100200fd  test    dx, dx
0x10020100  jz      short loc_10020117
0x10020102  mov     dx, [eax+2]
0x10020106  cmp     dx, [ecx+2]
0x1002010a  jnz     short loc_1002011B
0x1002010c  add     eax, 4
0x1002010f  add     ecx, 4
0x10020112  test    dx, dx
0x10020115  jnz     short loc_100200F5
0x10020117  xor     eax, eax
0x10020119  jmp     short loc_10020120
0x1002011b  sbb     eax, eax
0x1002011d  or      eax, 1
0x10020120  test    eax, eax
0x10020122  jz      loc_100201E0
0x10020128  mov     [ebp+var_18], esi
0x1002012b  inc     ebx
0x1002012c  mov     esi, [esi]
0x1002012e  mov     [ebp+var_10], ebx
0x10020131  test    esi, esi
0x10020133  jnz     short loc_100200F0
0x10020135  lea     eax, [ebp+var_C]
0x10020138  mov     edx, offset _ControlPanelSettings
0x1002013d  push    eax
0x1002013e  mov     ecx, edi
0x10020140  call    _FMTStoreFormat@12; FMTStoreFormat(x,x,x)
0x10020145  test    eax, eax
0x10020147  jnz     loc_10020383
0x1002014d  cmp     _ControlPanelSettings, 1
0x10020154  jnz     short loc_10020193
0x10020156  push    0FFFFFFFFh
0x10020158  push    offset asc_10004548; "$"
0x1002015d  push    0FFFFFFFFh
0x1002015f  push    offset dword_1003B8F0
0x10020164  push    30001h
0x10020169  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1002016f  push    eax
0x10020170  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x10020176  sub     eax, 2
0x10020179  jnz     short loc_10020193
0x1002017b  cmp     word_1003B920, 3Ah ; ':'
0x10020183  jnz     short loc_10020193
0x10020185  cmp     word_1003B922, 2Dh ; '-'
0x1002018d  jz      loc_100202D7
0x10020193  mov     esi, [ebp+var_C]
0x10020196  test    esi, esi
0x10020198  jz      loc_100202DA
0x1002019e  mov     eax, [esi+8]
0x100201a1  test    eax, eax
0x100201a3  jz      loc_100202DA
0x100201a9  mov     cl, [eax]
0x100201ab  test    cl, cl
0x100201ad  jz      loc_100202DA
0x100201b3  cmp     cl, 3
0x100201b6  jz      loc_100202DA
0x100201bc  cmp     cl, 2
0x100201bf  jnz     short loc_10020215
0x100201c1  mov     cl, [eax+8]
0x100201c4  and     cl, 70h
0x100201c7  test    byte ptr [eax+8], 0Fh
0x100201cb  jz      short loc_100201F3
0x100201cd  test    cl, cl
0x100201cf  jnz     short loc_10020206
0x100201d1  mov     ecx, esi
0x100201d3  call    _FMTDeleteFormat@4; FMTDeleteFormat(x)
0x100201d8  mov     ebx, dword ptr qword_1003B8D0
0x100201de  jmp     short loc_1002022C
0x100201e0  mov     eax, [ebp+arg_0]
0x100201e3  mov     ecx, [esi+4]
0x100201e6  pop     edi
0x100201e7  pop     esi
0x100201e8  mov     [eax], ecx
0x100201ea  xor     eax, eax
0x100201ec  pop     ebx
0x100201ed  mov     esp, ebp
0x100201ef  pop     ebp
0x100201f0  retn    4
0x100201f3  test    cl, cl
0x100201f5  jz      short loc_10020206
0x100201f7  mov     ecx, esi
0x100201f9  call    _FMTDeleteFormat@4; FMTDeleteFormat(x)
0x100201fe  mov     ebx, dword ptr qword_1003B8D0+4
0x10020204  jmp     short loc_1002022C
0x10020206  mov     ecx, esi
0x10020208  call    _FMTDeleteFormat@4; FMTDeleteFormat(x)
0x1002020d  mov     ebx, dword ptr _StandardFormats+0Ch
0x10020213  jmp     short loc_1002022C
0x10020215  cmp     dword ptr [eax+18h], 0
0x10020219  jz      loc_100202DA
0x1002021f  mov     ecx, esi
0x10020221  call    _FMTDeleteFormat@4; FMTDeleteFormat(x)
0x10020226  mov     ebx, dword ptr _StandardFormats
0x1002022c  mov     esi, [ebp+var_14]
0x1002022f  mov     [ebp+var_8], 1
0x10020236  mov     [ebp+var_4], ebx
0x10020239  mov     esi, [esi+4Ch]
0x1002023c  test    esi, esi
0x1002023e  jz      short loc_1002027E
0x10020240  mov     ecx, ebx
0x10020242  lea     eax, [esi+10h]
0x10020245  mov     dx, [eax]
0x10020248  cmp     dx, [ecx]
0x1002024b  jnz     short loc_1002026B
0x1002024d  test    dx, dx
0x10020250  jz      short loc_10020267
0x10020252  mov     dx, [eax+2]
0x10020256  cmp     dx, [ecx+2]
0x1002025a  jnz     short loc_1002026B
0x1002025c  add     eax, 4
0x1002025f  add     ecx, 4
0x10020262  test    dx, dx
0x10020265  jnz     short loc_10020245
0x10020267  xor     eax, eax
0x10020269  jmp     short loc_10020270
0x1002026b  sbb     eax, eax
0x1002026d  or      eax, 1
0x10020270  test    eax, eax
0x10020272  jz      loc_100201E0
0x10020278  mov     esi, [esi]
0x1002027a  test    esi, esi
0x1002027c  jnz     short loc_10020240
0x1002027e  lea     eax, [ebp+var_C]
0x10020281  mov     edx, offset _ControlPanelSettings
0x10020286  push    eax
0x10020287  mov     ecx, ebx
0x10020289  call    _FMTStoreFormat@12; FMTStoreFormat(x,x,x)
0x1002028e  test    eax, eax
0x10020290  jnz     loc_10020383
0x10020296  cmp     [ebp+var_8], eax
0x10020299  jz      short loc_100202D7
0x1002029b  mov     ecx, ebx
0x1002029d  lea     edx, [ecx+2]
0x100202a0  mov     ax, [ecx]
0x100202a3  add     ecx, 2
0x100202a6  test    ax, ax
0x100202a9  jnz     short loc_100202A0
0x100202ab  sub     ecx, edx
0x100202ad  sar     ecx, 1
0x100202af  lea     ecx, ds:14h[ecx*2]
0x100202b6  call    _MemAllocate@4; MemAllocate(x)
0x100202bb  mov     edi, eax
0x100202bd  test    edi, edi
0x100202bf  jz      short loc_10020301
0x100202c1  mov     ecx, [ebp+var_C]
0x100202c4  lea     ebx, [edi+4]
0x100202c7  mov     eax, [ebp+var_10]
0x100202ca  mov     [edi+8], ecx
0x100202cd  lea     ecx, [edi+10h]
0x100202d0  mov     [ebx], eax
0x100202d2  mov     eax, [ebp+var_4]
0x100202d5  jmp     short loc_1002032B
0x100202d7  mov     esi, [ebp+var_C]
0x100202da  mov     ecx, edi
0x100202dc  lea     edx, [ecx+2]
0x100202df  nop
0x100202e0  mov     ax, [ecx]
0x100202e3  add     ecx, 2
0x100202e6  test    ax, ax
0x100202e9  jnz     short loc_100202E0
0x100202eb  sub     ecx, edx
0x100202ed  sar     ecx, 1
0x100202ef  lea     ecx, ds:14h[ecx*2]
0x100202f6  call    _MemAllocate@4; MemAllocate(x)
0x100202fb  mov     edi, eax
0x100202fd  test    edi, edi
0x100202ff  jnz     short loc_1002030F
0x10020301  pop     edi
0x10020302  pop     esi
0x10020303  mov     eax, 0FFFFFFFEh
0x10020308  pop     ebx
0x10020309  mov     esp, ebp
0x1002030b  pop     ebp
0x1002030c  retn    4
0x1002030f  cmp     [ebp+var_8], 0
0x10020313  lea     ebx, [edi+4]
0x10020316  mov     eax, [ebp+var_10]
0x10020319  lea     ecx, [edi+10h]
0x1002031c  mov     [edi+8], esi
0x1002031f  mov     [ebx], eax
0x10020321  jz      short loc_10020328
0x10020323  mov     eax, [ebp+var_4]
0x10020326  jmp     short loc_1002032E
0x10020328  mov     eax, [ebp+var_1C]
0x1002032b  mov     [ebp+var_4], eax
0x1002032e  mov     esi, eax
0x10020330  lea     edx, [esi+2]
0x10020333  mov     ax, [esi]
0x10020336  add     esi, 2
0x10020339  test    ax, ax
0x1002033c  jnz     short loc_10020333
0x1002033e  sub     esi, edx
0x10020340  mov     edx, [ebp+var_4]
0x10020343  sar     esi, 1
0x10020345  lea     eax, [esi+1]
0x10020348  push    eax
0x10020349  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002034e  mov     eax, [ebp+var_14]
0x10020351  cmp     dword ptr [eax+4Ch], 0
0x10020355  jnz     short loc_1002036C
0x10020357  mov     [eax+4Ch], edi
0x1002035a  mov     eax, [ebp+arg_0]
0x1002035d  mov     ecx, [ebx]
0x1002035f  pop     edi
0x10020360  pop     esi
0x10020361  mov     [eax], ecx
0x10020363  xor     eax, eax
0x10020365  pop     ebx
0x10020366  mov     esp, ebp
0x10020368  pop     ebp
0x10020369  retn    4
0x1002036c  mov     eax, [ebp+var_18]
0x1002036f  mov     [eax], edi
0x10020371  mov     eax, [ebp+arg_0]
0x10020374  mov     ecx, [ebx]
0x10020376  pop     edi
0x10020377  pop     esi
0x10020378  mov     [eax], ecx
0x1002037a  xor     eax, eax
0x1002037c  pop     ebx
0x1002037d  mov     esp, ebp
0x1002037f  pop     ebp
0x10020380  retn    4
0x10020383  pop     edi
0x10020384  pop     esi
0x10020385  mov     eax, 0FFFFFFF6h
0x1002038a  pop     ebx
0x1002038b  mov     esp, ebp
0x1002038d  pop     ebp
0x1002038e  retn    4
```
