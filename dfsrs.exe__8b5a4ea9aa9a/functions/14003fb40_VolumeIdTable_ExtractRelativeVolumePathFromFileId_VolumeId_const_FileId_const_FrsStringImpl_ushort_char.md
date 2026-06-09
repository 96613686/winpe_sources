# VolumeIdTable::ExtractRelativeVolumePathFromFileId(VolumeId const &,FileId const &,FrsStringImpl<ushort,char> &)

- ea: `0x14003fb40`
- end: `0x14003ff66`
- name: `?ExtractRelativeVolumePathFromFileId@VolumeIdTable@@SAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `1062`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1400fc090`
- `0x1400ff13c`
- `0x140109b4c`
- `0x1401127a4`
- `0x1401184d0`
- `0x1401423d0`

## callees

- `0x14000cd1c`
- `0x14000ee94`
- `0x140010680`
- `0x14001c31c`
- `0x14001cfa0`
- `0x140022ce4`
- `0x1400248f4`
- `0x14003fb40`
- `0x14003ff6c`
- `0x1400af320`
- `0x1401b9494`
- `0x1401bec48`
- `0x1401bf310`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14003fdb3`
- `KERNEL32!GetCurrentThreadId` at `0x14003fed5`
- `KERNEL32!GetCurrentThreadId` at `0x14003fdb3`
- `KERNEL32!GetCurrentThreadId` at `0x14003fed5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003fe20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14003fe20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14003fda3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14003fda3`

## string_xrefs

- `0x14003fddc`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x14003fef7`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x14003fbf1`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fd06`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fd52`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fe8b`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fc39`: `realPath:%ws`
- `0x14003fd2b`: `realPathString:%?`
- `0x14003fd7f`: `realVolumePath:%ws`
- `0x14003fdd0`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fe00`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003fece`: `VolumeIdTable::ExtractRelativeVolumePathFromFileId`
- `0x14003febc`: `relativePath:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VolumeIdTable::ExtractRelativeVolumePathFromFileId(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rdx
  __int64 v5; // r10
  __int64 v6; // rbx
  unsigned int *FileInfo; // rdi
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rsi
  LPCRITICAL_SECTION v12; // rax
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  DWORD v17; // eax
  __int64 v18; // rcx
  const wchar_t *v20; // [rsp+58h] [rbp-29h] BYREF
  int v21; // [rsp+60h] [rbp-21h]
  int v22; // [rsp+64h] [rbp-1Dh]
  const wchar_t *v23; // [rsp+68h] [rbp-19h]
  __int64 v24; // [rsp+70h] [rbp-11h] BYREF
  __int64 v25; // [rsp+78h] [rbp-9h] BYREF
  _BYTE v26[8]; // [rsp+80h] [rbp-1h] BYREF
  void **v27; // [rsp+88h] [rbp+7h] BYREF
  __int64 v28; // [rsp+90h] [rbp+Fh] BYREF
  void **v29; // [rsp+98h] [rbp+17h] BYREF
  __int64 v30; // [rsp+A0h] [rbp+1Fh] BYREF
  void **v31; // [rsp+A8h] [rbp+27h] BYREF
  _BYTE v32[8]; // [rsp+B0h] [rbp+2Fh] BYREF
  unsigned __int16 *v33; // [rsp+100h] [rbp+7Fh] BYREF

  FilePath::FilePath((FilePath *)&v29);
  FilePath::FilePath((FilePath *)&v27);
  v33 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v6 = 0;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  v31 = &NtfsFileSystem::`vftable';
  FileInfo = (unsigned int *)NtfsFileSystem::GetFileInfo(&v31, v5, v4, 0, 0, 0, &v29, 0, 0, 0);
  if ( FileInfo )
    goto LABEL_32;
  FilePath::AppendTrailingBackslash((FilePath *)&v29);
  v8 = v30;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v20 = L"VolumeIdTable::ExtractRelativeVolumePathFromFileId";
    v21 = 1498;
    v22 = 5;
    v23 = L"CCTX";
    v24 = v30 + 18;
    dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v20, L"realPath:%ws", &v24);
  }
  v9 = v8 + 18;
  v10 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v32, v8 + 18);
  FileInfo = (unsigned int *)VolumeIdTable::ExtractVolumePathFromFilePath(v10, &v33);
  FrsStringImpl<char,unsigned short>::ReleaseBody(v32);
  if ( FileInfo )
    goto LABEL_32;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v20 = L"VolumeIdTable::ExtractRelativeVolumePathFromFileId";
    v21 = 1506;
    v22 = 5;
    v23 = L"CCTX";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(&v20, L"realVolumeString:%?", &v33);
  }
  FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v26, v8 + 18);
  FilePath::Set((FilePath *)&v27, v33 + 9);
  FilePath::AppendTrailingBackslash((FilePath *)&v27);
  v11 = v28;
  v12 = g_DebugLog;
  if ( g_DebugLog )
  {
    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v20 = L"VolumeIdTable::ExtractRelativeVolumePathFromFileId";
      v21 = 1513;
      v22 = 5;
      v23 = L"CCTX";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(&v20, L"realPathString:%?", v26);
      v12 = g_DebugLog;
    }
    if ( v12 && LODWORD(v12[1].LockSemaphore) && SLODWORD(v12[1].OwningThread) >= 5 )
    {
      v20 = L"VolumeIdTable::ExtractRelativeVolumePathFromFileId";
      v21 = 1514;
      v22 = 5;
      v23 = L"CCTX";
      v24 = v11 + 18;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v20, L"realVolumePath:%ws", &v24);
    }
  }
  v13 = *(_QWORD *)(v11 + 8);
  if ( *(_DWORD *)(v8 + 8) < (unsigned int)v13 || (unsigned int)_o__wcsnicmp(v8 + 18, v11 + 18, (unsigned int)v13) )
  {
    CurrentThreadId = GetCurrentThreadId();
    FileInfo = (unsigned int *)FrsStatusList::PushNewError(
                                 v15,
                                 161,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                                 "VolumeIdTable::ExtractRelativeVolumePathFromFileId",
                                 1518,
                                 CurrentThreadId,
                                 0);
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(v26);
  if ( FileInfo )
  {
LABEL_32:
    v17 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v18,
           FileInfo[1],
           FileInfo[2],
           *FileInfo,
           "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
           "VolumeIdTable::ExtractRelativeVolumePathFromFileId",
           1534,
           v17,
           FileInfo);
  }
  else
  {
    if ( (unsigned int)_o__wcsicmp(v9, v11 + 18) )
    {
      v16 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(
              &v25,
              v9 + 2 * (*(unsigned int *)(v11 + 8) - 1LL));
      FrsStringImpl<unsigned short,char>::Set(a3, v16);
      FrsStringImpl<char,unsigned short>::ReleaseBody(&v25);
    }
    else
    {
      FrsStringImpl<unsigned short,char>::Set(a3, L"\\");
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v20 = L"VolumeIdTable::ExtractRelativeVolumePathFromFileId";
      v21 = 1531;
      v22 = 5;
      v23 = L"CCTX";
      v25 = *a3 + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v20, L"relativePath:%ws", &v25);
    }
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v33);
  v27 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v28);
  v29 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v30);
  return v6;
}

```

## disassembly

```asm
0x14003fb40  mov     rax, rsp
0x14003fb43  mov     [rax+8], rbx
0x14003fb47  mov     [rax+10h], rsi
0x14003fb4b  mov     [rax+18h], rdi
0x14003fb4f  push    rbp
0x14003fb50  push    r12
0x14003fb52  push    r13
0x14003fb54  push    r14
0x14003fb56  push    r15
0x14003fb58  lea     rbp, [rax-5Fh]
0x14003fb5c  sub     rsp, 0B0h
0x14003fb63  mov     r12, r8
0x14003fb66  mov     r10, rcx
0x14003fb69  lea     rcx, [rbp+57h+var_40]; this
0x14003fb6d  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14003fb72  nop
0x14003fb73  lea     rcx, [rbp+57h+var_50]; this
0x14003fb77  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14003fb7c  nop
0x14003fb7d  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14003fb84  mov     [rbp+57h+arg_18], rax
0x14003fb88  xor     ebx, ebx
0x14003fb8a  cmp     cs:byte_140315A80, bl
0x14003fb90  jnz     short loc_14003FB99
0x14003fb92  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14003fb99  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x14003fba0  mov     [rbp+57h+var_30], rax
0x14003fba4  mov     [rsp+0D0h+var_88], rbx
0x14003fba9  mov     [rsp+0D0h+var_90], rbx
0x14003fbae  mov     [rsp+0D0h+var_98], rbx
0x14003fbb3  lea     rax, [rbp+57h+var_40]
0x14003fbb7  mov     [rsp+0D0h+var_A0], rax
0x14003fbbc  mov     [rsp+0D0h+var_A8], rbx
0x14003fbc1  mov     [rsp+0D0h+var_B0], rbx
0x14003fbc6  xor     r9d, r9d
0x14003fbc9  mov     r8, rdx
0x14003fbcc  mov     rdx, r10
0x14003fbcf  lea     rcx, [rbp+57h+var_30]
0x14003fbd3  call    ?GetFileInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEAVUsn@@PEAV4@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVFilePath@@PEAU_BY_HANDLE_FILE_INFORMATION@@PEAU_FILE_BASIC_INFORMATION@@PEAU_FILE_STANDARD_INFORMATION@@@Z; NtfsFileSystem::GetFileInfo(VolumeId const &,FileId const &,Usn *,FileId *,std::wstring *,FilePath *,_BY_HANDLE_FILE_INFORMATION *,_FILE_BASIC_INFORMATION *,_FILE_STANDARD_INFORMATION *)
0x14003fbd8  mov     rdi, rax
0x14003fbdb  test    rax, rax
0x14003fbde  jnz     loc_14003FECE
0x14003fbe4  lea     rcx, [rbp+57h+var_40]; this
0x14003fbe8  call    ?AppendTrailingBackslash@FilePath@@QEAAXXZ; FilePath::AppendTrailingBackslash(void)
0x14003fbed  lea     r13d, [rdi+5]
0x14003fbf1  lea     rsi, aVolumeidtableE; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fbf8  lea     rcx, aCctx; "CCTX"
0x14003fbff  mov     r15, [rbp+57h+var_38]
0x14003fc03  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003fc0a  test    rax, rax
0x14003fc0d  jz      short loc_14003FC49
0x14003fc0f  cmp     [rax+40h], ebx
0x14003fc12  jz      short loc_14003FC49
0x14003fc14  cmp     [rax+38h], r13d
0x14003fc18  jl      short loc_14003FC49
0x14003fc1a  mov     [rbp+57h+var_80], rsi
0x14003fc1e  mov     [rbp+57h+var_78], 5DAh
0x14003fc25  mov     [rbp+57h+var_74], r13d
0x14003fc29  mov     [rbp+57h+var_70], rcx
0x14003fc2d  lea     rax, [r15+12h]
0x14003fc31  mov     [rbp+57h+var_68], rax
0x14003fc35  lea     r8, [rbp+57h+var_68]
0x14003fc39  lea     rdx, aRealpathWs; "realPath:%ws"
0x14003fc40  lea     rcx, [rbp+57h+var_80]
0x14003fc44  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14003fc49  lea     r14, [r15+12h]
0x14003fc4d  mov     rdx, r14
0x14003fc50  lea     rcx, [rbp+57h+var_28]
0x14003fc54  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x14003fc59  nop
0x14003fc5a  lea     rdx, [rbp+57h+arg_18]
0x14003fc5e  mov     rcx, rax
0x14003fc61  call    ?ExtractVolumePathFromFilePath@VolumeIdTable@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAV3@@Z; VolumeIdTable::ExtractVolumePathFromFilePath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)
0x14003fc66  mov     rdi, rax
0x14003fc69  lea     rcx, [rbp+57h+var_28]
0x14003fc6d  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003fc72  test    rdi, rdi
0x14003fc75  jnz     loc_14003FECE
0x14003fc7b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003fc82  test    rax, rax
0x14003fc85  jz      short loc_14003FCC0
0x14003fc87  cmp     [rax+40h], ebx
0x14003fc8a  jz      short loc_14003FCC0
0x14003fc8c  cmp     [rax+38h], r13d
0x14003fc90  jl      short loc_14003FCC0
0x14003fc92  mov     [rbp+57h+var_80], rsi
0x14003fc96  mov     [rbp+57h+var_78], 5E2h
0x14003fc9d  mov     [rbp+57h+var_74], r13d
0x14003fca1  lea     rax, aCctx; "CCTX"
0x14003fca8  mov     [rbp+57h+var_70], rax
0x14003fcac  lea     r8, [rbp+57h+arg_18]
0x14003fcb0  lea     rdx, aRealvolumestri; "realVolumeString:%?"
0x14003fcb7  lea     rcx, [rbp+57h+var_80]
0x14003fcbb  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x14003fcc0  mov     rdx, r14
0x14003fcc3  lea     rcx, [rbp+57h+var_58]
0x14003fcc7  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x14003fccc  nop
0x14003fccd  mov     rdx, [rbp+57h+arg_18]
0x14003fcd1  add     rdx, 12h; unsigned __int16 *
0x14003fcd5  lea     rcx, [rbp+57h+var_50]; this
0x14003fcd9  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14003fcde  lea     rcx, [rbp+57h+var_50]; this
0x14003fce2  call    ?AppendTrailingBackslash@FilePath@@QEAAXXZ; FilePath::AppendTrailingBackslash(void)
0x14003fce7  mov     rsi, [rbp+57h+var_48]
0x14003fceb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003fcf2  test    rax, rax
0x14003fcf5  jz      loc_14003FD8F
0x14003fcfb  cmp     [rax+40h], ebx
0x14003fcfe  jz      short loc_14003FD42
0x14003fd00  cmp     [rax+38h], r13d
0x14003fd04  jl      short loc_14003FD42
0x14003fd06  lea     rax, aVolumeidtableE; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fd0d  mov     [rbp+57h+var_80], rax
0x14003fd11  mov     [rbp+57h+var_78], 5E9h
0x14003fd18  mov     [rbp+57h+var_74], r13d
0x14003fd1c  lea     rax, aCctx; "CCTX"
0x14003fd23  mov     [rbp+57h+var_70], rax
0x14003fd27  lea     r8, [rbp+57h+var_58]
0x14003fd2b  lea     rdx, aRealpathstring; "realPathString:%?"
0x14003fd32  lea     rcx, [rbp+57h+var_80]
0x14003fd36  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x14003fd3b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003fd42  test    rax, rax
0x14003fd45  jz      short loc_14003FD8F
0x14003fd47  cmp     [rax+40h], ebx
0x14003fd4a  jz      short loc_14003FD8F
0x14003fd4c  cmp     [rax+38h], r13d
0x14003fd50  jl      short loc_14003FD8F
0x14003fd52  lea     rax, aVolumeidtableE; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fd59  mov     [rbp+57h+var_80], rax
0x14003fd5d  mov     [rbp+57h+var_78], 5EAh
0x14003fd64  mov     [rbp+57h+var_74], r13d
0x14003fd68  lea     rax, aCctx; "CCTX"
0x14003fd6f  mov     [rbp+57h+var_70], rax
0x14003fd73  lea     rax, [rsi+12h]
0x14003fd77  mov     [rbp+57h+var_68], rax
0x14003fd7b  lea     r8, [rbp+57h+var_68]
0x14003fd7f  lea     rdx, aRealvolumepath; "realVolumePath:%ws"
0x14003fd86  lea     rcx, [rbp+57h+var_80]
0x14003fd8a  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14003fd8f  mov     rax, [rsi+8]
0x14003fd93  cmp     [r15+8], eax
0x14003fd97  jb      short loc_14003FDB3
0x14003fd99  mov     r8d, eax
0x14003fd9c  lea     rdx, [rsi+12h]
0x14003fda0  mov     rcx, r14
0x14003fda3  call    cs:__imp__o__wcsnicmp
0x14003fdaa  nop     dword ptr [rax+rax+00h]
0x14003fdaf  test    eax, eax
0x14003fdb1  jz      short loc_14003FE00
0x14003fdb3  call    cs:__imp_GetCurrentThreadId
0x14003fdba  nop     dword ptr [rax+rax+00h]
0x14003fdbf  mov     [rsp+0D0h+var_90], rbx
0x14003fdc4  mov     dword ptr [rsp+0D0h+var_98], eax
0x14003fdc8  mov     dword ptr [rsp+0D0h+var_A0], 5EEh
0x14003fdd0  lea     r15, aVolumeidtableE_1; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fdd7  mov     [rsp+0D0h+var_A8], r15
0x14003fddc  lea     rax, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x14003fde3  mov     [rsp+0D0h+var_B0], rax
0x14003fde8  mov     r9d, 1
0x14003fdee  xor     r8d, r8d
0x14003fdf1  mov     edx, 0A1h
0x14003fdf6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14003fdfb  mov     rdi, rax
0x14003fdfe  jmp     short loc_14003FE07
0x14003fe00  lea     r15, aVolumeidtableE_1; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fe07  lea     rcx, [rbp+57h+var_58]
0x14003fe0b  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003fe10  test    rdi, rdi
0x14003fe13  jnz     loc_14003FED5
0x14003fe19  lea     rdx, [rsi+12h]
0x14003fe1d  mov     rcx, r14
0x14003fe20  call    cs:__imp__o__wcsicmp
0x14003fe27  nop     dword ptr [rax+rax+00h]
0x14003fe2c  test    eax, eax
0x14003fe2e  jnz     short loc_14003FE41
0x14003fe30  lea     rdx, Delimiter; "\\"
0x14003fe37  mov     rcx, r12
0x14003fe3a  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x14003fe3f  jmp     short loc_14003FE68
0x14003fe41  mov     eax, [rsi+8]
0x14003fe44  dec     rax
0x14003fe47  lea     rdx, [r14+rax*2]
0x14003fe4b  lea     rcx, [rbp+57h+var_60]
0x14003fe4f  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x14003fe54  mov     rdx, rax
0x14003fe57  mov     rcx, r12
0x14003fe5a  call    ?Set@?$FrsStringImpl@GD@@QEAA_NAEBV1@@Z; FrsStringImpl<ushort,char>::Set(FrsStringImpl<ushort,char> const &)
0x14003fe5f  lea     rcx, [rbp+57h+var_60]
0x14003fe63  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003fe68  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14003fe6f  test    rax, rax
0x14003fe72  jz      loc_14003FF15
0x14003fe78  cmp     [rax+40h], ebx
0x14003fe7b  jz      loc_14003FF15
0x14003fe81  cmp     [rax+38h], r13d
0x14003fe85  jl      loc_14003FF15
0x14003fe8b  lea     rax, aVolumeidtableE; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fe92  mov     [rbp+57h+var_80], rax
0x14003fe96  mov     [rbp+57h+var_78], 5FBh
0x14003fe9d  mov     [rbp+57h+var_74], r13d
0x14003fea1  lea     rax, aCctx; "CCTX"
0x14003fea8  mov     [rbp+57h+var_70], rax
0x14003feac  mov     rax, [r12]
0x14003feb0  add     rax, 12h
0x14003feb4  mov     [rbp+57h+var_60], rax
0x14003feb8  lea     r8, [rbp+57h+var_60]
0x14003febc  lea     rdx, aRelativepathWs; "relativePath:%ws"
0x14003fec3  lea     rcx, [rbp+57h+var_80]
0x14003fec7  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14003fecc  jmp     short loc_14003FF15
0x14003fece  lea     r15, aVolumeidtableE_1; "VolumeIdTable::ExtractRelativeVolumePat"...
0x14003fed5  call    cs:__imp_GetCurrentThreadId
0x14003fedc  nop     dword ptr [rax+rax+00h]
0x14003fee1  mov     [rsp+0D0h+var_90], rdi
0x14003fee6  mov     dword ptr [rsp+0D0h+var_98], eax
0x14003feea  mov     dword ptr [rsp+0D0h+var_A0], 5FEh
0x14003fef2  mov     [rsp+0D0h+var_A8], r15
0x14003fef7  lea     rax, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x14003fefe  mov     [rsp+0D0h+var_B0], rax
0x14003ff03  mov     r9d, [rdi]
0x14003ff06  mov     r8d, [rdi+8]
0x14003ff0a  mov     edx, [rdi+4]
0x14003ff0d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14003ff12  mov     rbx, rax
0x14003ff15  lea     rcx, [rbp+57h+arg_18]
0x14003ff19  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003ff1e  nop
0x14003ff1f  lea     rdi, ??_7FilePath@@6B@; const FilePath::`vftable'
0x14003ff26  mov     [rbp+57h+var_50], rdi
0x14003ff2a  lea     rcx, [rbp+57h+var_48]
0x14003ff2e  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003ff33  nop
0x14003ff34  mov     [rbp+57h+var_40], rdi
0x14003ff38  lea     rcx, [rbp+57h+var_38]
0x14003ff3c  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14003ff41  mov     rax, rbx
0x14003ff44  lea     r11, [rsp+0D0h+var_20]
0x14003ff4c  mov     rbx, [r11+30h]
0x14003ff50  mov     rsi, [r11+38h]
0x14003ff54  mov     rdi, [r11+40h]
0x14003ff58  mov     rsp, r11
0x14003ff5b  pop     r15
0x14003ff5d  pop     r14
0x14003ff5f  pop     r13
0x14003ff61  pop     r12
0x14003ff63  pop     rbp
0x14003ff64  retn
```
