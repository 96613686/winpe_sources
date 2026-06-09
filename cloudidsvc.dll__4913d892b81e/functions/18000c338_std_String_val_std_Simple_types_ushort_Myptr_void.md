# std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)

- ea: `0x18000c338`
- end: `0x18000c350`
- name: `?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ`
- size: `24`
- prototype: `__int64()`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087c8`
- `0x180008c18`
- `0x180008d64`
- `0x180009d60`
- `0x18000ab30`
- `0x18000ac08`
- `0x18000b1d0`
- `0x18000b67c`
- `0x18000ba60`
- `0x18000c750`
- `0x18000c784`
- `0x18000d114`
- `0x18000d694`
- `0x18000de34`
- `0x18000dfcc`
- `0x18000e0b0`
- `0x18000e668`
- `0x18000e8e8`
- `0x18000eaf4`
- `0x18000ed90`
- `0x18000f7cc`
- `0x18000fd90`
- `0x18000fea0`

## callees

- `0x18000c2b8`
- `0x18000c338`

## pseudocode

```c
__int64 std::_String_val<std::_Simple_types<unsigned short>>::_Myptr()
{
  __int64 v0; // rcx

  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged() )
    return *(_QWORD *)v0;
  return v0;
}

```

## disassembly

```asm
0x18000c338  sub     rsp, 28h
0x18000c33c  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18000c341  test    al, al
0x18000c343  jz      short loc_18000C348
0x18000c345  mov     rcx, [rcx]
0x18000c348  mov     rax, rcx
0x18000c34b  add     rsp, 28h
0x18000c34f  retn
```
