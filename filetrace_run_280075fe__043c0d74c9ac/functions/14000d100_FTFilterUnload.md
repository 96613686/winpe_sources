# FTFilterUnload

- ea: `0x14000d100`
- end: `0x14000d20b`
- name: `FTFilterUnload`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400032b0`
- `0x14000d100`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000d14f`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000d14f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1d0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d17f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d17f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d1ec`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d1ec`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d124`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d137`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d124`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d137`
- `FLTMGR!FltObjectDereference` at `0x14000d1bc`
- `FLTMGR!FltObjectDereference` at `0x14000d1bc`
- `FLTMGR!FltUnregisterFilter` at `0x14000d111`
- `FLTMGR!FltUnregisterFilter` at `0x14000d111`

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
0x14000d100  mov     [rsp+arg_0], rbx
0x14000d105  push    rdi
0x14000d106  sub     rsp, 20h
0x14000d10a  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d111  call    cs:__imp_FltUnregisterFilter
0x14000d118  nop     dword ptr [rax+rax+00h]
0x14000d11d  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000d124  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d12b  nop     dword ptr [rax+rax+00h]
0x14000d130  lea     rcx, Lookaside; Lookaside
0x14000d137  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d13e  nop     dword ptr [rax+rax+00h]
0x14000d143  mov     edx, 80000002h; Action
0x14000d148  lea     rcx, WmiRegistrationContext; DeviceObject
0x14000d14f  call    cs:__imp_IoWMIRegistrationControl
0x14000d156  nop     dword ptr [rax+rax+00h]
0x14000d15b  mov     rcx, cs:LogSessions; P
0x14000d162  test    rcx, rcx
0x14000d165  jz      short loc_14000D178
0x14000d167  mov     edx, 72744C46h; Tag
0x14000d16c  call    cs:__imp_ExFreePoolWithTag
0x14000d173  nop     dword ptr [rax+rax+00h]
0x14000d178  lea     rcx, FastMutex; FastMutex
0x14000d17f  call    cs:__imp_ExAcquireFastMutex
0x14000d186  nop     dword ptr [rax+rax+00h]
0x14000d18b  lea     rdi, P
0x14000d192  mov     rbx, cs:P
0x14000d199  cmp     rbx, rdi
0x14000d19c  jz      short loc_14000D1E5
0x14000d19e  cmp     [rbx+8], rdi
0x14000d1a2  jnz     short loc_14000D1DE
0x14000d1a4  mov     rax, [rbx]
0x14000d1a7  cmp     [rax+8], rbx
0x14000d1ab  jnz     short loc_14000D1DE
0x14000d1ad  mov     cs:P, rax
0x14000d1b4  mov     [rax+8], rdi
0x14000d1b8  mov     rcx, [rbx+10h]; FltObject
0x14000d1bc  call    cs:__imp_FltObjectDereference
0x14000d1c3  nop     dword ptr [rax+rax+00h]
0x14000d1c8  mov     edx, 72744C46h; Tag
0x14000d1cd  mov     rcx, rbx; P
0x14000d1d0  call    cs:__imp_ExFreePoolWithTag
0x14000d1d7  nop     dword ptr [rax+rax+00h]
0x14000d1dc  jmp     short loc_14000D192
0x14000d1de  mov     ecx, 3
0x14000d1e3  int     29h; Win8: RtlFailFast(ecx)
0x14000d1e5  lea     rcx, FastMutex; FastMutex
0x14000d1ec  call    cs:__imp_ExReleaseFastMutex
0x14000d1f3  nop     dword ptr [rax+rax+00h]
0x14000d1f8  call    ThreadTableClear
0x14000d1fd  mov     rbx, [rsp+28h+arg_0]
0x14000d202  xor     eax, eax
0x14000d204  add     rsp, 20h
0x14000d208  pop     rdi
0x14000d209  retn
```
