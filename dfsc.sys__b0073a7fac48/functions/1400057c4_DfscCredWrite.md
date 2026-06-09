# DfscCredWrite

- ea: `0x1400057c4`
- end: `0x140005a68`
- name: `DfscCredWrite`
- size: `676`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014520`

## callees

- `0x140001bd8`
- `0x1400025a0`
- `0x1400027f8`
- `0x1400057c4`
- `0x140005f70`
- `0x140006380`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000594f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000594f`
- `ntoskrnl!KeInitializeEvent` at `0x14000583a`
- `ntoskrnl!KeInitializeEvent` at `0x14000583a`
- `msrpc!RpcAsyncInitializeHandle` at `0x14000584d`
- `msrpc!RpcAsyncInitializeHandle` at `0x14000584d`
- `msrpc!RpcAsyncCompleteCall` at `0x140005962`
- `msrpc!RpcAsyncCompleteCall` at `0x140005962`
- `msrpc!RpcBindingFree` at `0x1400059d9`
- `msrpc!RpcBindingFree` at `0x140005a30`
- `msrpc!RpcBindingFree` at `0x1400059d9`
- `msrpc!RpcBindingFree` at `0x140005a30`
- `msrpc!RpcBindingUnbind` at `0x1400059c0`
- `msrpc!RpcBindingUnbind` at `0x1400059c0`
- `msrpc!Ndr64AsyncClientCall` at `0x1400058e8`
- `msrpc!Ndr64AsyncClientCall` at `0x1400058e8`

## pseudocode

```c
__int64 __fastcall DfscCredWrite(__int64 a1, __int64 a2, __int64 a3)
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
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v7);
      }
    }
    else
    {
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.Event = &Event;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, &pAsync, Binding, a1, a2, a3, 0);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v7 = RpcAsyncCompleteCall(&pAsync, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids);
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
0x1400057c4  mov     [rsp+arg_18], rbx
0x1400057c9  push    rsi
0x1400057ca  push    r14
0x1400057cc  push    r15
0x1400057ce  sub     rsp, 0E0h
0x1400057d5  mov     rax, cs:__security_cookie
0x1400057dc  xor     rax, rsp
0x1400057df  mov     [rsp+0F8h+var_28], rax
0x1400057e7  mov     r15, r8
0x1400057ea  mov     r14, rdx
0x1400057ed  mov     rsi, rcx
0x1400057f0  xorps   xmm0, xmm0
0x1400057f3  xor     eax, eax
0x1400057f5  movups  xmmword ptr [rsp+0F8h+Event.Header], xmm0
0x1400057fa  mov     [rsp+0F8h+Event.Header.WaitListHead.Blink], rax
0x1400057ff  lea     ebx, [rax+58h]
0x140005802  mov     r8d, ebx; Size
0x140005805  xor     edx, edx; Val
0x140005807  lea     rcx, [rsp+0F8h+pAsync]; void *
0x14000580c  call    memset
0x140005811  mov     [rsp+0F8h+Binding], 0
0x14000581a  lea     rcx, [rsp+0F8h+Binding]
0x14000581f  call    DfscRpcConnect
0x140005824  test    eax, eax
0x140005826  jnz     loc_140005A42
0x14000582c  mov     [rsp+0F8h+var_A8], eax
0x140005830  xor     r8d, r8d; State
0x140005833  xor     edx, edx; Type
0x140005835  lea     rcx, [rsp+0F8h+Event]; Event
0x14000583a  call    cs:__imp_KeInitializeEvent
0x140005841  nop     dword ptr [rax+rax+00h]
0x140005846  mov     edx, ebx; Size
0x140005848  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x14000584d  call    cs:__imp_RpcAsyncInitializeHandle
0x140005854  nop     dword ptr [rax+rax+00h]
0x140005859  mov     ebx, eax
0x14000585b  mov     [rsp+0F8h+var_B8], eax
0x14000585f  test    eax, eax
0x140005861  jz      short loc_1400058A4
0x140005863  lea     rax, WPP_GLOBAL_Control
0x14000586a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005871  cmp     rcx, rax
0x140005874  jz      loc_1400059BA
0x14000587a  test    dword ptr [rcx+2Ch], 100000h
0x140005881  jz      loc_1400059BA
0x140005887  mov     edx, 0Dh
0x14000588c  mov     r9d, ebx
0x14000588f  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005896  mov     rcx, [rcx+18h]
0x14000589a  call    WPP_SF_D
0x14000589f  jmp     loc_1400059BA
0x1400058a4  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x1400058af  lea     rax, [rsp+0F8h+Event]
0x1400058b4  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x1400058bc  mov     [rsp+0F8h+var_C0], r15
0x1400058c1  mov     [rsp+0F8h+var_C8], r14
0x1400058c6  mov     [rsp+0F8h+var_D0], rsi
0x1400058cb  mov     rax, [rsp+0F8h+Binding]
0x1400058d0  mov     [rsp+0F8h+Timeout], rax
0x1400058d5  lea     r9, [rsp+0F8h+pAsync]
0x1400058da  xor     r8d, r8d; pReturnValue
0x1400058dd  lea     edx, [r8+2]; nProcNum
0x1400058e1  lea     rcx, pProxyInfo; pProxyInfo
0x1400058e8  call    cs:__imp_Ndr64AsyncClientCall
0x1400058ef  nop     dword ptr [rax+rax+00h]
0x1400058f4  jmp     short loc_140005931
0x1400058f6  mov     ebx, eax
0x1400058f8  mov     [rsp+0F8h+var_B8], eax
0x1400058fc  lea     rax, WPP_GLOBAL_Control
0x140005903  mov     rcx, cs:WPP_GLOBAL_Control
0x14000590a  cmp     rcx, rax
0x14000590d  jz      short loc_140005931
0x14000590f  test    dword ptr [rcx+2Ch], 100000h
0x140005916  jz      short loc_140005931
0x140005918  mov     edx, 0Eh
0x14000591d  mov     r9d, ebx
0x140005920  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005927  mov     rcx, [rcx+18h]
0x14000592b  call    WPP_SF_D
0x140005930  nop
0x140005931  test    ebx, ebx
0x140005933  jnz     loc_1400059BA
0x140005939  mov     [rsp+0F8h+Timeout], 0; Timeout
0x140005942  xor     r9d, r9d; Alertable
0x140005945  xor     r8d, r8d; WaitMode
0x140005948  xor     edx, edx; WaitReason
0x14000594a  lea     rcx, [rsp+0F8h+Event]; Object
0x14000594f  call    cs:__imp_KeWaitForSingleObject
0x140005956  nop     dword ptr [rax+rax+00h]
0x14000595b  xor     edx, edx; Reply
0x14000595d  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x140005962  call    cs:__imp_RpcAsyncCompleteCall
0x140005969  nop     dword ptr [rax+rax+00h]
0x14000596e  mov     ebx, eax
0x140005970  lea     rax, WPP_GLOBAL_Control
0x140005977  mov     rcx, cs:WPP_GLOBAL_Control
0x14000597e  cmp     rcx, rax
0x140005981  jz      short loc_1400059AC
0x140005983  test    dword ptr [rcx+2Ch], 400000h
0x14000598a  jz      short loc_1400059AC
0x14000598c  mov     edx, 0Fh
0x140005991  mov     dword ptr [rsp+0F8h+Timeout], 0
0x140005999  mov     r9d, ebx
0x14000599c  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x1400059a3  mov     rcx, [rcx+18h]
0x1400059a7  call    WPP_SF_dd
0x1400059ac  mov     eax, 0C0000022h
0x1400059b1  test    ebx, ebx
0x1400059b3  cmovnz  ebx, eax
0x1400059b6  mov     [rsp+0F8h+var_B8], ebx
0x1400059ba  nop
0x1400059bb  mov     rcx, [rsp+0F8h+Binding]; Binding
0x1400059c0  call    cs:__imp_RpcBindingUnbind
0x1400059c7  nop     dword ptr [rax+rax+00h]
0x1400059cc  mov     [rsp+0F8h+var_A8], 1
0x1400059d4  lea     rcx, [rsp+0F8h+Binding]; Binding
0x1400059d9  call    cs:__imp_RpcBindingFree
0x1400059e0  nop     dword ptr [rax+rax+00h]
0x1400059e5  mov     [rsp+0F8h+Binding], 0
0x1400059ee  jmp     short loc_140005A40
0x1400059f0  lea     rdx, WPP_GLOBAL_Control
0x1400059f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059fe  cmp     rcx, rdx
0x140005a01  jz      short loc_140005A24
0x140005a03  test    dword ptr [rcx+2Ch], 100000h
0x140005a0a  jz      short loc_140005A24
0x140005a0c  mov     edx, 10h
0x140005a11  mov     r9d, eax
0x140005a14  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005a1b  mov     rcx, [rcx+18h]
0x140005a1f  call    WPP_SF_D
0x140005a24  cmp     [rsp+0F8h+var_A8], 0
0x140005a29  jnz     short loc_140005A3C
0x140005a2b  lea     rcx, [rsp+0F8h+Binding]; Binding
0x140005a30  call    cs:__imp_RpcBindingFree
0x140005a37  nop     dword ptr [rax+rax+00h]
0x140005a3c  mov     ebx, [rsp+0F8h+var_B8]
0x140005a40  mov     eax, ebx
0x140005a42  mov     rcx, [rsp+0F8h+var_28]
0x140005a4a  xor     rcx, rsp; StackCookie
0x140005a4d  call    __security_check_cookie
0x140005a52  mov     rbx, [rsp+0F8h+arg_18]
0x140005a5a  add     rsp, 0E0h
0x140005a61  pop     r15
0x140005a63  pop     r14
0x140005a65  pop     rsi
0x140005a66  retn
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
