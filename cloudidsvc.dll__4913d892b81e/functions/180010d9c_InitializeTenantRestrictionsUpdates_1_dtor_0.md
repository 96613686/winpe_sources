# _InitializeTenantRestrictionsUpdates_::_1_::dtor$0

- ea: `0x180010d9c`
- end: `0x180010db9`
- name: `_InitializeTenantRestrictionsUpdates_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callees

- `0x180001a74`

## pseudocode

```c
void __fastcall InitializeTenantRestrictionsUpdates_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x180010d9c  push    rbp
0x180010d9e  sub     rsp, 20h
0x180010da2  mov     rbp, rdx
0x180010da5  mov     edx, 0D8h; unsigned __int64
0x180010daa  mov     rcx, [rbp+50h]; void *
0x180010dae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010db3  add     rsp, 20h
0x180010db7  pop     rbp
0x180010db8  retn
```
