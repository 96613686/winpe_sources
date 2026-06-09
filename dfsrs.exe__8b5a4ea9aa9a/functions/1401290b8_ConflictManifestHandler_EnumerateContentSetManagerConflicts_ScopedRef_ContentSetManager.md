# ConflictManifestHandler::EnumerateContentSetManagerConflicts(ScopedRef<ContentSetManager> &)

- ea: `0x1401290b8`
- end: `0x140129573`
- name: `?EnumerateContentSetManagerConflicts@ConflictManifestHandler@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VContentSetManager@@@@@Z`
- size: `1211`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140128f78`
- `0x14012a708`
- `0x14012af00`

## callees

- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001c1ac`
- `0x1400248f4`
- `0x140029390`
- `0x14004698c`
- `0x14005e8ec`
- `0x1401290b8`
- `0x140129920`
- `0x1401b9494`
- `0x1401bf3d0`
- `0x140223010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140129426`
- `KERNEL32!DeleteFileW` at `0x140129426`
- `KERNEL32!SetFileAttributesW` at `0x140129406`
- `KERNEL32!SetFileAttributesW` at `0x140129406`
- `KERNEL32!GetFileAttributesW` at `0x1401291b2`
- `KERNEL32!GetFileAttributesW` at `0x1401291b2`
- `KERNEL32!GetLastError` at `0x1401291d5`
- `KERNEL32!GetLastError` at `0x140129415`
- `KERNEL32!GetLastError` at `0x140129470`
- `KERNEL32!GetLastError` at `0x1401291d5`
- `KERNEL32!GetLastError` at `0x140129415`
- `KERNEL32!GetLastError` at `0x140129470`
- `KERNEL32!GetCurrentThreadId` at `0x140129140`
- `KERNEL32!GetCurrentThreadId` at `0x1401291c7`
- `KERNEL32!GetCurrentThreadId` at `0x1401292ba`
- `KERNEL32!GetCurrentThreadId` at `0x140129327`
- `KERNEL32!GetCurrentThreadId` at `0x1401294bb`
- `KERNEL32!GetCurrentThreadId` at `0x140129510`
- `KERNEL32!GetCurrentThreadId` at `0x140129140`
- `KERNEL32!GetCurrentThreadId` at `0x1401291c7`
- `KERNEL32!GetCurrentThreadId` at `0x1401292ba`
- `KERNEL32!GetCurrentThreadId` at `0x140129327`
- `KERNEL32!GetCurrentThreadId` at `0x1401294bb`
- `KERNEL32!GetCurrentThreadId` at `0x140129510`
- `ole32!CoCreateInstance` at `0x1401292ab`
- `ole32!CoCreateInstance` at `0x1401292ab`

## string_xrefs

- `0x140129169`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x1401291fe`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x1401292e3`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x140129349`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x14012936b`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x1401294b4`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x1401290ec`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x14012915d`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x1401291f2`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x1401292d7`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x140129305`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x1401294ad`: `ConflictManifestHandler::EnumerateContentSetManagerConflicts`
- `0x1401293ee`: `Error parsing %?, 0x%.08x: Deleting ConflictManifest file.`
- `0x14012949d`: `Error deleting ConflictManifest file %?. sfaGle=x%x, dfGle=x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConflictManifestHandler::EnumerateContentSetManagerConflicts(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  unsigned int *v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  __int64 v10; // rsi
  DWORD v11; // ebx
  DWORD LastError; // eax
  struct FrsStatus *v13; // rax
  DWORD v14; // eax
  __int64 v15; // rcx
  DWORD v16; // eax
  __int64 v17; // rcx
  struct FrsStatus *v18; // rbx
  BOOL v19; // r14d
  DWORD v20; // esi
  BOOL v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  LPVOID ppv; // [rsp+50h] [rbp-19h] BYREF
  struct FrsStatus *v29; // [rsp+58h] [rbp-11h] BYREF
  void **v30; // [rsp+60h] [rbp-9h] BYREF
  __int64 v31; // [rsp+68h] [rbp-1h] BYREF
  const wchar_t *v32; // [rsp+70h] [rbp+7h] BYREF
  int v33; // [rsp+78h] [rbp+Fh]
  int v34; // [rsp+7Ch] [rbp+13h]
  const wchar_t *v35; // [rsp+80h] [rbp+17h]
  unsigned int v36; // [rsp+D8h] [rbp+6Fh] BYREF
  struct FrsStatus *v37; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = 0;
  v5 = 0;
  v36 = 0;
  ppv = 0;
  FilePath::FilePath((FilePath *)&v30);
  v6 = 0;
  if ( !*v7 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v32 = L"ConflictManifestHandler::EnumerateContentSetManagerConflicts";
      v33 = 649;
      v34 = 4;
      v35 = L"CONF";
      dbgobj::DbgPrint<unsigned short>(&v32, L"Content set manager has not been set");
    }
    CurrentThreadId = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v9,
           1237,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
           "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
           650,
           CurrentThreadId,
           0);
    v5 = (unsigned int *)v6;
  }
  if ( !v6 )
  {
    GetManifestPath(*a2, *(unsigned int *)(a1 + 152), &v30);
    v10 = v31 + 18;
    if ( GetFileAttributesW((LPCWSTR)(v31 + 18)) == -1 )
    {
      v11 = GetCurrentThreadId();
      LastError = GetLastError();
      v13 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                                  LastError,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                                  "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
                                  658,
                                  v11,
                                  0);
      v37 = v13;
      if ( v13 )
      {
        if ( (unsigned int)FrsStatus::IsFileDeletedError(v13) )
        {
          CLEAR_ERROR(&v37);
          goto LABEL_42;
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v32 = L"ConflictManifestHandler::EnumerateContentSetManagerConflicts";
          v33 = 664;
          v34 = 3;
          v35 = L"CONF";
          v38 = v10;
          dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
            &v32,
            L"Failed to get file attributes %?. Error:%?",
            &v38);
        }
        CLEAR_ERROR(&v37);
      }
    }
    v36 = CoCreateInstance(
            &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
            0,
            0x17u,
            &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
            &ppv);
    v14 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v15,
           v36,
           0,
           4,
           "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
           "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
           678,
           v14,
           0);
    v5 = (unsigned int *)v6;
  }
  if ( !v6 )
  {
    v36 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 80LL))(ppv, a1);
    v16 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v17,
           v36,
           0,
           4,
           "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
           "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
           684,
           v16,
           0);
    v5 = (unsigned int *)v6;
  }
  if ( !v6 )
  {
    FilePath::TrimLongPathChars((FilePath *)&v30);
    v18 = (struct FrsStatus *)(v31 + 18);
    v36 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, v31 + 18);
    if ( v36 + 1072896768 <= 0x87 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v32 = L"ConflictManifestHandler::EnumerateContentSetManagerConflicts";
        v33 = 695;
        v34 = 2;
        v35 = L"CONF";
        v37 = v18;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long>(
          &v32,
          L"Error parsing %?, 0x%.08x: Deleting ConflictManifest file.",
          &v37,
          &v36);
      }
      v19 = SetFileAttributesW((LPCWSTR)v18, 0x80u);
      v20 = GetLastError();
      v21 = DeleteFileW((LPCWSTR)v18);
      if ( (!v19 || !v21)
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v32 = L"ConflictManifestHandler::EnumerateContentSetManagerConflicts";
        v33 = 703;
        v34 = 5;
        v35 = L"CONF";
        if ( v21 )
          v22 = 0;
        else
          v22 = GetLastError();
        LODWORD(v37) = v22;
        if ( v19 )
          v20 = 0;
        LODWORD(v38) = v20;
        v29 = v18;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long,unsigned long>(
          (unsigned int)&v32,
          (unsigned int)L"Error deleting ConflictManifest file %?. sfaGle=x%x, dfGle=x%x",
          (unsigned int)&v29,
          (unsigned int)&v38,
          (__int64)&v37);
      }
    }
    v23 = GetCurrentThreadId();
    v5 = (unsigned int *)FrsStatusList::PushNewError(
                           v24,
                           v36,
                           0,
                           4,
                           "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                           "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
                           709,
                           v23,
                           0);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v5 )
  {
    v25 = GetCurrentThreadId();
    v4 = FrsStatusList::PushNewError(
           v26,
           v5[1],
           v5[2],
           *v5,
           "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
           "ConflictManifestHandler::EnumerateContentSetManagerConflicts",
           716,
           v25,
           v5);
  }
LABEL_42:
  v30 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v31);
  return v4;
}

```

## disassembly

```asm
0x1401290b8  push    rbp
0x1401290ba  push    rbx
0x1401290bb  push    rsi
0x1401290bc  push    rdi
0x1401290bd  push    r12
0x1401290bf  push    r14
0x1401290c1  push    r15
0x1401290c3  lea     rbp, [rsp-27h]
0x1401290c8  sub     rsp, 90h
0x1401290cf  mov     rsi, rdx
0x1401290d2  mov     r14, rcx
0x1401290d5  xor     edi, edi
0x1401290d7  mov     ebx, edi
0x1401290d9  mov     [rbp+57h+arg_8], edi
0x1401290dc  mov     [rbp+57h+var_70], rdi
0x1401290e0  lea     rcx, [rbp+57h+var_60]; this
0x1401290e4  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1401290e9  nop
0x1401290ea  mov     eax, edi
0x1401290ec  lea     r15, aConflictmanife_4; "ConflictManifestHandler::EnumerateConte"...
0x1401290f3  lea     r12, aConf; "CONF"
0x1401290fa  cmp     [rdx], rdi
0x1401290fd  jnz     loc_14012918B
0x140129103  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012910a  test    rax, rax
0x14012910d  jz      short loc_140129140
0x14012910f  cmp     [rax+40h], edi
0x140129112  jz      short loc_140129140
0x140129114  cmp     dword ptr [rax+38h], 4
0x140129118  jl      short loc_140129140
0x14012911a  mov     [rbp+57h+var_50], r15
0x14012911e  mov     [rbp+57h+var_48], 289h
0x140129125  mov     [rbp+57h+var_44], 4
0x14012912c  mov     [rbp+57h+var_40], r12
0x140129130  lea     rdx, aContentSetMana_0; "Content set manager has not been set"
0x140129137  lea     rcx, [rbp+57h+var_50]
0x14012913b  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140129140  call    cs:__imp_GetCurrentThreadId
0x140129147  nop     dword ptr [rax+rax+00h]
0x14012914c  mov     [rsp+0C0h+var_80], rdi
0x140129151  mov     [rsp+0C0h+var_88], eax
0x140129155  mov     [rsp+0C0h+var_90], 28Ah
0x14012915d  lea     rax, aConflictmanife; "ConflictManifestHandler::EnumerateConte"...
0x140129164  mov     [rsp+0C0h+var_98], rax
0x140129169  lea     rax, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129170  mov     [rsp+0C0h+ppv], rax
0x140129175  mov     r9d, 1
0x14012917b  xor     r8d, r8d
0x14012917e  mov     edx, 4D5h
0x140129183  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129188  mov     rbx, rax
0x14012918b  test    rax, rax
0x14012918e  jnz     loc_140129305
0x140129194  lea     r8, [rbp+57h+var_60]
0x140129198  mov     edx, [r14+98h]
0x14012919f  mov     rcx, [rsi]
0x1401291a2  call    GetManifestPath
0x1401291a7  mov     rsi, [rbp+57h+var_58]
0x1401291ab  add     rsi, 12h
0x1401291af  mov     rcx, rsi; lpFileName
0x1401291b2  call    cs:__imp_GetFileAttributesW
0x1401291b9  nop     dword ptr [rax+rax+00h]
0x1401291be  cmp     eax, 0FFFFFFFFh
0x1401291c1  jnz     loc_14012928E
0x1401291c7  call    cs:__imp_GetCurrentThreadId
0x1401291ce  nop     dword ptr [rax+rax+00h]
0x1401291d3  mov     ebx, eax
0x1401291d5  call    cs:__imp_GetLastError
0x1401291dc  nop     dword ptr [rax+rax+00h]
0x1401291e1  mov     [rsp+0C0h+var_80], rdi
0x1401291e6  mov     [rsp+0C0h+var_88], ebx
0x1401291ea  mov     [rsp+0C0h+var_90], 292h
0x1401291f2  lea     rcx, aConflictmanife; "ConflictManifestHandler::EnumerateConte"...
0x1401291f9  mov     [rsp+0C0h+var_98], rcx
0x1401291fe  lea     rcx, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129205  mov     [rsp+0C0h+ppv], rcx
0x14012920a  mov     r9d, 1
0x140129210  xor     r8d, r8d
0x140129213  mov     edx, eax
0x140129215  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012921a  mov     r9, rax
0x14012921d  mov     [rbp+57h+arg_10], rax
0x140129221  test    rax, rax
0x140129224  jz      short loc_14012928E
0x140129226  mov     rcx, rax; this
0x140129229  call    ?IsFileDeletedError@FrsStatus@@QEBAHXZ; FrsStatus::IsFileDeletedError(void)
0x14012922e  test    eax, eax
0x140129230  jz      short loc_140129240
0x140129232  lea     rcx, [rbp+57h+arg_10]; struct FrsStatus **
0x140129236  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14012923b  jmp     loc_140129549
0x140129240  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140129247  test    rax, rax
0x14012924a  jz      short loc_140129285
0x14012924c  cmp     [rax+40h], edi
0x14012924f  jz      short loc_140129285
0x140129251  cmp     dword ptr [rax+38h], 3
0x140129255  jl      short loc_140129285
0x140129257  mov     [rbp+57h+var_50], r15
0x14012925b  mov     [rbp+57h+var_48], 298h
0x140129262  mov     [rbp+57h+var_44], 3
0x140129269  mov     [rbp+57h+var_40], r12
0x14012926d  mov     [rbp+57h+arg_18], rsi
0x140129271  lea     r8, [rbp+57h+arg_18]
0x140129275  lea     rdx, aFailedToGetFil; "Failed to get file attributes %?. Error"...
0x14012927c  lea     rcx, [rbp+57h+var_50]
0x140129280  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x140129285  lea     rcx, [rbp+57h+arg_10]; struct FrsStatus **
0x140129289  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14012928e  lea     rax, [rbp+57h+var_70]
0x140129292  mov     [rsp+0C0h+ppv], rax; ppv
0x140129297  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x14012929e  xor     edx, edx; pUnkOuter
0x1401292a0  lea     r8d, [rdx+17h]; dwClsContext
0x1401292a4  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x1401292ab  call    cs:__imp_CoCreateInstance
0x1401292b2  nop     dword ptr [rax+rax+00h]
0x1401292b7  mov     [rbp+57h+arg_8], eax
0x1401292ba  call    cs:__imp_GetCurrentThreadId
0x1401292c1  nop     dword ptr [rax+rax+00h]
0x1401292c6  mov     [rsp+0C0h+var_80], rdi
0x1401292cb  mov     [rsp+0C0h+var_88], eax
0x1401292cf  mov     [rsp+0C0h+var_90], 2A6h
0x1401292d7  lea     rsi, aConflictmanife; "ConflictManifestHandler::EnumerateConte"...
0x1401292de  mov     [rsp+0C0h+var_98], rsi
0x1401292e3  lea     rax, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x1401292ea  mov     [rsp+0C0h+ppv], rax
0x1401292ef  mov     r9d, 4
0x1401292f5  xor     r8d, r8d
0x1401292f8  mov     edx, [rbp+57h+arg_8]
0x1401292fb  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129300  mov     rbx, rax
0x140129303  jmp     short loc_14012930C
0x140129305  lea     rsi, aConflictmanife; "ConflictManifestHandler::EnumerateConte"...
0x14012930c  test    rax, rax
0x14012930f  jnz     short loc_14012936B
0x140129311  mov     rcx, [rbp+57h+var_70]
0x140129315  mov     rax, [rcx]
0x140129318  mov     rdx, r14
0x14012931b  mov     rax, [rax+50h]
0x14012931f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140129324  mov     [rbp+57h+arg_8], eax
0x140129327  call    cs:__imp_GetCurrentThreadId
0x14012932e  nop     dword ptr [rax+rax+00h]
0x140129333  mov     [rsp+0C0h+var_80], rdi
0x140129338  mov     [rsp+0C0h+var_88], eax
0x14012933c  mov     [rsp+0C0h+var_90], 2ACh
0x140129344  mov     [rsp+0C0h+var_98], rsi
0x140129349  lea     r14, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129350  mov     [rsp+0C0h+ppv], r14
0x140129355  mov     r9d, 4
0x14012935b  xor     r8d, r8d
0x14012935e  mov     edx, [rbp+57h+arg_8]
0x140129361  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129366  mov     rbx, rax
0x140129369  jmp     short loc_140129372
0x14012936b  lea     r14, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129372  test    rax, rax
0x140129375  jnz     loc_1401294F6
0x14012937b  lea     rcx, [rbp+57h+var_60]; this
0x14012937f  call    ?TrimLongPathChars@FilePath@@QEAAXXZ; FilePath::TrimLongPathChars(void)
0x140129384  mov     rcx, [rbp+57h+var_70]
0x140129388  mov     rax, [rcx]
0x14012938b  mov     rbx, [rbp+57h+var_58]
0x14012938f  add     rbx, 12h
0x140129393  mov     rdx, rbx
0x140129396  mov     rax, [rax+0A0h]
0x14012939d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401293a2  mov     [rbp+57h+arg_8], eax
0x1401293a5  add     eax, 3FF31B00h
0x1401293aa  cmp     eax, 87h
0x1401293af  ja      loc_1401294BB
0x1401293b5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401293bc  test    rax, rax
0x1401293bf  jz      short loc_1401293FE
0x1401293c1  cmp     [rax+40h], edi
0x1401293c4  jz      short loc_1401293FE
0x1401293c6  cmp     dword ptr [rax+38h], 2
0x1401293ca  jl      short loc_1401293FE
0x1401293cc  mov     [rbp+57h+var_50], r15
0x1401293d0  mov     [rbp+57h+var_48], 2B7h
0x1401293d7  mov     [rbp+57h+var_44], 2
0x1401293de  mov     [rbp+57h+var_40], r12
0x1401293e2  mov     [rbp+57h+arg_10], rbx
0x1401293e6  lea     r9, [rbp+57h+arg_8]
0x1401293ea  lea     r8, [rbp+57h+arg_10]
0x1401293ee  lea     rdx, aErrorParsing0x; "Error parsing %?, 0x%.08x: Deleting Con"...
0x1401293f5  lea     rcx, [rbp+57h+var_50]
0x1401293f9  call    ??$DbgPrint@GPEBGK@dbgobj@@QEAA_KPEBGAEBQEBGAEBK@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong>(ushort const *,ushort const * const &,ulong const &)
0x1401293fe  mov     edx, 80h; dwFileAttributes
0x140129403  mov     rcx, rbx; lpFileName
0x140129406  call    cs:__imp_SetFileAttributesW
0x14012940d  nop     dword ptr [rax+rax+00h]
0x140129412  mov     r14d, eax
0x140129415  call    cs:__imp_GetLastError
0x14012941c  nop     dword ptr [rax+rax+00h]
0x140129421  mov     esi, eax
0x140129423  mov     rcx, rbx; lpFileName
0x140129426  call    cs:__imp_DeleteFileW
0x14012942d  nop     dword ptr [rax+rax+00h]
0x140129432  test    r14d, r14d
0x140129435  jz      short loc_14012943B
0x140129437  test    eax, eax
0x140129439  jnz     short loc_1401294AD
0x14012943b  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140129442  test    rcx, rcx
0x140129445  jz      short loc_1401294AD
0x140129447  cmp     [rcx+40h], edi
0x14012944a  jz      short loc_1401294AD
0x14012944c  cmp     dword ptr [rcx+38h], 5
0x140129450  jl      short loc_1401294AD
0x140129452  mov     [rbp+57h+var_50], r15
0x140129456  mov     [rbp+57h+var_48], 2BFh
0x14012945d  mov     [rbp+57h+var_44], 5
0x140129464  mov     [rbp+57h+var_40], r12
0x140129468  test    eax, eax
0x14012946a  jz      short loc_140129470
0x14012946c  mov     eax, edi
0x14012946e  jmp     short loc_14012947C
0x140129470  call    cs:__imp_GetLastError
0x140129477  nop     dword ptr [rax+rax+00h]
0x14012947c  mov     dword ptr [rbp+57h+arg_10], eax
0x14012947f  test    r14d, r14d
0x140129482  cmovnz  esi, edi
0x140129485  mov     dword ptr [rbp+57h+arg_18], esi
0x140129488  mov     [rbp+57h+var_68], rbx
0x14012948c  lea     rax, [rbp+57h+arg_10]
0x140129490  mov     [rsp+0C0h+ppv], rax
0x140129495  lea     r9, [rbp+57h+arg_18]
0x140129499  lea     r8, [rbp+57h+var_68]
0x14012949d  lea     rdx, aErrorDeletingC; "Error deleting ConflictManifest file %?"...
0x1401294a4  lea     rcx, [rbp+57h+var_50]
0x1401294a8  call    ??$DbgPrint@GPEBGKK@dbgobj@@QEAA_KPEBGAEBQEBGAEBK2@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong,ulong>(ushort const *,ushort const * const &,ulong const &,ulong const &)
0x1401294ad  lea     rsi, aConflictmanife; "ConflictManifestHandler::EnumerateConte"...
0x1401294b4  lea     r14, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x1401294bb  call    cs:__imp_GetCurrentThreadId
0x1401294c2  nop     dword ptr [rax+rax+00h]
0x1401294c7  mov     [rsp+0C0h+var_80], rdi
0x1401294cc  mov     [rsp+0C0h+var_88], eax
0x1401294d0  mov     [rsp+0C0h+var_90], 2C5h
0x1401294d8  mov     [rsp+0C0h+var_98], rsi
0x1401294dd  mov     [rsp+0C0h+ppv], r14
0x1401294e2  mov     r9d, 4
0x1401294e8  xor     r8d, r8d
0x1401294eb  mov     edx, [rbp+57h+arg_8]
0x1401294ee  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401294f3  mov     rbx, rax
0x1401294f6  mov     rcx, [rbp+57h+var_70]
0x1401294fa  test    rcx, rcx
0x1401294fd  jz      short loc_14012950B
0x1401294ff  mov     rdx, [rcx]
0x140129502  mov     rax, [rdx+10h]
0x140129506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012950b  test    rbx, rbx
0x14012950e  jz      short loc_140129549
0x140129510  call    cs:__imp_GetCurrentThreadId
0x140129517  nop     dword ptr [rax+rax+00h]
0x14012951c  mov     [rsp+0C0h+var_80], rbx
0x140129521  mov     [rsp+0C0h+var_88], eax
0x140129525  mov     [rsp+0C0h+var_90], 2CCh
0x14012952d  mov     [rsp+0C0h+var_98], rsi
0x140129532  mov     [rsp+0C0h+ppv], r14
0x140129537  mov     r9d, [rbx]
0x14012953a  mov     r8d, [rbx+8]
0x14012953e  mov     edx, [rbx+4]
0x140129541  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129546  mov     rdi, rax
0x140129549  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140129550  mov     [rbp+57h+var_60], rax
0x140129554  lea     rcx, [rbp+57h+var_58]
0x140129558  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14012955d  mov     rax, rdi
0x140129560  add     rsp, 90h
0x140129567  pop     r15
0x140129569  pop     r14
0x14012956b  pop     r12
0x14012956d  pop     rdi
0x14012956e  pop     rsi
0x14012956f  pop     rbx
0x140129570  pop     rbp
0x140129571  retn
```
