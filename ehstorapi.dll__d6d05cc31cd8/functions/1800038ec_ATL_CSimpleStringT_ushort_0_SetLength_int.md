# ATL::CSimpleStringT<ushort,0>::SetLength(int)

- ea: `0x1800038ec`
- end: `0x18000391b`
- name: `?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `47`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000394c`
- `0x180006528`
- `0x1800080cc`
- `0x180008284`

## callees

- `0x180002338`
- `0x1800038ec`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetLength(_QWORD *a1, int a2)
{
  __int64 result; // rax

  if ( a2 < 0 || a2 > *(_DWORD *)(*a1 - 12LL) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16LL) = a2;
  result = 0;
  *(_WORD *)(*a1 + 2LL * a2) = 0;
  return result;
}

```

## disassembly

```asm
0x1800038ec  sub     rsp, 28h
0x1800038f0  test    edx, edx
0x1800038f2  js      short loc_180003910
0x1800038f4  mov     rax, [rcx]
0x1800038f7  cmp     edx, [rax-0Ch]
0x1800038fa  jg      short loc_180003910
0x1800038fc  mov     [rax-10h], edx
0x1800038ff  xor     eax, eax
0x180003901  mov     rcx, [rcx]
0x180003904  movsxd  rdx, edx
0x180003907  mov     [rcx+rdx*2], ax
0x18000390b  add     rsp, 28h
0x18000390f  retn
0x180003910  mov     ecx, 80070057h; int
0x180003915  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
