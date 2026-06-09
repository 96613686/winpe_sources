# CLogStorage::_OpenLogFile(ushort *,ulong *)

- ea: `0x18000c350`
- end: `0x18000c6b1`
- name: `?_OpenLogFile@CLogStorage@@AEAAJPEAGPEAK@Z`
- size: `865`
- prototype: `__int64 __fastcall(CLogStorage *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800065c8`

## callees

- `0x18000adf8`
- `0x18000c350`
- `0x18000d998`
- `0x18001280a`
- `0x180012830`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000c668`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000c668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c67a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000c617`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000c617`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c413`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c413`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c3fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c3fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c4c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c4c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c44a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c50e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c51b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c44a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c50e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c51b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c55e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c55e`

## string_xrefs

- `0x18000c3a7`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c428`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c574`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000c4e4`: `CreateFile`
- `0x18000c514`: `decompressing DTC log file\n`
- `0x18000c686`: `CreateFileMapping`

## pseudocode

```c
__int64 __fastcall CLogStorage::_OpenLogFile(CLogStorage *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  char *v7; // rdx
  int v8; // ecx
  unsigned int v9; // r9d
  HANDLE FirstFileW; // rax
  __int64 v12; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  void *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  DWORD FileSize; // eax
  unsigned int v19; // eax
  void *v20; // rcx
  DWORD v21; // eax
  HANDLE FileMappingW; // rax
  unsigned int hTemplateFile; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *lpOverlapped; // [rsp+38h] [rbp-C8h]
  unsigned int v25; // [rsp+40h] [rbp-C0h]
  DWORD dwFileAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int16 InBuffer; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v28; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+2B0h] [rbp+1B0h] BYREF

  *((_QWORD *)this + 19) = -1;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = "E_INVALIDARG";
    v8 = -2147024809;
    v9 = 2234;
LABEL_3:
    TraceFile(v8, v7, "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", v9);
    return v6;
  }
  TracedSafeSplitPathW(
    a2,
    (unsigned __int16 *)&BytesReturned,
    (unsigned int)a3,
    0,
    0,
    (unsigned __int16 *)this + 84,
    hTemplateFile,
    lpOverlapped,
    v25);
  dwFileAttributes = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a2, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    dwFileAttributes = FindFileData.dwFileAttributes;
    FindClose(FirstFileW);
  }
  if ( (dwFileAttributes & 0x1115) != 0 )
  {
    TraceFile(-2147467259, "bad logfile attributes", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x8ECu);
    OutputDebugStringA("ERROR: bad logfile attributes\r\n");
    v12 = *((_QWORD *)this + 97);
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, int, int, DWORD *, _QWORD))(*(_QWORD *)v12 + 24LL))(
        v12,
        4097,
        4,
        0,
        -1073737698,
        4,
        &dwFileAttributes,
        0);
    return 2147500037LL;
  }
  *((_DWORD *)this + 6) = 5;
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 3u, 0xB0000080, 0);
  *((_QWORD *)this + 19) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = 2336;
    v7 = "CreateFile";
    goto LABEL_12;
  }
  if ( (dwFileAttributes & 0x800) == 0 )
  {
LABEL_20:
    FileSize = GetFileSize(*((HANDLE *)this + 19), 0);
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      v9 = 2426;
      v7 = "GetFileSize";
    }
    else
    {
      v19 = FileSize >> 13;
      *((_DWORD *)this + 9) = v19;
      if ( a3 )
        *a3 = v19;
      v20 = (void *)*((_QWORD *)this + 19);
      v21 = *((_DWORD *)this + 9) << 13;
      *((_DWORD *)this + 8) = v21;
      FileMappingW = CreateFileMappingW(v20, 0, 4u, 0, v21, 0);
      *((_QWORD *)this + 20) = FileMappingW;
      if ( FileMappingW )
        return 0;
      LastError = GetLastError();
      v9 = 2450;
      v7 = "CreateFileMapping";
    }
LABEL_12:
    v6 = LastError;
    v8 = LastError;
    goto LABEL_3;
  }
  OutputDebugStringA("\r\n");
  OutputDebugStringA("decompressing DTC log file\r\n");
  v15 = (void *)*((_QWORD *)this + 19);
  InBuffer = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(v15, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
  {
    v17 = *((_QWORD *)this + 97);
    if ( v17 )
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
        v17,
        4099,
        4,
        0,
        1073745949,
        0,
        0,
        0);
    goto LABEL_20;
  }
  v28 = GetLastError();
  TraceFile(v28, "DeviceIoControl", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x940u);
  v16 = *((_QWORD *)this + 97);
  if ( v16 )
    (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, int, int, DWORD *, _QWORD))(*(_QWORD *)v16 + 24LL))(
      v16,
      4097,
      4,
      0,
      -1073737700,
      4,
      &v28,
      0);
  return v28;
}

```

## disassembly

```asm
0x18000c350  push    rbp
0x18000c352  push    rbx
0x18000c353  push    rsi
0x18000c354  push    rdi
0x18000c355  push    r14
0x18000c357  lea     rbp, [rsp-1C0h]
0x18000c35f  sub     rsp, 2C0h
0x18000c366  mov     rax, cs:__security_cookie
0x18000c36d  xor     rax, rsp
0x18000c370  mov     [rbp+1E0h+var_28], rax
0x18000c377  xor     r14d, r14d
0x18000c37a  mov     qword ptr [rcx+98h], 0FFFFFFFFFFFFFFFFh
0x18000c385  mov     rsi, r8
0x18000c388  mov     rdi, rdx
0x18000c38b  mov     rbx, rcx
0x18000c38e  test    rdx, rdx
0x18000c391  jnz     short loc_18000C3BA
0x18000c393  mov     ebx, 80070057h
0x18000c398  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000c39f  mov     ecx, ebx; int
0x18000c3a1  mov     r9d, 8BAh; unsigned int
0x18000c3a7  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c3ae  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c3b3  mov     eax, ebx
0x18000c3b5  jmp     loc_18000C694
0x18000c3ba  lea     rax, [rcx+0A8h]
0x18000c3c1  xor     r9d, r9d; unsigned __int16 *
0x18000c3c4  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18000c3c9  lea     rdx, [rbp+1E0h+BytesReturned]; unsigned __int16 *
0x18000c3d0  mov     rcx, rdi; unsigned __int16 *
0x18000c3d3  mov     [rsp+2E0h+dwCreationDisposition], r14d; unsigned int
0x18000c3d8  call    ?TracedSafeSplitPathW@@YAJPEAG0K0K0K0K@Z; TracedSafeSplitPathW(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong)
0x18000c3dd  xor     edx, edx; Val
0x18000c3df  mov     [rsp+2E0h+var_290], r14d
0x18000c3e4  mov     r8d, 250h; Size
0x18000c3ea  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18000c3ef  call    memset_0
0x18000c3f4  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18000c3f9  mov     rcx, rdi; lpFileName
0x18000c3fc  call    cs:__imp_FindFirstFileW
0x18000c402  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c406  jz      short loc_18000C419
0x18000c408  mov     ecx, [rsp+2E0h+FindFileData.dwFileAttributes]
0x18000c40c  mov     [rsp+2E0h+var_290], ecx
0x18000c410  mov     rcx, rax; hFindFile
0x18000c413  call    cs:__imp_FindClose
0x18000c419  test    [rsp+2E0h+var_290], 1115h
0x18000c421  jz      short loc_18000C49A
0x18000c423  mov     esi, 80004005h
0x18000c428  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c42f  mov     ecx, esi; int
0x18000c431  lea     rdx, aBadLogfileAttr; "bad logfile attributes"
0x18000c438  mov     r9d, 8ECh; unsigned int
0x18000c43e  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c443  lea     rcx, aErrorBadLogfil; "ERROR: bad logfile attributes\r\n"
0x18000c44a  call    cs:__imp_OutputDebugStringA
0x18000c450  mov     rcx, [rbx+308h]
0x18000c457  test    rcx, rcx
0x18000c45a  jz      short loc_18000C493
0x18000c45c  mov     rax, [rcx]
0x18000c45f  lea     rdx, [rsp+2E0h+var_290]
0x18000c464  mov     [rsp+2E0h+lpOverlapped], r14
0x18000c469  mov     edi, 4
0x18000c46e  mov     [rsp+2E0h+hTemplateFile], rdx
0x18000c473  xor     r9d, r9d
0x18000c476  mov     [rsp+2E0h+dwFlagsAndAttributes], edi
0x18000c47a  mov     r8d, edi
0x18000c47d  mov     rax, [rax+18h]
0x18000c481  mov     edx, 1001h
0x18000c486  mov     [rsp+2E0h+dwCreationDisposition], 0C000101Eh
0x18000c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c493  mov     eax, esi
0x18000c495  jmp     loc_18000C694
0x18000c49a  xor     r9d, r9d; lpSecurityAttributes
0x18000c49d  mov     [rsp+2E0h+hTemplateFile], r14; hTemplateFile
0x18000c4a2  mov     [rsp+2E0h+dwFlagsAndAttributes], 0B0000080h; dwFlagsAndAttributes
0x18000c4aa  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c4af  mov     rcx, rdi; lpFileName
0x18000c4b2  mov     dword ptr [rbx+18h], 5
0x18000c4b9  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c4c1  lea     r8d, [r9+1]; dwShareMode
0x18000c4c5  call    cs:__imp_CreateFileW
0x18000c4cb  mov     [rbx+98h], rax
0x18000c4d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c4d6  jnz     short loc_18000C4F4
0x18000c4d8  call    cs:__imp_GetLastError
0x18000c4de  mov     r9d, 920h
0x18000c4e4  lea     rdx, aCreatefile; "CreateFile"
0x18000c4eb  mov     ebx, eax
0x18000c4ed  mov     ecx, eax
0x18000c4ef  jmp     loc_18000C3A7
0x18000c4f4  test    [rsp+2E0h+var_290], 800h
0x18000c4fc  mov     edi, 4
0x18000c501  jz      loc_18000C60E
0x18000c507  lea     rcx, OutputString; "\r\n"
0x18000c50e  call    cs:__imp_OutputDebugStringA
0x18000c514  lea     rcx, aDecompressingD_0; "decompressing DTC log file\r\n"
0x18000c51b  call    cs:__imp_OutputDebugStringA
0x18000c521  mov     rcx, [rbx+98h]; hDevice
0x18000c528  lea     rax, [rbp+1E0h+BytesReturned]
0x18000c52f  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x18000c534  lea     r9d, [rdi-2]; nInBufferSize
0x18000c538  mov     [rsp+2E0h+hTemplateFile], rax; lpBytesReturned
0x18000c53d  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x18000c542  mov     [rsp+2E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18000c547  mov     edx, 9C040h; dwIoControlCode
0x18000c54c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r14; lpOutBuffer
0x18000c551  mov     [rsp+2E0h+InBuffer], r14w
0x18000c557  mov     [rbp+1E0h+BytesReturned], r14d
0x18000c55e  call    cs:__imp_DeviceIoControl
0x18000c564  test    eax, eax
0x18000c566  jnz     short loc_18000C5D4
0x18000c568  call    cs:__imp_GetLastError
0x18000c56e  mov     r9d, 940h; unsigned int
0x18000c574  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c57b  lea     rdx, aDeviceiocontro_0; "DeviceIoControl"
0x18000c582  mov     [rsp+2E0h+var_288], eax
0x18000c586  mov     ecx, eax; int
0x18000c588  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c58d  mov     rcx, [rbx+308h]
0x18000c594  test    rcx, rcx
0x18000c597  jz      short loc_18000C5CB
0x18000c599  mov     rax, [rcx]
0x18000c59c  lea     rdx, [rsp+2E0h+var_288]
0x18000c5a1  mov     [rsp+2E0h+lpOverlapped], r14
0x18000c5a6  xor     r9d, r9d
0x18000c5a9  mov     [rsp+2E0h+hTemplateFile], rdx
0x18000c5ae  mov     r8d, edi
0x18000c5b1  mov     [rsp+2E0h+dwFlagsAndAttributes], edi
0x18000c5b5  mov     edx, 1001h
0x18000c5ba  mov     rax, [rax+18h]
0x18000c5be  mov     [rsp+2E0h+dwCreationDisposition], 0C000101Ch
0x18000c5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5cb  mov     eax, [rsp+2E0h+var_288]
0x18000c5cf  jmp     loc_18000C694
0x18000c5d4  mov     rcx, [rbx+308h]
0x18000c5db  test    rcx, rcx
0x18000c5de  jz      short loc_18000C60E
0x18000c5e0  mov     rax, [rcx]
0x18000c5e3  xor     r9d, r9d
0x18000c5e6  mov     [rsp+2E0h+lpOverlapped], r14
0x18000c5eb  mov     r8d, edi
0x18000c5ee  mov     [rsp+2E0h+hTemplateFile], r14
0x18000c5f3  mov     edx, 1003h
0x18000c5f8  mov     [rsp+2E0h+dwFlagsAndAttributes], r14d
0x18000c5fd  mov     rax, [rax+18h]
0x18000c601  mov     [rsp+2E0h+dwCreationDisposition], 4000101Dh
0x18000c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60e  mov     rcx, [rbx+98h]; hFile
0x18000c615  xor     edx, edx; lpFileSizeHigh
0x18000c617  call    cs:__imp_GetFileSize
0x18000c61d  cmp     eax, 0FFFFFFFFh
0x18000c620  jnz     short loc_18000C63A
0x18000c622  call    cs:__imp_GetLastError
0x18000c628  mov     r9d, 97Ah
0x18000c62e  lea     rdx, aGetfilesize; "GetFileSize"
0x18000c635  jmp     loc_18000C4EB
0x18000c63a  shr     eax, 0Dh
0x18000c63d  mov     [rbx+24h], eax
0x18000c640  test    rsi, rsi
0x18000c643  jz      short loc_18000C647
0x18000c645  mov     [rsi], eax
0x18000c647  mov     eax, [rbx+24h]
0x18000c64a  xor     r9d, r9d; dwMaximumSizeHigh
0x18000c64d  mov     rcx, [rbx+98h]; hFile
0x18000c654  mov     r8d, edi; flProtect
0x18000c657  shl     eax, 0Dh
0x18000c65a  xor     edx, edx; lpFileMappingAttributes
0x18000c65c  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], r14; lpName
0x18000c661  mov     [rbx+20h], eax
0x18000c664  mov     [rsp+2E0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18000c668  call    cs:__imp_CreateFileMappingW
0x18000c66e  mov     [rbx+0A0h], rax
0x18000c675  test    rax, rax
0x18000c678  jnz     short loc_18000C692
0x18000c67a  call    cs:__imp_GetLastError
0x18000c680  mov     r9d, 992h
0x18000c686  lea     rdx, aCreatefilemapp_0; "CreateFileMapping"
0x18000c68d  jmp     loc_18000C4EB
0x18000c692  xor     eax, eax
0x18000c694  mov     rcx, [rbp+1E0h+var_28]
0x18000c69b  xor     rcx, rsp; StackCookie
0x18000c69e  call    __security_check_cookie
0x18000c6a3  add     rsp, 2C0h
0x18000c6aa  pop     r14
0x18000c6ac  pop     rdi
0x18000c6ad  pop     rsi
0x18000c6ae  pop     rbx
0x18000c6af  pop     rbp
0x18000c6b0  retn
```
