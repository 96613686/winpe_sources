# CDplAccount::DeleteRecoveryFile(ushort const *)

- ea: `0x1800a1d74`
- end: `0x1800a2171`
- name: `?DeleteRecoveryFile@CDplAccount@@AEAAJPEBG@Z`
- size: `1021`
- prototype: `__int64 __fastcall(CDplAccount *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800a5bdc`
- `0x1800a7d3c`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800a1d74`
- `0x1800dddf0`
- `0x1800ddeb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a207c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a20fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a207c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a20fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a20e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a20e7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a20d8`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a20d8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a204f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a204f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a1f26`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a1f26`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a20f0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a20f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1e37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1e84`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1ece`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1e37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1e84`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a1ece`
- `bcrypt!BCryptGenRandom` at `0x1800a1f88`
- `bcrypt!BCryptGenRandom` at `0x1800a1f88`
- `ntdll!RtlNtStatusToDosError` at `0x1800a20a3`
- `ntdll!RtlNtStatusToDosError` at `0x1800a20a3`

## pseudocode

```c
__int64 __fastcall CDplAccount::DeleteRecoveryFile(CDplAccount *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int v6; // eax
  union _LARGE_INTEGER v7; // rsi
  int v8; // ecx
  int v9; // edi
  DWORD v10; // r8d
  DWORD v11; // ecx
  signed int v12; // eax
  int v13; // eax
  signed int v14; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR pbBuffer[4096]; // [rsp+50h] [rbp-B0h] BYREF

  FileSize.QuadPart = 0;
  NumberOfBytesWritten = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 36, 99);
  if ( !a2 )
  {
    v3 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 36, 101);
    goto LABEL_49;
  }
  FileW = CreateFileW(a2, 0xC0010000, 0, 0, 3u, 0x4000080u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError == 2 )
    goto LABEL_43;
  if ( LastError != 32 )
    goto LABEL_11;
  FileW = CreateFileW(a2, 0xC0010000, 7u, 0, 3u, 0x4000080u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
LABEL_14:
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      for ( v7.QuadPart = 0; ; v7.QuadPart += NumberOfBytesWritten )
      {
        if ( v7.QuadPart >= FileSize.QuadPart )
        {
          FlushFileBuffers(FileW);
          goto LABEL_42;
        }
        v9 = BCryptGenRandom(0, pbBuffer, 0x1000u, 2u);
        if ( v9 )
          break;
        if ( FileSize.QuadPart - v7.QuadPart < 0x1000uLL )
        {
          fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 218);
          v11 = FileSize.LowPart - v7.LowPart;
          if ( FileSize.QuadPart - v7.QuadPart > 0xFFFFFFFFuLL )
            v11 = -1;
          NumberOfBytesWritten = v11;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      FileSize.QuadPart - v7.QuadPart > 0xFFFFFFFFuLL ? 0x80070216 : 0,
                      36,
                      218) < 0 )
            goto LABEL_42;
          v10 = NumberOfBytesWritten;
        }
        else
        {
          v10 = 4096;
          NumberOfBytesWritten = 4096;
        }
        if ( !WriteFile(FileW, pbBuffer, v10, &NumberOfBytesWritten, 0) )
        {
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 36, 223);
          goto LABEL_42;
        }
        if ( !NumberOfBytesWritten )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024865, 36, 228);
          goto LABEL_42;
        }
      }
      v13 = 0;
      if ( v9 < 0 )
      {
        v13 = RtlNtStatusToDosError(v9);
        if ( !v13 || v13 == 317 )
        {
          v13 = v9 | 0x10000000;
        }
        else if ( v13 > 0 )
        {
          v13 = (unsigned __int16)v13 | 0x80070000;
        }
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 36, 208);
    }
    else
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 36, 192);
    }
LABEL_42:
    CloseHandle(FileW);
    goto LABEL_43;
  }
  LastError = GetLastError();
  if ( LastError == 2 )
    goto LABEL_43;
  if ( LastError != 32 )
  {
LABEL_11:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, LastError, 36, 183);
    goto LABEL_43;
  }
  FileW = CreateFileW(a2, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_14;
  LastError = GetLastError();
  if ( LastError != 2 )
    goto LABEL_11;
LABEL_43:
  if ( DeleteFileW(a2) )
  {
    v3 = 0;
  }
  else
  {
    v14 = GetLastError();
    v3 = v14;
    if ( v14 > 0 )
      v3 = (unsigned __int16)v14 | 0x80070000;
    if ( v3 == -2147024894 )
      v3 = 0;
  }
LABEL_49:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v3,
    36,
    8);
  return v3;
}

```

## disassembly

```asm
0x1800a1d74  push    rbp
0x1800a1d76  push    rbx
0x1800a1d77  push    rsi
0x1800a1d78  push    rdi
0x1800a1d79  push    r12
0x1800a1d7b  push    r14
0x1800a1d7d  lea     rbp, [rsp-0F68h]
0x1800a1d85  mov     eax, 1068h
0x1800a1d8a  call    _alloca_probe
0x1800a1d8f  sub     rsp, rax
0x1800a1d92  mov     rax, cs:__security_cookie
0x1800a1d99  xor     rax, rsp
0x1800a1d9c  mov     [rbp+0F90h+var_40], rax
0x1800a1da3  mov     r14, rdx
0x1800a1da6  mov     qword ptr [rsp+1090h+FileSize], 0
0x1800a1daf  mov     r12d, 24h ; '$'
0x1800a1db5  mov     [rsp+1090h+NumberOfBytesWritten], 0
0x1800a1dbd  mov     r9d, r12d
0x1800a1dc0  mov     [rsp+1090h+dwCreationDisposition], 0C63h
0x1800a1dc8  lea     r8, sourceString
0x1800a1dcf  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800a1dd6  call    fnEfsLogTrace1Strings
0x1800a1ddb  test    r14, r14
0x1800a1dde  jnz     short loc_1800A1E0E
0x1800a1de0  mov     rcx, cs:g_hPublisher
0x1800a1de7  lea     rdx, EFS_TRACE_ERROR
0x1800a1dee  mov     r9d, r12d
0x1800a1df1  mov     [rsp+1090h+dwCreationDisposition], 0C65h
0x1800a1df9  mov     r8d, 80070057h
0x1800a1dff  mov     ebx, 80070057h
0x1800a1e04  call    fnEfsLogTrace1
0x1800a1e09  jmp     loc_1800A211E
0x1800a1e0e  mov     [rsp+1090h+hTemplateFile], 0; hTemplateFile
0x1800a1e17  mov     esi, 4000080h
0x1800a1e1c  mov     edi, 3
0x1800a1e21  mov     [rsp+1090h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1800a1e25  xor     r9d, r9d; lpSecurityAttributes
0x1800a1e28  mov     [rsp+1090h+dwCreationDisposition], edi; dwCreationDisposition
0x1800a1e2c  xor     r8d, r8d; dwShareMode
0x1800a1e2f  mov     edx, 0C0010000h; dwDesiredAccess
0x1800a1e34  mov     rcx, r14; lpFileName
0x1800a1e37  call    cs:__imp_CreateFileW
0x1800a1e3d  mov     rbx, rax
0x1800a1e40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1e44  jnz     loc_1800A1F1E
0x1800a1e4a  call    cs:__imp_GetLastError
0x1800a1e50  cmp     eax, 2
0x1800a1e53  jz      loc_1800A20ED
0x1800a1e59  cmp     eax, 20h ; ' '
0x1800a1e5c  jnz     loc_1800A1EEC
0x1800a1e62  mov     [rsp+1090h+hTemplateFile], 0; hTemplateFile
0x1800a1e6b  xor     r9d, r9d; lpSecurityAttributes
0x1800a1e6e  mov     [rsp+1090h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1800a1e72  mov     edx, 0C0010000h; dwDesiredAccess
0x1800a1e77  lea     esi, [rdi+4]
0x1800a1e7a  mov     [rsp+1090h+dwCreationDisposition], edi; dwCreationDisposition
0x1800a1e7e  mov     r8d, esi; dwShareMode
0x1800a1e81  mov     rcx, r14; lpFileName
0x1800a1e84  call    cs:__imp_CreateFileW
0x1800a1e8a  mov     rbx, rax
0x1800a1e8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1e91  jnz     loc_1800A1F1E
0x1800a1e97  call    cs:__imp_GetLastError
0x1800a1e9d  cmp     eax, 2
0x1800a1ea0  jz      loc_1800A20ED
0x1800a1ea6  cmp     eax, 20h ; ' '
0x1800a1ea9  jnz     short loc_1800A1EEC
0x1800a1eab  mov     [rsp+1090h+hTemplateFile], 0; hTemplateFile
0x1800a1eb4  xor     r9d, r9d; lpSecurityAttributes
0x1800a1eb7  mov     [rsp+1090h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a1ebf  mov     r8d, esi; dwShareMode
0x1800a1ec2  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a1ec7  mov     [rsp+1090h+dwCreationDisposition], edi; dwCreationDisposition
0x1800a1ecb  mov     rcx, r14; lpFileName
0x1800a1ece  call    cs:__imp_CreateFileW
0x1800a1ed4  mov     rbx, rax
0x1800a1ed7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1edb  jnz     short loc_1800A1F1E
0x1800a1edd  call    cs:__imp_GetLastError
0x1800a1ee3  cmp     eax, 2
0x1800a1ee6  jz      loc_1800A20ED
0x1800a1eec  test    eax, eax
0x1800a1eee  jle     short loc_1800A1EF8
0x1800a1ef0  movzx   eax, ax
0x1800a1ef3  or      eax, 80070000h
0x1800a1ef8  mov     rcx, cs:g_hPublisher
0x1800a1eff  lea     rdx, EFS_TRACE_ERROR
0x1800a1f06  mov     r9d, r12d
0x1800a1f09  mov     [rsp+1090h+dwCreationDisposition], 0CB7h
0x1800a1f11  mov     r8d, eax
0x1800a1f14  call    fnEfsLogTrace1
0x1800a1f19  jmp     loc_1800A20ED
0x1800a1f1e  lea     rdx, [rsp+1090h+FileSize]; lpFileSize
0x1800a1f23  mov     rcx, rbx; hFile
0x1800a1f26  call    cs:__imp_GetFileSizeEx
0x1800a1f2c  test    eax, eax
0x1800a1f2e  jnz     short loc_1800A1F68
0x1800a1f30  call    cs:__imp_GetLastError
0x1800a1f36  test    eax, eax
0x1800a1f38  jle     short loc_1800A1F42
0x1800a1f3a  movzx   eax, ax
0x1800a1f3d  or      eax, 80070000h
0x1800a1f42  mov     [rsp+1090h+dwCreationDisposition], 0CC0h
0x1800a1f4a  mov     r8d, eax
0x1800a1f4d  mov     rcx, cs:g_hPublisher
0x1800a1f54  lea     rdx, EFS_TRACE_ERROR
0x1800a1f5b  mov     r9d, r12d
0x1800a1f5e  call    fnEfsLogTrace1
0x1800a1f63  jmp     loc_1800A20DE
0x1800a1f68  xor     esi, esi
0x1800a1f6a  cmp     rsi, qword ptr [rsp+1090h+FileSize]
0x1800a1f6f  jge     loc_1800A20D5
0x1800a1f75  mov     r9d, 2; dwFlags
0x1800a1f7b  lea     rdx, [rsp+1090h+pbBuffer]; pbBuffer
0x1800a1f80  mov     r8d, 1000h; cbBuffer
0x1800a1f86  xor     ecx, ecx; hAlgorithm
0x1800a1f88  call    cs:__imp_BCryptGenRandom
0x1800a1f8e  mov     edi, eax
0x1800a1f90  test    eax, eax
0x1800a1f92  jnz     loc_1800A209B
0x1800a1f98  mov     rax, qword ptr [rsp+1090h+FileSize]
0x1800a1f9d  sub     rax, rsi
0x1800a1fa0  cmp     rax, 1000h
0x1800a1fa6  jb      short loc_1800A1FB8
0x1800a1fa8  mov     r8d, 1000h
0x1800a1fae  mov     [rsp+1090h+NumberOfBytesWritten], r8d
0x1800a1fb3  jmp     loc_1800A2039
0x1800a1fb8  mov     r9d, r12d
0x1800a1fbb  mov     [rsp+1090h+dwCreationDisposition], 0CDAh
0x1800a1fc3  lea     r8, sourceString
0x1800a1fca  lea     rdx, EFS_TRACE_START_EVENT
0x1800a1fd1  call    fnEfsLogTrace1Strings
0x1800a1fd6  mov     rax, qword ptr [rsp+1090h+FileSize]
0x1800a1fdb  mov     edi, 0FFFFFFFFh
0x1800a1fe0  sub     rax, rsi
0x1800a1fe3  mov     ecx, eax
0x1800a1fe5  cmp     rax, rdi
0x1800a1fe8  jbe     short loc_1800A1FEC
0x1800a1fea  mov     ecx, edi
0x1800a1fec  cmp     rdi, rax
0x1800a1fef  mov     [rsp+1090h+NumberOfBytesWritten], ecx
0x1800a1ff3  mov     rcx, cs:g_hPublisher
0x1800a1ffa  lea     r9, sourceString
0x1800a2001  sbb     eax, eax
0x1800a2003  mov     dword ptr [rsp+1090h+hTemplateFile], 0CDAh
0x1800a200b  and     eax, 80070216h
0x1800a2010  mov     [rsp+1090h+dwFlagsAndAttributes], r12d
0x1800a2015  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a201c  mov     [rsp+1090h+dwCreationDisposition], eax
0x1800a2020  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a2027  call    fnEfsLogTrace1String1Dword
0x1800a202c  test    eax, eax
0x1800a202e  js      loc_1800A20DE
0x1800a2034  mov     r8d, [rsp+1090h+NumberOfBytesWritten]; nNumberOfBytesToWrite
0x1800a2039  lea     r9, [rsp+1090h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a203e  mov     qword ptr [rsp+1090h+dwCreationDisposition], 0; lpOverlapped
0x1800a2047  lea     rdx, [rsp+1090h+pbBuffer]; lpBuffer
0x1800a204c  mov     rcx, rbx; hFile
0x1800a204f  call    cs:__imp_WriteFile
0x1800a2055  test    eax, eax
0x1800a2057  jz      short loc_1800A207C
0x1800a2059  mov     eax, [rsp+1090h+NumberOfBytesWritten]
0x1800a205d  test    eax, eax
0x1800a205f  jz      short loc_1800A2069
0x1800a2061  add     rsi, rax
0x1800a2064  jmp     loc_1800A1F6A
0x1800a2069  mov     [rsp+1090h+dwCreationDisposition], 0CE4h
0x1800a2071  mov     r8d, 8007001Fh
0x1800a2077  jmp     loc_1800A1F4D
0x1800a207c  call    cs:__imp_GetLastError
0x1800a2082  test    eax, eax
0x1800a2084  jle     short loc_1800A208E
0x1800a2086  movzx   eax, ax
0x1800a2089  or      eax, 80070000h
0x1800a208e  mov     [rsp+1090h+dwCreationDisposition], 0CDFh
0x1800a2096  jmp     loc_1800A1F4A
0x1800a209b  xor     eax, eax
0x1800a209d  test    edi, edi
0x1800a209f  jns     short loc_1800A20C8
0x1800a20a1  mov     ecx, edi; Status
0x1800a20a3  call    cs:__imp_RtlNtStatusToDosError
0x1800a20a9  test    eax, eax
0x1800a20ab  jz      short loc_1800A20C2
0x1800a20ad  cmp     eax, 13Dh
0x1800a20b2  jz      short loc_1800A20C2
0x1800a20b4  test    eax, eax
0x1800a20b6  jle     short loc_1800A20C8
0x1800a20b8  movzx   eax, ax
0x1800a20bb  or      eax, 80070000h
0x1800a20c0  jmp     short loc_1800A20C8
0x1800a20c2  mov     eax, edi
0x1800a20c4  bts     eax, 1Ch
0x1800a20c8  mov     [rsp+1090h+dwCreationDisposition], 0CD0h
0x1800a20d0  jmp     loc_1800A1F4A
0x1800a20d5  mov     rcx, rbx; hFile
0x1800a20d8  call    cs:__imp_FlushFileBuffers
0x1800a20de  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a20e2  jz      short loc_1800A20ED
0x1800a20e4  mov     rcx, rbx; hObject
0x1800a20e7  call    cs:__imp_CloseHandle
0x1800a20ed  mov     rcx, r14; lpFileName
0x1800a20f0  call    cs:__imp_DeleteFileW
0x1800a20f6  test    eax, eax
0x1800a20f8  jz      short loc_1800A20FE
0x1800a20fa  xor     ebx, ebx
0x1800a20fc  jmp     short loc_1800A211E
0x1800a20fe  call    cs:__imp_GetLastError
0x1800a2104  mov     ebx, eax
0x1800a2106  test    eax, eax
0x1800a2108  jle     short loc_1800A2113
0x1800a210a  movzx   ebx, ax
0x1800a210d  or      ebx, 80070000h
0x1800a2113  xor     ecx, ecx
0x1800a2115  cmp     ebx, 80070002h
0x1800a211b  cmovz   ebx, ecx
0x1800a211e  mov     rcx, cs:g_hPublisher
0x1800a2125  lea     r9, sourceString
0x1800a212c  mov     dword ptr [rsp+1090h+hTemplateFile], 0D08h
0x1800a2134  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800a213b  mov     [rsp+1090h+dwFlagsAndAttributes], r12d
0x1800a2140  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800a2147  mov     [rsp+1090h+dwCreationDisposition], ebx
0x1800a214b  call    fnEfsLogTrace1String1Dword
0x1800a2150  mov     eax, ebx
0x1800a2152  mov     rcx, [rbp+0F90h+var_40]
0x1800a2159  xor     rcx, rsp; StackCookie
0x1800a215c  call    __security_check_cookie
0x1800a2161  add     rsp, 1068h
0x1800a2168  pop     r14
0x1800a216a  pop     r12
0x1800a216c  pop     rdi
0x1800a216d  pop     rsi
0x1800a216e  pop     rbx
0x1800a216f  pop     rbp
0x1800a2170  retn
```
