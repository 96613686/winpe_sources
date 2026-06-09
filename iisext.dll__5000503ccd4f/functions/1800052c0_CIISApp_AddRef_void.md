# CIISApp::AddRef(void)

- ea: `0x1800052c0`
- end: `0x1800052d0`
- name: `?AddRef@CIISApp@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CIISApp *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052e0`
- `0x1800052f0`
- `0x180005300`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::AddRef(CIISApp *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x1800052c0  mov     rcx, [rcx+30h]
0x1800052c4  mov     rax, [rcx]
0x1800052c7  mov     rax, [rax+8]
0x1800052cb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
