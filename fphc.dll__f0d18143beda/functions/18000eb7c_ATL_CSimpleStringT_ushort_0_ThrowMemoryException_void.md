# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x18000eb7c`
- end: `0x18000eb8b`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d5d4`
- `0x18000dbdc`
- `0x18000dc68`
- `0x18000e5a8`

## callees

- `0x180004048`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x18000eb7c  sub     rsp, 28h
0x18000eb80  mov     ecx, 8007000Eh; int
0x18000eb85  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
