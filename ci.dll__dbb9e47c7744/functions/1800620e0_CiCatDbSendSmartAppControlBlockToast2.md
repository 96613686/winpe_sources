# CiCatDbSendSmartAppControlBlockToast2

- ea: `0x1800620e0`
- end: `0x180062492`
- name: `CiCatDbSendSmartAppControlBlockToast2`
- size: `946`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006466c`
- `0x1800b5098`

## callees

- `0x1800206d4`
- `0x18002bf20`
- `0x18002c380`
- `0x1800620e0`
- `0x18008b15c`
- `0x1800bbba4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006243b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006244f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180062463`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006243b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006244f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180062463`
- `ntoskrnl!KeStackAttachProcess` at `0x180062231`
- `ntoskrnl!KeStackAttachProcess` at `0x180062231`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062197`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800621c0`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800621e3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062197`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800621c0`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800621e3`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006241b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006241b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18006220e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18006220e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006242a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006242a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800621ff`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800621ff`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800623d7`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800623d7`
- `ntoskrnl!KeInitializeEvent` at `0x1800622a3`
- `ntoskrnl!KeInitializeEvent` at `0x1800622a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062335`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062378`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062335`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062378`
- `msrpc!RpcAsyncCancelCall` at `0x180062353`
- `msrpc!RpcAsyncCancelCall` at `0x180062353`
- `msrpc!RpcAsyncCompleteCall` at `0x180062391`
- `msrpc!RpcAsyncCompleteCall` at `0x1800623a7`
- `msrpc!RpcAsyncCompleteCall` at `0x180062391`
- `msrpc!RpcAsyncCompleteCall` at `0x1800623a7`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9cbb`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9cbb`
- `msrpc!RpcAsyncInitializeHandle` at `0x180062263`
- `msrpc!RpcAsyncInitializeHandle` at `0x180062263`

## pseudocode

```c
NTSTATUS __fastcall CiCatDbSendSmartAppControlBlockToast2(
        PCUNICODE_STRING StringIn,
        PCUNICODE_STRING a2,
        PCUNICODE_STRING a3,
        int a4,
        __int64 a5)
{
  __int64 v9; // r15
  NTSTATUS result; // eax
  NTSTATUS v11; // ebx
  unsigned int v12; // esi
  __int64 CurrentServerSilo; // rax
  __int64 v14; // r12
  NTSTATUS v15; // r15d
  RPC_STATUS v16; // eax
  int Reply; // [rsp+40h] [rbp-148h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-144h]
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp-140h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-138h] BYREF
  __int64 v21; // [rsp+58h] [rbp-130h]
  _QWORD v22[2]; // [rsp+60h] [rbp-128h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-118h] BYREF
  struct _UNICODE_STRING v24; // [rsp+80h] [rbp-108h] BYREF
  struct _UNICODE_STRING StringOut; // [rsp+90h] [rbp-F8h] BYREF
  struct _KEVENT Event; // [rsp+A0h] [rbp-E8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+C0h] [rbp-C8h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+120h] [rbp-68h] BYREF

  v9 = a5;
  v21 = a5;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  StringOut = 0;
  v24 = 0;
  UnicodeString = 0;
  memset(&Event, 0, sizeof(Event));
  Interval.QuadPart = 0;
  Reply = 0;
  v22[0] = 0;
  result = RtlDuplicateUnicodeString(1u, StringIn, &StringOut);
  if ( result >= 0 )
  {
    if ( !a2 || (v11 = RtlDuplicateUnicodeString(1u, a2, &v24), v11 >= 0) )
    {
      v11 = RtlDuplicateUnicodeString(1u, a3, &UnicodeString);
      if ( v11 >= 0 )
      {
        v12 = 0;
        v18 = 0;
        CurrentServerSilo = PsGetCurrentServerSilo();
        v14 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v22[1] = v14;
        KeStackAttachProcess(g_CiSystemProcess, &ApcState);
        v11 = CipCatDbRpcConnect(&Binding, v22);
        if ( v11 >= 0 )
        {
          while ( 1 )
          {
            if ( RpcAsyncInitializeHandle(&pAsync, 0x58u) )
              goto LABEL_7;
            pAsync.UserInfo = 0;
            pAsync.NotificationType = RpcNotificationTypeEvent;
            KeInitializeEvent(&Event, NotificationEvent, 0);
            pAsync.u.Event = &Event;
            SSCatDBSendSmartAppControlBlockToast2(
              (unsigned int)&pAsync,
              (_DWORD)Binding,
              StringOut.Buffer,
              v24.Buffer,
              (__int64)UnicodeString.Buffer,
              a4,
              v9);
            Interval.QuadPart = -80000000;
            v15 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
            if ( v15 )
            {
              RpcAsyncCancelCall(&pAsync, 1);
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              RpcAsyncCompleteCall(&pAsync, &Reply);
LABEL_7:
              v11 = -1073741823;
              goto LABEL_18;
            }
            v16 = RpcAsyncCompleteCall(&pAsync, &Reply);
            if ( v16 != -1073610728 || v12 >= 0x14 )
              break;
            v18 = ++v12;
            Interval.QuadPart = -1000000;
            KeDelayExecutionThread(0, 0, &Interval);
            v9 = v21;
          }
          v11 = -1073741823;
          if ( !v16 )
          {
            if ( Reply )
              v15 = -1073741823;
            v11 = v15;
          }
        }
LABEL_18:
        if ( Binding )
          CipCatDbRpcDisconnect(&Binding);
        KeUnstackDetachProcess(&ApcState);
        PsDetachSiloFromCurrentThread(v14);
        RtlFreeUnicodeString(&UnicodeString);
      }
      RtlFreeUnicodeString(&v24);
    }
    RtlFreeUnicodeString(&StringOut);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800620e0  mov     r11, rsp
0x1800620e3  mov     [r11+20h], r9d
0x1800620e7  push    rbx
0x1800620e8  push    rsi
0x1800620e9  push    r12
0x1800620eb  push    r13
0x1800620ed  push    r15
0x1800620ef  sub     rsp, 160h
0x1800620f6  mov     rax, cs:__security_cookie
0x1800620fd  xor     rax, rsp
0x180062100  mov     [rsp+188h+var_38], rax
0x180062108  mov     r13d, r9d
0x18006210b  mov     r12, r8
0x18006210e  mov     rsi, rdx
0x180062111  mov     rbx, rcx
0x180062114  mov     r15, [rsp+188h+arg_20]
0x18006211c  mov     [rsp+188h+var_130], r15
0x180062121  xorps   xmm0, xmm0
0x180062124  movups  xmmword ptr [r11-68h], xmm0
0x180062129  movups  xmmword ptr [r11-58h], xmm0
0x18006212e  movups  xmmword ptr [r11-48h], xmm0
0x180062133  xor     edx, edx; Val
0x180062135  lea     r8d, [rdx+58h]; Size
0x180062139  lea     rcx, [r11-0C8h]; void *
0x180062140  call    memset
0x180062145  mov     [rsp+188h+Binding], 0
0x18006214e  xorps   xmm0, xmm0
0x180062151  movups  xmmword ptr [rsp+188h+StringOut.Length], xmm0
0x180062159  xorps   xmm1, xmm1
0x18006215c  movups  xmmword ptr [rsp+188h+var_108.Length], xmm1
0x180062164  movups  xmmword ptr [rsp+188h+UnicodeString.Length], xmm0
0x180062169  xor     eax, eax
0x18006216b  movups  xmmword ptr [rsp+188h+Event.Header], xmm1
0x180062173  mov     [rsp+188h+Event.Header.WaitListHead.Blink], rax
0x18006217b  mov     qword ptr [rsp+188h+Interval], rax
0x180062180  mov     [rsp+188h+Reply], eax
0x180062184  mov     [rsp+188h+var_128], rax
0x180062189  lea     r8, [rsp+188h+StringOut]; StringOut
0x180062191  mov     rdx, rbx; StringIn
0x180062194  lea     ecx, [rax+1]; Flags
0x180062197  call    cs:__imp_RtlDuplicateUnicodeString
0x18006219e  nop     dword ptr [rax+rax+00h]
0x1800621a3  test    eax, eax
0x1800621a5  js      loc_180062471
0x1800621ab  test    rsi, rsi
0x1800621ae  jz      short loc_1800621D6
0x1800621b0  lea     r8, [rsp+188h+var_108]; StringOut
0x1800621b8  mov     rdx, rsi; StringIn
0x1800621bb  mov     ecx, 1; Flags
0x1800621c0  call    cs:__imp_RtlDuplicateUnicodeString
0x1800621c7  nop     dword ptr [rax+rax+00h]
0x1800621cc  mov     ebx, eax
0x1800621ce  test    eax, eax
0x1800621d0  js      loc_18006245B
0x1800621d6  lea     r8, [rsp+188h+UnicodeString]; StringOut
0x1800621db  mov     rdx, r12; StringIn
0x1800621de  mov     ecx, 1; Flags
0x1800621e3  call    cs:__imp_RtlDuplicateUnicodeString
0x1800621ea  nop     dword ptr [rax+rax+00h]
0x1800621ef  mov     ebx, eax
0x1800621f1  test    eax, eax
0x1800621f3  js      loc_180062447
0x1800621f9  xor     esi, esi
0x1800621fb  mov     [rsp+188h+var_144], esi
0x1800621ff  call    cs:__imp_PsGetCurrentServerSilo
0x180062206  nop     dword ptr [rax+rax+00h]
0x18006220b  mov     rcx, rax
0x18006220e  call    cs:__imp_PsAttachSiloToCurrentThread
0x180062215  nop     dword ptr [rax+rax+00h]
0x18006221a  mov     r12, rax
0x18006221d  mov     [rsp+188h+var_120], rax
0x180062222  lea     rdx, [rsp+188h+ApcState]; ApcState
0x18006222a  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180062231  call    cs:__imp_KeStackAttachProcess
0x180062238  nop     dword ptr [rax+rax+00h]
0x18006223d  lea     rdx, [rsp+188h+var_128]
0x180062242  lea     rcx, [rsp+188h+Binding]
0x180062247  call    CipCatDbRpcConnect
0x18006224c  mov     ebx, eax
0x18006224e  test    eax, eax
0x180062250  js      loc_180062401
0x180062256  mov     edx, 58h ; 'X'; Size
0x18006225b  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180062263  call    cs:__imp_RpcAsyncInitializeHandle
0x18006226a  nop     dword ptr [rax+rax+00h]
0x18006226f  mov     ebx, eax
0x180062271  test    eax, eax
0x180062273  jz      short loc_18006227F
0x180062275  mov     ebx, 0C0000001h
0x18006227a  jmp     loc_180062401
0x18006227f  mov     [rsp+188h+pAsync.UserInfo], 0
0x18006228b  mov     [rsp+188h+pAsync.NotificationType], 1
0x180062296  xor     r8d, r8d; State
0x180062299  xor     edx, edx; Type
0x18006229b  lea     rcx, [rsp+188h+Event]; Event
0x1800622a3  call    cs:__imp_KeInitializeEvent
0x1800622aa  nop     dword ptr [rax+rax+00h]
0x1800622af  lea     rax, [rsp+188h+Event]
0x1800622b7  mov     qword ptr [rsp+188h+pAsync.u], rax
0x1800622bf  mov     [rsp+188h+var_158], r15
0x1800622c4  mov     [rsp+188h+var_160], r13d
0x1800622c9  mov     rax, [rsp+188h+UnicodeString.Buffer]
0x1800622ce  mov     [rsp+188h+Timeout], rax
0x1800622d3  mov     r9, [rsp+188h+var_108.Buffer]
0x1800622db  mov     r8, [rsp+188h+StringOut.Buffer]
0x1800622e3  mov     rdx, [rsp+188h+Binding]
0x1800622e8  lea     rcx, [rsp+188h+pAsync]
0x1800622f0  call    SSCatDBSendSmartAppControlBlockToast2
0x1800622f5  jmp     short loc_18006230A
0x1800622f7  mov     ebx, eax
0x1800622f9  mov     r13d, [rsp+188h+arg_18]
0x180062301  mov     esi, [rsp+188h+var_144]
0x180062305  mov     r12, [rsp+188h+var_120]
0x18006230a  test    ebx, ebx
0x18006230c  jnz     loc_180062275
0x180062312  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFB3B4C00h
0x18006231b  lea     rax, [rsp+188h+Interval]
0x180062320  mov     [rsp+188h+Timeout], rax; Timeout
0x180062325  xor     r9d, r9d; Alertable
0x180062328  xor     r8d, r8d; WaitMode
0x18006232b  xor     edx, edx; WaitReason
0x18006232d  lea     rcx, [rsp+188h+Event]; Object
0x180062335  call    cs:__imp_KeWaitForSingleObject
0x18006233c  nop     dword ptr [rax+rax+00h]
0x180062341  mov     r15d, eax
0x180062344  lea     rcx, [rsp+188h+pAsync]; pAsync
0x18006234c  test    eax, eax
0x18006234e  jz      short loc_1800623A2
0x180062350  lea     edx, [rbx+1]; fAbort
0x180062353  call    cs:__imp_RpcAsyncCancelCall
0x18006235a  nop     dword ptr [rax+rax+00h]
0x18006235f  mov     [rsp+188h+Timeout], 0; Timeout
0x180062368  xor     r9d, r9d; Alertable
0x18006236b  xor     r8d, r8d; WaitMode
0x18006236e  xor     edx, edx; WaitReason
0x180062370  lea     rcx, [rsp+188h+Event]; Object
0x180062378  call    cs:__imp_KeWaitForSingleObject
0x18006237f  nop     dword ptr [rax+rax+00h]
0x180062384  lea     rdx, [rsp+188h+Reply]; Reply
0x180062389  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180062391  call    cs:__imp_RpcAsyncCompleteCall
0x180062398  nop     dword ptr [rax+rax+00h]
0x18006239d  jmp     loc_180062275
0x1800623a2  lea     rdx, [rsp+188h+Reply]; Reply
0x1800623a7  call    cs:__imp_RpcAsyncCompleteCall
0x1800623ae  nop     dword ptr [rax+rax+00h]
0x1800623b3  cmp     eax, 0C0020018h
0x1800623b8  jnz     short loc_1800623ED
0x1800623ba  cmp     esi, 14h
0x1800623bd  jnb     short loc_1800623ED
0x1800623bf  inc     esi
0x1800623c1  mov     [rsp+188h+var_144], esi
0x1800623c5  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800623ce  lea     r8, [rsp+188h+Interval]; Interval
0x1800623d3  xor     edx, edx; Alertable
0x1800623d5  xor     ecx, ecx; WaitMode
0x1800623d7  call    cs:__imp_KeDelayExecutionThread
0x1800623de  nop     dword ptr [rax+rax+00h]
0x1800623e3  mov     r15, [rsp+188h+var_130]
0x1800623e8  jmp     loc_180062256
0x1800623ed  mov     ebx, 0C0000001h
0x1800623f2  test    eax, eax
0x1800623f4  jnz     short loc_180062401
0x1800623f6  cmp     [rsp+188h+Reply], eax
0x1800623fa  cmovnz  r15d, ebx
0x1800623fe  mov     ebx, r15d
0x180062401  cmp     [rsp+188h+Binding], 0
0x180062407  jz      short loc_180062413
0x180062409  lea     rcx, [rsp+188h+Binding]; Binding
0x18006240e  call    CipCatDbRpcDisconnect
0x180062413  lea     rcx, [rsp+188h+ApcState]; ApcState
0x18006241b  call    cs:__imp_KeUnstackDetachProcess
0x180062422  nop     dword ptr [rax+rax+00h]
0x180062427  mov     rcx, r12
0x18006242a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180062431  nop     dword ptr [rax+rax+00h]
0x180062436  lea     rcx, [rsp+188h+UnicodeString]; UnicodeString
0x18006243b  call    cs:__imp_RtlFreeUnicodeString
0x180062442  nop     dword ptr [rax+rax+00h]
0x180062447  lea     rcx, [rsp+188h+var_108]; UnicodeString
0x18006244f  call    cs:__imp_RtlFreeUnicodeString
0x180062456  nop     dword ptr [rax+rax+00h]
0x18006245b  lea     rcx, [rsp+188h+StringOut]; UnicodeString
0x180062463  call    cs:__imp_RtlFreeUnicodeString
0x18006246a  nop     dword ptr [rax+rax+00h]
0x18006246f  mov     eax, ebx
0x180062471  mov     rcx, [rsp+188h+var_38]
0x180062479  xor     rcx, rsp; StackCookie
0x18006247c  call    __security_check_cookie
0x180062481  add     rsp, 160h
0x180062488  pop     r15
0x18006248a  pop     r13
0x18006248c  pop     r12
0x18006248e  pop     rsi
0x18006248f  pop     rbx
0x180062490  retn
0x1800e9cad  push    rbp
0x1800e9caf  sub     rsp, 40h
0x1800e9cb3  mov     rbp, rdx
0x1800e9cb6  mov     rcx, [rcx]
0x1800e9cb9  mov     ecx, [rcx]; ExceptionCode
0x1800e9cbb  call    cs:__imp_I_RpcExceptionFilter
0x1800e9cc2  nop     dword ptr [rax+rax+00h]
0x1800e9cc7  nop
0x1800e9cc8  add     rsp, 40h
0x1800e9ccc  pop     rbp
0x1800e9ccd  retn
```
