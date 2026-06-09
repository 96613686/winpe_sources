# Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(void)

- ea: `0x18000b010`
- end: `0x18000b01f`
- name: `??1?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAA@XZ`
- size: `15`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014662`

## callees

- `0x18000eae0`

## pseudocode

```c
__int64 __fastcall Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(
        __int64 a1)
{
  return Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(a1);
}

```

## disassembly

```asm
0x18000b010  sub     rsp, 28h
0x18000b014  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x18000b019  nop
0x18000b01a  add     rsp, 28h
0x18000b01e  retn
```
