# CADMCOMW::CImpExpHelp::Release(void)

- ea: `0x18000e960`
- end: `0x18000e970`
- name: `?Release@CImpExpHelp@CADMCOMW@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CADMCOMW::CImpExpHelp *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpExpHelp::Release(CADMCOMW::CImpExpHelp *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18000e960  mov     rcx, [rcx+8]
0x18000e964  mov     rax, [rcx]
0x18000e967  mov     rax, [rax+10h]
0x18000e96b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
