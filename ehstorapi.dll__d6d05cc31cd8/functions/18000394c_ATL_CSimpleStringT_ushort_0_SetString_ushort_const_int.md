# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000394c`
- end: `0x180003a1a`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180003924`
- `0x18000408c`
- `0x18000521c`

## callees

- `0x180002338`
- `0x180003724`
- `0x180003864`
- `0x1800038ec`
- `0x18000394c`
- `0x18000d010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800039f4`
- `msvcrt!memmove_s` at `0x1800039f4`
- `msvcrt!memcpy_s` at `0x1800039ff`
- `msvcrt!memcpy_s` at `0x1800039ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, __int64 a3)
{
  __int64 v3; // rbx
  ATL::CStringData *v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  char *v10; // rcx
  rsize_t v11; // rdx
  rsize_t v12; // r9

  v3 = (int)a3;
  if ( (_DWORD)a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v8 = *((unsigned int *)*a1 - 4);
    v9 = (a2 - *a1) >> 1;
    if ( (int)((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)a3, a3);
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
0x18000394c  push    rbx
0x18000394e  push    rbp
0x18000394f  push    rsi
0x180003950  push    rdi
0x180003951  push    r14
0x180003953  sub     rsp, 20h
0x180003957  movsxd  rbx, r8d
0x18000395a  mov     rbp, rdx
0x18000395d  mov     rdi, rcx
0x180003960  test    r8d, r8d
0x180003963  jnz     short loc_1800039A4
0x180003965  mov     rcx, [rcx]
0x180003968  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000396c  cmp     [rcx+8], r8d
0x180003970  jz      short loc_1800039A2
0x180003972  cmp     [rcx+10h], r8d
0x180003976  jge     short loc_180003984
0x180003978  xor     edx, edx
0x18000397a  mov     rcx, rdi
0x18000397d  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180003982  jmp     short loc_1800039A2
0x180003984  mov     rbx, [rcx]
0x180003987  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000398c  mov     rax, [rbx]
0x18000398f  mov     rcx, rbx
0x180003992  mov     rax, [rax+18h]
0x180003996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399b  add     rax, 18h
0x18000399f  mov     [rdi], rax
0x1800039a2  jmp     short loc_180003A0F
0x1800039a4  test    rbp, rbp
0x1800039a7  jnz     short loc_1800039B4
0x1800039a9  mov     ecx, 80070057h; int
0x1800039ae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800039b4  mov     rax, [rcx]
0x1800039b7  mov     r14d, [rax-10h]
0x1800039bb  mov     rsi, rbp
0x1800039be  sub     rsi, rax
0x1800039c1  sar     rsi, 1
0x1800039c4  mov     ecx, 1
0x1800039c9  sub     ecx, [rax-8]
0x1800039cc  mov     eax, [rax-0Ch]
0x1800039cf  sub     eax, ebx
0x1800039d1  or      ecx, eax
0x1800039d3  jge     short loc_1800039DF
0x1800039d5  mov     edx, ebx
0x1800039d7  mov     rcx, rdi
0x1800039da  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800039df  mov     rcx, [rdi]; Destination
0x1800039e2  mov     rdx, rbx
0x1800039e5  add     rdx, rdx; DestinationSize
0x1800039e8  mov     r9, rdx; SourceSize
0x1800039eb  cmp     rsi, r14
0x1800039ee  ja      short loc_1800039FC
0x1800039f0  lea     r8, [rcx+rsi*2]; Source
0x1800039f4  call    cs:__imp_memmove_s
0x1800039fa  jmp     short loc_180003A05
0x1800039fc  mov     r8, rbp; Source
0x1800039ff  call    cs:__imp_memcpy_s
0x180003a05  mov     edx, ebx
0x180003a07  mov     rcx, rdi
0x180003a0a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180003a0f  add     rsp, 20h
0x180003a13  pop     r14
0x180003a15  pop     rdi
0x180003a16  pop     rsi
0x180003a17  pop     rbp
0x180003a18  pop     rbx
0x180003a19  retn
```
