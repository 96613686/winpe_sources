# ATL::AtlThrowImpl(long)

- ea: `0x18000397c`
- end: `0x18000399b`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029fc`
- `0x180002d44`
- `0x180003248`
- `0x18000327c`
- `0x1800034c0`
- `0x18000420c`
- `0x180004818`
- `0x1800049dc`

## callees

- `0x180005afc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x18000399ALL);
}

```

## disassembly

```asm
0x18000397c  sub     rsp, 28h
0x180003980  cmp     ecx, 8007000Eh
0x180003986  mov     eax, 0C000001Dh
0x18000398b  mov     edx, 0C0000017h; unsigned int
0x180003990  cmovz   eax, edx
0x180003993  mov     ecx, eax; unsigned int
0x180003995  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
