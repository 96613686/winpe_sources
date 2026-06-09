# CSchedule::Release(void)

- ea: `0x1800073a0`
- end: `0x18000740f`
- name: `?Release@CSchedule@@UEAAKXZ`
- size: `111`
- prototype: `unsigned int __fastcall(CSchedule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800073a0`
- `0x180009f38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800073cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800073cf`

## pseudocode

```c
__int64 __fastcall CSchedule::Release(CSchedule *this)
{
  unsigned __int32 v2; // ebx
  void *v3; // rcx
  void *v4; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 18);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CSchedule::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v3 = (void *)*((_QWORD *)this + 7);
    if ( v3 )
      operator delete(v3);
    v4 = (void *)*((_QWORD *)this + 8);
    if ( v4 )
      operator delete(v4);
    _InterlockedDecrement((volatile signed __int32 *)&CDll::s_cObjs);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1800073a0  mov     [rsp+arg_0], rbx
0x1800073a5  push    rdi
0x1800073a6  sub     rsp, 20h
0x1800073aa  mov     rdi, rcx
0x1800073ad  mov     ebx, 0FFFFFFFFh
0x1800073b2  lock xadd [rcx+48h], ebx
0x1800073b7  sub     ebx, 1
0x1800073ba  jnz     short loc_1800073FB
0x1800073bc  test    rcx, rcx
0x1800073bf  jz      short loc_1800073FB
0x1800073c1  lea     rax, ??_7CSchedule@@6B@; const CSchedule::`vftable'
0x1800073c8  mov     [rcx], rax
0x1800073cb  add     rcx, 8; lpCriticalSection
0x1800073cf  call    cs:__imp_DeleteCriticalSection
0x1800073d5  mov     rcx, [rdi+38h]; Block
0x1800073d9  test    rcx, rcx
0x1800073dc  jnz     short loc_180007408
0x1800073de  mov     rcx, [rdi+40h]; Block
0x1800073e2  test    rcx, rcx
0x1800073e5  jz      short loc_1800073EC
0x1800073e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073ec  lock dec cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x1800073f3  mov     rcx, rdi; Block
0x1800073f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073fb  mov     eax, ebx
0x1800073fd  mov     rbx, [rsp+28h+arg_0]
0x180007402  add     rsp, 20h
0x180007406  pop     rdi
0x180007407  retn
0x180007408  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000740d  jmp     short loc_1800073DE
```
