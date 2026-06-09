# VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY(void)

- ea: `0x1800059e0`
- end: `0x180005a05`
- name: `??1VARY_BY_CACHE_KEY@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(VARY_BY_CACHE_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004778`
- `0x18000759c`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800059fe`

## pseudocode

```c
void __fastcall VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY(VARY_BY_CACHE_KEY *this)
{
  STRU::~STRU((VARY_BY_CACHE_KEY *)((char *)this + 312));
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x1800059e0  push    rbx
0x1800059e2  sub     rsp, 20h
0x1800059e6  mov     rbx, rcx
0x1800059e9  add     rcx, 138h
0x1800059f0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800059f6  mov     rcx, rbx
0x1800059f9  add     rsp, 20h
0x1800059fd  pop     rbx
0x1800059fe  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
