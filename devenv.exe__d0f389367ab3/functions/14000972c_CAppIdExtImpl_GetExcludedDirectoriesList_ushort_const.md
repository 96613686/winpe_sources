# CAppIdExtImpl::GetExcludedDirectoriesList(ushort const *)

- ea: `0x14000972c`
- end: `0x140009b0d`
- name: `?GetExcludedDirectoriesList@CAppIdExtImpl@@KA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `993`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x140005b70`
- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002160`
- `0x140002190`
- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x14000972c`
- `0x140009b10`
- `0x140009ba4`
- `0x14000bfa8`
- `0x14001f7c0`
- `0x140033ab0`
- `0x14003b6bc`
- `0x14003b7a0`
- `0x14003be28`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140009aed`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x140009aed`
- `SHLWAPI!PathFileExistsW` at `0x1400097b8`
- `SHLWAPI!PathFileExistsW` at `0x1400097b8`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14000984e`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140009944`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14000984e`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140009944`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400098df`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140009a99`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400098df`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140009a99`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14000985b`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14000985b`
- `MSVCP140!?ignore@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x140009923`
- `MSVCP140!?ignore@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x140009923`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1400099ca`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1400099ca`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x140009954`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x140009954`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400098d5`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140009a8f`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400098d5`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140009a8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall CAppIdExtImpl::GetExcludedDirectoriesList(_QWORD *a1, __int64 a2)
{
  _QWORD *LocalAppDataStoragePath; // rax
  _QWORD *v4; // rdx
  struct ATL::IAtlStringMgr *v5; // rax
  int v6; // ebx
  int v7; // eax
  bool v8; // zf
  __int64 v9; // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  LPCWSTR v11; // rdx
  int v12; // ebx
  unsigned int v13; // eax
  size_t v14; // rsi
  char *v15; // rdi
  char *v16; // r12
  char *v17; // rbx
  char *v18; // rax
  char *v19; // r14
  _QWORD *v20; // rdx
  const struct std::nothrow_t *v21; // rdi
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[152]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[96]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v31; // [rsp+160h] [rbp+60h]
  char *v32; // [rsp+170h] [rbp+70h]

  v25[0] = a1;
  pszPath = 0;
  LocalAppDataStoragePath = (_QWORD *)CAppIdExtImpl::GetLocalAppDataStoragePath(v25, a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &pszPath,
    *LocalAppDataStoragePath);
  v4 = (_QWORD *)(v25[0] - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v25[0] - 24LL + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  }
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
    &pszPath,
    L"ExcludedDirectories.lst");
  if ( PathFileExistsW(pszPath) )
  {
    memset_0(&v26, 0, 0x110u);
    std::ifstream::ifstream(&v26, pszPath);
    v6 = 1;
    while ( (v28[*(int *)(v26 + 4)] & 2) != 0 )
    {
      v7 = v6++;
      if ( v7 >= 10 )
        break;
      v8 = std::filebuf::open(v28, pszPath, 33) == 0;
      v9 = *(int *)(v26 + 4);
      if ( v8 )
        std::ios::setstate((char *)&v26 + v9, 2, 0);
      else
        std::ios::clear((char *)&v26 + v9, 0, 0);
    }
    if ( (v28[*(int *)(v26 + 4)] & 2) == 0 )
    {
      std::istream::ignore(&v26, 0x7FFFFFFFFFFFFFFFLL, 0xFFFFFFFFLL);
      v12 = v27;
      std::ios::clear((char *)&v26 + *(int *)(v26 + 4), 0, 0);
      std::istream::seekg(&v26, 0, 0);
      v13 = v12 + 1;
      v14 = (unsigned int)(v12 + 1);
      v31 = 0;
      v15 = 0;
      v32 = 0;
      v16 = 0;
      v17 = 0;
      if ( v13 )
      {
        _mm_lfence();
        if ( v13 < 0x1000uLL )
          v18 = (char *)operator new(v13);
        else
          v18 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v13);
        v17 = v18;
        v19 = v18;
        *(_QWORD *)&v31 = v18;
        v15 = &v18[v14];
        v16 = &v18[v14];
        v32 = &v18[v14];
        memset_0(v18, 0, v14);
        *((_QWORD *)&v31 + 1) = v15;
      }
      else
      {
        v19 = (char *)v31;
      }
      std::istream::read(&v26, v19, v16 - v17);
      v24 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v24,
        v19);
      *a1 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24 - 24) + 24;
      v20 = (_QWORD *)(v24 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
      }
      if ( v17 )
      {
        v21 = (const struct std::nothrow_t *)(v15 - v17);
        if ( (unsigned __int64)v21 >= 0x1000 )
        {
          v21 = (const struct std::nothrow_t *)((char *)v21 + 39);
          if ( (unsigned __int64)&v17[-*((_QWORD *)v17 - 1) - 8] > 0x1F )
            _invalid_parameter_noinfo_noreturn();
          v17 = (char *)*((_QWORD *)v17 - 1);
        }
        operator delete(v17, v21);
      }
      *(__int64 *)((char *)&v26 + *(int *)(v26 + 4)) = (__int64)&std::ifstream::`vftable';
      *(_DWORD *)((char *)&v25[1] + *(int *)(v26 + 4) + 4) = *(_DWORD *)(v26 + 4) - 176;
      std::filebuf::~filebuf<char,std::char_traits<char>>(v28);
      std::istream::~istream<char,std::char_traits<char>>(v29);
      std::ios::~ios<char,std::char_traits<char>>(v30);
      v11 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
        goto LABEL_31;
      return a1;
    }
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    *a1 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    *(__int64 *)((char *)&v26 + *(int *)(v26 + 4)) = (__int64)&std::ifstream::`vftable';
    *(_DWORD *)((char *)&v25[1] + *(int *)(v26 + 4) + 4) = *(_DWORD *)(v26 + 4) - 176;
    std::filebuf::~filebuf<char,std::char_traits<char>>(v28);
    std::istream::~istream<char,std::char_traits<char>>(v29);
    std::ios::~ios<char,std::char_traits<char>>(v30);
  }
  else
  {
    v5 = ATL::CAtlStringMgr::GetInstance();
    if ( !v5 )
      ATL::AtlThrowImpl(-2147467259);
    *a1 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v5 + 24LL))(v5) + 24;
  }
  v11 = pszPath - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
  {
LABEL_31:
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
  return a1;
}

```

## disassembly

```asm
0x14000972c  mov     [rsp-8+arg_10], rbx
0x140009731  mov     [rsp-8+arg_18], rsi
0x140009736  push    rbp
0x140009737  push    rdi
0x140009738  push    r12
0x14000973a  push    r14
0x14000973c  push    r15
0x14000973e  lea     rbp, [rsp-80h]
0x140009743  sub     rsp, 180h
0x14000974a  mov     rax, cs:__security_cookie
0x140009751  xor     rax, rsp
0x140009754  mov     [rbp+0A0h+var_28], rax
0x140009758  mov     r15, rcx
0x14000975b  mov     [rsp+1A0h+var_160], rcx
0x140009760  and     [rsp+1A0h+pszPath], 0
0x140009766  lea     rcx, [rsp+1A0h+var_160]
0x14000976b  call    ?GetLocalAppDataStoragePath@CAppIdExtImpl@@KA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CAppIdExtImpl::GetLocalAppDataStoragePath(ushort const *)
0x140009770  mov     rdx, [rax]
0x140009773  lea     rcx, [rsp+1A0h+pszPath]
0x140009778  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000977d  mov     rdx, [rsp+1A0h+var_160]
0x140009782  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009786  or      esi, 0FFFFFFFFh
0x140009789  mov     eax, esi
0x14000978b  lock xadd [rdx+10h], eax
0x140009790  add     eax, esi
0x140009792  test    eax, eax
0x140009794  jg      short loc_1400097A2
0x140009796  lfence
0x140009799  mov     rcx, [rdx]
0x14000979c  mov     rax, [rcx]
0x14000979f  call    qword ptr [rax+8]
0x1400097a2  lea     rdx, aExcludeddirect; "ExcludedDirectories.lst"
0x1400097a9  lea     rcx, [rsp+1A0h+pszPath]
0x1400097ae  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x1400097b3  mov     rcx, [rsp+1A0h+pszPath]; pszPath
0x1400097b8  call    cs:__imp_PathFileExistsW
0x1400097be  test    eax, eax
0x1400097c0  jnz     short loc_1400097E5
0x1400097c2  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400097c7  mov     rcx, rax
0x1400097ca  test    rax, rax
0x1400097cd  jz      loc_140009B02
0x1400097d3  mov     rax, [rax]
0x1400097d6  call    qword ptr [rax+18h]
0x1400097d9  add     rax, 18h
0x1400097dd  mov     [r15], rax
0x1400097e0  jmp     loc_1400098E6
0x1400097e5  xor     edx, edx; Val
0x1400097e7  mov     r8d, 110h; Size
0x1400097ed  lea     rcx, [rsp+1A0h+var_150]; void *
0x1400097f2  call    memset_0
0x1400097f7  mov     rdx, [rsp+1A0h+pszPath]
0x1400097fc  lea     rcx, [rsp+1A0h+var_150]
0x140009801  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x140009806  nop
0x140009807  mov     ebx, 1
0x14000980c  lea     edi, [rbx+1]
0x14000980f  jmp     short loc_140009861
0x140009811  mov     eax, ebx
0x140009813  inc     ebx
0x140009815  cmp     eax, 0Ah
0x140009818  jge     short loc_140009871
0x14000981a  mov     r9d, 20h ; ' '
0x140009820  lea     r8d, [r9+1]
0x140009824  mov     rdx, [rsp+1A0h+pszPath]
0x140009829  lea     rcx, [rsp+1A0h+var_140]
0x14000982e  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z; std::filebuf::open(ushort const *,int,int)
0x140009833  xor     r8d, r8d
0x140009836  test    rax, rax
0x140009839  mov     rax, [rsp+1A0h+var_150]
0x14000983e  movsxd  rcx, dword ptr [rax+4]
0x140009842  lea     rax, [rsp+1A0h+var_150]
0x140009847  jz      short loc_140009856
0x140009849  add     rcx, rax
0x14000984c  xor     edx, edx
0x14000984e  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x140009854  jmp     short loc_140009861
0x140009856  add     rcx, rax
0x140009859  mov     edx, edi
0x14000985b  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140009861  mov     rcx, [rsp+1A0h+var_150]
0x140009866  movsxd  rax, dword ptr [rcx+4]
0x14000986a  test    [rsp+rax+1A0h+var_140], dil
0x14000986f  jnz     short loc_140009811
0x140009871  movsxd  rax, dword ptr [rcx+4]
0x140009875  test    [rsp+rax+1A0h+var_140], dil
0x14000987a  jz      loc_140009911
0x140009880  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140009885  mov     rcx, rax
0x140009888  test    rax, rax
0x14000988b  jz      loc_140009AF4
0x140009891  mov     rax, [rax]
0x140009894  call    qword ptr [rax+18h]
0x140009897  add     rax, 18h
0x14000989b  mov     [r15], rax
0x14000989e  mov     rax, [rsp+1A0h+var_150]
0x1400098a3  movsxd  rcx, dword ptr [rax+4]
0x1400098a7  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x1400098ae  mov     [rsp+rcx+1A0h+var_150], rax
0x1400098b3  mov     rax, [rsp+1A0h+var_150]
0x1400098b8  movsxd  rcx, dword ptr [rax+4]
0x1400098bc  lea     edx, [rcx-0B0h]
0x1400098c2  mov     [rsp+rcx+1A0h+var_154], edx
0x1400098c6  lea     rcx, [rsp+1A0h+var_140]
0x1400098cb  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x1400098d0  lea     rcx, [rsp+1A0h+var_138]
0x1400098d5  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x1400098db  lea     rcx, [rbp+0A0h+var_A0]
0x1400098df  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x1400098e5  nop
0x1400098e6  mov     rdx, [rsp+1A0h+pszPath]
0x1400098eb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400098ef  mov     eax, esi
0x1400098f1  lock xadd [rdx+10h], eax
0x1400098f6  add     eax, esi
0x1400098f8  test    eax, eax
0x1400098fa  jg      loc_140009AC2
0x140009900  lfence
0x140009903  mov     rcx, [rdx]
0x140009906  mov     rax, [rcx]
0x140009909  call    qword ptr [rax+8]
0x14000990c  jmp     loc_140009AC2
0x140009911  mov     r8d, esi
0x140009914  mov     rdx, 7FFFFFFFFFFFFFFFh
0x14000991e  lea     rcx, [rsp+1A0h+var_150]
0x140009923  call    cs:__imp_?ignore@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::ignore(__int64,int)
0x140009929  mov     rbx, [rsp+1A0h+var_148]
0x14000992e  mov     rax, [rsp+1A0h+var_150]
0x140009933  movsxd  rcx, dword ptr [rax+4]
0x140009937  lea     rax, [rsp+1A0h+var_150]
0x14000993c  add     rcx, rax
0x14000993f  xor     r8d, r8d
0x140009942  xor     edx, edx
0x140009944  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x14000994a  xor     r8d, r8d
0x14000994d  xor     edx, edx
0x14000994f  lea     rcx, [rsp+1A0h+var_150]
0x140009954  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x14000995a  xorps   xmm0, xmm0
0x14000995d  lea     eax, [rbx+1]
0x140009960  mov     esi, eax
0x140009962  movdqu  [rbp+0A0h+var_40], xmm0
0x140009967  xor     edi, edi
0x140009969  mov     [rbp+0A0h+var_30], rdi
0x14000996d  xor     r12d, r12d
0x140009970  xor     ebx, ebx
0x140009972  test    eax, eax
0x140009974  jz      short loc_1400099B8
0x140009976  lfence
0x140009979  mov     ecx, esi; Size
0x14000997b  cmp     rsi, 1000h
0x140009982  jb      short loc_14000998B
0x140009984  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x140009989  jmp     short loc_140009990
0x14000998b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009990  mov     rbx, rax
0x140009993  mov     r14, rax
0x140009996  mov     qword ptr [rbp+0A0h+var_40], rax
0x14000999a  lea     rdi, [rax+rsi]
0x14000999e  mov     r12, rdi
0x1400099a1  mov     [rbp+0A0h+var_30], rdi
0x1400099a5  mov     r8, rsi; Size
0x1400099a8  xor     edx, edx; Val
0x1400099aa  mov     rcx, rax; void *
0x1400099ad  call    memset_0
0x1400099b2  mov     qword ptr [rbp+0A0h+var_40+8], rdi
0x1400099b6  jmp     short loc_1400099BC
0x1400099b8  mov     r14, qword ptr [rbp+0A0h+var_40]
0x1400099bc  sub     r12, rbx
0x1400099bf  mov     r8, r12
0x1400099c2  mov     rdx, r14
0x1400099c5  lea     rcx, [rsp+1A0h+var_150]
0x1400099ca  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1400099d0  and     [rsp+1A0h+var_168], 0
0x1400099d6  mov     rdx, r14
0x1400099d9  lea     rcx, [rsp+1A0h+var_168]
0x1400099de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x1400099e3  nop
0x1400099e4  mov     rcx, [rsp+1A0h+var_168]
0x1400099e9  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1400099ed  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400099f2  add     rax, 18h
0x1400099f6  mov     [r15], rax
0x1400099f9  mov     rdx, [rsp+1A0h+var_168]
0x1400099fe  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009a02  or      esi, 0FFFFFFFFh
0x140009a05  mov     eax, esi
0x140009a07  lock xadd [rdx+10h], eax
0x140009a0c  add     eax, esi
0x140009a0e  test    eax, eax
0x140009a10  jg      short loc_140009A1F
0x140009a12  lfence
0x140009a15  mov     rcx, [rdx]
0x140009a18  mov     rax, [rcx]
0x140009a1b  call    qword ptr [rax+8]
0x140009a1e  nop
0x140009a1f  test    rbx, rbx
0x140009a22  jz      short loc_140009A58
0x140009a24  sub     rdi, rbx
0x140009a27  cmp     rdi, 1000h
0x140009a2e  jb      short loc_140009A4C
0x140009a30  add     rdi, 27h ; '''
0x140009a34  mov     rcx, [rbx-8]
0x140009a38  sub     rbx, rcx
0x140009a3b  lea     rax, [rbx-8]
0x140009a3f  cmp     rax, 1Fh
0x140009a43  ja      loc_140009AED
0x140009a49  mov     rbx, rcx
0x140009a4c  mov     rdx, rdi; struct std::nothrow_t *
0x140009a4f  mov     rcx, rbx; void *
0x140009a52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009a57  nop
0x140009a58  mov     rax, [rsp+1A0h+var_150]
0x140009a5d  movsxd  rcx, dword ptr [rax+4]
0x140009a61  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x140009a68  mov     [rsp+rcx+1A0h+var_150], rax
0x140009a6d  mov     rax, [rsp+1A0h+var_150]
0x140009a72  movsxd  rcx, dword ptr [rax+4]
0x140009a76  lea     edx, [rcx-0B0h]
0x140009a7c  mov     [rsp+rcx+1A0h+var_154], edx
0x140009a80  lea     rcx, [rsp+1A0h+var_140]
0x140009a85  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x140009a8a  lea     rcx, [rsp+1A0h+var_138]
0x140009a8f  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x140009a95  lea     rcx, [rbp+0A0h+var_A0]
0x140009a99  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x140009a9f  mov     rdx, [rsp+1A0h+pszPath]
0x140009aa4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009aa8  mov     ecx, esi
0x140009aaa  lock xadd [rdx+10h], ecx
0x140009aaf  add     ecx, esi
0x140009ab1  test    ecx, ecx
0x140009ab3  jg      short loc_140009AC2
0x140009ab5  lfence
0x140009ab8  mov     rcx, [rdx]
0x140009abb  mov     r8, [rcx]
0x140009abe  call    qword ptr [r8+8]
0x140009ac2  mov     rax, r15
0x140009ac5  mov     rcx, [rbp+0A0h+var_28]
0x140009ac9  xor     rcx, rsp; StackCookie
0x140009acc  call    __security_check_cookie
0x140009ad1  lea     r11, [rsp+1A0h+var_20]
0x140009ad9  mov     rbx, [r11+40h]
0x140009add  mov     rsi, [r11+48h]
0x140009ae1  mov     rsp, r11
0x140009ae4  pop     r15
0x140009ae6  pop     r14
0x140009ae8  pop     r12
0x140009aea  pop     rdi
0x140009aeb  pop     rbp
0x140009aec  retn
0x140009aed  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x140009af4  mov     ecx, 80004005h; int
0x140009af9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009aff  jmp     short $+2
0x140009b01  nop
0x140009b02  mov     ecx, 80004005h; int
0x140009b07  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
