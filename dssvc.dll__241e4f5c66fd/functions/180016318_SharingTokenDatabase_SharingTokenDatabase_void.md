# SharingTokenDatabase::~SharingTokenDatabase(void)

- ea: `0x180016318`
- end: `0x180016338`
- name: `??1SharingTokenDatabase@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(SharingTokenDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b9a0`

## callees

- `0x180010148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016325`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016325`

## pseudocode

```c
void __fastcall SharingTokenDatabase::~SharingTokenDatabase(SharingTokenDatabase *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  Database::~Database(this);
}

```

## disassembly

```asm
0x180016318  push    rbx
0x18001631a  sub     rsp, 20h
0x18001631e  mov     rbx, rcx
0x180016321  add     rcx, 70h ; 'p'; lpCriticalSection
0x180016325  call    cs:__imp_DeleteCriticalSection
0x18001632b  mov     rcx, rbx; this
0x18001632e  add     rsp, 20h
0x180016332  pop     rbx
0x180016333  jmp     ??1Database@@UEAA@XZ; Database::~Database(void)
```
