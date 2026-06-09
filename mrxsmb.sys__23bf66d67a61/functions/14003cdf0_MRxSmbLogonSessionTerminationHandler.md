# MRxSmbLogonSessionTerminationHandler

- ea: `0x14003cdf0`
- end: `0x14003ce7e`
- name: `MRxSmbLogonSessionTerminationHandler`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x14003cdf0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003ce13`
- `ntoskrnl!ExAllocatePool2` at `0x14003ce13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce5f`
- `rdbss!RxDispatchToWorkerThread` at `0x14003ce47`
- `rdbss!RxDispatchToWorkerThread` at `0x14003ce47`

## pseudocode

```c
__int64 __fastcall MRxSmbLogonSessionTerminationHandler(_QWORD *a1, __int64 a2)
{
  _QWORD *Pool2; // rax
  void *v5; // rbx

  Pool2 = (_QWORD *)ExAllocatePool2(66, 16, 1834181955);
  v5 = Pool2;
  if ( Pool2 )
  {
    Pool2[1] = *a1;
    *Pool2 = a2;
    if ( RxDispatchToWorkerThread(
           MRxSmbDeviceObject,
           BackgroundWorkQueue,
           MRxSmbLogonSessionTerminationWorkRoutine,
           Pool2) < 0 )
      ExFreePoolWithTag(v5, 0x6D536543u);
  }
  return 0;
}

```

## disassembly

```asm
0x14003cdf0  mov     [rsp+arg_0], rbx
0x14003cdf5  mov     [rsp+arg_8], rsi
0x14003cdfa  push    rdi
0x14003cdfb  sub     rsp, 20h
0x14003cdff  mov     rdi, rdx
0x14003ce02  mov     rsi, rcx
0x14003ce05  mov     edx, 10h
0x14003ce0a  mov     r8d, 6D536543h
0x14003ce10  lea     ecx, [rdx+32h]
0x14003ce13  call    cs:__imp_ExAllocatePool2
0x14003ce1a  nop     dword ptr [rax+rax+00h]
0x14003ce1f  mov     rbx, rax
0x14003ce22  test    rax, rax
0x14003ce25  jz      short loc_14003CE6B
0x14003ce27  mov     rcx, [rsi]
0x14003ce2a  lea     r8, MRxSmbLogonSessionTerminationWorkRoutine; Routine
0x14003ce31  mov     [rax+8], rcx
0x14003ce35  mov     r9, rax; pContext
0x14003ce38  mov     [rax], rdi
0x14003ce3b  mov     edx, 4; WorkQueueType
0x14003ce40  mov     rcx, cs:MRxSmbDeviceObject; pMRxDeviceObject
0x14003ce47  call    cs:__imp_RxDispatchToWorkerThread
0x14003ce4e  nop     dword ptr [rax+rax+00h]
0x14003ce53  test    eax, eax
0x14003ce55  jns     short loc_14003CE6B
0x14003ce57  mov     edx, 6D536543h; Tag
0x14003ce5c  mov     rcx, rbx; P
0x14003ce5f  call    cs:__imp_ExFreePoolWithTag
0x14003ce66  nop     dword ptr [rax+rax+00h]
0x14003ce6b  mov     rbx, [rsp+28h+arg_0]
0x14003ce70  xor     eax, eax
0x14003ce72  mov     rsi, [rsp+28h+arg_8]
0x14003ce77  add     rsp, 20h
0x14003ce7b  pop     rdi
0x14003ce7c  retn
```
