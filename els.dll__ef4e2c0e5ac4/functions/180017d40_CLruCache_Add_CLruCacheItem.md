# CLruCache::Add(CLruCacheItem *)

- ea: `0x180017d40`
- end: `0x180017df5`
- name: `?Add@CLruCache@@UEAAJPEAVCLruCacheItem@@@Z`
- size: `181`
- prototype: `int(CLruCache *__hidden this, struct CLruCacheItem *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c4f0`
- `0x18000c728`
- `0x180018154`
- `0x18001b3f8`

## callees

- `0x180004f34`
- `0x180017d40`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017d5b`
- `KERNEL32!EnterCriticalSection` at `0x180017d5b`
- `KERNEL32!LeaveCriticalSection` at `0x180017de4`
- `KERNEL32!LeaveCriticalSection` at `0x180017de4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLruCache::Add(CLruCache *this, struct CLruCacheItem *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int v5; // ebp
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = 0;
  v6 = *((_QWORD *)this + 2);
  if ( *((_DWORD *)this + 2) >= *((_DWORD *)this + 3) )
  {
    v7 = 0;
    v8 = -1;
    if ( !v6 )
      goto LABEL_15;
    do
    {
      v9 = *(_DWORD *)(v6 + 24);
      if ( v9 <= v8 )
        v7 = v6;
      v6 = *(_QWORD *)(v6 + 8);
      if ( v9 > v8 )
        v9 = v8;
      v8 = v9;
    }
    while ( v6 );
    if ( v7 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, struct CLruCacheItem *, _QWORD))(*(_QWORD *)v7 + 16LL))(v7, a2, v9);
      if ( a2 )
        (**(void (__fastcall ***)(struct CLruCacheItem *, __int64))a2)(a2, 1);
    }
    else
    {
LABEL_15:
      *((_QWORD *)this + 2) = a2;
    }
  }
  else
  {
    if ( v6 )
      CDLink::LinkAfter(a2, (struct CDLink *)v6);
    else
      *((_QWORD *)this + 2) = a2;
    ++*((_DWORD *)this + 2);
  }
  LeaveCriticalSection(v4);
  return v5;
}

```

## disassembly

```asm
0x180017d40  push    rbx
0x180017d42  push    rbp
0x180017d43  push    rsi
0x180017d44  push    rdi
0x180017d45  sub     rsp, 28h
0x180017d49  mov     rsi, rdx
0x180017d4c  mov     rdi, rcx
0x180017d4f  lea     rbx, [rcx+18h]
0x180017d53  mov     [rsp+48h+arg_0], rbx
0x180017d58  mov     rcx, rbx; lpCriticalSection
0x180017d5b  call    cs:__imp_EnterCriticalSection
0x180017d61  nop
0x180017d62  xor     ebp, ebp
0x180017d64  mov     eax, [rdi+0Ch]
0x180017d67  mov     rdx, [rdi+10h]; struct CDLink *
0x180017d6b  cmp     [rdi+8], eax
0x180017d6e  jnb     short loc_180017D88
0x180017d70  test    rdx, rdx
0x180017d73  jz      short loc_180017D7F
0x180017d75  mov     rcx, rsi; this
0x180017d78  call    ?LinkAfter@CDLink@@QEAAXPEAV1@@Z; CDLink::LinkAfter(CDLink *)
0x180017d7d  jmp     short loc_180017D83
0x180017d7f  mov     [rdi+10h], rsi
0x180017d83  inc     dword ptr [rdi+8]
0x180017d86  jmp     short loc_180017DE1
0x180017d88  xor     ecx, ecx
0x180017d8a  or      r8d, 0FFFFFFFFh
0x180017d8e  test    rdx, rdx
0x180017d91  jz      short loc_180017DDD
0x180017d93  mov     eax, [rdx+18h]
0x180017d96  cmp     eax, r8d
0x180017d99  cmovbe  rcx, rdx
0x180017d9d  mov     rdx, [rdx+8]
0x180017da1  cmova   eax, r8d
0x180017da5  mov     r8d, eax
0x180017da8  test    rdx, rdx
0x180017dab  jnz     short loc_180017D93
0x180017dad  test    rcx, rcx
0x180017db0  jz      short loc_180017DDD
0x180017db2  mov     rax, [rcx]
0x180017db5  mov     rdx, rsi
0x180017db8  mov     rax, [rax+10h]
0x180017dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dc1  mov     ebp, eax
0x180017dc3  test    rsi, rsi
0x180017dc6  jz      short loc_180017DE1
0x180017dc8  mov     rcx, [rsi]
0x180017dcb  mov     rax, [rcx]
0x180017dce  mov     edx, 1
0x180017dd3  mov     rcx, rsi
0x180017dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ddb  jmp     short loc_180017DE1
0x180017ddd  mov     [rdi+10h], rsi
0x180017de1  mov     rcx, rbx; lpCriticalSection
0x180017de4  call    cs:__imp_LeaveCriticalSection
0x180017dea  mov     eax, ebp
0x180017dec  add     rsp, 28h
0x180017df0  pop     rdi
0x180017df1  pop     rsi
0x180017df2  pop     rbp
0x180017df3  pop     rbx
0x180017df4  retn
```
