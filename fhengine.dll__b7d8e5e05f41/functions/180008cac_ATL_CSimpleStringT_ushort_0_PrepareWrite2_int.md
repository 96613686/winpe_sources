# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180008cac`
- end: `0x180008d12`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800091a4`
- `0x1800097b0`
- `0x1800099ec`
- `0x18000a21c`
- `0x18000bb0c`
- `0x18000f728`
- `0x18000fc88`
- `0x180010d48`
- `0x180021e6c`

## callees

- `0x1800080cc`
- `0x180008cac`
- `0x180008eb0`

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
0x180008cac  sub     rsp, 28h
0x180008cb0  mov     r9, rcx
0x180008cb3  mov     r8d, edx
0x180008cb6  mov     rcx, [rcx]
0x180008cb9  cmp     [rcx-10h], edx
0x180008cbc  cmovg   r8d, [rcx-10h]
0x180008cc1  cmp     dword ptr [rcx-8], 1
0x180008cc5  jle     short loc_180008CD6
0x180008cc7  mov     edx, r8d
0x180008cca  mov     rcx, r9
0x180008ccd  add     rsp, 28h
0x180008cd1  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180008cd6  mov     ecx, [rcx-0Ch]
0x180008cd9  cmp     ecx, r8d
0x180008cdc  jge     short loc_180008D0D
0x180008cde  cmp     ecx, 40000000h
0x180008ce4  jle     short loc_180008CED
0x180008ce6  mov     eax, 100000h
0x180008ceb  jmp     short loc_180008CF9
0x180008ced  mov     eax, ecx
0x180008cef  mov     r10d, 2
0x180008cf5  cdq
0x180008cf6  idiv    r10d
0x180008cf9  add     eax, ecx
0x180008cfb  mov     rcx, r9
0x180008cfe  cmp     eax, r8d
0x180008d01  cmovge  r8d, eax
0x180008d05  mov     edx, r8d
0x180008d08  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180008d0d  add     rsp, 28h
0x180008d11  retn
```
