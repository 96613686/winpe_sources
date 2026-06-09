# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void * &&,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &)

- ea: `0x180191f44`
- end: `0x1801921b9`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@ZPEAXAEAPEAU2@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z$$QEAPEAXAEAPEAU4@@Z`
- size: `629`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180193dc0`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x1801911c0`
- `0x180191f44`
- `0x1801940d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019201b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019209e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019201b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019209e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191fbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801920ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019216d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801920ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019216d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18019206a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18019206a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801920d9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801920d9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191f83`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191f83`

## string_xrefs

- `0x180191fa3`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191fdc`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192085`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801920b6`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18019210b`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18019214d`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192188`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  unsigned int v7; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  const char *v11; // r9
  DWORD LastError; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  const char *v15; // r9
  unsigned int v16; // edi
  unsigned int v17; // ebx
  unsigned int Reply[4]; // [rsp+20h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+30h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v7 )
  {
    v8 = (const char *)v7;
    v9 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v11);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_UpdateHotPatches(&pAsync, *a3, *a4);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v13 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v13 = 735;
    }
    else if ( LastError == 258 )
    {
      v13 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v13 = LastError;
    }
    v14 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v14,
        Reply[0]);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v15);
  }
  Reply[0] = 0;
  v16 = RpcAsyncCompleteCall(&pAsync, Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v13 )
  {
    if ( v16 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v16,
        Reply[0]);
    v8 = (const char *)v13;
    v9 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  if ( v16 )
  {
    v8 = (const char *)v16;
    v9 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  v17 = Reply[0];
  if ( (Reply[0] & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)Reply[0],
    Reply[0]);
  return v17;
}

```

## disassembly

```asm
0x180191f44  push    rbx
0x180191f46  push    rsi
0x180191f47  push    rdi
0x180191f48  sub     rsp, 0B0h
0x180191f4f  mov     rax, cs:__security_cookie
0x180191f56  xor     rax, rsp
0x180191f59  mov     [rsp+0C8h+var_28], rax
0x180191f61  mov     rdi, r9
0x180191f64  mov     rbx, r8
0x180191f67  mov     esi, ecx
0x180191f69  xor     edx, edx; Val
0x180191f6b  lea     r8d, [rdx+70h]; Size
0x180191f6f  lea     rcx, [rsp+0C8h+pAsync]; void *
0x180191f74  call    memset_0
0x180191f79  mov     edx, 70h ; 'p'; Size
0x180191f7e  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180191f83  call    cs:__imp_RpcAsyncInitializeHandle
0x180191f8a  nop     dword ptr [rax+rax+00h]
0x180191f8f  test    eax, eax
0x180191f91  jz      short loc_180191FB4
0x180191f93  mov     r9d, eax; char *
0x180191f96  mov     edx, 84h; void *
0x180191f9b  mov     rcx, [rsp+0C8h]; this
0x180191fa3  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191faa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180191faf  jmp     loc_18019219D
0x180191fb4  xor     r9d, r9d; lpName
0x180191fb7  xor     r8d, r8d; bInitialState
0x180191fba  xor     edx, edx; bManualReset
0x180191fbc  xor     ecx, ecx; lpEventAttributes
0x180191fbe  call    cs:__imp_CreateEventW
0x180191fc5  nop     dword ptr [rax+rax+00h]
0x180191fca  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x180191fcf  test    rax, rax
0x180191fd2  jnz     short loc_180191FF2
0x180191fd4  mov     rcx, [rsp+0C8h]; this
0x180191fdc  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191fe3  mov     edx, 8Ah; void *
0x180191fe8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180191fed  jmp     loc_18019219D
0x180191ff2  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x180191ffb  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x180192003  mov     r8, [rdi]
0x180192006  mov     rdx, [rbx]
0x180192009  lea     rcx, [rsp+0C8h+pAsync]
0x18019200e  call    CmaRpcClt_UpdateHotPatches
0x180192013  nop
0x180192014  mov     edx, esi; dwMilliseconds
0x180192016  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019201b  call    cs:__imp_WaitForSingleObject
0x180192022  nop     dword ptr [rax+rax+00h]
0x180192027  xor     ebx, ebx
0x180192029  test    eax, eax
0x18019202b  jz      loc_1801920C7
0x180192031  cmp     eax, 80h
0x180192036  jz      short loc_18019205B
0x180192038  cmp     eax, 102h
0x18019203d  jz      short loc_180192054
0x18019203f  cmp     eax, 0FFFFFFFFh
0x180192042  jnz     short loc_180192050
0x180192044  call    cs:__imp_GetLastError
0x18019204b  nop     dword ptr [rax+rax+00h]
0x180192050  mov     ebx, eax
0x180192052  jmp     short loc_180192060
0x180192054  mov     ebx, 5B4h
0x180192059  jmp     short loc_180192060
0x18019205b  mov     ebx, 2DFh
0x180192060  mov     edx, 1; fAbort
0x180192065  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x18019206a  call    cs:__imp_RpcAsyncCancelCall
0x180192071  nop     dword ptr [rax+rax+00h]
0x180192076  test    eax, eax
0x180192078  jz      short loc_180192096
0x18019207a  mov     rcx, [rsp+0C8h]; this
0x180192082  mov     r9d, eax; char *
0x180192085  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019208c  mov     edx, 0BEh; void *
0x180192091  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192096  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192099  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019209e  call    cs:__imp_WaitForSingleObject
0x1801920a5  nop     dword ptr [rax+rax+00h]
0x1801920aa  test    eax, eax
0x1801920ac  jz      short loc_1801920C7
0x1801920ae  mov     rcx, [rsp+0C8h]; this
0x1801920b6  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801920bd  mov     edx, 0BFh; void *
0x1801920c2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801920c7  mov     [rsp+0C8h+Reply], 0; int
0x1801920cf  lea     rdx, [rsp+0C8h+Reply]; Reply
0x1801920d4  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801920d9  call    cs:__imp_RpcAsyncCompleteCall
0x1801920e0  nop     dword ptr [rax+rax+00h]
0x1801920e5  mov     edi, eax
0x1801920e7  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801920ec  call    cs:__imp_CloseHandle
0x1801920f3  nop     dword ptr [rax+rax+00h]
0x1801920f8  test    ebx, ebx
0x1801920fa  jz      short loc_180192129
0x1801920fc  test    edi, edi
0x1801920fe  jz      short loc_18019211C
0x180192100  mov     rcx, [rsp+0C8h]; this
0x180192108  mov     r9d, edi; char *
0x18019210b  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192112  mov     edx, 0CFh; void *
0x180192117  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18019211c  mov     r9d, ebx
0x18019211f  mov     edx, 0D0h
0x180192124  jmp     loc_180191F9B
0x180192129  test    edi, edi
0x18019212b  jz      short loc_18019213A
0x18019212d  mov     r9d, edi
0x180192130  mov     edx, 0D4h
0x180192135  jmp     loc_180191F9B
0x18019213a  mov     ebx, [rsp+0C8h+Reply]
0x18019213e  test    ebx, ebx
0x180192140  jns     short loc_180192162
0x180192142  mov     rcx, [rsp+0C8h]; this
0x18019214a  mov     r9d, ebx; char *
0x18019214d  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192154  mov     edx, 0D5h; void *
0x180192159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019215e  mov     eax, ebx
0x180192160  jmp     short loc_18019219D
0x180192162  xor     eax, eax
0x180192164  jmp     short loc_18019219D
0x180192166  mov     ebx, eax
0x180192168  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x18019216d  call    cs:__imp_CloseHandle
0x180192174  nop     dword ptr [rax+rax+00h]
0x180192179  test    ebx, ebx
0x18019217b  jz      short loc_18019219B
0x18019217d  mov     rcx, [rsp+0C8h]; this
0x180192185  mov     r9d, ebx; char *
0x180192188  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019218f  mov     edx, 96h; void *
0x180192194  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192199  jmp     short loc_18019219D
0x18019219b  xor     eax, eax
0x18019219d  mov     rcx, [rsp+0C8h+var_28]
0x1801921a5  xor     rcx, rsp; StackCookie
0x1801921a8  call    __security_check_cookie
0x1801921ad  add     rsp, 0B0h
0x1801921b4  pop     rdi
0x1801921b5  pop     rsi
0x1801921b6  pop     rbx
0x1801921b7  retn
```
