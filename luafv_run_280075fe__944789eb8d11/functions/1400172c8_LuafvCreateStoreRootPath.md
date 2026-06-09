# LuafvCreateStoreRootPath

- ea: `0x1400172c8`
- end: `0x1400173a6`
- name: `LuafvCreateStoreRootPath`
- size: `222`
- prototype: `__int64 __fastcall(PVOID FltObject)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140017648`
- `0x140019b10`

## callees

- `0x1400172c8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140017368`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017368`
- `ntoskrnl!KeInitializeEvent` at `0x140017312`
- `ntoskrnl!KeInitializeEvent` at `0x140017312`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140017380`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140017380`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140017340`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140017340`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400172f0`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400172f0`

## pseudocode

```c
__int64 __fastcall LuafvCreateStoreRootPath(PVOID FltObject, __int64 a2)
{
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rdi
  NTSTATUS v5; // ebx
  __int128 Context; // [rsp+30h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-28h] BYREF

  Context = 0;
  memset(&Event, 0, 20);
  GenericWorkItem = FltAllocateGenericWorkItem();
  if ( GenericWorkItem )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    *((_QWORD *)&Context + 1) = a2;
    v5 = FltQueueGenericWorkItem(
           GenericWorkItem,
           FltObject,
           (PFLT_GENERIC_WORKITEM_ROUTINE)LuafvCreateStoreRootPathWorker,
           DelayedWorkQueue,
           &Context);
    if ( v5 >= 0 )
    {
      v5 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( v5 >= 0 )
        v5 = Context;
    }
    FltFreeGenericWorkItem(GenericWorkItem);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400172c8  mov     [rsp+arg_0], rbx
0x1400172cd  mov     [rsp+arg_8], rsi
0x1400172d2  push    rdi
0x1400172d3  sub     rsp, 60h
0x1400172d7  xorps   xmm0, xmm0
0x1400172da  xor     eax, eax
0x1400172dc  movups  [rsp+68h+var_38], xmm0
0x1400172e1  mov     dword ptr [rsp+68h+Event.Header.WaitListHead.Blink], eax
0x1400172e5  mov     rbx, rdx
0x1400172e8  movups  xmmword ptr [rsp+68h+Event.Header], xmm0
0x1400172ed  mov     rsi, rcx
0x1400172f0  call    cs:__imp_FltAllocateGenericWorkItem
0x1400172f7  nop     dword ptr [rax+rax+00h]
0x1400172fc  mov     rdi, rax
0x1400172ff  test    rax, rax
0x140017302  jz      loc_14001738E
0x140017308  xor     r8d, r8d; State
0x14001730b  lea     rcx, [rsp+68h+Event]; Event
0x140017310  xor     edx, edx; Type
0x140017312  call    cs:__imp_KeInitializeEvent
0x140017319  nop     dword ptr [rax+rax+00h]
0x14001731e  lea     rax, [rsp+68h+var_38]
0x140017323  mov     qword ptr [rsp+68h+var_38+8], rbx
0x140017328  mov     r9d, 1; QueueType
0x14001732e  mov     [rsp+68h+Context], rax; Context
0x140017333  lea     r8, LuafvCreateStoreRootPathWorker; WorkerRoutine
0x14001733a  mov     rdx, rsi; FltObject
0x14001733d  mov     rcx, rdi; FltWorkItem
0x140017340  call    cs:__imp_FltQueueGenericWorkItem
0x140017347  nop     dword ptr [rax+rax+00h]
0x14001734c  mov     ebx, eax
0x14001734e  test    eax, eax
0x140017350  js      short loc_14001737D
0x140017352  xor     r9d, r9d; Alertable
0x140017355  mov     [rsp+68h+Context], 0; Timeout
0x14001735e  xor     r8d, r8d; WaitMode
0x140017361  lea     rcx, [rsp+68h+Event]; Object
0x140017366  xor     edx, edx; WaitReason
0x140017368  call    cs:__imp_KeWaitForSingleObject
0x14001736f  nop     dword ptr [rax+rax+00h]
0x140017374  test    eax, eax
0x140017376  mov     ebx, eax
0x140017378  cmovns  ebx, dword ptr [rsp+68h+var_38]
0x14001737d  mov     rcx, rdi; FltWorkItem
0x140017380  call    cs:__imp_FltFreeGenericWorkItem
0x140017387  nop     dword ptr [rax+rax+00h]
0x14001738c  jmp     short loc_140017393
0x14001738e  mov     ebx, 0C000009Ah
0x140017393  mov     rsi, [rsp+68h+arg_8]
0x140017398  mov     eax, ebx
0x14001739a  mov     rbx, [rsp+68h+arg_0]
0x14001739f  add     rsp, 60h
0x1400173a3  pop     rdi
0x1400173a4  retn
```
