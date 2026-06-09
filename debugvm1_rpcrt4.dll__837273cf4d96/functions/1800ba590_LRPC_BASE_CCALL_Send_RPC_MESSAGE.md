# LRPC_BASE_CCALL::Send(_RPC_MESSAGE *)

- ea: `0x1800ba590`
- end: `0x1800ba65f`
- name: `?Send@LRPC_BASE_CCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(LRPC_BASE_CCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ba670`

## callees

- `0x1800191d0`
- `0x180025280`
- `0x1800283bc`
- `0x18004b70c`
- `0x180061948`
- `0x1800a3fd4`
- `0x1800ba590`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ba5cc`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800ba5cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba5c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ba5c4`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_CCALL::Send(void **this, struct _RPC_MESSAGE *a2)
{
  __int64 v3; // r10
  __int64 v4; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  bool v7; // zf

  if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
  {
    v4 = *(_QWORD *)(v3 + 40) + 4LL;
    CurrentProcessId = GetCurrentProcessId();
    CommandLineW = (unsigned int)GetCommandLineW();
    McTemplateU0zdzj_EtwEventWriteTransfer(
      (unsigned int)L"ncalrpc",
      (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
      CommandLineW,
      CurrentProcessId,
      (__int64)L"ncalrpc",
      v4);
  }
  I_RpcBCacheFree(this[63]);
  v7 = this[64] == 0;
  this[63] = 0;
  if ( !v7 )
    LRPC_BASE_CCALL::FreeAlpcSectionAndView((LRPC_BASE_CCALL *)this, 1);
  REFERENCED_OBJECT::RemoveReference((REFERENCED_OBJECT *)this);
  RpcpErrorAddRecord(2u, 1764, 0x60Eu, 0, 0);
  return 1764;
}

```

## disassembly

```asm
0x1800ba590  mov     [rsp+arg_0], rbx
0x1800ba595  mov     [rsp+arg_8], rsi
0x1800ba59a  push    rdi
0x1800ba59b  sub     rsp, 30h
0x1800ba59f  mov     rsi, rcx
0x1800ba5a2  mov     r10, rdx
0x1800ba5a5  mov     ecx, 2; unsigned int
0x1800ba5aa  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800ba5af  test    eax, eax
0x1800ba5b1  jnz     short loc_1800BA5F5
0x1800ba5b3  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800ba5ba  jz      short loc_1800BA5F5
0x1800ba5bc  mov     rbx, [r10+28h]
0x1800ba5c0  add     rbx, 4
0x1800ba5c4  call    cs:__imp_GetCurrentProcessId
0x1800ba5ca  mov     edi, eax
0x1800ba5cc  call    cs:__imp_GetCommandLineW
0x1800ba5d2  lea     rcx, aNcalrpc; "ncalrpc"
0x1800ba5d9  mov     [rsp+38h+var_10], rbx
0x1800ba5de  mov     r8, rax
0x1800ba5e1  mov     [rsp+38h+var_18], rcx
0x1800ba5e6  mov     r9d, edi
0x1800ba5e9  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800ba5f0  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800ba5f5  mov     rcx, [rsi+1F8h]; void *
0x1800ba5fc  call    I_RpcBCacheFree
0x1800ba601  cmp     qword ptr [rsi+200h], 0
0x1800ba609  mov     qword ptr [rsi+1F8h], 0
0x1800ba614  jz      short loc_1800BA623
0x1800ba616  mov     edx, 1; int
0x1800ba61b  mov     rcx, rsi; this
0x1800ba61e  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x1800ba623  mov     rcx, rsi; this
0x1800ba626  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800ba62b  xor     r9d, r9d; int
0x1800ba62e  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800ba637  mov     ebx, 6E4h
0x1800ba63c  mov     r8d, 60Eh; unsigned __int16
0x1800ba642  mov     edx, ebx; int
0x1800ba644  lea     ecx, [r9+2]; unsigned int
0x1800ba648  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800ba64d  mov     rsi, [rsp+38h+arg_8]
0x1800ba652  mov     eax, ebx
0x1800ba654  mov     rbx, [rsp+38h+arg_0]
0x1800ba659  add     rsp, 30h
0x1800ba65d  pop     rdi
0x1800ba65e  retn
```
