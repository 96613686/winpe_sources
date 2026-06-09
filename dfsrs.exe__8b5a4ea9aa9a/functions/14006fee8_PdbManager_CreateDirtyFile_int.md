# PdbManager::CreateDirtyFile(int)

- ea: `0x14006fee8`
- end: `0x14007021c`
- name: `?CreateDirtyFile@PdbManager@@AEAAPEAVFrsStatus@@H@Z`
- size: `820`
- prototype: `struct FrsStatus *__fastcall(PdbManager *__hidden this, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x140072a34`
- `0x140072eac`
- `0x14007a244`

## callees

- `0x14000cd1c`
- `0x14000cdc0`
- `0x14000ee94`
- `0x1400248f4`
- `0x14005c620`
- `0x14006fee8`
- `0x1400bdc18`
- `0x1401b9494`
- `0x1401be04c`
- `0x1401beb7c`
- `0x1401bebec`
- `0x1401bec7c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14006ff8b`
- `KERNEL32!DeleteFileW` at `0x14006ffba`
- `KERNEL32!DeleteFileW` at `0x14006ff8b`
- `KERNEL32!DeleteFileW` at `0x14006ffba`
- `KERNEL32!CreateFileW` at `0x140070055`
- `KERNEL32!CreateFileW` at `0x140070055`
- `KERNEL32!GetLastError` at `0x14006ff99`
- `KERNEL32!GetLastError` at `0x14006ffc8`
- `KERNEL32!GetLastError` at `0x1400700e9`
- `KERNEL32!GetLastError` at `0x14006ff99`
- `KERNEL32!GetLastError` at `0x14006ffc8`
- `KERNEL32!GetLastError` at `0x1400700e9`
- `KERNEL32!GetCurrentThreadId` at `0x14006ffdf`
- `KERNEL32!GetCurrentThreadId` at `0x1400700db`
- `KERNEL32!GetCurrentThreadId` at `0x14007019d`
- `KERNEL32!GetCurrentThreadId` at `0x14006ffdf`
- `KERNEL32!GetCurrentThreadId` at `0x1400700db`
- `KERNEL32!GetCurrentThreadId` at `0x14007019d`

## string_xrefs

- `0x1400700c6`: `Created %ws`
- `0x14006fffc`: `PdbManager::CreateDirtyFile`
- `0x140070106`: `PdbManager::CreateDirtyFile`
- `0x14007013c`: `PdbManager::CreateDirtyFile`
- `0x14007009a`: `PdbManager::CreateDirtyFile`
- `0x140070161`: `PdbManager::CreateDirtyFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall PdbManager::CreateDirtyFile(PdbManager *this, int a2)
{
  __int64 v3; // r8
  WCHAR *v4; // r14
  BOOL v5; // ebx
  DWORD LastError; // eax
  DWORD v7; // esi
  __int64 v8; // r15
  __int64 v9; // rdi
  BOOL v10; // ebx
  DWORD v11; // eax
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  const WCHAR *v15; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD v17; // eax
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  void **v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h] BYREF
  void **v24; // [rsp+60h] [rbp+7h] BYREF
  __int64 v25; // [rsp+68h] [rbp+Fh] BYREF
  const wchar_t *v26; // [rsp+70h] [rbp+17h] BYREF
  int v27; // [rsp+78h] [rbp+1Fh]
  int v28; // [rsp+7Ch] [rbp+23h]
  const wchar_t *v29; // [rsp+80h] [rbp+27h]
  void *FileW; // [rsp+C0h] [rbp+67h] BYREF

  FilePath::FilePath((FilePath *)&v22);
  FilePath::FilePath((FilePath *)&v24);
  FileUtil::CreateWin32LongPath((const struct FilePath *)(*(_QWORD *)v3 + 32LL), (struct FilePath *)&v22);
  FilePath::ChopToParent((FilePath *)&v22);
  LOWORD(FileW) = 92;
  FrsStringImpl<unsigned short,char>::Append(&v23, &FileW, 1);
  FilePath::operator=(&v24, &v22);
  FilePath::Append((FilePath *)&v22, L"$db_dirty$");
  FilePath::Append((FilePath *)&v24, L"$db_clean$");
  v4 = (WCHAR *)(v25 + 18);
  v5 = DeleteFileW((LPCWSTR)(v25 + 18));
  LastError = GetLastError();
  v7 = LastError;
  v8 = v23;
  v9 = 0;
  if ( (v5 || LastError == 2)
    && ((v10 = DeleteFileW((LPCWSTR)(v23 + 18)), v11 = GetLastError(), v7 = v11, v10) || v11 == 2)
    || (v12 = GetCurrentThreadId(),
        (v14 = FrsStatusList::PushNewError(
                 v13,
                 v7,
                 0,
                 3,
                 "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                 "PdbManager::CreateDirtyFile",
                 6254,
                 v12,
                 0)) == 0) )
  {
    v15 = (const WCHAR *)(v8 + 18);
    if ( !a2 )
      v15 = v4;
    FileW = CreateFileW(v15, 0, 0, 0, 1u, 0, 0);
    if ( (char *)FileW - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandleEx(&FileW);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v26 = L"PdbManager::CreateDirtyFile";
        v27 = 6270;
        v28 = 5;
        v29 = L"PDBX";
        FileW = v4;
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v26, L"Created %ws", &FileW);
      }
      goto LABEL_19;
    }
    CurrentThreadId = GetCurrentThreadId();
    v17 = GetLastError();
    v14 = FrsStatusList::PushNewError(
            v18,
            v17,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
            "PdbManager::CreateDirtyFile",
            6267,
            CurrentThreadId,
            0);
    if ( !v14 )
      goto LABEL_19;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v26 = L"PdbManager::CreateDirtyFile";
    v27 = 6275;
    v28 = 2;
    v29 = L"PDBX";
    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v26, L"%?", v14);
  }
  v19 = GetCurrentThreadId();
  v9 = FrsStatusList::PushNewError(
         v20,
         9218,
         0,
         3,
         "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
         "PdbManager::CreateDirtyFile",
         6282,
         v19,
         v14);
LABEL_19:
  v24 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v25);
  v22 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v23);
  return (struct FrsStatus *)v9;
}

```

## disassembly

```asm
0x14006fee8  mov     [rsp-8+arg_8], rbx
0x14006feed  mov     [rsp-8+arg_10], rsi
0x14006fef2  push    rbp
0x14006fef3  push    rdi
0x14006fef4  push    r12
0x14006fef6  push    r14
0x14006fef8  push    r15
0x14006fefa  lea     rbp, [rsp-37h]
0x14006feff  sub     rsp, 90h
0x14006ff06  mov     r12d, edx
0x14006ff09  mov     r8, rcx
0x14006ff0c  lea     rcx, [rbp+57h+var_60]; this
0x14006ff10  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14006ff15  nop
0x14006ff16  lea     rcx, [rbp+57h+var_50]; this
0x14006ff1a  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14006ff1f  nop
0x14006ff20  mov     rcx, [r8]
0x14006ff23  add     rcx, 20h ; ' '; struct FilePath *
0x14006ff27  lea     rdx, [rbp+57h+var_60]; struct FilePath *
0x14006ff2b  call    ?CreateWin32LongPath@FileUtil@@SAXAEBVFilePath@@AEAV2@@Z; FileUtil::CreateWin32LongPath(FilePath const &,FilePath &)
0x14006ff30  lea     rcx, [rbp+57h+var_60]; this
0x14006ff34  call    ?ChopToParent@FilePath@@QEAAHXZ; FilePath::ChopToParent(void)
0x14006ff39  mov     eax, 5Ch ; '\'
0x14006ff3e  mov     word ptr [rbp+57h+arg_0], ax
0x14006ff42  lea     r8d, [rax-5Bh]
0x14006ff46  lea     rdx, [rbp+57h+arg_0]
0x14006ff4a  lea     rcx, [rbp+57h+var_58]
0x14006ff4e  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x14006ff53  lea     rdx, [rbp+57h+var_60]
0x14006ff57  lea     rcx, [rbp+57h+var_50]
0x14006ff5b  call    ??4FilePath@@QEAAAEAV0@AEBV0@@Z; FilePath::operator=(FilePath const &)
0x14006ff60  lea     rdx, aDbDirty; "$db_dirty$"
0x14006ff67  lea     rcx, [rbp+57h+var_60]; this
0x14006ff6b  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14006ff70  lea     rdx, aDbClean; "$db_clean$"
0x14006ff77  lea     rcx, [rbp+57h+var_50]; this
0x14006ff7b  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14006ff80  mov     r14, [rbp+57h+var_48]
0x14006ff84  add     r14, 12h
0x14006ff88  mov     rcx, r14; lpFileName
0x14006ff8b  call    cs:__imp_DeleteFileW
0x14006ff92  nop     dword ptr [rax+rax+00h]
0x14006ff97  mov     ebx, eax
0x14006ff99  call    cs:__imp_GetLastError
0x14006ffa0  nop     dword ptr [rax+rax+00h]
0x14006ffa5  mov     esi, eax
0x14006ffa7  mov     r15, [rbp+57h+var_58]
0x14006ffab  xor     edi, edi
0x14006ffad  test    ebx, ebx
0x14006ffaf  jnz     short loc_14006FFB6
0x14006ffb1  cmp     eax, 2
0x14006ffb4  jnz     short loc_14006FFDF
0x14006ffb6  lea     rcx, [r15+12h]; lpFileName
0x14006ffba  call    cs:__imp_DeleteFileW
0x14006ffc1  nop     dword ptr [rax+rax+00h]
0x14006ffc6  mov     ebx, eax
0x14006ffc8  call    cs:__imp_GetLastError
0x14006ffcf  nop     dword ptr [rax+rax+00h]
0x14006ffd4  mov     esi, eax
0x14006ffd6  test    ebx, ebx
0x14006ffd8  jnz     short loc_140070030
0x14006ffda  cmp     eax, 2
0x14006ffdd  jz      short loc_140070030
0x14006ffdf  call    cs:__imp_GetCurrentThreadId
0x14006ffe6  nop     dword ptr [rax+rax+00h]
0x14006ffeb  mov     [rsp+0B0h+var_70], rdi
0x14006fff0  mov     [rsp+0B0h+var_78], eax
0x14006fff4  mov     dword ptr [rsp+0B0h+hTemplateFile], 186Eh
0x14006fffc  lea     rax, aPdbmanagerCrea_1; "PdbManager::CreateDirtyFile"
0x140070003  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x140070008  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x14007000f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x140070014  mov     r9d, 3
0x14007001a  xor     r8d, r8d
0x14007001d  mov     edx, esi
0x14007001f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140070024  mov     rbx, rax
0x140070027  test    rax, rax
0x14007002a  jnz     loc_14007013C
0x140070030  test    r12d, r12d
0x140070033  lea     rcx, [r15+12h]
0x140070037  jnz     short loc_14007003C
0x140070039  mov     rcx, r14; lpFileName
0x14007003c  mov     [rsp+0B0h+hTemplateFile], rdi; hTemplateFile
0x140070041  mov     [rsp+0B0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x140070045  mov     [rsp+0B0h+dwCreationDisposition], 1; dwCreationDisposition
0x14007004d  xor     r9d, r9d; lpSecurityAttributes
0x140070050  xor     r8d, r8d; dwShareMode
0x140070053  xor     edx, edx; dwDesiredAccess
0x140070055  call    cs:__imp_CreateFileW
0x14007005c  nop     dword ptr [rax+rax+00h]
0x140070061  mov     [rbp+57h+arg_0], rax
0x140070065  dec     rax
0x140070068  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14007006c  ja      short loc_1400700DB
0x14007006e  lea     rcx, [rbp+57h+arg_0]; void **
0x140070072  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x140070077  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14007007e  test    rax, rax
0x140070081  jz      loc_1400701DA
0x140070087  cmp     [rax+40h], edi
0x14007008a  jz      loc_1400701DA
0x140070090  cmp     dword ptr [rax+38h], 5
0x140070094  jl      loc_1400701DA
0x14007009a  lea     rax, aPdbmanagerCrea; "PdbManager::CreateDirtyFile"
0x1400700a1  mov     [rbp+57h+var_40], rax
0x1400700a5  mov     [rbp+57h+var_38], 187Eh
0x1400700ac  mov     [rbp+57h+var_34], 5
0x1400700b3  lea     rax, aPdbx; "PDBX"
0x1400700ba  mov     [rbp+57h+var_30], rax
0x1400700be  mov     [rbp+57h+arg_0], r14
0x1400700c2  lea     r8, [rbp+57h+arg_0]
0x1400700c6  lea     rdx, aCreatedWs; "Created %ws"
0x1400700cd  lea     rcx, [rbp+57h+var_40]
0x1400700d1  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1400700d6  jmp     loc_1400701DA
0x1400700db  call    cs:__imp_GetCurrentThreadId
0x1400700e2  nop     dword ptr [rax+rax+00h]
0x1400700e7  mov     ebx, eax
0x1400700e9  call    cs:__imp_GetLastError
0x1400700f0  nop     dword ptr [rax+rax+00h]
0x1400700f5  mov     [rsp+0B0h+var_70], rdi
0x1400700fa  mov     [rsp+0B0h+var_78], ebx
0x1400700fe  mov     dword ptr [rsp+0B0h+hTemplateFile], 187Bh
0x140070106  lea     rsi, aPdbmanagerCrea_1; "PdbManager::CreateDirtyFile"
0x14007010d  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rsi
0x140070112  lea     r14, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070119  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x14007011e  mov     r9d, 1
0x140070124  xor     r8d, r8d
0x140070127  mov     edx, eax
0x140070129  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14007012e  mov     rbx, rax
0x140070131  test    rax, rax
0x140070134  jz      loc_1400701DA
0x14007013a  jmp     short loc_14007014A
0x14007013c  lea     rsi, aPdbmanagerCrea_1; "PdbManager::CreateDirtyFile"
0x140070143  lea     r14, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x14007014a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140070151  test    rax, rax
0x140070154  jz      short loc_14007019D
0x140070156  cmp     [rax+40h], edi
0x140070159  jz      short loc_140070198
0x14007015b  cmp     dword ptr [rax+38h], 2
0x14007015f  jl      short loc_140070198
0x140070161  lea     rax, aPdbmanagerCrea; "PdbManager::CreateDirtyFile"
0x140070168  mov     [rbp+57h+var_40], rax
0x14007016c  mov     [rbp+57h+var_38], 1883h
0x140070173  mov     [rbp+57h+var_34], 2
0x14007017a  lea     rax, aPdbx; "PDBX"
0x140070181  mov     [rbp+57h+var_30], rax
0x140070185  mov     r8, rbx
0x140070188  lea     rdx, asc_1402529CC; "%?"
0x14007018f  lea     rcx, [rbp+57h+var_40]
0x140070193  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x140070198  test    rbx, rbx
0x14007019b  jz      short loc_1400701DA
0x14007019d  call    cs:__imp_GetCurrentThreadId
0x1400701a4  nop     dword ptr [rax+rax+00h]
0x1400701a9  mov     [rsp+0B0h+var_70], rbx
0x1400701ae  mov     [rsp+0B0h+var_78], eax
0x1400701b2  mov     dword ptr [rsp+0B0h+hTemplateFile], 188Ah
0x1400701ba  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rsi
0x1400701bf  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x1400701c4  mov     r9d, 3
0x1400701ca  xor     r8d, r8d
0x1400701cd  mov     edx, 2402h
0x1400701d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400701d7  mov     rdi, rax
0x1400701da  lea     rbx, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1400701e1  mov     [rbp+57h+var_50], rbx
0x1400701e5  lea     rcx, [rbp+57h+var_48]
0x1400701e9  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400701ee  nop
0x1400701ef  mov     [rbp+57h+var_60], rbx
0x1400701f3  lea     rcx, [rbp+57h+var_58]
0x1400701f7  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400701fc  mov     rax, rdi
0x1400701ff  lea     r11, [rsp+0B0h+var_20]
0x140070207  mov     rbx, [r11+38h]
0x14007020b  mov     rsi, [r11+40h]
0x14007020f  mov     rsp, r11
0x140070212  pop     r15
0x140070214  pop     r14
0x140070216  pop     r12
0x140070218  pop     rdi
0x140070219  pop     rbp
0x14007021a  retn
```
