# SplCopyNumberOfFilesInternal(ushort *,ushort * *,ulong,ushort *,int,int *)

- ea: `0x18009b2f4`
- end: `0x18009b792`
- name: `?SplCopyNumberOfFilesInternal@@YAHPEAGPEAPEAGK0HPEAH@Z`
- size: `1182`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x18009a35c`
- `0x1800bc00c`

## callees

- `0x180008520`
- `0x180008560`
- `0x18000beb4`
- `0x18000c5fc`
- `0x180013c90`
- `0x180030a0c`
- `0x180033674`
- `0x180033a9c`
- `0x180035ae4`
- `0x18003ea2c`
- `0x180042ad0`
- `0x18007348c`
- `0x18009b190`
- `0x18009b2f4`
- `0x18009b798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b740`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b3c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b48a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b3c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b48a`
- `SPOOLSS!DllFreeSplMem` at `0x18009b6aa`
- `SPOOLSS!DllFreeSplMem` at `0x18009b6c4`
- `SPOOLSS!DllFreeSplMem` at `0x18009b71b`
- `SPOOLSS!DllFreeSplMem` at `0x18009b751`
- `SPOOLSS!DllFreeSplMem` at `0x18009b6aa`
- `SPOOLSS!DllFreeSplMem` at `0x18009b6c4`
- `SPOOLSS!DllFreeSplMem` at `0x18009b71b`
- `SPOOLSS!DllFreeSplMem` at `0x18009b751`
- `SPOOLSS!DllAllocSplMem` at `0x18009b34f`
- `SPOOLSS!DllAllocSplMem` at `0x18009b34f`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009b63b`
- `SPOOLSS!RevertToPrinterSelf` at `0x18009b63b`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009b6d2`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18009b6d2`

## string_xrefs

- `0x18009b765`: `File copy failed for printer '%ws'.  Destination '%ws', copy count %d.`
- `0x18009b3de`: `CreateFile %ws %ws with error code %d`
- `0x18009b4a6`: `CreateFile %ws %ws with error code %d`
- `0x18009b3e9`: `SplCopyNumberOfFilesInternal`
- `0x18009b4b4`: `SplCopyNumberOfFilesInternal`
- `0x18009b76c`: `SplCopyNumberOfFilesInternal`

## pseudocode

```c
__int64 __fastcall SplCopyNumberOfFilesInternal(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned int a3,
        unsigned __int16 *a4,
        int a5,
        int *a6)
{
  int *v6; // r15
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // r12
  unsigned __int16 **v9; // r13
  unsigned __int64 v10; // rcx
  __int64 v12; // rsi
  __int64 v13; // r14
  int v14; // eax
  unsigned int v15; // r15d
  int v16; // r12d
  __int64 v17; // rbx
  HANDLE FileW; // rax
  const unsigned __int16 *v19; // rbx
  DWORD LastError; // eax
  __int64 v21; // r14
  HANDLE v22; // rax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r14d
  __int64 v27; // r8
  void *v28; // rdx
  const unsigned __int16 *v29; // r14
  DWORD v30; // eax
  unsigned __int16 *v31; // r15
  unsigned int j; // r14d
  void *v33; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+28h] [rbp-59h]
  int v36; // [rsp+6Ch] [rbp-15h] BYREF
  LPCWSTR lpPathName; // [rsp+70h] [rbp-11h] BYREF
  LPCWSTR v38; // [rsp+78h] [rbp-9h] BYREF
  __int64 v39; // [rsp+80h] [rbp-1h]
  int i; // [rsp+E8h] [rbp+67h] BYREF
  unsigned __int16 *v43; // [rsp+F0h] [rbp+6Fh]

  v43 = a4;
  v6 = a6;
  v7 = (unsigned __int64)a1;
  v36 = 0;
  v8 = a4;
  lpPathName = 0;
  v9 = a2;
  *a6 = 0;
  v38 = 0;
  v10 = 32LL * a3;
  if ( v10 > 0xFFFFFFFF )
    return 0;
  v12 = DllAllocSplMem(v10);
  if ( !v12 )
    return 0;
  v13 = 0;
  v14 = 0;
  v39 = 0;
  if ( a3 )
  {
    v15 = 0;
    v16 = 0;
    if ( v7 )
    {
      do
      {
        v17 = 32 * v13;
        *(_QWORD *)(32 * v13 + v12) = v9[v13];
        FileW = CreateFileW(v9[v13], 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
        *(_QWORD *)(32 * v13 + v12 + 16) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          dwCreationDisposition[0] = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SplCopyNumberOfFilesInternal",
            L"CreateFile %ws %ws with error code %d",
            a1,
            v9[v13],
            *(_QWORD *)dwCreationDisposition);
          v19 = v9[v13];
          LastError = GetLastError();
          ReportCopyError(LastError, a1, v19);
          ++v16;
        }
        else if ( a5 )
        {
          if ( !(unsigned int)GetPrintDriverVersion(*(LPCWSTR *)(v17 + v12)) )
            *(_DWORD *)(v17 + v12 + 8) = 0;
          v9 = a2;
        }
        ++v15;
        ++v13;
      }
      while ( v15 < a3 );
    }
    else
    {
      do
      {
        v21 = 32LL * (unsigned int)v7;
        *(_QWORD *)(v21 + v12) = v9[v7];
        v22 = CreateFileW(v9[v7], 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
        *(_QWORD *)(v21 + v12 + 16) = v22;
        if ( v22 == (HANDLE)-1LL )
        {
          dwCreationDisposition[0] = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SplCopyNumberOfFilesInternal",
            L"CreateFile %ws %ws with error code %d",
            0,
            v9[v7],
            *(_QWORD *)dwCreationDisposition);
          ++v16;
        }
        else if ( a5 && !(unsigned int)GetPrintDriverVersion(*(LPCWSTR *)(v21 + v12)) )
        {
          *(_DWORD *)(v21 + v12 + 8) = 0;
        }
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < a3 );
    }
    v6 = a6;
    v14 = v16;
    v13 = v39;
    i = v16;
    v8 = v43;
  }
  if ( v14 == a3 )
  {
    v23 = 1;
  }
  else
  {
    v23 = 0;
    if ( (unsigned int)DirectoryExists(v8) || (unsigned int)CreateDirectoryWithoutImpersonatingUser(v8) )
    {
      v24 = StrCatAlloc(&lpPathName, v8, L"\\New", 0);
      if ( (unsigned int)BoolFromStatus(v24)
        && ((unsigned int)DirectoryExists(lpPathName)
         || (unsigned int)CreateDirectoryWithoutImpersonatingUser(lpPathName)) )
      {
        v25 = StrCatAlloc(&v38, v8, L"\\Old", 0);
        if ( (unsigned int)BoolFromStatus(v25) )
        {
          if ( (unsigned int)DirectoryExists(v38) || (unsigned int)CreateDirectoryWithoutImpersonatingUser(v38) )
          {
            EnterSplSem(0);
            v26 = 0;
            for ( i = 0; v26 < a3; ++v26 )
            {
              v27 = 32LL * v26;
              v28 = *(void **)(v27 + v12 + 16);
              if ( v28 != (void *)-1LL )
                UpdateFile(
                  0,
                  v28,
                  *(const wchar_t **)(v27 + v12),
                  *(_DWORD *)(v27 + v12 + 8),
                  v8,
                  8u,
                  0,
                  &i,
                  &v36,
                  1,
                  0);
            }
            v13 = (__int64)RevertToPrinterSelf();
            v23 = 0;
            LeaveSplSem(-v13);
          }
        }
      }
    }
  }
  if ( lpPathName )
  {
    DeleteDirectoryRecursively((unsigned __int16 *)lpPathName, 0);
    DllFreeSplMem(lpPathName);
  }
  if ( v38 )
  {
    DeleteDirectoryRecursively((unsigned __int16 *)v38, 0);
    DllFreeSplMem(v38);
  }
  if ( v13 )
    v23 &= -ImpersonatePrinterClient((HANDLE)v13);
  if ( *v6 && (v29 = (const unsigned __int16 *)BuildFilesCopiedAsAString(v12, a3)) != 0 )
  {
    v30 = GetLastError();
    v31 = a1;
    SplLogEvent(&MSG_FILES_COPIED, v30, v29, a1, 0);
    DllFreeSplMem(v29);
  }
  else
  {
    v31 = a1;
  }
  for ( j = 0; j < a3; ++j )
  {
    v33 = *(void **)(32LL * j + v12 + 16);
    if ( v33 != (void *)-1LL )
      CloseHandle(v33);
  }
  DllFreeSplMem(v12);
  if ( !v23 )
  {
    dwCreationDisposition[0] = a3;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplCopyNumberOfFilesInternal",
      L"File copy failed for printer '%ws'.  Destination '%ws', copy count %d.",
      v31,
      v8,
      *(_QWORD *)dwCreationDisposition);
  }
  return v23;
}

```

## disassembly

```asm
0x18009b2f4  mov     rax, rsp
0x18009b2f7  mov     [rax+20h], r9
0x18009b2fb  mov     [rax+10h], rdx
0x18009b2ff  mov     [rax+8], rcx
0x18009b303  push    rbp
0x18009b304  push    rbx
0x18009b305  push    rsi
0x18009b306  push    rdi
0x18009b307  push    r12
0x18009b309  push    r13
0x18009b30b  push    r14
0x18009b30d  push    r15
0x18009b30f  lea     rbp, [rax-4Fh]
0x18009b313  sub     rsp, 88h
0x18009b31a  mov     r15, [rbp+47h+arg_28]
0x18009b31e  xor     eax, eax
0x18009b320  mov     rbx, rcx
0x18009b323  mov     [rbp+47h+var_5C], eax
0x18009b326  mov     ecx, r8d
0x18009b329  mov     r12, r9
0x18009b32c  mov     [rbp+47h+lpPathName], rax
0x18009b330  mov     r13, rdx
0x18009b333  mov     [r15], eax
0x18009b336  mov     [rbp+47h+var_50], rax
0x18009b33a  mov     eax, 0FFFFFFFFh
0x18009b33f  shl     rcx, 5
0x18009b343  mov     edi, r8d
0x18009b346  cmp     rcx, rax
0x18009b349  ja      loc_18009B77C
0x18009b34f  call    cs:__imp_DllAllocSplMem
0x18009b355  mov     rsi, rax
0x18009b358  test    rax, rax
0x18009b35b  jz      loc_18009B77C
0x18009b361  xor     r14d, r14d
0x18009b364  mov     [rbp+47h+var_60], 0
0x18009b36b  xor     eax, eax
0x18009b36d  mov     [rbp+47h+var_48], r14
0x18009b371  test    edi, edi
0x18009b373  jz      loc_18009B503
0x18009b379  xor     r15d, r15d
0x18009b37c  mov     r12d, eax
0x18009b37f  test    rbx, rbx
0x18009b382  jz      loc_18009B450
0x18009b388  mov     rax, [r13+r14*8+0]
0x18009b38d  xor     r9d, r9d; lpSecurityAttributes
0x18009b390  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18009b399  mov     rbx, r14
0x18009b39c  shl     rbx, 5
0x18009b3a0  mov     edx, 80000000h; dwDesiredAccess
0x18009b3a5  mov     [rsp+0C0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18009b3ad  lea     r8d, [r9+1]; dwShareMode
0x18009b3b1  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18009b3b9  mov     [rbx+rsi], rax
0x18009b3bd  mov     rcx, [r13+r14*8+0]; lpFileName
0x18009b3c2  call    cs:__imp_CreateFileW
0x18009b3c8  mov     [rbx+rsi+10h], rax
0x18009b3cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009b3d1  jnz     short loc_18009B417
0x18009b3d3  call    cs:__imp_GetLastError
0x18009b3d9  mov     r9, [r13+r14*8+0]
0x18009b3de  lea     rdx, aCreatefileWsWs; "CreateFile %ws %ws with error code %d"
0x18009b3e5  mov     r8, [rbp+47h+arg_0]
0x18009b3e9  lea     rcx, aSplcopynumbero_0; "SplCopyNumberOfFilesInternal"
0x18009b3f0  mov     [rsp+0C0h+dwCreationDisposition], eax
0x18009b3f4  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009b3f9  mov     rbx, [r13+r14*8+0]
0x18009b3fe  call    cs:__imp_GetLastError
0x18009b404  mov     rdx, [rbp+47h+arg_0]; unsigned __int16 *
0x18009b408  mov     r8, rbx; unsigned __int16 *
0x18009b40b  mov     ecx, eax; dwMessageId
0x18009b40d  call    ?ReportCopyError@@YAXKPEBG0@Z; ReportCopyError(ulong,ushort const *,ushort const *)
0x18009b412  inc     r12d
0x18009b415  jmp     short loc_18009B43C
0x18009b417  cmp     [rbp+47h+arg_20], 0
0x18009b41b  jz      short loc_18009B43C
0x18009b41d  mov     rcx, [rbx+rsi]; lpwstrFilename
0x18009b421  lea     r13, [rbx+rsi]
0x18009b425  lea     r8, [r13+8]
0x18009b429  xor     edx, edx
0x18009b42b  call    GetPrintDriverVersion
0x18009b430  test    eax, eax
0x18009b432  jnz     short loc_18009B438
0x18009b434  mov     [r13+8], eax
0x18009b438  mov     r13, [rbp+47h+arg_8]
0x18009b43c  inc     r15d
0x18009b43f  inc     r14
0x18009b442  cmp     r15d, edi
0x18009b445  jb      loc_18009B388
0x18009b44b  jmp     loc_18009B4F0
0x18009b450  mov     rax, [r13+rbx*8+0]
0x18009b455  xor     r9d, r9d; lpSecurityAttributes
0x18009b458  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18009b461  mov     edx, 80000000h; dwDesiredAccess
0x18009b466  mov     r14d, ebx
0x18009b469  shl     r14, 5
0x18009b46d  mov     [rsp+0C0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18009b475  lea     r8d, [r9+1]; dwShareMode
0x18009b479  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18009b481  mov     [r14+rsi], rax
0x18009b485  mov     rcx, [r13+rbx*8+0]; lpFileName
0x18009b48a  call    cs:__imp_CreateFileW
0x18009b490  mov     [r14+rsi+10h], rax
0x18009b495  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009b499  jnz     short loc_18009B4C5
0x18009b49b  call    cs:__imp_GetLastError
0x18009b4a1  mov     r9, [r13+rbx*8+0]
0x18009b4a6  lea     rdx, aCreatefileWsWs; "CreateFile %ws %ws with error code %d"
0x18009b4ad  xor     r8d, r8d
0x18009b4b0  mov     [rsp+0C0h+dwCreationDisposition], eax
0x18009b4b4  lea     rcx, aSplcopynumbero_0; "SplCopyNumberOfFilesInternal"
0x18009b4bb  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009b4c0  inc     r12d
0x18009b4c3  jmp     short loc_18009B4E6
0x18009b4c5  cmp     [rbp+47h+arg_20], 0
0x18009b4c9  jz      short loc_18009B4E6
0x18009b4cb  mov     rcx, [r14+rsi]; lpwstrFilename
0x18009b4cf  lea     r15, [r14+rsi]
0x18009b4d3  lea     r8, [r15+8]
0x18009b4d7  xor     edx, edx
0x18009b4d9  call    GetPrintDriverVersion
0x18009b4de  test    eax, eax
0x18009b4e0  jnz     short loc_18009B4E6
0x18009b4e2  mov     [r15+8], eax
0x18009b4e6  inc     ebx
0x18009b4e8  cmp     ebx, edi
0x18009b4ea  jb      loc_18009B450
0x18009b4f0  mov     r15, [rbp+47h+arg_28]
0x18009b4f4  mov     eax, r12d
0x18009b4f7  mov     r14, [rbp+47h+var_48]
0x18009b4fb  mov     [rbp+47h+arg_10], r12d
0x18009b4ff  mov     r12, [rbp+47h+arg_18]
0x18009b503  xor     r13d, r13d
0x18009b506  cmp     eax, edi
0x18009b508  jnz     short loc_18009B513
0x18009b50a  lea     ebx, [r13+1]
0x18009b50e  jmp     loc_18009B695
0x18009b513  mov     rcx, r12
0x18009b516  mov     ebx, r13d
0x18009b519  call    DirectoryExists
0x18009b51e  test    eax, eax
0x18009b520  jnz     short loc_18009B532
0x18009b522  mov     rcx, r12; lpPathName
0x18009b525  call    CreateDirectoryWithoutImpersonatingUser
0x18009b52a  test    eax, eax
0x18009b52c  jz      loc_18009B695
0x18009b532  xor     r9d, r9d
0x18009b535  lea     r8, aNew; "\\New"
0x18009b53c  mov     rdx, r12
0x18009b53f  lea     rcx, [rbp+47h+lpPathName]
0x18009b543  call    StrCatAlloc
0x18009b548  mov     ecx, eax
0x18009b54a  call    BoolFromStatus
0x18009b54f  test    eax, eax
0x18009b551  jz      loc_18009B695
0x18009b557  mov     rcx, [rbp+47h+lpPathName]
0x18009b55b  call    DirectoryExists
0x18009b560  test    eax, eax
0x18009b562  jnz     short loc_18009B575
0x18009b564  mov     rcx, [rbp+47h+lpPathName]; lpPathName
0x18009b568  call    CreateDirectoryWithoutImpersonatingUser
0x18009b56d  test    eax, eax
0x18009b56f  jz      loc_18009B695
0x18009b575  xor     r9d, r9d
0x18009b578  lea     r8, aOld; "\\Old"
0x18009b57f  mov     rdx, r12
0x18009b582  lea     rcx, [rbp+47h+var_50]
0x18009b586  call    StrCatAlloc
0x18009b58b  mov     ecx, eax
0x18009b58d  call    BoolFromStatus
0x18009b592  test    eax, eax
0x18009b594  jz      loc_18009B695
0x18009b59a  mov     rcx, [rbp+47h+var_50]
0x18009b59e  call    DirectoryExists
0x18009b5a3  test    eax, eax
0x18009b5a5  jnz     short loc_18009B5B8
0x18009b5a7  mov     rcx, [rbp+47h+var_50]; lpPathName
0x18009b5ab  call    CreateDirectoryWithoutImpersonatingUser
0x18009b5b0  test    eax, eax
0x18009b5b2  jz      loc_18009B695
0x18009b5b8  xor     ecx, ecx
0x18009b5ba  call    EnterSplSem
0x18009b5bf  mov     eax, r13d
0x18009b5c2  mov     r14d, r13d
0x18009b5c5  mov     [rbp+47h+arg_10], eax
0x18009b5c8  test    edi, edi
0x18009b5ca  jz      short loc_18009B63B
0x18009b5cc  mov     r8d, r14d
0x18009b5cf  shl     r8, 5
0x18009b5d3  mov     rdx, [r8+rsi+10h]
0x18009b5d8  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18009b5dc  jz      short loc_18009B628
0x18009b5de  mov     r9d, [r8+rsi+8]
0x18009b5e3  lea     rax, [rbp+47h+var_5C]
0x18009b5e7  mov     r8, [r8+rsi]
0x18009b5eb  xor     ecx, ecx
0x18009b5ed  mov     [rsp+50h], r13d
0x18009b5f2  mov     [rsp+0C0h+var_78], 1
0x18009b5fa  mov     qword ptr [rsp+0C0h+var_80], rax
0x18009b5ff  lea     rax, [rbp+47h+arg_10]
0x18009b603  mov     [rsp+0C0h+var_88], rax
0x18009b608  mov     dword ptr [rsp+0C0h+hTemplateFile], r13d
0x18009b60d  mov     [rsp+0C0h+dwFlagsAndAttributes], 8
0x18009b615  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r12
0x18009b61a  call    UpdateFile
0x18009b61f  mov     ebx, eax
0x18009b621  test    eax, eax
0x18009b623  jz      short loc_18009B63B
0x18009b625  mov     eax, [rbp+47h+arg_10]
0x18009b628  test    eax, eax
0x18009b62a  jz      short loc_18009B633
0x18009b62c  mov     dword ptr [r15], 1
0x18009b633  inc     r14d
0x18009b636  cmp     r14d, edi
0x18009b639  jb      short loc_18009B5CC
0x18009b63b  call    cs:__imp_RevertToPrinterSelf
0x18009b641  mov     rcx, rax
0x18009b644  mov     r14, rax
0x18009b647  neg     rcx
0x18009b64a  sbb     edx, edx
0x18009b64c  and     ebx, edx
0x18009b64e  jz      short loc_18009B68D
0x18009b650  cmp     [r15], r13d
0x18009b653  jz      short loc_18009B690
0x18009b655  mov     r8, [rbp+47h+var_50]
0x18009b659  mov     r9, rsi
0x18009b65c  mov     rcx, [rbp+47h+lpPathName]
0x18009b660  mov     rdx, r12
0x18009b663  mov     dword ptr [rsp+0C0h+var_88], 1
0x18009b66b  mov     [rsp+0C0h+hTemplateFile], r13
0x18009b670  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], r13
0x18009b675  mov     [rsp+0C0h+dwCreationDisposition], edi
0x18009b679  call    MoveNewDriverRelatedFiles
0x18009b67e  mov     ebx, eax
0x18009b680  mov     eax, r13d
0x18009b683  test    ebx, ebx
0x18009b685  setz    al
0x18009b688  mov     [rbp+47h+var_60], eax
0x18009b68b  jmp     short loc_18009B690
0x18009b68d  mov     ebx, r13d
0x18009b690  call    LeaveSplSem
0x18009b695  mov     rcx, [rbp+47h+lpPathName]; unsigned __int16 *
0x18009b699  test    rcx, rcx
0x18009b69c  jz      short loc_18009B6B0
0x18009b69e  mov     edx, [rbp+47h+var_60]
0x18009b6a1  call    DeleteDirectoryRecursively
0x18009b6a6  mov     rcx, [rbp+47h+lpPathName]
0x18009b6aa  call    cs:__imp_DllFreeSplMem
0x18009b6b0  mov     rcx, [rbp+47h+var_50]; unsigned __int16 *
0x18009b6b4  test    rcx, rcx
0x18009b6b7  jz      short loc_18009B6CA
0x18009b6b9  xor     edx, edx
0x18009b6bb  call    DeleteDirectoryRecursively
0x18009b6c0  mov     rcx, [rbp+47h+var_50]
0x18009b6c4  call    cs:__imp_DllFreeSplMem
0x18009b6ca  test    r14, r14
0x18009b6cd  jz      short loc_18009B6DE
0x18009b6cf  mov     rcx, r14; hToken
0x18009b6d2  call    cs:__imp_ImpersonatePrinterClient
0x18009b6d8  neg     eax
0x18009b6da  sbb     ecx, ecx
0x18009b6dc  and     ebx, ecx
0x18009b6de  cmp     [r15], r13d
0x18009b6e1  jz      short loc_18009B723
0x18009b6e3  mov     edx, edi
0x18009b6e5  mov     rcx, rsi
0x18009b6e8  call    BuildFilesCopiedAsAString
0x18009b6ed  mov     r14, rax
0x18009b6f0  test    rax, rax
0x18009b6f3  jz      short loc_18009B723
0x18009b6f5  call    cs:__imp_GetLastError
0x18009b6fb  mov     r15, [rbp+47h+arg_0]
0x18009b6ff  lea     rcx, MSG_FILES_COPIED; struct _EVENT_DESCRIPTOR *
0x18009b706  mov     edx, eax; unsigned int
0x18009b708  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r13
0x18009b70d  mov     r9, r15
0x18009b710  mov     r8, r14; unsigned __int16 *
0x18009b713  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x18009b718  mov     rcx, r14
0x18009b71b  call    cs:__imp_DllFreeSplMem
0x18009b721  jmp     short loc_18009B727
0x18009b723  mov     r15, [rbp+47h+arg_0]
0x18009b727  mov     r14d, r13d
0x18009b72a  test    edi, edi
0x18009b72c  jz      short loc_18009B74E
0x18009b72e  mov     eax, r14d
0x18009b731  shl     rax, 5
0x18009b735  mov     rcx, [rax+rsi+10h]; hObject
0x18009b73a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009b73e  jz      short loc_18009B746
0x18009b740  call    cs:__imp_CloseHandle
0x18009b746  inc     r14d
0x18009b749  cmp     r14d, edi
0x18009b74c  jb      short loc_18009B72E
0x18009b74e  mov     rcx, rsi
0x18009b751  call    cs:__imp_DllFreeSplMem
0x18009b757  test    ebx, ebx
0x18009b759  jnz     short loc_18009B778
0x18009b75b  mov     r9, r12
0x18009b75e  mov     [rsp+0C0h+dwCreationDisposition], edi
0x18009b762  mov     r8, r15
  ... truncated ...
```
