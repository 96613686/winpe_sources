# COMPRESSION_CONTEXT::QueryBytesAvailable(void)

- ea: `0x1800069a0`
- end: `0x1800069bb`
- name: `?QueryBytesAvailable@COMPRESSION_CONTEXT@@QEAAKXZ`
- size: `27`
- prototype: `__int64 __fastcall(COMPRESSION_CONTEXT *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000674c`

## callees

- `0x1800069a0`

## pseudocode

```c
__int64 __fastcall COMPRESSION_CONTEXT::QueryBytesAvailable(COMPRESSION_CONTEXT *this)
{
  if ( *((_DWORD *)this + 28) )
    return *(unsigned int *)(*((_QWORD *)this + 13) + 16LL);
  else
    return (unsigned int)(*((_DWORD *)this + 35) - *((_DWORD *)this + 34));
}

```

## disassembly

```asm
0x1800069a0  cmp     dword ptr [rcx+70h], 0
0x1800069a4  jz      short loc_1800069AE
0x1800069a6  mov     rax, [rcx+68h]
0x1800069aa  mov     eax, [rax+10h]
0x1800069ad  retn
0x1800069ae  mov     eax, [rcx+8Ch]
0x1800069b4  sub     eax, [rcx+88h]
0x1800069ba  retn
```
