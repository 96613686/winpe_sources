# CONFIG_PATH_MAPPER::~CONFIG_PATH_MAPPER(void)

- ea: `0x18001a790`
- end: `0x18001a7c9`
- name: `??1CONFIG_PATH_MAPPER@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CONFIG_PATH_MAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001a6b8`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a7aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a7b4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a7aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a7b4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001a7a0`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001a7a0`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001a7c2`

## pseudocode

```c
void __fastcall CONFIG_PATH_MAPPER::~CONFIG_PATH_MAPPER(CONFIG_PATH_MAPPER *this)
{
  CReaderWriterLock3::~CReaderWriterLock3((CONFIG_PATH_MAPPER *)((char *)this + 208));
  STRU::~STRU((CONFIG_PATH_MAPPER *)((char *)this + 112));
  STRU::~STRU((CONFIG_PATH_MAPPER *)((char *)this + 56));
  MULTISZ::~MULTISZ(this);
}

```

## disassembly

```asm
0x18001a790  push    rbx
0x18001a792  sub     rsp, 20h
0x18001a796  mov     rbx, rcx
0x18001a799  add     rcx, 0D0h
0x18001a7a0  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18001a7a6  lea     rcx, [rbx+70h]
0x18001a7aa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001a7b0  lea     rcx, [rbx+38h]
0x18001a7b4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001a7ba  mov     rcx, rbx
0x18001a7bd  add     rsp, 20h
0x18001a7c1  pop     rbx
0x18001a7c2  jmp     cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
```
