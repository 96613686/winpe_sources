# ClasspUpdateDiskProperties

- ea: `0x140026020`
- end: `0x1400262c9`
- name: `ClasspUpdateDiskProperties`
- size: `681`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400134a0`
- `0x14001fc38`
- `0x14002001c`
- `0x14002249c`
- `0x140022514`
- `0x140026020`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002626b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002626b`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400260ec`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400260ec`
- `ntoskrnl!IoFreeWorkItem` at `0x140026295`
- `ntoskrnl!IoFreeWorkItem` at `0x140026295`
- `ntoskrnl!IofCallDriver` at `0x14002617d`
- `ntoskrnl!IofCallDriver` at `0x14002617d`
- `ntoskrnl!KeInitializeEvent` at `0x14002609c`
- `ntoskrnl!KeInitializeEvent` at `0x14002609c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400261a7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400261a7`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400260ab`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400260ab`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002611e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002611e`

## pseudocode

```c
void __fastcall ClasspUpdateDiskProperties(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  void *DeviceExtension; // rsi
  PIRP v3; // rdi
  __int64 v6; // r12
  char v7; // al
  PIRP v8; // rax
  int v9; // r14d
  __int64 v10; // rcx
  NTSTATUS Status; // ebx
  struct _DEVICE_OBJECT *Object; // [rsp+50h] [rbp-29h]
  struct _KEVENT Event; // [rsp+58h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  GUID v15; // [rsp+80h] [rbp+7h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  IoStatusBlock = 0;
  v3 = 0;
  memset(&Event, 0, sizeof(Event));
  v6 = *((_QWORD *)DeviceExtension + 143);
  if ( !*(_BYTE *)(v6 + 718) )
    goto LABEL_25;
  v7 = *((_BYTE *)DeviceExtension + 106);
  if ( (v7 & 0xFA) != 0 || v7 == 4 )
    goto LABEL_25;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  Object = IoGetAttachedDeviceReference(DeviceObject);
  v8 = IoBuildDeviceIoControlRequest(0x70140u, Object, 0, 0, 0, 0, 0, &Event, &IoStatusBlock);
  v3 = v8;
  if ( !v8 )
  {
    Status = -1073741670;
LABEL_20:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        198,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Status);
    }
    goto LABEL_24;
  }
  v9 = 0;
  v15 = 0;
  if ( ClassPnPETWEnabled )
  {
    if ( (int)IoGetActivityIdIrp(v8, &v15) >= 0 )
    {
      v9 = 1;
      if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
        McTemplateK0qpddd_EtwWriteTransfer(
          v3->Tail.Overlay.CurrentStackLocation->MinorFunction,
          (unsigned int)EventIOCTL,
          (unsigned int)&v15,
          *((_DWORD *)DeviceExtension + 147),
          (char)v3,
          v3->Tail.Overlay.CurrentStackLocation->MajorFunction,
          v3->Tail.Overlay.CurrentStackLocation->MinorFunction,
          64);
    }
  }
  Status = IofCallDriver(Object, v3);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( v9 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
    McTemplateK0qpd_EtwWriteTransfer(
      v10,
      (const EVENT_DESCRIPTOR *)EventNonReadWriteRequestComplete,
      &v15,
      *((_DWORD *)DeviceExtension + 147),
      (char)v3,
      Status);
  if ( Status < 0 )
    goto LABEL_20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 199, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
  }
LABEL_24:
  ObfDereferenceObject(Object);
LABEL_25:
  _InterlockedExchange((volatile __int32 *)(v6 + 1276), 0);
  ClassReleaseRemoveLock(*((PDEVICE_OBJECT *)DeviceExtension + 1), v3);
  if ( Context )
    IoFreeWorkItem(Context);
}

```

## disassembly

```asm
0x140026020  mov     [rsp-8+arg_10], rbx
0x140026025  push    rbp
0x140026026  push    rsi
0x140026027  push    rdi
0x140026028  push    r12
0x14002602a  push    r13
0x14002602c  push    r14
0x14002602e  push    r15
0x140026030  lea     rbp, [rsp-27h]
0x140026035  sub     rsp, 0A0h
0x14002603c  mov     rax, cs:__security_cookie
0x140026043  xor     rax, rsp
0x140026046  mov     [rbp+57h+var_40], rax
0x14002604a  mov     rsi, [rcx+40h]
0x14002604e  xor     eax, eax
0x140026050  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140026054  xorps   xmm0, xmm0
0x140026057  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14002605b  xor     edi, edi
0x14002605d  mov     r13, rdx
0x140026060  xorps   xmm1, xmm1
0x140026063  mov     r15, rcx
0x140026066  movups  xmmword ptr [rbp+57h+Event.Header.___u0], xmm1
0x14002606a  mov     r12, [rsi+478h]
0x140026071  cmp     [r12+2CEh], al
0x140026079  jz      loc_140026277
0x14002607f  mov     al, [rsi+6Ah]
0x140026082  test    al, 0FAh
0x140026084  jnz     loc_140026277
0x14002608a  cmp     al, 4
0x14002608c  jz      loc_140026277
0x140026092  xor     r8d, r8d; State
0x140026095  lea     edx, [rdi+1]; Type
0x140026098  lea     rcx, [rbp+57h+Event]; Event
0x14002609c  call    cs:__imp_KeInitializeEvent
0x1400260a3  nop     dword ptr [rax+rax+00h]
0x1400260a8  mov     rcx, r15; DeviceObject
0x1400260ab  call    cs:__imp_IoGetAttachedDeviceReference
0x1400260b2  nop     dword ptr [rax+rax+00h]
0x1400260b7  mov     [rbp+57h+Object], rax
0x1400260bb  xor     r9d, r9d; InputBufferLength
0x1400260be  mov     rbx, rax
0x1400260c1  xor     r8d, r8d; InputBuffer
0x1400260c4  lea     rax, [rbp+57h+var_60]
0x1400260c8  mov     rdx, rbx; DeviceObject
0x1400260cb  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x1400260d0  mov     ecx, 70140h; IoControlCode
0x1400260d5  lea     rax, [rbp+57h+Event]
0x1400260d9  mov     [rsp+0D0h+var_98], rax; Event
0x1400260de  mov     [rsp+0D0h+InternalDeviceIoControl], dil; InternalDeviceIoControl
0x1400260e3  mov     [rsp+0D0h+OutputBufferLength], edi; OutputBufferLength
0x1400260e7  mov     [rsp+0D0h+OutputBuffer], rdi; OutputBuffer
0x1400260ec  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400260f3  nop     dword ptr [rax+rax+00h]
0x1400260f8  mov     rdi, rax
0x1400260fb  test    rax, rax
0x1400260fe  jz      loc_140026224
0x140026104  xor     r14d, r14d
0x140026107  xorps   xmm0, xmm0
0x14002610a  cmp     cs:ClassPnPETWEnabled, r14b
0x140026111  movups  [rbp+57h+var_50], xmm0
0x140026115  jz      short loc_140026177
0x140026117  lea     rdx, [rbp+57h+var_50]
0x14002611b  mov     rcx, rax
0x14002611e  call    cs:__imp_IoGetActivityIdIrp
0x140026125  nop     dword ptr [rax+rax+00h]
0x14002612a  test    eax, eax
0x14002612c  js      short loc_140026177
0x14002612e  mov     r14d, 1
0x140026134  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, r14b
0x14002613b  jz      short loc_140026177
0x14002613d  mov     rax, [rdi+0B8h]
0x140026144  lea     r8, [rbp+57h+var_50]
0x140026148  mov     r9d, [rsi+24Ch]
0x14002614f  mov     dword ptr [rsp+0D0h+var_98], 70140h
0x140026157  movzx   edx, byte ptr [rax]
0x14002615a  movzx   ecx, byte ptr [rax+1]
0x14002615e  mov     dword ptr [rsp+0D0h+InternalDeviceIoControl], ecx
0x140026162  mov     [rsp+0D0h+OutputBufferLength], edx
0x140026166  lea     rdx, EventIOCTL
0x14002616d  mov     [rsp+0D0h+OutputBuffer], rdi
0x140026172  call    McTemplateK0qpddd_EtwWriteTransfer
0x140026177  mov     rdx, rdi; Irp
0x14002617a  mov     rcx, rbx; DeviceObject
0x14002617d  call    cs:__imp_IofCallDriver
0x140026184  nop     dword ptr [rax+rax+00h]
0x140026189  mov     ebx, eax
0x14002618b  cmp     eax, 103h
0x140026190  jnz     short loc_1400261B6
0x140026192  xor     r9d, r9d; Alertable
0x140026195  mov     [rsp+0D0h+OutputBuffer], 0; Timeout
0x14002619e  xor     r8d, r8d; WaitMode
0x1400261a1  lea     rcx, [rbp+57h+Event]; Object
0x1400261a5  xor     edx, edx; WaitReason
0x1400261a7  call    cs:__imp_KeWaitForSingleObject
0x1400261ae  nop     dword ptr [rax+rax+00h]
0x1400261b3  mov     ebx, dword ptr [rbp+57h+var_60]
0x1400261b6  test    r14d, r14d
0x1400261b9  jz      short loc_1400261E4
0x1400261bb  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 4
0x1400261c2  jz      short loc_1400261E4
0x1400261c4  mov     r9d, [rsi+24Ch]
0x1400261cb  lea     r8, [rbp+57h+var_50]
0x1400261cf  mov     [rsp+0D0h+OutputBufferLength], ebx
0x1400261d3  lea     rdx, EventNonReadWriteRequestComplete
0x1400261da  mov     [rsp+0D0h+OutputBuffer], rdi
0x1400261df  call    McTemplateK0qpd_EtwWriteTransfer
0x1400261e4  test    ebx, ebx
0x1400261e6  js      short loc_140026229
0x1400261e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261ef  lea     rax, WPP_GLOBAL_Control
0x1400261f6  cmp     rcx, rax
0x1400261f9  jz      short loc_140026267
0x1400261fb  test    dword ptr [rcx+2Ch], 100h
0x140026202  jz      short loc_140026267
0x140026204  cmp     byte ptr [rcx+29h], 4
0x140026208  jb      short loc_140026267
0x14002620a  mov     rcx, [rcx+18h]
0x14002620e  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140026215  mov     edx, 0C7h
0x14002621a  mov     r9, r15
0x14002621d  call    WPP_SF_q
0x140026222  jmp     short loc_140026267
0x140026224  mov     ebx, 0C000009Ah
0x140026229  mov     rcx, cs:WPP_GLOBAL_Control
0x140026230  lea     rax, WPP_GLOBAL_Control
0x140026237  cmp     rcx, rax
0x14002623a  jz      short loc_140026267
0x14002623c  test    dword ptr [rcx+2Ch], 100h
0x140026243  jz      short loc_140026267
0x140026245  cmp     byte ptr [rcx+29h], 3
0x140026249  jb      short loc_140026267
0x14002624b  mov     rcx, [rcx+18h]
0x14002624f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140026256  mov     edx, 0C6h
0x14002625b  mov     dword ptr [rsp+0D0h+OutputBuffer], ebx
0x14002625f  mov     r9, r15
0x140026262  call    WPP_SF_qD
0x140026267  mov     rcx, [rbp+57h+Object]; Object
0x14002626b  call    cs:__imp_ObfDereferenceObject
0x140026272  nop     dword ptr [rax+rax+00h]
0x140026277  xor     eax, eax
0x140026279  mov     rdx, rdi; Tag
0x14002627c  xchg    eax, [r12+4FCh]
0x140026284  mov     rcx, [rsi+8]; DeviceObject
0x140026288  call    ClassReleaseRemoveLock
0x14002628d  test    r13, r13
0x140026290  jz      short loc_1400262A1
0x140026292  mov     rcx, r13; IoWorkItem
0x140026295  call    cs:__imp_IoFreeWorkItem
0x14002629c  nop     dword ptr [rax+rax+00h]
0x1400262a1  mov     rcx, [rbp+57h+var_40]
0x1400262a5  xor     rcx, rsp; StackCookie
0x1400262a8  call    __security_check_cookie
0x1400262ad  mov     rbx, [rsp+0D0h+arg_10]
0x1400262b5  add     rsp, 0A0h
0x1400262bc  pop     r15
0x1400262be  pop     r14
0x1400262c0  pop     r13
0x1400262c2  pop     r12
0x1400262c4  pop     rdi
0x1400262c5  pop     rsi
0x1400262c6  pop     rbp
0x1400262c7  retn
```
