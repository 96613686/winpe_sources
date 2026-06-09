# CriticalSection::~CriticalSection(void)

- ea: `0x18000e33c`
- end: `0x18000e351`
- name: `??1CriticalSection@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800167a4`
- `0x180026c70`

## callees

- `0x18000e33c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e346`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e346`

## pseudocode

```c
void __fastcall CriticalSection::~CriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( !LOBYTE(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000e33c  sub     rsp, 28h
0x18000e340  cmp     byte ptr [rcx+28h], 0
0x18000e344  jnz     short loc_18000E34C
0x18000e346  call    cs:__imp_DeleteCriticalSection
0x18000e34c  add     rsp, 28h
0x18000e350  retn
```
