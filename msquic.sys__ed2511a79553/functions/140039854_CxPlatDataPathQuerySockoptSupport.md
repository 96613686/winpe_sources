# CxPlatDataPathQuerySockoptSupport

- ea: `0x140039854`
- end: `0x140039e0f`
- name: `CxPlatDataPathQuerySockoptSupport`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003aea0`

## callees

- `0x140039854`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400399b6`
- `ntoskrnl!_snprintf_s` at `0x140039adb`
- `ntoskrnl!_snprintf_s` at `0x140039bf5`
- `ntoskrnl!_snprintf_s` at `0x140039d0f`
- `ntoskrnl!_snprintf_s` at `0x1400399b6`
- `ntoskrnl!_snprintf_s` at `0x140039adb`
- `ntoskrnl!_snprintf_s` at `0x140039bf5`
- `ntoskrnl!_snprintf_s` at `0x140039d0f`
- `ntoskrnl!KeInitializeEvent` at `0x1400398b0`
- `ntoskrnl!KeInitializeEvent` at `0x1400398b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003995f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039a8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039ba9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039cc3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039dc6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003995f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039a8f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039ba9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039cc3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039dc6`
- `ntoskrnl!KeResetEvent` at `0x140039a19`
- `ntoskrnl!KeResetEvent` at `0x140039b39`
- `ntoskrnl!KeResetEvent` at `0x140039c56`
- `ntoskrnl!KeResetEvent` at `0x140039d90`
- `ntoskrnl!KeResetEvent` at `0x140039a19`
- `ntoskrnl!KeResetEvent` at `0x140039b39`
- `ntoskrnl!KeResetEvent` at `0x140039c56`
- `ntoskrnl!KeResetEvent` at `0x140039d90`
- `ntoskrnl!IoReuseIrp` at `0x1400399e9`
- `ntoskrnl!IoReuseIrp` at `0x140039b09`
- `ntoskrnl!IoReuseIrp` at `0x140039c26`
- `ntoskrnl!IoReuseIrp` at `0x140039d60`
- `ntoskrnl!IoReuseIrp` at `0x1400399e9`
- `ntoskrnl!IoReuseIrp` at `0x140039b09`
- `ntoskrnl!IoReuseIrp` at `0x140039c26`
- `ntoskrnl!IoReuseIrp` at `0x140039d60`
- `ntoskrnl!IoInitializeIrp` at `0x1400398d9`
- `ntoskrnl!IoInitializeIrp` at `0x1400398d9`
- `ntoskrnl!IoCleanupIrp` at `0x140039dd6`
- `ntoskrnl!IoCleanupIrp` at `0x140039dd6`

## string_xrefs

- `0x1400399a2`: `[data] UDP send segmentation helper socket failed to open, 0x%x`
- `0x140039984`: `[data] UDP send segmentation helper socket failed to open (async), 0x%x`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathQuerySockoptSupport(__int64 a1, _BYTE *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v4; // eax
  __int64 v5; // rcx
  ULONG_PTR Information; // r12
  __int64 v7; // r13
  struct _IO_STACK_LOCATION *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  struct _IO_STACK_LOCATION *v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  struct _IO_STACK_LOCATION *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  _BYTE *v17; // rcx
  int v18; // eax
  struct _IO_STACK_LOCATION *v19; // rax
  PLARGE_INTEGER Timeout; // [rsp+28h] [rbp-E0h]
  PLARGE_INTEGER Timeouta; // [rsp+28h] [rbp-E0h]
  PLARGE_INTEGER Timeoutb; // [rsp+28h] [rbp-E0h]
  PLARGE_INTEGER Timeoutc; // [rsp+28h] [rbp-E0h]
  struct _KEVENT Event; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+80h] [rbp-88h]
  __int64 v27; // [rsp+88h] [rbp-80h] BYREF
  _BYTE *v28; // [rsp+90h] [rbp-78h]
  char DstBuf[128]; // [rsp+98h] [rbp-70h] BYREF
  IRP Irp; // [rsp+118h] [rbp+10h] BYREF

  v28 = a2;
  v27 = 0;
  v26 = 0;
  Event.Header.WaitListHead = 0;
  KeInitializeEvent((PRKEVENT)&Event.Header.WaitListHead, SynchronizationEvent, 0);
  memset(&Irp, 0, 0x118u);
  IoInitializeIrp(&Irp, 0x118u, 1);
  CurrentStackLocation = Irp.Tail.Overlay.CurrentStackLocation;
  Irp.Tail.Overlay.CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
  CurrentStackLocation[-1].Context = &Event.Header.WaitListHead;
  CurrentStackLocation[-1].Control = -32;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, IRP *))(*(_QWORD *)(a1 + 104) + 8LL))(
         *(_QWORD *)(a1 + 96),
         23,
         2,
         17,
         0,
         0,
         0,
         0,
         0,
         0,
         &Irp);
  if ( v4 == 259 )
  {
    KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
    goto LABEL_3;
  }
  if ( v4 >= 0 )
  {
LABEL_3:
    if ( Irp.IoStatus.Status < 0 )
    {
      if ( (byte_14005C48E & 0x20) != 0 )
      {
        LODWORD(Timeout) = Irp.IoStatus.Status;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[data] UDP send segmentation helper socket failed to open (async), 0x%x",
          Timeout);
LABEL_9:
        McTemplateU0s_EtwWriteTransfer(v5, QuicLogWarning, DstBuf);
        return IoCleanupIrp(&Irp);
      }
      return IoCleanupIrp(&Irp);
    }
    Information = Irp.IoStatus.Information;
    Event.Header.LockNV = 0;
    v7 = *(_QWORD *)Irp.IoStatus.Information;
    IoReuseIrp(&Irp, 0);
    v8 = Irp.Tail.Overlay.CurrentStackLocation;
    Irp.Tail.Overlay.CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
    v8[-1].Context = &Event.Header.WaitListHead;
    v8[-1].Control = -32;
    KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
    HIDWORD(Timeouta) = 0;
    v9 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64, __int64))v7)(Information, 1, 2);
    if ( v9 == 259 )
    {
      KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
    }
    else if ( v9 < 0 )
    {
      if ( (byte_14005C48E & 0x20) == 0 )
        goto LABEL_20;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[data] Query for UDP_SEND_MSG_SIZE failed, 0x%x",
        (unsigned int)v9);
      goto LABEL_18;
    }
    if ( Irp.IoStatus.Status >= 0 )
    {
      *(_DWORD *)(a1 + 56) |= 4u;
LABEL_20:
      Event.Header.LockNV = 0;
      IoReuseIrp(&Irp, 0);
      v11 = Irp.Tail.Overlay.CurrentStackLocation;
      Irp.Tail.Overlay.CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
      v11[-1].Context = &Event.Header.WaitListHead;
      v11[-1].Control = -32;
      KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
      v12 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64, __int64, __int64, _QWORD, _QWORD, __int64, struct _KEVENT *, __int64 *, IRP *))v7)(
              Information,
              1,
              3,
              17,
              0,
              0,
              4,
              &Event,
              &v27,
              &Irp);
      if ( v12 == 259 )
      {
        KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
      }
      else if ( v12 < 0 )
      {
        if ( (byte_14005C48E & 0x20) == 0 )
          goto LABEL_30;
        LODWORD(Timeoutb) = v12;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[data] Query for UDP_RECV_MAX_COALESCED_SIZE failed, 0x%x",
          Timeoutb);
        goto LABEL_28;
      }
      if ( Irp.IoStatus.Status >= 0 )
      {
        *(_DWORD *)(a1 + 56) |= 2u;
LABEL_30:
        Event.Header.LockNV = 4;
        IoReuseIrp(&Irp, 0);
        v14 = Irp.Tail.Overlay.CurrentStackLocation;
        Irp.Tail.Overlay.CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
        v14[-1].Context = &Event.Header.WaitListHead;
        v14[-1].Control = -32;
        KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
        v15 = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD, __int64, __int64, __int64, struct _KEVENT *, _QWORD, _QWORD, __int64 *, IRP *))v7)(
                Information,
                0,
                39,
                41,
                4,
                &Event,
                0,
                0,
                &v27,
                &Irp);
        if ( v15 == 259 )
        {
          KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
        }
        else if ( v15 < 0 )
        {
          if ( (byte_14005C48E & 0x20) == 0 )
            goto LABEL_40;
          LODWORD(Timeoutc) = v15;
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[data] Test setting IPV6_TCLASS failed, 0x%x", Timeoutc);
          goto LABEL_38;
        }
        if ( Irp.IoStatus.Status >= 0 )
        {
          *(_DWORD *)(a1 + 56) |= 0x100u;
LABEL_40:
          if ( dword_14005DA50 != 20348 )
          {
            v17 = v28;
            v18 = *(_DWORD *)(a1 + 56) | 0x80;
            *(_DWORD *)(a1 + 56) = v18;
            if ( *v17 )
              *(_DWORD *)(a1 + 56) = v18 | 0x400;
          }
          IoReuseIrp(&Irp, 0);
          v19 = Irp.Tail.Overlay.CurrentStackLocation;
          Irp.Tail.Overlay.CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
          v19[-1].Context = &Event.Header.WaitListHead;
          v19[-1].Control = -32;
          KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
          if ( (*(unsigned int (__fastcall **)(ULONG_PTR, IRP *))(v7 + 8))(Information, &Irp) == 259 )
            KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
          return IoCleanupIrp(&Irp);
        }
        if ( (byte_14005C48E & 0x20) == 0 )
          goto LABEL_40;
        LODWORD(Timeoutc) = Irp.IoStatus.Status;
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "[data] Test setting IPV6_TCLASS failed (async), 0x%x",
          Timeoutc);
LABEL_38:
        McTemplateU0s_EtwWriteTransfer(v16, QuicLogWarning, DstBuf);
        goto LABEL_40;
      }
      if ( (byte_14005C48E & 0x20) == 0 )
        goto LABEL_30;
      LODWORD(Timeoutb) = Irp.IoStatus.Status;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[data] Query for UDP_RECV_MAX_COALESCED_SIZE failed (async), 0x%x",
        Timeoutb);
LABEL_28:
      McTemplateU0s_EtwWriteTransfer(v13, QuicLogWarning, DstBuf);
      goto LABEL_30;
    }
    if ( (byte_14005C48E & 0x20) == 0 )
      goto LABEL_20;
    LODWORD(Timeouta) = Irp.IoStatus.Status;
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[data] Query for UDP_SEND_MSG_SIZE failed (async), 0x%x",
      Timeouta);
LABEL_18:
    McTemplateU0s_EtwWriteTransfer(v10, QuicLogWarning, DstBuf);
    goto LABEL_20;
  }
  if ( (byte_14005C48E & 0x20) != 0 )
  {
    LODWORD(Timeout) = v4;
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[data] UDP send segmentation helper socket failed to open, 0x%x",
      Timeout);
    goto LABEL_9;
  }
  return IoCleanupIrp(&Irp);
}

```

## disassembly

```asm
0x140039854  mov     rax, rsp
0x140039857  mov     [rax+10h], rsi
0x14003985b  mov     [rax+18h], rdi
0x14003985f  mov     [rax+20h], r12
0x140039863  push    rbp
0x140039864  push    r13
0x140039866  push    r15
0x140039868  lea     rbp, [rax-158h]
0x14003986f  sub     rsp, 240h
0x140039876  mov     rax, cs:__security_cookie
0x14003987d  xor     rax, rsp
0x140039880  mov     [rbp+150h+var_20], rax
0x140039887  xor     edi, edi
0x140039889  mov     [rbp+150h+var_1C8], rdx
0x14003988d  mov     r15, rcx
0x140039890  mov     [rbp+150h+var_1D0], rdi
0x140039894  xorps   xmm0, xmm0
0x140039897  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x14003989c  xor     eax, eax
0x14003989e  xor     r8d, r8d; State
0x1400398a1  lea     esi, [rdi+1]
0x1400398a4  mov     [rsp+250h+var_1D8], rax
0x1400398a9  mov     edx, esi; Type
0x1400398ab  movups  xmmword ptr [rsp+250h+Event.Header.WaitListHead.Flink], xmm0
0x1400398b0  call    cs:__imp_KeInitializeEvent
0x1400398b7  nop     dword ptr [rax+rax+00h]
0x1400398bc  xor     edx, edx; Val
0x1400398be  lea     rcx, [rbp+150h+Irp]; void *
0x1400398c2  mov     r8d, 118h; Size
0x1400398c8  call    memset
0x1400398cd  mov     edx, 118h; PacketSize
0x1400398d2  lea     rcx, [rbp+150h+Irp]; Irp
0x1400398d6  mov     r8b, sil; StackSize
0x1400398d9  call    cs:__imp_IoInitializeIrp
0x1400398e0  nop     dword ptr [rax+rax+00h]
0x1400398e5  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x1400398ec  lea     rcx, CxPlatDataPathIoCompletion
0x1400398f3  lea     edx, [rdi+17h]
0x1400398f6  lea     r8d, [rdi+2]
0x1400398fa  lea     r9d, [rdi+11h]
0x1400398fe  mov     [rax-10h], rcx
0x140039902  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039907  mov     [rax-8], rcx
0x14003990b  lea     rcx, [rbp+150h+Irp]
0x14003990f  mov     [rsp+250h+var_200], rcx
0x140039914  mov     [rsp+250h+var_208], rdi
0x140039919  mov     byte ptr [rax-45h], 0E0h
0x14003991d  mov     rax, [r15+68h]
0x140039921  mov     rcx, [r15+60h]
0x140039925  mov     [rsp+250h+var_210], rdi
0x14003992a  mov     [rsp+250h+var_218], rdi
0x14003992f  mov     rax, [rax+8]
0x140039933  mov     [rsp+250h+var_220], rdi
0x140039938  mov     [rsp+250h+var_228], rdi
0x14003993d  mov     dword ptr [rsp+250h+Timeout], edi
0x140039941  call    _guard_dispatch_icall
0x140039946  cmp     eax, 103h
0x14003994b  jnz     short loc_14003998D
0x14003994d  xor     r9d, r9d; Alertable
0x140039950  mov     [rsp+250h+Timeout], rdi; Timeout
0x140039955  xor     r8d, r8d; WaitMode
0x140039958  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x14003995d  xor     edx, edx; WaitReason
0x14003995f  call    cs:__imp_KeWaitForSingleObject
0x140039966  nop     dword ptr [rax+rax+00h]
0x14003996b  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x14003996f  test    ecx, ecx
0x140039971  jns     short loc_1400399D7
0x140039973  test    cs:byte_14005C48E, 20h
0x14003997a  jz      loc_140039DD2
0x140039980  mov     dword ptr [rsp+250h+Timeout], ecx
0x140039984  lea     r9, aDataUdpSendSeg; "[data] UDP send segmentation helper soc"...
0x14003998b  jmp     short loc_1400399A9
0x14003998d  test    eax, eax
0x14003998f  jns     short loc_14003996B
0x140039991  test    cs:byte_14005C48E, 20h
0x140039998  jz      loc_140039DD2
0x14003999e  mov     dword ptr [rsp+250h+Timeout], eax
0x1400399a2  lea     r9, aDataUdpSendSeg_0; "[data] UDP send segmentation helper soc"...
0x1400399a9  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400399ad  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x1400399b1  mov     edx, 80h; SizeInBytes
0x1400399b6  call    cs:__imp__snprintf_s
0x1400399bd  nop     dword ptr [rax+rax+00h]
0x1400399c2  lea     r8, [rbp+150h+DstBuf]
0x1400399c6  lea     rdx, QuicLogWarning
0x1400399cd  call    McTemplateU0s_EtwWriteTransfer
0x1400399d2  jmp     loc_140039DD2
0x1400399d7  mov     r12, [rbp+150h+Irp.IoStatus.Information]
0x1400399db  lea     rcx, [rbp+150h+Irp]; Irp
0x1400399df  xor     edx, edx; Iostatus
0x1400399e1  mov     dword ptr [rsp+250h+Event.Header], edi
0x1400399e5  mov     r13, [r12]
0x1400399e9  call    cs:__imp_IoReuseIrp
0x1400399f0  nop     dword ptr [rax+rax+00h]
0x1400399f5  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x1400399fc  lea     rcx, CxPlatDataPathIoCompletion
0x140039a03  mov     [rax-10h], rcx
0x140039a07  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039a0c  mov     [rax-8], rcx
0x140039a10  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x140039a15  mov     byte ptr [rax-45h], 0E0h
0x140039a19  call    cs:__imp_KeResetEvent
0x140039a20  nop     dword ptr [rax+rax+00h]
0x140039a25  mov     rax, [r13+0]
0x140039a29  lea     rcx, [rbp+150h+Irp]
0x140039a2d  mov     [rsp+250h+var_208], rcx
0x140039a32  mov     r9d, 11h
0x140039a38  lea     rcx, [rbp+150h+var_1D0]
0x140039a3c  mov     edx, esi
0x140039a3e  mov     [rsp+250h+var_210], rcx
0x140039a43  lea     rcx, [rsp+250h+Event]
0x140039a48  mov     [rsp+250h+var_218], rcx
0x140039a4d  mov     rcx, r12
0x140039a50  mov     [rsp+250h+var_220], 4
0x140039a59  lea     r8d, [r9-0Fh]
0x140039a5d  mov     [rsp+250h+var_228], rdi
0x140039a62  mov     [rsp+250h+Timeout], rdi; Timeout
0x140039a67  call    _guard_dispatch_icall
0x140039a6c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140039a70  mov     edi, 80h
0x140039a75  cmp     eax, 103h
0x140039a7a  jnz     short loc_140039AB9
0x140039a7c  and     [rsp+250h+Timeout], 0
0x140039a82  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039a87  xor     r9d, r9d; Alertable
0x140039a8a  xor     r8d, r8d; WaitMode
0x140039a8d  xor     edx, edx; WaitReason
0x140039a8f  call    cs:__imp_KeWaitForSingleObject
0x140039a96  nop     dword ptr [rax+rax+00h]
0x140039a9b  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x140039a9f  test    ecx, ecx
0x140039aa1  jns     short loc_140039AF9
0x140039aa3  test    cs:byte_14005C48E, 20h
0x140039aaa  jz      short loc_140039AFE
0x140039aac  mov     dword ptr [rsp+250h+Timeout], ecx
0x140039ab0  lea     r9, aDataQueryForUd_1; "[data] Query for UDP_SEND_MSG_SIZE fail"...
0x140039ab7  jmp     short loc_140039AD1
0x140039ab9  test    eax, eax
0x140039abb  jns     short loc_140039A9B
0x140039abd  test    cs:byte_14005C48E, 20h
0x140039ac4  jz      short loc_140039AFE
0x140039ac6  mov     dword ptr [rsp+250h+Timeout], eax
0x140039aca  lea     r9, aDataQueryForUd; "[data] Query for UDP_SEND_MSG_SIZE fail"...
0x140039ad1  mov     r8, rsi; MaxCount
0x140039ad4  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x140039ad8  mov     rdx, rdi; SizeInBytes
0x140039adb  call    cs:__imp__snprintf_s
0x140039ae2  nop     dword ptr [rax+rax+00h]
0x140039ae7  lea     r8, [rbp+150h+DstBuf]
0x140039aeb  lea     rdx, QuicLogWarning
0x140039af2  call    McTemplateU0s_EtwWriteTransfer
0x140039af7  jmp     short loc_140039AFE
0x140039af9  or      dword ptr [r15+38h], 4
0x140039afe  and     dword ptr [rsp+250h+Event.Header], 0
0x140039b03  lea     rcx, [rbp+150h+Irp]; Irp
0x140039b07  xor     edx, edx; Iostatus
0x140039b09  call    cs:__imp_IoReuseIrp
0x140039b10  nop     dword ptr [rax+rax+00h]
0x140039b15  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x140039b1c  lea     rcx, CxPlatDataPathIoCompletion
0x140039b23  mov     [rax-10h], rcx
0x140039b27  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039b2c  mov     [rax-8], rcx
0x140039b30  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x140039b35  mov     byte ptr [rax-45h], 0E0h
0x140039b39  call    cs:__imp_KeResetEvent
0x140039b40  nop     dword ptr [rax+rax+00h]
0x140039b45  mov     rax, [r13+0]
0x140039b49  lea     rcx, [rbp+150h+Irp]
0x140039b4d  mov     [rsp+250h+var_208], rcx
0x140039b52  mov     edx, 1
0x140039b57  lea     rcx, [rbp+150h+var_1D0]
0x140039b5b  mov     [rsp+250h+var_210], rcx
0x140039b60  lea     rcx, [rsp+250h+Event]
0x140039b65  mov     [rsp+250h+var_218], rcx
0x140039b6a  mov     rcx, r12
0x140039b6d  mov     [rsp+250h+var_220], 4
0x140039b76  lea     r9d, [rdx+10h]
0x140039b7a  and     [rsp+250h+var_228], 0
0x140039b80  lea     r8d, [rdx+2]
0x140039b84  and     [rsp+250h+Timeout], 0
0x140039b8a  call    _guard_dispatch_icall
0x140039b8f  cmp     eax, 103h
0x140039b94  jnz     short loc_140039BD3
0x140039b96  and     [rsp+250h+Timeout], 0
0x140039b9c  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039ba1  xor     r9d, r9d; Alertable
0x140039ba4  xor     r8d, r8d; WaitMode
0x140039ba7  xor     edx, edx; WaitReason
0x140039ba9  call    cs:__imp_KeWaitForSingleObject
0x140039bb0  nop     dword ptr [rax+rax+00h]
0x140039bb5  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x140039bb9  test    ecx, ecx
0x140039bbb  jns     short loc_140039C13
0x140039bbd  test    cs:byte_14005C48E, 20h
0x140039bc4  jz      short loc_140039C18
0x140039bc6  mov     dword ptr [rsp+250h+Timeout], ecx
0x140039bca  lea     r9, aDataQueryForUd_2; "[data] Query for UDP_RECV_MAX_COALESCED"...
0x140039bd1  jmp     short loc_140039BEB
0x140039bd3  test    eax, eax
0x140039bd5  jns     short loc_140039BB5
0x140039bd7  test    cs:byte_14005C48E, 20h
0x140039bde  jz      short loc_140039C18
0x140039be0  mov     dword ptr [rsp+250h+Timeout], eax
0x140039be4  lea     r9, aDataQueryForUd_0; "[data] Query for UDP_RECV_MAX_COALESCED"...
0x140039beb  mov     r8, rsi; MaxCount
0x140039bee  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x140039bf2  mov     rdx, rdi; SizeInBytes
0x140039bf5  call    cs:__imp__snprintf_s
0x140039bfc  nop     dword ptr [rax+rax+00h]
0x140039c01  lea     r8, [rbp+150h+DstBuf]
0x140039c05  lea     rdx, QuicLogWarning
0x140039c0c  call    McTemplateU0s_EtwWriteTransfer
0x140039c11  jmp     short loc_140039C18
0x140039c13  or      dword ptr [r15+38h], 2
0x140039c18  xor     edx, edx; Iostatus
0x140039c1a  mov     dword ptr [rsp+250h+Event.Header], 4
0x140039c22  lea     rcx, [rbp+150h+Irp]; Irp
0x140039c26  call    cs:__imp_IoReuseIrp
0x140039c2d  nop     dword ptr [rax+rax+00h]
0x140039c32  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x140039c39  lea     rcx, CxPlatDataPathIoCompletion
0x140039c40  mov     [rax-10h], rcx
0x140039c44  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039c49  mov     [rax-8], rcx
0x140039c4d  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x140039c52  mov     byte ptr [rax-45h], 0E0h
0x140039c56  call    cs:__imp_KeResetEvent
0x140039c5d  nop     dword ptr [rax+rax+00h]
0x140039c62  mov     rax, [r13+0]
0x140039c66  lea     rcx, [rbp+150h+Irp]
0x140039c6a  mov     [rsp+250h+var_208], rcx
0x140039c6f  xor     edx, edx
0x140039c71  lea     rcx, [rbp+150h+var_1D0]
0x140039c75  mov     [rsp+250h+var_210], rcx
0x140039c7a  lea     rcx, [rsp+250h+Event]
0x140039c7f  and     [rsp+250h+var_218], 0
0x140039c85  and     [rsp+250h+var_220], 0
0x140039c8b  lea     r9d, [rdx+29h]
0x140039c8f  mov     [rsp+250h+var_228], rcx
0x140039c94  lea     r8d, [rdx+27h]
0x140039c98  mov     rcx, r12
0x140039c9b  mov     [rsp+250h+Timeout], 4; Timeout
0x140039ca4  call    _guard_dispatch_icall
0x140039ca9  cmp     eax, 103h
0x140039cae  jnz     short loc_140039CED
0x140039cb0  and     [rsp+250h+Timeout], 0
0x140039cb6  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039cbb  xor     r9d, r9d; Alertable
0x140039cbe  xor     r8d, r8d; WaitMode
0x140039cc1  xor     edx, edx; WaitReason
0x140039cc3  call    cs:__imp_KeWaitForSingleObject
0x140039cca  nop     dword ptr [rax+rax+00h]
0x140039ccf  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x140039cd3  test    ecx, ecx
0x140039cd5  jns     short loc_140039D2D
0x140039cd7  test    cs:byte_14005C48E, 20h
0x140039cde  jz      short loc_140039D33
0x140039ce0  mov     dword ptr [rsp+250h+Timeout], ecx
0x140039ce4  lea     r9, aDataTestSettin_0; "[data] Test setting IPV6_TCLASS failed "...
0x140039ceb  jmp     short loc_140039D05
0x140039ced  test    eax, eax
0x140039cef  jns     short loc_140039CCF
0x140039cf1  test    cs:byte_14005C48E, 20h
0x140039cf8  jz      short loc_140039D33
0x140039cfa  mov     dword ptr [rsp+250h+Timeout], eax
0x140039cfe  lea     r9, aDataTestSettin; "[data] Test setting IPV6_TCLASS failed,"...
0x140039d05  mov     r8, rsi; MaxCount
0x140039d08  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x140039d0c  mov     rdx, rdi; SizeInBytes
0x140039d0f  call    cs:__imp__snprintf_s
0x140039d16  nop     dword ptr [rax+rax+00h]
0x140039d1b  lea     r8, [rbp+150h+DstBuf]
0x140039d1f  lea     rdx, QuicLogWarning
0x140039d26  call    McTemplateU0s_EtwWriteTransfer
0x140039d2b  jmp     short loc_140039D33
0x140039d2d  bts     dword ptr [r15+38h], 8
0x140039d33  cmp     cs:dword_14005DA50, 4F7Ch
0x140039d3d  jz      short loc_140039D5A
0x140039d3f  mov     eax, [r15+38h]
0x140039d43  mov     rcx, [rbp+150h+var_1C8]
0x140039d47  or      eax, edi
0x140039d49  mov     [r15+38h], eax
0x140039d4d  cmp     byte ptr [rcx], 0
0x140039d50  jz      short loc_140039D5A
0x140039d52  bts     eax, 0Ah
0x140039d56  mov     [r15+38h], eax
0x140039d5a  xor     edx, edx; Iostatus
0x140039d5c  lea     rcx, [rbp+150h+Irp]; Irp
0x140039d60  call    cs:__imp_IoReuseIrp
0x140039d67  nop     dword ptr [rax+rax+00h]
0x140039d6c  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x140039d73  lea     rcx, CxPlatDataPathIoCompletion
0x140039d7a  mov     [rax-10h], rcx
0x140039d7e  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039d83  mov     [rax-8], rcx
0x140039d87  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x140039d8c  mov     byte ptr [rax-45h], 0E0h
0x140039d90  call    cs:__imp_KeResetEvent
  ... truncated ...
```
