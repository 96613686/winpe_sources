# VmbusTlLoopbackInitLookAsideList

- ea: `0x140006220`
- end: `0x140006259`
- name: `VmbusTlLoopbackInitLookAsideList`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140023b40`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140006247`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140006247`

## pseudocode

```c
void __fastcall VmbusTlLoopbackInitLookAsideList(struct _NPAGED_LOOKASIDE_LIST *a1)
{
  ExInitializeNPagedLookasideList(a1, 0, 0, 0x200u, 0x90u, 0x69706E56u, 0);
}

```

## disassembly

```asm
0x140006220  sub     rsp, 48h
0x140006224  xor     eax, eax
0x140006226  mov     r9d, 200h; Flags
0x14000622c  mov     [rsp+48h+Depth], ax; Depth
0x140006231  xor     r8d, r8d; Free
0x140006234  mov     [rsp+48h+Tag], 69706E56h; Tag
0x14000623c  xor     edx, edx; Allocate
0x14000623e  mov     [rsp+48h+Size], 90h; Size
0x140006247  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000624e  nop     dword ptr [rax+rax+00h]
0x140006253  add     rsp, 48h
0x140006257  retn
```
