# CDynamicArray::GetCount(void)

- ea: `0x180005d34`
- end: `0x180005d38`
- name: `?GetCount@CDynamicArray@@QEBAKXZ`
- size: `4`
- prototype: `__int64 __fastcall(CDynamicArray *this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007b10`
- `0x180007b74`
- `0x180007c2c`
- `0x180007d0c`
- `0x1800083e8`
- `0x1800084c8`
- `0x1800086b8`
- `0x180008970`
- `0x180008fb4`
- `0x180009944`

## pseudocode

```c
__int64 __fastcall CDynamicArray::GetCount(CDynamicArray *this)
{
  return *((unsigned int *)this + 4);
}

```

## disassembly

```asm
0x180005d34  mov     eax, [rcx+10h]
0x180005d37  retn
```
