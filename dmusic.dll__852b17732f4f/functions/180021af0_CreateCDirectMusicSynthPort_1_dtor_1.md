# _CreateCDirectMusicSynthPort_::_1_::dtor$1

- ea: `0x180021af0`
- end: `0x180021b0d`
- name: `_CreateCDirectMusicSynthPort_::_1_::dtor$1`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800012c4`

## pseudocode

```c
void __fastcall CreateCDirectMusicSynthPort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180021af0  push    rbp
0x180021af2  sub     rsp, 20h
0x180021af6  mov     rbp, rdx
0x180021af9  mov     edx, 368h; unsigned __int64
0x180021afe  mov     rcx, [rbp+40h]; void *
0x180021b02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021b07  add     rsp, 20h
0x180021b0b  pop     rbp
0x180021b0c  retn
```
