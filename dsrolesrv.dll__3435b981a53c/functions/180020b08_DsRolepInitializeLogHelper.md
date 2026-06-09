# DsRolepInitializeLogHelper

- ea: `0x180020b08`
- end: `0x180020db4`
- name: `DsRolepInitializeLogHelper`
- size: `684`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180003ff0`
- `0x180005400`
- `0x1800058a0`
- `0x180005e40`
- `0x1800065a0`
- `0x180006bf0`
- `0x180006c30`
- `0x180020b08`

## callees

- `0x180008ea4`
- `0x180020b08`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020c8e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020c8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020bd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020c73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020bd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180020c73`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180020c27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180020c27`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180020d09`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180020d09`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020b68`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020d2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020b68`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180020d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020d73`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180020d8c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180020d8c`
- `ntdll!RtlLeaveCriticalSection` at `0x180020cc5`
- `ntdll!RtlLeaveCriticalSection` at `0x180020da1`
- `ntdll!RtlLeaveCriticalSection` at `0x180020cc5`
- `ntdll!RtlLeaveCriticalSection` at `0x180020da1`
- `ntdll!RtlEnterCriticalSection` at `0x180020b58`
- `ntdll!RtlEnterCriticalSection` at `0x180020b58`

## pseudocode

```c
__int64 __fastcall DsRolepInitializeLogHelper(unsigned int a1)
{
  size_t v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rax
  DWORD LastError; // eax
  DWORD v7; // ebx
  size_t v8; // rdx
  _WORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v10; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszDest[264]; // [rsp+260h] [rbp+160h] BYREF

  v10 = -257;
  if ( a1 > 2 )
    return 31;
  RtlEnterCriticalSection(&LogFileCriticalSection);
  if ( !GetWindowsDirectoryW(Buffer, 0x105u) )
    goto LABEL_13;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  StringCchCatNW(Buffer, v3, L"\\debug\\DCPROMO.LOG", 260 - v5);
  DsRolepLogFile = CreateFileW(Buffer, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
  if ( DsRolepLogFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    DsRolepLogFile = 0;
    goto LABEL_14;
  }
  if ( GetLastError() != 183 )
  {
    NumberOfBytesWritten = 0;
    if ( WriteFile(DsRolepLogFile, &v10, 2u, &NumberOfBytesWritten, 0) )
      goto LABEL_10;
    goto LABEL_13;
  }
  v9[0] = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(DsRolepLogFile, v9, 2u, &NumberOfBytesRead, 0) )
    goto LABEL_13;
  if ( v10 == v9[0] )
  {
LABEL_10:
    v7 = 0;
    if ( DsRolepLogFile )
    {
      CloseHandle(DsRolepLogFile);
      DsRolepLogFile = 0;
    }
    DsRolepLogFile = CreateFileW(Buffer, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
    if ( SetFilePointer(DsRolepLogFile, 0, 0, 2u) != -1 )
      goto LABEL_17;
    goto LABEL_13;
  }
  if ( !GetWindowsDirectoryW(pszDest, 0x105u) )
    goto LABEL_13;
  do
    ++v4;
  while ( pszDest[v4] );
  StringCchCatNW(pszDest, v8, L"\\debug\\DCPROMO.BAK", 260 - v4);
  if ( DsRolepLogFile )
  {
    CloseHandle(DsRolepLogFile);
    DsRolepLogFile = 0;
  }
  if ( !MoveFileW(Buffer, pszDest) )
  {
LABEL_13:
    LastError = GetLastError();
LABEL_14:
    v7 = LastError;
    if ( LastError )
    {
      if ( DsRolepLogFile )
      {
        CloseHandle(DsRolepLogFile);
        DsRolepLogFile = 0;
      }
    }
LABEL_17:
    RtlLeaveCriticalSection(&LogFileCriticalSection);
    return v7;
  }
  RtlLeaveCriticalSection(&LogFileCriticalSection);
  return DsRolepInitializeLogHelper(a1 + 1);
}

```

## disassembly

```asm
0x180020b08  mov     [rsp-8+arg_8], rbx
0x180020b0d  mov     [rsp-8+arg_10], rsi
0x180020b12  push    rbp
0x180020b13  push    rdi
0x180020b14  push    r14
0x180020b16  lea     rbp, [rsp-380h]
0x180020b1e  sub     rsp, 480h
0x180020b25  mov     rax, cs:__security_cookie
0x180020b2c  xor     rax, rsp
0x180020b2f  mov     [rbp+390h+var_20], rax
0x180020b36  mov     eax, 0FEFFh
0x180020b3b  mov     edi, ecx
0x180020b3d  mov     [rsp+490h+var_44C], ax
0x180020b42  cmp     ecx, 2
0x180020b45  jbe     short loc_180020B51
0x180020b47  mov     eax, 1Fh
0x180020b4c  jmp     loc_180020CCD
0x180020b51  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020b58  call    cs:__imp_RtlEnterCriticalSection
0x180020b5e  mov     edx, 105h; uSize
0x180020b63  lea     rcx, [rsp+490h+Buffer]; lpBuffer
0x180020b68  call    cs:__imp_GetWindowsDirectoryW
0x180020b6e  xor     r14d, r14d
0x180020b71  test    eax, eax
0x180020b73  jz      loc_180020C99
0x180020b79  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020b7d  lea     rcx, [rsp+490h+Buffer]
0x180020b82  mov     rax, rbx
0x180020b85  inc     rax
0x180020b88  cmp     [rcx+rax*2], r14w
0x180020b8d  jnz     short loc_180020B85
0x180020b8f  mov     esi, 104h
0x180020b94  lea     r8, aDebugDcpromoLo; "\\debug\\DCPROMO.LOG"
0x180020b9b  mov     r9d, esi
0x180020b9e  lea     rcx, [rsp+490h+Buffer]; pszDest
0x180020ba3  sub     r9, rax; cchToAppend
0x180020ba6  call    StringCchCatNW
0x180020bab  xor     r9d, r9d; lpSecurityAttributes
0x180020bae  mov     [rsp+490h+hTemplateFile], r14; hTemplateFile
0x180020bb3  mov     [rsp+490h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180020bbb  lea     rcx, [rsp+490h+Buffer]; lpFileName
0x180020bc0  mov     edx, 0C0000000h; dwDesiredAccess
0x180020bc5  mov     [rsp+490h+dwCreationDisposition], 4; dwCreationDisposition
0x180020bcd  lea     r8d, [r9+3]; dwShareMode
0x180020bd1  call    cs:__imp_CreateFileW
0x180020bd7  mov     cs:DsRolepLogFile, rax
0x180020bde  cmp     rax, rbx
0x180020be1  jnz     short loc_180020BF5
0x180020be3  call    cs:__imp_GetLastError
0x180020be9  mov     cs:DsRolepLogFile, r14
0x180020bf0  jmp     loc_180020C9F
0x180020bf5  call    cs:__imp_GetLastError
0x180020bfb  mov     rcx, cs:DsRolepLogFile; hFile
0x180020c02  mov     r8d, 2; nNumberOfBytesToRead
0x180020c08  mov     qword ptr [rsp+490h+dwCreationDisposition], r14; lpOverlapped
0x180020c0d  cmp     eax, 0B7h
0x180020c12  jz      loc_180020CF4
0x180020c18  lea     r9, [rsp+490h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180020c1d  mov     [rsp+490h+NumberOfBytesWritten], r14d
0x180020c22  lea     rdx, [rsp+490h+var_44C]; lpBuffer
0x180020c27  call    cs:__imp_WriteFile
0x180020c2d  test    eax, eax
0x180020c2f  jz      short loc_180020C99
0x180020c31  mov     rcx, cs:DsRolepLogFile; hObject
0x180020c38  mov     ebx, r14d
0x180020c3b  test    rcx, rcx
0x180020c3e  jz      short loc_180020C4D
0x180020c40  call    cs:__imp_CloseHandle
0x180020c46  mov     cs:DsRolepLogFile, r14
0x180020c4d  xor     r9d, r9d; lpSecurityAttributes
0x180020c50  mov     [rsp+490h+hTemplateFile], r14; hTemplateFile
0x180020c55  mov     [rsp+490h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180020c5d  lea     rcx, [rsp+490h+Buffer]; lpFileName
0x180020c62  mov     edx, 40000000h; dwDesiredAccess
0x180020c67  mov     [rsp+490h+dwCreationDisposition], 4; dwCreationDisposition
0x180020c6f  lea     r8d, [r9+3]; dwShareMode
0x180020c73  call    cs:__imp_CreateFileW
0x180020c79  mov     r9d, 2; dwMoveMethod
0x180020c7f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180020c82  mov     rcx, rax; hFile
0x180020c85  mov     cs:DsRolepLogFile, rax
0x180020c8c  xor     edx, edx; lDistanceToMove
0x180020c8e  call    cs:__imp_SetFilePointer
0x180020c94  cmp     eax, 0FFFFFFFFh
0x180020c97  jnz     short loc_180020CBE
0x180020c99  call    cs:__imp_GetLastError
0x180020c9f  mov     ebx, eax
0x180020ca1  test    eax, eax
0x180020ca3  jz      short loc_180020CBE
0x180020ca5  mov     rcx, cs:DsRolepLogFile; hObject
0x180020cac  test    rcx, rcx
0x180020caf  jz      short loc_180020CBE
0x180020cb1  call    cs:__imp_CloseHandle
0x180020cb7  mov     cs:DsRolepLogFile, r14
0x180020cbe  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020cc5  call    cs:__imp_RtlLeaveCriticalSection
0x180020ccb  mov     eax, ebx
0x180020ccd  mov     rcx, [rbp+390h+var_20]
0x180020cd4  xor     rcx, rsp; StackCookie
0x180020cd7  call    __security_check_cookie
0x180020cdc  lea     r11, [rsp+490h+var_10]
0x180020ce4  mov     rbx, [r11+28h]
0x180020ce8  mov     rsi, [r11+30h]
0x180020cec  mov     rsp, r11
0x180020cef  pop     r14
0x180020cf1  pop     rdi
0x180020cf2  pop     rbp
0x180020cf3  retn
0x180020cf4  lea     r9, [rsp+490h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180020cf9  mov     [rsp+490h+var_450], r14w
0x180020cff  lea     rdx, [rsp+490h+var_450]; lpBuffer
0x180020d04  mov     [rsp+490h+NumberOfBytesRead], r14d
0x180020d09  call    cs:__imp_ReadFile
0x180020d0f  test    eax, eax
0x180020d11  jz      short loc_180020C99
0x180020d13  movzx   eax, [rsp+490h+var_450]
0x180020d18  cmp     [rsp+490h+var_44C], ax
0x180020d1d  jz      loc_180020C31
0x180020d23  mov     edx, 105h; uSize
0x180020d28  lea     rcx, [rbp+390h+pszDest]; lpBuffer
0x180020d2f  call    cs:__imp_GetWindowsDirectoryW
0x180020d35  test    eax, eax
0x180020d37  jz      loc_180020C99
0x180020d3d  lea     rax, [rbp+390h+pszDest]
0x180020d44  inc     rbx
0x180020d47  cmp     [rax+rbx*2], r14w
0x180020d4c  jnz     short loc_180020D44
0x180020d4e  sub     rsi, rbx
0x180020d51  lea     r8, aDebugDcpromoBa; "\\debug\\DCPROMO.BAK"
0x180020d58  mov     r9, rsi; cchToAppend
0x180020d5b  lea     rcx, [rbp+390h+pszDest]; pszDest
0x180020d62  call    StringCchCatNW
0x180020d67  mov     rcx, cs:DsRolepLogFile; hObject
0x180020d6e  test    rcx, rcx
0x180020d71  jz      short loc_180020D80
0x180020d73  call    cs:__imp_CloseHandle
0x180020d79  mov     cs:DsRolepLogFile, r14
0x180020d80  lea     rdx, [rbp+390h+pszDest]; lpNewFileName
0x180020d87  lea     rcx, [rsp+490h+Buffer]; lpExistingFileName
0x180020d8c  call    cs:__imp_MoveFileW
0x180020d92  test    eax, eax
0x180020d94  jz      loc_180020C99
0x180020d9a  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020da1  call    cs:__imp_RtlLeaveCriticalSection
0x180020da7  lea     ecx, [rdi+1]
0x180020daa  call    DsRolepInitializeLogHelper
0x180020daf  jmp     loc_180020CCD
```
