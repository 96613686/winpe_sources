# CacheBase::find(void const *)

- ea: `0x18002d8c0`
- end: `0x18002d95c`
- name: `?find@CacheBase@@QEAAPEAVCacheEntry@@PEBX@Z`
- size: `156`
- prototype: `struct CacheEntry *__fastcall(CacheBase *__hidden this, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021790`

## callees

- `0x18002d8c0`
- `0x18002d964`
- `0x18002dd04`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002d90c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002d90c`
- `KERNEL32!EnterCriticalSection` at `0x18002d8d3`
- `KERNEL32!EnterCriticalSection` at `0x18002d8d3`
- `KERNEL32!LeaveCriticalSection` at `0x18002d94a`
- `KERNEL32!LeaveCriticalSection` at `0x18002d94a`

## pseudocode

```c
struct CacheEntry *__fastcall CacheBase::find(CacheBase *this, const void *a2)
{
  struct HashTableEntry *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CacheBase::unsafe_evict(this);
  v4 = HashTableBase::find(this, a2);
  if ( v4 && *((_BYTE *)this + 92) )
  {
    v5 = *((_QWORD *)this + 10);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = *((_QWORD *)v4 + 3);
    *((_QWORD *)v4 + 4) = v5 + *(_QWORD *)&SystemTimeAsFileTime;
    v7 = *((_QWORD *)v4 + 2);
    *(_QWORD *)(v6 + 16) = v7;
    *(_QWORD *)(v7 + 24) = v6;
    v8 = *((_QWORD *)this + 8);
    *((_QWORD *)v4 + 2) = v8;
    *((_QWORD *)v4 + 3) = (char *)this + 48;
    *(_QWORD *)(v8 + 24) = v4;
    *((_QWORD *)this + 8) = v4;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v4;
}

```

## disassembly

```asm
0x18002d8c0  push    rbx
0x18002d8c2  push    rbp
0x18002d8c3  push    rsi
0x18002d8c4  push    rdi
0x18002d8c5  sub     rsp, 28h
0x18002d8c9  mov     rsi, rcx
0x18002d8cc  mov     rbx, rdx
0x18002d8cf  add     rcx, 18h; lpCriticalSection
0x18002d8d3  call    cs:__imp_EnterCriticalSection
0x18002d8d9  mov     rcx, rsi; this
0x18002d8dc  call    ?unsafe_evict@CacheBase@@IEAAXXZ; CacheBase::unsafe_evict(void)
0x18002d8e1  mov     rdx, rbx; void *
0x18002d8e4  mov     rcx, rsi; this
0x18002d8e7  call    ?find@HashTableBase@@QEAAPEAVHashTableEntry@@PEBX@Z; HashTableBase::find(void const *)
0x18002d8ec  mov     rdi, rax
0x18002d8ef  test    rax, rax
0x18002d8f2  jz      short loc_18002D946
0x18002d8f4  cmp     byte ptr [rsi+5Ch], 0
0x18002d8f8  jz      short loc_18002D946
0x18002d8fa  mov     rbx, [rsi+50h]
0x18002d8fe  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002d903  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002d90c  call    cs:__imp_GetSystemTimeAsFileTime
0x18002d912  mov     rax, [rdi+18h]
0x18002d916  mov     rdx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18002d91b  add     rdx, rbx
0x18002d91e  mov     [rdi+20h], rdx
0x18002d922  mov     rdx, [rdi+10h]
0x18002d926  mov     [rax+10h], rdx
0x18002d92a  mov     [rdx+18h], rax
0x18002d92e  lea     rdx, [rsi+30h]
0x18002d932  mov     rax, [rdx+10h]
0x18002d936  mov     [rdi+10h], rax
0x18002d93a  mov     [rdi+18h], rdx
0x18002d93e  mov     [rax+18h], rdi
0x18002d942  mov     [rdx+10h], rdi
0x18002d946  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002d94a  call    cs:__imp_LeaveCriticalSection
0x18002d950  mov     rax, rdi
0x18002d953  add     rsp, 28h
0x18002d957  pop     rdi
0x18002d958  pop     rsi
0x18002d959  pop     rbp
0x18002d95a  pop     rbx
0x18002d95b  retn
```
