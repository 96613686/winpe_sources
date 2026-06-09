# CWMDeColorConvDMO::Release(void)

- ea: `0x1800095d0`
- end: `0x1800095e3`
- name: `?Release@CWMDeColorConvDMO@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMDeColorConvDMO *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e060`
- `0x18000e080`
- `0x18000e0a0`
- `0x18000e0c0`
- `0x18000e0e0`

## callees

- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::Release(CWMDeColorConvDMO *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 54) + 16LL))(*((_QWORD *)this + 54));
}

```

## disassembly

```asm
0x1800095d0  mov     rcx, [rcx+1B0h]
0x1800095d7  mov     rax, [rcx]
0x1800095da  mov     rax, [rax+10h]
0x1800095de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
