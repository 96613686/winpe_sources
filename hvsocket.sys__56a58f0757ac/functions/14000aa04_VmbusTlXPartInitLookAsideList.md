# VmbusTlXPartInitLookAsideList

- ea: `0x14000aa04`
- end: `0x14000aa3d`
- name: `VmbusTlXPartInitLookAsideList`
- size: `57`
- prototype: `void __fastcall(struct _NPAGED_LOOKASIDE_LIST *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140023b40`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000aa2b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000aa2b`

## pseudocode

```c
void __fastcall VmbusTlXPartInitLookAsideList(struct _NPAGED_LOOKASIDE_LIST *a1)
{
  ExInitializeNPagedLookasideList(a1, 0, 0, 0x200u, 0x88u, 0x69706E56u, 0);
}

```

## disassembly

```asm
0x14000aa04  sub     rsp, 48h
0x14000aa08  xor     eax, eax
0x14000aa0a  mov     r9d, 200h; Flags
0x14000aa10  mov     [rsp+48h+Depth], ax; Depth
0x14000aa15  xor     r8d, r8d; Free
0x14000aa18  mov     [rsp+48h+Tag], 69706E56h; Tag
0x14000aa20  xor     edx, edx; Allocate
0x14000aa22  mov     [rsp+48h+Size], 88h; Size
0x14000aa2b  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000aa32  nop     dword ptr [rax+rax+00h]
0x14000aa37  add     rsp, 48h
0x14000aa3b  retn
```
