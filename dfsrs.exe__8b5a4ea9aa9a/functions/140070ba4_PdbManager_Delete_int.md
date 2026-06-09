# PdbManager::Delete(int)

- ea: `0x140070ba4`
- end: `0x140070e29`
- name: `?Delete@PdbManager@@QEAAPEAVFrsStatus@@H@Z`
- size: `645`
- prototype: `struct FrsStatus *__fastcall(PdbManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140072eac`
- `0x140080330`

## callees

- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x1400248f4`
- `0x14006f414`
- `0x140070ba4`
- `0x1400aee70`
- `0x1401b9494`
- `0x1401beb30`
- `0x1401bec7c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140070c57`
- `KERNEL32!DeleteFileW` at `0x140070d28`
- `KERNEL32!DeleteFileW` at `0x140070c57`
- `KERNEL32!DeleteFileW` at `0x140070d28`
- `KERNEL32!GetLastError` at `0x140070c6b`
- `KERNEL32!GetLastError` at `0x140070c6b`
- `KERNEL32!GetCurrentThreadId` at `0x140070c86`
- `KERNEL32!GetCurrentThreadId` at `0x140070d95`
- `KERNEL32!GetCurrentThreadId` at `0x140070c86`
- `KERNEL32!GetCurrentThreadId` at `0x140070d95`
- `ESENT!JetTerm2` at `0x140070c0b`
- `ESENT!JetTerm2` at `0x140070c0b`

## string_xrefs

- `0x140070c25`: `PdbManager::Delete`
- `0x140070cdf`: `PdbManager::Delete`
- `0x140070d0b`: `Failed to delete %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall PdbManager::Delete(PdbManager *this, int a2)
{
  __int64 v4; // rbx
  struct FrsStatus *v5; // rdi
  struct FrsStatus *v6; // r15
  DWORD LastError; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  struct FrsStatus *v10; // rax
  DWORD v11; // eax
  __int64 v12; // rcx
  void **v14; // [rsp+50h] [rbp-19h] BYREF
  __int64 v15; // [rsp+58h] [rbp-11h] BYREF
  void **v16; // [rsp+60h] [rbp-9h] BYREF
  __int64 v17; // [rsp+68h] [rbp-1h] BYREF
  void **v18; // [rsp+70h] [rbp+7h] BYREF
  __int64 v19; // [rsp+78h] [rbp+Fh] BYREF
  const wchar_t *v20; // [rsp+80h] [rbp+17h] BYREF
  int v21; // [rsp+88h] [rbp+1Fh]
  int v22; // [rsp+8Ch] [rbp+23h]
  const wchar_t *v23; // [rsp+90h] [rbp+27h]
  struct FrsStatus *v24; // [rsp+D0h] [rbp+67h] BYREF
  void **v25; // [rsp+E0h] [rbp+77h] BYREF

  FilePath::FilePath((FilePath *)&v18);
  FilePath::FilePath((FilePath *)&v16);
  FilePath::FilePath((FilePath *)&v14, (const struct FilePath *)(*(_QWORD *)this + 32LL));
  v25 = &NtfsFileSystem::`vftable';
  v4 = 0;
  v5 = 0;
  if ( *(_DWORD *)(*(_QWORD *)this + 56LL) )
  {
    JetTerm2(*(_QWORD *)(*(_QWORD *)this + 48LL), 6u);
    *(_QWORD *)(*(_QWORD *)this + 48LL) = -1;
    *(_DWORD *)(*(_QWORD *)this + 56LL) = 0;
  }
  if ( a2 )
  {
    PdbManager::BuildDbLossFileNames(this, (struct FilePath *)&v18, (struct FilePath *)&v16);
    v6 = (struct FrsStatus *)(v19 + 18);
    if ( DeleteFileW((LPCWSTR)(v19 + 18)) )
      goto LABEL_11;
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
      goto LABEL_11;
    CurrentThreadId = GetCurrentThreadId();
    v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v9,
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
                               "PdbManager::Delete",
                               7477,
                               CurrentThreadId,
                               0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v20 = L"PdbManager::Delete";
      v21 = 7478;
      v22 = 2;
      v23 = L"PDBX";
      v24 = v6;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v20, L"Failed to delete %s", &v24);
    }
    if ( !v5 )
LABEL_11:
      DeleteFileW((LPCWSTR)(v17 + 18));
  }
  FilePath::ChopToParent((FilePath *)&v14);
  if ( v5 )
    goto LABEL_17;
  v10 = (struct FrsStatus *)NtfsFileSystem::DeleteDirectory(
                              &v25,
                              *(_QWORD *)(*(_QWORD *)this + 8LL) + 168LL,
                              v15 + 18,
                              1);
  v5 = v10;
  v24 = v10;
  if ( v10 && (unsigned int)(*((_DWORD *)v10 + 1) - 2) <= 1 )
  {
    CLEAR_ERROR(&v24);
    v5 = v24;
  }
  if ( v5 )
  {
LABEL_17:
    v11 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v12,
           *((unsigned int *)v5 + 1),
           *((unsigned int *)v5 + 2),
           *(unsigned int *)v5,
           "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
           "PdbManager::Delete",
           7504,
           v11,
           v5);
  }
  v25 = &FileSystem::`vftable';
  v14 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v15);
  v16 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v17);
  v18 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v19);
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x140070ba4  mov     [rsp-8+arg_8], rbx
0x140070ba9  mov     [rsp-8+arg_18], rsi
0x140070bae  push    rbp
0x140070baf  push    rdi
0x140070bb0  push    r13
0x140070bb2  push    r14
0x140070bb4  push    r15
0x140070bb6  lea     rbp, [rsp-37h]
0x140070bbb  sub     rsp, 0A0h
0x140070bc2  mov     r14d, edx
0x140070bc5  mov     rsi, rcx
0x140070bc8  lea     rcx, [rbp+57h+var_50]; this
0x140070bcc  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140070bd1  nop
0x140070bd2  lea     rcx, [rbp+57h+var_60]; this
0x140070bd6  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140070bdb  nop
0x140070bdc  mov     rdx, [rsi]
0x140070bdf  add     rdx, 20h ; ' '; struct FilePath *
0x140070be3  lea     rcx, [rbp+57h+var_70]; this
0x140070be7  call    ??0FilePath@@QEAA@AEBV0@@Z; FilePath::FilePath(FilePath const &)
0x140070bec  nop
0x140070bed  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x140070bf4  mov     [rbp+57h+arg_10], rax
0x140070bf8  xor     ebx, ebx
0x140070bfa  mov     edi, ebx
0x140070bfc  mov     rcx, [rsi]
0x140070bff  cmp     [rcx+38h], ebx
0x140070c02  jz      short loc_140070C25
0x140070c04  lea     edx, [rbx+6]; grbit
0x140070c07  mov     rcx, [rcx+30h]; instance
0x140070c0b  call    cs:__imp_JetTerm2
0x140070c12  nop     dword ptr [rax+rax+00h]
0x140070c17  mov     rax, [rsi]
0x140070c1a  or      qword ptr [rax+30h], 0FFFFFFFFFFFFFFFFh
0x140070c1f  mov     rax, [rsi]
0x140070c22  mov     [rax+38h], ebx
0x140070c25  lea     r13, aPdbmanagerDele; "PdbManager::Delete"
0x140070c2c  lea     r15, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070c33  test    r14d, r14d
0x140070c36  jz      loc_140070D3B
0x140070c3c  lea     r8, [rbp+57h+var_60]; struct FilePath *
0x140070c40  lea     rdx, [rbp+57h+var_50]; struct FilePath *
0x140070c44  mov     rcx, rsi; this
0x140070c47  call    ?BuildDbLossFileNames@PdbManager@@AEAAXAEAVFilePath@@0@Z; PdbManager::BuildDbLossFileNames(FilePath &,FilePath &)
0x140070c4c  mov     r15, [rbp+57h+var_48]
0x140070c50  add     r15, 12h
0x140070c54  mov     rcx, r15; lpFileName
0x140070c57  call    cs:__imp_DeleteFileW
0x140070c5e  nop     dword ptr [rax+rax+00h]
0x140070c63  test    eax, eax
0x140070c65  jnz     loc_140070D20
0x140070c6b  call    cs:__imp_GetLastError
0x140070c72  nop     dword ptr [rax+rax+00h]
0x140070c77  mov     r14d, eax
0x140070c7a  lea     ecx, [rax-2]
0x140070c7d  cmp     ecx, 1
0x140070c80  jbe     loc_140070D20
0x140070c86  call    cs:__imp_GetCurrentThreadId
0x140070c8d  nop     dword ptr [rax+rax+00h]
0x140070c92  mov     [rsp+0C0h+var_80], rbx
0x140070c97  mov     [rsp+0C0h+var_88], eax
0x140070c9b  mov     [rsp+0C0h+var_90], 1D35h
0x140070ca3  mov     [rsp+0C0h+var_98], r13
0x140070ca8  lea     rax, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070caf  mov     [rsp+0C0h+var_A0], rax
0x140070cb4  mov     r9d, 1
0x140070cba  xor     r8d, r8d
0x140070cbd  mov     edx, r14d
0x140070cc0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140070cc5  mov     rdi, rax
0x140070cc8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140070ccf  test    rax, rax
0x140070cd2  jz      short loc_140070D1B
0x140070cd4  cmp     [rax+40h], ebx
0x140070cd7  jz      short loc_140070D1B
0x140070cd9  cmp     dword ptr [rax+38h], 2
0x140070cdd  jl      short loc_140070D1B
0x140070cdf  lea     rax, aPdbmanagerDele_0; "PdbManager::Delete"
0x140070ce6  mov     [rbp+57h+var_40], rax
0x140070cea  mov     [rbp+57h+var_38], 1D36h
0x140070cf1  mov     [rbp+57h+var_34], 2
0x140070cf8  lea     rax, aPdbx; "PDBX"
0x140070cff  mov     [rbp+57h+var_30], rax
0x140070d03  mov     [rbp+57h+arg_0], r15
0x140070d07  lea     r8, [rbp+57h+arg_0]
0x140070d0b  lea     rdx, aFailedToDelete_5; "Failed to delete %s"
0x140070d12  lea     rcx, [rbp+57h+var_40]
0x140070d16  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140070d1b  test    rdi, rdi
0x140070d1e  jnz     short loc_140070D34
0x140070d20  mov     rcx, [rbp+57h+var_58]
0x140070d24  add     rcx, 12h; lpFileName
0x140070d28  call    cs:__imp_DeleteFileW
0x140070d2f  nop     dword ptr [rax+rax+00h]
0x140070d34  lea     r15, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x140070d3b  lea     rcx, [rbp+57h+var_70]; this
0x140070d3f  call    ?ChopToParent@FilePath@@QEAAHXZ; FilePath::ChopToParent(void)
0x140070d44  test    rdi, rdi
0x140070d47  jnz     short loc_140070D95
0x140070d49  mov     r8, [rbp+57h+var_68]
0x140070d4d  add     r8, 12h
0x140070d51  mov     rax, [rsi]
0x140070d54  mov     rdx, [rax+8]
0x140070d58  add     rdx, 0A8h
0x140070d5f  lea     r9d, [rdi+1]
0x140070d63  lea     rcx, [rbp+57h+arg_10]
0x140070d67  call    ?DeleteDirectory@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@PEBGW4CONTINUE_DELETE@FileSystem@@@Z; NtfsFileSystem::DeleteDirectory(VolumeId const &,ushort const *,FileSystem::CONTINUE_DELETE)
0x140070d6c  mov     rdi, rax
0x140070d6f  mov     [rbp+57h+arg_0], rax
0x140070d73  test    rax, rax
0x140070d76  jz      short loc_140070D90
0x140070d78  mov     eax, [rax+4]
0x140070d7b  sub     eax, 2
0x140070d7e  cmp     eax, 1
0x140070d81  ja      short loc_140070D90
0x140070d83  lea     rcx, [rbp+57h+arg_0]; struct FrsStatus **
0x140070d87  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140070d8c  mov     rdi, [rbp+57h+arg_0]
0x140070d90  test    rdi, rdi
0x140070d93  jz      short loc_140070DCE
0x140070d95  call    cs:__imp_GetCurrentThreadId
0x140070d9c  nop     dword ptr [rax+rax+00h]
0x140070da1  mov     [rsp+0C0h+var_80], rdi
0x140070da6  mov     [rsp+0C0h+var_88], eax
0x140070daa  mov     [rsp+0C0h+var_90], 1D50h
0x140070db2  mov     [rsp+0C0h+var_98], r13
0x140070db7  mov     [rsp+0C0h+var_A0], r15
0x140070dbc  mov     r9d, [rdi]
0x140070dbf  mov     r8d, [rdi+8]
0x140070dc3  mov     edx, [rdi+4]
0x140070dc6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140070dcb  mov     rbx, rax
0x140070dce  lea     rax, ??_7FileSystem@@6B@; const FileSystem::`vftable'
0x140070dd5  mov     [rbp+57h+arg_10], rax
0x140070dd9  lea     rdi, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140070de0  mov     [rbp+57h+var_70], rdi
0x140070de4  lea     rcx, [rbp+57h+var_68]
0x140070de8  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140070ded  nop
0x140070dee  mov     [rbp+57h+var_60], rdi
0x140070df2  lea     rcx, [rbp+57h+var_58]
0x140070df6  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140070dfb  nop
0x140070dfc  mov     [rbp+57h+var_50], rdi
0x140070e00  lea     rcx, [rbp+57h+var_48]
0x140070e04  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140070e09  mov     rax, rbx
0x140070e0c  lea     r11, [rsp+0C0h+var_20]
0x140070e14  mov     rbx, [r11+38h]
0x140070e18  mov     rsi, [r11+48h]
0x140070e1c  mov     rsp, r11
0x140070e1f  pop     r15
0x140070e21  pop     r14
0x140070e23  pop     r13
0x140070e25  pop     rdi
0x140070e26  pop     rbp
0x140070e27  retn
```
