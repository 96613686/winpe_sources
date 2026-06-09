# WinExec

- ea: `0x180057fd0`
- end: `0x1800581a8`
- name: `WinExec`
- size: `472`
- prototype: `UINT __stdcall(LPCSTR lpCmdLine, UINT uCmdShow)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180057fd0`
- `0x18007a7dd`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!NtClose` at `0x18005813b`
- `ntdll!NtClose` at `0x180058146`
- `ntdll!NtClose` at `0x18005813b`
- `ntdll!NtClose` at `0x180058146`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180058111`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessA` at `0x180058111`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180058048`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180058048`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005808a`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18005808a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180058188`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180058188`

## pseudocode

```c
UINT __stdcall WinExec(LPCSTR lpCmdLine, UINT uCmdShow)
{
  UINT result; // eax
  UINT v5; // ebx
  DWORD v6; // edi
  ULONG v7; // eax
  ULONG v8; // eax
  int Value; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR Size; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _OWORD *v13; // [rsp+E8h] [rbp-18h]
  _OWORD v14[3]; // [rsp+F0h] [rbp-10h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x6Cu);
  Value = 0;
  Size = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(v14, 0, sizeof(v14));
  if ( (uCmdShow & 0x80000000) == 0 )
  {
    v6 = 0;
LABEL_7:
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.dwFlags = 1;
    StartupInfo.wShowWindow = uCmdShow;
    StartupInfo.cb = v6 != 0 ? 112 : 104;
    if ( CreateProcessA(0, (LPSTR)lpCmdLine, 0, 0, 0, v6, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( UserWaitForInputIdleRoutine )
        UserWaitForInputIdleRoutine(ProcessInformation.hProcess, 30000);
      NtClose(ProcessInformation.hProcess);
      NtClose(ProcessInformation.hThread);
      v5 = 33;
    }
    else
    {
      v5 = 2;
      v7 = NtCurrentTeb()->LastErrorValue - 2;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 == 190 )
            v5 = 11;
          else
            v5 = 0;
        }
        else
        {
          v5 = 3;
        }
      }
    }
    if ( !v6 )
      return v5;
    goto LABEL_18;
  }
  Size = 48;
  result = InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v14, 1u, 0, &Size);
  if ( !result )
    return result;
  Value = 1;
  if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v14, 0, 0x60001u, &Value, 4u, 0, 0) )
  {
    v6 = 0x80000;
    v13 = v14;
    goto LABEL_7;
  }
  v5 = 0;
LABEL_18:
  DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v14);
  return v5;
}

```

## disassembly

```asm
0x180057fd0  push    rbp
0x180057fd2  push    rbx
0x180057fd3  push    rsi
0x180057fd4  push    rdi
0x180057fd5  lea     rbp, [rsp-38h]
0x180057fda  sub     rsp, 138h
0x180057fe1  mov     rax, cs:__security_cookie
0x180057fe8  xor     rax, rsp
0x180057feb  mov     [rbp+50h+var_30], rax
0x180057fef  xor     eax, eax
0x180057ff1  mov     ebx, edx
0x180057ff3  mov     rsi, rcx
0x180057ff6  mov     dword ptr [rbp+50h+StartupInfo+4], eax
0x180057ff9  xor     edx, edx; Val
0x180057ffb  lea     rcx, [rbp+50h+StartupInfo]; void *
0x180057fff  lea     r8d, [rax+6Ch]; Size
0x180058003  call    memset_0
0x180058008  xor     eax, eax
0x18005800a  xorps   xmm0, xmm0
0x18005800d  mov     qword ptr [rsp+150h+ProcessInformation.dwProcessId], rax
0x180058012  mov     [rsp+150h+Value], eax
0x180058016  mov     [rsp+150h+Size], rax
0x18005801b  movups  xmmword ptr [rsp+150h+ProcessInformation.hProcess], xmm0
0x180058020  movups  [rbp+50h+var_60], xmm0
0x180058024  movups  [rbp+50h+var_50], xmm0
0x180058028  movups  [rbp+50h+var_40], xmm0
0x18005802c  test    ebx, ebx
0x18005802e  jns     short loc_1800580AA
0x180058030  lea     r9, [rsp+150h+Size]; lpSize
0x180058035  mov     [rsp+150h+Size], 30h ; '0'
0x18005803e  xor     r8d, r8d; dwFlags
0x180058041  lea     edx, [rax+1]; dwAttributeCount
0x180058044  lea     rcx, [rbp+50h+var_60]; lpAttributeList
0x180058048  call    cs:__imp_InitializeProcThreadAttributeList
0x18005804e  test    eax, eax
0x180058050  jz      loc_180058190
0x180058056  mov     [rsp+150h+lpReturnSize], 0; lpReturnSize
0x18005805f  lea     r9, [rsp+150h+Value]; lpValue
0x180058064  mov     [rsp+150h+lpPreviousValue], 0; lpPreviousValue
0x18005806d  lea     rcx, [rbp+50h+var_60]; lpAttributeList
0x180058071  xor     edx, edx; dwFlags
0x180058073  mov     [rsp+150h+cbSize], 4; cbSize
0x18005807c  mov     r8d, 60001h; Attribute
0x180058082  mov     [rsp+150h+Value], 1
0x18005808a  call    cs:__imp_UpdateProcThreadAttribute
0x180058090  test    eax, eax
0x180058092  jnz     short loc_18005809B
0x180058094  xor     ebx, ebx
0x180058096  jmp     loc_180058184
0x18005809b  lea     rax, [rbp+50h+var_60]
0x18005809f  mov     edi, 80000h
0x1800580a4  mov     [rbp+50h+var_68], rax
0x1800580a8  jmp     short loc_1800580AC
0x1800580aa  xor     edi, edi
0x1800580ac  xor     edx, edx; Val
0x1800580ae  lea     rcx, [rbp+50h+StartupInfo]; void *
0x1800580b2  lea     r8d, [rdx+68h]; Size
0x1800580b6  call    memset_0
0x1800580bb  mov     eax, edi
0x1800580bd  mov     [rbp+50h+StartupInfo.dwFlags], 1
0x1800580c4  neg     eax
0x1800580c6  mov     [rbp+50h+StartupInfo.wShowWindow], bx
0x1800580ca  lea     rax, [rsp+150h+ProcessInformation]
0x1800580cf  mov     rdx, rsi; lpCommandLine
0x1800580d2  mov     [rsp+150h+lpProcessInformation], rax; lpProcessInformation
0x1800580d7  sbb     ecx, ecx
0x1800580d9  and     ecx, 8
0x1800580dc  lea     rax, [rbp+50h+StartupInfo]
0x1800580e0  mov     [rsp+150h+lpStartupInfo], rax; lpStartupInfo
0x1800580e5  add     ecx, 68h ; 'h'
0x1800580e8  mov     [rsp+150h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800580f1  xor     r9d, r9d; lpThreadAttributes
0x1800580f4  mov     [rbp+50h+StartupInfo.cb], ecx
0x1800580f7  xor     r8d, r8d; lpProcessAttributes
0x1800580fa  mov     [rsp+150h+lpReturnSize], 0; lpEnvironment
0x180058103  xor     ecx, ecx; lpApplicationName
0x180058105  mov     dword ptr [rsp+150h+lpPreviousValue], edi; dwCreationFlags
0x180058109  mov     dword ptr [rsp+150h+cbSize], 0; bInheritHandles
0x180058111  call    cs:__imp_CreateProcessA
0x180058117  test    eax, eax
0x180058119  jz      short loc_180058153
0x18005811b  mov     rax, cs:UserWaitForInputIdleRoutine
0x180058122  test    rax, rax
0x180058125  jz      short loc_180058136
0x180058127  mov     rcx, [rsp+150h+ProcessInformation.hProcess]
0x18005812c  mov     edx, 7530h
0x180058131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058136  mov     rcx, [rsp+150h+ProcessInformation.hProcess]; Handle
0x18005813b  call    cs:__imp_NtClose
0x180058141  mov     rcx, [rsp+150h+ProcessInformation.hThread]; Handle
0x180058146  call    cs:__imp_NtClose
0x18005814c  mov     ebx, 21h ; '!'
0x180058151  jmp     short loc_180058180
0x180058153  mov     eax, gs:68h
0x18005815b  mov     ebx, 2
0x180058160  sub     eax, ebx
0x180058162  jz      short loc_180058180
0x180058164  sub     eax, 1
0x180058167  jz      short loc_18005817B
0x180058169  cmp     eax, 0BEh
0x18005816e  jz      short loc_180058174
0x180058170  xor     ebx, ebx
0x180058172  jmp     short loc_180058180
0x180058174  mov     ebx, 0Bh
0x180058179  jmp     short loc_180058180
0x18005817b  mov     ebx, 3
0x180058180  test    edi, edi
0x180058182  jz      short loc_18005818E
0x180058184  lea     rcx, [rbp+50h+var_60]; lpAttributeList
0x180058188  call    cs:__imp_DeleteProcThreadAttributeList
0x18005818e  mov     eax, ebx
0x180058190  mov     rcx, [rbp+50h+var_30]
0x180058194  xor     rcx, rsp; StackCookie
0x180058197  call    __security_check_cookie
0x18005819c  add     rsp, 138h
0x1800581a3  pop     rdi
0x1800581a4  pop     rsi
0x1800581a5  pop     rbx
0x1800581a6  pop     rbp
0x1800581a7  retn
```
