# CLogCache::CLogCache(void)

- ea: `0x180015684`
- end: `0x1800156e0`
- name: `??0CLogCache@@QEAA@XZ`
- size: `92`
- prototype: `CLogCache *__fastcall(CLogCache *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800172cc`
- `0x18001b658`

## callees

- `0x180015a14`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800156b9`
- `KERNEL32!InitializeCriticalSection` at `0x1800156b9`

## pseudocode

```c
CLogCache *__fastcall CLogCache::CLogCache(CLogCache *this)
{
  *(_QWORD *)this = &CLogCache::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 81) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  CLogCache::_FreeResources(this);
  return this;
}

```

## disassembly

```asm
0x180015684  push    rbx
0x180015686  sub     rsp, 20h
0x18001568a  lea     rax, ??_7CLogCache@@6B@; const CLogCache::`vftable'
0x180015691  mov     rbx, rcx
0x180015694  mov     [rcx], rax
0x180015697  mov     qword ptr [rcx+8], 0
0x18001569f  mov     qword ptr [rcx+10h], 0
0x1800156a7  mov     qword ptr [rcx+288h], 0
0x1800156b2  add     rcx, 260h; lpCriticalSection
0x1800156b9  call    cs:__imp_InitializeCriticalSection
0x1800156bf  mov     rcx, rbx; this
0x1800156c2  mov     qword ptr [rbx+18h], 0
0x1800156ca  mov     qword ptr [rbx+28h], 0
0x1800156d2  call    ?_FreeResources@CLogCache@@AEAAXXZ; CLogCache::_FreeResources(void)
0x1800156d7  mov     rax, rbx
0x1800156da  add     rsp, 20h
0x1800156de  pop     rbx
0x1800156df  retn
```
