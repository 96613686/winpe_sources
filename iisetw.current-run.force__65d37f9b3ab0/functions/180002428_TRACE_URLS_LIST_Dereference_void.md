# TRACE_URLS_LIST::Dereference(void)

- ea: `0x180002428`
- end: `0x180002496`
- name: `?Dereference@TRACE_URLS_LIST@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(TRACE_URLS_LIST *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800019a4`
- `0x180002238`
- `0x1800032e0`

## callees

- `0x180001048`
- `0x180002428`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000246c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000246c`

## pseudocode

```c
void __fastcall TRACE_URLS_LIST::Dereference(TRACE_URLS_LIST *this)
{
  TRACE_URLS_LIST *v2; // rdi
  TRACE_URLS_LIST *v3; // rax
  TRACE_URLS_LIST **v4; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 && this )
  {
    while ( 1 )
    {
      v2 = *(TRACE_URLS_LIST **)this;
      if ( *(TRACE_URLS_LIST **)this == this )
        break;
      v3 = *(TRACE_URLS_LIST **)v2;
      if ( *(TRACE_URLS_LIST **)(*(_QWORD *)v2 + 8LL) != v2 || (v4 = (TRACE_URLS_LIST **)*((_QWORD *)v2 + 1), *v4 != v2) )
        __fastfail(3u);
      *v4 = v3;
      *((_QWORD *)v3 + 1) = v4;
      STRU::~STRU((TRACE_URLS_LIST *)((char *)v2 + 16));
      operator delete(v2);
    }
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180002428  mov     [rsp+arg_8], rbx
0x18000242d  push    rdi
0x18000242e  sub     rsp, 20h
0x180002432  mov     rbx, rcx
0x180002435  or      eax, 0FFFFFFFFh
0x180002438  lock xadd [rcx+10h], eax
0x18000243d  cmp     eax, 1
0x180002440  jnz     short loc_18000248B
0x180002442  test    rcx, rcx
0x180002445  jz      short loc_18000248B
0x180002447  mov     rdi, [rbx]
0x18000244a  cmp     rdi, rbx
0x18000244d  jz      short loc_180002483
0x18000244f  mov     rax, [rdi]
0x180002452  cmp     [rax+8], rdi
0x180002456  jnz     short loc_18000247C
0x180002458  mov     rcx, [rdi+8]
0x18000245c  cmp     [rcx], rdi
0x18000245f  jnz     short loc_18000247C
0x180002461  mov     [rcx], rax
0x180002464  mov     [rax+8], rcx
0x180002468  lea     rcx, [rdi+10h]
0x18000246c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002472  mov     rcx, rdi; Block
0x180002475  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000247a  jmp     short loc_180002447
0x18000247c  mov     ecx, 3
0x180002481  int     29h; Win8: RtlFailFast(ecx)
0x180002483  mov     rcx, rbx; Block
0x180002486  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000248b  mov     rbx, [rsp+28h+arg_8]
0x180002490  add     rsp, 20h
0x180002494  pop     rdi
0x180002495  retn
```
