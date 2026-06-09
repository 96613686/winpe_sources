# CDynamicCountedObjectArray::CDynamicCountedObjectArray(void)

- ea: `0x1800059f4`
- end: `0x180005a0f`
- name: `??0CDynamicCountedObjectArray@@QEAA@XZ`
- size: `27`
- prototype: `CDynamicCountedObjectArray *__fastcall(CDynamicCountedObjectArray *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800079f4`
- `0x1800082bc`
- `0x1800086b8`
- `0x180008ce0`

## callees

- `0x1800059cc`

## pseudocode

```c
CDynamicCountedObjectArray *__fastcall CDynamicCountedObjectArray::CDynamicCountedObjectArray(
        CDynamicCountedObjectArray *this,
        unsigned __int64 a2)
{
  CDynamicCountedObjectArray *v2; // rcx
  CDynamicCountedObjectArray *result; // rax

  CDynamicArray::CDynamicArray(this, a2);
  result = v2;
  *(_QWORD *)v2 = &CDynamicCountedObjectArray::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800059f4  sub     rsp, 28h
0x1800059f8  call    ??0CDynamicArray@@QEAA@_K@Z; CDynamicArray::CDynamicArray(unsigned __int64)
0x1800059fd  lea     rdx, ??_7CDynamicCountedObjectArray@@6B@; const CDynamicCountedObjectArray::`vftable'
0x180005a04  mov     rax, rcx
0x180005a07  mov     [rcx], rdx
0x180005a0a  add     rsp, 28h
0x180005a0e  retn
```
