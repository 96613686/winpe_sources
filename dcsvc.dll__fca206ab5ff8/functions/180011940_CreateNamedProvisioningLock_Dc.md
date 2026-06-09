# CreateNamedProvisioningLock_Dc

- ea: `0x180011940`
- end: `0x180011945`
- name: `CreateNamedProvisioningLock_Dc`
- size: `5`
- prototype: `__int64 __fastcall(_DWORD *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010404`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CreateNamedProvisioningLock_Dc(
        _DWORD *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  return CreateNamedProvisioningLock(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180011940  jmp     ?CreateNamedProvisioningLock@@YAJPEAXPEBGPEAPEAG2@Z; CreateNamedProvisioningLock(void *,ushort const *,ushort * *,ushort * *)
```
