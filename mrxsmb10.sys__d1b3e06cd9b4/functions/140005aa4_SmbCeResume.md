# SmbCeResume

- ea: `0x140005aa4`
- end: `0x140005b1a`
- name: `SmbCeResume`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003450`
- `0x140005640`
- `0x140009340`
- `0x14000bfc0`
- `0x14000cd04`
- `0x14000e3e0`
- `0x140011280`
- `0x14004b5f0`

## callees

- `0x140005aa4`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140005ac0`
- `ntoskrnl!KeSetEvent` at `0x140005ac0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005ace`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005ace`
- `rdbss!RxDispatchToWorkerThread` at `0x140005af8`
- `rdbss!RxDispatchToWorkerThread` at `0x140005af8`
- `mrxsmb!MRxSmbDeviceObject` at `0x140005aec`

## pseudocode

```c
NTSTATUS __fastcall SmbCeResume(__int64 a1)
{
  if ( (*(_DWORD *)a1 & 1) == 0 )
    return KeSetEvent((PRKEVENT)(a1 + 16), 0, 0);
  if ( KeGetCurrentIrql() < 2u )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 8));
  return RxDispatchToWorkerThread(
           MRxSmbDeviceObject,
           CriticalWorkQueue,
           *(PRX_WORKERTHREAD_ROUTINE *)(a1 + 16),
           *(PVOID *)(a1 + 8));
}

```

## disassembly

```asm
0x140005aa4  mov     [rsp+arg_0], rbx
0x140005aa9  push    rdi
0x140005aaa  sub     rsp, 20h
0x140005aae  mov     eax, [rcx]
0x140005ab0  mov     rbx, rcx
0x140005ab3  test    al, 1
0x140005ab5  jnz     short loc_140005ACE
0x140005ab7  xor     r8d, r8d; Wait
0x140005aba  xor     edx, edx; Increment
0x140005abc  add     rcx, 10h; Event
0x140005ac0  call    cs:__imp_KeSetEvent
0x140005ac7  nop     dword ptr [rax+rax+00h]
0x140005acc  jmp     short loc_140005B0E
0x140005ace  call    cs:__imp_KeGetCurrentIrql
0x140005ad5  nop     dword ptr [rax+rax+00h]
0x140005ada  mov     rcx, [rbx+8]
0x140005ade  mov     rdx, [rbx+10h]
0x140005ae2  cmp     al, 2
0x140005ae4  jb      short loc_140005B06
0x140005ae6  mov     r9, rcx; pContext
0x140005ae9  mov     r8, rdx; Routine
0x140005aec  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140005af3  xor     edx, edx; WorkQueueType
0x140005af5  mov     rcx, [rcx]; pMRxDeviceObject
0x140005af8  call    cs:__imp_RxDispatchToWorkerThread
0x140005aff  nop     dword ptr [rax+rax+00h]
0x140005b04  jmp     short loc_140005B0E
0x140005b06  mov     rax, rdx
0x140005b09  call    _guard_dispatch_icall
0x140005b0e  mov     rbx, [rsp+28h+arg_0]
0x140005b13  add     rsp, 20h
0x140005b17  pop     rdi
0x140005b18  retn
```
