# [thunk]:CHtmlIFilter::GetClassID`adjustor{8}' (_GUID *)

- ea: `0x18001db40`
- end: `0x18001db49`
- name: `?GetClassID@CHtmlIFilter@@W7EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001db20`

## pseudocode

```c
__int64 __fastcall CHtmlIFilter::GetClassID(__int64 a1, struct _GUID *a2)
{
  return CHtmlIFilter::GetClassID((CHtmlIFilter *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x18001db40  sub     rcx, 8; this
0x18001db44  jmp     ?GetClassID@CHtmlIFilter@@UEAAJPEAU_GUID@@@Z; CHtmlIFilter::GetClassID(_GUID *)
```
