# CRasCredential::GetComboBoxValueCount(ulong,ulong *,ulong *)

- ea: `0x180003b30`
- end: `0x180003b36`
- name: `?GetComboBoxValueCount@CRasCredential@@UEAAJKPEAK0@Z`
- size: `6`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CRasCredential::GetComboBoxValueCount(
        CRasCredential *this,
        __int64 a2,
        unsigned int *a3,
        unsigned int *a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180003b30  mov     eax, 80004001h
0x180003b35  retn
```
