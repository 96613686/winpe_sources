# CopyPortsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x1800340d8`
- end: `0x18003456b`
- name: `?CopyPortsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `1171`
- prototype: `unsigned int __high(void *, enum _tag_FW_PROFILE_TYPE, const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

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
- `0x1800340d8`
- `0x1800348ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800343b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180034402`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180034445`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800343b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180034402`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180034445`
- `fwbase!FwBaseAlloc` at `0x1800342b9`
- `fwbase!FwBaseAlloc` at `0x1800342b9`
- `fwbase!FwSizeTMultiply` at `0x1800342a1`
- `fwbase!FwSizeTMultiply` at `0x1800342a1`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180034262`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800342fb`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180034262`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800342fb`
- `fwbase!FwHResultToWindowsError` at `0x18003415b`
- `fwbase!FwHResultToWindowsError` at `0x1800344dc`
- `fwbase!FwHResultToWindowsError` at `0x18003415b`
- `fwbase!FwHResultToWindowsError` at `0x1800344dc`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18003424f`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800342e4`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18003424f`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800342e4`
- `fwbase!FwStringCopy` at `0x180034326`
- `fwbase!FwStringCopy` at `0x180034326`

## string_xrefs

- `0x18003439e`: `@FirewallAPI.dll,-28502`
- `0x1800343e5`: `@FirewallAPI.dll,-23006`
- `0x180034428`: `@FirewallAPI.dll,-28752`

## pseudocode

```c
__int64 __fastcall CopyPortsSettingsToProfile(int a1, int a2, __int64 *a3, __int64 a4)
{
  int v6; // r14d
  int CurrentProfile; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v12; // r14d
  int v13; // eax
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r15d
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r14
  const WCHAR *v23; // r8
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+48h] [rbp-18h] BYREF
  int v26; // [rsp+4Ch] [rbp-14h] BYREF

  LODWORD(v24) = a2;
  v25 = 0;
  v6 = a2;
  v26 = 4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( v6 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v24);
    if ( CurrentProfile < 0 )
    {
      v9 = FwHResultToWindowsError((unsigned int)CurrentProfile);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v9);
      return v10;
    }
    v6 = v24;
  }
  *(_DWORD *)(a4 + 192) = 2;
  LODWORD(v24) = 0;
  v12 = FWGetConfig2(a1, 12, v6, 1, (__int64)&v25, (__int64)&v26, (__int64)&v24);
  if ( v12 == 50 )
  {
    v13 = 1;
    v25 = 1;
  }
  else
  {
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 26;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v12);
      }
      return v12;
    }
    v13 = v25;
  }
  *(_DWORD *)(a4 + 176) = 0;
  v16 = a3;
  for ( *(_DWORD *)(a4 + 196) = (v13 != 0) + 1; v16; v16 = (_QWORD *)*v16 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(v16) && (unsigned int)IsRuleOldGlobalOpenPort(v16) )
      ++*(_DWORD *)(a4 + 176);
  }
  v17 = *(_DWORD *)(a4 + 176);
  if ( v17 )
  {
    v24 = 0;
    if ( (int)FwSizeTMultiply(112, v17, &v24) >= 0 )
    {
      v18 = FwBaseAlloc(v24);
      *(_QWORD *)(a4 + 184) = v18;
      if ( v18 )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( !a3 )
          {
            *(_DWORD *)(a4 + 176) = v19;
            return 0;
          }
          if ( (unsigned int)IsRuleOpenPortOrAuthApp(a3) && (unsigned int)IsRuleOldGlobalOpenPort(a3) )
          {
            v20 = a3[3];
            if ( v20 )
            {
              v21 = FwStringCopy(v20, *(_QWORD *)(a4 + 184) + 112LL * v19);
              if ( v21 < 0 )
                return FwHResultToWindowsError((unsigned int)v21);
            }
            v22 = 112LL * v19;
            *(_WORD *)(*(_QWORD *)(a4 + 184) + v22 + 8) = *(_WORD *)a3[9];
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 12) = *((unsigned __int16 *)a3 + 24);
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 96) = IsRuleEnabled((const struct _tag_FW_RULE *)a3);
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 3;
            v23 = (const WCHAR *)a3[39];
            if ( v23 )
            {
              if ( CompareStringW(0x7Fu, 1u, v23, -1, L"@FirewallAPI.dll,-28502", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 0;
              }
              else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a3[39], -1, L"@FirewallAPI.dll,-23006", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 1;
              }
              else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a3[39], -1, L"@FirewallAPI.dll,-28752", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 2;
              }
            }
            *(_DWORD *)(v22 + *(_QWORD *)(a4 + 184) + 104) = *((_DWORD *)a3 + 85) == 1;
            v12 = CopySubnetRestrictions(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_SUBNETS_ *)(v22 + *(_QWORD *)(a4 + 184) + 16LL),
                    (struct ICF_SUBNETS6_ *)(v22 + *(_QWORD *)(a4 + 184) + 40LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 27;
                goto LABEL_17;
              }
              return v12;
            }
            v12 = CopyAddrRanges(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_RANGES_ *)(112LL * v19 + *(_QWORD *)(a4 + 184) + 64LL),
                    (struct ICF_RANGES6_ *)(112LL * v19 + *(_QWORD *)(a4 + 184) + 80LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 28;
                goto LABEL_17;
              }
              return v12;
            }
            ++v19;
          }
          a3 = (__int64 *)*a3;
        }
      }
    }
    return 8;
  }
  else
  {
    *(_QWORD *)(a4 + 184) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1800340d8  push    rbp
0x1800340da  push    rbx
0x1800340db  push    rsi
0x1800340dc  push    rdi
0x1800340dd  push    r13
0x1800340df  push    r14
0x1800340e1  push    r15
0x1800340e3  mov     rbp, rsp
0x1800340e6  sub     rsp, 60h
0x1800340ea  mov     rax, cs:__security_cookie
0x1800340f1  xor     rax, rsp
0x1800340f4  mov     [rbp+var_10], rax
0x1800340f8  mov     rbx, r9
0x1800340fb  mov     dword ptr [rbp+var_20], edx
0x1800340fe  mov     rsi, r8
0x180034101  mov     [rbp+var_18], 0
0x180034108  mov     r14d, edx
0x18003410b  mov     [rbp+var_14], 4
0x180034112  mov     r15, rcx
0x180034115  mov     rcx, cs:WPP_GLOBAL_Control
0x18003411c  lea     r13, WPP_GLOBAL_Control
0x180034123  cmp     rcx, r13
0x180034126  jz      short loc_180034143
0x180034128  test    byte ptr [rcx+1Ch], 8
0x18003412c  jz      short loc_180034143
0x18003412e  mov     rcx, [rcx+10h]
0x180034132  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180034139  mov     edx, 18h
0x18003413e  call    WPP_SF_
0x180034143  cmp     r14d, 80000000h
0x18003414a  jnz     short loc_1800341A1
0x18003414c  lea     rcx, [rbp+var_20]; enum _tag_FW_PROFILE_TYPE *
0x180034150  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x180034155  test    eax, eax
0x180034157  jns     short loc_18003419D
0x180034159  mov     ecx, eax
0x18003415b  call    cs:__imp_FwHResultToWindowsError
0x180034162  nop     dword ptr [rax+rax+00h]
0x180034167  mov     ebx, eax
0x180034169  mov     rcx, cs:WPP_GLOBAL_Control
0x180034170  cmp     rcx, r13
0x180034173  jz      short loc_180034196
0x180034175  mov     edi, 1
0x18003417a  test    [rcx+1Ch], dil
0x18003417e  jz      short loc_180034196
0x180034180  mov     rcx, [rcx+10h]
0x180034184  lea     edx, [rdi+18h]
0x180034187  mov     r9d, eax
0x18003418a  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180034191  call    WPP_SF_d
0x180034196  mov     eax, ebx
0x180034198  jmp     loc_18003454F
0x18003419d  mov     r14d, dword ptr [rbp+var_20]
0x1800341a1  lea     rax, [rbp+var_20]
0x1800341a5  mov     dword ptr [rbx+0C0h], 2
0x1800341af  mov     [rsp+60h+var_30], rax
0x1800341b4  mov     edi, 1
0x1800341b9  lea     rax, [rbp+var_14]
0x1800341bd  mov     dword ptr [rbp+var_20], 0
0x1800341c4  mov     qword ptr [rsp+60h+cchCount2], rax
0x1800341c9  mov     r9d, edi
0x1800341cc  lea     rax, [rbp+var_18]
0x1800341d0  mov     r8d, r14d
0x1800341d3  lea     edx, [rdi+0Bh]
0x1800341d6  mov     [rsp+60h+lpString2], rax
0x1800341db  mov     rcx, r15
0x1800341de  call    FWGetConfig2
0x1800341e3  mov     r14d, eax
0x1800341e6  cmp     eax, 32h ; '2'
0x1800341e9  jnz     short loc_1800341F2
0x1800341eb  mov     eax, edi
0x1800341ed  mov     [rbp+var_18], eax
0x1800341f0  jmp     short loc_18003422C
0x1800341f2  test    r14d, r14d
0x1800341f5  jz      short loc_180034229
0x1800341f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341fe  cmp     rcx, r13
0x180034201  jz      short loc_180034221
0x180034203  test    [rcx+1Ch], dil
0x180034207  jz      short loc_180034221
0x180034209  mov     edx, 1Ah
0x18003420e  mov     rcx, [rcx+10h]
0x180034212  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180034219  mov     r9d, r14d
0x18003421c  call    WPP_SF_d
0x180034221  mov     eax, r14d
0x180034224  jmp     loc_18003454F
0x180034229  mov     eax, [rbp+var_18]
0x18003422c  neg     eax
0x18003422e  mov     dword ptr [rbx+0B0h], 0
0x180034238  mov     r14, rsi
0x18003423b  sbb     eax, eax
0x18003423d  neg     eax
0x18003423f  add     eax, edi
0x180034241  mov     [rbx+0C4h], eax
0x180034247  test    rsi, rsi
0x18003424a  jz      short loc_180034280
0x18003424c  mov     rcx, r14
0x18003424f  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180034256  nop     dword ptr [rax+rax+00h]
0x18003425b  test    eax, eax
0x18003425d  jz      short loc_180034278
0x18003425f  mov     rcx, r14
0x180034262  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180034269  nop     dword ptr [rax+rax+00h]
0x18003426e  test    eax, eax
0x180034270  jz      short loc_180034278
0x180034272  add     [rbx+0B0h], edi
0x180034278  mov     r14, [r14]
0x18003427b  test    r14, r14
0x18003427e  jnz     short loc_18003424C
0x180034280  mov     eax, [rbx+0B0h]
0x180034286  test    eax, eax
0x180034288  jz      loc_180034542
0x18003428e  mov     edx, eax
0x180034290  mov     [rbp+var_20], 0
0x180034298  lea     r8, [rbp+var_20]
0x18003429c  mov     ecx, 70h ; 'p'
0x1800342a1  call    cs:__imp_FwSizeTMultiply
0x1800342a8  nop     dword ptr [rax+rax+00h]
0x1800342ad  test    eax, eax
0x1800342af  js      loc_18003453B
0x1800342b5  mov     rcx, [rbp+var_20]
0x1800342b9  call    cs:__imp_FwBaseAlloc
0x1800342c0  nop     dword ptr [rax+rax+00h]
0x1800342c5  mov     [rbx+0B8h], rax
0x1800342cc  test    rax, rax
0x1800342cf  jz      loc_18003453B
0x1800342d5  xor     r15d, r15d
0x1800342d8  test    rsi, rsi
0x1800342db  jz      loc_180034532
0x1800342e1  mov     rcx, rsi
0x1800342e4  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x1800342eb  nop     dword ptr [rax+rax+00h]
0x1800342f0  test    eax, eax
0x1800342f2  jz      loc_1800344D2
0x1800342f8  mov     rcx, rsi
0x1800342fb  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180034302  nop     dword ptr [rax+rax+00h]
0x180034307  test    eax, eax
0x180034309  jz      loc_1800344D2
0x18003430f  mov     rcx, [rsi+18h]
0x180034313  test    rcx, rcx
0x180034316  jz      short loc_18003433A
0x180034318  mov     eax, r15d
0x18003431b  imul    rdx, rax, 70h ; 'p'
0x18003431f  add     rdx, [rbx+0B8h]
0x180034326  call    cs:__imp_FwStringCopy
0x18003432d  nop     dword ptr [rax+rax+00h]
0x180034332  test    eax, eax
0x180034334  js      loc_1800344DA
0x18003433a  mov     rcx, [rbx+0B8h]
0x180034341  mov     eax, r15d
0x180034344  imul    r14, rax, 70h ; 'p'
0x180034348  mov     rax, [rsi+48h]
0x18003434c  movzx   eax, word ptr [rax]
0x18003434f  mov     [rcx+r14+8], ax
0x180034355  mov     rax, [rbx+0B8h]
0x18003435c  movzx   ecx, word ptr [rsi+30h]
0x180034360  mov     [rax+r14+0Ch], ecx
0x180034365  mov     rcx, rsi; struct _tag_FW_RULE *
0x180034368  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x18003436d  mov     ecx, eax
0x18003436f  mov     rax, [rbx+0B8h]
0x180034376  mov     [rax+r14+60h], ecx
0x18003437b  mov     rax, [rbx+0B8h]
0x180034382  mov     dword ptr [rax+r14+64h], 3
0x18003438b  mov     r8, [rsi+138h]; lpString1
0x180034392  test    r8, r8
0x180034395  jz      loc_180034466
0x18003439b  or      ecx, 0FFFFFFFFh
0x18003439e  lea     rax, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x1800343a5  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x1800343a9  mov     r9d, ecx; cchCount1
0x1800343ac  mov     ecx, 7Fh; Locale
0x1800343b1  mov     [rsp+60h+lpString2], rax; lpString2
0x1800343b6  mov     edx, edi; dwCmpFlags
0x1800343b8  call    cs:__imp_CompareStringW
0x1800343bf  nop     dword ptr [rax+rax+00h]
0x1800343c4  cmp     eax, 2
0x1800343c7  jnz     short loc_1800343DE
0x1800343c9  mov     rax, [rbx+0B8h]
0x1800343d0  mov     dword ptr [rax+r14+64h], 0
0x1800343d9  jmp     loc_180034466
0x1800343de  mov     r8, [rsi+138h]; lpString1
0x1800343e5  lea     rax, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x1800343ec  or      ecx, 0FFFFFFFFh
0x1800343ef  mov     edx, edi; dwCmpFlags
0x1800343f1  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x1800343f5  mov     r9d, ecx; cchCount1
0x1800343f8  mov     ecx, 7Fh; Locale
0x1800343fd  mov     [rsp+60h+lpString2], rax; lpString2
0x180034402  call    cs:__imp_CompareStringW
0x180034409  nop     dword ptr [rax+rax+00h]
0x18003440e  cmp     eax, 2
0x180034411  jnz     short loc_180034421
0x180034413  mov     rax, [rbx+0B8h]
0x18003441a  mov     [rax+r14+64h], edi
0x18003441f  jmp     short loc_180034466
0x180034421  mov     r8, [rsi+138h]; lpString1
0x180034428  lea     rax, aFirewallapiDll_6; "@FirewallAPI.dll,-28752"
0x18003442f  or      ecx, 0FFFFFFFFh
0x180034432  mov     edx, edi; dwCmpFlags
0x180034434  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x180034438  mov     r9d, ecx; cchCount1
0x18003443b  mov     ecx, 7Fh; Locale
0x180034440  mov     [rsp+60h+lpString2], rax; lpString2
0x180034445  call    cs:__imp_CompareStringW
0x18003444c  nop     dword ptr [rax+rax+00h]
0x180034451  cmp     eax, 2
0x180034454  jnz     short loc_180034466
0x180034456  mov     rax, [rbx+0B8h]
0x18003445d  mov     dword ptr [rax+r14+64h], 2
0x180034466  mov     rcx, [rbx+0B8h]
0x18003446d  cmp     [rsi+154h], edi
0x180034473  jnz     short loc_180034479
0x180034475  mov     eax, edi
0x180034477  jmp     short loc_18003447B
0x180034479  xor     eax, eax
0x18003447b  mov     [r14+rcx+68h], eax
0x180034480  mov     rcx, rsi; struct _tag_FW_RULE *
0x180034483  mov     rax, [rbx+0B8h]
0x18003448a  lea     r8, [rax+28h]
0x18003448e  lea     rdx, [rax+10h]
0x180034492  add     r8, r14; struct ICF_SUBNETS6_ *
0x180034495  add     rdx, r14; struct ICF_SUBNETS_ *
0x180034498  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x18003449d  mov     r14d, eax
0x1800344a0  test    eax, eax
0x1800344a2  jnz     short loc_18003450E
0x1800344a4  mov     eax, r15d
0x1800344a7  imul    rcx, rax, 70h ; 'p'
0x1800344ab  mov     rax, [rbx+0B8h]
0x1800344b2  lea     r8, [rax+50h]
0x1800344b6  lea     rdx, [rax+40h]
0x1800344ba  add     r8, rcx; struct ICF_RANGES6_ *
0x1800344bd  add     rdx, rcx; struct ICF_RANGES_ *
0x1800344c0  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800344c3  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x1800344c8  mov     r14d, eax
0x1800344cb  test    eax, eax
0x1800344cd  jnz     short loc_1800344EA
0x1800344cf  add     r15d, edi
0x1800344d2  mov     rsi, [rsi]
0x1800344d5  jmp     loc_1800342D8
0x1800344da  mov     ecx, eax
0x1800344dc  call    cs:__imp_FwHResultToWindowsError
0x1800344e3  nop     dword ptr [rax+rax+00h]
0x1800344e8  jmp     short loc_18003454F
0x1800344ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344f1  cmp     rcx, r13
0x1800344f4  jz      loc_180034221
0x1800344fa  test    [rcx+1Ch], dil
0x1800344fe  jz      loc_180034221
0x180034504  mov     edx, 1Ch
0x180034509  jmp     loc_18003420E
0x18003450e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034515  cmp     rcx, r13
0x180034518  jz      loc_180034221
0x18003451e  test    [rcx+1Ch], dil
0x180034522  jz      loc_180034221
0x180034528  mov     edx, 1Bh
0x18003452d  jmp     loc_18003420E
0x180034532  mov     [rbx+0B0h], r15d
0x180034539  jmp     short loc_18003454D
0x18003453b  mov     eax, 8
0x180034540  jmp     short loc_18003454F
0x180034542  mov     qword ptr [rbx+0B8h], 0
0x18003454d  xor     eax, eax
0x18003454f  mov     rcx, [rbp+var_10]
0x180034553  xor     rcx, rsp; StackCookie
0x180034556  call    __security_check_cookie
0x18003455b  add     rsp, 60h
0x18003455f  pop     r15
0x180034561  pop     r14
0x180034563  pop     r13
0x180034565  pop     rdi
0x180034566  pop     rsi
0x180034567  pop     rbx
0x180034568  pop     rbp
0x180034569  retn
```
