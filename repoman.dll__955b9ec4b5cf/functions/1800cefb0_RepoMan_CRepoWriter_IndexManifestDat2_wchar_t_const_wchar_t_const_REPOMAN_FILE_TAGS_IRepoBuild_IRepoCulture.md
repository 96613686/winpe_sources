# RepoMan::CRepoWriter::IndexManifestDat2(wchar_t const *,wchar_t const *,_REPOMAN_FILE_TAGS,IRepoBuild *,IRepoCulture *)

- ea: `0x1800cefb0`
- end: `0x1800cf4bf`
- name: `?IndexManifestDat2@CRepoWriter@RepoMan@@UEAAJPEB_W0W4_REPOMAN_FILE_TAGS@@PEAUIRepoBuild@@PEAUIRepoCulture@@@Z`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180003710`
- `0x1800038ac`
- `0x180013b14`
- `0x18002d958`
- `0x18002e5bc`
- `0x18002f9b0`
- `0x1800c7574`
- `0x1800c819c`
- `0x1800cefb0`
- `0x1800cf4c0`
- `0x1800d0ca8`
- `0x18018aed8`
- `0x18018b5f0`
- `0x18018e288`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cf11a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cf356`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cf11a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800cf356`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cf113`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cf34f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cf113`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800cf34f`

## string_xrefs

- `0x1800cf43a`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cf460`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cf486`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cf4ac`: `src\repoman\src\repoman\repowriter.cpp`
- `0x1800cf433`: `invalid parameter: datPath`
- `0x1800ceff5`: `CRepoWriter.IndexManifestDat2`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RepoMan::CRepoWriter::IndexManifestDat2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // rax
  void *v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // eax
  const char *v15; // r9
  unsigned int v16; // esi
  void *v17; // rcx
  __int64 v18; // rcx
  int v19; // r8d
  __int64 result; // rax
  __int64 v21; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v22; // [rsp+38h] [rbp-1D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-1C8h]
  __int128 v24; // [rsp+50h] [rbp-1B8h] BYREF
  __int128 v25; // [rsp+60h] [rbp-1A8h]
  __int64 v26; // [rsp+70h] [rbp-198h]
  _BYTE v27[72]; // [rsp+78h] [rbp-190h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-148h]
  _BYTE v29[40]; // [rsp+C8h] [rbp-140h] BYREF
  int v30; // [rsp+F0h] [rbp-118h] BYREF
  __int128 v31; // [rsp+F4h] [rbp-114h]
  int v32; // [rsp+104h] [rbp-104h]
  __int64 v33; // [rsp+108h] [rbp-100h]
  __int64 v34; // [rsp+110h] [rbp-F8h]
  __int64 v35; // [rsp+118h] [rbp-F0h]
  __int64 v36; // [rsp+120h] [rbp-E8h]
  __int64 v37; // [rsp+128h] [rbp-E0h] BYREF
  void *Block[2]; // [rsp+130h] [rbp-D8h] BYREF
  __m128i v39; // [rsp+140h] [rbp-C8h]
  CHAR v40[16]; // [rsp+150h] [rbp-B8h] BYREF
  __m128i v41; // [rsp+160h] [rbp-A8h]
  CHAR MultiByteStr[16]; // [rsp+170h] [rbp-98h] BYREF
  __m128i si128; // [rsp+180h] [rbp-88h]
  _BYTE v44[48]; // [rsp+190h] [rbp-78h] BYREF

  v23 = a1;
  RepoMan::Tracer::Tracer(v44, 1, "CRepoWriter.IndexManifestDat2");
  try
  {
    if ( !a2 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        564,
        (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
        (unsigned int)"invalid parameter: datPath",
        -2147024809,
        8);
    if ( !a3 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        565,
        (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
        (unsigned int)"invalid parameter: mediaName",
        -2147024809,
        8);
    if ( !a5 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        566,
        (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
        (unsigned int)"invalid parameter: build",
        -2147024809,
        8);
    if ( !a6 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        567,
        (unsigned int)"src\\repoman\\src\\repoman\\repowriter.cpp",
        (unsigned int)"invalid parameter: culture",
        -2147024809,
        8);
    v22 = 0;
    *(_OWORD *)Block = 0;
    v39 = 0;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a2 + 2 * v10) );
    std::wstring::_Construct<1,wchar_t const *>(Block, a2, v10);
    v11 = RepoMan::utf16_to_utf8(MultiByteStr, (LPCWCH)Block);
    RepoMan::FileSystem::OpenFileAsStream(&v21, v11, 0, &v22, 0);
    std::string::_Tidy_deallocate(MultiByteStr);
    *(_QWORD *)MultiByteStr = 19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v39.m128i_i64[1] > 7uLL )
    {
      v12 = Block[0];
      if ( (unsigned __int64)(2 * v39.m128i_i64[1] + 2) >= 0x1000 )
      {
        v12 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v12);
    }
    Block[0] = (void *)19937;
    v39 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v24 = 0;
    v25 = 0u;
    v26 = 0;
    memset(v27, 0, sizeof(v27));
    v28 = 0;
    memset(v29, 0, sizeof(v29));
    v30 = 0;
    v31 = 0u;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v13 = v21;
    v37 = v21;
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      v13 = v37;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, 0, 0, 0);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v14, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v15);
    v16 = RepoMan::StreamBase<>::Size(v37);
    RepoMan::Legacy::StreamHeader::Read(&v30, &v37);
    *((_QWORD *)&v25 + 1) = (unsigned int)v31;
    v26 = v16;
    RepoMan::Meta::FieldNItems<RepoMan::Legacy::PackageFileData>::Read<>(&v24, &v37);
    *(_OWORD *)Block = 0;
    v39 = 0;
    do
      ++v9;
    while ( *(_WORD *)(a3 + 2 * v9) );
    std::wstring::_Construct<1,wchar_t const *>(Block, a3, v9);
    RepoMan::utf16_to_utf8(v40, (LPCWCH)Block);
    if ( v39.m128i_i64[1] > 7uLL )
    {
      v17 = Block[0];
      if ( (unsigned __int64)(2 * v39.m128i_i64[1] + 2) >= 0x1000 )
      {
        v17 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v17);
    }
    Block[0] = (void *)19937;
    v39 = _mm_load_si128((const __m128i *)&_xmm);
    RepoMan::Legacy::StreamManifest::Index((__int64 *)&v24, v40, v23, a5, a6, a4);
    std::string::_Tidy_deallocate(v40);
    *(_QWORD *)v40 = 19937;
    v41 = _mm_load_si128((const __m128i *)&_xmm);
    RepoMan::Legacy::StreamManifest::~StreamManifest((RepoMan::Legacy::StreamManifest *)&v24);
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v44);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\repoman\\repowriter.cpp", (const char *)0x23F, v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800cefb0  mov     r11, rsp
0x1800cefb3  push    rbx
0x1800cefb4  push    rsi
0x1800cefb5  push    rdi
0x1800cefb6  push    r12
0x1800cefb8  push    r13
0x1800cefba  push    r14
0x1800cefbc  push    r15
0x1800cefbe  sub     rsp, 1D0h
0x1800cefc5  mov     rax, cs:__security_cookie
0x1800cefcc  xor     rax, rsp
0x1800cefcf  mov     [rsp+208h+var_48], rax
0x1800cefd7  mov     r13d, r9d
0x1800cefda  mov     r14, r8
0x1800cefdd  mov     rsi, rdx
0x1800cefe0  mov     [rsp+208h+var_1C8], rcx
0x1800cefe5  mov     r15, [rsp+208h+arg_20]
0x1800cefed  mov     r12, [rsp+208h+arg_28]
0x1800ceff5  lea     r8, aCrepowriterInd; "CRepoWriter.IndexManifestDat2"
0x1800ceffc  mov     edx, 1
0x1800cf001  lea     rcx, [r11-78h]
0x1800cf005  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x1800cf00a  nop
0x1800cf00b  xor     ebx, ebx
0x1800cf00d  test    rsi, rsi
0x1800cf010  jz      loc_1800CF425
0x1800cf016  test    r14, r14
0x1800cf019  jz      loc_1800CF44B
0x1800cf01f  test    r15, r15
0x1800cf022  jz      loc_1800CF471
0x1800cf028  test    r12, r12
0x1800cf02b  jz      loc_1800CF497
0x1800cf031  mov     [rsp+208h+var_1D0], rbx
0x1800cf036  xorps   xmm0, xmm0
0x1800cf039  movups  xmmword ptr [rsp+208h+Block], xmm0
0x1800cf041  xorps   xmm1, xmm1
0x1800cf044  movdqu  [rsp+208h+var_C8], xmm1
0x1800cf04d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800cf051  mov     r8, rdi
0x1800cf054  inc     r8
0x1800cf057  cmp     [rsi+r8*2], bx
0x1800cf05c  jnz     short loc_1800CF054
0x1800cf05e  mov     rdx, rsi
0x1800cf061  lea     rcx, [rsp+208h+Block]
0x1800cf069  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cf06e  nop
0x1800cf06f  lea     rdx, [rsp+208h+Block]; lpWideCharStr
0x1800cf077  lea     rcx, [rsp+208h+MultiByteStr]; lpMultiByteStr
0x1800cf07f  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800cf084  nop
0x1800cf085  mov     byte ptr [rsp+208h+Reserved], bl
0x1800cf089  lea     r9, [rsp+208h+var_1D0]
0x1800cf08e  xor     r8d, r8d
0x1800cf091  mov     rdx, rax
0x1800cf094  lea     rcx, [rsp+208h+var_1D8]
0x1800cf099  call    ?OpenFileAsStream@FileSystem@RepoMan@@YA?AV?$ComPtr@UIStream@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@AEBV?$ComPtr@UIRepoProgress@@@2@W4OpenFlags@@@Z; RepoMan::FileSystem::OpenFileAsStream(std::string const &,RepoMan::FileSystem::OpenMode,RepoMan::ComPtr<IRepoProgress> const &,OpenFlags)
0x1800cf09e  nop
0x1800cf09f  lea     rcx, [rsp+208h+MultiByteStr]
0x1800cf0a7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cf0ac  mov     esi, 4DE1h
0x1800cf0b1  mov     qword ptr [rsp+208h+MultiByteStr], rsi
0x1800cf0b9  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800cf0c1  movdqu  [rsp+208h+var_88], xmm0
0x1800cf0ca  mov     rax, qword ptr [rsp+208h+var_C8+8]
0x1800cf0d2  cmp     rax, 7
0x1800cf0d6  jbe     short loc_1800CF120
0x1800cf0d8  mov     rcx, [rsp+208h+Block]; Block
0x1800cf0e0  mov     rdx, rcx
0x1800cf0e3  lea     rax, ds:2[rax*2]
0x1800cf0eb  cmp     rax, 1000h
0x1800cf0f1  jb      short loc_1800CF11A
0x1800cf0f3  mov     rcx, [rcx-8]
0x1800cf0f7  sub     rdx, rcx
0x1800cf0fa  lea     rax, [rdx-8]
0x1800cf0fe  cmp     rax, 1Fh
0x1800cf102  jbe     short loc_1800CF11A
0x1800cf104  mov     [rsp+208h+Reserved], rbx; Reserved
0x1800cf109  xor     r9d, r9d; LineNo
0x1800cf10c  xor     r8d, r8d; FileName
0x1800cf10f  xor     edx, edx; FunctionName
0x1800cf111  xor     ecx, ecx; Expression
0x1800cf113  call    cs:__imp__invoke_watson
0x1800cf11a  call    cs:__imp_free
0x1800cf120  mov     [rsp+208h+Block], rsi
0x1800cf128  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800cf130  movdqu  [rsp+208h+var_C8], xmm0
0x1800cf139  mov     rcx, [rsp+208h+var_1D0]
0x1800cf13e  test    rcx, rcx
0x1800cf141  jz      short loc_1800CF150
0x1800cf143  mov     rax, [rcx]
0x1800cf146  mov     rax, [rax+10h]
0x1800cf14a  call    cs:__guard_dispatch_icall_fptr
0x1800cf150  xorps   xmm0, xmm0
0x1800cf153  xor     eax, eax
0x1800cf155  movups  [rsp+208h+var_1A8], xmm0
0x1800cf15a  movdqa  [rsp+208h+var_1B8], xmm0
0x1800cf160  mov     qword ptr [rsp+208h+var_1A8], rbx
0x1800cf165  mov     qword ptr [rsp+208h+var_1A8+8], rbx
0x1800cf16a  mov     [rsp+208h+var_198], rbx
0x1800cf16f  movups  [rsp+208h+var_190], xmm0
0x1800cf174  movups  xmmword ptr [rsp+208h+var_180], xmm0
0x1800cf17c  mov     qword ptr [rsp+208h+var_190], rbx
0x1800cf181  movdqa  [rsp+208h+var_190+8], xmm0
0x1800cf18a  xorps   xmm1, xmm1
0x1800cf18d  movdqa  xmmword ptr [rsp+208h+var_180+8], xmm1
0x1800cf196  movdqa  [rsp+208h+var_168], xmm0
0x1800cf19f  movdqa  [rsp+208h+var_158], xmm1
0x1800cf1a8  mov     [rsp+208h+var_148], rbx
0x1800cf1b0  movups  [rsp+208h+var_140], xmm0
0x1800cf1b8  movups  xmmword ptr [rsp+208h+var_130], xmm0
0x1800cf1c0  mov     qword ptr [rsp+208h+var_140], rbx
0x1800cf1c8  movdqa  [rsp+208h+var_140+8], xmm0
0x1800cf1d1  movdqa  xmmword ptr [rsp+208h+var_130+8], xmm1
0x1800cf1da  movups  [rsp+208h+var_118], xmm0
0x1800cf1e2  movups  [rsp+208h+var_108], xmm0
0x1800cf1ea  mov     qword ptr [rsp+208h+var_118+4], rax
0x1800cf1f2  mov     qword ptr [rsp+208h+var_118+0Ch], rax
0x1800cf1fa  mov     dword ptr [rsp+208h+var_108+4], eax
0x1800cf201  mov     qword ptr [rsp+208h+var_108+8], rbx
0x1800cf209  mov     [rsp+208h+var_F8], rbx
0x1800cf211  mov     [rsp+208h+var_F0], rbx
0x1800cf219  mov     [rsp+208h+var_E8], rbx
0x1800cf221  mov     rcx, [rsp+208h+var_1D8]
0x1800cf226  mov     [rsp+208h+var_E0], rcx
0x1800cf22e  test    rcx, rcx
0x1800cf231  jz      short loc_1800CF248
0x1800cf233  mov     rax, [rcx]
0x1800cf236  mov     rax, [rax+8]
0x1800cf23a  call    cs:__guard_dispatch_icall_fptr
0x1800cf240  mov     rcx, [rsp+208h+var_E0]
0x1800cf248  mov     rax, [rcx]
0x1800cf24b  xor     r9d, r9d
0x1800cf24e  xor     r8d, r8d
0x1800cf251  mov     rdx, rbx
0x1800cf254  mov     rax, [rax+28h]
0x1800cf258  call    cs:__guard_dispatch_icall_fptr
0x1800cf25e  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x1800cf265  mov     edx, 169h; int
0x1800cf26a  mov     ecx, eax; this
0x1800cf26c  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800cf271  mov     rcx, [rsp+208h+var_E0]
0x1800cf279  call    ?Size@?$StreamBase@$$V@RepoMan@@SA_KPEAUIStream@@@Z; RepoMan::StreamBase<>::Size(IStream *)
0x1800cf27e  mov     rsi, rax
0x1800cf281  lea     rdx, [rsp+208h+var_E0]
0x1800cf289  lea     rcx, [rsp+208h+var_118]
0x1800cf291  call    ?Read@StreamHeader@Legacy@RepoMan@@QEAAXAEAV?$ComPtr@UIStream@@@3@@Z; RepoMan::Legacy::StreamHeader::Read(RepoMan::ComPtr<IStream> &)
0x1800cf296  mov     ecx, dword ptr [rsp+208h+var_118+4]
0x1800cf29d  mov     qword ptr [rsp+208h+var_1A8+8], rcx
0x1800cf2a2  mov     eax, esi
0x1800cf2a4  mov     [rsp+208h+var_198], rax
0x1800cf2a9  lea     rdx, [rsp+208h+var_E0]
0x1800cf2b1  lea     rcx, [rsp+208h+var_1B8]
0x1800cf2b6  call    ??$Read@$$V@?$FieldNItems@VPackageFileData@Legacy@RepoMan@@@Meta@RepoMan@@QEAAXAEAV?$ComPtr@UIStream@@@2@@Z; RepoMan::Meta::FieldNItems<RepoMan::Legacy::PackageFileData>::Read<>(RepoMan::ComPtr<IStream> &)
0x1800cf2bb  xorps   xmm0, xmm0
0x1800cf2be  movups  xmmword ptr [rsp+208h+Block], xmm0
0x1800cf2c6  xorps   xmm1, xmm1
0x1800cf2c9  movdqu  [rsp+208h+var_C8], xmm1
0x1800cf2d2  inc     rdi
0x1800cf2d5  cmp     [r14+rdi*2], bx
0x1800cf2da  jnz     short loc_1800CF2D2
0x1800cf2dc  mov     r8, rdi
0x1800cf2df  mov     rdx, r14
0x1800cf2e2  lea     rcx, [rsp+208h+Block]
0x1800cf2ea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800cf2ef  nop
0x1800cf2f0  lea     rdx, [rsp+208h+Block]; lpWideCharStr
0x1800cf2f8  lea     rcx, [rsp+208h+var_B8]; lpMultiByteStr
0x1800cf300  call    ?utf16_to_utf8@RepoMan@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; RepoMan::utf16_to_utf8(std::wstring const &)
0x1800cf305  nop
0x1800cf306  mov     rax, qword ptr [rsp+208h+var_C8+8]
0x1800cf30e  cmp     rax, 7
0x1800cf312  jbe     short loc_1800CF35C
0x1800cf314  mov     rcx, [rsp+208h+Block]; Block
0x1800cf31c  mov     rdx, rcx
0x1800cf31f  lea     rax, ds:2[rax*2]
0x1800cf327  cmp     rax, 1000h
0x1800cf32d  jb      short loc_1800CF356
0x1800cf32f  mov     rcx, [rcx-8]
0x1800cf333  sub     rdx, rcx
0x1800cf336  lea     rax, [rdx-8]
0x1800cf33a  cmp     rax, 1Fh
0x1800cf33e  jbe     short loc_1800CF356
0x1800cf340  mov     [rsp+208h+Reserved], rbx; Reserved
0x1800cf345  xor     r9d, r9d; LineNo
0x1800cf348  xor     r8d, r8d; FileName
0x1800cf34b  xor     edx, edx; FunctionName
0x1800cf34d  xor     ecx, ecx; Expression
0x1800cf34f  call    cs:__imp__invoke_watson
0x1800cf356  call    cs:__imp_free
0x1800cf35c  mov     edi, 4DE1h
0x1800cf361  mov     [rsp+208h+Block], rdi
0x1800cf369  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800cf371  movdqu  [rsp+208h+var_C8], xmm0
0x1800cf37a  mov     [rsp+208h+var_1E0], r13d
0x1800cf37f  mov     [rsp+208h+Reserved], r12
0x1800cf384  mov     r9, r15
0x1800cf387  mov     r8, [rsp+208h+var_1C8]
0x1800cf38c  lea     rdx, [rsp+208h+var_B8]
0x1800cf394  lea     rcx, [rsp+208h+var_1B8]
0x1800cf399  call    ?Index@StreamManifest@Legacy@RepoMan@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUIRepoWriter@@PEAUIRepoBuild@@PEAUIRepoCulture@@W4_REPOMAN_FILE_TAGS@@@Z; RepoMan::Legacy::StreamManifest::Index(std::string const &,IRepoWriter *,IRepoBuild *,IRepoCulture *,_REPOMAN_FILE_TAGS)
0x1800cf39e  nop
0x1800cf39f  lea     rcx, [rsp+208h+var_B8]
0x1800cf3a7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cf3ac  mov     qword ptr [rsp+208h+var_B8], rdi
0x1800cf3b4  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x1800cf3bc  movdqu  [rsp+208h+var_A8], xmm0
0x1800cf3c5  lea     rcx, [rsp+208h+var_1B8]; this
0x1800cf3ca  call    ??1StreamManifest@Legacy@RepoMan@@QEAA@XZ; RepoMan::Legacy::StreamManifest::~StreamManifest(void)
0x1800cf3cf  nop
0x1800cf3d0  mov     rcx, [rsp+208h+var_1D8]
0x1800cf3d5  test    rcx, rcx
0x1800cf3d8  jz      short loc_1800CF3ED
0x1800cf3da  mov     [rsp+208h+var_1D8], rbx
0x1800cf3df  mov     rax, [rcx]
0x1800cf3e2  mov     rax, [rax+10h]
0x1800cf3e6  call    cs:__guard_dispatch_icall_fptr
0x1800cf3ec  nop
0x1800cf3ed  lea     rcx, [rsp+208h+var_78]; this
0x1800cf3f5  call    ??1Tracer@RepoMan@@QEAA@XZ; RepoMan::Tracer::~Tracer(void)
0x1800cf3fa  xor     eax, eax
0x1800cf3fc  jmp     short loc_1800CF402
0x1800cf3fe  mov     eax, dword ptr [rsp+208h+var_1D8]
0x1800cf402  mov     rcx, [rsp+208h+var_48]
0x1800cf40a  xor     rcx, rsp; StackCookie
0x1800cf40d  call    __security_check_cookie
0x1800cf412  add     rsp, 1D0h
0x1800cf419  pop     r15
0x1800cf41b  pop     r14
0x1800cf41d  pop     r13
0x1800cf41f  pop     r12
0x1800cf421  pop     rdi
0x1800cf422  pop     rsi
0x1800cf423  pop     rbx
0x1800cf424  retn
0x1800cf425  mov     dword ptr [rsp+208h+Reserved], 8
0x1800cf42d  mov     r9d, 80070057h
0x1800cf433  lea     r8, aInvalidParamet_4; "invalid parameter: datPath"
0x1800cf43a  lea     rdx, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cf441  mov     ecx, 234h
0x1800cf446  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800cf44b  mov     dword ptr [rsp+208h+Reserved], 8
0x1800cf453  mov     r9d, 80070057h
0x1800cf459  lea     r8, aInvalidParamet_5; "invalid parameter: mediaName"
0x1800cf460  lea     rdx, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cf467  mov     ecx, 235h
0x1800cf46c  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800cf471  mov     dword ptr [rsp+208h+Reserved], 8
0x1800cf479  mov     r9d, 80070057h
0x1800cf47f  lea     r8, aInvalidParamet; "invalid parameter: build"
0x1800cf486  lea     rdx, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cf48d  mov     ecx, 236h
0x1800cf492  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800cf497  mov     dword ptr [rsp+208h+Reserved], 8
0x1800cf49f  mov     r9d, 80070057h
0x1800cf4a5  lea     r8, aInvalidParamet_1; "invalid parameter: culture"
0x1800cf4ac  lea     rdx, aSrcRepomanSrcR_10; "src\\repoman\\src\\repoman\\repowriter."...
0x1800cf4b3  mov     ecx, 237h
0x1800cf4b8  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
