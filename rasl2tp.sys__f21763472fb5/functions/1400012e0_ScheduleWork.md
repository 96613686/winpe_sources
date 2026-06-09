# ScheduleWork

- ea: `0x1400012e0`
- end: `0x140001352`
- name: `ScheduleWork`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ce0`
- `0x1400023b0`
- `0x140002ce0`
- `0x140019810`
- `0x140019a80`
- `0x14001af80`
- `0x14001c050`

## callees

- `0x1400012e0`

## import_xrefs

- `NDIS!NdisQueueIoWorkItem` at `0x14000131d`
- `NDIS!NdisQueueIoWorkItem` at `0x14000131d`
- `NDIS!NdisAllocateIoWorkItem` at `0x1400012ff`
- `NDIS!NdisAllocateIoWorkItem` at `0x1400012ff`

## pseudocode

```c
__int64 __fastcall ScheduleWork(__int64 a1, NDIS_IO_WORKITEM_FUNCTION *a2, void *a3)
{
  NDIS_HANDLE IoWorkItem; // rax

  IoWorkItem = NdisAllocateIoWorkItem(*(NDIS_HANDLE *)(a1 + 328));
  if ( !IoWorkItem )
    return 3221225626LL;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  NdisQueueIoWorkItem(IoWorkItem, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x1400012e0  mov     [rsp+arg_0], rbx
0x1400012e5  mov     [rsp+arg_8], rsi
0x1400012ea  push    rdi
0x1400012eb  sub     rsp, 20h
0x1400012ef  mov     rbx, rcx
0x1400012f2  mov     rdi, r8
0x1400012f5  mov     rcx, [rcx+148h]; NdisObjectHandle
0x1400012fc  mov     rsi, rdx
0x1400012ff  call    cs:__imp_NdisAllocateIoWorkItem
0x140001306  nop     dword ptr [rax+rax+00h]
0x14000130b  test    rax, rax
0x14000130e  jz      short loc_14000133C
0x140001310  lock inc dword ptr [rbx+4]
0x140001314  mov     r8, rdi; WorkItemContext
0x140001317  mov     rdx, rsi; Routine
0x14000131a  mov     rcx, rax; NdisIoWorkItemHandle
0x14000131d  call    cs:__imp_NdisQueueIoWorkItem
0x140001324  nop     dword ptr [rax+rax+00h]
0x140001329  xor     eax, eax
0x14000132b  mov     rbx, [rsp+28h+arg_0]
0x140001330  mov     rsi, [rsp+28h+arg_8]
0x140001335  add     rsp, 20h
0x140001339  pop     rdi
0x14000133a  retn
0x14000133c  mov     rbx, [rsp+28h+arg_0]
0x140001341  mov     eax, 0C000009Ah
0x140001346  mov     rsi, [rsp+28h+arg_8]
0x14000134b  add     rsp, 20h
0x14000134f  pop     rdi
0x140001350  retn
```
