# Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140021a60`
- end: `0x140021c1a`
- name: `?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `442`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002180c`

## callees

- `0x140002368`
- `0x140009cd8`
- `0x14001c8a8`
- `0x14001d88c`
- `0x140021a60`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!RegLoadMUIStringW` at `0x140021b98`
- `ADVAPI32!RegLoadMUIStringW` at `0x140021b98`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140021be3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140021be3`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall Accommodation::QueryStringValue(ATL::CRegKey *this, unsigned __int16 *a2, char **a3)
{
  char **v3; // r14
  const unsigned __int16 *v4; // r13
  ATL::CRegKey *v5; // r12
  int v6; // eax
  __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  unsigned int v10; // r15d
  __int64 v11; // r8
  unsigned int v13; // [rsp+40h] [rbp-888h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-880h]
  ATL::CRegKey *v15; // [rsp+50h] [rbp-878h]
  unsigned __int16 *v16; // [rsp+58h] [rbp-870h]
  char **v17; // [rsp+60h] [rbp-868h]
  WCHAR pszOutBuf[1024]; // [rsp+70h] [rbp-858h] BYREF
  ATL::CAtlException *v19; // [rsp+870h] [rbp-58h] BYREF
  ATL::CAtlException *v20; // [rsp+878h] [rbp-50h] BYREF

  try
  {
    v3 = a3;
    v4 = a2;
    v5 = this;
    v15 = this;
    v16 = a2;
    v17 = a3;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a3);
    v13 = 0;
    v6 = ATL::CRegKey::QueryStringValue(v5, v4, 0, &v13);
  }
  catch ( ATL::CAtlException *v19 )
  {
    return 0;
  }
  if ( v6 || !v13 )
    return 1;
  v7 = -1;
  v8 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
  v9 = v8;
  v14 = v8;
  if ( !v8 )
    return 0;
  v10 = 1;
  *v8 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue(v5, v4, v8, &v13) && v13 )
  {
    if ( v13 > 0x400 )
      v9[1023] = 0;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    try
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(v3, v9, v11);
    }
    catch ( ATL::CAtlException *v20 )
    {
      v7 = -1;
      v10 = 0;
      v9 = v14;
      v5 = v15;
      v4 = v16;
      v3 = v17;
    }
  }
  if ( *v9 == 64 && v10 )
  {
    if ( RegLoadMUIStringW(*(HKEY *)v5, v4, pszOutBuf, 0x400u, 0, 1u, 0) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v3);
    }
    else
    {
      pszOutBuf[1023] = 0;
      do
        ++v7;
      while ( pszOutBuf[v7] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(v3, pszOutBuf, v7);
    }
  }
  operator delete[](v9);
  return v10;
}

```

## disassembly

```asm
0x140021a60  push    rbx
0x140021a62  push    rsi
0x140021a63  push    rdi
0x140021a64  push    r12
0x140021a66  push    r13
0x140021a68  push    r14
0x140021a6a  push    r15
0x140021a6c  sub     rsp, 890h
0x140021a73  mov     rax, cs:__security_cookie
0x140021a7a  xor     rax, rsp
0x140021a7d  mov     [rsp+8C8h+var_40], rax
0x140021a85  mov     r14, r8
0x140021a88  mov     r13, rdx
0x140021a8b  mov     r12, rcx
0x140021a8e  mov     [rsp+8C8h+var_878], rcx
0x140021a93  mov     [rsp+8C8h+var_870], rdx
0x140021a98  mov     [rsp+8C8h+var_868], r8
0x140021a9d  mov     rcx, r8
0x140021aa0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140021aa5  nop
0x140021aa6  xor     ebx, ebx
0x140021aa8  mov     [rsp+8C8h+var_888], ebx
0x140021aac  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x140021ab1  xor     r8d, r8d; unsigned __int16 *
0x140021ab4  mov     rdx, r13; unsigned __int16 *
0x140021ab7  mov     rcx, r12; this
0x140021aba  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140021abf  test    eax, eax
0x140021ac1  jnz     loc_140021BEE
0x140021ac7  cmp     [rsp+8C8h+var_888], ebx
0x140021acb  jz      loc_140021BEE
0x140021ad1  mov     ecx, [rsp+8C8h+var_888]
0x140021ad5  lea     eax, [rbx+2]
0x140021ad8  mul     rcx
0x140021adb  lea     rsi, [rbx-1]
0x140021adf  cmovb   rax, rsi
0x140021ae3  mov     rcx, rax; unsigned __int64
0x140021ae6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140021aeb  mov     rdi, rax
0x140021aee  mov     [rsp+8C8h+var_880], rax
0x140021af3  test    rax, rax
0x140021af6  jz      loc_140021BF5
0x140021afc  lea     r15d, [rbx+1]
0x140021b00  mov     [rax], bx
0x140021b03  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x140021b08  mov     r8, rax; unsigned __int16 *
0x140021b0b  mov     rdx, r13; unsigned __int16 *
0x140021b0e  mov     rcx, r12; this
0x140021b11  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140021b16  test    eax, eax
0x140021b18  jnz     short loc_140021B69
0x140021b1a  cmp     [rsp+8C8h+var_888], ebx
0x140021b1e  jbe     short loc_140021B69
0x140021b20  cmp     [rsp+8C8h+var_888], 400h
0x140021b28  jbe     short loc_140021B31
0x140021b2a  mov     [rdi+7FEh], bx
0x140021b31  mov     r8, rsi
0x140021b34  inc     r8
0x140021b37  cmp     [rdi+r8*2], bx
0x140021b3c  jnz     short loc_140021B34
0x140021b3e  mov     rdx, rdi
0x140021b41  mov     rcx, r14
0x140021b44  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140021b49  nop
0x140021b4a  jmp     short loc_140021B69
0x140021b4c  xor     ebx, ebx
0x140021b4e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140021b52  mov     r15d, ebx
0x140021b55  mov     rdi, [rsp+8C8h+var_880]
0x140021b5a  mov     r12, [rsp+8C8h+var_878]
0x140021b5f  mov     r13, [rsp+8C8h+var_870]
0x140021b64  mov     r14, [rsp+8C8h+var_868]
0x140021b69  cmp     word ptr [rdi], 40h ; '@'
0x140021b6d  jnz     short loc_140021BE0
0x140021b6f  test    r15d, r15d
0x140021b72  jz      short loc_140021BE0
0x140021b74  mov     [rsp+8C8h+pszDirectory], rbx; pszDirectory
0x140021b79  mov     [rsp+8C8h+Flags], 1; Flags
0x140021b81  mov     [rsp+8C8h+pcbData], rbx; pcbData
0x140021b86  mov     r9d, 400h; cbOutBuf
0x140021b8c  lea     r8, [rsp+8C8h+pszOutBuf]; pszOutBuf
0x140021b91  mov     rdx, r13; pszValue
0x140021b94  mov     rcx, [r12]; hKey
0x140021b98  call    cs:__imp_RegLoadMUIStringW
0x140021b9e  nop
0x140021b9f  test    eax, eax
0x140021ba1  jnz     short loc_140021BCB
0x140021ba3  mov     [rsp+8C8h+var_5A], bx
0x140021bab  lea     rax, [rsp+8C8h+pszOutBuf]
0x140021bb0  inc     rsi
0x140021bb3  cmp     [rax+rsi*2], bx
0x140021bb7  jnz     short loc_140021BB0
0x140021bb9  mov     r8d, esi
0x140021bbc  lea     rdx, [rsp+8C8h+pszOutBuf]
0x140021bc1  mov     rcx, r14
0x140021bc4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140021bc9  jmp     short loc_140021BD4
0x140021bcb  mov     rcx, r14
0x140021bce  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140021bd3  nop
0x140021bd4  jmp     short loc_140021BE0
0x140021bd6  mov     r15d, [rsp+8C8h+var_888]
0x140021bdb  mov     rdi, [rsp+8C8h+var_880]
0x140021be0  mov     rcx, rdi
0x140021be3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140021be9  mov     eax, r15d
0x140021bec  jmp     short loc_140021BF7
0x140021bee  mov     eax, 1
0x140021bf3  jmp     short loc_140021BF7
0x140021bf5  xor     eax, eax
0x140021bf7  mov     rcx, [rsp+8C8h+var_40]
0x140021bff  xor     rcx, rsp; StackCookie
0x140021c02  call    __security_check_cookie
0x140021c07  add     rsp, 890h
0x140021c0e  pop     r15
0x140021c10  pop     r14
0x140021c12  pop     r13
0x140021c14  pop     r12
0x140021c16  pop     rdi
0x140021c17  pop     rsi
0x140021c18  pop     rbx
0x140021c19  retn
```
