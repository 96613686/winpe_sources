# MapIntToComparisonResult(int)

- ea: `0x180004e98`
- end: `0x180004ea9`
- name: `?MapIntToComparisonResult@@YA?AW4_comparisonresult@@H@Z`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800044cc`
- `0x180004eb0`

## callees

- `0x180004e98`

## pseudocode

```c
__int64 __fastcall MapIntToComparisonResult(int a1)
{
  if ( a1 >= 0 )
    return a1 > 0;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180004e98  test    ecx, ecx
0x180004e9a  jns     short loc_180004EA1
0x180004e9c  or      eax, 0FFFFFFFFh
0x180004e9f  retn
0x180004ea1  xor     eax, eax
0x180004ea3  test    ecx, ecx
0x180004ea5  setnle  al
0x180004ea8  retn
```
