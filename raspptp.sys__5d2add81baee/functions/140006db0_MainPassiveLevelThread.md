# MainPassiveLevelThread

- ea: `0x140006db0`
- end: `0x140006e99`
- name: `MainPassiveLevelThread`
- size: `233`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006db0`
- `0x140007710`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006de1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006e52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006de1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006e52`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140006e3b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140006e3b`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140006dfb`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140006e6c`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140006dfb`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140006e6c`
- `ntoskrnl!PsTerminateSystemThread` at `0x140006e86`
- `ntoskrnl!PsTerminateSystemThread` at `0x140006e86`

## pseudocode

```c
void __fastcall MainPassiveLevelThread(PVOID StartContext)
{
  PLIST_ENTRY v1; // rax
  PLIST_ENTRY v2; // rbx
  PLIST_ENTRY v3; // rax
  PVOID Object[3]; // [rsp+40h] [rbp-18h] BYREF

  Object[0] = &EventPassiveThread;
  Object[1] = &EventKillThread;
  while ( !KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0) )
  {
    while ( 1 )
    {
      v1 = ExInterlockedRemoveHeadList(&WorkItemList, &GlobalThreadLock);
      v2 = v1;
      if ( !v1 )
        break;
      ((void (__fastcall *)(PLIST_ENTRY))v1[1].Flink)(v1);
      ExFreePoolWithTag(v2, 0);
    }
  }
  while ( 1 )
  {
    v3 = ExInterlockedRemoveHeadList(&WorkItemList, &GlobalThreadLock);
    if ( !v3 )
      break;
    ExFreePoolWithTag(v3, 0);
  }
  hPassiveThread = 0;
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140006db0  push    rbx
0x140006db2  sub     rsp, 50h
0x140006db6  lea     rax, EventPassiveThread
0x140006dbd  mov     [rsp+58h+Object], rax
0x140006dc2  lea     rax, EventKillThread
0x140006dc9  mov     [rsp+58h+var_10], rax
0x140006dce  jmp     short loc_140006E0F
0x140006dd0  mov     rax, [rbx+10h]
0x140006dd4  mov     rcx, rbx
0x140006dd7  call    _guard_dispatch_icall
0x140006ddc  xor     edx, edx; Tag
0x140006dde  mov     rcx, rbx; P
0x140006de1  call    cs:__imp_ExFreePoolWithTag
0x140006de8  nop     dword ptr [rax+rax+00h]
0x140006ded  lea     rdx, GlobalThreadLock; Lock
0x140006df4  lea     rcx, WorkItemList; ListHead
0x140006dfb  call    cs:__imp_ExInterlockedRemoveHeadList
0x140006e02  nop     dword ptr [rax+rax+00h]
0x140006e07  mov     rbx, rax
0x140006e0a  test    rax, rax
0x140006e0d  jnz     short loc_140006DD0
0x140006e0f  xor     r9d, r9d; WaitReason
0x140006e12  mov     [rsp+58h+WaitBlockArray], 0; WaitBlockArray
0x140006e1b  mov     [rsp+58h+Timeout], 0; Timeout
0x140006e24  lea     rdx, [rsp+58h+Object]; Object
0x140006e29  mov     [rsp+58h+Alertable], 0; Alertable
0x140006e2e  mov     [rsp+58h+WaitMode], 0; WaitMode
0x140006e33  lea     r8d, [r9+1]; WaitType
0x140006e37  lea     ecx, [r9+2]; Count
0x140006e3b  call    cs:__imp_KeWaitForMultipleObjects
0x140006e42  nop     dword ptr [rax+rax+00h]
0x140006e47  test    eax, eax
0x140006e49  jz      short loc_140006DED
0x140006e4b  jmp     short loc_140006E5E
0x140006e4d  xor     edx, edx; Tag
0x140006e4f  mov     rcx, rax; P
0x140006e52  call    cs:__imp_ExFreePoolWithTag
0x140006e59  nop     dword ptr [rax+rax+00h]
0x140006e5e  lea     rdx, GlobalThreadLock; Lock
0x140006e65  lea     rcx, WorkItemList; ListHead
0x140006e6c  call    cs:__imp_ExInterlockedRemoveHeadList
0x140006e73  nop     dword ptr [rax+rax+00h]
0x140006e78  test    rax, rax
0x140006e7b  jnz     short loc_140006E4D
0x140006e7d  xor     ecx, ecx; ExitStatus
0x140006e7f  mov     cs:hPassiveThread, rax
0x140006e86  call    cs:__imp_PsTerminateSystemThread
0x140006e8d  nop     dword ptr [rax+rax+00h]
0x140006e92  add     rsp, 50h
0x140006e96  pop     rbx
0x140006e97  retn
```
