# DriverEntry

- ea: `0x14000e078`
- end: `0x14000e2e8`
- name: `DriverEntry`
- size: `624`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e010`

## callees

- `0x140003900`
- `0x14000b838`
- `0x14000e078`
- `0x14000e2f0`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000e22e`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000e22e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1b1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e203`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e203`
- `ntoskrnl!KeInitializeEvent` at `0x14000e12e`
- `ntoskrnl!KeInitializeEvent` at `0x14000e12e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e0b4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e0b4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e167`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e196`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e167`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000e196`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2ba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2cd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e629`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e63c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2ba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2cd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e629`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e63c`
- `FLTMGR!FltStartFiltering` at `0x14000e285`
- `FLTMGR!FltStartFiltering` at `0x14000e285`
- `FLTMGR!FltRegisterFilter` at `0x14000e254`
- `FLTMGR!FltRegisterFilter` at `0x14000e254`
- `FLTMGR!FltUnregisterFilter` at `0x14000e2a7`
- `FLTMGR!FltUnregisterFilter` at `0x14000e615`
- `FLTMGR!FltUnregisterFilter` at `0x14000e2a7`
- `FLTMGR!FltUnregisterFilter` at `0x14000e615`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 i; // rbx
  __int64 *v4; // rdi
  char *PoolWithTag; // rax
  int started; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-40h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"KeAreAllApcsDisabled");
  GlobalLateBoundFunctions = (__int64 (*)(void))MmGetSystemRoutineAddress(&DestinationString);
  FTSequenceNumber = 0;
  dword_140007240 = 0;
  dword_140007244 = 1024;
  WmiRegistrationContext.Dpc.DpcData = DriverObject;
  qword_140007250 = (__int64)&P;
  P = &P;
  FastMutex.Count = 1;
  FastMutex.Owner = 0;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved,
    0,
    0,
    0x200u,
    0x110u,
    0x72744C46u,
    0);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x800u, 0x72744C46u, 0);
  KeInitializeSpinLock(&Lock);
  memset(ThreadTable, 0, 0x978u);
  for ( i = 0; (unsigned int)i < 0x65; i = (unsigned int)(i + 1) )
  {
    v4 = &qword_1400072E8[3 * i];
    v4[1] = (__int64)v4;
    *v4 = (__int64)v4;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x72744C46u);
    if ( !PoolWithTag )
      break;
    *(_OWORD *)PoolWithTag = 0;
    *((_QWORD *)PoolWithTag + 2) = 0;
    ExInterlockedInsertHeadList((PLIST_ENTRY)&qword_1400072E8[3 * i], (PLIST_ENTRY)(PoolWithTag + 8), &Lock);
    _InterlockedIncrement((volatile signed __int32 *)&ThreadTable[3 * i]);
  }
  started = FltRegisterFilter(
              DriverObject,
              &FilterRegistration,
              (PFLT_FILTER *)&WmiRegistrationContext.SecurityDescriptor);
  if ( started >= 0 )
  {
    started = FTInitTracing();
    if ( started >= 0 )
    {
      InitBootLoggingIfSet();
      started = FltStartFiltering((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor);
    }
  }
  if ( started < 0 )
  {
    if ( WmiRegistrationContext.SecurityDescriptor )
      FltUnregisterFilter((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor);
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved);
    ExDeleteNPagedLookasideList(&Lookaside);
  }
  return started;
}

```

## disassembly

```asm
0x14000e078  push    rbx
0x14000e07a  push    rsi
0x14000e07b  push    rdi
0x14000e07c  push    r12
0x14000e07e  push    r14
0x14000e080  sub     rsp, 60h
0x14000e084  mov     r14, rcx
0x14000e087  mov     [rsp+88h+var_48], 0C000000Dh
0x14000e08f  xorps   xmm0, xmm0
0x14000e092  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14000e097  lea     rdx, aKeareallapcsdi; "KeAreAllApcsDisabled"
0x14000e09e  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14000e0a3  call    cs:__imp_RtlInitUnicodeString
0x14000e0aa  nop     dword ptr [rax+rax+00h]
0x14000e0af  lea     rcx, [rsp+88h+DestinationString]; SystemRoutineName
0x14000e0b4  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e0bb  nop     dword ptr [rax+rax+00h]
0x14000e0c0  mov     cs:GlobalLateBoundFunctions, rax
0x14000e0c7  mov     cs:FTSequenceNumber, 0
0x14000e0d1  mov     cs:dword_140007240, 0
0x14000e0db  mov     cs:dword_140007244, 400h
0x14000e0e5  mov     cs:WmiRegistrationContext.Dpc.DpcData, r14
0x14000e0ec  lea     rax, P
0x14000e0f3  mov     cs:qword_140007250, rax
0x14000e0fa  mov     cs:P, rax
0x14000e101  mov     cs:FastMutex.Count, 1
0x14000e10b  mov     cs:FastMutex.Owner, 0
0x14000e116  mov     cs:FastMutex.Contention, 0
0x14000e120  xor     r8d, r8d; State
0x14000e123  lea     edx, [r8+1]; Type
0x14000e127  lea     rcx, FastMutex.Event; Event
0x14000e12e  call    cs:__imp_KeInitializeEvent
0x14000e135  nop     dword ptr [rax+rax+00h]
0x14000e13a  xor     eax, eax
0x14000e13c  mov     [rsp+88h+Depth], ax; Depth
0x14000e141  mov     ebx, 72744C46h
0x14000e146  mov     [rsp+88h+Tag], ebx; Tag
0x14000e14a  mov     [rsp+88h+Size], 110h; Size
0x14000e153  mov     edi, 200h
0x14000e158  mov     r9d, edi; Flags
0x14000e15b  xor     r8d, r8d; Free
0x14000e15e  xor     edx, edx; Allocate
0x14000e160  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e167  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000e16e  nop     dword ptr [rax+rax+00h]
0x14000e173  xor     eax, eax
0x14000e175  mov     [rsp+88h+Depth], ax; Depth
0x14000e17a  mov     [rsp+88h+Tag], ebx; Tag
0x14000e17e  mov     [rsp+88h+Size], 800h; Size
0x14000e187  mov     r9d, edi; Flags
0x14000e18a  xor     r8d, r8d; Free
0x14000e18d  xor     edx, edx; Allocate
0x14000e18f  lea     rcx, Lookaside; Lookaside
0x14000e196  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000e19d  nop     dword ptr [rax+rax+00h]
0x14000e1a2  mov     [rsp+88h+var_44], 0
0x14000e1aa  lea     rcx, Lock; SpinLock
0x14000e1b1  call    cs:__imp_KeInitializeSpinLock
0x14000e1b8  nop     dword ptr [rax+rax+00h]
0x14000e1bd  xor     edx, edx; Val
0x14000e1bf  mov     r8d, 978h; Size
0x14000e1c5  lea     r12, ThreadTable
0x14000e1cc  mov     rcx, r12; void *
0x14000e1cf  call    memset
0x14000e1d4  xor     ebx, ebx
0x14000e1d6  mov     [rsp+88h+var_44], ebx
0x14000e1da  cmp     ebx, 65h ; 'e'
0x14000e1dd  jnb     short loc_14000E243
0x14000e1df  lea     rsi, [rbx+rbx*2]
0x14000e1e3  lea     rdi, [r12+8]
0x14000e1e8  lea     rdi, [rdi+rsi*8]
0x14000e1ec  mov     [rdi+8], rdi
0x14000e1f0  mov     [rdi], rdi
0x14000e1f3  mov     edx, 18h; NumberOfBytes
0x14000e1f8  mov     ecx, 200h; PoolType
0x14000e1fd  mov     r8d, 72744C46h; Tag
0x14000e203  call    cs:__imp_ExAllocatePoolWithTag
0x14000e20a  nop     dword ptr [rax+rax+00h]
0x14000e20f  test    rax, rax
0x14000e212  jz      short loc_14000E243
0x14000e214  xorps   xmm0, xmm0
0x14000e217  xor     ecx, ecx
0x14000e219  movups  xmmword ptr [rax], xmm0
0x14000e21c  mov     [rax+10h], rcx
0x14000e220  lea     rdx, [rax+8]; ListEntry
0x14000e224  lea     r8, Lock; Lock
0x14000e22b  mov     rcx, rdi; ListHead
0x14000e22e  call    cs:__imp_ExInterlockedInsertHeadList
0x14000e235  nop     dword ptr [rax+rax+00h]
0x14000e23a  lock inc dword ptr [r12+rsi*8]
0x14000e23f  inc     ebx
0x14000e241  jmp     short loc_14000E1D6
0x14000e243  lea     r8, WmiRegistrationContext.SecurityDescriptor; RetFilter
0x14000e24a  lea     rdx, FilterRegistration; Registration
0x14000e251  mov     rcx, r14; Driver
0x14000e254  call    cs:__imp_FltRegisterFilter
0x14000e25b  nop     dword ptr [rax+rax+00h]
0x14000e260  mov     ebx, eax
0x14000e262  mov     [rsp+88h+var_48], eax
0x14000e266  test    eax, eax
0x14000e268  js      short loc_14000E297
0x14000e26a  call    FTInitTracing
0x14000e26f  mov     ebx, eax
0x14000e271  mov     [rsp+88h+var_48], eax
0x14000e275  test    eax, eax
0x14000e277  js      short loc_14000E297
0x14000e279  call    InitBootLoggingIfSet
0x14000e27e  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e285  call    cs:__imp_FltStartFiltering
0x14000e28c  nop     dword ptr [rax+rax+00h]
0x14000e291  mov     ebx, eax
0x14000e293  mov     [rsp+88h+var_48], eax
0x14000e297  test    ebx, ebx
0x14000e299  jns     short loc_14000E2D9
0x14000e29b  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e2a2  test    rcx, rcx
0x14000e2a5  jz      short loc_14000E2B3
0x14000e2a7  call    cs:__imp_FltUnregisterFilter
0x14000e2ae  nop     dword ptr [rax+rax+00h]
0x14000e2b3  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e2ba  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e2c1  nop     dword ptr [rax+rax+00h]
0x14000e2c6  lea     rcx, Lookaside; Lookaside
0x14000e2cd  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e2d4  nop     dword ptr [rax+rax+00h]
0x14000e2d9  mov     eax, ebx
0x14000e2db  add     rsp, 60h
0x14000e2df  pop     r14
0x14000e2e1  pop     r12
0x14000e2e3  pop     rdi
0x14000e2e4  pop     rsi
0x14000e2e5  pop     rbx
0x14000e2e6  retn
0x14000e5fa  push    rbp
0x14000e5fc  sub     rsp, 40h
0x14000e600  mov     rbp, rdx
0x14000e603  cmp     dword ptr [rbp+40h], 0
0x14000e607  jge     short loc_14000E649
0x14000e609  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e610  test    rcx, rcx
0x14000e613  jz      short loc_14000E622
0x14000e615  call    cs:__imp_FltUnregisterFilter
0x14000e61c  nop     dword ptr [rax+rax+00h]
0x14000e621  nop
0x14000e622  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e629  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e630  nop     dword ptr [rax+rax+00h]
0x14000e635  lea     rcx, Lookaside; Lookaside
0x14000e63c  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e643  nop     dword ptr [rax+rax+00h]
0x14000e648  nop
0x14000e649  add     rsp, 40h
0x14000e64d  pop     rbp
0x14000e64e  retn
```
