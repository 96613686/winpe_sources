# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x1400060c4`
- end: `0x140006125`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140005c80`
- `0x140005d70`
- `0x1400061dc`
- `0x1400062d0`
- `0x1400063bc`
- `0x14000651c`
- `0x14000813c`
- `0x1400081d8`
- `0x140008674`
- `0x140009398`
- `0x140009470`
- `0x14000d310`
- `0x14000d7a8`
- `0x14000e194`
- `0x1400125fc`
- `0x1400129ec`
- `0x140012acc`
- `0x140013278`
- `0x14001398c`
- `0x140013a44`
- `0x140013c8c`
- `0x140017f28`
- `0x14001e240`
- `0x140026b48`
- `0x140028c60`
- `0x14002b3c8`

## callees

- `0x140006020`
- `0x1400060c4`
- `0x14000612c`

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
0x1400060c4  sub     rsp, 28h
0x1400060c8  mov     r9, rcx
0x1400060cb  mov     r8d, edx
0x1400060ce  mov     rcx, [rcx]
0x1400060d1  cmp     [rcx-10h], edx
0x1400060d4  cmovg   r8d, [rcx-10h]
0x1400060d9  cmp     dword ptr [rcx-8], 1
0x1400060dd  jle     short loc_1400060EE
0x1400060df  mov     edx, r8d
0x1400060e2  mov     rcx, r9
0x1400060e5  add     rsp, 28h
0x1400060e9  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1400060ee  mov     ecx, [rcx-0Ch]
0x1400060f1  cmp     ecx, r8d
0x1400060f4  jge     short loc_140006120
0x1400060f6  cmp     ecx, 40000000h
0x1400060fc  jle     short loc_140006105
0x1400060fe  mov     eax, 100000h
0x140006103  jmp     short loc_14000610C
0x140006105  mov     eax, ecx
0x140006107  cdq
0x140006108  sub     eax, edx
0x14000610a  sar     eax, 1
0x14000610c  add     eax, ecx
0x14000610e  mov     rcx, r9
0x140006111  cmp     eax, r8d
0x140006114  cmovge  r8d, eax
0x140006118  mov     edx, r8d
0x14000611b  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x140006120  add     rsp, 28h
0x140006124  retn
```
