# SecPsInitializeWorkingThread

- ea: `0x14002f8e4`
- end: `0x14002fa58`
- name: `SecPsInitializeWorkingThread`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002f410`

## callees

- `0x140011650`
- `0x1400119c0`
- `0x14002f8e4`

## import_xrefs

- `ntoskrnl!KeInitializeGuardedMutex` at `0x14002f934`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14002f934`
- `ntoskrnl!PsCreateSystemThread` at `0x14002f9c4`
- `ntoskrnl!PsCreateSystemThread` at `0x14002f9c4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002fa31`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002fa31`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f995`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002f995`
- `ntoskrnl!KeInitializeEvent` at `0x14002f94c`
- `ntoskrnl!KeInitializeEvent` at `0x14002f964`
- `ntoskrnl!KeInitializeEvent` at `0x14002f94c`
- `ntoskrnl!KeInitializeEvent` at `0x14002f964`
- `ntoskrnl!ZwClose` at `0x14002fa1e`
- `ntoskrnl!ZwClose` at `0x14002fa1e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f9f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f9f7`

## pseudocode

```c
__int64 SecPsInitializeWorkingThread()
{
  NTSTATUS v0; // ebx
  void *ThreadHandle; // [rsp+40h] [rbp-18h] BYREF

  ThreadHandle = 0;
  memset(&Mutex, 0, 0x170u);
  qword_14001B2C8 = (__int64)&SecPsCalloutWorkQueue;
  SecPsCalloutWorkQueue = (__int64)&SecPsCalloutWorkQueue;
  KeInitializeGuardedMutex(&Mutex);
  KeInitializeEvent(&stru_14001B308, NotificationEvent, 0);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)&Lookaside, 0, 0, 0, 0x38u, 0x57636553u, 0);
  v0 = PsCreateSystemThread(&ThreadHandle, 0, 0, 0, 0, SecPsCalloutWorker, &SecPsCalloutWorkQueue);
  if ( v0 < 0 || (v0 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &qword_14001B320, 0), v0 < 0) )
  {
    if ( ThreadHandle )
      ZwClose(ThreadHandle);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)&Lookaside);
    return (unsigned int)v0;
  }
  else
  {
    byte_14001B400 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x14002f8e4  mov     [rsp+arg_0], rbx
0x14002f8e9  push    rdi
0x14002f8ea  sub     rsp, 50h
0x14002f8ee  mov     rax, cs:__security_cookie
0x14002f8f5  xor     rax, rsp
0x14002f8f8  mov     [rsp+58h+var_10], rax
0x14002f8fd  xor     edi, edi
0x14002f8ff  lea     rcx, Mutex; void *
0x14002f906  xor     edx, edx; Val
0x14002f908  mov     [rsp+58h+ThreadHandle], rdi
0x14002f90d  mov     r8d, 170h; Size
0x14002f913  call    memset
0x14002f918  lea     rbx, SecPsCalloutWorkQueue
0x14002f91f  lea     rcx, Mutex; Mutex
0x14002f926  mov     cs:qword_14001B2C8, rbx
0x14002f92d  mov     cs:SecPsCalloutWorkQueue, rbx
0x14002f934  call    cs:__imp_KeInitializeGuardedMutex
0x14002f93b  nop     dword ptr [rax+rax+00h]
0x14002f940  xor     r8d, r8d; State
0x14002f943  lea     rcx, stru_14001B308; Event
0x14002f94a  xor     edx, edx; Type
0x14002f94c  call    cs:__imp_KeInitializeEvent
0x14002f953  nop     dword ptr [rax+rax+00h]
0x14002f958  xor     r8d, r8d; State
0x14002f95b  lea     rcx, Event; Event
0x14002f962  xor     edx, edx; Type
0x14002f964  call    cs:__imp_KeInitializeEvent
0x14002f96b  nop     dword ptr [rax+rax+00h]
0x14002f970  mov     [rsp+58h+Depth], di; Depth
0x14002f975  lea     rcx, Lookaside; Lookaside
0x14002f97c  mov     [rsp+58h+Tag], 57636553h; Tag
0x14002f984  xor     r9d, r9d; Flags
0x14002f987  xor     r8d, r8d; Free
0x14002f98a  mov     [rsp+58h+Size], 38h ; '8'; Size
0x14002f993  xor     edx, edx; Allocate
0x14002f995  call    cs:__imp_ExInitializePagedLookasideList
0x14002f99c  nop     dword ptr [rax+rax+00h]
0x14002f9a1  lea     rax, SecPsCalloutWorker
0x14002f9a8  mov     qword ptr [rsp+58h+Depth], rbx; StartContext
0x14002f9ad  mov     qword ptr [rsp+58h+Tag], rax; StartRoutine
0x14002f9b2  lea     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x14002f9b7  xor     r9d, r9d; ProcessHandle
0x14002f9ba  mov     [rsp+58h+Size], rdi; ClientId
0x14002f9bf  xor     r8d, r8d; ObjectAttributes
0x14002f9c2  xor     edx, edx; DesiredAccess
0x14002f9c4  call    cs:__imp_PsCreateSystemThread
0x14002f9cb  nop     dword ptr [rax+rax+00h]
0x14002f9d0  mov     ebx, eax
0x14002f9d2  test    eax, eax
0x14002f9d4  js      short loc_14002FA14
0x14002f9d6  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x14002f9db  lea     rax, qword_14001B320
0x14002f9e2  mov     qword ptr [rsp+58h+Tag], rdi; HandleInformation
0x14002f9e7  xor     r9d, r9d; AccessMode
0x14002f9ea  xor     r8d, r8d; ObjectType
0x14002f9ed  mov     [rsp+58h+Size], rax; Object
0x14002f9f2  mov     edx, 1FFFFFh; DesiredAccess
0x14002f9f7  call    cs:__imp_ObReferenceObjectByHandle
0x14002f9fe  nop     dword ptr [rax+rax+00h]
0x14002fa03  mov     ebx, eax
0x14002fa05  test    eax, eax
0x14002fa07  js      short loc_14002FA14
0x14002fa09  mov     cs:byte_14001B400, 1
0x14002fa10  xor     eax, eax
0x14002fa12  jmp     short loc_14002FA3F
0x14002fa14  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x14002fa19  test    rcx, rcx
0x14002fa1c  jz      short loc_14002FA2A
0x14002fa1e  call    cs:__imp_ZwClose
0x14002fa25  nop     dword ptr [rax+rax+00h]
0x14002fa2a  lea     rcx, Lookaside; Lookaside
0x14002fa31  call    cs:__imp_ExDeletePagedLookasideList
0x14002fa38  nop     dword ptr [rax+rax+00h]
0x14002fa3d  mov     eax, ebx
0x14002fa3f  mov     rcx, [rsp+58h+var_10]
0x14002fa44  xor     rcx, rsp; StackCookie
0x14002fa47  call    __security_check_cookie
0x14002fa4c  mov     rbx, [rsp+58h+arg_0]
0x14002fa51  add     rsp, 50h
0x14002fa55  pop     rdi
0x14002fa56  retn
```
