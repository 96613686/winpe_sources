# OUTPUT_KEY::~OUTPUT_KEY(void)

- ea: `0x180005270`
- end: `0x1800052ac`
- name: `??1OUTPUT_KEY@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(OUTPUT_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f20`
- `0x180006338`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800052a5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005280`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000528d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005297`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005280`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000528d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005297`

## pseudocode

```c
void __fastcall OUTPUT_KEY::~OUTPUT_KEY(OUTPUT_KEY *this)
{
  STRU::~STRU((OUTPUT_KEY *)((char *)this + 488));
  STRU::~STRU((OUTPUT_KEY *)((char *)this + 176));
  STRU::~STRU((OUTPUT_KEY *)((char *)this + 56));
  BUFFER::~BUFFER(this);
}

```

## disassembly

```asm
0x180005270  push    rbx
0x180005272  sub     rsp, 20h
0x180005276  mov     rbx, rcx
0x180005279  add     rcx, 1E8h
0x180005280  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005286  lea     rcx, [rbx+0B0h]
0x18000528d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005293  lea     rcx, [rbx+38h]
0x180005297  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000529d  mov     rcx, rbx
0x1800052a0  add     rsp, 20h
0x1800052a4  pop     rbx
0x1800052a5  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
