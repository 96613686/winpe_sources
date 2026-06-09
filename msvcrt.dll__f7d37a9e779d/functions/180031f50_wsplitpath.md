# _wsplitpath

- ea: `0x180031f50`
- end: `0x180031fd8`
- name: `_wsplitpath`
- size: `136`
- prototype: `void __cdecl(const wchar_t *FullPath, wchar_t *Drive, wchar_t *Dir, wchar_t *Filename, wchar_t *Ext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031fe0`

## pseudocode

```c
void __cdecl wsplitpath(const wchar_t *FullPath, wchar_t *Drive, wchar_t *Dir, wchar_t *Filename, wchar_t *Ext)
{
  wsplitpath_helper(
    (wchar_t *)FullPath,
    Drive,
    Drive != 0 ? 3 : 0,
    Dir,
    -(__int64)(Dir != 0) & 0x100,
    Filename,
    -(__int64)(Filename != 0) & 0x100,
    Ext,
    -(__int64)(Ext != 0) & 0x100);
}

```

## disassembly

```asm
0x180031f50  mov     [rsp+arg_0], rbx
0x180031f55  mov     [rsp+arg_8], rsi
0x180031f5a  push    rdi
0x180031f5b  sub     rsp, 50h
0x180031f5f  mov     rbx, [rsp+58h+Ext]
0x180031f67  mov     rdi, r8
0x180031f6a  mov     rsi, rdx
0x180031f6d  mov     r8d, 100h
0x180031f73  mov     rax, rbx
0x180031f76  neg     rax
0x180031f79  mov     rax, r9
0x180031f7c  sbb     r11, r11
0x180031f7f  and     r11, r8
0x180031f82  neg     rax
0x180031f85  mov     [rsp+58h+var_18], r11; __int64
0x180031f8a  mov     [rsp+58h+var_20], rbx; wchar_t *
0x180031f8f  mov     rax, rdi
0x180031f92  sbb     r10, r10
0x180031f95  and     r10, r8
0x180031f98  neg     rax
0x180031f9b  mov     [rsp+58h+var_28], r10; __int64
0x180031fa0  mov     [rsp+58h+var_30], r9; wchar_t *
0x180031fa5  mov     rax, rsi
0x180031fa8  sbb     rdx, rdx
0x180031fab  mov     r9, rdi
0x180031fae  and     rdx, r8
0x180031fb1  neg     rax
0x180031fb4  mov     [rsp+58h+var_38], rdx; __int64
0x180031fb9  mov     rdx, rsi; Destination
0x180031fbc  sbb     r8, r8
0x180031fbf  and     r8d, 3
0x180031fc3  call    _wsplitpath_helper
0x180031fc8  mov     rbx, [rsp+58h+arg_0]
0x180031fcd  mov     rsi, [rsp+58h+arg_8]
0x180031fd2  add     rsp, 50h
0x180031fd6  pop     rdi
0x180031fd7  retn
```
