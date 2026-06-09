# CScriptingEngine::Release(void)

- ea: `0x140009060`
- end: `0x140009070`
- name: `?Release@CScriptingEngine@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CScriptingEngine *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140010590`
- `0x1400105a0`
- `0x1400105b0`
- `0x1400105c0`
- `0x1400105d0`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::Release(CScriptingEngine *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x140009060  mov     rcx, [rcx+30h]
0x140009064  mov     rax, [rcx]
0x140009067  mov     rax, [rax+10h]
0x14000906b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
