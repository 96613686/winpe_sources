# CCriticalSection::~CCriticalSection(void)

- ea: `0x140009268`
- end: `0x14000927d`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034b4`

## callees

- `0x140009268`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140009272`
- `KERNEL32!DeleteCriticalSection` at `0x140009272`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( BYTE1(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140009268  sub     rsp, 28h
0x14000926c  cmp     byte ptr [rcx+29h], 0
0x140009270  jz      short loc_140009278
0x140009272  call    cs:__imp_DeleteCriticalSection
0x140009278  add     rsp, 28h
0x14000927c  retn
```
