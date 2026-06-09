# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180019a0c`
- end: `0x180019ada`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `206`
- prototype: `void __fastcall(__int64 *, const void *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180019064`
- `0x1800194c0`
- `0x180019ae0`
- `0x180019d74`

## callees

- `0x180009e80`
- `0x180019694`
- `0x180019754`
- `0x1800199d4`
- `0x180019a0c`
- `0x18001c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180019ab4`
- `msvcrt!memmove_s` at `0x180019ab4`
- `msvcrt!memcpy_s` at `0x180019abf`
- `msvcrt!memcpy_s` at `0x180019abf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rbx
  ATL::CStringData *v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  char *v10; // rcx
  rsize_t v11; // rdx
  rsize_t v12; // r9

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v8 = *(unsigned int *)(*a1 - 16);
    v9 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v10 = (char *)*a1;
    v11 = 2 * v3;
    v12 = 2 * v3;
    if ( v9 > v8 )
      memcpy_s(v10, v11, a2, v12);
    else
      memmove_s(v10, v11, &v10[2 * v9], v12);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v3);
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
        *a1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24;
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
0x180019a0c  push    rbx
0x180019a0e  push    rbp
0x180019a0f  push    rsi
0x180019a10  push    rdi
0x180019a11  push    r14
0x180019a13  sub     rsp, 20h
0x180019a17  movsxd  rbx, r8d
0x180019a1a  mov     rbp, rdx
0x180019a1d  mov     rdi, rcx
0x180019a20  test    r8d, r8d
0x180019a23  jnz     short loc_180019A64
0x180019a25  mov     rcx, [rcx]
0x180019a28  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019a2c  cmp     [rcx+8], r8d
0x180019a30  jz      short loc_180019A62
0x180019a32  cmp     [rcx+10h], r8d
0x180019a36  jge     short loc_180019A44
0x180019a38  xor     edx, edx
0x180019a3a  mov     rcx, rdi
0x180019a3d  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180019a42  jmp     short loc_180019A62
0x180019a44  mov     rbx, [rcx]
0x180019a47  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019a4c  mov     rax, [rbx]
0x180019a4f  mov     rcx, rbx
0x180019a52  mov     rax, [rax+18h]
0x180019a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a5b  add     rax, 18h
0x180019a5f  mov     [rdi], rax
0x180019a62  jmp     short loc_180019ACF
0x180019a64  test    rbp, rbp
0x180019a67  jnz     short loc_180019A74
0x180019a69  mov     ecx, 80070057h; int
0x180019a6e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019a74  mov     rax, [rcx]
0x180019a77  mov     r14d, [rax-10h]
0x180019a7b  mov     rsi, rbp
0x180019a7e  sub     rsi, rax
0x180019a81  sar     rsi, 1
0x180019a84  mov     ecx, 1
0x180019a89  sub     ecx, [rax-8]
0x180019a8c  mov     eax, [rax-0Ch]
0x180019a8f  sub     eax, ebx
0x180019a91  or      ecx, eax
0x180019a93  jge     short loc_180019A9F
0x180019a95  mov     edx, ebx
0x180019a97  mov     rcx, rdi
0x180019a9a  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180019a9f  mov     rcx, [rdi]; Destination
0x180019aa2  mov     rdx, rbx
0x180019aa5  add     rdx, rdx; DestinationSize
0x180019aa8  mov     r9, rdx; SourceSize
0x180019aab  cmp     rsi, r14
0x180019aae  ja      short loc_180019ABC
0x180019ab0  lea     r8, [rcx+rsi*2]; Source
0x180019ab4  call    cs:__imp_memmove_s
0x180019aba  jmp     short loc_180019AC5
0x180019abc  mov     r8, rbp; Source
0x180019abf  call    cs:__imp_memcpy_s
0x180019ac5  mov     edx, ebx
0x180019ac7  mov     rcx, rdi
0x180019aca  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180019acf  add     rsp, 20h
0x180019ad3  pop     r14
0x180019ad5  pop     rdi
0x180019ad6  pop     rsi
0x180019ad7  pop     rbp
0x180019ad8  pop     rbx
0x180019ad9  retn
```
