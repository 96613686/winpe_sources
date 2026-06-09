# CiCatDbSendSmartAppControlBlockToast2

- ea: `0x180062244`
- end: `0x1800625f6`
- name: `CiCatDbSendSmartAppControlBlockToast2`
- size: `946`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800647dc`
- `0x1800b4f38`

## callees

- `0x1800207a4`
- `0x18002c0d0`
- `0x18002c500`
- `0x180062244`
- `0x18009c3a4`
- `0x1800bba44`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006259f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800625b3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800625c7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006259f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800625b3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800625c7`
- `ntoskrnl!KeStackAttachProcess` at `0x180062395`
- `ntoskrnl!KeStackAttachProcess` at `0x180062395`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800622fb`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062324`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062347`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800622fb`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062324`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180062347`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006257f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006257f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180062372`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180062372`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006258e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006258e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180062363`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180062363`
- `ntoskrnl!KeDelayExecutionThread` at `0x18006253b`
- `ntoskrnl!KeDelayExecutionThread` at `0x18006253b`
- `ntoskrnl!KeInitializeEvent` at `0x180062407`
- `ntoskrnl!KeInitializeEvent` at `0x180062407`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062499`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800624dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062499`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800624dc`
- `msrpc!RpcAsyncCancelCall` at `0x1800624b7`
- `msrpc!RpcAsyncCancelCall` at `0x1800624b7`
- `msrpc!RpcAsyncCompleteCall` at `0x1800624f5`
- `msrpc!RpcAsyncCompleteCall` at `0x18006250b`
- `msrpc!RpcAsyncCompleteCall` at `0x1800624f5`
- `msrpc!RpcAsyncCompleteCall` at `0x18006250b`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea4fb`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea4fb`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800623c7`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800623c7`

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
0x180062244  mov     r11, rsp
0x180062247  mov     [r11+20h], r9d
0x18006224b  push    rbx
0x18006224c  push    rsi
0x18006224d  push    r12
0x18006224f  push    r13
0x180062251  push    r15
0x180062253  sub     rsp, 160h
0x18006225a  mov     rax, cs:__security_cookie
0x180062261  xor     rax, rsp
0x180062264  mov     [rsp+188h+var_38], rax
0x18006226c  mov     r13d, r9d
0x18006226f  mov     r12, r8
0x180062272  mov     rsi, rdx
0x180062275  mov     rbx, rcx
0x180062278  mov     r15, [rsp+188h+arg_20]
0x180062280  mov     [rsp+188h+var_130], r15
0x180062285  xorps   xmm0, xmm0
0x180062288  movups  xmmword ptr [r11-68h], xmm0
0x18006228d  movups  xmmword ptr [r11-58h], xmm0
0x180062292  movups  xmmword ptr [r11-48h], xmm0
0x180062297  xor     edx, edx; Val
0x180062299  lea     r8d, [rdx+58h]; Size
0x18006229d  lea     rcx, [r11-0C8h]; void *
0x1800622a4  call    memset
0x1800622a9  mov     [rsp+188h+Binding], 0
0x1800622b2  xorps   xmm0, xmm0
0x1800622b5  movups  xmmword ptr [rsp+188h+StringOut.Length], xmm0
0x1800622bd  xorps   xmm1, xmm1
0x1800622c0  movups  xmmword ptr [rsp+188h+var_108.Length], xmm1
0x1800622c8  movups  xmmword ptr [rsp+188h+UnicodeString.Length], xmm0
0x1800622cd  xor     eax, eax
0x1800622cf  movups  xmmword ptr [rsp+188h+Event.Header], xmm1
0x1800622d7  mov     [rsp+188h+Event.Header.WaitListHead.Blink], rax
0x1800622df  mov     qword ptr [rsp+188h+Interval], rax
0x1800622e4  mov     [rsp+188h+Reply], eax
0x1800622e8  mov     [rsp+188h+var_128], rax
0x1800622ed  lea     r8, [rsp+188h+StringOut]; StringOut
0x1800622f5  mov     rdx, rbx; StringIn
0x1800622f8  lea     ecx, [rax+1]; Flags
0x1800622fb  call    cs:__imp_RtlDuplicateUnicodeString
0x180062302  nop     dword ptr [rax+rax+00h]
0x180062307  test    eax, eax
0x180062309  js      loc_1800625D5
0x18006230f  test    rsi, rsi
0x180062312  jz      short loc_18006233A
0x180062314  lea     r8, [rsp+188h+var_108]; StringOut
0x18006231c  mov     rdx, rsi; StringIn
0x18006231f  mov     ecx, 1; Flags
0x180062324  call    cs:__imp_RtlDuplicateUnicodeString
0x18006232b  nop     dword ptr [rax+rax+00h]
0x180062330  mov     ebx, eax
0x180062332  test    eax, eax
0x180062334  js      loc_1800625BF
0x18006233a  lea     r8, [rsp+188h+UnicodeString]; StringOut
0x18006233f  mov     rdx, r12; StringIn
0x180062342  mov     ecx, 1; Flags
0x180062347  call    cs:__imp_RtlDuplicateUnicodeString
0x18006234e  nop     dword ptr [rax+rax+00h]
0x180062353  mov     ebx, eax
0x180062355  test    eax, eax
0x180062357  js      loc_1800625AB
0x18006235d  xor     esi, esi
0x18006235f  mov     [rsp+188h+var_144], esi
0x180062363  call    cs:__imp_PsGetCurrentServerSilo
0x18006236a  nop     dword ptr [rax+rax+00h]
0x18006236f  mov     rcx, rax
0x180062372  call    cs:__imp_PsAttachSiloToCurrentThread
0x180062379  nop     dword ptr [rax+rax+00h]
0x18006237e  mov     r12, rax
0x180062381  mov     [rsp+188h+var_120], rax
0x180062386  lea     rdx, [rsp+188h+ApcState]; ApcState
0x18006238e  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180062395  call    cs:__imp_KeStackAttachProcess
0x18006239c  nop     dword ptr [rax+rax+00h]
0x1800623a1  lea     rdx, [rsp+188h+var_128]
0x1800623a6  lea     rcx, [rsp+188h+Binding]
0x1800623ab  call    CipCatDbRpcConnect
0x1800623b0  mov     ebx, eax
0x1800623b2  test    eax, eax
0x1800623b4  js      loc_180062565
0x1800623ba  mov     edx, 58h ; 'X'; Size
0x1800623bf  lea     rcx, [rsp+188h+pAsync]; pAsync
0x1800623c7  call    cs:__imp_RpcAsyncInitializeHandle
0x1800623ce  nop     dword ptr [rax+rax+00h]
0x1800623d3  mov     ebx, eax
0x1800623d5  test    eax, eax
0x1800623d7  jz      short loc_1800623E3
0x1800623d9  mov     ebx, 0C0000001h
0x1800623de  jmp     loc_180062565
0x1800623e3  mov     [rsp+188h+pAsync.UserInfo], 0
0x1800623ef  mov     [rsp+188h+pAsync.NotificationType], 1
0x1800623fa  xor     r8d, r8d; State
0x1800623fd  xor     edx, edx; Type
0x1800623ff  lea     rcx, [rsp+188h+Event]; Event
0x180062407  call    cs:__imp_KeInitializeEvent
0x18006240e  nop     dword ptr [rax+rax+00h]
0x180062413  lea     rax, [rsp+188h+Event]
0x18006241b  mov     qword ptr [rsp+188h+pAsync.u], rax
0x180062423  mov     [rsp+188h+var_158], r15
0x180062428  mov     [rsp+188h+var_160], r13d
0x18006242d  mov     rax, [rsp+188h+UnicodeString.Buffer]
0x180062432  mov     [rsp+188h+Timeout], rax
0x180062437  mov     r9, [rsp+188h+var_108.Buffer]
0x18006243f  mov     r8, [rsp+188h+StringOut.Buffer]
0x180062447  mov     rdx, [rsp+188h+Binding]
0x18006244c  lea     rcx, [rsp+188h+pAsync]
0x180062454  call    SSCatDBSendSmartAppControlBlockToast2
0x180062459  jmp     short loc_18006246E
0x18006245b  mov     ebx, eax
0x18006245d  mov     r13d, [rsp+188h+arg_18]
0x180062465  mov     esi, [rsp+188h+var_144]
0x180062469  mov     r12, [rsp+188h+var_120]
0x18006246e  test    ebx, ebx
0x180062470  jnz     loc_1800623D9
0x180062476  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFB3B4C00h
0x18006247f  lea     rax, [rsp+188h+Interval]
0x180062484  mov     [rsp+188h+Timeout], rax; Timeout
0x180062489  xor     r9d, r9d; Alertable
0x18006248c  xor     r8d, r8d; WaitMode
0x18006248f  xor     edx, edx; WaitReason
0x180062491  lea     rcx, [rsp+188h+Event]; Object
0x180062499  call    cs:__imp_KeWaitForSingleObject
0x1800624a0  nop     dword ptr [rax+rax+00h]
0x1800624a5  mov     r15d, eax
0x1800624a8  lea     rcx, [rsp+188h+pAsync]; pAsync
0x1800624b0  test    eax, eax
0x1800624b2  jz      short loc_180062506
0x1800624b4  lea     edx, [rbx+1]; fAbort
0x1800624b7  call    cs:__imp_RpcAsyncCancelCall
0x1800624be  nop     dword ptr [rax+rax+00h]
0x1800624c3  mov     [rsp+188h+Timeout], 0; Timeout
0x1800624cc  xor     r9d, r9d; Alertable
0x1800624cf  xor     r8d, r8d; WaitMode
0x1800624d2  xor     edx, edx; WaitReason
0x1800624d4  lea     rcx, [rsp+188h+Event]; Object
0x1800624dc  call    cs:__imp_KeWaitForSingleObject
0x1800624e3  nop     dword ptr [rax+rax+00h]
0x1800624e8  lea     rdx, [rsp+188h+Reply]; Reply
0x1800624ed  lea     rcx, [rsp+188h+pAsync]; pAsync
0x1800624f5  call    cs:__imp_RpcAsyncCompleteCall
0x1800624fc  nop     dword ptr [rax+rax+00h]
0x180062501  jmp     loc_1800623D9
0x180062506  lea     rdx, [rsp+188h+Reply]; Reply
0x18006250b  call    cs:__imp_RpcAsyncCompleteCall
0x180062512  nop     dword ptr [rax+rax+00h]
0x180062517  cmp     eax, 0C0020018h
0x18006251c  jnz     short loc_180062551
0x18006251e  cmp     esi, 14h
0x180062521  jnb     short loc_180062551
0x180062523  inc     esi
0x180062525  mov     [rsp+188h+var_144], esi
0x180062529  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFFF0BDC0h
0x180062532  lea     r8, [rsp+188h+Interval]; Interval
0x180062537  xor     edx, edx; Alertable
0x180062539  xor     ecx, ecx; WaitMode
0x18006253b  call    cs:__imp_KeDelayExecutionThread
0x180062542  nop     dword ptr [rax+rax+00h]
0x180062547  mov     r15, [rsp+188h+var_130]
0x18006254c  jmp     loc_1800623BA
0x180062551  mov     ebx, 0C0000001h
0x180062556  test    eax, eax
0x180062558  jnz     short loc_180062565
0x18006255a  cmp     [rsp+188h+Reply], eax
0x18006255e  cmovnz  r15d, ebx
0x180062562  mov     ebx, r15d
0x180062565  cmp     [rsp+188h+Binding], 0
0x18006256b  jz      short loc_180062577
0x18006256d  lea     rcx, [rsp+188h+Binding]; Binding
0x180062572  call    CipCatDbRpcDisconnect
0x180062577  lea     rcx, [rsp+188h+ApcState]; ApcState
0x18006257f  call    cs:__imp_KeUnstackDetachProcess
0x180062586  nop     dword ptr [rax+rax+00h]
0x18006258b  mov     rcx, r12
0x18006258e  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180062595  nop     dword ptr [rax+rax+00h]
0x18006259a  lea     rcx, [rsp+188h+UnicodeString]; UnicodeString
0x18006259f  call    cs:__imp_RtlFreeUnicodeString
0x1800625a6  nop     dword ptr [rax+rax+00h]
0x1800625ab  lea     rcx, [rsp+188h+var_108]; UnicodeString
0x1800625b3  call    cs:__imp_RtlFreeUnicodeString
0x1800625ba  nop     dword ptr [rax+rax+00h]
0x1800625bf  lea     rcx, [rsp+188h+StringOut]; UnicodeString
0x1800625c7  call    cs:__imp_RtlFreeUnicodeString
0x1800625ce  nop     dword ptr [rax+rax+00h]
0x1800625d3  mov     eax, ebx
0x1800625d5  mov     rcx, [rsp+188h+var_38]
0x1800625dd  xor     rcx, rsp; StackCookie
0x1800625e0  call    __security_check_cookie
0x1800625e5  add     rsp, 160h
0x1800625ec  pop     r15
0x1800625ee  pop     r13
0x1800625f0  pop     r12
0x1800625f2  pop     rsi
0x1800625f3  pop     rbx
0x1800625f4  retn
0x1800ea4ed  push    rbp
0x1800ea4ef  sub     rsp, 40h
0x1800ea4f3  mov     rbp, rdx
0x1800ea4f6  mov     rcx, [rcx]
0x1800ea4f9  mov     ecx, [rcx]; ExceptionCode
0x1800ea4fb  call    cs:__imp_I_RpcExceptionFilter
0x1800ea502  nop     dword ptr [rax+rax+00h]
0x1800ea507  nop
0x1800ea508  add     rsp, 40h
0x1800ea50c  pop     rbp
0x1800ea50d  retn
```
