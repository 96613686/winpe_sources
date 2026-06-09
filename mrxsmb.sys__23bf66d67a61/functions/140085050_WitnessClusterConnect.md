# WitnessClusterConnect

- ea: `0x140085050`
- end: `0x1400853d5`
- name: `WitnessClusterConnect`
- size: `901`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14003838c`
- `0x140039fa8`
- `0x14004cac0`
- `0x140059dc0`
- `0x14005a200`
- `0x140085050`
- `0x1400855d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140085227`
- `ntoskrnl!KeInitializeEvent` at `0x140085227`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400852f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140085373`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400852f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140085373`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008539f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008539f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400850c8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400850c8`
- `msrpc!RpcAsyncCancelCall` at `0x14008534d`
- `msrpc!RpcAsyncCancelCall` at `0x14008534d`
- `msrpc!RpcAsyncCompleteCall` at `0x14008538c`
- `msrpc!RpcAsyncCompleteCall` at `0x14008538c`
- `msrpc!RpcAsyncInitializeHandle` at `0x14008517f`
- `msrpc!RpcAsyncInitializeHandle` at `0x14008517f`
- `msrpc!I_RpcExceptionFilter` at `0x140095d27`
- `msrpc!I_RpcExceptionFilter` at `0x140095d27`

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
0x140085050  mov     [rsp+arg_8], rbx
0x140085055  push    rdi
0x140085056  sub     rsp, 110h
0x14008505d  mov     rax, cs:__security_cookie
0x140085064  xor     rax, rsp
0x140085067  mov     [rsp+118h+var_10], rax
0x14008506f  mov     rbx, rcx
0x140085072  mov     [rsp+118h+var_C8], rcx
0x140085077  mov     [rsp+118h+Reply], 0
0x14008507f  xorps   xmm0, xmm0
0x140085082  xor     eax, eax
0x140085084  movups  xmmword ptr [rsp+118h+Event.Header], xmm0
0x140085089  mov     [rsp+118h+Event.Header.WaitListHead.Blink], rax
0x14008508e  lea     edi, [rax+58h]
0x140085091  mov     r8d, edi; Size
0x140085094  xor     edx, edx; Val
0x140085096  lea     rcx, [rsp+118h+pAsync]; void *
0x14008509e  call    memset
0x1400850a3  mov     qword ptr [rsp+118h+var_D0], 0
0x1400850ac  xor     eax, eax
0x1400850ae  xorps   xmm0, xmm0
0x1400850b1  movups  [rsp+118h+var_28], xmm0
0x1400850b9  mov     qword ptr [rsp+118h+var_28+0Eh], rax
0x1400850c1  lea     rcx, WitnessRundownLock; RunRef
0x1400850c8  call    cs:__imp_ExAcquireRundownProtection
0x1400850cf  nop     dword ptr [rax+rax+00h]
0x1400850d4  test    al, al
0x1400850d6  jnz     short loc_14008511C
0x1400850d8  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400850df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400850e6  cmp     rcx, rax
0x1400850e9  jz      loc_1400853AB
0x1400850ef  mov     eax, [rcx+2Ch]
0x1400850f2  test    al, 1
0x1400850f4  jz      loc_1400853AB
0x1400850fa  cmp     byte ptr [rcx+29h], 1
0x1400850fe  jb      loc_1400853AB
0x140085104  lea     edx, [rdi-4Eh]
0x140085107  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x14008510e  mov     rcx, [rcx+18h]
0x140085112  call    WPP_SF_
0x140085117  jmp     loc_1400853AB
0x14008511c  cmp     cs:WitnessRpcBindingHandle, 0
0x140085124  jnz     short loc_14008516C
0x140085126  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008512d  mov     rcx, cs:WPP_GLOBAL_Control
0x140085134  cmp     rcx, rax
0x140085137  jz      loc_140085398
0x14008513d  mov     eax, [rcx+2Ch]
0x140085140  test    al, 1
0x140085142  jz      loc_140085398
0x140085148  cmp     byte ptr [rcx+29h], 1
0x14008514c  jb      loc_140085398
0x140085152  mov     edx, 0Bh
0x140085157  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x14008515e  mov     rcx, [rcx+18h]
0x140085162  call    WPP_SF_
0x140085167  jmp     loc_140085398
0x14008516c  mov     qword ptr [rsp+118h+var_D0], 0FFFFFFFFEE1E5D00h
0x140085175  mov     edx, edi; Size
0x140085177  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14008517f  call    cs:__imp_RpcAsyncInitializeHandle
0x140085186  nop     dword ptr [rax+rax+00h]
0x14008518b  mov     edi, eax
0x14008518d  test    eax, eax
0x14008518f  jz      short loc_1400851DD
0x140085191  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140085198  mov     r10, cs:WPP_GLOBAL_Control
0x14008519f  cmp     r10, rax
0x1400851a2  jz      loc_140085398
0x1400851a8  mov     ecx, [r10+2Ch]
0x1400851ac  test    cl, 1
0x1400851af  jz      loc_140085398
0x1400851b5  cmp     byte ptr [r10+29h], 1
0x1400851ba  jb      loc_140085398
0x1400851c0  mov     edx, 0Ch
0x1400851c5  mov     rcx, [r10+18h]
0x1400851c9  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x1400851d0  mov     r9d, edi
0x1400851d3  call    WPP_SF_d
0x1400851d8  jmp     loc_140085398
0x1400851dd  xorps   xmm0, xmm0
0x1400851e0  xor     eax, eax
0x1400851e2  movups  [rsp+118h+var_28], xmm0
0x1400851ea  mov     [rsp+118h+var_18], rax
0x1400851f2  movzx   eax, word ptr [rbx+30h]
0x1400851f6  mov     word ptr [rsp+118h+var_28], ax
0x1400851fe  cmp     ax, 2
0x140085202  jnz     short loc_140085210
0x140085204  mov     eax, [rbx+34h]
0x140085207  mov     dword ptr [rsp+118h+var_28+4], eax
0x14008520e  jmp     short loc_14008521D
0x140085210  movups  xmm0, xmmword ptr [rbx+38h]
0x140085214  movdqu  [rsp+118h+var_28+8], xmm0
0x14008521d  xor     r8d, r8d; State
0x140085220  xor     edx, edx; Type
0x140085222  lea     rcx, [rsp+118h+Event]; Event
0x140085227  call    cs:__imp_KeInitializeEvent
0x14008522e  nop     dword ptr [rax+rax+00h]
0x140085233  mov     [rsp+118h+pAsync.NotificationType], 1
0x14008523e  lea     rax, [rsp+118h+Event]
0x140085243  mov     qword ptr [rsp+118h+pAsync.u], rax
0x14008524b  movups  xmm0, xmmword ptr [rbx+20h]
0x14008524f  movaps  [rsp+118h+var_98], xmm0
0x140085257  mov     al, [rbx+4Ch]
0x14008525a  neg     al
0x14008525c  sbb     ecx, ecx
0x14008525e  neg     ecx
0x140085260  inc     ecx
0x140085262  movdqa  [rsp+118h+var_A8], xmm0
0x140085268  lea     r9, [rbx+10h]
0x14008526c  mov     [rsp+118h+var_E8], ecx
0x140085270  lea     rax, [rsp+118h+var_A8]
0x140085275  mov     [rsp+118h+var_F0], rax
0x14008527a  lea     rax, [rsp+118h+var_28]
0x140085282  mov     [rsp+118h+Timeout], rax
0x140085287  mov     r8, rbx
0x14008528a  lea     rcx, [rsp+118h+pAsync]
0x140085292  call    ClusterConnectUpcall
0x140085297  jmp     short loc_1400852A0
0x140085299  mov     edi, eax
0x14008529b  mov     rbx, [rsp+118h+var_C8]
0x1400852a0  test    edi, edi
0x1400852a2  jz      short loc_1400852DE
0x1400852a4  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400852ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400852b2  cmp     rcx, rax
0x1400852b5  jz      loc_140085398
0x1400852bb  mov     eax, [rcx+2Ch]
0x1400852be  test    al, 1
0x1400852c0  jz      loc_140085398
0x1400852c6  cmp     byte ptr [rcx+29h], 1
0x1400852ca  jb      loc_140085398
0x1400852d0  mov     edx, 0Dh
0x1400852d5  mov     rcx, [rcx+18h]
0x1400852d9  jmp     loc_1400851C9
0x1400852de  lea     rax, [rsp+118h+var_D0]
0x1400852e3  mov     [rsp+118h+Timeout], rax; Timeout
0x1400852e8  xor     r9d, r9d; Alertable
0x1400852eb  xor     r8d, r8d; WaitMode
0x1400852ee  xor     edx, edx; WaitReason
0x1400852f0  lea     rcx, [rsp+118h+Event]; Object
0x1400852f5  call    cs:__imp_KeWaitForSingleObject
0x1400852fc  nop     dword ptr [rax+rax+00h]
0x140085301  mov     r9d, eax
0x140085304  test    eax, eax
0x140085306  jz      short loc_14008537F
0x140085308  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14008530f  mov     r10, cs:WPP_GLOBAL_Control
0x140085316  cmp     r10, rax
0x140085319  jz      short loc_140085340
0x14008531b  mov     ecx, [r10+2Ch]
0x14008531f  test    cl, 1
0x140085322  jz      short loc_140085340
0x140085324  cmp     byte ptr [r10+29h], 1
0x140085329  jb      short loc_140085340
0x14008532b  mov     edx, 0Eh
0x140085330  lea     r8, WPP_4aae7ecede3c3aa3b02c7c25f7ff8218_Traceguids
0x140085337  mov     rcx, [r10+18h]
0x14008533b  call    WPP_SF_d
0x140085340  mov     edx, 1; fAbort
0x140085345  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14008534d  call    cs:__imp_RpcAsyncCancelCall
0x140085354  nop     dword ptr [rax+rax+00h]
0x140085359  test    eax, eax
0x14008535b  jnz     short loc_14008537F
0x14008535d  mov     [rsp+118h+Timeout], 0; Timeout
0x140085366  xor     r9d, r9d; Alertable
0x140085369  xor     r8d, r8d; WaitMode
0x14008536c  xor     edx, edx; WaitReason
0x14008536e  lea     rcx, [rsp+118h+Event]; Object
0x140085373  call    cs:__imp_KeWaitForSingleObject
0x14008537a  nop     dword ptr [rax+rax+00h]
0x14008537f  lea     rdx, [rsp+118h+Reply]; Reply
0x140085384  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14008538c  call    cs:__imp_RpcAsyncCompleteCall
0x140085393  nop     dword ptr [rax+rax+00h]
0x140085398  lea     rcx, WitnessRundownLock; RunRef
0x14008539f  call    cs:__imp_ExReleaseRundownProtection
0x1400853a6  nop     dword ptr [rax+rax+00h]
0x1400853ab  mov     rcx, rbx
0x1400853ae  call    WitnessFreeClusterConnectContext
0x1400853b3  mov     rcx, [rsp+118h+var_10]
0x1400853bb  xor     rcx, rsp; StackCookie
0x1400853be  call    __security_check_cookie
0x1400853c3  mov     rbx, [rsp+118h+arg_8]
0x1400853cb  add     rsp, 110h
0x1400853d2  pop     rdi
0x1400853d3  retn
0x140095d19  push    rbp
0x140095d1b  sub     rsp, 40h
0x140095d1f  mov     rbp, rdx
0x140095d22  mov     rcx, [rcx]
0x140095d25  mov     ecx, [rcx]; ExceptionCode
0x140095d27  call    cs:__imp_I_RpcExceptionFilter
0x140095d2e  nop     dword ptr [rax+rax+00h]
0x140095d33  nop
0x140095d34  add     rsp, 40h
0x140095d38  pop     rbp
0x140095d39  retn
```
