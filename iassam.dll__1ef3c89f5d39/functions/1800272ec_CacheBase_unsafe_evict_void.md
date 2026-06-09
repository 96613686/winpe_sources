# CacheBase::unsafe_evict(void)

- ea: `0x1800272ec`
- end: `0x18002739b`
- name: `?unsafe_evict@CacheBase@@IEAAXXZ`
- size: `175`
- prototype: `void __fastcall(CacheBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180026ea8`
- `0x180026fdc`

## callees

- `0x1800272ec`
- `0x1800273a4`
- `0x18002e010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002734c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002734c`

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
0x1800272ec  mov     [rsp+arg_8], rbx
0x1800272f1  push    rdi
0x1800272f2  sub     rsp, 20h
0x1800272f6  mov     eax, [rcx+14h]
0x1800272f9  mov     rdi, rcx
0x1800272fc  cmp     eax, [rcx+58h]
0x1800272ff  jbe     short loc_180027336
0x180027301  mov     rcx, [rdi+48h]
0x180027305  mov     rax, [rcx]
0x180027308  mov     rax, [rax+10h]
0x18002730c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027311  mov     rdx, rax; void *
0x180027314  mov     rcx, rdi; this
0x180027317  call    ?unsafe_remove@CacheBase@@IEAAPEAVCacheEntry@@PEBX@Z; CacheBase::unsafe_remove(void const *)
0x18002731c  mov     rdx, rax
0x18002731f  mov     rcx, [rax]
0x180027322  mov     rax, [rcx+8]
0x180027326  mov     rcx, rdx
0x180027329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002732e  mov     eax, [rdi+14h]
0x180027331  cmp     eax, [rdi+58h]
0x180027334  ja      short loc_180027301
0x180027336  test    eax, eax
0x180027338  jz      short loc_180027390
0x18002733a  mov     rbx, [rdi+48h]
0x18002733e  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027343  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002734c  call    cs:__imp_GetSystemTimeAsFileTime
0x180027352  mov     rax, [rbx+20h]
0x180027356  cmp     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002735b  jbe     short loc_180027390
0x18002735d  mov     rcx, [rdi+48h]
0x180027361  mov     rax, [rcx]
0x180027364  mov     rax, [rax+10h]
0x180027368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002736d  mov     rdx, rax; void *
0x180027370  mov     rcx, rdi; this
0x180027373  call    ?unsafe_remove@CacheBase@@IEAAPEAVCacheEntry@@PEBX@Z; CacheBase::unsafe_remove(void const *)
0x180027378  mov     rdx, rax
0x18002737b  mov     rcx, [rax]
0x18002737e  mov     rax, [rcx+8]
0x180027382  mov     rcx, rdx
0x180027385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738a  cmp     dword ptr [rdi+14h], 0
0x18002738e  jnz     short loc_18002733A
0x180027390  mov     rbx, [rsp+28h+arg_8]
0x180027395  add     rsp, 20h
0x180027399  pop     rdi
0x18002739a  retn
```
