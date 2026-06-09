# ATL::AtlHresultFromWin32(ulong)

- ea: `0x1800034a8`
- end: `0x1800034b8`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d44`
- `0x1800049dc`

## callees

- `0x1800034a8`

## pseudocode

```c
__int64 __fastcall ATL::AtlHresultFromWin32(int a1)
{
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1800034a8  test    ecx, ecx
0x1800034aa  jle     short loc_1800034B5
0x1800034ac  movzx   ecx, cx
0x1800034af  or      ecx, 80070000h
0x1800034b5  mov     eax, ecx
0x1800034b7  retn
```
