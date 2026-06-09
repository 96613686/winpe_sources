# _CreateCDirectMusicEmulatePort_::_1_::dtor$1

- ea: `0x180021b9e`
- end: `0x180021bbb`
- name: `_CreateCDirectMusicEmulatePort_::_1_::dtor$1`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800012c4`

## pseudocode

```c
void __fastcall CreateCDirectMusicEmulatePort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180021b9e  push    rbp
0x180021ba0  sub     rsp, 20h
0x180021ba4  mov     rbp, rdx
0x180021ba7  mov     edx, 86B8h; unsigned __int64
0x180021bac  mov     rcx, [rbp+40h]; void *
0x180021bb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021bb5  add     rsp, 20h
0x180021bb9  pop     rbp
0x180021bba  retn
```
