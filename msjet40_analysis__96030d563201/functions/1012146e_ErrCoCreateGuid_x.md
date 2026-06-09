# ErrCoCreateGuid(x)

- ea: `0x1012146e`
- end: `0x101214a8`
- name: `_ErrCoCreateGuid@4`
- size: `58`
- prototype: `int __thiscall(GUID *pguid)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10114166`
- `0x10119950`

## callees

- `0x1012146e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10121474`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10121474`

## pseudocode

```c
int __thiscall ErrCoCreateGuid(GUID *pguid)
{
  int v1; // esi
  HRESULT Guid; // eax

  v1 = 0;
  Guid = CoCreateGuid(pguid);
  if ( Guid )
  {
    switch ( Guid )
    {
      case -2147467259:
        return -20032;
      case -2147418113:
        return -20032;
      case -2147221167:
        return -20032;
    }
    v1 = -1011;
    if ( Guid != -2147024882 )
      return -20032;
  }
  return v1;
}

```

## disassembly

```asm
0x1012146e  mov     edi, edi
0x10121470  push    esi
0x10121471  push    ecx; pguid
0x10121472  xor     esi, esi
0x10121474  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x1012147a  test    eax, eax
0x1012147c  jz      short loc_101214A4
0x1012147e  cmp     eax, 80004005h
0x10121483  jz      short loc_1012149F
0x10121485  cmp     eax, 8000FFFFh
0x1012148a  jz      short loc_1012149F
0x1012148c  cmp     eax, 80040151h
0x10121491  jz      short loc_1012149F
0x10121493  mov     esi, 0FFFFFC0Dh
0x10121498  cmp     eax, 8007000Eh
0x1012149d  jz      short loc_101214A4
0x1012149f  mov     esi, 0FFFFB1C0h
0x101214a4  mov     eax, esi
0x101214a6  pop     esi
0x101214a7  retn
```
