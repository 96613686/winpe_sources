# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18000e5fc`
- end: `0x18000e7f5`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e2c4`

## callees

- `0x180004048`
- `0x18000e540`
- `0x18000e5fc`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000e645`
- `msvcrt!wcsstr` at `0x18000e794`
- `msvcrt!wcsstr` at `0x18000e645`
- `msvcrt!wcsstr` at `0x18000e794`
- `msvcrt!memmove_s` at `0x18000e717`
- `msvcrt!memmove_s` at `0x18000e717`
- `msvcrt!memcpy_s` at `0x18000e759`
- `msvcrt!memcpy_s` at `0x18000e759`

## string_xrefs

- `0x18000e74a`: `__CDATA_XML_CLOSE_SYMBOL__`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1)
{
  const wchar_t *v1; // rbx
  int v3; // r14d
  unsigned __int64 v4; // rbp
  wchar_t *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // ebx
  int v9; // edx
  const wchar_t *v10; // r12
  const wchar_t *v11; // rdi
  unsigned __int64 v12; // r13
  errno_t v14; // eax
  errno_t v15; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // r15
  __int64 v18; // rax
  int v19; // [rsp+80h] [rbp+18h]

  v1 = *a1;
  v3 = 0;
  v4 = (unsigned __int64)&(*a1)[*((int *)*a1 - 4)];
  if ( (unsigned __int64)*a1 < v4 )
  {
    do
    {
      while ( 1 )
      {
        v5 = wcsstr(v1, L"]]>");
        if ( !v5 )
          break;
        ++v3;
        v1 = v5 + 3;
      }
      if ( v1 )
      {
        v6 = -1;
        do
          ++v6;
        while ( v1[v6] );
      }
      else
      {
        LODWORD(v6) = 0;
      }
      v1 += (int)v6 + 1;
    }
    while ( (unsigned __int64)v1 < v4 );
    if ( v3 > 0 )
    {
      v7 = *((int *)*a1 - 4);
      v8 = v7 + 23 * v3;
      v9 = v8;
      if ( v8 <= (int)v7 )
        v9 = *((_DWORD *)*a1 - 4);
      if ( ((*((_DWORD *)*a1 - 3) - v9) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
      v10 = *a1;
      v11 = *a1;
      v12 = (unsigned __int64)&(*a1)[v7];
      if ( (unsigned __int64)*a1 < v12 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v16 = wcsstr(v11, L"]]>");
            v17 = v16;
            if ( v16 )
              break;
            if ( v11 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v11[v18] );
            }
            else
            {
              LODWORD(v18) = 0;
            }
            v11 += (int)v18 + 1;
            if ( (unsigned __int64)v11 >= v12 )
              goto LABEL_17;
          }
          v11 = v16 + 26;
          v19 = v7 - (v16 - v10) - 3;
          v14 = memmove_s(v16 + 26, 2LL * v19, v16 + 3, 2LL * v19);
          if ( v14 )
          {
            if ( v14 == 12 )
              goto LABEL_40;
            if ( v14 == 22 || v14 == 34 )
              goto LABEL_41;
            if ( v14 != 80 )
              goto LABEL_42;
          }
          v15 = memcpy_s(v17, 0x34u, L"__CDATA_XML_CLOSE_SYMBOL__", 0x34u);
          if ( v15 )
          {
            if ( v15 == 12 )
LABEL_40:
              ATL::AtlThrowImpl(-2147024882);
            if ( v15 == 22 || v15 == 34 )
              goto LABEL_41;
            if ( v15 != 80 )
LABEL_42:
              ATL::AtlThrowImpl(-2147467259);
          }
          LODWORD(v7) = v7 + 23;
          v17[v19 + 26] = 0;
        }
      }
LABEL_17:
      if ( v8 < 0 || v8 > *((_DWORD *)*a1 - 3) )
LABEL_41:
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)*a1 - 4) = v8;
      (*a1)[v8] = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e5fc  mov     [rsp+arg_10], r8
0x18000e601  push    rbx
0x18000e602  push    rbp
0x18000e603  push    rsi
0x18000e604  push    rdi
0x18000e605  push    r12
0x18000e607  push    r13
0x18000e609  push    r14
0x18000e60b  push    r15
0x18000e60d  sub     rsp, 28h
0x18000e611  mov     rbx, [rcx]
0x18000e614  xor     r15d, r15d
0x18000e617  mov     rsi, rcx
0x18000e61a  mov     r14d, r15d
0x18000e61d  movsxd  rax, dword ptr [rbx-10h]
0x18000e621  lea     rbp, [rbx+rax*2]
0x18000e625  cmp     rbx, rbp
0x18000e628  jnb     loc_18000E6D8
0x18000e62e  lea     edi, [r15+1]
0x18000e632  jmp     short loc_18000E63B
0x18000e634  add     r14d, edi
0x18000e637  lea     rbx, [rax+6]
0x18000e63b  lea     rdx, SubStr; "]]>"
0x18000e642  mov     rcx, rbx; Str
0x18000e645  call    cs:__imp_wcsstr
0x18000e64b  test    rax, rax
0x18000e64e  jnz     short loc_18000E634
0x18000e650  test    rbx, rbx
0x18000e653  jz      short loc_18000E665
0x18000e655  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e659  inc     rax
0x18000e65c  cmp     [rbx+rax*2], r15w
0x18000e661  jnz     short loc_18000E659
0x18000e663  jmp     short loc_18000E668
0x18000e665  mov     eax, r15d
0x18000e668  inc     eax
0x18000e66a  movsxd  rcx, eax
0x18000e66d  lea     rbx, [rbx+rcx*2]
0x18000e671  cmp     rbx, rbp
0x18000e674  jb      short loc_18000E63B
0x18000e676  test    r14d, r14d
0x18000e679  jle     short loc_18000E6D8
0x18000e67b  mov     rcx, [rsi]
0x18000e67e  imul    ebx, r14d, 17h
0x18000e682  movsxd  rbp, dword ptr [rcx-10h]
0x18000e686  mov     eax, [rcx-0Ch]
0x18000e689  add     ebx, ebp
0x18000e68b  cmp     ebx, ebp
0x18000e68d  mov     edx, ebx
0x18000e68f  cmovle  edx, ebp
0x18000e692  sub     edi, [rcx-8]
0x18000e695  sub     eax, edx
0x18000e697  or      edi, eax
0x18000e699  jge     short loc_18000E6A3
0x18000e69b  mov     rcx, rsi
0x18000e69e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000e6a3  mov     r12, [rsi]
0x18000e6a6  mov     rdi, r12
0x18000e6a9  lea     r13, [r12+rbp*2]
0x18000e6ad  cmp     r12, r13
0x18000e6b0  jb      loc_18000E78A
0x18000e6b6  test    ebx, ebx
0x18000e6b8  js      loc_18000E7DF
0x18000e6be  mov     rax, [rsi]
0x18000e6c1  cmp     ebx, [rax-0Ch]
0x18000e6c4  jg      loc_18000E7DF
0x18000e6ca  mov     [rax-10h], ebx
0x18000e6cd  mov     rcx, [rsi]
0x18000e6d0  movsxd  rdx, ebx
0x18000e6d3  mov     [rcx+rdx*2], r15w
0x18000e6d8  mov     eax, r14d
0x18000e6db  add     rsp, 28h
0x18000e6df  pop     r15
0x18000e6e1  pop     r14
0x18000e6e3  pop     r13
0x18000e6e5  pop     r12
0x18000e6e7  pop     rdi
0x18000e6e8  pop     rsi
0x18000e6e9  pop     rbp
0x18000e6ea  pop     rbx
0x18000e6eb  retn
0x18000e6ec  mov     eax, ebp
0x18000e6ee  lea     rdi, [r15+34h]
0x18000e6f2  mov     rcx, r15
0x18000e6f5  lea     r8, [r15+6]; Source
0x18000e6f9  sub     rcx, r12
0x18000e6fc  sar     rcx, 1
0x18000e6ff  sub     eax, ecx
0x18000e701  mov     rcx, rdi; Destination
0x18000e704  add     eax, 0FFFFFFFDh
0x18000e707  movsxd  rdx, eax
0x18000e70a  add     rdx, rdx; DestinationSize
0x18000e70d  mov     dword ptr [rsp+68h+arg_10], eax
0x18000e714  mov     r9, rdx; SourceSize
0x18000e717  call    cs:__imp_memmove_s
0x18000e71d  test    eax, eax
0x18000e71f  jz      short loc_18000E745
0x18000e721  cmp     eax, 0Ch
0x18000e724  jz      loc_18000E7D4
0x18000e72a  cmp     eax, 16h
0x18000e72d  jz      loc_18000E7DF
0x18000e733  cmp     eax, 22h ; '"'
0x18000e736  jz      loc_18000E7DF
0x18000e73c  cmp     eax, 50h ; 'P'
0x18000e73f  jnz     loc_18000E7EA
0x18000e745  mov     eax, 34h ; '4'
0x18000e74a  lea     r8, aCdataXmlCloseS; "__CDATA_XML_CLOSE_SYMBOL__"
0x18000e751  mov     r9d, eax; SourceSize
0x18000e754  mov     edx, eax; DestinationSize
0x18000e756  mov     rcx, r15; Destination
0x18000e759  call    cs:__imp_memcpy_s
0x18000e75f  test    eax, eax
0x18000e761  jz      short loc_18000E777
0x18000e763  cmp     eax, 0Ch
0x18000e766  jz      short loc_18000E7D4
0x18000e768  cmp     eax, 16h
0x18000e76b  jz      short loc_18000E7DF
0x18000e76d  cmp     eax, 22h ; '"'
0x18000e770  jz      short loc_18000E7DF
0x18000e772  cmp     eax, 50h ; 'P'
0x18000e775  jnz     short loc_18000E7EA
0x18000e777  movsxd  rcx, dword ptr [rsp+68h+arg_10]
0x18000e77f  xor     eax, eax
0x18000e781  add     ebp, 17h
0x18000e784  mov     [r15+rcx*2+34h], ax
0x18000e78a  lea     rdx, SubStr; "]]>"
0x18000e791  mov     rcx, rdi; Str
0x18000e794  call    cs:__imp_wcsstr
0x18000e79a  mov     r15, rax
0x18000e79d  test    rax, rax
0x18000e7a0  jnz     loc_18000E6EC
0x18000e7a6  xor     r15d, r15d
0x18000e7a9  test    rdi, rdi
0x18000e7ac  jz      short loc_18000E7BE
0x18000e7ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e7b2  inc     rax
0x18000e7b5  cmp     [rdi+rax*2], r15w
0x18000e7ba  jnz     short loc_18000E7B2
0x18000e7bc  jmp     short loc_18000E7C1
0x18000e7be  mov     eax, r15d
0x18000e7c1  inc     eax
0x18000e7c3  movsxd  rcx, eax
0x18000e7c6  lea     rdi, [rdi+rcx*2]
0x18000e7ca  cmp     rdi, r13
0x18000e7cd  jb      short loc_18000E78A
0x18000e7cf  jmp     loc_18000E6B6
0x18000e7d4  mov     ecx, 8007000Eh; int
0x18000e7d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e7df  mov     ecx, 80070057h; int
0x18000e7e4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e7ea  mov     ecx, 80004005h; int
0x18000e7ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
