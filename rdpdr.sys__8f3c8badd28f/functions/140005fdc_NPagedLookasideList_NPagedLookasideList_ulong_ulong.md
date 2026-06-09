# NPagedLookasideList::NPagedLookasideList(ulong,ulong)

- ea: `0x140005fdc`
- end: `0x14000603b`
- name: `??0NPagedLookasideList@@QEAA@KK@Z`
- size: `95`
- prototype: `NPagedLookasideList *(NPagedLookasideList *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400061e0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140006025`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140006025`
- `ntoskrnl!ExFreePool` at `0x140006007`

## pseudocode

```c
NPagedLookasideList *__fastcall NPagedLookasideList::NPagedLookasideList(
        NPagedLookasideList *this,
        unsigned int a2,
        ULONG Tag)
{
  *(_QWORD *)this = &NPagedLookasideList::`vftable';
  *((_BYTE *)this + 8) = 1;
  *((_DWORD *)this + 3) = 0;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)((char *)this + 64),
    TopObj::ExAllocatePool2Adapter,
    ExFreePool,
    0x200u,
    a2,
    Tag,
    0);
  return this;
}

```

## disassembly

```asm
0x140005fdc  push    rbx
0x140005fde  sub     rsp, 40h
0x140005fe2  lea     rax, ??_7NPagedLookasideList@@6B@; const NPagedLookasideList::`vftable'
0x140005fe9  mov     edx, edx
0x140005feb  mov     [rcx], rax
0x140005fee  mov     rbx, rcx
0x140005ff1  xor     eax, eax
0x140005ff3  mov     byte ptr [rcx+8], 1
0x140005ff7  mov     [rsp+48h+Depth], ax; Depth
0x140005ffc  mov     r9d, 200h; Flags
0x140006002  mov     [rsp+48h+Tag], r8d; Tag
0x140006007  mov     r8, cs:__imp_ExFreePool; Free
0x14000600e  mov     [rsp+48h+Size], rdx; Size
0x140006013  lea     rdx, ?ExAllocatePool2Adapter@TopObj@@KAPEAXW4_POOL_TYPE@@_KK@Z; Allocate
0x14000601a  mov     dword ptr [rcx+0Ch], 0
0x140006021  add     rcx, 40h ; '@'; Lookaside
0x140006025  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000602c  nop     dword ptr [rax+rax+00h]
0x140006031  mov     rax, rbx
0x140006034  add     rsp, 40h
0x140006038  pop     rbx
0x140006039  retn
```
