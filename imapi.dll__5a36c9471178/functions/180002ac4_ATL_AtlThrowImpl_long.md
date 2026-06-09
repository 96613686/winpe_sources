# ATL::AtlThrowImpl(long)

- ea: `0x180002ac4`
- end: `0x180002ae3`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180002178`
- `0x180002454`
- `0x180002958`
- `0x18000298c`
- `0x18000326c`
- `0x180003878`
- `0x180003a3c`
- `0x180004848`
- `0x180004d50`
- `0x1800056e8`
- `0x180006e50`
- `0x180007420`
- `0x1800082ac`
- `0x18000b10c`
- `0x18000c330`
- `0x18000c9e0`
- `0x18000ce60`
- `0x18000d830`
- `0x18000ef90`
- `0x180015670`
- `0x1800165b4`

## callees

- `0x1800046fc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180002AE2LL);
}

```

## disassembly

```asm
0x180002ac4  sub     rsp, 28h
0x180002ac8  cmp     ecx, 8007000Eh
0x180002ace  mov     eax, 0C000001Dh
0x180002ad3  mov     edx, 0C0000017h; unsigned int
0x180002ad8  cmovz   eax, edx
0x180002adb  mov     ecx, eax; unsigned int
0x180002add  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
