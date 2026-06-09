# SetUserStateSetting(USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant const &,void *,USERSTATE_SETTING_SOURCES,ushort const *)

- ea: `0x18000a084`
- end: `0x18000a597`
- name: `?SetUserStateSetting@@YAJPEBUUSERSTATE_SETTING_DESCRIPTOR@@AEBVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z`
- size: `1299`
- prototype: `__int64 __fastcall(__int64, VARIANTARG *, void *, unsigned int, char)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e9b8`
- `0x180028bb8`
- `0x180029174`

## callees

- `0x18000a084`
- `0x18000a840`
- `0x18000b1a8`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180027fd0`
- `0x180028048`
- `0x18002894c`
- `0x1800289d4`
- `0x180028af8`
- `0x180029964`
- `0x1800299cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a2f7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a45f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a4d5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a528`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a2f7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a45f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a4d5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a528`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000a373`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000a373`
- `OLEAUT32!__imp_VariantInit` at `0x18000a0b1`
- `OLEAUT32!__imp_VariantInit` at `0x18000a0b1`
- `OLEAUT32!__imp_VariantClear` at `0x18000a142`
- `OLEAUT32!__imp_VariantClear` at `0x18000a142`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000a0eb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000a0eb`

## pseudocode

```c
__int64 __fastcall SetUserStateSetting(__int64 a1, VARIANTARG *a2, void *a3, unsigned int a4, char a5)
{
  int v9; // ebx
  VARIANTARG *p_pvarg; // rdx
  HRESULT v11; // eax
  int v12; // r8d
  const wchar_t *bstrVal; // rcx
  __int64 v14; // r8
  int v15; // ecx
  int v16; // ebx
  unsigned int v17; // esi
  __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  LSTATUS v22; // eax
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // [rsp+50h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-11h] BYREF

  VariantInit(&pvarg);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v9 = *(_DWORD *)(a1 + 8);
    p_pvarg = &pvarg;
    if ( a2 )
      p_pvarg = a2;
    v11 = VariantChangeType(&pvarg, p_pvarg, 0, 8u);
    bstrVal = L"<undefined>";
    if ( v11 >= 0 )
      bstrVal = pvarg.bstrVal;
    WPP_SF_ddSqDDS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      (unsigned int)L"NULL",
      v12,
      *(_DWORD *)a1,
      a2->vt,
      (__int64)bstrVal,
      (char)a3,
      v9,
      a4,
      (__int64)L"NULL");
  }
  VariantClear(&pvarg);
  if ( a2->vt != 1 && *(_WORD *)(a1 + 4) != a2->vt )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_ddD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 1, v14, a2->vt, *(unsigned __int16 *)(a1 + 4));
    return 2147942487LL;
  }
  if ( !a4 )
    a4 = *(_DWORD *)(a1 + 8);
  if ( (a4 & 7) == 0 )
    a4 |= *(_DWORD *)(a1 + 8) & 7;
  v15 = a4 & 7;
  if ( ((v15 - 1) & 0xFFFFFFFC) != 0 || v15 == 3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 50, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a4);
    return 2147942487LL;
  }
  if ( (a4 & 0x30) == 0 )
    a4 |= *(_DWORD *)(a1 + 8) & 0x30;
  if ( (((a4 & 0x30) - 16) & 0xFFFFFFEF) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 51, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    return 2147942487LL;
  }
  v16 = 0;
  v28 = 0;
  a5 = 0;
  if ( (a4 & 1) == 0 )
  {
    v17 = 0;
    if ( (a4 & 4) == 0 )
    {
      v18 = WPP_GLOBAL_Control;
      goto LABEL_46;
    }
  }
  if ( !a3 )
  {
    v19 = UstCommon::CComImpersonator::Impersonate((UstCommon::CComImpersonator *)&v28, (int *)1);
    v17 = v19;
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
    {
      v16 = v28;
      goto LABEL_37;
    }
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v19);
    v16 = v28;
    goto LABEL_36;
  }
  v20 = UstCommon::CImpersonator::Impersonate((UstCommon::CImpersonator *)&a5, a3);
  v17 = v20;
  v18 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v20);
LABEL_36:
    v18 = WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( (v17 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(v18 + 16), 54, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v17);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( v16 )
    {
      CoRevertToSelf();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    }
    return v17;
  }
LABEL_46:
  phkResult = 0;
  if ( (a4 & 2) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      -2147483646);
    goto LABEL_54;
  }
  if ( (a4 & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v22 = RegOpenCurrentUser(0x20006u, &phkResult);
    v17 = v22;
    if ( v22 > 0 )
      v17 = (unsigned __int16)v22 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v17);
LABEL_54:
    if ( (v17 & 0x80000000) == 0 )
    {
      v23 = *(const unsigned __int16 **)(((a4 & 0x20) != 0 ? 0x10 : 0) + a1 + 24);
      v24 = *(const unsigned __int16 **)(((a4 & 0x20) != 0 ? 0x10 : 0) + a1 + 16);
      if ( a2->vt == 1 )
      {
        v25 = RemoveUserStateSetting(phkResult, v24, v23);
        v17 = v25;
        v26 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v27 = 59;
          goto LABEL_62;
        }
      }
      else
      {
        v25 = StoreUserStateSetting(phkResult, v24, v23, *(_WORD *)(a1 + 4), a2);
        v17 = v25;
        v26 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v27 = 58;
LABEL_62:
          WPP_SF_d(*(_QWORD *)(v26 + 16), v27, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v25);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( v16 )
    {
      CoRevertToSelf();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
    }
    return v17;
  }
  if ( (a4 & 4) != 0 )
  {
    if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v18 + 16), 56, WPP_313c576492293c0704086ae70e07ed75_Traceguids, 2147942487LL);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v16 )
      return 2147942487LL;
  }
  else
  {
    if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v18 + 16), 57, WPP_313c576492293c0704086ae70e07ed75_Traceguids, 2147942487LL);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&a5);
    if ( !v16 )
      return 2147942487LL;
  }
  CoRevertToSelf();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000a084  mov     [rsp-8+arg_8], rdx
0x18000a089  push    rbp
0x18000a08a  push    rbx
0x18000a08b  push    rsi
0x18000a08c  push    rdi
0x18000a08d  push    r12
0x18000a08f  push    r13
0x18000a091  push    r14
0x18000a093  push    r15
0x18000a095  lea     rbp, [rsp-17h]
0x18000a09a  sub     rsp, 88h
0x18000a0a1  mov     edi, r9d
0x18000a0a4  mov     r13, r8
0x18000a0a7  mov     rsi, rdx
0x18000a0aa  mov     r15, rcx
0x18000a0ad  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000a0b1  call    cs:__imp_VariantInit
0x18000a0b7  lea     rbx, WPP_GLOBAL_Control
0x18000a0be  mov     rax, cs:WPP_GLOBAL_Control
0x18000a0c5  cmp     rax, rbx
0x18000a0c8  jz      short loc_18000A13E
0x18000a0ca  test    byte ptr [rax+1Ch], 2
0x18000a0ce  jz      short loc_18000A13E
0x18000a0d0  mov     ebx, [r15+8]
0x18000a0d4  lea     rdx, [rbp+4Fh+pvarg]
0x18000a0d8  test    rsi, rsi
0x18000a0db  cmovnz  rdx, rsi; pvarSrc
0x18000a0df  mov     r9w, 8; vt
0x18000a0e4  xor     r8d, r8d; wFlags
0x18000a0e7  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x18000a0eb  call    cs:__imp_VariantChangeType
0x18000a0f1  lea     rcx, aUndefined; "<undefined>"
0x18000a0f8  test    eax, eax
0x18000a0fa  cmovns  rcx, qword ptr [rbp+4Fh+pvarg+8]
0x18000a0ff  movzx   eax, word ptr [rsi]
0x18000a102  lea     rdx, aNull_1; "NULL"
0x18000a109  mov     [rsp+0C0h+var_78], rdx
0x18000a10e  mov     [rsp+0C0h+var_80], edi
0x18000a112  mov     [rsp+0C0h+var_88], ebx
0x18000a116  mov     [rsp+0C0h+var_90], r13
0x18000a11b  mov     [rsp+0C0h+var_98], rcx
0x18000a120  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000a124  mov     r9d, [r15]
0x18000a127  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a12e  mov     rcx, [rcx+10h]
0x18000a132  call    WPP_SF_ddSqDDS
0x18000a137  lea     rbx, WPP_GLOBAL_Control
0x18000a13e  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000a142  call    cs:__imp_VariantClear
0x18000a148  mov     edx, 1; int *
0x18000a14d  cmp     [rsi], dx
0x18000a150  jz      short loc_18000A18C
0x18000a152  movzx   eax, word ptr [r15+4]
0x18000a157  cmp     ax, [rsi]
0x18000a15a  jz      short loc_18000A18C
0x18000a15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a163  cmp     rcx, rbx
0x18000a166  jz      loc_18000A57E
0x18000a16c  test    byte ptr [rcx+1Ch], 2
0x18000a170  jz      loc_18000A57E
0x18000a176  movzx   r9d, word ptr [rsi]
0x18000a17a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000a17e  mov     rcx, [rcx+10h]
0x18000a182  call    WPP_SF_ddD
0x18000a187  jmp     loc_18000A57E
0x18000a18c  test    edi, edi
0x18000a18e  jnz     short loc_18000A194
0x18000a190  mov     edi, [r15+8]
0x18000a194  test    dil, 7
0x18000a198  jnz     short loc_18000A1A3
0x18000a19a  mov     eax, [r15+8]
0x18000a19e  and     eax, 7
0x18000a1a1  or      edi, eax
0x18000a1a3  mov     ecx, edi
0x18000a1a5  and     ecx, 7
0x18000a1a8  lea     eax, [rcx-1]
0x18000a1ab  test    eax, 0FFFFFFFCh
0x18000a1b0  jnz     loc_18000A554
0x18000a1b6  cmp     ecx, 3
0x18000a1b9  jz      loc_18000A554
0x18000a1bf  test    dil, 30h
0x18000a1c3  jnz     short loc_18000A1CE
0x18000a1c5  mov     eax, [r15+8]
0x18000a1c9  and     eax, 30h
0x18000a1cc  or      edi, eax
0x18000a1ce  mov     eax, edi
0x18000a1d0  and     eax, 30h
0x18000a1d3  sub     eax, 10h
0x18000a1d6  test    eax, 0FFFFFFEFh
0x18000a1db  jz      short loc_18000A211
0x18000a1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1e4  cmp     rcx, rbx
0x18000a1e7  jz      loc_18000A57E
0x18000a1ed  test    byte ptr [rcx+1Ch], 2
0x18000a1f1  jz      loc_18000A57E
0x18000a1f7  mov     edx, 33h ; '3'
0x18000a1fc  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000a203  mov     rcx, [rcx+10h]
0x18000a207  call    WPP_SF_
0x18000a20c  jmp     loc_18000A57E
0x18000a211  xor     ebx, ebx
0x18000a213  mov     [rbp+4Fh+var_70], ebx
0x18000a216  mov     [rbp+4Fh+arg_20], bl
0x18000a219  mov     r12d, edi
0x18000a21c  lea     r14, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18000a223  and     r12d, edx
0x18000a226  jnz     short loc_18000A23C
0x18000a228  xor     esi, esi
0x18000a22a  test    dil, 4
0x18000a22e  jnz     short loc_18000A23C
0x18000a230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a237  jmp     loc_18000A32D
0x18000a23c  test    r13, r13
0x18000a23f  jnz     short loc_18000A283
0x18000a241  lea     rcx, [rbp+4Fh+var_70]; this
0x18000a245  call    ?Impersonate@CComImpersonator@UstCommon@@QEAAJPEAH@Z; UstCommon::CComImpersonator::Impersonate(int *)
0x18000a24a  mov     esi, eax
0x18000a24c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a253  lea     r13, WPP_GLOBAL_Control
0x18000a25a  cmp     rcx, r13
0x18000a25d  jz      short loc_18000A27E
0x18000a25f  test    byte ptr [rcx+1Ch], 2
0x18000a263  jz      short loc_18000A27E
0x18000a265  mov     edx, 34h ; '4'
0x18000a26a  mov     r9d, eax
0x18000a26d  mov     r8, r14
0x18000a270  mov     rcx, [rcx+10h]
0x18000a274  call    WPP_SF_d
0x18000a279  mov     ebx, [rbp+4Fh+var_70]
0x18000a27c  jmp     short loc_18000A2BE
0x18000a27e  mov     ebx, [rbp+4Fh+var_70]
0x18000a281  jmp     short loc_18000A2C5
0x18000a283  mov     rdx, r13; void *
0x18000a286  lea     rcx, [rbp+4Fh+arg_20]; this
0x18000a28a  call    ?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z; UstCommon::CImpersonator::Impersonate(void *)
0x18000a28f  mov     esi, eax
0x18000a291  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a298  lea     r13, WPP_GLOBAL_Control
0x18000a29f  cmp     rcx, r13
0x18000a2a2  jz      short loc_18000A2C5
0x18000a2a4  test    byte ptr [rcx+1Ch], 2
0x18000a2a8  jz      short loc_18000A2C5
0x18000a2aa  mov     edx, 35h ; '5'
0x18000a2af  mov     r9d, eax
0x18000a2b2  mov     r8, r14
0x18000a2b5  mov     rcx, [rcx+10h]
0x18000a2b9  call    WPP_SF_d
0x18000a2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2c5  test    esi, esi
0x18000a2c7  jns     short loc_18000A328
0x18000a2c9  cmp     rcx, r13
0x18000a2cc  jz      short loc_18000A2E9
0x18000a2ce  test    byte ptr [rcx+1Ch], 2
0x18000a2d2  jz      short loc_18000A2E9
0x18000a2d4  mov     edx, 36h ; '6'
0x18000a2d9  mov     r9d, esi
0x18000a2dc  mov     r8, r14
0x18000a2df  mov     rcx, [rcx+10h]
0x18000a2e3  call    WPP_SF_d
0x18000a2e8  nop
0x18000a2e9  lea     rcx, [rbp+4Fh+arg_20]; this
0x18000a2ed  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000a2f2  nop
0x18000a2f3  test    ebx, ebx
0x18000a2f5  jz      short loc_18000A321
0x18000a2f7  call    cs:__imp_CoRevertToSelf
0x18000a2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a304  cmp     rcx, r13
0x18000a307  jz      short loc_18000A321
0x18000a309  test    byte ptr [rcx+1Ch], 2
0x18000a30d  jz      short loc_18000A321
0x18000a30f  mov     edx, 0Bh
0x18000a314  mov     r8, r14
0x18000a317  mov     rcx, [rcx+10h]
0x18000a31b  call    WPP_SF_
0x18000a320  nop
0x18000a321  mov     eax, esi
0x18000a323  jmp     loc_18000A583
0x18000a328  mov     edx, 1
0x18000a32d  mov     [rbp+4Fh+phkResult], 0
0x18000a335  mov     r13b, 2
0x18000a338  test    r13b, dil
0x18000a33b  jz      short loc_18000A356
0x18000a33d  mov     rdx, 0FFFFFFFF80000002h
0x18000a344  lea     rcx, [rbp+4Fh+phkResult]
0x18000a348  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a34d  lea     r12, WPP_GLOBAL_Control
0x18000a354  jmp     short loc_18000A3B5
0x18000a356  test    r12d, r12d
0x18000a359  jz      loc_18000A48E
0x18000a35f  xor     edx, edx
0x18000a361  lea     rcx, [rbp+4Fh+phkResult]
0x18000a365  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000a36a  lea     rdx, [rbp+4Fh+phkResult]; phkResult
0x18000a36e  mov     ecx, 20006h; samDesired
0x18000a373  call    cs:__imp_RegOpenCurrentUser
0x18000a379  mov     esi, eax
0x18000a37b  test    eax, eax
0x18000a37d  jle     short loc_18000A388
0x18000a37f  movzx   esi, ax
0x18000a382  or      esi, 80070000h
0x18000a388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a38f  lea     r12, WPP_GLOBAL_Control
0x18000a396  cmp     rcx, r12
0x18000a399  jz      short loc_18000A3B5
0x18000a39b  test    [rcx+1Ch], r13b
0x18000a39f  jz      short loc_18000A3B5
0x18000a3a1  mov     edx, 37h ; '7'
0x18000a3a6  mov     r9d, esi
0x18000a3a9  mov     r8, r14
0x18000a3ac  mov     rcx, [rcx+10h]
0x18000a3b0  call    WPP_SF_d
0x18000a3b5  test    esi, esi
0x18000a3b7  js      loc_18000A447
0x18000a3bd  and     edi, 20h
0x18000a3c0  mov     eax, edi
0x18000a3c2  neg     eax
0x18000a3c4  sbb     r8, r8
0x18000a3c7  and     r8d, 10h
0x18000a3cb  neg     edi
0x18000a3cd  sbb     rdx, rdx
0x18000a3d0  and     edx, 10h
0x18000a3d3  mov     rax, [rbp+4Fh+arg_8]
0x18000a3d7  mov     ecx, 1
0x18000a3dc  mov     r8, [r8+r15+18h]; unsigned __int16 *
0x18000a3e1  mov     rdx, [rdx+r15+10h]; unsigned __int16 *
0x18000a3e6  cmp     [rax], cx
0x18000a3e9  mov     rcx, [rbp+4Fh+phkResult]; HKEY
0x18000a3ed  jz      short loc_18000A419
0x18000a3ef  mov     [rsp+0C0h+var_A0], rax; struct ATL::CComVariant *
0x18000a3f4  movzx   r9d, word ptr [r15+4]; unsigned __int16
0x18000a3f9  call    ?StoreUserStateSetting@@YAJPEAUHKEY__@@PEBG1GAEBVCComVariant@ATL@@@Z; StoreUserStateSetting(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant const &)
0x18000a3fe  mov     esi, eax
0x18000a400  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a407  cmp     rcx, r12
0x18000a40a  jz      short loc_18000A447
0x18000a40c  test    [rcx+1Ch], r13b
0x18000a410  jz      short loc_18000A447
0x18000a412  mov     edx, 3Ah ; ':'
0x18000a417  jmp     short loc_18000A437
0x18000a419  call    ?RemoveUserStateSetting@@YAJPEAUHKEY__@@PEBG1@Z; RemoveUserStateSetting(HKEY__ *,ushort const *,ushort const *)
0x18000a41e  mov     esi, eax
0x18000a420  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a427  cmp     rcx, r12
0x18000a42a  jz      short loc_18000A447
0x18000a42c  test    [rcx+1Ch], r13b
0x18000a430  jz      short loc_18000A447
0x18000a432  mov     edx, 3Bh ; ';'
0x18000a437  mov     r9d, eax
0x18000a43a  mov     r8, r14
0x18000a43d  mov     rcx, [rcx+10h]
0x18000a441  call    WPP_SF_d
0x18000a446  nop
0x18000a447  lea     rcx, [rbp+4Fh+phkResult]
0x18000a44b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a450  nop
0x18000a451  lea     rcx, [rbp+4Fh+arg_20]; this
0x18000a455  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000a45a  nop
0x18000a45b  test    ebx, ebx
0x18000a45d  jz      short loc_18000A489
0x18000a45f  call    cs:__imp_CoRevertToSelf
0x18000a465  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a46c  cmp     rcx, r12
0x18000a46f  jz      short loc_18000A489
0x18000a471  test    [rcx+1Ch], r13b
0x18000a475  jz      short loc_18000A489
0x18000a477  mov     edx, 0Bh
0x18000a47c  mov     r8, r14
0x18000a47f  mov     rcx, [rcx+10h]
0x18000a483  call    WPP_SF_
0x18000a488  nop
0x18000a489  jmp     loc_18000A321
0x18000a48e  test    dil, 4
0x18000a492  jz      short loc_18000A4E7
0x18000a494  lea     rdi, WPP_GLOBAL_Control
0x18000a49b  cmp     rcx, rdi
0x18000a49e  jz      short loc_18000A4BD
0x18000a4a0  test    [rcx+1Ch], dl
0x18000a4a3  jz      short loc_18000A4BD
0x18000a4a5  mov     edx, 38h ; '8'
0x18000a4aa  mov     r9d, 80070057h
0x18000a4b0  mov     r8, r14
0x18000a4b3  mov     rcx, [rcx+10h]
0x18000a4b7  call    WPP_SF_d
0x18000a4bc  nop
0x18000a4bd  lea     rcx, [rbp+4Fh+phkResult]
0x18000a4c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a4c6  nop
0x18000a4c7  lea     rcx, [rbp+4Fh+arg_20]; this
0x18000a4cb  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x18000a4d0  nop
0x18000a4d1  test    ebx, ebx
0x18000a4d3  jz      short loc_18000A552
0x18000a4d5  call    cs:__imp_CoRevertToSelf
0x18000a4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4e2  cmp     rcx, rdi
0x18000a4e5  jmp     short loc_18000A538
0x18000a4e7  lea     rdi, WPP_GLOBAL_Control
0x18000a4ee  cmp     rcx, rdi
  ... truncated ...
```
