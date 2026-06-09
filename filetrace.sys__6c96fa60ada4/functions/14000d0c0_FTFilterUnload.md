# FTFilterUnload

- ea: `0x14000d0c0`
- end: `0x14000d1cb`
- name: `FTFilterUnload`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400032b0`
- `0x14000d0c0`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000d10f`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000d10f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d12c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d190`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d12c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d190`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d13f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d13f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d1ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d1ac`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0e4`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0f7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0e4`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0f7`
- `FLTMGR!FltObjectDereference` at `0x14000d17c`
- `FLTMGR!FltObjectDereference` at `0x14000d17c`
- `FLTMGR!FltUnregisterFilter` at `0x14000d0d1`
- `FLTMGR!FltUnregisterFilter` at `0x14000d0d1`

## pseudocode

```c
__int64 FTFilterUnload()
{
  PVOID *v0; // rbx
  __int64 v1; // rax

  FltUnregisterFilter((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor);
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved);
  ExDeleteNPagedLookasideList(&Lookaside);
  IoWMIRegistrationControl(&WmiRegistrationContext, 0x80000002);
  if ( LogSessions )
    ExFreePoolWithTag(LogSessions, 0x72744C46u);
  ExAcquireFastMutex(&FastMutex);
  while ( 1 )
  {
    v0 = (PVOID *)P;
    if ( P == &P )
      break;
    if ( *((PVOID **)P + 1) != &P || (v1 = *(_QWORD *)P, *(PVOID *)(*(_QWORD *)P + 8LL) != P) )
      __fastfail(3u);
    P = *(PVOID *)P;
    *(_QWORD *)(v1 + 8) = &P;
    FltObjectDereference(v0[2]);
    ExFreePoolWithTag(v0, 0x72744C46u);
  }
  ExReleaseFastMutex(&FastMutex);
  ThreadTableClear();
  return 0;
}

```

## disassembly

```asm
0x14000d0c0  mov     [rsp+arg_0], rbx
0x14000d0c5  push    rdi
0x14000d0c6  sub     rsp, 20h
0x14000d0ca  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d0d1  call    cs:__imp_FltUnregisterFilter
0x14000d0d8  nop     dword ptr [rax+rax+00h]
0x14000d0dd  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000d0e4  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d0eb  nop     dword ptr [rax+rax+00h]
0x14000d0f0  lea     rcx, Lookaside; Lookaside
0x14000d0f7  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d0fe  nop     dword ptr [rax+rax+00h]
0x14000d103  mov     edx, 80000002h; Action
0x14000d108  lea     rcx, WmiRegistrationContext; DeviceObject
0x14000d10f  call    cs:__imp_IoWMIRegistrationControl
0x14000d116  nop     dword ptr [rax+rax+00h]
0x14000d11b  mov     rcx, cs:LogSessions; P
0x14000d122  test    rcx, rcx
0x14000d125  jz      short loc_14000D138
0x14000d127  mov     edx, 72744C46h; Tag
0x14000d12c  call    cs:__imp_ExFreePoolWithTag
0x14000d133  nop     dword ptr [rax+rax+00h]
0x14000d138  lea     rcx, FastMutex; FastMutex
0x14000d13f  call    cs:__imp_ExAcquireFastMutex
0x14000d146  nop     dword ptr [rax+rax+00h]
0x14000d14b  lea     rdi, P
0x14000d152  mov     rbx, cs:P
0x14000d159  cmp     rbx, rdi
0x14000d15c  jz      short loc_14000D1A5
0x14000d15e  cmp     [rbx+8], rdi
0x14000d162  jnz     short loc_14000D19E
0x14000d164  mov     rax, [rbx]
0x14000d167  cmp     [rax+8], rbx
0x14000d16b  jnz     short loc_14000D19E
0x14000d16d  mov     cs:P, rax
0x14000d174  mov     [rax+8], rdi
0x14000d178  mov     rcx, [rbx+10h]; FltObject
0x14000d17c  call    cs:__imp_FltObjectDereference
0x14000d183  nop     dword ptr [rax+rax+00h]
0x14000d188  mov     edx, 72744C46h; Tag
0x14000d18d  mov     rcx, rbx; P
0x14000d190  call    cs:__imp_ExFreePoolWithTag
0x14000d197  nop     dword ptr [rax+rax+00h]
0x14000d19c  jmp     short loc_14000D152
0x14000d19e  mov     ecx, 3
0x14000d1a3  int     29h; Win8: RtlFailFast(ecx)
0x14000d1a5  lea     rcx, FastMutex; FastMutex
0x14000d1ac  call    cs:__imp_ExReleaseFastMutex
0x14000d1b3  nop     dword ptr [rax+rax+00h]
0x14000d1b8  call    ThreadTableClear
0x14000d1bd  mov     rbx, [rsp+28h+arg_0]
0x14000d1c2  xor     eax, eax
0x14000d1c4  add     rsp, 20h
0x14000d1c8  pop     rdi
0x14000d1c9  retn
```
