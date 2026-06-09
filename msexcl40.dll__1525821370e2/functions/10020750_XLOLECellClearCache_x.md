# XLOLECellClearCache(x)

- ea: `0x10020750`
- end: `0x10020773`
- name: `_XLOLECellClearCache@4`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10020e70`

## callees

- `0x10020750`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1002075d`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1002075d`

## pseudocode

```c
HRESULT __thiscall XLOLECellClearCache(_DWORD *this)
{
  HRESULT result; // eax

  result = this[6];
  if ( result )
  {
    result = SafeArrayDestroy((SAFEARRAY *)this[6]);
    this[6] = 0;
  }
  this[4] = -1;
  return result;
}

```

## disassembly

```asm
0x10020750  mov     edi, edi
0x10020752  push    esi
0x10020753  mov     esi, ecx
0x10020755  mov     eax, [esi+18h]
0x10020758  test    eax, eax
0x1002075a  jz      short loc_1002076A
0x1002075c  push    eax; psa
0x1002075d  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x10020763  mov     dword ptr [esi+18h], 0
0x1002076a  mov     dword ptr [esi+10h], 0FFFFFFFFh
0x10020771  pop     esi
0x10020772  retn
```
