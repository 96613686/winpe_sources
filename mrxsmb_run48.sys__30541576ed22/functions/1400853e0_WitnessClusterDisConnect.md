# WitnessClusterDisConnect

- ea: `0x1400853e0`
- end: `0x1400855cb`
- name: `WitnessClusterDisConnect`
- size: `491`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14004cb34`
- `0x140059dc0`
- `0x14005a200`
- `0x1400853e0`
- `0x1400855d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400854b9`
- `ntoskrnl!KeInitializeEvent` at `0x1400854b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008552e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008556c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008552e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008556c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140085595`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140085595`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085452`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085452`
- `msrpc!RpcAsyncCancelCall` at `0x140085546`
- `msrpc!RpcAsyncCancelCall` at `0x140085546`
- `msrpc!RpcAsyncCompleteCall` at `0x140085582`
- `msrpc!RpcAsyncCompleteCall` at `0x140085582`
- `msrpc!RpcAsyncInitializeHandle` at `0x140085484`
- `msrpc!RpcAsyncInitializeHandle` at `0x140085484`
- `msrpc!I_RpcExceptionFilter` at `0x140095d4f`
- `msrpc!I_RpcExceptionFilter` at `0x140095d4f`

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
0x1400853e0  mov     [rsp+arg_8], rbx
0x1400853e5  push    rdi
0x1400853e6  sub     rsp, 0E0h
0x1400853ed  mov     rax, cs:__security_cookie
0x1400853f4  xor     rax, rsp
0x1400853f7  mov     [rsp+0E8h+var_10], rax
0x1400853ff  mov     rbx, rcx
0x140085402  mov     [rsp+0E8h+var_A8], rcx
0x140085407  mov     [rsp+0E8h+Reply], 0
0x14008540f  mov     edi, 58h ; 'X'
0x140085414  mov     r8d, edi; Size
0x140085417  xor     edx, edx; Val
0x140085419  lea     rcx, [rsp+0E8h+pAsync]; void *
0x14008541e  call    memset
0x140085423  mov     qword ptr [rsp+0E8h+var_B0], 0
0x14008542c  xorps   xmm0, xmm0
0x14008542f  xor     eax, eax
0x140085431  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x140085436  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x14008543b  movups  [rsp+0E8h+var_28], xmm0
0x140085443  mov     qword ptr [rsp+0E8h+var_28+0Eh], rax
0x14008544b  lea     rcx, WitnessRundownLock; RunRef
0x140085452  call    cs:__imp_ExAcquireRundownProtection
0x140085459  nop     dword ptr [rax+rax+00h]
0x14008545e  test    al, al
0x140085460  jz      loc_1400855A1
0x140085466  cmp     cs:WitnessRpcBindingHandle, 0
0x14008546e  jz      loc_14008558E
0x140085474  mov     qword ptr [rsp+0E8h+var_B0], 0FFFFFFFFEE1E5D00h
0x14008547d  mov     edx, edi; Size
0x14008547f  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x140085484  call    cs:__imp_RpcAsyncInitializeHandle
0x14008548b  nop     dword ptr [rax+rax+00h]
0x140085490  mov     edi, eax
0x140085492  test    eax, eax
0x140085494  jnz     loc_14008558E
0x14008549a  xorps   xmm0, xmm0
0x14008549d  xor     eax, eax
0x14008549f  movups  [rsp+0E8h+var_28], xmm0
0x1400854a7  mov     [rsp+0E8h+var_18], rax
0x1400854af  xor     r8d, r8d; State
0x1400854b2  xor     edx, edx; Type
0x1400854b4  lea     rcx, [rsp+0E8h+Event]; Event
0x1400854b9  call    cs:__imp_KeInitializeEvent
0x1400854c0  nop     dword ptr [rax+rax+00h]
0x1400854c5  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x1400854d0  lea     rax, [rsp+0E8h+Event]
0x1400854d5  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x1400854dd  mov     al, [rbx+4Ch]
0x1400854e0  neg     al
0x1400854e2  sbb     ecx, ecx
0x1400854e4  neg     ecx
0x1400854e6  inc     ecx
0x1400854e8  lea     r9, [rbx+10h]
0x1400854ec  mov     [rsp+0E8h+var_C0], ecx
0x1400854f0  lea     rax, [rsp+0E8h+var_28]
0x1400854f8  mov     [rsp+0E8h+Timeout], rax
0x1400854fd  mov     r8, rbx
0x140085500  lea     rcx, [rsp+0E8h+pAsync]
0x140085505  call    ClusterDisConnectUpcall
0x14008550a  jmp     short loc_140085513
0x14008550c  mov     edi, eax
0x14008550e  mov     rbx, [rsp+0E8h+var_A8]
0x140085513  test    edi, edi
0x140085515  jnz     short loc_14008558E
0x140085517  lea     rax, [rsp+0E8h+var_B0]
0x14008551c  mov     [rsp+0E8h+Timeout], rax; Timeout
0x140085521  xor     r9d, r9d; Alertable
0x140085524  xor     r8d, r8d; WaitMode
0x140085527  xor     edx, edx; WaitReason
0x140085529  lea     rcx, [rsp+0E8h+Event]; Object
0x14008552e  call    cs:__imp_KeWaitForSingleObject
0x140085535  nop     dword ptr [rax+rax+00h]
0x14008553a  test    eax, eax
0x14008553c  jz      short loc_140085578
0x14008553e  lea     edx, [rdi+1]; fAbort
0x140085541  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x140085546  call    cs:__imp_RpcAsyncCancelCall
0x14008554d  nop     dword ptr [rax+rax+00h]
0x140085552  test    eax, eax
0x140085554  jnz     short loc_140085578
0x140085556  mov     [rsp+0E8h+Timeout], 0; Timeout
0x14008555f  xor     r9d, r9d; Alertable
0x140085562  xor     r8d, r8d; WaitMode
0x140085565  xor     edx, edx; WaitReason
0x140085567  lea     rcx, [rsp+0E8h+Event]; Object
0x14008556c  call    cs:__imp_KeWaitForSingleObject
0x140085573  nop     dword ptr [rax+rax+00h]
0x140085578  lea     rdx, [rsp+0E8h+Reply]; Reply
0x14008557d  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x140085582  call    cs:__imp_RpcAsyncCompleteCall
0x140085589  nop     dword ptr [rax+rax+00h]
0x14008558e  lea     rcx, WitnessRundownLock; RunRef
0x140085595  call    cs:__imp_ExReleaseRundownProtection
0x14008559c  nop     dword ptr [rax+rax+00h]
0x1400855a1  mov     rcx, rbx
0x1400855a4  call    WitnessFreeClusterConnectContext
0x1400855a9  mov     rcx, [rsp+0E8h+var_10]
0x1400855b1  xor     rcx, rsp; StackCookie
0x1400855b4  call    __security_check_cookie
0x1400855b9  mov     rbx, [rsp+0E8h+arg_8]
0x1400855c1  add     rsp, 0E0h
0x1400855c8  pop     rdi
0x1400855c9  retn
0x140095d41  push    rbp
0x140095d43  sub     rsp, 30h
0x140095d47  mov     rbp, rdx
0x140095d4a  mov     rcx, [rcx]
0x140095d4d  mov     ecx, [rcx]; ExceptionCode
0x140095d4f  call    cs:__imp_I_RpcExceptionFilter
0x140095d56  nop     dword ptr [rax+rax+00h]
0x140095d5b  nop
0x140095d5c  add     rsp, 30h
0x140095d60  pop     rbp
0x140095d61  retn
```
