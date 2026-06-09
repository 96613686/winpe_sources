# RegisterRpcCallForCancel(void * *,ulong)

- ea: `0x180015738`
- end: `0x1800157f2`
- name: `?RegisterRpcCallForCancel@@YAXPEAPEAXK@Z`
- size: `186`
- prototype: `void __fastcall(void **, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800157f8`
- `0x18001593c`

## callees

- `0x180015738`

## import_xrefs

- `msvcrt!time` at `0x1800157c7`
- `msvcrt!time` at `0x1800157c7`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800157b7`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800157b7`
- `KERNEL32!GetCurrentThread` at `0x180015760`
- `KERNEL32!GetCurrentThread` at `0x180015760`
- `KERNEL32!DuplicateHandle` at `0x18001579e`
- `KERNEL32!DuplicateHandle` at `0x18001579e`
- `KERNEL32!GetCurrentProcess` at `0x180015769`
- `KERNEL32!GetCurrentProcess` at `0x180015772`
- `KERNEL32!GetCurrentProcess` at `0x180015769`
- `KERNEL32!GetCurrentProcess` at `0x180015772`
- `KERNEL32!TlsGetValue` at `0x180015750`
- `KERNEL32!TlsGetValue` at `0x180015750`
- `KERNEL32!TlsSetValue` at `0x1800157af`
- `KERNEL32!TlsSetValue` at `0x1800157af`
- `mqsec!g_CancelRpc` at `0x1800157d2`
- `mqsec!?Add@CCancelRpc@@QEAAXPEAX_J@Z` at `0x1800157dc`
- `mqsec!?Add@CCancelRpc@@QEAAXPEAX_J@Z` at `0x1800157dc`

## pseudocode

```c
void __fastcall RegisterRpcCallForCancel(void **a1)
{
  void *Value; // rax
  HANDLE CurrentThread; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v5; // rax
  int v6; // eax
  HANDLE TargetHandle; // [rsp+50h] [rbp+8h] BYREF

  Value = TlsGetValue(g_hThreadIndex);
  TargetHandle = Value;
  if ( !Value )
  {
    CurrentThread = GetCurrentThread();
    CurrentProcess = GetCurrentProcess();
    v5 = GetCurrentProcess();
    DuplicateHandle(v5, CurrentThread, CurrentProcess, &TargetHandle, 0, 0, 2u);
    TlsSetValue(g_hThreadIndex, TargetHandle);
    RpcMgmtSetCancelTimeout(0);
    Value = TargetHandle;
  }
  *a1 = Value;
  v6 = time(0);
  CCancelRpc::Add(g_CancelRpc, TargetHandle, v6);
}

```

## disassembly

```asm
0x180015738  mov     [rsp+arg_8], rbx
0x18001573d  mov     [rsp+arg_10], rsi
0x180015742  push    rdi
0x180015743  sub     rsp, 40h
0x180015747  mov     rsi, rcx
0x18001574a  mov     ecx, cs:?g_hThreadIndex@@3KA; dwTlsIndex
0x180015750  call    cs:__imp_TlsGetValue
0x180015756  mov     [rsp+48h+TargetHandle], rax
0x18001575b  test    rax, rax
0x18001575e  jnz     short loc_1800157C2
0x180015760  call    cs:__imp_GetCurrentThread
0x180015766  mov     rdi, rax
0x180015769  call    cs:__imp_GetCurrentProcess
0x18001576f  mov     rbx, rax
0x180015772  call    cs:__imp_GetCurrentProcess
0x180015778  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180015780  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x180015785  mov     rcx, rax; hSourceProcessHandle
0x180015788  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180015790  mov     r8, rbx; hTargetProcessHandle
0x180015793  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18001579b  mov     rdx, rdi; hSourceHandle
0x18001579e  call    cs:__imp_DuplicateHandle
0x1800157a4  mov     rdx, [rsp+48h+TargetHandle]; lpTlsValue
0x1800157a9  mov     ecx, cs:?g_hThreadIndex@@3KA; dwTlsIndex
0x1800157af  call    cs:__imp_TlsSetValue
0x1800157b5  xor     ecx, ecx; Timeout
0x1800157b7  call    cs:__imp_RpcMgmtSetCancelTimeout
0x1800157bd  mov     rax, [rsp+48h+TargetHandle]
0x1800157c2  xor     ecx, ecx; Time
0x1800157c4  mov     [rsi], rax
0x1800157c7  call    cs:__imp_time
0x1800157cd  mov     rdx, [rsp+48h+TargetHandle]
0x1800157d2  mov     rcx, cs:__imp_?g_CancelRpc@@3VCCancelRpc@@A; CCancelRpc g_CancelRpc
0x1800157d9  movsxd  r8, eax
0x1800157dc  call    cs:__imp_?Add@CCancelRpc@@QEAAXPEAX_J@Z; CCancelRpc::Add(void *,__int64)
0x1800157e2  mov     rbx, [rsp+48h+arg_8]
0x1800157e7  mov     rsi, [rsp+48h+arg_10]
0x1800157ec  add     rsp, 40h
0x1800157f0  pop     rdi
0x1800157f1  retn
```
