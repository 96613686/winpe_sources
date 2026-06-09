# CreateNewAdvertisingId

- ea: `0x180009a20`
- end: `0x180009a25`
- name: `CreateNewAdvertisingId`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006274`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CreateNewAdvertisingId(AdvertisingIdHelpers *this, const unsigned __int16 *a2, HKEY *a3)
{
  return AdvertisingIdHelpers::CreateNewAdvertisingId(this, a2, a3);
}

```

## disassembly

```asm
0x180009a20  jmp     ?CreateNewAdvertisingId@AdvertisingIdHelpers@@YAJPEBG@Z; AdvertisingIdHelpers::CreateNewAdvertisingId(ushort const *)
```
