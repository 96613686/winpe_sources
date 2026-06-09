# BthServicePolicyEnabled

- ea: `0x14001f2ac`
- end: `0x14001f2ed`
- name: `BthServicePolicyEnabled`
- size: `65`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x140006f68`
- `0x1400079c0`
- `0x14001f210`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f2b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f2b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f2d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f2d8`

## pseudocode

```c
bool BthServicePolicyEnabled()
{
  KIRQL v0; // al
  bool v1; // bl

  v0 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
  v1 = dword_14002D24C != 0;
  KeReleaseSpinLock(&g_PolicyLock, v0);
  return v1;
}

```

## disassembly

```asm
0x14001f2ac  push    rbx
0x14001f2ae  sub     rsp, 20h
0x14001f2b2  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f2b9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f2c0  nop     dword ptr [rax+rax+00h]
0x14001f2c5  cmp     cs:dword_14002D24C, 0
0x14001f2cc  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f2d3  mov     dl, al; NewIrql
0x14001f2d5  setnz   bl
0x14001f2d8  call    cs:__imp_KeReleaseSpinLock
0x14001f2df  nop     dword ptr [rax+rax+00h]
0x14001f2e4  mov     al, bl
0x14001f2e6  add     rsp, 20h
0x14001f2ea  pop     rbx
0x14001f2eb  retn
```
