# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x180003a40`
- end: `0x180003a4f`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002660`
- `0x1800037a8`
- `0x180004194`
- `0x1800080cc`

## callees

- `0x180002338`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x180003a40  sub     rsp, 28h
0x180003a44  mov     ecx, 8007000Eh; int
0x180003a49  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
