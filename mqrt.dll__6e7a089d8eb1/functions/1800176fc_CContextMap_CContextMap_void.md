# CContextMap::~CContextMap(void)

- ea: `0x1800176fc`
- end: `0x180017721`
- name: `??1CContextMap@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CContextMap *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180025680`

## import_xrefs

- `msvcrt!free` at `0x180017709`
- `msvcrt!free` at `0x180017709`
- `KERNEL32!DeleteCriticalSection` at `0x180017714`
- `KERNEL32!DeleteCriticalSection` at `0x180017714`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CContextMap::~CContextMap(CContextMap *this)
{
  free(*((void **)this + 1));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800176fc  push    rbx
0x1800176fe  sub     rsp, 20h
0x180017702  mov     rbx, rcx
0x180017705  mov     rcx, [rcx+8]; Block
0x180017709  call    cs:__imp_free
0x18001770f  nop
0x180017710  lea     rcx, [rbx+18h]; lpCriticalSection
0x180017714  call    cs:__imp_DeleteCriticalSection
0x18001771a  nop
0x18001771b  add     rsp, 20h
0x18001771f  pop     rbx
0x180017720  retn
```
