# CScriptingEngine::QueryInterface(_GUID const &,void * *)

- ea: `0x1400082d0`
- end: `0x1400082df`
- name: `?QueryInterface@CScriptingEngine@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CScriptingEngine *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140010530`
- `0x140010540`
- `0x140010550`
- `0x140010560`
- `0x140010570`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::QueryInterface(CScriptingEngine *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 6))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x1400082d0  mov     rcx, [rcx+30h]
0x1400082d4  mov     rax, [rcx]
0x1400082d7  mov     rax, [rax]
0x1400082da  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
