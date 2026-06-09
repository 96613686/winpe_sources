# PdbManager::CreateDbLossNameHolderFile(void)

- ea: `0x14006fc2c`
- end: `0x14006fee1`
- name: `?CreateDbLossNameHolderFile@PdbManager@@AEAAPEAVFrsStatus@@XZ`
- size: `693`
- prototype: `struct FrsStatus *__fastcall(PdbManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140072eac`
- `0x14007a244`

## callees

- `0x14000cd1c`
- `0x14000cdc0`
- `0x14000ee94`
- `0x1400248f4`
- `0x14005c620`
- `0x14006f414`
- `0x14006fc2c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14006fc79`
- `KERNEL32!DeleteFileW` at `0x14006fcb6`
- `KERNEL32!DeleteFileW` at `0x14006fc79`
- `KERNEL32!DeleteFileW` at `0x14006fcb6`
- `KERNEL32!CreateFileW` at `0x14006fd3f`
- `KERNEL32!CreateFileW` at `0x14006fd3f`
- `KERNEL32!GetLastError` at `0x14006fc87`
- `KERNEL32!GetLastError` at `0x14006fcc4`
- `KERNEL32!GetLastError` at `0x14006fdd3`
- `KERNEL32!GetLastError` at `0x14006fc87`
- `KERNEL32!GetLastError` at `0x14006fcc4`
- `KERNEL32!GetLastError` at `0x14006fdd3`
- `KERNEL32!GetCurrentThreadId` at `0x14006fcdb`
- `KERNEL32!GetCurrentThreadId` at `0x14006fdc5`
- `KERNEL32!GetCurrentThreadId` at `0x14006fe66`
- `KERNEL32!GetCurrentThreadId` at `0x14006fcdb`
- `KERNEL32!GetCurrentThreadId` at `0x14006fdc5`
- `KERNEL32!GetCurrentThreadId` at `0x14006fe66`

## string_xrefs

- `0x14006fdb0`: `Created %ws`
- `0x14006fc95`: `PdbManager::CreateDbLossNameHolderFile`
- `0x14006fd84`: `PdbManager::CreateDbLossNameHolderFile`
- `0x14006fe2a`: `PdbManager::CreateDbLossNameHolderFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall PdbManager::CreateDbLossNameHolderFile(PdbManager *this)
{
  PdbManager *v1; // r9
  BOOL v2; // ebx
  DWORD LastError; // eax
  DWORD v4; // esi
  __int64 v5; // r14
  __int64 v6; // rdi
  BOOL v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  __int64 v10; // rcx
  unsigned int *v11; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  void **v18; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h] BYREF
  void **v20; // [rsp+60h] [rbp+7h] BYREF
  __int64 v21; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v22; // [rsp+70h] [rbp+17h] BYREF
  int v23; // [rsp+78h] [rbp+1Fh]
  int v24; // [rsp+7Ch] [rbp+23h]
  const wchar_t *v25; // [rsp+80h] [rbp+27h]
  void *FileW; // [rsp+C8h] [rbp+6Fh] BYREF

  FilePath::FilePath((FilePath *)&v20);
  FilePath::FilePath((FilePath *)&v18);
  PdbManager::BuildDbLossFileNames(v1, (struct FilePath *)&v20, (struct FilePath *)&v18);
  v2 = DeleteFileW((LPCWSTR)(v21 + 18));
  LastError = GetLastError();
  v4 = LastError;
  v5 = v19;
  v6 = 0;
  if ( (v2 || LastError == 2) && ((v7 = DeleteFileW((LPCWSTR)(v19 + 18)), v8 = GetLastError(), v4 = v8, v7) || v8 == 2)
    || (v9 = GetCurrentThreadId(),
        (v11 = (unsigned int *)FrsStatusList::PushNewError(
                                 v10,
                                 v4,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                                 "PdbManager::CreateDbLossNameHolderFile",
                                 6413,
                                 v9,
                                 0)) == 0) )
  {
    FileW = CreateFileW((LPCWSTR)(v5 + 18), 0, 0, 0, 1u, 0, 0);
    if ( (char *)FileW - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandleEx(&FileW);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v22 = L"PdbManager::CreateDbLossNameHolderFile";
        v23 = 6429;
        v24 = 5;
        v25 = L"PDBX";
        FileW = (void *)(v5 + 18);
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v22, L"Created %ws", &FileW);
      }
      goto LABEL_17;
    }
    CurrentThreadId = GetCurrentThreadId();
    v13 = GetLastError();
    v11 = (unsigned int *)FrsStatusList::PushNewError(
                            v14,
                            v13,
                            0,
                            1,
                            "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                            "PdbManager::CreateDbLossNameHolderFile",
                            6426,
                            CurrentThreadId,
                            0);
    if ( !v11 )
      goto LABEL_17;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v22 = L"PdbManager::CreateDbLossNameHolderFile";
    v23 = 6434;
    v24 = 2;
    v25 = L"PDBX";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v22, L"%?", v11);
  }
  v15 = GetCurrentThreadId();
  v6 = FrsStatusList::PushNewError(
         v16,
         v11[1],
         v11[2],
         *v11,
         "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
         "PdbManager::CreateDbLossNameHolderFile",
         6437,
         v15,
         v11);
LABEL_17:
  v18 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v19);
  v20 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v21);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x14006fc2c  mov     [rsp-8+arg_0], rbx
0x14006fc31  mov     [rsp-8+arg_10], rsi
0x14006fc36  push    rbp
0x14006fc37  push    rdi
0x14006fc38  push    r12
0x14006fc3a  push    r13
0x14006fc3c  push    r14
0x14006fc3e  lea     rbp, [rsp-37h]
0x14006fc43  sub     rsp, 90h
0x14006fc4a  mov     r9, rcx
0x14006fc4d  lea     rcx, [rbp+57h+var_50]; this
0x14006fc51  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14006fc56  nop
0x14006fc57  lea     rcx, [rbp+57h+var_60]; this
0x14006fc5b  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14006fc60  nop
0x14006fc61  lea     r8, [rbp+57h+var_60]; struct FilePath *
0x14006fc65  lea     rdx, [rbp+57h+var_50]; struct FilePath *
0x14006fc69  mov     rcx, r9; this
0x14006fc6c  call    ?BuildDbLossFileNames@PdbManager@@AEAAXAEAVFilePath@@0@Z; PdbManager::BuildDbLossFileNames(FilePath &,FilePath &)
0x14006fc71  mov     rcx, [rbp+57h+var_48]
0x14006fc75  add     rcx, 12h; lpFileName
0x14006fc79  call    cs:__imp_DeleteFileW
0x14006fc80  nop     dword ptr [rax+rax+00h]
0x14006fc85  mov     ebx, eax
0x14006fc87  call    cs:__imp_GetLastError
0x14006fc8e  nop     dword ptr [rax+rax+00h]
0x14006fc93  mov     esi, eax
0x14006fc95  lea     r12, aPdbmanagerCrea_0; "PdbManager::CreateDbLossNameHolderFile"
0x14006fc9c  lea     r13, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x14006fca3  mov     r14, [rbp+57h+var_58]
0x14006fca7  xor     edi, edi
0x14006fca9  test    ebx, ebx
0x14006fcab  jnz     short loc_14006FCB2
0x14006fcad  cmp     eax, 2
0x14006fcb0  jnz     short loc_14006FCDB
0x14006fcb2  lea     rcx, [r14+12h]; lpFileName
0x14006fcb6  call    cs:__imp_DeleteFileW
0x14006fcbd  nop     dword ptr [rax+rax+00h]
0x14006fcc2  mov     ebx, eax
0x14006fcc4  call    cs:__imp_GetLastError
0x14006fccb  nop     dword ptr [rax+rax+00h]
0x14006fcd0  mov     esi, eax
0x14006fcd2  test    ebx, ebx
0x14006fcd4  jnz     short loc_14006FD1E
0x14006fcd6  cmp     eax, 2
0x14006fcd9  jz      short loc_14006FD1E
0x14006fcdb  call    cs:__imp_GetCurrentThreadId
0x14006fce2  nop     dword ptr [rax+rax+00h]
0x14006fce7  mov     [rsp+0B0h+var_70], rdi
0x14006fcec  mov     [rsp+0B0h+var_78], eax
0x14006fcf0  mov     dword ptr [rsp+0B0h+hTemplateFile], 190Dh
0x14006fcf8  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r12
0x14006fcfd  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r13
0x14006fd02  mov     r9d, 3
0x14006fd08  xor     r8d, r8d
0x14006fd0b  mov     edx, esi
0x14006fd0d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14006fd12  mov     rbx, rax
0x14006fd15  test    rax, rax
0x14006fd18  jnz     loc_14006FE13
0x14006fd1e  lea     rbx, [r14+12h]
0x14006fd22  mov     [rsp+0B0h+hTemplateFile], rdi; hTemplateFile
0x14006fd27  mov     [rsp+0B0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x14006fd2b  mov     esi, 1
0x14006fd30  mov     [rsp+0B0h+dwCreationDisposition], esi; dwCreationDisposition
0x14006fd34  xor     r9d, r9d; lpSecurityAttributes
0x14006fd37  xor     r8d, r8d; dwShareMode
0x14006fd3a  xor     edx, edx; dwDesiredAccess
0x14006fd3c  mov     rcx, rbx; lpFileName
0x14006fd3f  call    cs:__imp_CreateFileW
0x14006fd46  nop     dword ptr [rax+rax+00h]
0x14006fd4b  mov     [rbp+57h+arg_8], rax
0x14006fd4f  dec     rax
0x14006fd52  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006fd56  ja      short loc_14006FDC5
0x14006fd58  lea     rcx, [rbp+57h+arg_8]; void **
0x14006fd5c  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14006fd61  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14006fd68  test    rax, rax
0x14006fd6b  jz      loc_14006FE9F
0x14006fd71  cmp     [rax+40h], edi
0x14006fd74  jz      loc_14006FE9F
0x14006fd7a  cmp     dword ptr [rax+38h], 5
0x14006fd7e  jl      loc_14006FE9F
0x14006fd84  lea     rax, aPdbmanagerCrea_2; "PdbManager::CreateDbLossNameHolderFile"
0x14006fd8b  mov     [rbp+57h+var_40], rax
0x14006fd8f  mov     [rbp+57h+var_38], 191Dh
0x14006fd96  mov     [rbp+57h+var_34], 5
0x14006fd9d  lea     rax, aPdbx; "PDBX"
0x14006fda4  mov     [rbp+57h+var_30], rax
0x14006fda8  mov     [rbp+57h+arg_8], rbx
0x14006fdac  lea     r8, [rbp+57h+arg_8]
0x14006fdb0  lea     rdx, aCreatedWs; "Created %ws"
0x14006fdb7  lea     rcx, [rbp+57h+var_40]
0x14006fdbb  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14006fdc0  jmp     loc_14006FE9F
0x14006fdc5  call    cs:__imp_GetCurrentThreadId
0x14006fdcc  nop     dword ptr [rax+rax+00h]
0x14006fdd1  mov     ebx, eax
0x14006fdd3  call    cs:__imp_GetLastError
0x14006fdda  nop     dword ptr [rax+rax+00h]
0x14006fddf  mov     [rsp+0B0h+var_70], rdi
0x14006fde4  mov     [rsp+0B0h+var_78], ebx
0x14006fde8  mov     dword ptr [rsp+0B0h+hTemplateFile], 191Ah
0x14006fdf0  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r12
0x14006fdf5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r13
0x14006fdfa  mov     r9d, esi
0x14006fdfd  xor     r8d, r8d
0x14006fe00  mov     edx, eax
0x14006fe02  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14006fe07  mov     rbx, rax
0x14006fe0a  test    rax, rax
0x14006fe0d  jz      loc_14006FE9F
0x14006fe13  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14006fe1a  test    rax, rax
0x14006fe1d  jz      short loc_14006FE66
0x14006fe1f  cmp     [rax+40h], edi
0x14006fe22  jz      short loc_14006FE61
0x14006fe24  cmp     dword ptr [rax+38h], 2
0x14006fe28  jl      short loc_14006FE61
0x14006fe2a  lea     rax, aPdbmanagerCrea_2; "PdbManager::CreateDbLossNameHolderFile"
0x14006fe31  mov     [rbp+57h+var_40], rax
0x14006fe35  mov     [rbp+57h+var_38], 1922h
0x14006fe3c  mov     [rbp+57h+var_34], 2
0x14006fe43  lea     rax, aPdbx; "PDBX"
0x14006fe4a  mov     [rbp+57h+var_30], rax
0x14006fe4e  mov     r8, rbx
0x14006fe51  lea     rdx, asc_1402529CC; "%?"
0x14006fe58  lea     rcx, [rbp+57h+var_40]
0x14006fe5c  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14006fe61  test    rbx, rbx
0x14006fe64  jz      short loc_14006FE9F
0x14006fe66  call    cs:__imp_GetCurrentThreadId
0x14006fe6d  nop     dword ptr [rax+rax+00h]
0x14006fe72  mov     [rsp+0B0h+var_70], rbx
0x14006fe77  mov     [rsp+0B0h+var_78], eax
0x14006fe7b  mov     dword ptr [rsp+0B0h+hTemplateFile], 1925h
0x14006fe83  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r12
0x14006fe88  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r13
0x14006fe8d  mov     r9d, [rbx]
0x14006fe90  mov     r8d, [rbx+8]
0x14006fe94  mov     edx, [rbx+4]
0x14006fe97  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14006fe9c  mov     rdi, rax
0x14006fe9f  lea     rbx, ??_7FilePath@@6B@; const FilePath::`vftable'
0x14006fea6  mov     [rbp+57h+var_60], rbx
0x14006feaa  lea     rcx, [rbp+57h+var_58]
0x14006feae  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14006feb3  nop
0x14006feb4  mov     [rbp+57h+var_50], rbx
0x14006feb8  lea     rcx, [rbp+57h+var_48]
0x14006febc  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14006fec1  mov     rax, rdi
0x14006fec4  lea     r11, [rsp+0B0h+var_20]
0x14006fecc  mov     rbx, [r11+30h]
0x14006fed0  mov     rsi, [r11+40h]
0x14006fed4  mov     rsp, r11
0x14006fed7  pop     r14
0x14006fed9  pop     r13
0x14006fedb  pop     r12
0x14006fedd  pop     rdi
0x14006fede  pop     rbp
0x14006fedf  retn
```
