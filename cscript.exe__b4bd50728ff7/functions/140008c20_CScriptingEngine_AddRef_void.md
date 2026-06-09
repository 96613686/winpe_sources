# CScriptingEngine::AddRef(void)

- ea: `0x140008c20`
- end: `0x140008c30`
- name: `?AddRef@CScriptingEngine@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CScriptingEngine *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fd00`
- `0x14000fd10`
- `0x14000fd20`
- `0x14000fd30`
- `0x14000fd40`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::AddRef(CScriptingEngine *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x140008c20  mov     rcx, [rcx+30h]
0x140008c24  mov     rax, [rcx]
0x140008c27  mov     rax, [rax+8]
0x140008c2b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
