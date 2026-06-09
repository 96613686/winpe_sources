# CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_Action(void const *,void *)

- ea: `0x1800033d0`
- end: `0x1800033dd`
- name: `?_Action@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_Action(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(a2 + 8))(a1, *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x1800033d0  mov     rax, [rdx+8]
0x1800033d4  mov     rdx, [rdx+10h]
0x1800033d8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
