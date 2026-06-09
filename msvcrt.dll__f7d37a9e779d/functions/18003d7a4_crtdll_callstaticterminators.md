# __crtdll_callstaticterminators

- ea: `0x18003d7a4`
- end: `0x18003d7d2`
- name: `__crtdll_callstaticterminators`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a24`

## callees

- `0x18003dba0`

## pseudocode

```c
void _crtdll_callstaticterminators()
{
  initterm((_PVFV *)&_xp_a, (_PVFV *)&_xp_z);
  initterm((_PVFV *)&_xt_a, (_PVFV *)&_xt_z);
}

```

## disassembly

```asm
0x18003d7a4  sub     rsp, 28h
0x18003d7a8  lea     rdx, __xp_z; Last
0x18003d7af  lea     rcx, __xp_a; First
0x18003d7b6  call    _initterm
0x18003d7bb  lea     rdx, __xt_z
0x18003d7c2  lea     rcx, __xt_a
0x18003d7c9  add     rsp, 28h
0x18003d7cd  jmp     _initterm
```
