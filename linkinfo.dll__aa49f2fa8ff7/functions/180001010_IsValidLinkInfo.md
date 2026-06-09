# IsValidLinkInfo

- ea: `0x180001010`
- end: `0x18000141e`
- name: `IsValidLinkInfo`
- size: `1038`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001010`
- `0x180001430`
- `0x180001470`

## pseudocode

```c
__int64 __fastcall IsValidLinkInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r11
  unsigned int v4; // r9d
  unsigned int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // edx
  __int64 v8; // r10
  _BYTE *v9; // rax
  unsigned int v10; // ecx
  unsigned __int64 v11; // rdx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned int v16; // r9d
  __int64 v17; // r10
  unsigned int v18; // r9d
  _BYTE *v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // r9d
  int v25; // r10d
  unsigned int v26; // edx
  _BYTE *v27; // rcx
  unsigned int v28; // eax
  unsigned __int64 v29; // rdx
  __int64 v30; // rdx
  _BYTE *v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rdx
  int v34; // r10d
  unsigned int v35; // edx
  unsigned int v36; // r8d
  __int64 v37; // r9
  _WORD *v38; // rcx
  unsigned __int64 i; // rdx
  _WORD *v40; // rcx
  unsigned __int64 j; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  unsigned int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rax

  v3 = a1;
  if ( !a1 )
    return 0;
  v4 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 < 0x1Cu )
    return 0;
  v5 = *(_DWORD *)(a1 + 4);
  if ( v4 < v5 || v5 != 28 && v5 < 0x24 )
    return 0;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
  {
    v6 = *(unsigned int *)(a1 + 12);
    if ( (unsigned int)v6 >= v4 )
      return 0;
    v7 = *(_DWORD *)(a1 + 16);
    if ( v7 >= v4 )
      return 0;
    v8 = *(unsigned int *)(a1 + 24);
    if ( (unsigned int)v8 >= v4 )
      return 0;
    if ( (v6 & 3) != 0 )
      return 0;
    v9 = (_BYTE *)(a1 + v7);
    if ( !v9 )
      return 0;
    v10 = v4 - v7;
    v11 = v4 - v7;
    if ( v11 > 0x7FFFFFFF )
      return 0;
    if ( v10 )
    {
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v11;
      }
      while ( v11 );
    }
    if ( !v11 )
      return 0;
    v14 = (_BYTE *)(v3 + v8);
    if ( !(v3 + v8) )
      return 0;
    v15 = v4 - (unsigned int)v8;
    if ( v15 > 0x7FFFFFFF )
      return 0;
    if ( v4 != (_DWORD)v8 )
    {
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v15;
      }
      while ( v15 );
    }
    if ( !v15 )
      return 0;
    v16 = v4 - v6;
    if ( v16 < 0x10 )
      return 0;
    v17 = v3 + v6;
    a3 = *(unsigned int *)(v3 + v6);
    if ( (unsigned int)a3 > v16 )
      return 0;
    if ( (unsigned int)a3 < 0x10 )
      return 0;
    v18 = *(_DWORD *)(v17 + 12);
    if ( v18 >= (unsigned int)a3 )
      return 0;
    v19 = (_BYTE *)(v17 + v18);
    if ( !v19 )
      return 0;
    v20 = (unsigned int)a3 - v18;
    if ( v20 > 0x7FFFFFFF )
      return 0;
    if ( (_DWORD)a3 != v18 )
    {
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v20;
      }
      while ( v20 );
    }
    if ( !v20 )
      return 0;
    if ( v18 != 16 )
    {
      if ( (unsigned int)a3 < 0x14 )
        return 0;
      v13 = *(unsigned int *)(v17 + 16);
      if ( (unsigned int)v13 >= (unsigned int)a3
        || (v13 & 1) != 0
        || (unsigned int)StringCbLengthW(
                           (const unsigned __int16 *)(v17 + v13),
                           (unsigned int)(a3 - v13),
                           (unsigned __int64 *)(unsigned int)(a3 - v13)) )
      {
        return 0;
      }
    }
  }
  if ( (*(_BYTE *)(v3 + 8) & 2) == 0 )
    goto LABEL_85;
  v21 = *(unsigned int *)(v3 + 20);
  v22 = *(_DWORD *)v3;
  if ( (unsigned int)v21 >= *(_DWORD *)v3 )
    return 0;
  if ( *(_DWORD *)(v3 + 24) >= v22 )
    return 0;
  if ( (v21 & 3) != 0 )
    return 0;
  v23 = v22 - v21;
  if ( v23 < 0x14 )
    return 0;
  v24 = *(_DWORD *)(v3 + v21);
  a3 = v3 + v21;
  if ( v24 > v23 )
    return 0;
  if ( v24 < 0x14 )
    return 0;
  v25 = *(_DWORD *)(a3 + 4);
  if ( (v25 & 0xFFFFFFFC) != 0 )
    return 0;
  v26 = *(_DWORD *)(a3 + 8);
  if ( v26 >= v24 )
    return 0;
  v27 = (_BYTE *)(a3 + v26);
  if ( !v27 )
    return 0;
  v28 = v24 - v26;
  v29 = v24 - v26;
  if ( v29 > 0x7FFFFFFF )
    return 0;
  if ( v28 )
  {
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v29;
    }
    while ( v29 );
  }
  if ( !v29 )
    return 0;
  if ( (v25 & 1) != 0 )
  {
    v43 = *(unsigned int *)(a3 + 12);
    if ( (unsigned int)v43 >= v24
      || (unsigned int)StringCbLengthA((const char *)(a3 + v43), v24 - (unsigned int)v43, (unsigned __int64 *)a3) )
    {
      return 0;
    }
  }
  if ( *(_DWORD *)(a3 + 8) != 20 )
  {
    v44 = *(_DWORD *)a3;
    if ( *(_DWORD *)a3 < 0x1Cu )
      return 0;
    v45 = *(unsigned int *)(a3 + 20);
    if ( (unsigned int)v45 >= v44 )
      return 0;
    if ( (v45 & 1) != 0 )
      return 0;
    if ( (unsigned int)StringCbLengthW(
                         (const unsigned __int16 *)(a3 + v45),
                         v44 - (unsigned int)v45,
                         (unsigned __int64 *)a3) )
      return 0;
    if ( (*(_BYTE *)(a3 + 4) & 1) != 0 )
    {
      v46 = *(unsigned int *)(a3 + 24);
      if ( (unsigned int)v46 >= *(_DWORD *)a3
        || (v46 & 1) != 0
        || (unsigned int)StringCbLengthW(
                           (const unsigned __int16 *)(a3 + v46),
                           (unsigned int)(*(_DWORD *)a3 - v46),
                           (unsigned __int64 *)a3) )
      {
        return 0;
      }
    }
  }
  if ( *(_DWORD *)(v3 + 4) == 28 )
  {
    v30 = *(unsigned int *)(v3 + 24);
    v31 = (_BYTE *)(v30 + v3);
    if ( !(v30 + v3) )
      return 0;
    v32 = *(_DWORD *)v3 - v30;
    v33 = v32;
    if ( v32 > 0x7FFFFFFFuLL )
      return 0;
    if ( v32 )
    {
      do
      {
        if ( !*v31 )
          break;
        ++v31;
        --v33;
      }
      while ( v33 );
    }
    if ( !v33 )
      return 0;
  }
  else
  {
LABEL_85:
    if ( *(_DWORD *)(v3 + 4) >= 0x24u )
    {
      v34 = *(_DWORD *)(v3 + 8);
      if ( (v34 & 1) != 0 )
      {
        v35 = *(_DWORD *)(v3 + 28);
        v36 = *(_DWORD *)v3;
        if ( v35 >= *(_DWORD *)v3 )
          return 0;
        v37 = *(unsigned int *)(v3 + 32);
        if ( (unsigned int)v37 >= v36 )
          return 0;
        if ( (((unsigned __int8)v35 | (unsigned __int8)v37) & 1) != 0 )
          return 0;
        v38 = (_WORD *)(v3 + v35);
        if ( !v38 )
          return 0;
        for ( i = (unsigned __int64)(v36 - v35) >> 1; i; --i )
        {
          if ( !*v38 )
            break;
          ++v38;
        }
        if ( !i )
          return 0;
        v40 = (_WORD *)(v3 + v37);
        if ( !(v3 + v37) )
          return 0;
        a3 = v36 - (unsigned int)v37;
        for ( j = (unsigned __int64)(unsigned int)a3 >> 1; j; --j )
        {
          if ( !*v40 )
            break;
          ++v40;
        }
        if ( !j )
          return 0;
      }
      if ( (v34 & 2) != 0 )
      {
        v42 = *(unsigned int *)(v3 + 32);
        if ( (unsigned int)v42 >= *(_DWORD *)v3
          || (v42 & 1) != 0
          || (int)StringCbLengthW(
                    (const unsigned __int16 *)(v3 + v42),
                    (unsigned int)(*(_DWORD *)v3 - v42),
                    (unsigned __int64 *)a3) < 0 )
        {
          return 0;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  mov     r11, rcx
0x180001017  test    rcx, rcx
0x18000101a  jz      short loc_180001093
0x18000101c  mov     r9d, [rcx]
0x18000101f  cmp     r9d, 1Ch
0x180001023  jb      short loc_180001093
0x180001025  mov     eax, [rcx+4]
0x180001028  cmp     r9d, eax
0x18000102b  jb      short loc_180001093
0x18000102d  cmp     eax, 1Ch
0x180001030  jnz     loc_1800012A0
0x180001036  test    byte ptr [rcx+8], 1
0x18000103a  jz      loc_1800010CC
0x180001040  mov     r8d, [rcx+0Ch]
0x180001044  cmp     r8d, r9d
0x180001047  jnb     short loc_180001093
0x180001049  mov     edx, [rcx+10h]
0x18000104c  cmp     edx, r9d
0x18000104f  jnb     short loc_180001093
0x180001051  mov     r10d, [rcx+18h]
0x180001055  cmp     r10d, r9d
0x180001058  jnb     short loc_180001093
0x18000105a  test    r8b, 3
0x18000105e  jnz     short loc_180001093
0x180001060  mov     eax, edx
0x180001062  add     rax, r11
0x180001065  jz      short loc_180001093
0x180001067  mov     ecx, r9d
0x18000106a  sub     ecx, edx
0x18000106c  mov     edx, ecx
0x18000106e  cmp     rdx, 7FFFFFFFh
0x180001075  ja      short loc_180001093
0x180001077  test    ecx, ecx
0x180001079  jz      short loc_18000108E
0x18000107b  nop     dword ptr [rax+rax+00h]
0x180001080  cmp     byte ptr [rax], 0
0x180001083  jz      short loc_18000108E
0x180001085  inc     rax
0x180001088  sub     rdx, 1
0x18000108c  jnz     short loc_180001080
0x18000108e  test    rdx, rdx
0x180001091  jnz     short loc_1800010ED
0x180001093  xor     eax, eax
0x180001095  add     rsp, 28h
0x180001099  retn
0x18000109b  test    rdx, rdx
0x18000109e  jz      short loc_180001093
0x1800010a0  cmp     r9d, 10h
0x1800010a4  jz      short loc_1800010CC
0x1800010a6  cmp     r8d, 14h
0x1800010aa  jb      short loc_180001093
0x1800010ac  mov     eax, [r10+10h]
0x1800010b0  cmp     eax, r8d
0x1800010b3  jnb     short loc_180001093
0x1800010b5  test    al, 1
0x1800010b7  jnz     short loc_180001093
0x1800010b9  sub     r8d, eax; unsigned __int64 *
0x1800010bc  lea     rcx, [r10+rax]; unsigned __int16 *
0x1800010c0  mov     edx, r8d; unsigned __int64
0x1800010c3  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800010c8  test    eax, eax
0x1800010ca  jnz     short loc_180001093
0x1800010cc  test    byte ptr [r11+8], 2
0x1800010d1  jnz     loc_18000119C
0x1800010d7  cmp     dword ptr [r11+4], 24h ; '$'
0x1800010dc  jnb     loc_1800012AE
0x1800010e2  mov     eax, 1
0x1800010e7  add     rsp, 28h
0x1800010eb  retn
0x1800010ed  mov     rcx, r10
0x1800010f0  add     rcx, r11
0x1800010f3  jz      short loc_180001093
0x1800010f5  mov     eax, r9d
0x1800010f8  sub     eax, r10d
0x1800010fb  mov     edx, eax
0x1800010fd  cmp     rdx, 7FFFFFFFh
0x180001104  ja      short loc_180001093
0x180001106  test    eax, eax
0x180001108  jz      short loc_18000111E
0x18000110a  nop     word ptr [rax+rax+00h]
0x180001110  cmp     byte ptr [rcx], 0
0x180001113  jz      short loc_18000111E
0x180001115  inc     rcx
0x180001118  sub     rdx, 1
0x18000111c  jnz     short loc_180001110
0x18000111e  test    rdx, rdx
0x180001121  jz      loc_180001093
0x180001127  sub     r9d, r8d
0x18000112a  cmp     r9d, 10h
0x18000112e  jb      loc_180001093
0x180001134  lea     r10, [r11+r8]
0x180001138  mov     r8d, [r11+r8]
0x18000113c  cmp     r8d, r9d
0x18000113f  ja      loc_180001093
0x180001145  cmp     r8d, 10h
0x180001149  jb      loc_180001093
0x18000114f  mov     r9d, [r10+0Ch]
0x180001153  cmp     r9d, r8d
0x180001156  jnb     loc_180001093
0x18000115c  mov     ecx, r9d
0x18000115f  add     rcx, r10
0x180001162  jz      loc_180001093
0x180001168  mov     eax, r8d
0x18000116b  sub     eax, r9d
0x18000116e  mov     edx, eax
0x180001170  cmp     rdx, 7FFFFFFFh
0x180001177  ja      loc_180001093
0x18000117d  test    eax, eax
0x18000117f  jz      loc_18000109B
0x180001185  cmp     byte ptr [rcx], 0
0x180001188  jz      loc_18000109B
0x18000118e  inc     rcx
0x180001191  sub     rdx, 1
0x180001195  jnz     short loc_180001185
0x180001197  jmp     loc_18000109B
0x18000119c  mov     eax, [r11+14h]
0x1800011a0  mov     ecx, [r11]
0x1800011a3  cmp     eax, ecx
0x1800011a5  jnb     loc_180001093
0x1800011ab  cmp     [r11+18h], ecx
0x1800011af  jnb     loc_180001093
0x1800011b5  test    al, 3
0x1800011b7  jnz     loc_180001093
0x1800011bd  sub     ecx, eax
0x1800011bf  cmp     ecx, 14h
0x1800011c2  jb      loc_180001093
0x1800011c8  mov     r9d, [r11+rax]
0x1800011cc  lea     r8, [r11+rax]; unsigned __int64 *
0x1800011d0  cmp     r9d, ecx
0x1800011d3  ja      loc_180001093
0x1800011d9  cmp     r9d, 14h
0x1800011dd  jb      loc_180001093
0x1800011e3  mov     r10d, [r8+4]
0x1800011e7  test    r10d, 0FFFFFFFCh
0x1800011ee  jnz     loc_180001093
0x1800011f4  mov     edx, [r8+8]
0x1800011f8  cmp     edx, r9d
0x1800011fb  jnb     loc_180001093
0x180001201  mov     ecx, edx
0x180001203  add     rcx, r8
0x180001206  jz      loc_180001093
0x18000120c  mov     eax, r9d
0x18000120f  sub     eax, edx
0x180001211  mov     edx, eax
0x180001213  cmp     rdx, 7FFFFFFFh
0x18000121a  ja      loc_180001093
0x180001220  test    eax, eax
0x180001222  jz      short loc_180001232
0x180001224  cmp     byte ptr [rcx], 0
0x180001227  jz      short loc_180001232
0x180001229  inc     rcx
0x18000122c  sub     rdx, 1
0x180001230  jnz     short loc_180001224
0x180001232  test    rdx, rdx
0x180001235  jz      loc_180001093
0x18000123b  test    r10b, 1
0x18000123f  jnz     loc_180001384
0x180001245  cmp     dword ptr [r8+8], 14h
0x18000124a  jnz     loc_1800013AD
0x180001250  cmp     dword ptr [r11+4], 1Ch
0x180001255  jnz     loc_1800010D7
0x18000125b  mov     edx, [r11+18h]
0x18000125f  lea     rcx, [rdx+r11]
0x180001263  test    rcx, rcx
0x180001266  jz      loc_180001093
0x18000126c  mov     eax, [r11]
0x18000126f  sub     eax, edx
0x180001271  mov     edx, eax
0x180001273  cmp     rdx, 7FFFFFFFh
0x18000127a  ja      loc_180001093
0x180001280  test    eax, eax
0x180001282  jz      short loc_180001292
0x180001284  cmp     byte ptr [rcx], 0
0x180001287  jz      short loc_180001292
0x180001289  inc     rcx
0x18000128c  sub     rdx, 1
0x180001290  jnz     short loc_180001284
0x180001292  test    rdx, rdx
0x180001295  jnz     loc_1800010E2
0x18000129b  jmp     loc_180001093
0x1800012a0  cmp     eax, 24h ; '$'
0x1800012a3  jnb     loc_180001036
0x1800012a9  jmp     loc_180001093
0x1800012ae  mov     r10d, [r11+8]
0x1800012b2  test    r10b, 1
0x1800012b6  jz      loc_180001349
0x1800012bc  mov     edx, [r11+1Ch]
0x1800012c0  mov     r8d, [r11]
0x1800012c3  cmp     edx, r8d
0x1800012c6  jnb     loc_180001093
0x1800012cc  mov     r9d, [r11+20h]
0x1800012d0  cmp     r9d, r8d
0x1800012d3  jnb     loc_180001093
0x1800012d9  mov     eax, r9d
0x1800012dc  or      eax, edx
0x1800012de  test    al, 1
0x1800012e0  jnz     loc_180001093
0x1800012e6  mov     ecx, edx
0x1800012e8  add     rcx, r11
0x1800012eb  jz      loc_180001093
0x1800012f1  mov     eax, r8d
0x1800012f4  sub     eax, edx
0x1800012f6  mov     edx, eax
0x1800012f8  shr     rdx, 1
0x1800012fb  jz      short loc_180001310
0x1800012fd  nop     dword ptr [rax]
0x180001300  cmp     word ptr [rcx], 0
0x180001304  jz      short loc_180001310
0x180001306  add     rcx, 2
0x18000130a  sub     rdx, 1
0x18000130e  jnz     short loc_180001300
0x180001310  test    rdx, rdx
0x180001313  jz      loc_180001093
0x180001319  mov     rcx, r9
0x18000131c  add     rcx, r11
0x18000131f  jz      loc_180001093
0x180001325  sub     r8d, r9d; unsigned __int64 *
0x180001328  mov     eax, r8d
0x18000132b  shr     rax, 1
0x18000132e  jz      short loc_180001340
0x180001330  cmp     word ptr [rcx], 0
0x180001334  jz      short loc_180001340
0x180001336  add     rcx, 2
0x18000133a  sub     rax, 1
0x18000133e  jnz     short loc_180001330
0x180001340  test    rax, rax
0x180001343  jz      loc_180001093
0x180001349  test    r10b, 2
0x18000134d  jz      loc_1800010E2
0x180001353  mov     eax, [r11+20h]
0x180001357  mov     ecx, [r11]
0x18000135a  cmp     eax, ecx
0x18000135c  jnb     loc_180001093
0x180001362  test    al, 1
0x180001364  jnz     loc_180001093
0x18000136a  sub     ecx, eax
0x18000136c  mov     edx, ecx; unsigned __int64
0x18000136e  lea     rcx, [r11+rax]; unsigned __int16 *
0x180001372  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180001377  test    eax, eax
0x180001379  jns     loc_1800010E2
0x18000137f  jmp     loc_180001093
0x180001384  mov     eax, [r8+0Ch]
0x180001388  cmp     eax, r9d
0x18000138b  jnb     loc_180001093
0x180001391  sub     r9d, eax
0x180001394  lea     rcx, [r8+rax]; char *
0x180001398  mov     edx, r9d; unsigned __int64
0x18000139b  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800013a0  test    eax, eax
0x1800013a2  jz      loc_180001245
0x1800013a8  jmp     loc_180001093
0x1800013ad  mov     eax, [r8]
0x1800013b0  cmp     eax, 1Ch
0x1800013b3  jb      loc_180001093
0x1800013b9  mov     ecx, [r8+14h]
0x1800013bd  cmp     ecx, eax
0x1800013bf  jnb     loc_180001093
0x1800013c5  test    cl, 1
0x1800013c8  jnz     loc_180001093
0x1800013ce  sub     eax, ecx
0x1800013d0  add     rcx, r8; unsigned __int16 *
0x1800013d3  mov     edx, eax; unsigned __int64
0x1800013d5  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800013da  test    eax, eax
0x1800013dc  jnz     loc_180001093
0x1800013e2  test    byte ptr [r8+4], 1
0x1800013e7  jz      loc_180001250
0x1800013ed  mov     eax, [r8+18h]
0x1800013f1  mov     ecx, [r8]
0x1800013f4  cmp     eax, ecx
0x1800013f6  jnb     loc_180001093
0x1800013fc  test    al, 1
0x1800013fe  jnz     loc_180001093
0x180001404  sub     ecx, eax
0x180001406  mov     edx, ecx; unsigned __int64
0x180001408  lea     rcx, [r8+rax]; unsigned __int16 *
0x18000140c  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180001411  test    eax, eax
0x180001413  jnz     loc_180001093
0x180001419  jmp     loc_180001250
```
