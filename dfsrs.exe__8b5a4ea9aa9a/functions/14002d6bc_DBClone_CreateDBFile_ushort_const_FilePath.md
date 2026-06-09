# DBClone::CreateDBFile(ushort const *,FilePath &)

- ea: `0x14002d6bc`
- end: `0x14002d95f`
- name: `?CreateDBFile@DBClone@@AEAAPEAVFrsStatus@@PEBGAEAVFilePath@@@Z`
- size: `675`
- prototype: `struct FrsStatus *(DBClone *__hidden this, const unsigned __int16 *, struct FilePath *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x14002ddb0`
- `0x14002f630`

## callees

- `0x14000cd1c`
- `0x14000ee94`
- `0x14001c1ac`
- `0x1400248f4`
- `0x14002d6bc`
- `0x14005c620`
- `0x1401b9494`
- `0x1401be04c`
- `0x1401bebec`
- `0x1401bf310`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14002d72c`
- `KERNEL32!DeleteFileW` at `0x14002d72c`
- `KERNEL32!CreateFileW` at `0x14002d7c0`
- `KERNEL32!CreateFileW` at `0x14002d7c0`
- `KERNEL32!GetLastError` at `0x14002d73a`
- `KERNEL32!GetLastError` at `0x14002d854`
- `KERNEL32!GetLastError` at `0x14002d73a`
- `KERNEL32!GetLastError` at `0x14002d854`
- `KERNEL32!GetCurrentThreadId` at `0x14002d762`
- `KERNEL32!GetCurrentThreadId` at `0x14002d846`
- `KERNEL32!GetCurrentThreadId` at `0x14002d8f2`
- `KERNEL32!GetCurrentThreadId` at `0x14002d762`
- `KERNEL32!GetCurrentThreadId` at `0x14002d846`
- `KERNEL32!GetCurrentThreadId` at `0x14002d8f2`

## string_xrefs

- `0x14002d749`: `DBClone::CreateDBFile`
- `0x14002d805`: `DBClone::CreateDBFile`
- `0x14002d8ae`: `DBClone::CreateDBFile`
- `0x14002d831`: `Created %ws`
- `0x14002d8dd`: `Faile to create file:%? Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall DBClone::CreateDBFile(DBClone *this, const unsigned __int16 *a2, struct FilePath *a3)
{
  __int64 v4; // r8
  WCHAR *v5; // rsi
  DWORD LastError; // eax
  DWORD v7; // r14d
  __int64 v8; // rdi
  DWORD v9; // eax
  __int64 v10; // rcx
  unsigned int *v11; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  void **v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  const wchar_t *v20; // [rsp+60h] [rbp-20h] BYREF
  int v21; // [rsp+68h] [rbp-18h]
  int v22; // [rsp+6Ch] [rbp-14h]
  const wchar_t *v23; // [rsp+70h] [rbp-10h]
  void *FileW; // [rsp+B0h] [rbp+30h] BYREF

  FileW = this;
  FilePath::FilePath((FilePath *)&v18);
  FilePath::Set((FilePath *)&v18, (const unsigned __int16 *)(*(_QWORD *)(v4 + 8) + 18LL));
  LOWORD(FileW) = 92;
  FrsStringImpl<unsigned short,char>::Append(&v19, &FileW, 1);
  FilePath::Append((FilePath *)&v18, a2);
  v5 = (WCHAR *)(v19 + 18);
  LODWORD(a2) = DeleteFileW((LPCWSTR)(v19 + 18));
  LastError = GetLastError();
  v7 = LastError;
  v8 = 0;
  if ( (_DWORD)a2
    || LastError == 2
    || (v9 = GetCurrentThreadId(),
        (v11 = (unsigned int *)FrsStatusList::PushNewError(
                                 v10,
                                 v7,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                 "DBClone::CreateDBFile",
                                 2018,
                                 v9,
                                 0)) == 0) )
  {
    FileW = CreateFileW(v5, 0, 0, 0, 1u, 0, 0);
    if ( (char *)FileW - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandleEx(&FileW);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v20 = L"DBClone::CreateDBFile";
        v21 = 2034;
        v22 = 5;
        v23 = L"DBCL";
        FileW = v5;
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v20, L"Created %ws", &FileW);
      }
      goto LABEL_15;
    }
    CurrentThreadId = GetCurrentThreadId();
    v13 = GetLastError();
    v11 = (unsigned int *)FrsStatusList::PushNewError(
                            v14,
                            v13,
                            0,
                            1,
                            "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                            "DBClone::CreateDBFile",
                            2031,
                            CurrentThreadId,
                            0);
    if ( !v11 )
      goto LABEL_15;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v20 = L"DBClone::CreateDBFile";
    v21 = 2039;
    v22 = 2;
    v23 = L"DBCL";
    FileW = v5;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
      &v20,
      L"Faile to create file:%? Error:%?",
      &FileW,
      v11);
  }
  v15 = GetCurrentThreadId();
  v8 = FrsStatusList::PushNewError(
         v16,
         v11[1],
         v11[2],
         *v11,
         "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
         "DBClone::CreateDBFile",
         2044,
         v15,
         v11);
LABEL_15:
  v18 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v19);
  return (struct FrsStatus *)v8;
}

```

## disassembly

```asm
0x14002d6bc  mov     [rsp-28h+arg_8], rbx
0x14002d6c1  mov     [rsp-28h+arg_10], rsi
0x14002d6c6  mov     [rsp-28h+arg_0], rcx
0x14002d6cb  push    rbp
0x14002d6cc  push    rdi
0x14002d6cd  push    r12
0x14002d6cf  push    r14
0x14002d6d1  push    r15
0x14002d6d3  mov     rbp, rsp
0x14002d6d6  sub     rsp, 80h
0x14002d6dd  mov     rbx, rdx
0x14002d6e0  lea     rcx, [rbp+var_30]; this
0x14002d6e4  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14002d6e9  nop
0x14002d6ea  mov     rdx, [r8+8]
0x14002d6ee  add     rdx, 12h; unsigned __int16 *
0x14002d6f2  lea     rcx, [rbp+var_30]; this
0x14002d6f6  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x14002d6fb  mov     eax, 5Ch ; '\'
0x14002d700  mov     word ptr [rbp+arg_0], ax
0x14002d704  lea     r8d, [rax-5Bh]
0x14002d708  lea     rdx, [rbp+arg_0]
0x14002d70c  lea     rcx, [rbp+var_28]
0x14002d710  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG_K@Z; FrsStringImpl<ushort,char>::Append(ushort const *,unsigned __int64)
0x14002d715  mov     rdx, rbx; unsigned __int16 *
0x14002d718  lea     rcx, [rbp+var_30]; this
0x14002d71c  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14002d721  mov     rsi, [rbp+var_28]
0x14002d725  add     rsi, 12h
0x14002d729  mov     rcx, rsi; lpFileName
0x14002d72c  call    cs:__imp_DeleteFileW
0x14002d733  nop     dword ptr [rax+rax+00h]
0x14002d738  mov     ebx, eax
0x14002d73a  call    cs:__imp_GetLastError
0x14002d741  nop     dword ptr [rax+rax+00h]
0x14002d746  mov     r14d, eax
0x14002d749  lea     r15, aDbcloneCreated_0; "DBClone::CreateDBFile"
0x14002d750  lea     r12, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x14002d757  xor     edi, edi
0x14002d759  test    ebx, ebx
0x14002d75b  jnz     short loc_14002D7A4
0x14002d75d  cmp     eax, 2
0x14002d760  jz      short loc_14002D7A4
0x14002d762  call    cs:__imp_GetCurrentThreadId
0x14002d769  nop     dword ptr [rax+rax+00h]
0x14002d76e  mov     [rsp+80h+var_40], rdi
0x14002d773  mov     [rsp+80h+var_48], eax
0x14002d777  mov     dword ptr [rsp+80h+hTemplateFile], 7E2h
0x14002d77f  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r15
0x14002d784  mov     qword ptr [rsp+80h+dwCreationDisposition], r12
0x14002d789  lea     r9d, [rdi+3]
0x14002d78d  xor     r8d, r8d
0x14002d790  mov     edx, r14d
0x14002d793  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002d798  mov     rbx, rax
0x14002d79b  test    rax, rax
0x14002d79e  jnz     loc_14002D897
0x14002d7a4  mov     [rsp+80h+hTemplateFile], rdi; hTemplateFile
0x14002d7a9  mov     [rsp+80h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x14002d7ad  mov     [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x14002d7b5  xor     r9d, r9d; lpSecurityAttributes
0x14002d7b8  xor     r8d, r8d; dwShareMode
0x14002d7bb  xor     edx, edx; dwDesiredAccess
0x14002d7bd  mov     rcx, rsi; lpFileName
0x14002d7c0  call    cs:__imp_CreateFileW
0x14002d7c7  nop     dword ptr [rax+rax+00h]
0x14002d7cc  mov     [rbp+arg_0], rax
0x14002d7d0  dec     rax
0x14002d7d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002d7d7  ja      short loc_14002D846
0x14002d7d9  lea     rcx, [rbp+arg_0]; void **
0x14002d7dd  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14002d7e2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002d7e9  test    rax, rax
0x14002d7ec  jz      loc_14002D92B
0x14002d7f2  cmp     [rax+40h], edi
0x14002d7f5  jz      loc_14002D92B
0x14002d7fb  cmp     dword ptr [rax+38h], 5
0x14002d7ff  jl      loc_14002D92B
0x14002d805  lea     rax, aDbcloneCreated; "DBClone::CreateDBFile"
0x14002d80c  mov     [rbp+var_20], rax
0x14002d810  mov     [rbp+var_18], 7F2h
0x14002d817  mov     [rbp+var_14], 5
0x14002d81e  lea     rax, aDbcl; "DBCL"
0x14002d825  mov     [rbp+var_10], rax
0x14002d829  mov     [rbp+arg_0], rsi
0x14002d82d  lea     r8, [rbp+arg_0]
0x14002d831  lea     rdx, aCreatedWs; "Created %ws"
0x14002d838  lea     rcx, [rbp+var_20]
0x14002d83c  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x14002d841  jmp     loc_14002D92B
0x14002d846  call    cs:__imp_GetCurrentThreadId
0x14002d84d  nop     dword ptr [rax+rax+00h]
0x14002d852  mov     ebx, eax
0x14002d854  call    cs:__imp_GetLastError
0x14002d85b  nop     dword ptr [rax+rax+00h]
0x14002d860  mov     [rsp+80h+var_40], rdi
0x14002d865  mov     [rsp+80h+var_48], ebx
0x14002d869  mov     dword ptr [rsp+80h+hTemplateFile], 7EFh
0x14002d871  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r15
0x14002d876  mov     qword ptr [rsp+80h+dwCreationDisposition], r12
0x14002d87b  mov     r9d, 1
0x14002d881  xor     r8d, r8d
0x14002d884  mov     edx, eax
0x14002d886  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002d88b  mov     rbx, rax
0x14002d88e  test    rax, rax
0x14002d891  jz      loc_14002D92B
0x14002d897  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14002d89e  test    rax, rax
0x14002d8a1  jz      short loc_14002D8F2
0x14002d8a3  cmp     [rax+40h], edi
0x14002d8a6  jz      short loc_14002D8ED
0x14002d8a8  cmp     dword ptr [rax+38h], 2
0x14002d8ac  jl      short loc_14002D8ED
0x14002d8ae  lea     rax, aDbcloneCreated; "DBClone::CreateDBFile"
0x14002d8b5  mov     [rbp+var_20], rax
0x14002d8b9  mov     [rbp+var_18], 7F7h
0x14002d8c0  mov     [rbp+var_14], 2
0x14002d8c7  lea     rax, aDbcl; "DBCL"
0x14002d8ce  mov     [rbp+var_10], rax
0x14002d8d2  mov     [rbp+arg_0], rsi
0x14002d8d6  mov     r9, rbx
0x14002d8d9  lea     r8, [rbp+arg_0]
0x14002d8dd  lea     rdx, aFaileToCreateF; "Faile to create file:%? Error:%?"
0x14002d8e4  lea     rcx, [rbp+var_20]
0x14002d8e8  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x14002d8ed  test    rbx, rbx
0x14002d8f0  jz      short loc_14002D92B
0x14002d8f2  call    cs:__imp_GetCurrentThreadId
0x14002d8f9  nop     dword ptr [rax+rax+00h]
0x14002d8fe  mov     [rsp+80h+var_40], rbx
0x14002d903  mov     [rsp+80h+var_48], eax
0x14002d907  mov     dword ptr [rsp+80h+hTemplateFile], 7FCh
0x14002d90f  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r15
0x14002d914  mov     qword ptr [rsp+80h+dwCreationDisposition], r12
0x14002d919  mov     r9d, [rbx]
0x14002d91c  mov     r8d, [rbx+8]
0x14002d920  mov     edx, [rbx+4]
0x14002d923  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14002d928  mov     rdi, rax
0x14002d92b  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x14002d932  mov     [rbp+var_30], rax
0x14002d936  lea     rcx, [rbp+var_28]
0x14002d93a  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14002d93f  mov     rax, rdi
0x14002d942  lea     r11, [rsp+80h+var_s0]
0x14002d94a  mov     rbx, [r11+38h]
0x14002d94e  mov     rsi, [r11+40h]
0x14002d952  mov     rsp, r11
0x14002d955  pop     r15
0x14002d957  pop     r14
0x14002d959  pop     r12
0x14002d95b  pop     rdi
0x14002d95c  pop     rbp
0x14002d95d  retn
```
