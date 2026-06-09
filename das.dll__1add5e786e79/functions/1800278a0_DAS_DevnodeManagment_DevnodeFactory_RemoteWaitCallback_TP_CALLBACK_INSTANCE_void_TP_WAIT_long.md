# DAS::DevnodeManagment::DevnodeFactory::RemoteWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800278a0`
- end: `0x180027a2f`
- name: `?RemoteWaitCallback@DevnodeFactory@DevnodeManagment@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `399`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800240b4`
- `0x1800278a0`
- `0x180029994`
- `0x18002b908`
- `0x180045df0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800278c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800278c2`
- `RPCRT4!NdrClientCall3` at `0x180027900`
- `RPCRT4!NdrClientCall3` at `0x180027900`

## string_xrefs

- `0x180027930`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x180027963`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x180027992`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x1800279be`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x180027a12`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
void __fastcall DAS::DevnodeManagment::DevnodeFactory::RemoteWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  char *v5; // rdi
  int Pointer; // eax
  int v7; // eax
  int v8; // eax
  char *v9; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v11; // [rsp+58h] [rbp+10h] BYREF

  v5 = Context + 192;
  SetThreadpoolWait(*((PTP_WAIT *)Context + 26), *((HANDLE *)Context + 25), 0);
  v11 = 16;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180083280, 0x14u, 0, v5, &v11, Context + 216).Pointer;
  if ( Pointer != 1 )
  {
    if ( Pointer >= 0 )
    {
      if ( (v11 & 0x20) != 0 )
      {
        v7 = DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteDevnodeOp((__int64)Context, v11);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1DD,
            (int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
            (const char *)(unsigned int)v7);
      }
      else if ( (v11 & 0x10) != 0 )
      {
        v8 = DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteFactoryOp(Context);
        if ( v8 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1E7,
            (int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
            (const char *)(unsigned int)v8);
      }
      else
      {
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x1ED,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
          (const char *)0x80004001LL,
          (__int64)"unexpected operation from provider host",
          v9);
      }
    }
    else
    {
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)Pointer,
        (__int64)"DasHostPickupDevnodeManagementOperation failed.",
        v9);
    }
  }
}

```

## disassembly

```asm
0x1800278a0  mov     [rsp+arg_0], rbx
0x1800278a5  push    rdi
0x1800278a6  sub     rsp, 40h
0x1800278aa  mov     rbx, rdx
0x1800278ad  lea     rdi, [rdx+0C0h]
0x1800278b4  xor     r8d, r8d; pftTimeout
0x1800278b7  mov     rdx, [rdi+8]; h
0x1800278bb  mov     rcx, [rbx+0D0h]; pwa
0x1800278c2  call    cs:__imp_SetThreadpoolWait
0x1800278c8  mov     [rsp+48h+arg_8], 10h
0x1800278d0  mov     [rsp+48h+var_10], 0
0x1800278d9  lea     rax, [rbx+0D8h]
0x1800278e0  mov     [rsp+48h+var_20], rax; char *
0x1800278e5  lea     rax, [rsp+48h+arg_8]
0x1800278ea  mov     [rsp+48h+var_28], rax; int
0x1800278ef  mov     r9, rdi
0x1800278f2  xor     r8d, r8d; pReturnValue
0x1800278f5  lea     edx, [r8+14h]; nProcNum
0x1800278f9  lea     rcx, stru_180083280; pProxyInfo
0x180027900  call    cs:__imp_NdrClientCall3
0x180027906  mov     [rsp+48h+var_10], rax
0x18002790b  mov     [rsp+48h+var_18], eax
0x18002790f  cmp     eax, 1
0x180027912  jz      loc_180027A24
0x180027918  test    eax, eax
0x18002791a  jns     short loc_180027946
0x18002791c  lea     rdx, aDashostpickupd; "DasHostPickupDevnodeManagementOperation"...
0x180027923  mov     [rsp+48h+var_28], rdx; __int64
0x180027928  mov     r9d, eax; char *
0x18002792b  mov     edx, 1D6h; void *
0x180027930  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180027937  mov     rcx, [rsp+48h]; this
0x18002793c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027941  jmp     loc_180027A24
0x180027946  mov     edx, [rsp+48h+arg_8]
0x18002794a  test    dl, 20h
0x18002794d  jz      short loc_1800279A5
0x18002794f  mov     rcx, rbx
0x180027952  call    ?ProcessRemoteDevnodeOp@DevnodeFactory@DevnodeManagment@DAS@@AEAAJW4DEVMGMT_OP_TYPE@@@Z; DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteDevnodeOp(DEVMGMT_OP_TYPE)
0x180027957  mov     rcx, [rsp+48h]; this
0x18002795c  test    eax, eax
0x18002795e  jns     short loc_180027974
0x180027960  mov     r9d, eax; char *
0x180027963  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002796a  mov     edx, 1DDh; void *
0x18002796f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027974  jmp     loc_180027A24
0x180027979  cmp     eax, 1
0x18002797c  jl      short loc_180027986
0x18002797e  movzx   eax, ax
0x180027981  or      eax, 80010000h
0x180027986  test    eax, eax
0x180027988  jns     short loc_1800279A3
0x18002798a  mov     rcx, [rsp+48h]; this
0x18002798f  mov     r9d, eax; char *
0x180027992  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180027999  mov     edx, 1E1h; void *
0x18002799e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800279a3  jmp     short loc_180027A24
0x1800279a5  test    dl, 10h
0x1800279a8  jz      short loc_1800279D1
0x1800279aa  mov     rcx, rbx
0x1800279ad  call    ?ProcessRemoteFactoryOp@DevnodeFactory@DevnodeManagment@DAS@@AEAAJW4DEVMGMT_OP_TYPE@@@Z; DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteFactoryOp(DEVMGMT_OP_TYPE)
0x1800279b2  test    eax, eax
0x1800279b4  jns     short loc_180027A24
0x1800279b6  mov     rcx, [rsp+48h]; this
0x1800279bb  mov     r9d, eax; char *
0x1800279be  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x1800279c5  mov     edx, 1E7h; void *
0x1800279ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800279cf  jmp     short loc_180027A24
0x1800279d1  lea     rax, aUnexpectedOper; "unexpected operation from provider host"
0x1800279d8  mov     [rsp+48h+var_28], rax
0x1800279dd  mov     r9d, 80004001h
0x1800279e3  mov     edx, 1EDh
0x1800279e8  jmp     loc_180027930
0x1800279ed  cmp     eax, 1
0x1800279f0  jl      short loc_1800279FA
0x1800279f2  movzx   eax, ax
0x1800279f5  or      eax, 80010000h
0x1800279fa  mov     [rsp+48h+var_18], eax
0x1800279fe  mov     rcx, [rsp+48h]; this
0x180027a03  lea     rdx, aFailedToCallDa; "Failed to call DasHostPickupDevnodeMana"...
0x180027a0a  mov     [rsp+48h+var_28], rdx; __int64
0x180027a0f  mov     r9d, eax; char *
0x180027a12  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x180027a19  mov     edx, 1CBh; void *
0x180027a1e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027a23  nop
0x180027a24  mov     rbx, [rsp+48h+arg_0]
0x180027a29  add     rsp, 40h
0x180027a2d  pop     rdi
0x180027a2e  retn
```
