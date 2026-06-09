# W3_URL_INFO_CACHE::~W3_URL_INFO_CACHE(void)

- ea: `0x180001bf8`
- end: `0x180001c19`
- name: `??1W3_URL_INFO_CACHE@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(W3_URL_INFO_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001f30`

## callees

- `0x180001fa8`

## import_xrefs

- `iisutil!??1TREE_HASH_TABLE@@QEAA@XZ` at `0x180001c12`

## pseudocode

```c
void __fastcall W3_URL_INFO_CACHE::~W3_URL_INFO_CACHE(W3_URL_INFO_CACHE *this)
{
  ACTIVITY_TABLE::~ACTIVITY_TABLE((W3_URL_INFO_CACHE *)((char *)this + 48));
  TREE_HASH_TABLE::~TREE_HASH_TABLE(this);
}

```

## disassembly

```asm
0x180001bf8  push    rbx
0x180001bfa  sub     rsp, 20h
0x180001bfe  mov     rbx, rcx
0x180001c01  add     rcx, 30h ; '0'; this
0x180001c05  call    ??1ACTIVITY_TABLE@@QEAA@XZ; ACTIVITY_TABLE::~ACTIVITY_TABLE(void)
0x180001c0a  mov     rcx, rbx
0x180001c0d  add     rsp, 20h
0x180001c11  pop     rbx
0x180001c12  jmp     cs:__imp_??1TREE_HASH_TABLE@@QEAA@XZ; TREE_HASH_TABLE::~TREE_HASH_TABLE(void)
```
