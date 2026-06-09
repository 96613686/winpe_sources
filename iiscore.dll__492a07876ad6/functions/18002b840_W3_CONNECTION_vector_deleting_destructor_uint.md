# W3_CONNECTION::`vector deleting destructor'(uint)

- ea: `0x18002b840`
- end: `0x18002b87e`
- name: `??_EW3_CONNECTION@@EEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(W3_CONNECTION *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002b7a8`
- `0x18002b840`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002b863`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002b863`

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
0x18002b840  mov     [rsp+arg_0], rbx
0x18002b845  push    rdi
0x18002b846  sub     rsp, 20h
0x18002b84a  mov     ebx, edx
0x18002b84c  mov     rdi, rcx
0x18002b84f  call    ??1W3_CONNECTION@@EEAA@XZ; W3_CONNECTION::~W3_CONNECTION(void)
0x18002b854  test    bl, 1
0x18002b857  jz      short loc_18002B86F
0x18002b859  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x18002b860  mov     rdx, rdi
0x18002b863  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002b86a  nop     dword ptr [rax+rax+00h]
0x18002b86f  mov     rbx, [rsp+28h+arg_0]
0x18002b874  mov     rax, rdi
0x18002b877  add     rsp, 20h
0x18002b87b  pop     rdi
0x18002b87c  retn
```
