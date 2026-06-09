# ConflictWorkerTask::InsertResource(ushort const *,ID_UPDATE const &,ConflictManifest::CONFLICT_TYPE,ushort const *,_GUID const &,unsigned __int64,unsigned __int64)

- ea: `0x140129aa4`
- end: `0x140129dd0`
- name: `?InsertResource@ConflictWorkerTask@@AEAAPEAVFrsStatus@@PEBGAEBVID_UPDATE@@W4CONFLICT_TYPE@ConflictManifest@@0AEBU_GUID@@_K4@Z`
- size: `812`
- prototype: `struct FrsStatus *__high(const unsigned __int16 *, const struct ID_UPDATE *, enum ConflictManifest::CONFLICT_TYPE, const unsigned __int16 *, const struct _GUID *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x14012a880`

## callees

- `0x14000ee94`
- `0x1400248f4`
- `0x14005c620`
- `0x1400be540`
- `0x140129920`
- `0x140129aa4`
- `0x14012b314`
- `0x14012b6d0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140129c96`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140129c96`
- `KERNEL32!SetFileAttributesW` at `0x140129b1b`
- `KERNEL32!SetFileAttributesW` at `0x140129d35`
- `KERNEL32!SetFileAttributesW` at `0x140129b1b`
- `KERNEL32!SetFileAttributesW` at `0x140129d35`
- `KERNEL32!SetFilePointerEx` at `0x140129c28`
- `KERNEL32!SetFilePointerEx` at `0x140129c28`
- `KERNEL32!GetFileSizeEx` at `0x140129b66`
- `KERNEL32!GetFileSizeEx` at `0x140129b66`
- `KERNEL32!GetLastError` at `0x140129b84`
- `KERNEL32!GetLastError` at `0x140129c46`
- `KERNEL32!GetLastError` at `0x140129b84`
- `KERNEL32!GetLastError` at `0x140129c46`
- `KERNEL32!GetCurrentThreadId` at `0x140129b76`
- `KERNEL32!GetCurrentThreadId` at `0x140129c38`
- `KERNEL32!GetCurrentThreadId` at `0x140129d46`
- `KERNEL32!GetCurrentThreadId` at `0x140129b76`
- `KERNEL32!GetCurrentThreadId` at `0x140129c38`
- `KERNEL32!GetCurrentThreadId` at `0x140129d46`

## string_xrefs

- `0x140129be3`: `<?xml version="1.0" encoding="UTF-8"?>\n<PreExistingManifest>\n`
- `0x140129bea`: `<?xml version="1.0" encoding="UTF-8"?>\n<ConflictAndDeletedManifest>\n`
- `0x140129cff`: `</PreExistingManifest>\n`
- `0x140129d06`: `</ConflictAndDeletedManifest>\n`
- `0x140129bad`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x140129c6f`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x140129d6f`: `base\fs\remotefs\frs\src\sync\conflictmanifest.cpp`
- `0x140129ba1`: `ConflictWorkerTask::InsertResource`
- `0x140129c63`: `ConflictWorkerTask::InsertResource`
- `0x140129d63`: `ConflictWorkerTask::InsertResource`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConflictWorkerTask::InsertResource(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        struct _GUID *a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v11; // rdi
  const unsigned __int16 *v12; // r15
  struct FrsStatus *v13; // rbx
  DWORD v14; // ebx
  DWORD v15; // eax
  int v16; // ecx
  const char *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  const char *v22; // rdx
  DWORD v23; // eax
  __int64 v24; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-19h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+70h] [rbp-11h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-9h] BYREF
  int v29; // [rsp+80h] [rbp-1h]
  void **v30; // [rsp+88h] [rbp+7h] BYREF
  __int64 v31; // [rsp+90h] [rbp+Fh] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+C8h] [rbp+47h] BYREF

  v11 = 0;
  FileSize.QuadPart = 0;
  NewFilePointer.QuadPart = 0;
  hFile = (HANDLE)-1LL;
  v29 = 1;
  FilePath::FilePath((FilePath *)&v30);
  GetManifestPath(*(_QWORD *)(a1 + 312), *(unsigned int *)(a1 + 320), &v30);
  v12 = (const unsigned __int16 *)(v31 + 18);
  SetFileAttributesW((LPCWSTR)(v31 + 18), 0x80u);
  v13 = FileUtil::FrsCreateFile(v12, 2u, 0x80u, 7u, 3u, 0x4020u, &hFile);
  if ( !v13 )
  {
    if ( GetFileSizeEx(hFile, &FileSize)
      || (v14 = GetCurrentThreadId(),
          v15 = GetLastError(),
          (v13 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                                       v15,
                                       0,
                                       1,
                                       "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                                       "ConflictWorkerTask::InsertResource",
                                       1435,
                                       v14,
                                       0)) == 0) )
    {
      v16 = *(_DWORD *)(a1 + 320);
      if ( FileSize.QuadPart < 0x1FuLL )
      {
        v17 = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<ConflictAndDeletedManifest>\n";
        if ( v16 != 1 )
          v17 = "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<PreExistingManifest>\n";
        v18 = WriteFlushA(hFile, v17);
        goto LABEL_12;
      }
      v19 = 30;
      if ( v16 != 1 )
        v19 = 23;
      FileSize.QuadPart -= v19;
      if ( !SetFilePointerEx(hFile, FileSize, &NewFilePointer, 0) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v18 = FrsStatusList::PushNewError(
                "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                LastError,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
                "ConflictWorkerTask::InsertResource",
                1454,
                CurrentThreadId,
                0);
LABEL_12:
        v13 = (struct FrsStatus *)v18;
      }
    }
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !v13 )
  {
    v13 = (struct FrsStatus *)WriteConflictResource(
                                hFile,
                                a6,
                                *(_DWORD *)(a3 + 148),
                                a5,
                                &SystemTimeAsFileTime,
                                a4,
                                a8,
                                a7);
    if ( !v13 )
    {
      v22 = "</ConflictAndDeletedManifest>\n";
      if ( *(_DWORD *)(a1 + 320) != 1 )
        v22 = "</PreExistingManifest>\n";
      v13 = (struct FrsStatus *)WriteFlushA(hFile, v22);
    }
  }
  CloseHandleEx(&hFile);
  SetFileAttributesW(v12, 1u);
  if ( v13 )
  {
    v23 = GetCurrentThreadId();
    v11 = FrsStatusList::PushNewError(
            v24,
            *((unsigned int *)v13 + 1),
            *((unsigned int *)v13 + 2),
            *(unsigned int *)v13,
            "base\\fs\\remotefs\\frs\\src\\sync\\conflictmanifest.cpp",
            "ConflictWorkerTask::InsertResource",
            1487,
            v23,
            v13);
  }
  v30 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v31);
  CloseHandleEx(&hFile);
  return v11;
}

```

## disassembly

```asm
0x140129aa4  mov     rax, rsp
0x140129aa7  mov     [rax+10h], rbx
0x140129aab  mov     [rax+18h], rsi
0x140129aaf  mov     [rax+20h], rdi
0x140129ab3  push    rbp
0x140129ab4  push    r12
0x140129ab6  push    r13
0x140129ab8  push    r14
0x140129aba  push    r15
0x140129abc  lea     rbp, [rax-3Fh]
0x140129ac0  sub     rsp, 90h
0x140129ac7  mov     r12d, r9d
0x140129aca  mov     r14, r8
0x140129acd  mov     r13, rdx
0x140129ad0  mov     rsi, rcx
0x140129ad3  xor     edi, edi
0x140129ad5  mov     qword ptr [rbp+37h+FileSize], rdi
0x140129ad9  mov     qword ptr [rbp+37h+NewFilePointer], rdi
0x140129add  or      [rbp+37h+hFile], 0FFFFFFFFFFFFFFFFh
0x140129ae2  mov     [rbp+37h+var_38], 1
0x140129ae9  lea     rcx, [rbp+37h+var_30]; this
0x140129aed  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140129af2  nop
0x140129af3  lea     r8, [rbp+37h+var_30]
0x140129af7  mov     edx, [rsi+140h]
0x140129afd  mov     rcx, [rsi+138h]
0x140129b04  call    GetManifestPath
0x140129b09  mov     r15, [rbp+37h+var_28]
0x140129b0d  add     r15, 12h
0x140129b11  mov     ebx, 80h
0x140129b16  mov     edx, ebx; dwFileAttributes
0x140129b18  mov     rcx, r15; lpFileName
0x140129b1b  call    cs:__imp_SetFileAttributesW
0x140129b22  nop     dword ptr [rax+rax+00h]
0x140129b27  lea     rax, [rbp+37h+hFile]
0x140129b2b  mov     [rsp+0B0h+var_80], rax; void **
0x140129b30  mov     [rsp+0B0h+var_88], 4020h; unsigned int
0x140129b38  mov     dword ptr [rsp+0B0h+var_90], 3; unsigned int
0x140129b40  lea     r9d, [rdi+7]; unsigned int
0x140129b44  mov     r8d, ebx; unsigned int
0x140129b47  lea     edx, [rdi+2]; unsigned int
0x140129b4a  mov     rcx, r15; unsigned __int16 *
0x140129b4d  call    ?FrsCreateFile@FileUtil@@SAPEAVFrsStatus@@PEBGKKKKKPEAPEAX@Z; FileUtil::FrsCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)
0x140129b52  mov     rbx, rax
0x140129b55  test    rax, rax
0x140129b58  jnz     loc_140129C8E
0x140129b5e  lea     rdx, [rbp+37h+FileSize]; lpFileSize
0x140129b62  mov     rcx, [rbp+37h+hFile]; hFile
0x140129b66  call    cs:__imp_GetFileSizeEx
0x140129b6d  nop     dword ptr [rax+rax+00h]
0x140129b72  test    eax, eax
0x140129b74  jnz     short loc_140129BD3
0x140129b76  call    cs:__imp_GetCurrentThreadId
0x140129b7d  nop     dword ptr [rax+rax+00h]
0x140129b82  mov     ebx, eax
0x140129b84  call    cs:__imp_GetLastError
0x140129b8b  nop     dword ptr [rax+rax+00h]
0x140129b90  mov     qword ptr [rsp+0B0h+var_70], rdi
0x140129b95  mov     dword ptr [rsp+0B0h+lpFileTime], ebx
0x140129b99  mov     dword ptr [rsp+0B0h+var_80], 59Bh
0x140129ba1  lea     rcx, aConflictworker_2; "ConflictWorkerTask::InsertResource"
0x140129ba8  mov     qword ptr [rsp+0B0h+var_88], rcx
0x140129bad  lea     rcx, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129bb4  mov     [rsp+0B0h+var_90], rcx
0x140129bb9  lea     r9d, [rdi+1]
0x140129bbd  xor     r8d, r8d
0x140129bc0  mov     edx, eax
0x140129bc2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129bc7  mov     rbx, rax
0x140129bca  test    rax, rax
0x140129bcd  jnz     loc_140129C8E
0x140129bd3  mov     ecx, [rsi+140h]
0x140129bd9  mov     rdx, qword ptr [rbp+37h+FileSize]
0x140129bdd  cmp     rdx, 1Fh
0x140129be1  jnb     short loc_140129C06
0x140129be3  lea     rax, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x140129bea  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x140129bf1  cmp     ecx, 1
0x140129bf4  cmovnz  rdx, rax; lpBuffer
0x140129bf8  mov     rcx, [rbp+37h+hFile]; hFile
0x140129bfc  call    WriteFlushA
0x140129c01  jmp     loc_140129C8B
0x140129c06  mov     eax, 1Eh
0x140129c0b  lea     r8d, [rax-7]
0x140129c0f  cmp     ecx, 1
0x140129c12  cmovnz  eax, r8d
0x140129c16  sub     rdx, rax; liDistanceToMove
0x140129c19  mov     qword ptr [rbp+37h+FileSize], rdx
0x140129c1d  xor     r9d, r9d; dwMoveMethod
0x140129c20  lea     r8, [rbp+37h+NewFilePointer]; lpNewFilePointer
0x140129c24  mov     rcx, [rbp+37h+hFile]; hFile
0x140129c28  call    cs:__imp_SetFilePointerEx
0x140129c2f  nop     dword ptr [rax+rax+00h]
0x140129c34  test    eax, eax
0x140129c36  jnz     short loc_140129C8E
0x140129c38  call    cs:__imp_GetCurrentThreadId
0x140129c3f  nop     dword ptr [rax+rax+00h]
0x140129c44  mov     ebx, eax
0x140129c46  call    cs:__imp_GetLastError
0x140129c4d  nop     dword ptr [rax+rax+00h]
0x140129c52  mov     qword ptr [rsp+0B0h+var_70], rdi
0x140129c57  mov     dword ptr [rsp+0B0h+lpFileTime], ebx
0x140129c5b  mov     dword ptr [rsp+0B0h+var_80], 5AEh
0x140129c63  lea     rcx, aConflictworker_2; "ConflictWorkerTask::InsertResource"
0x140129c6a  mov     qword ptr [rsp+0B0h+var_88], rcx
0x140129c6f  lea     rcx, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129c76  mov     [rsp+0B0h+var_90], rcx
0x140129c7b  mov     r9d, 1
0x140129c81  xor     r8d, r8d
0x140129c84  mov     edx, eax
0x140129c86  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129c8b  mov     rbx, rax
0x140129c8e  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x140129c92  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140129c96  call    cs:__imp_GetSystemTimeAsFileTime
0x140129c9d  nop     dword ptr [rax+rax+00h]
0x140129ca2  test    rbx, rbx
0x140129ca5  jnz     short loc_140129D24
0x140129ca7  mov     ecx, [r14+94h]
0x140129cae  lea     r9, [r14+18h]
0x140129cb2  mov     rax, [rbp+37h+arg_30]
0x140129cb6  mov     [rsp+0B0h+var_60], rax; __int64
0x140129cbb  mov     rax, [rbp+37h+arg_38]
0x140129cbf  mov     [rsp+0B0h+var_68], rax; __int64
0x140129cc4  mov     [rsp+0B0h+var_70], r12d; int
0x140129cc9  lea     rax, [rbp+37h+SystemTimeAsFileTime]
0x140129ccd  mov     [rsp+0B0h+lpFileTime], rax; lpFileTime
0x140129cd2  mov     rax, [rbp+37h+arg_20]
0x140129cd6  mov     [rsp+0B0h+var_80], rax; __int64
0x140129cdb  mov     [rsp+0B0h+var_88], ecx; int
0x140129cdf  mov     rax, [rbp+37h+arg_28]
0x140129ce3  mov     [rsp+0B0h+var_90], rax; struct _GUID *
0x140129ce8  mov     r8, r14
0x140129ceb  mov     rdx, r13
0x140129cee  mov     rcx, [rbp+37h+hFile]; hFile
0x140129cf2  call    WriteConflictResource
0x140129cf7  mov     rbx, rax
0x140129cfa  test    rax, rax
0x140129cfd  jnz     short loc_140129D24
0x140129cff  lea     rax, aPreexistingman; "</PreExistingManifest>\n"
0x140129d06  lea     rdx, aConflictanddel; "</ConflictAndDeletedManifest>\n"
0x140129d0d  cmp     dword ptr [rsi+140h], 1
0x140129d14  cmovnz  rdx, rax; lpBuffer
0x140129d18  mov     rcx, [rbp+37h+hFile]; hFile
0x140129d1c  call    WriteFlushA
0x140129d21  mov     rbx, rax
0x140129d24  lea     rcx, [rbp+37h+hFile]; void **
0x140129d28  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x140129d2d  mov     edx, 1; dwFileAttributes
0x140129d32  mov     rcx, r15; lpFileName
0x140129d35  call    cs:__imp_SetFileAttributesW
0x140129d3c  nop     dword ptr [rax+rax+00h]
0x140129d41  test    rbx, rbx
0x140129d44  jz      short loc_140129D8D
0x140129d46  call    cs:__imp_GetCurrentThreadId
0x140129d4d  nop     dword ptr [rax+rax+00h]
0x140129d52  mov     qword ptr [rsp+0B0h+var_70], rbx
0x140129d57  mov     dword ptr [rsp+0B0h+lpFileTime], eax
0x140129d5b  mov     dword ptr [rsp+0B0h+var_80], 5CFh
0x140129d63  lea     rax, aConflictworker_2; "ConflictWorkerTask::InsertResource"
0x140129d6a  mov     qword ptr [rsp+0B0h+var_88], rax
0x140129d6f  lea     rax, aBaseFsRemotefs_63; "base\\fs\\remotefs\\frs\\src\\sync\\con"...
0x140129d76  mov     [rsp+0B0h+var_90], rax
0x140129d7b  mov     r9d, [rbx]
0x140129d7e  mov     r8d, [rbx+8]
0x140129d82  mov     edx, [rbx+4]
0x140129d85  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140129d8a  mov     rdi, rax
0x140129d8d  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140129d94  mov     [rbp+37h+var_30], rax
0x140129d98  lea     rcx, [rbp+37h+var_28]
0x140129d9c  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140129da1  nop
0x140129da2  lea     rcx, [rbp+37h+hFile]; void **
0x140129da6  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x140129dab  mov     rax, rdi
0x140129dae  lea     r11, [rsp+0B0h+var_20]
0x140129db6  mov     rbx, [r11+38h]
0x140129dba  mov     rsi, [r11+40h]
0x140129dbe  mov     rdi, [r11+48h]
0x140129dc2  mov     rsp, r11
0x140129dc5  pop     r15
0x140129dc7  pop     r14
0x140129dc9  pop     r13
0x140129dcb  pop     r12
0x140129dcd  pop     rbp
0x140129dce  retn
```
