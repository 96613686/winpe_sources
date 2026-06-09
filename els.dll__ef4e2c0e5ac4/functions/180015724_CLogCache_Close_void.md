# CLogCache::Close(void)

- ea: `0x180015724`
- end: `0x18001575f`
- name: `?Close@CLogCache@@QEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(CLogCache *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800156e8`
- `0x18001a054`
- `0x18001bc00`

## callees

- `0x180015a14`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001573b`
- `KERNEL32!EnterCriticalSection` at `0x18001573b`
- `KERNEL32!LeaveCriticalSection` at `0x18001574c`
- `KERNEL32!LeaveCriticalSection` at `0x18001574c`

## pseudocode

```c
__int64 __fastcall CLogCache::Close(CLogCache *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  CLogCache::_FreeResources(this);
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x180015724  mov     [rsp+arg_0], rbx
0x180015729  push    rdi
0x18001572a  sub     rsp, 20h
0x18001572e  lea     rdi, [rcx+260h]
0x180015735  mov     rbx, rcx
0x180015738  mov     rcx, rdi; lpCriticalSection
0x18001573b  call    cs:__imp_EnterCriticalSection
0x180015741  mov     rcx, rbx; this
0x180015744  call    ?_FreeResources@CLogCache@@AEAAXXZ; CLogCache::_FreeResources(void)
0x180015749  mov     rcx, rdi; lpCriticalSection
0x18001574c  call    cs:__imp_LeaveCriticalSection
0x180015752  mov     rbx, [rsp+28h+arg_0]
0x180015757  xor     eax, eax
0x180015759  add     rsp, 20h
0x18001575d  pop     rdi
0x18001575e  retn
```
