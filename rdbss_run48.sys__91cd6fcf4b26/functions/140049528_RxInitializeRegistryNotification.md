# RxInitializeRegistryNotification

- ea: `0x140049528`
- end: `0x14004966f`
- name: `RxInitializeRegistryNotification`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14008321c`

## callees

- `0x140026080`
- `0x140049528`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004957f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004957f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140049568`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140049568`
- `ntoskrnl!ZwOpenKey` at `0x1400495c1`
- `ntoskrnl!ZwOpenKey` at `0x1400495c1`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14004964f`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14004964f`

## string_xrefs

- `0x140049574`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
__int64 RxInitializeRegistryNotification()
{
  NTSTATUS v0; // ebx
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x48u);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)&WPP_MAIN_CB.DeviceQueue);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey((PHANDLE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0x10u, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    WPP_MAIN_CB.Queue.Wcb.DeviceObject = RxNotificationChangeHandler;
    ++LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    WPP_MAIN_CB.Queue.Wcb.CurrentIrp = 0;
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
    ZwNotifyChangeKey(
      *(HANDLE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
      0,
      (PIO_APC_ROUTINE)&WPP_MAIN_CB.Queue.Wcb.DeviceContext,
      (PVOID)1,
      (PIO_STATUS_BLOCK)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      4u,
      0,
      0,
      0,
      1u);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140049528  mov     [rsp-8+arg_0], rbx
0x14004952d  push    rbp
0x14004952e  lea     rbp, [rsp-57h]
0x140049533  sub     rsp, 90h
0x14004953a  xorps   xmm0, xmm0
0x14004953d  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x140049544  xor     eax, eax
0x140049546  xor     edx, edx; Val
0x140049548  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004954c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140049550  lea     r8d, [rax+48h]; Size
0x140049554  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140049558  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004955c  call    memset
0x140049561  lea     rcx, WPP_MAIN_CB.DeviceQueue; RunRef
0x140049568  call    cs:__imp_ExInitializeRundownProtection
0x14004956f  nop     dword ptr [rax+rax+00h]
0x140049574  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004957b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004957f  call    cs:__imp_RtlInitUnicodeString
0x140049586  nop     dword ptr [rax+rax+00h]
0x14004958b  lea     rax, [rbp+57h+DestinationString]
0x14004958f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140049596  xorps   xmm0, xmm0
0x140049599  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004959d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400495a1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400495a9  mov     edx, 10h; DesiredAccess
0x1400495ae  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400495b5  lea     rcx, WPP_MAIN_CB.Queue+10h; KeyHandle
0x1400495bc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400495c1  call    cs:__imp_ZwOpenKey
0x1400495c8  nop     dword ptr [rax+rax+00h]
0x1400495cd  mov     ebx, eax
0x1400495cf  test    eax, eax
0x1400495d1  js      loc_14004965B
0x1400495d7  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400495dd  lea     rax, RxNotificationChangeHandler
0x1400495e4  mov     r9d, 1; ApcContext
0x1400495ea  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x1400495f1  mov     [rsp+90h+Asynchronous], r9b; Asynchronous
0x1400495f6  lea     rax, WPP_MAIN_CB.Queue+40h
0x1400495fd  mov     [rsp+90h+BufferSize], 0; BufferSize
0x140049605  lea     r8, WPP_MAIN_CB.Queue+20h; ApcRoutine
0x14004960c  add     ecx, r9d
0x14004960f  mov     [rsp+90h+Buffer], 0; Buffer
0x140049618  mov     [rsp+90h+WatchTree], 0; WatchTree
0x14004961d  xor     edx, edx; Event
0x14004961f  mov     dword ptr cs:WPP_MAIN_CB.Queue+18h, ecx
0x140049625  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; KeyHandle
0x14004962c  mov     [rsp+90h+CompletionFilter], 4; CompletionFilter
0x140049634  mov     [rsp+90h+IoStatusBlock], rax; IoStatusBlock
0x140049639  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, 0
0x140049644  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14004964f  call    cs:__imp_ZwNotifyChangeKey
0x140049656  nop     dword ptr [rax+rax+00h]
0x14004965b  mov     eax, ebx
0x14004965d  mov     rbx, [rsp+90h+arg_0]
0x140049665  add     rsp, 90h
0x14004966c  pop     rbp
0x14004966d  retn
```
