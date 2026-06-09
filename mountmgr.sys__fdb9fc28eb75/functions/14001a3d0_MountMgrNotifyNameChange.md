# MountMgrNotifyNameChange

- ea: `0x14001a3d0`
- end: `0x14001a77c`
- name: `MountMgrNotifyNameChange`
- size: `940`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000be4c`
- `0x14000db54`
- `0x140013a20`
- `0x140018560`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002d70`
- `0x14001a3d0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a46a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a46a`
- `ntoskrnl!PsIsHostSilo` at `0x14001a434`
- `ntoskrnl!PsIsHostSilo` at `0x14001a434`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14001a73b`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14001a73b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a568`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a578`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a624`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a634`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a6a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a6b1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a74b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a568`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a578`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a624`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a634`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a6a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a6b1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a74b`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001a550`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001a550`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001a4ad`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001a4ad`
- `ntoskrnl!IofCallDriver` at `0x14001a5e4`
- `ntoskrnl!IofCallDriver` at `0x14001a5e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a6ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a704`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a6ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a704`
- `ntoskrnl!KeInitializeEvent` at `0x14001a517`
- `ntoskrnl!KeInitializeEvent` at `0x14001a517`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a611`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a611`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001a4fe`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001a4fe`

## pseudocode

```c
void __fastcall MountMgrNotifyNameChange(__int64 a1, struct _UNICODE_STRING *a2, char a3)
{
  __int64 v4; // rcx
  const UNICODE_STRING *v7; // rbx
  __int64 *v8; // rdi
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v10; // r8
  PIRP v11; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  NTSTATUS Status; // edi
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-29h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-9h] BYREF
  _OWORD NotificationStructure[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+A8h] [rbp+2Fh]

  v22 = 0;
  v4 = *(_QWORD *)(a1 + 368);
  FileObject = 0;
  DeviceObject = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  memset(NotificationStructure, 0, sizeof(NotificationStructure));
  if ( (unsigned __int8)PsIsHostSilo(v4) )
  {
    if ( !a3 )
      goto LABEL_9;
    v7 = *(const UNICODE_STRING **)(a1 + 16);
    v8 = (__int64 *)(a1 + 16);
    if ( v7 != (const UNICODE_STRING *)v8 )
    {
      while ( RtlCompareUnicodeString(a2, v7 + 5, 1u) )
      {
        v7 = *(const UNICODE_STRING **)&v7->Length;
        if ( v7 == (const UNICODE_STRING *)v8 )
          return;
      }
      if ( v7 && !HIBYTE(v7[8].Length) )
      {
LABEL_9:
        DeviceObjectPointer = IoGetDeviceObjectPointer(a2, 0x80u, &FileObject, &DeviceObject);
        if ( DeviceObjectPointer < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 104, v10, (unsigned int)DeviceObjectPointer);
          }
          return;
        }
        DeviceObject = IoGetAttachedDeviceReference(FileObject->DeviceObject);
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v11 = IoBuildDeviceIoControlRequest(0, DeviceObject, 0, 0, 0, 0, 0, &Event, &IoStatusBlock);
        if ( !v11 )
        {
          ObfDereferenceObject(DeviceObject);
          ObfDereferenceObject(FileObject);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105);
          }
          return;
        }
        CurrentStackLocation = v11->Tail.Overlay.CurrentStackLocation;
        v11->IoStatus.Status = -1073741637;
        v11->IoStatus.Information = 0;
        *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 1819;
        CurrentStackLocation[-1].Parameters.Read.Length = 4;
        CurrentStackLocation[-1].FileObject = FileObject;
        Status = IofCallDriver(DeviceObject, v11);
        if ( Status == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          Status = IoStatusBlock.Status;
        }
        else if ( Status < 0
               && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 106, v14, (unsigned int)Status);
          ObfDereferenceObject(DeviceObject);
          ObfDereferenceObject(FileObject);
          goto LABEL_20;
        }
        ObfDereferenceObject(DeviceObject);
        ObfDereferenceObject(FileObject);
        if ( Status < 0 )
        {
LABEL_20:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 107, v15, (unsigned int)Status);
          }
          return;
        }
        if ( *(_DWORD *)IoStatusBlock.Information )
        {
          DeviceObject = *(PDEVICE_OBJECT *)(IoStatusBlock.Information + 8);
          ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
          LODWORD(NotificationStructure[0]) = 2359297;
          *((_QWORD *)&NotificationStructure[1] + 1) = 0;
          *(GUID *)((char *)NotificationStructure + 4) = GUID_IO_VOLUME_NAME_CHANGE;
          LODWORD(v22) = -1;
          IoReportTargetDeviceChangeAsynchronous(DeviceObject, NotificationStructure, 0, 0);
          ObfDereferenceObject(DeviceObject);
        }
        else
        {
          ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 108, v16, (unsigned int)Status);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14001a3d0  mov     [rsp-8+arg_10], rbx
0x14001a3d5  mov     [rsp-8+arg_18], rsi
0x14001a3da  push    rbp
0x14001a3db  push    rdi
0x14001a3dc  push    r14
0x14001a3de  lea     rbp, [rsp-47h]
0x14001a3e3  sub     rsp, 0C0h
0x14001a3ea  mov     rax, cs:__security_cookie
0x14001a3f1  xor     rax, rsp
0x14001a3f4  mov     [rbp+57h+var_20], rax
0x14001a3f8  xorps   xmm0, xmm0
0x14001a3fb  xor     eax, eax
0x14001a3fd  xorps   xmm1, xmm1
0x14001a400  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001a404  mov     rdi, rcx
0x14001a407  mov     [rbp+57h+var_28], rax
0x14001a40b  mov     rcx, [rcx+170h]
0x14001a412  xor     r14d, r14d
0x14001a415  mov     [rbp+57h+FileObject], r14
0x14001a419  movzx   ebx, r8b
0x14001a41d  mov     [rbp+57h+DeviceObject], r14
0x14001a421  mov     rsi, rdx
0x14001a424  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14001a428  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x14001a42c  movups  [rbp+57h+NotificationStructure], xmm1
0x14001a430  movups  [rbp+57h+var_38], xmm1
0x14001a434  call    cs:__imp_PsIsHostSilo
0x14001a43b  nop     dword ptr [rax+rax+00h]
0x14001a440  test    al, al
0x14001a442  jz      loc_14001A757
0x14001a448  test    bl, bl
0x14001a44a  jz      short loc_14001A49D
0x14001a44c  mov     rbx, [rdi+10h]
0x14001a450  add     rdi, 10h
0x14001a454  cmp     rbx, rdi
0x14001a457  jz      loc_14001A757
0x14001a45d  nop     dword ptr [rax]
0x14001a460  lea     rdx, [rbx+50h]; String2
0x14001a464  mov     r8b, 1; CaseInSensitive
0x14001a467  mov     rcx, rsi; String1
0x14001a46a  call    cs:__imp_RtlCompareUnicodeString
0x14001a471  nop     dword ptr [rax+rax+00h]
0x14001a476  test    eax, eax
0x14001a478  jz      short loc_14001A487
0x14001a47a  mov     rbx, [rbx]
0x14001a47d  cmp     rbx, rdi
0x14001a480  jnz     short loc_14001A460
0x14001a482  jmp     loc_14001A757
0x14001a487  test    rbx, rbx
0x14001a48a  jz      loc_14001A757
0x14001a490  cmp     [rbx+81h], r14b
0x14001a497  jnz     loc_14001A757
0x14001a49d  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x14001a4a1  mov     edx, 80h; DesiredAccess
0x14001a4a6  lea     r8, [rbp+57h+FileObject]; FileObject
0x14001a4aa  mov     rcx, rsi; ObjectName
0x14001a4ad  call    cs:__imp_IoGetDeviceObjectPointer
0x14001a4b4  nop     dword ptr [rax+rax+00h]
0x14001a4b9  test    eax, eax
0x14001a4bb  jns     short loc_14001A4F6
0x14001a4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4c4  lea     rbx, WPP_GLOBAL_Control
0x14001a4cb  cmp     rcx, rbx
0x14001a4ce  jz      loc_14001A757
0x14001a4d4  mov     edx, [rcx+2Ch]
0x14001a4d7  test    dl, 1
0x14001a4da  jz      loc_14001A757
0x14001a4e0  mov     rcx, [rcx+18h]
0x14001a4e4  mov     edx, 68h ; 'h'
0x14001a4e9  mov     r9d, eax
0x14001a4ec  call    WPP_SF_L
0x14001a4f1  jmp     loc_14001A757
0x14001a4f6  mov     rcx, [rbp+57h+FileObject]
0x14001a4fa  mov     rcx, [rcx+8]; DeviceObject
0x14001a4fe  call    cs:__imp_IoGetAttachedDeviceReference
0x14001a505  nop     dword ptr [rax+rax+00h]
0x14001a50a  xor     r8d, r8d; State
0x14001a50d  lea     rcx, [rbp+57h+Event]; Event
0x14001a511  xor     edx, edx; Type
0x14001a513  mov     [rbp+57h+DeviceObject], rax
0x14001a517  call    cs:__imp_KeInitializeEvent
0x14001a51e  nop     dword ptr [rax+rax+00h]
0x14001a523  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x14001a527  lea     rax, [rbp+57h+var_70]
0x14001a52b  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x14001a530  xor     r9d, r9d; InputBufferLength
0x14001a533  lea     rax, [rbp+57h+Event]
0x14001a537  xor     r8d, r8d; InputBuffer
0x14001a53a  mov     [rsp+0D0h+var_98], rax; Event
0x14001a53f  xor     ecx, ecx; IoControlCode
0x14001a541  mov     [rsp+0D0h+InternalDeviceIoControl], r14b; InternalDeviceIoControl
0x14001a546  mov     [rsp+0D0h+OutputBufferLength], r14d; OutputBufferLength
0x14001a54b  mov     [rsp+0D0h+OutputBuffer], r14; OutputBuffer
0x14001a550  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14001a557  nop     dword ptr [rax+rax+00h]
0x14001a55c  mov     rdx, rax; Irp
0x14001a55f  test    rax, rax
0x14001a562  jnz     short loc_14001A5B9
0x14001a564  mov     rcx, [rbp+57h+DeviceObject]; Object
0x14001a568  call    cs:__imp_ObfDereferenceObject
0x14001a56f  nop     dword ptr [rax+rax+00h]
0x14001a574  mov     rcx, [rbp+57h+FileObject]; Object
0x14001a578  call    cs:__imp_ObfDereferenceObject
0x14001a57f  nop     dword ptr [rax+rax+00h]
0x14001a584  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a58b  lea     rbx, WPP_GLOBAL_Control
0x14001a592  cmp     rcx, rbx
0x14001a595  jz      loc_14001A757
0x14001a59b  mov     eax, [rcx+2Ch]
0x14001a59e  test    al, 4
0x14001a5a0  jz      loc_14001A757
0x14001a5a6  mov     rcx, [rcx+18h]
0x14001a5aa  mov     edx, 69h ; 'i'
0x14001a5af  call    WPP_SF_
0x14001a5b4  jmp     loc_14001A757
0x14001a5b9  mov     rcx, [rax+0B8h]
0x14001a5c0  mov     dword ptr [rax+30h], 0C00000BBh
0x14001a5c7  mov     [rax+38h], r14
0x14001a5cb  mov     word ptr [rcx-48h], 71Bh
0x14001a5d1  mov     dword ptr [rcx-40h], 4
0x14001a5d8  mov     rax, [rbp+57h+FileObject]
0x14001a5dc  mov     [rcx-18h], rax
0x14001a5e0  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14001a5e4  call    cs:__imp_IofCallDriver
0x14001a5eb  nop     dword ptr [rax+rax+00h]
0x14001a5f0  lea     rbx, WPP_GLOBAL_Control
0x14001a5f7  mov     edi, eax
0x14001a5f9  cmp     eax, 103h
0x14001a5fe  jnz     short loc_14001A675
0x14001a600  xor     r9d, r9d; Alertable
0x14001a603  mov     [rsp+0D0h+OutputBuffer], r14; Timeout
0x14001a608  xor     r8d, r8d; WaitMode
0x14001a60b  lea     rcx, [rbp+57h+Event]; Object
0x14001a60f  xor     edx, edx; WaitReason
0x14001a611  call    cs:__imp_KeWaitForSingleObject
0x14001a618  nop     dword ptr [rax+rax+00h]
0x14001a61d  mov     edi, dword ptr [rbp+57h+var_70]
0x14001a620  mov     rcx, [rbp+57h+DeviceObject]; Object
0x14001a624  call    cs:__imp_ObfDereferenceObject
0x14001a62b  nop     dword ptr [rax+rax+00h]
0x14001a630  mov     rcx, [rbp+57h+FileObject]; Object
0x14001a634  call    cs:__imp_ObfDereferenceObject
0x14001a63b  nop     dword ptr [rax+rax+00h]
0x14001a640  test    edi, edi
0x14001a642  jns     short loc_14001A6BF
0x14001a644  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a64b  cmp     rcx, rbx
0x14001a64e  jz      loc_14001A757
0x14001a654  mov     eax, [rcx+2Ch]
0x14001a657  test    al, 1
0x14001a659  jz      loc_14001A757
0x14001a65f  mov     rcx, [rcx+18h]
0x14001a663  mov     edx, 6Bh ; 'k'
0x14001a668  mov     r9d, edi
0x14001a66b  call    WPP_SF_L
0x14001a670  jmp     loc_14001A757
0x14001a675  test    edi, edi
0x14001a677  jns     short loc_14001A620
0x14001a679  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a680  cmp     rcx, rbx
0x14001a683  jz      short loc_14001A620
0x14001a685  mov     eax, [rcx+2Ch]
0x14001a688  test    al, 1
0x14001a68a  jz      short loc_14001A620
0x14001a68c  mov     rcx, [rcx+18h]
0x14001a690  mov     edx, 6Ah ; 'j'
0x14001a695  mov     r9d, edi
0x14001a698  call    WPP_SF_L
0x14001a69d  mov     rcx, [rbp+57h+DeviceObject]; Object
0x14001a6a1  call    cs:__imp_ObfDereferenceObject
0x14001a6a8  nop     dword ptr [rax+rax+00h]
0x14001a6ad  mov     rcx, [rbp+57h+FileObject]; Object
0x14001a6b1  call    cs:__imp_ObfDereferenceObject
0x14001a6b8  nop     dword ptr [rax+rax+00h]
0x14001a6bd  jmp     short loc_14001A644
0x14001a6bf  mov     rcx, [rbp+57h+var_70.Information]; P
0x14001a6c3  xor     edx, edx; Tag
0x14001a6c5  cmp     dword ptr [rcx], 1
0x14001a6c8  jnb     short loc_14001A6FC
0x14001a6ca  call    cs:__imp_ExFreePoolWithTag
0x14001a6d1  nop     dword ptr [rax+rax+00h]
0x14001a6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6dd  cmp     rcx, rbx
0x14001a6e0  jz      short loc_14001A757
0x14001a6e2  mov     eax, [rcx+2Ch]
0x14001a6e5  test    al, 1
0x14001a6e7  jz      short loc_14001A757
0x14001a6e9  mov     rcx, [rcx+18h]
0x14001a6ed  mov     edx, 6Ch ; 'l'
0x14001a6f2  mov     r9d, edi
0x14001a6f5  call    WPP_SF_L
0x14001a6fa  jmp     short loc_14001A757
0x14001a6fc  mov     rax, [rcx+8]
0x14001a700  mov     [rbp+57h+DeviceObject], rax
0x14001a704  call    cs:__imp_ExFreePoolWithTag
0x14001a70b  nop     dword ptr [rax+rax+00h]
0x14001a710  movups  xmm0, xmmword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x14001a717  mov     rcx, [rbp+57h+DeviceObject]; PhysicalDeviceObject
0x14001a71b  lea     rdx, [rbp+57h+NotificationStructure]; NotificationStructure
0x14001a71f  xor     r9d, r9d; Context
0x14001a722  mov     dword ptr [rbp+57h+NotificationStructure], 240001h
0x14001a729  xor     r8d, r8d; Callback
0x14001a72c  mov     qword ptr [rbp+57h+var_38+8], r14
0x14001a730  movups  [rbp+57h+NotificationStructure+4], xmm0
0x14001a734  mov     dword ptr [rbp+57h+var_28], 0FFFFFFFFh
0x14001a73b  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x14001a742  nop     dword ptr [rax+rax+00h]
0x14001a747  mov     rcx, [rbp+57h+DeviceObject]; Object
0x14001a74b  call    cs:__imp_ObfDereferenceObject
0x14001a752  nop     dword ptr [rax+rax+00h]
0x14001a757  mov     rcx, [rbp+57h+var_20]
0x14001a75b  xor     rcx, rsp; StackCookie
0x14001a75e  call    __security_check_cookie
0x14001a763  lea     r11, [rsp+0D0h+var_10]
0x14001a76b  mov     rbx, [r11+30h]
0x14001a76f  mov     rsi, [r11+38h]
0x14001a773  mov     rsp, r11
0x14001a776  pop     r14
0x14001a778  pop     rdi
0x14001a779  pop     rbp
0x14001a77a  retn
```
