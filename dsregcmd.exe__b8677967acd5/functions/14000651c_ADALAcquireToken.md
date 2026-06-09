# ADALAcquireToken

- ea: `0x14000651c`
- end: `0x140006810`
- name: `ADALAcquireToken`
- size: `756`
- prototype: `__int64 __fastcall(struct HADALCONTEXT__ *, unsigned __int16 *, GUID *rguid)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140003bc0`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x140005c58`
- `0x1400060c4`
- `0x1400062d0`
- `0x1400063bc`
- `0x140006484`
- `0x14000651c`
- `0x140007d8c`
- `0x140009e30`
- `0x14000e020`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000653d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000653d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400065fe`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400065fe`

## string_xrefs

- `0x1400066e4`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`
- `0x1400066a6`: `onecore\ds\security\dsreg\win32\adal.native\apireq.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ADALAcquireToken(struct HADALCONTEXT__ *a1, unsigned __int16 *a2, GUID *rguid)
{
  __int64 v6; // rax
  const std::exception *v7; // r14
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  OLECHAR *v12; // rdx
  int v13; // eax
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rax
  struct TokenRequest *v17; // r14
  APIReq *v18; // rax
  APIReq *v19; // r14
  _QWORD *v20; // rax
  __int64 v21; // rbx
  _DWORD *v22; // rax
  LPOLESTR v23; // rdx
  __int64 result; // rax
  const Exception *v25; // [rsp+40h] [rbp-58h] BYREF
  const std::exception *v26[3]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-38h] BYREF
  LPOLESTR lpsz; // [rsp+B8h] [rbp+20h] BYREF

  SetLastError(0);
  try
  {
    if ( !a1 || !(unsigned __int8)APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(a1) )
    {
      InvalidHandleException::InvalidHandleException((InvalidHandleException *)pExceptionObject, 0xCAA1000E);
      throw (InvalidHandleException *)pExceptionObject;
    }
    v6 = *((_QWORD *)a1 + 2);
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
    v7 = (const std::exception *)*((_QWORD *)a1 + 1);
    v26[1] = v7;
    v8 = (volatile signed __int32 *)*((_QWORD *)a1 + 2);
    v26[2] = (const std::exception *)v8;
    v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v12 = (OLECHAR *)(v9 + 24);
    lpsz = (LPOLESTR)(v9 + 24);
    if ( rguid )
    {
      if ( ((*(_DWORD *)(v9 + 12) - 38) | (1 - *(_DWORD *)(v9 + 16))) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpsz, 38, v10, v11);
        v12 = lpsz;
      }
      if ( *((int *)v12 - 3) < 38 )
        ATL::AtlThrowImpl(0x80070057);
      *((_DWORD *)v12 - 4) = 38;
      lpsz[38] = 0;
      v13 = StringFromGUID2(rguid, v12, 39);
      v14 = v13 - 1;
      if ( v13 <= 0 )
        v14 = 0;
      if ( v14 == -1 )
      {
        if ( lpsz )
        {
          v15 = -1;
          do
            ++v15;
          while ( lpsz[v15] );
        }
        else
        {
          LODWORD(v15) = 0;
        }
      }
      else
      {
        LODWORD(v15) = v14;
      }
      if ( (int)v15 < 0 || (int)v15 > *((_DWORD *)lpsz - 3) )
        ATL::AtlThrowImpl(0x80070057);
      *((_DWORD *)lpsz - 4) = v15;
      lpsz[(int)v15] = 0;
      v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(
              &lpsz,
              L"{}");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        v16,
        L"{}");
    }
    v17 = AuthenticationContext::AcquireToken(v7, a2, (__int64 *)&lpsz);
    v18 = (APIReq *)operator new(0x28u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\apireq.cpp");
    if ( v18 )
      v19 = APIReq::APIReq(v18, v17, a1);
    else
      v19 = 0;
    v20 = operator new(0x20u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\APIHandle.h");
    v21 = (__int64)v20;
    if ( v20 )
    {
      v20[1] = 0;
      v20[2] = 0;
      v22 = operator new(0x18u);
      if ( v22 )
      {
        v22[2] = 1;
        v22[3] = 1;
        *(_QWORD *)v22 = &std::_Ref_count<APIReq>::`vftable';
        *((_QWORD *)v22 + 2) = v19;
      }
      else
      {
        v22 = 0;
      }
      *(_QWORD *)(v21 + 8) = v19;
      *(_QWORD *)(v21 + 16) = v22;
      *(_DWORD *)v21 = -1440046422;
      *(_BYTE *)(v21 + 24) = 0;
    }
    else
    {
      v21 = 0;
    }
    *((_QWORD *)v19 + 4) = v21;
    v23 = lpsz - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)lpsz - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    result = v21;
  }
  catch ( const Exception *v25 )
  {
    HandleException(a1, v25);
    return 0;
  }
  catch ( const std::exception *v26 )
  {
    HandleException(a1, v26[0]);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000651c  mov     [rsp+arg_8], rbx
0x140006521  mov     [rsp+arg_0], rcx
0x140006526  push    rsi
0x140006527  push    rdi
0x140006528  push    r12
0x14000652a  push    r13
0x14000652c  push    r14
0x14000652e  sub     rsp, 70h
0x140006532  mov     rsi, r8
0x140006535  mov     r12, rdx
0x140006538  mov     rbx, rcx
0x14000653b  xor     ecx, ecx; dwErrCode
0x14000653d  call    cs:__imp_SetLastError
0x140006543  nop
0x140006544  xor     r13d, r13d
0x140006547  test    rbx, rbx
0x14000654a  jz      loc_1400067EE
0x140006550  mov     rcx, rbx
0x140006553  call    ?Validate@?$APIHandle@VAuthenticationContext@@PEAUHADALCONTEXT__@@$0?FFOFFOFG@@@CA_NPEBV1@@Z; APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254> const *)
0x140006558  test    al, al
0x14000655a  jz      loc_1400067EE
0x140006560  mov     rax, [rbx+10h]
0x140006564  test    rax, rax
0x140006567  jz      short loc_14000656D
0x140006569  lock inc dword ptr [rax+8]
0x14000656d  mov     r14, [rbx+8]
0x140006571  mov     [rsp+98h+var_48], r14
0x140006576  mov     rdi, [rbx+10h]
0x14000657a  mov     [rsp+98h+var_40], rdi
0x14000657f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006586  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000658d  mov     rax, [rax+18h]
0x140006591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006596  lea     rdx, [rax+18h]
0x14000659a  mov     [rsp+98h+lpsz], rdx
0x1400065a2  test    rsi, rsi
0x1400065a5  jz      loc_140006681
0x1400065ab  mov     ecx, 1
0x1400065b0  sub     ecx, [rdx-8]
0x1400065b3  mov     eax, [rdx-0Ch]
0x1400065b6  sub     eax, 26h ; '&'
0x1400065b9  or      ecx, eax
0x1400065bb  jge     short loc_1400065D7
0x1400065bd  mov     edx, 26h ; '&'
0x1400065c2  lea     rcx, [rsp+98h+lpsz]
0x1400065ca  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400065cf  mov     rdx, [rsp+98h+lpsz]; lpsz
0x1400065d7  cmp     dword ptr [rdx-0Ch], 26h ; '&'
0x1400065db  jl      loc_1400067D9
0x1400065e1  mov     dword ptr [rdx-10h], 26h ; '&'
0x1400065e8  mov     rax, [rsp+98h+lpsz]
0x1400065f0  mov     [rax+4Ch], r13w
0x1400065f5  mov     r8d, 27h ; '''; cchMax
0x1400065fb  mov     rcx, rsi; rguid
0x1400065fe  call    cs:__imp_StringFromGUID2
0x140006604  lea     edx, [rax-1]
0x140006607  test    eax, eax
0x140006609  cmovle  edx, r13d
0x14000660d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006611  mov     rcx, [rsp+98h+lpsz]
0x140006619  cmp     edx, esi
0x14000661b  jnz     short loc_140006636
0x14000661d  test    rcx, rcx
0x140006620  jnz     short loc_140006627
0x140006622  mov     eax, r13d
0x140006625  jmp     short loc_140006638
0x140006627  mov     rax, rsi
0x14000662a  inc     rax
0x14000662d  cmp     [rcx+rax*2], r13w
0x140006632  jnz     short loc_14000662A
0x140006634  jmp     short loc_140006638
0x140006636  mov     eax, edx
0x140006638  test    eax, eax
0x14000663a  js      loc_1400067E3
0x140006640  cmp     eax, [rcx-0Ch]
0x140006643  jg      loc_1400067E3
0x140006649  mov     [rcx-10h], eax
0x14000664c  movsxd  rdx, eax
0x14000664f  mov     rax, [rsp+98h+lpsz]
0x140006657  mov     [rax+rdx*2], r13w
0x14000665c  lea     rdx, asc_1400337A0; "{}"
0x140006663  lea     rcx, [rsp+98h+lpsz]
0x14000666b  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort const *)
0x140006670  lea     rdx, asc_1400337A0; "{}"
0x140006677  mov     rcx, rax
0x14000667a  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort const *)
0x14000667f  jmp     short loc_140006685
0x140006681  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006685  lea     r8, [rsp+98h+lpsz]
0x14000668d  mov     rdx, r12; unsigned __int16 *
0x140006690  mov     rcx, r14; struct ILogContext *
0x140006693  call    ?AcquireToken@AuthenticationContext@@QEAAPEAVTokenRequest@@PEBGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AuthenticationContext::AcquireToken(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140006698  mov     r14, rax
0x14000669b  mov     [rsp+98h+var_78], rax
0x1400066a0  mov     r9d, 32h ; '2'; int
0x1400066a6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x1400066ad  lea     edx, [r9-31h]; int
0x1400066b1  lea     ecx, [rdx+27h]; unsigned __int64
0x1400066b4  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x1400066b9  mov     [rsp+98h+var_70], rax
0x1400066be  test    rax, rax
0x1400066c1  jz      short loc_1400066D6
0x1400066c3  mov     r8, rbx; struct HADALCONTEXT__ *
0x1400066c6  mov     rdx, r14; struct TokenRequest *
0x1400066c9  mov     rcx, rax; this
0x1400066cc  call    ??0APIReq@@AEAA@PEAVTokenRequest@@PEAUHADALCONTEXT__@@@Z; APIReq::APIReq(TokenRequest *,HADALCONTEXT__ *)
0x1400066d1  mov     r14, rax
0x1400066d4  jmp     short loc_1400066D9
0x1400066d6  mov     r14, r13
0x1400066d9  mov     [rsp+98h+var_70], r14
0x1400066de  mov     r9d, 3Fh ; '?'; int
0x1400066e4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x1400066eb  lea     edx, [r9-3Eh]; int
0x1400066ef  lea     ecx, [rdx+1Fh]; unsigned __int64
0x1400066f2  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x1400066f7  mov     rbx, rax
0x1400066fa  mov     [rsp+98h+var_68], rax
0x1400066ff  test    rax, rax
0x140006702  jz      short loc_140006755
0x140006704  mov     [rax+8], r13
0x140006708  mov     [rax+10h], r13
0x14000670c  mov     [rsp+98h+var_60], r14
0x140006711  mov     ecx, 18h; Size
0x140006716  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000671b  test    rax, rax
0x14000671e  jz      short loc_14000673E
0x140006720  mov     dword ptr [rax+8], 1
0x140006727  mov     dword ptr [rax+0Ch], 1
0x14000672e  lea     rcx, ??_7?$_Ref_count@VAPIReq@@@std@@6B@; const std::_Ref_count<APIReq>::`vftable'
0x140006735  mov     [rax], rcx
0x140006738  mov     [rax+10h], r14
0x14000673c  jmp     short loc_140006741
0x14000673e  mov     rax, r13
0x140006741  mov     [rbx+8], r14
0x140006745  mov     [rbx+10h], rax
0x140006749  mov     dword ptr [rbx], 0AA2AA2AAh
0x14000674f  mov     [rbx+18h], r13b
0x140006753  jmp     short loc_140006758
0x140006755  mov     rbx, r13
0x140006758  mov     [r14+20h], rbx
0x14000675c  mov     rdx, [rsp+98h+lpsz]
0x140006764  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006768  mov     eax, esi
0x14000676a  lock xadd [rdx+10h], eax
0x14000676f  add     eax, esi
0x140006771  test    eax, eax
0x140006773  jg      short loc_140006785
0x140006775  mov     rcx, [rdx]
0x140006778  mov     rax, [rcx]
0x14000677b  mov     rax, [rax+8]
0x14000677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006784  nop
0x140006785  test    rdi, rdi
0x140006788  jz      short loc_1400067BD
0x14000678a  mov     eax, esi
0x14000678c  lock xadd [rdi+8], eax
0x140006791  add     eax, esi
0x140006793  jnz     short loc_1400067BD
0x140006795  mov     rax, [rdi]
0x140006798  mov     rcx, rdi
0x14000679b  mov     rax, [rax]
0x14000679e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067a3  mov     edx, esi
0x1400067a5  lock xadd [rdi+0Ch], edx
0x1400067aa  add     edx, esi
0x1400067ac  jnz     short loc_1400067BD
0x1400067ae  mov     rdx, [rdi]
0x1400067b1  mov     rcx, rdi
0x1400067b4  mov     rax, [rdx+8]
0x1400067b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067bd  mov     rax, rbx
0x1400067c0  jmp     short loc_1400067C4
0x1400067c2  xor     eax, eax
0x1400067c4  mov     rbx, [rsp+98h+arg_8]
0x1400067cc  add     rsp, 70h
0x1400067d0  pop     r14
0x1400067d2  pop     r13
0x1400067d4  pop     r12
0x1400067d6  pop     rdi
0x1400067d7  pop     rsi
0x1400067d8  retn
0x1400067d9  mov     ecx, 80070057h; unsigned int
0x1400067de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400067e3  mov     ecx, 80070057h; unsigned int
0x1400067e8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400067ee  mov     edx, 0CAA1000Eh; unsigned int
0x1400067f3  lea     rcx, [rsp+98h+pExceptionObject]; this
0x1400067f8  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x1400067fd  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x140006804  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140006809  call    _CxxThrowException_0
```
