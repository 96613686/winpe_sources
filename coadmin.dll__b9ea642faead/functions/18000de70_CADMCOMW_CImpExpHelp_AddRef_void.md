# CADMCOMW::CImpExpHelp::AddRef(void)

- ea: `0x18000de70`
- end: `0x18000de80`
- name: `?AddRef@CImpExpHelp@CADMCOMW@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CADMCOMW::CImpExpHelp *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpExpHelp::AddRef(CADMCOMW::CImpExpHelp *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18000de70  mov     rcx, [rcx+8]
0x18000de74  mov     rax, [rcx]
0x18000de77  mov     rax, [rax+8]
0x18000de7b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
