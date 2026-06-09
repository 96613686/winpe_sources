# UstCommon::CWmiLanternObject::GetContextProperties(IWbemContext *)

- ea: `0x1800273f0`
- end: `0x1800278fd`
- name: `?GetContextProperties@CWmiLanternObject@UstCommon@@EEAAJPEAUIWbemContext@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(UstCommon::CWmiLanternObject *__hidden this, struct IWbemContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x18000f60c`
- `0x180014068`
- `0x1800273f0`
- `0x180027df4`
- `0x180027eac`
- `0x18002c010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800275b1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800275b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800274b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800274e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027652`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800274b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800274e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180027652`
- `OLEAUT32!__imp_VariantInit` at `0x18002741e`
- `OLEAUT32!__imp_VariantInit` at `0x18002741e`
- `OLEAUT32!__imp_VariantClear` at `0x180027544`
- `OLEAUT32!__imp_VariantClear` at `0x1800276ee`
- `OLEAUT32!__imp_VariantClear` at `0x180027749`
- `OLEAUT32!__imp_VariantClear` at `0x1800277a4`
- `OLEAUT32!__imp_VariantClear` at `0x180027800`
- `OLEAUT32!__imp_VariantClear` at `0x18002788a`
- `OLEAUT32!__imp_VariantClear` at `0x180027544`
- `OLEAUT32!__imp_VariantClear` at `0x1800276ee`
- `OLEAUT32!__imp_VariantClear` at `0x180027749`
- `OLEAUT32!__imp_VariantClear` at `0x1800277a4`
- `OLEAUT32!__imp_VariantClear` at `0x180027800`
- `OLEAUT32!__imp_VariantClear` at `0x18002788a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800275a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800275a3`

## string_xrefs

- `0x1800277b5`: `PolicyPlatformContext_PrincipalContext_ProcessId`
- `0x180027811`: `PolicyPlatformContext_PrincipalContext_UserToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UstCommon::CWmiLanternObject::GetContextProperties(
        UstCommon::CWmiLanternObject *this,
        struct IWbemContext *a2)
{
  int v4; // eax
  signed int v5; // ebx
  const WCHAR *bstrVal; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  const wchar_t *v10; // r9
  int v11; // eax
  __int64 Lo; // r9
  int v13; // eax
  __int64 v14; // r9
  int v15; // eax
  __int64 uiVal; // r9
  int v17; // eax
  __int64 v18; // r8
  LONGLONG llVal; // r9
  __int64 v20; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  PSID Sid; // [rsp+A8h] [rbp+50h] BYREF

  if ( a2 )
  {
    VariantInit(&pvarg);
    v4 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
           a2,
           L"PolicyPlatformContext_PrincipalContext_Type",
           0,
           &pvarg);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
          (unsigned int)v4);
      goto LABEL_71;
    }
    if ( pvarg.vt == 8 && (bstrVal = pvarg.bstrVal) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_S(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          32,
          WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
          pvarg.llVal);
        bstrVal = pvarg.bstrVal;
      }
      if ( CompareStringOrdinal(bstrVal, -1, L"PolicyPlatform_MachineContext", -1, 1) == 2 )
      {
        *((_DWORD *)this + 2) = 1;
        goto LABEL_20;
      }
      if ( CompareStringOrdinal(pvarg.bstrVal, -1, L"PolicyPlatform_UserContext", -1, 1) == 2 )
      {
        *((_DWORD *)this + 2) = 2;
        goto LABEL_20;
      }
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
LABEL_19:
        v5 = -2147024809;
LABEL_20:
        if ( v5 < 0 )
        {
LABEL_71:
          VariantClear(&pvarg);
LABEL_75:
          v20 = WPP_GLOBAL_Control;
          goto LABEL_76;
        }
        VariantClear(&pvarg);
        v5 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
               a2,
               L"PolicyPlatformContext_PrincipalContext_Id",
               0,
               &pvarg);
        if ( v5 < 0 )
          goto LABEL_33;
        if ( pvarg.vt != 8 || !pvarg.llVal )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids);
            v9 = WPP_GLOBAL_Control;
          }
          v5 = -2147024809;
          goto LABEL_34;
        }
        if ( *((_DWORD *)this + 2) == 2 )
        {
          v5 = -2147024809;
          Sid = 0;
          if ( ConvertStringSidToSidW(pvarg.bstrVal, &Sid) )
          {
            v5 = !IsValidSid(Sid) ? 0x80070057 : 0;
            LocalFree(Sid);
          }
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
            goto LABEL_31;
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            36,
            WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
            (unsigned int)v5);
        }
        else if ( CompareStringOrdinal(pvarg.bstrVal, -1, L"SYSTEM", -1, 1) != 2 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 37, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids);
            v9 = WPP_GLOBAL_Control;
          }
          v5 = -2147024809;
          goto LABEL_31;
        }
        v9 = WPP_GLOBAL_Control;
LABEL_31:
        if ( v5 < 0 )
          goto LABEL_34;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 16,
          pvarg.llVal);
        pvarg.llVal = 0;
LABEL_33:
        v9 = WPP_GLOBAL_Control;
LABEL_34:
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 2) != 0 )
        {
          if ( v5 < 0 )
            v10 = L"<FAILED>";
          else
            v10 = (const wchar_t *)*((_QWORD *)this + 2);
          WPP_SF_S(*(_QWORD *)(v9 + 16), 39, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, v10);
        }
        if ( v5 >= 0 && *((_DWORD *)this + 2) == 2 )
        {
          VariantClear(&pvarg);
          v11 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
                  a2,
                  L"PolicyPlatformContext_PrincipalContext_UserSession",
                  0,
                  &pvarg);
          if ( v11 >= 0 )
          {
            Lo = pvarg.cyVal.Lo;
            *((_DWORD *)this + 6) = pvarg.lVal;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                40,
                WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
                Lo,
                v11);
            }
          }
          VariantClear(&pvarg);
          v13 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
                  a2,
                  L"PolicyPlatformContext_PrincipalContext_Flags",
                  0,
                  &pvarg);
          if ( v13 >= 0 )
          {
            v14 = pvarg.cyVal.Lo;
            *((_DWORD *)this + 7) = pvarg.lVal;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                41,
                WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
                v14,
                v13);
            }
          }
          VariantClear(&pvarg);
          v15 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
                  a2,
                  L"PolicyPlatformContext_PrincipalContext_ProcessId",
                  0,
                  &pvarg);
          if ( v15 >= 0 )
          {
            uiVal = pvarg.uiVal;
            *((_DWORD *)this + 10) = pvarg.uiVal;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_dd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                42,
                WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
                uiVal,
                v15);
            }
          }
          VariantClear(&pvarg);
          v17 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a2->lpVtbl->GetValue)(
                  a2,
                  L"PolicyPlatformContext_PrincipalContext_UserToken",
                  0,
                  &pvarg);
          if ( v17 >= 0 )
          {
            llVal = pvarg.llVal;
            *((_QWORD *)this + 6) = pvarg.llVal;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_iD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, v18, llVal, v17);
            }
          }
          v5 = 0;
        }
        goto LABEL_71;
      }
      v8 = 33;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_19;
      v8 = 34;
    }
    WPP_SF_(*(_QWORD *)(v7 + 16), v8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids);
    goto LABEL_19;
  }
  v5 = -2147024809;
  v20 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids);
    goto LABEL_75;
  }
LABEL_76:
  if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 2) != 0 )
    WPP_SF_d(*(_QWORD *)(v20 + 16), 45, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800273f0  push    rbp
0x1800273f2  push    rbx
0x1800273f3  push    rsi
0x1800273f4  push    rdi
0x1800273f5  push    r12
0x1800273f7  push    r13
0x1800273f9  push    r14
0x1800273fb  push    r15
0x1800273fd  mov     rbp, rsp
0x180027400  sub     rsp, 58h
0x180027404  mov     r12, rdx
0x180027407  mov     r15, rcx
0x18002740a  lea     r13, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027411  test    rdx, rdx
0x180027414  jz      loc_180027892
0x18002741a  lea     rcx, [rbp+pvarg]; pvarg
0x18002741e  call    cs:__imp_VariantInit
0x180027424  nop
0x180027425  mov     rax, [r12]
0x180027429  lea     r9, [rbp+pvarg]
0x18002742d  xor     r8d, r8d
0x180027430  lea     rdx, aPolicyplatform_2; "PolicyPlatformContext_PrincipalContext_"...
0x180027437  mov     rcx, r12
0x18002743a  mov     rax, [rax+48h]
0x18002743e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027443  mov     ebx, eax
0x180027445  mov     edi, 2
0x18002744a  test    eax, eax
0x18002744c  js      loc_180027858
0x180027452  mov     r14d, 80070057h
0x180027458  cmp     word ptr [rbp+pvarg], 8
0x18002745d  jnz     loc_18002750B
0x180027463  mov     rcx, qword ptr [rbp+pvarg+8]
0x180027467  test    rcx, rcx
0x18002746a  jz      loc_18002750B
0x180027470  lea     rsi, WPP_GLOBAL_Control
0x180027477  mov     rax, cs:WPP_GLOBAL_Control
0x18002747e  cmp     rax, rsi
0x180027481  jz      short loc_18002749F
0x180027483  test    [rax+1Ch], dil
0x180027487  jz      short loc_18002749F
0x180027489  lea     edx, [rdi+1Eh]
0x18002748c  mov     r9, rcx
0x18002748f  mov     r8, r13
0x180027492  mov     rcx, [rax+10h]
0x180027496  call    WPP_SF_S
0x18002749b  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x18002749f  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800274a7  or      r9d, 0FFFFFFFFh; cchCount2
0x1800274ab  lea     r8, aPolicyplatform_4; "PolicyPlatform_MachineContext"
0x1800274b2  or      edx, r9d; cchCount1
0x1800274b5  call    cs:__imp_CompareStringOrdinal
0x1800274bb  cmp     eax, edi
0x1800274bd  jnz     short loc_1800274C9
0x1800274bf  mov     dword ptr [r15+8], 1
0x1800274c7  jmp     short loc_180027538
0x1800274c9  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800274d1  or      edx, 0FFFFFFFFh; cchCount1
0x1800274d4  mov     r9d, edx; cchCount2
0x1800274d7  lea     r8, aPolicyplatform_0; "PolicyPlatform_UserContext"
0x1800274de  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x1800274e2  call    cs:__imp_CompareStringOrdinal
0x1800274e8  cmp     eax, edi
0x1800274ea  jnz     short loc_1800274F2
0x1800274ec  mov     [r15+8], edi
0x1800274f0  jmp     short loc_180027538
0x1800274f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274f9  cmp     rcx, rsi
0x1800274fc  jz      short loc_180027535
0x1800274fe  test    [rcx+1Ch], dil
0x180027502  jz      short loc_180027535
0x180027504  mov     edx, 21h ; '!'
0x180027509  jmp     short loc_180027529
0x18002750b  lea     rsi, WPP_GLOBAL_Control
0x180027512  mov     rcx, cs:WPP_GLOBAL_Control
0x180027519  cmp     rcx, rsi
0x18002751c  jz      short loc_180027535
0x18002751e  test    [rcx+1Ch], dil
0x180027522  jz      short loc_180027535
0x180027524  mov     edx, 22h ; '"'
0x180027529  mov     r8, r13
0x18002752c  mov     rcx, [rcx+10h]
0x180027530  call    WPP_SF_
0x180027535  mov     ebx, r14d
0x180027538  test    ebx, ebx
0x18002753a  js      loc_180027886
0x180027540  lea     rcx, [rbp+pvarg]; pvarg
0x180027544  call    cs:__imp_VariantClear
0x18002754a  mov     rax, [r12]
0x18002754e  lea     r9, [rbp+pvarg]
0x180027552  xor     r8d, r8d
0x180027555  lea     rdx, aPolicyplatform_6; "PolicyPlatformContext_PrincipalContext_"...
0x18002755c  mov     rcx, r12
0x18002755f  mov     rax, [rax+48h]
0x180027563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027568  mov     ebx, eax
0x18002756a  test    eax, eax
0x18002756c  js      loc_180027610
0x180027572  cmp     word ptr [rbp+pvarg], 8
0x180027577  jnz     loc_18002768E
0x18002757d  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x180027581  test    rcx, rcx
0x180027584  jz      loc_18002768E
0x18002758a  cmp     [r15+8], edi
0x18002758e  jnz     loc_18002763B
0x180027594  mov     ebx, r14d
0x180027597  mov     [rbp+Sid], 0
0x18002759f  lea     rdx, [rbp+Sid]; Sid
0x1800275a3  call    cs:__imp_ConvertStringSidToSidW
0x1800275a9  test    eax, eax
0x1800275ab  jz      short loc_1800275CA
0x1800275ad  mov     rcx, [rbp+Sid]; pSid
0x1800275b1  call    cs:__imp_IsValidSid
0x1800275b7  neg     eax
0x1800275b9  sbb     ebx, ebx
0x1800275bb  not     ebx
0x1800275bd  and     ebx, r14d
0x1800275c0  mov     rcx, [rbp+Sid]; hMem
0x1800275c4  call    cs:__imp_LocalFree
0x1800275ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275d1  cmp     rcx, rsi
0x1800275d4  jz      short loc_1800275F7
0x1800275d6  test    [rcx+1Ch], dil
0x1800275da  jz      short loc_1800275F7
0x1800275dc  mov     edx, 24h ; '$'
0x1800275e1  mov     r9d, ebx
0x1800275e4  mov     r8, r13
0x1800275e7  mov     rcx, [rcx+10h]
0x1800275eb  call    WPP_SF_d
0x1800275f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275f7  test    ebx, ebx
0x1800275f9  js      short loc_180027617
0x1800275fb  lea     rcx, [r15+10h]
0x1800275ff  mov     rdx, qword ptr [rbp+pvarg+8]
0x180027603  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180027608  mov     qword ptr [rbp+pvarg+8], 0
0x180027610  mov     rcx, cs:WPP_GLOBAL_Control
0x180027617  cmp     rcx, rsi
0x18002761a  jz      loc_1800276D8
0x180027620  test    [rcx+1Ch], dil
0x180027624  jz      loc_1800276D8
0x18002762a  test    ebx, ebx
0x18002762c  js      loc_1800276C0
0x180027632  mov     r9, [r15+10h]
0x180027636  jmp     loc_1800276C7
0x18002763b  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180027643  or      eax, 0FFFFFFFFh
0x180027646  mov     r9d, eax; cchCount2
0x180027649  lea     r8, aSystem; "SYSTEM"
0x180027650  mov     edx, eax; cchCount1
0x180027652  call    cs:__imp_CompareStringOrdinal
0x180027658  cmp     eax, edi
0x18002765a  jz      short loc_1800275F0
0x18002765c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027663  cmp     rcx, rsi
0x180027666  jz      short loc_180027686
0x180027668  test    [rcx+1Ch], dil
0x18002766c  jz      short loc_180027686
0x18002766e  mov     edx, 25h ; '%'
0x180027673  mov     r8, r13
0x180027676  mov     rcx, [rcx+10h]
0x18002767a  call    WPP_SF_
0x18002767f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027686  mov     ebx, r14d
0x180027689  jmp     loc_1800275F7
0x18002768e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027695  cmp     rcx, rsi
0x180027698  jz      short loc_1800276B8
0x18002769a  test    [rcx+1Ch], dil
0x18002769e  jz      short loc_1800276B8
0x1800276a0  mov     edx, 26h ; '&'
0x1800276a5  mov     r8, r13
0x1800276a8  mov     rcx, [rcx+10h]
0x1800276ac  call    WPP_SF_
0x1800276b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276b8  mov     ebx, r14d
0x1800276bb  jmp     loc_180027617
0x1800276c0  lea     r9, aFailed; "<FAILED>"
0x1800276c7  mov     edx, 27h ; '''
0x1800276cc  mov     r8, r13
0x1800276cf  mov     rcx, [rcx+10h]
0x1800276d3  call    WPP_SF_S
0x1800276d8  test    ebx, ebx
0x1800276da  js      loc_180027886
0x1800276e0  cmp     [r15+8], edi
0x1800276e4  jnz     loc_180027886
0x1800276ea  lea     rcx, [rbp+pvarg]; pvarg
0x1800276ee  call    cs:__imp_VariantClear
0x1800276f4  mov     rax, [r12]
0x1800276f8  lea     r9, [rbp+pvarg]
0x1800276fc  xor     r8d, r8d
0x1800276ff  lea     rdx, aPolicyplatform; "PolicyPlatformContext_PrincipalContext_"...
0x180027706  mov     rcx, r12
0x180027709  mov     rax, [rax+48h]
0x18002770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027712  test    eax, eax
0x180027714  js      short loc_180027745
0x180027716  mov     r9d, dword ptr [rbp+pvarg+8]
0x18002771a  mov     [r15+18h], r9d
0x18002771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027725  cmp     rcx, rsi
0x180027728  jz      short loc_180027745
0x18002772a  test    [rcx+1Ch], dil
0x18002772e  jz      short loc_180027745
0x180027730  mov     edx, 28h ; '('
0x180027735  mov     [rsp+58h+bIgnoreCase], eax
0x180027739  mov     r8, r13
0x18002773c  mov     rcx, [rcx+10h]
0x180027740  call    WPP_SF_dd
0x180027745  lea     rcx, [rbp+pvarg]; pvarg
0x180027749  call    cs:__imp_VariantClear
0x18002774f  mov     rax, [r12]
0x180027753  lea     r9, [rbp+pvarg]
0x180027757  xor     r8d, r8d
0x18002775a  lea     rdx, aPolicyplatform_1; "PolicyPlatformContext_PrincipalContext_"...
0x180027761  mov     rcx, r12
0x180027764  mov     rax, [rax+48h]
0x180027768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776d  test    eax, eax
0x18002776f  js      short loc_1800277A0
0x180027771  mov     r9d, dword ptr [rbp+pvarg+8]
0x180027775  mov     [r15+1Ch], r9d
0x180027779  mov     rcx, cs:WPP_GLOBAL_Control
0x180027780  cmp     rcx, rsi
0x180027783  jz      short loc_1800277A0
0x180027785  test    [rcx+1Ch], dil
0x180027789  jz      short loc_1800277A0
0x18002778b  mov     edx, 29h ; ')'
0x180027790  mov     [rsp+58h+bIgnoreCase], eax
0x180027794  mov     r8, r13
0x180027797  mov     rcx, [rcx+10h]
0x18002779b  call    WPP_SF_dd
0x1800277a0  lea     rcx, [rbp+pvarg]; pvarg
0x1800277a4  call    cs:__imp_VariantClear
0x1800277aa  mov     rax, [r12]
0x1800277ae  lea     r9, [rbp+pvarg]
0x1800277b2  xor     r8d, r8d
0x1800277b5  lea     rdx, aPolicyplatform_5; "PolicyPlatformContext_PrincipalContext_"...
0x1800277bc  mov     rcx, r12
0x1800277bf  mov     rax, [rax+48h]
0x1800277c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277c8  test    eax, eax
0x1800277ca  js      short loc_1800277FC
0x1800277cc  movzx   r9d, word ptr [rbp+pvarg+8]
0x1800277d1  mov     [r15+28h], r9d
0x1800277d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277dc  cmp     rcx, rsi
0x1800277df  jz      short loc_1800277FC
0x1800277e1  test    [rcx+1Ch], dil
0x1800277e5  jz      short loc_1800277FC
0x1800277e7  mov     edx, 2Ah ; '*'
0x1800277ec  mov     [rsp+58h+bIgnoreCase], eax
0x1800277f0  mov     r8, r13
0x1800277f3  mov     rcx, [rcx+10h]
0x1800277f7  call    WPP_SF_dd
0x1800277fc  lea     rcx, [rbp+pvarg]; pvarg
0x180027800  call    cs:__imp_VariantClear
0x180027806  mov     rax, [r12]
0x18002780a  lea     r9, [rbp+pvarg]
0x18002780e  xor     r8d, r8d
0x180027811  lea     rdx, aPolicyplatform_3; "PolicyPlatformContext_PrincipalContext_"...
0x180027818  mov     rcx, r12
0x18002781b  mov     rax, [rax+48h]
0x18002781f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027824  test    eax, eax
0x180027826  js      short loc_180027854
0x180027828  mov     r9, qword ptr [rbp+pvarg+8]
0x18002782c  mov     [r15+30h], r9
0x180027830  mov     rcx, cs:WPP_GLOBAL_Control
0x180027837  cmp     rcx, rsi
0x18002783a  jz      short loc_180027854
0x18002783c  test    [rcx+1Ch], dil
0x180027840  jz      short loc_180027854
0x180027842  mov     edx, 2Bh ; '+'
0x180027847  mov     [rsp+58h+bIgnoreCase], eax
0x18002784b  mov     rcx, [rcx+10h]
0x18002784f  call    WPP_SF_iD
0x180027854  xor     ebx, ebx
0x180027856  jmp     short loc_180027886
0x180027858  lea     rsi, WPP_GLOBAL_Control
0x18002785f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027866  cmp     rcx, rsi
0x180027869  jz      short loc_180027886
0x18002786b  test    [rcx+1Ch], dil
0x18002786f  jz      short loc_180027886
0x180027871  mov     edx, 23h ; '#'
0x180027876  mov     r9d, eax
0x180027879  mov     r8, r13
0x18002787c  mov     rcx, [rcx+10h]
0x180027880  call    WPP_SF_d
0x180027885  nop
0x180027886  lea     rcx, [rbp+pvarg]; pvarg
0x18002788a  call    cs:__imp_VariantClear
0x180027890  jmp     short loc_1800278C4
0x180027892  mov     ebx, 80070057h
0x180027897  lea     rsi, WPP_GLOBAL_Control
0x18002789e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278a5  cmp     rcx, rsi
0x1800278a8  jz      short loc_1800278EA
0x1800278aa  mov     edi, 2
  ... truncated ...
```
