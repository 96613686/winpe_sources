# COMPRESSION_CONTEXT::QueryBytePtr(void)

- ea: `0x180002ef0`
- end: `0x180002f0d`
- name: `?QueryBytePtr@COMPRESSION_CONTEXT@@QEAAPEAEXZ`
- size: `29`
- prototype: `unsigned __int8 *__fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002820`
- `0x180006588`
- `0x18000664c`

## callees

- `0x180002ef0`

## pseudocode

```c
unsigned __int8 *__fastcall COMPRESSION_CONTEXT::QueryBytePtr(COMPRESSION_CONTEXT *this)
{
  if ( *((_DWORD *)this + 28) )
    return *(unsigned __int8 **)(*((_QWORD *)this + 13) + 8LL);
  else
    return (unsigned __int8 *)(*((_QWORD *)this + 16) + *((unsigned int *)this + 34));
}

```

## disassembly

```asm
0x180002ef0  cmp     dword ptr [rcx+70h], 0
0x180002ef4  jz      short loc_180002EFF
0x180002ef6  mov     rax, [rcx+68h]
0x180002efa  mov     rax, [rax+8]
0x180002efe  retn
0x180002eff  mov     eax, [rcx+88h]
0x180002f05  add     rax, [rcx+80h]
0x180002f0c  retn
```
