# FveWipeResume

- ea: `0x14007a384`
- end: `0x14007a78e`
- name: `FveWipeResume`
- size: `1034`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005485c`
- `0x140079140`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14002559c`
- `0x14007a384`
- `0x14007b5f8`
- `0x140097240`
- `0x14009e2c0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14007a431`
- `ntoskrnl!KeInitializeEvent` at `0x14007a431`
- `ntoskrnl!KeClearEvent` at `0x14007a4a1`
- `ntoskrnl!KeClearEvent` at `0x14007a4b4`
- `ntoskrnl!KeClearEvent` at `0x14007a4c7`
- `ntoskrnl!KeClearEvent` at `0x14007a4a1`
- `ntoskrnl!KeClearEvent` at `0x14007a4b4`
- `ntoskrnl!KeClearEvent` at `0x14007a4c7`
- `ntoskrnl!PsCreateSystemThread` at `0x14007a54d`
- `ntoskrnl!PsCreateSystemThread` at `0x14007a60e`
- `ntoskrnl!PsCreateSystemThread` at `0x14007a54d`
- `ntoskrnl!PsCreateSystemThread` at `0x14007a60e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007a589`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007a64a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007a589`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14007a64a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007a6b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007a6b2`
- `ntoskrnl!KeBugCheckEx` at `0x14007a51c`
- `ntoskrnl!KeBugCheckEx` at `0x14007a781`
- `ntoskrnl!KeBugCheckEx` at `0x14007a51c`
- `ntoskrnl!KeBugCheckEx` at `0x14007a781`
- `ntoskrnl!ZwClose` at `0x14007a5a8`
- `ntoskrnl!ZwClose` at `0x14007a669`
- `ntoskrnl!ZwClose` at `0x14007a5a8`
- `ntoskrnl!ZwClose` at `0x14007a669`

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
0x14007a384  push    rbp
0x14007a386  push    rbx
0x14007a387  push    rsi
0x14007a388  push    rdi
0x14007a389  push    r12
0x14007a38b  push    r13
0x14007a38d  push    r14
0x14007a38f  push    r15
0x14007a391  lea     rbp, [rsp-58h]
0x14007a396  sub     rsp, 158h
0x14007a39d  xorps   xmm0, xmm0
0x14007a3a0  mov     r15, r8
0x14007a3a3  mov     r12b, dl
0x14007a3a6  mov     rsi, rcx
0x14007a3a9  xor     eax, eax
0x14007a3ab  lea     rcx, [rbp+90h+var_D0]; void *
0x14007a3af  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x14007a3b4  xor     r13d, r13d
0x14007a3b7  mov     [rbp+90h+var_108], rax
0x14007a3bb  xor     edx, edx; Val
0x14007a3bd  mov     [rbp+90h+ThreadHandle], r13
0x14007a3c4  mov     r8d, 90h; Size
0x14007a3ca  mov     r14, r9
0x14007a3cd  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x14007a3d2  movups  [rsp+190h+var_118], xmm0
0x14007a3d7  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x14007a3dc  call    memset
0x14007a3e1  xorps   xmm0, xmm0
0x14007a3e4  xor     eax, eax
0x14007a3e6  movups  xmmword ptr [rbp+90h+Event.Header], xmm0
0x14007a3ea  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x14007a3ee  movups  [rbp+90h+var_100], xmm0
0x14007a3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a3f9  lea     rax, WPP_GLOBAL_Control
0x14007a400  cmp     rcx, rax
0x14007a403  jz      short loc_14007A428
0x14007a405  test    dword ptr [rcx+2Ch], 1000h
0x14007a40c  jz      short loc_14007A428
0x14007a40e  cmp     byte ptr [rcx+29h], 5
0x14007a412  jb      short loc_14007A428
0x14007a414  mov     rcx, [rcx+18h]
0x14007a418  lea     edx, [r13+63h]
0x14007a41c  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007a423  call    WPP_SF_
0x14007a428  xor     r8d, r8d; State
0x14007a42b  lea     rcx, [rbp+90h+Event]; Event
0x14007a42f  xor     edx, edx; Type
0x14007a431  call    cs:__imp_KeInitializeEvent
0x14007a438  nop     dword ptr [rax+rax+00h]
0x14007a43d  mov     r8b, 1
0x14007a440  lea     rdx, [rbp+90h+var_D0]
0x14007a444  mov     rcx, rsi
0x14007a447  call    FvepAcquireDevFveLock
0x14007a44c  mov     rbx, [rsi+578h]
0x14007a453  lea     rcx, [rbp+90h+var_D0]
0x14007a457  call    FvepReleaseDevFveLock
0x14007a45c  test    rbx, rbx
0x14007a45f  jz      short loc_14007A469
0x14007a461  mov     rcx, rbx
0x14007a464  call    FveWipeStopSliderThread
0x14007a469  mov     r8b, 1
0x14007a46c  lea     rdx, [rbp+90h+var_D0]
0x14007a470  mov     rcx, rsi
0x14007a473  call    FvepAcquireDevFveLock
0x14007a478  mov     rbx, [rsi+578h]
0x14007a47f  mov     edi, 0C000000Dh
0x14007a484  test    rbx, rbx
0x14007a487  jz      loc_14007A694
0x14007a48d  cmp     [rbx+200h], r13
0x14007a494  jnz     loc_14007A694
0x14007a49a  lea     rcx, [rbx+138h]; Event
0x14007a4a1  call    cs:__imp_KeClearEvent
0x14007a4a8  nop     dword ptr [rax+rax+00h]
0x14007a4ad  lea     rcx, [rbx+150h]; Event
0x14007a4b4  call    cs:__imp_KeClearEvent
0x14007a4bb  nop     dword ptr [rax+rax+00h]
0x14007a4c0  lea     rcx, [rbx+168h]; Event
0x14007a4c7  call    cs:__imp_KeClearEvent
0x14007a4ce  nop     dword ptr [rax+rax+00h]
0x14007a4d3  xorps   xmm0, xmm0
0x14007a4d6  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14007a4de  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007a4e4  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14007a4e9  mov     eax, 1
0x14007a4ee  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14007a4f6  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14007a4fb  lock xadd [rbx], eax
0x14007a4ff  inc     eax
0x14007a501  xor     r9d, r9d; ProcessHandle
0x14007a504  cmp     eax, 2
0x14007a507  jz      short loc_14007A529
0x14007a509  cdqe
0x14007a50b  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007a50f  mov     r8, rbx; BugCheckParameter2
0x14007a512  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14007a517  mov     ecx, 120h; BugCheckCode
0x14007a51c  call    cs:__imp_KeBugCheckEx
0x14007a529  lea     rax, FveWipeSliderWorker
0x14007a530  mov     [rsp+190h+StartContext], rbx; StartContext
0x14007a535  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14007a53a  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14007a53f  xor     edx, edx; DesiredAccess
0x14007a541  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14007a546  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14007a54d  call    cs:__imp_PsCreateSystemThread
0x14007a554  nop     dword ptr [rax+rax+00h]
0x14007a559  mov     edi, eax
0x14007a55b  test    eax, eax
0x14007a55d  js      loc_14007A752
0x14007a563  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14007a56a  lea     rax, [rsp+190h+Object]
0x14007a56f  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14007a574  xor     r9d, r9d; AccessMode
0x14007a577  xor     r8d, r8d; ObjectType
0x14007a57a  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14007a57f  mov     edx, 1FFFFFh; DesiredAccess
0x14007a584  mov     [rsp+190h+Object], r13
0x14007a589  call    cs:__imp_ObReferenceObjectByHandle
0x14007a590  nop     dword ptr [rax+rax+00h]
0x14007a595  mov     rax, [rsp+190h+Object]
0x14007a59a  mov     [rbx+208h], rax
0x14007a5a1  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14007a5a8  call    cs:__imp_ZwClose
0x14007a5af  nop     dword ptr [rax+rax+00h]
0x14007a5b4  lea     rax, [rbp+90h+Event]
0x14007a5b8  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14007a5c0  mov     qword ptr [rbp+90h+var_100+8], rax
0x14007a5c4  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14007a5c9  lea     rax, [rbp+90h+var_100]
0x14007a5cd  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14007a5d2  mov     [rsp+190h+StartContext], rax; StartContext
0x14007a5d7  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14007a5de  lea     rax, FveWipePump
0x14007a5e5  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14007a5ed  xorps   xmm0, xmm0
0x14007a5f0  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14007a5f5  xor     r9d, r9d; ProcessHandle
0x14007a5f8  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14007a5fd  xor     edx, edx; DesiredAccess
0x14007a5ff  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14007a604  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007a60a  mov     qword ptr [rbp+90h+var_100], rsi
0x14007a60e  call    cs:__imp_PsCreateSystemThread
0x14007a615  nop     dword ptr [rax+rax+00h]
0x14007a61a  mov     edi, eax
0x14007a61c  test    eax, eax
0x14007a61e  js      loc_14007A746
0x14007a624  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14007a62b  lea     rax, [rsp+190h+Object]
0x14007a630  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14007a635  xor     r9d, r9d; AccessMode
0x14007a638  xor     r8d, r8d; ObjectType
0x14007a63b  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14007a640  mov     edx, 1FFFFFh; DesiredAccess
0x14007a645  mov     [rsp+190h+Object], r13
0x14007a64a  call    cs:__imp_ObReferenceObjectByHandle
0x14007a651  nop     dword ptr [rax+rax+00h]
0x14007a656  mov     rax, [rsp+190h+Object]
0x14007a65b  mov     [rbx+200h], rax
0x14007a662  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14007a669  call    cs:__imp_ZwClose
0x14007a670  nop     dword ptr [rax+rax+00h]
0x14007a675  test    r12b, r12b
0x14007a678  jz      short loc_14007A694
0x14007a67a  lea     r9, [rbx+2A8h]
0x14007a681  mov     rdx, r15
0x14007a684  mov     rcx, rsi
0x14007a687  call    FveWrqAddRequest
0x14007a68c  test    eax, eax
0x14007a68e  sets    al
0x14007a691  mov     [r14], al
0x14007a694  lea     rcx, [rbp+90h+var_D0]
0x14007a698  call    FvepReleaseDevFveLock
0x14007a69d  test    edi, edi
0x14007a69f  js      short loc_14007A6CB
0x14007a6a1  xor     r9d, r9d; Alertable
0x14007a6a4  mov     [rsp+190h+BugCheckParameter4], r13; Timeout
0x14007a6a9  xor     r8d, r8d; WaitMode
0x14007a6ac  lea     rcx, [rbp+90h+Event]; Object
0x14007a6b0  xor     edx, edx; WaitReason
0x14007a6b2  call    cs:__imp_KeWaitForSingleObject
0x14007a6b9  nop     dword ptr [rax+rax+00h]
0x14007a6be  mov     edx, 0Fh
0x14007a6c3  mov     rcx, rsi
0x14007a6c6  call    FveRaiseStatusChangedEvent
0x14007a6cb  mov     rcx, [rsi]
0x14007a6ce  lea     rax, FVE_CONV_RESUME
0x14007a6d5  lea     rdx, [rsp+190h+var_118]
0x14007a6da  mov     qword ptr [rsp+190h+var_118], rax
0x14007a6df  mov     [rsi+5A0h], edi
0x14007a6e5  mov     dword ptr [rbp+90h+var_118+8], r13d
0x14007a6e9  mov     dword ptr [rbp+90h+var_118+0Ch], edi
0x14007a6ec  mov     [rbp+90h+var_108], r13
0x14007a6f0  call    FveLogEvent
0x14007a6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6fc  lea     rax, WPP_GLOBAL_Control
0x14007a703  cmp     rcx, rax
0x14007a706  jz      short loc_14007A72F
0x14007a708  test    dword ptr [rcx+2Ch], 1000h
0x14007a70f  jz      short loc_14007A72F
0x14007a711  cmp     byte ptr [rcx+29h], 5
0x14007a715  jb      short loc_14007A72F
0x14007a717  mov     rcx, [rcx+18h]
0x14007a71b  lea     r8, WPP_8a32d04b4e3c3afe288af5df14c2f40d_Traceguids
0x14007a722  mov     edx, 64h ; 'd'
0x14007a727  mov     r9d, edi
0x14007a72a  call    WPP_SF_d
0x14007a72f  mov     eax, edi
0x14007a731  add     rsp, 158h
0x14007a738  pop     r15
0x14007a73a  pop     r14
0x14007a73c  pop     r13
0x14007a73e  pop     r12
0x14007a740  pop     rdi
0x14007a741  pop     rsi
0x14007a742  pop     rbx
0x14007a743  pop     rbp
0x14007a744  retn
0x14007a746  mov     [rbx+200h], r13
0x14007a74d  jmp     loc_14007A694
0x14007a752  mov     [rbx+208h], r13
0x14007a759  or      eax, 0FFFFFFFFh
0x14007a75c  lock xadd [rbx], eax
0x14007a760  dec     eax
0x14007a762  cmp     eax, 1
0x14007a765  jz      loc_14007A694
0x14007a76b  xor     r9d, r9d; BugCheckParameter3
0x14007a76e  cdqe
0x14007a770  mov     r8, rbx; BugCheckParameter2
0x14007a773  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14007a778  mov     ecx, 120h; BugCheckCode
0x14007a77d  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14007a781  call    cs:__imp_KeBugCheckEx
```
