# _dynamic_atexit_destructor_for__g_DirSearchCache__

- ea: `0x1800236b0`
- end: `0x180023739`
- name: `_dynamic_atexit_destructor_for__g_DirSearchCache__`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004f68`
- `0x1800236b0`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800236cb`
- `KERNEL32!EnterCriticalSection` at `0x1800236cb`
- `KERNEL32!LeaveCriticalSection` at `0x180023720`
- `KERNEL32!LeaveCriticalSection` at `0x180023720`
- `KERNEL32!DeleteCriticalSection` at `0x180023732`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_DirSearchCache__()
{
  CDLink *v0; // r9
  CDLink *v1; // rbx
  void (__fastcall ***v2)(_QWORD, __int64); // r9

  g_DirSearchCache = &CLruCache::`vftable';
  EnterCriticalSection(&stru_18002F0B8);
  v0 = qword_18002F0B0;
  if ( qword_18002F0B0 )
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
  qword_18002F0B0 = 0;
  dword_18002F0A8 = 0;
  LeaveCriticalSection(&stru_18002F0B8);
  DeleteCriticalSection(&stru_18002F0B8);
}

```

## disassembly

```asm
0x1800236b0  push    rbx
0x1800236b2  sub     rsp, 20h
0x1800236b6  lea     rax, ??_7CLruCache@@6B@; const CLruCache::`vftable'
0x1800236bd  lea     rcx, stru_18002F0B8; lpCriticalSection
0x1800236c4  mov     cs:?g_DirSearchCache@@3VCIDsCache@@A, rax; CIDsCache g_DirSearchCache
0x1800236cb  call    cs:__imp_EnterCriticalSection
0x1800236d1  mov     r9, cs:qword_18002F0B0
0x1800236d8  test    r9, r9
0x1800236db  jz      short loc_180023704
0x1800236dd  mov     rbx, [r9+8]
0x1800236e1  mov     rcx, r9; this
0x1800236e4  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x1800236e9  mov     rcx, [r9]
0x1800236ec  mov     edx, 1
0x1800236f1  mov     rax, [rcx]
0x1800236f4  mov     rcx, r9
0x1800236f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236fc  mov     r9, rbx
0x1800236ff  test    rbx, rbx
0x180023702  jnz     short loc_1800236DD
0x180023704  lea     rcx, stru_18002F0B8; lpCriticalSection
0x18002370b  mov     cs:qword_18002F0B0, 0
0x180023716  mov     cs:dword_18002F0A8, 0
0x180023720  call    cs:__imp_LeaveCriticalSection
0x180023726  lea     rcx, stru_18002F0B8
0x18002372d  add     rsp, 20h
0x180023731  pop     rbx
0x180023732  jmp     cs:__imp_DeleteCriticalSection
```
