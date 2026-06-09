# std::_Tree_temp_node<std::allocator<std::_Tree_node<ulong,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<ulong,void *>>>(void)

- ea: `0x18000f9a8`
- end: `0x18000f9c4`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011ea1`

## callees

- `0x180001d14`
- `0x18000f9a8`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<unsigned long,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000f9a8  sub     rsp, 28h
0x18000f9ac  mov     rcx, [rcx+8]; Block
0x18000f9b0  test    rcx, rcx
0x18000f9b3  jz      short loc_18000F9BF
0x18000f9b5  mov     edx, 20h ; ' '
0x18000f9ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f9bf  add     rsp, 28h
0x18000f9c3  retn
```
