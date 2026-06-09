# NameMapper::onSyncRequest(IRequest *)

- ea: `0x1800213d0`
- end: `0x180021a39`
- name: `?onSyncRequest@NameMapper@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180022ae0`

## callees

- `0x1800033bc`
- `0x18000acf4`
- `0x18000b24c`
- `0x18000b82c`
- `0x18000c1fc`
- `0x18000c28c`
- `0x18000c4a4`
- `0x18000c808`
- `0x18000d55c`
- `0x18000e754`
- `0x180016884`
- `0x1800169e0`
- `0x18001e620`
- `0x180020f28`
- `0x18002100c`
- `0x18002110c`
- `0x1800213d0`
- `0x180021a40`
- `0x18002309c`
- `0x1800254a0`
- `0x180028660`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800218fb`
- `msvcrt!_wcsupr` at `0x1800218fb`
- `msvcrt!wcschr` at `0x1800216f0`
- `msvcrt!wcschr` at `0x1800218e1`
- `msvcrt!wcschr` at `0x1800216f0`
- `msvcrt!wcschr` at `0x1800218e1`
- `msvcrt!free` at `0x1800219f5`
- `msvcrt!free` at `0x1800219f5`

## string_xrefs

- `0x180021824`: `Username is already an NT4 account name.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall NameMapper::onSyncRequest(NameMapper *a1, struct IRequest *a2)
{
  unsigned __int16 *v3; // rsi
  IdentityHelper *v4; // rcx
  bool v6; // dl
  unsigned __int64 v7; // r14
  IdentityHelper *v8; // rcx
  NameMapper *v9; // rcx
  DS_NAME_FORMAT v10; // r14d
  void *v11; // rax
  int v12; // eax
  wchar_t *v13; // r13
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  wchar_t *v16; // rax
  wchar_t *v17; // r14
  int v18; // r9d
  int v19; // edi
  struct IRequest *v20; // r14
  DS_NAME_FORMAT v21; // [rsp+30h] [rbp-2C8h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-2C0h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-2B8h] BYREF
  struct IAttributesRaw *v24; // [rsp+48h] [rbp-2B0h]
  int v25; // [rsp+50h] [rbp-2A8h]
  unsigned __int64 v26; // [rsp+58h] [rbp-2A0h] BYREF
  unsigned __int64 v27; // [rsp+60h] [rbp-298h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-290h] BYREF
  wchar_t *v29; // [rsp+70h] [rbp-288h]
  struct IRequest *v30; // [rsp+78h] [rbp-280h]
  struct IRequest *v31; // [rsp+80h] [rbp-278h]
  unsigned __int16 *Src[3]; // [rsp+90h] [rbp-268h] BYREF
  unsigned __int64 v33; // [rsp+A8h] [rbp-250h]
  wchar_t Str[256]; // [rsp+B0h] [rbp-248h] BYREF

  v30 = a2;
  v31 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Entering NTSamNames stage");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
    a2 = v30;
  }
  v3 = Str;
  v29 = Str;
  v25 = 0;
  v21 = DS_UNKNOWN_NAME;
  IASTL::IASRequest::IASRequest((IASTL::IASRequest *)v23, a2);
  pv = 0;
  if ( IASTL::IASAttribute::load((IASTL::IASAttribute *)&pv, v24, 0x1FB2u) )
  {
    if ( pv )
      IASAttributeRelease(pv);
    (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
    return 2;
  }
  v26 = 0;
  v27 = 254;
  if ( !IdentityHelper::getIdentity(v4, (struct IASTL::IASRequest *)v23, Str, &v27, &v26, (unsigned int *)&v21) )
  {
    v7 = v26;
    v3 = (unsigned __int16 *)operator new(saturated_mul(v26, 2u));
    v29 = v3;
    v27 = v7;
    if ( !IdentityHelper::getIdentity(v8, (struct IASTL::IASRequest *)v23, v3, &v27, &v26, (unsigned int *)&v21) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Error: no user identity found");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
      }
      _com_issue_error(118);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("not looking for MS_ATTRIBUTE_IDENTITY_TYPE (health check only) attribute any more. user authentication w"
                "ill always be performed");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
  }
  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v22, v6);
  *((_DWORD *)v22 + 2) = 4129;
  v21 = DS_UNKNOWN_NAME;
  if ( !NameMapper::isCrackable(a1, v3, &v21) )
    goto LABEL_54;
  v10 = v21;
  if ( v21 == DS_NT4_ACCOUNT_NAME || v21 == DS_DNS_DOMAIN_NAME )
  {
    v12 = ourRole;
    if ( !ourRole || !ourProductType )
    {
      v13 = wcschr(v3, 0x5Cu);
      *v13 = 0;
      if ( !(unsigned int)IASIsDomainLocal(v3) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Non-local users are not allowed -- rejecting.");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
        }
        _com_issue_error(32);
      }
      *v13 = 92;
      v12 = ourRole;
    }
    if ( v10 == DS_DNS_DOMAIN_NAME && v12 )
    {
      v33 = 7;
      Src[2] = 0;
      LOWORD(Src[0]) = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, wchar_t *, unsigned __int16 **))(*(_QWORD *)NameMapper::pCracker
                                                                                   + 16LL))(
             NameMapper::pCracker,
             Str,
             Src) )
      {
        IASTL::IASAttribute::setString((IASTL::IASAttribute *)&v22, v3);
      }
      else
      {
        v14 = (const unsigned __int16 *)Src;
        if ( v33 >= 8 )
          v14 = Src[0];
        IASTL::IASAttribute::setString((IASTL::IASAttribute *)&v22, v14);
      }
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Username is already an NT4 account name.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
      }
      IASTL::IASAttribute::setString((IASTL::IASAttribute *)&v22, v3);
    }
    goto LABEL_60;
  }
  if ( !ourRole )
  {
    if ( v21 == -17 || v21 == DS_USER_PRINCIPAL_NAME )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("IAS role is stand-alone and user format is UPN");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
      }
      v11 = NameMapper::copyIdentity(v9, v3);
LABEL_59:
      *((_QWORD *)v22 + 4) = v11;
      *((_QWORD *)v22 + 3) = 0;
      *((_DWORD *)v22 + 4) = 5;
      goto LABEL_60;
    }
LABEL_54:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Prepending default domain.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
    }
    v11 = NameMapper::prependDefaultDomain(v9, v3);
    goto LABEL_59;
  }
  NameMapper::mapName(v9, v3, (struct IASTL::IASAttribute *)&v22, v21, 0);
LABEL_60:
  v16 = wcschr(*((const wchar_t **)v22 + 4), 0x5Cu);
  v17 = v16;
  if ( v16 )
  {
    *v16 = 0;
    _wcsupr(*((wchar_t **)v22 + 4));
    *v17 = 92;
  }
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&v22, v24);
  IASStoreFQUserName(v24, DS_NT4_ACCOUNT_NAME, *((unsigned __int16 **)v22 + 4));
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&NameMapper::theNameMapped, v24);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("SAM-Account-Name is \"%S\".");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_40bf13076849362e12b869b0ef4fb463_Traceguids,
      v18,
      *((_QWORD *)v22 + 4));
  }
  if ( v22 )
    IASAttributeRelease(v22);
  if ( pv )
    IASAttributeRelease(pv);
  (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
  v19 = v25;
  v20 = v30;
  if ( v3 != Str )
    free(v3);
  if ( v19 && v19 < 0xFFFF )
    return IASProcessFailure(v20, (unsigned int)v19);
  else
    return 2;
}

```

## disassembly

```asm
0x1800213d0  push    rbx
0x1800213d2  push    rsi
0x1800213d3  push    rdi
0x1800213d4  push    r13
0x1800213d6  push    r14
0x1800213d8  push    r15
0x1800213da  sub     rsp, 2C8h
0x1800213e1  mov     rax, cs:__security_cookie
0x1800213e8  xor     rax, rsp
0x1800213eb  mov     [rsp+2F8h+var_48], rax
0x1800213f3  mov     [rsp+2F8h+var_280], rdx
0x1800213f8  mov     r15, rcx
0x1800213fb  mov     [rsp+2F8h+var_278], rdx
0x180021403  lea     r13, WPP_GLOBAL_Control
0x18002140a  mov     rax, cs:WPP_GLOBAL_Control
0x180021411  mov     dil, 4
0x180021414  cmp     rax, r13
0x180021417  jz      short loc_180021459
0x180021419  cmp     [rax+19h], dil
0x18002141d  jb      short loc_180021459
0x18002141f  test    [rax+1Ch], dil
0x180021423  jz      short loc_180021459
0x180021425  lea     rcx, aEnteringNtsamn; "Entering NTSamNames stage"
0x18002142c  call    WppDbgPrint
0x180021431  mov     edx, 0Ah
0x180021436  lea     r9, aNpssvc; "NPSSVC"
0x18002143d  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021444  mov     rcx, cs:WPP_GLOBAL_Control
0x18002144b  mov     rcx, [rcx+10h]
0x18002144f  call    WPP_SF_s
0x180021454  mov     rdx, [rsp+2F8h+var_280]; struct IRequest *
0x180021459  lea     rsi, [rsp+2F8h+Str]
0x180021461  mov     [rsp+2F8h+var_288], rsi
0x180021466  xor     ebx, ebx
0x180021468  mov     [rsp+2F8h+var_2A8], ebx
0x18002146c  mov     [rsp+2F8h+var_2C8], ebx
0x180021470  lea     rcx, [rsp+2F8h+var_2B8]; this
0x180021475  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x18002147a  nop
0x18002147b  mov     [rsp+2F8h+pv], rbx
0x180021480  mov     r8d, 1FB2h; unsigned int
0x180021486  mov     rdx, [rsp+2F8h+var_2B0]; struct IAttributesRaw *
0x18002148b  lea     rcx, [rsp+2F8h+pv]; this
0x180021490  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@K@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong)
0x180021495  test    al, al
0x180021497  jz      short loc_1800214C5
0x180021499  mov     rcx, [rsp+2F8h+pv]; pv
0x18002149e  test    rcx, rcx
0x1800214a1  jz      short loc_1800214A9
0x1800214a3  call    IASAttributeRelease
0x1800214a8  nop
0x1800214a9  mov     rcx, [rsp+2F8h+var_2B0]
0x1800214ae  mov     rax, [rcx]
0x1800214b1  mov     rax, [rax+10h]
0x1800214b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214ba  nop
0x1800214bb  mov     eax, 2
0x1800214c0  jmp     loc_180021A18
0x1800214c5  mov     [rsp+2F8h+var_2A0], rbx
0x1800214ca  mov     [rsp+2F8h+var_298], 0FEh
0x1800214d3  lea     rax, [rsp+2F8h+var_2C8]
0x1800214d8  mov     [rsp+2F8h+var_2D0], rax; unsigned int *
0x1800214dd  lea     rax, [rsp+2F8h+var_2A0]
0x1800214e2  mov     [rsp+2F8h+var_2D8], rax; unsigned __int64 *
0x1800214e7  lea     r9, [rsp+2F8h+var_298]; unsigned __int64 *
0x1800214ec  lea     r8, [rsp+2F8h+Str]; unsigned __int16 *
0x1800214f4  lea     rdx, [rsp+2F8h+var_2B8]; struct IASTL::IASRequest *
0x1800214f9  call    ?getIdentity@IdentityHelper@@QEAA_NAEAVIASRequest@IASTL@@PEAGAEA_K2AEAK@Z; IdentityHelper::getIdentity(IASTL::IASRequest &,ushort *,unsigned __int64 &,unsigned __int64 &,ulong &)
0x1800214fe  test    al, al
0x180021500  jnz     loc_1800215AE
0x180021506  mov     eax, 2
0x18002150b  mov     r14, [rsp+2F8h+var_2A0]
0x180021510  mul     r14
0x180021513  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002151a  cmovb   rax, rcx
0x18002151e  mov     rcx, rax; Size
0x180021521  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021526  mov     rsi, rax
0x180021529  mov     [rsp+2F8h+var_288], rax
0x18002152e  mov     [rsp+2F8h+var_298], r14
0x180021533  lea     rax, [rsp+2F8h+var_2C8]
0x180021538  mov     [rsp+2F8h+var_2D0], rax; unsigned int *
0x18002153d  lea     rax, [rsp+2F8h+var_2A0]
0x180021542  mov     [rsp+2F8h+var_2D8], rax; unsigned __int64 *
0x180021547  lea     r9, [rsp+2F8h+var_298]; unsigned __int64 *
0x18002154c  mov     r8, rsi; unsigned __int16 *
0x18002154f  lea     rdx, [rsp+2F8h+var_2B8]; struct IASTL::IASRequest *
0x180021554  call    ?getIdentity@IdentityHelper@@QEAA_NAEAVIASRequest@IASTL@@PEAGAEA_K2AEAK@Z; IdentityHelper::getIdentity(IASTL::IASRequest &,ushort *,unsigned __int64 &,unsigned __int64 &,ulong &)
0x180021559  test    al, al
0x18002155b  jnz     short loc_1800215AE
0x18002155d  mov     rax, cs:WPP_GLOBAL_Control
0x180021564  cmp     rax, r13
0x180021567  jz      short loc_1800215A4
0x180021569  cmp     byte ptr [rax+19h], 2
0x18002156d  jb      short loc_1800215A4
0x18002156f  test    [rax+1Ch], dil
0x180021573  jz      short loc_1800215A4
0x180021575  lea     rcx, aErrorNoUserIde; "Error: no user identity found"
0x18002157c  call    WppDbgPrint
0x180021581  mov     edx, 0Bh
0x180021586  lea     r9, aNpssvc; "NPSSVC"
0x18002158d  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021594  mov     rcx, cs:WPP_GLOBAL_Control
0x18002159b  mov     rcx, [rcx+10h]
0x18002159f  call    WPP_SF_s
0x1800215a4  mov     ecx, 76h ; 'v'; int
0x1800215a9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800215ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800215b5  cmp     rax, r13
0x1800215b8  jz      short loc_1800215F5
0x1800215ba  cmp     [rax+19h], dil
0x1800215be  jb      short loc_1800215F5
0x1800215c0  test    [rax+1Ch], dil
0x1800215c4  jz      short loc_1800215F5
0x1800215c6  lea     rcx, aNotLookingForM; "not looking for MS_ATTRIBUTE_IDENTITY_T"...
0x1800215cd  call    WppDbgPrint
0x1800215d2  mov     edx, 0Ch
0x1800215d7  lea     r9, aNpssvc; "NPSSVC"
0x1800215de  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x1800215e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215ec  mov     rcx, [rcx+10h]
0x1800215f0  call    WPP_SF_s
0x1800215f5  lea     rcx, [rsp+2F8h+var_2C0]; this
0x1800215fa  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x1800215ff  nop
0x180021600  mov     rax, [rsp+2F8h+var_2C0]
0x180021605  mov     dword ptr [rax+8], 1021h
0x18002160c  mov     [rsp+2F8h+var_2C8], ebx
0x180021610  lea     r8, [rsp+2F8h+var_2C8]; enum DS_NAME_FORMAT *
0x180021615  mov     rdx, rsi; unsigned __int16 *
0x180021618  mov     rcx, r15; this
0x18002161b  call    ?isCrackable@NameMapper@@IEBA_NPEBGAEAW4DS_NAME_FORMAT@@@Z; NameMapper::isCrackable(ushort const *,DS_NAME_FORMAT &)
0x180021620  test    al, al
0x180021622  jz      loc_180021862
0x180021628  mov     r14d, [rsp+2F8h+var_2C8]
0x18002162d  cmp     r14d, 2
0x180021631  jz      loc_1800216C7
0x180021637  cmp     r14d, 0Ch
0x18002163b  jz      loc_1800216C7
0x180021641  cmp     cs:ourRole, ebx
0x180021647  jz      short loc_180021663
0x180021649  mov     [rsp+2F8h+var_2D8], rbx; unsigned __int16 *
0x18002164e  mov     r9d, r14d; enum DS_NAME_FORMAT
0x180021651  lea     r8, [rsp+2F8h+var_2C0]; struct IASTL::IASAttribute *
0x180021656  mov     rdx, rsi; unsigned __int16 *
0x180021659  call    ?mapName@NameMapper@@IEAAXPEBGAEAVIASAttribute@IASTL@@W4DS_NAME_FORMAT@@0@Z; NameMapper::mapName(ushort const *,IASTL::IASAttribute &,DS_NAME_FORMAT,ushort const *)
0x18002165e  jmp     loc_1800218CF
0x180021663  cmp     r14d, 0FFFFFFEFh
0x180021667  jz      short loc_180021673
0x180021669  cmp     r14d, 8
0x18002166d  jnz     loc_180021862
0x180021673  mov     rax, cs:WPP_GLOBAL_Control
0x18002167a  cmp     rax, r13
0x18002167d  jz      short loc_1800216BA
0x18002167f  cmp     [rax+19h], dil
0x180021683  jb      short loc_1800216BA
0x180021685  test    [rax+1Ch], dil
0x180021689  jz      short loc_1800216BA
0x18002168b  lea     rcx, aIasRoleIsStand; "IAS role is stand-alone and user format"...
0x180021692  call    WppDbgPrint
0x180021697  mov     edx, 0Fh
0x18002169c  lea     r9, aNpssvc; "NPSSVC"
0x1800216a3  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x1800216aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216b1  mov     rcx, [rcx+10h]
0x1800216b5  call    WPP_SF_s
0x1800216ba  mov     rdx, rsi; unsigned __int16 *
0x1800216bd  call    ?copyIdentity@NameMapper@@IEAAPEAGPEBG@Z; NameMapper::copyIdentity(ushort const *)
0x1800216c2  jmp     loc_1800218B1
0x1800216c7  mov     eax, cs:ourRole
0x1800216cd  test    eax, eax
0x1800216cf  jz      short loc_1800216E4
0x1800216d1  cmp     cs:ourProductType, ebx
0x1800216d7  jz      short loc_1800216E4
0x1800216d9  mov     r15d, 5Ch ; '\'
0x1800216df  jmp     loc_180021771
0x1800216e4  mov     r15d, 5Ch ; '\'
0x1800216ea  mov     edx, r15d; Ch
0x1800216ed  mov     rcx, rsi; Str
0x1800216f0  call    cs:__imp_wcschr
0x1800216f6  mov     r13, rax
0x1800216f9  mov     [rax], bx
0x1800216fc  mov     rcx, rsi
0x1800216ff  call    IASIsDomainLocal
0x180021704  test    eax, eax
0x180021706  jnz     short loc_18002175F
0x180021708  mov     rax, cs:WPP_GLOBAL_Control
0x18002170f  lea     rcx, WPP_GLOBAL_Control
0x180021716  cmp     rax, rcx
0x180021719  jz      short loc_180021755
0x18002171b  cmp     byte ptr [rax+19h], 2
0x18002171f  jb      short loc_180021755
0x180021721  test    [rax+1Ch], dil
0x180021725  jz      short loc_180021755
0x180021727  lea     rcx, aNonLocalUsersA; "Non-local users are not allowed -- reje"...
0x18002172e  call    WppDbgPrint
0x180021733  lea     edx, [r15-4Fh]
0x180021737  lea     r9, aNpssvc; "NPSSVC"
0x18002173e  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021745  mov     rcx, cs:WPP_GLOBAL_Control
0x18002174c  mov     rcx, [rcx+10h]
0x180021750  call    WPP_SF_s
0x180021755  mov     ecx, 20h ; ' '; int
0x18002175a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002175f  mov     [r13+0], r15w
0x180021764  mov     eax, cs:ourRole
0x18002176a  lea     r13, WPP_GLOBAL_Control
0x180021771  cmp     r14d, 0Ch
0x180021775  jnz     loc_18002180C
0x18002177b  test    eax, eax
0x18002177d  jz      loc_18002180C
0x180021783  mov     [rsp+2F8h+var_250], 7
0x18002178f  mov     [rsp+2F8h+var_258], rbx
0x180021797  mov     word ptr [rsp+2F8h+Src], bx
0x18002179f  mov     rcx, cs:?pCracker@NameMapper@@1V?$auto_ptr@VNameCracker@@@std@@A; std::auto_ptr<NameCracker> NameMapper::pCracker
0x1800217a6  mov     rax, [rcx]
0x1800217a9  lea     r8, [rsp+2F8h+Src]
0x1800217b1  lea     rdx, [rsp+2F8h+Str]
0x1800217b9  mov     rax, [rax+10h]
0x1800217bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c2  lea     rcx, [rsp+2F8h+var_2C0]; this
0x1800217c7  test    eax, eax
0x1800217c9  jnz     short loc_1800217EC
0x1800217cb  lea     rdx, [rsp+2F8h+Src]
0x1800217d3  cmp     [rsp+2F8h+var_250], 8
0x1800217dc  cmovnb  rdx, [rsp+2F8h+Src]; Src
0x1800217e5  call    ?setString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setString(ushort const *)
0x1800217ea  jmp     short loc_1800217F5
0x1800217ec  mov     rdx, rsi; Src
0x1800217ef  call    ?setString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setString(ushort const *)
0x1800217f4  nop
0x1800217f5  xor     r8d, r8d
0x1800217f8  mov     dl, 1
0x1800217fa  lea     rcx, [rsp+2F8h+Src]
0x180021802  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180021807  jmp     loc_1800218D5
0x18002180c  mov     rax, cs:WPP_GLOBAL_Control
0x180021813  cmp     rax, r13
0x180021816  jz      short loc_180021853
0x180021818  cmp     [rax+19h], dil
0x18002181c  jb      short loc_180021853
0x18002181e  test    [rax+1Ch], dil
0x180021822  jz      short loc_180021853
0x180021824  lea     rcx, aUsernameIsAlre; "Username is already an NT4 account name"...
0x18002182b  call    WppDbgPrint
0x180021830  mov     edx, 0Eh
0x180021835  lea     r9, aNpssvc; "NPSSVC"
0x18002183c  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021843  mov     rcx, cs:WPP_GLOBAL_Control
0x18002184a  mov     rcx, [rcx+10h]
0x18002184e  call    WPP_SF_s
0x180021853  mov     rdx, rsi; Src
0x180021856  lea     rcx, [rsp+2F8h+var_2C0]; this
0x18002185b  call    ?setString@IASAttribute@IASTL@@QEAAXPEBG@Z; IASTL::IASAttribute::setString(ushort const *)
0x180021860  jmp     short loc_1800218D5
0x180021862  mov     rax, cs:WPP_GLOBAL_Control
0x180021869  cmp     rax, r13
0x18002186c  jz      short loc_1800218A9
0x18002186e  cmp     [rax+19h], dil
0x180021872  jb      short loc_1800218A9
0x180021874  test    [rax+1Ch], dil
0x180021878  jz      short loc_1800218A9
0x18002187a  lea     rcx, aPrependingDefa; "Prepending default domain."
0x180021881  call    WppDbgPrint
0x180021886  mov     edx, 10h
0x18002188b  lea     r9, aNpssvc; "NPSSVC"
0x180021892  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218a0  mov     rcx, [rcx+10h]
0x1800218a4  call    WPP_SF_s
0x1800218a9  mov     rdx, rsi; unsigned __int16 *
0x1800218ac  call    ?prependDefaultDomain@NameMapper@@IEAAPEAGPEBG@Z; NameMapper::prependDefaultDomain(ushort const *)
0x1800218b1  mov     rcx, [rsp+2F8h+var_2C0]
0x1800218b6  mov     [rcx+20h], rax
0x1800218ba  mov     rax, [rsp+2F8h+var_2C0]
0x1800218bf  mov     [rax+18h], rbx
0x1800218c3  mov     rax, [rsp+2F8h+var_2C0]
0x1800218c8  mov     dword ptr [rax+10h], 5
0x1800218cf  mov     r15d, 5Ch ; '\'
0x1800218d5  mov     edx, r15d; Ch
0x1800218d8  mov     rcx, [rsp+2F8h+var_2C0]
0x1800218dd  mov     rcx, [rcx+20h]; Str
0x1800218e1  call    cs:__imp_wcschr
0x1800218e7  mov     r14, rax
0x1800218ea  test    rax, rax
0x1800218ed  jz      short loc_180021905
0x1800218ef  mov     [rax], bx
0x1800218f2  mov     rcx, [rsp+2F8h+var_2C0]
0x1800218f7  mov     rcx, [rcx+20h]; String
0x1800218fb  call    cs:__imp__wcsupr
0x180021901  mov     [r14], r15w
0x180021905  mov     rdx, [rsp+2F8h+var_2B0]; struct IAttributesRaw *
0x18002190a  lea     rcx, [rsp+2F8h+var_2C0]; this
0x18002190f  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x180021914  mov     r8, [rsp+2F8h+var_2C0]
0x180021919  mov     r8, [r8+20h]; unsigned __int16 *
0x18002191d  mov     edx, 2; enum DS_NAME_FORMAT
0x180021922  mov     rcx, [rsp+2F8h+var_2B0]; struct IAttributesRaw *
0x180021927  call    ?IASStoreFQUserName@@YAJPEAUIAttributesRaw@@W4DS_NAME_FORMAT@@PEBG@Z; IASStoreFQUserName(IAttributesRaw *,DS_NAME_FORMAT,ushort const *)
0x18002192c  mov     rdx, [rsp+2F8h+var_2B0]; struct IAttributesRaw *
  ... truncated ...
```
