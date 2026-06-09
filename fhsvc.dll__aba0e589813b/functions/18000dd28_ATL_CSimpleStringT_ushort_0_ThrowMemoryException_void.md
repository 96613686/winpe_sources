# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x18000dd28`
- end: `0x18000dd37`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006d38`
- `0x180007930`
- `0x18000dc50`
- `0x18000ec74`

## callees

- `0x18000b48c`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x18000dd28  sub     rsp, 28h
0x18000dd2c  mov     ecx, 8007000Eh; int
0x18000dd31  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
