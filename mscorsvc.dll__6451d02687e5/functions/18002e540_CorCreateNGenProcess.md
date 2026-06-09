# CorCreateNGenProcess

- ea: `0x18002e540`
- end: `0x18002e78c`
- name: `CorCreateNGenProcess`
- size: `588`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, __int64, HANDLE *, HANDLE *, DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022344`

## callees

- `0x18002e540`
- `0x18003dc30`
- `0x18003e73c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18002e616`
- `ADVAPI32!OpenProcessToken` at `0x18002e616`
- `ADVAPI32!DuplicateTokenEx` at `0x18002e648`
- `ADVAPI32!DuplicateTokenEx` at `0x18002e648`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002e661`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002e661`
- `ADVAPI32!SetTokenInformation` at `0x18002e699`
- `ADVAPI32!SetTokenInformation` at `0x18002e699`
- `ADVAPI32!GetLengthSid` at `0x18002e681`
- `ADVAPI32!GetLengthSid` at `0x18002e681`
- `ADVAPI32!CreateProcessAsUserW` at `0x18002e6df`
- `ADVAPI32!CreateProcessAsUserW` at `0x18002e6df`
- `KERNEL32!GetCurrentProcess` at `0x18002e603`
- `KERNEL32!GetCurrentProcess` at `0x18002e603`
- `KERNEL32!LocalFree` at `0x18002e73d`
- `KERNEL32!LocalFree` at `0x18002e73d`
- `KERNEL32!CreateProcessW` at `0x18002e71a`
- `KERNEL32!CreateProcessW` at `0x18002e71a`
- `KERNEL32!CloseHandle` at `0x18002e74d`
- `KERNEL32!CloseHandle` at `0x18002e75d`
- `KERNEL32!CloseHandle` at `0x18002e74d`
- `KERNEL32!CloseHandle` at `0x18002e75d`

## pseudocode

```c
__int64 __fastcall CorCreateNGenProcess(
        LPCWSTR lpApplicationName,
        LPWSTR lpCommandLine,
        __int64 a3,
        HANDLE *a4,
        HANDLE *a5,
        DWORD *a6)
{
  __int64 v10; // rax
  HANDLE CurrentProcess; // rax
  unsigned int v12; // ebx
  DWORD LengthSid; // eax
  BOOL v14; // eax
  PSID v15; // rcx
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  __int128 TokenInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR StringSid[12]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v24; // [rsp+128h] [rbp+28h]

  TokenHandle = 0;
  hToken = 0;
  Sid = 0;
  TokenInformation = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  *a5 = 0;
  *a4 = 0;
  *a6 = 0;
  if ( !a3 )
    goto LABEL_10;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a3 + 2 * v10) );
  if ( !v10 )
  {
LABEL_10:
    v14 = CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation);
    goto LABEL_11;
  }
  wcscpy(StringSid, L"S-1-16-8192");
  v24 = 0;
  CurrentProcess = GetCurrentProcess();
  v12 = OpenProcessToken(CurrentProcess, 0x8Bu, &TokenHandle);
  if ( v12 )
  {
    v12 = DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenPrimary, &hToken);
    if ( v12 )
    {
      v12 = ConvertStringSidToSidW(StringSid, &Sid);
      if ( v12 )
      {
        *(_QWORD *)&TokenInformation = Sid;
        DWORD2(TokenInformation) = 32;
        LengthSid = GetLengthSid(Sid);
        v12 = SetTokenInformation(hToken, TokenIntegrityLevel, &TokenInformation, LengthSid + 16);
        if ( v12 )
        {
          v14 = CreateProcessAsUserW(
                  hToken,
                  lpApplicationName,
                  lpCommandLine,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  &StartupInfo,
                  &ProcessInformation);
LABEL_11:
          v12 = v14;
        }
      }
    }
  }
  v15 = Sid;
  *a5 = ProcessInformation.hThread;
  *a4 = ProcessInformation.hProcess;
  *a6 = ProcessInformation.dwProcessId;
  LocalFree(v15);
  if ( hToken )
    CloseHandle(hToken);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v12;
}

```

## disassembly

```asm
0x18002e540  mov     [rsp-8+arg_10], rbx
0x18002e545  push    rbp
0x18002e546  push    rsi
0x18002e547  push    rdi
0x18002e548  push    r12
0x18002e54a  push    r13
0x18002e54c  push    r14
0x18002e54e  push    r15
0x18002e550  lea     rbp, [rsp-40h]
0x18002e555  sub     rsp, 140h
0x18002e55c  mov     rax, cs:__security_cookie
0x18002e563  xor     rax, rsp
0x18002e566  mov     [rbp+70h+var_38], rax
0x18002e56a  mov     r15, [rbp+70h+arg_20]
0x18002e571  xor     r13d, r13d
0x18002e574  mov     r12, [rbp+70h+arg_28]
0x18002e57b  mov     rbx, r8
0x18002e57e  mov     rsi, rdx
0x18002e581  mov     [rsp+170h+TokenHandle], r13
0x18002e586  mov     rdi, rcx
0x18002e589  mov     [rsp+170h+hToken], r13
0x18002e58e  xorps   xmm0, xmm0
0x18002e591  mov     [rsp+170h+Sid], r13
0x18002e596  xorps   xmm1, xmm1
0x18002e599  lea     r8d, [r13+68h]; Size
0x18002e59d  xor     eax, eax
0x18002e59f  lea     rcx, [rbp+70h+StartupInfo]; void *
0x18002e5a3  xor     edx, edx; Val
0x18002e5a5  mov     qword ptr [rbp+70h+ProcessInformation.dwProcessId], rax
0x18002e5a9  mov     r14, r9
0x18002e5ac  movups  [rbp+70h+TokenInformation], xmm0
0x18002e5b0  movups  xmmword ptr [rsp+170h+ProcessInformation.hProcess], xmm1
0x18002e5b5  call    memset_0
0x18002e5ba  mov     [r15], r13
0x18002e5bd  mov     [r14], r13
0x18002e5c0  mov     [r12], r13d
0x18002e5c4  test    rbx, rbx
0x18002e5c7  jz      loc_18002E6E7
0x18002e5cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e5d1  inc     rax
0x18002e5d4  cmp     [rbx+rax*2], r13w
0x18002e5d9  jnz     short loc_18002E5D1
0x18002e5db  test    rax, rax
0x18002e5de  jz      loc_18002E6E7
0x18002e5e4  movups  xmm0, xmmword ptr cs:aS1168192; "S-1-16-8192"
0x18002e5eb  movsd   xmm1, qword ptr cs:aS1168192+10h; "192"
0x18002e5f3  movups  xmmword ptr [rbp+70h+StringSid], xmm0
0x18002e5f7  xorps   xmm0, xmm0
0x18002e5fa  movsd   [rbp+70h+var_50], xmm1
0x18002e5ff  movups  [rbp+70h+var_48], xmm0
0x18002e603  call    cs:__imp_GetCurrentProcess
0x18002e609  lea     r8, [rsp+170h+TokenHandle]; TokenHandle
0x18002e60e  mov     edx, 8Bh; DesiredAccess
0x18002e613  mov     rcx, rax; ProcessHandle
0x18002e616  call    cs:__imp_OpenProcessToken
0x18002e61c  mov     ebx, eax
0x18002e61e  test    eax, eax
0x18002e620  jz      loc_18002E722
0x18002e626  mov     rcx, [rsp+170h+TokenHandle]; hExistingToken
0x18002e62b  lea     rax, [rsp+170h+hToken]
0x18002e630  mov     [rsp+170h+phNewToken], rax; phNewToken
0x18002e635  mov     r9d, 2; ImpersonationLevel
0x18002e63b  xor     r8d, r8d; lpTokenAttributes
0x18002e63e  mov     [rsp+170h+TokenType], 1; TokenType
0x18002e646  xor     edx, edx; dwDesiredAccess
0x18002e648  call    cs:__imp_DuplicateTokenEx
0x18002e64e  mov     ebx, eax
0x18002e650  test    eax, eax
0x18002e652  jz      loc_18002E722
0x18002e658  lea     rdx, [rsp+170h+Sid]; Sid
0x18002e65d  lea     rcx, [rbp+70h+StringSid]; StringSid
0x18002e661  call    cs:__imp_ConvertStringSidToSidW
0x18002e667  mov     ebx, eax
0x18002e669  test    eax, eax
0x18002e66b  jz      loc_18002E722
0x18002e671  mov     rcx, [rsp+170h+Sid]; pSid
0x18002e676  mov     qword ptr [rbp+70h+TokenInformation], rcx
0x18002e67a  mov     dword ptr [rbp+70h+TokenInformation+8], 20h ; ' '
0x18002e681  call    cs:__imp_GetLengthSid
0x18002e687  mov     rcx, [rsp+170h+hToken]; TokenHandle
0x18002e68c  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x18002e690  mov     edx, 19h; TokenInformationClass
0x18002e695  lea     r9d, [rax+10h]; TokenInformationLength
0x18002e699  call    cs:__imp_SetTokenInformation
0x18002e69f  mov     ebx, eax
0x18002e6a1  test    eax, eax
0x18002e6a3  jz      short loc_18002E722
0x18002e6a5  mov     rcx, [rsp+170h+hToken]; hToken
0x18002e6aa  lea     rax, [rsp+170h+ProcessInformation]
0x18002e6af  mov     [rsp+170h+lpProcessInformation], rax; lpProcessInformation
0x18002e6b4  xor     r9d, r9d; lpProcessAttributes
0x18002e6b7  lea     rax, [rbp+70h+StartupInfo]
0x18002e6bb  mov     r8, rsi; lpCommandLine
0x18002e6be  mov     [rsp+170h+lpStartupInfo], rax; lpStartupInfo
0x18002e6c3  mov     rdx, rdi; lpApplicationName
0x18002e6c6  mov     [rsp+170h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18002e6cb  mov     [rsp+170h+lpEnvironment], r13; lpEnvironment
0x18002e6d0  mov     [rsp+170h+dwCreationFlags], r13d; dwCreationFlags
0x18002e6d5  mov     dword ptr [rsp+170h+phNewToken], r13d; bInheritHandles
0x18002e6da  mov     qword ptr [rsp+170h+TokenType], r13; lpThreadAttributes
0x18002e6df  call    cs:__imp_CreateProcessAsUserW
0x18002e6e5  jmp     short loc_18002E720
0x18002e6e7  lea     rax, [rsp+170h+ProcessInformation]
0x18002e6ec  xor     r9d, r9d; lpThreadAttributes
0x18002e6ef  mov     [rsp+170h+lpStartupInfo], rax; lpProcessInformation
0x18002e6f4  xor     r8d, r8d; lpProcessAttributes
0x18002e6f7  lea     rax, [rbp+70h+StartupInfo]
0x18002e6fb  mov     rdx, rsi; lpCommandLine
0x18002e6fe  mov     [rsp+170h+lpCurrentDirectory], rax; lpStartupInfo
0x18002e703  mov     rcx, rdi; lpApplicationName
0x18002e706  mov     [rsp+170h+lpEnvironment], r13; lpCurrentDirectory
0x18002e70b  mov     qword ptr [rsp+170h+dwCreationFlags], r13; lpEnvironment
0x18002e710  mov     dword ptr [rsp+170h+phNewToken], r13d; dwCreationFlags
0x18002e715  mov     [rsp+170h+TokenType], r13d; bInheritHandles
0x18002e71a  call    cs:__imp_CreateProcessW
0x18002e720  mov     ebx, eax
0x18002e722  mov     rax, [rbp+70h+ProcessInformation.hThread]
0x18002e726  mov     rcx, [rsp+170h+Sid]; hMem
0x18002e72b  mov     [r15], rax
0x18002e72e  mov     rax, [rsp+170h+ProcessInformation.hProcess]
0x18002e733  mov     [r14], rax
0x18002e736  mov     eax, [rbp+70h+ProcessInformation.dwProcessId]
0x18002e739  mov     [r12], eax
0x18002e73d  call    cs:__imp_LocalFree
0x18002e743  mov     rcx, [rsp+170h+hToken]; hObject
0x18002e748  test    rcx, rcx
0x18002e74b  jz      short loc_18002E753
0x18002e74d  call    cs:__imp_CloseHandle
0x18002e753  mov     rcx, [rsp+170h+TokenHandle]; hObject
0x18002e758  test    rcx, rcx
0x18002e75b  jz      short loc_18002E763
0x18002e75d  call    cs:__imp_CloseHandle
0x18002e763  mov     eax, ebx
0x18002e765  mov     rcx, [rbp+70h+var_38]
0x18002e769  xor     rcx, rsp; StackCookie
0x18002e76c  call    __security_check_cookie
0x18002e771  mov     rbx, [rsp+170h+arg_10]
0x18002e779  add     rsp, 140h
0x18002e780  pop     r15
0x18002e782  pop     r14
0x18002e784  pop     r13
0x18002e786  pop     r12
0x18002e788  pop     rdi
0x18002e789  pop     rsi
0x18002e78a  pop     rbp
0x18002e78b  retn
```
