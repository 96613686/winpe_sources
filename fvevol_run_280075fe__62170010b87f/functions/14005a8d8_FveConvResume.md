# FveConvResume

- ea: `0x14005a8d8`
- end: `0x14005acdf`
- name: `FveConvResume`
- size: `1031`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140052854`
- `0x140056e20`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x14002459c`
- `0x14005a8d8`
- `0x14005b0d0`
- `0x140095190`
- `0x14009c2c0`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005a984`
- `ntoskrnl!KeInitializeEvent` at `0x14005a984`
- `ntoskrnl!KeClearEvent` at `0x14005a9f4`
- `ntoskrnl!KeClearEvent` at `0x14005aa07`
- `ntoskrnl!KeClearEvent` at `0x14005aa1a`
- `ntoskrnl!KeClearEvent` at `0x14005a9f4`
- `ntoskrnl!KeClearEvent` at `0x14005aa07`
- `ntoskrnl!KeClearEvent` at `0x14005aa1a`
- `ntoskrnl!PsCreateSystemThread` at `0x14005aaa0`
- `ntoskrnl!PsCreateSystemThread` at `0x14005ab61`
- `ntoskrnl!PsCreateSystemThread` at `0x14005aaa0`
- `ntoskrnl!PsCreateSystemThread` at `0x14005ab61`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005aadc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005ab9d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005aadc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005ab9d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ac05`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ac05`
- `ntoskrnl!KeBugCheckEx` at `0x14005aa6f`
- `ntoskrnl!KeBugCheckEx` at `0x14005acd2`
- `ntoskrnl!KeBugCheckEx` at `0x14005aa6f`
- `ntoskrnl!KeBugCheckEx` at `0x14005acd2`
- `ntoskrnl!ZwClose` at `0x14005aafb`
- `ntoskrnl!ZwClose` at `0x14005abbc`
- `ntoskrnl!ZwClose` at `0x14005aafb`
- `ntoskrnl!ZwClose` at `0x14005abbc`

## pseudocode

```c
__int64 __fastcall FveConvResume(__int64 *a1, char a2, __int64 a3, bool *a4)
{
  __int64 v8; // r8
  __int64 v9; // rbx
  __int64 v10; // r8
  ULONG_PTR StartContext; // rbx
  NTSTATUS v12; // edi
  signed __int32 v13; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  signed __int32 v17; // eax
  PVOID Object; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  struct _KEVENT Event; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[208]; // [rsp+C0h] [rbp-40h] BYREF
  void *ThreadHandle; // [rsp+1A0h] [rbp+A0h] BYREF

  v21 = 0;
  ThreadHandle = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(v24, 0, 0x90u);
  memset(&Event, 0, sizeof(Event));
  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  LOBYTE(v8) = 1;
  FvepAcquireDevFveLock(a1, v24, v8);
  v9 = a1[174];
  FvepReleaseDevFveLock(v24);
  if ( v9 )
    FveConvStopSliderThread(v9);
  LOBYTE(v10) = 1;
  FvepAcquireDevFveLock(a1, v24, v10);
  StartContext = a1[174];
  v12 = -1073741811;
  if ( StartContext && !*(_QWORD *)(StartContext + 576) )
  {
    KeClearEvent((PRKEVENT)(StartContext + 440));
    KeClearEvent((PRKEVENT)(StartContext + 464));
    KeClearEvent((PRKEVENT)(StartContext + 488));
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    v13 = _InterlockedIncrement((volatile signed __int32 *)StartContext);
    if ( v13 != 2 )
      KeBugCheckEx(0x120u, 0xBu, StartContext, 0, v13);
    v12 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, FveConvSliderWorker, (PVOID)StartContext);
    if ( v12 < 0 )
    {
      *(_QWORD *)(StartContext + 584) = 0;
      v17 = _InterlockedDecrement((volatile signed __int32 *)StartContext);
      if ( v17 != 1 )
        KeBugCheckEx(0x120u, 0xBu, StartContext, 0, v17);
    }
    else
    {
      Object = 0;
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      *(_QWORD *)(StartContext + 584) = Object;
      ZwClose(ThreadHandle);
      ObjectAttributes.Length = 48;
      *((_QWORD *)&v22 + 1) = &Event;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      *(_QWORD *)&v22 = a1;
      v12 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, FveConvPump, &v22);
      if ( v12 < 0 )
      {
        *(_QWORD *)(StartContext + 576) = 0;
      }
      else
      {
        Object = 0;
        ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
        *(_QWORD *)(StartContext + 576) = Object;
        ZwClose(ThreadHandle);
        if ( a2 )
          *a4 = (int)FveWrqAddRequest(a1, a3, v14, StartContext + 744) < 0;
      }
    }
  }
  FvepReleaseDevFveLock(v24);
  if ( v12 >= 0 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    FveRaiseStatusChangedEvent(a1, 10);
  }
  v15 = *a1;
  *(_QWORD *)&v20 = FVE_CONV_RESUME;
  *((_DWORD *)a1 + 360) = v12;
  DWORD2(v20) = 0;
  HIDWORD(v20) = v12;
  v21 = 0;
  FveLogEvent(v15, &v20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      208,
      WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005a8d8  push    rbp
0x14005a8da  push    rbx
0x14005a8db  push    rsi
0x14005a8dc  push    rdi
0x14005a8dd  push    r12
0x14005a8df  push    r13
0x14005a8e1  push    r14
0x14005a8e3  push    r15
0x14005a8e5  lea     rbp, [rsp-58h]
0x14005a8ea  sub     rsp, 158h
0x14005a8f1  xorps   xmm0, xmm0
0x14005a8f4  mov     r15, r8
0x14005a8f7  mov     r12b, dl
0x14005a8fa  mov     rsi, rcx
0x14005a8fd  xor     eax, eax
0x14005a8ff  lea     rcx, [rbp+90h+var_D0]; void *
0x14005a903  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x14005a908  xor     r13d, r13d
0x14005a90b  mov     [rbp+90h+var_108], rax
0x14005a90f  xor     edx, edx; Val
0x14005a911  mov     [rbp+90h+ThreadHandle], r13
0x14005a918  mov     r8d, 90h; Size
0x14005a91e  mov     r14, r9
0x14005a921  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x14005a926  movups  [rsp+190h+var_118], xmm0
0x14005a92b  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x14005a930  call    memset
0x14005a935  xorps   xmm0, xmm0
0x14005a938  xor     eax, eax
0x14005a93a  movups  xmmword ptr [rbp+90h+Event.Header], xmm0
0x14005a93e  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x14005a942  movups  [rbp+90h+var_100], xmm0
0x14005a946  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a94d  lea     rax, WPP_GLOBAL_Control
0x14005a954  cmp     rcx, rax
0x14005a957  jz      short loc_14005A97B
0x14005a959  mov     eax, [rcx+2Ch]
0x14005a95c  test    al, 2
0x14005a95e  jz      short loc_14005A97B
0x14005a960  cmp     byte ptr [rcx+29h], 5
0x14005a964  jb      short loc_14005A97B
0x14005a966  mov     rcx, [rcx+18h]
0x14005a96a  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x14005a971  mov     edx, 0CFh
0x14005a976  call    WPP_SF_
0x14005a97b  xor     r8d, r8d; State
0x14005a97e  lea     rcx, [rbp+90h+Event]; Event
0x14005a982  xor     edx, edx; Type
0x14005a984  call    cs:__imp_KeInitializeEvent
0x14005a98b  nop     dword ptr [rax+rax+00h]
0x14005a990  mov     r8b, 1
0x14005a993  lea     rdx, [rbp+90h+var_D0]
0x14005a997  mov     rcx, rsi
0x14005a99a  call    FvepAcquireDevFveLock
0x14005a99f  mov     rbx, [rsi+570h]
0x14005a9a6  lea     rcx, [rbp+90h+var_D0]
0x14005a9aa  call    FvepReleaseDevFveLock
0x14005a9af  test    rbx, rbx
0x14005a9b2  jz      short loc_14005A9BC
0x14005a9b4  mov     rcx, rbx
0x14005a9b7  call    FveConvStopSliderThread
0x14005a9bc  mov     r8b, 1
0x14005a9bf  lea     rdx, [rbp+90h+var_D0]
0x14005a9c3  mov     rcx, rsi
0x14005a9c6  call    FvepAcquireDevFveLock
0x14005a9cb  mov     rbx, [rsi+570h]
0x14005a9d2  mov     edi, 0C000000Dh
0x14005a9d7  test    rbx, rbx
0x14005a9da  jz      loc_14005ABE7
0x14005a9e0  cmp     [rbx+240h], r13
0x14005a9e7  jnz     loc_14005ABE7
0x14005a9ed  lea     rcx, [rbx+1B8h]; Event
0x14005a9f4  call    cs:__imp_KeClearEvent
0x14005a9fb  nop     dword ptr [rax+rax+00h]
0x14005aa00  lea     rcx, [rbx+1D0h]; Event
0x14005aa07  call    cs:__imp_KeClearEvent
0x14005aa0e  nop     dword ptr [rax+rax+00h]
0x14005aa13  lea     rcx, [rbx+1E8h]; Event
0x14005aa1a  call    cs:__imp_KeClearEvent
0x14005aa21  nop     dword ptr [rax+rax+00h]
0x14005aa26  xorps   xmm0, xmm0
0x14005aa29  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14005aa31  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005aa37  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14005aa3c  mov     eax, 1
0x14005aa41  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14005aa49  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14005aa4e  lock xadd [rbx], eax
0x14005aa52  inc     eax
0x14005aa54  xor     r9d, r9d; ProcessHandle
0x14005aa57  cmp     eax, 2
0x14005aa5a  jz      short loc_14005AA7C
0x14005aa5c  cdqe
0x14005aa5e  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14005aa62  mov     r8, rbx; BugCheckParameter2
0x14005aa65  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14005aa6a  mov     ecx, 120h; BugCheckCode
0x14005aa6f  call    cs:__imp_KeBugCheckEx
0x14005aa7c  lea     rax, FveConvSliderWorker
0x14005aa83  mov     [rsp+190h+StartContext], rbx; StartContext
0x14005aa88  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14005aa8d  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14005aa92  xor     edx, edx; DesiredAccess
0x14005aa94  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14005aa99  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14005aaa0  call    cs:__imp_PsCreateSystemThread
0x14005aaa7  nop     dword ptr [rax+rax+00h]
0x14005aaac  mov     edi, eax
0x14005aaae  test    eax, eax
0x14005aab0  js      loc_14005ACA3
0x14005aab6  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005aabd  lea     rax, [rsp+190h+Object]
0x14005aac2  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14005aac7  xor     r9d, r9d; AccessMode
0x14005aaca  xor     r8d, r8d; ObjectType
0x14005aacd  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14005aad2  mov     edx, 1FFFFFh; DesiredAccess
0x14005aad7  mov     [rsp+190h+Object], r13
0x14005aadc  call    cs:__imp_ObReferenceObjectByHandle
0x14005aae3  nop     dword ptr [rax+rax+00h]
0x14005aae8  mov     rax, [rsp+190h+Object]
0x14005aaed  mov     [rbx+248h], rax
0x14005aaf4  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005aafb  call    cs:__imp_ZwClose
0x14005ab02  nop     dword ptr [rax+rax+00h]
0x14005ab07  lea     rax, [rbp+90h+Event]
0x14005ab0b  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14005ab13  mov     qword ptr [rbp+90h+var_100+8], rax
0x14005ab17  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14005ab1c  lea     rax, [rbp+90h+var_100]
0x14005ab20  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14005ab25  mov     [rsp+190h+StartContext], rax; StartContext
0x14005ab2a  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14005ab31  lea     rax, FveConvPump
0x14005ab38  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14005ab40  xorps   xmm0, xmm0
0x14005ab43  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14005ab48  xor     r9d, r9d; ProcessHandle
0x14005ab4b  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14005ab50  xor     edx, edx; DesiredAccess
0x14005ab52  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14005ab57  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005ab5d  mov     qword ptr [rbp+90h+var_100], rsi
0x14005ab61  call    cs:__imp_PsCreateSystemThread
0x14005ab68  nop     dword ptr [rax+rax+00h]
0x14005ab6d  mov     edi, eax
0x14005ab6f  test    eax, eax
0x14005ab71  js      loc_14005AC97
0x14005ab77  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005ab7e  lea     rax, [rsp+190h+Object]
0x14005ab83  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14005ab88  xor     r9d, r9d; AccessMode
0x14005ab8b  xor     r8d, r8d; ObjectType
0x14005ab8e  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14005ab93  mov     edx, 1FFFFFh; DesiredAccess
0x14005ab98  mov     [rsp+190h+Object], r13
0x14005ab9d  call    cs:__imp_ObReferenceObjectByHandle
0x14005aba4  nop     dword ptr [rax+rax+00h]
0x14005aba9  mov     rax, [rsp+190h+Object]
0x14005abae  mov     [rbx+240h], rax
0x14005abb5  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005abbc  call    cs:__imp_ZwClose
0x14005abc3  nop     dword ptr [rax+rax+00h]
0x14005abc8  test    r12b, r12b
0x14005abcb  jz      short loc_14005ABE7
0x14005abcd  lea     r9, [rbx+2E8h]
0x14005abd4  mov     rdx, r15
0x14005abd7  mov     rcx, rsi
0x14005abda  call    FveWrqAddRequest
0x14005abdf  test    eax, eax
0x14005abe1  sets    al
0x14005abe4  mov     [r14], al
0x14005abe7  lea     rcx, [rbp+90h+var_D0]
0x14005abeb  call    FvepReleaseDevFveLock
0x14005abf0  test    edi, edi
0x14005abf2  js      short loc_14005AC1E
0x14005abf4  xor     r9d, r9d; Alertable
0x14005abf7  mov     [rsp+190h+BugCheckParameter4], r13; Timeout
0x14005abfc  xor     r8d, r8d; WaitMode
0x14005abff  lea     rcx, [rbp+90h+Event]; Object
0x14005ac03  xor     edx, edx; WaitReason
0x14005ac05  call    cs:__imp_KeWaitForSingleObject
0x14005ac0c  nop     dword ptr [rax+rax+00h]
0x14005ac11  mov     edx, 0Ah
0x14005ac16  mov     rcx, rsi
0x14005ac19  call    FveRaiseStatusChangedEvent
0x14005ac1e  mov     rcx, [rsi]
0x14005ac21  lea     rax, FVE_CONV_RESUME
0x14005ac28  lea     rdx, [rsp+190h+var_118]
0x14005ac2d  mov     qword ptr [rsp+190h+var_118], rax
0x14005ac32  mov     [rsi+5A0h], edi
0x14005ac38  mov     dword ptr [rbp+90h+var_118+8], r13d
0x14005ac3c  mov     dword ptr [rbp+90h+var_118+0Ch], edi
0x14005ac3f  mov     [rbp+90h+var_108], r13
0x14005ac43  call    FveLogEvent
0x14005ac48  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac4f  lea     rax, WPP_GLOBAL_Control
0x14005ac56  cmp     rcx, rax
0x14005ac59  jz      short loc_14005AC80
0x14005ac5b  mov     eax, [rcx+2Ch]
0x14005ac5e  test    al, 2
0x14005ac60  jz      short loc_14005AC80
0x14005ac62  cmp     byte ptr [rcx+29h], 5
0x14005ac66  jb      short loc_14005AC80
0x14005ac68  mov     rcx, [rcx+18h]
0x14005ac6c  lea     r8, WPP_eba5d79693a933162ee0ce8e293fa86a_Traceguids
0x14005ac73  mov     edx, 0D0h
0x14005ac78  mov     r9d, edi
0x14005ac7b  call    WPP_SF_d
0x14005ac80  mov     eax, edi
0x14005ac82  add     rsp, 158h
0x14005ac89  pop     r15
0x14005ac8b  pop     r14
0x14005ac8d  pop     r13
0x14005ac8f  pop     r12
0x14005ac91  pop     rdi
0x14005ac92  pop     rsi
0x14005ac93  pop     rbx
0x14005ac94  pop     rbp
0x14005ac95  retn
0x14005ac97  mov     [rbx+240h], r13
0x14005ac9e  jmp     loc_14005ABE7
0x14005aca3  mov     [rbx+248h], r13
0x14005acaa  or      eax, 0FFFFFFFFh
0x14005acad  lock xadd [rbx], eax
0x14005acb1  dec     eax
0x14005acb3  cmp     eax, 1
0x14005acb6  jz      loc_14005ABE7
0x14005acbc  xor     r9d, r9d; BugCheckParameter3
0x14005acbf  cdqe
0x14005acc1  mov     r8, rbx; BugCheckParameter2
0x14005acc4  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14005acc9  mov     ecx, 120h; BugCheckCode
0x14005acce  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14005acd2  call    cs:__imp_KeBugCheckEx
```
