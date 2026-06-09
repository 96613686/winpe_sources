# HvSocketXboxReleaseReceiveIndications

- ea: `0x14000ad20`
- end: `0x14000ad7b`
- name: `HvSocketXboxReleaseReceiveIndications`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ad61`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ad61`

## pseudocode

```c
__int64 __fastcall HvSocketXboxReleaseReceiveIndications(__int64 a1, __int64 a2, _QWORD *a3)
{
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(a1 + 504) + 64LL))(*(_QWORD *)(a2 + 696), a3[9]);
  a3[9] = 0;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 112) + 704LL), a3);
  return 0;
}

```

## disassembly

```asm
0x14000ad20  mov     [rsp+arg_0], rbx
0x14000ad25  push    rdi
0x14000ad26  sub     rsp, 20h
0x14000ad2a  mov     rax, [rcx+1F8h]
0x14000ad31  mov     rbx, rdx
0x14000ad34  mov     rdx, [r8+48h]
0x14000ad38  mov     rdi, r8
0x14000ad3b  mov     rax, [rax+40h]
0x14000ad3f  mov     rcx, [rbx+2B8h]
0x14000ad46  call    _guard_dispatch_icall
0x14000ad4b  mov     qword ptr [rdi+48h], 0
0x14000ad53  mov     rdx, rdi; Entry
0x14000ad56  mov     rcx, [rbx+70h]
0x14000ad5a  add     rcx, 2C0h; Lookaside
0x14000ad61  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000ad68  nop     dword ptr [rax+rax+00h]
0x14000ad6d  mov     rbx, [rsp+28h+arg_0]
0x14000ad72  xor     eax, eax
0x14000ad74  add     rsp, 20h
0x14000ad78  pop     rdi
0x14000ad79  retn
```
