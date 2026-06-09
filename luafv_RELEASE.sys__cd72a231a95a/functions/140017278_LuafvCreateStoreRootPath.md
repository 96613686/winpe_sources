# LuafvCreateStoreRootPath

- ea: `0x140017278`
- end: `0x140017356`
- name: `LuafvCreateStoreRootPath`
- size: `222`
- prototype: `__int64 __fastcall(PVOID FltObject, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400175f8`
- `0x140019ac0`

## callees

- `0x140017278`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140017318`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017318`
- `ntoskrnl!KeInitializeEvent` at `0x1400172c2`
- `ntoskrnl!KeInitializeEvent` at `0x1400172c2`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140017330`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140017330`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400172f0`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400172f0`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400172a0`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400172a0`

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
    v5 = FltQueueGenericWorkItem(GenericWorkItem, FltObject, LuafvCreateStoreRootPathWorker, DelayedWorkQueue, &Context);
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
0x140017278  mov     [rsp+arg_0], rbx
0x14001727d  mov     [rsp+arg_8], rsi
0x140017282  push    rdi
0x140017283  sub     rsp, 60h
0x140017287  xorps   xmm0, xmm0
0x14001728a  xor     eax, eax
0x14001728c  movups  [rsp+68h+var_38], xmm0
0x140017291  mov     dword ptr [rsp+68h+Event.Header.WaitListHead.Blink], eax
0x140017295  mov     rbx, rdx
0x140017298  movups  xmmword ptr [rsp+68h+Event.Header], xmm0
0x14001729d  mov     rsi, rcx
0x1400172a0  call    cs:__imp_FltAllocateGenericWorkItem
0x1400172a7  nop     dword ptr [rax+rax+00h]
0x1400172ac  mov     rdi, rax
0x1400172af  test    rax, rax
0x1400172b2  jz      loc_14001733E
0x1400172b8  xor     r8d, r8d; State
0x1400172bb  lea     rcx, [rsp+68h+Event]; Event
0x1400172c0  xor     edx, edx; Type
0x1400172c2  call    cs:__imp_KeInitializeEvent
0x1400172c9  nop     dword ptr [rax+rax+00h]
0x1400172ce  lea     rax, [rsp+68h+var_38]
0x1400172d3  mov     qword ptr [rsp+68h+var_38+8], rbx
0x1400172d8  mov     r9d, 1; QueueType
0x1400172de  mov     [rsp+68h+Context], rax; Context
0x1400172e3  lea     r8, LuafvCreateStoreRootPathWorker; WorkerRoutine
0x1400172ea  mov     rdx, rsi; FltObject
0x1400172ed  mov     rcx, rdi; FltWorkItem
0x1400172f0  call    cs:__imp_FltQueueGenericWorkItem
0x1400172f7  nop     dword ptr [rax+rax+00h]
0x1400172fc  mov     ebx, eax
0x1400172fe  test    eax, eax
0x140017300  js      short loc_14001732D
0x140017302  xor     r9d, r9d; Alertable
0x140017305  mov     [rsp+68h+Context], 0; Timeout
0x14001730e  xor     r8d, r8d; WaitMode
0x140017311  lea     rcx, [rsp+68h+Event]; Object
0x140017316  xor     edx, edx; WaitReason
0x140017318  call    cs:__imp_KeWaitForSingleObject
0x14001731f  nop     dword ptr [rax+rax+00h]
0x140017324  test    eax, eax
0x140017326  mov     ebx, eax
0x140017328  cmovns  ebx, dword ptr [rsp+68h+var_38]
0x14001732d  mov     rcx, rdi; FltWorkItem
0x140017330  call    cs:__imp_FltFreeGenericWorkItem
0x140017337  nop     dword ptr [rax+rax+00h]
0x14001733c  jmp     short loc_140017343
0x14001733e  mov     ebx, 0C000009Ah
0x140017343  mov     rsi, [rsp+68h+arg_8]
0x140017348  mov     eax, ebx
0x14001734a  mov     rbx, [rsp+68h+arg_0]
0x14001734f  add     rsp, 60h
0x140017353  pop     rdi
0x140017354  retn
```
