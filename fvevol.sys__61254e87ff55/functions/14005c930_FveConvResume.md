# FveConvResume

- ea: `0x14005c930`
- end: `0x14005cd37`
- name: `FveConvResume`
- size: `1031`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005485c`
- `0x140058e70`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14002559c`
- `0x14005c930`
- `0x14005d130`
- `0x140097240`
- `0x14009e2c0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005c9dc`
- `ntoskrnl!KeInitializeEvent` at `0x14005c9dc`
- `ntoskrnl!KeClearEvent` at `0x14005ca4c`
- `ntoskrnl!KeClearEvent` at `0x14005ca5f`
- `ntoskrnl!KeClearEvent` at `0x14005ca72`
- `ntoskrnl!KeClearEvent` at `0x14005ca4c`
- `ntoskrnl!KeClearEvent` at `0x14005ca5f`
- `ntoskrnl!KeClearEvent` at `0x14005ca72`
- `ntoskrnl!PsCreateSystemThread` at `0x14005caf8`
- `ntoskrnl!PsCreateSystemThread` at `0x14005cbb9`
- `ntoskrnl!PsCreateSystemThread` at `0x14005caf8`
- `ntoskrnl!PsCreateSystemThread` at `0x14005cbb9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005cb34`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005cbf5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005cb34`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005cbf5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005cc5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005cc5d`
- `ntoskrnl!KeBugCheckEx` at `0x14005cac7`
- `ntoskrnl!KeBugCheckEx` at `0x14005cd2a`
- `ntoskrnl!KeBugCheckEx` at `0x14005cac7`
- `ntoskrnl!KeBugCheckEx` at `0x14005cd2a`
- `ntoskrnl!ZwClose` at `0x14005cb53`
- `ntoskrnl!ZwClose` at `0x14005cc14`
- `ntoskrnl!ZwClose` at `0x14005cb53`
- `ntoskrnl!ZwClose` at `0x14005cc14`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_8d48425948c73b66a608165fe5646329_Traceguids);
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
      WPP_8d48425948c73b66a608165fe5646329_Traceguids,
      (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005c930  push    rbp
0x14005c932  push    rbx
0x14005c933  push    rsi
0x14005c934  push    rdi
0x14005c935  push    r12
0x14005c937  push    r13
0x14005c939  push    r14
0x14005c93b  push    r15
0x14005c93d  lea     rbp, [rsp-58h]
0x14005c942  sub     rsp, 158h
0x14005c949  xorps   xmm0, xmm0
0x14005c94c  mov     r15, r8
0x14005c94f  mov     r12b, dl
0x14005c952  mov     rsi, rcx
0x14005c955  xor     eax, eax
0x14005c957  lea     rcx, [rbp+90h+var_D0]; void *
0x14005c95b  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x14005c960  xor     r13d, r13d
0x14005c963  mov     [rbp+90h+var_108], rax
0x14005c967  xor     edx, edx; Val
0x14005c969  mov     [rbp+90h+ThreadHandle], r13
0x14005c970  mov     r8d, 90h; Size
0x14005c976  mov     r14, r9
0x14005c979  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x14005c97e  movups  [rsp+190h+var_118], xmm0
0x14005c983  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x14005c988  call    memset
0x14005c98d  xorps   xmm0, xmm0
0x14005c990  xor     eax, eax
0x14005c992  movups  xmmword ptr [rbp+90h+Event.Header], xmm0
0x14005c996  mov     [rbp+90h+Event.Header.WaitListHead.Blink], rax
0x14005c99a  movups  [rbp+90h+var_100], xmm0
0x14005c99e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c9a5  lea     rax, WPP_GLOBAL_Control
0x14005c9ac  cmp     rcx, rax
0x14005c9af  jz      short loc_14005C9D3
0x14005c9b1  mov     eax, [rcx+2Ch]
0x14005c9b4  test    al, 2
0x14005c9b6  jz      short loc_14005C9D3
0x14005c9b8  cmp     byte ptr [rcx+29h], 5
0x14005c9bc  jb      short loc_14005C9D3
0x14005c9be  mov     rcx, [rcx+18h]
0x14005c9c2  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x14005c9c9  mov     edx, 0CFh
0x14005c9ce  call    WPP_SF_
0x14005c9d3  xor     r8d, r8d; State
0x14005c9d6  lea     rcx, [rbp+90h+Event]; Event
0x14005c9da  xor     edx, edx; Type
0x14005c9dc  call    cs:__imp_KeInitializeEvent
0x14005c9e3  nop     dword ptr [rax+rax+00h]
0x14005c9e8  mov     r8b, 1
0x14005c9eb  lea     rdx, [rbp+90h+var_D0]
0x14005c9ef  mov     rcx, rsi
0x14005c9f2  call    FvepAcquireDevFveLock
0x14005c9f7  mov     rbx, [rsi+570h]
0x14005c9fe  lea     rcx, [rbp+90h+var_D0]
0x14005ca02  call    FvepReleaseDevFveLock
0x14005ca07  test    rbx, rbx
0x14005ca0a  jz      short loc_14005CA14
0x14005ca0c  mov     rcx, rbx
0x14005ca0f  call    FveConvStopSliderThread
0x14005ca14  mov     r8b, 1
0x14005ca17  lea     rdx, [rbp+90h+var_D0]
0x14005ca1b  mov     rcx, rsi
0x14005ca1e  call    FvepAcquireDevFveLock
0x14005ca23  mov     rbx, [rsi+570h]
0x14005ca2a  mov     edi, 0C000000Dh
0x14005ca2f  test    rbx, rbx
0x14005ca32  jz      loc_14005CC3F
0x14005ca38  cmp     [rbx+240h], r13
0x14005ca3f  jnz     loc_14005CC3F
0x14005ca45  lea     rcx, [rbx+1B8h]; Event
0x14005ca4c  call    cs:__imp_KeClearEvent
0x14005ca53  nop     dword ptr [rax+rax+00h]
0x14005ca58  lea     rcx, [rbx+1D0h]; Event
0x14005ca5f  call    cs:__imp_KeClearEvent
0x14005ca66  nop     dword ptr [rax+rax+00h]
0x14005ca6b  lea     rcx, [rbx+1E8h]; Event
0x14005ca72  call    cs:__imp_KeClearEvent
0x14005ca79  nop     dword ptr [rax+rax+00h]
0x14005ca7e  xorps   xmm0, xmm0
0x14005ca81  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14005ca89  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005ca8f  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14005ca94  mov     eax, 1
0x14005ca99  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14005caa1  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14005caa6  lock xadd [rbx], eax
0x14005caaa  inc     eax
0x14005caac  xor     r9d, r9d; ProcessHandle
0x14005caaf  cmp     eax, 2
0x14005cab2  jz      short loc_14005CAD4
0x14005cab4  cdqe
0x14005cab6  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14005caba  mov     r8, rbx; BugCheckParameter2
0x14005cabd  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14005cac2  mov     ecx, 120h; BugCheckCode
0x14005cac7  call    cs:__imp_KeBugCheckEx
0x14005cad4  lea     rax, FveConvSliderWorker
0x14005cadb  mov     [rsp+190h+StartContext], rbx; StartContext
0x14005cae0  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14005cae5  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14005caea  xor     edx, edx; DesiredAccess
0x14005caec  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14005caf1  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14005caf8  call    cs:__imp_PsCreateSystemThread
0x14005caff  nop     dword ptr [rax+rax+00h]
0x14005cb04  mov     edi, eax
0x14005cb06  test    eax, eax
0x14005cb08  js      loc_14005CCFB
0x14005cb0e  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005cb15  lea     rax, [rsp+190h+Object]
0x14005cb1a  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14005cb1f  xor     r9d, r9d; AccessMode
0x14005cb22  xor     r8d, r8d; ObjectType
0x14005cb25  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14005cb2a  mov     edx, 1FFFFFh; DesiredAccess
0x14005cb2f  mov     [rsp+190h+Object], r13
0x14005cb34  call    cs:__imp_ObReferenceObjectByHandle
0x14005cb3b  nop     dword ptr [rax+rax+00h]
0x14005cb40  mov     rax, [rsp+190h+Object]
0x14005cb45  mov     [rbx+248h], rax
0x14005cb4c  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005cb53  call    cs:__imp_ZwClose
0x14005cb5a  nop     dword ptr [rax+rax+00h]
0x14005cb5f  lea     rax, [rbp+90h+Event]
0x14005cb63  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x14005cb6b  mov     qword ptr [rbp+90h+var_100+8], rax
0x14005cb6f  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x14005cb74  lea     rax, [rbp+90h+var_100]
0x14005cb78  mov     [rsp+190h+ObjectAttributes.RootDirectory], r13
0x14005cb7d  mov     [rsp+190h+StartContext], rax; StartContext
0x14005cb82  lea     rcx, [rbp+90h+ThreadHandle]; ThreadHandle
0x14005cb89  lea     rax, FveConvPump
0x14005cb90  mov     [rsp+190h+ObjectAttributes.Attributes], 200h
0x14005cb98  xorps   xmm0, xmm0
0x14005cb9b  mov     [rsp+190h+StartRoutine], rax; StartRoutine
0x14005cba0  xor     r9d, r9d; ProcessHandle
0x14005cba3  mov     [rsp+190h+BugCheckParameter4], r13; ClientId
0x14005cba8  xor     edx, edx; DesiredAccess
0x14005cbaa  mov     [rsp+190h+ObjectAttributes.ObjectName], r13
0x14005cbaf  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005cbb5  mov     qword ptr [rbp+90h+var_100], rsi
0x14005cbb9  call    cs:__imp_PsCreateSystemThread
0x14005cbc0  nop     dword ptr [rax+rax+00h]
0x14005cbc5  mov     edi, eax
0x14005cbc7  test    eax, eax
0x14005cbc9  js      loc_14005CCEF
0x14005cbcf  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005cbd6  lea     rax, [rsp+190h+Object]
0x14005cbdb  mov     [rsp+190h+StartRoutine], r13; HandleInformation
0x14005cbe0  xor     r9d, r9d; AccessMode
0x14005cbe3  xor     r8d, r8d; ObjectType
0x14005cbe6  mov     [rsp+190h+BugCheckParameter4], rax; Object
0x14005cbeb  mov     edx, 1FFFFFh; DesiredAccess
0x14005cbf0  mov     [rsp+190h+Object], r13
0x14005cbf5  call    cs:__imp_ObReferenceObjectByHandle
0x14005cbfc  nop     dword ptr [rax+rax+00h]
0x14005cc01  mov     rax, [rsp+190h+Object]
0x14005cc06  mov     [rbx+240h], rax
0x14005cc0d  mov     rcx, [rbp+90h+ThreadHandle]; Handle
0x14005cc14  call    cs:__imp_ZwClose
0x14005cc1b  nop     dword ptr [rax+rax+00h]
0x14005cc20  test    r12b, r12b
0x14005cc23  jz      short loc_14005CC3F
0x14005cc25  lea     r9, [rbx+2E8h]
0x14005cc2c  mov     rdx, r15
0x14005cc2f  mov     rcx, rsi
0x14005cc32  call    FveWrqAddRequest
0x14005cc37  test    eax, eax
0x14005cc39  sets    al
0x14005cc3c  mov     [r14], al
0x14005cc3f  lea     rcx, [rbp+90h+var_D0]
0x14005cc43  call    FvepReleaseDevFveLock
0x14005cc48  test    edi, edi
0x14005cc4a  js      short loc_14005CC76
0x14005cc4c  xor     r9d, r9d; Alertable
0x14005cc4f  mov     [rsp+190h+BugCheckParameter4], r13; Timeout
0x14005cc54  xor     r8d, r8d; WaitMode
0x14005cc57  lea     rcx, [rbp+90h+Event]; Object
0x14005cc5b  xor     edx, edx; WaitReason
0x14005cc5d  call    cs:__imp_KeWaitForSingleObject
0x14005cc64  nop     dword ptr [rax+rax+00h]
0x14005cc69  mov     edx, 0Ah
0x14005cc6e  mov     rcx, rsi
0x14005cc71  call    FveRaiseStatusChangedEvent
0x14005cc76  mov     rcx, [rsi]
0x14005cc79  lea     rax, FVE_CONV_RESUME
0x14005cc80  lea     rdx, [rsp+190h+var_118]
0x14005cc85  mov     qword ptr [rsp+190h+var_118], rax
0x14005cc8a  mov     [rsi+5A0h], edi
0x14005cc90  mov     dword ptr [rbp+90h+var_118+8], r13d
0x14005cc94  mov     dword ptr [rbp+90h+var_118+0Ch], edi
0x14005cc97  mov     [rbp+90h+var_108], r13
0x14005cc9b  call    FveLogEvent
0x14005cca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cca7  lea     rax, WPP_GLOBAL_Control
0x14005ccae  cmp     rcx, rax
0x14005ccb1  jz      short loc_14005CCD8
0x14005ccb3  mov     eax, [rcx+2Ch]
0x14005ccb6  test    al, 2
0x14005ccb8  jz      short loc_14005CCD8
0x14005ccba  cmp     byte ptr [rcx+29h], 5
0x14005ccbe  jb      short loc_14005CCD8
0x14005ccc0  mov     rcx, [rcx+18h]
0x14005ccc4  lea     r8, WPP_8d48425948c73b66a608165fe5646329_Traceguids
0x14005cccb  mov     edx, 0D0h
0x14005ccd0  mov     r9d, edi
0x14005ccd3  call    WPP_SF_d
0x14005ccd8  mov     eax, edi
0x14005ccda  add     rsp, 158h
0x14005cce1  pop     r15
0x14005cce3  pop     r14
0x14005cce5  pop     r13
0x14005cce7  pop     r12
0x14005cce9  pop     rdi
0x14005ccea  pop     rsi
0x14005cceb  pop     rbx
0x14005ccec  pop     rbp
0x14005cced  retn
0x14005ccef  mov     [rbx+240h], r13
0x14005ccf6  jmp     loc_14005CC3F
0x14005ccfb  mov     [rbx+248h], r13
0x14005cd02  or      eax, 0FFFFFFFFh
0x14005cd05  lock xadd [rbx], eax
0x14005cd09  dec     eax
0x14005cd0b  cmp     eax, 1
0x14005cd0e  jz      loc_14005CC3F
0x14005cd14  xor     r9d, r9d; BugCheckParameter3
0x14005cd17  cdqe
0x14005cd19  mov     r8, rbx; BugCheckParameter2
0x14005cd1c  mov     [rsp+190h+BugCheckParameter4], rax; BugCheckParameter4
0x14005cd21  mov     ecx, 120h; BugCheckCode
0x14005cd26  lea     edx, [r9+0Bh]; BugCheckParameter1
0x14005cd2a  call    cs:__imp_KeBugCheckEx
```
