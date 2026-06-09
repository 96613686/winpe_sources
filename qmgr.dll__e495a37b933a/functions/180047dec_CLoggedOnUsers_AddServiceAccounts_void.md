# CLoggedOnUsers::AddServiceAccounts(void)

- ea: `0x180047dec`
- end: `0x1800480d0`
- name: `?AddServiceAccounts@CLoggedOnUsers@@QEAAJXZ`
- size: `740`
- prototype: `__int64 __fastcall(CLoggedOnUsers *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180047114`

## callees

- `0x18000b4d0`
- `0x180034760`
- `0x180047dec`
- `0x1800490d0`
- `0x1800736e0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800c4bfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047e3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047e3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047e4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180047e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004802f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047f43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004802f`
- `SspiCli!LogonUserExExW` at `0x180047f20`
- `SspiCli!LogonUserExExW` at `0x18004800c`
- `SspiCli!LogonUserExExW` at `0x180047f20`
- `SspiCli!LogonUserExExW` at `0x18004800c`

## string_xrefs

- `0x180047f19`: `LocalService`
- `0x180048005`: `NetworkService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLoggedOnUsers::AddServiceAccounts(CLoggedOnUsers *this)
{
  int v2; // edi
  HANDLE CurrentProcess; // rax
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  EVENT_LOG *v7; // rcx
  signed int v8; // eax
  EVENT_LOG *v9; // rcx
  TaskScheduler *v11; // [rsp+60h] [rbp-10h] BYREF
  int v12; // [rsp+68h] [rbp-8h]
  unsigned int v13; // [rsp+A0h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+38h] BYREF

  v13 = 0;
  v11 = *(TaskScheduler **)this;
  v2 = 0;
  v12 = 0;
  if ( *((_DWORD *)v11 + 14) != GetCurrentThreadId() )
  {
    v2 = 1;
    v12 = 1;
    TaskScheduler::LockWriter(v11, 0);
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v4 = CLoggedOnUsers::LogonService(this, TokenHandle, &v13, 0);
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v4 >= 0 )
  {
    if ( (unsigned int)LogonUserExExW(
                         L"LocalService",
                         L"NT AUTHORITY",
                         &qword_18011AC70,
                         5,
                         0,
                         0,
                         &TokenHandle,
                         0,
                         0,
                         0,
                         0) )
    {
      v4 = CLoggedOnUsers::LogonService(this, TokenHandle, &v13, 0);
      CloseHandle(TokenHandle);
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    if ( v4 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
          (unsigned int)v4);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v4 != -2147023570 )
        goto LABEL_39;
      if ( v7 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v7 + 2), 36, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids);
    }
    if ( (unsigned int)LogonUserExExW(
                         L"NetworkService",
                         L"NT AUTHORITY",
                         &qword_18011AC70,
                         5,
                         0,
                         0,
                         &TokenHandle,
                         0,
                         0,
                         0,
                         0) )
    {
      v4 = CLoggedOnUsers::LogonService(this, TokenHandle, &v13, 0);
      CloseHandle(TokenHandle);
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
    }
    if ( v4 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
          (unsigned int)v4);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v4 != -2147023570 )
        goto LABEL_39;
      if ( v9 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)v9 + 2), 38, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids);
    }
    CLoggedOnUsers::TryAddContainerSpecificServiceAccounts(this);
    v4 = 0;
LABEL_39:
    HoldWriterLock::~HoldWriterLock((HoldWriterLock *)&v11);
    return (unsigned int)v4;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
      (unsigned int)v4);
  for ( ; v2; --v2 )
    TaskScheduler::UnlockWriter(v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047dec  mov     [rsp-28h+arg_10], rbx
0x180047df1  push    rbp
0x180047df2  push    rdi
0x180047df3  push    r13
0x180047df5  push    r14
0x180047df7  push    r15
0x180047df9  mov     rbp, rsp
0x180047dfc  sub     rsp, 70h
0x180047e00  mov     r13, rcx
0x180047e03  mov     [rbp+arg_0], 0
0x180047e0a  mov     r15, [rcx]
0x180047e0d  mov     [rbp+var_10], r15
0x180047e11  xor     edi, edi
0x180047e13  mov     [rbp+var_8], edi
0x180047e16  call    cs:__imp_GetCurrentThreadId
0x180047e1c  cmp     [r15+38h], eax
0x180047e20  jz      short loc_180047E35
0x180047e22  mov     edi, 1
0x180047e27  mov     [rbp+var_8], edi
0x180047e2a  xor     edx, edx; void *
0x180047e2c  mov     rcx, r15; this
0x180047e2f  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x180047e34  nop
0x180047e35  mov     [rbp+TokenHandle], 0
0x180047e3d  call    cs:__imp_GetCurrentProcess
0x180047e43  mov     rcx, rax; ProcessHandle
0x180047e46  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180047e4a  mov     edx, 0Ah; DesiredAccess
0x180047e4f  call    cs:__imp_OpenProcessToken
0x180047e55  test    eax, eax
0x180047e57  jz      short loc_180047E7A
0x180047e59  xor     r9d, r9d; bool
0x180047e5c  lea     r8, [rbp+arg_0]; unsigned int *
0x180047e60  mov     rdx, [rbp+TokenHandle]; void *
0x180047e64  mov     rcx, r13; this
0x180047e67  call    ?LogonService@CLoggedOnUsers@@QEAAJPEAXPEAK_N@Z; CLoggedOnUsers::LogonService(void *,ulong *,bool)
0x180047e6c  mov     ebx, eax
0x180047e6e  mov     rcx, [rbp+TokenHandle]; hObject
0x180047e72  call    cs:__imp_CloseHandle
0x180047e78  jmp     short loc_180047E8F
0x180047e7a  call    cs:__imp_GetLastError
0x180047e80  mov     ebx, eax
0x180047e82  test    eax, eax
0x180047e84  jle     short loc_180047E8F
0x180047e86  movzx   ebx, ax
0x180047e89  or      ebx, 80070000h
0x180047e8f  test    ebx, ebx
0x180047e91  jns     short loc_180047EDF
0x180047e93  lea     r14, WPP_GLOBAL_Control
0x180047e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ea1  cmp     rcx, r14
0x180047ea4  jz      short loc_180047EC5
0x180047ea6  test    byte ptr [rcx+1Ch], 2
0x180047eaa  jz      short loc_180047EC5
0x180047eac  mov     edx, 22h ; '"'
0x180047eb1  mov     r9d, ebx
0x180047eb4  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x180047ebb  mov     rcx, [rcx+10h]
0x180047ebf  call    WPP_SF_d
0x180047ec4  nop
0x180047ec5  test    edi, edi
0x180047ec7  jz      loc_1800480B9
0x180047ecd  mov     rcx, r15; this
0x180047ed0  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180047ed5  sub     edi, 1
0x180047ed8  jnz     short loc_180047ECD
0x180047eda  jmp     loc_1800480B9
0x180047edf  xor     edi, edi
0x180047ee1  mov     [rsp+70h+var_20], rdi
0x180047ee6  mov     [rsp+70h+var_28], rdi
0x180047eeb  mov     [rsp+70h+var_30], rdi
0x180047ef0  mov     [rsp+70h+var_38], rdi
0x180047ef5  lea     rax, [rbp+TokenHandle]
0x180047ef9  mov     [rsp+70h+var_40], rax
0x180047efe  mov     [rsp+70h+var_48], rdi
0x180047f03  mov     [rsp+70h+var_50], edi
0x180047f07  lea     r9d, [rdi+5]
0x180047f0b  lea     r8, qword_18011AC70
0x180047f12  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x180047f19  lea     rcx, aLocalservice; "LocalService"
0x180047f20  call    cs:__imp_LogonUserExExW
0x180047f26  test    eax, eax
0x180047f28  jz      short loc_180047F4B
0x180047f2a  xor     r9d, r9d; bool
0x180047f2d  lea     r8, [rbp+arg_0]; unsigned int *
0x180047f31  mov     rdx, [rbp+TokenHandle]; void *
0x180047f35  mov     rcx, r13; this
0x180047f38  call    ?LogonService@CLoggedOnUsers@@QEAAJPEAXPEAK_N@Z; CLoggedOnUsers::LogonService(void *,ulong *,bool)
0x180047f3d  mov     ebx, eax
0x180047f3f  mov     rcx, [rbp+TokenHandle]; hObject
0x180047f43  call    cs:__imp_CloseHandle
0x180047f49  jmp     short loc_180047F60
0x180047f4b  call    cs:__imp_GetLastError
0x180047f51  mov     ebx, eax
0x180047f53  test    eax, eax
0x180047f55  jle     short loc_180047F60
0x180047f57  movzx   ebx, ax
0x180047f5a  or      ebx, 80070000h
0x180047f60  lea     r14, WPP_GLOBAL_Control
0x180047f67  mov     r15d, 8007052Eh
0x180047f6d  test    ebx, ebx
0x180047f6f  jns     short loc_180047FCB
0x180047f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f78  cmp     rcx, r14
0x180047f7b  jz      short loc_180047FA2
0x180047f7d  test    byte ptr [rcx+1Ch], 2
0x180047f81  jz      short loc_180047FA2
0x180047f83  mov     edx, 23h ; '#'
0x180047f88  mov     r9d, ebx
0x180047f8b  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x180047f92  mov     rcx, [rcx+10h]
0x180047f96  call    WPP_SF_d
0x180047f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fa2  cmp     ebx, r15d
0x180047fa5  jnz     loc_1800480B0
0x180047fab  cmp     rcx, r14
0x180047fae  jz      short loc_180047FCB
0x180047fb0  test    byte ptr [rcx+1Ch], 2
0x180047fb4  jz      short loc_180047FCB
0x180047fb6  mov     edx, 24h ; '$'
0x180047fbb  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x180047fc2  mov     rcx, [rcx+10h]
0x180047fc6  call    WPP_SF_
0x180047fcb  mov     [rsp+70h+var_20], rdi
0x180047fd0  mov     [rsp+70h+var_28], rdi
0x180047fd5  mov     [rsp+70h+var_30], rdi
0x180047fda  mov     [rsp+70h+var_38], rdi
0x180047fdf  lea     rax, [rbp+TokenHandle]
0x180047fe3  mov     [rsp+70h+var_40], rax
0x180047fe8  mov     [rsp+70h+var_48], rdi
0x180047fed  mov     [rsp+70h+var_50], edi
0x180047ff1  mov     r9d, 5
0x180047ff7  lea     r8, qword_18011AC70
0x180047ffe  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x180048005  lea     rcx, aNetworkservice; "NetworkService"
0x18004800c  call    cs:__imp_LogonUserExExW
0x180048012  test    eax, eax
0x180048014  jz      short loc_180048037
0x180048016  xor     r9d, r9d; bool
0x180048019  lea     r8, [rbp+arg_0]; unsigned int *
0x18004801d  mov     rdx, [rbp+TokenHandle]; void *
0x180048021  mov     rcx, r13; this
0x180048024  call    ?LogonService@CLoggedOnUsers@@QEAAJPEAXPEAK_N@Z; CLoggedOnUsers::LogonService(void *,ulong *,bool)
0x180048029  mov     ebx, eax
0x18004802b  mov     rcx, [rbp+TokenHandle]; hObject
0x18004802f  call    cs:__imp_CloseHandle
0x180048035  jmp     short loc_18004804C
0x180048037  call    cs:__imp_GetLastError
0x18004803d  mov     ebx, eax
0x18004803f  test    eax, eax
0x180048041  jle     short loc_18004804C
0x180048043  movzx   ebx, ax
0x180048046  or      ebx, 80070000h
0x18004804c  test    ebx, ebx
0x18004804e  jns     short loc_1800480A6
0x180048050  mov     rcx, cs:WPP_GLOBAL_Control
0x180048057  cmp     rcx, r14
0x18004805a  jz      short loc_180048081
0x18004805c  test    byte ptr [rcx+1Ch], 2
0x180048060  jz      short loc_180048081
0x180048062  mov     edx, 25h ; '%'
0x180048067  mov     r9d, ebx
0x18004806a  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x180048071  mov     rcx, [rcx+10h]
0x180048075  call    WPP_SF_d
0x18004807a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048081  cmp     ebx, r15d
0x180048084  jnz     short loc_1800480B0
0x180048086  cmp     rcx, r14
0x180048089  jz      short loc_1800480A6
0x18004808b  test    byte ptr [rcx+1Ch], 2
0x18004808f  jz      short loc_1800480A6
0x180048091  mov     edx, 26h ; '&'
0x180048096  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x18004809d  mov     rcx, [rcx+10h]
0x1800480a1  call    WPP_SF_
0x1800480a6  mov     rcx, r13; this
0x1800480a9  call    ?TryAddContainerSpecificServiceAccounts@CLoggedOnUsers@@AEAAXXZ; CLoggedOnUsers::TryAddContainerSpecificServiceAccounts(void)
0x1800480ae  mov     ebx, edi
0x1800480b0  lea     rcx, [rbp+var_10]; this
0x1800480b4  call    ??1HoldWriterLock@@QEAA@XZ; HoldWriterLock::~HoldWriterLock(void)
0x1800480b9  mov     eax, ebx
0x1800480bb  mov     rbx, [rsp+70h+arg_10]
0x1800480c3  add     rsp, 70h
0x1800480c7  pop     r15
0x1800480c9  pop     r14
0x1800480cb  pop     r13
0x1800480cd  pop     rdi
0x1800480ce  pop     rbp
0x1800480cf  retn
```
