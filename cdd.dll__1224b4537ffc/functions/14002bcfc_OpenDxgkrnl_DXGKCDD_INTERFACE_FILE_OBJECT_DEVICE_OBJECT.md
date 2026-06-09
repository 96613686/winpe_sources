# OpenDxgkrnl(_DXGKCDD_INTERFACE *,_FILE_OBJECT * *,_DEVICE_OBJECT * *)

- ea: `0x14002bcfc`
- end: `0x14002bf02`
- name: `?OpenDxgkrnl@@YAJPEAU_DXGKCDD_INTERFACE@@PEAPEAU_FILE_OBJECT@@PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(PVOID InputBuffer, PFILE_OBJECT *FileObject, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14001d980`
- `0x140034838`

## callees

- `0x14002bcfc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002be3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002be3a`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002bd46`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002bd46`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002bdf3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002bdf3`
- `ntoskrnl!IofCallDriver` at `0x14002be0f`
- `ntoskrnl!IofCallDriver` at `0x14002be0f`
- `ntoskrnl!KeInitializeEvent` at `0x14002bdab`
- `ntoskrnl!KeInitializeEvent` at `0x14002bdab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bd2a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bd2a`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002be70`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002be70`
- `watchdog!WdLogSingleEntry1` at `0x14002bd61`
- `watchdog!WdLogSingleEntry1` at `0x14002bea8`
- `watchdog!WdLogSingleEntry1` at `0x14002bd61`
- `watchdog!WdLogSingleEntry1` at `0x14002bea8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002bd78`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002bebf`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002bd78`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002bebf`
- `watchdog!WdLogSingleEntry0` at `0x14002be59`
- `watchdog!WdLogSingleEntry0` at `0x14002be59`

## pseudocode

```c
__int64 __fastcall OpenDxgkrnl(PVOID InputBuffer, PFILE_OBJECT *FileObject, PDEVICE_OBJECT *DeviceObject)
{
  NTSTATUS DeviceObjectPointer; // eax
  NTSTATUS Status; // ebx
  int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  struct _DEVICE_OBJECT *v12; // rdx
  IRP *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct _UNICODE_STRING ObjectName; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-28h] BYREF

  ObjectName = 0;
  RtlInitUnicodeString(&ObjectName, L"\\Device\\DxgKrnl");
  DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 0xC0000000, FileObject, DeviceObject);
  Status = DeviceObjectPointer;
  if ( DeviceObjectPointer < 0 )
  {
    WdLogSingleEntry1(2, DeviceObjectPointer);
    v8 = 6002;
    WdLogGlobalForLineNumber = 6002;
    v11 = (_QWORD *)WdLogNewEntry5_WdError(v10, v9);
LABEL_10:
    v11[3] = gCddImageInfo;
    v11[4] = (unsigned int)dword_14003E570;
    v11[5] = 215857758;
    WdLogGlobalForLineNumber = v8;
    return (unsigned int)Status;
  }
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v12 = *DeviceObject;
  IoStatusBlock = 0;
  v13 = IoBuildDeviceIoControlRequest(
          0x23E05Bu,
          v12,
          InputBuffer,
          0x210u,
          InputBuffer,
          0x210u,
          1u,
          &Event,
          &IoStatusBlock);
  if ( !v13 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 6032;
    v14 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 6032;
    Status = -1073741801;
LABEL_9:
    WdLogSingleEntry1(2, Status);
    v8 = 6038;
    WdLogGlobalForLineNumber = 6038;
    v11 = (_QWORD *)WdLogNewEntry5_WdError(v16, v15);
    goto LABEL_10;
  }
  Status = IofCallDriver(*DeviceObject, v13);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
    goto LABEL_9;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14002bcfc  mov     rax, rsp
0x14002bcff  mov     [rax+8], rbx
0x14002bd03  mov     [rax+10h], rsi
0x14002bd07  push    rdi
0x14002bd08  sub     rsp, 90h
0x14002bd0f  mov     rbx, rdx
0x14002bd12  mov     rdi, rcx
0x14002bd15  xorps   xmm0, xmm0
0x14002bd18  lea     rdx, SourceString; "\\Device\\DxgKrnl"
0x14002bd1f  lea     rcx, [rax-48h]; DestinationString
0x14002bd23  mov     rsi, r8
0x14002bd26  movups  xmmword ptr [rax-48h], xmm0
0x14002bd2a  call    cs:__imp_RtlInitUnicodeString
0x14002bd31  nop     dword ptr [rax+rax+00h]
0x14002bd36  mov     r9, rsi; DeviceObject
0x14002bd39  lea     rcx, [rsp+98h+ObjectName]; ObjectName
0x14002bd3e  mov     r8, rbx; FileObject
0x14002bd41  mov     edx, 0C0000000h; DesiredAccess
0x14002bd46  call    cs:__imp_IoGetDeviceObjectPointer
0x14002bd4d  nop     dword ptr [rax+rax+00h]
0x14002bd52  movsxd  rbx, eax
0x14002bd55  test    eax, eax
0x14002bd57  jns     short loc_14002BD8E
0x14002bd59  mov     rdx, rbx
0x14002bd5c  mov     ecx, 2
0x14002bd61  call    cs:__imp_WdLogSingleEntry1
0x14002bd68  nop     dword ptr [rax+rax+00h]
0x14002bd6d  mov     esi, 1772h
0x14002bd72  mov     cs:WdLogGlobalForLineNumber, esi
0x14002bd78  call    cs:__imp_WdLogNewEntry5_WdError
0x14002bd7f  nop     dword ptr [rax+rax+00h]
0x14002bd84  mov     edi, 0CDDBA5Eh
0x14002bd89  jmp     loc_14002BECB
0x14002bd8e  xor     eax, eax
0x14002bd90  lea     rcx, [rsp+98h+Event]; Event
0x14002bd95  xorps   xmm0, xmm0
0x14002bd98  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x14002bda0  xor     r8d, r8d; State
0x14002bda3  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x14002bda8  lea     edx, [rax+1]; Type
0x14002bdab  call    cs:__imp_KeInitializeEvent
0x14002bdb2  nop     dword ptr [rax+rax+00h]
0x14002bdb7  mov     rdx, [rsi]; DeviceObject
0x14002bdba  lea     rax, [rsp+98h+var_38]
0x14002bdbf  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x14002bdc4  mov     r9d, 210h; InputBufferLength
0x14002bdca  lea     rax, [rsp+98h+Event]
0x14002bdcf  xorps   xmm0, xmm0
0x14002bdd2  mov     [rsp+98h+var_60], rax; Event
0x14002bdd7  mov     r8, rdi; InputBuffer
0x14002bdda  mov     [rsp+98h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14002bddf  mov     ecx, 23E05Bh; IoControlCode
0x14002bde4  mov     [rsp+98h+OutputBufferLength], r9d; OutputBufferLength
0x14002bde9  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x14002bdee  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x14002bdf3  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14002bdfa  nop     dword ptr [rax+rax+00h]
0x14002bdff  mov     edi, 0CDDBA5Eh
0x14002be04  test    rax, rax
0x14002be07  jz      short loc_14002BE54
0x14002be09  mov     rcx, [rsi]; DeviceObject
0x14002be0c  mov     rdx, rax; Irp
0x14002be0f  call    cs:__imp_IofCallDriver
0x14002be16  nop     dword ptr [rax+rax+00h]
0x14002be1b  mov     ebx, eax
0x14002be1d  cmp     eax, 103h
0x14002be22  jnz     short loc_14002BE4A
0x14002be24  xor     r9d, r9d; Alertable
0x14002be27  mov     [rsp+98h+OutputBuffer], 0; Timeout
0x14002be30  xor     r8d, r8d; WaitMode
0x14002be33  lea     rcx, [rsp+98h+Event]; Object
0x14002be38  xor     edx, edx; WaitReason
0x14002be3a  call    cs:__imp_KeWaitForSingleObject
0x14002be41  nop     dword ptr [rax+rax+00h]
0x14002be46  mov     ebx, dword ptr [rsp+98h+var_38]
0x14002be4a  test    ebx, ebx
0x14002be4c  jns     loc_14002BEEA
0x14002be52  jmp     short loc_14002BEA0
0x14002be54  mov     ecx, 6
0x14002be59  call    cs:__imp_WdLogSingleEntry0
0x14002be60  nop     dword ptr [rax+rax+00h]
0x14002be65  mov     ebx, 1790h
0x14002be6a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002be70  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002be77  nop     dword ptr [rax+rax+00h]
0x14002be7c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002be83  mov     [rax+18h], rcx
0x14002be87  mov     ecx, cs:dword_14003E570
0x14002be8d  mov     [rax+20h], rcx
0x14002be91  mov     [rax+28h], rdi
0x14002be95  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002be9b  mov     ebx, 0C0000017h
0x14002bea0  movsxd  rdx, ebx
0x14002bea3  mov     ecx, 2
0x14002bea8  call    cs:__imp_WdLogSingleEntry1
0x14002beaf  nop     dword ptr [rax+rax+00h]
0x14002beb4  mov     esi, 1796h
0x14002beb9  mov     cs:WdLogGlobalForLineNumber, esi
0x14002bebf  call    cs:__imp_WdLogNewEntry5_WdError
0x14002bec6  nop     dword ptr [rax+rax+00h]
0x14002becb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002bed2  mov     [rax+18h], rcx
0x14002bed6  mov     ecx, cs:dword_14003E570
0x14002bedc  mov     [rax+20h], rcx
0x14002bee0  mov     [rax+28h], rdi
0x14002bee4  mov     cs:WdLogGlobalForLineNumber, esi
0x14002beea  lea     r11, [rsp+98h+var_8]
0x14002bef2  mov     eax, ebx
0x14002bef4  mov     rbx, [r11+10h]
0x14002bef8  mov     rsi, [r11+18h]
0x14002befc  mov     rsp, r11
0x14002beff  pop     rdi
0x14002bf00  retn
```
