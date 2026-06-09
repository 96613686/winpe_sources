# FilePool::CreatePoolFile(FileListItem * *,ushort *)

- ea: `0x18003b550`
- end: `0x18003b73a`
- name: `?CreatePoolFile@FilePool@@AEAAJPEAPEAUFileListItem@@PEAG@Z`
- size: `490`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct FileListItem **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180034f5c`

## callees

- `0x180015e28`
- `0x1800306c4`
- `0x1800320dc`
- `0x18003b550`
- `0x18003ea2c`
- `0x1800a8848`
- `0x1800a891c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b6fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b6fa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003b5b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003b5b7`
- `SPOOLSS!DllFreeSplMem` at `0x18003b709`
- `SPOOLSS!DllFreeSplMem` at `0x18003b718`
- `SPOOLSS!DllFreeSplMem` at `0x18003b721`
- `SPOOLSS!DllFreeSplMem` at `0x18003b709`
- `SPOOLSS!DllFreeSplMem` at `0x18003b718`
- `SPOOLSS!DllFreeSplMem` at `0x18003b721`
- `SPOOLSS!DllAllocSplMem` at `0x18003b582`
- `SPOOLSS!DllAllocSplMem` at `0x18003b582`
- `SPOOLSS!AllocSplStr` at `0x18003b5d1`
- `SPOOLSS!AllocSplStr` at `0x18003b5de`
- `SPOOLSS!AllocSplStr` at `0x18003b683`
- `SPOOLSS!AllocSplStr` at `0x18003b5d1`
- `SPOOLSS!AllocSplStr` at `0x18003b5de`
- `SPOOLSS!AllocSplStr` at `0x18003b683`

## string_xrefs

- `0x18003b6e0`: `FilePool::CreatePoolFile`

## pseudocode

```c
__int64 __fastcall FilePool::CreatePoolFile(
        LPCRITICAL_SECTION lpCriticalSection,
        struct FileListItem **a2,
        unsigned __int16 *a3)
{
  int v6; // r15d
  unsigned int LastErrorAsFailHRNoBreak; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  int OwningThread; // r12d
  NCoreLibrary *v11; // rcx
  wchar_t *v12; // rax
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *SpinCount; // rdx
  unsigned __int16 *NextFileName; // rax
  int i; // eax
  unsigned __int16 *v17; // rdx
  __int64 v18; // r8
  wchar_t *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx

  v6 = 0;
  if ( !a2 )
  {
    v9 = 0;
    LastErrorAsFailHRNoBreak = -2147024809;
LABEL_23:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "FilePool::CreatePoolFile",
      L"Failed with error code hr: 0x%x",
      LastErrorAsFailHRNoBreak);
    if ( v9 )
    {
      if ( v6 )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
      v20 = *(_QWORD *)(v9 + 72);
      if ( v20 )
        DllFreeSplMem(v20);
      v21 = *(_QWORD *)(v9 + 80);
      if ( v21 )
        DllFreeSplMem(v21);
      DllFreeSplMem(v9);
    }
    return LastErrorAsFailHRNoBreak;
  }
  LastErrorAsFailHRNoBreak = -2147467259;
  v8 = DllAllocSplMem(120);
  v9 = v8;
  if ( !v8 )
    goto LABEL_23;
  *(_QWORD *)v8 = 0;
  *(_QWORD *)(v8 + 8) = 0;
  OwningThread = (int)lpCriticalSection[3].OwningThread;
  *(_DWORD *)(v8 + 68) = 0;
  *(_QWORD *)(v8 + 16) = lpCriticalSection;
  *(_DWORD *)(v8 + 112) = 0;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v8 + 24), 0x80000000) )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v11);
LABEL_20:
    if ( (LastErrorAsFailHRNoBreak & 0x80000000) == 0 )
      return LastErrorAsFailHRNoBreak;
    goto LABEL_23;
  }
  v6 = 1;
  if ( a3 )
  {
    *(_QWORD *)(v9 + 72) = AllocSplStr(a3);
    v12 = (wchar_t *)AllocSplStr(a3);
    *(_QWORD *)(v9 + 80) = v12;
    if ( *(_QWORD *)(v9 + 72) && v12 )
    {
      v13 = *(const unsigned __int16 **)&lpCriticalSection[3].LockCount;
      SpinCount = (const unsigned __int16 *)lpCriticalSection[2].SpinCount;
      *a2 = (struct FileListItem *)v9;
      ConvertFileExt(v12, SpinCount, v13);
      LastErrorAsFailHRNoBreak = 0;
      *(_QWORD *)(v9 + 96) = -1;
      *(_QWORD *)(v9 + 88) = -1;
      *(_QWORD *)(v9 + 104) = -1;
      return LastErrorAsFailHRNoBreak;
    }
    LastErrorAsFailHRNoBreak = -2147024882;
    goto LABEL_23;
  }
  NextFileName = FilePool::GetNextFileName(lpCriticalSection);
  *(_QWORD *)(v9 + 72) = NextFileName;
  if ( !NextFileName )
  {
    LastErrorAsFailHRNoBreak = -2147024882;
    goto LABEL_20;
  }
  for ( i = FileExists(NextFileName); i; i = FileExists(*(_QWORD *)(v9 + 72)) )
  {
    v17 = *(unsigned __int16 **)(v9 + 72);
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    FilePool::GetNextFileNameNoAlloc(lpCriticalSection, v17, v18 + 1);
    if ( OwningThread == LODWORD(lpCriticalSection[3].OwningThread) )
      goto LABEL_23;
  }
  LastErrorAsFailHRNoBreak = 0;
  v19 = (wchar_t *)AllocSplStr(*(_QWORD *)(v9 + 72));
  *(_QWORD *)(v9 + 80) = v19;
  if ( v19 )
  {
    ConvertFileExt(
      v19,
      (const unsigned __int16 *)lpCriticalSection[2].SpinCount,
      *(const unsigned __int16 **)&lpCriticalSection[3].LockCount);
    *(_QWORD *)(v9 + 96) = -1;
    *(_QWORD *)(v9 + 88) = -1;
    *(_QWORD *)(v9 + 104) = -1;
    *a2 = (struct FileListItem *)v9;
  }
  return LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x18003b550  push    rbx
0x18003b552  push    rbp
0x18003b553  push    rsi
0x18003b554  push    rdi
0x18003b555  push    r12
0x18003b557  push    r13
0x18003b559  push    r14
0x18003b55b  push    r15
0x18003b55d  sub     rsp, 28h
0x18003b561  xor     r13d, r13d
0x18003b564  mov     rsi, r8
0x18003b567  mov     r14, rdx
0x18003b56a  mov     rbp, rcx
0x18003b56d  mov     r15d, r13d
0x18003b570  test    rdx, rdx
0x18003b573  jz      loc_18003B6CE
0x18003b579  lea     ecx, [r13+78h]
0x18003b57d  mov     edi, 80004005h
0x18003b582  call    cs:__imp_DllAllocSplMem
0x18003b588  mov     rbx, rax
0x18003b58b  test    rax, rax
0x18003b58e  jz      loc_18003B6D6
0x18003b594  mov     [rax], r13
0x18003b597  lea     rcx, [rax+18h]; lpCriticalSection
0x18003b59b  mov     [rax+8], r13
0x18003b59f  mov     edx, 80000000h; dwSpinCount
0x18003b5a4  mov     r12d, [rbp+88h]
0x18003b5ab  mov     [rax+44h], r13d
0x18003b5af  mov     [rax+10h], rbp
0x18003b5b3  mov     [rax+70h], r13d
0x18003b5b7  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003b5bd  test    eax, eax
0x18003b5bf  jz      loc_18003B6C1
0x18003b5c5  lea     r15d, [r13+1]
0x18003b5c9  test    rsi, rsi
0x18003b5cc  jz      short loc_18003B62B
0x18003b5ce  mov     rcx, rsi
0x18003b5d1  call    cs:__imp_AllocSplStr
0x18003b5d7  mov     rcx, rsi
0x18003b5da  mov     [rbx+48h], rax
0x18003b5de  call    cs:__imp_AllocSplStr
0x18003b5e4  mov     [rbx+50h], rax
0x18003b5e8  cmp     [rbx+48h], r13
0x18003b5ec  jz      short loc_18003B621
0x18003b5ee  test    rax, rax
0x18003b5f1  jz      short loc_18003B621
0x18003b5f3  mov     r8, [rbp+80h]; unsigned __int16 *
0x18003b5fa  mov     rcx, rax; Str
0x18003b5fd  mov     rdx, [rbp+70h]; unsigned __int16 *
0x18003b601  mov     [r14], rbx
0x18003b604  call    ?ConvertFileExt@@YAJPEAGPEBG1@Z; ConvertFileExt(ushort *,ushort const *,ushort const *)
0x18003b609  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b60d  mov     edi, r13d
0x18003b610  mov     [rbx+60h], rsi
0x18003b614  mov     [rbx+58h], rsi
0x18003b618  mov     [rbx+68h], rsi
0x18003b61c  jmp     loc_18003B727
0x18003b621  mov     edi, 8007000Eh
0x18003b626  jmp     loc_18003B6D6
0x18003b62b  mov     rcx, rbp; lpCriticalSection
0x18003b62e  call    ?GetNextFileName@FilePool@@AEAAPEAGXZ; FilePool::GetNextFileName(void)
0x18003b633  mov     [rbx+48h], rax
0x18003b637  test    rax, rax
0x18003b63a  jz      short loc_18003B6BA
0x18003b63c  mov     rcx, rax
0x18003b63f  call    FileExists
0x18003b644  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b648  jmp     short loc_18003B678
0x18003b64a  mov     rdx, [rbx+48h]; unsigned __int16 *
0x18003b64e  mov     r8, rsi
0x18003b651  inc     r8
0x18003b654  cmp     [rdx+r8*2], r13w
0x18003b659  jnz     short loc_18003B651
0x18003b65b  inc     r8; unsigned __int64
0x18003b65e  mov     rcx, rbp; lpCriticalSection
0x18003b661  call    ?GetNextFileNameNoAlloc@FilePool@@AEAAJPEAG_K@Z; FilePool::GetNextFileNameNoAlloc(ushort *,unsigned __int64)
0x18003b666  cmp     r12d, [rbp+88h]
0x18003b66d  jz      short loc_18003B6D6
0x18003b66f  mov     rcx, [rbx+48h]
0x18003b673  call    FileExists
0x18003b678  test    eax, eax
0x18003b67a  jnz     short loc_18003B64A
0x18003b67c  mov     rcx, [rbx+48h]
0x18003b680  mov     edi, r13d
0x18003b683  call    cs:__imp_AllocSplStr
0x18003b689  mov     [rbx+50h], rax
0x18003b68d  test    rax, rax
0x18003b690  jz      loc_18003B727
0x18003b696  mov     r8, [rbp+80h]; unsigned __int16 *
0x18003b69d  mov     rcx, rax; Str
0x18003b6a0  mov     rdx, [rbp+70h]; unsigned __int16 *
0x18003b6a4  call    ?ConvertFileExt@@YAJPEAGPEBG1@Z; ConvertFileExt(ushort *,ushort const *,ushort const *)
0x18003b6a9  mov     [rbx+60h], rsi
0x18003b6ad  mov     [rbx+58h], rsi
0x18003b6b1  mov     [rbx+68h], rsi
0x18003b6b5  mov     [r14], rbx
0x18003b6b8  jmp     short loc_18003B727
0x18003b6ba  mov     edi, 8007000Eh
0x18003b6bf  jmp     short loc_18003B6C8
0x18003b6c1  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x18003b6c6  mov     edi, eax
0x18003b6c8  test    edi, edi
0x18003b6ca  jns     short loc_18003B727
0x18003b6cc  jmp     short loc_18003B6D6
0x18003b6ce  mov     rbx, r13
0x18003b6d1  mov     edi, 80070057h
0x18003b6d6  mov     r8d, edi
0x18003b6d9  lea     rdx, aFailedWithErro_1; "Failed with error code hr: 0x%x"
0x18003b6e0  lea     rcx, aFilepoolCreate; "FilePool::CreatePoolFile"
0x18003b6e7  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003b6ec  test    rbx, rbx
0x18003b6ef  jz      short loc_18003B727
0x18003b6f1  test    r15d, r15d
0x18003b6f4  jz      short loc_18003B700
0x18003b6f6  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003b6fa  call    cs:__imp_DeleteCriticalSection
0x18003b700  mov     rcx, [rbx+48h]
0x18003b704  test    rcx, rcx
0x18003b707  jz      short loc_18003B70F
0x18003b709  call    cs:__imp_DllFreeSplMem
0x18003b70f  mov     rcx, [rbx+50h]
0x18003b713  test    rcx, rcx
0x18003b716  jz      short loc_18003B71E
0x18003b718  call    cs:__imp_DllFreeSplMem
0x18003b71e  mov     rcx, rbx
0x18003b721  call    cs:__imp_DllFreeSplMem
0x18003b727  mov     eax, edi
0x18003b729  add     rsp, 28h
0x18003b72d  pop     r15
0x18003b72f  pop     r14
0x18003b731  pop     r13
0x18003b733  pop     r12
0x18003b735  pop     rdi
0x18003b736  pop     rsi
0x18003b737  pop     rbp
0x18003b738  pop     rbx
0x18003b739  retn
```
