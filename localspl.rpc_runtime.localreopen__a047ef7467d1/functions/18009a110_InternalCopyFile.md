# InternalCopyFile

- ea: `0x18009a110`
- end: `0x18009a354`
- name: `InternalCopyFile`
- size: `580`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180033a9c`

## callees

- `0x18001fb10`
- `0x18003ea2c`
- `0x18009a110`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a281`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a28a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a28a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a16e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a16e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009a1ef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009a1ef`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009a23e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009a23e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009a197`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009a197`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18009a22b`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18009a22b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009a1c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009a1c4`
- `SPOOLSS!DllFreeSplMem` at `0x18009a293`
- `SPOOLSS!DllFreeSplMem` at `0x18009a293`
- `SPOOLSS!DllAllocSplMem` at `0x18009a14d`
- `SPOOLSS!DllAllocSplMem` at `0x18009a14d`

## string_xrefs

- `0x18009a20b`: `InternalCopyFile`
- `0x18009a262`: `InternalCopyFile`
- `0x18009a2b1`: `InternalCopyFile`
- `0x18009a26d`: `InternalCopyFile sizes do not match for %ws: (%u %u) and (%u %u)`
- `0x18009a204`: `Failed to copy file data.  WriteFile returned %d, written %d, read %d.`

## pseudocode

```c
__int64 __fastcall InternalCopyFile(HANDLE hFile, __int64 a2, const WCHAR *a3)
{
  unsigned int v4; // ebx
  void *v7; // r14
  DWORD v8; // esi
  HANDLE FileW; // rsi
  unsigned int v10; // eax
  DWORD FileSize; // eax
  DWORD LastError; // eax
  struct SplLogType *v13; // rax
  __int64 v14; // r10
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-89h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-89h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-81h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-79h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-69h] BYREF
  DWORD FileSizeHigh; // [rsp+44h] [rbp-65h] BYREF
  int v22; // [rsp+48h] [rbp-61h] BYREF
  __int64 v23; // [rsp+50h] [rbp-59h]
  int v24; // [rsp+58h] [rbp-51h]
  DWORD v25; // [rsp+60h] [rbp-49h] BYREF
  __int64 v26; // [rsp+68h] [rbp-41h]
  int v27; // [rsp+70h] [rbp-39h]
  int v28; // [rsp+78h] [rbp-31h] BYREF
  __int64 v29; // [rsp+80h] [rbp-29h]
  int v30; // [rsp+88h] [rbp-21h]
  _BYTE v31[24]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v32[88]; // [rsp+A8h] [rbp-1h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+128h] [rbp+7Fh] BYREF

  FileSizeHigh = 0;
  v4 = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v7 = (void *)DllAllocSplMem(4096);
  if ( !v7 )
    goto LABEL_18;
  v8 = *(_DWORD *)a2 & 0xFFFFFFFE;
  if ( (*(_BYTE *)a2 & 1) != 0 )
    SetFileAttributesW(a3, v8);
  FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, v8 | 0x8000000, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v4 = ReadFile(hFile, v7, 0x1000u, &nNumberOfBytesToWrite, 0);
      if ( !v4 )
        break;
      if ( !nNumberOfBytesToWrite )
      {
        v4 = SetFileTime(FileW, (const FILETIME *)(a2 + 4), (const FILETIME *)(a2 + 12), (const FILETIME *)(a2 + 20));
        if ( v4 )
        {
          FileSize = GetFileSize(FileW, &FileSizeHigh);
          if ( FileSize != *(_DWORD *)(a2 + 32) || FileSizeHigh != *(_DWORD *)(a2 + 28) )
          {
            LODWORD(hTemplateFile) = FileSize;
            dwFlagsAndAttributes[0] = FileSizeHigh;
            dwCreationDisposition[0] = *(_DWORD *)(a2 + 32);
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "InternalCopyFile",
              L"InternalCopyFile sizes do not match for %ws: (%u %u) and (%u %u)",
              a3,
              *(unsigned int *)(a2 + 28),
              *(_QWORD *)dwCreationDisposition,
              *(_QWORD *)dwFlagsAndAttributes,
              hTemplateFile);
            v4 = 0;
            SetLastError(0x3EEu);
          }
        }
        break;
      }
      v10 = WriteFile(FileW, v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      if ( !v10 || NumberOfBytesWritten != nNumberOfBytesToWrite )
      {
        dwCreationDispositiona[0] = nNumberOfBytesToWrite;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "InternalCopyFile",
          L"Failed to copy file data.  WriteFile returned %d, written %d, read %d.",
          v10,
          NumberOfBytesWritten,
          *(_QWORD *)dwCreationDispositiona);
        v4 = 0;
        break;
      }
    }
    CloseHandle(FileW);
  }
  DllFreeSplMem(v7);
  if ( !v4 )
  {
LABEL_18:
    dwCreationDisposition[0] = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalCopyFile",
      L"hSourceFile %p %ws. Failed with error code %d",
      hFile,
      a3,
      *(_QWORD *)dwCreationDisposition);
    v22 = 105;
    v23 = 4;
    v24 = 0;
    LastError = GetLastError();
    v26 = 4;
    v25 = LastError;
    v27 = 0;
    v28 = 0;
    v29 = 4;
    v30 = 0;
    SplLogType::SplLogType((SplLogType *)v31, a3);
    v13 = SplLogType::SplLogType((SplLogType *)v32, (const unsigned __int16 *)(a2 + 44));
    SplLogEvent2(&SPOOLER_COPY_FILE_FAILED, v13, v14, &v28, &v25, &v22, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x18009a110  mov     [rsp-8+nNumberOfBytesToWrite], r9d
0x18009a115  push    rbp
0x18009a116  push    rbx
0x18009a117  push    rsi
0x18009a118  push    rdi
0x18009a119  push    r12
0x18009a11b  push    r13
0x18009a11d  push    r14
0x18009a11f  push    r15
0x18009a121  lea     rbp, [rsp-1Fh]
0x18009a126  sub     rsp, 0C8h
0x18009a12d  xor     r13d, r13d
0x18009a130  mov     r12, rcx
0x18009a133  mov     ecx, 1000h
0x18009a138  mov     [rbp+57h+FileSizeHigh], r13d
0x18009a13c  mov     ebx, r13d
0x18009a13f  mov     [rbp+57h+nNumberOfBytesToWrite], r13d
0x18009a143  mov     [rbp+57h+NumberOfBytesWritten], r13d
0x18009a147  mov     r15, r8
0x18009a14a  mov     rdi, rdx
0x18009a14d  call    cs:__imp_DllAllocSplMem
0x18009a153  mov     r14, rax
0x18009a156  test    rax, rax
0x18009a159  jz      loc_18009A2A1
0x18009a15f  mov     esi, [rdi]
0x18009a161  and     esi, 0FFFFFFFEh
0x18009a164  test    byte ptr [rdi], 1
0x18009a167  jz      short loc_18009A174
0x18009a169  mov     edx, esi; dwFileAttributes
0x18009a16b  mov     rcx, r15; lpFileName
0x18009a16e  call    cs:__imp_SetFileAttributesW
0x18009a174  mov     [rsp+100h+hTemplateFile], r13; hTemplateFile
0x18009a179  bts     esi, 1Bh
0x18009a17d  mov     [rsp+100h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18009a181  xor     r9d, r9d; lpSecurityAttributes
0x18009a184  xor     r8d, r8d; dwShareMode
0x18009a187  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x18009a18f  mov     edx, 40000000h; dwDesiredAccess
0x18009a194  mov     rcx, r15; lpFileName
0x18009a197  call    cs:__imp_CreateFileW
0x18009a19d  mov     rsi, rax
0x18009a1a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009a1a4  jz      loc_18009A290
0x18009a1aa  jmp     short loc_18009A1DA
0x18009a1ac  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18009a1b0  mov     rcx, rsi; hFile
0x18009a1b3  test    r8d, r8d
0x18009a1b6  jz      short loc_18009A21F
0x18009a1b8  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009a1bc  mov     qword ptr [rsp+100h+dwCreationDisposition], r13; lpOverlapped
0x18009a1c1  mov     rdx, r14; lpBuffer
0x18009a1c4  call    cs:__imp_WriteFile
0x18009a1ca  mov     ecx, [rbp+57h+nNumberOfBytesToWrite]
0x18009a1cd  mov     r9d, [rbp+57h+NumberOfBytesWritten]
0x18009a1d1  test    eax, eax
0x18009a1d3  jz      short loc_18009A200
0x18009a1d5  cmp     r9d, ecx
0x18009a1d8  jnz     short loc_18009A200
0x18009a1da  lea     r9, [rbp+57h+nNumberOfBytesToWrite]; lpNumberOfBytesRead
0x18009a1de  mov     qword ptr [rsp+100h+dwCreationDisposition], r13; lpOverlapped
0x18009a1e3  mov     r8d, 1000h; nNumberOfBytesToRead
0x18009a1e9  mov     rdx, r14; lpBuffer
0x18009a1ec  mov     rcx, r12; hFile
0x18009a1ef  call    cs:__imp_ReadFile
0x18009a1f5  mov     ebx, eax
0x18009a1f7  test    eax, eax
0x18009a1f9  jnz     short loc_18009A1AC
0x18009a1fb  jmp     loc_18009A287
0x18009a200  mov     [rsp+100h+dwCreationDisposition], ecx
0x18009a204  lea     rdx, aFailedToCopyFi; "Failed to copy file data.  WriteFile re"...
0x18009a20b  lea     rcx, aInternalcopyfi_0; "InternalCopyFile"
0x18009a212  mov     r8d, eax
0x18009a215  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a21a  mov     ebx, r13d
0x18009a21d  jmp     short loc_18009A287
0x18009a21f  lea     r9, [rdi+14h]; lpLastWriteTime
0x18009a223  lea     r8, [rdi+0Ch]; lpLastAccessTime
0x18009a227  lea     rdx, [rdi+4]; lpCreationTime
0x18009a22b  call    cs:__imp_SetFileTime
0x18009a231  mov     ebx, eax
0x18009a233  test    eax, eax
0x18009a235  jz      short loc_18009A287
0x18009a237  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x18009a23b  mov     rcx, rsi; hFile
0x18009a23e  call    cs:__imp_GetFileSize
0x18009a244  mov     edx, [rdi+20h]
0x18009a247  mov     ecx, [rbp+57h+FileSizeHigh]
0x18009a24a  cmp     eax, edx
0x18009a24c  jnz     short loc_18009A253
0x18009a24e  cmp     ecx, [rdi+1Ch]
0x18009a251  jz      short loc_18009A287
0x18009a253  mov     r9d, [rdi+1Ch]
0x18009a257  mov     r8, r15
0x18009a25a  mov     dword ptr [rsp+100h+hTemplateFile], eax
0x18009a25e  mov     [rsp+100h+dwFlagsAndAttributes], ecx
0x18009a262  lea     rcx, aInternalcopyfi_0; "InternalCopyFile"
0x18009a269  mov     [rsp+100h+dwCreationDisposition], edx
0x18009a26d  lea     rdx, aInternalcopyfi; "InternalCopyFile sizes do not match for"...
0x18009a274  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a279  mov     ecx, 3EEh; dwErrCode
0x18009a27e  mov     ebx, r13d
0x18009a281  call    cs:__imp_SetLastError
0x18009a287  mov     rcx, rsi; hObject
0x18009a28a  call    cs:__imp_CloseHandle
0x18009a290  mov     rcx, r14
0x18009a293  call    cs:__imp_DllFreeSplMem
0x18009a299  test    ebx, ebx
0x18009a29b  jnz     loc_18009A33E
0x18009a2a1  call    cs:__imp_GetLastError
0x18009a2a7  mov     r9, r15
0x18009a2aa  lea     rdx, aHsourcefilePWs; "hSourceFile %p %ws. Failed with error c"...
0x18009a2b1  lea     rcx, aInternalcopyfi_0; "InternalCopyFile"
0x18009a2b8  mov     [rsp+100h+dwCreationDisposition], eax
0x18009a2bc  mov     r8, r12
0x18009a2bf  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009a2c4  mov     esi, 4
0x18009a2c9  mov     [rbp+57h+var_B8], 69h ; 'i'
0x18009a2d0  mov     [rbp+57h+var_B0], rsi
0x18009a2d4  mov     [rbp+57h+var_A8], r13d
0x18009a2d8  call    cs:__imp_GetLastError
0x18009a2de  mov     rdx, r15; unsigned __int16 *
0x18009a2e1  mov     [rbp+57h+var_98], rsi
0x18009a2e5  lea     rcx, [rbp+57h+var_70]; this
0x18009a2e9  mov     [rbp+57h+var_A0], eax
0x18009a2ec  mov     [rbp+57h+var_90], r13d
0x18009a2f0  mov     [rbp+57h+var_88], r13d
0x18009a2f4  mov     [rbp+57h+var_80], rsi
0x18009a2f8  mov     [rbp+57h+var_78], r13d
0x18009a2fc  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18009a301  lea     rdx, [rdi+2Ch]; unsigned __int16 *
0x18009a305  mov     r10, rax
0x18009a308  lea     rcx, [rbp+57h+var_58]; this
0x18009a30c  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18009a311  lea     rcx, [rbp+57h+var_B8]
0x18009a315  mov     [rsp+100h+hTemplateFile], r13
0x18009a31a  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rcx
0x18009a31f  lea     r9, [rbp+57h+var_88]
0x18009a323  lea     rcx, [rbp+57h+var_A0]
0x18009a327  mov     r8, r10
0x18009a32a  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx
0x18009a32f  mov     rdx, rax; struct SplLogType *
0x18009a332  lea     rcx, SPOOLER_COPY_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x18009a339  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18009a33e  mov     eax, ebx
0x18009a340  add     rsp, 0C8h
0x18009a347  pop     r15
0x18009a349  pop     r14
0x18009a34b  pop     r13
0x18009a34d  pop     r12
0x18009a34f  pop     rdi
0x18009a350  pop     rsi
0x18009a351  pop     rbx
0x18009a352  pop     rbp
0x18009a353  retn
```
