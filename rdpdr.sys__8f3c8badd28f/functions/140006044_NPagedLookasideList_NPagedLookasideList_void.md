# NPagedLookasideList::~NPagedLookasideList(void)

- ea: `0x140006044`
- end: `0x140006078`
- name: `??1NPagedLookasideList@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(NPagedLookasideList *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400060c0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000605b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000605b`

## pseudocode

```c
void __fastcall NPagedLookasideList::~NPagedLookasideList(NPagedLookasideList *this)
{
  *(_QWORD *)this = &NPagedLookasideList::`vftable';
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)this + 64));
  *(_QWORD *)this = &TopObj::`vftable';
}

```

## disassembly

```asm
0x140006044  push    rbx
0x140006046  sub     rsp, 20h
0x14000604a  lea     rax, ??_7NPagedLookasideList@@6B@; const NPagedLookasideList::`vftable'
0x140006051  mov     rbx, rcx
0x140006054  mov     [rcx], rax
0x140006057  add     rcx, 40h ; '@'; Lookaside
0x14000605b  call    cs:__imp_ExDeleteNPagedLookasideList
0x140006062  nop     dword ptr [rax+rax+00h]
0x140006067  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x14000606e  mov     [rbx], rax
0x140006071  add     rsp, 20h
0x140006075  pop     rbx
0x140006076  retn
```
