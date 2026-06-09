# ConflictWorkerTask::UpdateConflictManifest(ConflictWorkerTask::IConflictUpdateCallback &)

- ea: `0x14012af00`
- end: `0x14012b30d`
- name: `?UpdateConflictManifest@ConflictWorkerTask@@AEAAPEAVFrsStatus@@AEAVIConflictUpdateCallback@1@@Z`
- size: `1037`
- prototype: `struct FrsStatus *__fastcall(ConflictWorkerTask *__hidden this, struct ConflictWorkerTask::IConflictUpdateCallback *)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1401285b4`
- `0x140128bb8`
- `0x140128c68`
- `0x14012a880`

## callees

- `0x1400036a0`
- `0x14000cd1c`
- `0x14000cdc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x1400248f4`
- `0x14005c620`
- `0x1400be540`
- `0x140127e20`
- `0x140128288`
- `0x1401290b8`
- `0x140129920`
- `0x14012af00`
- `0x14012b6d0`
- `0x1401bebc8`
- `0x140223010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14012b12a`
- `KERNEL32!DeleteFileW` at `0x14012b252`
- `KERNEL32!DeleteFileW` at `0x14012b12a`
- `KERNEL32!DeleteFileW` at `0x14012b252`
- `KERNEL32!SetFileAttributesW` at `0x14012b0ca`
- `KERNEL32!SetFileAttributesW` at `0x14012b1f2`
- `KERNEL32!SetFileAttributesW` at `0x14012b0ca`
- `KERNEL32!SetFileAttributesW` at `0x14012b1f2`
- `KERNEL32!MoveFileW` at `0x14012b18d`
- `KERNEL32!MoveFileW` at `0x14012b18d`

## string_xrefs

- `0x14012afdb`: `<?xml version="1.0" encoding="UTF-8"?>\n<PreExistingManifest>\n`
- `0x14012afe2`: `<?xml version="1.0" encoding="UTF-8"?>\n<ConflictAndDeletedManifest>\n`
- `0x14012b06b`: `</PreExistingManifest>\n`
- `0x14012b072`: `</ConflictAndDeletedManifest>\n`
- `0x14012b176`: `(Ignored) Failed to delete file:%ws`
- `0x14012b0a3`: `ConflictWorkerTask::UpdateConflictManifest`
- `0x14012b23e`: `(Ignored) Failed to set read-attribute on file:%ws`
- `0x14012b1d9`: `(Ignored) Failed to move file:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall ConflictWorkerTask::UpdateConflictManifest(
        ConflictWorkerTask *this,
        struct ConflictWorkerTask::IConflictUpdateCallback *a2)
{
  const WCHAR *v4; // r15
  struct FrsStatus *v5; // rbx
  struct FrsStatus *v6; // rdi
  const char *v7; // rdx
  const char *v8; // rdx
  const WCHAR *v9; // rdi
  const wchar_t *v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h]
  int v13; // [rsp+4Ch] [rbp-B4h]
  const wchar_t *v14; // [rsp+50h] [rbp-B0h]
  const WCHAR *v15; // [rsp+58h] [rbp-A8h] BYREF
  struct FrsStatus *v16; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hFile; // [rsp+68h] [rbp-98h] BYREF
  int v18; // [rsp+70h] [rbp-90h]
  void **v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  void **v21; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[160]; // [rsp+A0h] [rbp-60h] BYREF

  FilePath::FilePath((FilePath *)&v21);
  FilePath::FilePath((FilePath *)&v19);
  GetManifestPath(*((_QWORD *)this + 39), *((unsigned int *)this + 80), &v21);
  GetManifestPath(*((_QWORD *)this + 39), *((unsigned int *)this + 80), &v19);
  FilePath::operator+=(&v19, L".tmp");
  hFile = (HANDLE)-1LL;
  v18 = 1;
  v4 = (const WCHAR *)(v20 + 18);
  v5 = FileUtil::FrsCreateFile((const unsigned __int16 *)(v20 + 18), 2u, 0x80u, 7u, 5u, 0x4020u, &hFile);
  v16 = v5;
  v6 = v5;
  if ( !v5 )
  {
    v7 = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ConflictAndDeletedManifest>\n";
    if ( *((_DWORD *)this + 80) != 1 )
      v7 = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<PreExistingManifest>\n";
    v5 = (struct FrsStatus *)WriteFlushA(hFile, v7);
    v16 = v5;
    v6 = v5;
  }
  if ( !v6 )
  {
    v5 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct ConflictWorkerTask::IConflictUpdateCallback *, ConflictWorkerTask *, HANDLE))(*(_QWORD *)a2 + 16LL))(
                               a2,
                               this,
                               hFile);
    v16 = v5;
    v6 = v5;
    if ( !v5 )
    {
      ConflictManifestHandler::ConflictManifestHandler(v23, a2);
      v5 = (struct FrsStatus *)ConflictManifestHandler::EnumerateContentSetManagerConflicts(
                                 (__int64)v23,
                                 (_QWORD *)this + 39);
      v16 = v5;
      ConflictManifestHandler::~ConflictManifestHandler((ConflictManifestHandler *)v23);
      v6 = v5;
      if ( !v5 )
      {
        v8 = "</ConflictAndDeletedManifest>\n";
        if ( *((_DWORD *)this + 80) != 1 )
          v8 = "</PreExistingManifest>\n";
        v5 = (struct FrsStatus *)WriteFlushA(hFile, v8);
        v16 = v5;
        v6 = v5;
      }
    }
  }
  CloseHandleEx(&hFile);
  if ( !v6 )
  {
    v9 = (const WCHAR *)(v22 + 18);
    if ( !SetFileAttributesW((LPCWSTR)(v22 + 18), 0x80u)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v11 = L"ConflictWorkerTask::UpdateConflictManifest";
      v12 = 1582;
      v13 = 5;
      v14 = L"CONF";
      v15 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(
        &v11,
        L"(Ignored) Failed to set normal-attribute on file:%ws",
        &v15);
    }
    if ( !DeleteFileW(v9)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v11 = L"ConflictWorkerTask::UpdateConflictManifest";
      v12 = 1585;
      v13 = 5;
      v14 = L"CONF";
      v15 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v11, L"(Ignored) Failed to delete file:%ws", &v15);
    }
    if ( !MoveFileW(v4, v9)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v11 = L"ConflictWorkerTask::UpdateConflictManifest";
      v12 = 1588;
      v13 = 5;
      v14 = L"CONF";
      v15 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v11, L"(Ignored) Failed to move file:%ws", &v15);
    }
    if ( !SetFileAttributesW(v9, 1u)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v11 = L"ConflictWorkerTask::UpdateConflictManifest";
      v12 = 1591;
      v13 = 5;
      v14 = L"CONF";
      v15 = v9;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(
        &v11,
        L"(Ignored) Failed to set read-attribute on file:%ws",
        &v15);
    }
  }
  DeleteFileW(v4);
  if ( v5 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v11 = L"ConflictWorkerTask::UpdateConflictManifest";
      v12 = 1598;
      v13 = 5;
      v14 = L"CONF";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v11, L"(Ignored) Failed. Errror:%?", v5);
    }
    CLEAR_ERROR(&v16);
  }
  CloseHandleEx(&hFile);
  v19 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v20);
  v21 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v22);
  return 0;
}

```

## disassembly

```asm
0x14012af00  mov     [rsp-8+arg_10], rbx
0x14012af05  mov     [rsp-8+arg_18], rsi
0x14012af0a  push    rbp
0x14012af0b  push    rdi
0x14012af0c  push    r12
0x14012af0e  push    r14
0x14012af10  push    r15
0x14012af12  lea     rbp, [rsp-50h]
0x14012af17  sub     rsp, 150h
0x14012af1e  mov     rax, cs:__security_cookie
0x14012af25  xor     rax, rsp
0x14012af28  mov     [rbp+70h+var_30], rax
0x14012af2c  mov     r14, rdx
0x14012af2f  mov     rsi, rcx
0x14012af32  lea     rcx, [rbp+70h+var_E8]; this
0x14012af36  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14012af3b  nop
0x14012af3c  lea     rcx, [rsp+170h+var_F8]; this
0x14012af41  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14012af46  nop
0x14012af47  lea     r12, [rsi+138h]
0x14012af4e  lea     r8, [rbp+70h+var_E8]
0x14012af52  mov     edx, [rsi+140h]
0x14012af58  mov     rcx, [r12]
0x14012af5c  call    GetManifestPath
0x14012af61  lea     r8, [rsp+170h+var_F8]
0x14012af66  mov     edx, [rsi+140h]
0x14012af6c  mov     rcx, [r12]
0x14012af70  call    GetManifestPath
0x14012af75  lea     rdx, aTmp; ".tmp"
0x14012af7c  lea     rcx, [rsp+170h+var_F8]
0x14012af81  call    ??YFilePath@@QEAAAEAV0@PEBG@Z; FilePath::operator+=(ushort const *)
0x14012af86  or      [rsp+170h+hFile], 0FFFFFFFFFFFFFFFFh
0x14012af8c  mov     [rsp+170h+var_100], 1
0x14012af94  mov     r15, [rbp+70h+var_F0]
0x14012af98  add     r15, 12h
0x14012af9c  lea     rax, [rsp+170h+hFile]
0x14012afa1  mov     [rsp+170h+var_140], rax; void **
0x14012afa6  mov     [rsp+170h+var_148], 4020h; unsigned int
0x14012afae  mov     [rsp+170h+var_150], 5; unsigned int
0x14012afb6  mov     edx, 2; unsigned int
0x14012afbb  lea     r9d, [rdx+5]; unsigned int
0x14012afbf  lea     r8d, [rdx+7Eh]; unsigned int
0x14012afc3  mov     rcx, r15; unsigned __int16 *
0x14012afc6  call    ?FrsCreateFile@FileUtil@@SAPEAVFrsStatus@@PEBGKKKKKPEAPEAX@Z; FileUtil::FrsCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)
0x14012afcb  mov     rbx, rax
0x14012afce  mov     [rsp+170h+var_110], rax
0x14012afd3  mov     rdi, rax
0x14012afd6  test    rax, rax
0x14012afd9  jnz     short loc_14012B009
0x14012afdb  lea     rax, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x14012afe2  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x14012afe9  cmp     dword ptr [rsi+140h], 1
0x14012aff0  cmovnz  rdx, rax; lpBuffer
0x14012aff4  mov     rcx, [rsp+170h+hFile]; hFile
0x14012aff9  call    WriteFlushA
0x14012affe  mov     rbx, rax
0x14012b001  mov     [rsp+170h+var_110], rax
0x14012b006  mov     rdi, rax
0x14012b009  test    rdi, rdi
0x14012b00c  jnz     loc_14012B099
0x14012b012  mov     rax, [r14]
0x14012b015  mov     r8, [rsp+170h+hFile]
0x14012b01a  mov     rdx, rsi
0x14012b01d  mov     rcx, r14
0x14012b020  mov     rax, [rax+10h]
0x14012b024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012b029  mov     rbx, rax
0x14012b02c  mov     [rsp+170h+var_110], rax
0x14012b031  mov     rdi, rax
0x14012b034  test    rax, rax
0x14012b037  jnz     short loc_14012B099
0x14012b039  mov     rdx, r14
0x14012b03c  lea     rcx, [rbp+70h+var_D0]
0x14012b040  call    ??0ConflictManifestHandler@@QEAA@PEAVCallback@ConflictManifest@@PEAVFilter@2@W4MANIFEST_MODE@2@@Z; ConflictManifestHandler::ConflictManifestHandler(ConflictManifest::Callback *,ConflictManifest::Filter *,ConflictManifest::MANIFEST_MODE)
0x14012b045  nop
0x14012b046  mov     rdx, r12
0x14012b049  lea     rcx, [rbp+70h+var_D0]
0x14012b04d  call    ?EnumerateContentSetManagerConflicts@ConflictManifestHandler@@QEAAPEAVFrsStatus@@AEAV?$ScopedRef@VContentSetManager@@@@@Z; ConflictManifestHandler::EnumerateContentSetManagerConflicts(ScopedRef<ContentSetManager> &)
0x14012b052  mov     rbx, rax
0x14012b055  mov     [rsp+170h+var_110], rax
0x14012b05a  lea     rcx, [rbp+70h+var_D0]; this
0x14012b05e  call    ??1ConflictManifestHandler@@UEAA@XZ; ConflictManifestHandler::~ConflictManifestHandler(void)
0x14012b063  mov     rdi, rbx
0x14012b066  test    rbx, rbx
0x14012b069  jnz     short loc_14012B099
0x14012b06b  lea     rax, aPreexistingman; "</PreExistingManifest>\n"
0x14012b072  lea     rdx, aConflictanddel; "</ConflictAndDeletedManifest>\n"
0x14012b079  cmp     dword ptr [rsi+140h], 1
0x14012b080  cmovnz  rdx, rax; lpBuffer
0x14012b084  mov     rcx, [rsp+170h+hFile]; hFile
0x14012b089  call    WriteFlushA
0x14012b08e  mov     rbx, rax
0x14012b091  mov     [rsp+170h+var_110], rax
0x14012b096  mov     rdi, rax
0x14012b099  lea     rcx, [rsp+170h+hFile]; void **
0x14012b09e  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14012b0a3  lea     rsi, aConflictworker_9; "ConflictWorkerTask::UpdateConflictManif"...
0x14012b0aa  lea     r14, aConf; "CONF"
0x14012b0b1  test    rdi, rdi
0x14012b0b4  jnz     loc_14012B24F
0x14012b0ba  mov     rdi, [rbp+70h+var_E0]
0x14012b0be  add     rdi, 12h
0x14012b0c2  mov     edx, 80h; dwFileAttributes
0x14012b0c7  mov     rcx, rdi; lpFileName
0x14012b0ca  call    cs:__imp_SetFileAttributesW
0x14012b0d1  nop     dword ptr [rax+rax+00h]
0x14012b0d6  test    eax, eax
0x14012b0d8  jnz     short loc_14012B127
0x14012b0da  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012b0e1  test    rax, rax
0x14012b0e4  jz      short loc_14012B127
0x14012b0e6  cmp     dword ptr [rax+40h], 0
0x14012b0ea  jz      short loc_14012B127
0x14012b0ec  cmp     dword ptr [rax+38h], 5
0x14012b0f0  jl      short loc_14012B127
0x14012b0f2  mov     [rsp+170h+var_130], rsi
0x14012b0f7  mov     [rsp+170h+var_128], 62Eh
0x14012b0ff  mov     [rsp+170h+var_124], 5
0x14012b107  mov     [rsp+170h+var_120], r14
0x14012b10c  mov     [rsp+170h+var_118], rdi
0x14012b111  lea     r8, [rsp+170h+var_118]
0x14012b116  lea     rdx, aIgnoredFailedT_111; "(Ignored) Failed to set normal-attribut"...
0x14012b11d  lea     rcx, [rsp+170h+var_130]
0x14012b122  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14012b127  mov     rcx, rdi; lpFileName
0x14012b12a  call    cs:__imp_DeleteFileW
0x14012b131  nop     dword ptr [rax+rax+00h]
0x14012b136  test    eax, eax
0x14012b138  jnz     short loc_14012B187
0x14012b13a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012b141  test    rax, rax
0x14012b144  jz      short loc_14012B187
0x14012b146  cmp     dword ptr [rax+40h], 0
0x14012b14a  jz      short loc_14012B187
0x14012b14c  cmp     dword ptr [rax+38h], 5
0x14012b150  jl      short loc_14012B187
0x14012b152  mov     [rsp+170h+var_130], rsi
0x14012b157  mov     [rsp+170h+var_128], 631h
0x14012b15f  mov     [rsp+170h+var_124], 5
0x14012b167  mov     [rsp+170h+var_120], r14
0x14012b16c  mov     [rsp+170h+var_118], rdi
0x14012b171  lea     r8, [rsp+170h+var_118]
0x14012b176  lea     rdx, aIgnoredFailedT_6; "(Ignored) Failed to delete file:%ws"
0x14012b17d  lea     rcx, [rsp+170h+var_130]
0x14012b182  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14012b187  mov     rdx, rdi; lpNewFileName
0x14012b18a  mov     rcx, r15; lpExistingFileName
0x14012b18d  call    cs:__imp_MoveFileW
0x14012b194  nop     dword ptr [rax+rax+00h]
0x14012b199  test    eax, eax
0x14012b19b  jnz     short loc_14012B1EA
0x14012b19d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012b1a4  test    rax, rax
0x14012b1a7  jz      short loc_14012B1EA
0x14012b1a9  cmp     dword ptr [rax+40h], 0
0x14012b1ad  jz      short loc_14012B1EA
0x14012b1af  cmp     dword ptr [rax+38h], 5
0x14012b1b3  jl      short loc_14012B1EA
0x14012b1b5  mov     [rsp+170h+var_130], rsi
0x14012b1ba  mov     [rsp+170h+var_128], 634h
0x14012b1c2  mov     [rsp+170h+var_124], 5
0x14012b1ca  mov     [rsp+170h+var_120], r14
0x14012b1cf  mov     [rsp+170h+var_118], rdi
0x14012b1d4  lea     r8, [rsp+170h+var_118]
0x14012b1d9  lea     rdx, aIgnoredFailedT_116; "(Ignored) Failed to move file:%ws"
0x14012b1e0  lea     rcx, [rsp+170h+var_130]
0x14012b1e5  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14012b1ea  mov     edx, 1; dwFileAttributes
0x14012b1ef  mov     rcx, rdi; lpFileName
0x14012b1f2  call    cs:__imp_SetFileAttributesW
0x14012b1f9  nop     dword ptr [rax+rax+00h]
0x14012b1fe  test    eax, eax
0x14012b200  jnz     short loc_14012B24F
0x14012b202  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012b209  test    rax, rax
0x14012b20c  jz      short loc_14012B24F
0x14012b20e  cmp     dword ptr [rax+40h], 0
0x14012b212  jz      short loc_14012B24F
0x14012b214  cmp     dword ptr [rax+38h], 5
0x14012b218  jl      short loc_14012B24F
0x14012b21a  mov     [rsp+170h+var_130], rsi
0x14012b21f  mov     [rsp+170h+var_128], 637h
0x14012b227  mov     [rsp+170h+var_124], 5
0x14012b22f  mov     [rsp+170h+var_120], r14
0x14012b234  mov     [rsp+170h+var_118], rdi
0x14012b239  lea     r8, [rsp+170h+var_118]
0x14012b23e  lea     rdx, aIgnoredFailedT_104; "(Ignored) Failed to set read-attribute "...
0x14012b245  lea     rcx, [rsp+170h+var_130]
0x14012b24a  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14012b24f  mov     rcx, r15; lpFileName
0x14012b252  call    cs:__imp_DeleteFileW
0x14012b259  nop     dword ptr [rax+rax+00h]
0x14012b25e  test    rbx, rbx
0x14012b261  jz      short loc_14012B2B4
0x14012b263  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012b26a  test    rax, rax
0x14012b26d  jz      short loc_14012B2A9
0x14012b26f  cmp     dword ptr [rax+40h], 0
0x14012b273  jz      short loc_14012B2A9
0x14012b275  cmp     dword ptr [rax+38h], 5
0x14012b279  jl      short loc_14012B2A9
0x14012b27b  mov     [rsp+170h+var_130], rsi
0x14012b280  mov     [rsp+170h+var_128], 63Eh
0x14012b288  mov     [rsp+170h+var_124], 5
0x14012b290  mov     [rsp+170h+var_120], r14
0x14012b295  mov     r8, rbx
0x14012b298  lea     rdx, aIgnoredFailedE; "(Ignored) Failed. Errror:%?"
0x14012b29f  lea     rcx, [rsp+170h+var_130]
0x14012b2a4  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14012b2a9  lea     rcx, [rsp+170h+var_110]; struct FrsStatus **
0x14012b2ae  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14012b2b3  nop
0x14012b2b4  lea     rcx, [rsp+170h+hFile]; void **
0x14012b2b9  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14012b2be  nop
0x14012b2bf  lea     rbx, ??_7FilePath@@6B@; const FilePath::`vftable'
0x14012b2c6  mov     [rsp+170h+var_F8], rbx
0x14012b2cb  lea     rcx, [rbp+70h+var_F0]
0x14012b2cf  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14012b2d4  nop
0x14012b2d5  mov     [rbp+70h+var_E8], rbx
0x14012b2d9  lea     rcx, [rbp+70h+var_E0]
0x14012b2dd  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14012b2e2  xor     eax, eax
0x14012b2e4  mov     rcx, [rbp+70h+var_30]
0x14012b2e8  xor     rcx, rsp; StackCookie
0x14012b2eb  call    __security_check_cookie
0x14012b2f0  lea     r11, [rsp+170h+var_20]
0x14012b2f8  mov     rbx, [r11+40h]
0x14012b2fc  mov     rsi, [r11+48h]
0x14012b300  mov     rsp, r11
0x14012b303  pop     r15
0x14012b305  pop     r14
0x14012b307  pop     r12
0x14012b309  pop     rdi
0x14012b30a  pop     rbp
0x14012b30b  retn
```
