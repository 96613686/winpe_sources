# COMCTL32::E_InitCommonControlsEx

- ea: `0x140008fd0`
- end: `0x140008fea`
- name: `COMCTL32::E_InitCommonControlsEx`
- size: `26`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a010`

## pseudocode

```c
__int64 COMCTL32::E_InitCommonControlsEx()
{
  COMCTL32::InitCommonControls();
  return 1;
}

```

## disassembly

```asm
0x140008fd0  sub     rsp, 28h
0x140008fd4  mov     rax, cs:?InitCommonControls@COMCTL32@@3P6AXXZEA; void (*COMCTL32::InitCommonControls)(void)
0x140008fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fe0  mov     eax, 1
0x140008fe5  add     rsp, 28h
0x140008fe9  retn
```
