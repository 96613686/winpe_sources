# ShellProcess::Start(ushort const *,int,void *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800da60c`
- end: `0x1800daa2f`
- name: `?Start@ShellProcess@@QEAAJPEBGHPEAX000@Z`
- size: `1059`
- prototype: `__int64 __usercall@<rax>(ShellProcess *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, void *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801f8310`

## callees

- `0x1800793cc`
- `0x18007c2dc`
- `0x18007cf9c`
- `0x18007d14c`
- `0x18008d550`
- `0x1800954c4`
- `0x1800da60c`
- `0x1800daa38`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180246f8c`
- `0x1802e35dc`
- `0x1802e8bbc`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800da855`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800da855`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da6bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da9c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800da81c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800da81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800da7bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800da7bf`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800da7ce`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800da7ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800da98b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800da98b`

## string_xrefs

- `0x1800da754`: `ComSpec`
- `0x1800da8cc`: `.shell: Not enough room for command line\n`
- `0x1800da940`: `CreateProcess(%s) failed, %s.\n    "%s"\n`
- `0x1800da9a0`: `.shell: Unable to create reader thread\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellProcess::Start(
        ShellProcess *this,
        const unsigned __int16 *a2,
        int a3,
        void *a4,
        const unsigned __int16 *lpFileName,
        const unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  wint_t *v10; // rbx
  char v11; // r14
  __int64 v12; // r9
  DWORD IoPipes; // edi
  HANDLE EventW; // rax
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // eax
  DWORD dwCreationFlags; // ecx
  signed int v18; // eax
  int *v19; // r8
  unsigned __int16 **v20; // r9
  const unsigned __int16 *v21; // rbx
  unsigned __int16 *v22; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-90h]
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-80h] BYREF
  LPWSTR lpCommandLine[3]; // [rsp+F8h] [rbp-10h] BYREF
  char v31; // [rsp+110h] [rbp+8h] BYREF

  v28 = -2;
  ProcessInformation.hProcess = a7;
  v10 = g_CurCmd;
  v11 = 1;
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
    (unsigned int)lpCommandLine,
    (unsigned int)&v31,
    260,
    (_DWORD)a4,
    1);
  if ( !a6 || lpFileName || v12 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 9) = EventW;
    if ( EventW )
    {
      if ( a3
        || (IoPipes = ShellProcess::CreateIoPipes(
                        (void **)this,
                        a4,
                        lpFileName,
                        a6,
                        (LPCWSTR)ProcessInformation.hProcess)) == 0 )
      {
        if ( (unsigned int)DbsDynamicString<unsigned short>::GetEnvStr(lpCommandLine, L"DBGENG_SHELL_PREFIX", 0) )
        {
          v11 = 0;
          if ( (unsigned int)DbsDynamicString<unsigned short>::GetEnvStr(lpCommandLine, L"SHELL", 0) )
            DbsDynamicString<unsigned short>::GetEnvStr(lpCommandLine, L"ComSpec", L"cmd.exe");
        }
        if ( !v10 )
          goto LABEL_13;
        while ( iswspace(*v10) )
          ++v10;
        if ( *v10
          && (!v11
           && (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)lpCommandLine, L" /c")
           || (unsigned int)DbsDynamicString<unsigned short>::AppendStr(
                              (DbsDynamicBuffer *)lpCommandLine,
                              (void *)L" \"")
           || (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)lpCommandLine, v10)
           || (unsigned int)DbsDynamicString<unsigned short>::AppendChar((DbsDynamicBuffer *)lpCommandLine)) )
        {
          ErrOut(L".shell: Not enough room for command line\n");
          IoPipes = -2147024809;
        }
        else
        {
LABEL_13:
          memset(&StartupInfo, 0, sizeof(StartupInfo));
          StartupInfo.cb = 104;
          if ( !a3 )
          {
            StartupInfo.dwFlags = 256;
            StartupInfo.hStdInput = (HANDLE)*((_QWORD *)this + 2);
            StartupInfo.hStdOutput = (HANDLE)*((_QWORD *)this + 3);
            StartupInfo.hStdError = (HANDLE)*((_QWORD *)this + 4);
          }
          StartupInfo.wShowWindow = 5;
          *(_OWORD *)&ProcessInformation.hThread = 0;
          v27 = 0;
          CurrentProcess = GetCurrentProcess();
          PriorityClass = GetPriorityClass(CurrentProcess);
          dwCreationFlags = PriorityClass | 8;
          if ( !a3 )
            dwCreationFlags = PriorityClass;
          if ( CreateProcessW(
                 0,
                 lpCommandLine[0],
                 0,
                 0,
                 a3 == 0,
                 dwCreationFlags,
                 0,
                 0,
                 &StartupInfo,
                 (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
          {
            *((_QWORD *)this + 7) = ProcessInformation.hThread;
            *((_QWORD *)this + 6) = *(_QWORD *)&ProcessInformation.dwProcessId;
            if ( !*((_QWORD *)this + 1)
              || (LODWORD(ProcessInformation.hProcess) = 0,
                  Thread = CreateThread(0, 0, ShellProcess::ReaderThreadCb, this, 0, (LPDWORD)&ProcessInformation),
                  (*((_QWORD *)this + 8) = Thread) != 0) )
            {
              if ( !a3 )
                ShellProcess::WaitForProcessExit(this);
              IoPipes = 0;
            }
            else
            {
              ErrOut(L".shell: Unable to create reader thread\n");
              if ( GetLastError() )
              {
                LastError = GetLastError();
                IoPipes = LastError;
                if ( LastError > 0 )
                  IoPipes = (unsigned __int16)LastError | 0x80070000;
              }
              else
              {
                IoPipes = -2147467259;
              }
            }
          }
          else
          {
            if ( GetLastError() )
            {
              v18 = GetLastError();
              IoPipes = v18;
              if ( v18 > 0 )
                IoPipes = (unsigned __int16)v18 | 0x80070000;
            }
            else
            {
              IoPipes = -2147467259;
            }
            if ( GetLastError() == 2 )
            {
              ErrOut(L"'%s' could not be executed\n", lpCommandLine[0]);
            }
            else
            {
              v21 = FormatAnyStatus(IoPipes, 0, v19, v20);
              v22 = FormatStatusCode(IoPipes);
              ErrOut(L"CreateProcess(%s) failed, %s.\n    \"%s\"\n", lpCommandLine[0], v22, v21);
            }
          }
        }
      }
    }
    else
    {
      IoPipes = -2147467259;
      ErrOut(L".shell: Error creating event\n");
    }
    ShellProcess::Close(this);
  }
  else
  {
    ErrOut(L".shell: Input must be redirected with output\n");
    IoPipes = -2147024809;
  }
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(lpCommandLine);
  return IoPipes;
}

```

## disassembly

```asm
0x1800da60c  mov     rax, rsp
0x1800da60f  push    rbp
0x1800da610  push    rsi
0x1800da611  push    rdi
0x1800da612  push    r12
0x1800da614  push    r13
0x1800da616  push    r14
0x1800da618  push    r15
0x1800da61a  lea     rbp, [rax-258h]
0x1800da621  sub     rsp, 320h
0x1800da628  mov     [rsp+350h+var_2E0], 0FFFFFFFFFFFFFFFEh
0x1800da631  mov     [rax+10h], rbx
0x1800da635  mov     rax, cs:__security_cookie
0x1800da63c  xor     rax, rsp
0x1800da63f  mov     [rbp+250h+var_40], rax
0x1800da646  mov     rdi, r9
0x1800da649  mov     r15d, r8d
0x1800da64c  mov     rsi, rcx
0x1800da64f  mov     r12, [rbp+250h+lpFileName]
0x1800da656  mov     r13, [rbp+250h+arg_28]
0x1800da65d  mov     rax, [rbp+250h+arg_30]
0x1800da664  mov     [rsp+350h+ProcessInformation.hProcess], rax
0x1800da669  mov     rbx, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800da670  mov     r14d, 1
0x1800da676  mov     byte ptr [rsp+350h+bInheritHandles], r14b
0x1800da67b  mov     r8d, 104h
0x1800da681  lea     rdx, [rbp+250h+var_248]
0x1800da685  lea     rcx, [rbp+250h+lpCommandLine]
0x1800da689  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1800da68e  nop
0x1800da68f  test    r13, r13
0x1800da692  jz      short loc_1800DA6B4
0x1800da694  test    r12, r12
0x1800da697  jnz     short loc_1800DA6B4
0x1800da699  test    r9, r9
0x1800da69c  jnz     short loc_1800DA6B4
0x1800da69e  lea     rcx, aShellInputMust; ".shell: Input must be redirected with o"...
0x1800da6a5  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da6aa  mov     edi, 80070057h
0x1800da6af  jmp     loc_1800DA9F9
0x1800da6b4  xor     r9d, r9d; lpName
0x1800da6b7  xor     r8d, r8d; bInitialState
0x1800da6ba  mov     edx, r14d; bManualReset
0x1800da6bd  xor     ecx, ecx; lpEventAttributes
0x1800da6bf  call    cs:__imp_CreateEventW
0x1800da6c6  nop     dword ptr [rax+rax+00h]
0x1800da6cb  mov     [rsi+48h], rax
0x1800da6cf  test    rax, rax
0x1800da6d2  jnz     short loc_1800DA6EA
0x1800da6d4  mov     edi, 80004005h
0x1800da6d9  lea     rcx, aShellErrorCrea; ".shell: Error creating event\n"
0x1800da6e0  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da6e5  jmp     loc_1800DA9F0
0x1800da6ea  test    r15d, r15d
0x1800da6ed  jnz     short loc_1800DA719
0x1800da6ef  mov     rax, [rsp+350h+ProcessInformation.hProcess]
0x1800da6f4  mov     qword ptr [rsp+350h+bInheritHandles], rax; LPCWSTR
0x1800da6f9  mov     r9, r13; LPCWSTR
0x1800da6fc  mov     r8, r12; lpFileName
0x1800da6ff  mov     rdx, rdi; hSourceHandle
0x1800da702  mov     rcx, rsi; this
0x1800da705  call    ?CreateIoPipes@ShellProcess@@QEAAJPEAXPEBG11@Z; ShellProcess::CreateIoPipes(void *,ushort const *,ushort const *,ushort const *)
0x1800da70a  mov     edi, eax
0x1800da70c  xor     r12d, r12d
0x1800da70f  test    eax, eax
0x1800da711  jnz     loc_1800DA9F0
0x1800da717  jmp     short loc_1800DA71C
0x1800da719  xor     r12d, r12d
0x1800da71c  xor     r8d, r8d
0x1800da71f  lea     rdx, aDbgengShellPre; "DBGENG_SHELL_PREFIX"
0x1800da726  lea     rcx, [rbp+250h+lpCommandLine]
0x1800da72a  call    ?GetEnvStr@?$DbsDynamicString@G@@QEAAJPEBG0@Z; DbsDynamicString<ushort>::GetEnvStr(ushort const *,ushort const *)
0x1800da72f  test    eax, eax
0x1800da731  jz      short loc_1800DA764
0x1800da733  mov     r14b, r12b
0x1800da736  xor     r8d, r8d
0x1800da739  lea     rdx, aShell; "SHELL"
0x1800da740  lea     rcx, [rbp+250h+lpCommandLine]
0x1800da744  call    ?GetEnvStr@?$DbsDynamicString@G@@QEAAJPEBG0@Z; DbsDynamicString<ushort>::GetEnvStr(ushort const *,ushort const *)
0x1800da749  test    eax, eax
0x1800da74b  jz      short loc_1800DA764
0x1800da74d  lea     r8, aCmdExe_0; "cmd.exe"
0x1800da754  lea     rdx, aComspec; "ComSpec"
0x1800da75b  lea     rcx, [rbp+250h+lpCommandLine]
0x1800da75f  call    ?GetEnvStr@?$DbsDynamicString@G@@QEAAJPEBG0@Z; DbsDynamicString<ushort>::GetEnvStr(ushort const *,ushort const *)
0x1800da764  test    rbx, rbx
0x1800da767  jnz     loc_1800DA852
0x1800da76d  mov     ebx, 68h ; 'h'
0x1800da772  mov     r8d, ebx; Size
0x1800da775  xor     edx, edx; Val
0x1800da777  lea     rcx, [rbp+250h+StartupInfo]; void *
0x1800da77b  call    memset
0x1800da780  mov     [rbp+250h+StartupInfo.cb], ebx
0x1800da783  test    r15d, r15d
0x1800da786  jnz     short loc_1800DA7A7
0x1800da788  mov     [rbp+250h+StartupInfo.dwFlags], 100h
0x1800da78f  mov     rax, [rsi+10h]
0x1800da793  mov     [rbp+250h+StartupInfo.hStdInput], rax
0x1800da797  mov     rax, [rsi+18h]
0x1800da79b  mov     [rbp+250h+StartupInfo.hStdOutput], rax
0x1800da79f  mov     rax, [rsi+20h]
0x1800da7a3  mov     [rbp+250h+StartupInfo.hStdError], rax
0x1800da7a7  mov     eax, 5
0x1800da7ac  mov     [rbp+250h+StartupInfo.wShowWindow], ax
0x1800da7b0  xorps   xmm0, xmm0
0x1800da7b3  xor     eax, eax
0x1800da7b5  movups  xmmword ptr [rsp+350h+ProcessInformation.hThread], xmm0
0x1800da7ba  mov     [rsp+350h+var_2E8], rax
0x1800da7bf  call    cs:__imp_GetCurrentProcess
0x1800da7c6  nop     dword ptr [rax+rax+00h]
0x1800da7cb  mov     rcx, rax; hProcess
0x1800da7ce  call    cs:__imp_GetPriorityClass
0x1800da7d5  nop     dword ptr [rax+rax+00h]
0x1800da7da  mov     ecx, eax
0x1800da7dc  or      ecx, 8
0x1800da7df  test    r15d, r15d
0x1800da7e2  cmovz   ecx, eax
0x1800da7e5  mov     eax, r12d
0x1800da7e8  setz    al
0x1800da7eb  lea     rdx, [rsp+350h+ProcessInformation.hThread]
0x1800da7f0  mov     [rsp+350h+lpProcessInformation], rdx; lpProcessInformation
0x1800da7f5  lea     rdx, [rbp+250h+StartupInfo]
0x1800da7f9  mov     [rsp+350h+lpStartupInfo], rdx; lpStartupInfo
0x1800da7fe  mov     [rsp+350h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800da803  mov     [rsp+350h+lpEnvironment], r12; lpEnvironment
0x1800da808  mov     [rsp+350h+dwCreationFlags], ecx; dwCreationFlags
0x1800da80c  mov     [rsp+350h+bInheritHandles], eax; bInheritHandles
0x1800da810  xor     r9d, r9d; lpThreadAttributes
0x1800da813  xor     r8d, r8d; lpProcessAttributes
0x1800da816  mov     rdx, [rbp+250h+lpCommandLine]; lpCommandLine
0x1800da81a  xor     ecx, ecx; lpApplicationName
0x1800da81c  call    cs:__imp_CreateProcessW
0x1800da823  nop     dword ptr [rax+rax+00h]
0x1800da828  test    eax, eax
0x1800da82a  jnz     loc_1800DA951
0x1800da830  call    cs:__imp_GetLastError
0x1800da837  nop     dword ptr [rax+rax+00h]
0x1800da83c  test    eax, eax
0x1800da83e  jnz     loc_1800DA8E2
0x1800da844  mov     edi, 80004005h
0x1800da849  jmp     loc_1800DA8FD
0x1800da84e  add     rbx, 2
0x1800da852  movzx   ecx, word ptr [rbx]; C
0x1800da855  call    cs:__imp_iswspace
0x1800da85c  nop     dword ptr [rax+rax+00h]
0x1800da861  test    eax, eax
0x1800da863  jnz     short loc_1800DA84E
0x1800da865  cmp     [rbx], r12w
0x1800da869  jz      loc_1800DA76D
0x1800da86f  or      edi, 0FFFFFFFFh
0x1800da872  test    r14b, r14b
0x1800da875  jnz     short loc_1800DA88E
0x1800da877  mov     r8d, edi
0x1800da87a  lea     rdx, aC_0; " /c"
0x1800da881  lea     rcx, [rbp+250h+lpCommandLine]; this
0x1800da885  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x1800da88a  test    eax, eax
0x1800da88c  jnz     short loc_1800DA8CC
0x1800da88e  mov     r8d, edi
0x1800da891  lea     rdx, asc_180654BF8; " \""
0x1800da898  lea     rcx, [rbp+250h+lpCommandLine]; this
0x1800da89c  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x1800da8a1  test    eax, eax
0x1800da8a3  jnz     short loc_1800DA8CC
0x1800da8a5  mov     r8d, edi
0x1800da8a8  mov     rdx, rbx; Src
0x1800da8ab  lea     rcx, [rbp+250h+lpCommandLine]; this
0x1800da8af  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x1800da8b4  test    eax, eax
0x1800da8b6  jnz     short loc_1800DA8CC
0x1800da8b8  lea     edx, [rax+22h]
0x1800da8bb  lea     rcx, [rbp+250h+lpCommandLine]; this
0x1800da8bf  call    ?AppendChar@?$DbsDynamicString@G@@QEAAJG@Z; DbsDynamicString<ushort>::AppendChar(ushort)
0x1800da8c4  test    eax, eax
0x1800da8c6  jz      loc_1800DA76D
0x1800da8cc  lea     rcx, aShellNotEnough; ".shell: Not enough room for command lin"...
0x1800da8d3  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da8d8  mov     edi, 80070057h
0x1800da8dd  jmp     loc_1800DA9F0
0x1800da8e2  call    cs:__imp_GetLastError
0x1800da8e9  nop     dword ptr [rax+rax+00h]
0x1800da8ee  mov     edi, eax
0x1800da8f0  test    eax, eax
0x1800da8f2  jle     short loc_1800DA8FD
0x1800da8f4  movzx   edi, ax
0x1800da8f7  or      edi, 80070000h
0x1800da8fd  call    cs:__imp_GetLastError
0x1800da904  nop     dword ptr [rax+rax+00h]
0x1800da909  cmp     eax, 2
0x1800da90c  jnz     short loc_1800DA923
0x1800da90e  mov     rdx, [rbp+250h+lpCommandLine]
0x1800da912  lea     rcx, aSCouldNotBeExe; "'%s' could not be executed\n"
0x1800da919  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da91e  jmp     loc_1800DA9F0
0x1800da923  xor     edx, edx; Arguments
0x1800da925  mov     ecx, edi; dwMessageId
0x1800da927  call    ?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z; FormatAnyStatus(long,void *,int *,ushort * *)
0x1800da92c  mov     rbx, rax
0x1800da92f  mov     ecx, edi; int
0x1800da931  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800da936  mov     r9, rbx
0x1800da939  mov     r8, rax
0x1800da93c  mov     rdx, [rbp+250h+lpCommandLine]
0x1800da940  lea     rcx, aCreateprocessS; "CreateProcess(%s) failed, %s.\n    \"%s"...
0x1800da947  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da94c  jmp     loc_1800DA9F0
0x1800da951  mov     rax, [rsp+350h+ProcessInformation.hThread]
0x1800da956  mov     [rsi+38h], rax
0x1800da95a  mov     rax, qword ptr [rsp+350h+ProcessInformation.dwProcessId]
0x1800da95f  mov     [rsi+30h], rax
0x1800da963  cmp     [rsi+8], r12
0x1800da967  jz      short loc_1800DA9E0
0x1800da969  mov     dword ptr [rsp+350h+ProcessInformation.hProcess], r12d
0x1800da96e  lea     rax, [rsp+350h+ProcessInformation]
0x1800da973  mov     qword ptr [rsp+350h+dwCreationFlags], rax; lpThreadId
0x1800da978  mov     [rsp+350h+bInheritHandles], r12d; dwCreationFlags
0x1800da97d  mov     r9, rsi; lpParameter
0x1800da980  lea     r8, ?ReaderThreadCb@ShellProcess@@SAKPEAX@Z; lpStartAddress
0x1800da987  xor     edx, edx; dwStackSize
0x1800da989  xor     ecx, ecx; lpThreadAttributes
0x1800da98b  call    cs:__imp_CreateThread
0x1800da992  nop     dword ptr [rax+rax+00h]
0x1800da997  mov     [rsi+40h], rax
0x1800da99b  test    rax, rax
0x1800da99e  jnz     short loc_1800DA9E0
0x1800da9a0  lea     rcx, aShellUnableToC; ".shell: Unable to create reader thread"...
0x1800da9a7  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800da9ac  call    cs:__imp_GetLastError
0x1800da9b3  nop     dword ptr [rax+rax+00h]
0x1800da9b8  test    eax, eax
0x1800da9ba  jnz     short loc_1800DA9C3
0x1800da9bc  mov     edi, 80004005h
0x1800da9c1  jmp     short loc_1800DA9F0
0x1800da9c3  call    cs:__imp_GetLastError
0x1800da9ca  nop     dword ptr [rax+rax+00h]
0x1800da9cf  mov     edi, eax
0x1800da9d1  test    eax, eax
0x1800da9d3  jle     short loc_1800DA9F0
0x1800da9d5  movzx   edi, ax
0x1800da9d8  or      edi, 80070000h
0x1800da9de  jmp     short loc_1800DA9F0
0x1800da9e0  test    r15d, r15d
0x1800da9e3  jnz     short loc_1800DA9ED
0x1800da9e5  mov     rcx, rsi; this
0x1800da9e8  call    ?WaitForProcessExit@ShellProcess@@QEAAXXZ; ShellProcess::WaitForProcessExit(void)
0x1800da9ed  mov     edi, r12d
0x1800da9f0  mov     rcx, rsi; this
0x1800da9f3  call    ?Close@ShellProcess@@QEAAXXZ; ShellProcess::Close(void)
0x1800da9f8  nop
0x1800da9f9  lea     rcx, [rbp+250h+lpCommandLine]
0x1800da9fd  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1800daa02  mov     eax, edi
0x1800daa04  mov     rcx, [rbp+250h+var_40]
0x1800daa0b  xor     rcx, rsp; StackCookie
0x1800daa0e  call    __security_check_cookie
0x1800daa13  mov     rbx, [rsp+350h+arg_8]
0x1800daa1b  add     rsp, 320h
0x1800daa22  pop     r15
0x1800daa24  pop     r14
0x1800daa26  pop     r13
0x1800daa28  pop     r12
0x1800daa2a  pop     rdi
0x1800daa2b  pop     rsi
0x1800daa2c  pop     rbp
0x1800daa2d  retn
```
