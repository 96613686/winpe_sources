# FTInitTracing

- ea: `0x14000b838`
- end: `0x14000b90c`
- name: `FTInitTracing`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e078`

## callees

- `0x14000b838`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b8c5`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b8c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da82`
- `ntoskrnl!ExAllocatePool2` at `0x14000b856`
- `ntoskrnl!ExAllocatePool2` at `0x14000b856`
- `ntoskrnl!KeInitializeEvent` at `0x14000b8ad`
- `ntoskrnl!KeInitializeEvent` at `0x14000b8ad`

## pseudocode

```c
__int64 FTInitTracing()
{
  NTSTATUS v0; // ebx

  LogSessions = (PVOID)ExAllocatePool2(64, 320, 1920224326);
  if ( LogSessions )
  {
    SessionSerialNumber = 0;
    SessionLock.Count = 1;
    SessionLock.Owner = 0;
    SessionLock.Contention = 0;
    KeInitializeEvent(&SessionLock.Event, SynchronizationEvent, 0);
    v0 = IoWMIRegistrationControl(&WmiRegistrationContext, 0x80000001);
  }
  else
  {
    v0 = -1073741670;
  }
  if ( v0 < 0 && LogSessions )
  {
    ExFreePoolWithTag(LogSessions, 0x72744C46u);
    LogSessions = 0;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000b838  push    rbx
0x14000b83a  sub     rsp, 30h
0x14000b83e  mov     [rsp+38h+var_18], 0
0x14000b846  mov     edx, 140h
0x14000b84b  mov     ecx, 40h ; '@'
0x14000b850  mov     r8d, 72744C46h
0x14000b856  call    cs:__imp_ExAllocatePool2
0x14000b85d  nop     dword ptr [rax+rax+00h]
0x14000b862  mov     cs:LogSessions, rax
0x14000b869  test    rax, rax
0x14000b86c  jnz     short loc_14000B879
0x14000b86e  mov     ebx, 0C000009Ah
0x14000b873  mov     [rsp+38h+var_18], ebx
0x14000b877  jmp     short loc_14000B8D7
0x14000b879  mov     cs:SessionSerialNumber, 0
0x14000b883  mov     edx, 1; Type
0x14000b888  mov     cs:SessionLock.Count, edx
0x14000b88e  mov     cs:SessionLock.Owner, 0
0x14000b899  mov     cs:SessionLock.Contention, 0
0x14000b8a3  xor     r8d, r8d; State
0x14000b8a6  lea     rcx, SessionLock.Event; Event
0x14000b8ad  call    cs:__imp_KeInitializeEvent
0x14000b8b4  nop     dword ptr [rax+rax+00h]
0x14000b8b9  mov     edx, 80000001h; Action
0x14000b8be  lea     rcx, WmiRegistrationContext; DeviceObject
0x14000b8c5  call    cs:__imp_IoWMIRegistrationControl
0x14000b8cc  nop     dword ptr [rax+rax+00h]
0x14000b8d1  mov     ebx, eax
0x14000b8d3  mov     [rsp+38h+var_18], eax
0x14000b8d7  test    ebx, ebx
0x14000b8d9  jns     short loc_14000B903
0x14000b8db  mov     rcx, cs:LogSessions; P
0x14000b8e2  test    rcx, rcx
0x14000b8e5  jz      short loc_14000B903
0x14000b8e7  mov     edx, 72744C46h; Tag
0x14000b8ec  call    cs:__imp_ExFreePoolWithTag
0x14000b8f3  nop     dword ptr [rax+rax+00h]
0x14000b8f8  mov     cs:LogSessions, 0
0x14000b903  mov     eax, ebx
0x14000b905  add     rsp, 30h
0x14000b909  pop     rbx
0x14000b90a  retn
0x14000da62  push    rbp
0x14000da64  sub     rsp, 20h
0x14000da68  mov     rbp, rdx
0x14000da6b  cmp     dword ptr [rbp+20h], 0
0x14000da6f  jge     short loc_14000DA99
0x14000da71  mov     rcx, cs:LogSessions; P
0x14000da78  test    rcx, rcx
0x14000da7b  jz      short loc_14000DA99
0x14000da7d  mov     edx, 72744C46h; Tag
0x14000da82  call    cs:__imp_ExFreePoolWithTag
0x14000da89  nop     dword ptr [rax+rax+00h]
0x14000da8e  mov     cs:LogSessions, 0
0x14000da99  add     rsp, 20h
0x14000da9d  pop     rbp
0x14000da9e  retn
```
