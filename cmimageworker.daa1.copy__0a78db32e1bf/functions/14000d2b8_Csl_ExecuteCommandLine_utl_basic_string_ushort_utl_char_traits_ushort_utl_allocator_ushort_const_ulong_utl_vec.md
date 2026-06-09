# Csl::ExecuteCommandLine(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ulong &,utl::vector<uchar,utl::allocator<uchar>> *,ulong)

- ea: `0x14000d2b8`
- end: `0x14000d785`
- name: `?ExecuteCommandLine@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAKPEAV?$vector@EV?$allocator@E@utl@@@3@K@Z`
- size: `1229`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000d1d4`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000ce58`
- `0x14000d16c`
- `0x14000d2b8`
- `0x14000d78c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000d492`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000d492`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d566`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000d42d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000d42d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000d51b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000d51b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d37a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d46d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d577`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d6a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d73f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d37a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d46d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d577`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d6a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d73f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d75a`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x14000d3b3`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x14000d3b3`
- `ntdll!NtTerminateProcess` at `0x14000d4b1`
- `ntdll!NtTerminateProcess` at `0x14000d4b1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000d5a1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000d5a1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000d62e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000d62e`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x14000d344`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x14000d344`

## pseudocode

```c
__int64 __fastcall Csl::ExecuteCommandLine(WCHAR **a1, DWORD *a2, __int64 a3, DWORD a4)
{
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // eax
  void *v11; // rcx
  unsigned int v12; // ebx
  bool v13; // cc
  void *v14; // rcx
  bool v15; // cc
  WCHAR *v17; // rdx
  const char *v18; // r9
  __int64 v19; // rdx
  struct _PROCESS_INFORMATION *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // r8d
  struct _PROCESS_INFORMATION *v23; // rdx
  struct _PROCESS_INFORMATION *v24; // rdx
  void *v25; // rsi
  DWORD v26; // ebx
  DWORD FileSize; // eax
  size_t v28; // r14
  __int64 v29; // r15
  void *v30; // rbx
  LPVOID lpSecurityDescriptor; // rsi
  const char *v32; // r9
  struct _PROCESS_INFORMATION *v33; // rdx
  unsigned int v34; // edi
  void *v35; // rcx
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  void *hWritePipe; // [rsp+50h] [rbp-B0h] BYREF
  void *hReadPipe; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  DWORD ExitCode; // [rsp+150h] [rbp+50h] BYREF

  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  hReadPipe = 0;
  hWritePipe = 0;
  if ( a3 )
  {
    *(_QWORD *)&PipeAttributes.nLength = 24;
    *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
    PipeAttributes.lpSecurityDescriptor = 0;
    if ( !CreatePipe(&hReadPipe, &hWritePipe, &PipeAttributes, 0) )
    {
      v9 = 1374;
LABEL_4:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v9,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
                    v8);
      v11 = hWritePipe;
      v12 = LastError;
      v13 = (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_5:
      if ( v13 )
        CloseHandle(v11);
      v14 = hReadPipe;
      v15 = (char *)hReadPipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_8:
      if ( v15 )
        CloseHandle(v14);
      return v12;
    }
    if ( !SetHandleInformation(hReadPipe, 1u, 0) )
    {
      v9 = 1378;
      goto LABEL_4;
    }
    StartupInfo.dwFlags |= 0x100u;
    StartupInfo.hStdError = hWritePipe;
    StartupInfo.hStdOutput = hWritePipe;
  }
  v17 = *a1;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, v17, 0, 0, a3 != 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v19 = 1395;
LABEL_16:
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
            v18);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v20);
    if ( (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hWritePipe);
    v14 = hReadPipe;
    v15 = (char *)hReadPipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_8;
  }
  if ( WaitForSingleObject(ProcessInformation.hProcess, a4) == 258 )
  {
    v12 = -2147023436;
    v21 = NtTerminateProcess(ProcessInformation.hProcess, -2147023436);
    if ( (int)(v21 + 0x80000000) >= 0 && v21 != -1073741558 )
      wil::details::in1diag3::Log_NtStatus(retaddr, (void *)0x80000000LL, v22, (const char *)v21, bInheritHandles);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x585,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)0x800705B4LL,
      bInheritHandles);
LABEL_24:
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v23);
    v11 = hWritePipe;
    v13 = (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_5;
  }
  ExitCode = 0;
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
    v19 = 1420;
    goto LABEL_16;
  }
  if ( a3 )
  {
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
    v25 = hWritePipe;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v26 = GetLastError();
      CloseHandle(v25);
      SetLastError(v26);
    }
    hWritePipe = 0;
    FileSize = GetFileSize(hReadPipe, 0);
    v28 = FileSize;
    if ( FileSize == -1 )
    {
      v19 = 1430;
      goto LABEL_16;
    }
    v29 = -1;
    NumberOfBytesRead = 0;
    *(_QWORD *)&PipeAttributes.bInheritHandle = -1;
    *(__m128i *)&PipeAttributes.nLength = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    if ( FileSize )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               &PipeAttributes,
                               FileSize) )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
          (const char *)0x8007000ELL,
          bInheritHandles);
        if ( *(_QWORD *)&PipeAttributes.nLength != -1 )
          operator delete(*(void **)&PipeAttributes.nLength, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_24;
      }
      memset_0(PipeAttributes.lpSecurityDescriptor, 0, v28);
      v30 = *(void **)&PipeAttributes.nLength;
      v29 = *(_QWORD *)&PipeAttributes.bInheritHandle;
      lpSecurityDescriptor = (LPVOID)(*(_QWORD *)&PipeAttributes.nLength + v28);
      if ( !ReadFile(hReadPipe, *(LPVOID *)&PipeAttributes.nLength, v28, &NumberOfBytesRead, 0) )
      {
        v34 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x5A4,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
                v32);
        if ( v30 != (void *)-1LL )
          operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v33);
        if ( (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hWritePipe);
        if ( (char *)hReadPipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hReadPipe);
        return v34;
      }
    }
    else
    {
      lpSecurityDescriptor = PipeAttributes.lpSecurityDescriptor;
      v30 = *(void **)&PipeAttributes.nLength;
    }
    v35 = *(void **)a3;
    if ( *(_QWORD *)a3 != -1 )
    {
      *(_QWORD *)(a3 + 8) = v35;
      operator delete(v35, (const struct std::nothrow_t *)&std::nothrow);
    }
    *(_QWORD *)a3 = v30;
    *(_QWORD *)(a3 + 8) = lpSecurityDescriptor;
    *(_QWORD *)(a3 + 16) = v29;
  }
  *a2 = ExitCode;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v24);
  if ( (char *)hWritePipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hWritePipe);
  if ( (char *)hReadPipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hReadPipe);
  return 0;
}

```

## disassembly

```asm
0x14000d2b8  mov     [rsp-8+arg_0], rbx
0x14000d2bd  mov     [rsp-8+arg_8], rsi
0x14000d2c2  push    rbp
0x14000d2c3  push    rdi
0x14000d2c4  push    r12
0x14000d2c6  push    r14
0x14000d2c8  push    r15
0x14000d2ca  lea     rbp, [rsp-10h]
0x14000d2cf  sub     rsp, 110h
0x14000d2d6  mov     r12, rdx
0x14000d2d9  mov     rdi, r8
0x14000d2dc  xor     edx, edx; Val
0x14000d2de  mov     rsi, rcx
0x14000d2e1  lea     rcx, [rbp+30h+StartupInfo+4]; void *
0x14000d2e5  mov     ebx, r9d
0x14000d2e8  lea     r8d, [rdx+64h]; Size
0x14000d2ec  call    memset_0
0x14000d2f1  mov     [rbp+30h+StartupInfo.cb], 68h ; 'h'
0x14000d2f8  mov     [rsp+130h+hReadPipe], 0
0x14000d301  mov     [rsp+130h+hWritePipe], 0
0x14000d30a  test    rdi, rdi
0x14000d30d  jz      loc_14000D3DC
0x14000d313  xor     r9d, r9d; nSize
0x14000d316  mov     qword ptr [rsp+130h+PipeAttributes.nLength], 18h
0x14000d31f  lea     r8, [rsp+130h+PipeAttributes]; lpPipeAttributes
0x14000d324  mov     qword ptr [rbp+30h+PipeAttributes.bInheritHandle], 1
0x14000d32c  lea     rdx, [rsp+130h+hWritePipe]; hWritePipe
0x14000d331  mov     [rbp+30h+PipeAttributes.lpSecurityDescriptor], 0
0x14000d339  lea     rcx, [rsp+130h+hReadPipe]; hReadPipe
0x14000d33e  mov     r14d, 1
0x14000d344  call    cs:__imp_CreatePipe
0x14000d34b  nop     dword ptr [rax+rax+00h]
0x14000d350  test    eax, eax
0x14000d352  jnz     short loc_14000D3A8
0x14000d354  mov     edx, 55Eh; void *
0x14000d359  mov     rcx, [rbp+38h]; this
0x14000d35d  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d364  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d369  mov     rcx, [rsp+130h+hWritePipe]; hObject
0x14000d36e  mov     ebx, eax
0x14000d370  lea     rdx, [rcx-1]
0x14000d374  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000d378  ja      short loc_14000D386
0x14000d37a  call    cs:__imp_CloseHandle
0x14000d381  nop     dword ptr [rax+rax+00h]
0x14000d386  mov     rcx, [rsp+130h+hReadPipe]; hObject
0x14000d38b  lea     rdx, [rcx-1]
0x14000d38f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000d393  ja      short loc_14000D3A1
0x14000d395  call    cs:__imp_CloseHandle
0x14000d39c  nop     dword ptr [rax+rax+00h]
0x14000d3a1  mov     eax, ebx
0x14000d3a3  jmp     loc_14000D768
0x14000d3a8  mov     rcx, [rsp+130h+hReadPipe]; hObject
0x14000d3ad  xor     r8d, r8d; dwFlags
0x14000d3b0  mov     edx, r14d; dwMask
0x14000d3b3  call    cs:__imp_SetHandleInformation
0x14000d3ba  nop     dword ptr [rax+rax+00h]
0x14000d3bf  test    eax, eax
0x14000d3c1  jnz     short loc_14000D3CA
0x14000d3c3  mov     edx, 562h
0x14000d3c8  jmp     short loc_14000D359
0x14000d3ca  mov     rax, [rsp+130h+hWritePipe]
0x14000d3cf  bts     [rbp+30h+StartupInfo.dwFlags], 8
0x14000d3d4  mov     [rbp+30h+StartupInfo.hStdError], rax
0x14000d3d8  mov     [rbp+30h+StartupInfo.hStdOutput], rax
0x14000d3dc  mov     rdx, [rsi]; lpCommandLine
0x14000d3df  lea     rcx, [rsp+130h+ProcessInformation]
0x14000d3e4  mov     [rsp+130h+lpProcessInformation], rcx; lpProcessInformation
0x14000d3e9  xor     eax, eax
0x14000d3eb  lea     rcx, [rbp+30h+StartupInfo]
0x14000d3ef  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x14000d3f4  mov     [rsp+130h+lpStartupInfo], rcx; lpStartupInfo
0x14000d3f9  xorps   xmm0, xmm0
0x14000d3fc  mov     [rsp+130h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14000d405  test    rdi, rdi
0x14000d408  mov     [rsp+130h+lpEnvironment], 0; lpEnvironment
0x14000d411  setnz   al
0x14000d414  mov     [rsp+130h+dwCreationFlags], 8000000h; dwCreationFlags
0x14000d41c  xor     r9d, r9d; lpThreadAttributes
0x14000d41f  mov     [rsp+130h+bInheritHandles], eax; int
0x14000d423  xor     r8d, r8d; lpProcessAttributes
0x14000d426  xor     ecx, ecx; lpApplicationName
0x14000d428  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x14000d42d  call    cs:__imp_CreateProcessW
0x14000d434  nop     dword ptr [rax+rax+00h]
0x14000d439  test    eax, eax
0x14000d43b  jnz     short loc_14000D48B
0x14000d43d  mov     edx, 573h; void *
0x14000d442  mov     rcx, [rbp+38h]; this
0x14000d446  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d44d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d452  lea     rcx, [rsp+130h+ProcessInformation]; this
0x14000d457  mov     ebx, eax
0x14000d459  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14000d45e  mov     rcx, [rsp+130h+hWritePipe]; hObject
0x14000d463  lea     rdx, [rcx-1]
0x14000d467  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000d46b  ja      short loc_14000D479
0x14000d46d  call    cs:__imp_CloseHandle
0x14000d474  nop     dword ptr [rax+rax+00h]
0x14000d479  mov     rcx, [rsp+130h+hReadPipe]
0x14000d47e  lea     rax, [rcx-1]
0x14000d482  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d486  jmp     loc_14000D393
0x14000d48b  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hHandle
0x14000d490  mov     edx, ebx; dwMilliseconds
0x14000d492  call    cs:__imp_WaitForSingleObject
0x14000d499  nop     dword ptr [rax+rax+00h]
0x14000d49e  mov     rcx, [rsp+130h+ProcessInformation.hProcess]; hProcess
0x14000d4a3  cmp     eax, 102h
0x14000d4a8  jnz     short loc_14000D510
0x14000d4aa  mov     ebx, 800705B4h
0x14000d4af  mov     edx, ebx; ExitStatus
0x14000d4b1  call    cs:__imp_NtTerminateProcess
0x14000d4b8  nop     dword ptr [rax+rax+00h]
0x14000d4bd  mov     edx, 80000000h; void *
0x14000d4c2  lea     ecx, [rax+rdx]
0x14000d4c5  test    edx, ecx
0x14000d4c7  jnz     short loc_14000D4DC
0x14000d4c9  cmp     eax, 0C000010Ah
0x14000d4ce  jz      short loc_14000D4DC
0x14000d4d0  mov     rcx, [rbp+38h]; this
0x14000d4d4  mov     r9d, eax; char *
0x14000d4d7  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x14000d4dc  mov     rcx, [rbp+38h]; this
0x14000d4e0  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d4e7  mov     r9d, ebx; char *
0x14000d4ea  mov     edx, 585h; void *
0x14000d4ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d4f4  lea     rcx, [rsp+130h+ProcessInformation]; this
0x14000d4f9  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14000d4fe  mov     rcx, [rsp+130h+hWritePipe]
0x14000d503  lea     rax, [rcx-1]
0x14000d507  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d50b  jmp     loc_14000D378
0x14000d510  lea     rdx, [rbp+30h+ExitCode]; lpExitCode
0x14000d514  mov     [rbp+30h+ExitCode], 0
0x14000d51b  call    cs:__imp_GetExitCodeProcess
0x14000d522  nop     dword ptr [rax+rax+00h]
0x14000d527  test    eax, eax
0x14000d529  jnz     short loc_14000D535
0x14000d52b  mov     edx, 58Ch
0x14000d530  jmp     loc_14000D442
0x14000d535  test    rdi, rdi
0x14000d538  jz      loc_14000D71F
0x14000d53e  lea     rcx, [rsp+130h+ProcessInformation]; this
0x14000d543  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14000d548  mov     rsi, [rsp+130h+hWritePipe]
0x14000d54d  xor     eax, eax
0x14000d54f  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x14000d554  xorps   xmm0, xmm0
0x14000d557  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x14000d55c  lea     rax, [rsi-1]
0x14000d560  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d564  ja      short loc_14000D591
0x14000d566  call    cs:__imp_GetLastError
0x14000d56d  nop     dword ptr [rax+rax+00h]
0x14000d572  mov     rcx, rsi; hObject
0x14000d575  mov     ebx, eax
0x14000d577  call    cs:__imp_CloseHandle
0x14000d57e  nop     dword ptr [rax+rax+00h]
0x14000d583  mov     ecx, ebx; dwErrCode
0x14000d585  call    cs:__imp_SetLastError
0x14000d58c  nop     dword ptr [rax+rax+00h]
0x14000d591  mov     rcx, [rsp+130h+hReadPipe]; hFile
0x14000d596  xor     edx, edx; lpFileSizeHigh
0x14000d598  mov     [rsp+130h+hWritePipe], 0
0x14000d5a1  call    cs:__imp_GetFileSize
0x14000d5a8  nop     dword ptr [rax+rax+00h]
0x14000d5ad  mov     r14d, eax
0x14000d5b0  cmp     eax, 0FFFFFFFFh
0x14000d5b3  jnz     short loc_14000D5BF
0x14000d5b5  mov     edx, 596h
0x14000d5ba  jmp     loc_14000D442
0x14000d5bf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000d5c7  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000d5cb  mov     [rbp+30h+NumberOfBytesRead], 0
0x14000d5d2  mov     qword ptr [rbp+30h+PipeAttributes.bInheritHandle], r15
0x14000d5d6  movdqu  xmmword ptr [rsp+130h+PipeAttributes.nLength], xmm0
0x14000d5dc  test    eax, eax
0x14000d5de  jz      loc_14000D6F2
0x14000d5e4  mov     rdx, r14
0x14000d5e7  lea     rcx, [rsp+130h+PipeAttributes]
0x14000d5ec  mov     rsi, r14
0x14000d5ef  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000d5f4  test    al, al
0x14000d5f6  jz      loc_14000D6B5
0x14000d5fc  mov     rcx, [rbp+30h+PipeAttributes.lpSecurityDescriptor]; void *
0x14000d600  mov     r8, r14; Size
0x14000d603  xor     edx, edx; Val
0x14000d605  call    memset_0
0x14000d60a  mov     rbx, qword ptr [rsp+130h+PipeAttributes.nLength]
0x14000d60f  lea     r9, [rbp+30h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000d613  mov     rcx, [rsp+130h+hReadPipe]; hFile
0x14000d618  mov     rdx, rbx; lpBuffer
0x14000d61b  mov     r15, qword ptr [rbp+30h+PipeAttributes.bInheritHandle]
0x14000d61f  mov     r8d, r14d; nNumberOfBytesToRead
0x14000d622  add     rsi, rbx
0x14000d625  mov     qword ptr [rsp+130h+bInheritHandles], 0; lpOverlapped
0x14000d62e  call    cs:__imp_ReadFile
0x14000d635  nop     dword ptr [rax+rax+00h]
0x14000d63a  test    eax, eax
0x14000d63c  jnz     loc_14000D6FB
0x14000d642  mov     rcx, [rbp+38h]; this
0x14000d646  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d64d  mov     edx, 5A4h; void *
0x14000d652  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d657  mov     edi, eax
0x14000d659  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d65d  jz      short loc_14000D66E
0x14000d65f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d666  mov     rcx, rbx; void *
0x14000d669  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d66e  lea     rcx, [rsp+130h+ProcessInformation]; this
0x14000d673  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14000d678  mov     rcx, [rsp+130h+hWritePipe]; hObject
0x14000d67d  lea     rdx, [rcx-1]
0x14000d681  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000d685  ja      short loc_14000D693
0x14000d687  call    cs:__imp_CloseHandle
0x14000d68e  nop     dword ptr [rax+rax+00h]
0x14000d693  mov     rcx, [rsp+130h+hReadPipe]; hObject
0x14000d698  lea     rax, [rcx-1]
0x14000d69c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d6a0  ja      short loc_14000D6AE
0x14000d6a2  call    cs:__imp_CloseHandle
0x14000d6a9  nop     dword ptr [rax+rax+00h]
0x14000d6ae  mov     eax, edi
0x14000d6b0  jmp     loc_14000D768
0x14000d6b5  mov     rcx, [rbp+38h]; this
0x14000d6b9  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d6c0  mov     ebx, 8007000Eh
0x14000d6c5  mov     edx, 59Dh; void *
0x14000d6ca  mov     r9d, ebx; char *
0x14000d6cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d6d2  mov     rcx, qword ptr [rsp+130h+PipeAttributes.nLength]; void *
0x14000d6d7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d6db  jz      loc_14000D4F4
0x14000d6e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d6e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d6ed  jmp     loc_14000D4F4
0x14000d6f2  mov     rsi, [rbp+30h+PipeAttributes.lpSecurityDescriptor]
0x14000d6f6  mov     rbx, qword ptr [rsp+130h+PipeAttributes.nLength]
0x14000d6fb  mov     rcx, [rdi]; void *
0x14000d6fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d702  jz      short loc_14000D714
0x14000d704  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d70b  mov     [rdi+8], rcx
0x14000d70f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d714  mov     [rdi], rbx
0x14000d717  mov     [rdi+8], rsi
0x14000d71b  mov     [rdi+10h], r15
0x14000d71f  mov     eax, [rbp+30h+ExitCode]
0x14000d722  lea     rcx, [rsp+130h+ProcessInformation]; this
0x14000d727  mov     [r12], eax
0x14000d72b  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14000d730  mov     rcx, [rsp+130h+hWritePipe]; hObject
0x14000d735  lea     rax, [rcx-1]
0x14000d739  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d73d  ja      short loc_14000D74B
0x14000d73f  call    cs:__imp_CloseHandle
0x14000d746  nop     dword ptr [rax+rax+00h]
0x14000d74b  mov     rcx, [rsp+130h+hReadPipe]; hObject
0x14000d750  lea     rax, [rcx-1]
0x14000d754  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d758  ja      short loc_14000D766
0x14000d75a  call    cs:__imp_CloseHandle
0x14000d761  nop     dword ptr [rax+rax+00h]
0x14000d766  xor     eax, eax
0x14000d768  lea     r11, [rsp+130h+var_20]
0x14000d770  mov     rbx, [r11+30h]
0x14000d774  mov     rsi, [r11+38h]
0x14000d778  mov     rsp, r11
0x14000d77b  pop     r15
0x14000d77d  pop     r14
0x14000d77f  pop     r12
0x14000d781  pop     rdi
0x14000d782  pop     rbp
0x14000d783  retn
```
