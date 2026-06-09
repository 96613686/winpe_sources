# woff2::_anonymous_namespace_::ReadWOFF2Header

- ea: `0x180219060`
- end: `0x180219856`
- name: `woff2::_anonymous_namespace_::ReadWOFF2Header`
- size: `2038`
- prototype: `bool __fastcall(__int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180218c80`

## callees

- `0x1801dd4c8`
- `0x1801e22d0`
- `0x1801efbdc`
- `0x180212f4c`
- `0x180212ffc`
- `0x1802175b0`
- `0x180217790`
- `0x180219060`
- `0x18021e1ce`
- `0x1802250f0`
- `0x180225180`
- `0x180225210`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1802196e4`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1802197c5`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1802196e4`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1802197c5`

## string_xrefs

- `0x1802192aa`: `pamcdaehaehhxtmhpxameman2/SOtsop tvcmgpffylgacolperp FFCGROVTDBECLBEpsagxmdhnrekHSTLTLCPXMDVaehvxtmvESABFEDGSOPGBUSGCSBEFTSJHTAMTDBCCLBCRLOCLAPC GVSxibstncaravatadbcolbnlsbravccsdftaefxtmfravfravgytshtsujracltromxromdbpoporpkartfpaZfliStalGcolGtaeFlliS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall woff2::_anonymous_namespace_::ReadWOFF2Header(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // r13
  __int64 v5; // r9
  unsigned __int64 v6; // r10
  unsigned int *v7; // r8
  unsigned __int32 v8; // eax
  unsigned __int32 v9; // edx
  unsigned __int32 v10; // eax
  unsigned int v11; // edx
  unsigned __int32 v12; // edx
  char *v13; // rdi
  __int64 *v14; // r12
  __int64 v15; // rsi
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  __int64 v18; // rbx
  int v19; // esi
  unsigned int v20; // r14d
  unsigned __int64 i; // r15
  __int64 v22; // rdi
  unsigned __int8 v23; // bl
  __int64 v24; // rax
  unsigned __int32 v25; // edi
  __int64 v26; // r12
  unsigned __int8 v27; // bl
  unsigned int v28; // eax
  int v29; // ebx
  unsigned __int32 *v30; // rcx
  __int64 v31; // r14
  unsigned __int64 v32; // r8
  unsigned int v33; // edx
  bool v34; // zf
  __int64 v35; // rcx
  unsigned __int32 v36; // eax
  _QWORD *v37; // rbx
  __int64 *v38; // r15
  __int64 v39; // r10
  _QWORD *v40; // rsi
  _QWORD *k; // rdi
  unsigned __int64 j; // r9
  unsigned int v43; // edi
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // r15
  char *v47; // r14
  __int64 v48; // rax
  __int64 v49; // rdi
  unsigned __int64 v50; // rsi
  char *v51; // rax
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rdx
  __int64 v54; // r14
  char *v55; // rbx
  size_t v56; // rbx
  unsigned int v57; // ebx
  unsigned int v58; // esi
  __int64 v59; // rdi
  FILE *v60; // rax
  woff2 *v62; // rcx
  __int64 v63; // rbx
  unsigned __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rdi
  __int64 m; // rcx
  __int64 v68; // rax
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rbx
  FILE *v71; // rax
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  __int64 v74; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v75; // [rsp+38h] [rbp-40h]
  __int64 v76; // [rsp+40h] [rbp-38h]
  unsigned __int64 v77; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int32 v78; // [rsp+50h] [rbp-28h]
  unsigned __int32 v79; // [rsp+54h] [rbp-24h]
  unsigned __int32 v80; // [rsp+58h] [rbp-20h]
  unsigned __int32 v81; // [rsp+5Ch] [rbp-1Ch]
  __int64 *v82; // [rsp+60h] [rbp-18h]
  unsigned int v83; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v84; // [rsp+C8h] [rbp+50h] BYREF
  __int64 v85; // [rsp+D0h] [rbp+58h]
  __int64 *v86; // [rsp+D8h] [rbp+60h]

  v85 = a3;
  v74 = a1;
  v75 = a2;
  v4 = a2;
  v5 = a1;
  v6 = a2;
  if ( a2 < 4 )
    return 0;
  if ( _byteswap_ulong(*(_DWORD *)a1) != 2001684018 )
    return 0;
  if ( a2 < 8 )
    return 0;
  *(_DWORD *)a3 = _byteswap_ulong(*(_DWORD *)(a1 + 4));
  if ( a2 < 0xC )
    return 0;
  if ( a2 != _byteswap_ulong(*(_DWORD *)(a1 + 8)) )
    return 0;
  if ( a2 < 0xE )
    return 0;
  v7 = (unsigned int *)*(unsigned __int16 *)(a1 + 12);
  LOWORD(v7) = __ROR2__((_WORD)v7, 8);
  *(_WORD *)(a3 + 8) = (_WORD)v7;
  if ( !(_WORD)v7 )
    return 0;
  if ( a2 < 0x14 )
    return 0;
  if ( a2 - 6 < 0xE )
    return 0;
  if ( a2 < 0x18 )
    return 0;
  *(_DWORD *)(a3 + 24) = _byteswap_ulong(*(_DWORD *)(a1 + 20));
  if ( a2 < 0x1C )
    return 0;
  if ( a2 - 4 < 0x18 )
    return 0;
  if ( a2 < 0x20 )
    return 0;
  v8 = _byteswap_ulong(*(_DWORD *)(a1 + 28));
  v78 = v8;
  if ( a2 < 0x24 )
    return 0;
  v9 = _byteswap_ulong(*(_DWORD *)(a1 + 32));
  v79 = v9;
  if ( v6 < 0x28 || v8 && (v8 >= v6 || v6 - v8 < v9) )
    return 0;
  if ( v4 < 0x2C )
    return 0;
  v10 = _byteswap_ulong(*(_DWORD *)(a1 + 40));
  v80 = v10;
  if ( v4 < 0x30 )
    return 0;
  v11 = *(_DWORD *)(a1 + 44);
  v76 = 48;
  v12 = _byteswap_ulong(v11);
  v81 = v12;
  if ( v10 )
  {
    if ( v10 >= v4 || v4 - v10 < v12 )
      return 0;
  }
  v13 = *(char **)(a3 + 40);
  v14 = (__int64 *)(a3 + 32);
  v15 = *(_QWORD *)(a3 + 32);
  v16 = (__int64)&v13[-v15];
  v86 = (__int64 *)(a3 + 32);
  if ( (unsigned __int16)v7 >= (unsigned __int64)((__int64)&v13[-v15] / 40) )
  {
    if ( (unsigned __int16)v7 > (unsigned __int64)(v16 / 40) )
    {
      v17 = (*(_QWORD *)(a3 + 48) - v15) / 40;
      if ( (unsigned __int16)v7 <= v17 )
      {
        v18 = (unsigned __int16)v7 - v16 / 40;
        if ( v18 )
        {
          LOBYTE(v17) = 0;
          memset_0(v13, v17, 40 * v18);
          do
          {
            v13 += 40;
            --v18;
          }
          while ( v18 );
          v6 = v75;
          v5 = v74;
        }
        *(_QWORD *)(a3 + 40) = v13;
      }
      else
      {
        std::vector<woff2::Table>::_Resize_reallocate<std::_Value_init_tag>(a3 + 32, (unsigned __int16)v7, &v83);
        v6 = v75;
        v5 = v74;
      }
    }
  }
  else
  {
    *(_QWORD *)(a3 + 40) = v15 + 40LL * (unsigned __int16)v7;
  }
  v19 = 0;
  v77 = *(unsigned __int16 *)(a3 + 8);
  v20 = 0;
  for ( i = 0; i < v77; v5 = v74 )
  {
    v22 = v76 + 1;
    if ( v76 + 1 > v6 )
      return 0;
    v23 = *(_BYTE *)(v76 + v5);
    ++v76;
    if ( (v23 & 0x3F) == 0x3F )
    {
      v24 = v22 + 4;
      if ( v22 + 4 > v6 )
        return 0;
      v25 = _byteswap_ulong(*(_DWORD *)(v22 + v5));
      v76 = v24;
    }
    else
    {
      v25 = *(_DWORD *)&woff2::kKnownTags[4 * (v23 & 0x3F)];
    }
    v26 = *v14;
    v27 = v23 >> 6;
    if ( v25 == 1735162214 || v25 == 1819239265 )
    {
      if ( !v27 )
        v19 = 256;
    }
    else if ( v27 )
    {
      v19 = 256;
    }
    if ( !woff2::ReadBase128((woff2 *)&v74, (struct woff2::Buffer *)&v84, v7) )
      return 0;
    v28 = v84;
    v29 = v19 | v27;
    v83 = v84;
    if ( (v29 & 0x100) != 0 )
    {
      if ( !woff2::ReadBase128((woff2 *)&v74, (struct woff2::Buffer *)&v83, v7) )
        return 0;
      v28 = v83;
      if ( v25 == 1819239265 )
      {
        if ( v83 )
          return 0;
      }
    }
    if ( v20 + v28 < v20 )
      return 0;
    v19 = 0;
    v30 = (unsigned __int32 *)(v26 + 40 * i);
    v14 = v86;
    v30[2] = v20;
    ++i;
    v30[3] = v83;
    v20 += v83;
    *v30 = v25;
    v30[1] = v29;
    v30[4] = v83;
    v30[6] = v84;
    v6 = v75;
  }
  v31 = v85;
  v32 = *(_QWORD *)(v85 + 40);
  v33 = *(_DWORD *)(v32 - 32) + *(_DWORD *)(v32 - 28);
  *(_DWORD *)(v85 + 28) = v33;
  if ( v33 < *(_DWORD *)(v32 - 32) )
    return 0;
  v34 = *(_DWORD *)v31 == 1953784678;
  *(_DWORD *)(v31 + 4) = 0;
  if ( v34 )
  {
    v35 = v76 + 4;
    if ( v76 + 4 > v6 )
      return 0;
    v36 = _byteswap_ulong(*(_DWORD *)(v76 + v5));
    *(_DWORD *)(v31 + 4) = v36;
    v76 = v35;
    if ( ((v36 - 0x10000) & 0xFFFEFFFF) != 0
      || !woff2::Read255UShort((woff2 *)&v74, (struct woff2::Buffer *)&v84, (unsigned int *)v32)
      || !v84 )
    {
      return 0;
    }
    v37 = *(_QWORD **)(v31 + 64);
    v38 = (__int64 *)(v31 + 56);
    v39 = *(_QWORD *)(v31 + 56);
    v82 = (__int64 *)(v31 + 56);
    v32 = ((__int64)v37 - v39) / 40;
    if ( v84 >= v32 )
    {
      if ( v84 > (unsigned __int64)(((__int64)v37 - v39) / 40) )
      {
        if ( v84 <= (unsigned __int64)((*(_QWORD *)(v31 + 72) - v39) / 40) )
        {
          for ( j = v84 - v32; j; --j )
          {
            *v37 = 0;
            v37[1] = 0;
            v37[2] = 0;
            v37[3] = 0;
            v37[4] = 0;
            v37 += 5;
          }
          *(_QWORD *)(v31 + 64) = v37;
        }
        else
        {
          std::vector_woff2::_anonymous_namespace_::TtcFont_std::allocator_woff2::_anonymous_namespace_::TtcFont___::_Resize_reallocate_std::_Value_init_tag_(
            v31 + 56,
            v84,
            &v83);
        }
      }
    }
    else
    {
      v40 = (_QWORD *)(v39 + 40LL * v84);
      for ( k = v40; k != v37; k += 5 )
        CachedBitmapWriter::~CachedBitmapWriter((CachedBitmapWriter *)(k + 2));
      *(_QWORD *)(v31 + 64) = v40;
    }
    v43 = 0;
    LODWORD(v86) = 0;
    if ( v84 )
    {
      while ( 1 )
      {
        v44 = *v38;
        if ( !woff2::Read255UShort((woff2 *)&v74, (struct woff2::Buffer *)&v83, (unsigned int *)v32) )
          return 0;
        if ( !v83 )
          return 0;
        v32 = v76;
        if ( v76 + 4 > v75 )
          return 0;
        v45 = v44 + 40LL * v43;
        v46 = v45 + 16;
        *(_DWORD *)v45 = _byteswap_ulong(*(_DWORD *)(v76 + v74));
        v76 += 4;
        v47 = *(char **)(v45 + 24);
        v48 = *(_QWORD *)(v45 + 16);
        v49 = v83;
        v50 = (__int64)&v47[-v48] >> 1;
        if ( v83 < v50 )
          break;
        if ( v83 <= v50 )
          goto LABEL_84;
        v52 = (*(_QWORD *)(v45 + 32) - v48) >> 1;
        if ( v83 <= v52 )
        {
          v56 = 2 * (v83 - v50);
          memset_0(v47, 0, v56);
          v51 = &v47[v56];
          goto LABEL_83;
        }
        v53 = v52 >> 1;
        if ( v52 <= 0x7FFFFFFFFFFFFFFFLL - (v52 >> 1) )
        {
          v54 = v53 + v52;
          if ( v53 + v52 < v83 )
            v54 = v83;
        }
        else
        {
          v54 = 0x7FFFFFFFFFFFFFFFLL;
        }
        v55 = (char *)std::allocator<unsigned short>::allocate(v46, v54);
        memset_0(&v55[2 * v50], 0, 2 * (v49 - v50));
        memmove_0(v55, *(const void **)v46, *(_QWORD *)(v46 + 8) - *(_QWORD *)v46);
        std::vector<DWRITE_SHAPING_GLYPH_PROPERTIES>::_Change_array(v46, v55, v49, v54);
LABEL_84:
        v31 = v85;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        if ( v83 )
        {
          while ( woff2::Read255UShort((woff2 *)&v74, (struct woff2::Buffer *)&v77, (unsigned int *)v32)
               && (unsigned int)v77 < (unsigned __int64)((*(_QWORD *)(v31 + 40) - *v14) / 40) )
          {
            *(_WORD *)(*(_QWORD *)v46 + 2 * v59) = v77;
            v32 = *(unsigned int *)(*v14 + 40LL * (unsigned int)v77);
            if ( (_DWORD)v32 == 1819239265 )
            {
              v58 = v77;
            }
            else if ( (_DWORD)v32 == 1735162214 )
            {
              v57 = v77;
            }
            v59 = (unsigned int)(v59 + 1);
            if ( (unsigned int)v59 >= v83 )
            {
              if ( (v57 || v58) && (v57 > v58 || v58 - v57 != 1) )
              {
                v60 = __acrt_iob_func(2u);
                fprintf(v60, "TTC font %d has non-consecutive glyf/loca\n", (_DWORD)v86);
                return 0;
              }
              goto LABEL_96;
            }
          }
          return 0;
        }
LABEL_96:
        v43 = (_DWORD)v86 + 1;
        LODWORD(v86) = v43;
        if ( v43 >= v84 )
          goto LABEL_100;
        v38 = v82;
      }
      v51 = (char *)(v48 + 2LL * v83);
LABEL_83:
      *(_QWORD *)(v46 + 8) = v51;
      goto LABEL_84;
    }
  }
LABEL_100:
  v62 = (woff2 *)*(unsigned int *)(v31 + 4);
  if ( (_DWORD)v62 )
  {
    v63 = (*(_QWORD *)(v31 + 64) - *(_QWORD *)(v31 + 56)) / 40LL;
    v64 = woff2::CollectionHeaderSize(v62, v63, v32);
    v65 = *(_QWORD *)(v31 + 64);
    v66 = v64 + 12 * v63;
    for ( m = *(_QWORD *)(v31 + 56); m != v65; v66 += 16 * (v68 >> 1) )
    {
      v68 = *(_QWORD *)(m + 24) - *(_QWORD *)(m + 16);
      m += 40;
    }
  }
  else
  {
    v66 = 16LL * *(unsigned __int16 *)(v31 + 8) + 12;
  }
  v69 = v76;
  *(_QWORD *)(v31 + 16) = v76;
  if ( v69 > 0xFFFFFFFF )
    return 0;
  v70 = v69 + *(unsigned int *)(v31 + 24);
  if ( ~v70 >= 3 )
    v70 = (v70 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v70 > v4 )
  {
    v71 = __acrt_iob_func(2u);
    fprintf(v71, "offset fail; src_offset %llu length %lu dst_offset %llu\n", v70, v4, v66);
    return 0;
  }
  if ( v78 )
  {
    if ( v70 != v78 )
      return 0;
    v72 = v79 + v78;
    if ( ~(v79 + v78) >= 3 )
      v72 = (v72 + 3) & 0xFFFFFFFC;
    v70 = v72;
  }
  if ( v80 )
  {
    if ( v70 != v80 )
      return 0;
    v73 = v81 + v80;
    if ( ~(v81 + v80) >= 3 )
      v73 = (v73 + 3) & 0xFFFFFFFC;
    v70 = v73;
  }
  if ( ~v4 >= 3 )
    v4 = (v4 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  return v70 == v4;
}

```

## disassembly

```asm
0x180219060  mov     [rsp-40h+arg_10], r8
0x180219065  push    rbp
0x180219066  push    rbx
0x180219067  push    rsi
0x180219068  push    rdi
0x180219069  push    r12
0x18021906b  push    r13
0x18021906d  push    r14
0x18021906f  push    r15
0x180219071  mov     rbp, rsp
0x180219074  sub     rsp, 78h
0x180219078  mov     [rbp+var_48], rcx
0x18021907c  mov     r14, r8
0x18021907f  mov     [rbp+var_40], rdx
0x180219083  mov     r13, rdx
0x180219086  mov     r9, rcx
0x180219089  mov     r10, rdx
0x18021908c  cmp     rdx, 4
0x180219090  jb      loc_1802196FD
0x180219096  mov     eax, [rcx]
0x180219098  bswap   eax
0x18021909a  cmp     eax, 774F4632h
0x18021909f  jnz     loc_1802196FD
0x1802190a5  cmp     rdx, 8
0x1802190a9  jb      loc_1802196FD
0x1802190af  mov     eax, [rcx+4]
0x1802190b2  bswap   eax
0x1802190b4  mov     [r8], eax
0x1802190b7  cmp     rdx, 0Ch
0x1802190bb  jb      loc_1802196FD
0x1802190c1  mov     eax, [rcx+8]
0x1802190c4  bswap   eax
0x1802190c6  mov     eax, eax
0x1802190c8  cmp     rdx, rax
0x1802190cb  jnz     loc_1802196FD
0x1802190d1  cmp     rdx, 0Eh
0x1802190d5  jb      loc_1802196FD
0x1802190db  movzx   r8d, word ptr [rcx+0Ch]
0x1802190e0  ror     r8w, 8
0x1802190e5  mov     [r14+8], r8w
0x1802190ea  test    r8w, r8w
0x1802190ee  jz      loc_1802196FD
0x1802190f4  cmp     rdx, 14h
0x1802190f8  jb      loc_1802196FD
0x1802190fe  lea     rax, [rdx-6]
0x180219102  cmp     rax, 0Eh
0x180219106  jb      loc_1802196FD
0x18021910c  cmp     rdx, 18h
0x180219110  jb      loc_1802196FD
0x180219116  mov     eax, [rcx+14h]
0x180219119  bswap   eax
0x18021911b  mov     [r14+18h], eax
0x18021911f  cmp     rdx, 1Ch
0x180219123  jb      loc_1802196FD
0x180219129  lea     rax, [rdx-4]
0x18021912d  cmp     rax, 18h
0x180219131  jb      loc_1802196FD
0x180219137  cmp     rdx, 20h ; ' '
0x18021913b  jb      loc_1802196FD
0x180219141  mov     eax, [rcx+1Ch]
0x180219144  bswap   eax
0x180219146  mov     [rbp+var_28], eax
0x180219149  cmp     rdx, 24h ; '$'
0x18021914d  jb      loc_1802196FD
0x180219153  mov     edx, [rcx+20h]
0x180219156  bswap   edx
0x180219158  mov     [rbp+var_24], edx
0x18021915b  cmp     r10, 28h ; '('
0x18021915f  jb      loc_1802196FD
0x180219165  test    eax, eax
0x180219167  jz      short loc_180219185
0x180219169  mov     eax, eax
0x18021916b  cmp     rax, r10
0x18021916e  jnb     loc_1802196FD
0x180219174  mov     rcx, r10
0x180219177  sub     rcx, rax
0x18021917a  mov     eax, edx
0x18021917c  cmp     rcx, rax
0x18021917f  jb      loc_1802196FD
0x180219185  cmp     r13, 2Ch ; ','
0x180219189  jb      loc_1802196FD
0x18021918f  mov     eax, [r9+28h]
0x180219193  bswap   eax
0x180219195  mov     [rbp+var_20], eax
0x180219198  cmp     r13, 30h ; '0'
0x18021919c  jb      loc_1802196FD
0x1802191a2  mov     edx, [r9+2Ch]
0x1802191a6  mov     [rbp+var_38], 30h ; '0'
0x1802191ae  bswap   edx
0x1802191b0  mov     [rbp+var_1C], edx
0x1802191b3  test    eax, eax
0x1802191b5  jz      short loc_1802191D3
0x1802191b7  mov     eax, eax
0x1802191b9  cmp     rax, r13
0x1802191bc  jnb     loc_1802196FD
0x1802191c2  mov     rcx, r13
0x1802191c5  sub     rcx, rax
0x1802191c8  mov     eax, edx
0x1802191ca  cmp     rcx, rax
0x1802191cd  jb      loc_1802196FD
0x1802191d3  mov     rdi, [r14+28h]
0x1802191d7  lea     r12, [r14+20h]
0x1802191db  mov     rsi, [r12]
0x1802191df  mov     rcx, rdi
0x1802191e2  sub     rcx, rsi
0x1802191e5  movzx   ebx, r8w
0x1802191e9  mov     r15, 6666666666666667h
0x1802191f3  mov     [rbp+arg_18], r12
0x1802191f7  mov     rax, r15
0x1802191fa  imul    rcx
0x1802191fd  mov     r11, rdx
0x180219200  sar     r11, 4
0x180219204  mov     rax, r11
0x180219207  shr     rax, 3Fh
0x18021920b  add     r11, rax
0x18021920e  cmp     rbx, r11
0x180219211  jnb     short loc_180219222
0x180219213  lea     rax, [rbx+rbx*4]
0x180219217  lea     rcx, [rsi+rax*8]
0x18021921b  mov     [r12+8], rcx
0x180219220  jmp     short loc_18021928C
0x180219222  jbe     short loc_18021928C
0x180219224  mov     rcx, [r12+10h]
0x180219229  mov     rax, r15
0x18021922c  sub     rcx, rsi
0x18021922f  imul    rcx
0x180219232  sar     rdx, 4
0x180219236  mov     rax, rdx
0x180219239  shr     rax, 3Fh
0x18021923d  add     rdx, rax
0x180219240  cmp     rbx, rdx
0x180219243  jbe     short loc_18021925E
0x180219245  lea     r8, [rbp+arg_0]
0x180219249  mov     rdx, rbx
0x18021924c  mov     rcx, r12
0x18021924f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UTable@woff2@@V?$allocator@UTable@woff2@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<woff2::Table>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180219254  mov     r10, [rbp+var_40]
0x180219258  mov     r9, [rbp+var_48]
0x18021925c  jmp     short loc_18021928C
0x18021925e  sub     rbx, r11
0x180219261  jz      short loc_180219287
0x180219263  lea     r8, [rbx+rbx*4]
0x180219267  xor     dl, dl; Val
0x180219269  shl     r8, 3; Size
0x18021926d  mov     rcx, rdi; void *
0x180219270  call    memset_0
0x180219275  add     rdi, 28h ; '('
0x180219279  sub     rbx, 1
0x18021927d  jnz     short loc_180219275
0x18021927f  mov     r10, [rbp+var_40]
0x180219283  mov     r9, [rbp+var_48]
0x180219287  mov     [r12+8], rdi
0x18021928c  movzx   eax, word ptr [r14+8]
0x180219291  xor     esi, esi
0x180219293  mov     [rbp+var_30], rax
0x180219297  mov     r14d, esi
0x18021929a  mov     r15d, esi
0x18021929d  test    rax, rax
0x1802192a0  jz      loc_1802193B7
0x1802192a6  mov     rax, [rbp+var_38]
0x1802192aa  lea     rdx, ?kKnownTags@woff2@@3QBIB; "pamcdaehaehhxtmhpxameman2/SOtsop tvcmgp"...
0x1802192b1  mov     ecx, 100h
0x1802192b6  lea     rdi, [rax+1]
0x1802192ba  cmp     rdi, r10
0x1802192bd  ja      loc_1802196FD
0x1802192c3  movzx   ebx, byte ptr [rax+r9]
0x1802192c8  movzx   eax, bl
0x1802192cb  mov     [rbp+var_38], rdi
0x1802192cf  and     al, 3Fh
0x1802192d1  cmp     al, 3Fh ; '?'
0x1802192d3  jnz     short loc_1802192EE
0x1802192d5  lea     rax, [rdi+4]
0x1802192d9  cmp     rax, r10
0x1802192dc  ja      loc_1802196FD
0x1802192e2  mov     edi, [rdi+r9]
0x1802192e6  bswap   edi
0x1802192e8  mov     [rbp+var_38], rax
0x1802192ec  jmp     short loc_1802192F7
0x1802192ee  mov     rax, rbx
0x1802192f1  and     eax, 3Fh
0x1802192f4  mov     edi, [rdx+rax*4]
0x1802192f7  mov     r12, [r12]
0x1802192fb  shr     bl, 6
0x1802192fe  cmp     edi, 676C7966h
0x180219304  jz      short loc_180219316
0x180219306  cmp     edi, 6C6F6361h
0x18021930c  jz      short loc_180219316
0x18021930e  test    bl, bl
0x180219310  jz      short loc_18021931B
0x180219312  mov     esi, ecx
0x180219314  jmp     short loc_18021931B
0x180219316  test    bl, bl
0x180219318  cmovz   esi, ecx
0x18021931b  lea     rdx, [rbp+arg_8]; struct woff2::Buffer *
0x18021931f  lea     rcx, [rbp+var_48]; this
0x180219323  call    ?ReadBase128@woff2@@YA_NPEAVBuffer@1@PEAI@Z; woff2::ReadBase128(woff2::Buffer *,uint *)
0x180219328  test    al, al
0x18021932a  jz      loc_1802196FD
0x180219330  mov     eax, [rbp+arg_8]
0x180219333  movzx   ebx, bl
0x180219336  or      ebx, esi
0x180219338  mov     [rbp+arg_0], eax
0x18021933b  bt      ebx, 8
0x18021933f  jnb     short loc_180219369
0x180219341  lea     rdx, [rbp+arg_0]; struct woff2::Buffer *
0x180219345  lea     rcx, [rbp+var_48]; this
0x180219349  call    ?ReadBase128@woff2@@YA_NPEAVBuffer@1@PEAI@Z; woff2::ReadBase128(woff2::Buffer *,uint *)
0x18021934e  test    al, al
0x180219350  jz      loc_1802196FD
0x180219356  mov     eax, [rbp+arg_0]
0x180219359  cmp     edi, 6C6F6361h
0x18021935f  jnz     short loc_180219369
0x180219361  test    eax, eax
0x180219363  jnz     loc_1802196FD
0x180219369  add     eax, r14d
0x18021936c  cmp     eax, r14d
0x18021936f  jb      loc_1802196FD
0x180219375  lea     rax, [r15+r15*4]
0x180219379  xor     esi, esi
0x18021937b  lea     rcx, [r12+rax*8]
0x18021937f  mov     r12, [rbp+arg_18]
0x180219383  mov     [rcx+8], r14d
0x180219387  inc     r15
0x18021938a  mov     eax, [rbp+arg_0]
0x18021938d  mov     [rcx+0Ch], eax
0x180219390  add     r14d, [rbp+arg_0]
0x180219394  mov     [rcx], edi
0x180219396  mov     [rcx+4], ebx
0x180219399  mov     eax, [rbp+arg_0]
0x18021939c  mov     [rcx+10h], eax
0x18021939f  mov     eax, [rbp+arg_8]
0x1802193a2  mov     [rcx+18h], eax
0x1802193a5  mov     r10, [rbp+var_40]
0x1802193a9  mov     r9, [rbp+var_48]
0x1802193ad  cmp     r15, [rbp+var_30]
0x1802193b1  jb      loc_1802192A6
0x1802193b7  mov     r14, [rbp+arg_10]
0x1802193bb  mov     r8, [r14+28h]; unsigned int
0x1802193bf  mov     edx, [r8-1Ch]
0x1802193c3  add     edx, [r8-20h]
0x1802193c7  mov     [r14+1Ch], edx
0x1802193cb  cmp     edx, [r8-20h]
0x1802193cf  jb      loc_1802196FD
0x1802193d5  cmp     dword ptr [r14], 74746366h
0x1802193dc  mov     [r14+4], esi
0x1802193e0  jnz     loc_180219710
0x1802193e6  mov     rax, [rbp+var_38]
0x1802193ea  lea     rcx, [rax+4]
0x1802193ee  cmp     rcx, r10
0x1802193f1  ja      loc_1802196FD
0x1802193f7  mov     eax, [rax+r9]
0x1802193fb  bswap   eax
0x1802193fd  mov     [r14+4], eax
0x180219401  add     eax, 0FFFF0000h
0x180219406  mov     [rbp+var_38], rcx
0x18021940a  test    eax, 0FFFEFFFFh
0x18021940f  jnz     loc_1802196FD
0x180219415  lea     rdx, [rbp+arg_8]; struct woff2::Buffer *
0x180219419  lea     rcx, [rbp+var_48]; this
0x18021941d  call    ?Read255UShort@woff2@@YA_NPEAVBuffer@1@PEAI@Z; woff2::Read255UShort(woff2::Buffer *,uint *)
0x180219422  test    al, al
0x180219424  jz      loc_1802196FD
0x18021942a  mov     eax, [rbp+arg_8]
0x18021942d  test    eax, eax
0x18021942f  jz      loc_1802196FD
0x180219435  mov     rbx, [r14+40h]
0x180219439  lea     r15, [r14+38h]
0x18021943d  mov     r10, [r15]
0x180219440  mov     r9d, eax
0x180219443  mov     rcx, rbx
0x180219446  mov     [rbp+var_18], r15
0x18021944a  sub     rcx, r10
0x18021944d  mov     r11, 6666666666666667h
0x180219457  mov     rax, r11
0x18021945a  imul    rcx
0x18021945d  mov     r8, rdx
0x180219460  sar     r8, 4
0x180219464  mov     rax, r8
0x180219467  shr     rax, 3Fh
0x18021946b  add     r8, rax; unsigned int *
0x18021946e  cmp     r9, r8
0x180219471  jnb     short loc_18021949D
0x180219473  lea     rax, [r9+r9*4]
0x180219477  lea     rsi, [r10+rax*8]
0x18021947b  mov     rdi, rsi
0x18021947e  cmp     rsi, rbx
0x180219481  jz      short loc_180219495
0x180219483  lea     rcx, [rdi+10h]; this
0x180219487  call    ??1CachedBitmapWriter@@QEAA@XZ; CachedBitmapWriter::~CachedBitmapWriter(void)
0x18021948c  add     rdi, 28h ; '('
0x180219490  cmp     rdi, rbx
0x180219493  jnz     short loc_180219483
0x180219495  mov     [r15+8], rsi
0x180219499  xor     esi, esi
0x18021949b  jmp     short loc_180219501
0x18021949d  jbe     short loc_180219501
0x18021949f  mov     rcx, [r15+10h]
0x1802194a3  mov     rax, r11
0x1802194a6  sub     rcx, r10
0x1802194a9  imul    rcx
  ... truncated ...
```
