# DfscGetDCName

- ea: `0x14000193c`
- end: `0x140001bd0`
- name: `DfscGetDCName`
- size: `660`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002cd0`
- `0x140003020`
- `0x14001abc0`
- `0x140022840`
- `0x140022a48`

## callees

- `0x14000193c`
- `0x140001bd8`
- `0x1400027f8`
- `0x140005f70`
- `0x140006380`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140001ac0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001ac0`
- `ntoskrnl!KeInitializeEvent` at `0x1400019b1`
- `ntoskrnl!KeInitializeEvent` at `0x1400019b1`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400019c4`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400019c4`
- `msrpc!I_RpcExceptionFilter` at `0x14000688b`
- `msrpc!I_RpcExceptionFilter` at `0x1400068ad`
- `msrpc!I_RpcExceptionFilter` at `0x14000688b`
- `msrpc!I_RpcExceptionFilter` at `0x1400068ad`
- `msrpc!RpcAsyncCompleteCall` at `0x140001ad3`
- `msrpc!RpcAsyncCompleteCall` at `0x140001ad3`
- `msrpc!RpcBindingFree` at `0x140001b42`
- `msrpc!RpcBindingFree` at `0x140001b99`
- `msrpc!RpcBindingFree` at `0x140001b42`
- `msrpc!RpcBindingFree` at `0x140001b99`
- `msrpc!RpcBindingUnbind` at `0x140001b29`
- `msrpc!RpcBindingUnbind` at `0x140001b29`
- `msrpc!Ndr64AsyncClientCall` at `0x140001a5d`
- `msrpc!Ndr64AsyncClientCall` at `0x140001a5d`

## pseudocode

```c
__int64 __fastcall DfscGetDCName(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-B0h] BYREF
  int v9; // [rsp+50h] [rbp-A8h]
  _KEVENT Event; // [rsp+58h] [rbp-A0h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  result = DfscRpcConnect(&Binding);
  if ( !(_DWORD)result )
  {
    v9 = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v7 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v7);
      }
    }
    else
    {
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.Event = &Event;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, &pAsync, Binding, a1, a3, a2, 0);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v7 = RpcAsyncCompleteCall(&pAsync, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v7);
      }
      if ( v7 )
        v7 = -1073741790;
    }
    RpcBindingUnbind(Binding);
    v9 = 1;
    RpcBindingFree(&Binding);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14000193c  mov     [rsp+arg_18], rbx
0x140001941  push    rsi
0x140001942  push    rdi
0x140001943  push    r14
0x140001945  sub     rsp, 0E0h
0x14000194c  mov     rax, cs:__security_cookie
0x140001953  xor     rax, rsp
0x140001956  mov     [rsp+0F8h+var_28], rax
0x14000195e  mov     r14d, r8d
0x140001961  mov     rsi, rdx
0x140001964  mov     rdi, rcx
0x140001967  xorps   xmm0, xmm0
0x14000196a  xor     eax, eax
0x14000196c  movups  xmmword ptr [rsp+0F8h+Event.Header], xmm0
0x140001971  mov     [rsp+0F8h+Event.Header.WaitListHead.Blink], rax
0x140001976  lea     ebx, [rax+58h]
0x140001979  mov     r8d, ebx; Size
0x14000197c  xor     edx, edx; Val
0x14000197e  lea     rcx, [rsp+0F8h+pAsync]; void *
0x140001983  call    memset
0x140001988  mov     [rsp+0F8h+Binding], 0
0x140001991  lea     rcx, [rsp+0F8h+Binding]
0x140001996  call    DfscRpcConnect
0x14000199b  test    eax, eax
0x14000199d  jnz     loc_140001BAB
0x1400019a3  mov     [rsp+0F8h+var_A8], eax
0x1400019a7  xor     r8d, r8d; State
0x1400019aa  xor     edx, edx; Type
0x1400019ac  lea     rcx, [rsp+0F8h+Event]; Event
0x1400019b1  call    cs:__imp_KeInitializeEvent
0x1400019b8  nop     dword ptr [rax+rax+00h]
0x1400019bd  mov     edx, ebx; Size
0x1400019bf  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1400019c4  call    cs:__imp_RpcAsyncInitializeHandle
0x1400019cb  nop     dword ptr [rax+rax+00h]
0x1400019d0  mov     ebx, eax
0x1400019d2  mov     [rsp+0F8h+var_B8], eax
0x1400019d6  test    eax, eax
0x1400019d8  jz      short loc_140001A1B
0x1400019da  lea     rax, WPP_GLOBAL_Control
0x1400019e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019e8  cmp     rcx, rax
0x1400019eb  jz      loc_140001B23
0x1400019f1  test    dword ptr [rcx+2Ch], 100000h
0x1400019f8  jz      loc_140001B23
0x1400019fe  mov     edx, 15h
0x140001a03  mov     r9d, ebx
0x140001a06  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001a0d  mov     rcx, [rcx+18h]
0x140001a11  call    WPP_SF_D
0x140001a16  jmp     loc_140001B23
0x140001a1b  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x140001a26  lea     rax, [rsp+0F8h+Event]
0x140001a2b  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x140001a33  mov     [rsp+0F8h+var_C0], rsi
0x140001a38  mov     [rsp+0F8h+var_C8], r14d
0x140001a3d  mov     [rsp+0F8h+var_D0], rdi
0x140001a42  mov     rax, [rsp+0F8h+Binding]
0x140001a47  mov     [rsp+0F8h+Timeout], rax
0x140001a4c  lea     r9, [rsp+0F8h+pAsync]
0x140001a51  xor     r8d, r8d; pReturnValue
0x140001a54  xor     edx, edx; nProcNum
0x140001a56  lea     rcx, pProxyInfo; pProxyInfo
0x140001a5d  call    cs:__imp_Ndr64AsyncClientCall
0x140001a64  nop     dword ptr [rax+rax+00h]
0x140001a69  jmp     short loc_140001AA6
0x140001a6b  mov     ebx, eax
0x140001a6d  mov     [rsp+0F8h+var_B8], eax
0x140001a71  lea     rax, WPP_GLOBAL_Control
0x140001a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a7f  cmp     rcx, rax
0x140001a82  jz      short loc_140001AA6
0x140001a84  test    dword ptr [rcx+2Ch], 100000h
0x140001a8b  jz      short loc_140001AA6
0x140001a8d  mov     edx, 16h
0x140001a92  mov     r9d, ebx
0x140001a95  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001a9c  mov     rcx, [rcx+18h]
0x140001aa0  call    WPP_SF_D
0x140001aa5  nop
0x140001aa6  test    ebx, ebx
0x140001aa8  jnz     short loc_140001B23
0x140001aaa  mov     [rsp+0F8h+Timeout], 0; Timeout
0x140001ab3  xor     r9d, r9d; Alertable
0x140001ab6  xor     r8d, r8d; WaitMode
0x140001ab9  xor     edx, edx; WaitReason
0x140001abb  lea     rcx, [rsp+0F8h+Event]; Object
0x140001ac0  call    cs:__imp_KeWaitForSingleObject
0x140001ac7  nop     dword ptr [rax+rax+00h]
0x140001acc  xor     edx, edx; Reply
0x140001ace  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x140001ad3  call    cs:__imp_RpcAsyncCompleteCall
0x140001ada  nop     dword ptr [rax+rax+00h]
0x140001adf  mov     ebx, eax
0x140001ae1  lea     rax, WPP_GLOBAL_Control
0x140001ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aef  cmp     rcx, rax
0x140001af2  jz      short loc_140001B15
0x140001af4  test    dword ptr [rcx+2Ch], 400000h
0x140001afb  jz      short loc_140001B15
0x140001afd  mov     edx, 17h
0x140001b02  mov     r9d, ebx
0x140001b05  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001b0c  mov     rcx, [rcx+18h]
0x140001b10  call    WPP_SF_D
0x140001b15  mov     eax, 0C0000022h
0x140001b1a  test    ebx, ebx
0x140001b1c  cmovnz  ebx, eax
0x140001b1f  mov     [rsp+0F8h+var_B8], ebx
0x140001b23  nop
0x140001b24  mov     rcx, [rsp+0F8h+Binding]; Binding
0x140001b29  call    cs:__imp_RpcBindingUnbind
0x140001b30  nop     dword ptr [rax+rax+00h]
0x140001b35  mov     [rsp+0F8h+var_A8], 1
0x140001b3d  lea     rcx, [rsp+0F8h+Binding]; Binding
0x140001b42  call    cs:__imp_RpcBindingFree
0x140001b49  nop     dword ptr [rax+rax+00h]
0x140001b4e  mov     [rsp+0F8h+Binding], 0
0x140001b57  jmp     short loc_140001BA9
0x140001b59  lea     rdx, WPP_GLOBAL_Control
0x140001b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b67  cmp     rcx, rdx
0x140001b6a  jz      short loc_140001B8D
0x140001b6c  test    dword ptr [rcx+2Ch], 100000h
0x140001b73  jz      short loc_140001B8D
0x140001b75  mov     edx, 18h
0x140001b7a  mov     r9d, eax
0x140001b7d  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140001b84  mov     rcx, [rcx+18h]
0x140001b88  call    WPP_SF_D
0x140001b8d  cmp     [rsp+0F8h+var_A8], 0
0x140001b92  jnz     short loc_140001BA5
0x140001b94  lea     rcx, [rsp+0F8h+Binding]; Binding
0x140001b99  call    cs:__imp_RpcBindingFree
0x140001ba0  nop     dword ptr [rax+rax+00h]
0x140001ba5  mov     ebx, [rsp+0F8h+var_B8]
0x140001ba9  mov     eax, ebx
0x140001bab  mov     rcx, [rsp+0F8h+var_28]
0x140001bb3  xor     rcx, rsp; StackCookie
0x140001bb6  call    __security_check_cookie
0x140001bbb  mov     rbx, [rsp+0F8h+arg_18]
0x140001bc3  add     rsp, 0E0h
0x140001bca  pop     r14
0x140001bcc  pop     rdi
0x140001bcd  pop     rsi
0x140001bce  retn
0x14000687d  push    rbp
0x14000687f  sub     rsp, 40h
0x140006883  mov     rbp, rdx
0x140006886  mov     rcx, [rcx]
0x140006889  mov     ecx, [rcx]; ExceptionCode
0x14000688b  call    cs:__imp_I_RpcExceptionFilter
0x140006892  nop     dword ptr [rax+rax+00h]
0x140006897  nop
0x140006898  add     rsp, 40h
0x14000689c  pop     rbp
0x14000689d  retn
0x14000689f  push    rbp
0x1400068a1  sub     rsp, 40h
0x1400068a5  mov     rbp, rdx
0x1400068a8  mov     rcx, [rcx]
0x1400068ab  mov     ecx, [rcx]; ExceptionCode
0x1400068ad  call    cs:__imp_I_RpcExceptionFilter
0x1400068b4  nop     dword ptr [rax+rax+00h]
0x1400068b9  nop
0x1400068ba  add     rsp, 40h
0x1400068be  pop     rbp
0x1400068bf  retn
```
