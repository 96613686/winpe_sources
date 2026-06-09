# CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)

- ea: `0x1800254a8`
- end: `0x1800254ed`
- name: `??1CAbsSecurityDsecripror@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CAbsSecurityDsecripror *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180027ca0`
- `0x180027ed0`
- `0x1800306e6`
- `0x1800306f8`

## import_xrefs

- `msvcrt!free` at `0x1800254b5`
- `msvcrt!free` at `0x1800254c0`
- `msvcrt!free` at `0x1800254cb`
- `msvcrt!free` at `0x1800254d6`
- `msvcrt!free` at `0x1800254e0`
- `msvcrt!free` at `0x1800254b5`
- `msvcrt!free` at `0x1800254c0`
- `msvcrt!free` at `0x1800254cb`
- `msvcrt!free` at `0x1800254d6`
- `msvcrt!free` at `0x1800254e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void **this)
{
  free(this[4]);
  free(this[3]);
  free(this[2]);
  free(this[1]);
  free(*this);
}

```

## disassembly

```asm
0x1800254a8  push    rbx
0x1800254aa  sub     rsp, 20h
0x1800254ae  mov     rbx, rcx
0x1800254b1  mov     rcx, [rcx+20h]; Block
0x1800254b5  call    cs:__imp_free
0x1800254bb  nop
0x1800254bc  mov     rcx, [rbx+18h]; Block
0x1800254c0  call    cs:__imp_free
0x1800254c6  nop
0x1800254c7  mov     rcx, [rbx+10h]; Block
0x1800254cb  call    cs:__imp_free
0x1800254d1  nop
0x1800254d2  mov     rcx, [rbx+8]; Block
0x1800254d6  call    cs:__imp_free
0x1800254dc  nop
0x1800254dd  mov     rcx, [rbx]; Block
0x1800254e0  call    cs:__imp_free
0x1800254e6  nop
0x1800254e7  add     rsp, 20h
0x1800254eb  pop     rbx
0x1800254ec  retn
```
