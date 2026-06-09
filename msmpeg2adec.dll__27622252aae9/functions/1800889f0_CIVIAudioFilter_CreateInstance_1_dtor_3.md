# _CIVIAudioFilter::CreateInstance_::_1_::dtor$3

- ea: `0x1800889f0`
- end: `0x180088a0e`
- name: `_CIVIAudioFilter::CreateInstance_::_1_::dtor$3`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001b80`

## pseudocode

```c
void __fastcall CIVIAudioFilter::CreateInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 112));
}

```

## disassembly

```asm
0x1800889f0  push    rbp
0x1800889f2  sub     rsp, 20h
0x1800889f6  mov     rbp, rdx
0x1800889f9  mov     edx, 45B0h
0x1800889fe  mov     rcx, [rbp+70h]; Block
0x180088a02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180088a07  add     rsp, 20h
0x180088a0b  pop     rbp
0x180088a0c  retn
```
