# _DllForwarder::DllForwarder_::_1_::dtor$5

- ea: `0x18000daeb`
- end: `0x18000db08`
- name: `_DllForwarder::DllForwarder_::_1_::dtor$5`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180001f70`

## pseudocode

```c
void __fastcall DllForwarder::DllForwarder_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000daeb  push    rbp
0x18000daed  sub     rsp, 20h
0x18000daf1  mov     rbp, rdx
0x18000daf4  mov     edx, 10h; unsigned __int64
0x18000daf9  mov     rcx, [rbp+28h]; void *
0x18000dafd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000db02  add     rsp, 20h
0x18000db06  pop     rbp
0x18000db07  retn
```
