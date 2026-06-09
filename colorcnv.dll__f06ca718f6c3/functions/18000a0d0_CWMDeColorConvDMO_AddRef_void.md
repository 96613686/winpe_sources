# CWMDeColorConvDMO::AddRef(void)

- ea: `0x18000a0d0`
- end: `0x18000a0e3`
- name: `?AddRef@CWMDeColorConvDMO@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMDeColorConvDMO *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c030`
- `0x18000c050`
- `0x18000c070`
- `0x18000c090`
- `0x18000c0b0`

## callees

- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::AddRef(CWMDeColorConvDMO *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 8LL))(*((_QWORD *)this + 54));
}

```

## disassembly

```asm
0x18000a0d0  mov     rcx, [rcx+1B0h]
0x18000a0d7  mov     rax, [rcx]
0x18000a0da  mov     rax, [rax+8]
0x18000a0de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
