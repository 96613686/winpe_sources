# Int_FWVerifyConnectionSecurityRule

- ea: `0x1800150e0`
- end: `0x180016643`
- name: `Int_FWVerifyConnectionSecurityRule`
- size: `5475`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c6a0`

## callees

- `0x18000cb50`
- `0x18000ccd4`
- `0x18000cd30`
- `0x18000d3fc`
- `0x18000f520`
- `0x18000fbc0`
- `0x180010f20`
- `0x1800113f4`
- `0x180013b60`
- `0x1800150e0`
- `0x180017ca0`
- `0x180017d1c`
- `0x180017d44`
- `0x18002df50`
- `0x18002e010`
- `0x18002f668`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015278`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015278`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyConnectionSecurityRule(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // r9
  unsigned int v6; // ebp
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  int v10; // r14d
  const WCHAR *v11; // r8
  unsigned __int16 v12; // ax
  int v13; // edx
  wchar_t *v14; // rcx
  _WORD *v15; // r15
  _WORD *v16; // r14
  char IsEnabled; // al
  int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // r12
  unsigned __int8 near *v21; // r13
  __int16 v22; // ax
  int v23; // eax
  __int64 v24; // rax
  _DWORD *v25; // rax
  _DWORD *v26; // r15
  unsigned __int8 near **v27; // r14
  __int64 v28; // rdx
  int v29; // r15d
  __int64 v30; // rax
  BOOL v31; // r14d
  int v32; // ecx
  int v33; // ecx
  _DWORD *v34; // rcx
  int v35; // r14d
  unsigned int v36; // r8d
  unsigned int v37; // edx
  unsigned int v38; // r9d
  unsigned int v39; // edx
  __int64 v40; // r8
  __int64 v41; // rcx
  unsigned int v42; // r14d
  unsigned int v43; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *a3 = 0x10000;
  if ( *(_WORD *)(a2 + 8) < 0x200u )
  {
    v5 = 87;
    *a3 = 1069136;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 76;
LABEL_355:
      WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v5);
      return v6;
    }
    return v6;
  }
  if ( *(_WORD *)(a2 + 8) >= 0x300u )
    *a3 = 0x40000;
  v9 = Int_FwValidateComplianceAndReduceConnSecRuleToVersion(a2, a3, *(unsigned __int16 *)(a2 + 8));
  v10 = 0;
  v6 = v9;
  if ( !v9 )
  {
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 16), 0, 1u, 0x200u) )
    {
      v5 = 87;
      *a3 = 524296;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 78;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 24), 0, 1u, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524289;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 79;
        goto LABEL_355;
      }
      return v6;
    }
    v11 = *(const WCHAR **)(a2 + 24);
    if ( v11 && CompareStringW(0x7Fu, 1u, v11, -1, L"ALL", -1) == 2 )
    {
      v5 = 87;
      *a3 = 524289;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 80;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 32), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524290;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 81;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 344), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524295;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 82;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateProfiles(*(_DWORD *)(a2 + 40)) )
    {
      v5 = 87;
      *a3 = 1048656;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 83;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateAddresses(a2 + 48, 1, 0, a3) )
    {
      v5 = 87;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 84;
        goto LABEL_355;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateAddresses(a2 + 120, 1, 0, a3) )
    {
      v5 = 87;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 85;
        goto LABEL_355;
      }
      return v6;
    }
    if ( !(unsigned int)IsAddressesEmpty(a2 + 48) && (*(_DWORD *)(a2 + 192) || *(_DWORD *)(a2 + 208)) )
    {
      v5 = 87;
      *a3 = 1048651;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 86;
        goto LABEL_355;
      }
      return v6;
    }
    if ( *(_DWORD *)(a2 + 192) )
    {
      if ( *(_QWORD *)(a2 + 200) )
      {
LABEL_55:
        if ( *(_DWORD *)(a2 + 208) >= 0x10u )
        {
          v5 = 87;
          *a3 = 1048689;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 88;
            goto LABEL_355;
          }
          return v6;
        }
        v12 = *(_WORD *)(a2 + 304);
        if ( v12 > 0x100u )
        {
          v5 = 87;
          *a3 = 1048736;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 89;
            goto LABEL_355;
          }
          return v6;
        }
        LOBYTE(v10) = *(_DWORD *)(a2 + 336) == 4;
        if ( v12 == 6 || v12 == 17 )
        {
          if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 256), 0, v10, a3) )
          {
            v5 = 87;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 90;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned int)Int_FwValidatePorts((unsigned __int16 *)(a2 + 280), 0, v10, a3) )
          {
            v5 = 87;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 91;
              goto LABEL_355;
            }
            return v6;
          }
        }
        else if ( *(_DWORD *)(a2 + 264) || *(_DWORD *)(a2 + 288) || *(_WORD *)(a2 + 256) || *(_WORD *)(a2 + 280) )
        {
          v5 = 87;
          *a3 = 1048737;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 92;
            goto LABEL_355;
          }
          return v6;
        }
        v13 = *(_DWORD *)(a2 + 336);
        if ( (unsigned int)(v13 - 1) > 3 )
        {
          v5 = 87;
          *a3 = 1048704;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 93;
            goto LABEL_355;
          }
          return v6;
        }
        v14 = *(wchar_t **)(a2 + 312);
        if ( v13 == 4 )
        {
          if ( v14 || *(_QWORD *)(a2 + 328) || *(_QWORD *)(a2 + 320) )
          {
            v5 = 87;
            *a3 = 1048706;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 94;
              goto LABEL_355;
            }
            return v6;
          }
        }
        else
        {
          if ( !v14 )
          {
            v5 = 87;
            *a3 = 1049856;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 95;
              goto LABEL_355;
            }
            return v6;
          }
          if ( !*(_QWORD *)(a2 + 320) )
          {
            v5 = 87;
            *a3 = 1049872;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 96;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned int)Int_FwValidateString(v14, 0, 1u, 0xFFu) )
          {
            v5 = 87;
            *a3 = 524297;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 97;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 328), 1, 1u, 0xFFu) )
          {
            v5 = 87;
            *a3 = 524299;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 98;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 320), 0, 1u, 0xFFu) )
          {
            v5 = 87;
            *a3 = 524298;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 99;
              goto LABEL_355;
            }
            return v6;
          }
        }
        v15 = (_WORD *)(a2 + 340);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl) )
        {
          if ( *v15 >= 0x400u )
          {
            v5 = 87;
            *a3 = 1048752;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 100;
              goto LABEL_355;
            }
            return v6;
          }
          v16 = (_WORD *)(a2 + 340);
        }
        else
        {
          if ( *v15 >= 0x200u )
          {
            v5 = 87;
            *a3 = 1048752;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 101;
              goto LABEL_355;
            }
            return v6;
          }
          v16 = (_WORD *)(a2 + 340);
        }
        if ( !(unsigned int)IsTunnelMode((struct _tag_FW_CS_RULE *)a2) )
        {
          if ( (*(_BYTE *)v15 & 0x10) != 0 )
          {
            v5 = 87;
            *a3 = 1077248;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 118;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (*(_BYTE *)v15 & 8) != 0 )
          {
            v5 = 87;
            *a3 = 1077249;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 119;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl)
            && (*v16 & 0x200) != 0 )
          {
            v5 = 87;
            *a3 = 1048752;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 120;
              goto LABEL_355;
            }
            return v6;
          }
          goto LABEL_258;
        }
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl);
        v18 = 0;
        v19 = a2 + 48;
        if ( IsEnabled )
        {
          if ( ((unsigned int)IsAddressesEmpty(v19) || (unsigned int)IsAddressesEmpty(a2 + 120))
            && (*(_BYTE *)v15 & 2) == 0
            && (*(_BYTE *)(a2 + 496) & 4) == 0 )
          {
            v5 = 87;
            *a3 = 1048653;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 102;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (*(_BYTE *)(a2 + 496) & 4) != (((unsigned __int16)*v15 >> 7) & 4) )
          {
            v5 = 87;
            *a3 = 1048752;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 103;
              goto LABEL_355;
            }
            return v6;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_Rule_Validation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_Rule_Validation>::GetImpl'::`2'::impl)
            && (*v15 & 0x200) != 0 )
          {
            v20 = qword_18003C8D8;
            v21 = g_IPV6_UNSPECIFIED_ADDRESS;
            if ( *(_DWORD *)(a2 + 212)
              || *(_DWORD *)(a2 + 232)
              || *(unsigned __int8 near **)(a2 + 216) != g_IPV6_UNSPECIFIED_ADDRESS
              || *(_QWORD *)(a2 + 224) != qword_18003C8D8
              || *(unsigned __int8 near **)(a2 + 236) != g_IPV6_UNSPECIFIED_ADDRESS
              || *(_QWORD *)(a2 + 244) != qword_18003C8D8 )
            {
              v18 = 1;
            }
            if ( (!(unsigned int)IsAddressesEmpty(a2 + 48) || !(unsigned int)IsAddressesEmpty(a2 + 120)) && !v18 )
            {
              v5 = 87;
              *a3 = 1048653;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 104;
                goto LABEL_355;
              }
              return v6;
            }
LABEL_158:
            if ( *(_QWORD *)(a2 + 504) )
            {
              v5 = 87;
              *a3 = 1049878;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 106;
                goto LABEL_355;
              }
              return v6;
            }
            if ( *(_QWORD *)(a2 + 512) )
            {
              v5 = 87;
              *a3 = 1049879;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 107;
                goto LABEL_355;
              }
              return v6;
            }
            v22 = *v15 & 2;
            if ( v22 && *(_DWORD *)(a2 + 336) == 4 )
            {
              if ( *(_DWORD *)(a2 + 212)
                || *(_DWORD *)(a2 + 232)
                || *(unsigned __int8 near **)(a2 + 216) != v21
                || *(_QWORD *)(a2 + 224) != v20
                || *(unsigned __int8 near **)(a2 + 236) != v21
                || *(_QWORD *)(a2 + 244) != v20 )
              {
                v5 = 87;
                *a3 = 1048817;
                v6 = 87;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 108;
                  goto LABEL_355;
                }
                return v6;
              }
LABEL_258:
              v34 = (_DWORD *)(a2 + 352);
              if ( *(_QWORD *)(a2 + 360) )
              {
                if ( *v34 )
                {
LABEL_260:
                  if ( (unsigned int)Int_FwValidatePlatformValidityLists(v34, a3) )
                  {
                    v5 = 87;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 122;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( (unsigned int)Int_FwValidateAddresses(a2 + 424, 0, 1, a3) )
                  {
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 123;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( (unsigned int)IsAddressesEmpty(a2 + 424) )
                  {
                    v35 = 0;
                  }
                  else if ( *(_DWORD *)(a2 + 212)
                         || *(_DWORD *)(a2 + 232)
                         || *(unsigned __int8 near **)(a2 + 216) != g_IPV6_UNSPECIFIED_ADDRESS
                         || *(_QWORD *)(a2 + 224) != qword_18003C8D8
                         || (v35 = 1, *(unsigned __int8 near **)(a2 + 236) != g_IPV6_UNSPECIFIED_ADDRESS)
                         || *(_QWORD *)(a2 + 244) != qword_18003C8D8 )
                  {
                    v5 = 87;
                    *a3 = 1048655;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 124;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( *(_DWORD *)(a2 + 432) )
                  {
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 125;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( *(_DWORD *)(a2 + 464) )
                  {
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 126;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  v36 = *(_DWORD *)(a2 + 448);
                  v37 = 0;
                  if ( v36 )
                  {
                    while ( *(_DWORD *)(*(_QWORD *)(a2 + 456) + 8LL * v37) == *(_DWORD *)(*(_QWORD *)(a2 + 456)
                                                                                        + 8LL * v37
                                                                                        + 4) )
                    {
                      if ( ++v37 >= v36 )
                        goto LABEL_294;
                    }
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 127;
                      goto LABEL_355;
                    }
                    return v6;
                  }
LABEL_294:
                  v38 = *(_DWORD *)(a2 + 480);
                  v39 = 0;
                  if ( v38 )
                  {
                    v40 = *(_QWORD *)(a2 + 488);
                    while ( 1 )
                    {
                      v41 = 32LL * v39;
                      if ( *(_QWORD *)(v40 + v41) != *(_QWORD *)(v40 + v41 + 16)
                        || *(_QWORD *)(v40 + v41 + 8) != *(_QWORD *)(v40 + v41 + 24) )
                      {
                        break;
                      }
                      if ( ++v39 >= v38 )
                        goto LABEL_299;
                    }
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 128;
                      goto LABEL_355;
                    }
                    return v6;
                  }
LABEL_299:
                  if ( *(_DWORD *)(a2 + 424) )
                  {
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 129;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( *(_DWORD *)(a2 + 428) )
                  {
                    v5 = 87;
                    *a3 = 524303;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 130;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 416), 1, 1u, 0x200u) )
                  {
                    v5 = 87;
                    *a3 = 524304;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 131;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( !v35 && *(_QWORD *)(a2 + 416) )
                  {
                    v5 = 87;
                    *a3 = 524304;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 132;
                      goto LABEL_355;
                    }
                    return v6;
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl) )
                  {
                    if ( *(_DWORD *)(a2 + 496) >= 8u )
                    {
LABEL_324:
                      v5 = 87;
                      *a3 = 524305;
                      v6 = 87;
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        v8 = 133;
                        goto LABEL_355;
                      }
                      return v6;
                    }
                  }
                  else
                  {
                    v42 = *(_DWORD *)(a2 + 496);
                    if ( (unsigned int)IsCSRuleTunnelMode(a2) )
                    {
                      if ( v42 > 2 )
                        goto LABEL_324;
                    }
                    else if ( v42 >= 8 )
                    {
                      goto LABEL_324;
                    }
                  }
                  v43 = *(_DWORD *)(a2 + 500);
                  if ( v43 >= 0x2A300 || v43 - 1 <= 0x4C )
                  {
                    v5 = 87;
                    *a3 = 524307;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 134;
                      goto LABEL_355;
                    }
                  }
                  else if ( (*(_BYTE *)(a2 + 340) & 0x20) != 0 && (*(_QWORD *)(a2 + 504) || *(_QWORD *)(a2 + 512)) )
                  {
                    v5 = 87;
                    *a3 = 1049880;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 135;
                      goto LABEL_355;
                    }
                  }
                  else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 504), 1, 0, 0x2710u)
                         || (unsigned int)Int_FwValidateSecurityDescriptor(*(LPCWSTR *)(a2 + 504)) )
                  {
                    v5 = 87;
                    *a3 = 524308;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 136;
                      goto LABEL_355;
                    }
                  }
                  else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 512), 1, 0, 0x2710u)
                         || (unsigned int)Int_FwValidateSecurityDescriptor(*(LPCWSTR *)(a2 + 512)) )
                  {
                    v5 = 87;
                    *a3 = 524309;
                    v6 = 87;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v8 = 137;
                      goto LABEL_355;
                    }
                  }
                  return v6;
                }
              }
              else if ( !*v34 )
              {
                goto LABEL_260;
              }
              v5 = 87;
              *a3 = 1048800;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 121;
                goto LABEL_355;
              }
              return v6;
            }
            if ( *(_DWORD *)(a2 + 336) != 3 )
            {
              v5 = 87;
              *a3 = 1048704;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 109;
                goto LABEL_355;
              }
              return v6;
            }
            if ( *(_WORD *)(a2 + 304) != 256 )
            {
              v5 = 87;
              *a3 = 1048736;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 110;
                goto LABEL_355;
              }
              return v6;
            }
            if ( *(_WORD *)(a2 + 256) || *(_DWORD *)(a2 + 264) || *(_WORD *)(a2 + 280) || *(_DWORD *)(a2 + 288) )
            {
              v5 = 87;
              *a3 = 1048609;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 111;
                goto LABEL_355;
              }
              return v6;
            }
            if ( !v22 )
            {
              v23 = *(_DWORD *)(a2 + 232);
              if ( *(_DWORD *)(a2 + 212) )
              {
                if ( v23 )
                  goto LABEL_192;
              }
              else if ( !v23 )
              {
LABEL_192:
                v24 = *(_QWORD *)(a2 + 216) - (_QWORD)v21;
                if ( !v24 )
                  v24 = *(_QWORD *)(a2 + 224) - v20;
                if ( v24 && *(unsigned __int8 near **)(a2 + 236) == v21 && *(_QWORD *)(a2 + 244) == v20
                  || *(unsigned __int8 near **)(a2 + 216) == v21
                  && *(_QWORD *)(a2 + 224) == v20
                  && (*(unsigned __int8 near **)(a2 + 236) != v21 || *(_QWORD *)(a2 + 244) != v20) )
                {
                  v5 = 87;
                  *a3 = 1048650;
                  v6 = 87;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 113;
                    goto LABEL_355;
                  }
                  return v6;
                }
                goto LABEL_230;
              }
              v5 = 87;
              *a3 = 1048652;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 112;
                goto LABEL_355;
              }
              return v6;
            }
            v25 = (_DWORD *)(a2 + 232);
            if ( *(_DWORD *)(a2 + 212) && (v26 = (_DWORD *)(a2 + 232), *v25) )
            {
              v27 = (unsigned __int8 near **)(a2 + 216);
            }
            else
            {
              v27 = (unsigned __int8 near **)(a2 + 216);
              if ( *(unsigned __int8 near **)(a2 + 216) == v21 && *(_QWORD *)(a2 + 224) == v20 )
                goto LABEL_222;
              v28 = *(_QWORD *)(a2 + 236) - (_QWORD)v21;
              if ( !v28 )
                v28 = *(_QWORD *)(a2 + 244) - v20;
              v26 = (_DWORD *)(a2 + 232);
              if ( !v28 )
              {
LABEL_222:
                v29 = (*(_DWORD *)(a2 + 212) != 0) | (*v25 != 0 ? 2 : 0);
                v30 = *v27 - v21;
                if ( *v27 == v21 )
                  v30 = (__int64)&v27[1][-v20];
                v31 = v30 != 0;
                v32 = memcmp_0((const void *)(a2 + 236), &g_IPV6_UNSPECIFIED_ADDRESS, 0x10u) != 0 ? 2 : 0;
                if ( v29 )
                {
                  v33 = v31 | v32;
                  if ( v33 )
                  {
                    if ( v29 != v33 )
                    {
                      v5 = 87;
                      *a3 = 1048655;
                      v6 = 87;
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        v8 = 115;
                        goto LABEL_355;
                      }
                      return v6;
                    }
                  }
                }
LABEL_230:
                if ( *(unsigned __int8 near **)(a2 + 216) == g_IPV6_LOOPBACK_ADDRESS
                  && *(_QWORD *)(a2 + 224) == qword_18003C240
                  || *(unsigned __int8 near **)(a2 + 236) == g_IPV6_LOOPBACK_ADDRESS
                  && *(_QWORD *)(a2 + 244) == qword_18003C240 )
                {
                  v5 = 87;
                  *a3 = 1048650;
                  v6 = 87;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 116;
                    goto LABEL_355;
                  }
                  return v6;
                }
                if ( *(_DWORD *)(a2 + 212) == 2130706433 || *(_DWORD *)(a2 + 232) == 2130706433 )
                {
                  v5 = 87;
                  *a3 = 1048652;
                  v6 = 87;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 117;
                    goto LABEL_355;
                  }
                  return v6;
                }
                goto LABEL_258;
              }
            }
            if ( !(unsigned int)IsAddressesEmpty(a2 + 48) && !(unsigned int)IsAddressesEmpty(a2 + 120) )
            {
              v5 = 87;
              *a3 = 1048816;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 114;
                goto LABEL_355;
              }
              return v6;
            }
            v25 = v26;
            goto LABEL_222;
          }
        }
        else if ( ((unsigned int)IsAddressesEmpty(v19) || (unsigned int)IsAddressesEmpty(a2 + 120))
               && (*(_BYTE *)v15 & 2) == 0 )
        {
          v5 = 87;
          *a3 = 1048653;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 105;
            goto LABEL_355;
          }
          return v6;
        }
        v20 = qword_18003C8D8;
        v21 = g_IPV6_UNSPECIFIED_ADDRESS;
        goto LABEL_158;
      }
    }
    else if ( !*(_QWORD *)(a2 + 200) )
    {
      goto LABEL_55;
    }
    v5 = 87;
    *a3 = 1048688;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 87;
      goto LABEL_355;
    }
    return v6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 77;
    v5 = v9;
    goto LABEL_355;
  }
  return v6;
}

```

## disassembly

```asm
0x1800150e0  push    rbx
0x1800150e2  push    rbp
0x1800150e3  push    rsi
0x1800150e4  push    rdi
0x1800150e5  push    r12
0x1800150e7  push    r13
0x1800150e9  push    r14
0x1800150eb  push    r15
0x1800150ed  sub     rsp, 38h
0x1800150f1  mov     rsi, r8
0x1800150f4  mov     rdi, rdx
0x1800150f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150fe  lea     r15, WPP_GLOBAL_Control
0x180015105  lea     r13, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18001510c  cmp     rcx, r15
0x18001510f  jz      short loc_180015128
0x180015111  test    byte ptr [rcx+1Ch], 8
0x180015115  jz      short loc_180015128
0x180015117  mov     rcx, [rcx+10h]
0x18001511b  mov     edx, 4Bh ; 'K'
0x180015120  mov     r8, r13
0x180015123  call    WPP_SF_
0x180015128  mov     ebx, 200h
0x18001512d  mov     dword ptr [rsi], 10000h
0x180015133  cmp     [rdi+8], bx
0x180015137  jnb     short loc_180015170
0x180015139  mov     r9d, 57h ; 'W'
0x18001513f  mov     dword ptr [rsi], 105050h
0x180015145  mov     ebp, r9d
0x180015148  mov     rcx, cs:WPP_GLOBAL_Control
0x18001514f  cmp     rcx, r15
0x180015152  jz      loc_180016630
0x180015158  lea     ebx, [r9-56h]
0x18001515c  test    [rcx+1Ch], bl
0x18001515f  jz      loc_180016630
0x180015165  lea     edx, [rbx+4Bh]
0x180015168  mov     r8, r13
0x18001516b  jmp     loc_180016627
0x180015170  mov     eax, 300h
0x180015175  cmp     [rdi+8], ax
0x180015179  jb      short loc_180015181
0x18001517b  mov     dword ptr [rsi], 40000h
0x180015181  movzx   r8d, word ptr [rdi+8]
0x180015186  mov     rdx, rsi
0x180015189  mov     rcx, rdi
0x18001518c  call    Int_FwValidateComplianceAndReduceConnSecRuleToVersion
0x180015191  xor     r14d, r14d
0x180015194  mov     ebp, eax
0x180015196  test    eax, eax
0x180015198  jz      short loc_1800151BF
0x18001519a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151a1  cmp     rcx, r15
0x1800151a4  jz      loc_180016630
0x1800151aa  lea     ebx, [r14+1]
0x1800151ae  test    [rcx+1Ch], bl
0x1800151b1  jz      loc_180016630
0x1800151b7  lea     edx, [rbx+4Ch]
0x1800151ba  mov     r9d, eax
0x1800151bd  jmp     short loc_180015168
0x1800151bf  mov     rcx, [rdi+10h]; Str
0x1800151c3  mov     r9d, ebx
0x1800151c6  mov     ebx, 1
0x1800151cb  xor     edx, edx
0x1800151cd  mov     r8d, ebx
0x1800151d0  call    Int_FwValidateString
0x1800151d5  test    eax, eax
0x1800151d7  jz      short loc_180015207
0x1800151d9  lea     r9d, [rbx+56h]
0x1800151dd  mov     dword ptr [rsi], 80008h
0x1800151e3  mov     ebp, r9d
0x1800151e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151ed  cmp     rcx, r15
0x1800151f0  jz      loc_180016630
0x1800151f6  test    [rcx+1Ch], bl
0x1800151f9  jz      loc_180016630
0x1800151ff  lea     edx, [rbx+4Dh]
0x180015202  jmp     loc_180015168
0x180015207  mov     rcx, [rdi+18h]; Str
0x18001520b  mov     r12d, 2710h
0x180015211  mov     r9d, r12d
0x180015214  mov     r8d, ebx
0x180015217  xor     edx, edx
0x180015219  call    Int_FwValidateString
0x18001521e  test    eax, eax
0x180015220  jz      short loc_180015253
0x180015222  mov     r9d, 57h ; 'W'
0x180015228  mov     dword ptr [rsi], 80001h
0x18001522e  mov     ebp, r9d
0x180015231  mov     rcx, cs:WPP_GLOBAL_Control
0x180015238  cmp     rcx, r15
0x18001523b  jz      loc_180016630
0x180015241  test    [rcx+1Ch], bl
0x180015244  jz      loc_180016630
0x18001524a  lea     edx, [r9-8]
0x18001524e  jmp     loc_180015168
0x180015253  mov     r8, [rdi+18h]; lpString1
0x180015257  test    r8, r8
0x18001525a  jz      short loc_1800152B1
0x18001525c  or      r9d, 0FFFFFFFFh; cchCount1
0x180015260  lea     rax, String2; "ALL"
0x180015267  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18001526c  mov     edx, ebx; dwCmpFlags
0x18001526e  mov     ecx, 7Fh; Locale
0x180015273  mov     [rsp+78h+lpString2], rax; lpString2
0x180015278  call    cs:__imp_CompareStringW
0x18001527e  cmp     eax, 2
0x180015281  jnz     short loc_1800152B1
0x180015283  lea     r9d, [rax+55h]
0x180015287  mov     dword ptr [rsi], 80001h
0x18001528d  mov     ebp, r9d
0x180015290  mov     rcx, cs:WPP_GLOBAL_Control
0x180015297  cmp     rcx, r15
0x18001529a  jz      loc_180016630
0x1800152a0  test    [rcx+1Ch], bl
0x1800152a3  jz      loc_180016630
0x1800152a9  lea     edx, [rax+4Eh]
0x1800152ac  jmp     loc_180015168
0x1800152b1  mov     rcx, [rdi+20h]; Str
0x1800152b5  mov     r9d, r12d
0x1800152b8  xor     r8d, r8d
0x1800152bb  mov     edx, ebx
0x1800152bd  call    Int_FwValidateString
0x1800152c2  test    eax, eax
0x1800152c4  jz      short loc_1800152F7
0x1800152c6  mov     r9d, 57h ; 'W'
0x1800152cc  mov     dword ptr [rsi], 80002h
0x1800152d2  mov     ebp, r9d
0x1800152d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152dc  cmp     rcx, r15
0x1800152df  jz      loc_180016630
0x1800152e5  test    [rcx+1Ch], bl
0x1800152e8  jz      loc_180016630
0x1800152ee  lea     edx, [r9-6]
0x1800152f2  jmp     loc_180015168
0x1800152f7  mov     rcx, [rdi+158h]; Str
0x1800152fe  mov     r9d, r12d
0x180015301  xor     r8d, r8d
0x180015304  mov     edx, ebx
0x180015306  call    Int_FwValidateString
0x18001530b  test    eax, eax
0x18001530d  jz      short loc_180015340
0x18001530f  mov     r9d, 57h ; 'W'
0x180015315  mov     dword ptr [rsi], 80007h
0x18001531b  mov     ebp, r9d
0x18001531e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015325  cmp     rcx, r15
0x180015328  jz      loc_180016630
0x18001532e  test    [rcx+1Ch], bl
0x180015331  jz      loc_180016630
0x180015337  lea     edx, [r9-5]
0x18001533b  jmp     loc_180015168
0x180015340  mov     ecx, [rdi+28h]
0x180015343  call    Int_FwValidateProfiles
0x180015348  test    eax, eax
0x18001534a  jz      short loc_18001537D
0x18001534c  mov     r9d, 57h ; 'W'
0x180015352  mov     dword ptr [rsi], 100050h
0x180015358  mov     ebp, r9d
0x18001535b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015362  cmp     rcx, r15
0x180015365  jz      loc_180016630
0x18001536b  test    [rcx+1Ch], bl
0x18001536e  jz      loc_180016630
0x180015374  lea     edx, [r9-4]
0x180015378  jmp     loc_180015168
0x18001537d  lea     r12, [rdi+30h]
0x180015381  mov     r9, rsi
0x180015384  mov     rcx, r12
0x180015387  xor     r8d, r8d
0x18001538a  mov     edx, ebx
0x18001538c  call    Int_FwValidateAddresses
0x180015391  test    eax, eax
0x180015393  jz      short loc_1800153C0
0x180015395  mov     r9d, 57h ; 'W'
0x18001539b  mov     ebp, r9d
0x18001539e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153a5  cmp     rcx, r15
0x1800153a8  jz      loc_180016630
0x1800153ae  test    [rcx+1Ch], bl
0x1800153b1  jz      loc_180016630
0x1800153b7  lea     edx, [r9-3]
0x1800153bb  jmp     loc_180015168
0x1800153c0  lea     r13, [rdi+78h]
0x1800153c4  mov     r9, rsi
0x1800153c7  mov     rcx, r13
0x1800153ca  xor     r8d, r8d
0x1800153cd  mov     edx, ebx
0x1800153cf  call    Int_FwValidateAddresses
0x1800153d4  test    eax, eax
0x1800153d6  jz      short loc_180015403
0x1800153d8  mov     r9d, 57h ; 'W'
0x1800153de  mov     ebp, r9d
0x1800153e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153e8  cmp     rcx, r15
0x1800153eb  jz      loc_180016630
0x1800153f1  test    [rcx+1Ch], bl
0x1800153f4  jz      loc_180016630
0x1800153fa  lea     edx, [r9-2]
0x1800153fe  jmp     loc_180016620
0x180015403  mov     rcx, r12
0x180015406  call    IsAddressesEmpty
0x18001540b  test    eax, eax
0x18001540d  jnz     short loc_180015452
0x18001540f  cmp     [rdi+0C0h], r14d
0x180015416  jnz     short loc_180015421
0x180015418  cmp     [rdi+0D0h], r14d
0x18001541f  jz      short loc_180015452
0x180015421  mov     r9d, 57h ; 'W'
0x180015427  mov     dword ptr [rsi], 10004Bh
0x18001542d  mov     ebp, r9d
0x180015430  mov     rcx, cs:WPP_GLOBAL_Control
0x180015437  cmp     rcx, r15
0x18001543a  jz      loc_180016630
0x180015440  test    [rcx+1Ch], bl
0x180015443  jz      loc_180016630
0x180015449  lea     edx, [r9-1]
0x18001544d  jmp     loc_180016620
0x180015452  cmp     [rdi+0C0h], r14d
0x180015459  jnz     short loc_18001549E
0x18001545b  cmp     [rdi+0C8h], r14
0x180015462  jnz     short loc_1800154A7
0x180015464  cmp     dword ptr [rdi+0D0h], 10h
0x18001546b  jb      short loc_1800154D7
0x18001546d  mov     r9d, 57h ; 'W'
0x180015473  mov     dword ptr [rsi], 100071h
0x180015479  mov     ebp, r9d
0x18001547c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015483  cmp     rcx, r15
0x180015486  jz      loc_180016630
0x18001548c  test    [rcx+1Ch], bl
0x18001548f  jz      loc_180016630
0x180015495  lea     edx, [r9+1]
0x180015499  jmp     loc_180016620
0x18001549e  cmp     [rdi+0C8h], r14
0x1800154a5  jnz     short loc_180015464
0x1800154a7  mov     r9d, 57h ; 'W'
0x1800154ad  mov     dword ptr [rsi], 100070h
0x1800154b3  mov     ebp, r9d
0x1800154b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154bd  cmp     rcx, r15
0x1800154c0  jz      loc_180016630
0x1800154c6  test    [rcx+1Ch], bl
0x1800154c9  jz      loc_180016630
0x1800154cf  mov     edx, r9d
0x1800154d2  jmp     loc_180016620
0x1800154d7  movzx   eax, word ptr [rdi+130h]
0x1800154de  mov     ecx, 100h
0x1800154e3  cmp     ax, cx
0x1800154e6  jbe     short loc_180015519
0x1800154e8  mov     r9d, 57h ; 'W'
0x1800154ee  mov     dword ptr [rsi], 1000A0h
0x1800154f4  mov     ebp, r9d
0x1800154f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154fe  cmp     rcx, r15
0x180015501  jz      loc_180016630
0x180015507  test    [rcx+1Ch], bl
0x18001550a  jz      loc_180016630
0x180015510  lea     edx, [r9+2]
0x180015514  jmp     loc_180016620
0x180015519  cmp     dword ptr [rdi+150h], 4
0x180015520  setz    r14b
0x180015524  cmp     ax, 6
0x180015528  jz      short loc_18001558E
0x18001552a  cmp     ax, 11h
0x18001552e  jz      short loc_18001558E
0x180015530  xor     r14d, r14d
0x180015533  cmp     [rdi+108h], r14d
0x18001553a  jnz     short loc_18001555D
0x18001553c  cmp     [rdi+120h], r14d
0x180015543  jnz     short loc_18001555D
0x180015545  cmp     [rdi+100h], r14w
0x18001554d  jnz     short loc_18001555D
0x18001554f  cmp     [rdi+118h], r14w
0x180015557  jz      loc_180015615
0x18001555d  mov     r9d, 57h ; 'W'
0x180015563  mov     dword ptr [rsi], 1000A1h
0x180015569  mov     ebp, r9d
0x18001556c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015573  cmp     rcx, r15
0x180015576  jz      loc_180016630
0x18001557c  test    [rcx+1Ch], bl
0x18001557f  jz      loc_180016630
0x180015585  lea     edx, [r9+5]
0x180015589  jmp     loc_180016620
0x18001558e  xor     edx, edx
0x180015590  lea     rcx, [rdi+100h]
0x180015597  mov     r9, rsi
0x18001559a  mov     r8d, r14d
0x18001559d  call    Int_FwValidatePorts
0x1800155a2  test    eax, eax
0x1800155a4  jz      short loc_1800155D1
0x1800155a6  mov     r9d, 57h ; 'W'
0x1800155ac  mov     ebp, r9d
0x1800155af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155b6  cmp     rcx, r15
0x1800155b9  jz      loc_180016630
0x1800155bf  test    [rcx+1Ch], bl
0x1800155c2  jz      loc_180016630
0x1800155c8  lea     edx, [r9+3]
0x1800155cc  jmp     loc_180016620
  ... truncated ...
```
