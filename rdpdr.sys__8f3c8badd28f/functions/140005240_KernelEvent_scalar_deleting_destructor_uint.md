# KernelEvent::`scalar deleting destructor'(uint)

- ea: `0x140005240`
- end: `0x14000527c`
- name: `??_GKernelEvent@@UEAAPEAXI@Z`
- size: `60`
- prototype: `void *__fastcall(PVOID Entry, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140005240`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005266`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005266`

## pseudocode

```c
_QWORD *__fastcall KernelEvent::`scalar deleting destructor'(_QWORD *Entry, char a2)
{
  *Entry = &TopObj::`vftable';
  if ( (a2 & 1) != 0 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)WPP_MAIN_CB.Dpc.DeferredContext + 64), Entry);
  return Entry;
}

```

## disassembly

```asm
0x140005240  push    rbx
0x140005242  sub     rsp, 20h
0x140005246  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x14000524d  mov     rbx, rcx
0x140005250  mov     [rcx], rax
0x140005253  test    dl, 1
0x140005256  jz      short loc_140005272
0x140005258  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext
0x14000525f  mov     rdx, rbx; Entry
0x140005262  add     rcx, 40h ; '@'; Lookaside
0x140005266  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000526d  nop     dword ptr [rax+rax+00h]
0x140005272  mov     rax, rbx
0x140005275  add     rsp, 20h
0x140005279  pop     rbx
0x14000527a  retn
```
