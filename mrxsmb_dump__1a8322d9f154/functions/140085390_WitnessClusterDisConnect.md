# WitnessClusterDisConnect

- ea: `0x140085390`
- end: `0x14008557b`
- name: `WitnessClusterDisConnect`
- size: `491`
- prototype: `void __fastcall(_BYTE *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14004cb34`
- `0x140059dc0`
- `0x14005a200`
- `0x140085390`
- `0x140085584`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140085469`
- `ntoskrnl!KeInitializeEvent` at `0x140085469`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400854de`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008551c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400854de`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008551c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140085545`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140085545`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085402`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085402`
- `msrpc!RpcAsyncCancelCall` at `0x1400854f6`
- `msrpc!RpcAsyncCancelCall` at `0x1400854f6`
- `msrpc!RpcAsyncCompleteCall` at `0x140085532`
- `msrpc!RpcAsyncCompleteCall` at `0x140085532`
- `msrpc!RpcAsyncInitializeHandle` at `0x140085434`
- `msrpc!RpcAsyncInitializeHandle` at `0x140085434`
- `msrpc!I_RpcExceptionFilter` at `0x140095cff`
- `msrpc!I_RpcExceptionFilter` at `0x140095cff`

## pseudocode

```c
void __fastcall WitnessClusterDisConnect(_BYTE *Context)
{
  int v2; // edx
  int Reply; // [rsp+30h] [rbp-B8h] BYREF
  LARGE_INTEGER Timeout; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE *v5; // [rsp+40h] [rbp-A8h]
  struct _KEVENT Event; // [rsp+48h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v8[24]; // [rsp+C0h] [rbp-28h] BYREF

  v5 = Context;
  Reply = 0;
  memset(&pAsync, 0, sizeof(pAsync));
  Timeout.QuadPart = 0;
  memset(&Event, 0, sizeof(Event));
  memset(v8, 0, 22);
  if ( ExAcquireRundownProtection(&WitnessRundownLock) )
  {
    if ( WitnessRpcBindingHandle )
    {
      Timeout.QuadPart = -300000000;
      if ( !RpcAsyncInitializeHandle(&pAsync, 0x58u) )
      {
        memset(v8, 0, sizeof(v8));
        KeInitializeEvent(&Event, NotificationEvent, 0);
        pAsync.NotificationType = RpcNotificationTypeEvent;
        pAsync.u.Event = &Event;
        ClusterDisConnectUpcall(
          (unsigned int)&pAsync,
          v2,
          (_DWORD)Context,
          (_DWORD)Context + 16,
          (__int64)v8,
          (Context[76] != 0) + 1);
        if ( KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout) && !RpcAsyncCancelCall(&pAsync, 1) )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        RpcAsyncCompleteCall(&pAsync, &Reply);
      }
    }
    ExReleaseRundownProtection(&WitnessRundownLock);
  }
  WitnessFreeClusterConnectContext(Context);
}

```

## disassembly

```asm
0x140085390  mov     [rsp+arg_8], rbx
0x140085395  push    rdi
0x140085396  sub     rsp, 0E0h
0x14008539d  mov     rax, cs:__security_cookie
0x1400853a4  xor     rax, rsp
0x1400853a7  mov     [rsp+0E8h+var_10], rax
0x1400853af  mov     rbx, rcx
0x1400853b2  mov     [rsp+0E8h+var_A8], rcx
0x1400853b7  mov     [rsp+0E8h+Reply], 0
0x1400853bf  mov     edi, 58h ; 'X'
0x1400853c4  mov     r8d, edi; Size
0x1400853c7  xor     edx, edx; Val
0x1400853c9  lea     rcx, [rsp+0E8h+pAsync]; void *
0x1400853ce  call    memset
0x1400853d3  mov     qword ptr [rsp+0E8h+var_B0], 0
0x1400853dc  xorps   xmm0, xmm0
0x1400853df  xor     eax, eax
0x1400853e1  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x1400853e6  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x1400853eb  movups  [rsp+0E8h+var_28], xmm0
0x1400853f3  mov     qword ptr [rsp+0E8h+var_28+0Eh], rax
0x1400853fb  lea     rcx, WitnessRundownLock; RunRef
0x140085402  call    cs:__imp_ExAcquireRundownProtection
0x140085409  nop     dword ptr [rax+rax+00h]
0x14008540e  test    al, al
0x140085410  jz      loc_140085551
0x140085416  cmp     cs:WitnessRpcBindingHandle, 0
0x14008541e  jz      loc_14008553E
0x140085424  mov     qword ptr [rsp+0E8h+var_B0], 0FFFFFFFFEE1E5D00h
0x14008542d  mov     edx, edi; Size
0x14008542f  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x140085434  call    cs:__imp_RpcAsyncInitializeHandle
0x14008543b  nop     dword ptr [rax+rax+00h]
0x140085440  mov     edi, eax
0x140085442  test    eax, eax
0x140085444  jnz     loc_14008553E
0x14008544a  xorps   xmm0, xmm0
0x14008544d  xor     eax, eax
0x14008544f  movups  [rsp+0E8h+var_28], xmm0
0x140085457  mov     [rsp+0E8h+var_18], rax
0x14008545f  xor     r8d, r8d; State
0x140085462  xor     edx, edx; Type
0x140085464  lea     rcx, [rsp+0E8h+Event]; Event
0x140085469  call    cs:__imp_KeInitializeEvent
0x140085470  nop     dword ptr [rax+rax+00h]
0x140085475  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x140085480  lea     rax, [rsp+0E8h+Event]
0x140085485  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x14008548d  mov     al, [rbx+4Ch]
0x140085490  neg     al
0x140085492  sbb     ecx, ecx
0x140085494  neg     ecx
0x140085496  inc     ecx
0x140085498  lea     r9, [rbx+10h]
0x14008549c  mov     [rsp+0E8h+var_C0], ecx
0x1400854a0  lea     rax, [rsp+0E8h+var_28]
0x1400854a8  mov     [rsp+0E8h+Timeout], rax
0x1400854ad  mov     r8, rbx
0x1400854b0  lea     rcx, [rsp+0E8h+pAsync]
0x1400854b5  call    ClusterDisConnectUpcall
0x1400854ba  jmp     short loc_1400854C3
0x1400854bc  mov     edi, eax
0x1400854be  mov     rbx, [rsp+0E8h+var_A8]
0x1400854c3  test    edi, edi
0x1400854c5  jnz     short loc_14008553E
0x1400854c7  lea     rax, [rsp+0E8h+var_B0]
0x1400854cc  mov     [rsp+0E8h+Timeout], rax; Timeout
0x1400854d1  xor     r9d, r9d; Alertable
0x1400854d4  xor     r8d, r8d; WaitMode
0x1400854d7  xor     edx, edx; WaitReason
0x1400854d9  lea     rcx, [rsp+0E8h+Event]; Object
0x1400854de  call    cs:__imp_KeWaitForSingleObject
0x1400854e5  nop     dword ptr [rax+rax+00h]
0x1400854ea  test    eax, eax
0x1400854ec  jz      short loc_140085528
0x1400854ee  lea     edx, [rdi+1]; fAbort
0x1400854f1  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1400854f6  call    cs:__imp_RpcAsyncCancelCall
0x1400854fd  nop     dword ptr [rax+rax+00h]
0x140085502  test    eax, eax
0x140085504  jnz     short loc_140085528
0x140085506  mov     [rsp+0E8h+Timeout], 0; Timeout
0x14008550f  xor     r9d, r9d; Alertable
0x140085512  xor     r8d, r8d; WaitMode
0x140085515  xor     edx, edx; WaitReason
0x140085517  lea     rcx, [rsp+0E8h+Event]; Object
0x14008551c  call    cs:__imp_KeWaitForSingleObject
0x140085523  nop     dword ptr [rax+rax+00h]
0x140085528  lea     rdx, [rsp+0E8h+Reply]; Reply
0x14008552d  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x140085532  call    cs:__imp_RpcAsyncCompleteCall
0x140085539  nop     dword ptr [rax+rax+00h]
0x14008553e  lea     rcx, WitnessRundownLock; RunRef
0x140085545  call    cs:__imp_ExReleaseRundownProtection
0x14008554c  nop     dword ptr [rax+rax+00h]
0x140085551  mov     rcx, rbx
0x140085554  call    WitnessFreeClusterConnectContext
0x140085559  mov     rcx, [rsp+0E8h+var_10]
0x140085561  xor     rcx, rsp; StackCookie
0x140085564  call    __security_check_cookie
0x140085569  mov     rbx, [rsp+0E8h+arg_8]
0x140085571  add     rsp, 0E0h
0x140085578  pop     rdi
0x140085579  retn
0x140095cf1  push    rbp
0x140095cf3  sub     rsp, 30h
0x140095cf7  mov     rbp, rdx
0x140095cfa  mov     rcx, [rcx]
0x140095cfd  mov     ecx, [rcx]; ExceptionCode
0x140095cff  call    cs:__imp_I_RpcExceptionFilter
0x140095d06  nop     dword ptr [rax+rax+00h]
0x140095d0b  nop
0x140095d0c  add     rsp, 30h
0x140095d10  pop     rbp
0x140095d11  retn
```
