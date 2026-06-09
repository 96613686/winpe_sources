# CacheBase::insert(CacheEntry &,bool)

- ea: `0x180026fdc`
- end: `0x180027074`
- name: `?insert@CacheBase@@QEAA_NAEAVCacheEntry@@_N@Z`
- size: `152`
- prototype: `bool __fastcall(CacheBase *__hidden this, struct CacheEntry *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fa44`
- `0x18001fb74`

## callees

- `0x180026fdc`
- `0x18002707c`
- `0x1800272ec`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180027058`
- `KERNEL32!LeaveCriticalSection` at `0x180027058`
- `KERNEL32!EnterCriticalSection` at `0x180026ff8`
- `KERNEL32!EnterCriticalSection` at `0x180026ff8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002702a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002702a`

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
0x180026fdc  mov     [rsp+arg_8], rbx
0x180026fe1  mov     [rsp+arg_10], rbp
0x180026fe6  push    rsi
0x180026fe7  push    rdi
0x180026fe8  push    r14
0x180026fea  sub     rsp, 20h
0x180026fee  mov     rsi, rcx
0x180026ff1  mov     rdi, rdx
0x180026ff4  add     rcx, 18h; lpCriticalSection
0x180026ff8  call    cs:__imp_EnterCriticalSection
0x180026ffe  mov     rcx, rsi; this
0x180027001  call    ?unsafe_evict@CacheBase@@IEAAXXZ; CacheBase::unsafe_evict(void)
0x180027006  mov     rdx, rdi; struct HashTableEntry *
0x180027009  mov     rcx, rsi; this
0x18002700c  call    ?insert@HashTableBase@@QEAA_NAEAVHashTableEntry@@_N@Z; HashTableBase::insert(HashTableEntry &,bool)
0x180027011  mov     r14b, al
0x180027014  test    al, al
0x180027016  jz      short loc_180027054
0x180027018  mov     rbx, [rsi+50h]
0x18002701c  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027021  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002702a  call    cs:__imp_GetSystemTimeAsFileTime
0x180027030  mov     r8, qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime]
0x180027035  add     r8, rbx
0x180027038  mov     [rdi+20h], r8
0x18002703c  lea     r8, [rsi+30h]
0x180027040  mov     rdx, [r8+10h]
0x180027044  mov     [rdi+10h], rdx
0x180027048  mov     [rdi+18h], r8
0x18002704c  mov     [rdx+18h], rdi
0x180027050  mov     [r8+10h], rdi
0x180027054  lea     rcx, [rsi+18h]; lpCriticalSection
0x180027058  call    cs:__imp_LeaveCriticalSection
0x18002705e  mov     rbx, [rsp+38h+arg_8]
0x180027063  mov     al, r14b
0x180027066  mov     rbp, [rsp+38h+arg_10]
0x18002706b  add     rsp, 20h
0x18002706f  pop     r14
0x180027071  pop     rdi
0x180027072  pop     rsi
0x180027073  retn
```
