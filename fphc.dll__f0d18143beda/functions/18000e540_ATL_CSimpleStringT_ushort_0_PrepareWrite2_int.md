# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000e540`
- end: `0x18000e5a1`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db3c`
- `0x18000dd44`
- `0x18000e470`
- `0x18000e5fc`
- `0x18000e7fc`

## callees

- `0x18000dc68`
- `0x18000e540`
- `0x18000e5a8`

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
0x18000e540  sub     rsp, 28h
0x18000e544  mov     r9, rcx
0x18000e547  mov     r8d, edx
0x18000e54a  mov     rcx, [rcx]
0x18000e54d  cmp     [rcx-10h], edx
0x18000e550  cmovg   r8d, [rcx-10h]
0x18000e555  cmp     dword ptr [rcx-8], 1
0x18000e559  jle     short loc_18000E56A
0x18000e55b  mov     edx, r8d
0x18000e55e  mov     rcx, r9
0x18000e561  add     rsp, 28h
0x18000e565  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000e56a  mov     ecx, [rcx-0Ch]
0x18000e56d  cmp     ecx, r8d
0x18000e570  jge     short loc_18000E59C
0x18000e572  cmp     ecx, 40000000h
0x18000e578  jle     short loc_18000E581
0x18000e57a  mov     eax, 100000h
0x18000e57f  jmp     short loc_18000E588
0x18000e581  mov     eax, ecx
0x18000e583  cdq
0x18000e584  sub     eax, edx
0x18000e586  sar     eax, 1
0x18000e588  add     eax, ecx
0x18000e58a  mov     rcx, r9
0x18000e58d  cmp     eax, r8d
0x18000e590  cmovge  r8d, eax
0x18000e594  mov     edx, r8d
0x18000e597  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000e59c  add     rsp, 28h
0x18000e5a0  retn
```
