# CopyAuthAppsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x180033600`
- end: `0x180033af0`
- name: `?CopyAuthAppsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `1264`
- prototype: `unsigned int __high(void *, enum _tag_FW_PROFILE_TYPE, const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035500`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x18001ce34`
- `0x1800294b0`
- `0x18003336c`
- `0x1800333a0`
- `0x180033488`
- `0x180033600`
- `0x1800348ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800338b4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800338b4`
- `fwbase!FwBaseAlloc` at `0x1800337df`
- `fwbase!FwBaseAlloc` at `0x1800337df`
- `fwbase!FwBaseFree` at `0x1800338d2`
- `fwbase!FwBaseFree` at `0x180033a63`
- `fwbase!FwBaseFree` at `0x1800338d2`
- `fwbase!FwBaseFree` at `0x180033a63`
- `fwbase!FwSizeTMultiply` at `0x1800337c7`
- `fwbase!FwSizeTMultiply` at `0x1800337c7`
- `fwbase!FwHResultToWindowsError` at `0x180033683`
- `fwbase!FwHResultToWindowsError` at `0x180033aa9`
- `fwbase!FwHResultToWindowsError` at `0x180033683`
- `fwbase!FwHResultToWindowsError` at `0x180033aa9`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180033853`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180033853`
- `fwbase!IsRuleOldAuthApp` at `0x180033788`
- `fwbase!IsRuleOldAuthApp` at `0x180033830`
- `fwbase!IsRuleOldAuthApp` at `0x180033788`
- `fwbase!IsRuleOldAuthApp` at `0x180033830`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033775`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033819`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033775`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033819`
- `fwbase!FwStringCopy` at `0x18003390b`
- `fwbase!FwStringCopy` at `0x180033932`
- `fwbase!FwStringCopy` at `0x18003390b`
- `fwbase!FwStringCopy` at `0x180033932`

## pseudocode

```c
__int64 __fastcall CopyAuthAppsSettingsToProfile(int a1, int a2, __int64 *a3, __int64 a4)
{
  int v6; // r14d
  int CurrentProfile; // eax
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v12; // r14d
  int v13; // eax
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r12d
  int ExpandedCanonicalLongPathName; // r14d
  const WCHAR *lpString2; // rdx
  unsigned int i; // r14d
  __int64 v23; // r14
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rcx
  PCNZWCH v28; // [rsp+40h] [rbp-30h] BYREF
  __int64 v29; // [rsp+48h] [rbp-28h] BYREF
  int v30; // [rsp+50h] [rbp-20h] BYREF
  int v31; // [rsp+58h] [rbp-18h] BYREF
  int v32; // [rsp+5Ch] [rbp-14h] BYREF

  v30 = a2;
  v31 = 0;
  v6 = a2;
  v32 = 4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( v6 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v30);
    if ( CurrentProfile < 0 )
    {
      v9 = FwHResultToWindowsError((unsigned int)CurrentProfile);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v9);
      return v10;
    }
    v6 = v30;
  }
  *(_DWORD *)(a4 + 232) = 2;
  v30 = 0;
  v12 = FWGetConfig2(a1, 11, v6, 1, (__int64)&v31, (__int64)&v32, (__int64)&v30);
  if ( v12 == 50 )
  {
    v13 = 1;
    v31 = 1;
  }
  else
  {
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 31;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v12);
      }
      return v12;
    }
    v13 = v31;
  }
  *(_DWORD *)(a4 + 216) = 0;
  v16 = a3;
  for ( *(_DWORD *)(a4 + 236) = (v13 != 0) + 1; v16; v16 = (_QWORD *)*v16 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(v16) && (unsigned int)IsRuleOldAuthApp(v16) )
      ++*(_DWORD *)(a4 + 216);
  }
  v17 = *(_DWORD *)(a4 + 216);
  if ( v17 )
  {
    v29 = 0;
    if ( (int)FwSizeTMultiply(112, v17, &v29) >= 0 )
    {
      v18 = FwBaseAlloc(v29);
      *(_QWORD *)(a4 + 224) = v18;
      if ( v18 )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( !a3 )
          {
            *(_DWORD *)(a4 + 216) = v19;
            return 0;
          }
          v28 = 0;
          v30 = 0;
          if ( (unsigned int)IsRuleOpenPortOrAuthApp(a3) && (unsigned int)IsRuleOldAuthApp(a3) )
          {
            ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a3[34], &v28, &v30);
            if ( ExpandedCanonicalLongPathName < 0 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids,
                  (unsigned int)ExpandedCanonicalLongPathName);
              }
              v27 = (unsigned int)ExpandedCanonicalLongPathName;
              return FwHResultToWindowsError(v27);
            }
            lpString2 = v28;
            if ( !v30 || !v28 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
                lpString2 = v28;
              }
              FwBaseFree(lpString2);
              return 31;
            }
            for ( i = 0; i < v19; ++i )
            {
              if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(112LL * i + *(_QWORD *)(a4 + 224) + 16), -1, lpString2, -1) == 2 )
              {
                FwBaseFree(v28);
                goto LABEL_46;
              }
              lpString2 = v28;
            }
            v23 = 112LL * v19;
            *(_QWORD *)(v23 + *(_QWORD *)(a4 + 224) + 16) = lpString2;
            v24 = FwStringCopy(a3[34], v23 + *(_QWORD *)(a4 + 224) + 8LL);
            if ( v24 < 0 || (v25 = a3[3]) != 0 && (v24 = FwStringCopy(v25, v23 + *(_QWORD *)(a4 + 224)), v24 < 0) )
            {
              v27 = (unsigned int)v24;
              return FwHResultToWindowsError(v27);
            }
            *(_DWORD *)(v23 + *(_QWORD *)(a4 + 224) + 104) = IsRuleEnabled((const struct _tag_FW_RULE *)a3);
            *(_DWORD *)(v23 + *(_QWORD *)(a4 + 224) + 108) = *((_DWORD *)a3 + 85) == 1;
            v26 = CopySubnetRestrictions(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_SUBNETS_ *)(v23 + *(_QWORD *)(a4 + 224) + 24LL),
                    (struct ICF_SUBNETS6_ *)(v23 + *(_QWORD *)(a4 + 224) + 48LL));
            if ( v26 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v26);
              }
              return v26;
            }
            v12 = CopyAddrRanges(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_RANGES_ *)(v23 + *(_QWORD *)(a4 + 224) + 72LL),
                    (struct ICF_RANGES6_ *)(v23 + *(_QWORD *)(a4 + 224) + 88LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 35;
                goto LABEL_17;
              }
              return v12;
            }
            ++v19;
          }
LABEL_46:
          a3 = (__int64 *)*a3;
        }
      }
    }
    return 8;
  }
  else
  {
    *(_QWORD *)(a4 + 224) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180033600  push    rbp
0x180033602  push    rbx
0x180033603  push    rsi
0x180033604  push    rdi
0x180033605  push    r12
0x180033607  push    r14
0x180033609  push    r15
0x18003360b  mov     rbp, rsp
0x18003360e  sub     rsp, 70h
0x180033612  mov     rax, cs:__security_cookie
0x180033619  xor     rax, rsp
0x18003361c  mov     [rbp+var_10], rax
0x180033620  mov     rdi, r9
0x180033623  mov     [rbp+var_20], edx
0x180033626  mov     rsi, r8
0x180033629  mov     [rbp+var_18], 0
0x180033630  mov     r14d, edx
0x180033633  mov     [rbp+var_14], 4
0x18003363a  mov     r15, rcx
0x18003363d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033644  lea     r12, WPP_GLOBAL_Control
0x18003364b  cmp     rcx, r12
0x18003364e  jz      short loc_18003366B
0x180033650  test    byte ptr [rcx+1Ch], 8
0x180033654  jz      short loc_18003366B
0x180033656  mov     rcx, [rcx+10h]
0x18003365a  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180033661  mov     edx, 1Dh
0x180033666  call    WPP_SF_
0x18003366b  cmp     r14d, 80000000h
0x180033672  jnz     short loc_1800336C8
0x180033674  lea     rcx, [rbp+var_20]; enum _tag_FW_PROFILE_TYPE *
0x180033678  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x18003367d  test    eax, eax
0x18003367f  jns     short loc_1800336C4
0x180033681  mov     ecx, eax
0x180033683  call    cs:__imp_FwHResultToWindowsError
0x18003368a  nop     dword ptr [rax+rax+00h]
0x18003368f  mov     edi, eax
0x180033691  mov     rcx, cs:WPP_GLOBAL_Control
0x180033698  cmp     rcx, r12
0x18003369b  jz      short loc_1800336BD
0x18003369d  mov     ebx, 1
0x1800336a2  test    [rcx+1Ch], bl
0x1800336a5  jz      short loc_1800336BD
0x1800336a7  mov     rcx, [rcx+10h]
0x1800336ab  lea     edx, [rbx+1Dh]
0x1800336ae  mov     r9d, eax
0x1800336b1  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800336b8  call    WPP_SF_d
0x1800336bd  mov     eax, edi
0x1800336bf  jmp     loc_180033AD4
0x1800336c4  mov     r14d, [rbp+var_20]
0x1800336c8  lea     rax, [rbp+var_20]
0x1800336cc  mov     dword ptr [rdi+0E8h], 2
0x1800336d6  mov     [rsp+70h+var_40], rax
0x1800336db  mov     ebx, 1
0x1800336e0  lea     rax, [rbp+var_14]
0x1800336e4  mov     [rbp+var_20], 0
0x1800336eb  mov     qword ptr [rsp+70h+cchCount2], rax
0x1800336f0  mov     r9d, ebx
0x1800336f3  lea     rax, [rbp+var_18]
0x1800336f7  mov     r8d, r14d
0x1800336fa  lea     edx, [rbx+0Ah]
0x1800336fd  mov     [rsp+70h+lpString2], rax
0x180033702  mov     rcx, r15
0x180033705  call    FWGetConfig2
0x18003370a  mov     r14d, eax
0x18003370d  cmp     eax, 32h ; '2'
0x180033710  jnz     short loc_180033719
0x180033712  mov     eax, ebx
0x180033714  mov     [rbp+var_18], ebx
0x180033717  jmp     short loc_180033752
0x180033719  test    r14d, r14d
0x18003371c  jz      short loc_18003374F
0x18003371e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033725  cmp     rcx, r12
0x180033728  jz      short loc_180033747
0x18003372a  test    [rcx+1Ch], bl
0x18003372d  jz      short loc_180033747
0x18003372f  mov     edx, 1Fh
0x180033734  mov     rcx, [rcx+10h]
0x180033738  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003373f  mov     r9d, r14d
0x180033742  call    WPP_SF_d
0x180033747  mov     eax, r14d
0x18003374a  jmp     loc_180033AD4
0x18003374f  mov     eax, [rbp+var_18]
0x180033752  neg     eax
0x180033754  mov     dword ptr [rdi+0D8h], 0
0x18003375e  mov     r14, rsi
0x180033761  sbb     eax, eax
0x180033763  neg     eax
0x180033765  add     eax, ebx
0x180033767  mov     [rdi+0ECh], eax
0x18003376d  test    rsi, rsi
0x180033770  jz      short loc_1800337A6
0x180033772  mov     rcx, r14
0x180033775  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x18003377c  nop     dword ptr [rax+rax+00h]
0x180033781  test    eax, eax
0x180033783  jz      short loc_18003379E
0x180033785  mov     rcx, r14
0x180033788  call    cs:__imp_IsRuleOldAuthApp
0x18003378f  nop     dword ptr [rax+rax+00h]
0x180033794  test    eax, eax
0x180033796  jz      short loc_18003379E
0x180033798  add     [rdi+0D8h], ebx
0x18003379e  mov     r14, [r14]
0x1800337a1  test    r14, r14
0x1800337a4  jnz     short loc_180033772
0x1800337a6  mov     eax, [rdi+0D8h]
0x1800337ac  test    eax, eax
0x1800337ae  jz      loc_180033AC7
0x1800337b4  mov     edx, eax
0x1800337b6  mov     [rbp+var_28], 0
0x1800337be  lea     r8, [rbp+var_28]
0x1800337c2  mov     ecx, 70h ; 'p'
0x1800337c7  call    cs:__imp_FwSizeTMultiply
0x1800337ce  nop     dword ptr [rax+rax+00h]
0x1800337d3  test    eax, eax
0x1800337d5  js      loc_180033AC0
0x1800337db  mov     rcx, [rbp+var_28]
0x1800337df  call    cs:__imp_FwBaseAlloc
0x1800337e6  nop     dword ptr [rax+rax+00h]
0x1800337eb  mov     [rdi+0E0h], rax
0x1800337f2  test    rax, rax
0x1800337f5  jz      loc_180033AC0
0x1800337fb  xor     r12d, r12d
0x1800337fe  test    rsi, rsi
0x180033801  jz      loc_180033AB7
0x180033807  mov     rcx, rsi
0x18003380a  mov     [rbp+var_30], 0
0x180033812  mov     [rbp+var_20], 0
0x180033819  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180033820  nop     dword ptr [rax+rax+00h]
0x180033825  test    eax, eax
0x180033827  jz      loc_1800339C1
0x18003382d  mov     rcx, rsi
0x180033830  call    cs:__imp_IsRuleOldAuthApp
0x180033837  nop     dword ptr [rax+rax+00h]
0x18003383c  test    eax, eax
0x18003383e  jz      loc_1800339C1
0x180033844  mov     rcx, [rsi+110h]
0x18003384b  lea     r8, [rbp+var_20]
0x18003384f  lea     rdx, [rbp+var_30]
0x180033853  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x18003385a  nop     dword ptr [rax+rax+00h]
0x18003385f  mov     r14d, eax
0x180033862  test    eax, eax
0x180033864  js      loc_180033A76
0x18003386a  cmp     [rbp+var_20], 0
0x18003386e  mov     rdx, [rbp+var_30]
0x180033872  jz      loc_180033A2F
0x180033878  test    rdx, rdx
0x18003387b  jz      loc_180033A2F
0x180033881  xor     r14d, r14d
0x180033884  cmp     r14d, r12d
0x180033887  jnb     short loc_1800338E3
0x180033889  mov     r8, [rdi+0E0h]
0x180033890  or      r9d, 0FFFFFFFFh; cchCount1
0x180033894  mov     eax, r14d
0x180033897  imul    rcx, rax, 70h ; 'p'
0x18003389b  mov     [rsp+70h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800338a3  mov     [rsp+70h+lpString2], rdx; lpString2
0x1800338a8  mov     edx, ebx; dwCmpFlags
0x1800338aa  mov     r8, [rcx+r8+10h]; lpString1
0x1800338af  mov     ecx, 7Fh; Locale
0x1800338b4  call    cs:__imp_CompareStringW
0x1800338bb  nop     dword ptr [rax+rax+00h]
0x1800338c0  cmp     eax, 2
0x1800338c3  jz      short loc_1800338CE
0x1800338c5  mov     rdx, [rbp+var_30]
0x1800338c9  add     r14d, ebx
0x1800338cc  jmp     short loc_180033884
0x1800338ce  mov     rcx, [rbp+var_30]
0x1800338d2  call    cs:__imp_FwBaseFree
0x1800338d9  nop     dword ptr [rax+rax+00h]
0x1800338de  jmp     loc_1800339C1
0x1800338e3  mov     eax, r12d
0x1800338e6  imul    r14, rax, 70h ; 'p'
0x1800338ea  mov     rax, [rdi+0E0h]
0x1800338f1  mov     [r14+rax+10h], rdx
0x1800338f6  mov     rdx, [rdi+0E0h]
0x1800338fd  mov     rcx, [rsi+110h]
0x180033904  add     rdx, 8
0x180033908  add     rdx, r14
0x18003390b  call    cs:__imp_FwStringCopy
0x180033912  nop     dword ptr [rax+rax+00h]
0x180033917  test    eax, eax
0x180033919  js      loc_180033A2B
0x18003391f  mov     rcx, [rsi+18h]
0x180033923  test    rcx, rcx
0x180033926  jz      short loc_180033946
0x180033928  mov     rdx, [rdi+0E0h]
0x18003392f  add     rdx, r14
0x180033932  call    cs:__imp_FwStringCopy
0x180033939  nop     dword ptr [rax+rax+00h]
0x18003393e  test    eax, eax
0x180033940  js      loc_180033A2B
0x180033946  mov     rcx, rsi; struct _tag_FW_RULE *
0x180033949  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x18003394e  mov     ecx, eax
0x180033950  mov     rax, [rdi+0E0h]
0x180033957  mov     [r14+rax+68h], ecx
0x18003395c  mov     rcx, [rdi+0E0h]
0x180033963  cmp     [rsi+154h], ebx
0x180033969  jnz     short loc_18003396F
0x18003396b  mov     eax, ebx
0x18003396d  jmp     short loc_180033971
0x18003396f  xor     eax, eax
0x180033971  mov     [r14+rcx+6Ch], eax
0x180033976  mov     rcx, rsi; struct _tag_FW_RULE *
0x180033979  mov     rax, [rdi+0E0h]
0x180033980  lea     r8, [rax+30h]
0x180033984  lea     rdx, [rax+18h]
0x180033988  add     r8, r14; struct ICF_SUBNETS6_ *
0x18003398b  add     rdx, r14; struct ICF_SUBNETS_ *
0x18003398e  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180033993  mov     r15d, eax
0x180033996  test    eax, eax
0x180033998  jnz     short loc_1800339F3
0x18003399a  mov     rax, [rdi+0E0h]
0x1800339a1  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800339a4  lea     r8, [rax+58h]
0x1800339a8  lea     rdx, [rax+48h]
0x1800339ac  add     r8, r14; struct ICF_RANGES6_ *
0x1800339af  add     rdx, r14; struct ICF_RANGES_ *
0x1800339b2  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x1800339b7  mov     r14d, eax
0x1800339ba  test    eax, eax
0x1800339bc  jnz     short loc_1800339C9
0x1800339be  add     r12d, ebx
0x1800339c1  mov     rsi, [rsi]
0x1800339c4  jmp     loc_1800337FE
0x1800339c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339d0  lea     rax, WPP_GLOBAL_Control
0x1800339d7  cmp     rcx, rax
0x1800339da  jz      loc_180033747
0x1800339e0  test    [rcx+1Ch], bl
0x1800339e3  jz      loc_180033747
0x1800339e9  mov     edx, 23h ; '#'
0x1800339ee  jmp     loc_180033734
0x1800339f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339fa  lea     rax, WPP_GLOBAL_Control
0x180033a01  cmp     rcx, rax
0x180033a04  jz      short loc_180033A23
0x180033a06  test    [rcx+1Ch], bl
0x180033a09  jz      short loc_180033A23
0x180033a0b  mov     rcx, [rcx+10h]
0x180033a0f  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180033a16  mov     edx, 22h ; '"'
0x180033a1b  mov     r9d, r15d
0x180033a1e  call    WPP_SF_d
0x180033a23  mov     eax, r15d
0x180033a26  jmp     loc_180033AD4
0x180033a2b  mov     ecx, eax
0x180033a2d  jmp     short loc_180033AA9
0x180033a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a36  lea     rax, WPP_GLOBAL_Control
0x180033a3d  cmp     rcx, rax
0x180033a40  jz      short loc_180033A60
0x180033a42  test    [rcx+1Ch], bl
0x180033a45  jz      short loc_180033A60
0x180033a47  mov     rcx, [rcx+10h]
0x180033a4b  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180033a52  mov     edx, 21h ; '!'
0x180033a57  call    WPP_SF_
0x180033a5c  mov     rdx, [rbp+var_30]
0x180033a60  mov     rcx, rdx
0x180033a63  call    cs:__imp_FwBaseFree
0x180033a6a  nop     dword ptr [rax+rax+00h]
0x180033a6f  mov     eax, 1Fh
0x180033a74  jmp     short loc_180033AD4
0x180033a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a7d  lea     rax, WPP_GLOBAL_Control
0x180033a84  cmp     rcx, rax
0x180033a87  jz      short loc_180033AA6
0x180033a89  test    [rcx+1Ch], bl
0x180033a8c  jz      short loc_180033AA6
0x180033a8e  mov     rcx, [rcx+10h]
0x180033a92  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180033a99  mov     edx, 20h ; ' '
0x180033a9e  mov     r9d, r14d
0x180033aa1  call    WPP_SF_d
0x180033aa6  mov     ecx, r14d
0x180033aa9  call    cs:__imp_FwHResultToWindowsError
0x180033ab0  nop     dword ptr [rax+rax+00h]
0x180033ab5  jmp     short loc_180033AD4
0x180033ab7  mov     [rdi+0D8h], r12d
0x180033abe  jmp     short loc_180033AD2
0x180033ac0  mov     eax, 8
0x180033ac5  jmp     short loc_180033AD4
0x180033ac7  mov     qword ptr [rdi+0E0h], 0
0x180033ad2  xor     eax, eax
0x180033ad4  mov     rcx, [rbp+var_10]
0x180033ad8  xor     rcx, rsp; StackCookie
0x180033adb  call    __security_check_cookie
0x180033ae0  add     rsp, 70h
0x180033ae4  pop     r15
  ... truncated ...
```
