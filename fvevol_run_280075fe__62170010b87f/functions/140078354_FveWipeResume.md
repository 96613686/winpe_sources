# FveWipeResume

- ea: `0x140078354`
- end: `0x14007875e`
- name: `FveWipeResume`
- size: `1034`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140052854`
- `0x140077110`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x14002459c`
- `0x140078354`
- `0x1400795c8`
- `0x140095190`
- `0x14009c2c0`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140078401`
- `ntoskrnl!KeInitializeEvent` at `0x140078401`
- `ntoskrnl!KeClearEvent` at `0x140078471`
- `ntoskrnl!KeClearEvent` at `0x140078484`
- `ntoskrnl!KeClearEvent` at `0x140078497`
- `ntoskrnl!KeClearEvent` at `0x140078471`
- `ntoskrnl!KeClearEvent` at `0x140078484`
- `ntoskrnl!KeClearEvent` at `0x140078497`
- `ntoskrnl!PsCreateSystemThread` at `0x14007851d`
- `ntoskrnl!PsCreateSystemThread` at `0x1400785de`
- `ntoskrnl!PsCreateSystemThread` at `0x14007851d`
- `ntoskrnl!PsCreateSystemThread` at `0x1400785de`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140078559`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007861a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140078559`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007861a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140078682`
- `ntoskrnl!KeWaitForSingleObject` at `0x140078682`
- `ntoskrnl!KeBugCheckEx` at `0x1400784ec`
- `ntoskrnl!KeBugCheckEx` at `0x140078751`
- `ntoskrnl!KeBugCheckEx` at `0x1400784ec`
- `ntoskrnl!KeBugCheckEx` at `0x140078751`
- `ntoskrnl!ZwClose` at `0x140078578`
- `ntoskrnl!ZwClose` at `0x140078639`
- `ntoskrnl!ZwClose` at `0x140078578`
- `ntoskrnl!ZwClose` at `0x140078639`

## pseudocode

```c
__int64 __fastcall FveWipeResume(__int64 *a1, char a2, __int64 a3, bool *a4)
{
  __int64 v8; // r8
  __int64 v9; // rbx
  __int64 v10; // r8
  struct _KEVENT *StartContext; // rbx
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
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  LOBYTE(v8) = 1;
  FvepAcquireDevFveLock(a1, v24, v8);
  v9 = a1[175];
  FvepReleaseDevFveLock(v24);
  if ( v9 )
    FveWipeStopSliderThread(v9);
  LOBYTE(v10) = 1;
  FvepAcquireDevFveLock(a1, v24, v10);
  StartContext = (struct _KEVENT *)a1[175];
  v12 = -1073741811;
  if ( StartContext && !StartContext[21].Header.WaitListHead.Flink )
  {
    KeClearEvent(StartContext + 13);
    KeClearEvent(StartContext + 14);
    KeClearEvent(StartContext + 15);
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    v13 = _InterlockedIncrement(&StartContext->Header.Lock);
    if ( v13 != 2 )
      KeBugCheckEx(0x120u, 0xBu, (ULONG_PTR)StartContext, 0, v13);
    v12 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, FveWipeSliderWorker, StartContext);
    if ( v12 < 0 )
    {
      StartContext[21].Header.WaitListHead.Blink = 0;
      v17 = _InterlockedDecrement(&StartContext->Header.Lock);
      if ( v17 != 1 )
        KeBugCheckEx(0x120u, 0xBu, (ULONG_PTR)StartContext, 0, v17);
    }
    else
    {
      Object = 0;
      ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      StartContext[21].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)Object;
      ZwClose(ThreadHandle);
      ObjectAttributes.Length = 48;
      *((_QWORD *)&v22 + 1) = &Event;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      *(_QWORD *)&v22 = a1;
      v12 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, FveWipePump, &v22);
      if ( v12 < 0 )
      {
        StartContext[21].Header.WaitListHead.Flink = 0;
      }
      else
      {
        Object = 0;
        ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
        StartContext[21].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)Object;
        ZwClose(ThreadHandle);
        if ( a2 )
          *a4 = (int)FveWrqAddRequest(a1, a3, v14, &StartContext[28].Header.WaitListHead) < 0;
      }
    }
  }
  FvepReleaseDevFveLock(v24);
  if ( v12 >= 0 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    FveRaiseStatusChangedEvent(a1, 15);
  }
  v15 = *a1;
  *(_QWORD *)&v20 = FVE_CONV_RESUME;
  *((_DWORD *)a1 + 360) = v12;
  DWORD2(v20) = 0;
  HIDWORD(v20) = v12;
  v21 = 0;
  FveLogEvent(v15, &v20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      100,
      WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140078354  push    rbp
0x140078356  push    rbx
0x140078357  push    rsi
0x140078358  push    rdi
0x140078359  push    r12
0x14007835b  push    r13
0x14007835d  push    r14
0x14007835f  push    r15
0x140078361  lea     rbp, [rsp-58h]
0x140078366  sub     rsp, 158h
0x14007836d  xorps   xmm0, xmm0
0x140078370  mov     r15, r8
0x140078373  mov     r12b, dl
0x140078376  mov     rsi, rcx
0x140078379  xor     eax, eax
0x14007837b  lea     rcx, [rbp+90h+var_D0]; void *
0x14007837f  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x140078384  xor     r13d, r13d
0x140078387  mov     [rbp+90h+var_108], rax
0x14007838b  xor     edx, edx; Val
0x14007838d  mov     [rbp+90h+ThreadHandle], r13
0x140078394  mov     r8d, 90h; Size
0x14007839a  mov     r14, r9
0x14007839d  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x1400783a2  movups  [rsp+190h+var_118], xmm0
0x1400783a7  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x1400783ac  call    memset
0x1400783b1  xorps   xmm0, xmm0
0x1400783b4  xor     eax, eax
0x1400783b6  movups  xmmword ptr [rbp+90h+Event.Header], xmm0
0x1400783ba  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x1400783be  movups  [rbp+90h+var_100], xmm0
0x1400783c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400783c9  lea     rax, WPP_GLOBAL_Control
0x1400783d0  cmp     rcx, rax
0x1400783d3  jz      short loc_1400783F8
0x1400783d5  test    dword ptr [rcx+2Ch], 1000h
0x1400783dc  jz      short loc_1400783F8
0x1400783de  cmp     byte ptr [rcx+29h], 5
0x1400783e2  jb      short loc_1400783F8
0x1400783e4  mov     rcx, [rcx+18h]
0x1400783e8  lea     edx, [r13+63h]
0x1400783ec  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400783f3  call    WPP_SF_
0x1400783f8  xor     r8d, r8d; State
0x1400783fb  lea     rcx, [rbp+90h+Event]; Event
0x1400783ff  xor     edx, edx; Type
0x140078401  call    cs:__imp_KeInitializeEvent
0x140078408  nop     dword ptr [rax+rax+00h]
0x14007840d  mov     r8b, 1
0x140078410  lea     rdx, [rbp+90h+var_D0]
0x140078414  mov     rcx, rsi
0x140078417  call    FvepAcquireDevFveLock
0x14007841c  mov     rbx, [rsi+578h]
0x140078423  lea     rcx, [rbp+90h+var_D0]
0x140078427  call    FvepReleaseDevFveLock
0x14007842c  test    rbx, rbx
0x14007842f  jz      short loc_140078439
0x140078431  mov     rcx, rbx
0x140078434  call    FveWipeStopSliderThread
0x140078439  mov     r8b, 1
0x14007843c  lea     rdx, [rbp+90h+var_D0]
0x140078440  mov     rcx, rsi
0x140078443  call    FvepAcquireDevFveLock
0x140078448  mov     rbx, [rsi+578h]
0x14007844f  mov     edi, 0C000000Dh
0x140078454  test    rbx, rbx
0x140078457  jz      loc_140078664
0x14007845d  cmp     [rbx+200h], r13
0x140078464  jnz     loc_140078664
0x14007846a  lea     rcx, [rbx+138h]; Event
0x140078471  call    cs:__imp_KeClearEvent
0x140078478  nop     dword ptr [rax+rax+00h]
0x14007847d  lea     rcx, [rbx+150h]; Event
0x140078484  call    cs:__imp_KeClearEvent
0x14007848b  nop     dword ptr [rax+rax+00h]
0x140078490  lea     rcx, [rbx+168h]; Event
0x140078497  call    cs:__imp_KeClearEvent
0x14007849e  nop     dword ptr [rax+rax+00h]
0x1400784a3  xorps   xmm0, xmm0
0x1400784a6  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400784ae  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400784b4  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x1400784b9  mov     eax, 1
0x1400784be  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x1400784c6  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x1400784cb  lock xadd [rbx], eax
0x1400784cf  inc     eax
0x1400784d1  xor     r9d, r9d; ProcessHandle
0x1400784d4  cmp     eax, 2
0x1400784d7  jz      short loc_1400784F9
0x1400784d9  cdqe
0x1400784db  lea     edx, [r9+0Bh]; BugCheckParameter1
0x1400784df  mov     r8, rbx; BugCheckParameter2
0x1400784e2  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x1400784e7  mov     ecx, 120h; BugCheckCode
0x1400784ec  call    cs:__imp_KeBugCheckEx
0x1400784f9  lea     rax, FveWipeSliderWorker
0x140078500  mov     [rsp+190h+StartContext], rbx; StartContext
0x140078505  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14007850a  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14007850f  xor     edx, edx; DesiredAccess
0x140078511  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x140078516  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14007851d  call    cs:__imp_PsCreateSystemThread
0x140078524  nop     dword ptr [rax+rax+00h]
0x140078529  mov     edi, eax
0x14007852b  test    eax, eax
0x14007852d  js      loc_140078722
0x140078533  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14007853a  lea     rax, [rsp+190h+Object]
0x14007853f  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x140078544  xor     r9d, r9d; AccessMode
0x140078547  xor     r8d, r8d; ObjectType
0x14007854a  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14007854f  mov     edx, 1FFFFFh; DesiredAccess
0x140078554  mov     [rsp+190h+Object], r13
0x140078559  call    cs:__imp_ObReferenceObjectByHandle
0x140078560  nop     dword ptr [rax+rax+00h]
0x140078565  mov     rax, [rsp+190h+Object]
0x14007856a  mov     [rbx+208h], rax
0x140078571  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x140078578  call    cs:__imp_ZwClose
0x14007857f  nop     dword ptr [rax+rax+00h]
0x140078584  lea     rax, [rbp+90h+Event]
0x140078588  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x140078590  mov     qword ptr [rbp+90h+var_100+8], rax
0x140078594  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x140078599  lea     rax, [rbp+90h+var_100]
0x14007859d  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x1400785a2  mov     [rsp+190h+StartContext], rax; StartContext
0x1400785a7  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x1400785ae  lea     rax, FveWipePump
0x1400785b5  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x1400785bd  xorps   xmm0, xmm0
0x1400785c0  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x1400785c5  xor     r9d, r9d; ProcessHandle
0x1400785c8  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x1400785cd  xor     edx, edx; DesiredAccess
0x1400785cf  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x1400785d4  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400785da  mov     qword ptr [rbp+90h+var_100], rsi
0x1400785de  call    cs:__imp_PsCreateSystemThread
0x1400785e5  nop     dword ptr [rax+rax+00h]
0x1400785ea  mov     edi, eax
0x1400785ec  test    eax, eax
0x1400785ee  js      loc_140078716
0x1400785f4  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x1400785fb  lea     rax, [rsp+190h+Object]
0x140078600  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x140078605  xor     r9d, r9d; AccessMode
0x140078608  xor     r8d, r8d; ObjectType
0x14007860b  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x140078610  mov     edx, 1FFFFFh; DesiredAccess
0x140078615  mov     [rsp+190h+Object], r13
0x14007861a  call    cs:__imp_ObReferenceObjectByHandle
0x140078621  nop     dword ptr [rax+rax+00h]
0x140078626  mov     rax, [rsp+190h+Object]
0x14007862b  mov     [rbx+200h], rax
0x140078632  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x140078639  call    cs:__imp_ZwClose
0x140078640  nop     dword ptr [rax+rax+00h]
0x140078645  test    r12b, r12b
0x140078648  jz      short loc_140078664
0x14007864a  lea     r9, [rbx+2A8h]
0x140078651  mov     rdx, r15
0x140078654  mov     rcx, rsi
0x140078657  call    FveWrqAddRequest
0x14007865c  test    eax, eax
0x14007865e  sets    al
0x140078661  mov     [r14], al
0x140078664  lea     rcx, [rbp+90h+var_D0]
0x140078668  call    FvepReleaseDevFveLock
0x14007866d  test    edi, edi
0x14007866f  js      short loc_14007869B
0x140078671  xor     r9d, r9d; Alertable
0x140078674  mov     [rsp+190h+BugCheckParameter4], r13; Timeout
0x140078679  xor     r8d, r8d; WaitMode
0x14007867c  lea     rcx, [rbp+90h+Event]; Object
0x140078680  xor     edx, edx; WaitReason
0x140078682  call    cs:__imp_KeWaitForSingleObject
0x140078689  nop     dword ptr [rax+rax+00h]
0x14007868e  mov     edx, 0Fh
0x140078693  mov     rcx, rsi
0x140078696  call    FveRaiseStatusChangedEvent
0x14007869b  mov     rcx, [rsi]
0x14007869e  lea     rax, FVE_CONV_RESUME
0x1400786a5  lea     rdx, [rsp+190h+var_118]
0x1400786aa  mov     qword ptr [rsp+190h+var_118], rax
0x1400786af  mov     [rsi+5A0h], edi
0x1400786b5  mov     dword ptr [rbp+90h+var_118+8], r13d
0x1400786b9  mov     dword ptr [rbp+90h+var_118+0Ch], edi
0x1400786bc  mov     [rbp+90h+var_108], r13
0x1400786c0  call    FveLogEvent
0x1400786c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400786cc  lea     rax, WPP_GLOBAL_Control
0x1400786d3  cmp     rcx, rax
0x1400786d6  jz      short loc_1400786FF
0x1400786d8  test    dword ptr [rcx+2Ch], 1000h
0x1400786df  jz      short loc_1400786FF
0x1400786e1  cmp     byte ptr [rcx+29h], 5
0x1400786e5  jb      short loc_1400786FF
0x1400786e7  mov     rcx, [rcx+18h]
0x1400786eb  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x1400786f2  mov     edx, 64h ; 'd'
0x1400786f7  mov     r9d, edi
0x1400786fa  call    WPP_SF_d
0x1400786ff  mov     eax, edi
0x140078701  add     rsp, 158h
0x140078708  pop     r15
0x14007870a  pop     r14
0x14007870c  pop     r13
0x14007870e  pop     r12
0x140078710  pop     rdi
0x140078711  pop     rsi
0x140078712  pop     rbx
0x140078713  pop     rbp
0x140078714  retn
0x140078716  mov     [rbx+200h], r13
0x14007871d  jmp     loc_140078664
0x140078722  mov     [rbx+208h], r13
0x140078729  or      eax, 0FFFFFFFFh
0x14007872c  lock xadd [rbx], eax
0x140078730  dec     eax
0x140078732  cmp     eax, 1
0x140078735  jz      loc_140078664
0x14007873b  xor     r9d, r9d; BugCheckParameter3
0x14007873e  cdqe
0x140078740  mov     r8, rbx; BugCheckParameter2
0x140078743  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x140078748  mov     ecx, 120h; BugCheckCode
0x14007874d  lea     edx, [r9+0Bh]; BugCheckParameter1
0x140078751  call    cs:__imp_KeBugCheckEx
```
