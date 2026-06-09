# LsnCreate

- ea: `0x1800149e0`
- end: `0x180014a10`
- name: `LsnCreate`
- size: `48`
- prototype: `CLFS_LSN __stdcall(CLFS_CONTAINER_ID cidContainer, ULONG offBlock, ULONG cRecord)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800149e0`

## pseudocode

```c
CLFS_LSN __stdcall LsnCreate(CLFS_CONTAINER_ID cidContainer, ULONG offBlock, ULONG cRecord)
{
  if ( cidContainer == -1 || (offBlock & 0x1FF) != 0 || (cRecord & 0xFFFFFE00) != 0 )
    return CLFS_LSN_INVALID;
  else
    return (CLFS_LSN)__PAIR64__(cidContainer, cRecord | offBlock);
}

```

## disassembly

```asm
0x1800149e0  cmp     ecx, 0FFFFFFFFh
0x1800149e3  jz      short loc_180014A08
0x1800149e5  test    edx, 1FFh
0x1800149eb  jnz     short loc_180014A08
0x1800149ed  test    r8d, 0FFFFFE00h
0x1800149f4  jnz     short loc_180014A08
0x1800149f6  or      edx, r8d
0x1800149f9  mov     dword ptr [rsp+arg_18+4], ecx
0x1800149fd  mov     dword ptr [rsp+arg_18], edx
0x180014a01  mov     rax, [rsp+arg_18]
0x180014a06  retn
0x180014a08  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180014a0f  retn
```
