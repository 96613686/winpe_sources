# DeviceChangeNotificationRoutine

- ea: `0x14000d030`
- end: `0x14000d0b4`
- name: `DeviceChangeNotificationRoutine`
- size: `132`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000d030`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d09a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000d09a`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000d087`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000d087`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000d057`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000d057`

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
0x14000d030  mov     [rsp+arg_0], rbx
0x14000d035  push    rdi
0x14000d036  sub     rsp, 30h
0x14000d03a  mov     rax, [rcx+4]
0x14000d03e  mov     rdi, rdx
0x14000d041  cmp     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data1
0x14000d048  jnz     short loc_14000D0A6
0x14000d04a  mov     rax, [rcx+0Ch]
0x14000d04e  cmp     rax, qword ptr cs:GUID_IO_VOLUME_NAME_CHANGE.Data4
0x14000d055  jnz     short loc_14000D0A6
0x14000d057  call    cs:__imp_FltAllocateGenericWorkItem
0x14000d05e  nop     dword ptr [rax+rax+00h]
0x14000d063  mov     rbx, rax
0x14000d066  test    rax, rax
0x14000d069  jz      short loc_14000D0A6
0x14000d06b  mov     rdx, cs:WmiRegistrationContext.SecurityDescriptor; FltObject
0x14000d072  lea     r8, UpdateDosDriveLetter; WorkerRoutine
0x14000d079  mov     r9d, 1; QueueType
0x14000d07f  mov     [rsp+38h+Context], rdi; Context
0x14000d084  mov     rcx, rax; FltWorkItem
0x14000d087  call    cs:__imp_FltQueueGenericWorkItem
0x14000d08e  nop     dword ptr [rax+rax+00h]
0x14000d093  test    eax, eax
0x14000d095  jns     short loc_14000D0A6
0x14000d097  mov     rcx, rbx; FltWorkItem
0x14000d09a  call    cs:__imp_FltFreeGenericWorkItem
0x14000d0a1  nop     dword ptr [rax+rax+00h]
0x14000d0a6  mov     rbx, [rsp+38h+arg_0]
0x14000d0ab  xor     eax, eax
0x14000d0ad  add     rsp, 30h
0x14000d0b1  pop     rdi
0x14000d0b2  retn
```
