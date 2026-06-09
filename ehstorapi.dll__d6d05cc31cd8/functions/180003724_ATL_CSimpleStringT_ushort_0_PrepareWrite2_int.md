# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180003724`
- end: `0x18000378a`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000394c`
- `0x180006528`
- `0x1800079d0`
- `0x180008a7c`

## callees

- `0x180002660`
- `0x180003724`
- `0x1800037a8`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  int v3; // r8d
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // eax
  int v7; // eax

  v3 = a2;
  v4 = *a1;
  if ( *(_DWORD *)(v4 - 16) > a2 )
    v3 = *(_DWORD *)(v4 - 16);
  if ( *(int *)(v4 - 8) <= 1 )
  {
    v5 = *(_DWORD *)(v4 - 12);
    if ( v5 < v3 )
    {
      if ( v5 <= 0x40000000 )
        v6 = v5 / 2;
      else
        v6 = 0x100000;
      v7 = v5 + v6;
      if ( v7 >= v3 )
        v3 = v7;
      ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)v3);
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x180003724  sub     rsp, 28h
0x180003728  mov     r9, rcx
0x18000372b  mov     r8d, edx
0x18000372e  mov     rcx, [rcx]
0x180003731  cmp     [rcx-10h], edx
0x180003734  cmovg   r8d, [rcx-10h]
0x180003739  cmp     dword ptr [rcx-8], 1
0x18000373d  jle     short loc_18000374E
0x18000373f  mov     edx, r8d
0x180003742  mov     rcx, r9
0x180003745  add     rsp, 28h
0x180003749  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000374e  mov     ecx, [rcx-0Ch]
0x180003751  cmp     ecx, r8d
0x180003754  jge     short loc_180003785
0x180003756  cmp     ecx, 40000000h
0x18000375c  jle     short loc_180003765
0x18000375e  mov     eax, 100000h
0x180003763  jmp     short loc_180003771
0x180003765  mov     eax, ecx
0x180003767  mov     r10d, 2
0x18000376d  cdq
0x18000376e  idiv    r10d
0x180003771  add     eax, ecx
0x180003773  mov     rcx, r9
0x180003776  cmp     eax, r8d
0x180003779  cmovge  r8d, eax
0x18000377d  mov     edx, r8d
0x180003780  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180003785  add     rsp, 28h
0x180003789  retn
```
