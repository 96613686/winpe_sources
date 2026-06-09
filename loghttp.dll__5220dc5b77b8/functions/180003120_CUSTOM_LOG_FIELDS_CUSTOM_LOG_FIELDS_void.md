# CUSTOM_LOG_FIELDS::~CUSTOM_LOG_FIELDS(void)

- ea: `0x180003120`
- end: `0x18000314c`
- name: `??1CUSTOM_LOG_FIELDS@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CUSTOM_LOG_FIELDS *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003194`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180003137`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003137`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000312d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000312d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003145`

## pseudocode

```c
void __fastcall CUSTOM_LOG_FIELDS::~CUSTOM_LOG_FIELDS(CUSTOM_LOG_FIELDS *this)
{
  STRU::~STRU((CUSTOM_LOG_FIELDS *)((char *)this + 112));
  STRA::~STRA((CUSTOM_LOG_FIELDS *)((char *)this + 56));
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x180003120  push    rbx
0x180003122  sub     rsp, 20h
0x180003126  mov     rbx, rcx
0x180003129  add     rcx, 70h ; 'p'
0x18000312d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003133  lea     rcx, [rbx+38h]
0x180003137  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000313d  mov     rcx, rbx
0x180003140  add     rsp, 20h
0x180003144  pop     rbx
0x180003145  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
