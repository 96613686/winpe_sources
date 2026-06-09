# SecPsCalloutRundown

- ea: `0x14002f4cc`
- end: `0x14002f5d7`
- name: `SecPsCalloutRundown`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002a5e8`

## callees

- `0x140011610`
- `0x14002f4cc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002f555`
- `ntoskrnl!KeSetEvent` at `0x14002f56f`
- `ntoskrnl!KeSetEvent` at `0x14002f555`
- `ntoskrnl!KeSetEvent` at `0x14002f56f`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14002f52d`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14002f52d`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14002f4e5`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14002f4e5`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14002f4f8`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14002f4f8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f5be`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f5be`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f598`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002f598`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f5ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f5ab`

## pseudocode

```c
void SecPsCalloutRundown()
{
  __int64 v0; // r8

  *((_BYTE *)SecData + 1268) = 0;
  PsRemoveCreateThreadNotifyRoutine(SecCreateThreadNotifyProxyRoutine);
  PsRemoveLoadImageNotifyRoutine(SecPsLoadImageNotify);
  if ( qword_140020010 )
  {
    LOBYTE(v0) = 1;
    qword_140020010(0, SecPsCreateProcessNotify, v0);
  }
  else
  {
    PsSetCreateProcessNotifyRoutineEx(SecPsCreateProcessNotify, 1u);
  }
  if ( byte_14001B400 )
  {
    KeSetEvent(&stru_14001B308, 1, 0);
    KeSetEvent(&Event, 1, 0);
    if ( qword_14001B320 )
    {
      KeWaitForSingleObject(qword_14001B320, Executive, 0, 0, 0);
      ObfDereferenceObject(qword_14001B320);
    }
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)&Lookaside);
    byte_14001B400 = 0;
  }
}

```

## disassembly

```asm
0x14002f4cc  sub     rsp, 38h
0x14002f4d0  mov     rax, cs:SecData
0x14002f4d7  lea     rcx, SecCreateThreadNotifyProxyRoutine; NotifyRoutine
0x14002f4de  mov     byte ptr [rax+4F4h], 0
0x14002f4e5  call    cs:__imp_PsRemoveCreateThreadNotifyRoutine
0x14002f4ec  nop     dword ptr [rax+rax+00h]
0x14002f4f1  lea     rcx, SecPsLoadImageNotify; NotifyRoutine
0x14002f4f8  call    cs:__imp_PsRemoveLoadImageNotifyRoutine
0x14002f4ff  nop     dword ptr [rax+rax+00h]
0x14002f504  mov     rax, cs:qword_140020010
0x14002f50b  test    rax, rax
0x14002f50e  jz      short loc_14002F524
0x14002f510  mov     r8b, 1
0x14002f513  lea     rdx, SecPsCreateProcessNotify
0x14002f51a  xor     ecx, ecx
0x14002f51c  call    cs:__guard_dispatch_icall_fptr
0x14002f522  jmp     short loc_14002F539
0x14002f524  mov     dl, 1; Remove
0x14002f526  lea     rcx, SecPsCreateProcessNotify; NotifyRoutine
0x14002f52d  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x14002f534  nop     dword ptr [rax+rax+00h]
0x14002f539  mov     al, cs:byte_14001B400
0x14002f53f  test    al, al
0x14002f541  jz      loc_14002F5D1
0x14002f547  xor     r8d, r8d; Wait
0x14002f54a  lea     rcx, stru_14001B308; Event
0x14002f551  lea     edx, [r8+1]; Increment
0x14002f555  call    cs:__imp_KeSetEvent
0x14002f55c  nop     dword ptr [rax+rax+00h]
0x14002f561  xor     r8d, r8d; Wait
0x14002f564  lea     rcx, Event; Event
0x14002f56b  lea     edx, [r8+1]; Increment
0x14002f56f  call    cs:__imp_KeSetEvent
0x14002f576  nop     dword ptr [rax+rax+00h]
0x14002f57b  mov     rcx, cs:qword_14001B320; Object
0x14002f582  test    rcx, rcx
0x14002f585  jz      short loc_14002F5B7
0x14002f587  xor     r9d, r9d; Alertable
0x14002f58a  mov     [rsp+38h+Timeout], 0; Timeout
0x14002f593  xor     r8d, r8d; WaitMode
0x14002f596  xor     edx, edx; WaitReason
0x14002f598  call    cs:__imp_KeWaitForSingleObject
0x14002f59f  nop     dword ptr [rax+rax+00h]
0x14002f5a4  mov     rcx, cs:qword_14001B320; Object
0x14002f5ab  call    cs:__imp_ObfDereferenceObject
0x14002f5b2  nop     dword ptr [rax+rax+00h]
0x14002f5b7  lea     rcx, Lookaside; Lookaside
0x14002f5be  call    cs:__imp_ExDeletePagedLookasideList
0x14002f5c5  nop     dword ptr [rax+rax+00h]
0x14002f5ca  mov     cs:byte_14001B400, 0
0x14002f5d1  add     rsp, 38h
0x14002f5d5  retn
```
