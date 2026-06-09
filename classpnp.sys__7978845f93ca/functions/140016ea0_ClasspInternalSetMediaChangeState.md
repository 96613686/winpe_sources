# ClasspInternalSetMediaChangeState

- ea: `0x140016ea0`
- end: `0x140016f1d`
- name: `ClasspInternalSetMediaChangeState`
- size: `125`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140016c00`
- `0x140016d50`
- `0x140054010`

## callees

- `0x1400157d0`
- `0x140016ea0`
- `0x140019020`
- `0x14001feac`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140040dc2`
- `ntoskrnl!IoQueueWorkItem` at `0x140040dc2`
- `ntoskrnl!IoAllocateWorkItem` at `0x140040d85`
- `ntoskrnl!IoAllocateWorkItem` at `0x140040d85`

## pseudocode

```c
void __fastcall ClasspInternalSetMediaChangeState(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        unsigned __int32 a2,
        char a3)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rsi
  __int32 v6; // eax
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rcx
  unsigned __int8 CurrentState; // al
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v10; // rbp
  GUID *v11; // rdx
  unsigned int ExtraData; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int32 v13; // [rsp+44h] [rbp+Ch]

  if ( a2 <= 3 )
  {
    MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
    if ( MediaChangeDetectionInfo )
    {
      v6 = _InterlockedExchange((volatile __int32 *)&MediaChangeDetectionInfo->MediaChangeDetectionState, a2);
      if ( v6 || a3 )
      {
        if ( v6 != a2 )
        {
          PrivateFdoData = FdoExtension->PrivateFdoData;
          if ( PrivateFdoData->IsStackInitialized == 1 )
          {
            CurrentState = FdoExtension->CommonExtension.CurrentState;
            if ( (CurrentState & 0xFA) == 0
              && CurrentState != 4
              && !_InterlockedCompareExchange(
                    (volatile signed __int32 *)&PrivateFdoData->UpdateDiskPropertiesWorkItemActive,
                    1,
                    0) )
            {
              WorkItem = IoAllocateWorkItem(FdoExtension->DeviceObject);
              v10 = WorkItem;
              if ( WorkItem )
              {
                ClassAcquireRemoveLockEx(
                  FdoExtension->DeviceObject,
                  WorkItem,
                  "minkernel\\storage\\classpnp\\autorun.c",
                  0x366u);
                IoQueueWorkItem(v10, (PIO_WORKITEM_ROUTINE)ClasspUpdateDiskProperties, DelayedWorkQueue, v10);
              }
              else
              {
                _InterlockedExchange(
                  (volatile __int32 *)&FdoExtension->PrivateFdoData->UpdateDiskPropertiesWorkItemActive,
                  0);
              }
            }
          }
          if ( !MediaChangeDetectionInfo->MediaChangeDetectionDisableCount )
          {
            ExtraData = FdoExtension->MediaChangeCount;
            v13 = a2;
            if ( a2 == 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
              }
              v11 = &GUID_IO_MEDIA_ARRIVAL;
            }
            else
            {
              if ( a2 - 2 > 1 )
                return;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
              }
              v11 = &GUID_IO_MEDIA_REMOVAL;
            }
            ClassSendNotification(FdoExtension, v11, 8u, &ExtraData);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
    }
  }
}

```

## disassembly

```asm
0x140016ea0  cmp     edx, 3
0x140016ea3  ja      short locret_140016EDD
0x140016ea5  push    rbx
0x140016ea6  push    rdi
0x140016ea7  sub     rsp, 28h
0x140016eab  mov     [rsp+38h+arg_10], rsi
0x140016eb0  mov     ebx, edx
0x140016eb2  mov     rsi, [rcx+288h]
0x140016eb9  mov     rdi, rcx
0x140016ebc  test    rsi, rsi
0x140016ebf  jz      short loc_140016ED2
0x140016ec1  mov     eax, edx
0x140016ec3  xchg    eax, [rsi+38h]
0x140016ec6  test    eax, eax
0x140016ec8  jz      short loc_140016EDF
0x140016eca  cmp     eax, ebx
0x140016ecc  jnz     loc_140040D3C
0x140016ed2  mov     rsi, [rsp+38h+arg_10]
0x140016ed7  add     rsp, 28h
0x140016edb  pop     rdi
0x140016edc  pop     rbx
0x140016edd  retn
0x140016edf  test    r8b, r8b
0x140016ee2  jnz     short loc_140016ECA
0x140016ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016eeb  lea     rax, WPP_GLOBAL_Control
0x140016ef2  cmp     rcx, rax
0x140016ef5  jz      short loc_140016ED2
0x140016ef7  test    dword ptr [rcx+2Ch], 1000h
0x140016efe  jz      short loc_140016ED2
0x140016f00  cmp     byte ptr [rcx+29h], 4
0x140016f04  jb      short loc_140016ED2
0x140016f06  mov     rcx, [rcx+18h]
0x140016f0a  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140016f11  mov     edx, 17h
0x140016f16  call    WPP_SF_
0x140016f1b  jmp     short loc_140016ED2
0x140040d3c  mov     rcx, [rcx+478h]
0x140040d43  cmp     byte ptr [rcx+2CEh], 1
0x140040d4a  jnz     loc_140040DE9
0x140040d50  movzx   eax, byte ptr [rdi+6Ah]
0x140040d54  test    al, 0FAh
0x140040d56  jnz     loc_140040DE9
0x140040d5c  cmp     al, 4
0x140040d5e  jz      loc_140040DE9
0x140040d64  mov     [rsp+38h+var_18], r14
0x140040d69  xor     eax, eax
0x140040d6b  mov     r14d, 1
0x140040d71  lock cmpxchg [rcx+4FCh], r14d
0x140040d7a  jnz     short loc_140040DE4
0x140040d7c  mov     rcx, [rdi+8]; DeviceObject
0x140040d80  mov     [rsp+38h+arg_8], rbp
0x140040d85  call    cs:__imp_IoAllocateWorkItem
0x140040d8c  nop     dword ptr [rax+rax+00h]
0x140040d91  mov     rbp, rax
0x140040d94  test    rax, rax
0x140040d97  jz      short loc_140040DD0
0x140040d99  mov     rcx, [rdi+8]; DeviceObject
0x140040d9d  lea     r8, aMinkernelStora_1; "minkernel\\storage\\classpnp\\autorun.c"
0x140040da4  mov     r9d, 366h; Line
0x140040daa  mov     rdx, rax; Tag
0x140040dad  call    ClassAcquireRemoveLockEx
0x140040db2  mov     r9, rbp; Context
0x140040db5  lea     rdx, ClasspUpdateDiskProperties; WorkerRoutine
0x140040dbc  mov     r8d, r14d; QueueType
0x140040dbf  mov     rcx, rbp; IoWorkItem
0x140040dc2  call    cs:__imp_IoQueueWorkItem
0x140040dc9  nop     dword ptr [rax+rax+00h]
0x140040dce  jmp     short loc_140040DDF
0x140040dd0  mov     rcx, [rdi+478h]
0x140040dd7  xor     eax, eax
0x140040dd9  xchg    eax, [rcx+4FCh]
0x140040ddf  mov     rbp, [rsp+38h+arg_8]
0x140040de4  mov     r14, [rsp+38h+var_18]
0x140040de9  cmp     dword ptr [rsi+3Ch], 0
0x140040ded  jnz     loc_140016ED2
0x140040df3  mov     eax, [rdi+2B8h]
0x140040df9  mov     [rsp+38h+ExtraData], eax
0x140040dfd  mov     [rsp+38h+arg_4], ebx
0x140040e01  cmp     ebx, 1
0x140040e04  jnz     short loc_140040E46
0x140040e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140040e0d  lea     rax, WPP_GLOBAL_Control
0x140040e14  cmp     rcx, rax
0x140040e17  jz      short loc_140040E3D
0x140040e19  test    dword ptr [rcx+2Ch], 1000h
0x140040e20  jz      short loc_140040E3D
0x140040e22  cmp     byte ptr [rcx+29h], 4
0x140040e26  jb      short loc_140040E3D
0x140040e28  mov     rcx, [rcx+18h]
0x140040e2c  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140040e33  mov     edx, 1Ah
0x140040e38  call    WPP_SF_
0x140040e3d  lea     rdx, GUID_IO_MEDIA_ARRIVAL
0x140040e44  jmp     short loc_140040E90
0x140040e46  add     ebx, 0FFFFFFFEh
0x140040e49  cmp     ebx, 1
0x140040e4c  ja      loc_140016ED2
0x140040e52  mov     rcx, cs:WPP_GLOBAL_Control
0x140040e59  lea     rax, WPP_GLOBAL_Control
0x140040e60  cmp     rcx, rax
0x140040e63  jz      short loc_140040E89
0x140040e65  test    dword ptr [rcx+2Ch], 1000h
0x140040e6c  jz      short loc_140040E89
0x140040e6e  cmp     byte ptr [rcx+29h], 4
0x140040e72  jb      short loc_140040E89
0x140040e74  mov     rcx, [rcx+18h]
0x140040e78  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140040e7f  mov     edx, 1Bh
0x140040e84  call    WPP_SF_
0x140040e89  lea     rdx, GUID_IO_MEDIA_REMOVAL; Guid
0x140040e90  lea     r9, [rsp+38h+ExtraData]; ExtraData
0x140040e95  mov     r8d, 8; ExtraDataSize
0x140040e9b  mov     rcx, rdi; FdoExtension
0x140040e9e  call    ClassSendNotification
0x140040ea3  nop
0x140040ea4  jmp     loc_140016ED2
```
