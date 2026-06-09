# TOKEN_KEY::~TOKEN_KEY(void)

- ea: `0x18000c45c`
- end: `0x18000c47f`
- name: `??1TOKEN_KEY@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c898`
- `0x180010a80`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c469`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c469`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c478`

## pseudocode

```c
void __fastcall TOKEN_KEY::~TOKEN_KEY(TOKEN_KEY *this)
{
  STRU::~STRU((TOKEN_KEY *)((char *)this + 64));
  STRU::~STRU((TOKEN_KEY *)((char *)this + 8));
}

```

## disassembly

```asm
0x18000c45c  push    rbx
0x18000c45e  sub     rsp, 20h
0x18000c462  mov     rbx, rcx
0x18000c465  add     rcx, 40h ; '@'
0x18000c469  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c46f  lea     rcx, [rbx+8]
0x18000c473  add     rsp, 20h
0x18000c477  pop     rbx
0x18000c478  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
