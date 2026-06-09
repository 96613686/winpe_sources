# _InitializeConfigurationOnce_::_1_::dtor$0

- ea: `0x1800157c9`
- end: `0x1800157e6`
- name: `_InitializeConfigurationOnce_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180001bb4`

## pseudocode

```c
void __fastcall InitializeConfigurationOnce_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x1800157c9  push    rbp
0x1800157cb  sub     rsp, 20h
0x1800157cf  mov     rbp, rdx
0x1800157d2  mov     edx, 10h
0x1800157d7  mov     rcx, [rbp+30h]; Block
0x1800157db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800157e0  add     rsp, 20h
0x1800157e4  pop     rbp
0x1800157e5  retn
```
