# ADALCreateAuthenticationContextNoUI

- ea: `0x140006818`
- end: `0x1400069e4`
- name: `ADALCreateAuthenticationContextNoUI`
- size: `460`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140003bc0`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400054e8`
- `0x1400061dc`
- `0x140006818`
- `0x140007180`
- `0x140007bf8`
- `0x140009b24`
- `0x14000be04`
- `0x14000be24`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006832`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006832`

## string_xrefs

- `0x14000683f`: `onecore\ds\security\dsreg\win32\adal.native\adal.cpp`
- `0x140006936`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ADALCreateAuthenticationContextNoUI(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        AuthenticationContext *a3)
{
  AuthenticationContext *v5; // rax
  AuthenticationContext *v6; // rdi
  __int64 v7; // r8
  _QWORD *v8; // rdx
  AuthenticationContext *v9; // rax
  __int64 v10; // rbx
  _DWORD *v11; // rax
  __int64 result; // rax
  const Exception *v13; // [rsp+28h] [rbp-40h] BYREF
  const std::exception *v14; // [rsp+30h] [rbp-38h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+38h] [rbp-30h] BYREF
  AuthenticationContext *v16; // [rsp+80h] [rbp+18h] BYREF
  AuthenticationContext *v17; // [rsp+88h] [rbp+20h]

  v16 = a3;
  SetLastError(0);
  try
  {
    v5 = (AuthenticationContext *)operator new(0x170u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\adal.cpp");
    v16 = v5;
    if ( v5 )
      v6 = AuthenticationContext::AuthenticationContext(v5);
    else
      v6 = 0;
    v17 = v6;
    ArgumentException::ThrowIfNullOrEmpty(a1, 0xCAA10007);
    ArgumentException::ThrowIfNullOrEmpty(a2, 0xCAA10009);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v16,
      (__int64)a1);
    if ( !(unsigned __int8)AuthenticationContext::ValidateAndExtractStsUrl(&v16) )
    {
      ArgumentException::ArgumentException((ArgumentException *)pExceptionObject, -895418363);
      throw (ArgumentException *)pExceptionObject;
    }
    if ( a2 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a2[v7] );
    }
    else
    {
      v7 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v6 + 16, a2, v7);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)v6 + 1,
      &v16);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v6 + 40, 0, 0);
    v8 = (_QWORD *)((char *)v16 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    v17 = 0;
    v9 = (AuthenticationContext *)operator new(
                                    0x20u,
                                    1,
                                    "onecore\\ds\\security\\dsreg\\win32\\adal.native\\APIHandle.h");
    v10 = (__int64)v9;
    v16 = v9;
    if ( v9 )
    {
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      v11 = operator new(0x18u);
      if ( v11 )
      {
        v11[2] = 1;
        v11[3] = 1;
        *(_QWORD *)v11 = &std::_Ref_count<AuthenticationContext>::`vftable';
        *((_QWORD *)v11 + 2) = v6;
      }
      else
      {
        v11 = 0;
      }
      *(_QWORD *)(v10 + 8) = v6;
      *(_QWORD *)(v10 + 16) = v11;
      *(_DWORD *)v10 = -1441095254;
      *(_BYTE *)(v10 + 24) = 0;
    }
    else
    {
      v10 = 0;
    }
    result = v10;
  }
  catch ( const Exception *v13 )
  {
    HandleException(0, v13);
    return 0;
  }
  catch ( const std::exception *v14 )
  {
    HandleException(0, v14);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006818  mov     [rsp+arg_0], rbx
0x14000681d  mov     [rsp+arg_10], r8
0x140006822  push    rsi
0x140006823  push    rdi
0x140006824  push    r14
0x140006826  sub     rsp, 50h
0x14000682a  mov     rbx, rdx
0x14000682d  mov     rsi, rcx
0x140006830  xor     ecx, ecx; dwErrCode
0x140006832  call    cs:__imp_SetLastError
0x140006838  nop
0x140006839  mov     r9d, 1Eh; int
0x14000683f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140006846  lea     edx, [r9-1Dh]; int
0x14000684a  mov     ecx, 170h; unsigned __int64
0x14000684f  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140006854  mov     [rsp+68h+arg_10], rax
0x14000685c  xor     r14d, r14d
0x14000685f  test    rax, rax
0x140006862  jz      short loc_140006871
0x140006864  mov     rcx, rax; this
0x140006867  call    ??0AuthenticationContext@@QEAA@XZ; AuthenticationContext::AuthenticationContext(void)
0x14000686c  mov     rdi, rax
0x14000686f  jmp     short loc_140006874
0x140006871  mov     rdi, r14
0x140006874  mov     [rsp+68h+arg_18], rdi
0x14000687c  mov     edx, 0CAA10007h; unsigned int
0x140006881  mov     rcx, rsi; unsigned __int16 *
0x140006884  call    ?ThrowIfNullOrEmpty@ArgumentException@@SAXPEBGK@Z; ArgumentException::ThrowIfNullOrEmpty(ushort const *,ulong)
0x140006889  mov     edx, 0CAA10009h; unsigned int
0x14000688e  mov     rcx, rbx; unsigned __int16 *
0x140006891  call    ?ThrowIfNullOrEmpty@ArgumentException@@SAXPEBGK@Z; ArgumentException::ThrowIfNullOrEmpty(ushort const *,ulong)
0x140006896  mov     rdx, rsi
0x140006899  lea     rcx, [rsp+68h+arg_10]
0x1400068a1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400068a6  nop
0x1400068a7  lea     rcx, [rsp+68h+arg_10]
0x1400068af  call    ?ValidateAndExtractStsUrl@AuthenticationContext@@CA_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AuthenticationContext::ValidateAndExtractStsUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400068b4  test    al, al
0x1400068b6  jz      loc_1400069C2
0x1400068bc  test    rbx, rbx
0x1400068bf  jnz     short loc_1400068C6
0x1400068c1  mov     r8d, r14d
0x1400068c4  jmp     short loc_1400068D4
0x1400068c6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400068ca  inc     r8
0x1400068cd  cmp     [rbx+r8*2], r14w
0x1400068d2  jnz     short loc_1400068CA
0x1400068d4  lea     rcx, [rdi+10h]
0x1400068d8  mov     rdx, rbx
0x1400068db  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400068e0  lea     rcx, [rdi+8]
0x1400068e4  lea     rdx, [rsp+68h+arg_10]
0x1400068ec  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400068f1  lea     rcx, [rdi+28h]
0x1400068f5  xor     r8d, r8d
0x1400068f8  xor     edx, edx
0x1400068fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400068ff  nop
0x140006900  mov     rdx, [rsp+68h+arg_10]
0x140006908  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000690c  or      eax, 0FFFFFFFFh
0x14000690f  lock xadd [rdx+10h], eax
0x140006914  sub     eax, 1
0x140006917  jg      short loc_140006928
0x140006919  mov     rcx, [rdx]
0x14000691c  mov     rax, [rcx]
0x14000691f  mov     rax, [rax+8]
0x140006923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006928  mov     [rsp+68h+arg_18], r14
0x140006930  mov     r9d, 3Fh ; '?'; int
0x140006936  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000693d  lea     edx, [r9-3Eh]; int
0x140006941  lea     ecx, [rdx+1Fh]; unsigned __int64
0x140006944  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140006949  mov     rbx, rax
0x14000694c  mov     [rsp+68h+arg_10], rax
0x140006954  test    rax, rax
0x140006957  jz      short loc_1400069AA
0x140006959  mov     [rax+8], r14
0x14000695d  mov     [rax+10h], r14
0x140006961  mov     [rsp+68h+var_48], rdi
0x140006966  mov     ecx, 18h; Size
0x14000696b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006970  test    rax, rax
0x140006973  jz      short loc_140006993
0x140006975  mov     dword ptr [rax+8], 1
0x14000697c  mov     dword ptr [rax+0Ch], 1
0x140006983  lea     rcx, ??_7?$_Ref_count@VAuthenticationContext@@@std@@6B@; const std::_Ref_count<AuthenticationContext>::`vftable'
0x14000698a  mov     [rax], rcx
0x14000698d  mov     [rax+10h], rdi
0x140006991  jmp     short loc_140006996
0x140006993  mov     rax, r14
0x140006996  mov     [rbx+8], rdi
0x14000699a  mov     [rbx+10h], rax
0x14000699e  mov     dword ptr [rbx], 0AA1AA1AAh
0x1400069a4  mov     [rbx+18h], r14b
0x1400069a8  jmp     short loc_1400069AD
0x1400069aa  mov     rbx, r14
0x1400069ad  mov     rax, rbx
0x1400069b0  jmp     short loc_1400069B4
0x1400069b2  xor     eax, eax
0x1400069b4  mov     rbx, [rsp+68h+arg_0]
0x1400069b9  add     rsp, 50h
0x1400069bd  pop     r14
0x1400069bf  pop     rdi
0x1400069c0  pop     rsi
0x1400069c1  retn
0x1400069c2  mov     edx, 0CAA10005h; unsigned int
0x1400069c7  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400069cc  call    ??0ArgumentException@@QEAA@K@Z; ArgumentException::ArgumentException(ulong)
0x1400069d1  lea     rdx, _TI3?AVArgumentException@@; pThrowInfo
0x1400069d8  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400069dd  call    _CxxThrowException_0
```
