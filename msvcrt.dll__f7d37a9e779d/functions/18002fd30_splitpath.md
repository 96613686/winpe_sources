# _splitpath

- ea: `0x18002fd30`
- end: `0x18002fdb8`
- name: `_splitpath`
- size: `136`
- prototype: `void __cdecl(const char *FullPath, char *Drive, char *Dir, char *Filename, char *Ext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002fdc0`

## pseudocode

```c
void __cdecl splitpath(const char *FullPath, char *Drive, char *Dir, char *Filename, char *Ext)
{
  splitpath_helper(
    (unsigned __int8 *)FullPath,
    (unsigned __int8 *)Drive,
    Drive != 0 ? 3 : 0,
    (unsigned __int8 *)Dir,
    -(__int64)(Dir != 0) & 0x100,
    (unsigned __int8 *)Filename,
    -(__int64)(Filename != 0) & 0x100,
    (unsigned __int8 *)Ext,
    -(__int64)(Ext != 0) & 0x100);
}

```

## disassembly

```asm
0x18002fd30  mov     [rsp+arg_0], rbx
0x18002fd35  mov     [rsp+arg_8], rsi
0x18002fd3a  push    rdi
0x18002fd3b  sub     rsp, 50h
0x18002fd3f  mov     rbx, [rsp+58h+Ext]
0x18002fd47  mov     rdi, r8
0x18002fd4a  mov     rsi, rdx
0x18002fd4d  mov     r8d, 100h
0x18002fd53  mov     rax, rbx
0x18002fd56  neg     rax
0x18002fd59  mov     rax, r9
0x18002fd5c  sbb     r11, r11
0x18002fd5f  and     r11, r8
0x18002fd62  neg     rax
0x18002fd65  mov     [rsp+58h+var_18], r11; __int64
0x18002fd6a  mov     [rsp+58h+var_20], rbx; unsigned __int8 *
0x18002fd6f  mov     rax, rdi
0x18002fd72  sbb     r10, r10
0x18002fd75  and     r10, r8
0x18002fd78  neg     rax
0x18002fd7b  mov     [rsp+58h+var_28], r10; __int64
0x18002fd80  mov     [rsp+58h+var_30], r9; unsigned __int8 *
0x18002fd85  mov     rax, rsi
0x18002fd88  sbb     rdx, rdx
0x18002fd8b  mov     r9, rdi
0x18002fd8e  and     rdx, r8
0x18002fd91  neg     rax
0x18002fd94  mov     [rsp+58h+var_38], rdx; __int64
0x18002fd99  mov     rdx, rsi; Dst
0x18002fd9c  sbb     r8, r8
0x18002fd9f  and     r8d, 3
0x18002fda3  call    _splitpath_helper
0x18002fda8  mov     rbx, [rsp+58h+arg_0]
0x18002fdad  mov     rsi, [rsp+58h+arg_8]
0x18002fdb2  add     rsp, 50h
0x18002fdb6  pop     rdi
0x18002fdb7  retn
```
