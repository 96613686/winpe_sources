# HidpCallDriverSynchronous

- ea: `0x18003de60`
- end: `0x18003dfc6`
- name: `HidpCallDriverSynchronous`
- size: `358`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008a80`
- `0x180037008`
- `0x18003d8fc`
- `0x18003da1c`
- `0x18003f2b4`
- `0x180042b00`

## callees

- `0x18000a020`
- `0x180019350`
- `0x18003de60`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18003de95`
- `ntoskrnl!KeInitializeEvent` at `0x18003de95`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003deeb`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003df6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003deeb`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003df6c`
- `ntoskrnl!IoCancelIrp` at `0x18003df4a`
- `ntoskrnl!IoCancelIrp` at `0x18003df4a`

## pseudocode

```c
__int64 __fastcall HidpCallDriverSynchronous(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 result; // rax
  int v7; // edx
  int v8; // r8d
  int Timeout; // [rsp+20h] [rbp-68h]
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))HidpSynchronousCallCompletion;
  CurrentStackLocation[-1].Context = &Event;
  CurrentStackLocation[-1].Control = -32;
  result = HidpCallDriver(a1, (ULONG_PTR)a2);
  if ( (_DWORD)result == 259 )
  {
    if ( KeWaitForSingleObject(&Event, Executive, 0, 0, &::Timeout) == 258 )
    {
      LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, v7, v8, *(_QWORD *)(v2 + 704), Timeout);
      }
      IoCancelIrp(a2);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      result = (unsigned int)a2->IoStatus.Status;
      if ( (_DWORD)result == -1073741536 )
        result = 3221225653LL;
      a2->IoStatus.Status = result;
    }
    else
    {
      return (unsigned int)a2->IoStatus.Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003de60  mov     [rsp+arg_0], rbx
0x18003de65  mov     [rsp+arg_8], rsi
0x18003de6a  push    rdi
0x18003de6b  sub     rsp, 80h
0x18003de72  mov     rsi, [rcx+40h]
0x18003de76  mov     rbx, rdx
0x18003de79  mov     rdi, rcx
0x18003de7c  xorps   xmm0, xmm0
0x18003de7f  xor     eax, eax
0x18003de81  lea     rcx, [rsp+88h+Event]; Event
0x18003de86  xor     edx, edx; Type
0x18003de88  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x18003de8d  xor     r8d, r8d; State
0x18003de90  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x18003de95  call    cs:__imp_KeInitializeEvent
0x18003de9c  nop     dword ptr [rax+rax+00h]
0x18003dea1  mov     rax, [rbx+0B8h]
0x18003dea8  lea     rcx, HidpSynchronousCallCompletion
0x18003deaf  mov     rdx, rbx
0x18003deb2  mov     [rax-10h], rcx
0x18003deb6  lea     rcx, [rsp+88h+Event]
0x18003debb  mov     [rax-8], rcx
0x18003debf  mov     rcx, rdi
0x18003dec2  mov     byte ptr [rax-45h], 0E0h
0x18003dec6  call    HidpCallDriver
0x18003decb  cmp     eax, 103h
0x18003ded0  jnz     short loc_18003DF01
0x18003ded2  lea     rax, Timeout
0x18003ded9  xor     r9d, r9d; Alertable
0x18003dedc  xor     r8d, r8d; WaitMode
0x18003dedf  mov     qword ptr [rsp+88h+Timeout], rax; Timeout
0x18003dee4  xor     edx, edx; WaitReason
0x18003dee6  lea     rcx, [rsp+88h+Event]; Object
0x18003deeb  call    cs:__imp_KeWaitForSingleObject
0x18003def2  nop     dword ptr [rax+rax+00h]
0x18003def7  cmp     eax, 102h
0x18003defc  jz      short loc_18003DF17
0x18003defe  mov     eax, [rbx+30h]
0x18003df01  lea     r11, [rsp+88h+var_8]
0x18003df09  mov     rbx, [r11+10h]
0x18003df0d  mov     rsi, [r11+18h]
0x18003df11  mov     rsp, r11
0x18003df14  pop     rdi
0x18003df15  retn
0x18003df17  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df1e  lea     rax, WPP_GLOBAL_Control
0x18003df25  cmp     rcx, rax
0x18003df28  jnz     short loc_18003DF90
0x18003df2a  xor     dl, dl
0x18003df2c  lea     rax, WPP_RECORDER_INITIALIZED
0x18003df33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003df3a  setnz   r8b
0x18003df3e  test    dl, dl
0x18003df40  jnz     short loc_18003DFA1
0x18003df42  test    r8b, r8b
0x18003df45  jnz     short loc_18003DFA1
0x18003df47  mov     rcx, rbx; Irp
0x18003df4a  call    cs:__imp_IoCancelIrp
0x18003df51  nop     dword ptr [rax+rax+00h]
0x18003df56  xor     r9d, r9d; Alertable
0x18003df59  mov     qword ptr [rsp+88h+Timeout], 0; Timeout
0x18003df62  xor     r8d, r8d; WaitMode
0x18003df65  lea     rcx, [rsp+88h+Event]; Object
0x18003df6a  xor     edx, edx; WaitReason
0x18003df6c  call    cs:__imp_KeWaitForSingleObject
0x18003df73  nop     dword ptr [rax+rax+00h]
0x18003df78  mov     eax, [rbx+30h]
0x18003df7b  mov     ecx, 0C00000B5h
0x18003df80  cmp     eax, 0C0000120h
0x18003df85  cmovz   eax, ecx
0x18003df88  mov     [rbx+30h], eax
0x18003df8b  jmp     loc_18003DF01
0x18003df90  mov     eax, [rcx+2Ch]
0x18003df93  test    al, 8
0x18003df95  jz      short loc_18003DF2A
0x18003df97  cmp     byte ptr [rcx+29h], 3
0x18003df9b  jb      short loc_18003DF2A
0x18003df9d  mov     dl, 1
0x18003df9f  jmp     short loc_18003DF2C
0x18003dfa1  mov     rax, [rsi+20h]
0x18003dfa5  mov     r9, [rsi+2C0h]
0x18003dfac  mov     rcx, [rcx+18h]
0x18003dfb0  mov     [rsp+88h+var_38], rbx
0x18003dfb5  mov     [rsp+88h+var_40], rdi
0x18003dfba  mov     [rsp+88h+var_48], rax
0x18003dfbf  call    WPP_RECORDER_AND_TRACE_SF_qqq
0x18003dfc4  jmp     short loc_18003DF47
```
