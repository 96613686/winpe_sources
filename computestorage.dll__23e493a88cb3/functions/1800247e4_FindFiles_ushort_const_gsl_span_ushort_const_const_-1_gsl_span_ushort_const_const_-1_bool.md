# FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)

- ea: `0x1800247e4`
- end: `0x180024c05`
- name: `?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z`
- size: `1057`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, _QWORD *, _QWORD *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024f88`
- `0x180027668`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180008fac`
- `0x18000a578`
- `0x180012818`
- `0x1800138b4`
- `0x180013d30`
- `0x180022228`
- `0x1800247e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a7d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024b6d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024b6d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024956`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024956`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180024aa3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180024aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b41`

## string_xrefs

- `0x180024bd1`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180024bed`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
__int64 __fastcall FindFiles(__int64 a1, const WCHAR *a2, _QWORD *a3, _QWORD *a4, char a5)
{
  PCWSTR *v8; // rbx
  PCWSTR *v9; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  const WCHAR *v13; // rdx
  const WCHAR *v14; // rcx
  char *FirstFileW; // rbx
  const WCHAR *v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  char **v19; // rcx
  _QWORD *v20; // rdi
  gsl::details *v21; // rdx
  gsl::details *v22; // rcx
  gsl::details *v23; // rax
  __int64 *v24; // r15
  _QWORD *v25; // r14
  DWORD LastError; // eax
  const WCHAR *v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  DWORD v30; // eax
  _QWORD Src[4]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v33[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  PCWSTR pszPathIn[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-60h]
  LPCWSTR lpFileName[4]; // [rsp+B0h] [rbp-50h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v34 = 0;
  v35 = 0;
  v8 = (PCWSTR *)a3[1];
  v9 = &v8[*a3];
  while ( v8 != v9 )
  {
    v10 = Vml::CombineFilePath(lpFileName, a2, *v8);
    v11 = *((_QWORD *)&v34 + 1);
    if ( *((_QWORD *)&v34 + 1) == v35 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v34, *((_QWORD *)&v34 + 1), v10);
    }
    else
    {
      **((_OWORD **)&v34 + 1) = 0;
      *(_QWORD *)(v11 + 16) = 0;
      *(_QWORD *)(v11 + 24) = 0;
      *(_OWORD *)v11 = *(_OWORD *)v10;
      *(_OWORD *)(v11 + 16) = *((_OWORD *)v10 + 1);
      v10[2] = 0;
      v10[3] = 7;
      *(_WORD *)v10 = 0;
      *((_QWORD *)&v34 + 1) += 32LL;
    }
    std::wstring::~wstring((char **)lpFileName);
    ++v8;
  }
  while ( 1 )
  {
    v12 = *((_QWORD *)&v34 + 1);
    if ( (_QWORD)v34 == *((_QWORD *)&v34 + 1) )
      break;
    *(_OWORD *)pszPathIn = 0;
    v37 = 0;
    *(_OWORD *)pszPathIn = *(_OWORD *)(*((_QWORD *)&v34 + 1) - 32LL);
    v37 = *(_OWORD *)(*((_QWORD *)&v34 + 1) - 16LL);
    *(_QWORD *)(*((_QWORD *)&v34 + 1) - 16LL) = 0;
    *(_QWORD *)(v12 - 8) = 7;
    *(_WORD *)(v12 - 32) = 0;
    std::wstring::~wstring((char **)(*((_QWORD *)&v34 + 1) - 32LL));
    *((_QWORD *)&v34 + 1) -= 32LL;
    v13 = (const WCHAR *)pszPathIn;
    if ( *((_QWORD *)&v37 + 1) > 7u )
      v13 = pszPathIn[0];
    Vml::CombineFilePath(lpFileName, v13, L"*");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v14 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v14 = lpFileName[0];
    FirstFileW = (char *)FindFirstFileW(v14, &FindFileData);
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( !a5
            || FindFileData.cFileName[0] == 46 && !FindFileData.cFileName[1]
            || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2] )
          {
            goto LABEL_37;
          }
          v16 = (const WCHAR *)pszPathIn;
          if ( *((_QWORD *)&v37 + 1) > 7u )
            v16 = pszPathIn[0];
          v17 = Vml::CombineFilePath(Src, v16, FindFileData.cFileName);
          v18 = *((_QWORD *)&v34 + 1);
          if ( *((_QWORD *)&v34 + 1) == v35 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v34, *((_QWORD *)&v34 + 1), v17);
          }
          else
          {
            **((_OWORD **)&v34 + 1) = 0;
            *(_QWORD *)(v18 + 16) = 0;
            *(_QWORD *)(v18 + 24) = 0;
            *(_OWORD *)v18 = *(_OWORD *)v17;
            *(_OWORD *)(v18 + 16) = *((_OWORD *)v17 + 1);
            v17[2] = 0;
            v17[3] = 7;
            *(_WORD *)v17 = 0;
            *((_QWORD *)&v34 + 1) += 32LL;
          }
          v19 = (char **)Src;
        }
        else
        {
          v20 = (_QWORD *)a4[1];
          v21 = 0;
          v22 = 0;
          if ( !FindFileData.cFileName[0] )
            goto LABEL_32;
          do
          {
            v23 = v22;
            if ( FindFileData.cFileName[(_QWORD)v22] != 46 )
              v23 = v21;
            v21 = v23;
            v22 = (gsl::details *)((char *)v22 + 1);
          }
          while ( FindFileData.cFileName[(_QWORD)v22] );
          if ( v23 )
            v24 = (__int64 *)&FindFileData.cAlternateFileName[(_QWORD)v23 - 259];
          else
LABEL_32:
            v24 = &qword_18004C4D0;
          v25 = &v20[*a4];
          if ( v20 > v25 )
          {
            gsl::details::terminate(v22);
            JUMPOUT(0x180024C04LL);
          }
          if ( v20 == v25 )
            goto LABEL_37;
          while ( (unsigned int)_o__wcsicmp(v24, *v20) )
          {
            if ( ++v20 == v25 )
              goto LABEL_37;
          }
          v27 = (const WCHAR *)pszPathIn;
          if ( *((_QWORD *)&v37 + 1) > 7u )
            v27 = pszPathIn[0];
          v28 = Vml::CombineFilePath(v33, v27, FindFileData.cFileName);
          v29 = *(_QWORD *)(a1 + 8);
          if ( v29 == *(_QWORD *)(a1 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v29, v28);
          }
          else
          {
            *(_OWORD *)v29 = 0;
            *(_QWORD *)(v29 + 16) = 0;
            *(_QWORD *)(v29 + 24) = 0;
            *(_OWORD *)v29 = *(_OWORD *)v28;
            *(_OWORD *)(v29 + 16) = *((_OWORD *)v28 + 1);
            v28[2] = 0;
            v28[3] = 7;
            *(_WORD *)v28 = 0;
            *(_QWORD *)(a1 + 8) += 32LL;
          }
          v19 = (char **)v33;
        }
        std::wstring::~wstring(v19);
LABEL_37:
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          LastError = GetLastError();
          if ( LastError != 18 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x80,
              (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
              (const char *)LastError,
              1u);
          goto LABEL_48;
        }
      }
    }
    v30 = GetLastError();
    if ( ((v30 - 2) & 0xFFFFFFFC) != 0 || v30 == 4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)v30,
        1u);
LABEL_48:
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(FirstFileW);
    std::wstring::~wstring((char **)lpFileName);
    std::wstring::~wstring((char **)pszPathIn);
  }
  std::vector<std::wstring>::_Tidy(&v34);
  return a1;
}

```

## disassembly

```asm
0x1800247e4  mov     [rsp-8+arg_18], rbx
0x1800247e9  push    rbp
0x1800247ea  push    rsi
0x1800247eb  push    rdi
0x1800247ec  push    r12
0x1800247ee  push    r13
0x1800247f0  push    r14
0x1800247f2  push    r15
0x1800247f4  lea     rbp, [rsp-230h]
0x1800247fc  sub     rsp, 330h
0x180024803  mov     rax, cs:__security_cookie
0x18002480a  xor     rax, rsp
0x18002480d  mov     [rbp+260h+var_40], rax
0x180024814  mov     r12, r9
0x180024817  mov     r14, rdx
0x18002481a  mov     rsi, rcx
0x18002481d  mov     [rsp+360h+var_338], rcx
0x180024822  xor     r13d, r13d
0x180024825  mov     [rsp+360h+var_340], r13d
0x18002482a  xorps   xmm0, xmm0
0x18002482d  movups  xmmword ptr [rcx], xmm0
0x180024830  mov     [rcx], r13
0x180024833  mov     [rcx+8], r13
0x180024837  mov     [rcx+10h], r13
0x18002483b  mov     [rsp+360h+var_340], 1
0x180024843  xorps   xmm1, xmm1
0x180024846  movdqu  [rsp+360h+var_2E8], xmm1
0x18002484c  mov     [rbp+260h+var_2D8], r13
0x180024850  mov     rbx, [r8+8]
0x180024854  mov     rax, [r8]
0x180024857  lea     rdi, [rbx+rax*8]
0x18002485b  lea     r15d, [r13+7]
0x18002485f  jmp     short loc_1800248C4
0x180024861  mov     r8, [rbx]; pszMore
0x180024864  mov     rdx, r14; pszPathIn
0x180024867  lea     rcx, [rbp+260h+lpFileName]; Src
0x18002486b  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z
0x180024870  mov     r8, rax
0x180024873  mov     rdx, qword ptr [rbp+260h+var_2E8+8]
0x180024877  cmp     rdx, [rbp+260h+var_2D8]
0x18002487b  jz      short loc_1800248AC
0x18002487d  xorps   xmm0, xmm0
0x180024880  movups  xmmword ptr [rdx], xmm0
0x180024883  mov     [rdx+10h], r13
0x180024887  mov     [rdx+18h], r13
0x18002488b  movups  xmm0, xmmword ptr [rax]
0x18002488e  movups  xmmword ptr [rdx], xmm0
0x180024891  movups  xmm1, xmmword ptr [rax+10h]
0x180024895  movups  xmmword ptr [rdx+10h], xmm1
0x180024899  mov     [rax+10h], r13
0x18002489d  mov     [rax+18h], r15
0x1800248a1  mov     [rax], r13w
0x1800248a5  add     qword ptr [rbp+260h+var_2E8+8], 20h ; ' '
0x1800248aa  jmp     short loc_1800248B7
0x1800248ac  lea     rcx, [rsp+360h+var_2E8]
0x1800248b1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z
0x1800248b6  nop
0x1800248b7  lea     rcx, [rbp+260h+lpFileName]
0x1800248bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800248c0  add     rbx, 8
0x1800248c4  cmp     rbx, rdi
0x1800248c7  jnz     short loc_180024861
0x1800248c9  mov     rcx, qword ptr [rbp+260h+var_2E8+8]
0x1800248cd  cmp     qword ptr [rsp+360h+var_2E8], rcx
0x1800248d2  jz      loc_180024B92
0x1800248d8  xorps   xmm0, xmm0
0x1800248db  movups  xmmword ptr [rbp+260h+pszPathIn], xmm0
0x1800248df  xorps   xmm1, xmm1
0x1800248e2  movdqu  [rbp+260h+var_2C0], xmm1
0x1800248e7  movups  xmm0, xmmword ptr [rcx-20h]
0x1800248eb  movups  xmmword ptr [rbp+260h+pszPathIn], xmm0
0x1800248ef  movups  xmm1, xmmword ptr [rcx-10h]
0x1800248f3  movups  [rbp+260h+var_2C0], xmm1
0x1800248f7  mov     [rcx-10h], r13
0x1800248fb  mov     [rcx-8], r15
0x1800248ff  mov     [rcx-20h], r13w
0x180024904  mov     rcx, qword ptr [rbp+260h+var_2E8+8]
0x180024908  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18002490c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180024911  sub     qword ptr [rbp+260h+var_2E8+8], 20h ; ' '
0x180024916  lea     rdx, [rbp+260h+pszPathIn]
0x18002491a  cmp     qword ptr [rbp+260h+var_2C0+8], r15
0x18002491e  cmova   rdx, [rbp+260h+pszPathIn]; pszPathIn
0x180024923  lea     r8, asc_18004E954
0x18002492a  lea     rcx, [rbp+260h+lpFileName]; Src
0x18002492e  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z
0x180024933  nop
0x180024934  xor     edx, edx; Val
0x180024936  mov     r8d, 250h; Size
0x18002493c  lea     rcx, [rbp+260h+FindFileData]; void *
0x180024940  call    memset_0
0x180024945  lea     rcx, [rbp+260h+lpFileName]
0x180024949  cmp     [rbp+260h+var_298], r15
0x18002494d  cmova   rcx, [rbp+260h+lpFileName]; lpFileName
0x180024952  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x180024956  call    cs:__imp_FindFirstFileW
0x18002495d  nop     dword ptr [rax+rax+00h]
0x180024962  mov     rbx, rax
0x180024965  mov     [rsp+360h+var_330], rax
0x18002496a  dec     rax
0x18002496d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024971  ja      loc_180024B41
0x180024977  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x18002497b  jz      loc_180024A21
0x180024981  cmp     [rbp+260h+arg_20], r13b
0x180024988  jz      loc_180024A9C
0x18002498e  movzx   eax, [rbp+260h+FindFileData.cFileName+2]
0x180024992  cmp     [rbp+260h+FindFileData.cFileName], 2Eh ; '.'
0x180024997  jnz     short loc_1800249A2
0x180024999  test    ax, ax
0x18002499c  jz      loc_180024A9C
0x1800249a2  cmp     ax, 2Eh ; '.'
0x1800249a6  jnz     short loc_1800249B3
0x1800249a8  cmp     [rbp+260h+FindFileData.cFileName+4], r13w
0x1800249ad  jz      loc_180024A9C
0x1800249b3  lea     rdx, [rbp+260h+pszPathIn]
0x1800249b7  cmp     qword ptr [rbp+260h+var_2C0+8], r15
0x1800249bb  cmova   rdx, [rbp+260h+pszPathIn]; pszPathIn
0x1800249c0  lea     r8, [rbp+260h+FindFileData.cFileName]; pszMore
0x1800249c4  lea     rcx, [rsp+360h+Src]; Src
0x1800249c9  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z
0x1800249ce  mov     r8, rax
0x1800249d1  mov     rdx, qword ptr [rbp+260h+var_2E8+8]
0x1800249d5  cmp     rdx, [rbp+260h+var_2D8]
0x1800249d9  jz      short loc_180024A0A
0x1800249db  xorps   xmm0, xmm0
0x1800249de  movups  xmmword ptr [rdx], xmm0
0x1800249e1  mov     [rdx+10h], r13
0x1800249e5  mov     [rdx+18h], r13
0x1800249e9  movups  xmm0, xmmword ptr [rax]
0x1800249ec  movups  xmmword ptr [rdx], xmm0
0x1800249ef  movups  xmm1, xmmword ptr [rax+10h]
0x1800249f3  movups  xmmword ptr [rdx+10h], xmm1
0x1800249f7  mov     [rax+10h], r13
0x1800249fb  mov     [rax+18h], r15
0x1800249ff  mov     [rax], r13w
0x180024a03  add     qword ptr [rbp+260h+var_2E8+8], 20h ; ' '
0x180024a08  jmp     short loc_180024A15
0x180024a0a  lea     rcx, [rsp+360h+var_2E8]
0x180024a0f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z
0x180024a14  nop
0x180024a15  lea     rcx, [rsp+360h+Src]
0x180024a1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180024a1f  jmp     short loc_180024A9C
0x180024a21  mov     r8, [r12]
0x180024a25  mov     rdi, [r12+8]
0x180024a2a  mov     rdx, r13
0x180024a2d  mov     rcx, r13; this
0x180024a30  cmp     [rbp+260h+FindFileData.cFileName], r13w
0x180024a35  jz      short loc_180024A61
0x180024a37  mov     rax, rcx
0x180024a3a  cmp     [rbp+rcx*2+260h+FindFileData.cFileName], 2Eh ; '.'
0x180024a40  cmovnz  rax, rdx
0x180024a44  mov     rdx, rax
0x180024a47  inc     rcx
0x180024a4a  cmp     [rbp+rcx*2+260h+FindFileData.cFileName], r13w
0x180024a50  jnz     short loc_180024A37
0x180024a52  test    rax, rax
0x180024a55  jz      short loc_180024A61
0x180024a57  lea     r15, [rbp+260h+FindFileData.cFileName+2]
0x180024a5b  lea     r15, [r15+rax*2]
0x180024a5f  jmp     short loc_180024A68
0x180024a61  lea     r15, qword_18004C4D0
0x180024a68  lea     r14, [rdi+r8*8]
0x180024a6c  cmp     rdi, r14
0x180024a6f  ja      loc_180024BFF
0x180024a75  jz      short loc_180024A96
0x180024a77  mov     rdx, [rdi]
0x180024a7a  mov     rcx, r15
0x180024a7d  call    cs:__imp__o__wcsicmp
0x180024a84  nop     dword ptr [rax+rax+00h]
0x180024a89  test    eax, eax
0x180024a8b  jz      short loc_180024AD1
0x180024a8d  add     rdi, 8
0x180024a91  cmp     rdi, r14
0x180024a94  jnz     short loc_180024A77
0x180024a96  mov     r15d, 7
0x180024a9c  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x180024aa0  mov     rcx, rbx; hFindFile
0x180024aa3  call    cs:__imp_FindNextFileW
0x180024aaa  nop     dword ptr [rax+rax+00h]
0x180024aaf  test    eax, eax
0x180024ab1  jnz     loc_180024977
0x180024ab7  call    cs:__imp_GetLastError
0x180024abe  nop     dword ptr [rax+rax+00h]
0x180024ac3  cmp     eax, 12h
0x180024ac6  jnz     loc_180024BE3
0x180024acc  jmp     loc_180024B60
0x180024ad1  lea     rdx, [rbp+260h+pszPathIn]
0x180024ad5  mov     r15d, 7
0x180024adb  cmp     qword ptr [rbp+260h+var_2C0+8], r15
0x180024adf  cmova   rdx, [rbp+260h+pszPathIn]; pszPathIn
0x180024ae4  lea     r8, [rbp+260h+FindFileData.cFileName]; pszMore
0x180024ae8  lea     rcx, [rsp+360h+var_308]; Src
0x180024aed  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z
0x180024af2  mov     r8, rax
0x180024af5  mov     rdx, [rsi+8]
0x180024af9  cmp     rdx, [rsi+10h]
0x180024afd  jz      short loc_180024B2E
0x180024aff  xorps   xmm0, xmm0
0x180024b02  movups  xmmword ptr [rdx], xmm0
0x180024b05  mov     [rdx+10h], r13
0x180024b09  mov     [rdx+18h], r13
0x180024b0d  movups  xmm0, xmmword ptr [rax]
0x180024b10  movups  xmmword ptr [rdx], xmm0
0x180024b13  movups  xmm1, xmmword ptr [rax+10h]
0x180024b17  movups  xmmword ptr [rdx+10h], xmm1
0x180024b1b  mov     [rax+10h], r13
0x180024b1f  mov     [rax+18h], r15
0x180024b23  mov     [rax], r13w
0x180024b27  add     qword ptr [rsi+8], 20h ; ' '
0x180024b2c  jmp     short loc_180024B37
0x180024b2e  mov     rcx, rsi
0x180024b31  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z
0x180024b36  nop
0x180024b37  lea     rcx, [rsp+360h+var_308]
0x180024b3c  jmp     loc_180024A1A
0x180024b41  call    cs:__imp_GetLastError
0x180024b48  nop     dword ptr [rax+rax+00h]
0x180024b4d  mov     r9d, eax; char *
0x180024b50  add     eax, 0FFFFFFFEh
0x180024b53  test    eax, 0FFFFFFFCh
0x180024b58  jnz     short loc_180024BCA
0x180024b5a  cmp     r9d, 4
0x180024b5e  jz      short loc_180024BCA
0x180024b60  lea     rax, [rbx-1]
0x180024b64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024b68  ja      short loc_180024B7A
0x180024b6a  mov     rcx, rbx; hFindFile
0x180024b6d  call    cs:__imp_FindClose
0x180024b74  nop     dword ptr [rax+rax+00h]
0x180024b79  nop
0x180024b7a  lea     rcx, [rbp+260h+lpFileName]
0x180024b7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180024b83  nop
0x180024b84  lea     rcx, [rbp+260h+pszPathIn]
0x180024b88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180024b8d  jmp     loc_1800248C9
0x180024b92  lea     rcx, [rsp+360h+var_2E8]
0x180024b97  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ
0x180024b9c  mov     rax, rsi
0x180024b9f  mov     rcx, [rbp+260h+var_40]
0x180024ba6  xor     rcx, rsp; StackCookie
0x180024ba9  call    __security_check_cookie
0x180024bae  mov     rbx, [rsp+360h+arg_18]
0x180024bb6  add     rsp, 330h
0x180024bbd  pop     r15
0x180024bbf  pop     r14
0x180024bc1  pop     r13
0x180024bc3  pop     r12
0x180024bc5  pop     rdi
0x180024bc6  pop     rsi
0x180024bc7  pop     rbp
0x180024bc8  retn
0x180024bca  mov     rcx, [rbp+268h]; this
0x180024bd1  lea     r8, aOnecoreVmCompu_4
0x180024bd8  mov     edx, 64h ; 'd'; void *
0x180024bdd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z
0x180024be3  mov     rcx, [rbp+268h]; this
0x180024bea  mov     r9d, eax; char *
0x180024bed  lea     r8, aOnecoreVmCompu_4
0x180024bf4  mov     edx, 80h; void *
0x180024bf9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z
0x180024bff  call    ?terminate@details@gsl@@YAXXZ
```
