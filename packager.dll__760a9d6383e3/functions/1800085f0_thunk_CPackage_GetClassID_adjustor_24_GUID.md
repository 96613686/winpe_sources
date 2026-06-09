# [thunk]:CPackage::GetClassID`adjustor{24}' (_GUID *)

- ea: `0x1800085f0`
- end: `0x1800085f9`
- name: `?GetClassID@CPackage@@WBI@EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall CPackage::GetClassID(__int64 a1, struct _GUID *a2)
{
  return CPackage::GetClassID((CPackage *)(a1 - 24), a2);
}

```

## disassembly

```asm
0x1800085f0  sub     rcx, 18h; this
0x1800085f4  jmp     ?GetClassID@CPackage@@UEAAJPEAU_GUID@@@Z; CPackage::GetClassID(_GUID *)
```
