# operator delete(void *,uint)

- ea: `0x100358c5`
- end: `0x100358d5`
- name: `??3@YAXPAXI@Z`
- size: `16`
- prototype: `void __cdecl(void *, unsigned int)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1001b2f0`
- `0x1001bbd0`
- `0x1001eca0`
- `0x1001f3d0`
- `0x1001f420`
- `0x1001f550`
- `0x1001f5a0`
- `0x1001f730`
- `0x1001f760`
- `0x1001fa20`
- `0x1001fe30`
- `0x100203a0`
- `0x10020680`
- `0x10020780`
- `0x10020e70`
- `0x10022090`
- `0x10022160`
- `0x10022240`

## callees

- `0x1001eba0`

## pseudocode

```c
void __cdecl operator delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x100358c5  mov     edi, edi
0x100358c7  push    ebp
0x100358c8  mov     ebp, esp
0x100358ca  push    [ebp+arg_0]; void *
0x100358cd  call    ??3@YAXPAX@Z; operator delete(void *)
0x100358d2  pop     ecx
0x100358d3  pop     ebp
0x100358d4  retn
```
