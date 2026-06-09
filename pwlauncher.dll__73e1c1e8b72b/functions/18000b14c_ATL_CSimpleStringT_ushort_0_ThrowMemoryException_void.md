# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x18000b14c`
- end: `0x18000b15b`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c58`
- `0x180009d58`
- `0x180009e04`
- `0x18000ab40`

## callees

- `0x18000374c`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x18000b14c  sub     rsp, 28h
0x18000b150  mov     ecx, 8007000Eh; int
0x18000b155  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
