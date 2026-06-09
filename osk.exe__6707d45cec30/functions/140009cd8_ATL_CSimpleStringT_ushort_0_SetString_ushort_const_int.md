# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x140009cd8`
- end: `0x140009d6e`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x1400045f4`
- `0x1400084f8`
- `0x14000a414`
- `0x14001c324`
- `0x14001c58c`
- `0x14001c940`
- `0x14001dae4`
- `0x14001dc50`
- `0x14001dccc`
- `0x14001f060`
- `0x14001f728`
- `0x14002140c`
- `0x14002180c`
- `0x140021a60`
- `0x140024ba4`

## callees

- `0x140005b50`
- `0x140005ef4`
- `0x140007ee8`
- `0x140009ca0`
- `0x140009cd8`

## import_xrefs

- `msvcrt!memmove_s` at `0x140009d48`
- `msvcrt!memmove_s` at `0x140009d48`
- `msvcrt!memcpy_s` at `0x140009d53`
- `msvcrt!memcpy_s` at `0x140009d53`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  char *v9; // rcx
  rsize_t v10; // rdx
  rsize_t v11; // r9

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
  if ( !a2 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
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
0x140009cd8  push    rbx
0x140009cda  push    rbp
0x140009cdb  push    rsi
0x140009cdc  push    rdi
0x140009cdd  push    r14
0x140009cdf  sub     rsp, 20h
0x140009ce3  movsxd  rdi, r8d
0x140009ce6  mov     rbp, rdx
0x140009ce9  mov     rbx, rcx
0x140009cec  test    r8d, r8d
0x140009cef  jnz     short loc_140009CF8
0x140009cf1  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140009cf6  jmp     short loc_140009D63
0x140009cf8  test    rbp, rbp
0x140009cfb  jnz     short loc_140009D08
0x140009cfd  mov     ecx, 80070057h; int
0x140009d02  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009d08  mov     rax, [rcx]
0x140009d0b  mov     rsi, rbp
0x140009d0e  sub     rsi, rax
0x140009d11  mov     ecx, 1
0x140009d16  sar     rsi, 1
0x140009d19  sub     ecx, [rax-8]
0x140009d1c  mov     r14d, [rax-10h]
0x140009d20  mov     eax, [rax-0Ch]
0x140009d23  sub     eax, edi
0x140009d25  or      ecx, eax
0x140009d27  jge     short loc_140009D33
0x140009d29  mov     edx, edi
0x140009d2b  mov     rcx, rbx
0x140009d2e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140009d33  mov     rcx, [rbx]; Destination
0x140009d36  mov     rdx, rdi
0x140009d39  add     rdx, rdx; DestinationSize
0x140009d3c  mov     r9, rdx; SourceSize
0x140009d3f  cmp     rsi, r14
0x140009d42  ja      short loc_140009D50
0x140009d44  lea     r8, [rcx+rsi*2]; Source
0x140009d48  call    cs:__imp_memmove_s
0x140009d4e  jmp     short loc_140009D59
0x140009d50  mov     r8, rbp; Source
0x140009d53  call    cs:__imp_memcpy_s
0x140009d59  mov     edx, edi
0x140009d5b  mov     rcx, rbx
0x140009d5e  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x140009d63  add     rsp, 20h
0x140009d67  pop     r14
0x140009d69  pop     rdi
0x140009d6a  pop     rsi
0x140009d6b  pop     rbp
0x140009d6c  pop     rbx
0x140009d6d  retn
```
