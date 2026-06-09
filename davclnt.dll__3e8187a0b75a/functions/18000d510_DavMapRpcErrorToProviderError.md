# DavMapRpcErrorToProviderError

- ea: `0x18000d510`
- end: `0x18000d5e7`
- name: `DavMapRpcErrorToProviderError`
- size: `215`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180001310`
- `0x180001600`
- `0x180003b90`
- `0x180007ad0`
- `0x18000b4f0`
- `0x18000c170`
- `0x18000c7e0`
- `0x18000cb10`
- `0x18000ceb0`
- `0x18000e494`
- `0x18000f2d0`
- `0x18000fd30`

## callees

- `0x18000d510`

## pseudocode

```c
__int64 __fastcall DavMapRpcErrorToProviderError(unsigned int a1)
{
  __int64 result; // rax

  if ( a1 <= 0x6A6 )
  {
    if ( a1 != 1702 && a1 != 6 )
    {
      if ( a1 == 51 )
        return 67;
      if ( a1 != 59 )
      {
        if ( a1 == 85 )
          return 85;
        if ( a1 == 86 )
          return 86;
        if ( a1 != 87 )
        {
          switch ( a1 )
          {
            case 0x3E6u:
              return 487;
            case 0x490u:
              return 2250;
            case 0x4B0u:
              return 1200;
          }
          return a1;
        }
        return 87;
      }
      return 1222;
    }
    return 6;
  }
  switch ( a1 )
  {
    case 0x6B5u:
    case 0x6BAu:
    case 0x6D9u:
      return 1222;
    case 0x6EFu:
    case 0x6F1u:
    case 0x6F2u:
      return 6;
    case 0x6F4u:
      return 87;
  }
  result = 2401;
  if ( a1 != 2401 )
  {
    result = 487;
    if ( a1 != -1073741819 )
      return a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000d510  mov     eax, 6A6h
0x18000d515  cmp     ecx, eax
0x18000d517  ja      short loc_18000D585
0x18000d519  jz      loc_18000D5DB
0x18000d51f  mov     eax, ecx
0x18000d521  sub     eax, 6
0x18000d524  jz      loc_18000D5DB
0x18000d52a  sub     eax, 2Dh ; '-'
0x18000d52d  jz      short loc_18000D57F
0x18000d52f  sub     eax, 8
0x18000d532  jz      loc_18000D5E1
0x18000d538  sub     eax, 1Ah
0x18000d53b  jz      short loc_18000D579
0x18000d53d  sub     eax, 1
0x18000d540  jz      short loc_18000D573
0x18000d542  sub     eax, 1
0x18000d545  jz      loc_18000D5D5
0x18000d54b  sub     eax, 38Fh
0x18000d550  jz      short loc_18000D56D
0x18000d552  sub     eax, 0AAh
0x18000d557  jz      short loc_18000D567
0x18000d559  cmp     eax, 20h ; ' '
0x18000d55c  jz      short loc_18000D561
0x18000d55e  mov     eax, ecx
0x18000d560  retn
0x18000d561  mov     eax, 4B0h
0x18000d566  retn
0x18000d567  mov     eax, 8CAh
0x18000d56c  retn
0x18000d56d  mov     eax, 1E7h
0x18000d572  retn
0x18000d573  mov     eax, 56h ; 'V'
0x18000d578  retn
0x18000d579  mov     eax, 55h ; 'U'
0x18000d57e  retn
0x18000d57f  mov     eax, 43h ; 'C'
0x18000d584  retn
0x18000d585  cmp     ecx, 6B5h
0x18000d58b  jz      short loc_18000D5E1
0x18000d58d  cmp     ecx, 6BAh
0x18000d593  jz      short loc_18000D5E1
0x18000d595  cmp     ecx, 6D9h
0x18000d59b  jz      short loc_18000D5E1
0x18000d59d  cmp     ecx, 6EFh
0x18000d5a3  jz      short loc_18000D5DB
0x18000d5a5  cmp     ecx, 6F1h
0x18000d5ab  jz      short loc_18000D5DB
0x18000d5ad  cmp     ecx, 6F2h
0x18000d5b3  jz      short loc_18000D5DB
0x18000d5b5  cmp     ecx, 6F4h
0x18000d5bb  jz      short loc_18000D5D5
0x18000d5bd  mov     eax, 961h
0x18000d5c2  cmp     ecx, eax
0x18000d5c4  jz      short locret_18000D5E6
0x18000d5c6  cmp     ecx, 0C0000005h
0x18000d5cc  mov     eax, 1E7h
0x18000d5d1  cmovnz  eax, ecx
0x18000d5d4  retn
0x18000d5d5  mov     eax, 57h ; 'W'
0x18000d5da  retn
0x18000d5db  mov     eax, 6
0x18000d5e0  retn
0x18000d5e1  mov     eax, 4C6h
0x18000d5e6  retn
```
