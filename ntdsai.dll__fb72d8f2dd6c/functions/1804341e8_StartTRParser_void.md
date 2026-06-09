# StartTRParser(void)

- ea: `0x1804341e8`
- end: `0x1804344af`
- name: `?StartTRParser@@YAKXZ`
- size: `711`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180433fdc`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180434064`
- `0x180434144`
- `0x1804341e8`
- `0x1804344b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180434455`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180434455`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1804342d3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1804342d3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1804343e3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1804343e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1804342fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1804342fd`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1804343b5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1804343b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180434286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804342dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180434286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804342dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18043430f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18043430f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043447c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18043447c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804343cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180434465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804343cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180434465`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180434429`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180434429`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180434369`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180434369`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18043427c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18043427c`

## string_xrefs

- `0x18043425c`: `%windir%\system32\TransformationRulesParser.exe`

## pseudocode

```c
unsigned int StartTRParser(void)
{
  unsigned int result; // eax
  struct _TOKEN_PRIVILEGES *v1; // rbx
  struct _TOKEN_PRIVILEGES *v2; // rax
  unsigned int v3; // edi
  int v4; // ecx
  DWORD v5; // eax
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID Luid; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handles[3]; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset_0(Dst, 0, 0x20Au);
  StopTRParser();
  result = CreatePipes();
  ExitCode = result;
  if ( result )
    return result;
  StartupInfo.dwFlags |= 0x100u;
  StartupInfo.hStdError = g_hChild_Stdout_Wr;
  StartupInfo.hStdOutput = g_hChild_Stdout_Wr;
  StartupInfo.hStdInput = g_hChild_Stdin_Rd;
  if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\TransformationRulesParser.exe", Dst, 0x105u) )
    return GetLastError();
  v1 = 0;
  TokenHandle = 0;
  if ( CreateProcessW(0, Dst, 0, 0, 0, 0x24u, 0, 0, &StartupInfo, (LPPROCESS_INFORMATION)&g_TRParserProcInfo)
    && OpenProcessToken(g_TRParserProcInfo, 0x2000000u, &TokenHandle) )
  {
    v2 = (struct _TOKEN_PRIVILEGES *)LocalAlloc(0x40u, 0xACu);
    v1 = v2;
    if ( !v2 )
    {
      ExitCode = 12;
      goto LABEL_22;
    }
    memset_0(v2->Privileges, 0, 0xA8u);
    v3 = 0;
    v1->PrivilegeCount = 13;
    while ( v3 < 0xD )
    {
      Luid = 0;
      if ( !LookupPrivilegeValueW(0, (LPCWSTR)*(&g_TRParserPriviligeAdjustments + 2 * (int)v3), &Luid) )
        goto LABEL_5;
      v4 = -(*((_DWORD *)&g_TRParserPriviligeAdjustments + 4 * (int)v3 + 2) != 0);
      v1->Privileges[0].Luid = Luid;
      v1->Privileges[0].Attributes = (v4 & 0xFFFFFFFE) + 4;
      ++v3;
    }
    if ( AdjustTokenPrivileges(TokenHandle, 0, v1, 0, 0, 0) )
    {
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      TokenHandle = 0;
      if ( ResumeThread(*(&g_TRParserProcInfo + 1)) != -1 )
      {
        ExitCode = CreateBindingHandle();
        if ( !ExitCode )
        {
          Handles[0] = g_TRParserProcInfo;
          Handles[1] = g_hUninitializeEvent;
          v5 = WaitForMultipleObjects(2u, Handles, 0, 0x3E8u);
          if ( v5 )
          {
            if ( v5 != 258 )
              ExitCode = 11;
          }
          else
          {
            GetExitCodeProcess(g_TRParserProcInfo, &ExitCode);
          }
        }
        goto LABEL_22;
      }
    }
  }
LABEL_5:
  ExitCode = GetLastError();
LABEL_22:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v1 )
    LocalFree(v1);
  if ( ExitCode )
    StopTRParser();
  return ExitCode;
}

```

## disassembly

```asm
0x1804341e8  push    rbp
0x1804341ea  push    rbx
0x1804341eb  push    rsi
0x1804341ec  push    rdi
0x1804341ed  push    r15
0x1804341ef  lea     rbp, [rsp-210h]
0x1804341f7  sub     rsp, 310h
0x1804341fe  mov     rax, cs:__security_cookie
0x180434205  xor     rax, rsp
0x180434208  mov     [rbp+230h+var_30], rax
0x18043420f  xor     edx, edx; Val
0x180434211  lea     rcx, [rbp+230h+StartupInfo+4]; void *
0x180434215  lea     r8d, [rdx+64h]; Size
0x180434219  call    memset_0
0x18043421e  xor     edx, edx; Val
0x180434220  mov     [rbp+230h+StartupInfo.cb], 68h ; 'h'
0x180434227  mov     r8d, 20Ah; Size
0x18043422d  lea     rcx, [rbp+230h+Dst]; void *
0x180434231  call    memset_0
0x180434236  call    ?StopTRParser@@YAXXZ; StopTRParser(void)
0x18043423b  call    ?CreatePipes@@YAKXZ; CreatePipes(void)
0x180434240  mov     [rsp+330h+ExitCode], eax
0x180434244  test    eax, eax
0x180434246  jnz     loc_180434492
0x18043424c  mov     rax, cs:?g_hChild_Stdout_Wr@@3PEAXEA; void * g_hChild_Stdout_Wr
0x180434253  lea     rdx, [rbp+230h+Dst]; lpDst
0x180434257  bts     [rbp+230h+StartupInfo.dwFlags], 8
0x18043425c  lea     rcx, aWindirSystem32; "%windir%\\system32\\TransformationRules"...
0x180434263  mov     [rbp+230h+StartupInfo.hStdError], rax
0x180434267  mov     r8d, 105h; nSize
0x18043426d  mov     [rbp+230h+StartupInfo.hStdOutput], rax
0x180434271  mov     rax, cs:?g_hChild_Stdin_Rd@@3PEAXEA; void * g_hChild_Stdin_Rd
0x180434278  mov     [rbp+230h+StartupInfo.hStdInput], rax
0x18043427c  call    cs:__imp_ExpandEnvironmentStringsW
0x180434282  test    eax, eax
0x180434284  jnz     short loc_180434291
0x180434286  call    cs:__imp_GetLastError
0x18043428c  jmp     loc_180434492
0x180434291  xor     ebx, ebx
0x180434293  mov     [rsp+330h+TokenHandle], 0
0x18043429c  lea     rax, ?g_TRParserProcInfo@@3U_PROCESS_INFORMATION@@A; _PROCESS_INFORMATION g_TRParserProcInfo
0x1804342a3  xor     r9d, r9d; lpThreadAttributes
0x1804342a6  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x1804342ab  lea     rdx, [rbp+230h+Dst]; lpCommandLine
0x1804342af  lea     rax, [rbp+230h+StartupInfo]
0x1804342b3  xor     r8d, r8d; lpProcessAttributes
0x1804342b6  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x1804342bb  xor     ecx, ecx; lpApplicationName
0x1804342bd  mov     [rsp+330h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x1804342c2  mov     [rsp+330h+lpEnvironment], rbx; lpEnvironment
0x1804342c7  mov     [rsp+330h+dwCreationFlags], 24h ; '$'; dwCreationFlags
0x1804342cf  mov     [rsp+330h+bInheritHandles], ebx; bInheritHandles
0x1804342d3  call    cs:__imp_CreateProcessW
0x1804342d9  test    eax, eax
0x1804342db  jnz     short loc_1804342EC
0x1804342dd  call    cs:__imp_GetLastError
0x1804342e3  mov     [rsp+330h+ExitCode], eax
0x1804342e7  jmp     loc_18043445B
0x1804342ec  mov     rcx, qword ptr cs:?g_TRParserProcInfo@@3U_PROCESS_INFORMATION@@A; ProcessHandle
0x1804342f3  lea     r8, [rsp+330h+TokenHandle]; TokenHandle
0x1804342f8  mov     edx, 2000000h; DesiredAccess
0x1804342fd  call    cs:__imp_OpenProcessToken
0x180434303  test    eax, eax
0x180434305  jz      short loc_1804342DD
0x180434307  mov     edx, 0ACh; uBytes
0x18043430c  lea     ecx, [rdx-6Ch]; uFlags
0x18043430f  call    cs:__imp_LocalAlloc
0x180434315  mov     rbx, rax
0x180434318  test    rax, rax
0x18043431b  jnz     short loc_18043432A
0x18043431d  mov     [rsp+330h+ExitCode], 0Ch
0x180434325  jmp     loc_18043445B
0x18043432a  lea     rcx, [rax+4]; void *
0x18043432e  xor     edx, edx; Val
0x180434330  mov     r8d, 0A8h; Size
0x180434336  call    memset_0
0x18043433b  xor     edi, edi
0x18043433d  mov     dword ptr [rbx], 0Dh
0x180434343  lea     r15, ?g_TRParserPriviligeAdjustments@@3PAUPrivilegeAdjustments@@A; PrivilegeAdjustments near * g_TRParserPriviligeAdjustments
0x18043434a  cmp     edi, 0Dh
0x18043434d  jnb     short loc_180434396
0x18043434f  movsxd  rsi, edi
0x180434352  lea     r8, [rsp+330h+Luid]; lpLuid
0x180434357  add     rsi, rsi
0x18043435a  mov     qword ptr [rsp+330h+Luid.LowPart], 0
0x180434363  xor     ecx, ecx; lpSystemName
0x180434365  mov     rdx, [r15+rsi*8]; lpName
0x180434369  call    cs:__imp_LookupPrivilegeValueW
0x18043436f  test    eax, eax
0x180434371  jz      loc_1804342DD
0x180434377  mov     eax, [r15+rsi*8+8]
0x18043437c  neg     eax
0x18043437e  mov     rax, qword ptr [rsp+330h+Luid.LowPart]
0x180434383  sbb     ecx, ecx
0x180434385  mov     [rbx+4], rax
0x180434389  and     ecx, 0FFFFFFFEh
0x18043438c  add     ecx, 4
0x18043438f  mov     [rbx+0Ch], ecx
0x180434392  inc     edi
0x180434394  jmp     short loc_18043434A
0x180434396  mov     rcx, [rsp+330h+TokenHandle]; TokenHandle
0x18043439b  xor     r9d, r9d; BufferLength
0x18043439e  mov     qword ptr [rsp+330h+dwCreationFlags], 0; ReturnLength
0x1804343a7  mov     r8, rbx; NewState
0x1804343aa  xor     edx, edx; DisableAllPrivileges
0x1804343ac  mov     qword ptr [rsp+330h+bInheritHandles], 0; PreviousState
0x1804343b5  call    cs:__imp_AdjustTokenPrivileges
0x1804343bb  test    eax, eax
0x1804343bd  jz      loc_1804342DD
0x1804343c3  mov     rcx, [rsp+330h+TokenHandle]; hObject
0x1804343c8  test    rcx, rcx
0x1804343cb  jz      short loc_1804343D3
0x1804343cd  call    cs:__imp_CloseHandle
0x1804343d3  mov     rcx, qword ptr cs:?g_TRParserProcInfo@@3U_PROCESS_INFORMATION@@A+8; hThread
0x1804343da  mov     [rsp+330h+TokenHandle], 0
0x1804343e3  call    cs:__imp_ResumeThread
0x1804343e9  cmp     eax, 0FFFFFFFFh
0x1804343ec  jz      loc_1804342DD
0x1804343f2  call    ?CreateBindingHandle@@YAJXZ; CreateBindingHandle(void)
0x1804343f7  mov     [rsp+330h+ExitCode], eax
0x1804343fb  test    eax, eax
0x1804343fd  jnz     short loc_18043445B
0x1804343ff  mov     rax, qword ptr cs:?g_TRParserProcInfo@@3U_PROCESS_INFORMATION@@A; _PROCESS_INFORMATION g_TRParserProcInfo
0x180434406  lea     rdx, [rsp+330h+Handles]; lpHandles
0x18043440b  xor     r8d, r8d; bWaitAll
0x18043440e  mov     [rsp+330h+Handles], rax
0x180434413  mov     rax, cs:?g_hUninitializeEvent@@3PEAXEA; void * g_hUninitializeEvent
0x18043441a  mov     r9d, 3E8h; dwMilliseconds
0x180434420  mov     [rsp+330h+var_2C0], rax
0x180434425  lea     ecx, [r8+2]; nCount
0x180434429  call    cs:__imp_WaitForMultipleObjects
0x18043442f  test    eax, eax
0x180434431  jz      short loc_180434449
0x180434433  sub     eax, 1
0x180434436  jz      short loc_18043443F
0x180434438  cmp     eax, 101h
0x18043443d  jz      short loc_18043445B
0x18043443f  mov     [rsp+330h+ExitCode], 0Bh
0x180434447  jmp     short loc_18043445B
0x180434449  mov     rcx, qword ptr cs:?g_TRParserProcInfo@@3U_PROCESS_INFORMATION@@A; hProcess
0x180434450  lea     rdx, [rsp+330h+ExitCode]; lpExitCode
0x180434455  call    cs:__imp_GetExitCodeProcess
0x18043445b  mov     rcx, [rsp+330h+TokenHandle]; hObject
0x180434460  test    rcx, rcx
0x180434463  jz      short loc_180434474
0x180434465  call    cs:__imp_CloseHandle
0x18043446b  mov     [rsp+330h+TokenHandle], 0
0x180434474  test    rbx, rbx
0x180434477  jz      short loc_180434482
0x180434479  mov     rcx, rbx; hMem
0x18043447c  call    cs:__imp_LocalFree
0x180434482  cmp     [rsp+330h+ExitCode], 0
0x180434487  jz      short loc_18043448E
0x180434489  call    ?StopTRParser@@YAXXZ; StopTRParser(void)
0x18043448e  mov     eax, [rsp+330h+ExitCode]
0x180434492  mov     rcx, [rbp+230h+var_30]
0x180434499  xor     rcx, rsp; StackCookie
0x18043449c  call    __security_check_cookie
0x1804344a1  add     rsp, 310h
0x1804344a8  pop     r15
0x1804344aa  pop     rdi
0x1804344ab  pop     rsi
0x1804344ac  pop     rbx
0x1804344ad  pop     rbp
0x1804344ae  retn
```
