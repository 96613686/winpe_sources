# _dynamic_atexit_destructor_for__g_DllCache__

- ea: `0x180023500`
- end: `0x180023589`
- name: `_dynamic_atexit_destructor_for__g_DllCache__`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004f68`
- `0x180023500`
- `0x180024010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002351b`
- `KERNEL32!EnterCriticalSection` at `0x18002351b`
- `KERNEL32!LeaveCriticalSection` at `0x180023570`
- `KERNEL32!LeaveCriticalSection` at `0x180023570`
- `KERNEL32!DeleteCriticalSection` at `0x180023582`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_DllCache__()
{
  CDLink *v0; // r9
  CDLink *v1; // rbx
  void (__fastcall ***v2)(_QWORD, __int64); // r9

  g_DllCache = &CLruCache::`vftable';
  EnterCriticalSection(&stru_18002F138);
  v0 = qword_18002F130;
  if ( qword_18002F130 )
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
  qword_18002F130 = 0;
  dword_18002F128 = 0;
  LeaveCriticalSection(&stru_18002F138);
  DeleteCriticalSection(&stru_18002F138);
}

```

## disassembly

```asm
0x180023500  push    rbx
0x180023502  sub     rsp, 20h
0x180023506  lea     rax, ??_7CLruCache@@6B@; const CLruCache::`vftable'
0x18002350d  lea     rcx, stru_18002F138; lpCriticalSection
0x180023514  mov     cs:?g_DllCache@@3VCDllCache@@A, rax; CDllCache g_DllCache
0x18002351b  call    cs:__imp_EnterCriticalSection
0x180023521  mov     r9, cs:qword_18002F130
0x180023528  test    r9, r9
0x18002352b  jz      short loc_180023554
0x18002352d  mov     rbx, [r9+8]
0x180023531  mov     rcx, r9; this
0x180023534  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x180023539  mov     rcx, [r9]
0x18002353c  mov     edx, 1
0x180023541  mov     rax, [rcx]
0x180023544  mov     rcx, r9
0x180023547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002354c  mov     r9, rbx
0x18002354f  test    rbx, rbx
0x180023552  jnz     short loc_18002352D
0x180023554  lea     rcx, stru_18002F138; lpCriticalSection
0x18002355b  mov     cs:qword_18002F130, 0
0x180023566  mov     cs:dword_18002F128, 0
0x180023570  call    cs:__imp_LeaveCriticalSection
0x180023576  lea     rcx, stru_18002F138
0x18002357d  add     rsp, 20h
0x180023581  pop     rbx
0x180023582  jmp     cs:__imp_DeleteCriticalSection
```
