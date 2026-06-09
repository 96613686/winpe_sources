# CPushButtonReset::RunSystemProcess(ushort const *)

- ea: `0x18001d10c`
- end: `0x18001d4b6`
- name: `?RunSystemProcess@CPushButtonReset@@CAKPEBG@Z`
- size: `938`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cc3c`

## callees

- `0x180002488`
- `0x180003d50`
- `0x18001d10c`
- `0x18001d4bc`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d1aa`
- `KERNEL32!GetLastError` at `0x18001d2d0`
- `KERNEL32!GetLastError` at `0x18001d3dd`
- `KERNEL32!GetLastError` at `0x18001d1aa`
- `KERNEL32!GetLastError` at `0x18001d2d0`
- `KERNEL32!GetLastError` at `0x18001d3dd`
- `KERNEL32!CloseHandle` at `0x18001d235`
- `KERNEL32!CloseHandle` at `0x18001d24a`
- `KERNEL32!CloseHandle` at `0x18001d44e`
- `KERNEL32!CloseHandle` at `0x18001d458`
- `KERNEL32!CloseHandle` at `0x18001d46c`
- `KERNEL32!CloseHandle` at `0x18001d481`
- `KERNEL32!CloseHandle` at `0x18001d235`
- `KERNEL32!CloseHandle` at `0x18001d24a`
- `KERNEL32!CloseHandle` at `0x18001d44e`
- `KERNEL32!CloseHandle` at `0x18001d458`
- `KERNEL32!CloseHandle` at `0x18001d46c`
- `KERNEL32!CloseHandle` at `0x18001d481`
- `KERNEL32!WaitForSingleObject` at `0x18001d3c4`
- `KERNEL32!WaitForSingleObject` at `0x18001d3c4`
- `KERNEL32!CreateProcessW` at `0x18001d368`
- `KERNEL32!CreateProcessW` at `0x18001d368`
- `KERNEL32!GetExitCodeProcess` at `0x18001d3d3`
- `KERNEL32!GetExitCodeProcess` at `0x18001d3d3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001d40b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001d40b`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001d1d2`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001d1d2`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001d1a0`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001d1a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001d277`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001d277`

## string_xrefs

- `0x18001d1e5`: `CreatePipe`
- `0x18001d28a`: `GetSystemDirectory`
- `0x18001d377`: `CreateProcess`
- `0x18001d436`: `ReadFile %#x`

## pseudocode

```c
__int64 __fastcall CPushButtonReset::RunSystemProcess(const unsigned __int16 *a1)
{
  DWORD v2; // edi
  __int64 v3; // rax
  const wchar_t *v4; // rcx
  __int64 v5; // rdx
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rcx
  UINT SystemDirectoryW; // eax
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rcx
  DWORD v15; // ebx
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  unsigned __int64 v18; // rcx
  DWORD dwCreationFlags; // [rsp+28h] [rbp-D8h]
  DWORD dwCreationFlagsa; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ExitCode; // [rsp+54h] [rbp-ACh] BYREF
  DWORD LastError; // [rsp+58h] [rbp-A8h]
  HANDLE hReadPipe[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  *(_QWORD *)&PipeAttributes.nLength = 24;
  ExitCode = 0;
  NumberOfBytesRead = 0;
  *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
  PipeAttributes.lpSecurityDescriptor = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreatePipe(hReadPipe, &hReadPipe[1], &PipeAttributes, 0) )
  {
    LastError = 0;
    SetHandleInformation(hReadPipe[0], 1u, 0);
    v2 = 0;
  }
  else
  {
    LastError = GetLastError();
    *(_OWORD *)hReadPipe = 0;
    v2 = LastError;
  }
  if ( v2 )
  {
    v3 = 2147483646;
    v4 = L"CreatePipe";
    v5 = 4096;
    v6 = &CPushButtonReset::_wszErrorInfo;
    do
    {
      if ( !v3 )
        break;
      if ( !*v4 )
        break;
      *v6++ = *v4++;
      --v3;
      --v5;
    }
    while ( v5 );
    v7 = v6 - 1;
    if ( v5 )
      v7 = v6;
    *v7 = 0;
    if ( hReadPipe[0] )
    {
      CloseHandle(hReadPipe[0]);
      hReadPipe[0] = 0;
    }
    if ( hReadPipe[1] )
      CloseHandle(hReadPipe[1]);
    return v2;
  }
  StartupInfo.dwFlags |= 0x100u;
  StartupInfo.cb = 104;
  StartupInfo.hStdError = hReadPipe[1];
  StartupInfo.hStdOutput = hReadPipe[1];
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  NumberOfBytesRead = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    v25 = 260LL - SystemDirectoryW;
    v26 = &Buffer[SystemDirectoryW];
    StringCchCatExW(v26, v25, L"\\", &v26, &v25, dwCreationFlags);
    StringCchCatExW(v26, v25, a1, &v26, &v25, dwCreationFlagsa);
    if ( CreateProcessW(0, Buffer, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0x2BF20u);
      if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      {
        ExitCode = GetLastError();
        NumberOfBytesRead = 0;
        if ( ReadFile(hReadPipe[0], &CPushButtonReset::_wszErrorInfo, 0xFFFu, &NumberOfBytesRead, 0) )
        {
          v18 = 2LL * NumberOfBytesRead;
          if ( v18 >= 0x2000 )
            _report_rangecheckfailure();
          *(unsigned __int16 *)((char *)&CPushButtonReset::_wszErrorInfo + v18) = 0;
        }
        else
        {
          StringCchPrintfW(&CPushButtonReset::_wszErrorInfo, 0x1000u, L"ReadFile %#x", ExitCode);
        }
      }
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
      v15 = ExitCode;
      goto LABEL_36;
    }
    v16 = 2147483646;
    v17 = L"CreateProcess";
    v12 = 4096;
    v13 = &CPushButtonReset::_wszErrorInfo;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v13++ = *v17++;
      --v16;
      --v12;
    }
    while ( v12 );
  }
  else
  {
    v10 = 2147483646;
    v11 = L"GetSystemDirectory";
    v12 = 4096;
    v13 = &CPushButtonReset::_wszErrorInfo;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
  }
  v14 = v13 - 1;
  if ( v12 )
    v14 = v13;
  *v14 = 0;
  v15 = GetLastError();
LABEL_36:
  if ( hReadPipe[0] )
  {
    CloseHandle(hReadPipe[0]);
    hReadPipe[0] = 0;
  }
  if ( hReadPipe[1] )
    CloseHandle(hReadPipe[1]);
  return v15;
}

```

## disassembly

```asm
0x18001d10c  mov     [rsp-8+arg_8], rbx
0x18001d111  mov     [rsp-8+arg_10], rsi
0x18001d116  push    rbp
0x18001d117  push    rdi
0x18001d118  push    r14
0x18001d11a  lea     rbp, [rsp-240h]
0x18001d122  sub     rsp, 340h
0x18001d129  mov     rax, cs:__security_cookie
0x18001d130  xor     rax, rsp
0x18001d133  mov     [rbp+250h+var_20], rax
0x18001d13a  mov     rsi, rcx
0x18001d13d  xor     edx, edx; Val
0x18001d13f  lea     rcx, [rbp+250h+Buffer]; void *
0x18001d143  mov     r8d, 208h; Size
0x18001d149  call    memset_0
0x18001d14e  mov     ebx, 68h ; 'h'
0x18001d153  lea     rcx, [rbp+250h+StartupInfo]; void *
0x18001d157  mov     r8d, ebx; Size
0x18001d15a  xor     edx, edx; Val
0x18001d15c  call    memset_0
0x18001d161  xor     r14d, r14d
0x18001d164  mov     qword ptr [rbp+250h+PipeAttributes.nLength], 18h
0x18001d16c  xorps   xmm0, xmm0
0x18001d16f  mov     [rsp+350h+ExitCode], r14d
0x18001d174  xor     eax, eax
0x18001d176  mov     [rsp+350h+NumberOfBytesRead], r14d
0x18001d17b  xor     r9d, r9d; nSize
0x18001d17e  mov     qword ptr [rbp+250h+ProcessInformation.dwProcessId], rax
0x18001d182  lea     r8, [rbp+250h+PipeAttributes]; lpPipeAttributes
0x18001d186  mov     qword ptr [rbp+250h+PipeAttributes.bInheritHandle], 1
0x18001d18e  lea     rdx, [rsp+350h+hReadPipe+8]; hWritePipe
0x18001d193  mov     [rbp+250h+PipeAttributes.lpSecurityDescriptor], r14
0x18001d197  lea     rcx, [rsp+350h+hReadPipe]; hReadPipe
0x18001d19c  movups  xmmword ptr [rbp+250h+ProcessInformation.hProcess], xmm0
0x18001d1a0  call    cs:__imp_CreatePipe
0x18001d1a6  test    eax, eax
0x18001d1a8  jnz     short loc_18001D1C1
0x18001d1aa  call    cs:__imp_GetLastError
0x18001d1b0  xorps   xmm0, xmm0
0x18001d1b3  mov     [rsp+350h+var_2F8], eax
0x18001d1b7  movdqu  xmmword ptr [rsp+350h+hReadPipe], xmm0
0x18001d1bd  mov     edi, eax
0x18001d1bf  jmp     short loc_18001D1DC
0x18001d1c1  mov     rcx, [rsp+350h+hReadPipe]; hObject
0x18001d1c6  xor     r8d, r8d; dwFlags
0x18001d1c9  mov     [rsp+350h+var_2F8], r14d
0x18001d1ce  lea     edx, [r8+1]; dwMask
0x18001d1d2  call    cs:__imp_SetHandleInformation
0x18001d1d8  mov     edi, [rsp+350h+var_2F8]
0x18001d1dc  test    edi, edi
0x18001d1de  jz      short loc_18001D257
0x18001d1e0  mov     eax, 7FFFFFFEh
0x18001d1e5  lea     rcx, aCreatepipe; "CreatePipe"
0x18001d1ec  mov     edx, 1000h
0x18001d1f1  lea     rbx, ?_wszErrorInfo@CPushButtonReset@@0PAGA; ushort near * CPushButtonReset::_wszErrorInfo
0x18001d1f8  test    rax, rax
0x18001d1fb  jz      short loc_18001D21C
0x18001d1fd  movzx   r8d, word ptr [rcx]
0x18001d201  test    r8w, r8w
0x18001d205  jz      short loc_18001D21C
0x18001d207  mov     [rbx], r8w
0x18001d20b  add     rcx, 2
0x18001d20f  add     rbx, 2
0x18001d213  dec     rax
0x18001d216  sub     rdx, 1
0x18001d21a  jnz     short loc_18001D1F8
0x18001d21c  test    rdx, rdx
0x18001d21f  lea     rcx, [rbx-2]
0x18001d223  cmovnz  rcx, rbx
0x18001d227  mov     [rcx], r14w
0x18001d22b  mov     rcx, [rsp+350h+hReadPipe]; hObject
0x18001d230  test    rcx, rcx
0x18001d233  jz      short loc_18001D240
0x18001d235  call    cs:__imp_CloseHandle
0x18001d23b  mov     [rsp+350h+hReadPipe], r14
0x18001d240  mov     rcx, [rsp+350h+hReadPipe+8]; hObject
0x18001d245  test    rcx, rcx
0x18001d248  jz      short loc_18001D250
0x18001d24a  call    cs:__imp_CloseHandle
0x18001d250  mov     eax, edi
0x18001d252  jmp     loc_18001D489
0x18001d257  mov     rax, [rsp+350h+hReadPipe+8]
0x18001d25c  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x18001d260  bts     [rbp+250h+StartupInfo.dwFlags], 8
0x18001d265  mov     [rbp+250h+StartupInfo.cb], ebx
0x18001d268  mov     ebx, 104h
0x18001d26d  mov     edx, ebx; uSize
0x18001d26f  mov     [rbp+250h+StartupInfo.hStdError], rax
0x18001d273  mov     [rbp+250h+StartupInfo.hStdOutput], rax
0x18001d277  call    cs:__imp_GetSystemDirectoryW
0x18001d27d  mov     [rsp+350h+NumberOfBytesRead], eax
0x18001d281  test    eax, eax
0x18001d283  jnz     short loc_18001D2DD
0x18001d285  mov     eax, 7FFFFFFEh
0x18001d28a  lea     rcx, aGetsystemdirec; "GetSystemDirectory"
0x18001d291  mov     edx, 1000h
0x18001d296  lea     rbx, ?_wszErrorInfo@CPushButtonReset@@0PAGA; ushort near * CPushButtonReset::_wszErrorInfo
0x18001d29d  test    rax, rax
0x18001d2a0  jz      short loc_18001D2C1
0x18001d2a2  movzx   r8d, word ptr [rcx]
0x18001d2a6  test    r8w, r8w
0x18001d2aa  jz      short loc_18001D2C1
0x18001d2ac  mov     [rbx], r8w
0x18001d2b0  add     rcx, 2
0x18001d2b4  add     rbx, 2
0x18001d2b8  dec     rax
0x18001d2bb  sub     rdx, 1
0x18001d2bf  jnz     short loc_18001D29D
0x18001d2c1  test    rdx, rdx
0x18001d2c4  lea     rcx, [rbx-2]
0x18001d2c8  cmovnz  rcx, rbx
0x18001d2cc  mov     [rcx], r14w
0x18001d2d0  call    cs:__imp_GetLastError
0x18001d2d6  mov     ebx, eax
0x18001d2d8  jmp     loc_18001D462
0x18001d2dd  mov     eax, eax
0x18001d2df  lea     rcx, [rbp+250h+Buffer]
0x18001d2e3  sub     rbx, rax
0x18001d2e6  lea     r9, [rsp+350h+var_2D8]; unsigned __int16 **
0x18001d2eb  lea     r8, asc_180025E28; "\\"
0x18001d2f2  mov     [rsp+350h+var_2E0], rbx
0x18001d2f7  mov     rdx, rbx; unsigned __int64
0x18001d2fa  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001d2fe  lea     rax, [rsp+350h+var_2E0]
0x18001d303  mov     [rsp+350h+var_2D8], rcx
0x18001d308  mov     qword ptr [rsp+350h+bInheritHandles], rax; unsigned __int64 *
0x18001d30d  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001d312  mov     rdx, [rsp+350h+var_2E0]; unsigned __int64
0x18001d317  lea     rax, [rsp+350h+var_2E0]
0x18001d31c  mov     rcx, [rsp+350h+var_2D8]; unsigned __int16 *
0x18001d321  lea     r9, [rsp+350h+var_2D8]; unsigned __int16 **
0x18001d326  mov     r8, rsi; unsigned __int16 *
0x18001d329  mov     qword ptr [rsp+350h+bInheritHandles], rax; unsigned __int64 *
0x18001d32e  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001d333  lea     rax, [rbp+250h+ProcessInformation]
0x18001d337  xor     r9d, r9d; lpThreadAttributes
0x18001d33a  mov     [rsp+350h+lpProcessInformation], rax; lpProcessInformation
0x18001d33f  lea     rdx, [rbp+250h+Buffer]; lpCommandLine
0x18001d343  lea     rax, [rbp+250h+StartupInfo]
0x18001d347  xor     r8d, r8d; lpProcessAttributes
0x18001d34a  mov     [rsp+350h+lpStartupInfo], rax; lpStartupInfo
0x18001d34f  xor     ecx, ecx; lpApplicationName
0x18001d351  mov     [rsp+350h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18001d356  mov     [rsp+350h+lpEnvironment], r14; lpEnvironment
0x18001d35b  mov     [rsp+350h+dwCreationFlags], r14d; dwCreationFlags
0x18001d360  mov     [rsp+350h+bInheritHandles], 1; bInheritHandles
0x18001d368  call    cs:__imp_CreateProcessW
0x18001d36e  test    eax, eax
0x18001d370  jnz     short loc_18001D3BB
0x18001d372  mov     eax, 7FFFFFFEh
0x18001d377  lea     rcx, aCreateprocess; "CreateProcess"
0x18001d37e  mov     edx, 1000h
0x18001d383  lea     rbx, ?_wszErrorInfo@CPushButtonReset@@0PAGA; ushort near * CPushButtonReset::_wszErrorInfo
0x18001d38a  test    rax, rax
0x18001d38d  jz      loc_18001D2C1
0x18001d393  movzx   r8d, word ptr [rcx]
0x18001d397  test    r8w, r8w
0x18001d39b  jz      loc_18001D2C1
0x18001d3a1  mov     [rbx], r8w
0x18001d3a5  add     rcx, 2
0x18001d3a9  add     rbx, 2
0x18001d3ad  dec     rax
0x18001d3b0  sub     rdx, 1
0x18001d3b4  jnz     short loc_18001D38A
0x18001d3b6  jmp     loc_18001D2C1
0x18001d3bb  mov     rcx, [rbp+250h+ProcessInformation.hProcess]; hHandle
0x18001d3bf  mov     edx, 2BF20h; dwMilliseconds
0x18001d3c4  call    cs:__imp_WaitForSingleObject
0x18001d3ca  mov     rcx, [rbp+250h+ProcessInformation.hProcess]; hProcess
0x18001d3ce  lea     rdx, [rsp+350h+ExitCode]; lpExitCode
0x18001d3d3  call    cs:__imp_GetExitCodeProcess
0x18001d3d9  test    eax, eax
0x18001d3db  jnz     short loc_18001D44A
0x18001d3dd  call    cs:__imp_GetLastError
0x18001d3e3  mov     rcx, [rsp+350h+hReadPipe]; hFile
0x18001d3e8  lea     rbx, ?_wszErrorInfo@CPushButtonReset@@0PAGA; ushort near * CPushButtonReset::_wszErrorInfo
0x18001d3ef  mov     rdx, rbx; lpBuffer
0x18001d3f2  mov     [rsp+350h+ExitCode], eax
0x18001d3f6  lea     r9, [rsp+350h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001d3fb  mov     [rsp+350h+NumberOfBytesRead], r14d
0x18001d400  mov     r8d, 0FFFh; nNumberOfBytesToRead
0x18001d406  mov     qword ptr [rsp+350h+bInheritHandles], r14; lpOverlapped
0x18001d40b  call    cs:__imp_ReadFile
0x18001d411  test    eax, eax
0x18001d413  jz      short loc_18001D431
0x18001d415  mov     eax, [rsp+350h+NumberOfBytesRead]
0x18001d419  lea     rcx, [rax+rax]
0x18001d41d  cmp     rcx, 2000h
0x18001d424  jnb     loc_18001D4B0
0x18001d42a  mov     [rcx+rbx], r14w
0x18001d42f  jmp     short loc_18001D44A
0x18001d431  mov     r9d, [rsp+350h+ExitCode]
0x18001d436  lea     r8, aReadfileX; "ReadFile %#x"
0x18001d43d  mov     edx, 1000h; unsigned __int64
0x18001d442  mov     rcx, rbx; unsigned __int16 *
0x18001d445  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d44a  mov     rcx, [rbp+250h+ProcessInformation.hProcess]; hObject
0x18001d44e  call    cs:__imp_CloseHandle
0x18001d454  mov     rcx, [rbp+250h+ProcessInformation.hThread]; hObject
0x18001d458  call    cs:__imp_CloseHandle
0x18001d45e  mov     ebx, [rsp+350h+ExitCode]
0x18001d462  mov     rcx, [rsp+350h+hReadPipe]; hObject
0x18001d467  test    rcx, rcx
0x18001d46a  jz      short loc_18001D477
0x18001d46c  call    cs:__imp_CloseHandle
0x18001d472  mov     [rsp+350h+hReadPipe], r14
0x18001d477  mov     rcx, [rsp+350h+hReadPipe+8]; hObject
0x18001d47c  test    rcx, rcx
0x18001d47f  jz      short loc_18001D487
0x18001d481  call    cs:__imp_CloseHandle
0x18001d487  mov     eax, ebx
0x18001d489  mov     rcx, [rbp+250h+var_20]
0x18001d490  xor     rcx, rsp; StackCookie
0x18001d493  call    __security_check_cookie
0x18001d498  lea     r11, [rsp+350h+var_10]
0x18001d4a0  mov     rbx, [r11+28h]
0x18001d4a4  mov     rsi, [r11+30h]
0x18001d4a8  mov     rsp, r11
0x18001d4ab  pop     r14
0x18001d4ad  pop     rdi
0x18001d4ae  pop     rbp
0x18001d4af  retn
0x18001d4b0  call    __report_rangecheckfailure
```
