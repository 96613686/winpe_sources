# DavDisplayTypeToUsage

- ea: `0x180009b70`
- end: `0x180009b9e`
- name: `DavDisplayTypeToUsage`
- size: `46`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001600`
- `0x180004340`
- `0x18000f7f0`

## callees

- `0x180009b70`

## pseudocode

```c
__int64 __fastcall DavDisplayTypeToUsage(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx

  if ( a1 == 2 )
    return 2;
  v1 = a1 - 1;
  if ( !v1 )
    return 2;
  v2 = v1 - 2;
  if ( !v2 )
    return 5;
  v3 = v2 - 3;
  if ( !v3 )
    return 2;
  if ( v3 == 2 )
    return 4;
  return 0;
}

```

## disassembly

```asm
0x180009b70  cmp     ecx, 2
0x180009b73  jz      short loc_180009B98
0x180009b75  sub     ecx, 1
0x180009b78  jz      short loc_180009B98
0x180009b7a  sub     ecx, 2
0x180009b7d  jz      short loc_180009B92
0x180009b7f  sub     ecx, 3
0x180009b82  jz      short loc_180009B98
0x180009b84  cmp     ecx, 2
0x180009b87  jz      short loc_180009B8C
0x180009b89  xor     eax, eax
0x180009b8b  retn
0x180009b8c  mov     eax, 4
0x180009b91  retn
0x180009b92  mov     eax, 5
0x180009b97  retn
0x180009b98  mov     eax, 2
0x180009b9d  retn
```
