# RunningAsLocalSystem(void)

- ea: `0x180013fe4`
- end: `0x18001414c`
- name: `?RunningAsLocalSystem@@YA?AW4TRI@@XZ`
- size: `360`
- prototype: ``
- caller_count: `38`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001386c`
- `0x180013d64`
- `0x180014528`
- `0x180015310`
- `0x180036bb0`
- `0x180042394`
- `0x18004e85c`
- `0x18004eb1c`
- `0x180056624`
- `0x180068e88`
- `0x18007d678`
- `0x180096164`
- `0x18009b520`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18009ecb8`
- `0x1800af2f0`
- `0x1800b4aac`
- `0x1800ee56c`
- `0x1800f80e0`
- `0x1800fa4d0`
- `0x18012e4e8`
- `0x180148960`
- `0x18014b72c`
- `0x18014bc24`
- `0x1801961b8`
- `0x180196a0c`
- `0x18019b520`
- `0x18019b6c0`
- `0x1801bba60`
- `0x1801bcc00`
- `0x1801bd55c`
- `0x1801bd890`
- `0x1801be090`
- `0x1801c7b04`
- `0x1801e7568`
- `0x1801ea40c`
- `0x180251a18`

## callees

- `0x18000c4bc`
- `0x180013fe4`
- `0x180045ba4`
- `0x18015cbac`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180014092`
- `ADVAPI32!SetThreadToken` at `0x1800140e7`
- `ADVAPI32!SetThreadToken` at `0x180014092`
- `ADVAPI32!SetThreadToken` at `0x1800140e7`
- `ADVAPI32!OpenThreadToken` at `0x180014026`
- `ADVAPI32!OpenThreadToken` at `0x180014026`
- `ADVAPI32!OpenProcessToken` at `0x180014065`
- `ADVAPI32!OpenProcessToken` at `0x180014065`
- `KERNEL32!CloseHandle` at `0x1800140ac`
- `KERNEL32!CloseHandle` at `0x1800140cf`
- `KERNEL32!CloseHandle` at `0x1800140ac`
- `KERNEL32!CloseHandle` at `0x1800140cf`
- `KERNEL32!GetCurrentThread` at `0x180014009`
- `KERNEL32!GetCurrentThread` at `0x180014009`
- `KERNEL32!GetCurrentProcess` at `0x18001404c`
- `KERNEL32!GetCurrentProcess` at `0x18001404c`

## pseudocode

```c
__int64 RunningAsLocalSystem()
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v3; // ebx
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+10h] BYREF

  if ( dword_180310D00 == -1 )
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
      dword_180310D00 = v3;
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
  return (unsigned int)dword_180310D00;
}

```

## disassembly

```asm
0x180013fe4  push    rbx
0x180013fe6  sub     rsp, 60h
0x180013fea  cmp     cs:dword_180310D00, 0FFFFFFFFh
0x180013ff1  jz      short loc_180014000
0x180013ff3  mov     eax, cs:dword_180310D00
0x180013ff9  add     rsp, 60h
0x180013ffd  pop     rbx
0x180013ffe  retn
0x180014000  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180014009  call    cs:__imp_GetCurrentThread
0x180014010  nop     dword ptr [rax+rax+00h]
0x180014015  mov     edx, 4; DesiredAccess
0x18001401a  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18001401f  mov     rcx, rax; ThreadHandle
0x180014022  lea     r8d, [rdx-3]; OpenAsSelf
0x180014026  call    cs:__imp_OpenThreadToken
0x18001402d  nop     dword ptr [rax+rax+00h]
0x180014032  test    eax, eax
0x180014034  jnz     loc_1800140E3
0x18001403a  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180014043  mov     [rsp+68h+hObject], 0
0x18001404c  call    cs:__imp_GetCurrentProcess
0x180014053  nop     dword ptr [rax+rax+00h]
0x180014058  lea     r8, [rsp+68h+hObject]; TokenHandle
0x18001405d  mov     edx, 8; DesiredAccess
0x180014062  mov     rcx, rax; ProcessHandle
0x180014065  call    cs:__imp_OpenProcessToken
0x18001406c  nop     dword ptr [rax+rax+00h]
0x180014071  test    eax, eax
0x180014073  jnz     short loc_1800140BD
0x180014075  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18001407b  jnz     loc_180014105
0x180014081  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180014086  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001408a  jz      loc_180013FF3
0x180014090  xor     ecx, ecx; Thread
0x180014092  call    cs:__imp_SetThreadToken
0x180014099  nop     dword ptr [rax+rax+00h]
0x18001409e  test    eax, eax
0x1800140a0  jnz     short loc_1800140A7
0x1800140a2  call    ExitProcessIfNotClient
0x1800140a7  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800140ac  call    cs:__imp_CloseHandle
0x1800140b3  nop     dword ptr [rax+rax+00h]
0x1800140b8  jmp     loc_180013FF3
0x1800140bd  mov     rcx, [rsp+68h+hObject]; void *
0x1800140c2  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1800140c7  mov     rcx, [rsp+68h+hObject]; hObject
0x1800140cc  movzx   ebx, al
0x1800140cf  call    cs:__imp_CloseHandle
0x1800140d6  nop     dword ptr [rax+rax+00h]
0x1800140db  mov     cs:dword_180310D00, ebx
0x1800140e1  jmp     short loc_180014081
0x1800140e3  xor     edx, edx; Token
0x1800140e5  xor     ecx, ecx; Thread
0x1800140e7  call    cs:__imp_SetThreadToken
0x1800140ee  nop     dword ptr [rax+rax+00h]
0x1800140f3  test    eax, eax
0x1800140f5  jnz     loc_180014043
0x1800140fb  call    ExitProcessIfNotClient
0x180014100  jmp     loc_180014043
0x180014105  lea     rax, aNull; "(NULL)"
0x18001410c  xor     edx, edx; unsigned __int16
0x18001410e  mov     [rsp+68h+var_10], rdx; void *
0x180014113  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18001411a  mov     [rsp+68h+var_18], edx; unsigned int
0x18001411e  xor     r8d, r8d; int
0x180014121  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x180014126  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x18001412b  lea     ecx, [rdx+9]; int
0x18001412e  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x180014133  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180014138  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001413d  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180014142  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180014147  jmp     loc_180014081
```
