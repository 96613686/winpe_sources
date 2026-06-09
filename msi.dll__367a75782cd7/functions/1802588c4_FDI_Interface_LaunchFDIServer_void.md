# FDI_Interface::LaunchFDIServer(void)

- ea: `0x1802588c4`
- end: `0x180258ace`
- name: `?LaunchFDIServer@FDI_Interface@@AEAAHXZ`
- size: `522`
- prototype: `__int64 __fastcall(FDI_Interface *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18024fff0`

## callees

- `0x18006ab6c`
- `0x18007af4c`
- `0x18007fa28`
- `0x180083178`
- `0x1800833ec`
- `0x180129200`
- `0x1802588c4`

## import_xrefs

- `ADVAPI32!DuplicateToken` at `0x1802589b6`
- `ADVAPI32!DuplicateToken` at `0x1802589b6`
- `ADVAPI32!OpenThreadToken` at `0x1802589a2`
- `ADVAPI32!OpenThreadToken` at `0x1802589a2`
- `KERNEL32!CloseHandle` at `0x180258a82`
- `KERNEL32!CloseHandle` at `0x180258a82`
- `KERNEL32!GetLastError` at `0x1802588f8`
- `KERNEL32!GetLastError` at `0x1802588f8`
- `KERNEL32!WaitForSingleObject` at `0x180258a77`
- `KERNEL32!WaitForSingleObject` at `0x180258a77`
- `KERNEL32!GetCurrentThread` at `0x18025898d`
- `KERNEL32!GetCurrentThread` at `0x18025898d`
- `KERNEL32!CreateEventW` at `0x1802588eb`
- `KERNEL32!CreateEventW` at `0x180258925`
- `KERNEL32!CreateEventW` at `0x1802588eb`
- `KERNEL32!CreateEventW` at `0x180258925`
- `KERNEL32!CreateThread` at `0x180258a4e`
- `KERNEL32!CreateThread` at `0x180258a4e`

## pseudocode

```c
__int64 __fastcall FDI_Interface::LaunchFDIServer(FDI_Interface *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rcx
  HANDLE *v4; // rbx
  bool v5; // zf
  _QWORD *v6; // rdi
  HANDLE CurrentThread; // rax
  bool v8; // cl
  BOOL v9; // ebp
  int v10; // eax
  HANDLE v11; // rcx
  HANDLE v12; // rax
  HANDLE v13; // rcx
  void *v14; // rdi
  DWORD v15; // ebx
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = 0;
  g_hFDIServerEvent = CreateEventW(0, 0, 0, 0);
  GetLastError();
  if ( !g_hFDIServerEvent )
    return 0;
  if ( !(unsigned int)((__int64 (*)(void))MsiRegisterSysHandle)() )
    goto LABEL_28;
  EventW = CreateEventW(0, 0, 0, 0);
  g_hFDIInterfaceEvent = EventW;
  if ( !EventW )
  {
    MsiCloseSysHandle(g_hFDIServerEvent);
    goto LABEL_28;
  }
  if ( !(unsigned int)MsiRegisterSysHandle(EventW) )
  {
    v3 = g_hFDIServerEvent;
LABEL_6:
    MsiCloseSysHandle(v3);
    g_hFDIInterfaceEvent = 0;
LABEL_28:
    g_hFDIServerEvent = 0;
    return 0;
  }
  v4 = (HANDLE *)((char *)this + 2648);
  v5 = g_scServerContext == 2;
  v6 = (_QWORD *)((char *)this + 2656);
  *((_QWORD *)this + 331) = -1;
  *((_QWORD *)this + 332) = -1;
  if ( !v5 )
    goto LABEL_21;
  StartImpersonating();
  CurrentThread = GetCurrentThread();
  v9 = OpenThreadToken(CurrentThread, 0x2000000u, 1, (PHANDLE)this + 331)
    && DuplicateToken(*v4, SecurityImpersonation, (PHANDLE)this + 332);
  StopImpersonating(v8);
  if ( !v9 )
  {
    if ( *v4 != (HANDLE)-1LL )
      MsiCloseUnregisteredSysHandle(*v4);
    if ( *v6 != -1 )
      MsiCloseUnregisteredSysHandle(*v6);
    return 0;
  }
  v10 = MsiRegisterSysHandle(*v4);
  v11 = (HANDLE)*v6;
  if ( !v10 )
    goto LABEL_18;
  if ( (unsigned int)MsiRegisterSysHandle(v11) )
  {
LABEL_21:
    *((_BYTE *)this + 2708) = IsImpersonating(1);
    v12 = CreateThread(0, 0, StartFDIServer, this, 0, &ThreadId);
    v13 = g_hFDIServerEvent;
    v14 = v12;
    if ( v12 )
    {
      v15 = WaitForSingleObject(g_hFDIServerEvent, 0xFFFFFFFF);
      CloseHandle(v14);
      if ( !v15 && *((_DWORD *)this + 1) != 23 )
        return 1;
      v13 = g_hFDIServerEvent;
    }
    MsiCloseSysHandle(v13);
    v3 = g_hFDIInterfaceEvent;
    goto LABEL_6;
  }
  v11 = *v4;
LABEL_18:
  MsiCloseSysHandle(v11);
  *v4 = (HANDLE)-1LL;
  *v6 = -1;
  return 0;
}

```

## disassembly

```asm
0x1802588c4  mov     [rsp+arg_0], rbx
0x1802588c9  mov     [rsp+arg_10], rbp
0x1802588ce  push    rsi
0x1802588cf  push    rdi
0x1802588d0  push    r15
0x1802588d2  sub     rsp, 30h
0x1802588d6  mov     rsi, rcx
0x1802588d9  mov     [rsp+48h+ThreadId], 0
0x1802588e1  xor     ecx, ecx; lpEventAttributes
0x1802588e3  xor     r9d, r9d; lpName
0x1802588e6  xor     r8d, r8d; bInitialState
0x1802588e9  xor     edx, edx; bManualReset
0x1802588eb  call    cs:__imp_CreateEventW
0x1802588f1  mov     cs:?g_hFDIServerEvent@@3PEAXEA, rax; void * g_hFDIServerEvent
0x1802588f8  call    cs:__imp_GetLastError
0x1802588fe  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180258905  test    rcx, rcx
0x180258908  jz      loc_180258AB9
0x18025890e  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180258913  test    eax, eax
0x180258915  jz      loc_180258AAE
0x18025891b  xor     r9d, r9d; lpName
0x18025891e  xor     r8d, r8d; bInitialState
0x180258921  xor     edx, edx; bManualReset
0x180258923  xor     ecx, ecx; lpEventAttributes
0x180258925  call    cs:__imp_CreateEventW
0x18025892b  mov     cs:?g_hFDIInterfaceEvent@@3PEAXEA, rax; void * g_hFDIInterfaceEvent
0x180258932  test    rax, rax
0x180258935  jz      loc_180258AA2
0x18025893b  mov     rcx, rax
0x18025893e  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180258943  test    eax, eax
0x180258945  jnz     short loc_180258963
0x180258947  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x18025894e  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180258953  mov     cs:?g_hFDIInterfaceEvent@@3PEAXEA, 0; void * g_hFDIInterfaceEvent
0x18025895e  jmp     loc_180258AAE
0x180258963  or      r15, 0FFFFFFFFFFFFFFFFh
0x180258967  lea     rbx, [rsi+0A58h]
0x18025896e  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180258975  lea     rdi, [rsi+0A60h]
0x18025897c  mov     [rbx], r15
0x18025897f  mov     [rdi], r15
0x180258982  jnz     loc_180258A21
0x180258988  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18025898d  call    cs:__imp_GetCurrentThread
0x180258993  mov     r9, rbx; TokenHandle
0x180258996  lea     r8d, [r15+2]; OpenAsSelf
0x18025899a  mov     rcx, rax; ThreadHandle
0x18025899d  mov     edx, 2000000h; DesiredAccess
0x1802589a2  call    cs:__imp_OpenThreadToken
0x1802589a8  test    eax, eax
0x1802589aa  jz      short loc_1802589C6
0x1802589ac  mov     rcx, [rbx]; ExistingTokenHandle
0x1802589af  lea     edx, [r15+3]; ImpersonationLevel
0x1802589b3  mov     r8, rdi; DuplicateTokenHandle
0x1802589b6  call    cs:__imp_DuplicateToken
0x1802589bc  test    eax, eax
0x1802589be  jz      short loc_1802589C6
0x1802589c0  lea     ebp, [r15+2]
0x1802589c4  jmp     short loc_1802589C8
0x1802589c6  xor     ebp, ebp
0x1802589c8  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1802589cd  test    ebp, ebp
0x1802589cf  jnz     short loc_1802589F4
0x1802589d1  cmp     [rbx], r15
0x1802589d4  jz      short loc_1802589DE
0x1802589d6  mov     rcx, [rbx]
0x1802589d9  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x1802589de  cmp     [rdi], r15
0x1802589e1  jz      loc_180258AB9
0x1802589e7  mov     rcx, [rdi]
0x1802589ea  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x1802589ef  jmp     loc_180258AB9
0x1802589f4  mov     rcx, [rbx]
0x1802589f7  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x1802589fc  mov     rcx, [rdi]
0x1802589ff  test    eax, eax
0x180258a01  jnz     short loc_180258A13
0x180258a03  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180258a08  mov     [rbx], r15
0x180258a0b  mov     [rdi], r15
0x180258a0e  jmp     loc_180258AB9
0x180258a13  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180258a18  test    eax, eax
0x180258a1a  jnz     short loc_180258A21
0x180258a1c  mov     rcx, [rbx]
0x180258a1f  jmp     short loc_180258A03
0x180258a21  mov     cl, 1; bool
0x180258a23  call    ?IsImpersonating@@YA_N_N@Z; IsImpersonating(bool)
0x180258a28  mov     [rsi+0A94h], al
0x180258a2e  lea     r8, ?StartFDIServer@@YAKPEAX@Z; lpStartAddress
0x180258a35  lea     rax, [rsp+48h+ThreadId]
0x180258a3a  mov     r9, rsi; lpParameter
0x180258a3d  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180258a42  xor     edx, edx; dwStackSize
0x180258a44  xor     ecx, ecx; lpThreadAttributes
0x180258a46  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180258a4e  call    cs:__imp_CreateThread
0x180258a54  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; hHandle
0x180258a5b  mov     rdi, rax
0x180258a5e  test    rax, rax
0x180258a61  jnz     short loc_180258A74
0x180258a63  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180258a68  mov     rcx, cs:?g_hFDIInterfaceEvent@@3PEAXEA; void * g_hFDIInterfaceEvent
0x180258a6f  jmp     loc_18025894E
0x180258a74  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180258a77  call    cs:__imp_WaitForSingleObject
0x180258a7d  mov     rcx, rdi; hObject
0x180258a80  mov     ebx, eax
0x180258a82  call    cs:__imp_CloseHandle
0x180258a88  test    ebx, ebx
0x180258a8a  jnz     short loc_180258A99
0x180258a8c  mov     ecx, [rsi+4]
0x180258a8f  cmp     ecx, 17h
0x180258a92  jz      short loc_180258A99
0x180258a94  lea     eax, [rbx+1]
0x180258a97  jmp     short loc_180258ABB
0x180258a99  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180258aa0  jmp     short loc_180258A63
0x180258aa2  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180258aa9  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180258aae  mov     cs:?g_hFDIServerEvent@@3PEAXEA, 0; void * g_hFDIServerEvent
0x180258ab9  xor     eax, eax
0x180258abb  mov     rbx, [rsp+48h+arg_0]
0x180258ac0  mov     rbp, [rsp+48h+arg_10]
0x180258ac5  add     rsp, 30h
0x180258ac9  pop     r15
0x180258acb  pop     rdi
0x180258acc  pop     rsi
0x180258acd  retn
```
