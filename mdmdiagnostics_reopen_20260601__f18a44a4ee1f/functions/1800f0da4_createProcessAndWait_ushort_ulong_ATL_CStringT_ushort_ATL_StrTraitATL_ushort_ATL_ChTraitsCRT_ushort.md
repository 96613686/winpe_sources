# createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800f0da4`
- end: `0x1800f1083`
- name: `?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, LPDWORD lpExitCode)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f029c`
- `0x1800f0b28`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e9378`
- `0x1800edae0`
- `0x1800f0da4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f0e5e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f0e5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f0eb2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f0eb2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0f60`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f0f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f1020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f104a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f0f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f1020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f104a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f0fe8`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f0fe8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f0f44`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f0f44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1037`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f0e30`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f0e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall createProcessAndWait(LPWSTR lpCommandLine, LPDWORD lpExitCode, __int64 a3)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  UINT TempFileNameW; // ebx
  HANDLE v9; // rdi
  unsigned int v10; // edi
  DWORD v11; // eax
  struct _PROCESS_INFORMATION *v12; // rdx
  DWORD LastError; // eax
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  HANDLE *p_hObject; // [rsp+88h] [rbp-78h]
  char v19; // [rsp+90h] [rbp-70h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR TempFileName[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR PathName[264]; // [rsp+320h] [rbp+220h] BYREF

  hObject = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  if ( !lpCommandLine )
    goto LABEL_25;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( lpCommandLine[v7] );
  if ( !v7 )
  {
LABEL_25:
    SetLastError(0x57u);
    return 0;
  }
  p_hObject = &hObject;
  v19 = 1;
  if ( (unsigned int)GetTempPath2W(260, PathName) - 1 > 0x103
    || (TempFileNameW = GetTempFileNameW(PathName, L"DIAG", 0, TempFileName)) == 0
    || (*(_QWORD *)&SecurityAttributes.nLength = 24,
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 1,
        SecurityAttributes.lpSecurityDescriptor = 0,
        v9 = CreateFileW(TempFileName, 4u, 3u, &SecurityAttributes, 2u, 0x80u, 0),
        hObject = v9,
        v9 == (HANDLE)-1LL) )
  {
    LastError = GetLastError();
    SetLastError(LastError);
    if ( hObject )
      CloseHandle(hObject);
    return 0;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.wShowWindow = 2;
  StartupInfo.hStdError = v9;
  StartupInfo.hStdOutput = v9;
  StartupInfo.hStdInput = 0;
  StartupInfo.dwFlags = 256;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v10 = CreateProcessW(0, lpCommandLine, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation);
  if ( v10 )
  {
    v11 = WaitForSingleObject(ProcessInformation.hProcess, 0xDBBA0u);
    if ( v11 )
    {
      if ( v11 == -1 )
        goto LABEL_11;
    }
    else
    {
      if ( !lpExitCode || GetExitCodeProcess(ProcessInformation.hProcess, lpExitCode) )
      {
LABEL_21:
        if ( v10 )
          goto LABEL_13;
        goto LABEL_12;
      }
      v11 = GetLastError();
      v10 = 0;
    }
    TempFileNameW = v11;
    goto LABEL_21;
  }
LABEL_11:
  v10 = 0;
  TempFileNameW = GetLastError();
LABEL_12:
  SetLastError(TempFileNameW);
  do
LABEL_13:
    ++v6;
  while ( TempFileName[v6] );
  ATL::CSimpleStringT<unsigned short,0>::SetString(a3, TempFileName);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v12);
  if ( hObject )
    CloseHandle(hObject);
  return v10;
}

```

## disassembly

```asm
0x1800f0da4  mov     [rsp-8+arg_18], rbx
0x1800f0da9  push    rbp
0x1800f0daa  push    rsi
0x1800f0dab  push    rdi
0x1800f0dac  push    r12
0x1800f0dae  push    r13
0x1800f0db0  push    r14
0x1800f0db2  push    r15
0x1800f0db4  lea     rbp, [rsp-440h]
0x1800f0dbc  sub     rsp, 540h
0x1800f0dc3  mov     rax, cs:__security_cookie
0x1800f0dca  xor     rax, rsp
0x1800f0dcd  mov     [rbp+470h+var_40], rax
0x1800f0dd4  mov     r12, r8
0x1800f0dd7  mov     r15, rdx
0x1800f0dda  mov     r14, rcx
0x1800f0ddd  xor     r13d, r13d
0x1800f0de0  mov     [rsp+570h+hObject], r13
0x1800f0de5  xor     edx, edx; Val
0x1800f0de7  lea     r8d, [r13+68h]; Size
0x1800f0deb  lea     rcx, [rbp+470h+StartupInfo]; void *
0x1800f0def  call    memset_0
0x1800f0df4  test    r14, r14
0x1800f0df7  jz      loc_1800F1045
0x1800f0dfd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f0e01  mov     rax, rsi
0x1800f0e04  inc     rax
0x1800f0e07  cmp     [r14+rax*2], r13w
0x1800f0e0c  jnz     short loc_1800F0E04
0x1800f0e0e  test    rax, rax
0x1800f0e11  jz      loc_1800F1045
0x1800f0e17  lea     rax, [rsp+570h+hObject]
0x1800f0e1c  mov     [rbp+470h+var_4E8], rax
0x1800f0e20  mov     [rbp+470h+var_4E0], 1
0x1800f0e24  lea     rdx, [rbp+470h+PathName]
0x1800f0e2b  mov     ecx, 104h
0x1800f0e30  call    cs:__imp_GetTempPath2W
0x1800f0e37  nop     dword ptr [rax+rax+00h]
0x1800f0e3c  dec     eax
0x1800f0e3e  cmp     eax, 103h
0x1800f0e43  ja      loc_1800F1012
0x1800f0e49  lea     r9, [rbp+470h+TempFileName]; lpTempFileName
0x1800f0e4d  xor     r8d, r8d; uUnique
0x1800f0e50  lea     rdx, PrefixString; "DIAG"
0x1800f0e57  lea     rcx, [rbp+470h+PathName]; lpPathName
0x1800f0e5e  call    cs:__imp_GetTempFileNameW
0x1800f0e65  nop     dword ptr [rax+rax+00h]
0x1800f0e6a  mov     ebx, eax
0x1800f0e6c  test    eax, eax
0x1800f0e6e  jz      loc_1800F1012
0x1800f0e74  mov     qword ptr [rsp+570h+SecurityAttributes.nLength], 18h
0x1800f0e7d  mov     qword ptr [rsp+570h+SecurityAttributes.bInheritHandle], 1
0x1800f0e86  mov     [rsp+570h+SecurityAttributes.lpSecurityDescriptor], r13
0x1800f0e8b  mov     [rsp+570h+hTemplateFile], r13; hTemplateFile
0x1800f0e90  mov     [rsp+570h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f0e98  mov     [rsp+570h+dwCreationDisposition], 2; dwCreationDisposition
0x1800f0ea0  lea     r9, [rsp+570h+SecurityAttributes]; lpSecurityAttributes
0x1800f0ea5  mov     edx, 4; dwDesiredAccess
0x1800f0eaa  lea     r8d, [rdx-1]; dwShareMode
0x1800f0eae  lea     rcx, [rbp+470h+TempFileName]; lpFileName
0x1800f0eb2  call    cs:__imp_CreateFileW
0x1800f0eb9  nop     dword ptr [rax+rax+00h]
0x1800f0ebe  mov     rdi, rax
0x1800f0ec1  mov     [rsp+570h+hObject], rax
0x1800f0ec6  cmp     rax, rsi
0x1800f0ec9  jz      loc_1800F1012
0x1800f0ecf  xor     edx, edx; Val
0x1800f0ed1  lea     r8d, [rdx+68h]; Size
0x1800f0ed5  lea     rcx, [rbp+470h+StartupInfo]; void *
0x1800f0ed9  call    memset_0
0x1800f0ede  mov     [rbp+470h+StartupInfo.cb], 68h ; 'h'
0x1800f0ee5  mov     eax, 2
0x1800f0eea  mov     [rbp+470h+StartupInfo.wShowWindow], ax
0x1800f0eee  mov     [rbp+470h+StartupInfo.hStdError], rdi
0x1800f0ef2  mov     [rbp+470h+StartupInfo.hStdOutput], rdi
0x1800f0ef6  mov     [rbp+470h+StartupInfo.hStdInput], r13
0x1800f0efa  mov     [rbp+470h+StartupInfo.dwFlags], 100h
0x1800f0f01  xorps   xmm0, xmm0
0x1800f0f04  xor     eax, eax
0x1800f0f06  movups  xmmword ptr [rsp+570h+ProcessInformation.hProcess], xmm0
0x1800f0f0b  mov     qword ptr [rbp+470h+ProcessInformation.dwProcessId], rax
0x1800f0f0f  lea     rax, [rsp+570h+ProcessInformation]
0x1800f0f14  mov     [rsp+570h+lpProcessInformation], rax; lpProcessInformation
0x1800f0f19  lea     rax, [rbp+470h+StartupInfo]
0x1800f0f1d  mov     [rsp+570h+lpStartupInfo], rax; lpStartupInfo
0x1800f0f22  mov     [rsp+570h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1800f0f27  mov     [rsp+570h+hTemplateFile], r13; lpEnvironment
0x1800f0f2c  mov     [rsp+570h+dwFlagsAndAttributes], r13d; dwCreationFlags
0x1800f0f31  mov     [rsp+570h+dwCreationDisposition], 1; bInheritHandles
0x1800f0f39  xor     r9d, r9d; lpThreadAttributes
0x1800f0f3c  xor     r8d, r8d; lpProcessAttributes
0x1800f0f3f  mov     rdx, r14; lpCommandLine
0x1800f0f42  xor     ecx, ecx; lpApplicationName
0x1800f0f44  call    cs:__imp_CreateProcessW
0x1800f0f4b  nop     dword ptr [rax+rax+00h]
0x1800f0f50  mov     edi, eax
0x1800f0f52  test    eax, eax
0x1800f0f54  jz      short loc_1800F0F79
0x1800f0f56  mov     edx, 0DBBA0h; dwMilliseconds
0x1800f0f5b  mov     rcx, [rsp+570h+ProcessInformation.hProcess]; hHandle
0x1800f0f60  call    cs:__imp_WaitForSingleObject
0x1800f0f67  nop     dword ptr [rax+rax+00h]
0x1800f0f6c  test    eax, eax
0x1800f0f6e  jz      short loc_1800F0FDB
0x1800f0f70  cmp     eax, 0FFFFFFFFh
0x1800f0f73  jnz     loc_1800F1007
0x1800f0f79  call    cs:__imp_GetLastError
0x1800f0f80  nop     dword ptr [rax+rax+00h]
0x1800f0f85  mov     edi, r13d
0x1800f0f88  mov     ebx, eax
0x1800f0f8a  mov     ecx, ebx; dwErrCode
0x1800f0f8c  call    cs:__imp_SetLastError
0x1800f0f93  nop     dword ptr [rax+rax+00h]
0x1800f0f98  lea     rax, [rbp+470h+TempFileName]
0x1800f0f9c  inc     rsi
0x1800f0f9f  cmp     [rax+rsi*2], r13w
0x1800f0fa4  jnz     short loc_1800F0F9C
0x1800f0fa6  mov     r8d, esi
0x1800f0fa9  lea     rdx, [rbp+470h+TempFileName]
0x1800f0fad  mov     rcx, r12
0x1800f0fb0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800f0fb5  nop
0x1800f0fb6  lea     rcx, [rsp+570h+ProcessInformation]; this
0x1800f0fbb  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800f0fc0  nop
0x1800f0fc1  mov     rcx, [rsp+570h+hObject]; hObject
0x1800f0fc6  test    rcx, rcx
0x1800f0fc9  jz      short loc_1800F0FD7
0x1800f0fcb  call    cs:__imp_CloseHandle
0x1800f0fd2  nop     dword ptr [rax+rax+00h]
0x1800f0fd7  mov     eax, edi
0x1800f0fd9  jmp     short loc_1800F1058
0x1800f0fdb  test    r15, r15
0x1800f0fde  jz      short loc_1800F1009
0x1800f0fe0  mov     rdx, r15; lpExitCode
0x1800f0fe3  mov     rcx, [rsp+570h+ProcessInformation.hProcess]; hProcess
0x1800f0fe8  call    cs:__imp_GetExitCodeProcess
0x1800f0fef  nop     dword ptr [rax+rax+00h]
0x1800f0ff4  test    eax, eax
0x1800f0ff6  jnz     short loc_1800F1009
0x1800f0ff8  call    cs:__imp_GetLastError
0x1800f0fff  nop     dword ptr [rax+rax+00h]
0x1800f1004  mov     edi, r13d
0x1800f1007  mov     ebx, eax
0x1800f1009  test    edi, edi
0x1800f100b  jnz     short loc_1800F0F98
0x1800f100d  jmp     loc_1800F0F8A
0x1800f1012  call    cs:__imp_GetLastError
0x1800f1019  nop     dword ptr [rax+rax+00h]
0x1800f101e  mov     ecx, eax; dwErrCode
0x1800f1020  call    cs:__imp_SetLastError
0x1800f1027  nop     dword ptr [rax+rax+00h]
0x1800f102c  nop
0x1800f102d  mov     rcx, [rsp+570h+hObject]; hObject
0x1800f1032  test    rcx, rcx
0x1800f1035  jz      short loc_1800F1056
0x1800f1037  call    cs:__imp_CloseHandle
0x1800f103e  nop     dword ptr [rax+rax+00h]
0x1800f1043  jmp     short loc_1800F1056
0x1800f1045  mov     ecx, 57h ; 'W'; dwErrCode
0x1800f104a  call    cs:__imp_SetLastError
0x1800f1051  nop     dword ptr [rax+rax+00h]
0x1800f1056  xor     eax, eax
0x1800f1058  mov     rcx, [rbp+470h+var_40]
0x1800f105f  xor     rcx, rsp; StackCookie
0x1800f1062  call    __security_check_cookie
0x1800f1067  mov     rbx, [rsp+570h+arg_18]
0x1800f106f  add     rsp, 540h
0x1800f1076  pop     r15
0x1800f1078  pop     r14
0x1800f107a  pop     r13
0x1800f107c  pop     r12
0x1800f107e  pop     rdi
0x1800f107f  pop     rsi
0x1800f1080  pop     rbp
0x1800f1081  retn
```
