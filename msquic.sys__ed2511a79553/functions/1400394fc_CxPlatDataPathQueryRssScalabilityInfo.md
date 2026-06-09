# CxPlatDataPathQueryRssScalabilityInfo

- ea: `0x1400394fc`
- end: `0x14003984b`
- name: `CxPlatDataPathQueryRssScalabilityInfo`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003aea0`

## callees

- `0x1400394fc`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003965f`
- `ntoskrnl!_snprintf_s` at `0x140039775`
- `ntoskrnl!_snprintf_s` at `0x14003965f`
- `ntoskrnl!_snprintf_s` at `0x140039775`
- `ntoskrnl!KeInitializeEvent` at `0x140039558`
- `ntoskrnl!KeInitializeEvent` at `0x140039558`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039608`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039726`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039802`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039608`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039726`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039802`
- `ntoskrnl!KeResetEvent` at `0x1400396b6`
- `ntoskrnl!KeResetEvent` at `0x1400397cd`
- `ntoskrnl!KeResetEvent` at `0x1400396b6`
- `ntoskrnl!KeResetEvent` at `0x1400397cd`
- `ntoskrnl!IoReuseIrp` at `0x14003968d`
- `ntoskrnl!IoReuseIrp` at `0x1400397a4`
- `ntoskrnl!IoReuseIrp` at `0x14003968d`
- `ntoskrnl!IoReuseIrp` at `0x1400397a4`
- `ntoskrnl!IoInitializeIrp` at `0x140039580`
- `ntoskrnl!IoInitializeIrp` at `0x140039580`
- `ntoskrnl!IoCleanupIrp` at `0x140039812`
- `ntoskrnl!IoCleanupIrp` at `0x140039812`

## string_xrefs

- `0x14003964b`: `[data] RSS helper socket failed to open, 0x%x`
- `0x14003962d`: `[data] RSS helper socket failed to open (async), 0x%x`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathQueryRssScalabilityInfo(__int64 a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v3; // eax
  __int64 v4; // rcx
  ULONG_PTR Information; // rdi
  __int64 v6; // rsi
  struct _IO_STACK_LOCATION *v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  struct _IO_STACK_LOCATION *v10; // rax
  PLARGE_INTEGER Timeout; // [rsp+28h] [rbp-E0h]
  PLARGE_INTEGER Timeouta; // [rsp+28h] [rbp-E0h]
  struct _KEVENT Event; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+80h] [rbp-88h]
  __int64 v16; // [rsp+88h] [rbp-80h] BYREF
  char DstBuf[128]; // [rsp+98h] [rbp-70h] BYREF
  IRP Irp; // [rsp+118h] [rbp+10h] BYREF

  v15 = 0;
  v16 = 0;
  Event.Header.Type = 0;
  Event.Header.WaitListHead = 0;
  KeInitializeEvent((PRKEVENT)&Event.Header.WaitListHead, SynchronizationEvent, 0);
  memset(&Irp, 0, 0x118u);
  IoInitializeIrp(&Irp, 0x118u, 1);
  CurrentStackLocation = Irp.Tail.Overlay.CurrentStackLocation;
  Irp.Tail.Overlay.CurrentStackLocation[-1].Context = &Event.Header.WaitListHead;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
  CurrentStackLocation[-1].Control = -32;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, IRP *))(*(_QWORD *)(a1 + 104) + 8LL))(
         *(_QWORD *)(a1 + 96),
         23,
         1,
         6,
         0,
         0,
         0,
         0,
         0,
         0,
         &Irp);
  if ( v3 == 259 )
  {
    KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
    goto LABEL_3;
  }
  if ( v3 >= 0 )
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
          "[data] RSS helper socket failed to open (async), 0x%x",
          Timeout);
LABEL_9:
        McTemplateU0s_EtwWriteTransfer(v4, QuicLogWarning, DstBuf);
        return IoCleanupIrp(&Irp);
      }
      return IoCleanupIrp(&Irp);
    }
    Information = Irp.IoStatus.Information;
    v6 = *(_QWORD *)Irp.IoStatus.Information;
    IoReuseIrp(&Irp, 0);
    v7 = Irp.Tail.Overlay.CurrentStackLocation;
    Irp.Tail.Overlay.CurrentStackLocation[-1].Context = &Event.Header.WaitListHead;
    v7[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
    v7[-1].Control = -32;
    KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
    v8 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64, __int64, __int64, _QWORD, _QWORD, __int64, struct _KEVENT *, __int64 *, IRP *))v6)(
           Information,
           2,
           1476395218,
           0xFFFF,
           0,
           0,
           1,
           &Event,
           &v16,
           &Irp);
    if ( v8 == 259 )
    {
      KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
    }
    else if ( v8 < 0 )
    {
      if ( (byte_14005C48E & 0x20) == 0 )
        goto LABEL_21;
      LODWORD(Timeouta) = v8;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "[data] Query for SIO_QUERY_RSS_SCALABILITY_INFO failed, 0x%x",
        Timeouta);
      goto LABEL_18;
    }
    if ( Irp.IoStatus.Status >= 0 )
    {
      if ( Event.Header.Type )
        *(_DWORD *)(a1 + 56) |= 1u;
      goto LABEL_21;
    }
    if ( (byte_14005C48E & 0x20) == 0 )
    {
LABEL_21:
      IoReuseIrp(&Irp, 0);
      v10 = Irp.Tail.Overlay.CurrentStackLocation;
      Irp.Tail.Overlay.CurrentStackLocation[-1].Context = &Event.Header.WaitListHead;
      v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CxPlatDataPathIoCompletion;
      v10[-1].Control = -32;
      KeResetEvent((PRKEVENT)&Event.Header.WaitListHead);
      if ( (*(unsigned int (__fastcall **)(ULONG_PTR, IRP *))(v6 + 8))(Information, &Irp) == 259 )
        KeWaitForSingleObject(&Event.Header.WaitListHead, Executive, 0, 0, 0);
      return IoCleanupIrp(&Irp);
    }
    LODWORD(Timeouta) = Irp.IoStatus.Status;
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[data] Query for SIO_QUERY_RSS_SCALABILITY_INFO failed (async), 0x%x",
      Timeouta);
LABEL_18:
    McTemplateU0s_EtwWriteTransfer(v9, QuicLogWarning, DstBuf);
    goto LABEL_21;
  }
  if ( (byte_14005C48E & 0x20) != 0 )
  {
    LODWORD(Timeout) = v3;
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[data] RSS helper socket failed to open, 0x%x", Timeout);
    goto LABEL_9;
  }
  return IoCleanupIrp(&Irp);
}

```

## disassembly

```asm
0x1400394fc  mov     rax, rsp
0x1400394ff  mov     [rax+10h], rbx
0x140039503  mov     [rax+18h], rsi
0x140039507  mov     [rax+20h], rdi
0x14003950b  push    rbp
0x14003950c  push    r13
0x14003950e  push    r14
0x140039510  lea     rbp, [rax-158h]
0x140039517  sub     rsp, 240h
0x14003951e  mov     rax, cs:__security_cookie
0x140039525  xor     rax, rsp
0x140039528  mov     [rbp+150h+var_20], rax
0x14003952f  xor     eax, eax
0x140039531  mov     rbx, rcx
0x140039534  xor     r14d, r14d
0x140039537  mov     [rsp+250h+var_1D8], rax
0x14003953c  xorps   xmm0, xmm0
0x14003953f  mov     [rbp+150h+var_1D0], r14
0x140039543  xor     r8d, r8d; State
0x140039546  mov     byte ptr [rsp+250h+Event.Header], r14b
0x14003954b  lea     edx, [rax+1]; Type
0x14003954e  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x140039553  movups  xmmword ptr [rsp+250h+Event.Header.WaitListHead.Flink], xmm0
0x140039558  call    cs:__imp_KeInitializeEvent
0x14003955f  nop     dword ptr [rax+rax+00h]
0x140039564  mov     edi, 118h
0x140039569  lea     rcx, [rbp+150h+Irp]; void *
0x14003956d  mov     r8d, edi; Size
0x140039570  xor     edx, edx; Val
0x140039572  call    memset
0x140039577  mov     edx, edi; PacketSize
0x140039579  lea     rcx, [rbp+150h+Irp]; Irp
0x14003957d  mov     r8b, 1; StackSize
0x140039580  call    cs:__imp_IoInitializeIrp
0x140039587  nop     dword ptr [rax+rax+00h]
0x14003958c  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x140039593  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x140039598  lea     r13, CxPlatDataPathIoCompletion
0x14003959f  lea     edx, [r14+17h]
0x1400395a3  lea     r8d, [r14+1]
0x1400395a7  mov     [rax-8], rcx
0x1400395ab  lea     r9d, [r14+6]
0x1400395af  mov     [rax-10h], r13
0x1400395b3  lea     rcx, [rbp+150h+Irp]
0x1400395b7  mov     [rsp+250h+var_200], rcx
0x1400395bc  mov     [rsp+250h+var_208], r14
0x1400395c1  mov     byte ptr [rax-45h], 0E0h
0x1400395c5  mov     rax, [rbx+68h]
0x1400395c9  mov     rcx, [rbx+60h]
0x1400395cd  mov     [rsp+250h+var_210], r14
0x1400395d2  mov     [rsp+250h+var_218], r14
0x1400395d7  mov     rax, [rax+8]
0x1400395db  mov     [rsp+250h+var_220], r14
0x1400395e0  mov     [rsp+250h+var_228], r14
0x1400395e5  mov     dword ptr [rsp+250h+Timeout], r14d
0x1400395ea  call    _guard_dispatch_icall
0x1400395ef  cmp     eax, 103h
0x1400395f4  jnz     short loc_140039636
0x1400395f6  xor     r9d, r9d; Alertable
0x1400395f9  mov     [rsp+250h+Timeout], r14; Timeout
0x1400395fe  xor     r8d, r8d; WaitMode
0x140039601  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039606  xor     edx, edx; WaitReason
0x140039608  call    cs:__imp_KeWaitForSingleObject
0x14003960f  nop     dword ptr [rax+rax+00h]
0x140039614  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x140039618  test    ecx, ecx
0x14003961a  jns     short loc_140039680
0x14003961c  test    cs:byte_14005C48E, 20h
0x140039623  jz      loc_14003980E
0x140039629  mov     dword ptr [rsp+250h+Timeout], ecx
0x14003962d  lea     r9, aDataRssHelperS_0; "[data] RSS helper socket failed to open"...
0x140039634  jmp     short loc_140039652
0x140039636  test    eax, eax
0x140039638  jns     short loc_140039614
0x14003963a  test    cs:byte_14005C48E, 20h
0x140039641  jz      loc_14003980E
0x140039647  mov     dword ptr [rsp+250h+Timeout], eax
0x14003964b  lea     r9, aDataRssHelperS; "[data] RSS helper socket failed to open"...
0x140039652  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140039656  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x14003965a  mov     edx, 80h; SizeInBytes
0x14003965f  call    cs:__imp__snprintf_s
0x140039666  nop     dword ptr [rax+rax+00h]
0x14003966b  lea     r8, [rbp+150h+DstBuf]
0x14003966f  lea     rdx, QuicLogWarning
0x140039676  call    McTemplateU0s_EtwWriteTransfer
0x14003967b  jmp     loc_14003980E
0x140039680  mov     rdi, [rbp+150h+Irp.IoStatus.Information]
0x140039684  lea     rcx, [rbp+150h+Irp]; Irp
0x140039688  xor     edx, edx; Iostatus
0x14003968a  mov     rsi, [rdi]
0x14003968d  call    cs:__imp_IoReuseIrp
0x140039694  nop     dword ptr [rax+rax+00h]
0x140039699  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x1400396a0  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x1400396a5  mov     [rax-8], rcx
0x1400396a9  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x1400396ae  mov     [rax-10h], r13
0x1400396b2  mov     byte ptr [rax-45h], 0E0h
0x1400396b6  call    cs:__imp_KeResetEvent
0x1400396bd  nop     dword ptr [rax+rax+00h]
0x1400396c2  mov     rax, [rsi]
0x1400396c5  lea     rcx, [rbp+150h+Irp]
0x1400396c9  mov     [rsp+250h+var_208], rcx
0x1400396ce  mov     edx, 2
0x1400396d3  lea     rcx, [rbp+150h+var_1D0]
0x1400396d7  mov     r9d, 0FFFFh
0x1400396dd  mov     [rsp+250h+var_210], rcx
0x1400396e2  mov     r8d, 580000D2h
0x1400396e8  lea     rcx, [rsp+250h+Event]
0x1400396ed  mov     [rsp+250h+var_218], rcx
0x1400396f2  mov     rcx, rdi
0x1400396f5  mov     [rsp+250h+var_220], 1
0x1400396fe  mov     [rsp+250h+var_228], r14
0x140039703  mov     [rsp+250h+Timeout], r14
0x140039708  call    _guard_dispatch_icall
0x14003970d  cmp     eax, 103h
0x140039712  jnz     short loc_140039750
0x140039714  xor     r9d, r9d; Alertable
0x140039717  mov     [rsp+250h+Timeout], r14; Timeout
0x14003971c  xor     r8d, r8d; WaitMode
0x14003971f  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039724  xor     edx, edx; WaitReason
0x140039726  call    cs:__imp_KeWaitForSingleObject
0x14003972d  nop     dword ptr [rax+rax+00h]
0x140039732  mov     rcx, qword ptr [rbp+150h+Irp.IoStatus]
0x140039736  test    ecx, ecx
0x140039738  jns     short loc_140039793
0x14003973a  test    cs:byte_14005C48E, 20h
0x140039741  jz      short loc_14003979E
0x140039743  mov     dword ptr [rsp+250h+Timeout], ecx
0x140039747  lea     r9, aDataQueryForSi; "[data] Query for SIO_QUERY_RSS_SCALABIL"...
0x14003974e  jmp     short loc_140039768
0x140039750  test    eax, eax
0x140039752  jns     short loc_140039732
0x140039754  test    cs:byte_14005C48E, 20h
0x14003975b  jz      short loc_14003979E
0x14003975d  mov     dword ptr [rsp+250h+Timeout], eax
0x140039761  lea     r9, aDataQueryForSi_0; "[data] Query for SIO_QUERY_RSS_SCALABIL"...
0x140039768  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003976c  lea     rcx, [rbp+150h+DstBuf]; DstBuf
0x140039770  mov     edx, 80h; SizeInBytes
0x140039775  call    cs:__imp__snprintf_s
0x14003977c  nop     dword ptr [rax+rax+00h]
0x140039781  lea     r8, [rbp+150h+DstBuf]
0x140039785  lea     rdx, QuicLogWarning
0x14003978c  call    McTemplateU0s_EtwWriteTransfer
0x140039791  jmp     short loc_14003979E
0x140039793  cmp     byte ptr [rsp+250h+Event.Header], r14b
0x140039798  jz      short loc_14003979E
0x14003979a  or      dword ptr [rbx+38h], 1
0x14003979e  xor     edx, edx; Iostatus
0x1400397a0  lea     rcx, [rbp+150h+Irp]; Irp
0x1400397a4  call    cs:__imp_IoReuseIrp
0x1400397ab  nop     dword ptr [rax+rax+00h]
0x1400397b0  mov     rax, qword ptr [rbp+150h+Irp.Tail+40h]
0x1400397b7  lea     rcx, [rsp+250h+Event.Header.WaitListHead]
0x1400397bc  mov     [rax-8], rcx
0x1400397c0  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Event
0x1400397c5  mov     [rax-10h], r13
0x1400397c9  mov     byte ptr [rax-45h], 0E0h
0x1400397cd  call    cs:__imp_KeResetEvent
0x1400397d4  nop     dword ptr [rax+rax+00h]
0x1400397d9  mov     rax, [rsi+8]
0x1400397dd  lea     rdx, [rbp+150h+Irp]
0x1400397e1  mov     rcx, rdi
0x1400397e4  call    _guard_dispatch_icall
0x1400397e9  cmp     eax, 103h
0x1400397ee  jnz     short loc_14003980E
0x1400397f0  xor     r9d, r9d; Alertable
0x1400397f3  mov     [rsp+250h+Timeout], r14; Timeout
0x1400397f8  xor     r8d, r8d; WaitMode
0x1400397fb  lea     rcx, [rsp+250h+Event.Header.WaitListHead]; Object
0x140039800  xor     edx, edx; WaitReason
0x140039802  call    cs:__imp_KeWaitForSingleObject
0x140039809  nop     dword ptr [rax+rax+00h]
0x14003980e  lea     rcx, [rbp+150h+Irp]
0x140039812  call    cs:__imp_IoCleanupIrp
0x140039819  nop     dword ptr [rax+rax+00h]
0x14003981e  mov     rcx, [rbp+150h+var_20]
0x140039825  xor     rcx, rsp; StackCookie
0x140039828  call    __security_check_cookie
0x14003982d  lea     r11, [rsp+250h+var_10]
0x140039835  mov     rbx, [r11+28h]
0x140039839  mov     rsi, [r11+30h]
0x14003983d  mov     rdi, [r11+38h]
0x140039841  mov     rsp, r11
0x140039844  pop     r14
0x140039846  pop     r13
0x140039848  pop     rbp
0x140039849  retn
```
