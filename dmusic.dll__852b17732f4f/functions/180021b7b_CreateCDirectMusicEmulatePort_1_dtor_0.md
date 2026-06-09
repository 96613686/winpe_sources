# _CreateCDirectMusicEmulatePort_::_1_::dtor$0

- ea: `0x180021b7b`
- end: `0x180021b98`
- name: `_CreateCDirectMusicEmulatePort_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800012c4`

## pseudocode

```c
void __fastcall CreateCDirectMusicEmulatePort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180021b7b  push    rbp
0x180021b7d  sub     rsp, 20h
0x180021b81  mov     rbp, rdx
0x180021b84  mov     edx, 1E8h; unsigned __int64
0x180021b89  mov     rcx, [rbp+40h]; void *
0x180021b8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021b92  add     rsp, 20h
0x180021b96  pop     rbp
0x180021b97  retn
```
