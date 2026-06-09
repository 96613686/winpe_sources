# CacheBase::insert(CacheEntry &,bool)

- ea: `0x18002d9f4`
- end: `0x18002da8c`
- name: `?insert@CacheBase@@QEAA_NAEAVCacheEntry@@_N@Z`
- size: `152`
- prototype: `bool __fastcall(CacheBase *__hidden this, struct CacheEntry *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180024324`
- `0x180024408`

## callees

- `0x18002d9f4`
- `0x18002da94`
- `0x18002dd04`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002da42`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002da42`
- `KERNEL32!EnterCriticalSection` at `0x18002da10`
- `KERNEL32!EnterCriticalSection` at `0x18002da10`
- `KERNEL32!LeaveCriticalSection` at `0x18002da70`
- `KERNEL32!LeaveCriticalSection` at `0x18002da70`

## pseudocode

```c
bool __fastcall CacheBase::insert(CacheBase *this, struct CacheEntry *a2)
{
  bool v4; // r8
  bool v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CacheBase::unsafe_evict(this);
  v5 = HashTableBase::insert(this, a2, v4);
  if ( v5 )
  {
    v6 = *((_QWORD *)this + 10);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *((_QWORD *)a2 + 4) = v6 + *(_QWORD *)&SystemTimeAsFileTime;
    v7 = *((_QWORD *)this + 8);
    *((_QWORD *)a2 + 2) = v7;
    *((_QWORD *)a2 + 3) = (char *)this + 48;
    *(_QWORD *)(v7 + 24) = a2;
    *((_QWORD *)this + 8) = a2;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v5;
}

```

## disassembly

```asm
0x18002d9f4  mov     [rsp+arg_8], rbx
0x18002d9f9  mov     [rsp+arg_10], rbp
0x18002d9fe  push    rsi
0x18002d9ff  push    rdi
0x18002da00  push    r14
0x18002da02  sub     rsp, 20h
0x18002da06  mov     rsi, rcx
0x18002da09  mov     rdi, rdx
0x18002da0c  add     rcx, 18h; lpCriticalSection
0x18002da10  call    cs:__imp_EnterCriticalSection
0x18002da16  mov     rcx, rsi; this
0x18002da19  call    ?unsafe_evict@CacheBase@@IEAAXXZ; CacheBase::unsafe_evict(void)
0x18002da1e  mov     rdx, rdi; struct HashTableEntry *
0x18002da21  mov     rcx, rsi; this
0x18002da24  call    ?insert@HashTableBase@@QEAA_NAEAVHashTableEntry@@_N@Z; HashTableBase::insert(HashTableEntry &,bool)
0x18002da29  mov     r14b, al
0x18002da2c  test    al, al
0x18002da2e  jz      short loc_18002DA6C
0x18002da30  mov     rbx, [rsi+50h]
0x18002da34  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002da39  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002da42  call    cs:__imp_GetSystemTimeAsFileTime
0x18002da48  mov     r8, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x18002da4d  add     r8, rbx
0x18002da50  mov     [rdi+20h], r8
0x18002da54  lea     r8, [rsi+30h]
0x18002da58  mov     rdx, [r8+10h]
0x18002da5c  mov     [rdi+10h], rdx
0x18002da60  mov     [rdi+18h], r8
0x18002da64  mov     [rdx+18h], rdi
0x18002da68  mov     [r8+10h], rdi
0x18002da6c  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002da70  call    cs:__imp_LeaveCriticalSection
0x18002da76  mov     rbx, [rsp+38h+arg_8]
0x18002da7b  mov     al, r14b
0x18002da7e  mov     rbp, [rsp+38h+arg_10]
0x18002da83  add     rsp, 20h
0x18002da87  pop     r14
0x18002da89  pop     rdi
0x18002da8a  pop     rsi
0x18002da8b  retn
```
