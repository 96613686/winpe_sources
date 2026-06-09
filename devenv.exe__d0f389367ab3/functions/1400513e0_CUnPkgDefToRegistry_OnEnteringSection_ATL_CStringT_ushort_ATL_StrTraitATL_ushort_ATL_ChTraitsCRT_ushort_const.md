# CUnPkgDefToRegistry::OnEnteringSection(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1400513e0`
- end: `0x1400515c0`
- name: `?OnEnteringSection@CUnPkgDefToRegistry@@MEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140004950`
- `0x140007740`
- `0x1400102a0`
- `0x140011b10`
- `0x140033ab0`
- `0x1400464b0`
- `0x140046514`
- `0x1400513e0`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051494`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051494`
- `ADVAPI32!RevertToSelf` at `0x140051585`
- `ADVAPI32!RevertToSelf` at `0x140051585`
- `VCRUNTIME140!wcsstr` at `0x14005141e`
- `VCRUNTIME140!wcsstr` at `0x14005141e`

## string_xrefs

- `0x14005152c`: `PkgUnDef: Did not find key '%s' to open. Skipping`
- `0x1400514f4`: `PkgUnDef: Error opening key '%s'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUnPkgDefToRegistry::OnEnteringSection(__int64 a1, const wchar_t **a2)
{
  wchar_t *v4; // rax
  __int64 v5; // rax
  const unsigned __int16 **v6; // r14
  unsigned __int16 *v7; // rdx
  bool v8; // di
  int v9; // esi
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // edx
  unsigned int v14; // esi
  unsigned __int16 *v16; // [rsp+20h] [rbp-28h] BYREF
  bool v17; // [rsp+28h] [rbp-20h]

  if ( *((int *)*a2 - 4) >= 0 && (v4 = wcsstr(*a2, L"\\")) != 0 )
    v5 = v4 - *a2;
  else
    LODWORD(v5) = -1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    a2,
    &v16,
    (unsigned int)(v5 + 1),
    (unsigned int)(*((_DWORD *)*a2 - 4) - (v5 + 1)));
  v6 = (const unsigned __int16 **)(a1 + 240);
  ATL::CSimpleStringT<unsigned short,0>::operator=(a1 + 240, &v16);
  v7 = v16 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  }
  *(_WORD *)(a1 + 248) = 0;
  v8 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 176));
  v17 = v8;
  v9 = ATL::CRegKey::Open((ATL::CRegKey *)(a1 + 216), *(HKEY *)(a1 + 208), *v6, 0x2001Fu);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v11 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
  v16 = v11;
  if ( v9 )
  {
    v12 = *v6;
    if ( v9 == 2 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v16,
        L"PkgUnDef: Did not find key '%s' to open. Skipping",
        v12);
      v11 = v16;
      CLogger::LogWarn(v16, 0, **(const unsigned __int16 ***)(a1 + 256));
      v14 = 1;
      *(_BYTE *)(a1 + 249) = 1;
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v16,
        L"PkgUnDef: Error opening key '%s'.",
        v12);
      v13 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v13 = v9;
      v11 = v16;
      CLogger::LogError(v16, v13, **(const unsigned __int16 ***)(a1 + 256));
      v14 = -2147467259;
    }
  }
  else
  {
    v14 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
  }
  if ( v8 )
    RevertToSelf();
  return v14;
}

```

## disassembly

```asm
0x1400513e0  mov     rax, rsp
0x1400513e3  mov     [rax+8], rbx
0x1400513e7  mov     [rax+10h], rbp
0x1400513eb  mov     [rax+18h], rsi
0x1400513ef  mov     [rax+20h], rdi
0x1400513f3  push    r14
0x1400513f5  sub     rsp, 40h
0x1400513f9  mov     rax, cs:__security_cookie
0x140051400  xor     rax, rsp
0x140051403  mov     [rsp+48h+var_18], rax
0x140051408  mov     rbx, rdx
0x14005140b  mov     rbp, rcx
0x14005140e  mov     rcx, [rdx]; Str
0x140051411  cmp     dword ptr [rcx-10h], 0
0x140051415  jl      short loc_140051429
0x140051417  lea     rdx, SubBlock; "\\"
0x14005141e  call    cs:__imp_wcsstr
0x140051424  test    rax, rax
0x140051427  jnz     short loc_14005142E
0x140051429  or      eax, 0FFFFFFFFh
0x14005142c  jmp     short loc_140051434
0x14005142e  sub     rax, [rbx]
0x140051431  sar     rax, 1
0x140051434  lea     r8d, [rax+1]
0x140051438  mov     rax, [rbx]
0x14005143b  mov     r9d, [rax-10h]
0x14005143f  sub     r9d, r8d
0x140051442  lea     rdx, [rsp+48h+var_28]
0x140051447  mov     rcx, rbx
0x14005144a  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x14005144f  lea     r14, [rbp+0F0h]
0x140051456  lea     rdx, [rsp+48h+var_28]
0x14005145b  mov     rcx, r14
0x14005145e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140051463  mov     rdx, [rsp+48h+var_28]
0x140051468  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14005146c  or      eax, 0FFFFFFFFh
0x14005146f  lock xadd [rdx+10h], eax
0x140051474  sub     eax, 1
0x140051477  jg      short loc_140051485
0x140051479  lfence
0x14005147c  mov     rcx, [rdx]
0x14005147f  mov     rax, [rcx]
0x140051482  call    qword ptr [rax+8]
0x140051485  and     word ptr [rbp+0F8h], 0
0x14005148d  mov     rcx, [rbp+0B0h]; hToken
0x140051494  call    cs:__imp_ImpersonateLoggedOnUser
0x14005149a  test    eax, eax
0x14005149c  setnz   dil
0x1400514a0  mov     [rsp+48h+var_20], dil
0x1400514a5  lea     rcx, [rbp+0D8h]; this
0x1400514ac  mov     r9d, 2001Fh; unsigned int
0x1400514b2  mov     r8, [r14]; unsigned __int16 *
0x1400514b5  mov     rdx, [rbp+0D0h]; HKEY
0x1400514bc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400514c1  mov     esi, eax
0x1400514c3  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400514c8  mov     rcx, rax
0x1400514cb  test    rax, rax
0x1400514ce  jz      loc_1400515B5
0x1400514d4  mov     rax, [rax]
0x1400514d7  call    qword ptr [rax+18h]
0x1400514da  lea     rbx, [rax+18h]
0x1400514de  mov     [rsp+48h+var_28], rbx
0x1400514e3  test    esi, esi
0x1400514e5  jz      short loc_14005155F
0x1400514e7  mov     r8, [r14]
0x1400514ea  lea     rcx, [rsp+48h+var_28]
0x1400514ef  cmp     esi, 2
0x1400514f2  jz      short loc_14005152C
0x1400514f4  lea     rdx, aPkgundefErrorO_0; "PkgUnDef: Error opening key '%s'."
0x1400514fb  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140051500  mov     r8, [rbp+100h]
0x140051507  movzx   edx, si
0x14005150a  or      edx, 80070000h
0x140051510  test    esi, esi
0x140051512  cmovle  edx, esi; int
0x140051515  mov     r8, [r8]; unsigned __int16 *
0x140051518  mov     rbx, [rsp+48h+var_28]
0x14005151d  mov     rcx, rbx; unsigned __int16 *
0x140051520  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051525  mov     esi, 80004005h
0x14005152a  jmp     short loc_140051561
0x14005152c  lea     rdx, aPkgundefDidNot; "PkgUnDef: Did not find key '%s' to open"...
0x140051533  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140051538  mov     r8, [rbp+100h]
0x14005153f  mov     r8, [r8]; unsigned __int16 *
0x140051542  xor     edx, edx; int
0x140051544  mov     rbx, [rsp+48h+var_28]
0x140051549  mov     rcx, rbx; unsigned __int16 *
0x14005154c  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140051551  mov     esi, 1
0x140051556  mov     [rbp+0F9h], sil
0x14005155d  jmp     short loc_140051561
0x14005155f  xor     esi, esi
0x140051561  lea     rdx, [rbx-18h]
0x140051565  or      eax, 0FFFFFFFFh
0x140051568  lock xadd [rdx+10h], eax
0x14005156d  sub     eax, 1
0x140051570  jg      short loc_140051580
0x140051572  lfence
0x140051575  mov     rcx, [rdx]
0x140051578  mov     r8, [rcx]
0x14005157b  call    qword ptr [r8+8]
0x14005157f  nop
0x140051580  test    dil, dil
0x140051583  jz      short loc_14005158B
0x140051585  call    cs:__imp_RevertToSelf
0x14005158b  mov     eax, esi
0x14005158d  mov     rcx, [rsp+48h+var_18]
0x140051592  xor     rcx, rsp; StackCookie
0x140051595  call    __security_check_cookie
0x14005159a  mov     rbx, [rsp+48h+arg_0]
0x14005159f  mov     rbp, [rsp+48h+arg_8]
0x1400515a4  mov     rsi, [rsp+48h+arg_10]
0x1400515a9  mov     rdi, [rsp+48h+arg_18]
0x1400515ae  add     rsp, 40h
0x1400515b2  pop     r14
0x1400515b4  retn
0x1400515b5  mov     ecx, 80004005h; int
0x1400515ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
