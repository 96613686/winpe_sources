# SmbCeUninitializeServerTransport

- ea: `0x140040c10`
- end: `0x140040d7f`
- name: `SmbCeUninitializeServerTransport`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140011590`
- `0x140011e70`

## callees

- `0x140014d04`
- `0x1400169c0`
- `0x140040bb0`
- `0x140040c10`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140040d42`
- `ntoskrnl!KeWaitForSingleObject` at `0x140040d42`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040c3c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040cdf`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040c3c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040cdf`
- `ntoskrnl!KeInitializeEvent` at `0x140040cb1`
- `ntoskrnl!KeInitializeEvent` at `0x140040cb1`
- `ntoskrnl!ExAllocatePool2` at `0x140040c6a`
- `ntoskrnl!ExAllocatePool2` at `0x140040c6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d5c`
- `rdbss!RxGetRDBSSProcess` at `0x140040c2d`
- `rdbss!RxGetRDBSSProcess` at `0x140040cd0`
- `rdbss!RxGetRDBSSProcess` at `0x140040c2d`
- `rdbss!RxGetRDBSSProcess` at `0x140040cd0`
- `rdbss!RxPostToWorkerThread` at `0x140040d19`
- `rdbss!RxPostToWorkerThread` at `0x140040d19`
- `mrxsmb!MRxSmbDeviceObject` at `0x140040cfa`

## pseudocode

```c
__int64 __fastcall SmbCeUninitializeServerTransport(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  struct _KPROCESS *v7; // rbx
  __int64 pContext; // rdi
  struct _KPROCESS *RDBSSProcess; // rbx
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  v3 = 0;
  if ( a2 || (v7 = RxGetRDBSSProcess(), IoGetCurrentProcess() != v7) )
  {
    pContext = ExAllocatePool2(66, 128, 1884581203);
    if ( !pContext )
      return (unsigned int)-1073741670;
    memset(&Event, 0, sizeof(Event));
    memset((void *)pContext, 0, 0x80u);
    *(_QWORD *)(pContext + 32) = a1;
    if ( a2 )
    {
      *(_QWORD *)(pContext + 16) = a3;
      *(_QWORD *)(pContext + 8) = a2;
    }
    else
    {
      KeInitializeEvent(&Event, NotificationEvent, 0);
      *(_QWORD *)(pContext + 24) = &Event;
    }
    RDBSSProcess = RxGetRDBSSProcess();
    if ( IoGetCurrentProcess() == RDBSSProcess )
    {
      SmbCeTearDownServerTransport((PVOID)pContext);
    }
    else
    {
      v3 = RxPostToWorkerThread(
             MRxSmbDeviceObject,
             HyperCriticalWorkQueue,
             (PRX_WORK_QUEUE_ITEM)(pContext + 64),
             SmbCeTearDownServerTransport,
             (PVOID)pContext);
      if ( v3 )
      {
        ExFreePoolWithTag((PVOID)pContext, 0);
        return v3;
      }
    }
    if ( a2 )
      return 259;
    else
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  else
  {
    SmbCepTearDownServerTransport(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x140040c10  push    rbx
0x140040c12  push    rbp
0x140040c13  push    rsi
0x140040c14  push    rdi
0x140040c15  push    r14
0x140040c17  push    r15
0x140040c19  sub     rsp, 58h
0x140040c1d  xor     esi, esi
0x140040c1f  mov     r15, r8
0x140040c22  mov     rbp, rdx
0x140040c25  mov     r14, rcx
0x140040c28  test    rdx, rdx
0x140040c2b  jnz     short loc_140040C5A
0x140040c2d  call    cs:__imp_RxGetRDBSSProcess
0x140040c34  nop     dword ptr [rax+rax+00h]
0x140040c39  mov     rbx, rax
0x140040c3c  call    cs:__imp_IoGetCurrentProcess
0x140040c43  nop     dword ptr [rax+rax+00h]
0x140040c48  cmp     rax, rbx
0x140040c4b  jnz     short loc_140040C5A
0x140040c4d  mov     rcx, r14
0x140040c50  call    SmbCepTearDownServerTransport
0x140040c55  jmp     loc_140040D6F
0x140040c5a  mov     ebx, 80h
0x140040c5f  mov     r8d, 70546D53h
0x140040c65  mov     edx, ebx
0x140040c67  lea     ecx, [rbx-3Eh]
0x140040c6a  call    cs:__imp_ExAllocatePool2
0x140040c71  nop     dword ptr [rax+rax+00h]
0x140040c76  mov     rdi, rax
0x140040c79  test    rax, rax
0x140040c7c  jz      loc_140040D6A
0x140040c82  xorps   xmm0, xmm0
0x140040c85  xor     eax, eax
0x140040c87  mov     r8d, ebx; Size
0x140040c8a  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140040c8f  xor     edx, edx; Val
0x140040c91  mov     rcx, rdi; void *
0x140040c94  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x140040c99  call    memset
0x140040c9e  mov     [rdi+20h], r14
0x140040ca2  test    rbp, rbp
0x140040ca5  jnz     short loc_140040CC8
0x140040ca7  xor     r8d, r8d; State
0x140040caa  lea     rcx, [rsp+88h+Event]; Event
0x140040caf  xor     edx, edx; Type
0x140040cb1  call    cs:__imp_KeInitializeEvent
0x140040cb8  nop     dword ptr [rax+rax+00h]
0x140040cbd  lea     rax, [rsp+88h+Event]
0x140040cc2  mov     [rdi+18h], rax
0x140040cc6  jmp     short loc_140040CD0
0x140040cc8  mov     [rdi+10h], r15
0x140040ccc  mov     [rdi+8], rbp
0x140040cd0  call    cs:__imp_RxGetRDBSSProcess
0x140040cd7  nop     dword ptr [rax+rax+00h]
0x140040cdc  mov     rbx, rax
0x140040cdf  call    cs:__imp_IoGetCurrentProcess
0x140040ce6  nop     dword ptr [rax+rax+00h]
0x140040ceb  cmp     rax, rbx
0x140040cee  jnz     short loc_140040CFA
0x140040cf0  mov     rcx, rdi; Context
0x140040cf3  call    SmbCeTearDownServerTransport
0x140040cf8  jmp     short loc_140040D2B
0x140040cfa  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140040d01  lea     r8, [rdi+40h]; pWorkQueueItem
0x140040d05  lea     r9, SmbCeTearDownServerTransport; Routine
0x140040d0c  mov     [rsp+88h+pContext], rdi; pContext
0x140040d11  mov     edx, 2; WorkQueueType
0x140040d16  mov     rcx, [rcx]; pMRxDeviceObject
0x140040d19  call    cs:__imp_RxPostToWorkerThread
0x140040d20  nop     dword ptr [rax+rax+00h]
0x140040d25  mov     esi, eax
0x140040d27  test    eax, eax
0x140040d29  jnz     short loc_140040D57
0x140040d2b  test    rbp, rbp
0x140040d2e  jnz     short loc_140040D50
0x140040d30  xor     r9d, r9d; Alertable
0x140040d33  mov     [rsp+88h+pContext], rbp; Timeout
0x140040d38  xor     r8d, r8d; WaitMode
0x140040d3b  lea     rcx, [rsp+88h+Event]; Object
0x140040d40  xor     edx, edx; WaitReason
0x140040d42  call    cs:__imp_KeWaitForSingleObject
0x140040d49  nop     dword ptr [rax+rax+00h]
0x140040d4e  jmp     short loc_140040D6F
0x140040d50  mov     esi, 103h
0x140040d55  jmp     short loc_140040D6F
0x140040d57  xor     edx, edx; Tag
0x140040d59  mov     rcx, rdi; P
0x140040d5c  call    cs:__imp_ExFreePoolWithTag
0x140040d63  nop     dword ptr [rax+rax+00h]
0x140040d68  jmp     short loc_140040D6F
0x140040d6a  mov     esi, 0C000009Ah
0x140040d6f  mov     eax, esi
0x140040d71  add     rsp, 58h
0x140040d75  pop     r15
0x140040d77  pop     r14
0x140040d79  pop     rdi
0x140040d7a  pop     rsi
0x140040d7b  pop     rbp
0x140040d7c  pop     rbx
0x140040d7d  retn
```
