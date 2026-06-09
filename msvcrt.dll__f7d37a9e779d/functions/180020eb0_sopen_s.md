# _sopen_s

- ea: `0x180020eb0`
- end: `0x180020ee2`
- name: `_sopen_s`
- size: `50`
- prototype: `errno_t __cdecl(int *FileHandle, const char *FileName, int OpenFlag, int ShareFlag, int PermissionMode)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e6c0`
- `0x180052478`
- `0x180059844`
- `0x180065be0`
- `0x180065eb0`

## callees

- `0x180020dc4`

## pseudocode

```c
errno_t __cdecl sopen_s(int *FileHandle, const char *FileName, int OpenFlag, int ShareFlag, int PermissionMode)
{
  return sopen_helper(FileName, OpenFlag, ShareFlag, PermissionMode, FileHandle, 1);
}

```

## disassembly

```asm
0x180020eb0  sub     rsp, 38h
0x180020eb4  mov     eax, r9d
0x180020eb7  mov     [rsp+38h+var_10], 1
0x180020ebf  mov     r9d, [rsp+38h+PermissionMode]
0x180020ec4  mov     r10d, r8d
0x180020ec7  mov     r11, rdx
0x180020eca  mov     [rsp+38h+var_18], rcx
0x180020ecf  mov     r8d, eax
0x180020ed2  mov     edx, r10d
0x180020ed5  mov     rcx, r11
0x180020ed8  call    _sopen_helper
0x180020edd  add     rsp, 38h
0x180020ee1  retn
```
