# CDynamicCountedObjectArray::Get(ulong)

- ea: `0x180005d04`
- end: `0x180005d2d`
- name: `?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z`
- size: `41`
- prototype: `struct CCountedObject *(CDynamicCountedObjectArray *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007b74`
- `0x180007c2c`
- `0x180007d0c`
- `0x1800084c8`
- `0x1800086b8`
- `0x180008fb4`
- `0x180009944`

## callees

- `0x180005cc4`

## pseudocode

```c
struct CCountedObject *__fastcall CDynamicCountedObjectArray::Get(CDynamicCountedObjectArray *this, unsigned int a2)
{
  int v2; // eax
  __int64 v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  v2 = CDynamicArray::Get(this, &v4, a2);
  return (struct CCountedObject *)(v4 & -(__int64)(v2 != 0));
}

```

## disassembly

```asm
0x180005d04  sub     rsp, 28h
0x180005d08  mov     r8d, edx; unsigned int
0x180005d0b  mov     [rsp+28h+arg_10], 0
0x180005d14  lea     rdx, [rsp+28h+arg_10]; void *
0x180005d19  call    ?Get@CDynamicArray@@QEBAHPEAXK@Z; CDynamicArray::Get(void *,ulong)
0x180005d1e  neg     eax
0x180005d20  sbb     rax, rax
0x180005d23  and     rax, [rsp+28h+arg_10]
0x180005d28  add     rsp, 28h
0x180005d2c  retn
```
