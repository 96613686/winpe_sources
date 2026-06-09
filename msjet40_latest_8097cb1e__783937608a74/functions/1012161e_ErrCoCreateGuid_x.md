# ErrCoCreateGuid(x)

- ea: `0x1012161e`
- end: `0x10121658`
- name: `_ErrCoCreateGuid@4`
- size: `58`
- prototype: `int __thiscall(GUID *pguid)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10114316`
- `0x10119b00`

## callees

- `0x1012161e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10121624`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x10121624`

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
0x1012161e  mov     edi, edi
0x10121620  push    esi
0x10121621  push    ecx; pguid
0x10121622  xor     esi, esi
0x10121624  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x1012162a  test    eax, eax
0x1012162c  jz      short loc_10121654
0x1012162e  cmp     eax, 80004005h
0x10121633  jz      short loc_1012164F
0x10121635  cmp     eax, 8000FFFFh
0x1012163a  jz      short loc_1012164F
0x1012163c  cmp     eax, 80040151h
0x10121641  jz      short loc_1012164F
0x10121643  mov     esi, 0FFFFFC0Dh
0x10121648  cmp     eax, 8007000Eh
0x1012164d  jz      short loc_10121654
0x1012164f  mov     esi, 0FFFFB1C0h
0x10121654  mov     eax, esi
0x10121656  pop     esi
0x10121657  retn
```
