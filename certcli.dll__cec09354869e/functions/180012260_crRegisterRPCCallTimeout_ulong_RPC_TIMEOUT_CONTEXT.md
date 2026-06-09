# crRegisterRPCCallTimeout(ulong,_RPC_TIMEOUT_CONTEXT *)

- ea: `0x180012260`
- end: `0x18001234f`
- name: `?crRegisterRPCCallTimeout@@YAJKPEAU_RPC_TIMEOUT_CONTEXT@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, struct _RPC_TIMEOUT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e14`

## callees

- `0x180011fc4`
- `0x180012260`
- `0x180021438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800122d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800122d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800122b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800122b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001228b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001228b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180012313`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180012313`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001232b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001232b`

## pseudocode

```c
__int64 __fastcall crRegisterRPCCallTimeout(__int64 a1, struct _RPC_TIMEOUT_CONTEXT *a2)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ecx
  HANDLE EventW; // rax
  unsigned int v9; // ebx

  *((_DWORD *)a2 + 6) = 1818;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v5 = GetCurrentProcess();
  if ( DuplicateHandle(v5, CurrentThread, CurrentProcess, (LPHANDLE)a2 + 2, 0, 0, 2u) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)a2 + 1) = EventW;
    if ( EventW )
    {
      v9 = 0;
      if ( RegisterWaitForSingleObject((PHANDLE)a2, EventW, crRPCTimeoutCallback, a2, 0xEA60u, 8u) )
        return v9;
      v6 = myHLastError();
      v7 = 247923396;
    }
    else
    {
      v6 = myHLastError();
      v7 = 247071428;
    }
  }
  else
  {
    v6 = myHLastError();
    v7 = 246612676;
  }
  v9 = v6;
  CSPrintErrorLineFile(v7, v6);
  if ( v9 )
    crCloseRPCCallTimeout(a2);
  return v9;
}

```

## disassembly

```asm
0x180012260  mov     [rsp+arg_0], rbx
0x180012265  mov     [rsp+arg_8], rsi
0x18001226a  push    rdi
0x18001226b  sub     rsp, 40h
0x18001226f  mov     rsi, rdx
0x180012272  mov     dword ptr [rdx+18h], 71Ah
0x180012279  call    cs:__imp_GetCurrentProcess
0x18001227f  mov     rdi, rax
0x180012282  call    cs:__imp_GetCurrentThread
0x180012288  mov     rbx, rax
0x18001228b  call    cs:__imp_GetCurrentProcess
0x180012291  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180012299  lea     r9, [rsi+10h]; lpTargetHandle
0x18001229d  mov     rcx, rax; hSourceProcessHandle
0x1800122a0  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x1800122a8  mov     r8, rdi; hTargetProcessHandle
0x1800122ab  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x1800122b3  mov     rdx, rbx; hSourceHandle
0x1800122b6  call    cs:__imp_DuplicateHandle
0x1800122bc  test    eax, eax
0x1800122be  jnz     short loc_1800122CC
0x1800122c0  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800122c5  mov     ecx, 0EB302C4h
0x1800122ca  jmp     short loc_180012327
0x1800122cc  xor     r9d, r9d; lpName
0x1800122cf  xor     r8d, r8d; bInitialState
0x1800122d2  xor     edx, edx; bManualReset
0x1800122d4  xor     ecx, ecx; lpEventAttributes
0x1800122d6  call    cs:__imp_CreateEventW
0x1800122dc  mov     [rsi+8], rax
0x1800122e0  test    rax, rax
0x1800122e3  jnz     short loc_1800122F1
0x1800122e5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800122ea  mov     ecx, 0EBA02C4h
0x1800122ef  jmp     short loc_180012327
0x1800122f1  mov     [rsp+48h+bInheritHandle], 8; dwFlags
0x1800122f9  lea     r8, ?crRPCTimeoutCallback@@YAXPEAXE@Z; Callback
0x180012300  mov     r9, rsi; Context
0x180012303  mov     [rsp+48h+dwDesiredAccess], 0EA60h; dwMilliseconds
0x18001230b  mov     rdx, rax; hObject
0x18001230e  mov     rcx, rsi; phNewWaitObject
0x180012311  xor     ebx, ebx
0x180012313  call    cs:__imp_RegisterWaitForSingleObject
0x180012319  test    eax, eax
0x18001231b  jnz     short loc_18001233D
0x18001231d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180012322  mov     ecx, 0EC702C4h
0x180012327  mov     edx, eax
0x180012329  mov     ebx, eax
0x18001232b  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180012331  test    ebx, ebx
0x180012333  jz      short loc_18001233D
0x180012335  mov     rcx, rsi; struct _RPC_TIMEOUT_CONTEXT *
0x180012338  call    ?crCloseRPCCallTimeout@@YAJPEAU_RPC_TIMEOUT_CONTEXT@@@Z; crCloseRPCCallTimeout(_RPC_TIMEOUT_CONTEXT *)
0x18001233d  mov     rsi, [rsp+48h+arg_8]
0x180012342  mov     eax, ebx
0x180012344  mov     rbx, [rsp+48h+arg_0]
0x180012349  add     rsp, 40h
0x18001234d  pop     rdi
0x18001234e  retn
```
