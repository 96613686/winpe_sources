# Ssl::ReadData(wchar_t const *,std::vector<char,std::allocator<char>> &)

- ea: `0x18017c5d0`
- end: `0x18017c8b6`
- name: `?ReadData@Ssl@@CAKPEB_WAEAV?$vector@DV?$allocator@D@std@@@std@@@Z`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18017c160`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x18009c770`
- `0x18009cbe0`
- `0x180178ac0`
- `0x180178c10`
- `0x18017c5d0`
- `0x1801a65e1`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18017c68c`
- `KERNEL32!GetLastError` at `0x18017c68c`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18017c879`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18017c879`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18017c86b`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18017c86b`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x18017c77e`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x18017c7a6`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x18017c77e`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x18017c7a6`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18017c796`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18017c796`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18017c76e`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18017c76e`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18017c6a6`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18017c6a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Ssl::ReadData(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  DWORD LastError; // edi
  __m128i v7; // xmm1
  __m128i si128; // xmm2
  unsigned __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  char v19[4]; // [rsp+30h] [rbp-188h] BYREF
  int v20; // [rsp+34h] [rbp-184h]
  const std::bad_alloc *v21; // [rsp+38h] [rbp-180h] BYREF
  char v22[24]; // [rsp+58h] [rbp-160h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-148h] BYREF
  _QWORD v24[2]; // [rsp+80h] [rbp-138h] BYREF
  char v25[8]; // [rsp+90h] [rbp-128h] BYREF
  char v26[120]; // [rsp+98h] [rbp-120h] BYREF
  __int64 v27; // [rsp+110h] [rbp-A8h]
  char v28[96]; // [rsp+130h] [rbp-88h] BYREF

  v23[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266D80[0] )
    bidScopeEnterW(v23, off_180266D80[0], a1, a4);
  LastError = 0;
  memset_0(v24, 0, 0x110u);
  std::ifstream::ifstream(v24, a1, 36, 64, 1);
  std::vector<char>::_Assign_counted_range<char const *>(a2, 0, 0);
  if ( !v27 )
  {
    LastError = GetLastError();
    goto LABEL_22;
  }
  v7 = *(__m128i *)std::istream::tellg(v24, v22);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v9 = v7.m128i_i64[0] + _mm_srli_si128(v7, 8).m128i_u64[0];
  if ( si128.m128i_i64[0] + _mm_srli_si128(si128, 8).m128i_u64[0] == v9 )
  {
    LastError = 30;
    goto LABEL_22;
  }
  if ( v9 > 0x7FFFFFFFFFFFFFFFLL )
  {
    LastError = 14;
    goto LABEL_22;
  }
  try
  {
    v10 = a2[1];
    v11 = *a2;
    v12 = v10 - *a2;
    if ( v9 < v12 )
    {
      v13 = v11 + v9;
LABEL_16:
      a2[1] = v13;
      goto LABEL_32;
    }
    if ( v9 > v12 )
    {
      if ( v9 <= a2[2] - v11 )
      {
        v14 = v9 - v12;
        memset_0((void *)a2[1], 0, v9 - v12);
        v13 = v10 + v14;
        goto LABEL_16;
      }
      _mm_lfence();
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, v9, v19);
    }
  }
  catch ( const std::bad_alloc *v21 )
  {
    v20 = 14;
    if ( (bidGblFlags & 2) != 0 && off_1802652B0[0] )
    {
      v18 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v21 + 8LL))(v21);
      bidTraceW(off_180261F68[0], 1019904, off_1802652B0[0], v18);
    }
    LastError = v20;
    goto LABEL_22;
  }
LABEL_32:
  v15 = std::istream::seekg(v24, 0, 0);
  if ( (unsigned __int8)std::ios_base::operator!(v15 + *(int *)(*(_QWORD *)v15 + 4LL))
    || (v16 = std::istream::read(v24, *a2, v9),
        (unsigned __int8)std::ios_base::operator!(v16 + *(int *)(*(_QWORD *)v16 + 4LL))) )
  {
    LastError = 30;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_1802652B8[0] )
        bidTraceW(off_180261F70[0], 1027072, off_1802652B8[0], 30);
    }
  }
LABEL_22:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802652C0[0] )
    bidTraceW(off_180261F78[0], 1033216, off_1802652C0[0], LastError);
  *(_QWORD *)((char *)v24 + *(int *)(v24[0] + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)((char *)&v23[1] + *(int *)(v24[0] + 4LL) + 4) = *(_DWORD *)(v24[0] + 4LL) - 176;
  std::filebuf::~filebuf<char,std::char_traits<char>>(v25);
  std::istream::~istream<char,std::char_traits<char>>(v26);
  std::ios::~ios<char,std::char_traits<char>>(v28);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v23);
  return LastError;
}

```

## disassembly

```asm
0x18017c5d0  mov     [rsp+arg_10], rbx
0x18017c5d5  mov     [rsp+arg_18], rsi
0x18017c5da  push    rdi
0x18017c5db  push    r14
0x18017c5dd  push    r15
0x18017c5df  sub     rsp, 1A0h
0x18017c5e6  mov     rax, cs:__security_cookie
0x18017c5ed  xor     rax, rsp
0x18017c5f0  mov     [rsp+1B8h+var_28], rax
0x18017c5f8  mov     r14, rdx
0x18017c5fb  mov     rbx, rcx
0x18017c5fe  mov     [rsp+1B8h+var_148], 0FFFFFFFFFFFFFFFFh
0x18017c607  mov     eax, cs:_bidGblFlags
0x18017c60d  and     eax, 20004h
0x18017c612  cmp     eax, 20004h
0x18017c617  jnz     short loc_18017C639
0x18017c619  mov     rax, cs:off_180266D80; "<Ssl::ReadData|API|SNI> fileName: %s\n"
0x18017c620  test    rax, rax
0x18017c623  jz      short loc_18017C639
0x18017c625  mov     r8, rcx
0x18017c628  mov     rdx, cs:off_180266D80; "<Ssl::ReadData|API|SNI> fileName: %s\n"
0x18017c62f  lea     rcx, [rsp+1B8h+var_148]
0x18017c634  call    _bidScopeEnterW
0x18017c639  xor     edi, edi
0x18017c63b  xor     edx, edx; Val
0x18017c63d  mov     r8d, 110h; Size
0x18017c643  lea     rcx, [rsp+1B8h+var_138]; void *
0x18017c64b  call    memset_0
0x18017c650  mov     [rsp+1B8h+var_198], 1
0x18017c658  mov     r9d, 40h ; '@'
0x18017c65e  mov     r8d, 24h ; '$'
0x18017c664  mov     rdx, rbx
0x18017c667  lea     rcx, [rsp+1B8h+var_138]
0x18017c66f  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x18017c674  nop
0x18017c675  xor     r8d, r8d
0x18017c678  xor     edx, edx
0x18017c67a  mov     rcx, r14
0x18017c67d  call    ??$_Assign_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXPEBD_K@Z; std::vector<char>::_Assign_counted_range<char const *>(char const *,unsigned __int64)
0x18017c682  cmp     [rsp+1B8h+var_A8], rdi
0x18017c68a  jnz     short loc_18017C699
0x18017c68c  call    cs:__imp_GetLastError
0x18017c692  mov     edi, eax
0x18017c694  jmp     loc_18017C7EB
0x18017c699  lea     rdx, [rsp+1B8h+var_160]
0x18017c69e  lea     rcx, [rsp+1B8h+var_138]
0x18017c6a6  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18017c6ac  movups  xmm1, xmmword ptr [rax]
0x18017c6af  movdqa  xmm2, cs:__xmm@0000000000000000ffffffffffffffff
0x18017c6b7  movdqa  xmm0, xmm1
0x18017c6bb  psrldq  xmm0, 8
0x18017c6c0  movq    rsi, xmm0
0x18017c6c5  movq    rax, xmm1
0x18017c6ca  add     rsi, rax
0x18017c6cd  movdqa  xmm0, xmm2
0x18017c6d1  psrldq  xmm0, 8
0x18017c6d6  movq    rcx, xmm0
0x18017c6db  movq    rax, xmm2
0x18017c6e0  add     rcx, rax
0x18017c6e3  cmp     rcx, rsi
0x18017c6e6  jnz     short loc_18017C6F2
0x18017c6e8  mov     edi, 1Eh
0x18017c6ed  jmp     loc_18017C7EB
0x18017c6f2  mov     rax, 7FFFFFFFFFFFFFFFh
0x18017c6fc  cmp     rsi, rax
0x18017c6ff  jbe     short loc_18017C70B
0x18017c701  mov     edi, 0Eh
0x18017c706  jmp     loc_18017C7EB
0x18017c70b  mov     r15, [r14+8]
0x18017c70f  mov     rdx, [r14]
0x18017c712  mov     rcx, r15
0x18017c715  sub     rcx, rdx
0x18017c718  cmp     rsi, rcx
0x18017c71b  jnb     short loc_18017C723
0x18017c71d  lea     rax, [rdx+rsi]
0x18017c721  jmp     short loc_18017C75D
0x18017c723  jbe     short loc_18017C761
0x18017c725  mov     rax, [r14+10h]
0x18017c729  sub     rax, rdx
0x18017c72c  cmp     rsi, rax
0x18017c72f  jbe     short loc_18017C746
0x18017c731  lfence
0x18017c734  lea     r8, [rsp+1B8h+var_188]
0x18017c739  mov     rdx, rsi
0x18017c73c  mov     rcx, r14
0x18017c73f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18017c744  jmp     short loc_18017C761
0x18017c746  mov     rbx, rsi
0x18017c749  sub     rbx, rcx
0x18017c74c  mov     r8, rbx; Size
0x18017c74f  xor     edx, edx; Val
0x18017c751  mov     rcx, r15; void *
0x18017c754  call    memset_0
0x18017c759  lea     rax, [r15+rbx]
0x18017c75d  mov     [r14+8], rax
0x18017c761  xor     r8d, r8d
0x18017c764  xor     edx, edx
0x18017c766  lea     rcx, [rsp+1B8h+var_138]
0x18017c76e  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18017c774  mov     rcx, [rax]
0x18017c777  movsxd  rcx, dword ptr [rcx+4]
0x18017c77b  add     rcx, rax
0x18017c77e  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x18017c784  test    al, al
0x18017c786  jnz     short loc_18017C7B0
0x18017c788  mov     r8, rsi
0x18017c78b  mov     rdx, [r14]
0x18017c78e  lea     rcx, [rsp+1B8h+var_138]
0x18017c796  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18017c79c  mov     rcx, [rax]
0x18017c79f  movsxd  rcx, dword ptr [rcx+4]
0x18017c7a3  add     rcx, rax
0x18017c7a6  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x18017c7ac  test    al, al
0x18017c7ae  jz      short loc_18017C7EB
0x18017c7b0  mov     edi, 1Eh
0x18017c7b5  test    byte ptr cs:_bidGblFlags, 2
0x18017c7bc  jz      short loc_18017C7EB
0x18017c7be  mov     rax, cs:off_1802652B8; "<Ssl::ReadData|ERR|SNI> Unable to creat"...
0x18017c7c5  test    rax, rax
0x18017c7c8  jz      short loc_18017C7EB
0x18017c7ca  mov     r9d, edi
0x18017c7cd  mov     r8, cs:off_1802652B8; "<Ssl::ReadData|ERR|SNI> Unable to creat"...
0x18017c7d4  mov     edx, 0FAC00h
0x18017c7d9  mov     rcx, cs:off_180261F70; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c7e0  call    _bidTraceW
0x18017c7e5  jmp     short loc_18017C7EB
0x18017c7e7  mov     edi, [rsp+1B8h+var_184]
0x18017c7eb  mov     eax, cs:_bidGblFlags
0x18017c7f1  and     eax, 20002h
0x18017c7f6  cmp     eax, 20002h
0x18017c7fb  jnz     short loc_18017C825
0x18017c7fd  mov     rax, cs:off_1802652C0; "<Ssl::ReadData|RET|SNI> %d{WINERR}\n"
0x18017c804  test    rax, rax
0x18017c807  jz      short loc_18017C825
0x18017c809  mov     r9d, edi
0x18017c80c  mov     r8, cs:off_1802652C0; "<Ssl::ReadData|RET|SNI> %d{WINERR}\n"
0x18017c813  mov     edx, 0FC400h
0x18017c818  mov     rcx, cs:off_180261F78; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017c81f  call    _bidTraceW
0x18017c824  nop
0x18017c825  mov     rax, [rsp+1B8h+var_138]
0x18017c82d  movsxd  rcx, dword ptr [rax+4]
0x18017c831  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x18017c838  mov     [rsp+rcx+1B8h+var_138], rax
0x18017c840  mov     rax, [rsp+1B8h+var_138]
0x18017c848  movsxd  rcx, dword ptr [rax+4]
0x18017c84c  lea     edx, [rcx-0B0h]
0x18017c852  mov     [rsp+rcx+1B8h+var_13C], edx
0x18017c856  lea     rcx, [rsp+1B8h+var_128]
0x18017c85e  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x18017c863  lea     rcx, [rsp+1B8h+var_120]
0x18017c86b  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x18017c871  lea     rcx, [rsp+1B8h+var_88]
0x18017c879  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18017c87f  nop
0x18017c880  lea     rcx, [rsp+1B8h+var_148]; this
0x18017c885  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18017c88a  nop
0x18017c88b  mov     eax, edi
0x18017c88d  mov     rcx, [rsp+1B8h+var_28]
0x18017c895  xor     rcx, rsp; StackCookie
0x18017c898  call    __security_check_cookie
0x18017c89d  lea     r11, [rsp+1B8h+var_18]
0x18017c8a5  mov     rbx, [r11+30h]
0x18017c8a9  mov     rsi, [r11+38h]
0x18017c8ad  mov     rsp, r11
0x18017c8b0  pop     r15
0x18017c8b2  pop     r14
0x18017c8b4  pop     rdi
0x18017c8b5  retn
```
