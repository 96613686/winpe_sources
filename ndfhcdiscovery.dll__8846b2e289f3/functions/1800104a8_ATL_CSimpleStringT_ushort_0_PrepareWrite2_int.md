# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x1800104a8`
- end: `0x18001050a`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce9c`
- `0x18000d2f0`
- `0x18001032c`

## callees

- `0x18000d240`
- `0x1800104a8`
- `0x180010510`

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
0x1800104a8  sub     rsp, 28h
0x1800104ac  mov     r9, rcx
0x1800104af  mov     r8d, edx
0x1800104b2  mov     rcx, [rcx]
0x1800104b5  cmp     [rcx-10h], edx
0x1800104b8  cmovg   r8d, [rcx-10h]
0x1800104bd  cmp     dword ptr [rcx-8], 1
0x1800104c1  jle     short loc_1800104D2
0x1800104c3  mov     edx, r8d
0x1800104c6  mov     rcx, r9
0x1800104c9  add     rsp, 28h
0x1800104cd  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800104d2  mov     ecx, [rcx-0Ch]
0x1800104d5  cmp     ecx, r8d
0x1800104d8  jge     short loc_180010504
0x1800104da  cmp     ecx, 40000000h
0x1800104e0  jle     short loc_1800104E9
0x1800104e2  mov     eax, 100000h
0x1800104e7  jmp     short loc_1800104F0
0x1800104e9  mov     eax, ecx
0x1800104eb  cdq
0x1800104ec  sub     eax, edx
0x1800104ee  sar     eax, 1
0x1800104f0  add     eax, ecx
0x1800104f2  mov     rcx, r9
0x1800104f5  cmp     eax, r8d
0x1800104f8  cmovge  r8d, eax
0x1800104fc  mov     edx, r8d
0x1800104ff  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180010504  add     rsp, 28h
0x180010508  retn
```
