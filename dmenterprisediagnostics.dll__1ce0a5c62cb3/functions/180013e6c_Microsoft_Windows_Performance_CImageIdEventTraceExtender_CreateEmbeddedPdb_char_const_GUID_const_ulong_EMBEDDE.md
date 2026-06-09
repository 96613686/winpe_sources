# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x180013e6c`
- end: `0x180014192`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, const char *, const struct _GUID *, int, DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800121e8`

## callees

- `0x1800017e0`
- `0x180009994`
- `0x1800099b8`
- `0x18000c120`
- `0x18000f754`
- `0x18000f83c`
- `0x18001048c`
- `0x180010924`
- `0x180013b90`
- `0x180013e6c`
- `0x180014270`
- `0x180017ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001414d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001414d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001407b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001407b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013ec0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013eff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013f44`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013ec0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013eff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013f44`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800140d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800140d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800140f4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800140f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014125`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014125`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014049`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014049`

## pseudocode

```c
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
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(183) )
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
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(183) )
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
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(183) )
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
0x180013e6c  mov     [rsp-8+arg_18], rbx
0x180013e71  push    rbp
0x180013e72  push    rsi
0x180013e73  push    rdi
0x180013e74  push    r12
0x180013e76  push    r13
0x180013e78  push    r14
0x180013e7a  push    r15
0x180013e7c  lea     rbp, [rsp-1Fh]
0x180013e81  sub     rsp, 0A0h
0x180013e88  mov     rax, cs:__security_cookie
0x180013e8f  xor     rax, rsp
0x180013e92  mov     [rbp+4Fh+var_40], rax
0x180013e96  mov     r15d, r9d
0x180013e99  mov     r12, r8
0x180013e9c  mov     rsi, rdx
0x180013e9f  mov     r13, [rbp+4Fh+arg_20]
0x180013ea3  lea     r14, [rcx+148h]
0x180013eaa  mov     rdx, r14
0x180013ead  lea     rcx, [rbp+4Fh+lpPathName]
0x180013eb1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180013eb6  nop
0x180013eb7  xor     edx, edx; lpSecurityAttributes
0x180013eb9  mov     rbx, [rbp+4Fh+lpPathName]
0x180013ebd  mov     rcx, rbx; lpPathName
0x180013ec0  call    cs:__imp_CreateDirectoryW
0x180013ec6  test    eax, eax
0x180013ec8  jnz     short loc_180013EE3
0x180013eca  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013ecf  mov     edi, eax
0x180013ed1  mov     ecx, 0B7h; unsigned int
0x180013ed6  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180013edb  cmp     edi, eax
0x180013edd  jnz     loc_180014160
0x180013ee3  mov     r8, rsi
0x180013ee6  lea     rdx, aHs_0; "\\%hs"
0x180013eed  lea     rcx, [rbp+4Fh+lpPathName]
0x180013ef1  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180013ef6  xor     edx, edx; lpSecurityAttributes
0x180013ef8  mov     rbx, [rbp+4Fh+lpPathName]
0x180013efc  mov     rcx, rbx; lpPathName
0x180013eff  call    cs:__imp_CreateDirectoryW
0x180013f05  test    eax, eax
0x180013f07  jnz     short loc_180013F22
0x180013f09  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013f0e  mov     edi, eax
0x180013f10  mov     ecx, 0B7h; unsigned int
0x180013f15  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180013f1a  cmp     edi, eax
0x180013f1c  jnz     loc_180014160
0x180013f22  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d
0x180013f27  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12
0x180013f2c  mov     r9, rsi
0x180013f2f  mov     r8, [r14]
0x180013f32  lea     rdx, [rbp+4Fh+lpPathName]
0x180013f36  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x180013f3b  xor     edx, edx; lpSecurityAttributes
0x180013f3d  mov     rbx, [rbp+4Fh+lpPathName]
0x180013f41  mov     rcx, rbx; lpPathName
0x180013f44  call    cs:__imp_CreateDirectoryW
0x180013f4a  xor     r12d, r12d
0x180013f4d  test    eax, eax
0x180013f4f  jnz     short loc_180013F6A
0x180013f51  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013f56  mov     edi, eax
0x180013f58  mov     ecx, 0B7h; unsigned int
0x180013f5d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180013f62  cmp     edi, eax
0x180013f64  jnz     loc_180014160
0x180013f6a  xorps   xmm0, xmm0
0x180013f6d  movups  [rbp+4Fh+Src], xmm0
0x180013f71  mov     qword ptr [rbp+4Fh+var_70], r12
0x180013f75  mov     qword ptr [rbp+4Fh+var_70+8], r12
0x180013f79  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013f7d  inc     r8
0x180013f80  cmp     [rsi+r8], r12b
0x180013f84  jnz     short loc_180013F7D
0x180013f86  mov     rdx, rsi
0x180013f89  lea     rcx, [rbp+4Fh+Src]
0x180013f8d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180013f92  nop
0x180013f93  lea     rcx, [rbp+4Fh+Src]
0x180013f97  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x180013f9c  cmova   rcx, qword ptr [rbp+4Fh+Src]
0x180013fa1  mov     rdx, qword ptr [rbp+4Fh+var_70]
0x180013fa5  call    ??$_Traits_rfind_ch@U?$char_traits@D@std@@@std@@YA_KQEBD_K1D@Z; std::_Traits_rfind_ch<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char)
0x180013faa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013fae  jz      short loc_180014015
0x180013fb0  xorps   xmm0, xmm0
0x180013fb3  movups  [rbp+4Fh+var_60], xmm0
0x180013fb7  xorps   xmm1, xmm1
0x180013fba  movdqu  [rbp+4Fh+var_50], xmm1
0x180013fbf  cmp     qword ptr [rbp+4Fh+var_70], rax
0x180013fc3  cmovb   rax, qword ptr [rbp+4Fh+var_70]
0x180013fc8  lea     rdx, [rbp+4Fh+Src]
0x180013fcc  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x180013fd1  cmova   rdx, qword ptr [rbp+4Fh+Src]
0x180013fd6  mov     r8, rax
0x180013fd9  lea     rcx, [rbp+4Fh+var_60]
0x180013fdd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180013fe2  lea     rcx, [rbp+4Fh+Src]
0x180013fe6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180013feb  movups  xmm0, [rbp+4Fh+var_60]
0x180013fef  movups  [rbp+4Fh+Src], xmm0
0x180013ff3  movups  xmm1, [rbp+4Fh+var_50]
0x180013ff7  movups  [rbp+4Fh+var_70], xmm1
0x180013ffb  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180014003  movdqu  [rbp+4Fh+var_50], xmm0
0x180014008  mov     byte ptr [rbp+4Fh+var_60], r12b
0x18001400c  lea     rcx, [rbp+4Fh+var_60]
0x180014010  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014015  mov     r8d, 5
0x18001401b  lea     rcx, [rbp+4Fh+Src]; Src
0x18001401f  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180014024  lea     r8, [rbp+4Fh+Src]
0x180014028  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x18001402d  cmova   r8, qword ptr [rbp+4Fh+Src]
0x180014032  lea     rdx, aHs_0; "\\%hs"
0x180014039  lea     rcx, [rbp+4Fh+lpPathName]
0x18001403d  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180014042  mov     rbx, [rbp+4Fh+lpPathName]
0x180014046  mov     rcx, rbx; lpFileName
0x180014049  call    cs:__imp_GetFileAttributesW
0x18001404f  cmp     eax, 0FFFFFFFFh
0x180014052  jnz     loc_180014154
0x180014058  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x18001405d  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014065  mov     [rsp+0D0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001406d  xor     r9d, r9d; lpSecurityAttributes
0x180014070  xor     r8d, r8d; dwShareMode
0x180014073  mov     edx, 40000000h; dwDesiredAccess
0x180014078  mov     rcx, rbx; lpFileName
0x18001407b  call    cs:__imp_CreateFileW
0x180014081  mov     r14, rax
0x180014084  test    rax, rax
0x180014087  jnz     short loc_1800140BB
0x180014089  call    cs:__imp_GetLastError
0x18001408f  cmp     eax, 50h ; 'P'
0x180014092  jz      loc_180014154
0x180014098  call    cs:__imp_GetLastError
0x18001409e  test    eax, eax
0x1800140a0  mov     edi, eax
0x1800140a2  jle     short loc_1800140AD
0x1800140a4  movzx   edi, ax
0x1800140a7  or      edi, 80070000h
0x1800140ad  lea     rcx, [rbp+4Fh+Src]
0x1800140b1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800140b6  jmp     loc_180014160
0x1800140bb  mov     esi, [r13+0]
0x1800140bf  mov     dword ptr [rbp+4Fh+liDistanceToMove], esi
0x1800140c2  xor     eax, eax
0x1800140c4  mov     dword ptr [rbp+4Fh+liDistanceToMove+4], eax
0x1800140c7  xor     r9d, r9d; dwMoveMethod
0x1800140ca  xor     r8d, r8d; lpNewFilePointer
0x1800140cd  mov     rdi, qword ptr [rbp+4Fh+liDistanceToMove]
0x1800140d1  mov     rdx, rdi; liDistanceToMove
0x1800140d4  mov     rcx, r14; hFile
0x1800140d7  call    cs:__imp_SetFilePointerEx
0x1800140dd  mov     rcx, r14; hFile
0x1800140e0  test    eax, eax
0x1800140e2  jnz     short loc_1800140EC
0x1800140e4  call    cs:__imp_CloseHandle
0x1800140ea  jmp     short loc_180014098
0x1800140ec  xor     r9d, r9d; dwMoveMethod
0x1800140ef  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800140f2  xor     edx, edx; lDistanceToMove
0x1800140f4  call    cs:__imp_SetFilePointer
0x1800140fa  mov     eax, 10000h
0x1800140ff  cmp     esi, eax
0x180014101  cmova   esi, eax
0x180014104  mov     r15, [r13+8]
0x180014108  mov     r13d, eax
0x18001410b  mov     rcx, r14; hObject
0x18001410e  test    esi, esi
0x180014110  jz      short loc_18001414D
0x180014112  mov     dword ptr [rbp+4Fh+lpPathName], r12d
0x180014116  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12; lpOverlapped
0x18001411b  lea     r9, [rbp+4Fh+lpPathName]; lpNumberOfBytesWritten
0x18001411f  mov     r8d, esi; nNumberOfBytesToWrite
0x180014122  mov     rdx, r15; lpBuffer
0x180014125  call    cs:__imp_WriteFile
0x18001412b  test    eax, eax
0x18001412d  jz      short loc_180014148
0x18001412f  mov     eax, dword ptr [rbp+4Fh+lpPathName]
0x180014132  sub     rdi, rax
0x180014135  mov     qword ptr [rbp+4Fh+liDistanceToMove], rdi
0x180014139  add     r15, rax
0x18001413c  mov     esi, dword ptr [rbp+4Fh+liDistanceToMove]
0x18001413f  cmp     esi, r13d
0x180014142  cmova   esi, r13d
0x180014146  jmp     short loc_18001410B
0x180014148  mov     rcx, r14
0x18001414b  jmp     short loc_1800140E4
0x18001414d  call    cs:__imp_CloseHandle
0x180014153  nop
0x180014154  lea     rcx, [rbp+4Fh+Src]
0x180014158  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001415d  mov     edi, r12d
0x180014160  lea     rcx, [rbx-18h]; this
0x180014164  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014169  mov     eax, edi
0x18001416b  mov     rcx, [rbp+4Fh+var_40]
0x18001416f  xor     rcx, rsp; StackCookie
0x180014172  call    __security_check_cookie
0x180014177  mov     rbx, [rsp+0D0h+arg_18]
0x18001417f  add     rsp, 0A0h
0x180014186  pop     r15
0x180014188  pop     r14
0x18001418a  pop     r13
0x18001418c  pop     r12
0x18001418e  pop     rdi
0x18001418f  pop     rsi
0x180014190  pop     rbp
0x180014191  retn
```
