# FTInitTracing

- ea: `0x14000b838`
- end: `0x14000b91b`
- name: `FTInitTracing`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e078`

## callees

- `0x140003900`
- `0x14000b838`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b8d4`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b8d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dac2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dac2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b858`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b858`
- `ntoskrnl!KeInitializeEvent` at `0x14000b8bc`
- `ntoskrnl!KeInitializeEvent` at `0x14000b8bc`

## pseudocode

```c
__int64 FTInitTracing()
{
  PVOID PoolWithTag; // rax
  NTSTATUS v1; // ebx

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x140u, 0x72744C46u);
  LogSessions = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x140u);
    SessionSerialNumber = 0;
    SessionLock.Count = 1;
    SessionLock.Owner = 0;
    SessionLock.Contention = 0;
    KeInitializeEvent(&SessionLock.Event, SynchronizationEvent, 0);
    v1 = IoWMIRegistrationControl(&WmiRegistrationContext, 0x80000001);
  }
  else
  {
    v1 = -1073741670;
  }
  if ( v1 < 0 && LogSessions )
  {
    ExFreePoolWithTag(LogSessions, 0x72744C46u);
    LogSessions = 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000b838  push    rbx
0x14000b83a  sub     rsp, 30h
0x14000b83e  mov     [rsp+38h+var_18], 0
0x14000b846  mov     ebx, 140h
0x14000b84b  mov     r8d, 72744C46h; Tag
0x14000b851  mov     edx, ebx; NumberOfBytes
0x14000b853  mov     ecx, 200h; PoolType
0x14000b858  call    cs:__imp_ExAllocatePoolWithTag
0x14000b85f  nop     dword ptr [rax+rax+00h]
0x14000b864  mov     cs:LogSessions, rax
0x14000b86b  test    rax, rax
0x14000b86e  jnz     short loc_14000B87B
0x14000b870  mov     ebx, 0C000009Ah
0x14000b875  mov     [rsp+38h+var_18], ebx
0x14000b879  jmp     short loc_14000B8E6
0x14000b87b  mov     r8, rbx; Size
0x14000b87e  xor     edx, edx; Val
0x14000b880  mov     rcx, rax; void *
0x14000b883  call    memset
0x14000b888  mov     cs:SessionSerialNumber, 0
0x14000b892  mov     edx, 1; Type
0x14000b897  mov     cs:SessionLock.Count, edx
0x14000b89d  mov     cs:SessionLock.Owner, 0
0x14000b8a8  mov     cs:SessionLock.Contention, 0
0x14000b8b2  xor     r8d, r8d; State
0x14000b8b5  lea     rcx, SessionLock.Event; Event
0x14000b8bc  call    cs:__imp_KeInitializeEvent
0x14000b8c3  nop     dword ptr [rax+rax+00h]
0x14000b8c8  mov     edx, 80000001h; Action
0x14000b8cd  lea     rcx, WmiRegistrationContext; DeviceObject
0x14000b8d4  call    cs:__imp_IoWMIRegistrationControl
0x14000b8db  nop     dword ptr [rax+rax+00h]
0x14000b8e0  mov     ebx, eax
0x14000b8e2  mov     [rsp+38h+var_18], eax
0x14000b8e6  test    ebx, ebx
0x14000b8e8  jns     short loc_14000B912
0x14000b8ea  mov     rcx, cs:LogSessions; P
0x14000b8f1  test    rcx, rcx
0x14000b8f4  jz      short loc_14000B912
0x14000b8f6  mov     edx, 72744C46h; Tag
0x14000b8fb  call    cs:__imp_ExFreePoolWithTag
0x14000b902  nop     dword ptr [rax+rax+00h]
0x14000b907  mov     cs:LogSessions, 0
0x14000b912  mov     eax, ebx
0x14000b914  add     rsp, 30h
0x14000b918  pop     rbx
0x14000b919  retn
0x14000daa2  push    rbp
0x14000daa4  sub     rsp, 20h
0x14000daa8  mov     rbp, rdx
0x14000daab  cmp     dword ptr [rbp+20h], 0
0x14000daaf  jge     short loc_14000DAD9
0x14000dab1  mov     rcx, cs:LogSessions; P
0x14000dab8  test    rcx, rcx
0x14000dabb  jz      short loc_14000DAD9
0x14000dabd  mov     edx, 72744C46h; Tag
0x14000dac2  call    cs:__imp_ExFreePoolWithTag
0x14000dac9  nop     dword ptr [rax+rax+00h]
0x14000dace  mov     cs:LogSessions, 0
0x14000dad9  add     rsp, 20h
0x14000dadd  pop     rbp
0x14000dade  retn
```
