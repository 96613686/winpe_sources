# MountMgrTargetDeviceNotification

- ea: `0x140019f70`
- end: `0x14001a0a8`
- name: `MountMgrTargetDeviceNotification`
- size: `312`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a050`
- `0x14000d494`
- `0x140019140`
- `0x140019f70`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001a038`
- `ntoskrnl!KeReleaseMutex` at `0x14001a038`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a01b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a01b`

## pseudocode

```c
__int64 __fastcall MountMgrTargetDeviceNotification(char *NotificationStructure, __int64 Context)
{
  __int64 v2; // rax
  struct _KMUTANT *v3; // rsi
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax

  v2 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1;
  v3 = *(struct _KMUTANT **)(Context + 152);
  if ( !v2 )
    v2 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4;
  if ( v2 )
  {
    v5 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
    if ( !v5 )
      v5 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
    if ( v5 )
    {
      v6 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_UNIQUE_ID_CHANGE.Data1;
      if ( !v6 )
        v6 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_UNIQUE_ID_CHANGE.Data4;
      if ( v6 )
      {
        v7 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_PREPARE_DELETE.Data1;
        if ( !v7 )
          v7 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_PREPARE_DELETE.Data4;
        if ( !v7 )
          *(_BYTE *)(Context + 135) = 1;
      }
      else
      {
        MountMgrUniqueIdChangeRoutine(Context, (unsigned __int16 *)NotificationStructure + 18);
      }
    }
    else if ( _InterlockedCompareExchange((volatile signed __int32 *)(Context + 136), 0, 0) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(Context + 136));
    }
    else if ( *(_BYTE *)(Context + 131) )
    {
      *(_BYTE *)(Context + 131) = 0;
      KeWaitForSingleObject(&v3[1], Executive, 0, 0, 0);
      ReconcileThisDatabaseWithMaster(v3);
      KeReleaseMutex(v3 + 1, 0);
    }
    return 0;
  }
  else
  {
    MountMgrMountedDeviceRemoval(v3, (const UNICODE_STRING *)(Context + 64), 0);
    return 0;
  }
}

```

## disassembly

```asm
0x140019f70  mov     [rsp+arg_8], rsi
0x140019f75  push    rdi
0x140019f76  sub     rsp, 30h
0x140019f7a  mov     rax, [rcx+4]
0x140019f7e  mov     rdi, rdx
0x140019f81  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
0x140019f88  mov     rsi, [rdx+98h]
0x140019f8f  jnz     short loc_140019F9C
0x140019f91  mov     rax, [rcx+0Ch]
0x140019f95  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4
0x140019f9c  test    rax, rax
0x140019f9f  jnz     short loc_140019FBE
0x140019fa1  add     rdx, 40h ; '@'
0x140019fa5  xor     r8d, r8d
0x140019fa8  mov     rcx, rsi
0x140019fab  call    MountMgrMountedDeviceRemoval
0x140019fb0  xor     eax, eax
0x140019fb2  mov     rsi, [rsp+38h+arg_8]
0x140019fb7  add     rsp, 30h
0x140019fbb  pop     rdi
0x140019fbc  retn
0x140019fbe  mov     rax, [rcx+4]
0x140019fc2  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x140019fc9  jnz     short loc_140019FD6
0x140019fcb  mov     rax, [rcx+0Ch]
0x140019fcf  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x140019fd6  test    rax, rax
0x140019fd9  jnz     short loc_14001A04B
0x140019fdb  xor     ecx, ecx
0x140019fdd  lock cmpxchg [rdx+88h], ecx
0x140019fe5  jz      short loc_140019FF3
0x140019fe7  lock dec dword ptr [rdx+88h]
0x140019fee  jmp     loc_14001A09A
0x140019ff3  cmp     [rdx+83h], cl
0x140019ff9  jz      loc_14001A09A
0x140019fff  mov     [rdx+83h], cl
0x14001a005  xor     r9d, r9d; Alertable
0x14001a008  mov     [rsp+38h+Timeout], rcx; Timeout
0x14001a00d  xor     edx, edx; WaitReason
0x14001a00f  lea     rcx, [rsi+38h]; Object
0x14001a013  mov     [rsp+38h+arg_0], rbx
0x14001a018  xor     r8d, r8d; WaitMode
0x14001a01b  call    cs:__imp_KeWaitForSingleObject
0x14001a022  nop     dword ptr [rax+rax+00h]
0x14001a027  mov     rdx, rdi
0x14001a02a  mov     rcx, rsi; Context
0x14001a02d  call    ReconcileThisDatabaseWithMaster
0x14001a032  xor     edx, edx; Wait
0x14001a034  lea     rcx, [rsi+38h]; Mutex
0x14001a038  call    cs:__imp_KeReleaseMutex
0x14001a03f  nop     dword ptr [rax+rax+00h]
0x14001a044  mov     rbx, [rsp+38h+arg_0]
0x14001a049  jmp     short loc_14001A09A
0x14001a04b  mov     rax, [rcx+4]
0x14001a04f  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNIQUE_ID_CHANGE.Data1
0x14001a056  jnz     short loc_14001A063
0x14001a058  mov     rax, [rcx+0Ch]
0x14001a05c  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNIQUE_ID_CHANGE.Data4
0x14001a063  test    rax, rax
0x14001a066  jnz     short loc_14001A076
0x14001a068  lea     rdx, [rcx+24h]
0x14001a06c  mov     rcx, rdi
0x14001a06f  call    MountMgrUniqueIdChangeRoutine
0x14001a074  jmp     short loc_14001A09A
0x14001a076  mov     rax, [rcx+4]
0x14001a07a  sub     rax, qword ptr cs:GUID_IO_VOLUME_PREPARE_DELETE.Data1
0x14001a081  jnz     short loc_14001A08E
0x14001a083  mov     rax, [rcx+0Ch]
0x14001a087  sub     rax, qword ptr cs:GUID_IO_VOLUME_PREPARE_DELETE.Data4
0x14001a08e  test    rax, rax
0x14001a091  jnz     short loc_14001A09A
0x14001a093  mov     byte ptr [rdx+87h], 1
0x14001a09a  xor     eax, eax
0x14001a09c  mov     rsi, [rsp+38h+arg_8]
0x14001a0a1  add     rsp, 30h
0x14001a0a5  pop     rdi
0x14001a0a6  retn
```
