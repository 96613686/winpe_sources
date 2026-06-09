# AutoDeleteFileStream::Revert(void)

- ea: `0x14000d930`
- end: `0x14000d940`
- name: `?Revert@AutoDeleteFileStream@@UEAAJXZ`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Revert(AutoDeleteFileStream *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 72LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x14000d930  mov     rcx, [rcx+30h]
0x14000d934  mov     rax, [rcx]
0x14000d937  mov     rax, [rax+48h]
0x14000d93b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
