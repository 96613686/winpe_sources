# CWMWriterInputPin::Release(void)

- ea: `0x180006160`
- end: `0x180006170`
- name: `?Release@CWMWriterInputPin@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWMWriterInputPin *__hidden this)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c8f0`
- `0x18000c900`
- `0x18000c920`
- `0x18000c940`
- `0x18000c950`
- `0x18000c960`
- `0x18000c970`
- `0x18000c980`
- `0x180011270`
- `0x180011290`
- `0x1800112b0`
- `0x1800112d0`
- `0x1800112f0`
- `0x180014d20`
- `0x180014d40`
- `0x180014d60`
- `0x180014d80`
- `0x180014da0`
- `0x18001a420`

## callees

- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::Release(CWMWriterInputPin *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 16LL))(*((_QWORD *)this - 2));
}

```

## disassembly

```asm
0x180006160  mov     rcx, [rcx-10h]
0x180006164  mov     rax, [rcx]
0x180006167  mov     rax, [rax+10h]
0x18000616b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
