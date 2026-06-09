# CriticalSection::~CriticalSection(void)

- ea: `0x1000ba80`
- end: `0x1000ba8a`
- name: `??1CriticalSection@@QAE@XZ`
- size: `10`
- prototype: `void __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x10017160`
- `0x1001b720`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1000ba83`
- `KERNEL32!DeleteCriticalSection` at `0x1000ba83`

## pseudocode

```c
void __thiscall CriticalSection::~CriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1000ba80  mov     edi, edi
0x1000ba82  push    ecx; lpCriticalSection
0x1000ba83  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000ba89  retn
```
