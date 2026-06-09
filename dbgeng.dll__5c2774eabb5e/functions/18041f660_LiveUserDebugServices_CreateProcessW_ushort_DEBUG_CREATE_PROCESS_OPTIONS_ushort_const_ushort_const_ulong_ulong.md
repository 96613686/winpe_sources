# LiveUserDebugServices::CreateProcessW(ushort *,_DEBUG_CREATE_PROCESS_OPTIONS *,ushort const *,ushort const *,ulong *,ulong *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18041f660`
- end: `0x18041f9a6`
- name: `?CreateProcessW@LiveUserDebugServices@@UEAAJPEAGPEAU_DEBUG_CREATE_PROCESS_OPTIONS@@PEBG2PEAK3PEA_K4@Z`
- size: `838`
- prototype: `int(LiveUserDebugServices *__hidden this, unsigned __int16 *, struct _DEBUG_CREATE_PROCESS_OPTIONS *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800f0f40`
- `0x1804153c8`
- `0x18041649c`
- `0x18041f4f4`
- `0x18041f660`
- `0x180424bec`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041f8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041f8d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041f8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041f8d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041f7ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041f943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041f7ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041f943`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18041f8ae`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18041f8ae`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f70e`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f753`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f911`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f926`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f70e`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f753`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f911`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableA` at `0x18041f926`

## pseudocode

```c
__int64 __fastcall LiveUserDebugServices::CreateProcessW(
        LiveUserDebugServices *this,
        unsigned __int16 *a2,
        struct _DEBUG_CREATE_PROCESS_OPTIONS *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *lpEnvironment,
        unsigned int *a6,
        unsigned int *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9)
{
  __int64 result; // rax
  bool v13; // zf
  unsigned int v14; // ebx
  ULONG CreateFlags; // ebx
  int v16; // ebx
  int v17; // ebx
  BOOL bInheritHandles; // eax
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v22; // [rsp+70h] [rbp-90h]
  unsigned int *v23; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v24; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v25; // [rsp+88h] [rbp-78h]
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  CHAR Value[16]; // [rsp+100h] [rbp+0h] BYREF

  v22 = a6;
  v23 = a7;
  v24 = a8;
  v25 = a9;
  result = EnableDebugPrivilege();
  if ( (_DWORD)result )
    return result;
  if ( (a3->EngCreateFlags & 4) != 0 )
  {
    a2 = g_UserServicesCreateCommandLine;
    if ( !g_UserServicesCreateCommandLine )
      return 2147942487LL;
  }
  if ( (a3->CreateFlags & 0x400) != 0 )
  {
    if ( lpEnvironment )
      return 2147500033LL;
    SetEnvironmentVariableA("_NO_DEBUG_HEAP", "1");
  }
  if ( (a3->EngCreateFlags & 2) != 0 )
  {
    if ( lpEnvironment )
      return 2147500033LL;
    PrintString(Value, 16, "0x%08x", a3->VerifierFlags);
    SetEnvironmentVariableA("_VERIFIER_SETTING", Value);
  }
  v13 = (a3->CreateFlags & 3) == 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( v13 )
    goto LABEL_15;
  if ( !*((_DWORD *)this + 98) )
  {
    v16 = *((_DWORD *)this + 99);
    if ( v16 && GetCurrentThreadId() != v16 )
    {
      v14 = -805306070;
      goto LABEL_29;
    }
LABEL_15:
    CreateFlags = a3->CreateFlags;
    if ( (a3->CreateFlags & 0x10000) != 0 )
    {
      if ( !*((_DWORD *)this + 98) )
      {
        v14 = -2147418113;
        goto LABEL_29;
      }
      v17 = NtSimpleCreateProcess(a2, a3, a4, lpEnvironment, *((void **)this + 48), &ProcessInformation);
      if ( v17 < 0 )
      {
        v14 = v17 | 0x10000000;
        goto LABEL_29;
      }
    }
    else
    {
      memset(&StartupInfo.cb + 1, 0, 0x64u);
      bInheritHandles = a3->EngCreateFlags & 1;
      StartupInfo.cb = 104;
      if ( !CreateProcessW(
              0,
              a2,
              0,
              0,
              bInheritHandles,
              CreateFlags & 0xFFFEFBFF | 0x400,
              lpEnvironment,
              a4,
              &StartupInfo,
              &ProcessInformation) )
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v14 = -2147467259;
        }
        goto LABEL_29;
      }
    }
    v14 = 0;
    goto LABEL_29;
  }
  v14 = -2147467263;
LABEL_29:
  SetEnvironmentVariableA("_NO_DEBUG_HEAP", 0);
  SetEnvironmentVariableA("_VERIFIER_SETTING", 0);
  if ( !v14 )
  {
    if ( (a3->CreateFlags & 3) != 0 && !*((_DWORD *)this + 98) )
      *((_DWORD *)this + 99) = GetCurrentThreadId();
    *v22 = ProcessInformation.dwProcessId;
    *v23 = ProcessInformation.dwThreadId;
    *v24 = (unsigned __int64)ProcessInformation.hProcess;
    *v25 = (unsigned __int64)ProcessInformation.hThread;
  }
  return v14;
}

```

## disassembly

```asm
0x18041f660  push    rbp
0x18041f662  push    rbx
0x18041f663  push    rsi
0x18041f664  push    rdi
0x18041f665  push    r12
0x18041f667  push    r13
0x18041f669  push    r14
0x18041f66b  push    r15
0x18041f66d  lea     rbp, [rsp-28h]
0x18041f672  sub     rsp, 128h
0x18041f679  mov     rax, cs:__security_cookie
0x18041f680  xor     rax, rsp
0x18041f683  mov     [rbp+60h+var_50], rax
0x18041f687  mov     rax, [rbp+60h+arg_28]
0x18041f68e  mov     rdi, r8
0x18041f691  mov     r15, [rbp+60h+arg_20]
0x18041f698  mov     r14, rdx
0x18041f69b  mov     [rsp+160h+var_F0], rax
0x18041f6a0  mov     rsi, rcx
0x18041f6a3  mov     rax, [rbp+60h+arg_30]
0x18041f6aa  mov     [rsp+160h+var_E8], rax
0x18041f6af  mov     rax, [rbp+60h+arg_38]
0x18041f6b6  mov     [rbp+60h+var_E0], rax
0x18041f6ba  mov     rax, [rbp+60h+arg_40]
0x18041f6c1  mov     [rbp+60h+var_D8], rax
0x18041f6c5  mov     [rsp+160h+var_110], r9
0x18041f6ca  call    ?EnableDebugPrivilege@@YAJXZ; EnableDebugPrivilege(void)
0x18041f6cf  test    eax, eax
0x18041f6d1  jnz     loc_18041F985
0x18041f6d7  test    byte ptr [rdi+4], 4
0x18041f6db  jz      short loc_18041F6F3
0x18041f6dd  mov     r14, cs:?g_UserServicesCreateCommandLine@@3PEAGEA; ushort * g_UserServicesCreateCommandLine
0x18041f6e4  test    r14, r14
0x18041f6e7  jnz     short loc_18041F6F3
0x18041f6e9  mov     eax, 80070057h
0x18041f6ee  jmp     loc_18041F985
0x18041f6f3  test    dword ptr [rdi], 400h
0x18041f6f9  jz      short loc_18041F71A
0x18041f6fb  test    r15, r15
0x18041f6fe  jnz     short loc_18041F725
0x18041f700  lea     rdx, a1_0; "1"
0x18041f707  lea     rcx, aNoDebugHeap; "_NO_DEBUG_HEAP"
0x18041f70e  call    cs:__imp_SetEnvironmentVariableA
0x18041f715  nop     dword ptr [rax+rax+00h]
0x18041f71a  test    byte ptr [rdi+4], 2
0x18041f71e  jz      short loc_18041F75F
0x18041f720  test    r15, r15
0x18041f723  jz      short loc_18041F72F
0x18041f725  mov     eax, 80004001h
0x18041f72a  jmp     loc_18041F985
0x18041f72f  mov     r9d, [rdi+8]
0x18041f733  lea     r8, a0x08x_0; "0x%08x"
0x18041f73a  mov     edx, 10h
0x18041f73f  lea     rcx, [rbp+60h+Value]
0x18041f743  call    PrintString
0x18041f748  lea     rdx, [rbp+60h+Value]; lpValue
0x18041f74c  lea     rcx, aVerifierSettin; "_VERIFIER_SETTING"
0x18041f753  call    cs:__imp_SetEnvironmentVariableA
0x18041f75a  nop     dword ptr [rax+rax+00h]
0x18041f75f  xor     eax, eax
0x18041f761  xor     r13d, r13d
0x18041f764  xor     r12d, r12d
0x18041f767  mov     qword ptr [rsp+160h+ProcessInformation.dwProcessId], rax
0x18041f76c  test    byte ptr [rdi], 3
0x18041f76f  xorps   xmm0, xmm0
0x18041f772  movups  xmmword ptr [rsp+160h+ProcessInformation.hProcess], xmm0
0x18041f777  jz      short loc_18041F7D1
0x18041f779  cmp     [rsi+188h], eax
0x18041f77f  jz      short loc_18041F7F5
0x18041f781  mov     rax, cs:qword_18082DC38
0x18041f788  test    rax, rax
0x18041f78b  jnz     short loc_18041F797
0x18041f78d  mov     ebx, 80004001h
0x18041f792  jmp     loc_18041F908
0x18041f797  mov     rax, cs:qword_18082DC28
0x18041f79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18041f7a3  lea     r12, [rsi+180h]
0x18041f7aa  mov     r13, rax
0x18041f7ad  mov     rcx, r12; void **
0x18041f7b0  call    ?CreateDebugObject@@YAJPEAPEAX@Z; CreateDebugObject(void * *)
0x18041f7b5  mov     ebx, eax
0x18041f7b7  test    eax, eax
0x18041f7b9  js      short loc_18041F7EC
0x18041f7bb  mov     rax, cs:qword_18082DC38
0x18041f7c2  mov     rcx, [r12]
0x18041f7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18041f7cb  mov     r12d, 1
0x18041f7d1  mov     ebx, [rdi]
0x18041f7d3  bt      ebx, 10h
0x18041f7d7  jnb     short loc_18041F855
0x18041f7d9  cmp     dword ptr [rsi+188h], 0
0x18041f7e0  jnz     short loc_18041F819
0x18041f7e2  mov     ebx, 8000FFFFh
0x18041f7e7  jmp     loc_18041F8F4
0x18041f7ec  bts     ebx, 1Ch
0x18041f7f0  jmp     loc_18041F908
0x18041f7f5  mov     ebx, [rsi+18Ch]
0x18041f7fb  test    ebx, ebx
0x18041f7fd  jz      short loc_18041F7D1
0x18041f7ff  call    cs:__imp_GetCurrentThreadId
0x18041f806  nop     dword ptr [rax+rax+00h]
0x18041f80b  cmp     eax, ebx
0x18041f80d  jz      short loc_18041F7D1
0x18041f80f  mov     ebx, 0D000012Ah
0x18041f814  jmp     loc_18041F908
0x18041f819  mov     r8, [rsp+160h+var_110]; unsigned __int16 *
0x18041f81e  lea     rax, [rsp+160h+ProcessInformation]
0x18041f823  mov     qword ptr [rsp+160h+dwCreationFlags], rax; struct _PROCESS_INFORMATION *
0x18041f828  mov     r9, r15; unsigned __int16 *
0x18041f82b  mov     rax, [rsi+180h]
0x18041f832  mov     rdx, rdi; struct _DEBUG_CREATE_PROCESS_OPTIONS *
0x18041f835  mov     rcx, r14; Src
0x18041f838  mov     qword ptr [rsp+160h+bInheritHandles], rax; void *
0x18041f83d  call    ?NtSimpleCreateProcess@@YAJPEBGPEAU_DEBUG_CREATE_PROCESS_OPTIONS@@00PEAXPEAU_PROCESS_INFORMATION@@@Z; NtSimpleCreateProcess(ushort const *,_DEBUG_CREATE_PROCESS_OPTIONS *,ushort const *,ushort const *,void *,_PROCESS_INFORMATION *)
0x18041f842  mov     ebx, eax
0x18041f844  test    eax, eax
0x18041f846  jns     loc_18041F8F2
0x18041f84c  bts     ebx, 1Ch
0x18041f850  jmp     loc_18041F8F4
0x18041f855  xor     edx, edx; Val
0x18041f857  lea     rcx, [rbp+60h+StartupInfo+4]; void *
0x18041f85b  lea     r8d, [rdx+64h]; Size
0x18041f85f  call    memset
0x18041f864  mov     eax, [rdi+4]
0x18041f867  lea     rcx, [rsp+160h+ProcessInformation]
0x18041f86c  mov     [rsp+160h+lpProcessInformation], rcx; lpProcessInformation
0x18041f871  and     eax, 1
0x18041f874  lea     rcx, [rbp+60h+StartupInfo]
0x18041f878  mov     [rbp+60h+StartupInfo.cb], 68h ; 'h'
0x18041f87f  mov     [rsp+160h+lpStartupInfo], rcx; lpStartupInfo
0x18041f884  btr     ebx, 10h
0x18041f888  mov     rcx, [rsp+160h+var_110]
0x18041f88d  bts     ebx, 0Ah
0x18041f891  mov     [rsp+160h+lpCurrentDirectory], rcx; lpCurrentDirectory
0x18041f896  xor     r9d, r9d; lpThreadAttributes
0x18041f899  mov     [rsp+160h+lpEnvironment], r15; lpEnvironment
0x18041f89e  xor     r8d, r8d; lpProcessAttributes
0x18041f8a1  mov     [rsp+160h+dwCreationFlags], ebx; dwCreationFlags
0x18041f8a5  mov     rdx, r14; lpCommandLine
0x18041f8a8  xor     ecx, ecx; lpApplicationName
0x18041f8aa  mov     [rsp+160h+bInheritHandles], eax; bInheritHandles
0x18041f8ae  call    cs:__imp_CreateProcessW
0x18041f8b5  nop     dword ptr [rax+rax+00h]
0x18041f8ba  test    eax, eax
0x18041f8bc  jnz     short loc_18041F8F2
0x18041f8be  call    cs:__imp_GetLastError
0x18041f8c5  nop     dword ptr [rax+rax+00h]
0x18041f8ca  test    eax, eax
0x18041f8cc  jnz     short loc_18041F8D5
0x18041f8ce  mov     ebx, 80004005h
0x18041f8d3  jmp     short loc_18041F8F4
0x18041f8d5  call    cs:__imp_GetLastError
0x18041f8dc  nop     dword ptr [rax+rax+00h]
0x18041f8e1  mov     ebx, eax
0x18041f8e3  test    eax, eax
0x18041f8e5  jle     short loc_18041F8F4
0x18041f8e7  movzx   ebx, ax
0x18041f8ea  or      ebx, 80070000h
0x18041f8f0  jmp     short loc_18041F8F4
0x18041f8f2  xor     ebx, ebx
0x18041f8f4  test    r12d, r12d
0x18041f8f7  jz      short loc_18041F908
0x18041f8f9  mov     rax, cs:qword_18082DC38
0x18041f900  mov     rcx, r13
0x18041f903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18041f908  xor     edx, edx; lpValue
0x18041f90a  lea     rcx, aNoDebugHeap; "_NO_DEBUG_HEAP"
0x18041f911  call    cs:__imp_SetEnvironmentVariableA
0x18041f918  nop     dword ptr [rax+rax+00h]
0x18041f91d  xor     edx, edx; lpValue
0x18041f91f  lea     rcx, aVerifierSettin; "_VERIFIER_SETTING"
0x18041f926  call    cs:__imp_SetEnvironmentVariableA
0x18041f92d  nop     dword ptr [rax+rax+00h]
0x18041f932  test    ebx, ebx
0x18041f934  jnz     short loc_18041F983
0x18041f936  test    byte ptr [rdi], 3
0x18041f939  jz      short loc_18041F955
0x18041f93b  cmp     [rsi+188h], ebx
0x18041f941  jnz     short loc_18041F955
0x18041f943  call    cs:__imp_GetCurrentThreadId
0x18041f94a  nop     dword ptr [rax+rax+00h]
0x18041f94f  mov     [rsi+18Ch], eax
0x18041f955  mov     ecx, [rsp+160h+ProcessInformation.dwProcessId]
0x18041f959  mov     rax, [rsp+160h+var_F0]
0x18041f95e  mov     [rax], ecx
0x18041f960  mov     rax, [rsp+160h+var_E8]
0x18041f965  mov     ecx, [rsp+160h+ProcessInformation.dwThreadId]
0x18041f969  mov     [rax], ecx
0x18041f96b  mov     rax, [rbp+60h+var_E0]
0x18041f96f  mov     rcx, [rsp+160h+ProcessInformation.hProcess]
0x18041f974  mov     [rax], rcx
0x18041f977  mov     rax, [rbp+60h+var_D8]
0x18041f97b  mov     rcx, [rsp+160h+ProcessInformation.hThread]
0x18041f980  mov     [rax], rcx
0x18041f983  mov     eax, ebx
0x18041f985  mov     rcx, [rbp+60h+var_50]
0x18041f989  xor     rcx, rsp; StackCookie
0x18041f98c  call    __security_check_cookie
0x18041f991  add     rsp, 128h
0x18041f998  pop     r15
0x18041f99a  pop     r14
0x18041f99c  pop     r13
0x18041f99e  pop     r12
0x18041f9a0  pop     rdi
0x18041f9a1  pop     rsi
0x18041f9a2  pop     rbx
0x18041f9a3  pop     rbp
0x18041f9a4  retn
```
