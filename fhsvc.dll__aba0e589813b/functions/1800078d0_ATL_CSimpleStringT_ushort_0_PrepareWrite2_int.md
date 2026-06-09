# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x1800078d0`
- end: `0x180007921`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `81`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180003390`
- `0x180006dd0`
- `0x180007720`
- `0x180007800`
- `0x18000b250`
- `0x18000b348`
- `0x18000b998`

## callees

- `0x1800078d0`
- `0x180007930`
- `0x18000dc50`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  __int64 v3; // rdx
  int v4; // r9d
  int v5; // eax
  int v6; // eax

  v3 = *a1;
  if ( *(_DWORD *)(*a1 - 16) > a2 )
    a2 = *(_DWORD *)(v3 - 16);
  if ( *(int *)(v3 - 8) <= 1 )
  {
    v4 = *(_DWORD *)(v3 - 12);
    if ( v4 < a2 )
    {
      if ( v4 <= 0x40000000 )
        v5 = v4 / 2;
      else
        v5 = 0x100000;
      v6 = v4 + v5;
      if ( v6 >= a2 )
        a2 = v6;
      ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)a2);
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)a2);
  }
}

```

## disassembly

```asm
0x1800078d0  mov     r8d, edx
0x1800078d3  mov     rdx, [rcx]
0x1800078d6  cmp     [rdx-10h], r8d
0x1800078da  cmovg   r8d, [rdx-10h]
0x1800078df  cmp     dword ptr [rdx-8], 1
0x1800078e3  jle     short loc_1800078ED
0x1800078e5  mov     edx, r8d
0x1800078e8  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800078ed  mov     r9d, [rdx-0Ch]
0x1800078f1  cmp     r9d, r8d
0x1800078f4  jge     short locret_180007920
0x1800078f6  cmp     r9d, 40000000h
0x1800078fd  jle     short loc_180007906
0x1800078ff  mov     eax, 100000h
0x180007904  jmp     short loc_18000790E
0x180007906  mov     eax, r9d
0x180007909  cdq
0x18000790a  sub     eax, edx
0x18000790c  sar     eax, 1
0x18000790e  add     eax, r9d
0x180007911  cmp     eax, r8d
0x180007914  cmovge  r8d, eax
0x180007918  mov     edx, r8d
0x18000791b  jmp     ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180007920  retn
```
