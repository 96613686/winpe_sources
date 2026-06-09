# SetPreferredMasterKeyGuid(void *,ushort const *,_GUID *)

- ea: `0x18002dd6c`
- end: `0x18002deef`
- name: `?SetPreferredMasterKeyGuid@@YAHPEAXPEBGPEAU_GUID@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018a20`
- `0x18002b0ec`

## callees

- `0x1800060e0`
- `0x180007f10`
- `0x18001d810`
- `0x18002dd6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dea2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002de36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002de36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ddac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ddac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002decc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002decc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002de67`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002de67`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18002de90`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18002de90`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ddc0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002ddc0`

## string_xrefs

- `0x18002de1f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002deb4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall SetPreferredMasterKeyGuid(void *a1, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int128 v4; // xmm0
  unsigned __int64 v6; // r9
  DWORD v7; // eax
  DWORD v8; // ebx
  HANDLE v10; // rdi
  unsigned int v11; // ebx
  DWORD LastError; // eax
  __int64 v13; // r9
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-40h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-38h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  SystemTime = 0;
  v4 = (__int128)*a3;
  FileTime = 0;
  hFile = 0;
  Buffer = v4;
  NumberOfBytesWritten = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  v6 = FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32) + 77760000000000LL;
  FileTime.dwLowDateTime -= 382894080;
  FileTime.dwHighDateTime = HIDWORD(v6);
  v7 = OpenFileInStorageArea(a1, 0x40000000u, a2, L"Preferred", &hFile);
  v8 = v7;
  if ( v7 )
  {
    DebugTraceError(v7, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 7451);
    SetLastError(v8);
    return 0;
  }
  v10 = hFile;
  v11 = WriteFile(hFile, &Buffer, 0x18u, &NumberOfBytesWritten, 0);
  if ( !v11 )
  {
    LastError = GetLastError();
    v13 = 7463;
LABEL_7:
    DebugTraceError(LastError, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v13);
    goto LABEL_8;
  }
  v11 = FlushFileBuffers(v10);
  if ( !v11 )
  {
    LastError = GetLastError();
    v13 = 7472;
    goto LABEL_7;
  }
LABEL_8:
  CloseHandle(v10);
  return v11;
}

```

## disassembly

```asm
0x18002dd6c  push    rbp
0x18002dd6e  push    rbx
0x18002dd6f  push    rdi
0x18002dd70  mov     rbp, rsp
0x18002dd73  sub     rsp, 70h
0x18002dd77  mov     rax, cs:__security_cookie
0x18002dd7e  xor     rax, rsp
0x18002dd81  mov     [rbp+var_8], rax
0x18002dd85  xor     eax, eax
0x18002dd87  xorps   xmm0, xmm0
0x18002dd8a  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18002dd8e  mov     rdi, rcx
0x18002dd91  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002dd95  movups  xmm0, xmmword ptr [r8]
0x18002dd99  mov     rbx, rdx
0x18002dd9c  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18002dda0  mov     [rbp+hFile], rax
0x18002dda4  movdqu  [rbp+Buffer], xmm0
0x18002dda9  mov     [rbp+NumberOfBytesWritten], eax
0x18002ddac  call    cs:__imp_GetSystemTime
0x18002ddb3  nop     dword ptr [rax+rax+00h]
0x18002ddb8  lea     rdx, [rbp+FileTime]; lpFileTime
0x18002ddbc  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18002ddc0  call    cs:__imp_SystemTimeToFileTime
0x18002ddc7  nop     dword ptr [rax+rax+00h]
0x18002ddcc  mov     edx, [rbp+FileTime.dwLowDateTime]
0x18002ddcf  lea     rax, [rbp+hFile]
0x18002ddd3  mov     r9d, [rbp+FileTime.dwHighDateTime]
0x18002ddd7  mov     rcx, 46B8E92D8000h
0x18002dde1  shl     r9, 20h
0x18002dde5  mov     r8, rbx; unsigned __int16 *
0x18002dde8  add     r9, rcx
0x18002ddeb  mov     [rsp+70h+lpOverlapped], rax; void **
0x18002ddf0  add     r9, rdx
0x18002ddf3  mov     rcx, rdi; void *
0x18002ddf6  mov     [rbp+FileTime.dwLowDateTime], r9d
0x18002ddfa  mov     edx, 40000000h; unsigned int
0x18002ddff  shr     r9, 20h
0x18002de03  mov     [rbp+FileTime.dwHighDateTime], r9d
0x18002de07  lea     r9, aPreferred; "Preferred"
0x18002de0e  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x18002de13  mov     ebx, eax
0x18002de15  test    eax, eax
0x18002de17  jz      short loc_18002DE49
0x18002de19  mov     r9d, 1D1Bh
0x18002de1f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002de26  lea     rdx, aDwlasterror; "dwLastError"
0x18002de2d  mov     ecx, eax
0x18002de2f  call    DebugTraceError
0x18002de34  mov     ecx, ebx; dwErrCode
0x18002de36  call    cs:__imp_SetLastError
0x18002de3d  nop     dword ptr [rax+rax+00h]
0x18002de42  xor     eax, eax
0x18002de44  jmp     loc_18002DEDA
0x18002de49  mov     rdi, [rbp+hFile]
0x18002de4d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002de51  mov     rcx, rdi; hFile
0x18002de54  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18002de5d  mov     r8d, 18h; nNumberOfBytesToWrite
0x18002de63  lea     rdx, [rbp+Buffer]; lpBuffer
0x18002de67  call    cs:__imp_WriteFile
0x18002de6e  nop     dword ptr [rax+rax+00h]
0x18002de73  mov     ebx, eax
0x18002de75  test    eax, eax
0x18002de77  jnz     short loc_18002DE8D
0x18002de79  call    cs:__imp_GetLastError
0x18002de80  nop     dword ptr [rax+rax+00h]
0x18002de85  mov     r9d, 1D27h
0x18002de8b  jmp     short loc_18002DEB4
0x18002de8d  mov     rcx, rdi; hFile
0x18002de90  call    cs:__imp_FlushFileBuffers
0x18002de97  nop     dword ptr [rax+rax+00h]
0x18002de9c  mov     ebx, eax
0x18002de9e  test    eax, eax
0x18002dea0  jnz     short loc_18002DEC9
0x18002dea2  call    cs:__imp_GetLastError
0x18002dea9  nop     dword ptr [rax+rax+00h]
0x18002deae  mov     r9d, 1D30h
0x18002deb4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002debb  mov     ecx, eax
0x18002debd  lea     rdx, aGetlasterror; "GetLastError()"
0x18002dec4  call    DebugTraceError
0x18002dec9  mov     rcx, rdi; hObject
0x18002decc  call    cs:__imp_CloseHandle
0x18002ded3  nop     dword ptr [rax+rax+00h]
0x18002ded8  mov     eax, ebx
0x18002deda  mov     rcx, [rbp+var_8]
0x18002dede  xor     rcx, rsp; StackCookie
0x18002dee1  call    __security_check_cookie
0x18002dee6  add     rsp, 70h
0x18002deea  pop     rdi
0x18002deeb  pop     rbx
0x18002deec  pop     rbp
0x18002deed  retn
```
