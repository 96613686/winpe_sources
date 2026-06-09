# std::bad_alloc::`vector deleting destructor'(uint)

- ea: `0x140001890`
- end: `0x1400018cc`
- name: `??_Ebad_alloc@std@@UEAAPEAXI@Z`
- size: `60`
- prototype: `void *__fastcall(std::bad_alloc *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001890`

## import_xrefs

- `msvcrt!free` at `0x1400018b7`
- `msvcrt!free` at `0x1400018b7`
- `msvcrt!??1exception@@UEAA@XZ` at `0x1400018a9`
- `msvcrt!??1exception@@UEAA@XZ` at `0x1400018a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::bad_alloc *__fastcall std::bad_alloc::`vector deleting destructor'(std::bad_alloc *this, char a2)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  exception::~exception(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x140001890  mov     [rsp+arg_0], rbx
0x140001895  push    rdi
0x140001896  sub     rsp, 20h
0x14000189a  mov     ebx, edx
0x14000189c  mov     rdi, rcx
0x14000189f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1400018a6  mov     [rcx], rax
0x1400018a9  call    cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
0x1400018af  test    bl, 1
0x1400018b2  jz      short loc_1400018BE
0x1400018b4  mov     rcx, rdi; Block
0x1400018b7  call    cs:__imp_free
0x1400018bd  nop
0x1400018be  mov     rax, rdi
0x1400018c1  mov     rbx, [rsp+28h+arg_0]
0x1400018c6  add     rsp, 20h
0x1400018ca  pop     rdi
0x1400018cb  retn
```
