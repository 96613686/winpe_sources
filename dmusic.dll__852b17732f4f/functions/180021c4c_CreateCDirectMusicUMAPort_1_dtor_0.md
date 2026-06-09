# _CreateCDirectMusicUMAPort_::_1_::dtor$0

- ea: `0x180021c4c`
- end: `0x180021c69`
- name: `_CreateCDirectMusicUMAPort_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800012c4`

## pseudocode

```c
void __fastcall CreateCDirectMusicUMAPort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x180021c4c  push    rbp
0x180021c4e  sub     rsp, 20h
0x180021c52  mov     rbp, rdx
0x180021c55  mov     edx, 8B10h; unsigned __int64
0x180021c5a  mov     rcx, [rbp+28h]; void *
0x180021c5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021c63  add     rsp, 20h
0x180021c67  pop     rbp
0x180021c68  retn
```
