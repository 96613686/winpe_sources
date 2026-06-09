# DasHostCreateDevnodeManagementContext

- ea: `0x14000dbe0`
- end: `0x14000ddfe`
- name: `DasHostCreateDevnodeManagementContext`
- size: `542`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, unsigned __int16 *, unsigned __int16 *, HANDLE *, struct CDasHostDevnodeMgmt **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000dbe0`
- `0x14000f48c`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000dc86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000dc86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ddaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ddaa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000ddcf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000ddcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dceb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14000dd41`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14000dd41`
- `RPCRT4!RpcImpersonateClient` at `0x14000dd61`
- `RPCRT4!RpcImpersonateClient` at `0x14000dd61`
- `RPCRT4!RpcRevertToSelf` at `0x14000dd9f`
- `RPCRT4!RpcRevertToSelf` at `0x14000ddd9`
- `RPCRT4!RpcRevertToSelf` at `0x14000dd9f`
- `RPCRT4!RpcRevertToSelf` at `0x14000ddd9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000dd7c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000dd7c`

## pseudocode

```c
__int64 __fastcall DasHostCreateDevnodeManagementContext(
        RPC_BINDING_HANDLE Binding,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        HANDLE *a4,
        struct CDasHostDevnodeMgmt **a5)
{
  const unsigned __int16 *v7; // rbx
  HANDLE EventW; // rdi
  HANDLE v9; // rsi
  struct CDasHostDevnodeMgmt **v11; // r14
  __int64 v12; // rax
  int v13; // edx
  int v14; // ebx
  int v15; // r8d
  signed int LastError; // eax
  bool v17; // cc
  RPC_STATUS v19; // eax
  signed int v20; // eax
  HANDLE CurrentProcess; // rax
  struct CDasHostDevnodeMgmt *v22; // rax
  BOOL bInheritHandle; // [rsp+28h] [rbp-30h]
  HANDLE hObject; // [rsp+40h] [rbp-18h] BYREF
  struct CDasHostDevnodeMgmt *v25; // [rsp+48h] [rbp-10h] BYREF
  unsigned int Pid; // [rsp+B0h] [rbp+58h] BYREF

  v7 = a3;
  v25 = 0;
  EventW = 0;
  Pid = 0;
  v9 = 0;
  hObject = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)&WPP_RECORDER_INITIALIZED,
      (int)a3,
      10,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids);
  v11 = a5;
  *a5 = 0;
  if ( !v7 )
    goto LABEL_7;
  v12 = -1;
  do
    ++v12;
  while ( v7[v12] );
  if ( !v12 )
LABEL_7:
    v7 = 0;
  v14 = CDasHostDevnodeMgmt::Create(a2, v7, (RTL_SRWLOCK **)&v25);
  if ( v14 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v14 = LastError;
      v17 = LastError <= 0;
      goto LABEL_11;
    }
    v19 = I_RpcBindingInqLocalClientPID(Binding, &Pid);
    v14 = v19;
    if ( v19 >= 1 )
      v14 = (unsigned __int16)v19 | 0x80010000;
    if ( v14 >= 0 )
    {
      LastError = RpcImpersonateClient(0);
      v14 = LastError;
      v17 = LastError <= 0;
      if ( LastError )
      {
LABEL_11:
        if ( !v17 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_13;
      }
      v9 = OpenProcess(0x1040u, 0, Pid);
      if ( v9 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(CurrentProcess, EventW, v9, &hObject, 0x100000u, 0, 0) )
        {
          RpcRevertToSelf();
          v22 = v25;
          v14 = 0;
          *((_QWORD *)v25 + 3) = EventW;
          *v11 = v22;
          *a4 = hObject;
          hObject = 0;
LABEL_20:
          CloseHandle(v9);
          goto LABEL_21;
        }
      }
      v20 = GetLastError();
      v14 = v20;
      if ( v20 > 0 )
        v14 = (unsigned __int16)v20 | 0x80070000;
      RpcRevertToSelf();
    }
  }
LABEL_13:
  if ( v25 )
    (*(void (__fastcall **)(struct CDasHostDevnodeMgmt *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( EventW )
    CloseHandle(EventW);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v9 )
    goto LABEL_20;
LABEL_21:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v15,
      11,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids,
      bInheritHandle,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000dbe0  push    rbp
0x14000dbe2  push    rbx
0x14000dbe3  push    rsi
0x14000dbe4  push    rdi
0x14000dbe5  push    r12
0x14000dbe7  push    r13
0x14000dbe9  push    r14
0x14000dbeb  push    r15
0x14000dbed  mov     rbp, rsp
0x14000dbf0  sub     rsp, 58h
0x14000dbf4  mov     r12, rcx
0x14000dbf7  mov     r13, r9
0x14000dbfa  xor     ecx, ecx
0x14000dbfc  mov     rbx, r8
0x14000dbff  mov     [rbp+var_10], rcx
0x14000dc03  mov     edi, ecx
0x14000dc05  mov     [rbp+Pid], ecx
0x14000dc08  mov     esi, ecx
0x14000dc0a  mov     [rbp+hObject], rcx
0x14000dc0e  mov     r15, rdx
0x14000dc11  lea     rdx, WPP_RECORDER_INITIALIZED; int
0x14000dc18  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000dc1f  lea     rax, WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids
0x14000dc26  jz      short loc_14000DC43
0x14000dc28  lea     r9d, [rcx+0Ah]; int
0x14000dc2c  mov     qword ptr [rsp+58h+dwDesiredAccess], rax; MessageGuid
0x14000dc31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc38  mov     rcx, [rcx+28h]; int
0x14000dc3c  call    WPP_RECORDER_SF_s
0x14000dc41  xor     ecx, ecx
0x14000dc43  mov     r14, [rbp+arg_20]
0x14000dc47  mov     [r14], rcx
0x14000dc4a  test    rbx, rbx
0x14000dc4d  jz      short loc_14000DC61
0x14000dc4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000dc53  inc     rax
0x14000dc56  cmp     [rbx+rax*2], cx
0x14000dc5a  jnz     short loc_14000DC53
0x14000dc5c  test    rax, rax
0x14000dc5f  jnz     short loc_14000DC64
0x14000dc61  mov     rbx, rcx
0x14000dc64  lea     r8, [rbp+var_10]; struct CDasHostDevnodeMgmt **
0x14000dc68  mov     rdx, rbx; unsigned __int16 *
0x14000dc6b  mov     rcx, r15; unsigned __int16 *
0x14000dc6e  call    ?Create@CDasHostDevnodeMgmt@@SAJPEBG0PEAPEAV1@@Z; CDasHostDevnodeMgmt::Create(ushort const *,ushort const *,CDasHostDevnodeMgmt * *)
0x14000dc73  xor     r15d, r15d
0x14000dc76  mov     ebx, eax
0x14000dc78  test    eax, eax
0x14000dc7a  js      short loc_14000DCAD
0x14000dc7c  xor     r9d, r9d; lpName
0x14000dc7f  xor     r8d, r8d; bInitialState
0x14000dc82  xor     edx, edx; bManualReset
0x14000dc84  xor     ecx, ecx; lpEventAttributes
0x14000dc86  call    cs:__imp_CreateEventW
0x14000dc8c  mov     rdi, rax
0x14000dc8f  test    rax, rax
0x14000dc92  jnz     loc_14000DD3A
0x14000dc98  call    cs:__imp_GetLastError
0x14000dc9e  mov     ebx, eax
0x14000dca0  test    eax, eax
0x14000dca2  jle     short loc_14000DCAD
0x14000dca4  movzx   ebx, ax
0x14000dca7  or      ebx, 80070000h
0x14000dcad  mov     rcx, [rbp+var_10]
0x14000dcb1  test    rcx, rcx
0x14000dcb4  jz      short loc_14000DCC2
0x14000dcb6  mov     rax, [rcx]
0x14000dcb9  mov     rax, [rax+10h]
0x14000dcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcc2  test    rdi, rdi
0x14000dcc5  jz      short loc_14000DCD0
0x14000dcc7  mov     rcx, rdi; hObject
0x14000dcca  call    cs:__imp_CloseHandle
0x14000dcd0  mov     rcx, [rbp+hObject]; hObject
0x14000dcd4  test    rcx, rcx
0x14000dcd7  jz      short loc_14000DCE3
0x14000dcd9  call    cs:__imp_CloseHandle
0x14000dcdf  mov     [rbp+hObject], r15
0x14000dce3  test    rsi, rsi
0x14000dce6  jz      short loc_14000DCF1
0x14000dce8  mov     rcx, rsi; hObject
0x14000dceb  call    cs:__imp_CloseHandle
0x14000dcf1  lea     rax, WPP_RECORDER_INITIALIZED
0x14000dcf8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000dcff  jz      short loc_14000DD27
0x14000dd01  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd08  lea     rax, WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids
0x14000dd0f  mov     r9d, 0Bh; int
0x14000dd15  mov     [rsp+58h+dwOptions], ebx; char
0x14000dd19  mov     qword ptr [rsp+58h+dwDesiredAccess], rax; MessageGuid
0x14000dd1e  mov     rcx, [rcx+28h]; int
0x14000dd22  call    WPP_RECORDER_SF_sd
0x14000dd27  mov     eax, ebx
0x14000dd29  add     rsp, 58h
0x14000dd2d  pop     r15
0x14000dd2f  pop     r14
0x14000dd31  pop     r13
0x14000dd33  pop     r12
0x14000dd35  pop     rdi
0x14000dd36  pop     rsi
0x14000dd37  pop     rbx
0x14000dd38  pop     rbp
0x14000dd39  retn
0x14000dd3a  lea     rdx, [rbp+Pid]; Pid
0x14000dd3e  mov     rcx, r12; Binding
0x14000dd41  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14000dd47  mov     ebx, eax
0x14000dd49  cmp     eax, 1
0x14000dd4c  jl      short loc_14000DD57
0x14000dd4e  movzx   ebx, ax
0x14000dd51  or      ebx, 80010000h
0x14000dd57  test    ebx, ebx
0x14000dd59  js      loc_14000DCAD
0x14000dd5f  xor     ecx, ecx; BindingHandle
0x14000dd61  call    cs:__imp_RpcImpersonateClient
0x14000dd67  mov     ebx, eax
0x14000dd69  test    eax, eax
0x14000dd6b  jnz     loc_14000DCA2
0x14000dd71  mov     r8d, [rbp+Pid]; dwProcessId
0x14000dd75  xor     edx, edx; bInheritHandle
0x14000dd77  mov     ecx, 1040h; dwDesiredAccess
0x14000dd7c  call    cs:__imp_OpenProcess
0x14000dd82  mov     rsi, rax
0x14000dd85  test    rax, rax
0x14000dd88  jnz     short loc_14000DDAA
0x14000dd8a  call    cs:__imp_GetLastError
0x14000dd90  mov     ebx, eax
0x14000dd92  test    eax, eax
0x14000dd94  jle     short loc_14000DD9F
0x14000dd96  movzx   ebx, ax
0x14000dd99  or      ebx, 80070000h
0x14000dd9f  call    cs:__imp_RpcRevertToSelf
0x14000dda5  jmp     loc_14000DCAD
0x14000ddaa  call    cs:__imp_GetCurrentProcess
0x14000ddb0  mov     [rsp+58h+dwOptions], r15d; dwOptions
0x14000ddb5  lea     r9, [rbp+hObject]; lpTargetHandle
0x14000ddb9  mov     rcx, rax; hSourceProcessHandle
0x14000ddbc  mov     [rsp+58h+bInheritHandle], r15d; bInheritHandle
0x14000ddc1  mov     r8, rsi; hTargetProcessHandle
0x14000ddc4  mov     [rsp+58h+dwDesiredAccess], 100000h; dwDesiredAccess
0x14000ddcc  mov     rdx, rdi; hSourceHandle
0x14000ddcf  call    cs:__imp_DuplicateHandle
0x14000ddd5  test    eax, eax
0x14000ddd7  jz      short loc_14000DD8A
0x14000ddd9  call    cs:__imp_RpcRevertToSelf
0x14000dddf  mov     rax, [rbp+var_10]
0x14000dde3  mov     ebx, r15d
0x14000dde6  mov     [rax+18h], rdi
0x14000ddea  mov     [r14], rax
0x14000dded  mov     rax, [rbp+hObject]
0x14000ddf1  mov     [r13+0], rax
0x14000ddf5  mov     [rbp+hObject], r15
0x14000ddf9  jmp     loc_14000DCE8
```
