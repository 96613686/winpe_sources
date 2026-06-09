# RxVmbusInitiateAsynchronousConnect

- ea: `0x140055440`
- end: `0x1400554c9`
- name: `RxVmbusInitiateAsynchronousConnect`
- size: `137`
- prototype: `NTSTATUS __fastcall(_QWORD *pContext)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001cda0`

## callees

- `0x140055440`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140055483`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140055483`
- `ntoskrnl!ExAllocatePool2` at `0x140055465`
- `ntoskrnl!ExAllocatePool2` at `0x140055465`
- `rdbss!RxDispatchToWorkerThread` at `0x1400554a9`
- `rdbss!RxDispatchToWorkerThread` at `0x1400554a9`

## pseudocode

```c
NTSTATUS __fastcall RxVmbusInitiateAsynchronousConnect(_QWORD *pContext)
{
  __int64 v1; // rsi
  __int64 v2; // rbp
  struct _EX_RUNDOWN_REF *Pool2; // rax
  struct _EX_RUNDOWN_REF *v5; // rdi
  NTSTATUS result; // eax

  v1 = pContext[1];
  v2 = pContext[27];
  Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(66, 56, 1665366098);
  v5 = Pool2;
  if ( !Pool2 )
    return -1073741670;
  ExInitializeRundownProtection(Pool2);
  *(_QWORD *)(v2 + 128) = v5;
  result = RxDispatchToWorkerThread(
             *(PRDBSS_DEVICE_OBJECT *)(v1 + 32),
             BackgroundWorkQueue,
             RxVmbusInitiateConnectWorker,
             pContext);
  if ( result >= 0 )
    return 259;
  return result;
}

```

## disassembly

```asm
0x140055440  push    rbx
0x140055442  push    rbp
0x140055443  push    rsi
0x140055444  push    rdi
0x140055445  sub     rsp, 28h
0x140055449  mov     rsi, [rcx+8]
0x14005544d  mov     edx, 38h ; '8'
0x140055452  mov     rbp, [rcx+0D8h]
0x140055459  mov     rbx, rcx
0x14005545c  mov     r8d, 63437852h
0x140055462  lea     ecx, [rdx+0Ah]
0x140055465  call    cs:__imp_ExAllocatePool2
0x14005546c  nop     dword ptr [rax+rax+00h]
0x140055471  mov     rdi, rax
0x140055474  test    rax, rax
0x140055477  jnz     short loc_140055480
0x140055479  mov     eax, 0C000009Ah
0x14005547e  jmp     short loc_1400554BF
0x140055480  mov     rcx, rdi; RunRef
0x140055483  call    cs:__imp_ExInitializeRundownProtection
0x14005548a  nop     dword ptr [rax+rax+00h]
0x14005548f  mov     [rbp+80h], rdi
0x140055496  lea     r8, RxVmbusInitiateConnectWorker; Routine
0x14005549d  mov     rcx, [rsi+20h]; pMRxDeviceObject
0x1400554a1  mov     r9, rbx; pContext
0x1400554a4  mov     edx, 4; WorkQueueType
0x1400554a9  call    cs:__imp_RxDispatchToWorkerThread
0x1400554b0  nop     dword ptr [rax+rax+00h]
0x1400554b5  test    eax, eax
0x1400554b7  mov     ecx, 103h
0x1400554bc  cmovns  eax, ecx
0x1400554bf  add     rsp, 28h
0x1400554c3  pop     rdi
0x1400554c4  pop     rsi
0x1400554c5  pop     rbp
0x1400554c6  pop     rbx
0x1400554c7  retn
```
