# _CreateCDirectMusicSynthPort_::_1_::dtor$0

- ea: `0x180021acd`
- end: `0x180021aea`
- name: `_CreateCDirectMusicSynthPort_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800012c4`

## pseudocode

```c
void __fastcall CreateCDirectMusicSynthPort_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x180021acd  push    rbp
0x180021acf  sub     rsp, 20h
0x180021ad3  mov     rbp, rdx
0x180021ad6  mov     edx, 340h; unsigned __int64
0x180021adb  mov     rcx, [rbp+40h]; void *
0x180021adf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021ae4  add     rsp, 20h
0x180021ae8  pop     rbp
0x180021ae9  retn
```
