# ATL::CSimpleStringT<ushort,0>::SetLength(int)

- ea: `0x18000ba44`
- end: `0x18000ba73`
- name: `?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dd0`
- `0x180007644`
- `0x18000b998`
- `0x18000ec74`

## callees

- `0x18000b48c`
- `0x18000ba44`

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
0x18000ba44  sub     rsp, 28h
0x18000ba48  test    edx, edx
0x18000ba4a  js      short loc_18000BA68
0x18000ba4c  mov     rax, [rcx]
0x18000ba4f  cmp     edx, [rax-0Ch]
0x18000ba52  jg      short loc_18000BA68
0x18000ba54  mov     [rax-10h], edx
0x18000ba57  xor     eax, eax
0x18000ba59  mov     rcx, [rcx]
0x18000ba5c  movsxd  rdx, edx
0x18000ba5f  mov     [rcx+rdx*2], ax
0x18000ba63  add     rsp, 28h
0x18000ba67  retn
0x18000ba68  mov     ecx, 80070057h; int
0x18000ba6d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
