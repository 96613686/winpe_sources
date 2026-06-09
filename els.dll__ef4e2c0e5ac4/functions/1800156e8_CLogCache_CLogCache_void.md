# CLogCache::~CLogCache(void)

- ea: `0x1800156e8`
- end: `0x18001571b`
- name: `??1CLogCache@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CLogCache *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800172cc`
- `0x18001b8a0`
- `0x180023244`

## callees

- `0x1800153ac`
- `0x180015724`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180015707`
- `KERNEL32!DeleteCriticalSection` at `0x180015707`

## pseudocode

```c
void __fastcall CLogCache::~CLogCache(CLogCache *this)
{
  *(_QWORD *)this = &CLogCache::`vftable';
  CLogCache::Close(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  CEventLog::Close((CLogCache *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800156e8  push    rbx
0x1800156ea  sub     rsp, 20h
0x1800156ee  lea     rax, ??_7CLogCache@@6B@; const CLogCache::`vftable'
0x1800156f5  mov     rbx, rcx
0x1800156f8  mov     [rcx], rax
0x1800156fb  call    ?Close@CLogCache@@QEAAJXZ; CLogCache::Close(void)
0x180015700  lea     rcx, [rbx+260h]; lpCriticalSection
0x180015707  call    cs:__imp_DeleteCriticalSection
0x18001570d  lea     rcx, [rbx+8]; this
0x180015711  add     rsp, 20h
0x180015715  pop     rbx
0x180015716  jmp     ?Close@CEventLog@@QEAAXXZ; CEventLog::Close(void)
```
