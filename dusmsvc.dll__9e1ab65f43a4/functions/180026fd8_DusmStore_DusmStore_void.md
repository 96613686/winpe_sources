# DusmStore::~DusmStore(void)

- ea: `0x180026fd8`
- end: `0x180026ffa`
- name: `??1DusmStore@@AEAA@XZ`
- size: `34`
- prototype: `void __fastcall(DusmStore *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002d448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026fe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026fe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026ff3`

## pseudocode

```c
void __fastcall DusmStore::~DusmStore(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180026fd8  push    rbx
0x180026fda  sub     rsp, 20h
0x180026fde  mov     rbx, rcx
0x180026fe1  add     rcx, 28h ; '('; lpCriticalSection
0x180026fe5  call    cs:__imp_DeleteCriticalSection
0x180026feb  mov     rcx, rbx
0x180026fee  add     rsp, 20h
0x180026ff2  pop     rbx
0x180026ff3  jmp     cs:__imp_DeleteCriticalSection
```
