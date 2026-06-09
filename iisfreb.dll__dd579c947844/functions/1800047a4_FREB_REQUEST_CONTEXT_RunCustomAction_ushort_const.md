# FREB_REQUEST_CONTEXT::RunCustomAction(ushort const *)

- ea: `0x1800047a4`
- end: `0x180004adb`
- name: `?RunCustomAction@FREB_REQUEST_CONTEXT@@AEAAJPEBG@Z`
- size: `823`
- prototype: `__int64 __fastcall(FREB_REQUEST_CONTEXT *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005588`

## callees

- `0x180003570`
- `0x1800047a4`
- `0x18000ac52`
- `0x18000ac5e`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004a09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004a09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000481b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000481b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000499e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000499e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a52`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180004a1d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180004a1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000485f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000485f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180004868`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180004868`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800049ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800049ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004977`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004990`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004990`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000487f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000487f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180004a75`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180004a75`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004a44`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aa6`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000494e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18000494e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000489c`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000489c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ab0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004ab0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800047e8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800047e8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800048b3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800048b3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800048d1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800048d1`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004964`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004964`

## pseudocode

```c
__int64 __fastcall FREB_REQUEST_CONTEXT::RunCustomAction(FREB_REQUEST_CONTEXT *this, const unsigned __int16 *a2)
{
  int v4; // eax
  __int64 v5; // r12
  __int64 v6; // rsi
  int v7; // ebx
  __int64 v8; // rdi
  const unsigned __int16 *v9; // r13
  __int64 v10; // r12
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  DWORD ThreadId; // r15d
  int v14; // ebx
  int v15; // eax
  HANDLE v16; // rax
  signed int LastError; // eax
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ProcessId; // [rsp+54h] [rbp-ACh]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpApplicationName; // [rsp+78h] [rbp-88h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[32]; // [rsp+F0h] [rbp-10h] BYREF
  LPWSTR lpCommandLine; // [rsp+110h] [rbp+10h]
  unsigned __int16 v27[104]; // [rsp+130h] [rbp+30h] BYREF

  lpApplicationName = *(LPCWSTR *)(*((_QWORD *)this + 10) + 88LL);
  STRU::STRU((STRU *)v25);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  ExitCode = 0;
  EnterCriticalSection(&FREB_REQUEST_CONTEXT::sm_csCustomActionSerializer);
  v4 = wcscmp_0(a2, L"TIME_TAKEN");
  v5 = *((_QWORD *)this + 10);
  v6 = -1;
  v7 = v4;
  v8 = -1;
  v9 = *(const unsigned __int16 **)(v5 + 88);
  do
    ++v8;
  while ( v9[v8] );
  v10 = *(_QWORD *)(v5 + 144);
  do
    ++v6;
  while ( *(_WORD *)(v10 + 2 * v6) );
  CurrentProcess = GetCurrentProcess();
  ProcessId = GetProcessId(CurrentProcess);
  if ( v7 )
  {
    CurrentThread = GetCurrentThread();
    ThreadId = GetThreadId(CurrentThread);
  }
  else
  {
    ThreadId = 0;
  }
  v14 = STRU::Resize((STRU *)v25, 2 * (v6 + v8 + 101));
  if ( v14 >= 0 )
  {
    v14 = STRU::Copy((STRU *)v25, v9);
    if ( v14 >= 0 )
    {
      v14 = STRU::Append((STRU *)v25, L" ");
      if ( v14 >= 0 )
      {
        memset_0(v27, 0, 0xC8u);
        v14 = StringCchPrintfW(v27, 0x64u, L"1=%d%c2=%d", ProcessId, 0, ThreadId);
        if ( v14 >= 0 )
        {
          v22 = 0;
          v15 = RtlExpandEnvironmentStrings(
                  v27,
                  v10,
                  (unsigned int)v6,
                  &lpCommandLine[(unsigned int)v8 + 1],
                  (unsigned int)(v6 + 100),
                  &v22);
          if ( v15 >= 0 )
          {
            STRU::SyncWithBuffer((STRU *)v25);
            goto LABEL_16;
          }
          v14 = v15 | 0x10000000;
        }
      }
    }
  }
  if ( v14 < 0 )
    goto LABEL_29;
LABEL_16:
  v16 = GetCurrentThread();
  if ( OpenThreadToken(v16, 4u, 1, &FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken) )
  {
    if ( FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken && !RevertToSelf() )
    {
LABEL_27:
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError <= 0 )
        goto LABEL_29;
      goto LABEL_28;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_23;
    FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken = 0;
  }
  if ( !CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    goto LABEL_27;
  CloseHandle(ProcessInformation.hThread);
  if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF)
    || !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
    goto LABEL_27;
  }
  LastError = ExitCode;
  if ( !ExitCode )
    goto LABEL_29;
LABEL_23:
  if ( LastError <= 0 )
  {
    v14 = LastError;
    goto LABEL_29;
  }
LABEL_28:
  v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_29:
  if ( FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken )
  {
    SetThreadToken(0, FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken);
    CloseHandle(FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken);
    FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken = 0;
  }
  LeaveCriticalSection(&FREB_REQUEST_CONTEXT::sm_csCustomActionSerializer);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800047a4  push    rbp
0x1800047a6  push    rbx
0x1800047a7  push    rsi
0x1800047a8  push    rdi
0x1800047a9  push    r12
0x1800047ab  push    r13
0x1800047ad  push    r14
0x1800047af  push    r15
0x1800047b1  lea     rbp, [rsp-118h]
0x1800047b9  sub     rsp, 218h
0x1800047c0  mov     rax, cs:__security_cookie
0x1800047c7  xor     rax, rsp
0x1800047ca  mov     [rbp+150h+var_50], rax
0x1800047d1  mov     rax, [rcx+50h]
0x1800047d5  mov     rdi, rcx
0x1800047d8  lea     rcx, [rbp+150h+var_160]
0x1800047dc  mov     rbx, rdx
0x1800047df  mov     rax, [rax+58h]
0x1800047e3  mov     [rsp+250h+lpApplicationName], rax
0x1800047e8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800047ee  xor     edx, edx; Val
0x1800047f0  lea     rcx, [rbp+150h+StartupInfo]; void *
0x1800047f4  lea     r8d, [rdx+68h]; Size
0x1800047f8  call    memset_0
0x1800047fd  xorps   xmm0, xmm0
0x180004800  lea     rcx, ?sm_csCustomActionSerializer@FREB_REQUEST_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004807  xor     eax, eax
0x180004809  xor     r14d, r14d
0x18000480c  movups  xmmword ptr [rsp+250h+ProcessInformation.hProcess], xmm0
0x180004811  mov     qword ptr [rsp+250h+ProcessInformation.dwProcessId], rax
0x180004816  mov     [rsp+250h+ExitCode], r14d
0x18000481b  call    cs:__imp_EnterCriticalSection
0x180004821  lea     rdx, aTimeTaken; "TIME_TAKEN"
0x180004828  mov     rcx, rbx; String1
0x18000482b  call    wcscmp_0
0x180004830  mov     r12, [rdi+50h]
0x180004834  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004838  mov     ebx, eax
0x18000483a  mov     rdi, rsi
0x18000483d  mov     r13, [r12+58h]
0x180004842  inc     rdi
0x180004845  cmp     [r13+rdi*2+0], r14w
0x18000484b  jnz     short loc_180004842
0x18000484d  mov     r12, [r12+90h]
0x180004855  inc     rsi
0x180004858  cmp     [r12+rsi*2], r14w
0x18000485d  jnz     short loc_180004855
0x18000485f  call    cs:__imp_GetCurrentProcess
0x180004865  mov     rcx, rax; Process
0x180004868  call    cs:__imp_GetProcessId
0x18000486e  mov     [rsp+250h+var_1FC], eax
0x180004872  test    ebx, ebx
0x180004874  jz      short loc_18000488A
0x180004876  call    cs:__imp_GetCurrentThread
0x18000487c  mov     rcx, rax; Thread
0x18000487f  call    cs:__imp_GetThreadId
0x180004885  mov     r15d, eax
0x180004888  jmp     short loc_18000488D
0x18000488a  mov     r15d, r14d
0x18000488d  lea     r14d, [rdi+65h]
0x180004891  add     r14d, esi
0x180004894  lea     rcx, [rbp+150h+var_160]
0x180004898  lea     edx, [r14+r14]
0x18000489c  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800048a2  mov     ebx, eax
0x1800048a4  test    eax, eax
0x1800048a6  js      loc_18000496C
0x1800048ac  mov     rdx, r13
0x1800048af  lea     rcx, [rbp+150h+var_160]
0x1800048b3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800048b9  xor     r13d, r13d
0x1800048bc  mov     ebx, eax
0x1800048be  test    eax, eax
0x1800048c0  js      loc_18000496F
0x1800048c6  lea     rdx, asc_18000D7B0; " "
0x1800048cd  lea     rcx, [rbp+150h+var_160]
0x1800048d1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800048d7  mov     ebx, eax
0x1800048d9  test    eax, eax
0x1800048db  js      loc_18000496F
0x1800048e1  xor     edx, edx; Val
0x1800048e3  lea     rcx, [rbp+150h+var_120]; void *
0x1800048e7  mov     r8d, 0C8h; Size
0x1800048ed  call    memset_0
0x1800048f2  mov     r9d, [rsp+250h+var_1FC]
0x1800048f7  lea     r8, a1DC2D; "1=%d%c2=%d"
0x1800048fe  lea     edx, [r13+64h]; unsigned __int64
0x180004902  mov     [rsp+250h+dwCreationFlags], r15d
0x180004907  lea     rcx, [rbp+150h+var_120]; unsigned __int16 *
0x18000490b  mov     qword ptr [rsp+250h+bInheritHandles], r13
0x180004910  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004915  mov     ebx, eax
0x180004917  test    eax, eax
0x180004919  js      short loc_18000496F
0x18000491b  mov     r8, [rbp+150h+lpCommandLine]
0x18000491f  sub     r14d, edi
0x180004922  add     r8, 2
0x180004926  mov     eax, edi
0x180004928  mov     rdx, r12
0x18000492b  mov     [rsp+250h+var_1E0], r13
0x180004930  lea     ecx, [r14-1]
0x180004934  lea     r9, [r8+rax*2]
0x180004938  mov     r8d, esi
0x18000493b  lea     rax, [rsp+250h+var_1E0]
0x180004940  mov     qword ptr [rsp+250h+dwCreationFlags], rax
0x180004945  mov     qword ptr [rsp+250h+bInheritHandles], rcx
0x18000494a  lea     rcx, [rbp+150h+var_120]
0x18000494e  call    cs:__imp_RtlExpandEnvironmentStrings
0x180004954  test    eax, eax
0x180004956  jns     short loc_180004960
0x180004958  mov     ebx, eax
0x18000495a  bts     ebx, 1Ch
0x18000495e  jmp     short loc_18000496F
0x180004960  lea     rcx, [rbp+150h+var_160]
0x180004964  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000496a  jmp     short loc_180004977
0x18000496c  xor     r13d, r13d
0x18000496f  test    ebx, ebx
0x180004971  js      loc_180004A67
0x180004977  call    cs:__imp_GetCurrentThread
0x18000497d  mov     edx, 4; DesiredAccess
0x180004982  lea     r9, ?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA; TokenHandle
0x180004989  mov     rcx, rax; ThreadHandle
0x18000498c  lea     r8d, [rdx-3]; OpenAsSelf
0x180004990  call    cs:__imp_OpenThreadToken
0x180004996  test    eax, eax
0x180004998  jnz     loc_180004A37
0x18000499e  call    cs:__imp_GetLastError
0x1800049a4  cmp     eax, 3F0h
0x1800049a9  jnz     loc_180004A2F
0x1800049af  mov     cs:?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA, r13; void * FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken
0x1800049b6  mov     rdx, [rbp+150h+lpCommandLine]; lpCommandLine
0x1800049ba  lea     rax, [rsp+250h+ProcessInformation]
0x1800049bf  mov     rcx, [rsp+250h+lpApplicationName]; lpApplicationName
0x1800049c4  xor     r9d, r9d; lpThreadAttributes
0x1800049c7  mov     [rsp+250h+lpProcessInformation], rax; lpProcessInformation
0x1800049cc  xor     r8d, r8d; lpProcessAttributes
0x1800049cf  lea     rax, [rbp+150h+StartupInfo]
0x1800049d3  mov     [rsp+250h+lpStartupInfo], rax; lpStartupInfo
0x1800049d8  mov     [rsp+250h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1800049dd  mov     [rsp+250h+lpEnvironment], r13; lpEnvironment
0x1800049e2  mov     [rsp+250h+dwCreationFlags], r13d; dwCreationFlags
0x1800049e7  mov     [rsp+250h+bInheritHandles], r13d; bInheritHandles
0x1800049ec  call    cs:__imp_CreateProcessW
0x1800049f2  test    eax, eax
0x1800049f4  jz      short loc_180004A52
0x1800049f6  mov     rcx, [rsp+250h+ProcessInformation.hThread]; hObject
0x1800049fb  call    cs:__imp_CloseHandle
0x180004a01  mov     rcx, [rsp+250h+ProcessInformation.hProcess]; hHandle
0x180004a06  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004a09  call    cs:__imp_WaitForSingleObject
0x180004a0f  test    eax, eax
0x180004a11  jnz     short loc_180004A52
0x180004a13  mov     rcx, [rsp+250h+ProcessInformation.hProcess]; hProcess
0x180004a18  lea     rdx, [rsp+250h+ExitCode]; lpExitCode
0x180004a1d  call    cs:__imp_GetExitCodeProcess
0x180004a23  test    eax, eax
0x180004a25  jz      short loc_180004A52
0x180004a27  mov     eax, [rsp+250h+ExitCode]
0x180004a2b  test    eax, eax
0x180004a2d  jz      short loc_180004A67
0x180004a2f  test    eax, eax
0x180004a31  jg      short loc_180004A5E
0x180004a33  mov     ebx, eax
0x180004a35  jmp     short loc_180004A67
0x180004a37  cmp     cs:?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA, r13; void * FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken
0x180004a3e  jz      loc_1800049B6
0x180004a44  call    cs:__imp_RevertToSelf
0x180004a4a  test    eax, eax
0x180004a4c  jnz     loc_1800049B6
0x180004a52  call    cs:__imp_GetLastError
0x180004a58  mov     ebx, eax
0x180004a5a  test    eax, eax
0x180004a5c  jle     short loc_180004A67
0x180004a5e  movzx   ebx, ax
0x180004a61  or      ebx, 80070000h
0x180004a67  mov     rdx, cs:?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA; Token
0x180004a6e  test    rdx, rdx
0x180004a71  jz      short loc_180004A8F
0x180004a73  xor     ecx, ecx; Thread
0x180004a75  call    cs:__imp_SetThreadToken
0x180004a7b  mov     rcx, cs:?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA; hObject
0x180004a82  call    cs:__imp_CloseHandle
0x180004a88  mov     cs:?sm_hCustomActionThreadToken@FREB_REQUEST_CONTEXT@@0PEAXEA, r13; void * FREB_REQUEST_CONTEXT::sm_hCustomActionThreadToken
0x180004a8f  lea     rcx, ?sm_csCustomActionSerializer@FREB_REQUEST_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004a96  call    cs:__imp_LeaveCriticalSection
0x180004a9c  mov     rcx, [rsp+250h+ProcessInformation.hProcess]; hObject
0x180004aa1  test    rcx, rcx
0x180004aa4  jz      short loc_180004AAC
0x180004aa6  call    cs:__imp_CloseHandle
0x180004aac  lea     rcx, [rbp+150h+var_160]
0x180004ab0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004ab6  mov     eax, ebx
0x180004ab8  mov     rcx, [rbp+150h+var_50]
0x180004abf  xor     rcx, rsp; StackCookie
0x180004ac2  call    __security_check_cookie
0x180004ac7  add     rsp, 218h
0x180004ace  pop     r15
0x180004ad0  pop     r14
0x180004ad2  pop     r13
0x180004ad4  pop     r12
0x180004ad6  pop     rdi
0x180004ad7  pop     rsi
0x180004ad8  pop     rbx
0x180004ad9  pop     rbp
0x180004ada  retn
```
