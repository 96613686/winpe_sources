# CMyLockBytes::~CMyLockBytes(void)

- ea: `0x180020d78`
- end: `0x180020da6`
- name: `??1CMyLockBytes@@UEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CMyLockBytes *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020db0`

## callees

- `0x180020e94`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180020d99`
- `KERNEL32!DeleteCriticalSection` at `0x180020d99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMyLockBytes::~CMyLockBytes(CMyLockBytes *this)
{
  *(_QWORD *)this = &CMyLockBytes::`vftable';
  CMyLockBytes::DeleteBlocks(this, *((struct CMyMemNode **)this + 8));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180020d78  push    rbx
0x180020d7a  sub     rsp, 20h
0x180020d7e  mov     rbx, rcx
0x180020d81  lea     rax, ??_7CMyLockBytes@@6B@; const CMyLockBytes::`vftable'
0x180020d88  mov     [rcx], rax
0x180020d8b  mov     rdx, [rcx+40h]; struct CMyMemNode *
0x180020d8f  call    ?DeleteBlocks@CMyLockBytes@@AEAAXPEAUCMyMemNode@@@Z; CMyLockBytes::DeleteBlocks(CMyMemNode *)
0x180020d94  nop
0x180020d95  lea     rcx, [rbx+8]; lpCriticalSection
0x180020d99  call    cs:__imp_DeleteCriticalSection
0x180020d9f  nop
0x180020da0  add     rsp, 20h
0x180020da4  pop     rbx
0x180020da5  retn
```
