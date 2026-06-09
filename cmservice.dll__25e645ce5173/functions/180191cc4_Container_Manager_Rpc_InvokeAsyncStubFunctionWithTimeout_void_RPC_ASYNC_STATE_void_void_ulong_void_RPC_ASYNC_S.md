# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *),void *>(ulong,void (*)(_RPC_ASYNC_STATE *,void *),void * &&)

- ea: `0x180191cc4`
- end: `0x180191f3b`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAX@ZPEAX@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAX@Z$$QEAPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180067240`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x1801911c0`
- `0x180191cc4`
- `0x180193f44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191e1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191e1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191d3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191ee9`
- `RPCRT4!RpcAsyncCancelCall` at `0x180191de6`
- `RPCRT4!RpcAsyncCancelCall` at `0x180191de6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180191e55`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180191e55`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191d02`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191d02`

## string_xrefs

- `0x180191d22`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191d5b`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191e01`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191e32`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191e87`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191ec9`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191f04`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *),void *>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 v7; // rdx
  const char *v9; // r9
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  const char *v13; // r9
  unsigned int v14; // edi
  unsigned int v15; // ebx
  unsigned int Reply[4]; // [rsp+20h] [rbp-98h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+30h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v5 )
  {
    v6 = (const char *)v5;
    v7 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v9);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_InitiateShutdown(&pAsync, *a3);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v11 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v11 = 735;
    }
    else if ( LastError == 258 )
    {
      v11 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v11 = LastError;
    }
    v12 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v12 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v12,
        Reply[0]);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v13);
  }
  Reply[0] = 0;
  v14 = RpcAsyncCompleteCall(&pAsync, Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v11 )
  {
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v14,
        Reply[0]);
    v6 = (const char *)v11;
    v7 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  if ( v14 )
  {
    v6 = (const char *)v14;
    v7 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  v15 = Reply[0];
  if ( (Reply[0] & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)Reply[0],
    Reply[0]);
  return v15;
}

```

## disassembly

```asm
0x180191cc4  mov     [rsp+arg_8], rbx
0x180191cc9  push    rdi
0x180191cca  sub     rsp, 0B0h
0x180191cd1  mov     rax, cs:__security_cookie
0x180191cd8  xor     rax, rsp
0x180191cdb  mov     [rsp+0B8h+var_18], rax
0x180191ce3  mov     rbx, r8
0x180191ce6  mov     edi, ecx
0x180191ce8  xor     edx, edx; Val
0x180191cea  lea     r8d, [rdx+70h]; Size
0x180191cee  lea     rcx, [rsp+0B8h+pAsync]; void *
0x180191cf3  call    memset_0
0x180191cf8  mov     edx, 70h ; 'p'; Size
0x180191cfd  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191d02  call    cs:__imp_RpcAsyncInitializeHandle
0x180191d09  nop     dword ptr [rax+rax+00h]
0x180191d0e  test    eax, eax
0x180191d10  jz      short loc_180191D33
0x180191d12  mov     r9d, eax; char *
0x180191d15  mov     edx, 84h; void *
0x180191d1a  mov     rcx, [rsp+0B8h]; this
0x180191d22  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191d29  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180191d2e  jmp     loc_180191F19
0x180191d33  xor     r9d, r9d; lpName
0x180191d36  xor     r8d, r8d; bInitialState
0x180191d39  xor     edx, edx; bManualReset
0x180191d3b  xor     ecx, ecx; lpEventAttributes
0x180191d3d  call    cs:__imp_CreateEventW
0x180191d44  nop     dword ptr [rax+rax+00h]
0x180191d49  mov     qword ptr [rsp+0B8h+pAsync.u], rax
0x180191d4e  test    rax, rax
0x180191d51  jnz     short loc_180191D71
0x180191d53  mov     rcx, [rsp+0B8h]; this
0x180191d5b  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191d62  mov     edx, 8Ah; void *
0x180191d67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180191d6c  jmp     loc_180191F19
0x180191d71  mov     [rsp+0B8h+pAsync.UserInfo], 0
0x180191d7a  mov     [rsp+0B8h+pAsync.NotificationType], 1
0x180191d82  mov     rdx, [rbx]
0x180191d85  lea     rcx, [rsp+0B8h+pAsync]
0x180191d8a  call    CmaRpcClt_InitiateShutdown
0x180191d8f  nop
0x180191d90  mov     edx, edi; dwMilliseconds
0x180191d92  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hHandle
0x180191d97  call    cs:__imp_WaitForSingleObject
0x180191d9e  nop     dword ptr [rax+rax+00h]
0x180191da3  xor     ebx, ebx
0x180191da5  test    eax, eax
0x180191da7  jz      loc_180191E43
0x180191dad  cmp     eax, 80h
0x180191db2  jz      short loc_180191DD7
0x180191db4  cmp     eax, 102h
0x180191db9  jz      short loc_180191DD0
0x180191dbb  cmp     eax, 0FFFFFFFFh
0x180191dbe  jnz     short loc_180191DCC
0x180191dc0  call    cs:__imp_GetLastError
0x180191dc7  nop     dword ptr [rax+rax+00h]
0x180191dcc  mov     ebx, eax
0x180191dce  jmp     short loc_180191DDC
0x180191dd0  mov     ebx, 5B4h
0x180191dd5  jmp     short loc_180191DDC
0x180191dd7  mov     ebx, 2DFh
0x180191ddc  mov     edx, 1; fAbort
0x180191de1  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191de6  call    cs:__imp_RpcAsyncCancelCall
0x180191ded  nop     dword ptr [rax+rax+00h]
0x180191df2  test    eax, eax
0x180191df4  jz      short loc_180191E12
0x180191df6  mov     rcx, [rsp+0B8h]; this
0x180191dfe  mov     r9d, eax; char *
0x180191e01  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191e08  mov     edx, 0BEh; void *
0x180191e0d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180191e12  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180191e15  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hHandle
0x180191e1a  call    cs:__imp_WaitForSingleObject
0x180191e21  nop     dword ptr [rax+rax+00h]
0x180191e26  test    eax, eax
0x180191e28  jz      short loc_180191E43
0x180191e2a  mov     rcx, [rsp+0B8h]; this
0x180191e32  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191e39  mov     edx, 0BFh; void *
0x180191e3e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180191e43  mov     [rsp+0B8h+Reply], 0; int
0x180191e4b  lea     rdx, [rsp+0B8h+Reply]; Reply
0x180191e50  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191e55  call    cs:__imp_RpcAsyncCompleteCall
0x180191e5c  nop     dword ptr [rax+rax+00h]
0x180191e61  mov     edi, eax
0x180191e63  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hObject
0x180191e68  call    cs:__imp_CloseHandle
0x180191e6f  nop     dword ptr [rax+rax+00h]
0x180191e74  test    ebx, ebx
0x180191e76  jz      short loc_180191EA5
0x180191e78  test    edi, edi
0x180191e7a  jz      short loc_180191E98
0x180191e7c  mov     rcx, [rsp+0B8h]; this
0x180191e84  mov     r9d, edi; char *
0x180191e87  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191e8e  mov     edx, 0CFh; void *
0x180191e93  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180191e98  mov     r9d, ebx
0x180191e9b  mov     edx, 0D0h
0x180191ea0  jmp     loc_180191D1A
0x180191ea5  test    edi, edi
0x180191ea7  jz      short loc_180191EB6
0x180191ea9  mov     r9d, edi
0x180191eac  mov     edx, 0D4h
0x180191eb1  jmp     loc_180191D1A
0x180191eb6  mov     ebx, [rsp+0B8h+Reply]
0x180191eba  test    ebx, ebx
0x180191ebc  jns     short loc_180191EDE
0x180191ebe  mov     rcx, [rsp+0B8h]; this
0x180191ec6  mov     r9d, ebx; char *
0x180191ec9  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191ed0  mov     edx, 0D5h; void *
0x180191ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180191eda  mov     eax, ebx
0x180191edc  jmp     short loc_180191F19
0x180191ede  xor     eax, eax
0x180191ee0  jmp     short loc_180191F19
0x180191ee2  mov     ebx, eax
0x180191ee4  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hObject
0x180191ee9  call    cs:__imp_CloseHandle
0x180191ef0  nop     dword ptr [rax+rax+00h]
0x180191ef5  test    ebx, ebx
0x180191ef7  jz      short loc_180191F17
0x180191ef9  mov     rcx, [rsp+0B8h]; this
0x180191f01  mov     r9d, ebx; char *
0x180191f04  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191f0b  mov     edx, 96h; void *
0x180191f10  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180191f15  jmp     short loc_180191F19
0x180191f17  xor     eax, eax
0x180191f19  mov     rcx, [rsp+0B8h+var_18]
0x180191f21  xor     rcx, rsp; StackCookie
0x180191f24  call    __security_check_cookie
0x180191f29  mov     rbx, [rsp+0B8h+arg_8]
0x180191f31  add     rsp, 0B0h
0x180191f38  pop     rdi
0x180191f39  retn
```
