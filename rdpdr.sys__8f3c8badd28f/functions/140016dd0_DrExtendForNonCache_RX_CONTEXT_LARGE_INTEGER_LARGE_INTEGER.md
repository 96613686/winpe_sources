# DrExtendForNonCache(_RX_CONTEXT *,_LARGE_INTEGER *,_LARGE_INTEGER *)

- ea: `0x140016dd0`
- end: `0x140016dd9`
- name: `?DrExtendForNonCache@@YAJPEAU_RX_CONTEXT@@PEAT_LARGE_INTEGER@@1@Z`
- size: `9`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *, union _LARGE_INTEGER *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall DrExtendForNonCache(struct _RX_CONTEXT *a1, union _LARGE_INTEGER *a2, union _LARGE_INTEGER *a3)
{
  *a3 = *a2;
  return 0;
}

```

## disassembly

```asm
0x140016dd0  mov     rax, [rdx]
0x140016dd3  mov     [r8], rax
0x140016dd6  xor     eax, eax
0x140016dd8  retn
```
