# _anonymous_namespace_::GetStringListPropertyAsBSTRArray

- ea: `0x140010cc4`
- end: `0x140010e44`
- name: `_anonymous_namespace_::GetStringListPropertyAsBSTRArray`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140005b70`

## callees

- `0x140001020`
- `0x140002196`
- `0x14000b710`
- `0x140010880`
- `0x140010cc4`
- `0x140010e44`
- `0x140033ab0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140010d6e`
- `OLEAUT32!__imp_SysAllocString` at `0x140010d6e`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d9c`
- `OLEAUT32!__imp_SysFreeString` at `0x140010d9c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140010d34`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140010d34`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140010d49`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140010d49`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140010dae`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140010dae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::GetStringListPropertyAsBSTRArray(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // edi
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rbx
  _QWORD *v7; // rdi
  unsigned int v8; // esi
  const OLECHAR *v9; // rcx
  OLECHAR *v10; // rbx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  OLECHAR *v15; // [rsp+20h] [rbp-50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-48h] BYREF
  SAFEARRAY *v17; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 Block; // [rsp+48h] [rbp-28h]
  void *Block_8[2]; // [rsp+50h] [rbp-20h]
  __int64 v21; // [rsp+60h] [rbp-10h]

  v18 = 0;
  Block = 0;
  *(_OWORD *)Block_8 = 0;
  v21 = 10;
  v4 =  Microsoft::VisualStudio::PkgDef::CPkgDefEnvironment::`vcall'{40,{flat}}(a1, &v18);
  if ( v4 >= 0 )
  {
    rgsabound.cElements = Block;
    rgsabound.lLbound = 0;
    v5 = SafeArrayCreate(8u, 1u, &rgsabound);
    v6 = v5;
    v17 = v5;
    if ( v5 )
      SafeArrayLock(v5);
    v7 = (_QWORD *)v18;
    v8 = 0;
    if ( (_QWORD)v18 )
    {
      do
      {
        v9 = (const OLECHAR *)v7[2];
        v7 = (_QWORD *)*v7;
        if ( v9 )
        {
          v10 = SysAllocString(v9);
          rgsabound = (SAFEARRAYBOUND)v10;
          if ( !v10 )
            ATL::AtlThrowImpl(-2147024882);
        }
        else
        {
          v10 = 0;
          rgsabound = 0;
        }
        v15 = v10;
        ATL::CComSafeArray<unsigned short *,8>::SetAt(&v17, v8++, &v15);
        SysFreeString(v10);
      }
      while ( v7 );
      v6 = v17;
    }
    SafeArrayUnlock(v6);
    *(_QWORD *)(a3 + 8) = v6;
    *(_WORD *)a3 = 8200;
    v4 = 0;
  }
  while ( Block )
  {
    v11 = v18;
    if ( !(_QWORD)v18 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)&v18 = *(_QWORD *)v18;
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(
      &v18,
      v11);
  }
  v18 = 0;
  Block_8[1] = 0;
  v12 = Block_8[0];
  if ( Block_8[0] )
  {
    do
    {
      v13 = (_QWORD *)*v12;
      free_0(v12);
      v12 = v13;
    }
    while ( v13 );
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140010cc4  mov     [rsp-18h+arg_8], rbx
0x140010cc9  mov     [rsp-18h+arg_18], rsi
0x140010cce  push    rbp
0x140010ccf  push    rdi
0x140010cd0  push    r14
0x140010cd2  mov     rbp, rsp
0x140010cd5  sub     rsp, 70h
0x140010cd9  mov     rax, cs:__security_cookie
0x140010ce0  xor     rax, rsp
0x140010ce3  mov     [rbp+var_8], rax
0x140010ce7  mov     r14, r8
0x140010cea  xorps   xmm0, xmm0
0x140010ced  movups  xmmword ptr [rbp+Block], xmm0
0x140010cf1  movups  [rbp+var_18], xmm0
0x140010cf5  movdqu  [rbp+var_38], xmm0
0x140010cfa  and     [rbp+Block], 0
0x140010cff  movdqu  xmmword ptr [rbp+Block+8], xmm0
0x140010d04  mov     dword ptr [rbp+var_18+8], 0Ah
0x140010d0b  lea     rdx, [rbp+var_38]
0x140010d0f  call    ??_9CPkgDefEnvironment@PkgDef@VisualStudio@Microsoft@@$BCI@AA; [thunk]: Microsoft::VisualStudio::PkgDef::CPkgDefEnvironment::`vcall'{40,{flat}}
0x140010d14  mov     edi, eax
0x140010d16  test    eax, eax
0x140010d18  js      loc_140010DC0
0x140010d1e  mov     eax, dword ptr [rbp+Block]
0x140010d21  mov     [rbp+rgsabound.cElements], eax
0x140010d24  and     [rbp+rgsabound.lLbound], 0
0x140010d28  mov     ecx, 8; vt
0x140010d2d  lea     r8, [rbp+rgsabound]; rgsabound
0x140010d31  lea     edx, [rcx-7]; cDims
0x140010d34  call    cs:__imp_SafeArrayCreate
0x140010d3a  mov     rbx, rax
0x140010d3d  mov     [rbp+var_40], rax
0x140010d41  test    rax, rax
0x140010d44  jz      short loc_140010D4F
0x140010d46  mov     rcx, rax; psa
0x140010d49  call    cs:__imp_SafeArrayLock
0x140010d4f  mov     rdi, qword ptr [rbp+var_38]
0x140010d53  xor     esi, esi
0x140010d55  test    rdi, rdi
0x140010d58  jz      short loc_140010DAB
0x140010d5a  mov     rcx, [rdi+10h]; psz
0x140010d5e  mov     rdi, [rdi]
0x140010d61  test    rcx, rcx
0x140010d64  jnz     short loc_140010D6E
0x140010d66  xor     ebx, ebx
0x140010d68  mov     qword ptr [rbp+rgsabound.cElements], rbx
0x140010d6c  jmp     short loc_140010D84
0x140010d6e  call    cs:__imp_SysAllocString
0x140010d74  mov     rbx, rax
0x140010d77  mov     qword ptr [rbp+rgsabound.cElements], rax
0x140010d7b  test    rax, rax
0x140010d7e  jz      loc_140010E2B
0x140010d84  mov     [rbp+var_50], rbx
0x140010d88  lea     r8, [rbp+var_50]
0x140010d8c  mov     edx, esi
0x140010d8e  lea     rcx, [rbp+var_40]
0x140010d92  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x140010d97  inc     esi
0x140010d99  mov     rcx, rbx; bstrString
0x140010d9c  call    cs:__imp_SysFreeString
0x140010da2  test    rdi, rdi
0x140010da5  jnz     short loc_140010D5A
0x140010da7  mov     rbx, [rbp+var_40]
0x140010dab  mov     rcx, rbx; psa
0x140010dae  call    cs:__imp_SafeArrayUnlock
0x140010db4  mov     [r14+8], rbx
0x140010db8  mov     word ptr [r14], 2008h
0x140010dbe  xor     edi, edi
0x140010dc0  jmp     short loc_140010DDB
0x140010dc2  mov     rdx, qword ptr [rbp+var_38]
0x140010dc6  test    rdx, rdx
0x140010dc9  jz      short loc_140010E39
0x140010dcb  mov     rax, [rdx]
0x140010dce  mov     qword ptr [rbp+var_38], rax
0x140010dd2  lea     rcx, [rbp+var_38]
0x140010dd6  call    ?FreeNode@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::FreeNode(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode *)
0x140010ddb  cmp     [rbp+Block], 0
0x140010de0  ja      short loc_140010DC2
0x140010de2  xorps   xmm0, xmm0
0x140010de5  movdqu  [rbp+var_38], xmm0
0x140010dea  and     qword ptr [rbp+var_18], 0
0x140010def  mov     rcx, [rbp+Block+8]; Block
0x140010df3  test    rcx, rcx
0x140010df6  jz      short loc_140010E08
0x140010df8  mov     rbx, [rcx]
0x140010dfb  call    free_0
0x140010e00  mov     rcx, rbx
0x140010e03  test    rbx, rbx
0x140010e06  jnz     short loc_140010DF8
0x140010e08  mov     eax, edi
0x140010e0a  mov     rcx, [rbp+var_8]
0x140010e0e  xor     rcx, rsp; StackCookie
0x140010e11  call    __security_check_cookie
0x140010e16  lea     r11, [rsp+70h+var_s0]
0x140010e1b  mov     rbx, [r11+28h]
0x140010e1f  mov     rsi, [r11+38h]
0x140010e23  mov     rsp, r11
0x140010e26  pop     r14
0x140010e28  pop     rdi
0x140010e29  pop     rbp
0x140010e2a  retn
0x140010e2b  mov     ecx, 8007000Eh; int
0x140010e30  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140010e36  jmp     short $+2
0x140010e38  nop
0x140010e39  mov     ecx, 80004005h; int
0x140010e3e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
