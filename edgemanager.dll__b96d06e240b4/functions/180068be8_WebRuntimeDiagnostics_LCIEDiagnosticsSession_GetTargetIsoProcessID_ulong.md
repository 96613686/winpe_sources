# WebRuntimeDiagnostics::LCIEDiagnosticsSession::GetTargetIsoProcessID(ulong *)

- ea: `0x180068be8`
- end: `0x180068f07`
- name: `?GetTargetIsoProcessID@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJPEAK@Z`
- size: `799`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800689a4`
- `0x180072c04`

## callees

- `0x18002b530`
- `0x18002c5b0`
- `0x180037b5c`
- `0x180068be8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068c3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068c3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068c50`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068da3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068c50`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068ed9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180068d80`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180068d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068ee4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068ee4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068cc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068df9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068cc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180068df9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068c93`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068dd8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068c93`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068dd8`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x180068d07`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x180068d07`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180068e47`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180068e47`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180068cea`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180068cea`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::GetTargetIsoProcessID(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this,
        unsigned int *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  HANDLE Toolhelp32Snapshot; // rax
  void *v8; // rdi
  WCHAR *szExeFile; // rax
  int v10; // edx
  int v11; // ecx
  HANDLE v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  LPWSTR v16; // rax
  int v17; // r8d
  int v18; // ecx
  unsigned int v19; // ebx
  signed int v20; // eax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v24; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v26; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v29[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+78h] [rbp-88h]
  PROCESSENTRY32W pe; // [rsp+80h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+2C0h] [rbp+1C0h] BYREF
  PSID Sid[12]; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  memset_0(&pe, 0, sizeof(pe));
  TokenHandle = 0;
  ReturnLength = 0;
  StringSid = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
      v4);
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
      v5);
  if ( !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
      v6);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v8 = Toolhelp32Snapshot;
  if ( Toolhelp32Snapshot == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
  pe.dwSize = 568;
  if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
  {
    v20 = GetLastError();
    v19 = v20;
    if ( v20 > 0 )
      v19 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_30;
  }
  while ( 1 )
  {
    v30 = *(_DWORD *)L"e";
    szExeFile = pe.szExeFile;
    v29[0] = *(_OWORD *)L"MicrosoftEdge.exe";
    v29[1] = *(_OWORD *)L"tEdge.exe";
    do
    {
      v10 = *(WCHAR *)((char *)szExeFile + (char *)v29 - (char *)pe.szExeFile);
      v11 = *szExeFile - v10;
      if ( v11 )
        break;
      ++szExeFile;
    }
    while ( v10 );
    if ( v11 )
      goto LABEL_22;
    v24 = 0;
    hObject = 0;
    v26 = 0;
    v12 = OpenProcess(0x100400u, 0, pe.th32ProcessID);
    if ( !v12 )
      goto LABEL_22;
    if ( !OpenProcessToken(v12, 8u, &hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
        v13);
    if ( !GetTokenInformation(hObject, TokenUser, Sid, 0x58u, &v24) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
        v14);
    if ( !ConvertSidToStringSidW(Sid[0], &v26) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
        v15);
    v16 = StringSid;
    do
    {
      v17 = *(LPWSTR)((char *)v16 + (char *)v26 - (char *)StringSid);
      v18 = *v16 - v17;
      if ( v18 )
        break;
      ++v16;
    }
    while ( v17 );
    if ( !v18 )
      break;
    CloseHandle(hObject);
    LocalFree(v26);
LABEL_22:
    if ( !Process32NextW(v8, &pe) )
      goto LABEL_23;
  }
  *a2 = pe.th32ProcessID;
LABEL_23:
  v19 = 0;
LABEL_30:
  CloseHandle(v8);
LABEL_33:
  CloseHandle(TokenHandle);
  LocalFree(StringSid);
  return v19;
}

```

## disassembly

```asm
0x180068be8  push    rbp
0x180068bea  push    rbx
0x180068beb  push    rsi
0x180068bec  push    rdi
0x180068bed  lea     rbp, [rsp-298h]
0x180068bf5  sub     rsp, 398h
0x180068bfc  mov     rax, cs:__security_cookie
0x180068c03  xor     rax, rsp
0x180068c06  mov     [rbp+2B0h+var_30], rax
0x180068c0d  mov     rsi, rdx
0x180068c10  lea     rcx, [rbp+2B0h+pe]; void *
0x180068c14  mov     ebx, 238h
0x180068c19  xor     edx, edx; Val
0x180068c1b  mov     r8d, ebx; Size
0x180068c1e  call    memset_0
0x180068c23  mov     [rsp+3B0h+TokenHandle], 0
0x180068c2c  mov     [rsp+3B0h+var_380], 0
0x180068c34  mov     [rsp+3B0h+StringSid], 0
0x180068c3d  call    cs:__imp_GetCurrentProcess
0x180068c43  lea     r8, [rsp+3B0h+TokenHandle]; TokenHandle
0x180068c48  mov     edx, 8; DesiredAccess
0x180068c4d  mov     rcx, rax; ProcessHandle
0x180068c50  call    cs:__imp_OpenProcessToken
0x180068c56  test    eax, eax
0x180068c58  jnz     short loc_180068C73
0x180068c5a  mov     rcx, [rbp+2B8h]; this
0x180068c61  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068c68  mov     edx, 0C0h; void *
0x180068c6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068c73  mov     rcx, [rsp+3B0h+TokenHandle]; TokenHandle
0x180068c78  lea     rax, [rsp+3B0h+var_380]
0x180068c7d  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180068c83  mov     [rsp+3B0h+ReturnLength], rax; ReturnLength
0x180068c88  lea     r8, [rbp+2B0h+TokenInformation]; TokenInformation
0x180068c8f  lea     edx, [r9-57h]; TokenInformationClass
0x180068c93  call    cs:__imp_GetTokenInformation
0x180068c99  test    eax, eax
0x180068c9b  jnz     short loc_180068CB6
0x180068c9d  mov     rcx, [rbp+2B8h]; this
0x180068ca4  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068cab  mov     edx, 0C1h; void *
0x180068cb0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068cb6  mov     rcx, [rbp+2B0h+TokenInformation]; Sid
0x180068cbd  lea     rdx, [rsp+3B0h+StringSid]; StringSid
0x180068cc2  call    cs:__imp_ConvertSidToStringSidW
0x180068cc8  test    eax, eax
0x180068cca  jnz     short loc_180068CE5
0x180068ccc  mov     rcx, [rbp+2B8h]; this
0x180068cd3  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068cda  mov     edx, 0C2h; void *
0x180068cdf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068ce5  xor     edx, edx; th32ProcessID
0x180068ce7  lea     ecx, [rdx+2]; dwFlags
0x180068cea  call    cs:__imp_CreateToolhelp32Snapshot
0x180068cf0  mov     rdi, rax
0x180068cf3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068cf7  jz      loc_180068EBF
0x180068cfd  lea     rdx, [rbp+2B0h+pe]; lppe
0x180068d01  mov     [rbp+2B0h+pe.dwSize], ebx
0x180068d04  mov     rcx, rax; hSnapshot
0x180068d07  call    cs:__imp_Process32FirstW
0x180068d0d  test    eax, eax
0x180068d0f  jz      loc_180068E9F
0x180068d15  mov     eax, dword ptr cs:aMicrosoftedgeE+20h; "e"
0x180068d1b  lea     r8, [rsp+3B0h+var_358]
0x180068d20  movups  xmm0, xmmword ptr cs:aMicrosoftedgeE; "MicrosoftEdge.exe"
0x180068d27  mov     [rsp+3B0h+var_338], eax
0x180068d2b  lea     rax, [rbp+2B0h+pe.szExeFile]
0x180068d2f  movups  xmm1, xmmword ptr cs:aMicrosoftedgeE+10h; "tEdge.exe"
0x180068d36  sub     r8, rax
0x180068d39  movups  [rsp+3B0h+var_358], xmm0
0x180068d3e  movups  [rsp+3B0h+var_348], xmm1
0x180068d43  movzx   ecx, word ptr [rax]
0x180068d46  movzx   edx, word ptr [rax+r8]
0x180068d4b  sub     ecx, edx
0x180068d4d  jnz     short loc_180068D57
0x180068d4f  add     rax, 2
0x180068d53  test    edx, edx
0x180068d55  jnz     short loc_180068D43
0x180068d57  test    ecx, ecx
0x180068d59  jnz     loc_180068E40
0x180068d5f  mov     r8d, [rbp+2B0h+pe.th32ProcessID]; dwProcessId
0x180068d63  xor     edx, edx; bInheritHandle
0x180068d65  mov     [rsp+3B0h+var_37C], ecx
0x180068d69  mov     ecx, 100400h; dwDesiredAccess
0x180068d6e  mov     [rsp+3B0h+hObject], 0
0x180068d77  mov     [rsp+3B0h+var_370], 0
0x180068d80  call    cs:__imp_OpenProcess
0x180068d86  test    rax, rax
0x180068d89  jz      loc_180068E40
0x180068d8f  mov     rbx, [rbp+2B8h]
0x180068d96  lea     r8, [rsp+3B0h+hObject]; TokenHandle
0x180068d9b  mov     edx, 8; DesiredAccess
0x180068da0  mov     rcx, rax; ProcessHandle
0x180068da3  call    cs:__imp_OpenProcessToken
0x180068da9  test    eax, eax
0x180068dab  jz      loc_180068E8A
0x180068db1  mov     rcx, [rsp+3B0h+hObject]; TokenHandle
0x180068db6  lea     rax, [rsp+3B0h+var_37C]
0x180068dbb  mov     rbx, [rbp+2B8h]
0x180068dc2  lea     r8, [rbp+2B0h+Sid]; TokenInformation
0x180068dc9  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180068dcf  mov     [rsp+3B0h+ReturnLength], rax; ReturnLength
0x180068dd4  lea     edx, [r9-57h]; TokenInformationClass
0x180068dd8  call    cs:__imp_GetTokenInformation
0x180068dde  test    eax, eax
0x180068de0  jz      loc_180068E75
0x180068de6  mov     rcx, [rbp+2B0h+Sid]; Sid
0x180068ded  lea     rdx, [rsp+3B0h+var_370]; StringSid
0x180068df2  mov     rbx, [rbp+2B8h]
0x180068df9  call    cs:__imp_ConvertSidToStringSidW
0x180068dff  test    eax, eax
0x180068e01  jz      short loc_180068E60
0x180068e03  mov     rax, [rsp+3B0h+StringSid]
0x180068e08  mov     rdx, [rsp+3B0h+var_370]
0x180068e0d  sub     rdx, rax
0x180068e10  movzx   ecx, word ptr [rax]
0x180068e13  movzx   r8d, word ptr [rax+rdx]
0x180068e18  sub     ecx, r8d
0x180068e1b  jnz     short loc_180068E26
0x180068e1d  add     rax, 2
0x180068e21  test    r8d, r8d
0x180068e24  jnz     short loc_180068E10
0x180068e26  test    ecx, ecx
0x180068e28  jz      short loc_180068E59
0x180068e2a  mov     rcx, [rsp+3B0h+hObject]; hObject
0x180068e2f  call    cs:__imp_CloseHandle
0x180068e35  mov     rcx, [rsp+3B0h+var_370]; hMem
0x180068e3a  call    cs:__imp_LocalFree
0x180068e40  lea     rdx, [rbp+2B0h+pe]; lppe
0x180068e44  mov     rcx, rdi; hSnapshot
0x180068e47  call    cs:__imp_Process32NextW
0x180068e4d  test    eax, eax
0x180068e4f  jnz     loc_180068D15
0x180068e55  xor     ebx, ebx
0x180068e57  jmp     short loc_180068EB4
0x180068e59  mov     eax, [rbp+2B0h+pe.th32ProcessID]
0x180068e5c  mov     [rsi], eax
0x180068e5e  jmp     short loc_180068E55
0x180068e60  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068e67  mov     edx, 0DFh; void *
0x180068e6c  mov     rcx, rbx; this
0x180068e6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068e75  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068e7c  mov     edx, 0DEh; void *
0x180068e81  mov     rcx, rbx; this
0x180068e84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068e8a  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068e91  mov     edx, 0DDh; void *
0x180068e96  mov     rcx, rbx; this
0x180068e99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068e9f  call    cs:__imp_GetLastError
0x180068ea5  mov     ebx, eax
0x180068ea7  test    eax, eax
0x180068ea9  jle     short loc_180068EB4
0x180068eab  movzx   ebx, ax
0x180068eae  or      ebx, 80070000h
0x180068eb4  mov     rcx, rdi; hObject
0x180068eb7  call    cs:__imp_CloseHandle
0x180068ebd  jmp     short loc_180068ED4
0x180068ebf  call    cs:__imp_GetLastError
0x180068ec5  mov     ebx, eax
0x180068ec7  test    eax, eax
0x180068ec9  jle     short loc_180068ED4
0x180068ecb  movzx   ebx, ax
0x180068ece  or      ebx, 80070000h
0x180068ed4  mov     rcx, [rsp+3B0h+TokenHandle]; hObject
0x180068ed9  call    cs:__imp_CloseHandle
0x180068edf  mov     rcx, [rsp+3B0h+StringSid]; hMem
0x180068ee4  call    cs:__imp_LocalFree
0x180068eea  mov     eax, ebx
0x180068eec  mov     rcx, [rbp+2B0h+var_30]
0x180068ef3  xor     rcx, rsp; StackCookie
0x180068ef6  call    __security_check_cookie
0x180068efb  add     rsp, 398h
0x180068f02  pop     rdi
0x180068f03  pop     rsi
0x180068f04  pop     rbx
0x180068f05  pop     rbp
0x180068f06  retn
```
