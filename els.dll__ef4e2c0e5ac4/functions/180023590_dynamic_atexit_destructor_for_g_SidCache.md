# _dynamic_atexit_destructor_for__g_SidCache__

- ea: `0x180023590`
- end: `0x180023619`
- name: `_dynamic_atexit_destructor_for__g_SidCache__`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004f68`
- `0x180023590`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800235ab`
- `KERNEL32!EnterCriticalSection` at `0x1800235ab`
- `KERNEL32!LeaveCriticalSection` at `0x180023600`
- `KERNEL32!LeaveCriticalSection` at `0x180023600`
- `KERNEL32!DeleteCriticalSection` at `0x180023612`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_SidCache__()
{
  CDLink *v0; // r9
  CDLink *v1; // rbx
  void (__fastcall ***v2)(_QWORD, __int64); // r9

  g_SidCache = &CLruCache::`vftable';
  EnterCriticalSection(&CriticalSection);
  v0 = qword_18002F0F0;
  if ( qword_18002F0F0 )
  {
    do
    {
      v1 = (CDLink *)*((_QWORD *)v0 + 1);
      CDLink::UnLink(v0);
      (**v2)(v2, 1);
      v0 = v1;
    }
    while ( v1 );
  }
  qword_18002F0F0 = 0;
  dword_18002F0E8 = 0;
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180023590  push    rbx
0x180023592  sub     rsp, 20h
0x180023596  lea     rax, ??_7CLruCache@@6B@; const CLruCache::`vftable'
0x18002359d  lea     rcx, CriticalSection; lpCriticalSection
0x1800235a4  mov     cs:?g_SidCache@@3VCSidCache@@A, rax; CSidCache g_SidCache
0x1800235ab  call    cs:__imp_EnterCriticalSection
0x1800235b1  mov     r9, cs:qword_18002F0F0
0x1800235b8  test    r9, r9
0x1800235bb  jz      short loc_1800235E4
0x1800235bd  mov     rbx, [r9+8]
0x1800235c1  mov     rcx, r9; this
0x1800235c4  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x1800235c9  mov     rcx, [r9]
0x1800235cc  mov     edx, 1
0x1800235d1  mov     rax, [rcx]
0x1800235d4  mov     rcx, r9
0x1800235d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235dc  mov     r9, rbx
0x1800235df  test    rbx, rbx
0x1800235e2  jnz     short loc_1800235BD
0x1800235e4  lea     rcx, CriticalSection; lpCriticalSection
0x1800235eb  mov     cs:qword_18002F0F0, 0
0x1800235f6  mov     cs:dword_18002F0E8, 0
0x180023600  call    cs:__imp_LeaveCriticalSection
0x180023606  lea     rcx, CriticalSection
0x18002360d  add     rsp, 20h
0x180023611  pop     rbx
0x180023612  jmp     cs:__imp_DeleteCriticalSection
```
