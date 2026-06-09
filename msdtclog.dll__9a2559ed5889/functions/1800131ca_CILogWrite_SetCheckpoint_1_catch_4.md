# _CILogWrite::SetCheckpoint_::_1_::catch$4

- ea: `0x1800131ca`
- end: `0x1800131f1`
- name: `_CILogWrite::SetCheckpoint_::_1_::catch$4`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogWrite::SetCheckpoint_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 184) = *(_DWORD *)(a2 + 84);
  return 0;
}

```

## disassembly

```asm
0x1800131ca  mov     [rsp+arg_8], rdx
0x1800131cf  push    rbp
0x1800131d0  sub     rsp, 50h
0x1800131d4  mov     rbp, rdx
0x1800131d7  mov     eax, [rbp+54h]
0x1800131da  mov     [rbp+0B8h], eax
0x1800131e0  mov     rax, 0
0x1800131ea  add     rsp, 50h
0x1800131ee  pop     rbp
0x1800131ef  retn
```
