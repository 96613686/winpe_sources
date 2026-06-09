# CreateRemoteDatabase

- ea: `0x14000afb4`
- end: `0x14000b14a`
- name: `CreateRemoteDatabase`
- size: `406`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011500`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x14000afb4`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14000b053`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000b053`
- `ntoskrnl!ExAllocatePool2` at `0x14000affb`
- `ntoskrnl!ExAllocatePool2` at `0x14000affb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b12b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b12b`
- `ntoskrnl!KeInitializeEvent` at `0x14000afe1`
- `ntoskrnl!KeInitializeEvent` at `0x14000afe1`
- `ntoskrnl!IoQueueWorkItem` at `0x14000b0b1`
- `ntoskrnl!IoQueueWorkItem` at `0x14000b0b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b0d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b0d3`

## pseudocode

```c
__int64 __fastcall CreateRemoteDatabase(__int64 a1, _QWORD *a2)
{
  __int64 Pool2; // rax
  unsigned int *v5; // rbx
  unsigned int v6; // edi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  struct _IO_WORKITEM *WorkItem; // rax
  __int64 v10; // r8
  struct _KEVENT Object; // [rsp+30h] [rbp-28h] BYREF

  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, NotificationEvent, 0);
  Pool2 = ExAllocatePool2(64, 40, 1098149453);
  v5 = (unsigned int *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = a1;
    *(_QWORD *)(Pool2 + 16) = &Object;
    WorkItem = IoAllocateWorkItem(**(PDEVICE_OBJECT **)(a1 + 152));
    *(_QWORD *)v5 = WorkItem;
    if ( WorkItem )
    {
      IoQueueWorkItem(WorkItem, (PIO_WORKITEM_ROUTINE)CreateRemoteDatabaseWorker, DelayedWorkQueue, v5);
      KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
      v6 = v5[6];
      if ( (v6 & 0x80000000) == 0 )
      {
        *a2 = *((_QWORD *)v5 + 4);
LABEL_17:
        ExFreePoolWithTag(v5, 0);
        return v6;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 34, v10, v6);
    }
    else
    {
      v6 = -1073741670;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v8 = 33;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = -1073741670;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v8 = 32;
LABEL_9:
      WPP_SF_(v7->AttachedDevice, v8);
    }
  }
  *a2 = 0;
  if ( v5 )
    goto LABEL_17;
  return v6;
}

```

## disassembly

```asm
0x14000afb4  mov     r11, rsp
0x14000afb7  mov     [r11+8], rbx
0x14000afbb  mov     [r11+10h], rsi
0x14000afbf  push    rdi
0x14000afc0  sub     rsp, 50h
0x14000afc4  xorps   xmm0, xmm0
0x14000afc7  mov     rsi, rdx
0x14000afca  mov     rdi, rcx
0x14000afcd  xor     eax, eax
0x14000afcf  movups  xmmword ptr [rsp+58h+Object.Header], xmm0
0x14000afd4  xor     r8d, r8d; State
0x14000afd7  mov     [r11-18h], rax
0x14000afdb  xor     edx, edx; Type
0x14000afdd  lea     rcx, [r11-28h]; Event
0x14000afe1  call    cs:__imp_KeInitializeEvent
0x14000afe8  nop     dword ptr [rax+rax+00h]
0x14000afed  mov     edx, 28h ; '('
0x14000aff2  mov     r8d, 41746E4Dh
0x14000aff8  lea     ecx, [rdx+18h]
0x14000affb  call    cs:__imp_ExAllocatePool2
0x14000b002  nop     dword ptr [rax+rax+00h]
0x14000b007  mov     rbx, rax
0x14000b00a  test    rax, rax
0x14000b00d  jnz     short loc_14000B03C
0x14000b00f  mov     edi, 0C000009Ah
0x14000b014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b01b  lea     rax, WPP_GLOBAL_Control
0x14000b022  cmp     rcx, rax
0x14000b025  jz      loc_14000B111
0x14000b02b  mov     edx, [rcx+2Ch]
0x14000b02e  test    dl, 4
0x14000b031  jz      loc_14000B111
0x14000b037  lea     edx, [rbx+20h]
0x14000b03a  jmp     short loc_14000B093
0x14000b03c  mov     [rbx+8], rdi
0x14000b040  lea     rax, [rsp+58h+Object]
0x14000b045  mov     [rbx+10h], rax
0x14000b049  mov     rcx, [rdi+98h]
0x14000b050  mov     rcx, [rcx]; DeviceObject
0x14000b053  call    cs:__imp_IoAllocateWorkItem
0x14000b05a  nop     dword ptr [rax+rax+00h]
0x14000b05f  mov     [rbx], rax
0x14000b062  test    rax, rax
0x14000b065  jnz     short loc_14000B09E
0x14000b067  mov     edi, 0C000009Ah
0x14000b06c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b073  lea     rax, WPP_GLOBAL_Control
0x14000b07a  cmp     rcx, rax
0x14000b07d  jz      loc_14000B111
0x14000b083  mov     eax, [rcx+2Ch]
0x14000b086  test    al, 4
0x14000b088  jz      loc_14000B111
0x14000b08e  mov     edx, 21h ; '!'
0x14000b093  mov     rcx, [rcx+18h]
0x14000b097  call    WPP_SF_
0x14000b09c  jmp     short loc_14000B111
0x14000b09e  mov     r9, rbx; Context
0x14000b0a1  lea     rdx, CreateRemoteDatabaseWorker; WorkerRoutine
0x14000b0a8  mov     r8d, 1; QueueType
0x14000b0ae  mov     rcx, rax; IoWorkItem
0x14000b0b1  call    cs:__imp_IoQueueWorkItem
0x14000b0b8  nop     dword ptr [rax+rax+00h]
0x14000b0bd  xor     r9d, r9d; Alertable
0x14000b0c0  mov     [rsp+58h+Timeout], 0; Timeout
0x14000b0c9  xor     r8d, r8d; WaitMode
0x14000b0cc  lea     rcx, [rsp+58h+Object]; Object
0x14000b0d1  xor     edx, edx; WaitReason
0x14000b0d3  call    cs:__imp_KeWaitForSingleObject
0x14000b0da  nop     dword ptr [rax+rax+00h]
0x14000b0df  mov     edi, [rbx+18h]
0x14000b0e2  test    edi, edi
0x14000b0e4  jns     short loc_14000B11F
0x14000b0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0ed  lea     rax, WPP_GLOBAL_Control
0x14000b0f4  cmp     rcx, rax
0x14000b0f7  jz      short loc_14000B111
0x14000b0f9  mov     eax, [rcx+2Ch]
0x14000b0fc  test    al, 1
0x14000b0fe  jz      short loc_14000B111
0x14000b100  mov     rcx, [rcx+18h]
0x14000b104  mov     edx, 22h ; '"'
0x14000b109  mov     r9d, edi
0x14000b10c  call    WPP_SF_L
0x14000b111  mov     qword ptr [rsi], 0
0x14000b118  test    rbx, rbx
0x14000b11b  jz      short loc_14000B137
0x14000b11d  jmp     short loc_14000B126
0x14000b11f  mov     rcx, [rbx+20h]
0x14000b123  mov     [rsi], rcx
0x14000b126  xor     edx, edx; Tag
0x14000b128  mov     rcx, rbx; P
0x14000b12b  call    cs:__imp_ExFreePoolWithTag
0x14000b132  nop     dword ptr [rax+rax+00h]
0x14000b137  mov     rbx, [rsp+58h+arg_0]
0x14000b13c  mov     eax, edi
0x14000b13e  mov     rsi, [rsp+58h+arg_8]
0x14000b143  add     rsp, 50h
0x14000b147  pop     rdi
0x14000b148  retn
```
