# Csl::IsWcifsReparsePoint(Csl::Path const &,bool &)

- ea: `0x1801984e8`
- end: `0x180198a88`
- name: `?IsWcifsReparsePoint@Csl@@YAJAEBVPath@1@AEA_N@Z`
- size: `1440`
- prototype: `__int64 __fastcall(Csl *__hidden this, const struct Path *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path`

## callers

- `0x1800ca424`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x180016774`
- `0x18002f8ac`
- `0x18002fc68`
- `0x1801984e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198822`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801985fd`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801985fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801985b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180198765`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801985b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180198765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801988b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801988dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801989a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801989f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801988b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801988dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801989a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801989f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a1c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019880e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019880e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801986c8`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801986c8`

## pseudocode

```c
__int64 __fastcall Csl::IsWcifsReparsePoint(Csl *this, const struct Path *a2, struct Path *a3)
{
  int v4; // eax
  unsigned int LastError; // ebx
  WCHAR *v6; // rcx
  HANDLE FileW; // rsi
  const char *v9; // r9
  const char *v10; // r9
  __int64 nFileIndexHigh; // rbx
  __int64 nFileIndexLow; // r15
  _QWORD *v13; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  HANDLE v16; // r14
  unsigned __int64 v17; // r12
  char v18; // r13
  unsigned int *v19; // rax
  unsigned int *v20; // rbx
  const char *v21; // r9
  const char *v22; // r9
  unsigned int *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  unsigned int *v25; // r15
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  unsigned int v28; // r15d
  char *i; // rdx
  char *v30; // rcx
  __int64 v31; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszVolumeMountPoint[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v38[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  const struct Path *v40; // [rsp+88h] [rbp-78h]
  _QWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  char v42[16]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD InBuffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h]
  __int64 v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR szVolumeName[56]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v40 = a2;
  lpFileName[0] = v36;
  lpFileName[1] = v36;
  v36[0] = 0;
  v4 = Csl::ConvertToLongPath(this, (const struct Path *)lpFileName, a3);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
    goto LABEL_3;
  }
  FileW = CreateFileW(lpFileName[0], 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x13A,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v9);
    goto LABEL_3;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x140,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v10);
    if ( FileW )
      CloseHandle(FileW);
LABEL_3:
    v6 = (WCHAR *)lpFileName[0];
    if ( lpFileName[0] == v36 )
      return LastError;
LABEL_4:
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  nFileIndexHigh = FileInformation.nFileIndexHigh;
  nFileIndexLow = FileInformation.nFileIndexLow;
  lpszVolumeMountPoint[0] = v38;
  v38[0] = 0;
  lpszVolumeMountPoint[1] = v38;
  v41[0] = this;
  v41[1] = 0;
  v13 = (_QWORD *)Csl::Path::Iterator::operator*(v41, v42);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpszVolumeMountPoint,
                           *v13,
                           v13[1]) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_69:
    if ( lpszVolumeMountPoint[0] != v38 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( FileW )
      CloseHandle(FileW);
    if ( lpFileName[0] != v36 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint[0], szVolumeName, 0x32u) )
  {
    v15 = 332;
    goto LABEL_15;
  }
  szVolumeName[48] = 0;
  v16 = CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
  if ( v16 == (HANDLE)-1LL )
  {
    v15 = 347;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v14);
    if ( lpszVolumeMountPoint[0] != v38 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( FileW )
      CloseHandle(FileW);
    v6 = (WCHAR *)lpFileName[0];
    if ( lpFileName[0] == v36 )
      return LastError;
    goto LABEL_4;
  }
  v44 = 2;
  v17 = 1024;
  v45 = nFileIndexLow | (nFileIndexHigh << 32);
  v18 = 1;
  v46 = v45;
  InBuffer[1] = 16549;
  InBuffer[0] = 1;
  v19 = (unsigned int *)operator new[](0x400u, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v19;
  if ( !v19 )
  {
    v26 = 373;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositionb);
    if ( v16 )
      CloseHandle(v16);
    goto LABEL_69;
  }
  memset_0(v19, 0, 0x400u);
  while ( 1 )
  {
    BytesReturned = 0;
    if ( DeviceIoControl(v16, 0x90277u, InBuffer, 0x20u, v20, v17, &BytesReturned, 0) )
      break;
    if ( GetLastError() != 122 )
    {
      v28 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x191,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
              v22);
      if ( v20 )
        operator delete(v20, v27);
      if ( v16 )
        CloseHandle(v16);
      if ( lpszVolumeMountPoint[0] != v38 )
        operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( FileW )
        CloseHandle(FileW);
      if ( lpFileName[0] != v36 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      return v28;
    }
    v17 *= 2LL;
    v23 = (unsigned int *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    v25 = v23;
    if ( v23 )
      memset_0(v23, 0, v17);
    else
      v25 = 0;
    if ( v20 )
      operator delete(v20, v24);
    if ( !v25 )
    {
      v26 = 397;
      goto LABEL_67;
    }
    v20 = v25;
  }
  for ( i = (char *)v20 + v20[1] + *(unsigned int *)((char *)v20 + v20[1] + 28);
        *((_DWORD *)i + 1);
        i += *((unsigned int *)i + 1) )
  {
    if ( *((_DWORD *)i + 9) == 192 )
      goto LABEL_52;
  }
  if ( *((_DWORD *)i + 9) != 192 )
  {
    *(_BYTE *)v40 = 0;
    goto LABEL_57;
  }
LABEL_52:
  if ( (i[8] & 0x10) == 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      v21);
  v30 = &i[*((unsigned int *)i + 8)];
  v31 = *((unsigned int *)v30 + 4);
  if ( *(_DWORD *)&v30[v31] != -2147483624 && *(_DWORD *)&v30[v31] != -1879044072 )
    v18 = 0;
  *(_BYTE *)v40 = v18;
LABEL_57:
  operator delete(v20, (const struct std::nothrow_t *)i);
  if ( v16 )
    CloseHandle(v16);
  if ( lpszVolumeMountPoint[0] != v38 )
    operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FileW )
    CloseHandle(FileW);
  if ( lpFileName[0] != v36 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1801984e8  mov     [rsp-8+arg_10], rbx
0x1801984ed  push    rbp
0x1801984ee  push    rsi
0x1801984ef  push    rdi
0x1801984f0  push    r12
0x1801984f2  push    r13
0x1801984f4  push    r14
0x1801984f6  push    r15
0x1801984f8  lea     rbp, [rsp-90h]
0x180198500  sub     rsp, 190h
0x180198507  mov     rax, cs:__security_cookie
0x18019850e  xor     rax, rsp
0x180198511  mov     [rbp+0C0h+var_40], rax
0x180198518  lea     rax, [rsp+1C0h+var_170]
0x18019851d  mov     [rbp+0C0h+var_138], rdx
0x180198521  mov     [rsp+1C0h+lpFileName], rax
0x180198526  lea     rdx, [rsp+1C0h+lpFileName]; struct Path *
0x18019852b  lea     rax, [rsp+1C0h+var_170]
0x180198530  xor     r12d, r12d
0x180198533  mov     [rsp+1C0h+var_178], rax
0x180198538  mov     rdi, rcx
0x18019853b  mov     [rsp+1C0h+var_170], r12w
0x180198541  call    ?ConvertToLongPath@Csl@@YAJAEBVPath@1@AEAV21@@Z; Csl::ConvertToLongPath(Csl::Path const &,Csl::Path &)
0x180198546  mov     ebx, eax
0x180198548  test    eax, eax
0x18019854a  jns     short loc_180198589
0x18019854c  mov     rcx, [rbp+0C8h]; this
0x180198553  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019855a  mov     r9d, eax; char *
0x18019855d  mov     edx, 12Eh; void *
0x180198562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198567  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x18019856c  lea     rax, [rsp+1C0h+var_170]
0x180198571  cmp     rcx, rax
0x180198574  jz      short loc_180198582
0x180198576  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019857d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198582  mov     eax, ebx
0x180198584  jmp     loc_180198A44
0x180198589  mov     rcx, [rsp+1C0h+lpFileName]; lpFileName
0x18019858e  mov     r14d, 3
0x180198594  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x180198599  xor     r9d, r9d; lpSecurityAttributes
0x18019859c  mov     [rsp+1C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1801985a4  mov     [rsp+1C0h+dwCreationDisposition], r14d; int
0x1801985a9  lea     edx, [r14+7Dh]; dwDesiredAccess
0x1801985ad  lea     r8d, [r14+4]; dwShareMode
0x1801985b1  call    cs:__imp_CreateFileW
0x1801985b8  nop     dword ptr [rax+rax+00h]
0x1801985bd  mov     rsi, rax
0x1801985c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801985c4  jnz     short loc_1801985E2
0x1801985c6  mov     rcx, [rbp+0C8h]; this
0x1801985cd  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801985d4  mov     edx, 13Ah; void *
0x1801985d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801985de  mov     ebx, eax
0x1801985e0  jmp     short loc_180198567
0x1801985e2  xorps   xmm0, xmm0
0x1801985e5  lea     rdx, [rbp+0C0h+FileInformation]; lpFileInformation
0x1801985e9  xor     eax, eax
0x1801985eb  mov     rcx, rsi; hFile
0x1801985ee  movups  xmmword ptr [rbp+0C0h+FileInformation.dwFileAttributes], xmm0
0x1801985f2  mov     [rbp+0C0h+FileInformation.nFileIndexLow], eax
0x1801985f5  movups  xmmword ptr [rbp+0C0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1801985f9  movups  xmmword ptr [rbp+0C0h+FileInformation.nFileSizeHigh], xmm0
0x1801985fd  call    cs:__imp_GetFileInformationByHandle
0x180198604  nop     dword ptr [rax+rax+00h]
0x180198609  test    eax, eax
0x18019860b  jnz     short loc_180198644
0x18019860d  mov     rcx, [rbp+0C8h]; this
0x180198614  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019861b  mov     edx, 140h; void *
0x180198620  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180198625  mov     ebx, eax
0x180198627  test    rsi, rsi
0x18019862a  jz      loc_180198567
0x180198630  mov     rcx, rsi; hObject
0x180198633  call    cs:__imp_CloseHandle
0x18019863a  nop     dword ptr [rax+rax+00h]
0x18019863f  jmp     loc_180198567
0x180198644  mov     ebx, [rbp+0C0h+FileInformation.nFileIndexHigh]
0x180198647  lea     rax, [rsp+1C0h+var_150]
0x18019864c  mov     r15d, [rbp+0C0h+FileInformation.nFileIndexLow]
0x180198650  lea     rdx, [rbp+0C0h+var_120]
0x180198654  mov     [rsp+1C0h+lpszVolumeMountPoint], rax
0x180198659  lea     rcx, [rbp+0C0h+var_130]
0x18019865d  lea     rax, [rsp+1C0h+var_150]
0x180198662  mov     [rsp+1C0h+var_150], r12w
0x180198668  mov     [rsp+1C0h+var_158], rax
0x18019866d  mov     [rbp+0C0h+var_130], rdi
0x180198671  mov     [rbp+0C0h+var_128], r12
0x180198675  call    ??DIterator@Path@Csl@@QEBA?AV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@XZ; Csl::Path::Iterator::operator*(void)
0x18019867a  lea     rcx, [rsp+1C0h+lpszVolumeMountPoint]
0x18019867f  mov     r8, [rax+8]
0x180198683  mov     rdx, [rax]
0x180198686  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18019868b  test    al, al
0x18019868d  jnz     short loc_1801986B9
0x18019868f  mov     rcx, [rbp+0C8h]; this
0x180198696  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019869d  mov     r9d, 8007000Eh; char *
0x1801986a3  mov     edx, 147h; void *
0x1801986a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801986ad  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801986b4  jmp     loc_1801989FD
0x1801986b9  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x1801986be  lea     rdx, [rbp+0C0h+szVolumeName]; lpszVolumeName
0x1801986c2  mov     r8d, 32h ; '2'; cchBufferLength
0x1801986c8  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801986cf  nop     dword ptr [rax+rax+00h]
0x1801986d4  test    eax, eax
0x1801986d6  jnz     short loc_18019873F
0x1801986d8  mov     edx, 14Ch; void *
0x1801986dd  mov     rcx, [rbp+0C8h]; this
0x1801986e4  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801986eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801986f0  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x1801986f5  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801986fc  mov     ebx, eax
0x1801986fe  lea     rax, [rsp+1C0h+var_150]
0x180198703  cmp     rcx, rax
0x180198706  jz      short loc_180198710
0x180198708  mov     rdx, rdi; struct std::nothrow_t *
0x18019870b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198710  test    rsi, rsi
0x180198713  jz      short loc_180198724
0x180198715  mov     rcx, rsi; hObject
0x180198718  call    cs:__imp_CloseHandle
0x18019871f  nop     dword ptr [rax+rax+00h]
0x180198724  mov     rcx, [rsp+1C0h+lpFileName]
0x180198729  lea     rax, [rsp+1C0h+var_170]
0x18019872e  cmp     rcx, rax
0x180198731  jz      loc_180198582
0x180198737  mov     rdx, rdi
0x18019873a  jmp     loc_18019857D
0x18019873f  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x180198744  lea     rcx, [rbp+0C0h+szVolumeName]; lpFileName
0x180198748  mov     [rsp+1C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180198750  xor     r9d, r9d; lpSecurityAttributes
0x180198753  mov     r8d, r14d; dwShareMode
0x180198756  mov     [rsp+1C0h+dwCreationDisposition], r14d; int
0x18019875b  mov     edx, 80000000h; dwDesiredAccess
0x180198760  mov     [rbp+0C0h+var_50], r12w
0x180198765  call    cs:__imp_CreateFileW
0x18019876c  nop     dword ptr [rax+rax+00h]
0x180198771  mov     r14, rax
0x180198774  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180198778  jnz     short loc_180198784
0x18019877a  mov     edx, 15Bh
0x18019877f  jmp     loc_1801986DD
0x180198784  shl     rbx, 20h
0x180198788  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18019878f  or      rbx, r15
0x180198792  mov     [rbp+0C0h+var_108], 2
0x18019879a  mov     r12d, 400h
0x1801987a0  mov     [rbp+0C0h+var_100], rbx
0x1801987a4  mov     r13d, 1
0x1801987aa  mov     [rbp+0C0h+var_F8], rbx
0x1801987ae  mov     rdx, rdi; struct std::nothrow_t *
0x1801987b1  mov     [rbp+0C0h+var_10C], 40A5h
0x1801987b8  mov     ecx, r12d; unsigned __int64
0x1801987bb  mov     [rbp+0C0h+InBuffer], r13d
0x1801987bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801987c4  xor     r15d, r15d
0x1801987c7  mov     rbx, rax
0x1801987ca  test    rax, rax
0x1801987cd  jz      loc_1801989CB
0x1801987d3  mov     r8d, r12d; Size
0x1801987d6  xor     edx, edx; Val
0x1801987d8  mov     rcx, rax; void *
0x1801987db  call    memset_0
0x1801987e0  mov     [rsp+1C0h+lpOverlapped], r15; lpOverlapped
0x1801987e5  lea     rax, [rbp+0C0h+BytesReturned]
0x1801987e9  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1801987ee  lea     r8, [rbp+0C0h+InBuffer]; lpInBuffer
0x1801987f2  mov     [rsp+1C0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x1801987f7  mov     r9d, 20h ; ' '; nInBufferSize
0x1801987fd  mov     edx, 90277h; dwIoControlCode
0x180198802  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rbx; lpOutBuffer
0x180198807  mov     rcx, r14; hDevice
0x18019880a  mov     [rbp+0C0h+BytesReturned], r15d
0x18019880e  call    cs:__imp_DeviceIoControl
0x180198815  nop     dword ptr [rax+rax+00h]
0x18019881a  test    eax, eax
0x18019881c  jnz     loc_180198908
0x180198822  call    cs:__imp_GetLastError
0x180198829  nop     dword ptr [rax+rax+00h]
0x18019882e  cmp     eax, 7Ah ; 'z'
0x180198831  jnz     short loc_180198882
0x180198833  add     r12, r12
0x180198836  mov     rdx, rdi; struct std::nothrow_t *
0x180198839  mov     rcx, r12; unsigned __int64
0x18019883c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180198841  mov     r15, rax
0x180198844  test    rax, rax
0x180198847  jz      short loc_180198858
0x180198849  mov     r8, r12; Size
0x18019884c  xor     edx, edx; Val
0x18019884e  mov     rcx, rax; void *
0x180198851  call    memset_0
0x180198856  jmp     short loc_18019885B
0x180198858  xor     r15d, r15d
0x18019885b  test    rbx, rbx
0x18019885e  jz      short loc_180198868
0x180198860  mov     rcx, rbx; void *
0x180198863  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198868  test    r15, r15
0x18019886b  jz      short loc_180198878
0x18019886d  mov     rbx, r15
0x180198870  xor     r15d, r15d
0x180198873  jmp     loc_1801987E0
0x180198878  mov     edx, 18Dh
0x18019887d  jmp     loc_1801989D0
0x180198882  mov     rcx, [rbp+0C8h]; this
0x180198889  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198890  mov     edx, 191h; void *
0x180198895  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019889a  mov     r15d, eax
0x18019889d  test    rbx, rbx
0x1801988a0  jz      short loc_1801988AA
0x1801988a2  mov     rcx, rbx; void *
0x1801988a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801988aa  test    r14, r14
0x1801988ad  jz      short loc_1801988BE
0x1801988af  mov     rcx, r14; hObject
0x1801988b2  call    cs:__imp_CloseHandle
0x1801988b9  nop     dword ptr [rax+rax+00h]
0x1801988be  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x1801988c3  lea     rax, [rsp+1C0h+var_150]
0x1801988c8  cmp     rcx, rax
0x1801988cb  jz      short loc_1801988D5
0x1801988cd  mov     rdx, rdi; struct std::nothrow_t *
0x1801988d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801988d5  test    rsi, rsi
0x1801988d8  jz      short loc_1801988E9
0x1801988da  mov     rcx, rsi; hObject
0x1801988dd  call    cs:__imp_CloseHandle
0x1801988e4  nop     dword ptr [rax+rax+00h]
0x1801988e9  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x1801988ee  lea     rax, [rsp+1C0h+var_170]
0x1801988f3  cmp     rcx, rax
0x1801988f6  jz      short loc_180198900
0x1801988f8  mov     rdx, rdi; struct std::nothrow_t *
0x1801988fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198900  mov     eax, r15d
0x180198903  jmp     loc_180198A44
0x180198908  mov     ecx, [rbx+4]
0x18019890b  add     rcx, rbx
0x18019890e  mov     edx, [rcx+1Ch]
0x180198911  add     rdx, rcx
0x180198914  mov     ecx, 0C0h
0x180198919  jmp     short loc_180198926
0x18019891b  cmp     [rdx+24h], ecx
0x18019891e  jz      short loc_18019893A
0x180198920  mov     eax, [rdx+4]
0x180198923  add     rdx, rax; struct std::nothrow_t *
0x180198926  cmp     [rdx+4], r15d
0x18019892a  jnz     short loc_18019891B
0x18019892c  cmp     [rdx+24h], ecx
0x18019892f  jz      short loc_18019893A
0x180198931  mov     rax, [rbp+0C0h+var_138]
0x180198935  mov     [rax], r15b
0x180198938  jmp     short loc_180198969
0x18019893a  test    byte ptr [rdx+8], 10h
0x18019893e  jz      loc_180198A6F
0x180198944  mov     ecx, [rdx+20h]
0x180198947  add     rcx, rdx
0x18019894a  mov     eax, [rcx+10h]
0x18019894d  cmp     dword ptr [rax+rcx], 80000018h
0x180198954  jz      short loc_180198962
0x180198956  cmp     dword ptr [rax+rcx], 90001018h
0x18019895d  jz      short loc_180198962
0x18019895f  mov     r13b, r15b
0x180198962  mov     rax, [rbp+0C0h+var_138]
0x180198966  mov     [rax], r13b
0x180198969  mov     rcx, rbx; void *
0x18019896c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198971  test    r14, r14
0x180198974  jz      short loc_180198985
0x180198976  mov     rcx, r14; hObject
0x180198979  call    cs:__imp_CloseHandle
0x180198980  nop     dword ptr [rax+rax+00h]
0x180198985  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x18019898a  lea     rax, [rsp+1C0h+var_150]
0x18019898f  cmp     rcx, rax
0x180198992  jz      short loc_18019899C
0x180198994  mov     rdx, rdi; struct std::nothrow_t *
0x180198997  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019899c  test    rsi, rsi
0x18019899f  jz      short loc_1801989B0
0x1801989a1  mov     rcx, rsi; hObject
0x1801989a4  call    cs:__imp_CloseHandle
0x1801989ab  nop     dword ptr [rax+rax+00h]
0x1801989b0  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x1801989b5  lea     rax, [rsp+1C0h+var_170]
0x1801989ba  cmp     rcx, rax
0x1801989bd  jz      short loc_1801989C7
0x1801989bf  mov     rdx, rdi; struct std::nothrow_t *
0x1801989c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
  ... truncated ...
```
