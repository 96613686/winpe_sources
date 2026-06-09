# NpFsdCleanup

- ea: `0x14000e920`
- end: `0x14000e977`
- name: `NpFsdCleanup`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000e980`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e930`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e930`
- `ntoskrnl!IofCompleteRequest` at `0x14000e95d`
- `ntoskrnl!IofCompleteRequest` at `0x14000e95d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e949`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e949`

## pseudocode

```c
__int64 __fastcall NpFsdCleanup(__int64 a1, IRP *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9

  KeEnterCriticalRegion();
  LODWORD(a1) = NpCommonCleanup(a1, (__int64)a2, v4, v5);
  KeLeaveCriticalRegion();
  a2->IoStatus.Status = a1;
  IofCompleteRequest(a2, 2);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x14000e920  mov     [rsp+arg_0], rbx
0x14000e925  push    rdi
0x14000e926  sub     rsp, 20h
0x14000e92a  mov     rdi, rdx
0x14000e92d  mov     rbx, rcx
0x14000e930  call    cs:__imp_KeEnterCriticalRegion
0x14000e937  nop     dword ptr [rax+rax+00h]
0x14000e93c  mov     rdx, rdi
0x14000e93f  mov     rcx, rbx
0x14000e942  call    NpCommonCleanup
0x14000e947  mov     ebx, eax
0x14000e949  call    cs:__imp_KeLeaveCriticalRegion
0x14000e950  nop     dword ptr [rax+rax+00h]
0x14000e955  mov     dl, 2; PriorityBoost
0x14000e957  mov     [rdi+30h], ebx
0x14000e95a  mov     rcx, rdi; Irp
0x14000e95d  call    cs:__imp_IofCompleteRequest
0x14000e964  nop     dword ptr [rax+rax+00h]
0x14000e969  mov     eax, ebx
0x14000e96b  mov     rbx, [rsp+28h+arg_0]
0x14000e970  add     rsp, 20h
0x14000e974  pop     rdi
0x14000e975  retn
```
