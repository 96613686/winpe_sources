# DfscIsDomainController

- ea: `0x140005a70`
- end: `0x140005d06`
- name: `DfscIsDomainController`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003020`
- `0x140016070`
- `0x1400172ec`
- `0x140022840`

## callees

- `0x140001bd8`
- `0x1400027f8`
- `0x140005a70`
- `0x140005f70`
- `0x140006380`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140005bf6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005bf6`
- `ntoskrnl!KeInitializeEvent` at `0x140005ae5`
- `ntoskrnl!KeInitializeEvent` at `0x140005ae5`
- `msrpc!RpcAsyncInitializeHandle` at `0x140005af8`
- `msrpc!RpcAsyncInitializeHandle` at `0x140005af8`
- `msrpc!I_RpcExceptionFilter` at `0x1400068fd`
- `msrpc!I_RpcExceptionFilter` at `0x14000691f`
- `msrpc!I_RpcExceptionFilter` at `0x1400068fd`
- `msrpc!I_RpcExceptionFilter` at `0x14000691f`
- `msrpc!RpcAsyncCompleteCall` at `0x140005c09`
- `msrpc!RpcAsyncCompleteCall` at `0x140005c09`
- `msrpc!RpcBindingFree` at `0x140005c78`
- `msrpc!RpcBindingFree` at `0x140005ccf`
- `msrpc!RpcBindingFree` at `0x140005c78`
- `msrpc!RpcBindingFree` at `0x140005ccf`
- `msrpc!RpcBindingUnbind` at `0x140005c5f`
- `msrpc!RpcBindingUnbind` at `0x140005c5f`
- `msrpc!Ndr64AsyncClientCall` at `0x140005b93`
- `msrpc!Ndr64AsyncClientCall` at `0x140005b93`

## pseudocode

```c
__int64 __fastcall DfscIsDomainController(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-B0h] BYREF
  int v9; // [rsp+50h] [rbp-A8h]
  struct _KEVENT Event; // [rsp+58h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

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
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v7);
      }
    }
    else
    {
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.Event = &Event;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, &pAsync, Binding, a1, a2, a3, 0);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v7 = RpcAsyncCompleteCall(&pAsync, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v7);
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
0x140005a70  mov     [rsp+arg_18], rbx
0x140005a75  push    rsi
0x140005a76  push    rdi
0x140005a77  push    r14
0x140005a79  sub     rsp, 0E0h
0x140005a80  mov     rax, cs:__security_cookie
0x140005a87  xor     rax, rsp
0x140005a8a  mov     [rsp+0F8h+var_28], rax
0x140005a92  mov     r14, r8
0x140005a95  mov     rsi, rdx
0x140005a98  mov     rdi, rcx
0x140005a9b  xorps   xmm0, xmm0
0x140005a9e  xor     eax, eax
0x140005aa0  movups  xmmword ptr [rsp+0F8h+Event.Header], xmm0
0x140005aa5  mov     [rsp+0F8h+Event.Header.WaitListHead.Blink], rax
0x140005aaa  lea     ebx, [rax+58h]
0x140005aad  mov     r8d, ebx; Size
0x140005ab0  xor     edx, edx; Val
0x140005ab2  lea     rcx, [rsp+0F8h+pAsync]; void *
0x140005ab7  call    memset
0x140005abc  mov     [rsp+0F8h+Binding], 0
0x140005ac5  lea     rcx, [rsp+0F8h+Binding]
0x140005aca  call    DfscRpcConnect
0x140005acf  test    eax, eax
0x140005ad1  jnz     loc_140005CE1
0x140005ad7  mov     [rsp+0F8h+var_A8], eax
0x140005adb  xor     r8d, r8d; State
0x140005ade  xor     edx, edx; Type
0x140005ae0  lea     rcx, [rsp+0F8h+Event]; Event
0x140005ae5  call    cs:__imp_KeInitializeEvent
0x140005aec  nop     dword ptr [rax+rax+00h]
0x140005af1  mov     edx, ebx; Size
0x140005af3  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x140005af8  call    cs:__imp_RpcAsyncInitializeHandle
0x140005aff  nop     dword ptr [rax+rax+00h]
0x140005b04  mov     ebx, eax
0x140005b06  mov     [rsp+0F8h+var_B8], eax
0x140005b0a  test    eax, eax
0x140005b0c  jz      short loc_140005B4F
0x140005b0e  lea     rax, WPP_GLOBAL_Control
0x140005b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b1c  cmp     rcx, rax
0x140005b1f  jz      loc_140005C59
0x140005b25  test    dword ptr [rcx+2Ch], 100000h
0x140005b2c  jz      loc_140005C59
0x140005b32  mov     edx, 19h
0x140005b37  mov     r9d, ebx
0x140005b3a  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005b41  mov     rcx, [rcx+18h]
0x140005b45  call    WPP_SF_D
0x140005b4a  jmp     loc_140005C59
0x140005b4f  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x140005b5a  lea     rax, [rsp+0F8h+Event]
0x140005b5f  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x140005b67  mov     [rsp+0F8h+var_C0], r14
0x140005b6c  mov     [rsp+0F8h+var_C8], rsi
0x140005b71  mov     [rsp+0F8h+var_D0], rdi
0x140005b76  mov     rax, [rsp+0F8h+Binding]
0x140005b7b  mov     [rsp+0F8h+Timeout], rax
0x140005b80  lea     r9, [rsp+0F8h+pAsync]
0x140005b85  xor     r8d, r8d; pReturnValue
0x140005b88  lea     edx, [r8+1]; nProcNum
0x140005b8c  lea     rcx, pProxyInfo; pProxyInfo
0x140005b93  call    cs:__imp_Ndr64AsyncClientCall
0x140005b9a  nop     dword ptr [rax+rax+00h]
0x140005b9f  jmp     short loc_140005BDC
0x140005ba1  mov     ebx, eax
0x140005ba3  mov     [rsp+0F8h+var_B8], eax
0x140005ba7  lea     rax, WPP_GLOBAL_Control
0x140005bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bb5  cmp     rcx, rax
0x140005bb8  jz      short loc_140005BDC
0x140005bba  test    dword ptr [rcx+2Ch], 100000h
0x140005bc1  jz      short loc_140005BDC
0x140005bc3  mov     edx, 1Ah
0x140005bc8  mov     r9d, ebx
0x140005bcb  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005bd2  mov     rcx, [rcx+18h]
0x140005bd6  call    WPP_SF_D
0x140005bdb  nop
0x140005bdc  test    ebx, ebx
0x140005bde  jnz     short loc_140005C59
0x140005be0  mov     [rsp+0F8h+Timeout], 0; Timeout
0x140005be9  xor     r9d, r9d; Alertable
0x140005bec  xor     r8d, r8d; WaitMode
0x140005bef  xor     edx, edx; WaitReason
0x140005bf1  lea     rcx, [rsp+0F8h+Event]; Object
0x140005bf6  call    cs:__imp_KeWaitForSingleObject
0x140005bfd  nop     dword ptr [rax+rax+00h]
0x140005c02  xor     edx, edx; Reply
0x140005c04  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x140005c09  call    cs:__imp_RpcAsyncCompleteCall
0x140005c10  nop     dword ptr [rax+rax+00h]
0x140005c15  mov     ebx, eax
0x140005c17  lea     rax, WPP_GLOBAL_Control
0x140005c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c25  cmp     rcx, rax
0x140005c28  jz      short loc_140005C4B
0x140005c2a  test    dword ptr [rcx+2Ch], 400000h
0x140005c31  jz      short loc_140005C4B
0x140005c33  mov     edx, 1Bh
0x140005c38  mov     r9d, ebx
0x140005c3b  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005c42  mov     rcx, [rcx+18h]
0x140005c46  call    WPP_SF_D
0x140005c4b  mov     eax, 0C0000022h
0x140005c50  test    ebx, ebx
0x140005c52  cmovnz  ebx, eax
0x140005c55  mov     [rsp+0F8h+var_B8], ebx
0x140005c59  nop
0x140005c5a  mov     rcx, [rsp+0F8h+Binding]; Binding
0x140005c5f  call    cs:__imp_RpcBindingUnbind
0x140005c66  nop     dword ptr [rax+rax+00h]
0x140005c6b  mov     [rsp+0F8h+var_A8], 1
0x140005c73  lea     rcx, [rsp+0F8h+Binding]; Binding
0x140005c78  call    cs:__imp_RpcBindingFree
0x140005c7f  nop     dword ptr [rax+rax+00h]
0x140005c84  mov     [rsp+0F8h+Binding], 0
0x140005c8d  jmp     short loc_140005CDF
0x140005c8f  lea     rdx, WPP_GLOBAL_Control
0x140005c96  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c9d  cmp     rcx, rdx
0x140005ca0  jz      short loc_140005CC3
0x140005ca2  test    dword ptr [rcx+2Ch], 100000h
0x140005ca9  jz      short loc_140005CC3
0x140005cab  mov     edx, 1Ch
0x140005cb0  mov     r9d, eax
0x140005cb3  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005cba  mov     rcx, [rcx+18h]
0x140005cbe  call    WPP_SF_D
0x140005cc3  cmp     [rsp+0F8h+var_A8], 0
0x140005cc8  jnz     short loc_140005CDB
0x140005cca  lea     rcx, [rsp+0F8h+Binding]; Binding
0x140005ccf  call    cs:__imp_RpcBindingFree
0x140005cd6  nop     dword ptr [rax+rax+00h]
0x140005cdb  mov     ebx, [rsp+0F8h+var_B8]
0x140005cdf  mov     eax, ebx
0x140005ce1  mov     rcx, [rsp+0F8h+var_28]
0x140005ce9  xor     rcx, rsp; StackCookie
0x140005cec  call    __security_check_cookie
0x140005cf1  mov     rbx, [rsp+0F8h+arg_18]
0x140005cf9  add     rsp, 0E0h
0x140005d00  pop     r14
0x140005d02  pop     rdi
0x140005d03  pop     rsi
0x140005d04  retn
0x1400068ef  push    rbp
0x1400068f1  sub     rsp, 40h
0x1400068f5  mov     rbp, rdx
0x1400068f8  mov     rcx, [rcx]
0x1400068fb  mov     ecx, [rcx]; ExceptionCode
0x1400068fd  call    cs:__imp_I_RpcExceptionFilter
0x140006904  nop     dword ptr [rax+rax+00h]
0x140006909  nop
0x14000690a  add     rsp, 40h
0x14000690e  pop     rbp
0x14000690f  retn
0x140006911  push    rbp
0x140006913  sub     rsp, 40h
0x140006917  mov     rbp, rdx
0x14000691a  mov     rcx, [rcx]
0x14000691d  mov     ecx, [rcx]; ExceptionCode
0x14000691f  call    cs:__imp_I_RpcExceptionFilter
0x140006926  nop     dword ptr [rax+rax+00h]
0x14000692b  nop
0x14000692c  add     rsp, 40h
0x140006930  pop     rbp
0x140006931  retn
```
