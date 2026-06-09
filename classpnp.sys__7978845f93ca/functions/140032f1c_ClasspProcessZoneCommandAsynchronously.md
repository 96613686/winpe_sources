# ClasspProcessZoneCommandAsynchronously

- ea: `0x140032f1c`
- end: `0x14003303f`
- name: `ClasspProcessZoneCommandAsynchronously`
- size: `291`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x1400327ac`

## callees

- `0x140032f1c`
- `0x14003c3a4`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140032f8c`
- `ntoskrnl!ExAllocatePool2` at `0x140032f8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032fb9`
- `ntoskrnl!IoQueueWorkItem` at `0x140033031`
- `ntoskrnl!IoQueueWorkItem` at `0x140033031`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140032f63`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140032f63`
- `ntoskrnl!IoSizeofWorkItem` at `0x140032f6f`
- `ntoskrnl!IoSizeofWorkItem` at `0x140032f6f`
- `ntoskrnl!IoAllocateWorkItem` at `0x140032fa3`
- `ntoskrnl!IoAllocateWorkItem` at `0x140032fa3`

## pseudocode

```c
char __fastcall ClasspProcessZoneCommandAsynchronously(
        PDEVICE_OBJECT DeviceObject,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  char v4; // bp
  ULONG v9; // eax
  __int64 Pool2; // rbx
  PIO_WORKITEM WorkItem; // rax
  char v12; // di
  __int64 v14; // rax
  __int128 v15; // [rsp+20h] [rbp-48h] BYREF

  v4 = ClassPnPETWEnabled;
  v15 = 0;
  if ( ClassPnPETWEnabled )
    IoGetActivityIdIrp(a2, &v15);
  v9 = IoSizeofWorkItem();
  Pool2 = ExAllocatePool2(64, v9 + 32LL, 1868194643);
  if ( Pool2 )
  {
    WorkItem = IoAllocateWorkItem(DeviceObject);
    if ( WorkItem )
    {
      *(_QWORD *)(Pool2 + 8) = a2;
      *(_QWORD *)Pool2 = WorkItem;
      *(_QWORD *)(Pool2 + 16) = a3;
      *(_DWORD *)(Pool2 + 24) = a4;
      v14 = *(_QWORD *)(a2 + 184);
      v12 = 1;
      *(_BYTE *)(v14 + 3) |= 1u;
      IoQueueWorkItem(*(PIO_WORKITEM *)Pool2, ClasspProcessZoneCommandWorker, DelayedWorkQueue, (PVOID)Pool2);
      return v12;
    }
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
  v12 = 0;
  if ( v4 )
    ClasspZoneCommandProcessAsyncFailureEvent(&v15, DeviceObject, a4);
  return v12;
}

```

## disassembly

```asm
0x140032f1c  mov     [rsp+arg_10], rbx
0x140032f21  push    rbp
0x140032f22  push    rsi
0x140032f23  push    rdi
0x140032f24  push    r14
0x140032f26  push    r15
0x140032f28  sub     rsp, 40h
0x140032f2c  mov     rax, cs:__security_cookie
0x140032f33  xor     rax, rsp
0x140032f36  mov     [rsp+68h+var_38], rax
0x140032f3b  mov     bpl, cs:ClassPnPETWEnabled
0x140032f42  xorps   xmm0, xmm0
0x140032f45  mov     r14d, r9d
0x140032f48  mov     r15, r8
0x140032f4b  mov     rdi, rdx
0x140032f4e  mov     rsi, rcx
0x140032f51  movups  [rsp+68h+var_48], xmm0
0x140032f56  test    bpl, bpl
0x140032f59  jz      short loc_140032F6F
0x140032f5b  lea     rdx, [rsp+68h+var_48]
0x140032f60  mov     rcx, rdi
0x140032f63  call    cs:__imp_IoGetActivityIdIrp
0x140032f6a  nop     dword ptr [rax+rax+00h]
0x140032f6f  call    cs:__imp_IoSizeofWorkItem
0x140032f76  nop     dword ptr [rax+rax+00h]
0x140032f7b  mov     edx, eax
0x140032f7d  mov     ecx, 40h ; '@'
0x140032f82  add     rdx, 20h ; ' '
0x140032f86  mov     r8d, 6F5A6353h
0x140032f8c  call    cs:__imp_ExAllocatePool2
0x140032f93  nop     dword ptr [rax+rax+00h]
0x140032f98  mov     rbx, rax
0x140032f9b  test    rax, rax
0x140032f9e  jz      short loc_140032FC5
0x140032fa0  mov     rcx, rsi; DeviceObject
0x140032fa3  call    cs:__imp_IoAllocateWorkItem
0x140032faa  nop     dword ptr [rax+rax+00h]
0x140032faf  test    rax, rax
0x140032fb2  jnz     short loc_140033002
0x140032fb4  xor     edx, edx; Tag
0x140032fb6  mov     rcx, rbx; P
0x140032fb9  call    cs:__imp_ExFreePoolWithTag
0x140032fc0  nop     dword ptr [rax+rax+00h]
0x140032fc5  xor     dil, dil
0x140032fc8  test    bpl, bpl
0x140032fcb  jz      short loc_140032FDD
0x140032fcd  mov     r8d, r14d
0x140032fd0  lea     rcx, [rsp+68h+var_48]
0x140032fd5  mov     rdx, rsi
0x140032fd8  call    ClasspZoneCommandProcessAsyncFailureEvent
0x140032fdd  mov     al, dil
0x140032fe0  mov     rcx, [rsp+68h+var_38]
0x140032fe5  xor     rcx, rsp; StackCookie
0x140032fe8  call    __security_check_cookie
0x140032fed  mov     rbx, [rsp+68h+arg_10]
0x140032ff5  add     rsp, 40h
0x140032ff9  pop     r15
0x140032ffb  pop     r14
0x140032ffd  pop     rdi
0x140032ffe  pop     rsi
0x140032fff  pop     rbp
0x140033000  retn
0x140033002  mov     [rbx+8], rdi
0x140033006  lea     rdx, ClasspProcessZoneCommandWorker; WorkerRoutine
0x14003300d  mov     [rbx], rax
0x140033010  mov     r9, rbx; Context
0x140033013  mov     [rbx+10h], r15
0x140033017  mov     [rbx+18h], r14d
0x14003301b  mov     rax, [rdi+0B8h]
0x140033022  mov     edi, 1
0x140033027  mov     r8d, edi; QueueType
0x14003302a  or      [rax+3], dil
0x14003302e  mov     rcx, [rbx]; IoWorkItem
0x140033031  call    cs:__imp_IoQueueWorkItem
0x140033038  nop     dword ptr [rax+rax+00h]
0x14003303d  jmp     short loc_140032FDD
```
