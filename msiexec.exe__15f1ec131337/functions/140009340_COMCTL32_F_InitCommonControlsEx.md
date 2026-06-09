# COMCTL32::F_InitCommonControlsEx

- ea: `0x140009340`
- end: `0x14000935b`
- name: `COMCTL32::F_InitCommonControlsEx`
- size: `27`
- prototype: `__int64 __fastcall(const char *, __int64 (**)(void), __int64 (*)(void))`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140008cc8`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall COMCTL32::F_InitCommonControlsEx(const char *a1, __int64 (**a2)(void), __int64 (*a3)(void))
{
  int (*v4)(struct tagINITCOMMONCONTROLSEX *); // rax

  v4 = BindOpt_COMCTL32(a1, a2, a3);
  return ((__int64 (__fastcall *)(const char *))v4)(a1);
}

```

## disassembly

```asm
0x140009340  push    rbx
0x140009342  sub     rsp, 20h
0x140009346  mov     rbx, rcx
0x140009349  call    ?BindOpt_COMCTL32@@YAP6A_JXZPEBDPEAP6A_JXZP6A_JXZ@Z; BindOpt_COMCTL32(char const *,__int64 (**)(void),__int64 (*)(void))
0x14000934e  mov     rcx, rbx
0x140009351  add     rsp, 20h
0x140009355  pop     rbx
0x140009356  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
