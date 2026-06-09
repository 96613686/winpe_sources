# ATL::AtlThrowImpl(long)

- ea: `0x1800025a0`
- end: `0x1800025bf`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025c8`
- `0x180002b64`
- `0x180002e90`
- `0x180003128`
- `0x180003210`
- `0x180003310`
- `0x180003410`
- `0x180003b00`

## callees

- `0x180003ae8`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x1800025BELL);
}

```

## disassembly

```asm
0x1800025a0  sub     rsp, 28h
0x1800025a4  cmp     ecx, 8007000Eh
0x1800025aa  mov     eax, 0C000001Dh
0x1800025af  mov     edx, 0C0000017h; unsigned int
0x1800025b4  cmovz   eax, edx
0x1800025b7  mov     ecx, eax; unsigned int
0x1800025b9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
