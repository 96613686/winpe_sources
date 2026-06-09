# ATL::AtlHresultFromWin32(ulong)

- ea: `0x140002bfc`
- end: `0x140002c0c`
- name: `?AtlHresultFromWin32@ATL@@YAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400025a4`
- `0x1400042ec`

## callees

- `0x140002bfc`

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
0x140002bfc  test    ecx, ecx
0x140002bfe  jle     short loc_140002C09
0x140002c00  movzx   ecx, cx
0x140002c03  or      ecx, 80070000h
0x140002c09  mov     eax, ecx
0x140002c0b  retn
```
