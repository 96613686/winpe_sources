# NbtOpenAndAssocConnection

- ea: `0x140012a10`
- end: `0x14001317b`
- name: `NbtOpenAndAssocConnection`
- size: `1899`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x14000efd4`
- `0x140011d68`
- `0x140012694`
- `0x140029d28`
- `0x14004bb10`

## callees

- `0x140012a10`
- `0x140013184`
- `0x140014500`
- `0x140014564`
- `0x140030f40`
- `0x140031440`
- `0x140041cf4`
- `0x1400439bc`
- `0x14004c4a8`
- `0x14004eaa0`
- `0x14004eda0`
- `0x140050b38`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140012c44`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140012c44`
- `ntoskrnl!IofCallDriver` at `0x140012c82`
- `ntoskrnl!IofCallDriver` at `0x140012c82`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140012c03`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140012c6e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140012c03`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140012c6e`
- `ntoskrnl!ExQueueWorkItem` at `0x140012e7b`
- `ntoskrnl!ExQueueWorkItem` at `0x140012e7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400130df`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400130df`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012f16`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001300b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400130fd`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012f16`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001300b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400130fd`
- `ntoskrnl!KeStackAttachProcess` at `0x140012f56`
- `ntoskrnl!KeStackAttachProcess` at `0x140012f56`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012acd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140012acd`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140012cd7`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140012cd7`
- `ntoskrnl!KeInitializeEvent` at `0x140012bf2`
- `ntoskrnl!KeInitializeEvent` at `0x140012bf2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012d16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012d16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e03`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012da9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012caa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012caa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f35`
- `ntoskrnl!ExAllocatePool2` at `0x140012a95`
- `ntoskrnl!ExAllocatePool2` at `0x140012b95`
- `ntoskrnl!ExAllocatePool2` at `0x140012eb0`
- `ntoskrnl!ExAllocatePool2` at `0x140012a95`
- `ntoskrnl!ExAllocatePool2` at `0x140012b95`
- `ntoskrnl!ExAllocatePool2` at `0x140012eb0`

## pseudocode

```c
__int64 __fastcall NbtOpenAndAssocConnection(__int64 a1, __int64 a2, char **a3, char a4)
{
  __int64 v4; // rdi
  char *Pool2; // rax
  char *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  char v13; // r13
  __int64 v14; // rdx
  int v15; // ebp
  const char *v16; // r8
  __int64 v17; // rax
  void *v18; // rdi
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  PIRP v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  struct _DEVICE_OBJECT *v23; // rax
  unsigned int v24; // eax
  __int64 Status; // r9
  struct _LIST_ENTRY *v26; // rcx
  KIRQL v27; // al
  KIRQL v28; // dl
  KSPIN_LOCK *v29; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdi
  KIRQL v33; // al
  __int64 *v34; // rcx
  KIRQL v35; // bl
  __int64 v36; // rax
  int v37; // edx
  int v38; // r8d
  int v39; // eax
  int InternalDeviceIoControl; // [rsp+30h] [rbp-C8h]
  int FileObject; // [rsp+50h] [rbp-A8h]
  struct _FILE_OBJECT *FileObjecta; // [rsp+50h] [rbp-A8h]
  PIRP Irp; // [rsp+58h] [rbp-A0h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-80h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+88h] [rbp-70h] BYREF

  v4 = 0;
  Irp = 0;
  HIWORD(FileObject) = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( a3 )
    *a3 = 0;
  LOBYTE(FileObject) = a4;
  BYTE1(FileObject) = 76;
  Pool2 = (char *)ExAllocatePool2(64, 296, (((FileObject << 16) | FileObject & 0xFF00) << 8) | 0x624Eu);
  v9 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x128u);
    if ( (PRKPROCESS)PsGetCurrentProcess(v11, v10, v12) == NbtFspProcess )
    {
      v13 = 0;
    }
    else
    {
      KeStackAttachProcess(NbtFspProcess, &ApcState);
      v13 = 1;
    }
    v15 = NbtTdiOpenConnection(v9, a1);
    if ( v15 < 0 )
    {
      if ( v13 )
        KeUnstackDetachProcess(&ApcState);
      ExFreePoolWithTag(v9, 0);
      return (unsigned int)v15;
    }
    v16 = "minio\\netbt\\sys\\name.c";
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    {
      WPP_SF_qddds(
        *((_DWORD *)v9 + 5),
        11,
        (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
        (_DWORD)v9,
        *((_DWORD *)v9 + 5),
        *((_DWORD *)v9 + 5) + 1,
        19,
        (__int64)"minio\\netbt\\sys\\name.c");
      v16 = "minio\\netbt\\sys\\name.c";
    }
    _InterlockedIncrement((volatile signed __int32 *)v9 + 5);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v9 + 5),
        11,
        (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
        (_DWORD)v9,
        *((_DWORD *)v9 + 5),
        *((_DWORD *)v9 + 5) + 1,
        20,
        (__int64)"minio\\netbt\\sys\\name.c");
    _InterlockedIncrement((volatile signed __int32 *)v9 + 5);
    if ( a2 )
    {
      v15 = NbtSetEndpointOptionsPrebind(a2, v14, v16);
      if ( v15 >= 0 )
      {
        *((_DWORD *)v9 + 23) = 0;
        *((_QWORD *)v9 + 25) = RejectAnyData;
        *((_DWORD *)v9 + 52) = 15;
        v39 = NbtTdiOpenAddress(
                (void **)v9 + 9,
                (PDEVICE_OBJECT *)&Irp,
                (struct _FILE_OBJECT **)v9 + 7,
                a1,
                0,
                *(_DWORD *)(a1 + 488),
                InternalDeviceIoControl,
                1);
        v4 = *((_QWORD *)v9 + 9);
        v15 = v39;
      }
      NbtCleanupPrebindOptions(a2);
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 624);
    }
    if ( v4 )
    {
      if ( v15 >= 0 )
      {
        v15 = NbtTdiAssociateConnection(*((PFILE_OBJECT *)v9 + 6));
        if ( v15 >= 0 )
        {
          if ( *(_BYTE *)(a1 + 908) )
            goto LABEL_23;
          FileObjecta = (struct _FILE_OBJECT *)*((_QWORD *)v9 + 6);
          v17 = ExAllocatePool2(64, 32, 842162766);
          v18 = (void *)v17;
          if ( !v17 )
            goto LABEL_23;
          *(_QWORD *)v17 = 1024;
          *(_QWORD *)(v17 + 24) = 1;
          *(_DWORD *)(v17 + 8) = 512;
          *(_DWORD *)(v17 + 20) = 4;
          *(_DWORD *)(v17 + 16) = 1;
          *(_DWORD *)(v17 + 12) = 768;
          IoStatusBlock = 0;
          memset(&Event, 0, sizeof(Event));
          KeInitializeEvent(&Event, NotificationEvent, 0);
          RelatedDeviceObject = IoGetRelatedDeviceObject(FileObjecta);
          v20 = IoBuildDeviceIoControlRequest(
                  0x128004u,
                  RelatedDeviceObject,
                  v18,
                  0x20u,
                  0,
                  0,
                  0,
                  &Event,
                  &IoStatusBlock);
          Irp = v20;
          if ( v20 )
          {
            v20->Tail.Overlay.CurrentStackLocation[-1].FileObject = FileObjecta;
            v23 = IoGetRelatedDeviceObject(FileObjecta);
            v24 = IofCallDriver(v23, Irp);
            Status = v24;
            if ( v24 == 259 )
            {
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              Status = (unsigned int)IoStatusBlock.Status;
            }
            if ( (int)Status >= 0 )
              goto LABEL_22;
          }
          else
          {
            Status = 3221225626LL;
          }
          if ( (BYTE1(xmmword_140038420) & 1) != 0 )
            WPP_SF_DDDD(v21, 41, v22, Status, 1, 768, 1);
LABEL_22:
          ExFreePoolWithTag(v18, 0);
LABEL_23:
          if ( a2 )
          {
            *((_QWORD *)v9 + 3) = a2;
            v26 = (struct _LIST_ENTRY *)(a1 + 400);
          }
          else
          {
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 896));
            v26 = (struct _LIST_ENTRY *)(a1 + 416);
          }
          ExInterlockedInsertTailList(v26, (PLIST_ENTRY)v9, (PKSPIN_LOCK)(a1 + 848));
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 900));
          if ( v13 )
            KeUnstackDetachProcess(&ApcState);
          if ( a3 )
            *a3 = v9;
          if ( a2 )
            v15 = NbtSetEndpointOptionsPostbind(a2, *((_QWORD *)v9 + 7));
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              *((_DWORD *)v9 + 5),
              83,
              (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
              (_DWORD)v9,
              *((_DWORD *)v9 + 5),
              *((_DWORD *)v9 + 5) - 1,
              109,
              (__int64)"minio\\netbt\\sys\\name.c");
          v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v9 + 13);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 5, 0xFFFFFFFF) == 1 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v9 + 5) + 900LL));
            v31 = *((_QWORD *)v9 + 3);
            *((_DWORD *)v9 + 5) = 1000;
            if ( v31 && ((*(_DWORD *)(v31 + 16) - 829321027) & 0xFEFFFFFF) == 0 )
            {
              *(_DWORD *)(v31 + 48) = 9;
              *(_QWORD *)(v31 + 24) = 0;
              *((_QWORD *)v9 + 3) = 0;
              *(_BYTE *)(v31 + 267) = 9;
              v9[124] = 9;
            }
            KeReleaseSpinLock((PKSPIN_LOCK)v9 + 13, v27);
            v32 = (__int64)(v9 + 128);
            if ( v9 == (char *)-128LL || *((_DWORD *)v9 + 48) )
            {
              v36 = ExAllocatePool2(64, 72, 842162766);
              v32 = v36;
              if ( !v36 )
                return (unsigned int)v15;
              *(_DWORD *)(v36 + 60) = 1;
            }
            else
            {
              *((_DWORD *)v9 + 47) = 0;
            }
            *(_DWORD *)(v32 + 64) = 1;
            *(_QWORD *)(v32 + 48) = &DelayedWipeOutLowerconn;
            *(_QWORD *)(v32 + 16) = 0;
            *(_QWORD *)(v32 + 24) = v9;
            *(_QWORD *)(v32 + 32) = 0;
            *(_QWORD *)(v32 + 40) = 0;
            *(_BYTE *)(v32 + 68) = 32;
            *(_QWORD *)(v32 + 8) = v32;
            *(_QWORD *)v32 = v32;
            v33 = KeAcquireSpinLockRaiseToDpc(&qword_1400396D8);
            v34 = (__int64 *)qword_1400396E8;
            v35 = v33;
            if ( *(PVOID **)qword_1400396E8 != &P )
              __fastfail(3u);
            *(_QWORD *)v32 = &P;
            *(_QWORD *)(v32 + 8) = v34;
            *v34 = v32;
            qword_1400396E8 = v32;
            _InterlockedIncrement(&dword_1400396F0);
            if ( !byte_140039752 && !_InterlockedExchange(&dword_1400396F4, 1) )
            {
              WorkItem.List.Flink = 0;
              WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NTExecuteWorker;
              WorkItem.Parameter = &WorkItem;
              ExQueueWorkItem(&WorkItem, CriticalWorkQueue);
            }
            v28 = v35;
            v29 = &qword_1400396D8;
          }
          else
          {
            v28 = v27;
            v29 = (KSPIN_LOCK *)(v9 + 104);
          }
          KeReleaseSpinLock(v29, v28);
          return (unsigned int)v15;
        }
      }
    }
    else
    {
      v15 = -1073741823;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 900));
    NbtDereferenceLowerConnection((_DWORD)v9, v14, (_DWORD)v16, 2169, (__int64)"minio\\netbt\\sys\\name.c");
    NbtDereferenceLowerConnection((_DWORD)v9, v37, v38, 2170, (__int64)"minio\\netbt\\sys\\name.c");
    if ( v13 )
      KeUnstackDetachProcess(&ApcState);
    return (unsigned int)v15;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140012a10  mov     r11, rsp
0x140012a13  push    rbx
0x140012a14  push    rsi
0x140012a15  push    rdi
0x140012a16  push    r14
0x140012a18  push    r15
0x140012a1a  sub     rsp, 0D0h
0x140012a21  mov     rax, cs:__security_cookie
0x140012a28  xor     rax, rsp
0x140012a2b  mov     [rsp+0F8h+var_40], rax
0x140012a33  xor     edi, edi
0x140012a35  xorps   xmm0, xmm0
0x140012a38  mov     [rsp+0F8h+Irp], rdi
0x140012a3d  mov     r15, r8
0x140012a40  mov     dword ptr [rsp+0F8h+FileObject], edi
0x140012a44  mov     r14, rdx
0x140012a47  mov     rsi, rcx
0x140012a4a  movups  xmmword ptr [r11-70h], xmm0
0x140012a4f  movups  xmmword ptr [r11-60h], xmm0
0x140012a54  movups  xmmword ptr [r11-50h], xmm0
0x140012a59  test    r8, r8
0x140012a5c  jnz     loc_140012F46
0x140012a62  mov     byte ptr [rsp+0F8h+FileObject], r9b
0x140012a67  mov     edx, 128h
0x140012a6c  mov     byte ptr [rsp+0F8h+FileObject+1], 4Ch ; 'L'
0x140012a71  mov     ecx, 40h ; '@'
0x140012a76  mov     eax, dword ptr [rsp+0F8h+FileObject]
0x140012a7a  mov     r8d, eax
0x140012a7d  and     r8d, 0FF00h
0x140012a84  shl     eax, 10h
0x140012a87  or      r8d, eax
0x140012a8a  shl     r8d, 8
0x140012a8e  or      r8d, 624Eh
0x140012a95  call    cs:__imp_ExAllocatePool2
0x140012a9c  nop     dword ptr [rax+rax+00h]
0x140012aa1  mov     rbx, rax
0x140012aa4  test    rax, rax
0x140012aa7  jz      loc_140012E96
0x140012aad  mov     [rsp+0F8h+arg_18], rbp
0x140012ab5  xor     edx, edx; Val
0x140012ab7  mov     r8d, 128h; Size
0x140012abd  mov     [rsp+0F8h+var_38], r13
0x140012ac5  mov     rcx, rax; void *
0x140012ac8  call    memset
0x140012acd  call    cs:__imp_PsGetCurrentProcess
0x140012ad4  nop     dword ptr [rax+rax+00h]
0x140012ad9  mov     rcx, cs:NbtFspProcess; PROCESS
0x140012ae0  cmp     rax, rcx
0x140012ae3  jnz     loc_140012F4E
0x140012ae9  xor     r13b, r13b
0x140012aec  mov     rdx, rsi
0x140012aef  mov     rcx, rbx; VirtualAddress
0x140012af2  call    NbtTdiOpenConnection
0x140012af7  mov     ebp, eax
0x140012af9  test    eax, eax
0x140012afb  js      loc_140012F27
0x140012b01  mov     [rsp+0F8h+var_30], r12
0x140012b09  test    byte ptr cs:xmmword_140038420+9, 40h
0x140012b10  lea     r8, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140012b17  jnz     loc_14001301C
0x140012b1d  lock inc dword ptr [rbx+14h]
0x140012b21  test    byte ptr cs:xmmword_140038420+9, 40h
0x140012b28  jnz     loc_140013057
0x140012b2e  lock inc dword ptr [rbx+14h]
0x140012b32  mov     r12d, 1
0x140012b38  test    r14, r14
0x140012b3b  jnz     loc_140012F85
0x140012b41  mov     rdi, [rsi+270h]
0x140012b48  test    rdi, rdi
0x140012b4b  jz      loc_14001308B
0x140012b51  test    ebp, ebp
0x140012b53  js      loc_140012ED1
0x140012b59  mov     rcx, [rbx+30h]; FileObject
0x140012b5d  mov     rdx, rdi
0x140012b60  call    NbtTdiAssociateConnection
0x140012b65  mov     ebp, eax
0x140012b67  test    eax, eax
0x140012b69  js      loc_140012ED1
0x140012b6f  cmp     byte ptr [rsi+38Ch], 0
0x140012b76  jnz     loc_140012CB6
0x140012b7c  mov     rax, [rbx+30h]
0x140012b80  mov     edx, 20h ; ' '
0x140012b85  mov     ecx, 40h ; '@'
0x140012b8a  mov     [rsp+0F8h+FileObject], rax
0x140012b8f  mov     r8d, 3232624Eh
0x140012b95  call    cs:__imp_ExAllocatePool2
0x140012b9c  nop     dword ptr [rax+rax+00h]
0x140012ba1  mov     rdi, rax
0x140012ba4  test    rax, rax
0x140012ba7  jz      loc_140012CB6
0x140012bad  mov     qword ptr [rax], 400h
0x140012bb4  lea     rcx, [rsp+0F8h+Event]; Event
0x140012bb9  mov     [rax+18h], r12
0x140012bbd  xorps   xmm0, xmm0
0x140012bc0  mov     dword ptr [rax+8], 200h
0x140012bc7  xorps   xmm1, xmm1
0x140012bca  mov     dword ptr [rax+14h], 4
0x140012bd1  xor     r8d, r8d; State
0x140012bd4  mov     [rax+10h], r12d
0x140012bd8  xor     edx, edx; Type
0x140012bda  mov     dword ptr [rax+0Ch], 300h
0x140012be1  xor     eax, eax
0x140012be3  mov     [rsp+0F8h+Event.Header.WaitListHead.Blink], rax
0x140012be8  movups  xmmword ptr [rsp+0F8h+var_80], xmm0
0x140012bed  movups  xmmword ptr [rsp+0F8h+Event.Header], xmm1
0x140012bf2  call    cs:__imp_KeInitializeEvent
0x140012bf9  nop     dword ptr [rax+rax+00h]
0x140012bfe  mov     rcx, [rsp+0F8h+FileObject]; FileObject
0x140012c03  call    cs:__imp_IoGetRelatedDeviceObject
0x140012c0a  nop     dword ptr [rax+rax+00h]
0x140012c0f  mov     r9d, 20h ; ' '; InputBufferLength
0x140012c15  mov     r8, rdi; InputBuffer
0x140012c18  mov     rdx, rax; DeviceObject
0x140012c1b  mov     ecx, 128004h; IoControlCode
0x140012c20  lea     rax, [rsp+0F8h+var_80]
0x140012c25  mov     [rsp+0F8h+IoStatusBlock], rax; IoStatusBlock
0x140012c2a  lea     rax, [rsp+0F8h+Event]
0x140012c2f  mov     [rsp+0F8h+var_C0], rax; Event
0x140012c34  xor     eax, eax
0x140012c36  mov     [rsp+0F8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140012c3b  mov     [rsp+0F8h+OutputBufferLength], eax; OutputBufferLength
0x140012c3f  mov     [rsp+0F8h+OutputBuffer], rax; OutputBuffer
0x140012c44  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140012c4b  nop     dword ptr [rax+rax+00h]
0x140012c50  mov     [rsp+0F8h+Irp], rax
0x140012c55  test    rax, rax
0x140012c58  jz      loc_140013095
0x140012c5e  mov     rax, [rax+0B8h]
0x140012c65  mov     rcx, [rsp+0F8h+FileObject]; FileObject
0x140012c6a  mov     [rax-18h], rcx
0x140012c6e  call    cs:__imp_IoGetRelatedDeviceObject
0x140012c75  nop     dword ptr [rax+rax+00h]
0x140012c7a  mov     rdx, [rsp+0F8h+Irp]; Irp
0x140012c7f  mov     rcx, rax; DeviceObject
0x140012c82  call    cs:__imp_IofCallDriver
0x140012c89  nop     dword ptr [rax+rax+00h]
0x140012c8e  mov     r9d, eax
0x140012c91  cmp     eax, 103h
0x140012c96  jz      loc_1400130C9
0x140012c9c  test    r9d, r9d
0x140012c9f  js      loc_14001309B
0x140012ca5  xor     edx, edx; Tag
0x140012ca7  mov     rcx, rdi; P
0x140012caa  call    cs:__imp_ExFreePoolWithTag
0x140012cb1  nop     dword ptr [rax+rax+00h]
0x140012cb6  lea     r8, [rsi+350h]; Lock
0x140012cbd  mov     rdx, rbx; ListEntry
0x140012cc0  test    r14, r14
0x140012cc3  jnz     loc_140012FEC
0x140012cc9  lock inc dword ptr [rsi+380h]
0x140012cd0  lea     rcx, [rsi+1A0h]; ListHead
0x140012cd7  call    cs:__imp_ExInterlockedInsertTailList
0x140012cde  nop     dword ptr [rax+rax+00h]
0x140012ce3  lock inc dword ptr [rsi+384h]
0x140012cea  test    r13b, r13b
0x140012ced  jnz     loc_1400130F5
0x140012cf3  test    r15, r15
0x140012cf6  jnz     loc_140012F7D
0x140012cfc  test    r14, r14
0x140012cff  jnz     loc_140012F6A
0x140012d05  test    byte ptr cs:xmmword_140038420+9, 40h
0x140012d0c  jnz     loc_14001310E
0x140012d12  lea     rcx, [rbx+68h]; SpinLock
0x140012d16  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012d1d  nop     dword ptr [rax+rax+00h]
0x140012d22  movzx   ecx, al
0x140012d25  mov     edx, 0FFFFFFFFh
0x140012d2a  lock xadd [rbx+14h], edx
0x140012d2f  cmp     edx, r12d
0x140012d32  jz      short loc_140012D81
0x140012d34  movzx   edx, al; NewIrql
0x140012d37  lea     rcx, [rbx+68h]; SpinLock
0x140012d3b  call    cs:__imp_KeReleaseSpinLock
0x140012d42  nop     dword ptr [rax+rax+00h]
0x140012d47  mov     r12, [rsp+0F8h+var_30]
0x140012d4f  mov     r13, [rsp+0F8h+var_38]
0x140012d57  mov     eax, ebp
0x140012d59  mov     rbp, [rsp+0F8h+arg_18]
0x140012d61  mov     rcx, [rsp+0F8h+var_40]
0x140012d69  xor     rcx, rsp; StackCookie
0x140012d6c  call    __security_check_cookie
0x140012d71  add     rsp, 0D0h
0x140012d78  pop     r15
0x140012d7a  pop     r14
0x140012d7c  pop     rdi
0x140012d7d  pop     rsi
0x140012d7e  pop     rbx
0x140012d7f  retn
0x140012d81  mov     rax, [rbx+28h]
0x140012d85  xor     esi, esi
0x140012d87  lock dec dword ptr [rax+384h]
0x140012d8e  mov     rdx, [rbx+18h]
0x140012d92  mov     dword ptr [rbx+14h], 3E8h
0x140012d99  test    rdx, rdx
0x140012d9c  jnz     loc_140013149
0x140012da2  movzx   edx, cl; NewIrql
0x140012da5  lea     rcx, [rbx+68h]; SpinLock
0x140012da9  call    cs:__imp_KeReleaseSpinLock
0x140012db0  nop     dword ptr [rax+rax+00h]
0x140012db5  lea     rdi, [rbx+80h]
0x140012dbc  test    rdi, rdi
0x140012dbf  jz      loc_140012EA0
0x140012dc5  cmp     dword ptr [rdi+40h], 0
0x140012dc9  jnz     loc_140012EA0
0x140012dcf  mov     [rdi+3Ch], esi
0x140012dd2  mov     [rdi+40h], r12d
0x140012dd6  lea     rax, DelayedWipeOutLowerconn
0x140012ddd  mov     [rdi+30h], rax
0x140012de1  lea     rcx, qword_1400396D8; SpinLock
0x140012de8  mov     [rdi+10h], rsi
0x140012dec  mov     [rdi+18h], rbx
0x140012df0  mov     [rdi+20h], rsi
0x140012df4  mov     [rdi+28h], rsi
0x140012df8  mov     byte ptr [rdi+44h], 20h ; ' '
0x140012dfc  mov     [rdi+8], rdi
0x140012e00  mov     [rdi], rdi
0x140012e03  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012e0a  nop     dword ptr [rax+rax+00h]
0x140012e0f  mov     rcx, cs:qword_1400396E8
0x140012e16  movzx   ebx, al
0x140012e19  lea     rax, P
0x140012e20  cmp     [rcx], rax
0x140012e23  jnz     loc_140012FFC
0x140012e29  mov     [rdi], rax
0x140012e2c  mov     [rdi+8], rcx
0x140012e30  mov     [rcx], rdi
0x140012e33  mov     cs:qword_1400396E8, rdi
0x140012e3a  lock inc cs:dword_1400396F0
0x140012e41  cmp     cs:byte_140039752, 0
0x140012e48  jnz     short loc_140012E87
0x140012e4a  xchg    r12d, cs:dword_1400396F4
0x140012e51  test    r12d, r12d
0x140012e54  jnz     short loc_140012E87
0x140012e56  lea     rax, NTExecuteWorker
0x140012e5d  mov     cs:WorkItem.List.Flink, rsi
0x140012e64  lea     rcx, WorkItem; WorkItem
0x140012e6b  mov     cs:WorkItem.WorkerRoutine, rax
0x140012e72  xor     edx, edx; QueueType
0x140012e74  mov     cs:WorkItem.Parameter, rcx
0x140012e7b  call    cs:__imp_ExQueueWorkItem
0x140012e82  nop     dword ptr [rax+rax+00h]
0x140012e87  movzx   edx, bl
0x140012e8a  lea     rcx, qword_1400396D8
0x140012e91  jmp     loc_140012D3B
0x140012e96  mov     eax, 0C000009Ah
0x140012e9b  jmp     loc_140012D61
0x140012ea0  mov     edx, 48h ; 'H'
0x140012ea5  mov     ecx, 40h ; '@'
0x140012eaa  mov     r8d, 3232624Eh
0x140012eb0  call    cs:__imp_ExAllocatePool2
0x140012eb7  nop     dword ptr [rax+rax+00h]
0x140012ebc  mov     rdi, rax
0x140012ebf  test    rax, rax
0x140012ec2  jz      loc_140012D47
0x140012ec8  mov     [rax+3Ch], r12d
0x140012ecc  jmp     loc_140012DD2
0x140012ed1  lock inc dword ptr [rsi+384h]
0x140012ed8  lea     rdi, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140012edf  mov     r9d, 879h
0x140012ee5  mov     rcx, rbx
0x140012ee8  mov     [rsp+0F8h+OutputBuffer], rdi
0x140012eed  call    NbtDereferenceLowerConnection
0x140012ef2  mov     r9d, 87Ah
0x140012ef8  mov     [rsp+0F8h+OutputBuffer], rdi
0x140012efd  mov     rcx, rbx
0x140012f00  call    NbtDereferenceLowerConnection
0x140012f05  test    r13b, r13b
0x140012f08  jz      loc_140012D47
0x140012f0e  lea     rcx, [rsp+0F8h+ApcState]; ApcState
0x140012f16  call    cs:__imp_KeUnstackDetachProcess
0x140012f1d  nop     dword ptr [rax+rax+00h]
0x140012f22  jmp     loc_140012D47
0x140012f27  test    r13b, r13b
0x140012f2a  jnz     loc_140013003
0x140012f30  xor     edx, edx; Tag
0x140012f32  mov     rcx, rbx; P
0x140012f35  call    cs:__imp_ExFreePoolWithTag
0x140012f3c  nop     dword ptr [rax+rax+00h]
0x140012f41  jmp     loc_140012D4F
0x140012f46  mov     [r8], rdi
0x140012f49  jmp     loc_140012A62
0x140012f4e  lea     rdx, [rsp+0F8h+ApcState]; ApcState
0x140012f56  call    cs:__imp_KeStackAttachProcess
0x140012f5d  nop     dword ptr [rax+rax+00h]
0x140012f62  mov     r13b, 1
0x140012f65  jmp     loc_140012AEC
0x140012f6a  mov     rdx, [rbx+38h]
0x140012f6e  mov     rcx, r14
0x140012f71  call    NbtSetEndpointOptionsPostbind
0x140012f76  mov     ebp, eax
0x140012f78  jmp     loc_140012D05
0x140012f7d  mov     [r15], rbx
0x140012f80  jmp     loc_140012CFC
0x140012f85  mov     rcx, r14
0x140012f88  call    NbtSetEndpointOptionsPrebind
0x140012f8d  mov     ebp, eax
0x140012f8f  test    eax, eax
0x140012f91  js      short loc_140012FDF
0x140012f93  lea     rax, RejectAnyData
0x140012f9a  mov     [rbx+5Ch], edi
  ... truncated ...
```
