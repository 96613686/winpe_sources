# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180004c70`
- end: `0x180004d46`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `214`
- prototype: ``
- caller_count: `32`
- callee_count: `6`
- tags: ``

## callers

- `0x1800023d0`
- `0x1800027f0`
- `0x1800059b0`
- `0x180005ff0`
- `0x180006900`
- `0x180007e80`
- `0x18000b730`
- `0x18000c8f0`
- `0x18000cb00`
- `0x18000d024`
- `0x18000d7d0`
- `0x18000e6a0`
- `0x18000e870`
- `0x18000ef40`
- `0x18000f500`
- `0x18000f650`
- `0x18000f930`
- `0x180015d48`
- `0x180016fd4`
- `0x180019354`
- `0x18001a2d4`
- `0x18001b9d4`
- `0x18001cab0`
- `0x18001d8a8`
- `0x180020fd0`
- `0x180021374`
- `0x180030910`
- `0x180048188`
- `0x180048e74`
- `0x18004b470`
- `0x18005d7f0`
- `0x180083c88`

## callees

- `0x180004c70`
- `0x180005568`
- `0x180005cb4`
- `0x180018db4`
- `0x18002d064`
- `0x180088010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180004d21`
- `msvcrt!memmove_s` at `0x180004d21`
- `msvcrt!memcpy_s` at `0x180004d2c`
- `msvcrt!memcpy_s` at `0x180004d2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rbx
  ATL::CStringData *v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rbp
  char *v10; // rcx
  rsize_t v11; // rdx
  rsize_t v12; // r9

  v3 = (int)a3;
  if ( a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v8 = *((unsigned int *)*a1 - 4);
    v9 = (a2 - *a1) >> 1;
    if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v10 = *a1;
    v11 = 2 * v3;
    v12 = 2 * v3;
    if ( v9 > v8 )
      memcpy_s(v10, v11, a2, v12);
    else
      memmove_s(v10, v11, &v10[2 * v9], v12);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
  }
  else
  {
    v6 = (ATL::CStringData *)(*a1 - 24);
    if ( *((_DWORD *)v6 + 2) )
    {
      if ( *((int *)v6 + 4) >= 0 )
      {
        v7 = *(_QWORD *)v6;
        ATL::CStringData::Release(v6);
        *a1 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180004c70  push    rbx
0x180004c72  push    rbp
0x180004c73  push    rsi
0x180004c74  push    rdi
0x180004c75  push    r14
0x180004c77  sub     rsp, 20h
0x180004c7b  movsxd  rbx, r8d
0x180004c7e  mov     rsi, rdx
0x180004c81  mov     rdi, rcx
0x180004c84  test    r8d, r8d
0x180004c87  jnz     short loc_180004CD1
0x180004c89  mov     rcx, [rcx]
0x180004c8c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180004c90  cmp     [rcx+8], r8d
0x180004c94  jz      short loc_180004CC6
0x180004c96  cmp     [rcx+10h], r8d
0x180004c9a  jge     short loc_180004CA8
0x180004c9c  xor     edx, edx
0x180004c9e  mov     rcx, rdi
0x180004ca1  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180004ca6  jmp     short loc_180004CC6
0x180004ca8  mov     rbx, [rcx]
0x180004cab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180004cb0  mov     rax, [rbx]
0x180004cb3  mov     rcx, rbx
0x180004cb6  mov     rax, [rax+18h]
0x180004cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cbf  add     rax, 18h
0x180004cc3  mov     [rdi], rax
0x180004cc6  add     rsp, 20h
0x180004cca  pop     r14
0x180004ccc  pop     rdi
0x180004ccd  pop     rsi
0x180004cce  pop     rbp
0x180004ccf  pop     rbx
0x180004cd0  retn
0x180004cd1  test    rsi, rsi
0x180004cd4  jnz     short loc_180004CE1
0x180004cd6  mov     ecx, 80070057h; int
0x180004cdb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004ce1  mov     rax, [rcx]
0x180004ce4  mov     r14d, [rax-10h]
0x180004ce8  mov     rbp, rsi
0x180004ceb  sub     rbp, rax
0x180004cee  sar     rbp, 1
0x180004cf1  mov     ecx, 1
0x180004cf6  sub     ecx, [rax-8]
0x180004cf9  mov     eax, [rax-0Ch]
0x180004cfc  sub     eax, ebx
0x180004cfe  or      ecx, eax
0x180004d00  jge     short loc_180004D0C
0x180004d02  mov     edx, ebx
0x180004d04  mov     rcx, rdi
0x180004d07  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180004d0c  mov     rcx, [rdi]; Destination
0x180004d0f  mov     rdx, rbx
0x180004d12  add     rdx, rdx; DestinationSize
0x180004d15  mov     r9, rdx; SourceSize
0x180004d18  cmp     rbp, r14
0x180004d1b  ja      short loc_180004D29
0x180004d1d  lea     r8, [rcx+rbp*2]; Source
0x180004d21  call    cs:__imp_memmove_s
0x180004d27  jmp     short loc_180004D32
0x180004d29  mov     r8, rsi; Source
0x180004d2c  call    cs:__imp_memcpy_s
0x180004d32  mov     edx, ebx
0x180004d34  mov     rcx, rdi
0x180004d37  add     rsp, 20h
0x180004d3b  pop     r14
0x180004d3d  pop     rdi
0x180004d3e  pop     rsi
0x180004d3f  pop     rbp
0x180004d40  pop     rbx
0x180004d41  jmp     ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
```
