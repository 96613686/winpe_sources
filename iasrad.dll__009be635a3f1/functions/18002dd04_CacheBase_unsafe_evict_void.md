# CacheBase::unsafe_evict(void)

- ea: `0x18002dd04`
- end: `0x18002ddb3`
- name: `?unsafe_evict@CacheBase@@IEAAXXZ`
- size: `175`
- prototype: `void __fastcall(CacheBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d8c0`
- `0x18002d9f4`

## callees

- `0x18002dd04`
- `0x18002ddbc`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002dd64`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002dd64`

## pseudocode

```c
void __fastcall CacheBase::unsafe_evict(CacheBase *this)
{
  unsigned int i; // eax
  const void *v3; // rax
  struct CacheEntry *v4; // rax
  __int64 v5; // rbx
  const void *v6; // rax
  struct CacheEntry *v7; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  for ( i = *((_DWORD *)this + 5); i > *((_DWORD *)this + 22); i = *((_DWORD *)this + 5) )
  {
    v3 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
    v4 = CacheBase::unsafe_remove(this, v3);
    (*(void (__fastcall **)(struct CacheEntry *))(*(_QWORD *)v4 + 8LL))(v4);
  }
  if ( i )
  {
    do
    {
      v5 = *((_QWORD *)this + 9);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( *(unsigned __int64 *)&SystemTimeAsFileTime <= *(_QWORD *)(v5 + 32) )
        break;
      v6 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
      v7 = CacheBase::unsafe_remove(this, v6);
      (*(void (__fastcall **)(struct CacheEntry *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    while ( *((_DWORD *)this + 5) );
  }
}

```

## disassembly

```asm
0x18002dd04  mov     [rsp+arg_8], rbx
0x18002dd09  push    rdi
0x18002dd0a  sub     rsp, 20h
0x18002dd0e  mov     eax, [rcx+14h]
0x18002dd11  mov     rdi, rcx
0x18002dd14  cmp     eax, [rcx+58h]
0x18002dd17  jbe     short loc_18002DD4E
0x18002dd19  mov     rcx, [rdi+48h]
0x18002dd1d  mov     rax, [rcx]
0x18002dd20  mov     rax, [rax+10h]
0x18002dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd29  mov     rdx, rax; void *
0x18002dd2c  mov     rcx, rdi; this
0x18002dd2f  call    ?unsafe_remove@CacheBase@@IEAAPEAVCacheEntry@@PEBX@Z; CacheBase::unsafe_remove(void const *)
0x18002dd34  mov     rdx, rax
0x18002dd37  mov     rcx, [rax]
0x18002dd3a  mov     rax, [rcx+8]
0x18002dd3e  mov     rcx, rdx
0x18002dd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd46  mov     eax, [rdi+14h]
0x18002dd49  cmp     eax, [rdi+58h]
0x18002dd4c  ja      short loc_18002DD19
0x18002dd4e  test    eax, eax
0x18002dd50  jz      short loc_18002DDA8
0x18002dd52  mov     rbx, [rdi+48h]
0x18002dd56  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002dd5b  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002dd64  call    cs:__imp_GetSystemTimeAsFileTime
0x18002dd6a  mov     rax, [rbx+20h]
0x18002dd6e  cmp     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002dd73  jbe     short loc_18002DDA8
0x18002dd75  mov     rcx, [rdi+48h]
0x18002dd79  mov     rax, [rcx]
0x18002dd7c  mov     rax, [rax+10h]
0x18002dd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd85  mov     rdx, rax; void *
0x18002dd88  mov     rcx, rdi; this
0x18002dd8b  call    ?unsafe_remove@CacheBase@@IEAAPEAVCacheEntry@@PEBX@Z; CacheBase::unsafe_remove(void const *)
0x18002dd90  mov     rdx, rax
0x18002dd93  mov     rcx, [rax]
0x18002dd96  mov     rax, [rcx+8]
0x18002dd9a  mov     rcx, rdx
0x18002dd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda2  cmp     dword ptr [rdi+14h], 0
0x18002dda6  jnz     short loc_18002DD52
0x18002dda8  mov     rbx, [rsp+28h+arg_8]
0x18002ddad  add     rsp, 20h
0x18002ddb1  pop     rdi
0x18002ddb2  retn
```
