# DeviceChangeNotificationRoutine

- ea: `0x14000d070`
- end: `0x14000d0f4`
- name: `DeviceChangeNotificationRoutine`
- size: `132`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000d070`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d0da`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d0da`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000d0c7`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000d0c7`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000d097`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000d097`

## pseudocode

```c
__int64 __fastcall DeviceChangeNotificationRoutine(char *NotificationStructure, PVOID Context)
{
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v4; // rbx

  if ( *(_OWORD *)(NotificationStructure + 4) == *(_OWORD *)&GUID_IO_VOLUME_NAME_CHANGE )
  {
    GenericWorkItem = FltAllocateGenericWorkItem();
    v4 = GenericWorkItem;
    if ( GenericWorkItem )
    {
      if ( FltQueueGenericWorkItem(
             GenericWorkItem,
             WmiRegistrationContext.SecurityDescriptor,
             (PFLT_GENERIC_WORKITEM_ROUTINE)UpdateDosDriveLetter,
             DelayedWorkQueue,
             Context) < 0 )
        FltFreeGenericWorkItem(v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d070  mov     [rsp+arg_0], rbx
0x14000d075  push    rdi
0x14000d076  sub     rsp, 30h
0x14000d07a  mov     rax, [rcx+4]
0x14000d07e  mov     rdi, rdx
0x14000d081  cmp     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x14000d088  jnz     short loc_14000D0E6
0x14000d08a  mov     rax, [rcx+0Ch]
0x14000d08e  cmp     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data4
0x14000d095  jnz     short loc_14000D0E6
0x14000d097  call    cs:__imp_FltAllocateGenericWorkItem
0x14000d09e  nop     dword ptr [rax+rax+00h]
0x14000d0a3  mov     rbx, rax
0x14000d0a6  test    rax, rax
0x14000d0a9  jz      short loc_14000D0E6
0x14000d0ab  mov     rdx, cs:WmiRegistrationContext.SecurityDescriptor; FltObject
0x14000d0b2  lea     r8, UpdateDosDriveLetter; WorkerRoutine
0x14000d0b9  mov     r9d, 1; QueueType
0x14000d0bf  mov     [rsp+38h+Context], rdi; Context
0x14000d0c4  mov     rcx, rax; FltWorkItem
0x14000d0c7  call    cs:__imp_FltQueueGenericWorkItem
0x14000d0ce  nop     dword ptr [rax+rax+00h]
0x14000d0d3  test    eax, eax
0x14000d0d5  jns     short loc_14000D0E6
0x14000d0d7  mov     rcx, rbx; FltWorkItem
0x14000d0da  call    cs:__imp_FltFreeGenericWorkItem
0x14000d0e1  nop     dword ptr [rax+rax+00h]
0x14000d0e6  mov     rbx, [rsp+38h+arg_0]
0x14000d0eb  xor     eax, eax
0x14000d0ed  add     rsp, 30h
0x14000d0f1  pop     rdi
0x14000d0f2  retn
```
