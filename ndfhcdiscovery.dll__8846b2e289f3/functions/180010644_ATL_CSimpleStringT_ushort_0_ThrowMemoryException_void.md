# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x180010644`
- end: `0x180010653`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d240`
- `0x180010510`
- `0x180011dac`
- `0x180011e48`

## callees

- `0x1800068ec`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x180010644  sub     rsp, 28h
0x180010648  mov     ecx, 8007000Eh; int
0x18001064d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
