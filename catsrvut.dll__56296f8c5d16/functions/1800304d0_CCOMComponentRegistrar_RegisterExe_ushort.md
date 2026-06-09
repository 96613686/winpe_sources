# CCOMComponentRegistrar::RegisterExe(ushort *)

- ea: `0x1800304d0`
- end: `0x18003070a`
- name: `?RegisterExe@CCOMComponentRegistrar@@UEAAJPEAG@Z`
- size: `570`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074d8`
- `0x180007a4c`
- `0x1800304d0`
- `0x180043b94`
- `0x180043c14`
- `0x18005583a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003066c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003066c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003057c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003057c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306de`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003065a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003065a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030534`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180030534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003051c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003051c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003067b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003067b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030572`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030572`
- `MfcSubs!??H@YA?AVCString@@AEBV0@PEBG@Z` at `0x1800305d2`
- `MfcSubs!??H@YA?AVCString@@AEBV0@PEBG@Z` at `0x1800305d2`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800305dc`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800306bf`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800305dc`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800306bf`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800305bd`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800305bd`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::RegisterExe(CCOMComponentRegistrar *this, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int v5; // eax
  CString *v6; // rax
  signed int LastError; // eax
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpCommandLine; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  void *ppInterface; // [rsp+88h] [rbp-78h] BYREF
  int v13; // [rsp+90h] [rbp-70h]
  __int64 v14; // [rsp+98h] [rbp-68h]
  _BYTE v15[16]; // [rsp+A0h] [rbp-60h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  int v17; // [rsp+148h] [rbp+48h] BYREF
  DWORD ExitCode; // [rsp+150h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+158h] [rbp+58h] BYREF

  TokenHandle = 0;
  hToken = 0;
  ppInterface = 0;
  v13 = 0;
  v14 = 0;
  if ( a2 )
  {
    v17 = CImpersonate::ImpersonateClient(&ppInterface);
    if ( v17 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle);
      v17 = CImpersonate::SuspendImpersonation((CImpersonate *)&ppInterface);
      if ( v17 >= 0 )
      {
        if ( DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
        {
          memset_0(&StartupInfo, 0, sizeof(StartupInfo));
          ExitCode = 0;
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          v6 = CString::CString((CString *)v15, a2);
          operator+(&lpCommandLine, v6, L" /RegServer");
          CString::~CString((CString *)v15);
          memset_0(&StartupInfo, 0, sizeof(StartupInfo));
          StartupInfo.lpDesktop = (LPWSTR)&Password;
          StartupInfo.cb = 104;
          StartupInfo.lpReserved = 0;
          StartupInfo.lpTitle = 0;
          StartupInfo.dwFlags = 129;
          *(_DWORD *)&StartupInfo.wShowWindow = 6;
          StartupInfo.lpReserved2 = 0;
          if ( CreateProcessAsUserW(hToken, 0, lpCommandLine, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
            GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
            CloseHandle(ProcessInformation.hProcess);
            CloseHandle(ProcessInformation.hThread);
            if ( ExitCode )
              v17 = -2147467259;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v17 = LastError;
          }
          CString::~CString((CString *)&lpCommandLine);
        }
        else
        {
          v5 = GetLastError();
          if ( v5 > 0 )
            v5 = (unsigned __int16)v5 | 0x80070000;
          v17 = v5;
        }
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( hToken )
      CloseHandle(hToken);
    CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v17);
    v3 = v17;
  }
  else
  {
    v3 = -2147467261;
  }
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return v3;
}

```

## disassembly

```asm
0x1800304d0  push    rbp
0x1800304d2  push    rbx
0x1800304d3  push    rsi
0x1800304d4  lea     rbp, [rsp-20h]
0x1800304d9  sub     rsp, 120h
0x1800304e0  xor     esi, esi
0x1800304e2  mov     rbx, rdx
0x1800304e5  mov     [rbp+30h+TokenHandle], rsi
0x1800304e9  mov     [rsp+130h+hToken], rsi
0x1800304ee  mov     [rbp+30h+ppInterface], rsi
0x1800304f2  mov     [rbp+30h+var_A0], esi
0x1800304f5  mov     [rbp+30h+var_98], rsi
0x1800304f9  test    rdx, rdx
0x1800304fc  jnz     short loc_180030508
0x1800304fe  mov     ebx, 80004003h
0x180030503  jmp     loc_1800306F4
0x180030508  lea     rcx, [rbp+30h+ppInterface]; ppInterface
0x18003050c  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x180030511  mov     [rbp+30h+arg_8], eax
0x180030514  test    eax, eax
0x180030516  js      loc_1800306C5
0x18003051c  call    cs:__imp_GetCurrentThread
0x180030522  lea     r9, [rbp+30h+TokenHandle]; TokenHandle
0x180030526  mov     edx, 0F01FFh; DesiredAccess
0x18003052b  mov     rcx, rax; ThreadHandle
0x18003052e  mov     r8d, 1; OpenAsSelf
0x180030534  call    cs:__imp_OpenThreadToken
0x18003053a  lea     rcx, [rbp+30h+ppInterface]; this
0x18003053e  call    ?SuspendImpersonation@CImpersonate@@QEAAJXZ; CImpersonate::SuspendImpersonation(void)
0x180030543  mov     [rbp+30h+arg_8], eax
0x180030546  test    eax, eax
0x180030548  js      loc_1800306C5
0x18003054e  mov     rcx, [rbp+30h+TokenHandle]; hExistingToken
0x180030552  lea     rax, [rsp+130h+hToken]
0x180030557  mov     [rsp+130h+phNewToken], rax; phNewToken
0x18003055c  mov     r9d, 2; ImpersonationLevel
0x180030562  xor     r8d, r8d; lpTokenAttributes
0x180030565  mov     [rsp+130h+TokenType], 1; TokenType
0x18003056d  mov     edx, 0F01FFh; dwDesiredAccess
0x180030572  call    cs:__imp_DuplicateTokenEx
0x180030578  test    eax, eax
0x18003057a  jnz     short loc_180030596
0x18003057c  call    cs:__imp_GetLastError
0x180030582  test    eax, eax
0x180030584  jle     short loc_18003058E
0x180030586  movzx   eax, ax
0x180030589  or      eax, 80070000h
0x18003058e  mov     [rbp+30h+arg_8], eax
0x180030591  jmp     loc_1800306C5
0x180030596  xor     edx, edx; Val
0x180030598  lea     rcx, [rbp+30h+StartupInfo]; void *
0x18003059c  lea     r8d, [rdx+68h]; Size
0x1800305a0  call    memset_0
0x1800305a5  xorps   xmm0, xmm0
0x1800305a8  mov     [rbp+30h+ExitCode], esi
0x1800305ab  xor     eax, eax
0x1800305ad  lea     rcx, [rbp+30h+var_90]
0x1800305b1  mov     rdx, rbx
0x1800305b4  mov     qword ptr [rbp+30h+ProcessInformation.dwProcessId], rax
0x1800305b8  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x1800305bd  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800305c3  mov     rdx, rax
0x1800305c6  lea     r8, aRegserver; " /RegServer"
0x1800305cd  lea     rcx, [rsp+130h+lpCommandLine]
0x1800305d2  call    cs:__imp_??H@YA?AVCString@@AEBV0@PEBG@Z; operator+(CString const &,ushort const *)
0x1800305d8  lea     rcx, [rbp+30h+var_90]
0x1800305dc  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800305e2  xor     edx, edx; Val
0x1800305e4  lea     rcx, [rbp+30h+StartupInfo]; void *
0x1800305e8  lea     r8d, [rdx+68h]; Size
0x1800305ec  call    memset_0
0x1800305f1  mov     r8, [rsp+130h+lpCommandLine]; lpCommandLine
0x1800305f6  lea     rax, Password
0x1800305fd  mov     rcx, [rsp+130h+hToken]; hToken
0x180030602  xor     r9d, r9d; lpProcessAttributes
0x180030605  mov     [rbp+30h+StartupInfo.lpDesktop], rax
0x180030609  xor     edx, edx; lpApplicationName
0x18003060b  lea     rax, [rsp+130h+ProcessInformation]
0x180030610  mov     [rbp+30h+StartupInfo.cb], 68h ; 'h'
0x180030617  mov     [rsp+130h+lpProcessInformation], rax; lpProcessInformation
0x18003061c  lea     rax, [rbp+30h+StartupInfo]
0x180030620  mov     [rsp+130h+lpStartupInfo], rax; lpStartupInfo
0x180030625  mov     [rsp+130h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18003062a  mov     [rsp+130h+lpEnvironment], rsi; lpEnvironment
0x18003062f  mov     [rsp+130h+dwCreationFlags], 8; dwCreationFlags
0x180030637  mov     dword ptr [rsp+130h+phNewToken], esi; bInheritHandles
0x18003063b  mov     qword ptr [rsp+130h+TokenType], rsi; lpThreadAttributes
0x180030640  mov     [rbp+30h+StartupInfo.lpReserved], rsi
0x180030644  mov     [rbp+30h+StartupInfo.lpTitle], rsi
0x180030648  mov     [rbp+30h+StartupInfo.dwFlags], 81h
0x18003064f  mov     dword ptr [rbp+30h+StartupInfo.wShowWindow], 6
0x180030656  mov     [rbp+30h+StartupInfo.lpReserved2], rsi
0x18003065a  call    cs:__imp_CreateProcessAsUserW
0x180030660  test    eax, eax
0x180030662  jz      short loc_1800306A5
0x180030664  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hHandle
0x180030669  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003066c  call    cs:__imp_WaitForSingleObject
0x180030672  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hProcess
0x180030677  lea     rdx, [rbp+30h+ExitCode]; lpExitCode
0x18003067b  call    cs:__imp_GetExitCodeProcess
0x180030681  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hObject
0x180030686  call    cs:__imp_CloseHandle
0x18003068c  mov     rcx, [rsp+130h+ProcessInformation.hThread]; hObject
0x180030691  call    cs:__imp_CloseHandle
0x180030697  cmp     [rbp+30h+ExitCode], esi
0x18003069a  jz      short loc_1800306BA
0x18003069c  mov     [rbp+30h+arg_8], 80004005h
0x1800306a3  jmp     short loc_1800306BA
0x1800306a5  call    cs:__imp_GetLastError
0x1800306ab  test    eax, eax
0x1800306ad  jle     short loc_1800306B7
0x1800306af  movzx   eax, ax
0x1800306b2  or      eax, 80070000h
0x1800306b7  mov     [rbp+30h+arg_8], eax
0x1800306ba  lea     rcx, [rsp+130h+lpCommandLine]
0x1800306bf  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800306c5  mov     rcx, [rbp+30h+TokenHandle]; hObject
0x1800306c9  test    rcx, rcx
0x1800306cc  jz      short loc_1800306D4
0x1800306ce  call    cs:__imp_CloseHandle
0x1800306d4  mov     rcx, [rsp+130h+hToken]; hObject
0x1800306d9  test    rcx, rcx
0x1800306dc  jz      short loc_1800306E4
0x1800306de  call    cs:__imp_CloseHandle
0x1800306e4  lea     rdx, [rbp+30h+arg_8]; int *
0x1800306e8  lea     rcx, [rbp+30h+ppInterface]; this
0x1800306ec  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x1800306f1  mov     ebx, [rbp+30h+arg_8]
0x1800306f4  lea     rcx, [rbp+30h+ppInterface]; this
0x1800306f8  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1800306fd  mov     eax, ebx
0x1800306ff  add     rsp, 120h
0x180030706  pop     rsi
0x180030707  pop     rbx
0x180030708  pop     rbp
0x180030709  retn
```
