# AssertW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000c0a8`
- end: `0x18000c23e`
- name: `?AssertW@@YAXPEBG000K@Z`
- size: `406`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, CHAR Response)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014ed8`

## callees

- `0x18000c0a8`
- `0x18000c244`

## import_xrefs

- `ntdll!DbgPrompt` at `0x18000c17e`
- `ntdll!DbgPrompt` at `0x18000c17e`
- `ntdll!DbgPrintEx` at `0x18000c15f`
- `ntdll!DbgPrintEx` at `0x18000c1a7`
- `ntdll!DbgPrintEx` at `0x18000c221`
- `ntdll!DbgPrintEx` at `0x18000c15f`
- `ntdll!DbgPrintEx` at `0x18000c1a7`
- `ntdll!DbgPrintEx` at `0x18000c221`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c1f0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18000c1f0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000c206`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000c206`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c1e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c1e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0f0`

## string_xrefs

- `0x18000c177`: `Break, Go (continue), terminate Process, or terminate Thread (bgpt)? `
- `0x18000c19d`: `(No kernel debugger is present.) Respond with:\n  g                    -- Go (continue)\n  eb 0x%p 'p';g  -- terminate Process\n  eb 0x%p 't';g  -- terminate Thread\n or regular debugging.\n`

## pseudocode

```c
void __fastcall AssertW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int16 Response)
{
  int v5; // eax
  int v6; // ebx
  BOOL v7; // eax
  char v8; // cl
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax

  if ( IsDebuggerPresent() || (unsigned int)IsKernelDebuggerPresent() )
  {
    while ( 1 )
    {
      v5 = IsKernelDebuggerPresent();
      Response = 63;
      v6 = v5;
      if ( !v5 )
      {
        v7 = IsDebuggerPresent();
        v8 = Response;
        if ( v7 )
          v8 = 103;
        LOBYTE(Response) = v8;
      }
      DbgPrintEx(
        0x65u,
        0,
        "\n*** Assertion failed: %ls%ls%ls\n***   %s%ls%sSource: `%ls:%ld`\n\n",
        L"Unexpected HRESULT in MilInstrumentation* caller",
        (const wchar_t *)&qword_18001A0D0,
        (const wchar_t *)&qword_18001A0D0,
        "Function: ",
        L"MilInstrumentationBreak",
        ", ",
        L"clientcore\\windows\\dwm\\shared\\util\\utillib\\debugbreak.cpp",
        221);
      if ( !v6 )
      {
        DbgPrintEx(
          0x65u,
          0,
          "(No kernel debugger is present.) Respond with:\n"
          "  g                    -- Go (continue)\n"
          "  eb 0x%p 'p';g  -- terminate Process\n"
          "  eb 0x%p 't';g  -- terminate Thread\n"
          " or regular debugging.\n",
          &Response,
          &Response);
        __debugbreak();
      }
      DbgPrompt("Break, Go (continue), terminate Process, or terminate Thread (bgpt)? ", (PCH)&Response, 2u);
      if ( (char)Response > 98 )
      {
        if ( (_BYTE)Response == 103 )
          return;
        if ( (_BYTE)Response == 105 )
          goto LABEL_25;
        if ( (_BYTE)Response != 112 )
        {
          if ( (_BYTE)Response != 116 )
            goto LABEL_24;
          goto LABEL_22;
        }
LABEL_23:
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0xC0000001);
LABEL_24:
        DbgPrintEx(0x65u, 0, "Unrecognized response.\n");
      }
      else
      {
        if ( (_BYTE)Response == 98 || (_BYTE)Response == 66 )
        {
          __debugbreak();
          return;
        }
        if ( (_BYTE)Response == 71 )
          return;
        if ( (_BYTE)Response != 73 )
        {
          if ( (_BYTE)Response != 80 )
          {
            if ( (_BYTE)Response != 84 )
              goto LABEL_24;
LABEL_22:
            CurrentThread = GetCurrentThread();
            TerminateThread(CurrentThread, 0xC0000001);
            goto LABEL_24;
          }
          goto LABEL_23;
        }
LABEL_25:
        DbgPrintEx(0x65u, 0, "'i' is only supported with debug builds.\n");
      }
    }
  }
}

```

## disassembly

```asm
0x18000c0a8  mov     [rsp+arg_0], rbx
0x18000c0ad  mov     [rsp+arg_8], rbp
0x18000c0b2  push    r14
0x18000c0b4  sub     rsp, 60h
0x18000c0b8  call    cs:__imp_IsDebuggerPresent
0x18000c0be  test    eax, eax
0x18000c0c0  jnz     short loc_18000C0CF
0x18000c0c2  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x18000c0c7  test    eax, eax
0x18000c0c9  jz      loc_18000C22D
0x18000c0cf  mov     ebp, 67h ; 'g'
0x18000c0d4  lea     r14, qword_18001A0D0
0x18000c0db  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x18000c0e0  mov     [rsp+68h+Response], 3Fh ; '?'
0x18000c0ea  mov     ebx, eax
0x18000c0ec  test    eax, eax
0x18000c0ee  jnz     short loc_18000C10A
0x18000c0f0  call    cs:__imp_IsDebuggerPresent
0x18000c0f6  movzx   ecx, byte ptr [rsp+68h+Response]
0x18000c0fe  test    eax, eax
0x18000c100  cmovnz  ecx, ebp
0x18000c103  mov     byte ptr [rsp+68h+Response], cl
0x18000c10a  mov     [rsp+68h+var_18], 0DDh
0x18000c112  lea     rax, aClientcoreWind_5; "clientcore\\windows\\dwm\\shared\\util"...
0x18000c119  mov     [rsp+68h+var_20], rax
0x18000c11e  lea     r9, aUnexpectedHres; "Unexpected HRESULT in MilInstrumentatio"...
0x18000c125  lea     rax, asc_18001A778; ", "
0x18000c12c  xor     edx, edx; Level
0x18000c12e  mov     [rsp+68h+var_28], rax
0x18000c133  lea     r8, Format; "\n*** Assertion failed: %ls%ls%ls\n*** "...
0x18000c13a  lea     rax, aMilinstrumenta; "MilInstrumentationBreak"
0x18000c141  mov     [rsp+68h+var_30], rax
0x18000c146  lea     rax, aFunction; "Function: "
0x18000c14d  mov     [rsp+68h+var_38], rax
0x18000c152  lea     ecx, [rdx+65h]; ComponentId
0x18000c155  mov     [rsp+68h+var_40], r14
0x18000c15a  mov     [rsp+68h+var_48], r14
0x18000c15f  call    cs:__imp_DbgPrintEx
0x18000c165  test    ebx, ebx
0x18000c167  jz      short loc_18000C186
0x18000c169  mov     r8d, 2; MaximumResponseLength
0x18000c16f  lea     rdx, [rsp+68h+Response]; Response
0x18000c177  lea     rcx, Prompt; "Break, Go (continue), terminate Process"...
0x18000c17e  call    cs:__imp_DbgPrompt
0x18000c184  jmp     short loc_18000C1AE
0x18000c186  xor     edx, edx; Level
0x18000c188  lea     rax, [rsp+68h+Response]
0x18000c190  lea     r9, [rsp+68h+Response]
0x18000c198  mov     [rsp+68h+var_48], rax
0x18000c19d  lea     r8, aNoKernelDebugg; "(No kernel debugger is present.) Respon"...
0x18000c1a4  lea     ecx, [rdx+65h]; ComponentId
0x18000c1a7  call    cs:__imp_DbgPrintEx
0x18000c1ad  int     3; Trap to Debugger
0x18000c1ae  mov     al, byte ptr [rsp+68h+Response]
0x18000c1b5  cmp     al, 62h ; 'b'
0x18000c1b7  jg      short loc_18000C1D1
0x18000c1b9  jz      short loc_18000C22C
0x18000c1bb  cmp     al, 42h ; 'B'
0x18000c1bd  jz      short loc_18000C22C
0x18000c1bf  cmp     al, 47h ; 'G'
0x18000c1c1  jz      short loc_18000C22D
0x18000c1c3  cmp     al, 49h ; 'I'
0x18000c1c5  jz      short loc_18000C215
0x18000c1c7  cmp     al, 50h ; 'P'
0x18000c1c9  jz      short loc_18000C1F8
0x18000c1cb  cmp     al, 54h ; 'T'
0x18000c1cd  jnz     short loc_18000C20C
0x18000c1cf  jmp     short loc_18000C1E2
0x18000c1d1  cmp     al, bpl
0x18000c1d4  jz      short loc_18000C22D
0x18000c1d6  cmp     al, 69h ; 'i'
0x18000c1d8  jz      short loc_18000C215
0x18000c1da  cmp     al, 70h ; 'p'
0x18000c1dc  jz      short loc_18000C1F8
0x18000c1de  cmp     al, 74h ; 't'
0x18000c1e0  jnz     short loc_18000C20C
0x18000c1e2  call    cs:__imp_GetCurrentThread
0x18000c1e8  mov     rcx, rax; hThread
0x18000c1eb  mov     edx, 0C0000001h; dwExitCode
0x18000c1f0  call    cs:__imp_TerminateThread
0x18000c1f6  jmp     short loc_18000C20C
0x18000c1f8  call    cs:__imp_GetCurrentProcess
0x18000c1fe  mov     rcx, rax; hProcess
0x18000c201  mov     edx, 0C0000001h; uExitCode
0x18000c206  call    cs:__imp_TerminateProcess
0x18000c20c  lea     r8, aUnrecognizedRe; "Unrecognized response.\n"
0x18000c213  jmp     short loc_18000C21C
0x18000c215  lea     r8, aIIsOnlySupport; "'i' is only supported with debug builds"...
0x18000c21c  xor     edx, edx; Level
0x18000c21e  lea     ecx, [rdx+65h]; ComponentId
0x18000c221  call    cs:__imp_DbgPrintEx
0x18000c227  jmp     loc_18000C0DB
0x18000c22c  int     3; Trap to Debugger
0x18000c22d  mov     rbx, [rsp+68h+arg_0]
0x18000c232  mov     rbp, [rsp+68h+arg_8]
0x18000c237  add     rsp, 60h
0x18000c23b  pop     r14
0x18000c23d  retn
```
