# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x1800150fc`
- end: `0x1800155ca`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1230`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000f2b4`

## callees

- `0x18000fb64`
- `0x1800150fc`
- `0x1800155d0`
- `0x180016870`
- `0x180017424`
- `0x1800174b0`
- `0x180017544`
- `0x1800177d0`
- `0x18005551a`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800154a6`
- `msvcrt!wcscat_s` at `0x1800154b7`
- `msvcrt!wcscat_s` at `0x1800154cc`
- `msvcrt!wcscat_s` at `0x1800154eb`
- `msvcrt!wcscat_s` at `0x1800154a6`
- `msvcrt!wcscat_s` at `0x1800154b7`
- `msvcrt!wcscat_s` at `0x1800154cc`
- `msvcrt!wcscat_s` at `0x1800154eb`
- `msvcrt!malloc` at `0x180015144`
- `msvcrt!malloc` at `0x180015199`
- `msvcrt!malloc` at `0x18001540d`
- `msvcrt!malloc` at `0x180015144`
- `msvcrt!malloc` at `0x180015199`
- `msvcrt!malloc` at `0x18001540d`
- `msvcrt!free` at `0x1800151aa`
- `msvcrt!free` at `0x1800153ef`
- `msvcrt!free` at `0x1800153f8`
- `msvcrt!free` at `0x180015420`
- `msvcrt!free` at `0x180015543`
- `msvcrt!free` at `0x18001555e`
- `msvcrt!free` at `0x180015567`
- `msvcrt!free` at `0x18001557d`
- `msvcrt!free` at `0x180015586`
- `msvcrt!free` at `0x180015599`
- `msvcrt!free` at `0x1800151aa`
- `msvcrt!free` at `0x1800153ef`
- `msvcrt!free` at `0x1800153f8`
- `msvcrt!free` at `0x180015420`
- `msvcrt!free` at `0x180015543`
- `msvcrt!free` at `0x18001555e`
- `msvcrt!free` at `0x180015567`
- `msvcrt!free` at `0x18001557d`
- `msvcrt!free` at `0x180015586`
- `msvcrt!free` at `0x180015599`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180015214`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180015214`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18001546f`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18001546f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800153b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015535`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800153b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015535`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x180015491`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x180015491`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015186`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180015186`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  ATL::CRegParser *v5; // r12
  const WCHAR *v6; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int Token; // ebx
  unsigned int i; // ebx
  unsigned __int16 *v12; // rdi
  __int16 v13; // r14
  HKEY v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 cbData; // r13
  __int64 v18; // rax
  void *v19; // rsp
  BYTE *lpData; // r15
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  char v23; // r8
  unsigned __int64 v24; // rdx
  char v25; // al
  __int64 v26; // rbx
  const BYTE *v27; // r13
  _WORD *v28; // r14
  __int64 v29; // rax
  ATL::CRegObject *v30; // rcx
  const WCHAR *v31; // rax
  const wchar_t *v32; // r12
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // r15
  __int64 v35; // rax
  BYTE Data[8]; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  _QWORD *v39; // [rsp+40h] [rbp+10h] BYREF
  ATL::CRegParser *v40; // [rsp+48h] [rbp+18h]
  HKEY *v41; // [rsp+50h] [rbp+20h]
  unsigned __int16 *v42; // [rsp+58h] [rbp+28h]
  _QWORD *v43; // [rsp+60h] [rbp+30h] BYREF

  v5 = this;
  v40 = this;
  v42 = a4;
  v39 = 0;
  v6 = a3;
  *(_QWORD *)Data = a3;
  v41 = a2;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_9;
  Token = ATL::CRegParser::NextToken(v5, v8);
  if ( Token < 0 )
  {
LABEL_74:
    free(v9);
    goto LABEL_75;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 2147614729LL;
    }
    if ( !lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v12 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v12 )
    goto LABEL_8;
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v5);
  Token = ATL::CRegParser::NextToken(v5, v12);
  if ( Token < 0 )
  {
LABEL_73:
    free(v12);
    goto LABEL_74;
  }
  pulOut = 0;
  if ( v13 != 8 )
  {
    if ( v13 != 17 )
    {
      if ( v13 == 19 )
      {
        VarUI4FromStr(v12, 0, 0, &pulOut);
        v14 = *a2;
        *(_DWORD *)Data = pulOut;
        RegSetValueExW(v14, v6, 0, 4u, Data, 4u);
      }
      goto LABEL_72;
    }
    v15 = -1;
    do
      ++v15;
    while ( v12[v15] );
    if ( (v15 & 1) == 0 )
    {
      v16 = (unsigned int)((int)v15 >> 31);
      cbData = (int)v15 / 2;
      if ( cbData <= 0x400
        && (LODWORD(v16) = (int)v15 % 2,
            ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v15 / 2), v16)) )
      {
        v18 = cbData + 15;
        if ( cbData + 15 < cbData )
          v18 = 0xFFFFFFFFFFFFFF0LL;
        v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
        lpData = Data;
      }
      else
      {
        lpData = (BYTE *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                           &v39,
                           cbData);
      }
      if ( lpData )
      {
        memset_0(lpData, 0, cbData);
        v21 = 0;
        if ( (int)v15 <= 0 )
        {
LABEL_52:
          RegSetValueExW(*v41, *(LPCWSTR *)Data, 0, 3u, lpData, cbData);
          goto LABEL_72;
        }
        while ( 2 )
        {
          v22 = v12[v21];
          if ( v22 > 0x61 )
          {
            if ( v22 != 98 && v22 != 99 && v22 != 100 && v22 - 101 >= 2 )
              goto LABEL_49;
          }
          else if ( v22 != 97 )
          {
            if ( v22 > 0x38 )
            {
              if ( v22 == 57 )
                goto LABEL_37;
              if ( v22 != 65 && v22 != 66 && v22 != 67 && v22 != 68 && v22 - 69 > 1 )
                goto LABEL_49;
              v23 = v22 - 55;
            }
            else
            {
              if ( v22 == 56
                || v22 == 48
                || v22 == 49
                || v22 == 50
                || v22 == 51
                || v22 == 52
                || v22 == 53
                || v22 - 54 <= 1 )
              {
LABEL_37:
                v23 = v22 - 48;
                goto LABEL_51;
              }
LABEL_49:
              v23 = 0;
            }
LABEL_51:
            v24 = (unsigned __int64)v21 >> 1;
            v25 = 4 * (v21++ & 1);
            lpData[v24] |= v23 << (4 - v25);
            if ( (int)v21 >= (int)v15 )
              goto LABEL_52;
            continue;
          }
          break;
        }
        v23 = v22 - 87;
        goto LABEL_51;
      }
    }
    goto LABEL_57;
  }
  v26 = -1;
  v27 = (const BYTE *)v12;
  v28 = 0;
  if ( !a5 )
  {
    do
LABEL_69:
      ++v26;
    while ( *(_WORD *)&v27[2 * v26] );
    RegSetValueExW(*v41, v6, 0, 1u, v27, 2 * v26 + 2);
    if ( v28 )
      free(v28);
LABEL_72:
    Token = ATL::CRegParser::NextToken(v5, v42);
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 0;
    }
    goto LABEL_73;
  }
  v29 = -1;
  do
    ++v29;
  while ( v12[v29] );
  if ( (int)v29 > 4094 )
  {
LABEL_57:
    free(v12);
    free(v9);
    Token = -2147467259;
    goto LABEL_75;
  }
  v28 = malloc(0x2000u);
  if ( v28 )
  {
    v30 = (ATL::CRegObject *)*((_QWORD *)v5 + 1);
    v43 = 0;
    v31 = ATL::CRegObject::StrFromMap(v30, L"Module");
    v32 = v31;
    if ( v31 )
    {
      v33 = (unsigned __int16 *)ATL::CRegParser::StrStrW(v12, v31);
      v34 = v33;
      if ( v33 && (v33 == v42 || *CharPrevW(v12, v33) != 34) )
      {
        *v28 = 0;
        lstrcpynW(v28, v12, v34 - v12);
        wcscat_s(v28, 0x1000u, L"\"");
        wcscat_s(v28, 0x1000u, v32);
        wcscat_s(v28, 0x1000u, L"\"");
        v35 = -1;
        do
          ++v35;
        while ( v32[v35] );
        wcscat_s(v28, 0x1000u, &v34[v35]);
        v27 = (const BYTE *)v28;
      }
      v6 = *(const WCHAR **)Data;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v43);
    v5 = v40;
    goto LABEL_69;
  }
  free(v12);
LABEL_8:
  free(v9);
LABEL_9:
  Token = -2147024882;
LABEL_75:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x1800150fc  push    rbp
0x1800150fe  push    rbx
0x1800150ff  push    rsi
0x180015100  push    rdi
0x180015101  push    r12
0x180015103  push    r13
0x180015105  push    r14
0x180015107  push    r15
0x180015109  sub     rsp, 78h
0x18001510d  lea     rbp, [rsp+30h]
0x180015112  mov     rax, cs:__security_cookie
0x180015119  xor     rax, rbp
0x18001511c  mov     [rbp+80h+var_48], rax
0x180015120  mov     r12, rcx
0x180015123  mov     [rbp+80h+var_68], rcx
0x180015127  xor     edi, edi
0x180015129  mov     [rbp+80h+var_58], r9
0x18001512d  mov     ecx, 2000h; Size
0x180015132  mov     [rbp+80h+var_70], rdi
0x180015136  mov     r15, r8
0x180015139  mov     qword ptr [rbp+80h+Data], r8
0x18001513d  mov     r13, rdx
0x180015140  mov     [rbp+80h+var_60], rdx
0x180015144  call    cs:__imp_malloc
0x18001514a  mov     rsi, rax
0x18001514d  test    rax, rax
0x180015150  jz      short loc_1800151B0
0x180015152  mov     rdx, rax; unsigned __int16 *
0x180015155  mov     rcx, r12; this
0x180015158  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001515d  mov     ebx, eax
0x18001515f  test    eax, eax
0x180015161  js      loc_180015564
0x180015167  mov     ebx, edi
0x180015169  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180015170  mov     rcx, rsi; Block
0x180015173  cmp     ebx, 3
0x180015176  jnb     loc_180015599
0x18001517c  movsxd  r14, ebx
0x18001517f  add     r14, r14
0x180015182  mov     rdx, [rax+r14*8]; lpString2
0x180015186  call    cs:__imp_lstrcmpiW
0x18001518c  test    eax, eax
0x18001518e  jz      short loc_180015194
0x180015190  inc     ebx
0x180015192  jmp     short loc_180015169
0x180015194  mov     ecx, 2000h; Size
0x180015199  call    cs:__imp_malloc
0x18001519f  mov     rdi, rax
0x1800151a2  test    rax, rax
0x1800151a5  jnz     short loc_1800151BA
0x1800151a7  mov     rcx, rsi; Block
0x1800151aa  call    cs:__imp_free
0x1800151b0  mov     ebx, 8007000Eh
0x1800151b5  jmp     loc_18001556D
0x1800151ba  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800151c1  mov     rcx, r12; this
0x1800151c4  movzx   r14d, word ptr [rax+r14*8+8]
0x1800151ca  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800151cf  mov     rdx, rdi; unsigned __int16 *
0x1800151d2  mov     rcx, r12; this
0x1800151d5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800151da  xor     ecx, ecx
0x1800151dc  mov     ebx, eax
0x1800151de  test    eax, eax
0x1800151e0  js      loc_18001555B
0x1800151e6  lea     eax, [rcx+8]
0x1800151e9  mov     [rbp+80h+pulOut], ecx
0x1800151ec  cmp     r14w, ax
0x1800151f0  jz      loc_1800153C3
0x1800151f6  cmp     r14w, 11h
0x1800151fb  jz      short loc_180015243
0x1800151fd  cmp     r14w, 13h
0x180015202  jnz     loc_180015549
0x180015208  lea     r9, [rbp+80h+pulOut]; pulOut
0x18001520c  xor     r8d, r8d; dwFlags
0x18001520f  xor     edx, edx; lcid
0x180015211  mov     rcx, rdi; strIn
0x180015214  call    cs:__imp_VarUI4FromStr
0x18001521a  mov     eax, [rbp+80h+pulOut]
0x18001521d  mov     r9d, 4
0x180015223  mov     rcx, [r13+0]
0x180015227  mov     rdx, r15
0x18001522a  mov     dword ptr [rbp+80h+Data], eax
0x18001522d  lea     rax, [rbp+80h+Data]
0x180015231  mov     [rsp+0B0h+cbData], 4
0x180015239  mov     [rsp+0B0h+lpData], rax
0x18001523e  jmp     loc_1800153B5
0x180015243  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015247  inc     rbx
0x18001524a  cmp     [rdi+rbx*2], cx
0x18001524e  jnz     short loc_180015247
0x180015250  test    bl, 1
0x180015253  jnz     loc_1800153EC
0x180015259  mov     eax, ebx
0x18001525b  mov     ecx, 2
0x180015260  cdq; unsigned __int64
0x180015261  idiv    ecx
0x180015263  movsxd  r13, eax
0x180015266  cmp     r13, 400h
0x18001526d  ja      short loc_1800152A1
0x18001526f  mov     rcx, r13; this
0x180015272  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180015277  test    al, al
0x180015279  jz      short loc_1800152A1
0x18001527b  lea     rax, [r13+0Fh]
0x18001527f  cmp     rax, r13
0x180015282  ja      short loc_18001528E
0x180015284  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001528e  and     rax, 0FFFFFFFFFFFFFFF0h
0x180015292  call    _alloca_probe
0x180015297  sub     rsp, rax
0x18001529a  lea     r15, [rsp+0B0h+Data]
0x18001529f  jmp     short loc_1800152B0
0x1800152a1  mov     rdx, r13
0x1800152a4  lea     rcx, [rbp+80h+var_70]
0x1800152a8  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x1800152ad  mov     r15, rax
0x1800152b0  test    r15, r15
0x1800152b3  jz      loc_1800153EC
0x1800152b9  mov     r8, r13; Size
0x1800152bc  xor     edx, edx; Val
0x1800152be  mov     rcx, r15; void *
0x1800152c1  call    memset_0
0x1800152c6  xor     eax, eax
0x1800152c8  mov     r9d, eax
0x1800152cb  test    ebx, ebx
0x1800152cd  jle     loc_18001539A
0x1800152d3  mov     eax, r9d
0x1800152d6  movzx   r8d, word ptr [rdi+rax*2]
0x1800152db  cmp     r8d, 61h ; 'a'
0x1800152df  ja      short loc_18001534C
0x1800152e1  jz      loc_18001536D
0x1800152e7  cmp     r8d, 38h ; '8'
0x1800152eb  ja      short loc_180015320
0x1800152ed  jz      short loc_18001531A
0x1800152ef  mov     ecx, r8d
0x1800152f2  sub     ecx, 30h ; '0'
0x1800152f5  jz      short loc_18001531A
0x1800152f7  sub     ecx, 1
0x1800152fa  jz      short loc_18001531A
0x1800152fc  sub     ecx, 1
0x1800152ff  jz      short loc_18001531A
0x180015301  sub     ecx, 1
0x180015304  jz      short loc_18001531A
0x180015306  sub     ecx, 1
0x180015309  jz      short loc_18001531A
0x18001530b  sub     ecx, 1
0x18001530e  jz      short loc_18001531A
0x180015310  sub     ecx, 1
0x180015313  jz      short loc_18001531A
0x180015315  cmp     ecx, 1
0x180015318  jnz     short loc_180015368
0x18001531a  sub     r8b, 30h ; '0'
0x18001531e  jmp     short loc_180015371
0x180015320  mov     ecx, r8d
0x180015323  sub     ecx, 39h ; '9'
0x180015326  jz      short loc_18001531A
0x180015328  sub     ecx, 8
0x18001532b  jz      short loc_180015346
0x18001532d  sub     ecx, 1
0x180015330  jz      short loc_180015346
0x180015332  sub     ecx, 1
0x180015335  jz      short loc_180015346
0x180015337  sub     ecx, 1
0x18001533a  jz      short loc_180015346
0x18001533c  sub     ecx, 1
0x18001533f  jz      short loc_180015346
0x180015341  cmp     ecx, 1
0x180015344  jnz     short loc_180015368
0x180015346  sub     r8b, 37h ; '7'
0x18001534a  jmp     short loc_180015371
0x18001534c  mov     ecx, r8d
0x18001534f  sub     ecx, 62h ; 'b'
0x180015352  jz      short loc_18001536D
0x180015354  sub     ecx, 1
0x180015357  jz      short loc_18001536D
0x180015359  sub     ecx, 1
0x18001535c  jz      short loc_18001536D
0x18001535e  sub     ecx, 1
0x180015361  jz      short loc_18001536D
0x180015363  cmp     ecx, 1
0x180015366  jz      short loc_18001536D
0x180015368  xor     r8b, r8b
0x18001536b  jmp     short loc_180015371
0x18001536d  sub     r8b, 57h ; 'W'
0x180015371  mov     eax, r9d
0x180015374  mov     edx, r9d
0x180015377  and     eax, 1
0x18001537a  shr     rdx, 1
0x18001537d  shl     eax, 2
0x180015380  mov     ecx, 4
0x180015385  sub     ecx, eax
0x180015387  inc     r9d
0x18001538a  shl     r8b, cl
0x18001538d  or      [rdx+r15], r8b
0x180015391  cmp     r9d, ebx
0x180015394  jl      loc_1800152D3
0x18001539a  mov     rcx, [rbp+80h+var_60]
0x18001539e  mov     r9d, 3; dwType
0x1800153a4  mov     rdx, qword ptr [rbp+80h+Data]; lpValueName
0x1800153a8  mov     [rsp+0B0h+cbData], r13d; cbData
0x1800153ad  mov     [rsp+0B0h+lpData], r15; lpData
0x1800153b2  mov     rcx, [rcx]; hKey
0x1800153b5  xor     r8d, r8d; Reserved
0x1800153b8  call    cs:__imp_RegSetValueExW
0x1800153be  jmp     loc_180015549
0x1800153c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800153c7  mov     r13, rdi
0x1800153ca  mov     r14, rcx
0x1800153cd  cmp     [rbp+80h+arg_20], cl
0x1800153d3  jz      loc_180015507
0x1800153d9  mov     rax, rbx
0x1800153dc  inc     rax
0x1800153df  cmp     [rdi+rax*2], cx
0x1800153e3  jnz     short loc_1800153DC
0x1800153e5  cmp     eax, 0FFEh
0x1800153ea  jle     short loc_180015408
0x1800153ec  mov     rcx, rdi; Block
0x1800153ef  call    cs:__imp_free
0x1800153f5  mov     rcx, rsi; Block
0x1800153f8  call    cs:__imp_free
0x1800153fe  mov     ebx, 80004005h
0x180015403  jmp     loc_18001556D
0x180015408  mov     ecx, 2000h; Size
0x18001540d  call    cs:__imp_malloc
0x180015413  mov     r14, rax
0x180015416  xor     eax, eax
0x180015418  test    r14, r14
0x18001541b  jnz     short loc_18001542B
0x18001541d  mov     rcx, rdi; Block
0x180015420  call    cs:__imp_free
0x180015426  jmp     loc_1800151A7
0x18001542b  mov     rcx, [r12+8]; this
0x180015430  lea     rdx, aModule; "Module"
0x180015437  mov     [rbp+80h+var_50], rax
0x18001543b  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180015440  mov     r12, rax
0x180015443  test    rax, rax
0x180015446  jz      loc_1800154F8
0x18001544c  mov     rdx, rax; LPCWSTR
0x18001544f  mov     rcx, rdi; lpsz
0x180015452  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x180015457  mov     r15, rax
0x18001545a  test    rax, rax
0x18001545d  jz      loc_1800154F4
0x180015463  cmp     rax, [rbp+80h+var_58]
0x180015467  jz      short loc_18001547B
0x180015469  mov     rdx, rax; lpszCurrent
0x18001546c  mov     rcx, rdi; lpszStart
0x18001546f  call    cs:__imp_CharPrevW
0x180015475  cmp     word ptr [rax], 22h ; '"'
0x180015479  jz      short loc_1800154F4
0x18001547b  mov     r8, r15
0x18001547e  xor     r13d, r13d
0x180015481  sub     r8, rdi
0x180015484  mov     [r14], r13w
0x180015488  sar     r8, 1; iMaxLength
0x18001548b  mov     rdx, rdi; lpString2
0x18001548e  mov     rcx, r14; lpString1
0x180015491  call    cs:__imp_lstrcpynW
0x180015497  lea     r8, Source; "\""
0x18001549e  mov     edx, 1000h; SizeInWords
0x1800154a3  mov     rcx, r14; Destination
0x1800154a6  call    cs:__imp_wcscat_s
0x1800154ac  mov     r8, r12; Source
0x1800154af  mov     edx, 1000h; SizeInWords
0x1800154b4  mov     rcx, r14; Destination
0x1800154b7  call    cs:__imp_wcscat_s
0x1800154bd  lea     r8, Source; "\""
0x1800154c4  mov     edx, 1000h; SizeInWords
0x1800154c9  mov     rcx, r14; Destination
0x1800154cc  call    cs:__imp_wcscat_s
0x1800154d2  mov     rax, rbx
0x1800154d5  inc     rax
0x1800154d8  cmp     [r12+rax*2], r13w
0x1800154dd  jnz     short loc_1800154D5
0x1800154df  lea     r8, [r15+rax*2]; Source
0x1800154e3  mov     edx, 1000h; SizeInWords
0x1800154e8  mov     rcx, r14; Destination
0x1800154eb  call    cs:__imp_wcscat_s
0x1800154f1  mov     r13, r14
0x1800154f4  mov     r15, qword ptr [rbp+80h+Data]
0x1800154f8  lea     rcx, [rbp+80h+var_50]
0x1800154fc  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180015501  mov     r12, [rbp+80h+var_68]
0x180015505  xor     ecx, ecx
0x180015507  inc     rbx
0x18001550a  cmp     [r13+rbx*2+0], cx
0x180015510  jnz     short loc_180015507
0x180015512  mov     rcx, [rbp+80h+var_60]
0x180015516  lea     eax, ds:2[rbx*2]
0x18001551d  mov     [rsp+0B0h+cbData], eax; cbData
0x180015521  mov     r9d, 1; dwType
0x180015527  xor     r8d, r8d; Reserved
0x18001552a  mov     [rsp+0B0h+lpData], r13; lpData
0x18001552f  mov     rdx, r15; lpValueName
0x180015532  mov     rcx, [rcx]; hKey
0x180015535  call    cs:__imp_RegSetValueExW
0x18001553b  test    r14, r14
  ... truncated ...
```
