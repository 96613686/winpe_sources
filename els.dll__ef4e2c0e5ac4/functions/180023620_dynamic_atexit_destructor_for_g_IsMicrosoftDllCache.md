# _dynamic_atexit_destructor_for__g_IsMicrosoftDllCache__

- ea: `0x180023620`
- end: `0x1800236a9`
- name: `_dynamic_atexit_destructor_for__g_IsMicrosoftDllCache__`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004f68`
- `0x180023620`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002363b`
- `KERNEL32!EnterCriticalSection` at `0x18002363b`
- `KERNEL32!LeaveCriticalSection` at `0x180023690`
- `KERNEL32!LeaveCriticalSection` at `0x180023690`
- `KERNEL32!DeleteCriticalSection` at `0x1800236a2`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_IsMicrosoftDllCache__()
{
  CDLink *v0; // r9
  CDLink *v1; // rbx
  void (__fastcall ***v2)(_QWORD, __int64); // r9

  g_IsMicrosoftDllCache = &CLruCache::`vftable';
  EnterCriticalSection(&stru_18002F078);
  v0 = qword_18002F070;
  if ( qword_18002F070 )
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
  qword_18002F070 = 0;
  dword_18002F068 = 0;
  LeaveCriticalSection(&stru_18002F078);
  DeleteCriticalSection(&stru_18002F078);
}

```

## disassembly

```asm
0x180023620  push    rbx
0x180023622  sub     rsp, 20h
0x180023626  lea     rax, ??_7CLruCache@@6B@; const CLruCache::`vftable'
0x18002362d  lea     rcx, stru_18002F078; lpCriticalSection
0x180023634  mov     cs:?g_IsMicrosoftDllCache@@3VCIsMicrosoftDllCache@@A, rax; CIsMicrosoftDllCache g_IsMicrosoftDllCache
0x18002363b  call    cs:__imp_EnterCriticalSection
0x180023641  mov     r9, cs:qword_18002F070
0x180023648  test    r9, r9
0x18002364b  jz      short loc_180023674
0x18002364d  mov     rbx, [r9+8]
0x180023651  mov     rcx, r9; this
0x180023654  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x180023659  mov     rcx, [r9]
0x18002365c  mov     edx, 1
0x180023661  mov     rax, [rcx]
0x180023664  mov     rcx, r9
0x180023667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002366c  mov     r9, rbx
0x18002366f  test    rbx, rbx
0x180023672  jnz     short loc_18002364D
0x180023674  lea     rcx, stru_18002F078; lpCriticalSection
0x18002367b  mov     cs:qword_18002F070, 0
0x180023686  mov     cs:dword_18002F068, 0
0x180023690  call    cs:__imp_LeaveCriticalSection
0x180023696  lea     rcx, stru_18002F078
0x18002369d  add     rsp, 20h
0x1800236a1  pop     rbx
0x1800236a2  jmp     cs:__imp_DeleteCriticalSection
```
