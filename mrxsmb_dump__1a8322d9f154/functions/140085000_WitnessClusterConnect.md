# WitnessClusterConnect

- ea: `0x140085000`
- end: `0x140085385`
- name: `WitnessClusterConnect`
- size: `901`
- prototype: `void __fastcall(char *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14003838c`
- `0x140039fa8`
- `0x14004cac0`
- `0x140059dc0`
- `0x14005a200`
- `0x140085000`
- `0x140085584`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400851d7`
- `ntoskrnl!KeInitializeEvent` at `0x1400851d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400852a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140085323`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400852a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140085323`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008534f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008534f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085078`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140085078`
- `msrpc!RpcAsyncCancelCall` at `0x1400852fd`
- `msrpc!RpcAsyncCancelCall` at `0x1400852fd`
- `msrpc!RpcAsyncCompleteCall` at `0x14008533c`
- `msrpc!RpcAsyncCompleteCall` at `0x14008533c`
- `msrpc!RpcAsyncInitializeHandle` at `0x14008512f`
- `msrpc!RpcAsyncInitializeHandle` at `0x14008512f`
- `msrpc!I_RpcExceptionFilter` at `0x140095cd7`
- `msrpc!I_RpcExceptionFilter` at `0x140095cd7`

## pseudocode

```c
void __fastcall WitnessClusterConnect(char *Context)
{
  unsigned int v2; // edi
  int v3; // ecx
  int v4; // edx
  unsigned int v5; // eax
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  LARGE_INTEGER Timeout; // [rsp+48h] [rbp-D0h] BYREF
  char *v8; // [rsp+50h] [rbp-C8h]
  struct _KEVENT Event; // [rsp+58h] [rbp-C0h] BYREF
  __int128 v10; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+80h] [rbp-98h]
  _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v13[24]; // [rsp+F0h] [rbp-28h] BYREF

  v8 = Context;
  Reply = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  Timeout.QuadPart = 0;
  memset(v13, 0, 22);
  if ( ExAcquireRundownProtection(&WitnessRundownLock) )
  {
    if ( WitnessRpcBindingHandle )
    {
      Timeout.QuadPart = -300000000;
      v2 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids, v2);
        }
      }
      else
      {
        memset(v13, 0, sizeof(v13));
        *(_WORD *)v13 = *((_WORD *)Context + 24);
        if ( *(_WORD *)v13 == 2 )
          *(_DWORD *)&v13[4] = *((_DWORD *)Context + 13);
        else
          *(_OWORD *)&v13[8] = *(_OWORD *)(Context + 56);
        KeInitializeEvent(&Event, NotificationEvent, 0);
        pAsync.NotificationType = RpcNotificationTypeEvent;
        pAsync.u.Event = &Event;
        v11 = *((_OWORD *)Context + 2);
        v3 = (Context[76] != 0) + 1;
        v10 = v11;
        ClusterConnectUpcall(
          (unsigned int)&pAsync,
          v4,
          (_DWORD)Context,
          (_DWORD)Context + 16,
          (__int64)v13,
          (__int64)&v10,
          v3);
        v5 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids, v5);
          }
          if ( !RpcAsyncCancelCall(&pAsync, 1) )
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        }
        RpcAsyncCompleteCall(&pAsync, &Reply);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids);
    }
    ExReleaseRundownProtection(&WitnessRundownLock);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids);
  }
  WitnessFreeClusterConnectContext(Context);
}

```

## disassembly

```asm
0x140085000  mov     [rsp+arg_8], rbx
0x140085005  push    rdi
0x140085006  sub     rsp, 110h
0x14008500d  mov     rax, cs:__security_cookie
0x140085014  xor     rax, rsp
0x140085017  mov     [rsp+118h+var_10], rax
0x14008501f  mov     rbx, rcx
0x140085022  mov     [rsp+118h+var_C8], rcx
0x140085027  mov     [rsp+118h+Reply], 0
0x14008502f  xorps   xmm0, xmm0
0x140085032  xor     eax, eax
0x140085034  movups  xmmword ptr [rsp+118h+Event.Header], xmm0
0x140085039  mov     [rsp+118h+Event.Header.WaitListHead.Blink], rax
0x14008503e  lea     edi, [rax+58h]
0x140085041  mov     r8d, edi; Size
0x140085044  xor     edx, edx; Val
0x140085046  lea     rcx, [rsp+118h+pAsync]; void *
0x14008504e  call    memset
0x140085053  mov     qword ptr [rsp+118h+var_D0], 0
0x14008505c  xor     eax, eax
0x14008505e  xorps   xmm0, xmm0
0x140085061  movups  [rsp+118h+var_28], xmm0
0x140085069  mov     qword ptr [rsp+118h+var_28+0Eh], rax
0x140085071  lea     rcx, WitnessRundownLock; RunRef
0x140085078  call    cs:__imp_ExAcquireRundownProtection
0x14008507f  nop     dword ptr [rax+rax+00h]
0x140085084  test    al, al
0x140085086  jnz     short loc_1400850CC
0x140085088  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008508f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085096  cmp     rcx, rax
0x140085099  jz      loc_14008535B
0x14008509f  mov     eax, [rcx+2Ch]
0x1400850a2  test    al, 1
0x1400850a4  jz      loc_14008535B
0x1400850aa  cmp     byte ptr [rcx+29h], 1
0x1400850ae  jb      loc_14008535B
0x1400850b4  lea     edx, [rdi-4Eh]
0x1400850b7  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x1400850be  mov     rcx, [rcx+18h]
0x1400850c2  call    WPP_SF_
0x1400850c7  jmp     loc_14008535B
0x1400850cc  cmp     cs:WitnessRpcBindingHandle, 0
0x1400850d4  jnz     short loc_14008511C
0x1400850d6  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400850dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400850e4  cmp     rcx, rax
0x1400850e7  jz      loc_140085348
0x1400850ed  mov     eax, [rcx+2Ch]
0x1400850f0  test    al, 1
0x1400850f2  jz      loc_140085348
0x1400850f8  cmp     byte ptr [rcx+29h], 1
0x1400850fc  jb      loc_140085348
0x140085102  mov     edx, 0Bh
0x140085107  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x14008510e  mov     rcx, [rcx+18h]
0x140085112  call    WPP_SF_
0x140085117  jmp     loc_140085348
0x14008511c  mov     qword ptr [rsp+118h+var_D0], 0FFFFFFFFEE1E5D00h
0x140085125  mov     edx, edi; Size
0x140085127  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14008512f  call    cs:__imp_RpcAsyncInitializeHandle
0x140085136  nop     dword ptr [rax+rax+00h]
0x14008513b  mov     edi, eax
0x14008513d  test    eax, eax
0x14008513f  jz      short loc_14008518D
0x140085141  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140085148  mov     r10, cs:WPP_GLOBAL_Control
0x14008514f  cmp     r10, rax
0x140085152  jz      loc_140085348
0x140085158  mov     ecx, [r10+2Ch]
0x14008515c  test    cl, 1
0x14008515f  jz      loc_140085348
0x140085165  cmp     byte ptr [r10+29h], 1
0x14008516a  jb      loc_140085348
0x140085170  mov     edx, 0Ch
0x140085175  mov     rcx, [r10+18h]
0x140085179  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x140085180  mov     r9d, edi
0x140085183  call    WPP_SF_d
0x140085188  jmp     loc_140085348
0x14008518d  xorps   xmm0, xmm0
0x140085190  xor     eax, eax
0x140085192  movups  [rsp+118h+var_28], xmm0
0x14008519a  mov     [rsp+118h+var_18], rax
0x1400851a2  movzx   eax, word ptr [rbx+30h]
0x1400851a6  mov     word ptr [rsp+118h+var_28], ax
0x1400851ae  cmp     ax, 2
0x1400851b2  jnz     short loc_1400851C0
0x1400851b4  mov     eax, [rbx+34h]
0x1400851b7  mov     dword ptr [rsp+118h+var_28+4], eax
0x1400851be  jmp     short loc_1400851CD
0x1400851c0  movups  xmm0, xmmword ptr [rbx+38h]
0x1400851c4  movdqu  [rsp+118h+var_28+8], xmm0
0x1400851cd  xor     r8d, r8d; State
0x1400851d0  xor     edx, edx; Type
0x1400851d2  lea     rcx, [rsp+118h+Event]; Event
0x1400851d7  call    cs:__imp_KeInitializeEvent
0x1400851de  nop     dword ptr [rax+rax+00h]
0x1400851e3  mov     [rsp+118h+pAsync.NotificationType], 1
0x1400851ee  lea     rax, [rsp+118h+Event]
0x1400851f3  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1400851fb  movups  xmm0, xmmword ptr [rbx+20h]
0x1400851ff  movaps  [rsp+118h+var_98], xmm0
0x140085207  mov     al, [rbx+4Ch]
0x14008520a  neg     al
0x14008520c  sbb     ecx, ecx
0x14008520e  neg     ecx
0x140085210  inc     ecx
0x140085212  movdqa  [rsp+118h+var_A8], xmm0
0x140085218  lea     r9, [rbx+10h]
0x14008521c  mov     [rsp+118h+var_E8], ecx
0x140085220  lea     rax, [rsp+118h+var_A8]
0x140085225  mov     [rsp+118h+var_F0], rax
0x14008522a  lea     rax, [rsp+118h+var_28]
0x140085232  mov     [rsp+118h+Timeout], rax
0x140085237  mov     r8, rbx
0x14008523a  lea     rcx, [rsp+118h+pAsync]
0x140085242  call    ClusterConnectUpcall
0x140085247  jmp     short loc_140085250
0x140085249  mov     edi, eax
0x14008524b  mov     rbx, [rsp+118h+var_C8]
0x140085250  test    edi, edi
0x140085252  jz      short loc_14008528E
0x140085254  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008525b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085262  cmp     rcx, rax
0x140085265  jz      loc_140085348
0x14008526b  mov     eax, [rcx+2Ch]
0x14008526e  test    al, 1
0x140085270  jz      loc_140085348
0x140085276  cmp     byte ptr [rcx+29h], 1
0x14008527a  jb      loc_140085348
0x140085280  mov     edx, 0Dh
0x140085285  mov     rcx, [rcx+18h]
0x140085289  jmp     loc_140085179
0x14008528e  lea     rax, [rsp+118h+var_D0]
0x140085293  mov     [rsp+118h+Timeout], rax; Timeout
0x140085298  xor     r9d, r9d; Alertable
0x14008529b  xor     r8d, r8d; WaitMode
0x14008529e  xor     edx, edx; WaitReason
0x1400852a0  lea     rcx, [rsp+118h+Event]; Object
0x1400852a5  call    cs:__imp_KeWaitForSingleObject
0x1400852ac  nop     dword ptr [rax+rax+00h]
0x1400852b1  mov     r9d, eax
0x1400852b4  test    eax, eax
0x1400852b6  jz      short loc_14008532F
0x1400852b8  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400852bf  mov     r10, cs:WPP_GLOBAL_Control
0x1400852c6  cmp     r10, rax
0x1400852c9  jz      short loc_1400852F0
0x1400852cb  mov     ecx, [r10+2Ch]
0x1400852cf  test    cl, 1
0x1400852d2  jz      short loc_1400852F0
0x1400852d4  cmp     byte ptr [r10+29h], 1
0x1400852d9  jb      short loc_1400852F0
0x1400852db  mov     edx, 0Eh
0x1400852e0  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x1400852e7  mov     rcx, [r10+18h]
0x1400852eb  call    WPP_SF_d
0x1400852f0  mov     edx, 1; fAbort
0x1400852f5  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1400852fd  call    cs:__imp_RpcAsyncCancelCall
0x140085304  nop     dword ptr [rax+rax+00h]
0x140085309  test    eax, eax
0x14008530b  jnz     short loc_14008532F
0x14008530d  mov     [rsp+118h+Timeout], 0; Timeout
0x140085316  xor     r9d, r9d; Alertable
0x140085319  xor     r8d, r8d; WaitMode
0x14008531c  xor     edx, edx; WaitReason
0x14008531e  lea     rcx, [rsp+118h+Event]; Object
0x140085323  call    cs:__imp_KeWaitForSingleObject
0x14008532a  nop     dword ptr [rax+rax+00h]
0x14008532f  lea     rdx, [rsp+118h+Reply]; Reply
0x140085334  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14008533c  call    cs:__imp_RpcAsyncCompleteCall
0x140085343  nop     dword ptr [rax+rax+00h]
0x140085348  lea     rcx, WitnessRundownLock; RunRef
0x14008534f  call    cs:__imp_ExReleaseRundownProtection
0x140085356  nop     dword ptr [rax+rax+00h]
0x14008535b  mov     rcx, rbx
0x14008535e  call    WitnessFreeClusterConnectContext
0x140085363  mov     rcx, [rsp+118h+var_10]
0x14008536b  xor     rcx, rsp; StackCookie
0x14008536e  call    __security_check_cookie
0x140085373  mov     rbx, [rsp+118h+arg_8]
0x14008537b  add     rsp, 110h
0x140085382  pop     rdi
0x140085383  retn
0x140095cc9  push    rbp
0x140095ccb  sub     rsp, 40h
0x140095ccf  mov     rbp, rdx
0x140095cd2  mov     rcx, [rcx]
0x140095cd5  mov     ecx, [rcx]; ExceptionCode
0x140095cd7  call    cs:__imp_I_RpcExceptionFilter
0x140095cde  nop     dword ptr [rax+rax+00h]
0x140095ce3  nop
0x140095ce4  add     rsp, 40h
0x140095ce8  pop     rbp
0x140095ce9  retn
```
