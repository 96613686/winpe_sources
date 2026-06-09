# CLogCache::CopyRecFromCache(ulong)

- ea: `0x180015768`
- end: `0x1800157d3`
- name: `?CopyRecFromCache@CLogCache@@QEAAPEAU_EVENTLOGRECORD@@K@Z`
- size: `107`
- prototype: `struct _EVENTLOGRECORD *__fastcall(CLogCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a2d0`

## callees

- `0x180002bb8`
- `0x1800036a6`
- `0x180015768`
- `0x180015abc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180015787`
- `KERNEL32!EnterCriticalSection` at `0x180015787`
- `KERNEL32!LeaveCriticalSection` at `0x1800157c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800157c1`

## pseudocode

```c
struct _EVENTLOGRECORD *__fastcall CLogCache::CopyRecFromCache(CLogCache *this, unsigned int a2)
{
  void *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  struct _EVENTLOGRECORD *v6; // rax
  struct _EVENTLOGRECORD *v7; // rbx
  void *v8; // rax

  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v6 = CLogCache::_SearchCache(this, a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = operator new[](v6->Length);
    v4 = v8;
    if ( v8 )
      memcpy_0(v8, v7, v7->Length);
  }
  LeaveCriticalSection(v5);
  return (struct _EVENTLOGRECORD *)v4;
}

```

## disassembly

```asm
0x180015768  push    rbx
0x18001576a  push    rbp
0x18001576b  push    rsi
0x18001576c  push    rdi
0x18001576d  sub     rsp, 28h
0x180015771  mov     ebx, edx
0x180015773  mov     rdi, rcx
0x180015776  xor     esi, esi
0x180015778  lea     rbp, [rcx+260h]
0x18001577f  mov     [rsp+48h+arg_0], rbp
0x180015784  mov     rcx, rbp; lpCriticalSection
0x180015787  call    cs:__imp_EnterCriticalSection
0x18001578d  nop
0x18001578e  mov     edx, ebx; unsigned int
0x180015790  mov     rcx, rdi; this
0x180015793  call    ?_SearchCache@CLogCache@@AEAAPEAU_EVENTLOGRECORD@@K@Z; CLogCache::_SearchCache(ulong)
0x180015798  mov     rbx, rax
0x18001579b  test    rax, rax
0x18001579e  jz      short loc_1800157BE
0x1800157a0  mov     ecx, [rax]; unsigned __int64
0x1800157a2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800157a7  mov     rsi, rax
0x1800157aa  test    rax, rax
0x1800157ad  jz      short loc_1800157BE
0x1800157af  mov     r8d, [rbx]; Size
0x1800157b2  mov     rdx, rbx; Src
0x1800157b5  mov     rcx, rax; void *
0x1800157b8  call    memcpy_0
0x1800157bd  nop
0x1800157be  mov     rcx, rbp; lpCriticalSection
0x1800157c1  call    cs:__imp_LeaveCriticalSection
0x1800157c7  mov     rax, rsi
0x1800157ca  add     rsp, 28h
0x1800157ce  pop     rdi
0x1800157cf  pop     rsi
0x1800157d0  pop     rbp
0x1800157d1  pop     rbx
0x1800157d2  retn
```
