# CACSecurityContext::~CACSecurityContext(void)

- ea: `0x18000a524`
- end: `0x18000a553`
- name: `??1CACSecurityContext@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CACSecurityContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a4f4`
- `0x18000a67c`
- `0x180016278`

## import_xrefs

- `msvcrt!free` at `0x18000a530`
- `msvcrt!free` at `0x18000a53b`
- `msvcrt!free` at `0x18000a546`
- `msvcrt!free` at `0x18000a530`
- `msvcrt!free` at `0x18000a53b`
- `msvcrt!free` at `0x18000a546`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CACSecurityContext::~CACSecurityContext(void **this)
{
  free(*this);
  free(this[1]);
  free(this[2]);
}

```

## disassembly

```asm
0x18000a524  push    rbx
0x18000a526  sub     rsp, 20h
0x18000a52a  mov     rbx, rcx
0x18000a52d  mov     rcx, [rcx]; Block
0x18000a530  call    cs:__imp_free
0x18000a536  nop
0x18000a537  mov     rcx, [rbx+8]; Block
0x18000a53b  call    cs:__imp_free
0x18000a541  nop
0x18000a542  mov     rcx, [rbx+10h]; Block
0x18000a546  call    cs:__imp_free
0x18000a54c  nop
0x18000a54d  add     rsp, 20h
0x18000a551  pop     rbx
0x18000a552  retn
```
