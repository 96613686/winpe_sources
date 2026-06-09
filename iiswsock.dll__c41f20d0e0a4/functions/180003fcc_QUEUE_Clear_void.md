# QUEUE::Clear(void)

- ea: `0x180003fcc`
- end: `0x180004038`
- name: `?Clear@QUEUE@@QEAAXXZ`
- size: `108`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003180`
- `0x180003300`
- `0x1800059f0`

## callees

- `0x180003fcc`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003fd9`

## pseudocode

```c
void __fastcall QUEUE::Clear(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  _QWORD *p_Type; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rax
  _QWORD *v5; // rcx

  EnterCriticalSection(this);
  v2 = this + 1;
  while ( 1 )
  {
    p_Type = &v2->DebugInfo->Type;
    if ( (struct _RTL_CRITICAL_SECTION *)v2->DebugInfo == v2 )
      break;
    if ( (struct _RTL_CRITICAL_SECTION *)p_Type[1] != v2
      || (v4 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*p_Type, *(_QWORD **)(*p_Type + 8LL) != p_Type) )
    {
      __fastfail(3u);
    }
    v2->DebugInfo = v4;
    v5 = p_Type - 1;
    v4->CriticalSection = v2;
    HIDWORD(this[1].OwningThread) -= *((_DWORD *)v5 + 6);
    (*(void (__fastcall **)(_QWORD *, __int64))*v5)(v5, 1);
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180003fcc  mov     [rsp+arg_0], rbx
0x180003fd1  push    rdi
0x180003fd2  sub     rsp, 20h
0x180003fd6  mov     rdi, rcx
0x180003fd9  call    cs:__imp_EnterCriticalSection
0x180003fdf  lea     rbx, [rdi+28h]
0x180003fe3  mov     rcx, [rbx]
0x180003fe6  cmp     rcx, rbx
0x180003fe9  jz      short loc_180004024
0x180003feb  cmp     [rcx+8], rbx
0x180003fef  jnz     short loc_18000401D
0x180003ff1  mov     rax, [rcx]
0x180003ff4  cmp     [rax+8], rcx
0x180003ff8  jnz     short loc_18000401D
0x180003ffa  mov     [rbx], rax
0x180003ffd  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180004001  mov     [rax+8], rbx
0x180004005  mov     edx, 1
0x18000400a  mov     eax, [rcx+18h]
0x18000400d  sub     [rdi+3Ch], eax
0x180004010  mov     rax, [rcx]
0x180004013  mov     rax, [rax]
0x180004016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401b  jmp     short loc_180003FE3
0x18000401d  mov     ecx, 3
0x180004022  int     29h; Win8: RtlFailFast(ecx)
0x180004024  mov     rcx, rdi
0x180004027  mov     rbx, [rsp+28h+arg_0]
0x18000402c  add     rsp, 20h
0x180004030  pop     rdi
0x180004031  jmp     cs:__imp_LeaveCriticalSection
```
