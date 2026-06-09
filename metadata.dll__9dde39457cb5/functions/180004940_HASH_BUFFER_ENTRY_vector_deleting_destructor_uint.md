# HASH_BUFFER_ENTRY::`vector deleting destructor'(uint)

- ea: `0x180004940`
- end: `0x1800049a5`
- name: `??_EHASH_BUFFER_ENTRY@@UEAAPEAXI@Z`
- size: `101`
- prototype: `void *__fastcall(HASH_BUFFER_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004940`

## import_xrefs

- `IisRTL!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000498f`
- `IisRTL!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000498f`

## pseudocode

```c
HASH_BUFFER_ENTRY *__fastcall HASH_BUFFER_ENTRY::`vector deleting destructor'(HASH_BUFFER_ENTRY *this, char a2)
{
  _QWORD *v3; // rax
  __int64 v4; // r8
  _QWORD *v5; // rcx

  *(_QWORD *)this = &HASH_BUFFER_ENTRY::`vftable';
  v3 = (_QWORD *)((char *)this + 24);
  v4 = *((_QWORD *)this + 3);
  if ( *(HASH_BUFFER_ENTRY **)(v4 + 8) != (HASH_BUFFER_ENTRY *)((char *)this + 24)
    || (v5 = (_QWORD *)*((_QWORD *)this + 4), (_QWORD *)*v5 != v3) )
  {
    __fastfail(3u);
  }
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  v3[1] = v3;
  *v3 = v3;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)HASH_BUFFER_ENTRY::sm_pach, this);
  return this;
}

```

## disassembly

```asm
0x180004940  push    rbx
0x180004942  sub     rsp, 20h
0x180004946  lea     rax, ??_7HASH_BUFFER_ENTRY@@6B@; const HASH_BUFFER_ENTRY::`vftable'
0x18000494d  mov     rbx, rcx
0x180004950  mov     [rcx], rax
0x180004953  lea     rax, [rcx+18h]
0x180004957  mov     r8, [rax]
0x18000495a  cmp     [r8+8], rax
0x18000495e  jnz     short loc_18000499E
0x180004960  mov     rcx, [rax+8]
0x180004964  cmp     [rcx], rax
0x180004967  jnz     short loc_18000499E
0x180004969  mov     [rcx], r8
0x18000496c  mov     [r8+8], rcx
0x180004970  mov     [rax+8], rax
0x180004974  mov     [rax], rax
0x180004977  xor     eax, eax
0x180004979  mov     [rbx+8], rax
0x18000497d  mov     [rbx+10h], eax
0x180004980  test    dl, 1
0x180004983  jz      short loc_180004995
0x180004985  mov     rcx, cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x18000498c  mov     rdx, rbx
0x18000498f  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180004995  mov     rax, rbx
0x180004998  add     rsp, 20h
0x18000499c  pop     rbx
0x18000499d  retn
0x18000499e  mov     ecx, 3
0x1800049a3  int     29h; Win8: RtlFailFast(ecx)
```
