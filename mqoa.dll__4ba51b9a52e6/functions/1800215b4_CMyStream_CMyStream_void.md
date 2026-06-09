# CMyStream::~CMyStream(void)

- ea: `0x1800215b4`
- end: `0x1800215e9`
- name: `??1CMyStream@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CMyStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800215f0`

## callees

- `0x180029010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800215dc`
- `KERNEL32!DeleteCriticalSection` at `0x1800215dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMyStream::~CMyStream(CMyStream *this)
{
  *(_QWORD *)this = &CMyStream::`vftable';
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800215b4  push    rbx
0x1800215b6  sub     rsp, 20h
0x1800215ba  mov     rbx, rcx
0x1800215bd  lea     rax, ??_7CMyStream@@6B@; const CMyStream::`vftable'
0x1800215c4  mov     [rcx], rax
0x1800215c7  mov     rcx, [rcx+38h]
0x1800215cb  mov     rax, [rcx]
0x1800215ce  mov     rax, [rax+10h]
0x1800215d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215d7  nop
0x1800215d8  lea     rcx, [rbx+8]; lpCriticalSection
0x1800215dc  call    cs:__imp_DeleteCriticalSection
0x1800215e2  nop
0x1800215e3  add     rsp, 20h
0x1800215e7  pop     rbx
0x1800215e8  retn
```
