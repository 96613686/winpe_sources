# KsVerifierInitialize

- ea: `0x1800126e4`
- end: `0x1800129d1`
- name: `KsVerifierInitialize`
- size: `749`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18007b090`

## callees

- `0x1800126e4`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180012838`
- `ntoskrnl!ObfDereferenceObject` at `0x180012889`
- `ntoskrnl!ObfDereferenceObject` at `0x1800128a5`
- `ntoskrnl!ObfDereferenceObject` at `0x180012838`
- `ntoskrnl!ObfDereferenceObject` at `0x180012889`
- `ntoskrnl!ObfDereferenceObject` at `0x1800128a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012946`
- `ntoskrnl!RtlInitUnicodeString` at `0x180012946`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180012823`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180012823`
- `ntoskrnl!IofCallDriver` at `0x18001284d`
- `ntoskrnl!IofCallDriver` at `0x18001284d`
- `ntoskrnl!MmLockPagableDataSection` at `0x180012985`
- `ntoskrnl!MmLockPagableDataSection` at `0x180012985`
- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x18001274d`
- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x18001274d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1800127c3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1800127c3`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001272d`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001272d`
- `ntoskrnl!KeWaitForSingleObject` at `0x180012875`
- `ntoskrnl!KeWaitForSingleObject` at `0x180012875`
- `ntoskrnl!KeInitializeEvent` at `0x1800127dc`
- `ntoskrnl!KeInitializeEvent` at `0x1800127dc`

## pseudocode

```c
char KsVerifierInitialize()
{
  char v0; // bl
  IRP *v2; // rax
  NTSTATUS Status; // eax
  PFILE_OBJECT v4; // rcx
  int v5; // ecx
  int OutputBuffer; // [rsp+20h] [rbp-39h]
  UNICODE_STRING ObjectName; // [rsp+50h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+7h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _KEVENT Event; // [rsp+80h] [rbp+27h] BYREF
  unsigned int v11; // [rsp+C0h] [rbp+67h] BYREF
  PFILE_OBJECT FileObject; // [rsp+C8h] [rbp+6Fh] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+D0h] [rbp+77h] BYREF
  __int64 *InputBuffer; // [rsp+D8h] [rbp+7Fh] BYREF

  DestinationString = 0;
  v11 = 2;
  if ( KsVerifierInitialized )
    return 1;
  WPP_MAIN_CB.Queue.ListEntry.Blink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.Queue.ListEntry.Flink = &WPP_MAIN_CB.Queue.ListEntry;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  if ( (int)DifRegisterClassDriverPlugin(16, &KsVerifierDdiTable, 1200) < 0 )
    goto LABEL_4;
  DeviceObject = 0;
  FileObject = 0;
  InputBuffer = &KsVerifierUtilTable;
  *(_QWORD *)&ObjectName.Length = 2621478;
  ObjectName.Buffer = L"\\Device\\VerifierExt";
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  if ( IoGetDeviceObjectPointer(&ObjectName, 0, &FileObject, &DeviceObject) < 0 )
    return 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v2 = IoBuildDeviceIoControlRequest(0x10002004u, DeviceObject, &InputBuffer, 8u, 0, 0, 0, &Event, &IoStatusBlock);
  if ( !v2 )
  {
    ObfDereferenceObject(FileObject);
    goto LABEL_17;
  }
  Status = IofCallDriver(DeviceObject, v2);
  if ( Status == 259 )
  {
    if ( KeWaitForSingleObject(&Event, Executive, 0, 0, 0) < 0 )
    {
      v4 = FileObject;
LABEL_13:
      ObfDereferenceObject(v4);
      return 0;
    }
    Status = IoStatusBlock.Status;
  }
  v4 = FileObject;
  if ( Status < 0 )
    goto LABEL_13;
  ObfDereferenceObject(FileObject);
  if ( !*InputBuffer )
    return 0;
LABEL_17:
  (*(void (__fastcall **)(UNICODE_STRING *, unsigned int *))(KsVerifierUtilTable + 168))(&DestinationString, &v11);
  v5 = v11;
  v0 = 1;
  if ( v11 > 1 )
  {
    if ( v11 > 0xFFFF )
      v5 = 0xFFFF;
    XDV_KS_KSSTATE_TIMELIMIT *= v5;
    XDV_KS_DEVICE_CALLBACKS_TIMELIMIT *= v5;
    XDV_KS_FILTER_CALLBACK_TIMELIMIT *= v5;
    XDV_KS_PIN_CALLBACK_TIMELIMIT *= v5;
    XDV_KS_PROCESSING_MUTEX_TIMELIMIT *= v5;
  }
  RtlInitUnicodeString(&DestinationString, L"XdvTimedFactor");
  KsVerifierInitialized = 1;
  KsXdvExtLevel = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 152))(3);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    KsXdvPageSectionHandle = MmLockPagableDataSection(KsXdvTimedCallback);
    if ( KsXdvPageSectionHandle )
    {
      LOBYTE(OutputBuffer) = 2;
      (*(void (__fastcall **)(__int64, __int64, __int64 (__fastcall *)(), __int64 (__fastcall *)(), int))(KsVerifierUtilTable + 104))(
        3,
        10,
        KsXdvTimedCallback,
        KsXdvRuleId2TimedLimit,
        OutputBuffer);
      return v0;
    }
LABEL_4:
    KsXdvExtLevel = 0;
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800126e4  push    rbp
0x1800126e6  push    rbx
0x1800126e7  lea     rbp, [rsp-4Fh]
0x1800126ec  sub     rsp, 0A8h
0x1800126f3  cmp     cs:KsVerifierInitialized, 0
0x1800126fa  xorps   xmm0, xmm0
0x1800126fd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180012701  mov     [rbp+57h+arg_0], 2
0x180012708  jz      short loc_180012711
0x18001270a  mov     ebx, 1
0x18001270f  jmp     short loc_180012769
0x180012711  lea     rax, WPP_MAIN_CB.Queue
0x180012718  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x18001271f  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x180012726  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x18001272d  call    cs:__imp_KeInitializeSpinLock
0x180012734  nop     dword ptr [rax+rax+00h]
0x180012739  xor     r9d, r9d
0x18001273c  lea     rdx, KsVerifierDdiTable
0x180012743  mov     r8d, 4B0h
0x180012749  lea     ecx, [r9+10h]
0x18001274d  call    cs:__imp_DifRegisterClassDriverPlugin
0x180012754  nop     dword ptr [rax+rax+00h]
0x180012759  test    eax, eax
0x18001275b  jns     short loc_180012776
0x18001275d  mov     cs:KsXdvExtLevel, 0
0x180012767  xor     bl, bl
0x180012769  mov     al, bl
0x18001276b  add     rsp, 0A8h
0x180012772  pop     rbx
0x180012773  pop     rbp
0x180012774  retn
0x180012776  xorps   xmm0, xmm0
0x180012779  mov     [rbp+57h+DeviceObject], 0
0x180012781  lea     rax, KsVerifierUtilTable
0x180012788  mov     [rbp+57h+FileObject], 0
0x180012790  mov     [rbp+57h+InputBuffer], rax
0x180012794  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x180012798  xor     eax, eax
0x18001279a  mov     qword ptr [rbp+57h+ObjectName.Length], 280026h
0x1800127a2  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1800127a6  lea     r8, [rbp+57h+FileObject]; FileObject
0x1800127aa  lea     rax, aDeviceVerifier; "\\Device\\VerifierExt"
0x1800127b1  xor     edx, edx; DesiredAccess
0x1800127b3  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x1800127b7  mov     [rbp+57h+ObjectName.Buffer], rax
0x1800127bb  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x1800127bf  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800127c3  call    cs:__imp_IoGetDeviceObjectPointer
0x1800127ca  nop     dword ptr [rax+rax+00h]
0x1800127cf  test    eax, eax
0x1800127d1  js      short loc_180012767
0x1800127d3  xor     r8d, r8d; State
0x1800127d6  lea     rcx, [rbp+57h+Event]; Event
0x1800127da  xor     edx, edx; Type
0x1800127dc  call    cs:__imp_KeInitializeEvent
0x1800127e3  nop     dword ptr [rax+rax+00h]
0x1800127e8  mov     rdx, [rbp+57h+DeviceObject]; DeviceObject
0x1800127ec  lea     rax, [rbp+57h+var_50]
0x1800127f0  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x1800127f5  lea     r8, [rbp+57h+InputBuffer]; InputBuffer
0x1800127f9  lea     rax, [rbp+57h+Event]
0x1800127fd  mov     r9d, 8; InputBufferLength
0x180012803  mov     [rsp+0B0h+var_78], rax; Event
0x180012808  mov     ecx, 10002004h; IoControlCode
0x18001280d  mov     [rsp+0B0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x180012812  mov     [rsp+0B0h+OutputBufferLength], 0; OutputBufferLength
0x18001281a  mov     [rsp+0B0h+OutputBuffer], 0; OutputBuffer
0x180012823  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18001282a  nop     dword ptr [rax+rax+00h]
0x18001282f  test    rax, rax
0x180012832  jnz     short loc_180012846
0x180012834  mov     rcx, [rbp+57h+FileObject]; Object
0x180012838  call    cs:__imp_ObfDereferenceObject
0x18001283f  nop     dword ptr [rax+rax+00h]
0x180012844  jmp     short loc_1800128BF
0x180012846  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18001284a  mov     rdx, rax; Irp
0x18001284d  call    cs:__imp_IofCallDriver
0x180012854  nop     dword ptr [rax+rax+00h]
0x180012859  cmp     eax, 103h
0x18001285e  jnz     short loc_18001289D
0x180012860  xor     r9d, r9d; Alertable
0x180012863  mov     [rsp+0B0h+OutputBuffer], 0; Timeout
0x18001286c  xor     r8d, r8d; WaitMode
0x18001286f  lea     rcx, [rbp+57h+Event]; Object
0x180012873  xor     edx, edx; WaitReason
0x180012875  call    cs:__imp_KeWaitForSingleObject
0x18001287c  nop     dword ptr [rax+rax+00h]
0x180012881  test    eax, eax
0x180012883  jns     short loc_18001289A
0x180012885  mov     rcx, [rbp+57h+FileObject]; Object
0x180012889  call    cs:__imp_ObfDereferenceObject
0x180012890  nop     dword ptr [rax+rax+00h]
0x180012895  jmp     loc_180012767
0x18001289a  mov     eax, dword ptr [rbp+57h+var_50]
0x18001289d  mov     rcx, [rbp+57h+FileObject]; Object
0x1800128a1  test    eax, eax
0x1800128a3  js      short loc_180012889
0x1800128a5  call    cs:__imp_ObfDereferenceObject
0x1800128ac  nop     dword ptr [rax+rax+00h]
0x1800128b1  mov     rax, [rbp+57h+InputBuffer]
0x1800128b5  cmp     qword ptr [rax], 0
0x1800128b9  jz      loc_180012767
0x1800128bf  mov     rax, cs:KsVerifierUtilTable
0x1800128c6  lea     rdx, [rbp+57h+arg_0]
0x1800128ca  lea     rcx, [rbp+57h+DestinationString]
0x1800128ce  mov     rax, [rax+0A8h]
0x1800128d5  call    _guard_dispatch_icall
0x1800128da  mov     ecx, [rbp+57h+arg_0]
0x1800128dd  mov     ebx, 1
0x1800128e2  cmp     ecx, ebx
0x1800128e4  jbe     short loc_18001293B
0x1800128e6  mov     eax, 0FFFFh
0x1800128eb  cmp     ecx, eax
0x1800128ed  cmova   ecx, eax
0x1800128f0  mov     eax, cs:XDV_KS_KSSTATE_TIMELIMIT
0x1800128f6  imul    eax, ecx
0x1800128f9  mov     cs:XDV_KS_KSSTATE_TIMELIMIT, eax
0x1800128ff  mov     eax, cs:XDV_KS_DEVICE_CALLBACKS_TIMELIMIT
0x180012905  imul    eax, ecx
0x180012908  mov     cs:XDV_KS_DEVICE_CALLBACKS_TIMELIMIT, eax
0x18001290e  mov     eax, cs:XDV_KS_FILTER_CALLBACK_TIMELIMIT
0x180012914  imul    eax, ecx
0x180012917  mov     cs:XDV_KS_FILTER_CALLBACK_TIMELIMIT, eax
0x18001291d  mov     eax, cs:XDV_KS_PIN_CALLBACK_TIMELIMIT
0x180012923  imul    eax, ecx
0x180012926  mov     cs:XDV_KS_PIN_CALLBACK_TIMELIMIT, eax
0x18001292c  mov     eax, cs:XDV_KS_PROCESSING_MUTEX_TIMELIMIT
0x180012932  imul    eax, ecx
0x180012935  mov     cs:XDV_KS_PROCESSING_MUTEX_TIMELIMIT, eax
0x18001293b  lea     rdx, aXdvtimedfactor; "XdvTimedFactor"
0x180012942  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180012946  call    cs:__imp_RtlInitUnicodeString
0x18001294d  nop     dword ptr [rax+rax+00h]
0x180012952  mov     rax, cs:KsVerifierUtilTable
0x180012959  mov     ecx, 3
0x18001295e  mov     cs:KsVerifierInitialized, bl
0x180012964  mov     rax, [rax+98h]
0x18001296b  call    _guard_dispatch_icall
0x180012970  mov     cs:KsXdvExtLevel, eax
0x180012976  test    al, 18h
0x180012978  jz      loc_180012769
0x18001297e  lea     rcx, KsXdvTimedCallback; AddressWithinSection
0x180012985  call    cs:__imp_MmLockPagableDataSection
0x18001298c  nop     dword ptr [rax+rax+00h]
0x180012991  mov     cs:KsXdvPageSectionHandle, rax
0x180012998  test    rax, rax
0x18001299b  jz      loc_18001275D
0x1800129a1  mov     rax, cs:KsVerifierUtilTable
0x1800129a8  lea     r9, KsXdvRuleId2TimedLimit
0x1800129af  mov     edx, 0Ah
0x1800129b4  mov     byte ptr [rsp+0B0h+OutputBuffer], 2
0x1800129b9  lea     r8, KsXdvTimedCallback
0x1800129c0  mov     rax, [rax+68h]
0x1800129c4  lea     ecx, [rdx-7]
0x1800129c7  call    _guard_dispatch_icall
0x1800129cc  jmp     loc_180012769
```
