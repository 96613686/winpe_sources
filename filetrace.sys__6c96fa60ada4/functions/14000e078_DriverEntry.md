# DriverEntry

- ea: `0x14000e078`
- end: `0x14000e2da`
- name: `DriverEntry`
- size: `610`
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
- `0x14000e2e0`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000e220`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14000e220`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1b1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000e1b1`
- `ntoskrnl!ExAllocatePool2` at `0x14000e201`
- `ntoskrnl!ExAllocatePool2` at `0x14000e201`
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
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2ac`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2bf`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e617`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e62a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2ac`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e2bf`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e617`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000e62a`
- `FLTMGR!FltStartFiltering` at `0x14000e277`
- `FLTMGR!FltStartFiltering` at `0x14000e277`
- `FLTMGR!FltRegisterFilter` at `0x14000e246`
- `FLTMGR!FltRegisterFilter` at `0x14000e246`
- `FLTMGR!FltUnregisterFilter` at `0x14000e299`
- `FLTMGR!FltUnregisterFilter` at `0x14000e603`
- `FLTMGR!FltUnregisterFilter` at `0x14000e299`
- `FLTMGR!FltUnregisterFilter` at `0x14000e603`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 i; // rbx
  __int64 *v4; // rdi
  __int64 Pool2; // rax
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
    Pool2 = ExAllocatePool2(64, 24, 1920224326);
    if ( !Pool2 )
      break;
    ExInterlockedInsertHeadList((PLIST_ENTRY)&qword_1400072E8[3 * i], (PLIST_ENTRY)(Pool2 + 8), &Lock);
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
0x14000e141  mov     edi, 72744C46h
0x14000e146  mov     [rsp+88h+Tag], edi; Tag
0x14000e14a  mov     [rsp+88h+Size], 110h; Size
0x14000e153  mov     ebx, 200h
0x14000e158  mov     r9d, ebx; Flags
0x14000e15b  xor     r8d, r8d; Free
0x14000e15e  xor     edx, edx; Allocate
0x14000e160  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e167  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000e16e  nop     dword ptr [rax+rax+00h]
0x14000e173  xor     eax, eax
0x14000e175  mov     [rsp+88h+Depth], ax; Depth
0x14000e17a  mov     [rsp+88h+Tag], edi; Tag
0x14000e17e  mov     [rsp+88h+Size], 800h; Size
0x14000e187  mov     r9d, ebx; Flags
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
0x14000e1dd  jnb     short loc_14000E235
0x14000e1df  lea     rsi, [rbx+rbx*2]
0x14000e1e3  lea     rdi, [r12+8]
0x14000e1e8  lea     rdi, [rdi+rsi*8]
0x14000e1ec  mov     [rdi+8], rdi
0x14000e1f0  mov     [rdi], rdi
0x14000e1f3  mov     edx, 18h
0x14000e1f8  lea     ecx, [rdx+28h]
0x14000e1fb  mov     r8d, 72744C46h
0x14000e201  call    cs:__imp_ExAllocatePool2
0x14000e208  nop     dword ptr [rax+rax+00h]
0x14000e20d  test    rax, rax
0x14000e210  jz      short loc_14000E235
0x14000e212  lea     rdx, [rax+8]; ListEntry
0x14000e216  lea     r8, Lock; Lock
0x14000e21d  mov     rcx, rdi; ListHead
0x14000e220  call    cs:__imp_ExInterlockedInsertHeadList
0x14000e227  nop     dword ptr [rax+rax+00h]
0x14000e22c  lock inc dword ptr [r12+rsi*8]
0x14000e231  inc     ebx
0x14000e233  jmp     short loc_14000E1D6
0x14000e235  lea     r8, WmiRegistrationContext.SecurityDescriptor; RetFilter
0x14000e23c  lea     rdx, FilterRegistration; Registration
0x14000e243  mov     rcx, r14; Driver
0x14000e246  call    cs:__imp_FltRegisterFilter
0x14000e24d  nop     dword ptr [rax+rax+00h]
0x14000e252  mov     ebx, eax
0x14000e254  mov     [rsp+88h+var_48], eax
0x14000e258  test    eax, eax
0x14000e25a  js      short loc_14000E289
0x14000e25c  call    FTInitTracing
0x14000e261  mov     ebx, eax
0x14000e263  mov     [rsp+88h+var_48], eax
0x14000e267  test    eax, eax
0x14000e269  js      short loc_14000E289
0x14000e26b  call    InitBootLoggingIfSet
0x14000e270  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e277  call    cs:__imp_FltStartFiltering
0x14000e27e  nop     dword ptr [rax+rax+00h]
0x14000e283  mov     ebx, eax
0x14000e285  mov     [rsp+88h+var_48], eax
0x14000e289  test    ebx, ebx
0x14000e28b  jns     short loc_14000E2CB
0x14000e28d  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e294  test    rcx, rcx
0x14000e297  jz      short loc_14000E2A5
0x14000e299  call    cs:__imp_FltUnregisterFilter
0x14000e2a0  nop     dword ptr [rax+rax+00h]
0x14000e2a5  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e2ac  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e2b3  nop     dword ptr [rax+rax+00h]
0x14000e2b8  lea     rcx, Lookaside; Lookaside
0x14000e2bf  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e2c6  nop     dword ptr [rax+rax+00h]
0x14000e2cb  mov     eax, ebx
0x14000e2cd  add     rsp, 60h
0x14000e2d1  pop     r14
0x14000e2d3  pop     r12
0x14000e2d5  pop     rdi
0x14000e2d6  pop     rsi
0x14000e2d7  pop     rbx
0x14000e2d8  retn
0x14000e5e8  push    rbp
0x14000e5ea  sub     rsp, 40h
0x14000e5ee  mov     rbp, rdx
0x14000e5f1  cmp     dword ptr [rbp+40h], 0
0x14000e5f5  jge     short loc_14000E637
0x14000e5f7  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000e5fe  test    rcx, rcx
0x14000e601  jz      short loc_14000E610
0x14000e603  call    cs:__imp_FltUnregisterFilter
0x14000e60a  nop     dword ptr [rax+rax+00h]
0x14000e60f  nop
0x14000e610  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x14000e617  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e61e  nop     dword ptr [rax+rax+00h]
0x14000e623  lea     rcx, Lookaside; Lookaside
0x14000e62a  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000e631  nop     dword ptr [rax+rax+00h]
0x14000e636  nop
0x14000e637  add     rsp, 40h
0x14000e63b  pop     rbp
0x14000e63c  retn
```
