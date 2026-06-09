# CDpUrlAccessor::IsDirectory(void)

- ea: `0x180003730`
- end: `0x180003736`
- name: `?IsDirectory@CDpUrlAccessor@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CDpUrlAccessor *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::IsDirectory(CDpUrlAccessor *this)
{
  return 1;
}

```

## disassembly

```asm
0x180003730  mov     eax, 1
0x180003735  retn
```
