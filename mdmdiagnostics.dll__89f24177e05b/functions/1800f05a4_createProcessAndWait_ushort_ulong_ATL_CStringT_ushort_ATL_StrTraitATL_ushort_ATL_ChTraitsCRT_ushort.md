# createProcessAndWait(ushort *,ulong *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800f05a4`
- end: `0x1800f0827`
- name: `?createProcessAndWait@@YAHPEAGPEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, LPDWORD lpExitCode, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800efab4`
- `0x1800f02b4`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e8fbc`
- `0x1800ed4a0`
- `0x1800f05a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f0658`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f0658`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f06a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f06a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0748`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f07cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f0764`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f07d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f07f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f0764`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f07d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f07f5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f07b4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f07b4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f0732`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f0732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f079d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f07e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f079d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f07e8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f0630`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800f0630`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800f05a4  mov     [rsp-8+arg_18], rbx
0x1800f05a9  push    rbp
0x1800f05aa  push    rsi
0x1800f05ab  push    rdi
0x1800f05ac  push    r12
0x1800f05ae  push    r13
0x1800f05b0  push    r14
0x1800f05b2  push    r15
0x1800f05b4  lea     rbp, [rsp-440h]
0x1800f05bc  sub     rsp, 540h
0x1800f05c3  mov     rax, cs:__security_cookie
0x1800f05ca  xor     rax, rsp
0x1800f05cd  mov     [rbp+470h+var_40], rax
0x1800f05d4  mov     r12, r8
0x1800f05d7  mov     r15, rdx
0x1800f05da  mov     r14, rcx
0x1800f05dd  xor     r13d, r13d
0x1800f05e0  mov     [rsp+570h+hObject], r13
0x1800f05e5  xor     edx, edx; Val
0x1800f05e7  lea     r8d, [r13+68h]; Size
0x1800f05eb  lea     rcx, [rbp+470h+StartupInfo]; void *
0x1800f05ef  call    memset_0
0x1800f05f4  test    r14, r14
0x1800f05f7  jz      loc_1800F07F0
0x1800f05fd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f0601  mov     rax, rsi
0x1800f0604  inc     rax
0x1800f0607  cmp     [r14+rax*2], r13w
0x1800f060c  jnz     short loc_1800F0604
0x1800f060e  test    rax, rax
0x1800f0611  jz      loc_1800F07F0
0x1800f0617  lea     rax, [rsp+570h+hObject]
0x1800f061c  mov     [rbp+470h+var_4E8], rax
0x1800f0620  mov     [rbp+470h+var_4E0], 1
0x1800f0624  lea     rdx, [rbp+470h+PathName]
0x1800f062b  mov     ecx, 104h
0x1800f0630  call    cs:__imp_GetTempPath2W
0x1800f0636  dec     eax
0x1800f0638  cmp     eax, 103h
0x1800f063d  ja      loc_1800F07CF
0x1800f0643  lea     r9, [rbp+470h+TempFileName]; lpTempFileName
0x1800f0647  xor     r8d, r8d; uUnique
0x1800f064a  lea     rdx, PrefixString; "DIAG"
0x1800f0651  lea     rcx, [rbp+470h+PathName]; lpPathName
0x1800f0658  call    cs:__imp_GetTempFileNameW
0x1800f065e  mov     ebx, eax
0x1800f0660  test    eax, eax
0x1800f0662  jz      loc_1800F07CF
0x1800f0668  mov     qword ptr [rsp+570h+SecurityAttributes.nLength], 18h
0x1800f0671  mov     qword ptr [rsp+570h+SecurityAttributes.bInheritHandle], 1
0x1800f067a  mov     [rsp+570h+SecurityAttributes.lpSecurityDescriptor], r13
0x1800f067f  mov     [rsp+570h+hTemplateFile], r13; hTemplateFile
0x1800f0684  mov     [rsp+570h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f068c  mov     [rsp+570h+dwCreationDisposition], 2; dwCreationDisposition
0x1800f0694  lea     r9, [rsp+570h+SecurityAttributes]; lpSecurityAttributes
0x1800f0699  mov     edx, 4; dwDesiredAccess
0x1800f069e  lea     r8d, [rdx-1]; dwShareMode
0x1800f06a2  lea     rcx, [rbp+470h+TempFileName]; lpFileName
0x1800f06a6  call    cs:__imp_CreateFileW
0x1800f06ac  mov     rdi, rax
0x1800f06af  mov     [rsp+570h+hObject], rax
0x1800f06b4  cmp     rax, rsi
0x1800f06b7  jz      loc_1800F07CF
0x1800f06bd  xor     edx, edx; Val
0x1800f06bf  lea     r8d, [rdx+68h]; Size
0x1800f06c3  lea     rcx, [rbp+470h+StartupInfo]; void *
0x1800f06c7  call    memset_0
0x1800f06cc  mov     [rbp+470h+StartupInfo.cb], 68h ; 'h'
0x1800f06d3  mov     eax, 2
0x1800f06d8  mov     [rbp+470h+StartupInfo.wShowWindow], ax
0x1800f06dc  mov     [rbp+470h+StartupInfo.hStdError], rdi
0x1800f06e0  mov     [rbp+470h+StartupInfo.hStdOutput], rdi
0x1800f06e4  mov     [rbp+470h+StartupInfo.hStdInput], r13
0x1800f06e8  mov     [rbp+470h+StartupInfo.dwFlags], 100h
0x1800f06ef  xorps   xmm0, xmm0
0x1800f06f2  xor     eax, eax
0x1800f06f4  movups  xmmword ptr [rsp+570h+ProcessInformation.hProcess], xmm0
0x1800f06f9  mov     qword ptr [rbp+470h+ProcessInformation.dwProcessId], rax
0x1800f06fd  lea     rax, [rsp+570h+ProcessInformation]
0x1800f0702  mov     [rsp+570h+lpProcessInformation], rax; lpProcessInformation
0x1800f0707  lea     rax, [rbp+470h+StartupInfo]
0x1800f070b  mov     [rsp+570h+lpStartupInfo], rax; lpStartupInfo
0x1800f0710  mov     [rsp+570h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1800f0715  mov     [rsp+570h+hTemplateFile], r13; lpEnvironment
0x1800f071a  mov     [rsp+570h+dwFlagsAndAttributes], r13d; dwCreationFlags
0x1800f071f  mov     [rsp+570h+dwCreationDisposition], 1; bInheritHandles
0x1800f0727  xor     r9d, r9d; lpThreadAttributes
0x1800f072a  xor     r8d, r8d; lpProcessAttributes
0x1800f072d  mov     rdx, r14; lpCommandLine
0x1800f0730  xor     ecx, ecx; lpApplicationName
0x1800f0732  call    cs:__imp_CreateProcessW
0x1800f0738  mov     edi, eax
0x1800f073a  test    eax, eax
0x1800f073c  jz      short loc_1800F0757
0x1800f073e  mov     edx, 0DBBA0h; dwMilliseconds
0x1800f0743  mov     rcx, [rsp+570h+ProcessInformation.hProcess]; hHandle
0x1800f0748  call    cs:__imp_WaitForSingleObject
0x1800f074e  test    eax, eax
0x1800f0750  jz      short loc_1800F07A7
0x1800f0752  cmp     eax, 0FFFFFFFFh
0x1800f0755  jnz     short loc_1800F07C7
0x1800f0757  call    cs:__imp_GetLastError
0x1800f075d  mov     edi, r13d
0x1800f0760  mov     ebx, eax
0x1800f0762  mov     ecx, ebx; dwErrCode
0x1800f0764  call    cs:__imp_SetLastError
0x1800f076a  lea     rax, [rbp+470h+TempFileName]
0x1800f076e  inc     rsi
0x1800f0771  cmp     [rax+rsi*2], r13w
0x1800f0776  jnz     short loc_1800F076E
0x1800f0778  mov     r8d, esi
0x1800f077b  lea     rdx, [rbp+470h+TempFileName]
0x1800f077f  mov     rcx, r12
0x1800f0782  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800f0787  nop
0x1800f0788  lea     rcx, [rsp+570h+ProcessInformation]; this
0x1800f078d  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800f0792  nop
0x1800f0793  mov     rcx, [rsp+570h+hObject]; hObject
0x1800f0798  test    rcx, rcx
0x1800f079b  jz      short loc_1800F07A3
0x1800f079d  call    cs:__imp_CloseHandle
0x1800f07a3  mov     eax, edi
0x1800f07a5  jmp     short loc_1800F07FD
0x1800f07a7  test    r15, r15
0x1800f07aa  jz      short loc_1800F07C9
0x1800f07ac  mov     rdx, r15; lpExitCode
0x1800f07af  mov     rcx, [rsp+570h+ProcessInformation.hProcess]; hProcess
0x1800f07b4  call    cs:__imp_GetExitCodeProcess
0x1800f07ba  test    eax, eax
0x1800f07bc  jnz     short loc_1800F07C9
0x1800f07be  call    cs:__imp_GetLastError
0x1800f07c4  mov     edi, r13d
0x1800f07c7  mov     ebx, eax
0x1800f07c9  test    edi, edi
0x1800f07cb  jnz     short loc_1800F076A
0x1800f07cd  jmp     short loc_1800F0762
0x1800f07cf  call    cs:__imp_GetLastError
0x1800f07d5  mov     ecx, eax; dwErrCode
0x1800f07d7  call    cs:__imp_SetLastError
0x1800f07dd  nop
0x1800f07de  mov     rcx, [rsp+570h+hObject]; hObject
0x1800f07e3  test    rcx, rcx
0x1800f07e6  jz      short loc_1800F07FB
0x1800f07e8  call    cs:__imp_CloseHandle
0x1800f07ee  jmp     short loc_1800F07FB
0x1800f07f0  mov     ecx, 57h ; 'W'; dwErrCode
0x1800f07f5  call    cs:__imp_SetLastError
0x1800f07fb  xor     eax, eax
0x1800f07fd  mov     rcx, [rbp+470h+var_40]
0x1800f0804  xor     rcx, rsp; StackCookie
0x1800f0807  call    __security_check_cookie
0x1800f080c  mov     rbx, [rsp+570h+arg_18]
0x1800f0814  add     rsp, 540h
0x1800f081b  pop     r15
0x1800f081d  pop     r14
0x1800f081f  pop     r13
0x1800f0821  pop     r12
0x1800f0823  pop     rdi
0x1800f0824  pop     rsi
0x1800f0825  pop     rbp
0x1800f0826  retn
```
