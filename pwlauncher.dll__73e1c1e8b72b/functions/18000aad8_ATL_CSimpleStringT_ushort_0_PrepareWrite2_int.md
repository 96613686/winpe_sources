# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000aad8`
- end: `0x18000ab39`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a38c`
- `0x18000ad08`

## callees

- `0x180009d58`
- `0x18000aad8`
- `0x18000ab40`

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
0x18000aad8  sub     rsp, 28h
0x18000aadc  mov     r9, rcx
0x18000aadf  mov     r8d, edx
0x18000aae2  mov     rcx, [rcx]
0x18000aae5  cmp     [rcx-10h], edx
0x18000aae8  cmovg   r8d, [rcx-10h]
0x18000aaed  cmp     dword ptr [rcx-8], 1
0x18000aaf1  jle     short loc_18000AB02
0x18000aaf3  mov     edx, r8d
0x18000aaf6  mov     rcx, r9
0x18000aaf9  add     rsp, 28h
0x18000aafd  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000ab02  mov     ecx, [rcx-0Ch]
0x18000ab05  cmp     ecx, r8d
0x18000ab08  jge     short loc_18000AB34
0x18000ab0a  cmp     ecx, 40000000h
0x18000ab10  jle     short loc_18000AB19
0x18000ab12  mov     eax, 100000h
0x18000ab17  jmp     short loc_18000AB20
0x18000ab19  mov     eax, ecx
0x18000ab1b  cdq
0x18000ab1c  sub     eax, edx
0x18000ab1e  sar     eax, 1
0x18000ab20  add     eax, ecx
0x18000ab22  mov     rcx, r9
0x18000ab25  cmp     eax, r8d
0x18000ab28  cmovge  r8d, eax
0x18000ab2c  mov     edx, r8d
0x18000ab2f  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000ab34  add     rsp, 28h
0x18000ab38  retn
```
