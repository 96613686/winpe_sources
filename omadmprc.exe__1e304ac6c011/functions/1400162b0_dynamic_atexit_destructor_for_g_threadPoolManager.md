# _dynamic_atexit_destructor_for__g_threadPoolManager__

- ea: `0x1400162b0`
- end: `0x1400162e1`
- name: `_dynamic_atexit_destructor_for__g_threadPoolManager__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400162b0`
- `0x140017010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__g_threadPoolManager__()
{
  __int64 (__fastcall ***v0)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v0 = (__int64 (__fastcall ***)(_QWORD, __int64))qword_140024308;
  qword_140024308 = 0;
  if ( v0 )
    return (**v0)(v0, 1);
  return result;
}

```

## disassembly

```asm
0x1400162b0  sub     rsp, 28h
0x1400162b4  mov     rcx, cs:qword_140024308
0x1400162bb  mov     cs:qword_140024308, 0
0x1400162c6  test    rcx, rcx
0x1400162c9  jz      short loc_1400162DB
0x1400162cb  mov     rax, [rcx]
0x1400162ce  mov     edx, 1
0x1400162d3  mov     rax, [rax]
0x1400162d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162db  add     rsp, 28h
0x1400162df  retn
```
