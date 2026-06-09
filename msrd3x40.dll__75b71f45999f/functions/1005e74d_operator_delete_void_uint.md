# operator delete(void *,uint)

- ea: `0x1005e74d`
- end: `0x1005e75d`
- name: `??3@YAXPAXI@Z`
- size: `16`
- prototype: `void __cdecl(void *Block, unsigned int)`
- caller_count: `98`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100085b0`
- `0x10009620`
- `0x1000f230`
- `0x1000f260`
- `0x10012ec0`
- `0x10012f60`
- `0x10013290`
- `0x10018200`
- `0x10018700`
- `0x10019240`
- `0x10019580`
- `0x100195b0`
- `0x10019960`
- `0x10019ca0`
- `0x10019d90`
- `0x1001dc70`
- `0x1001df90`
- `0x1001dfc0`
- `0x1001f780`
- `0x1001f7e0`
- `0x1001f910`
- `0x1001fdb0`
- `0x10021720`
- `0x10026200`
- `0x10027b40`
- `0x10027d30`
- `0x1002eec0`
- `0x1002f160`
- `0x10030600`
- `0x10031a90`
- `0x10031c70`
- `0x100338b0`
- `0x10033a50`
- `0x10034160`
- `0x10034bd0`
- `0x10035650`
- `0x10035910`
- `0x10035e10`
- `0x10035f50`
- `0x10036620`
- `0x10036910`
- `0x100374c0`
- `0x10037bb0`
- `0x1003a360`
- `0x1003a3c0`
- `0x1003a400`
- `0x1003a430`
- `0x1003a620`
- `0x1003ab80`
- `0x1003bac0`

## callees

- `0x1005ef05`

## pseudocode

```c
void __cdecl operator delete(void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1005e74d  mov     edi, edi
0x1005e74f  push    ebp
0x1005e750  mov     ebp, esp
0x1005e752  push    [ebp+Block]; Block
0x1005e755  call    ??3@YAXPAX@Z; operator delete(void *)
0x1005e75a  pop     ecx
0x1005e75b  pop     ebp
0x1005e75c  retn
```
