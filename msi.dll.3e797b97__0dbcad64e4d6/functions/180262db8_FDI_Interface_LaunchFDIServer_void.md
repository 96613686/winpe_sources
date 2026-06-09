# FDI_Interface::LaunchFDIServer(void)

- ea: `0x180262db8`
- end: `0x180262ff9`
- name: `?LaunchFDIServer@FDI_Interface@@AEAAHXZ`
- size: `577`
- prototype: `__int64 __fastcall(FDI_Interface *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18025a370`

## callees

- `0x18006a558`
- `0x180078fc8`
- `0x18007dd00`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18012e4e8`
- `0x180262db8`

## import_xrefs

- `ADVAPI32!DuplicateToken` at `0x180262ec8`
- `ADVAPI32!DuplicateToken` at `0x180262ec8`
- `ADVAPI32!OpenThreadToken` at `0x180262eae`
- `ADVAPI32!OpenThreadToken` at `0x180262eae`
- `KERNEL32!CloseHandle` at `0x180262fa6`
- `KERNEL32!CloseHandle` at `0x180262fa6`
- `KERNEL32!GetLastError` at `0x180262df2`
- `KERNEL32!GetLastError` at `0x180262df2`
- `KERNEL32!WaitForSingleObject` at `0x180262f95`
- `KERNEL32!WaitForSingleObject` at `0x180262f95`
- `KERNEL32!GetCurrentThread` at `0x180262e93`
- `KERNEL32!GetCurrentThread` at `0x180262e93`
- `KERNEL32!CreateEventW` at `0x180262ddf`
- `KERNEL32!CreateEventW` at `0x180262e25`
- `KERNEL32!CreateEventW` at `0x180262ddf`
- `KERNEL32!CreateEventW` at `0x180262e25`
- `KERNEL32!CreateThread` at `0x180262f66`
- `KERNEL32!CreateThread` at `0x180262f66`

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
0x180262db8  mov     [rsp+arg_0], rbx
0x180262dbd  mov     [rsp+arg_10], rbp
0x180262dc2  push    rsi
0x180262dc3  push    rdi
0x180262dc4  push    r15
0x180262dc6  sub     rsp, 30h
0x180262dca  mov     rsi, rcx
0x180262dcd  mov     [rsp+48h+ThreadId], 0
0x180262dd5  xor     ecx, ecx; lpEventAttributes
0x180262dd7  xor     r9d, r9d; lpName
0x180262dda  xor     r8d, r8d; bInitialState
0x180262ddd  xor     edx, edx; bManualReset
0x180262ddf  call    cs:__imp_CreateEventW
0x180262de6  nop     dword ptr [rax+rax+00h]
0x180262deb  mov     cs:?g_hFDIServerEvent@@3PEAXEA, rax; void * g_hFDIServerEvent
0x180262df2  call    cs:__imp_GetLastError
0x180262df9  nop     dword ptr [rax+rax+00h]
0x180262dfe  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180262e05  test    rcx, rcx
0x180262e08  jz      loc_180262FE3
0x180262e0e  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180262e13  test    eax, eax
0x180262e15  jz      loc_180262FD8
0x180262e1b  xor     r9d, r9d; lpName
0x180262e1e  xor     r8d, r8d; bInitialState
0x180262e21  xor     edx, edx; bManualReset
0x180262e23  xor     ecx, ecx; lpEventAttributes
0x180262e25  call    cs:__imp_CreateEventW
0x180262e2c  nop     dword ptr [rax+rax+00h]
0x180262e31  mov     cs:?g_hFDIInterfaceEvent@@3PEAXEA, rax; void * g_hFDIInterfaceEvent
0x180262e38  test    rax, rax
0x180262e3b  jz      loc_180262FCC
0x180262e41  mov     rcx, rax
0x180262e44  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180262e49  test    eax, eax
0x180262e4b  jnz     short loc_180262E69
0x180262e4d  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180262e54  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180262e59  mov     cs:?g_hFDIInterfaceEvent@@3PEAXEA, 0; void * g_hFDIInterfaceEvent
0x180262e64  jmp     loc_180262FD8
0x180262e69  or      r15, 0FFFFFFFFFFFFFFFFh
0x180262e6d  lea     rbx, [rsi+0A58h]
0x180262e74  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180262e7b  lea     rdi, [rsi+0A60h]
0x180262e82  mov     [rbx], r15
0x180262e85  mov     [rdi], r15
0x180262e88  jnz     loc_180262F39
0x180262e8e  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180262e93  call    cs:__imp_GetCurrentThread
0x180262e9a  nop     dword ptr [rax+rax+00h]
0x180262e9f  mov     r9, rbx; TokenHandle
0x180262ea2  lea     r8d, [r15+2]; OpenAsSelf
0x180262ea6  mov     rcx, rax; ThreadHandle
0x180262ea9  mov     edx, 2000000h; DesiredAccess
0x180262eae  call    cs:__imp_OpenThreadToken
0x180262eb5  nop     dword ptr [rax+rax+00h]
0x180262eba  test    eax, eax
0x180262ebc  jz      short loc_180262EDE
0x180262ebe  mov     rcx, [rbx]; ExistingTokenHandle
0x180262ec1  lea     edx, [r15+3]; ImpersonationLevel
0x180262ec5  mov     r8, rdi; DuplicateTokenHandle
0x180262ec8  call    cs:__imp_DuplicateToken
0x180262ecf  nop     dword ptr [rax+rax+00h]
0x180262ed4  test    eax, eax
0x180262ed6  jz      short loc_180262EDE
0x180262ed8  lea     ebp, [r15+2]
0x180262edc  jmp     short loc_180262EE0
0x180262ede  xor     ebp, ebp
0x180262ee0  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180262ee5  test    ebp, ebp
0x180262ee7  jnz     short loc_180262F0C
0x180262ee9  cmp     [rbx], r15
0x180262eec  jz      short loc_180262EF6
0x180262eee  mov     rcx, [rbx]
0x180262ef1  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x180262ef6  cmp     [rdi], r15
0x180262ef9  jz      loc_180262FE3
0x180262eff  mov     rcx, [rdi]
0x180262f02  call    ?MsiCloseUnregisteredSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseUnregisteredSysHandle(void *)
0x180262f07  jmp     loc_180262FE3
0x180262f0c  mov     rcx, [rbx]
0x180262f0f  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180262f14  mov     rcx, [rdi]
0x180262f17  test    eax, eax
0x180262f19  jnz     short loc_180262F2B
0x180262f1b  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180262f20  mov     [rbx], r15
0x180262f23  mov     [rdi], r15
0x180262f26  jmp     loc_180262FE3
0x180262f2b  call    ?MsiRegisterSysHandle@@YA?AW4Bool@@PEAX@Z; MsiRegisterSysHandle(void *)
0x180262f30  test    eax, eax
0x180262f32  jnz     short loc_180262F39
0x180262f34  mov     rcx, [rbx]
0x180262f37  jmp     short loc_180262F1B
0x180262f39  mov     cl, 1; bool
0x180262f3b  call    ?IsImpersonating@@YA_N_N@Z; IsImpersonating(bool)
0x180262f40  mov     [rsi+0A94h], al
0x180262f46  lea     r8, ?StartFDIServer@@YAKPEAX@Z; lpStartAddress
0x180262f4d  lea     rax, [rsp+48h+ThreadId]
0x180262f52  mov     r9, rsi; lpParameter
0x180262f55  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180262f5a  xor     edx, edx; dwStackSize
0x180262f5c  xor     ecx, ecx; lpThreadAttributes
0x180262f5e  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180262f66  call    cs:__imp_CreateThread
0x180262f6d  nop     dword ptr [rax+rax+00h]
0x180262f72  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; hHandle
0x180262f79  mov     rdi, rax
0x180262f7c  test    rax, rax
0x180262f7f  jnz     short loc_180262F92
0x180262f81  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180262f86  mov     rcx, cs:?g_hFDIInterfaceEvent@@3PEAXEA; void * g_hFDIInterfaceEvent
0x180262f8d  jmp     loc_180262E54
0x180262f92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180262f95  call    cs:__imp_WaitForSingleObject
0x180262f9c  nop     dword ptr [rax+rax+00h]
0x180262fa1  mov     rcx, rdi; hObject
0x180262fa4  mov     ebx, eax
0x180262fa6  call    cs:__imp_CloseHandle
0x180262fad  nop     dword ptr [rax+rax+00h]
0x180262fb2  test    ebx, ebx
0x180262fb4  jnz     short loc_180262FC3
0x180262fb6  mov     ecx, [rsi+4]
0x180262fb9  cmp     ecx, 17h
0x180262fbc  jz      short loc_180262FC3
0x180262fbe  lea     eax, [rbx+1]
0x180262fc1  jmp     short loc_180262FE5
0x180262fc3  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180262fca  jmp     short loc_180262F81
0x180262fcc  mov     rcx, cs:?g_hFDIServerEvent@@3PEAXEA; void * g_hFDIServerEvent
0x180262fd3  call    ?MsiCloseSysHandle@@YA?AW4Bool@@PEAX@Z; MsiCloseSysHandle(void *)
0x180262fd8  mov     cs:?g_hFDIServerEvent@@3PEAXEA, 0; void * g_hFDIServerEvent
0x180262fe3  xor     eax, eax
0x180262fe5  mov     rbx, [rsp+48h+arg_0]
0x180262fea  mov     rbp, [rsp+48h+arg_10]
0x180262fef  add     rsp, 30h
0x180262ff3  pop     r15
0x180262ff5  pop     rdi
0x180262ff6  pop     rsi
0x180262ff7  retn
```
