# CADMCOMW::CImpIConnectionPointContainer::Release(void)

- ea: `0x18000c530`
- end: `0x18000c540`
- name: `?Release@CImpIConnectionPointContainer@CADMCOMW@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CADMCOMW::CImpIConnectionPointContainer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpIConnectionPointContainer::Release(CADMCOMW::CImpIConnectionPointContainer *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x18000c530  mov     rcx, [rcx+10h]
0x18000c534  mov     rax, [rcx]
0x18000c537  mov     rax, [rax+10h]
0x18000c53b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
