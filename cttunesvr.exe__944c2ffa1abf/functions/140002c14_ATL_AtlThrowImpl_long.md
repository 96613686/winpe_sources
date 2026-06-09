# ATL::AtlThrowImpl(long)

- ea: `0x140002c14`
- end: `0x140002c33`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140002308`
- `0x1400025a4`
- `0x140002aa8`
- `0x140002adc`
- `0x140003abc`
- `0x140004128`
- `0x1400042ec`
- `0x140005384`
- `0x14000552c`
- `0x1400059e8`

## callees

- `0x14000522c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x140002C32LL);
}

```

## disassembly

```asm
0x140002c14  sub     rsp, 28h
0x140002c18  cmp     ecx, 8007000Eh
0x140002c1e  mov     eax, 0C000001Dh
0x140002c23  mov     edx, 0C0000017h; unsigned int
0x140002c28  cmovz   eax, edx
0x140002c2b  mov     ecx, eax; unsigned int
0x140002c2d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
