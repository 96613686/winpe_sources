# GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x1800104d4`
- end: `0x180010845`
- name: `?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *)`
- caller_count: `6`
- callee_count: `13`
- tags: ``

## callers

- `0x180008c24`
- `0x18000b84c`
- `0x18000be70`
- `0x18000d590`
- `0x18000ffa4`
- `0x180010124`

## callees

- `0x180001540`
- `0x180002e54`
- `0x180002f70`
- `0x180003648`
- `0x180008414`
- `0x18000aa84`
- `0x18000b24c`
- `0x18000c728`
- `0x18000f83c`
- `0x18000fe48`
- `0x1800104d4`
- `0x180010cb4`
- `0x180013de0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001062f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001066c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001062f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001066c`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath(__int64 a1, LPCWSTR *a2)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rdx
  LPCWSTR v9; // rax
  __int64 not_ch; // rax
  __int64 v11; // r11
  __int64 v12; // rdx
  unsigned __int64 FullPathNameW; // rdx
  WCHAR *v14; // rdi
  DWORD v15; // eax
  __int64 v16; // r8
  const char *v17; // r9
  const wchar_t *v18; // rdx
  size_t v19; // r14
  WCHAR *v20; // r8
  wchar_t **v21; // rdx
  const wchar_t *v22; // rdx
  WCHAR *v23; // rdx
  const wchar_t *v24; // rdx
  __int64 v25; // rax
  const wchar_t *v26; // rdx
  const wchar_t *v27; // rcx
  __int64 v28; // r8
  const char *v29; // r9
  LPCWSTR v30; // rdx
  unsigned __int64 v31; // r8
  char *v33[3]; // [rsp+40h] [rbp-C8h] BYREF
  WCHAR *v34; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD String1[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h]
  wchar_t *v37[2]; // [rsp+98h] [rbp-70h] BYREF
  size_t v38[2]; // [rsp+A8h] [rbp-60h]
  wchar_t *v39[2]; // [rsp+B8h] [rbp-50h] BYREF
  size_t v40[2]; // [rsp+C8h] [rbp-40h]
  wchar_t *String2[2]; // [rsp+D8h] [rbp-30h] BYREF
  size_t MaxCount[2]; // [rsp+E8h] [rbp-20h]
  _OWORD v43[2]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  *(_OWORD *)&String1[1] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[1]) = 0;
  *(_OWORD *)String2 = 0;
  *(_OWORD *)MaxCount = 0;
  std::wstring::_Construct<1,wchar_t const *>((__int64)String2, L"\\\\", 2u);
  *(_OWORD *)v37 = 0;
  *(_OWORD *)v38 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( asc_1800183E0[v5] );
  std::wstring::_Construct<1,wchar_t const *>((__int64)v37, L"\\\\?\\", v5);
  memset(v43, 0, sizeof(v43));
  v6 = -1;
  do
    ++v6;
  while ( aUnc[v6] );
  std::wstring::_Construct<1,wchar_t const *>((__int64)v43, L"\\\\?\\UNC\\", v6);
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  v7 = -1;
  do
    ++v7;
  while ( asc_1800183C0[v7] );
  std::wstring::_Construct<1,wchar_t const *>((__int64)v39, L"\\\\.\\", v7);
  UnicodeStringBuffer::UnicodeStringBuffer((UnicodeStringBuffer *)&v34, v8);
  v9 = a2[1];
  if ( !v9
    || (not_ch = std::_Find_not_ch_vectorized<wchar_t>(*a2, &(*a2)[(_QWORD)v9]), not_ch == v12)
    || (not_ch - v11) >> 1 == -1 )
  {
    v30 = *a2;
    v31 = (unsigned __int64)a2[1];
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a1, v30, v31);
    goto LABEL_37;
  }
  FullPathNameW = GetFullPathNameW(*a2, (__int64)(String1[0] - (_QWORD)v34) >> 1, v34, 0);
  v14 = v34;
  if ( (__int64)(String1[0] - (_QWORD)v34) >> 1 < FullPathNameW )
  {
    std::vector<wchar_t>::resize(&v34, FullPathNameW);
    v15 = GetFullPathNameW(*a2, (__int64)(String1[0] - (_QWORD)v34) >> 1, v34, 0);
    v14 = v34;
    if ( (__int64)(String1[0] - (_QWORD)v34) >> 1 <= (unsigned __int64)v15 )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x171, v16, v17);
  }
  v18 = (const wchar_t *)String2;
  if ( MaxCount[1] > 7 )
    v18 = String2[0];
  v19 = MaxCount[0];
  if ( wcsncmp_0(v14, v18, LODWORD(MaxCount[0])) )
  {
    v20 = v14;
    v21 = v37;
LABEL_29:
    v25 = std::operator+<wchar_t>(v33, v21, v20);
    std::wstring::operator=((char **)&String1[1], v25);
    std::wstring::~wstring(v33);
    goto LABEL_30;
  }
  v22 = (const wchar_t *)v39;
  if ( v40[1] > 7 )
    v22 = v39[0];
  if ( !wcsncmp_0(v14, v22, LODWORD(v40[0])) )
  {
    v14[2] = 63;
    v23 = v34;
    do
      ++v4;
    while ( v34[v4] );
  }
  else
  {
    v24 = (const wchar_t *)v37;
    if ( v38[1] > 7 )
      v24 = v37[0];
    if ( wcsncmp_0(v14, v24, LODWORD(v38[0])) )
    {
      v20 = &v14[v19];
      v21 = (wchar_t **)v43;
      goto LABEL_29;
    }
    do
      ++v4;
    while ( v14[v4] );
    v23 = v14;
  }
  std::wstring::_Assign<wchar_t>((void **)&String1[1], v23, v4);
LABEL_30:
  v26 = (const wchar_t *)v37;
  if ( v38[1] > 7 )
    v26 = v37[0];
  v27 = (const wchar_t *)&String1[1];
  if ( si128.m128i_i64[1] > 7uLL )
    v27 = (const wchar_t *)String1[1];
  if ( wcsncmp_0(v27, v26, LODWORD(v38[0])) )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0x18E, v28, v29);
  *(_OWORD *)a1 = *(_OWORD *)&String1[1];
  *(__m128i *)(a1 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(String1[1]) = 0;
LABEL_37:
  std::vector<wchar_t>::~vector<wchar_t>((char **)&v34);
  std::wstring::~wstring((char **)v39);
  std::wstring::~wstring((char **)v43);
  std::wstring::~wstring((char **)v37);
  std::wstring::~wstring((char **)String2);
  std::wstring::~wstring((char **)&String1[1]);
  return a1;
}

```

## disassembly

```asm
0x1800104d4  mov     rax, rsp
0x1800104d7  push    rbp
0x1800104d8  push    rsi
0x1800104d9  push    rdi
0x1800104da  push    r14
0x1800104dc  push    r15
0x1800104de  lea     rbp, [rax-48h]
0x1800104e2  sub     rsp, 120h
0x1800104e9  mov     [rsp+140h+var_118], 0FFFFFFFFFFFFFFFEh
0x1800104f2  mov     [rax+18h], rbx
0x1800104f6  mov     rax, cs:__security_cookie
0x1800104fd  xor     rax, rsp
0x180010500  mov     [rbp+40h+var_30], rax
0x180010504  mov     r14, rdx
0x180010507  mov     rsi, rcx
0x18001050a  mov     qword ptr [rsp+140h+var_110], rcx
0x18001050f  xor     r15d, r15d
0x180010512  xorps   xmm0, xmm0
0x180010515  movups  xmmword ptr [rsp+140h+String1+8], xmm0
0x18001051a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180010522  movdqu  [rbp+40h+var_C0], xmm1
0x180010527  mov     word ptr [rsp+140h+String1+8], r15w
0x18001052d  movups  xmmword ptr [rbp+40h+String2], xmm0
0x180010531  xorps   xmm1, xmm1
0x180010534  movdqu  xmmword ptr [rbp+40h+MaxCount], xmm1
0x180010539  lea     r8d, [r15+2]
0x18001053d  lea     rdx, asc_180018320; "\\\\"
0x180010544  lea     rcx, [rbp+40h+String2]
0x180010548  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001054d  nop
0x18001054e  xorps   xmm0, xmm0
0x180010551  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180010555  xorps   xmm1, xmm1
0x180010558  movdqu  xmmword ptr [rbp+40h+var_A0], xmm1
0x18001055d  lea     rdx, asc_1800183E0; "\\\\?\\"
0x180010564  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010568  mov     r8, rbx
0x18001056b  inc     r8
0x18001056e  cmp     [rdx+r8*2], r15w
0x180010573  jnz     short loc_18001056B
0x180010575  lea     rcx, [rbp+40h+var_B0]
0x180010579  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001057e  nop
0x18001057f  xorps   xmm0, xmm0
0x180010582  movups  [rbp+40h+var_50], xmm0
0x180010586  xorps   xmm1, xmm1
0x180010589  movdqu  [rbp+40h+var_40], xmm1
0x18001058e  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x180010595  mov     r8, rbx
0x180010598  inc     r8
0x18001059b  cmp     [rdx+r8*2], r15w
0x1800105a0  jnz     short loc_180010598
0x1800105a2  lea     rcx, [rbp+40h+var_50]
0x1800105a6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800105ab  nop
0x1800105ac  xorps   xmm0, xmm0
0x1800105af  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x1800105b3  xorps   xmm1, xmm1
0x1800105b6  movdqu  xmmword ptr [rbp+40h+var_80], xmm1
0x1800105bb  lea     rdx, asc_1800183C0; "\\\\.\\"
0x1800105c2  mov     r8, rbx
0x1800105c5  inc     r8
0x1800105c8  cmp     [rdx+r8*2], r15w
0x1800105cd  jnz     short loc_1800105C5
0x1800105cf  lea     rcx, [rbp+40h+var_90]
0x1800105d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800105d8  nop
0x1800105d9  lea     rcx, [rsp+140h+var_E8]; this
0x1800105de  call    ??0UnicodeStringBuffer@@QEAA@_K@Z; UnicodeStringBuffer::UnicodeStringBuffer(unsigned __int64)
0x1800105e3  nop
0x1800105e4  mov     rax, [r14+8]
0x1800105e8  cmp     rax, 1
0x1800105ec  jb      loc_1800107AB
0x1800105f2  mov     r11, [r14]
0x1800105f5  lea     rdx, [r11+rax*2]
0x1800105f9  mov     rcx, r11
0x1800105fc  call    ??$_Find_not_ch_vectorized@_W@std@@YAPEB_WQEB_W0_W@Z; std::_Find_not_ch_vectorized<wchar_t>(wchar_t const * const,wchar_t const * const,wchar_t)
0x180010601  cmp     rax, rdx
0x180010604  jz      loc_1800107AB
0x18001060a  sub     rax, r11
0x18001060d  sar     rax, 1
0x180010610  cmp     rax, rbx
0x180010613  jz      loc_1800107AB
0x180010619  mov     r8, [rsp+140h+var_E8]; lpBuffer
0x18001061e  mov     rdx, qword ptr [rsp+140h+String1]
0x180010623  sub     rdx, r8
0x180010626  sar     rdx, 1; nBufferLength
0x180010629  xor     r9d, r9d; lpFilePart
0x18001062c  mov     rcx, [r14]; lpFileName
0x18001062f  call    cs:__imp_GetFullPathNameW
0x180010635  mov     edx, eax
0x180010637  mov     rax, qword ptr [rsp+140h+String1]
0x18001063c  mov     rdi, [rsp+140h+var_E8]
0x180010641  sub     rax, rdi
0x180010644  sar     rax, 1
0x180010647  cmp     rax, rdx
0x18001064a  jnb     short loc_180010691
0x18001064c  lea     rcx, [rsp+140h+var_E8]
0x180010651  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x180010656  mov     r8, [rsp+140h+var_E8]; lpBuffer
0x18001065b  mov     rdx, qword ptr [rsp+140h+String1]
0x180010660  sub     rdx, r8
0x180010663  sar     rdx, 1; nBufferLength
0x180010666  xor     r9d, r9d; lpFilePart
0x180010669  mov     rcx, [r14]; lpFileName
0x18001066c  call    cs:__imp_GetFullPathNameW
0x180010672  mov     rcx, [rbp+48h]; this
0x180010676  mov     rdx, qword ptr [rsp+140h+String1]
0x18001067b  mov     rdi, [rsp+140h+var_E8]
0x180010680  sub     rdx, rdi
0x180010683  sar     rdx, 1
0x180010686  mov     eax, eax
0x180010688  cmp     rdx, rax
0x18001068b  jbe     loc_18001083A
0x180010691  lea     rdx, [rbp+40h+String2]
0x180010695  cmp     [rbp+40h+MaxCount+8], 7
0x18001069a  cmova   rdx, [rbp+40h+String2]; String2
0x18001069f  mov     r14, [rbp+40h+MaxCount]
0x1800106a3  mov     r8d, r14d; MaxCount
0x1800106a6  mov     rcx, rdi; String1
0x1800106a9  call    wcsncmp_0
0x1800106ae  test    eax, eax
0x1800106b0  jz      short loc_1800106BB
0x1800106b2  mov     r8, rdi
0x1800106b5  lea     rdx, [rbp+40h+var_B0]
0x1800106b9  jmp     short loc_180010732
0x1800106bb  lea     rdx, [rbp+40h+var_90]
0x1800106bf  cmp     [rbp+40h+var_80+8], 7
0x1800106c4  cmova   rdx, [rbp+40h+var_90]; String2
0x1800106c9  mov     r8d, dword ptr [rbp+40h+var_80]; MaxCount
0x1800106cd  mov     rcx, rdi; String1
0x1800106d0  call    wcsncmp_0
0x1800106d5  test    eax, eax
0x1800106d7  jnz     short loc_1800106F0
0x1800106d9  mov     word ptr [rdi+4], 3Fh ; '?'
0x1800106df  mov     rdx, [rsp+140h+var_E8]
0x1800106e4  inc     rbx
0x1800106e7  cmp     [rdx+rbx*2], r15w
0x1800106ec  jnz     short loc_1800106E4
0x1800106ee  jmp     short loc_18001071B
0x1800106f0  lea     rdx, [rbp+40h+var_B0]
0x1800106f4  cmp     [rbp+40h+var_A0+8], 7
0x1800106f9  cmova   rdx, [rbp+40h+var_B0]; String2
0x1800106fe  mov     r8d, dword ptr [rbp+40h+var_A0]; MaxCount
0x180010702  mov     rcx, rdi; String1
0x180010705  call    wcsncmp_0
0x18001070a  test    eax, eax
0x18001070c  jnz     short loc_18001072A
0x18001070e  inc     rbx
0x180010711  cmp     [rdi+rbx*2], r15w
0x180010716  jnz     short loc_18001070E
0x180010718  mov     rdx, rdi
0x18001071b  mov     r8, rbx
0x18001071e  lea     rcx, [rsp+140h+String1+8]
0x180010723  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180010728  jmp     short loc_180010753
0x18001072a  lea     r8, [rdi+r14*2]
0x18001072e  lea     rdx, [rbp+40h+var_50]
0x180010732  lea     rcx, [rsp+38h]
0x180010737  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x18001073c  mov     rdx, rax
0x18001073f  lea     rcx, [rsp+140h+String1+8]
0x180010744  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010749  lea     rcx, [rsp+38h]
0x18001074e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010753  lea     rdx, [rbp+40h+var_B0]
0x180010757  cmp     [rbp+40h+var_A0+8], 7
0x18001075c  cmova   rdx, [rbp+40h+var_B0]; String2
0x180010761  lea     rcx, [rsp+140h+String1+8]
0x180010766  cmp     qword ptr [rbp+40h+var_C0+8], 7
0x18001076b  cmova   rcx, qword ptr [rsp+140h+String1+8]; String1
0x180010771  mov     rbx, [rbp+48h]
0x180010775  mov     r8d, dword ptr [rbp+40h+var_A0]; MaxCount
0x180010779  call    wcsncmp_0
0x18001077e  test    eax, eax
0x180010780  jnz     loc_18001082C
0x180010786  movups  xmm0, xmmword ptr [rsp+140h+String1+8]
0x18001078b  movups  xmmword ptr [rsi], xmm0
0x18001078e  movups  xmm1, [rbp+40h+var_C0]
0x180010792  movups  xmmword ptr [rsi+10h], xmm1
0x180010796  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001079e  movdqu  [rbp+40h+var_C0], xmm0
0x1800107a3  mov     word ptr [rsp+140h+String1+8], r15w
0x1800107a9  jmp     short loc_1800107C9
0x1800107ab  mov     rdx, [r14]
0x1800107ae  mov     r8, [r14+8]
0x1800107b2  xorps   xmm0, xmm0
0x1800107b5  movups  xmmword ptr [rsi], xmm0
0x1800107b8  mov     [rsi+10h], r15
0x1800107bc  mov     [rsi+18h], r15
0x1800107c0  mov     rcx, rsi
0x1800107c3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800107c8  nop
0x1800107c9  lea     rcx, [rsp+140h+var_E8]
0x1800107ce  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1800107d3  nop
0x1800107d4  lea     rcx, [rbp+40h+var_90]
0x1800107d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800107dd  nop
0x1800107de  lea     rcx, [rbp+40h+var_50]
0x1800107e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800107e7  nop
0x1800107e8  lea     rcx, [rbp+40h+var_B0]
0x1800107ec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800107f1  nop
0x1800107f2  lea     rcx, [rbp+40h+String2]
0x1800107f6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800107fb  nop
0x1800107fc  lea     rcx, [rsp+140h+String1+8]
0x180010801  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010806  mov     rax, rsi
0x180010809  mov     rcx, [rbp+40h+var_30]
0x18001080d  xor     rcx, rsp; StackCookie
0x180010810  call    __security_check_cookie
0x180010815  mov     rbx, [rsp+140h+arg_10]
0x18001081d  add     rsp, 120h
0x180010824  pop     r15
0x180010826  pop     r14
0x180010828  pop     rdi
0x180010829  pop     rsi
0x18001082a  pop     rbp
0x18001082b  retn
0x18001082c  mov     edx, 18Eh; void *
0x180010831  mov     rcx, rbx; this
0x180010834  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001083a  mov     edx, 171h; void *
0x18001083f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
