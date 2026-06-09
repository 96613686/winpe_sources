# ATL::AtlThrowImpl(long)

- ea: `0x1400045e4`
- end: `0x140004603`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400044cc`
- `0x140004bb0`
- `0x14000c654`
- `0x14000cb58`
- `0x14000d138`
- `0x14000d708`
- `0x14000d8cc`
- `0x14000eb64`

## callees

- `0x140009858`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x140004602LL);
}

```

## disassembly

```asm
0x1400045e4  sub     rsp, 28h
0x1400045e8  cmp     ecx, 8007000Eh
0x1400045ee  mov     eax, 0C000001Dh
0x1400045f3  mov     edx, 0C0000017h; unsigned int
0x1400045f8  cmovz   eax, edx
0x1400045fb  mov     ecx, eax; unsigned int
0x1400045fd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
