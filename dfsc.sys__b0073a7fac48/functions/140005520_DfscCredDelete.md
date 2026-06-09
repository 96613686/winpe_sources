# DfscCredDelete

- ea: `0x140005520`
- end: `0x1400057be`
- name: `DfscCredDelete`
- size: `670`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014810`

## callees

- `0x140001bd8`
- `0x1400025a0`
- `0x1400027f8`
- `0x140005520`
- `0x140005f70`
- `0x140006380`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400056a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400056a4`
- `ntoskrnl!KeInitializeEvent` at `0x140005594`
- `ntoskrnl!KeInitializeEvent` at `0x140005594`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400055a7`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400055a7`
- `msrpc!RpcAsyncCompleteCall` at `0x1400056b7`
- `msrpc!RpcAsyncCompleteCall` at `0x1400056b7`
- `msrpc!RpcBindingFree` at `0x14000572e`
- `msrpc!RpcBindingFree` at `0x140005785`
- `msrpc!RpcBindingFree` at `0x14000572e`
- `msrpc!RpcBindingFree` at `0x140005785`
- `msrpc!RpcBindingUnbind` at `0x140005715`
- `msrpc!RpcBindingUnbind` at `0x140005715`
- `msrpc!Ndr64AsyncClientCall` at `0x14000563d`
- `msrpc!Ndr64AsyncClientCall` at `0x14000563d`

## pseudocode

```c
__int64 __fastcall DfscCredDelete(__int64 a1, int a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-A0h] BYREF
  int v7; // [rsp+50h] [rbp-98h]
  struct _KEVENT Event; // [rsp+58h] [rbp-90h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-78h] BYREF

  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  result = DfscRpcConnect(&Binding);
  if ( !(_DWORD)result )
  {
    v7 = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v5 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids, v5);
      }
    }
    else
    {
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.Event = &Event;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, &pAsync, Binding, a1, a2);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v5 = RpcAsyncCompleteCall(&pAsync, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids);
      }
      if ( v5 )
        v5 = -1073741790;
    }
    RpcBindingUnbind(Binding);
    v7 = 1;
    RpcBindingFree(&Binding);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140005520  mov     r11, rsp
0x140005523  mov     [r11+18h], rbx
0x140005527  mov     [r11+20h], rsi
0x14000552b  push    r14
0x14000552d  sub     rsp, 0E0h
0x140005534  mov     rax, cs:__security_cookie
0x14000553b  xor     rax, rsp
0x14000553e  mov     [rsp+0E8h+var_18], rax
0x140005546  mov     r14d, edx
0x140005549  mov     rsi, rcx
0x14000554c  xorps   xmm0, xmm0
0x14000554f  xor     eax, eax
0x140005551  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x140005556  mov     [r11-80h], rax
0x14000555a  lea     ebx, [rax+58h]
0x14000555d  mov     r8d, ebx; Size
0x140005560  xor     edx, edx; Val
0x140005562  lea     rcx, [r11-78h]; void *
0x140005566  call    memset
0x14000556b  mov     [rsp+0E8h+Binding], 0
0x140005574  lea     rcx, [rsp+0E8h+Binding]
0x140005579  call    DfscRpcConnect
0x14000557e  test    eax, eax
0x140005580  jnz     loc_140005797
0x140005586  mov     [rsp+0E8h+var_98], eax
0x14000558a  xor     r8d, r8d; State
0x14000558d  xor     edx, edx; Type
0x14000558f  lea     rcx, [rsp+0E8h+Event]; Event
0x140005594  call    cs:__imp_KeInitializeEvent
0x14000559b  nop     dword ptr [rax+rax+00h]
0x1400055a0  mov     edx, ebx; Size
0x1400055a2  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1400055a7  call    cs:__imp_RpcAsyncInitializeHandle
0x1400055ae  nop     dword ptr [rax+rax+00h]
0x1400055b3  mov     ebx, eax
0x1400055b5  mov     [rsp+0E8h+var_A8], eax
0x1400055b9  test    eax, eax
0x1400055bb  jz      short loc_1400055FE
0x1400055bd  lea     rax, WPP_GLOBAL_Control
0x1400055c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055cb  cmp     rcx, rax
0x1400055ce  jz      loc_14000570F
0x1400055d4  test    dword ptr [rcx+2Ch], 100000h
0x1400055db  jz      loc_14000570F
0x1400055e1  mov     edx, 11h
0x1400055e6  mov     r9d, ebx
0x1400055e9  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x1400055f0  mov     rcx, [rcx+18h]
0x1400055f4  call    WPP_SF_D
0x1400055f9  jmp     loc_14000570F
0x1400055fe  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x140005609  lea     rax, [rsp+0E8h+Event]
0x14000560e  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x140005616  mov     [rsp+0E8h+var_B8], r14d
0x14000561b  mov     [rsp+0E8h+var_C0], rsi
0x140005620  mov     rax, [rsp+0E8h+Binding]
0x140005625  mov     [rsp+0E8h+Timeout], rax
0x14000562a  lea     r9, [rsp+0E8h+pAsync]
0x14000562f  xor     r8d, r8d; pReturnValue
0x140005632  lea     edx, [r8+3]; nProcNum
0x140005636  lea     rcx, pProxyInfo; pProxyInfo
0x14000563d  call    cs:__imp_Ndr64AsyncClientCall
0x140005644  nop     dword ptr [rax+rax+00h]
0x140005649  jmp     short loc_140005686
0x14000564b  mov     ebx, eax
0x14000564d  mov     [rsp+0E8h+var_A8], eax
0x140005651  lea     rax, WPP_GLOBAL_Control
0x140005658  mov     rcx, cs:WPP_GLOBAL_Control
0x14000565f  cmp     rcx, rax
0x140005662  jz      short loc_140005686
0x140005664  test    dword ptr [rcx+2Ch], 100000h
0x14000566b  jz      short loc_140005686
0x14000566d  mov     edx, 12h
0x140005672  mov     r9d, ebx
0x140005675  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x14000567c  mov     rcx, [rcx+18h]
0x140005680  call    WPP_SF_D
0x140005685  nop
0x140005686  test    ebx, ebx
0x140005688  jnz     loc_14000570F
0x14000568e  mov     [rsp+0E8h+Timeout], 0; Timeout
0x140005697  xor     r9d, r9d; Alertable
0x14000569a  xor     r8d, r8d; WaitMode
0x14000569d  xor     edx, edx; WaitReason
0x14000569f  lea     rcx, [rsp+0E8h+Event]; Object
0x1400056a4  call    cs:__imp_KeWaitForSingleObject
0x1400056ab  nop     dword ptr [rax+rax+00h]
0x1400056b0  xor     edx, edx; Reply
0x1400056b2  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1400056b7  call    cs:__imp_RpcAsyncCompleteCall
0x1400056be  nop     dword ptr [rax+rax+00h]
0x1400056c3  mov     ebx, eax
0x1400056c5  lea     rax, WPP_GLOBAL_Control
0x1400056cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400056d3  cmp     rcx, rax
0x1400056d6  jz      short loc_140005701
0x1400056d8  test    dword ptr [rcx+2Ch], 400000h
0x1400056df  jz      short loc_140005701
0x1400056e1  mov     edx, 13h
0x1400056e6  mov     dword ptr [rsp+0E8h+Timeout], 0
0x1400056ee  mov     r9d, ebx
0x1400056f1  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x1400056f8  mov     rcx, [rcx+18h]
0x1400056fc  call    WPP_SF_dd
0x140005701  mov     eax, 0C0000022h
0x140005706  test    ebx, ebx
0x140005708  cmovnz  ebx, eax
0x14000570b  mov     [rsp+0E8h+var_A8], ebx
0x14000570f  nop
0x140005710  mov     rcx, [rsp+0E8h+Binding]; Binding
0x140005715  call    cs:__imp_RpcBindingUnbind
0x14000571c  nop     dword ptr [rax+rax+00h]
0x140005721  mov     [rsp+0E8h+var_98], 1
0x140005729  lea     rcx, [rsp+0E8h+Binding]; Binding
0x14000572e  call    cs:__imp_RpcBindingFree
0x140005735  nop     dword ptr [rax+rax+00h]
0x14000573a  mov     [rsp+0E8h+Binding], 0
0x140005743  jmp     short loc_140005795
0x140005745  lea     rdx, WPP_GLOBAL_Control
0x14000574c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005753  cmp     rcx, rdx
0x140005756  jz      short loc_140005779
0x140005758  test    dword ptr [rcx+2Ch], 100000h
0x14000575f  jz      short loc_140005779
0x140005761  mov     edx, 14h
0x140005766  mov     r9d, eax
0x140005769  lea     r8, WPP_647e9e2fa1ea3758e828fdefd6c76ce6_Traceguids
0x140005770  mov     rcx, [rcx+18h]
0x140005774  call    WPP_SF_D
0x140005779  cmp     [rsp+0E8h+var_98], 0
0x14000577e  jnz     short loc_140005791
0x140005780  lea     rcx, [rsp+0E8h+Binding]; Binding
0x140005785  call    cs:__imp_RpcBindingFree
0x14000578c  nop     dword ptr [rax+rax+00h]
0x140005791  mov     ebx, [rsp+0E8h+var_A8]
0x140005795  mov     eax, ebx
0x140005797  mov     rcx, [rsp+0E8h+var_18]
0x14000579f  xor     rcx, rsp; StackCookie
0x1400057a2  call    __security_check_cookie
0x1400057a7  lea     r11, [rsp+0E8h+var_8]
0x1400057af  mov     rbx, [r11+20h]
0x1400057b3  mov     rsi, [r11+28h]
0x1400057b7  mov     rsp, r11
0x1400057ba  pop     r14
0x1400057bc  retn
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
