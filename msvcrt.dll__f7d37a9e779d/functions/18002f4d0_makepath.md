# _makepath

- ea: `0x18002f4d0`
- end: `0x18002f4f7`
- name: `_makepath`
- size: `39`
- prototype: `void __cdecl(char *Buffer, const char *Drive, const char *Dir, const char *Filename, const char *Ext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002f500`

## pseudocode

```c
void __cdecl makepath(char *Buffer, const char *Drive, const char *Dir, const char *Filename, const char *Ext)
{
  makepath_s(Buffer, 0xFFFFFFFFFFFFFFFFuLL, Drive, Dir, Filename, Ext);
}

```

## disassembly

```asm
0x18002f4d0  sub     rsp, 38h
0x18002f4d4  mov     rax, [rsp+38h+Ext]
0x18002f4d9  mov     [rsp+38h+var_10], rax; Ext
0x18002f4de  mov     [rsp+38h+Filename], r9; Filename
0x18002f4e3  mov     r9, r8; Dir
0x18002f4e6  mov     r8, rdx; Drive
0x18002f4e9  or      rdx, 0FFFFFFFFFFFFFFFFh; BufferCount
0x18002f4ed  call    _makepath_s
0x18002f4f2  add     rsp, 38h
0x18002f4f6  retn
```
