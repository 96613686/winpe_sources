# RunningAsLocalSystem(void)

- ea: `0x180024f9c`
- end: `0x1800250cb`
- name: `?RunningAsLocalSystem@@YA?AW4TRI@@XZ`
- size: `303`
- prototype: ``
- caller_count: `38`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001036c`
- `0x180013878`
- `0x1800227d0`
- `0x1800252a8`
- `0x180025904`
- `0x180025f60`
- `0x180027c60`
- `0x1800523b8`
- `0x1800694d0`
- `0x1800700e0`
- `0x18007f42c`
- `0x180081a5c`
- `0x180082560`
- `0x180083178`
- `0x1800833ec`
- `0x1800a6e28`
- `0x1800c998c`
- `0x1800e798c`
- `0x1800f11e0`
- `0x180112f24`
- `0x1801131bc`
- `0x180129200`
- `0x180143e10`
- `0x180146568`
- `0x180146828`
- `0x18018f898`
- `0x1801900c8`
- `0x1801948c0`
- `0x180194a60`
- `0x1801b3c60`
- `0x1801b4dc0`
- `0x1801b5718`
- `0x1801b5a30`
- `0x1801b6220`
- `0x1801bf700`
- `0x1801de630`
- `0x1801e142c`
- `0x180247828`

## callees

- `0x180024f9c`
- `0x180025a18`
- `0x1800a9d48`
- `0x180157094`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180025029`
- `ADVAPI32!SetThreadToken` at `0x18002506c`
- `ADVAPI32!SetThreadToken` at `0x180025029`
- `ADVAPI32!SetThreadToken` at `0x18002506c`
- `ADVAPI32!OpenThreadToken` at `0x180024fd7`
- `ADVAPI32!OpenThreadToken` at `0x180024fd7`
- `ADVAPI32!OpenProcessToken` at `0x18002500a`
- `ADVAPI32!OpenProcessToken` at `0x18002500a`
- `KERNEL32!CloseHandle` at `0x18002503d`
- `KERNEL32!CloseHandle` at `0x18002505a`
- `KERNEL32!CloseHandle` at `0x18002503d`
- `KERNEL32!CloseHandle` at `0x18002505a`
- `KERNEL32!GetCurrentThread` at `0x180024fc0`
- `KERNEL32!GetCurrentThread` at `0x180024fc0`
- `KERNEL32!GetCurrentProcess` at `0x180024ff7`
- `KERNEL32!GetCurrentProcess` at `0x180024ff7`

## pseudocode

```c
__int64 RunningAsLocalSystem()
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v3; // ebx
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+10h] BYREF

  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v3 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v3;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
  }
  return (unsigned int)dword_180306D40;
}

```

## disassembly

```asm
0x180024f9c  push    rbx
0x180024f9e  sub     rsp, 60h
0x180024fa2  cmp     cs:dword_180306D40, 0FFFFFFFFh
0x180024fa9  jz      short loc_180024FB7
0x180024fab  mov     eax, cs:dword_180306D40
0x180024fb1  add     rsp, 60h
0x180024fb5  pop     rbx
0x180024fb6  retn
0x180024fb7  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180024fc0  call    cs:__imp_GetCurrentThread
0x180024fc6  mov     edx, 4; DesiredAccess
0x180024fcb  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180024fd0  mov     rcx, rax; ThreadHandle
0x180024fd3  lea     r8d, [rdx-3]; OpenAsSelf
0x180024fd7  call    cs:__imp_OpenThreadToken
0x180024fdd  test    eax, eax
0x180024fdf  jnz     loc_180025068
0x180024fe5  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180024fee  mov     [rsp+68h+hObject], 0
0x180024ff7  call    cs:__imp_GetCurrentProcess
0x180024ffd  lea     r8, [rsp+68h+hObject]; TokenHandle
0x180025002  mov     edx, 8; DesiredAccess
0x180025007  mov     rcx, rax; ProcessHandle
0x18002500a  call    cs:__imp_OpenProcessToken
0x180025010  test    eax, eax
0x180025012  jnz     short loc_180025048
0x180025014  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18002501a  jnz     short loc_180025084
0x18002501c  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180025021  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180025025  jz      short loc_180024FAB
0x180025027  xor     ecx, ecx; Thread
0x180025029  call    cs:__imp_SetThreadToken
0x18002502f  test    eax, eax
0x180025031  jnz     short loc_180025038
0x180025033  call    ExitProcessIfNotClient
0x180025038  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18002503d  call    cs:__imp_CloseHandle
0x180025043  jmp     loc_180024FAB
0x180025048  mov     rcx, [rsp+68h+hObject]; void *
0x18002504d  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180025052  mov     rcx, [rsp+68h+hObject]; hObject
0x180025057  movzx   ebx, al
0x18002505a  call    cs:__imp_CloseHandle
0x180025060  mov     cs:dword_180306D40, ebx
0x180025066  jmp     short loc_18002501C
0x180025068  xor     edx, edx; Token
0x18002506a  xor     ecx, ecx; Thread
0x18002506c  call    cs:__imp_SetThreadToken
0x180025072  test    eax, eax
0x180025074  jnz     loc_180024FEE
0x18002507a  call    ExitProcessIfNotClient
0x18002507f  jmp     loc_180024FEE
0x180025084  lea     rax, aNull; "(NULL)"
0x18002508b  xor     edx, edx; unsigned __int16
0x18002508d  mov     [rsp+68h+var_10], rdx; void *
0x180025092  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x180025099  mov     [rsp+68h+var_18], edx; unsigned int
0x18002509d  xor     r8d, r8d; int
0x1800250a0  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x1800250a5  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x1800250aa  lea     ecx, [rdx+9]; int
0x1800250ad  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x1800250b2  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x1800250b7  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800250bc  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800250c1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800250c6  jmp     loc_18002501C
```
