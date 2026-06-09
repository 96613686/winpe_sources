# CUtils::DebugBreakIfAskedEx(ushort *,ushort *)

- ea: `0x180049e54`
- end: `0x18004a168`
- name: `?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z`
- size: `788`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cf00`

## callees

- `0x18000c17c`
- `0x1800282e0`
- `0x180049e54`
- `0x18004e850`
- `0x18004f354`

## import_xrefs

- `ntdll!DbgPrint` at `0x18004a05e`
- `ntdll!DbgPrint` at `0x18004a12b`
- `ntdll!DbgPrint` at `0x18004a143`
- `ntdll!DbgPrint` at `0x18004a05e`
- `ntdll!DbgPrint` at `0x18004a12b`
- `ntdll!DbgPrint` at `0x18004a143`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004a0c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004a0c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a027`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180049f86`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180049f86`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180049f6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180049fa8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004a10f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180049f6d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180049fa8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004a10f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049eb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049eb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049efc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049f43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049fea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049efc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049f43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049f97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049f97`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004a103`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004a103`

## string_xrefs

- `0x18004a13c`: `TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n`
- `0x18004a0d1`: `TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n`

## pseudocode

```c
void __fastcall CUtils::DebugBreakIfAskedEx(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD CurrentProcessId; // eax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CommandLine[256]; // [rsp+F0h] [rbp-10h] BYREF
  BYTE v10[512]; // [rsp+2F0h] [rbp+1F0h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DebugTS", 0, &Type, Data, &cbData) || Type != 4 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"LSMBreakOnStart", 0, &Type, Data, &cbData) || Type != 4 )
        goto LABEL_12;
    }
    if ( *(_DWORD *)Data != 1 )
    {
      if ( *(_DWORD *)Data == 2 )
      {
        if ( !IsDebuggerPresent() )
        {
          cbData = 256;
          if ( RegQueryValueExW(hKey, L"Debugger", 0, &Type, v10, &cbData) || Type != 1 )
          {
            DbgPrint("TERMSRV:*-----------------* Did not find the debugger entry. *-----------------*\n");
          }
          else
          {
            memset(&ProcessInformation, 0, sizeof(ProcessInformation));
            memset_0(&StartupInfo, 0, sizeof(StartupInfo));
            CurrentProcessId = GetCurrentProcessId();
            if ( (int)StringCchPrintfW(CommandLine, 0x100u, L"ntsd -d -G -x -p %d", CurrentProcessId) >= 0 )
            {
              DbgPrint("TERMSRV:*-----------------* Executing:<%ws> *-----------------*\n", CommandLine);
              memset_0(&StartupInfo.cb + 1, 0, 0x64u);
              StartupInfo.cb = 104;
              if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
                while ( !IsDebuggerPresent() )
                  Sleep(0x1F4u);
              }
              else
              {
                DbgPrint("TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n");
              }
            }
          }
          goto LABEL_12;
        }
LABEL_11:
        DebugBreak();
        goto LABEL_12;
      }
      if ( *(_DWORD *)Data != 3 )
      {
LABEL_12:
        RegCloseKey(hKey);
        return;
      }
    }
    if ( !IsDebuggerPresent() && !(unsigned int)CUtils::IsKernelDebuggerAttached() )
      goto LABEL_12;
    goto LABEL_11;
  }
  DbgPrint("TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n");
}

```

## disassembly

```asm
0x180049e54  push    rbp
0x180049e56  lea     rbp, [rsp-400h]
0x180049e5e  sub     rsp, 500h
0x180049e65  mov     rax, cs:__security_cookie
0x180049e6c  xor     rax, rsp
0x180049e6f  mov     [rbp+400h+var_10], rax
0x180049e76  lea     rax, [rsp+500h+hKey]
0x180049e7b  mov     [rsp+500h+hKey], 0
0x180049e84  mov     r9d, 20019h; samDesired
0x180049e8a  mov     [rsp+500h+phkResult], rax; phkResult
0x180049e8f  xor     r8d, r8d; ulOptions
0x180049e92  mov     dword ptr [rsp+500h+Data], 0
0x180049e9a  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180049ea1  mov     [rsp+500h+Type], 0
0x180049ea9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049eb0  mov     [rsp+500h+cbData], 0
0x180049eb8  call    cs:__imp_RegOpenKeyExW
0x180049ebf  nop     dword ptr [rax+rax+00h]
0x180049ec4  test    eax, eax
0x180049ec6  jnz     loc_18004A13C
0x180049ecc  mov     rcx, [rsp+500h+hKey]; hKey
0x180049ed1  lea     rax, [rsp+500h+cbData]
0x180049ed6  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180049edb  lea     r9, [rsp+500h+Type]; lpType
0x180049ee0  lea     rax, [rsp+500h+Data]
0x180049ee5  mov     [rsp+500h+cbData], 4
0x180049eed  xor     r8d, r8d; lpReserved
0x180049ef0  mov     [rsp+500h+phkResult], rax; lpData
0x180049ef5  lea     rdx, aDebugts; "DebugTS"
0x180049efc  call    cs:__imp_RegQueryValueExW
0x180049f03  nop     dword ptr [rax+rax+00h]
0x180049f08  test    eax, eax
0x180049f0a  jnz     short loc_180049F13
0x180049f0c  cmp     [rsp+500h+Type], 4
0x180049f11  jz      short loc_180049F5A
0x180049f13  mov     rcx, [rsp+500h+hKey]; hKey
0x180049f18  lea     rax, [rsp+500h+cbData]
0x180049f1d  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180049f22  lea     r9, [rsp+500h+Type]; lpType
0x180049f27  lea     rax, [rsp+500h+Data]
0x180049f2c  mov     [rsp+500h+cbData], 4
0x180049f34  xor     r8d, r8d; lpReserved
0x180049f37  mov     [rsp+500h+phkResult], rax; lpData
0x180049f3c  lea     rdx, aLsmbreakonstar; "LSMBreakOnStart"
0x180049f43  call    cs:__imp_RegQueryValueExW
0x180049f4a  nop     dword ptr [rax+rax+00h]
0x180049f4f  test    eax, eax
0x180049f51  jnz     short loc_180049F92
0x180049f53  cmp     [rsp+500h+Type], 4
0x180049f58  jnz     short loc_180049F92
0x180049f5a  mov     eax, dword ptr [rsp+500h+Data]
0x180049f5e  sub     eax, 1
0x180049f61  jz      short loc_180049F6D
0x180049f63  sub     eax, 1
0x180049f66  jz      short loc_180049FA8
0x180049f68  cmp     eax, 1
0x180049f6b  jnz     short loc_180049F92
0x180049f6d  call    cs:__imp_IsDebuggerPresent
0x180049f74  nop     dword ptr [rax+rax+00h]
0x180049f79  test    eax, eax
0x180049f7b  jnz     short loc_180049F86
0x180049f7d  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x180049f82  test    eax, eax
0x180049f84  jz      short loc_180049F92
0x180049f86  call    cs:__imp_DebugBreak
0x180049f8d  nop     dword ptr [rax+rax+00h]
0x180049f92  mov     rcx, [rsp+500h+hKey]; hKey
0x180049f97  call    cs:__imp_RegCloseKey
0x180049f9e  nop     dword ptr [rax+rax+00h]
0x180049fa3  jmp     loc_18004A14F
0x180049fa8  call    cs:__imp_IsDebuggerPresent
0x180049faf  nop     dword ptr [rax+rax+00h]
0x180049fb4  test    eax, eax
0x180049fb6  jnz     short loc_180049F86
0x180049fb8  mov     rcx, [rsp+500h+hKey]; hKey
0x180049fbd  lea     rax, [rsp+500h+cbData]
0x180049fc2  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180049fc7  lea     r9, [rsp+500h+Type]; lpType
0x180049fcc  lea     rax, [rbp+400h+var_210]
0x180049fd3  mov     [rsp+500h+cbData], 100h
0x180049fdb  xor     r8d, r8d; lpReserved
0x180049fde  mov     [rsp+500h+phkResult], rax; lpData
0x180049fe3  lea     rdx, aDebugger; "Debugger"
0x180049fea  call    cs:__imp_RegQueryValueExW
0x180049ff1  nop     dword ptr [rax+rax+00h]
0x180049ff6  test    eax, eax
0x180049ff8  jnz     loc_18004A124
0x180049ffe  cmp     [rsp+500h+Type], 1
0x18004a003  jnz     loc_18004A124
0x18004a009  xor     eax, eax
0x18004a00b  lea     rcx, [rbp+400h+StartupInfo]; void *
0x18004a00f  xorps   xmm0, xmm0
0x18004a012  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x18004a017  xor     edx, edx; Val
0x18004a019  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x18004a01e  lea     r8d, [rax+68h]; Size
0x18004a022  call    memset_0
0x18004a027  call    cs:__imp_GetCurrentProcessId
0x18004a02e  nop     dword ptr [rax+rax+00h]
0x18004a033  lea     r8, aNtsdDGXPD; "ntsd -d -G -x -p %d"
0x18004a03a  mov     edx, 100h; unsigned __int64
0x18004a03f  mov     r9d, eax
0x18004a042  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x18004a046  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a04b  test    eax, eax
0x18004a04d  js      loc_180049F92
0x18004a053  lea     rdx, [rbp+400h+CommandLine]
0x18004a057  lea     rcx, aTermsrvExecuti; "TERMSRV:*-----------------* Executing:<"...
0x18004a05e  call    cs:__imp_DbgPrint
0x18004a065  nop     dword ptr [rax+rax+00h]
0x18004a06a  xor     edx, edx; Val
0x18004a06c  lea     rcx, [rbp+400h+StartupInfo+4]; void *
0x18004a070  lea     r8d, [rdx+64h]; Size
0x18004a074  call    memset_0
0x18004a079  lea     rax, [rsp+500h+ProcessInformation]
0x18004a07e  mov     [rbp+400h+StartupInfo.cb], 68h ; 'h'
0x18004a085  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x18004a08a  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x18004a08e  lea     rax, [rbp+400h+StartupInfo]
0x18004a092  xor     r9d, r9d; lpThreadAttributes
0x18004a095  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x18004a09a  xor     r8d, r8d; lpProcessAttributes
0x18004a09d  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18004a0a6  xor     ecx, ecx; lpApplicationName
0x18004a0a8  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x18004a0b1  mov     dword ptr [rsp+500h+lpcbData], 0; dwCreationFlags
0x18004a0b9  mov     dword ptr [rsp+500h+phkResult], 0; bInheritHandles
0x18004a0c1  call    cs:__imp_CreateProcessW
0x18004a0c8  nop     dword ptr [rax+rax+00h]
0x18004a0cd  test    eax, eax
0x18004a0cf  jnz     short loc_18004A0DA
0x18004a0d1  lea     rcx, aTermsrvTermsrv; "TERMSRV:*-----------------* TERMSRV:Cre"...
0x18004a0d8  jmp     short loc_18004A12B
0x18004a0da  mov     rcx, [rsp+500h+ProcessInformation.hProcess]; hObject
0x18004a0df  call    cs:__imp_CloseHandle
0x18004a0e6  nop     dword ptr [rax+rax+00h]
0x18004a0eb  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x18004a0f0  call    cs:__imp_CloseHandle
0x18004a0f7  nop     dword ptr [rax+rax+00h]
0x18004a0fc  jmp     short loc_18004A10F
0x18004a0fe  mov     ecx, 1F4h; dwMilliseconds
0x18004a103  call    cs:__imp_Sleep
0x18004a10a  nop     dword ptr [rax+rax+00h]
0x18004a10f  call    cs:__imp_IsDebuggerPresent
0x18004a116  nop     dword ptr [rax+rax+00h]
0x18004a11b  test    eax, eax
0x18004a11d  jz      short loc_18004A0FE
0x18004a11f  jmp     loc_180049F92
0x18004a124  lea     rcx, aTermsrvDidNotF; "TERMSRV:*-----------------* Did not fin"...
0x18004a12b  call    cs:__imp_DbgPrint
0x18004a132  nop     dword ptr [rax+rax+00h]
0x18004a137  jmp     loc_180049F92
0x18004a13c  lea     rcx, aTermsrvCouldNo; "TERMSRV:*-----------------* Could not o"...
0x18004a143  call    cs:__imp_DbgPrint
0x18004a14a  nop     dword ptr [rax+rax+00h]
0x18004a14f  mov     rcx, [rbp+400h+var_10]
0x18004a156  xor     rcx, rsp; StackCookie
0x18004a159  call    __security_check_cookie
0x18004a15e  add     rsp, 500h
0x18004a165  pop     rbp
0x18004a166  retn
```
