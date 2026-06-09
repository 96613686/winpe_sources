# ATL::AtlThrowImpl(long)

- ea: `0x180004a90`
- end: `0x180004aaf`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff0`
- `0x180004314`
- `0x180004818`
- `0x18000484c`
- `0x180007310`
- `0x180008c0c`
- `0x180008dd0`

## callees

- `0x18000b3dc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  DWORD v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1);
  JUMPOUT(0x180004AAELL);
}

```

## disassembly

```asm
0x180004a90  sub     rsp, 28h
0x180004a94  cmp     ecx, 8007000Eh
0x180004a9a  mov     eax, 0C000001Dh
0x180004a9f  mov     edx, 0C0000017h; unsigned int
0x180004aa4  cmovz   eax, edx
0x180004aa7  mov     ecx, eax; unsigned int
0x180004aa9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
