# CUtils::DebugBreakIfAskedEx(ushort *,ushort *)

- ea: `0x180046dec`
- end: `0x180047099`
- name: `?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z`
- size: `685`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ae4c`

## callees

- `0x180018200`
- `0x1800261f4`
- `0x180046dec`
- `0x18004b460`
- `0x18004bf44`

## import_xrefs

- `ntdll!DbgPrint` at `0x180046fc0`
- `ntdll!DbgPrint` at `0x180047069`
- `ntdll!DbgPrint` at `0x18004707b`
- `ntdll!DbgPrint` at `0x180046fc0`
- `ntdll!DbgPrint` at `0x180047069`
- `ntdll!DbgPrint` at `0x18004707b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004701d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18004701d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046f8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046f8f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180046f06`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180046f06`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180046ef3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180046f1c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047053`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180046ef3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180046f1c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047035`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047035`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047040`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046e50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046e50`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046e8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046ecf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046f58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046e8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046ecf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046f58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046f11`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004704d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004704d`

## string_xrefs

- `0x180047074`: `TERMSRV:*-----------------* Could not open termsrv registry *-----------------*\n`
- `0x180047027`: `TERMSRV:*-----------------* TERMSRV:CreateProcess failed *-----------------*\n`

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
0x180046dec  push    rbp
0x180046dee  lea     rbp, [rsp-400h]
0x180046df6  sub     rsp, 500h
0x180046dfd  mov     rax, cs:__security_cookie
0x180046e04  xor     rax, rsp
0x180046e07  mov     [rbp+400h+var_10], rax
0x180046e0e  lea     rax, [rsp+500h+hKey]
0x180046e13  mov     [rsp+500h+hKey], 0
0x180046e1c  mov     r9d, 20019h; samDesired
0x180046e22  mov     [rsp+500h+phkResult], rax; phkResult
0x180046e27  xor     r8d, r8d; ulOptions
0x180046e2a  mov     dword ptr [rsp+500h+Data], 0
0x180046e32  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180046e39  mov     [rsp+500h+Type], 0
0x180046e41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046e48  mov     [rsp+500h+cbData], 0
0x180046e50  call    cs:__imp_RegOpenKeyExW
0x180046e56  test    eax, eax
0x180046e58  jnz     loc_180047074
0x180046e5e  mov     rcx, [rsp+500h+hKey]; hKey
0x180046e63  lea     rax, [rsp+500h+cbData]
0x180046e68  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180046e6d  lea     r9, [rsp+500h+Type]; lpType
0x180046e72  lea     rax, [rsp+500h+Data]
0x180046e77  mov     [rsp+500h+cbData], 4
0x180046e7f  xor     r8d, r8d; lpReserved
0x180046e82  mov     [rsp+500h+phkResult], rax; lpData
0x180046e87  lea     rdx, aDebugts; "DebugTS"
0x180046e8e  call    cs:__imp_RegQueryValueExW
0x180046e94  test    eax, eax
0x180046e96  jnz     short loc_180046E9F
0x180046e98  cmp     [rsp+500h+Type], 4
0x180046e9d  jz      short loc_180046EE0
0x180046e9f  mov     rcx, [rsp+500h+hKey]; hKey
0x180046ea4  lea     rax, [rsp+500h+cbData]
0x180046ea9  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180046eae  lea     r9, [rsp+500h+Type]; lpType
0x180046eb3  lea     rax, [rsp+500h+Data]
0x180046eb8  mov     [rsp+500h+cbData], 4
0x180046ec0  xor     r8d, r8d; lpReserved
0x180046ec3  mov     [rsp+500h+phkResult], rax; lpData
0x180046ec8  lea     rdx, aLsmbreakonstar; "LSMBreakOnStart"
0x180046ecf  call    cs:__imp_RegQueryValueExW
0x180046ed5  test    eax, eax
0x180046ed7  jnz     short loc_180046F0C
0x180046ed9  cmp     [rsp+500h+Type], 4
0x180046ede  jnz     short loc_180046F0C
0x180046ee0  mov     eax, dword ptr [rsp+500h+Data]
0x180046ee4  sub     eax, 1
0x180046ee7  jz      short loc_180046EF3
0x180046ee9  sub     eax, 1
0x180046eec  jz      short loc_180046F1C
0x180046eee  cmp     eax, 1
0x180046ef1  jnz     short loc_180046F0C
0x180046ef3  call    cs:__imp_IsDebuggerPresent
0x180046ef9  test    eax, eax
0x180046efb  jnz     short loc_180046F06
0x180046efd  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x180046f02  test    eax, eax
0x180046f04  jz      short loc_180046F0C
0x180046f06  call    cs:__imp_DebugBreak
0x180046f0c  mov     rcx, [rsp+500h+hKey]; hKey
0x180046f11  call    cs:__imp_RegCloseKey
0x180046f17  jmp     loc_180047081
0x180046f1c  call    cs:__imp_IsDebuggerPresent
0x180046f22  test    eax, eax
0x180046f24  jnz     short loc_180046F06
0x180046f26  mov     rcx, [rsp+500h+hKey]; hKey
0x180046f2b  lea     rax, [rsp+500h+cbData]
0x180046f30  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180046f35  lea     r9, [rsp+500h+Type]; lpType
0x180046f3a  lea     rax, [rbp+400h+var_210]
0x180046f41  mov     [rsp+500h+cbData], 100h
0x180046f49  xor     r8d, r8d; lpReserved
0x180046f4c  mov     [rsp+500h+phkResult], rax; lpData
0x180046f51  lea     rdx, aDebugger; "Debugger"
0x180046f58  call    cs:__imp_RegQueryValueExW
0x180046f5e  test    eax, eax
0x180046f60  jnz     loc_180047062
0x180046f66  cmp     [rsp+500h+Type], 1
0x180046f6b  jnz     loc_180047062
0x180046f71  xor     eax, eax
0x180046f73  lea     rcx, [rbp+400h+StartupInfo]; void *
0x180046f77  xorps   xmm0, xmm0
0x180046f7a  mov     qword ptr [rsp+500h+ProcessInformation.dwProcessId], rax
0x180046f7f  xor     edx, edx; Val
0x180046f81  movups  xmmword ptr [rsp+500h+ProcessInformation.hProcess], xmm0
0x180046f86  lea     r8d, [rax+68h]; Size
0x180046f8a  call    memset_0
0x180046f8f  call    cs:__imp_GetCurrentProcessId
0x180046f95  lea     r8, aNtsdDGXPD; "ntsd -d -G -x -p %d"
0x180046f9c  mov     edx, 100h; unsigned __int64
0x180046fa1  mov     r9d, eax
0x180046fa4  lea     rcx, [rbp+400h+CommandLine]; unsigned __int16 *
0x180046fa8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046fad  test    eax, eax
0x180046faf  js      loc_180046F0C
0x180046fb5  lea     rdx, [rbp+400h+CommandLine]
0x180046fb9  lea     rcx, aTermsrvExecuti; "TERMSRV:*-----------------* Executing:<"...
0x180046fc0  call    cs:__imp_DbgPrint
0x180046fc6  xor     edx, edx; Val
0x180046fc8  lea     rcx, [rbp+400h+StartupInfo+4]; void *
0x180046fcc  lea     r8d, [rdx+64h]; Size
0x180046fd0  call    memset_0
0x180046fd5  lea     rax, [rsp+500h+ProcessInformation]
0x180046fda  mov     [rbp+400h+StartupInfo.cb], 68h ; 'h'
0x180046fe1  mov     [rsp+500h+lpProcessInformation], rax; lpProcessInformation
0x180046fe6  lea     rdx, [rbp+400h+CommandLine]; lpCommandLine
0x180046fea  lea     rax, [rbp+400h+StartupInfo]
0x180046fee  xor     r9d, r9d; lpThreadAttributes
0x180046ff1  mov     [rsp+500h+lpStartupInfo], rax; lpStartupInfo
0x180046ff6  xor     r8d, r8d; lpProcessAttributes
0x180046ff9  mov     [rsp+500h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180047002  xor     ecx, ecx; lpApplicationName
0x180047004  mov     [rsp+500h+lpEnvironment], 0; lpEnvironment
0x18004700d  mov     dword ptr [rsp+500h+lpcbData], 0; dwCreationFlags
0x180047015  mov     dword ptr [rsp+500h+phkResult], 0; bInheritHandles
0x18004701d  call    cs:__imp_CreateProcessW
0x180047023  test    eax, eax
0x180047025  jnz     short loc_180047030
0x180047027  lea     rcx, aTermsrvTermsrv; "TERMSRV:*-----------------* TERMSRV:Cre"...
0x18004702e  jmp     short loc_180047069
0x180047030  mov     rcx, [rsp+500h+ProcessInformation.hProcess]; hObject
0x180047035  call    cs:__imp_CloseHandle
0x18004703b  mov     rcx, [rsp+500h+ProcessInformation.hThread]; hObject
0x180047040  call    cs:__imp_CloseHandle
0x180047046  jmp     short loc_180047053
0x180047048  mov     ecx, 1F4h; dwMilliseconds
0x18004704d  call    cs:__imp_Sleep
0x180047053  call    cs:__imp_IsDebuggerPresent
0x180047059  test    eax, eax
0x18004705b  jz      short loc_180047048
0x18004705d  jmp     loc_180046F0C
0x180047062  lea     rcx, aTermsrvDidNotF; "TERMSRV:*-----------------* Did not fin"...
0x180047069  call    cs:__imp_DbgPrint
0x18004706f  jmp     loc_180046F0C
0x180047074  lea     rcx, aTermsrvCouldNo; "TERMSRV:*-----------------* Could not o"...
0x18004707b  call    cs:__imp_DbgPrint
0x180047081  mov     rcx, [rbp+400h+var_10]
0x180047088  xor     rcx, rsp; StackCookie
0x18004708b  call    __security_check_cookie
0x180047090  add     rsp, 500h
0x180047097  pop     rbp
0x180047098  retn
```
