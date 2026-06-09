# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x180014688`
- end: `0x1800149f7`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, const char *, const struct _GUID *, unsigned int, const struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800129cc`

## callees

- `0x180001800`
- `0x180009e70`
- `0x180009e98`
- `0x18000c6e4`
- `0x18000fe40`
- `0x18000ff28`
- `0x180010c1c`
- `0x1800110b4`
- `0x180014380`
- `0x180014688`
- `0x180014adc`
- `0x18001892c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014930`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014930`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800149ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800148af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800148af`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800146dc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014721`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001476c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800146dc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180014721`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001476c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001491d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001491d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014946`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014946`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001497d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001497d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014877`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014877`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        const char *a2,
        const struct _GUID *a3,
        int a4,
        DWORD *a5)
{
  _QWORD *v8; // r14
  const WCHAR *v9; // rbx
  unsigned int Error; // edi
  int v11; // ecx
  __int64 v12; // r8
  __int128 *p_Src; // rcx
  __int128 *v14; // rdx
  __int128 *v15; // r8
  HANDLE FileW; // r14
  signed int LastError; // eax
  DWORD LowPart; // esi
  LARGE_INTEGER v19; // rdi
  BOOL v20; // eax
  void *v21; // rcx
  char *v22; // r15
  LPCWSTR lpPathName; // [rsp+40h] [rbp-41h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+48h] [rbp-39h]
  __int128 Src; // [rsp+50h] [rbp-31h] BYREF
  __m128i v27; // [rsp+60h] [rbp-21h]
  __int128 v28; // [rsp+70h] [rbp-11h] BYREF
  __m128i si128; // [rsp+80h] [rbp-1h]

  v8 = (_QWORD *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 328);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    a2);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v11,
    (unsigned int)&lpPathName,
    *v8,
    (_DWORD)a2,
    (__int64)a3,
    a4);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  Src = 0;
  v27 = 0u;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  std::string::_Construct<1,char const *>(&Src, a2);
  p_Src = &Src;
  if ( v27.m128i_i64[1] > 0xFuLL )
    p_Src = (__int128 *)Src;
  if ( std::_Traits_rfind_ch<std::char_traits<char>>(p_Src, v27.m128i_i64[0]) != -1 )
  {
    v28 = 0;
    si128 = 0;
    v14 = &Src;
    if ( v27.m128i_i64[1] > 0xFuLL )
      v14 = (__int128 *)Src;
    std::string::_Construct<1,char const *>(&v28, v14);
    std::string::_Tidy_deallocate(&Src);
    Src = v28;
    v27 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v28) = 0;
    std::string::_Tidy_deallocate(&v28);
  }
  std::string::_Append<char>(&Src);
  v15 = &Src;
  if ( v27.m128i_i64[1] > 0xFuLL )
    v15 = (__int128 *)Src;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    v15);
  v9 = lpPathName;
  if ( GetFileAttributesW(lpPathName) != -1 )
    goto LABEL_35;
  FileW = CreateFileW(v9, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( FileW )
  {
    LowPart = *a5;
    liDistanceToMove.QuadPart = *a5;
    v19 = liDistanceToMove;
    v20 = SetFilePointerEx(FileW, liDistanceToMove, 0, 0);
    v21 = FileW;
    if ( !v20 )
    {
LABEL_24:
      CloseHandle(v21);
      goto LABEL_20;
    }
    SetFilePointer(FileW, 0, 0, 0);
    if ( LowPart > 0x10000 )
      LowPart = 0x10000;
    v22 = (char *)*((_QWORD *)a5 + 1);
    while ( LowPart )
    {
      LODWORD(lpPathName) = 0;
      if ( !WriteFile(FileW, v22, LowPart, (LPDWORD)&lpPathName, 0) )
      {
        v21 = FileW;
        goto LABEL_24;
      }
      v19.QuadPart -= (unsigned int)lpPathName;
      liDistanceToMove = v19;
      v22 += (unsigned int)lpPathName;
      LowPart = v19.LowPart;
      if ( v19.LowPart > 0x10000 )
        LowPart = 0x10000;
    }
    CloseHandle(FileW);
LABEL_35:
    std::string::_Tidy_deallocate(&Src);
    Error = 0;
    goto LABEL_36;
  }
  if ( GetLastError() == 80 )
    goto LABEL_35;
LABEL_20:
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  std::string::_Tidy_deallocate(&Src);
LABEL_36:
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  return Error;
}

```

## disassembly

```asm
0x180014688  mov     [rsp-8+arg_18], rbx
0x18001468d  push    rbp
0x18001468e  push    rsi
0x18001468f  push    rdi
0x180014690  push    r12
0x180014692  push    r13
0x180014694  push    r14
0x180014696  push    r15
0x180014698  lea     rbp, [rsp-1Fh]
0x18001469d  sub     rsp, 0A0h
0x1800146a4  mov     rax, cs:__security_cookie
0x1800146ab  xor     rax, rsp
0x1800146ae  mov     [rbp+4Fh+var_40], rax
0x1800146b2  mov     r15d, r9d
0x1800146b5  mov     r12, r8
0x1800146b8  mov     rsi, rdx
0x1800146bb  mov     r13, [rbp+4Fh+arg_20]
0x1800146bf  lea     r14, [rcx+148h]
0x1800146c6  mov     rdx, r14
0x1800146c9  lea     rcx, [rbp+4Fh+lpPathName]
0x1800146cd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800146d2  nop
0x1800146d3  xor     edx, edx; lpSecurityAttributes
0x1800146d5  mov     rbx, [rbp+4Fh+lpPathName]
0x1800146d9  mov     rcx, rbx; lpPathName
0x1800146dc  call    cs:__imp_CreateDirectoryW
0x1800146e3  nop     dword ptr [rax+rax+00h]
0x1800146e8  test    eax, eax
0x1800146ea  jnz     short loc_180014705
0x1800146ec  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800146f1  mov     edi, eax
0x1800146f3  mov     ecx, 0B7h; unsigned int
0x1800146f8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800146fd  cmp     edi, eax
0x1800146ff  jnz     loc_1800149C4
0x180014705  mov     r8, rsi
0x180014708  lea     rdx, aHs_0; "\\%hs"
0x18001470f  lea     rcx, [rbp+4Fh+lpPathName]
0x180014713  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180014718  xor     edx, edx; lpSecurityAttributes
0x18001471a  mov     rbx, [rbp+4Fh+lpPathName]
0x18001471e  mov     rcx, rbx; lpPathName
0x180014721  call    cs:__imp_CreateDirectoryW
0x180014728  nop     dword ptr [rax+rax+00h]
0x18001472d  test    eax, eax
0x18001472f  jnz     short loc_18001474A
0x180014731  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180014736  mov     edi, eax
0x180014738  mov     ecx, 0B7h; unsigned int
0x18001473d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180014742  cmp     edi, eax
0x180014744  jnz     loc_1800149C4
0x18001474a  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d
0x18001474f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12
0x180014754  mov     r9, rsi
0x180014757  mov     r8, [r14]
0x18001475a  lea     rdx, [rbp+4Fh+lpPathName]
0x18001475e  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x180014763  xor     edx, edx; lpSecurityAttributes
0x180014765  mov     rbx, [rbp+4Fh+lpPathName]
0x180014769  mov     rcx, rbx; lpPathName
0x18001476c  call    cs:__imp_CreateDirectoryW
0x180014773  nop     dword ptr [rax+rax+00h]
0x180014778  xor     r12d, r12d
0x18001477b  test    eax, eax
0x18001477d  jnz     short loc_180014798
0x18001477f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180014784  mov     edi, eax
0x180014786  mov     ecx, 0B7h; unsigned int
0x18001478b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180014790  cmp     edi, eax
0x180014792  jnz     loc_1800149C4
0x180014798  xorps   xmm0, xmm0
0x18001479b  movups  [rbp+4Fh+Src], xmm0
0x18001479f  mov     qword ptr [rbp+4Fh+var_70], r12
0x1800147a3  mov     qword ptr [rbp+4Fh+var_70+8], r12
0x1800147a7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800147ab  inc     r8
0x1800147ae  cmp     [rsi+r8], r12b
0x1800147b2  jnz     short loc_1800147AB
0x1800147b4  mov     rdx, rsi
0x1800147b7  lea     rcx, [rbp+4Fh+Src]
0x1800147bb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800147c0  nop
0x1800147c1  lea     rcx, [rbp+4Fh+Src]
0x1800147c5  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x1800147ca  cmova   rcx, qword ptr [rbp+4Fh+Src]
0x1800147cf  mov     rdx, qword ptr [rbp+4Fh+var_70]
0x1800147d3  call    ??$_Traits_rfind_ch@U?$char_traits@D@std@@@std@@YA_KQEBD_K1D@Z; std::_Traits_rfind_ch<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char)
0x1800147d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800147dc  jz      short loc_180014843
0x1800147de  xorps   xmm0, xmm0
0x1800147e1  movups  [rbp+4Fh+var_60], xmm0
0x1800147e5  xorps   xmm1, xmm1
0x1800147e8  movdqu  [rbp+4Fh+var_50], xmm1
0x1800147ed  cmp     qword ptr [rbp+4Fh+var_70], rax
0x1800147f1  cmovb   rax, qword ptr [rbp+4Fh+var_70]
0x1800147f6  lea     rdx, [rbp+4Fh+Src]
0x1800147fa  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x1800147ff  cmova   rdx, qword ptr [rbp+4Fh+Src]
0x180014804  mov     r8, rax
0x180014807  lea     rcx, [rbp+4Fh+var_60]
0x18001480b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180014810  lea     rcx, [rbp+4Fh+Src]
0x180014814  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014819  movups  xmm0, [rbp+4Fh+var_60]
0x18001481d  movups  [rbp+4Fh+Src], xmm0
0x180014821  movups  xmm1, [rbp+4Fh+var_50]
0x180014825  movups  [rbp+4Fh+var_70], xmm1
0x180014829  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180014831  movdqu  [rbp+4Fh+var_50], xmm0
0x180014836  mov     byte ptr [rbp+4Fh+var_60], r12b
0x18001483a  lea     rcx, [rbp+4Fh+var_60]
0x18001483e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014843  mov     r8d, 5
0x180014849  lea     rcx, [rbp+4Fh+Src]; Src
0x18001484d  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180014852  lea     r8, [rbp+4Fh+Src]
0x180014856  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x18001485b  cmova   r8, qword ptr [rbp+4Fh+Src]
0x180014860  lea     rdx, aHs_0; "\\%hs"
0x180014867  lea     rcx, [rbp+4Fh+lpPathName]
0x18001486b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180014870  mov     rbx, [rbp+4Fh+lpPathName]
0x180014874  mov     rcx, rbx; lpFileName
0x180014877  call    cs:__imp_GetFileAttributesW
0x18001487e  nop     dword ptr [rax+rax+00h]
0x180014883  cmp     eax, 0FFFFFFFFh
0x180014886  jnz     loc_1800149B8
0x18001488c  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x180014891  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014899  mov     [rsp+0D0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800148a1  xor     r9d, r9d; lpSecurityAttributes
0x1800148a4  xor     r8d, r8d; dwShareMode
0x1800148a7  mov     edx, 40000000h; dwDesiredAccess
0x1800148ac  mov     rcx, rbx; lpFileName
0x1800148af  call    cs:__imp_CreateFileW
0x1800148b6  nop     dword ptr [rax+rax+00h]
0x1800148bb  mov     r14, rax
0x1800148be  test    rax, rax
0x1800148c1  jnz     short loc_180014901
0x1800148c3  call    cs:__imp_GetLastError
0x1800148ca  nop     dword ptr [rax+rax+00h]
0x1800148cf  cmp     eax, 50h ; 'P'
0x1800148d2  jz      loc_1800149B8
0x1800148d8  call    cs:__imp_GetLastError
0x1800148df  nop     dword ptr [rax+rax+00h]
0x1800148e4  test    eax, eax
0x1800148e6  mov     edi, eax
0x1800148e8  jle     short loc_1800148F3
0x1800148ea  movzx   edi, ax
0x1800148ed  or      edi, 80070000h
0x1800148f3  lea     rcx, [rbp+4Fh+Src]
0x1800148f7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800148fc  jmp     loc_1800149C4
0x180014901  mov     esi, [r13+0]
0x180014905  mov     dword ptr [rbp+4Fh+liDistanceToMove], esi
0x180014908  xor     eax, eax
0x18001490a  mov     dword ptr [rbp+4Fh+liDistanceToMove+4], eax
0x18001490d  xor     r9d, r9d; dwMoveMethod
0x180014910  xor     r8d, r8d; lpNewFilePointer
0x180014913  mov     rdi, qword ptr [rbp+4Fh+liDistanceToMove]
0x180014917  mov     rdx, rdi; liDistanceToMove
0x18001491a  mov     rcx, r14; hFile
0x18001491d  call    cs:__imp_SetFilePointerEx
0x180014924  nop     dword ptr [rax+rax+00h]
0x180014929  mov     rcx, r14; hFile
0x18001492c  test    eax, eax
0x18001492e  jnz     short loc_18001493E
0x180014930  call    cs:__imp_CloseHandle
0x180014937  nop     dword ptr [rax+rax+00h]
0x18001493c  jmp     short loc_1800148D8
0x18001493e  xor     r9d, r9d; dwMoveMethod
0x180014941  xor     r8d, r8d; lpDistanceToMoveHigh
0x180014944  xor     edx, edx; lDistanceToMove
0x180014946  call    cs:__imp_SetFilePointer
0x18001494d  nop     dword ptr [rax+rax+00h]
0x180014952  mov     eax, 10000h
0x180014957  cmp     esi, eax
0x180014959  cmova   esi, eax
0x18001495c  mov     r15, [r13+8]
0x180014960  mov     r13d, eax
0x180014963  mov     rcx, r14; hObject
0x180014966  test    esi, esi
0x180014968  jz      short loc_1800149AB
0x18001496a  mov     dword ptr [rbp+4Fh+lpPathName], r12d
0x18001496e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12; lpOverlapped
0x180014973  lea     r9, [rbp+4Fh+lpPathName]; lpNumberOfBytesWritten
0x180014977  mov     r8d, esi; nNumberOfBytesToWrite
0x18001497a  mov     rdx, r15; lpBuffer
0x18001497d  call    cs:__imp_WriteFile
0x180014984  nop     dword ptr [rax+rax+00h]
0x180014989  test    eax, eax
0x18001498b  jz      short loc_1800149A6
0x18001498d  mov     eax, dword ptr [rbp+4Fh+lpPathName]
0x180014990  sub     rdi, rax
0x180014993  mov     qword ptr [rbp+4Fh+liDistanceToMove], rdi
0x180014997  add     r15, rax
0x18001499a  mov     esi, dword ptr [rbp+4Fh+liDistanceToMove]
0x18001499d  cmp     esi, r13d
0x1800149a0  cmova   esi, r13d
0x1800149a4  jmp     short loc_180014963
0x1800149a6  mov     rcx, r14
0x1800149a9  jmp     short loc_180014930
0x1800149ab  call    cs:__imp_CloseHandle
0x1800149b2  nop     dword ptr [rax+rax+00h]
0x1800149b7  nop
0x1800149b8  lea     rcx, [rbp+4Fh+Src]
0x1800149bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800149c1  mov     edi, r12d
0x1800149c4  lea     rcx, [rbx-18h]; this
0x1800149c8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800149cd  mov     eax, edi
0x1800149cf  mov     rcx, [rbp+4Fh+var_40]
0x1800149d3  xor     rcx, rsp; StackCookie
0x1800149d6  call    __security_check_cookie
0x1800149db  mov     rbx, [rsp+0D0h+arg_18]
0x1800149e3  add     rsp, 0A0h
0x1800149ea  pop     r15
0x1800149ec  pop     r14
0x1800149ee  pop     r13
0x1800149f0  pop     r12
0x1800149f2  pop     rdi
0x1800149f3  pop     rsi
0x1800149f4  pop     rbp
0x1800149f5  retn
```
