# CCommand::GetPCriticalSection(void)

- ea: `0x10013b90`
- end: `0x10013b97`
- name: `?GetPCriticalSection@CCommand@@MAEPAVCriticalSection@@XZ`
- size: `7`
- prototype: `struct CriticalSection *__thiscall(CCommand *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct CriticalSection *__thiscall CCommand::GetPCriticalSection(CCommand *this)
{
  return (CCommand *)((char *)this + 248);
}

```

## disassembly

```asm
0x10013b90  lea     eax, [ecx+0F8h]
0x10013b96  retn
```
