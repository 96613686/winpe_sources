# W3_CONNECTION::`vector deleting destructor'(uint)

- ea: `0x1800293c0`
- end: `0x1800293f7`
- name: `??_EW3_CONNECTION@@EEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(W3_CONNECTION *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002931c`
- `0x1800293c0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800293e3`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800293e3`

## pseudocode

```c
W3_CONNECTION *__fastcall W3_CONNECTION::`vector deleting destructor'(W3_CONNECTION *this, char a2)
{
  W3_CONNECTION::~W3_CONNECTION(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free(W3_CONNECTION::sm_pachW3Connections, this);
  return this;
}

```

## disassembly

```asm
0x1800293c0  mov     [rsp+arg_0], rbx
0x1800293c5  push    rdi
0x1800293c6  sub     rsp, 20h
0x1800293ca  mov     ebx, edx
0x1800293cc  mov     rdi, rcx
0x1800293cf  call    ??1W3_CONNECTION@@EEAA@XZ; W3_CONNECTION::~W3_CONNECTION(void)
0x1800293d4  test    bl, 1
0x1800293d7  jz      short loc_1800293E9
0x1800293d9  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x1800293e0  mov     rdx, rdi
0x1800293e3  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800293e9  mov     rbx, [rsp+28h+arg_0]
0x1800293ee  mov     rax, rdi
0x1800293f1  add     rsp, 20h
0x1800293f5  pop     rdi
0x1800293f6  retn
```
