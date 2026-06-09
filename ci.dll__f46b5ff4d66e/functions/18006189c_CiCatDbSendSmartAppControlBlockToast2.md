# CiCatDbSendSmartAppControlBlockToast2

- ea: `0x18006189c`
- end: `0x180061c4e`
- name: `CiCatDbSendSmartAppControlBlockToast2`
- size: `946`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180063d3c`
- `0x1800b3c18`

## callees

- `0x180020764`
- `0x18002bef0`
- `0x18002c340`
- `0x18006189c`
- `0x180089b2c`
- `0x1800ba724`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180061bf7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061c0b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061c1f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061bf7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061c0b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180061c1f`
- `ntoskrnl!KeStackAttachProcess` at `0x1800619ed`
- `ntoskrnl!KeStackAttachProcess` at `0x1800619ed`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180061953`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006197c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006199f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180061953`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006197c`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006199f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180061bd7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180061bd7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800619ca`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800619ca`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180061be6`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180061be6`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800619bb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800619bb`
- `ntoskrnl!KeDelayExecutionThread` at `0x180061b93`
- `ntoskrnl!KeDelayExecutionThread` at `0x180061b93`
- `ntoskrnl!KeInitializeEvent` at `0x180061a5f`
- `ntoskrnl!KeInitializeEvent` at `0x180061a5f`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061af1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061b34`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061af1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061b34`
- `msrpc!RpcAsyncCancelCall` at `0x180061b0f`
- `msrpc!RpcAsyncCancelCall` at `0x180061b0f`
- `msrpc!RpcAsyncCompleteCall` at `0x180061b4d`
- `msrpc!RpcAsyncCompleteCall` at `0x180061b63`
- `msrpc!RpcAsyncCompleteCall` at `0x180061b4d`
- `msrpc!RpcAsyncCompleteCall` at `0x180061b63`
- `msrpc!I_RpcExceptionFilter` at `0x1800e84b2`
- `msrpc!I_RpcExceptionFilter` at `0x1800e84b2`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061a1f`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061a1f`

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
0x18006189c  mov     r11, rsp
0x18006189f  mov     [r11+20h], r9d
0x1800618a3  push    rbx
0x1800618a4  push    rsi
0x1800618a5  push    r12
0x1800618a7  push    r13
0x1800618a9  push    r15
0x1800618ab  sub     rsp, 160h
0x1800618b2  mov     rax, cs:__security_cookie
0x1800618b9  xor     rax, rsp
0x1800618bc  mov     [rsp+188h+var_38], rax
0x1800618c4  mov     r13d, r9d
0x1800618c7  mov     r12, r8
0x1800618ca  mov     rsi, rdx
0x1800618cd  mov     rbx, rcx
0x1800618d0  mov     r15, [rsp+188h+arg_20]
0x1800618d8  mov     [rsp+188h+var_130], r15
0x1800618dd  xorps   xmm0, xmm0
0x1800618e0  movups  xmmword ptr [r11-68h], xmm0
0x1800618e5  movups  xmmword ptr [r11-58h], xmm0
0x1800618ea  movups  xmmword ptr [r11-48h], xmm0
0x1800618ef  xor     edx, edx; Val
0x1800618f1  lea     r8d, [rdx+58h]; Size
0x1800618f5  lea     rcx, [r11-0C8h]; void *
0x1800618fc  call    memset
0x180061901  mov     [rsp+188h+Binding], 0
0x18006190a  xorps   xmm0, xmm0
0x18006190d  movups  xmmword ptr [rsp+188h+StringOut.Length], xmm0
0x180061915  xorps   xmm1, xmm1
0x180061918  movups  xmmword ptr [rsp+188h+var_108.Length], xmm1
0x180061920  movups  xmmword ptr [rsp+188h+UnicodeString.Length], xmm0
0x180061925  xor     eax, eax
0x180061927  movups  xmmword ptr [rsp+188h+Event.Header], xmm1
0x18006192f  mov     [rsp+188h+Event.Header.WaitListHead.Blink], rax
0x180061937  mov     qword ptr [rsp+188h+Interval], rax
0x18006193c  mov     [rsp+188h+Reply], eax
0x180061940  mov     [rsp+188h+var_128], rax
0x180061945  lea     r8, [rsp+188h+StringOut]; StringOut
0x18006194d  mov     rdx, rbx; StringIn
0x180061950  lea     ecx, [rax+1]; Flags
0x180061953  call    cs:__imp_RtlDuplicateUnicodeString
0x18006195a  nop     dword ptr [rax+rax+00h]
0x18006195f  test    eax, eax
0x180061961  js      loc_180061C2D
0x180061967  test    rsi, rsi
0x18006196a  jz      short loc_180061992
0x18006196c  lea     r8, [rsp+188h+var_108]; StringOut
0x180061974  mov     rdx, rsi; StringIn
0x180061977  mov     ecx, 1; Flags
0x18006197c  call    cs:__imp_RtlDuplicateUnicodeString
0x180061983  nop     dword ptr [rax+rax+00h]
0x180061988  mov     ebx, eax
0x18006198a  test    eax, eax
0x18006198c  js      loc_180061C17
0x180061992  lea     r8, [rsp+188h+UnicodeString]; StringOut
0x180061997  mov     rdx, r12; StringIn
0x18006199a  mov     ecx, 1; Flags
0x18006199f  call    cs:__imp_RtlDuplicateUnicodeString
0x1800619a6  nop     dword ptr [rax+rax+00h]
0x1800619ab  mov     ebx, eax
0x1800619ad  test    eax, eax
0x1800619af  js      loc_180061C03
0x1800619b5  xor     esi, esi
0x1800619b7  mov     [rsp+188h+var_144], esi
0x1800619bb  call    cs:__imp_PsGetCurrentServerSilo
0x1800619c2  nop     dword ptr [rax+rax+00h]
0x1800619c7  mov     rcx, rax
0x1800619ca  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800619d1  nop     dword ptr [rax+rax+00h]
0x1800619d6  mov     r12, rax
0x1800619d9  mov     [rsp+188h+var_120], rax
0x1800619de  lea     rdx, [rsp+188h+ApcState]; ApcState
0x1800619e6  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x1800619ed  call    cs:__imp_KeStackAttachProcess
0x1800619f4  nop     dword ptr [rax+rax+00h]
0x1800619f9  lea     rdx, [rsp+188h+var_128]
0x1800619fe  lea     rcx, [rsp+188h+Binding]
0x180061a03  call    CipCatDbRpcConnect
0x180061a08  mov     ebx, eax
0x180061a0a  test    eax, eax
0x180061a0c  js      loc_180061BBD
0x180061a12  mov     edx, 58h ; 'X'; Size
0x180061a17  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180061a1f  call    cs:__imp_RpcAsyncInitializeHandle
0x180061a26  nop     dword ptr [rax+rax+00h]
0x180061a2b  mov     ebx, eax
0x180061a2d  test    eax, eax
0x180061a2f  jz      short loc_180061A3B
0x180061a31  mov     ebx, 0C0000001h
0x180061a36  jmp     loc_180061BBD
0x180061a3b  mov     [rsp+188h+pAsync.UserInfo], 0
0x180061a47  mov     [rsp+188h+pAsync.NotificationType], 1
0x180061a52  xor     r8d, r8d; State
0x180061a55  xor     edx, edx; Type
0x180061a57  lea     rcx, [rsp+188h+Event]; Event
0x180061a5f  call    cs:__imp_KeInitializeEvent
0x180061a66  nop     dword ptr [rax+rax+00h]
0x180061a6b  lea     rax, [rsp+188h+Event]
0x180061a73  mov     qword ptr [rsp+188h+pAsync.u], rax
0x180061a7b  mov     [rsp+188h+var_158], r15
0x180061a80  mov     [rsp+188h+var_160], r13d
0x180061a85  mov     rax, [rsp+188h+UnicodeString.Buffer]
0x180061a8a  mov     [rsp+188h+Timeout], rax
0x180061a8f  mov     r9, [rsp+188h+var_108.Buffer]
0x180061a97  mov     r8, [rsp+188h+StringOut.Buffer]
0x180061a9f  mov     rdx, [rsp+188h+Binding]
0x180061aa4  lea     rcx, [rsp+188h+pAsync]
0x180061aac  call    SSCatDBSendSmartAppControlBlockToast2
0x180061ab1  jmp     short loc_180061AC6
0x180061ab3  mov     ebx, eax
0x180061ab5  mov     r13d, [rsp+188h+arg_18]
0x180061abd  mov     esi, [rsp+188h+var_144]
0x180061ac1  mov     r12, [rsp+188h+var_120]
0x180061ac6  test    ebx, ebx
0x180061ac8  jnz     loc_180061A31
0x180061ace  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFB3B4C00h
0x180061ad7  lea     rax, [rsp+188h+Interval]
0x180061adc  mov     [rsp+188h+Timeout], rax; Timeout
0x180061ae1  xor     r9d, r9d; Alertable
0x180061ae4  xor     r8d, r8d; WaitMode
0x180061ae7  xor     edx, edx; WaitReason
0x180061ae9  lea     rcx, [rsp+188h+Event]; Object
0x180061af1  call    cs:__imp_KeWaitForSingleObject
0x180061af8  nop     dword ptr [rax+rax+00h]
0x180061afd  mov     r15d, eax
0x180061b00  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180061b08  test    eax, eax
0x180061b0a  jz      short loc_180061B5E
0x180061b0c  lea     edx, [rbx+1]; fAbort
0x180061b0f  call    cs:__imp_RpcAsyncCancelCall
0x180061b16  nop     dword ptr [rax+rax+00h]
0x180061b1b  mov     [rsp+188h+Timeout], 0; Timeout
0x180061b24  xor     r9d, r9d; Alertable
0x180061b27  xor     r8d, r8d; WaitMode
0x180061b2a  xor     edx, edx; WaitReason
0x180061b2c  lea     rcx, [rsp+188h+Event]; Object
0x180061b34  call    cs:__imp_KeWaitForSingleObject
0x180061b3b  nop     dword ptr [rax+rax+00h]
0x180061b40  lea     rdx, [rsp+188h+Reply]; Reply
0x180061b45  lea     rcx, [rsp+188h+pAsync]; pAsync
0x180061b4d  call    cs:__imp_RpcAsyncCompleteCall
0x180061b54  nop     dword ptr [rax+rax+00h]
0x180061b59  jmp     loc_180061A31
0x180061b5e  lea     rdx, [rsp+188h+Reply]; Reply
0x180061b63  call    cs:__imp_RpcAsyncCompleteCall
0x180061b6a  nop     dword ptr [rax+rax+00h]
0x180061b6f  cmp     eax, 0C0020018h
0x180061b74  jnz     short loc_180061BA9
0x180061b76  cmp     esi, 14h
0x180061b79  jnb     short loc_180061BA9
0x180061b7b  inc     esi
0x180061b7d  mov     [rsp+188h+var_144], esi
0x180061b81  mov     qword ptr [rsp+188h+Interval], 0FFFFFFFFFFF0BDC0h
0x180061b8a  lea     r8, [rsp+188h+Interval]; Interval
0x180061b8f  xor     edx, edx; Alertable
0x180061b91  xor     ecx, ecx; WaitMode
0x180061b93  call    cs:__imp_KeDelayExecutionThread
0x180061b9a  nop     dword ptr [rax+rax+00h]
0x180061b9f  mov     r15, [rsp+188h+var_130]
0x180061ba4  jmp     loc_180061A12
0x180061ba9  mov     ebx, 0C0000001h
0x180061bae  test    eax, eax
0x180061bb0  jnz     short loc_180061BBD
0x180061bb2  cmp     [rsp+188h+Reply], eax
0x180061bb6  cmovnz  r15d, ebx
0x180061bba  mov     ebx, r15d
0x180061bbd  cmp     [rsp+188h+Binding], 0
0x180061bc3  jz      short loc_180061BCF
0x180061bc5  lea     rcx, [rsp+188h+Binding]; Binding
0x180061bca  call    CipCatDbRpcDisconnect
0x180061bcf  lea     rcx, [rsp+188h+ApcState]; ApcState
0x180061bd7  call    cs:__imp_KeUnstackDetachProcess
0x180061bde  nop     dword ptr [rax+rax+00h]
0x180061be3  mov     rcx, r12
0x180061be6  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180061bed  nop     dword ptr [rax+rax+00h]
0x180061bf2  lea     rcx, [rsp+188h+UnicodeString]; UnicodeString
0x180061bf7  call    cs:__imp_RtlFreeUnicodeString
0x180061bfe  nop     dword ptr [rax+rax+00h]
0x180061c03  lea     rcx, [rsp+188h+var_108]; UnicodeString
0x180061c0b  call    cs:__imp_RtlFreeUnicodeString
0x180061c12  nop     dword ptr [rax+rax+00h]
0x180061c17  lea     rcx, [rsp+188h+StringOut]; UnicodeString
0x180061c1f  call    cs:__imp_RtlFreeUnicodeString
0x180061c26  nop     dword ptr [rax+rax+00h]
0x180061c2b  mov     eax, ebx
0x180061c2d  mov     rcx, [rsp+188h+var_38]
0x180061c35  xor     rcx, rsp; StackCookie
0x180061c38  call    __security_check_cookie
0x180061c3d  add     rsp, 160h
0x180061c44  pop     r15
0x180061c46  pop     r13
0x180061c48  pop     r12
0x180061c4a  pop     rsi
0x180061c4b  pop     rbx
0x180061c4c  retn
0x1800e84a4  push    rbp
0x1800e84a6  sub     rsp, 40h
0x1800e84aa  mov     rbp, rdx
0x1800e84ad  mov     rcx, [rcx]
0x1800e84b0  mov     ecx, [rcx]; ExceptionCode
0x1800e84b2  call    cs:__imp_I_RpcExceptionFilter
0x1800e84b9  nop     dword ptr [rax+rax+00h]
0x1800e84be  nop
0x1800e84bf  add     rsp, 40h
0x1800e84c3  pop     rbp
0x1800e84c4  retn
```
