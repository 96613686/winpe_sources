# UL_RESPONSE_CACHE_KEY::~UL_RESPONSE_CACHE_KEY(void)

- ea: `0x180001180`
- end: `0x1800011b2`
- name: `??1UL_RESPONSE_CACHE_KEY@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(UL_RESPONSE_CACHE_KEY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001048`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001190`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000119d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001190`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000119d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800011ab`

## pseudocode

```c
void __fastcall UL_RESPONSE_CACHE_KEY::~UL_RESPONSE_CACHE_KEY(UL_RESPONSE_CACHE_KEY *this)
{
  STRU::~STRU((UL_RESPONSE_CACHE_KEY *)((char *)this + 368));
  STRU::~STRU((UL_RESPONSE_CACHE_KEY *)((char *)this + 184));
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x180001180  push    rbx
0x180001182  sub     rsp, 20h
0x180001186  mov     rbx, rcx
0x180001189  add     rcx, 170h
0x180001190  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001196  lea     rcx, [rbx+0B8h]
0x18000119d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800011a3  mov     rcx, rbx
0x1800011a6  add     rsp, 20h
0x1800011aa  pop     rbx
0x1800011ab  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
