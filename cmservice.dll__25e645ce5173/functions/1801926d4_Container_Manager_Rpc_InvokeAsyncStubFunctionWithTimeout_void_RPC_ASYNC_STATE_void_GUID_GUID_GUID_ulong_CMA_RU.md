# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,ulong,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void *,_GUID * &,_GUID * &,_GUID * &,ulong &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,ulong,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void * &&,_GUID * &,_GUID * &,_GUID * &,ulong &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &)

- ea: `0x1801926d4`
- end: `0x1801929dd`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_GUID@@22KPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@H@ZPEAXAEAPEAU2@AEAPEAU2@AEAPEAU2@AEAKAEAPEAU3@AEAPEAU4@AEA_N@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_GUID@@22KPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@H@Z$$QEAPEAXAEAPEAU4@77AEAKAEAPEAU5@AEAPEAU6@AEA_N@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18019344c`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x1801911c0`
- `0x1801926d4`
- `0x180193f78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019282e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801928b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019282e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801928b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192790`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192857`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192989`
- `RPCRT4!RpcAsyncCancelCall` at `0x18019287d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18019287d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801928ef`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801928ef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180192755`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180192755`

## string_xrefs

- `0x180192775`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801927b1`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192898`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801928cc`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192924`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192966`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801929a4`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,unsigned long,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void *,_GUID * &,_GUID * &,_GUID * &,unsigned long &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        __int64 *a8,
        __int64 *a9,
        unsigned __int8 *a10)
{
  unsigned int v13; // eax
  const char *v14; // r9
  __int64 v15; // rdx
  const char *v17; // r9
  DWORD LastError; // eax
  unsigned int v19; // ebx
  unsigned int v20; // eax
  const char *v21; // r9
  unsigned int v22; // edi
  int v23; // ebx
  unsigned int v24; // [rsp+20h] [rbp-108h]
  int Reply; // [rsp+50h] [rbp-D8h] BYREF
  unsigned __int8 *v26; // [rsp+58h] [rbp-D0h]
  __int64 *v27; // [rsp+60h] [rbp-C8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v27 = a9;
  v26 = a10;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v13 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v13 )
  {
    v14 = (const char *)v13;
    v15 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v17);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_NotifyCreating((unsigned int)&pAsync, *a3, *a4, *a5, *a6, *a7, *a8, *v27, *v26);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v19 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v19 = 735;
    }
    else if ( LastError == 258 )
    {
      v19 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v19 = LastError;
    }
    v20 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v20 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v20,
        v24);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v21);
  }
  Reply = 0;
  v22 = RpcAsyncCompleteCall(&pAsync, &Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v19 )
  {
    if ( v22 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v22,
        v24);
    v14 = (const char *)v19;
    v15 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  if ( v22 )
  {
    v14 = (const char *)v22;
    v15 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  v23 = Reply;
  if ( Reply >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Reply,
    v24);
  return v23;
}

```

## disassembly

```asm
0x1801926d4  push    rbx
0x1801926d6  push    rsi
0x1801926d7  push    rdi
0x1801926d8  push    r12
0x1801926da  push    r13
0x1801926dc  push    r14
0x1801926de  push    r15
0x1801926e0  sub     rsp, 0F0h
0x1801926e7  mov     rax, cs:__security_cookie
0x1801926ee  xor     rax, rsp
0x1801926f1  mov     [rsp+128h+var_48], rax
0x1801926f9  mov     rsi, r9
0x1801926fc  mov     rdi, r8
0x1801926ff  mov     ebx, ecx
0x180192701  mov     r14, [rsp+128h+arg_20]
0x180192709  mov     r15, [rsp+128h+arg_28]
0x180192711  mov     r12, [rsp+128h+arg_30]
0x180192719  mov     r13, [rsp+128h+arg_38]
0x180192721  mov     rax, [rsp+128h+arg_40]
0x180192729  mov     [rsp+128h+var_C8], rax
0x18019272e  mov     rax, [rsp+128h+arg_48]
0x180192736  mov     [rsp+128h+var_D0], rax
0x18019273b  xor     edx, edx; Val
0x18019273d  lea     r8d, [rdx+70h]; Size
0x180192741  lea     rcx, [rsp+128h+pAsync]; void *
0x180192746  call    memset_0
0x18019274b  mov     edx, 70h ; 'p'; Size
0x180192750  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180192755  call    cs:__imp_RpcAsyncInitializeHandle
0x18019275c  nop     dword ptr [rax+rax+00h]
0x180192761  test    eax, eax
0x180192763  jz      short loc_180192786
0x180192765  mov     r9d, eax; char *
0x180192768  mov     edx, 84h; void *
0x18019276d  mov     rcx, [rsp+128h]; this
0x180192775  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019277c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192781  jmp     loc_1801929B9
0x180192786  xor     r9d, r9d; lpName
0x180192789  xor     r8d, r8d; bInitialState
0x18019278c  xor     edx, edx; bManualReset
0x18019278e  xor     ecx, ecx; lpEventAttributes
0x180192790  call    cs:__imp_CreateEventW
0x180192797  nop     dword ptr [rax+rax+00h]
0x18019279c  mov     qword ptr [rsp+128h+pAsync.u], rax
0x1801927a4  test    rax, rax
0x1801927a7  jnz     short loc_1801927C7
0x1801927a9  mov     rcx, [rsp+128h]; this
0x1801927b1  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801927b8  mov     edx, 8Ah; void *
0x1801927bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801927c2  jmp     loc_1801929B9
0x1801927c7  mov     [rsp+128h+pAsync.UserInfo], 0
0x1801927d3  mov     [rsp+128h+pAsync.NotificationType], 1
0x1801927de  mov     rax, [rsp+128h+var_D0]
0x1801927e3  movzx   eax, byte ptr [rax]
0x1801927e6  mov     [rsp+128h+var_E8], eax
0x1801927ea  mov     rax, [rsp+128h+var_C8]
0x1801927ef  mov     rax, [rax]
0x1801927f2  mov     [rsp+128h+var_F0], rax
0x1801927f7  mov     rax, [r13+0]
0x1801927fb  mov     [rsp+128h+var_F8], rax
0x180192800  mov     eax, [r12]
0x180192804  mov     [rsp+128h+var_100], eax
0x180192808  mov     rax, [r15]
0x18019280b  mov     qword ptr [rsp+128h+var_108], rax; int
0x180192810  mov     r9, [r14]
0x180192813  mov     r8, [rsi]
0x180192816  mov     rdx, [rdi]
0x180192819  lea     rcx, [rsp+128h+pAsync]
0x18019281e  call    CmaRpcClt_NotifyCreating
0x180192823  nop
0x180192824  mov     edx, ebx; dwMilliseconds
0x180192826  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hHandle
0x18019282e  call    cs:__imp_WaitForSingleObject
0x180192835  nop     dword ptr [rax+rax+00h]
0x18019283a  xor     ebx, ebx
0x18019283c  test    eax, eax
0x18019283e  jz      loc_1801928DD
0x180192844  cmp     eax, 80h
0x180192849  jz      short loc_18019286E
0x18019284b  cmp     eax, 102h
0x180192850  jz      short loc_180192867
0x180192852  cmp     eax, 0FFFFFFFFh
0x180192855  jnz     short loc_180192863
0x180192857  call    cs:__imp_GetLastError
0x18019285e  nop     dword ptr [rax+rax+00h]
0x180192863  mov     ebx, eax
0x180192865  jmp     short loc_180192873
0x180192867  mov     ebx, 5B4h
0x18019286c  jmp     short loc_180192873
0x18019286e  mov     ebx, 2DFh
0x180192873  mov     edx, 1; fAbort
0x180192878  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18019287d  call    cs:__imp_RpcAsyncCancelCall
0x180192884  nop     dword ptr [rax+rax+00h]
0x180192889  test    eax, eax
0x18019288b  jz      short loc_1801928A9
0x18019288d  mov     rcx, [rsp+128h]; this
0x180192895  mov     r9d, eax; char *
0x180192898  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019289f  mov     edx, 0BEh; void *
0x1801928a4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1801928a9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801928ac  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hHandle
0x1801928b4  call    cs:__imp_WaitForSingleObject
0x1801928bb  nop     dword ptr [rax+rax+00h]
0x1801928c0  test    eax, eax
0x1801928c2  jz      short loc_1801928DD
0x1801928c4  mov     rcx, [rsp+128h]; this
0x1801928cc  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801928d3  mov     edx, 0BFh; void *
0x1801928d8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801928dd  mov     [rsp+128h+Reply], 0
0x1801928e5  lea     rdx, [rsp+128h+Reply]; Reply
0x1801928ea  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1801928ef  call    cs:__imp_RpcAsyncCompleteCall
0x1801928f6  nop     dword ptr [rax+rax+00h]
0x1801928fb  mov     edi, eax
0x1801928fd  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180192905  call    cs:__imp_CloseHandle
0x18019290c  nop     dword ptr [rax+rax+00h]
0x180192911  test    ebx, ebx
0x180192913  jz      short loc_180192942
0x180192915  test    edi, edi
0x180192917  jz      short loc_180192935
0x180192919  mov     rcx, [rsp+128h]; this
0x180192921  mov     r9d, edi; char *
0x180192924  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019292b  mov     edx, 0CFh; void *
0x180192930  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192935  mov     r9d, ebx
0x180192938  mov     edx, 0D0h
0x18019293d  jmp     loc_18019276D
0x180192942  test    edi, edi
0x180192944  jz      short loc_180192953
0x180192946  mov     r9d, edi
0x180192949  mov     edx, 0D4h
0x18019294e  jmp     loc_18019276D
0x180192953  mov     ebx, [rsp+128h+Reply]
0x180192957  test    ebx, ebx
0x180192959  jns     short loc_18019297B
0x18019295b  mov     rcx, [rsp+128h]; this
0x180192963  mov     r9d, ebx; char *
0x180192966  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019296d  mov     edx, 0D5h; void *
0x180192972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192977  mov     eax, ebx
0x180192979  jmp     short loc_1801929B9
0x18019297b  xor     eax, eax
0x18019297d  jmp     short loc_1801929B9
0x18019297f  mov     ebx, eax
0x180192981  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180192989  call    cs:__imp_CloseHandle
0x180192990  nop     dword ptr [rax+rax+00h]
0x180192995  test    ebx, ebx
0x180192997  jz      short loc_1801929B7
0x180192999  mov     rcx, [rsp+128h]; this
0x1801929a1  mov     r9d, ebx; char *
0x1801929a4  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801929ab  mov     edx, 96h; void *
0x1801929b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801929b5  jmp     short loc_1801929B9
0x1801929b7  xor     eax, eax
0x1801929b9  mov     rcx, [rsp+128h+var_48]
0x1801929c1  xor     rcx, rsp; StackCookie
0x1801929c4  call    __security_check_cookie
0x1801929c9  add     rsp, 0F0h
0x1801929d0  pop     r15
0x1801929d2  pop     r14
0x1801929d4  pop     r13
0x1801929d6  pop     r12
0x1801929d8  pop     rdi
0x1801929d9  pop     rsi
0x1801929da  pop     rbx
0x1801929db  retn
```
