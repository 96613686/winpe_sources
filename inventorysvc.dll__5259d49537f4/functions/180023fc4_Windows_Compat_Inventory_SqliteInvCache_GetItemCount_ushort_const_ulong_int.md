# Windows::Compat::Inventory::SqliteInvCache::GetItemCount(ushort const *,ulong &,int)

- ea: `0x180023fc4`
- end: `0x18002459a`
- name: `?GetItemCount@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAKH@Z`
- size: `1494`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800264ec`

## callees

- `0x180002bf0`
- `0x180005477`
- `0x180005483`
- `0x18000698c`
- `0x180006a04`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f3b4`
- `0x18001f4a4`
- `0x18001f558`
- `0x180023fc4`
- `0x180028c48`
- `0x18002e028`
- `0x180067f5c`
- `0x1800817cc`
- `0x18009f8e0`
- `0x18009f9e0`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180024385`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180024385`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002436e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002436e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024346`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800244f7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024346`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800244f7`

## string_xrefs

- `0x1800242b2`: `OpenDb failed [%#x]`
- `0x1800242bf`: `Windows::Compat::Inventory::SqliteInvCache::GetItemCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::GetItemCount(
        const unsigned __int16 *a1,
        unsigned int *a2)
{
  __int64 v3; // r14
  __int64 v4; // r8
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // r15
  __int64 v9; // rdi
  __int128 *v10; // r9
  void **v11; // rdx
  void *v12; // rdi
  size_t v13; // rbx
  void **v14; // rdx
  __int64 v15; // rcx
  char *v16; // rdi
  void **v17; // rdx
  size_t v18; // rbx
  void **v19; // rdx
  __int64 v20; // r15
  int v21; // eax
  unsigned int v22; // ebx
  struct sqlite3 *v23; // r13
  _QWORD *v24; // rdx
  int v25; // eax
  int v26; // edi
  int i; // r12d
  int v28; // esi
  const wchar_t *v29; // rax
  wchar_t *v30; // rax
  int v31; // eax
  int v32; // ebx
  _WORD *v33; // r9
  unsigned int v34; // edi
  __int64 v35; // rdx
  __int64 v36; // rax
  _QWORD *v37; // rdx
  int v38; // eax
  int v39; // edi
  unsigned int v40; // eax
  __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  struct sqlite3 *v44; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v45; // [rsp+48h] [rbp-B8h]
  void *Src[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  __int128 v48; // [rsp+70h] [rbp-90h] BYREF
  __m128i v49; // [rsp+80h] [rbp-80h]
  void *v50[2]; // [rsp+90h] [rbp-70h] BYREF
  __m128i v51; // [rsp+A0h] [rbp-60h]
  _QWORD v52[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v53[9]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v54[6]; // [rsp+11Ah] [rbp+1Ah] BYREF

  v45 = a2;
  v44 = 0;
  *(_OWORD *)Src = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(Src, L"SELECT COUNT(*) FROM ", 21);
  std::operator+<unsigned short>(v52, Src, a1);
  std::wstring::~wstring(Src);
  v3 = 0;
  v43 = 0;
  *(_OWORD *)Src = 0;
  si128 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  std::wstring::_Construct<1,unsigned short const *>(Src, a1, v4);
  *(_OWORD *)v50 = 0;
  v51 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    v50,
    L"SELECT name FROM sqlite_master WHERE type = 'table' AND name LIKE '",
    67);
  v48 = 0;
  v49 = 0;
  v5 = v51.m128i_i64[0];
  v6 = si128.m128i_i64[0];
  v7 = v51.m128i_u64[1];
  v8 = si128.m128i_u64[1];
  v9 = v51.m128i_i64[0] + si128.m128i_i64[0];
  v42 = v51.m128i_i64[0] + si128.m128i_i64[0];
  if ( si128.m128i_i64[0] > (unsigned __int64)(v51.m128i_i64[1] - v51.m128i_i64[0])
    || si128.m128i_i64[1] > (unsigned __int64)v51.m128i_i64[1] )
  {
    if ( v51.m128i_i64[0] > (unsigned __int64)(si128.m128i_i64[1] - si128.m128i_i64[0]) )
    {
      v15 = 0x7FFFFFFFFFFFFFFELL;
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v51.m128i_i64[0]) < si128.m128i_i64[0] )
        std::_Xlen_string();
      if ( (v9 | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v15 = v9 | 7;
        if ( (v9 | 7uLL) < 0xA )
          v15 = 10;
      }
      v42 = v15;
      v16 = (char *)std::wstring::_Allocate_for_capacity<0>(v15, &v42);
      *(_QWORD *)&v48 = v16;
      v49.m128i_i64[0] = v5 + v6;
      v49.m128i_i64[1] = v42;
      v17 = v50;
      if ( v7 > 7 )
        v17 = (void **)v50[0];
      v18 = 2 * v5;
      memcpy_0(v16, v17, v18);
      v19 = Src;
      if ( v8 > 7 )
        v19 = (void **)Src[0];
      memcpy_0(&v16[v18], v19, 2 * v6 + 2);
    }
    else
    {
      v48 = *(_OWORD *)Src;
      v49 = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src[0]) = 0;
      v12 = (void *)v48;
      v13 = 2 * v51.m128i_i64[0];
      memmove_0((void *)(v48 + 2 * v51.m128i_i64[0]), (const void *)v48, 2 * v6 + 2);
      v14 = v50;
      if ( v7 > 7 )
        v14 = (void **)v50[0];
      memcpy_0(v12, v14, v13);
      v49.m128i_i64[0] = v42;
    }
  }
  else
  {
    v48 = *(_OWORD *)v50;
    v49 = v51;
    v51 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v50[0]) = 0;
    v10 = &v48;
    if ( _mm_srli_si128(v49, 8).m128i_u64[0] > 7 )
      v10 = (__int128 *)v48;
    v11 = Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (void **)Src[0];
    memcpy_0((char *)v10 + 2 * v5, v11, 2 * si128.m128i_i64[0] + 2);
    v49.m128i_i64[0] = v9;
  }
  std::operator+<unsigned short>(v53, &v48, L"%';");
  std::wstring::~wstring(&v48);
  std::wstring::~wstring(v50);
  std::wstring::~wstring(Src);
  v20 = 0;
  v42 = 0;
  *v45 = 0;
  v21 = Windows::Compat::Inventory::SqliteInvCache::OpenDb(a1, &v44, 0);
  v22 = v21;
  v23 = v44;
  if ( v21 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::GetItemCount", 801, "OpenDb failed [%#x]", v21);
    goto LABEL_67;
  }
  v42 = 0;
  v24 = v53;
  if ( v53[3] > 7u )
    LODWORD(v24) = v53[0];
  v25 = sqlite3Prepare16((_DWORD)v44, (_DWORD)v24, -1, 128, (__int64)&v42, 0);
  if ( v25 )
  {
    if ( v25 > 0 )
      v22 = (unsigned __int16)v25 | 0x80070000;
    else
      v22 = v25;
    v20 = v42;
    goto LABEL_67;
  }
  v26 = -1;
  v20 = v42;
  while ( 1 )
  {
    for ( i = 0; i < 100; ++i )
    {
      v28 = sqlite3_step(v20);
      if ( (unsigned int)(v28 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v28 != 100 )
      break;
    v29 = (const wchar_t *)sqlite3_column_text16(v20, 0);
    v30 = wcsstr(v29, L"_");
    if ( v30 )
    {
      v31 = wcstol(v30 + 1, 0, 10);
      if ( v31 > v26 )
        v26 = v31;
    }
  }
  if ( v28 != 101 )
  {
    if ( v28 > 0 )
    {
      v32 = (unsigned __int16)v28;
      goto LABEL_43;
    }
LABEL_45:
    v22 = v28;
    goto LABEL_67;
  }
  v28 = 0;
  if ( v26 == -1 )
    goto LABEL_45;
  v33 = v54;
  if ( v26 >= 0 )
  {
    do
    {
      *--v33 = v26 % 0xAu + 48;
      v26 /= 0xAu;
    }
    while ( v26 );
  }
  else
  {
    v34 = -v26;
    do
    {
      *--v33 = v34 % 0xA + 48;
      v34 /= 0xAu;
    }
    while ( v34 );
    *--v33 = 45;
  }
  std::wstring::wstring(Src, v33, v54);
  v36 = std::operator+<unsigned short>(&v48, v35, Src);
  std::operator+<unsigned short>(v50, v36, L";");
  std::wstring::append(v52);
  std::wstring::~wstring(v50);
  std::wstring::~wstring(&v48);
  std::wstring::~wstring(Src);
  v43 = 0;
  v37 = v52;
  if ( v52[3] > 7u )
    LODWORD(v37) = v52[0];
  v38 = sqlite3Prepare16((_DWORD)v23, (_DWORD)v37, -1, 128, (__int64)&v43, 0);
  if ( !v38 )
  {
    v3 = v43;
    if ( !v43 )
    {
      v22 = -2147467259;
      goto LABEL_67;
    }
    do
    {
      v39 = sqlite3_step(v3);
      if ( (unsigned int)(v39 - 5) > 1 )
        break;
      Sleep(5u);
      ++v28;
    }
    while ( v28 < 100 );
    if ( v39 == 100 )
    {
      v40 = sqlite3_column_int(v3, 0);
      *v45 = v40;
      goto LABEL_67;
    }
    if ( v39 <= 0 )
    {
      v22 = v39;
      goto LABEL_67;
    }
    v32 = (unsigned __int16)v39;
LABEL_43:
    v22 = v32 | 0x80070000;
    goto LABEL_67;
  }
  if ( v38 > 0 )
    v22 = (unsigned __int16)v38 | 0x80070000;
  else
    v22 = v38;
  v3 = v43;
LABEL_67:
  sqlite3Close(v23, 0);
  if ( v20 )
    sqlite3_finalize(v20);
  std::wstring::~wstring(v53);
  if ( v3 )
    sqlite3_finalize(v3);
  std::wstring::~wstring(v52);
  return v22;
}

```

## disassembly

```asm
0x180023fc4  mov     [rsp-8+arg_10], rbx
0x180023fc9  push    rbp
0x180023fca  push    rsi
0x180023fcb  push    rdi
0x180023fcc  push    r12
0x180023fce  push    r13
0x180023fd0  push    r14
0x180023fd2  push    r15
0x180023fd4  lea     rbp, [rsp-30h]
0x180023fd9  sub     rsp, 130h
0x180023fe0  mov     rax, cs:__security_cookie
0x180023fe7  xor     rax, rsp
0x180023fea  mov     [rbp+60h+var_40], rax
0x180023fee  mov     [rsp+160h+var_118], rdx
0x180023ff3  mov     r12, rcx
0x180023ff6  xor     ebx, ebx
0x180023ff8  mov     [rsp+160h+var_120], rbx
0x180023ffd  xorps   xmm0, xmm0
0x180024000  movups  xmmword ptr [rsp+160h+Src], xmm0
0x180024005  xorps   xmm1, xmm1
0x180024008  movdqu  [rsp+160h+var_100], xmm1
0x18002400e  lea     r8d, [rbx+15h]
0x180024012  lea     rdx, aSelectCountFro; "SELECT COUNT(*) FROM "
0x180024019  lea     rcx, [rsp+160h+Src]
0x18002401e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024023  nop
0x180024024  mov     r8, r12
0x180024027  lea     rdx, [rsp+160h+Src]
0x18002402c  lea     rcx, [rbp+60h+var_B0]
0x180024030  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180024035  nop
0x180024036  lea     rcx, [rsp+160h+Src]; void *
0x18002403b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024040  mov     r14d, ebx
0x180024043  mov     [rsp+160h+var_128], rbx
0x180024048  xorps   xmm0, xmm0
0x18002404b  movups  xmmword ptr [rsp+160h+Src], xmm0
0x180024050  xorps   xmm1, xmm1
0x180024053  movdqu  [rsp+160h+var_100], xmm1
0x180024059  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002405d  inc     r8
0x180024060  cmp     [r12+r8*2], bx
0x180024065  jnz     short loc_18002405D
0x180024067  mov     rdx, r12
0x18002406a  lea     rcx, [rsp+160h+Src]
0x18002406f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024074  nop
0x180024075  xorps   xmm0, xmm0
0x180024078  movups  xmmword ptr [rbp+60h+var_D0], xmm0
0x18002407c  xorps   xmm1, xmm1
0x18002407f  movdqu  [rbp+60h+var_C0], xmm1
0x180024084  mov     r8d, 43h ; 'C'
0x18002408a  lea     rdx, aSelectNameFrom; "SELECT name FROM sqlite_master WHERE ty"...
0x180024091  lea     rcx, [rbp+60h+var_D0]
0x180024095  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002409a  nop
0x18002409b  xorps   xmm0, xmm0
0x18002409e  movups  [rsp+160h+var_F0], xmm0
0x1800240a3  xorps   xmm1, xmm1
0x1800240a6  movdqu  [rbp+60h+var_E0], xmm1
0x1800240ab  mov     rbx, qword ptr [rbp+60h+var_C0]
0x1800240af  mov     rsi, qword ptr [rsp+160h+var_100]
0x1800240b4  mov     r13, qword ptr [rbp+60h+var_C0+8]
0x1800240b8  mov     r15, qword ptr [rsp+160h+var_100+8]
0x1800240bd  lea     rdi, [rbx+rsi]
0x1800240c1  mov     [rsp+160h+var_130], rdi
0x1800240c6  mov     rax, r13
0x1800240c9  sub     rax, rbx
0x1800240cc  mov     edx, 0Ah
0x1800240d1  cmp     rsi, rax
0x1800240d4  ja      short loc_180024145
0x1800240d6  cmp     r15, r13
0x1800240d9  ja      short loc_180024145
0x1800240db  movups  xmm1, xmmword ptr [rbp+60h+var_D0]
0x1800240df  movups  [rsp+160h+var_F0], xmm1
0x1800240e4  movups  xmm2, [rbp+60h+var_C0]
0x1800240e8  movdqu  [rbp+60h+var_E0], xmm2
0x1800240ed  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800240f5  movdqu  [rbp+60h+var_C0], xmm0
0x1800240fa  xor     eax, eax
0x1800240fc  mov     word ptr [rbp+60h+var_D0], ax
0x180024100  lea     r9, [rsp+160h+var_F0]
0x180024105  movq    rcx, xmm1
0x18002410a  psrldq  xmm2, 8
0x18002410f  movq    rax, xmm2
0x180024114  cmp     rax, 7
0x180024118  cmova   r9, rcx
0x18002411c  lea     rdx, [rsp+160h+Src]
0x180024121  cmp     r15, 7
0x180024125  cmova   rdx, [rsp+160h+Src]; Src
0x18002412b  lea     r8, ds:2[rsi*2]; Size
0x180024133  lea     rcx, [r9+rbx*2]; void *
0x180024137  call    memcpy_0
0x18002413c  mov     qword ptr [rbp+60h+var_E0], rdi
0x180024140  jmp     loc_18002424D
0x180024145  mov     rax, r15
0x180024148  sub     rax, rsi
0x18002414b  cmp     rbx, rax
0x18002414e  ja      short loc_1800241BA
0x180024150  movups  xmm2, xmmword ptr [rsp+160h+Src]
0x180024155  movups  [rsp+160h+var_F0], xmm2
0x18002415a  movups  xmm0, [rsp+160h+var_100]
0x18002415f  movups  [rbp+60h+var_E0], xmm0
0x180024163  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002416b  movdqu  [rsp+160h+var_100], xmm1
0x180024171  xor     eax, eax
0x180024173  mov     word ptr [rsp+160h+Src], ax
0x180024178  movq    rdi, xmm2
0x18002417d  add     rbx, rbx
0x180024180  lea     r8, ds:2[rsi*2]; Size
0x180024188  lea     rcx, [rdi+rbx]; void *
0x18002418c  mov     rdx, rdi; Src
0x18002418f  call    memmove_0
0x180024194  lea     rdx, [rbp+60h+var_D0]
0x180024198  cmp     r13, 7
0x18002419c  cmova   rdx, [rbp+60h+var_D0]; Src
0x1800241a1  mov     r8, rbx; Size
0x1800241a4  mov     rcx, rdi; void *
0x1800241a7  call    memcpy_0
0x1800241ac  mov     rax, [rsp+160h+var_130]
0x1800241b1  mov     qword ptr [rbp+60h+var_E0], rax
0x1800241b5  jmp     loc_18002424D
0x1800241ba  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800241c4  mov     rax, rcx
0x1800241c7  sub     rax, rbx
0x1800241ca  cmp     rax, rsi
0x1800241cd  jb      loc_180024594
0x1800241d3  mov     rax, rdi
0x1800241d6  or      rax, 7
0x1800241da  cmp     rax, rcx
0x1800241dd  ja      short loc_1800241E9
0x1800241df  mov     rcx, rax
0x1800241e2  cmp     rax, rdx
0x1800241e5  cmovb   rcx, rdx
0x1800241e9  mov     [rsp+160h+var_130], rcx
0x1800241ee  lea     rdx, [rsp+160h+var_130]
0x1800241f3  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800241f8  mov     rdi, rax
0x1800241fb  mov     qword ptr [rsp+160h+var_F0], rax
0x180024200  lea     rax, [rbx+rsi]
0x180024204  mov     qword ptr [rbp+60h+var_E0], rax
0x180024208  mov     rcx, [rsp+160h+var_130]
0x18002420d  mov     qword ptr [rbp+60h+var_E0+8], rcx
0x180024211  lea     rdx, [rbp+60h+var_D0]
0x180024215  cmp     r13, 7
0x180024219  cmova   rdx, [rbp+60h+var_D0]; Src
0x18002421e  add     rbx, rbx
0x180024221  mov     r8, rbx; Size
0x180024224  mov     rcx, rdi; void *
0x180024227  call    memcpy_0
0x18002422c  lea     rdx, [rsp+160h+Src]
0x180024231  cmp     r15, 7
0x180024235  cmova   rdx, [rsp+160h+Src]; Src
0x18002423b  lea     r8, ds:2[rsi*2]; Size
0x180024243  lea     rcx, [rdi+rbx]; void *
0x180024247  call    memcpy_0
0x18002424c  nop
0x18002424d  lea     r8, asc_1800DB7E8; "%';"
0x180024254  lea     rdx, [rsp+160h+var_F0]
0x180024259  lea     rcx, [rbp+60h+var_90]
0x18002425d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180024262  nop
0x180024263  lea     rcx, [rsp+160h+var_F0]; void *
0x180024268  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002426d  nop
0x18002426e  lea     rcx, [rbp+60h+var_D0]; void *
0x180024272  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024277  nop
0x180024278  lea     rcx, [rsp+160h+Src]; void *
0x18002427d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024282  xor     esi, esi
0x180024284  mov     r15d, esi
0x180024287  mov     [rsp+160h+var_130], rsi
0x18002428c  mov     rax, [rsp+160h+var_118]
0x180024291  mov     [rax], esi
0x180024293  xor     r8d, r8d; int
0x180024296  lea     rdx, [rsp+160h+var_120]; struct sqlite3 **
0x18002429b  mov     rcx, r12; unsigned __int16 *
0x18002429e  call    ?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z; Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)
0x1800242a3  mov     ebx, eax
0x1800242a5  mov     r13, [rsp+160h+var_120]
0x1800242aa  test    eax, eax
0x1800242ac  jns     short loc_1800242D3
0x1800242ae  mov     dword ptr [rsp+160h+var_140], eax
0x1800242b2  lea     r9, aOpendbFailedX; "OpenDb failed [%#x]"
0x1800242b9  mov     r8d, 321h
0x1800242bf  lea     rdx, aWindowsCompatI_24; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800242c6  lea     ecx, [rsi+1]
0x1800242c9  call    AslLogCallPrintf
0x1800242ce  jmp     loc_180024531
0x1800242d3  mov     [rsp+160h+var_130], rsi
0x1800242d8  lea     rdx, [rbp+60h+var_90]
0x1800242dc  cmp     [rbp+60h+var_78], 7
0x1800242e1  cmova   rdx, [rbp+60h+var_90]
0x1800242e6  mov     [rsp+160h+var_138], rsi
0x1800242eb  lea     rax, [rsp+160h+var_130]
0x1800242f0  mov     [rsp+160h+var_140], rax
0x1800242f5  mov     r9d, 80h
0x1800242fb  or      r8d, 0FFFFFFFFh
0x1800242ff  mov     rcx, r13
0x180024302  call    sqlite3Prepare16
0x180024307  test    eax, eax
0x180024309  jz      short loc_180024324
0x18002430b  jg      short loc_180024311
0x18002430d  mov     ebx, eax
0x18002430f  jmp     short loc_18002431A
0x180024311  movzx   ebx, ax
0x180024314  or      ebx, 80070000h
0x18002431a  mov     r15, [rsp+160h+var_130]
0x18002431f  jmp     loc_180024531
0x180024324  or      edi, 0FFFFFFFFh
0x180024327  mov     r15, [rsp+160h+var_130]
0x18002432c  mov     r12d, esi
0x18002432f  mov     rcx, r15
0x180024332  call    sqlite3_step
0x180024337  mov     esi, eax
0x180024339  lea     ecx, [rax-5]
0x18002433c  cmp     ecx, 1
0x18002433f  ja      short loc_180024355
0x180024341  mov     ecx, 5; dwMilliseconds
0x180024346  call    cs:__imp_Sleep
0x18002434c  inc     r12d
0x18002434f  cmp     r12d, 64h ; 'd'
0x180024353  jl      short loc_18002432F
0x180024355  cmp     esi, 64h ; 'd'
0x180024358  jnz     short loc_180024393
0x18002435a  xor     edx, edx
0x18002435c  mov     rcx, r15
0x18002435f  call    sqlite3_column_text16
0x180024364  lea     rdx, asc_1800DC264; "_"
0x18002436b  mov     rcx, rax; Str
0x18002436e  call    cs:__imp_wcsstr
0x180024374  xor     esi, esi
0x180024376  test    rax, rax
0x180024379  jz      short loc_18002432C
0x18002437b  lea     rcx, [rax+2]; String
0x18002437f  xor     edx, edx; EndPtr
0x180024381  lea     r8d, [rsi+0Ah]; Radix
0x180024385  call    cs:__imp_wcstol
0x18002438b  cmp     eax, edi
0x18002438d  jle     short loc_18002432C
0x18002438f  mov     edi, eax
0x180024391  jmp     short loc_18002432C
0x180024393  cmp     esi, 65h ; 'e'
0x180024396  jz      short loc_1800243AA
0x180024398  test    esi, esi
0x18002439a  jle     short loc_1800243B1
0x18002439c  movzx   ebx, si
0x18002439f  or      ebx, 80070000h
0x1800243a5  jmp     loc_180024531
0x1800243aa  xor     esi, esi
0x1800243ac  cmp     edi, 0FFFFFFFFh
0x1800243af  jnz     short loc_1800243B8
0x1800243b1  mov     ebx, esi
0x1800243b3  jmp     loc_180024531
0x1800243b8  lea     r9, [rbp+60h+var_46]
0x1800243bc  test    edi, edi
0x1800243be  jns     short loc_1800243FA
0x1800243c0  neg     edi
0x1800243c2  sub     r9, 2
0x1800243c6  mov     eax, 0CCCCCCCDh
0x1800243cb  mul     edi
0x1800243cd  shr     edx, 3
0x1800243d0  movzx   eax, dx
0x1800243d3  shl     ax, 2
0x1800243d7  lea     ecx, [rax+rdx]
0x1800243da  add     cx, cx
0x1800243dd  sub     di, cx
0x1800243e0  add     di, 30h ; '0'
0x1800243e4  mov     [r9], di
0x1800243e8  mov     edi, edx
0x1800243ea  test    edx, edx
0x1800243ec  jnz     short loc_1800243C2
0x1800243ee  add     r9, 0FFFFFFFFFFFFFFFEh
0x1800243f2  mov     word ptr [r9], 2Dh ; '-'
0x1800243f8  jmp     short loc_180024426
0x1800243fa  sub     r9, 2
0x1800243fe  mov     eax, 0CCCCCCCDh
0x180024403  mul     edi
0x180024405  shr     edx, 3
0x180024408  movzx   eax, dx
0x18002440b  shl     ax, 2
0x18002440f  lea     ecx, [rax+rdx]
0x180024412  add     cx, cx
0x180024415  sub     di, cx
0x180024418  add     di, 30h ; '0'
0x18002441c  mov     [r9], di
0x180024420  mov     edi, edx
0x180024422  test    edx, edx
0x180024424  jnz     short loc_1800243FA
0x180024426  lea     r8, [rbp+60h+var_46]
0x18002442a  mov     rdx, r9
0x18002442d  lea     rcx, [rsp+160h+Src]
0x180024432  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180024437  nop
0x180024438  lea     r8, [rsp+160h+Src]
0x18002443d  lea     rcx, [rsp+160h+var_F0]
0x180024442  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180024447  nop
0x180024448  lea     r8, Delimiter; ";"
  ... truncated ...
```
