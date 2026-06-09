# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180006f04`
- end: `0x180006f9a`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `5`
- tags: ``

## callers

- `0x180005734`
- `0x180006df8`
- `0x180008248`
- `0x18000e034`
- `0x180011c20`
- `0x1800121d0`
- `0x180012b44`
- `0x18001421c`
- `0x18001bfc0`
- `0x18001f71c`
- `0x18001f924`
- `0x180020024`
- `0x1800203c0`
- `0x1800205b0`
- `0x180022740`
- `0x1800239f4`
- `0x180024d80`
- `0x180025910`
- `0x180025c50`
- `0x1800264ec`
- `0x180026d20`
- `0x180029bc0`
- `0x180029c2c`
- `0x180029e00`
- `0x18002ba6c`
- `0x18002bd7c`
- `0x18002be68`

## callees

- `0x180005c18`
- `0x180005e54`
- `0x180006c44`
- `0x180006dc0`
- `0x180006f04`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006f7f`
- `msvcrt!memcpy_s` at `0x180006f7f`
- `msvcrt!memmove_s` at `0x180006f74`
- `msvcrt!memmove_s` at `0x180006f74`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  char *v9; // rcx
  rsize_t v10; // rdx
  rsize_t v11; // r9

  v3 = a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( ((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v10, a2, v11);
  else
    memmove_s(v9, v10, &v9[2 * v7], v11);
  return ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
}

```

## disassembly

```asm
0x180006f04  push    rbx
0x180006f06  push    rbp
0x180006f07  push    rsi
0x180006f08  push    rdi
0x180006f09  push    r14
0x180006f0b  sub     rsp, 20h
0x180006f0f  movsxd  rdi, r8d
0x180006f12  mov     rbp, rdx
0x180006f15  mov     rbx, rcx
0x180006f18  test    r8d, r8d
0x180006f1b  jnz     short loc_180006F24
0x180006f1d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180006f22  jmp     short loc_180006F8F
0x180006f24  test    rbp, rbp
0x180006f27  jnz     short loc_180006F34
0x180006f29  mov     ecx, 80070057h; int
0x180006f2e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006f34  mov     rax, [rcx]
0x180006f37  mov     rsi, rbp
0x180006f3a  sub     rsi, rax
0x180006f3d  mov     ecx, 1
0x180006f42  sar     rsi, 1
0x180006f45  sub     ecx, [rax-8]
0x180006f48  mov     r14d, [rax-10h]
0x180006f4c  mov     eax, [rax-0Ch]
0x180006f4f  sub     eax, edi
0x180006f51  or      ecx, eax
0x180006f53  jge     short loc_180006F5F
0x180006f55  mov     edx, edi
0x180006f57  mov     rcx, rbx
0x180006f5a  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180006f5f  mov     rcx, [rbx]; Destination
0x180006f62  mov     rdx, rdi
0x180006f65  add     rdx, rdx; DestinationSize
0x180006f68  mov     r9, rdx; SourceSize
0x180006f6b  cmp     rsi, r14
0x180006f6e  ja      short loc_180006F7C
0x180006f70  lea     r8, [rcx+rsi*2]; Source
0x180006f74  call    cs:__imp_memmove_s
0x180006f7a  jmp     short loc_180006F85
0x180006f7c  mov     r8, rbp; Source
0x180006f7f  call    cs:__imp_memcpy_s
0x180006f85  mov     edx, edi
0x180006f87  mov     rcx, rbx
0x180006f8a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180006f8f  add     rsp, 20h
0x180006f93  pop     r14
0x180006f95  pop     rdi
0x180006f96  pop     rsi
0x180006f97  pop     rbp
0x180006f98  pop     rbx
0x180006f99  retn
```
