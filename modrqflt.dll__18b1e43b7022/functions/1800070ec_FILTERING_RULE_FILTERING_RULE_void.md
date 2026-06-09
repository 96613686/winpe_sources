# FILTERING_RULE::~FILTERING_RULE(void)

- ea: `0x1800070ec`
- end: `0x180007128`
- name: `??1FILTERING_RULE@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(FILTERING_RULE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005520`

## import_xrefs

- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180007113`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180007113`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800070fc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007109`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800070fc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007109`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007121`

## pseudocode

```c
void __fastcall FILTERING_RULE::~FILTERING_RULE(FILTERING_RULE *this)
{
  MULTISZ::~MULTISZ((FILTERING_RULE *)((char *)this + 184));
  MULTISZ::~MULTISZ((FILTERING_RULE *)((char *)this + 128));
  MULTISZA::~MULTISZA((FILTERING_RULE *)((char *)this + 72));
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x1800070ec  push    rbx
0x1800070ee  sub     rsp, 20h
0x1800070f2  mov     rbx, rcx
0x1800070f5  add     rcx, 0B8h
0x1800070fc  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007102  lea     rcx, [rbx+80h]
0x180007109  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000710f  lea     rcx, [rbx+48h]
0x180007113  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180007119  mov     rcx, rbx
0x18000711c  add     rsp, 20h
0x180007120  pop     rbx
0x180007121  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
