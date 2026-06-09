# FwGetConstrainedInterfaceRules

- ea: `0x180035e2c`
- end: `0x1800362a9`
- name: `FwGetConstrainedInterfaceRules`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180036990`

## callees

- `0x18000af3c`
- `0x180035e2c`
- `0x180056cfc`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `fwbase!FwStringBuild` at `0x180035fe5`
- `fwbase!FwStringBuild` at `0x1800360a0`
- `fwbase!FwStringBuild` at `0x180035fe5`
- `fwbase!FwStringBuild` at `0x1800360a0`
- `FWPolicyIOMgr!FwFreeHyperVRulesBySchemaVersion` at `0x180036263`
- `FWPolicyIOMgr!FwFreeHyperVRulesBySchemaVersion` at `0x180036263`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x180035f65`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x180036039`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18003613e`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x1800361df`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x180035f65`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x180036039`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18003613e`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x1800361df`

## pseudocode

```c
__int64 __fastcall FwGetConstrainedInterfaceRules(_QWORD *a1)
{
  int ConstrainedInterfaceRuleId; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rdx
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+5Ah] [rbp-A6h]
  __int16 v13; // [rsp+5Eh] [rbp-A2h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  const wchar_t *v15; // [rsp+68h] [rbp-98h]
  __int16 v16; // [rsp+70h] [rbp-90h]
  __int16 v17; // [rsp+72h] [rbp-8Eh]
  int v18; // [rsp+74h] [rbp-8Ch]
  GUID v19; // [rsp+78h] [rbp-88h]
  __int16 v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+8Ah] [rbp-76h]
  __int16 v22; // [rsp+8Eh] [rbp-72h]
  _BYTE v23[72]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v24; // [rsp+D8h] [rbp-28h]
  __int64 v25; // [rsp+E8h] [rbp-18h]
  _DWORD v26[8]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD *v27; // [rsp+110h] [rbp+10h]
  int v28; // [rsp+128h] [rbp+28h]
  __int64 *v29; // [rsp+130h] [rbp+30h]
  __int128 v30; // [rsp+138h] [rbp+38h]
  __int64 v31; // [rsp+148h] [rbp+48h]
  int v32; // [rsp+150h] [rbp+50h]
  int v33; // [rsp+154h] [rbp+54h]
  int v34; // [rsp+158h] [rbp+58h]
  int v35; // [rsp+15Ch] [rbp+5Ch]
  __int128 v36; // [rsp+160h] [rbp+60h]
  __int64 v37; // [rsp+170h] [rbp+70h]
  __int64 v38; // [rsp+180h] [rbp+80h] BYREF
  int v39; // [rsp+188h] [rbp+88h]
  __int64 v40; // [rsp+18Ch] [rbp+8Ch]
  __int64 v41; // [rsp+194h] [rbp+94h]
  int v42; // [rsp+19Ch] [rbp+9Ch]
  _DWORD v43[2]; // [rsp+1A0h] [rbp+A0h] BYREF

  v11 = 545;
  v9[0] = 0;
  v12 = 0;
  v13 = 0;
  v17 = 0;
  v10 = 0;
  v20 = 256;
  v14 = 0;
  v18 = 1;
  v19 = GUID_NULL;
  v21 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v25 = 0;
  v24 = 0;
  memset_0(v26, 0, 0x48u);
  v33 = 3;
  v31 = 0;
  v37 = 0;
  v34 = 1;
  v15 = L"MPSSVC Constrained Interface Block Rule";
  v35 = 5;
  v30 = 0;
  v43[0] = 2130706432;
  v36 = 0;
  v43[1] = 0x7FFFFFFF;
  v38 = 0;
  v39 = 0;
  v40 = 0x1000000;
  v41 = 0;
  v42 = 0x1000000;
  v32 = 2;
  v16 = 2;
  ConstrainedInterfaceRuleId = FwCopyHyperVRule(&v10, v9);
  if ( ConstrainedInterfaceRuleId < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v4 = 13;
LABEL_5:
      WPP_SF_d(
        *(_QWORD *)(v3 + 16),
        v4,
        WPP_a1a9abb887e435996575206ee3f3f861_Traceguids,
        (unsigned int)ConstrainedInterfaceRuleId);
      return (unsigned int)ConstrainedInterfaceRuleId;
    }
    return (unsigned int)ConstrainedInterfaceRuleId;
  }
  ConstrainedInterfaceRuleId = FwStringBuild(v9[0] + 16LL, L"MPSSVC_CONSTRAINED_INTERFACE_RULE", L"_", L"INBOUND");
  if ( ConstrainedInterfaceRuleId >= 0 )
  {
    *(_DWORD *)(v9[0] + 36LL) = 1;
    v5 = v9[0];
    v9[0] = 0;
    ConstrainedInterfaceRuleId = FwCopyHyperVRule(&v10, v9);
    if ( ConstrainedInterfaceRuleId >= 0 )
    {
      ConstrainedInterfaceRuleId = FwStringBuild(v9[0] + 16LL, L"MPSSVC_CONSTRAINED_INTERFACE_RULE", L"_", L"OUTBOUND");
      if ( ConstrainedInterfaceRuleId >= 0 )
      {
        *(_DWORD *)(v9[0] + 36LL) = 2;
        *(_QWORD *)v9[0] = v5;
        v5 = v9[0];
        v15 = L"MPSSVC Constrained Interface Allow Rule";
        v27 = v43;
        v29 = &v38;
        v9[0] = 0;
        v32 = 3;
        v26[0] = 1;
        v26[1] = 1;
        v26[6] = 1;
        v28 = 1;
        v16 = 1;
        ConstrainedInterfaceRuleId = FwCopyHyperVRule(&v10, v9);
        if ( ConstrainedInterfaceRuleId >= 0 )
        {
          ConstrainedInterfaceRuleId = FwGetConstrainedInterfaceRuleId(1, 3, v9[0] + 16LL);
          if ( ConstrainedInterfaceRuleId >= 0 )
          {
            *(_DWORD *)(v9[0] + 36LL) = 1;
            *(_QWORD *)v9[0] = v5;
            v5 = v9[0];
            v9[0] = 0;
            ConstrainedInterfaceRuleId = FwCopyHyperVRule(&v10, v9);
            if ( ConstrainedInterfaceRuleId >= 0 )
            {
              ConstrainedInterfaceRuleId = FwGetConstrainedInterfaceRuleId(2, 3, v9[0] + 16LL);
              if ( ConstrainedInterfaceRuleId >= 0 )
              {
                *(_DWORD *)(v9[0] + 36LL) = 2;
                *(_QWORD *)v9[0] = v5;
                *a1 = v9[0];
                return (unsigned int)ConstrainedInterfaceRuleId;
              }
              v6 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_35;
              }
              v7 = 20;
              goto LABEL_34;
            }
            v6 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v7 = 19;
              goto LABEL_34;
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v7 = 18;
              goto LABEL_34;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v7 = 17;
            goto LABEL_34;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 16;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 15;
LABEL_34:
        WPP_SF_d(
          *(_QWORD *)(v6 + 16),
          v7,
          WPP_a1a9abb887e435996575206ee3f3f861_Traceguids,
          (unsigned int)ConstrainedInterfaceRuleId);
      }
    }
LABEL_35:
    if ( v5 )
      FwFreeHyperVRulesBySchemaVersion(v5, 545);
    return (unsigned int)ConstrainedInterfaceRuleId;
  }
  v3 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v4 = 14;
    goto LABEL_5;
  }
  return (unsigned int)ConstrainedInterfaceRuleId;
}

```

## disassembly

```asm
0x180035e2c  push    rbp
0x180035e2e  push    rbx
0x180035e2f  push    rsi
0x180035e30  push    rdi
0x180035e31  push    r12
0x180035e33  push    r13
0x180035e35  push    r14
0x180035e37  push    r15
0x180035e39  lea     rbp, [rsp-0B8h]
0x180035e41  sub     rsp, 1B8h
0x180035e48  mov     rax, cs:__security_cookie
0x180035e4f  xor     rax, rsp
0x180035e52  mov     [rbp+0F0h+var_48], rax
0x180035e59  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035e60  xor     r14d, r14d
0x180035e63  mov     eax, 221h
0x180035e68  mov     [rsp+1F0h+var_198], ax
0x180035e6d  mov     rsi, rcx
0x180035e70  xor     eax, eax
0x180035e72  mov     [rsp+1F0h+var_1B0], r14
0x180035e77  mov     [rsp+1F0h+var_196], eax
0x180035e7b  lea     rcx, [rbp+0F0h+var_160]; void *
0x180035e7f  mov     [rsp+1F0h+var_192], ax
0x180035e84  lea     r15d, [r14+1]
0x180035e88  mov     [rsp+1F0h+var_17E], ax
0x180035e8d  xor     edx, edx; Val
0x180035e8f  mov     eax, 100h
0x180035e94  mov     [rsp+1F0h+var_1A0], r14
0x180035e99  mov     [rbp+0F0h+var_168], ax
0x180035e9d  xor     eax, eax
0x180035e9f  mov     [rsp+1F0h+var_190], r14
0x180035ea4  mov     [rsp+1F0h+var_17C], r15d
0x180035ea9  movdqu  [rsp+1F0h+var_178], xmm0
0x180035eaf  lea     ebx, [rax+48h]
0x180035eb2  mov     [rbp+0F0h+var_166], eax
0x180035eb5  mov     r8d, ebx; Size
0x180035eb8  mov     [rbp+0F0h+var_162], ax
0x180035ebc  call    memset_0
0x180035ec1  xor     eax, eax
0x180035ec3  lea     rcx, [rbp+0F0h+var_100]; void *
0x180035ec7  xorps   xmm0, xmm0
0x180035eca  mov     [rbp+0F0h+var_108], rax
0x180035ece  mov     r8d, ebx; Size
0x180035ed1  xor     edx, edx; Val
0x180035ed3  movups  [rbp+0F0h+var_118], xmm0
0x180035ed7  call    memset_0
0x180035edc  xor     eax, eax
0x180035ede  mov     [rbp+0F0h+var_9C], 3
0x180035ee5  xorps   xmm0, xmm0
0x180035ee8  mov     [rbp+0F0h+var_A8], rax
0x180035eec  mov     [rbp+0F0h+var_80], rax
0x180035ef0  lea     r13d, [r14+2]
0x180035ef4  lea     rax, aMpssvcConstrai_0; "MPSSVC Constrained Interface Block Rule"
0x180035efb  mov     [rbp+0F0h+var_98], r15d
0x180035eff  lea     rdx, [rsp+1F0h+var_1B0]
0x180035f04  mov     [rsp+1F0h+var_188], rax
0x180035f09  lea     rcx, [rsp+1F0h+var_1A0]
0x180035f0e  mov     [rbp+0F0h+var_94], 5
0x180035f15  movups  [rbp+0F0h+var_B8], xmm0
0x180035f19  mov     [rbp+0F0h+var_50], 7F000000h
0x180035f23  movups  [rbp+0F0h+var_90], xmm0
0x180035f27  mov     [rbp+0F0h+var_4C], 7FFFFFFFh
0x180035f31  mov     [rbp+0F0h+var_70], r14
0x180035f38  mov     [rbp+0F0h+var_68], r14d
0x180035f3f  mov     [rbp+0F0h+var_64], 1000000h
0x180035f4a  mov     [rbp+0F0h+var_5C], r14
0x180035f51  mov     [rbp+0F0h+var_54], 1000000h
0x180035f5b  mov     [rbp+0F0h+var_A0], r13d
0x180035f5f  mov     [rsp+1F0h+var_180], r13w
0x180035f65  call    cs:__imp_FwCopyHyperVRule
0x180035f6b  mov     ebx, eax
0x180035f6d  test    eax, eax
0x180035f6f  jns     short loc_180035FAE
0x180035f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f78  lea     rax, WPP_GLOBAL_Control
0x180035f7f  cmp     rcx, rax
0x180035f82  jz      loc_180036284
0x180035f88  test    [rcx+1Ch], r15b
0x180035f8c  jz      loc_180036284
0x180035f92  lea     edx, [r14+0Dh]
0x180035f96  mov     rcx, [rcx+10h]
0x180035f9a  lea     r8, WPP_a1a9abb887e435996575206ee3f3f861_Traceguids
0x180035fa1  mov     r9d, ebx
0x180035fa4  call    WPP_SF_d
0x180035fa9  jmp     loc_180036284
0x180035fae  mov     rcx, [rsp+1F0h+var_1B0]
0x180035fb3  lea     rax, aBlock; "BLOCK"
0x180035fba  lea     r12, asc_1800F82FC; "_"
0x180035fc1  mov     [rsp+1F0h+var_1C0], r14
0x180035fc6  mov     [rsp+1F0h+var_1C8], rax
0x180035fcb  lea     r9, aInbound; "INBOUND"
0x180035fd2  add     rcx, 10h
0x180035fd6  mov     [rsp+1F0h+var_1D0], r12
0x180035fdb  mov     r8, r12
0x180035fde  lea     rdx, aMpssvcConstrai_1; "MPSSVC_CONSTRAINED_INTERFACE_RULE"
0x180035fe5  call    cs:__imp_FwStringBuild
0x180035feb  mov     ebx, eax
0x180035fed  test    eax, eax
0x180035fef  jns     short loc_18003601C
0x180035ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ff8  lea     rax, WPP_GLOBAL_Control
0x180035fff  cmp     rcx, rax
0x180036002  jz      loc_180036284
0x180036008  test    [rcx+1Ch], r15b
0x18003600c  jz      loc_180036284
0x180036012  mov     edx, 0Eh
0x180036017  jmp     loc_180035F96
0x18003601c  mov     rax, [rsp+1F0h+var_1B0]
0x180036021  lea     rdx, [rsp+1F0h+var_1B0]
0x180036026  lea     rcx, [rsp+1F0h+var_1A0]
0x18003602b  mov     [rax+24h], r15d
0x18003602f  mov     rdi, [rsp+1F0h+var_1B0]
0x180036034  mov     [rsp+1F0h+var_1B0], r14
0x180036039  call    cs:__imp_FwCopyHyperVRule
0x18003603f  mov     ebx, eax
0x180036041  test    eax, eax
0x180036043  jns     short loc_180036070
0x180036045  mov     rcx, cs:WPP_GLOBAL_Control
0x18003604c  lea     rax, WPP_GLOBAL_Control
0x180036053  cmp     rcx, rax
0x180036056  jz      loc_180036256
0x18003605c  test    [rcx+1Ch], r15b
0x180036060  jz      loc_180036256
0x180036066  mov     edx, 0Fh
0x18003606b  jmp     loc_180036243
0x180036070  mov     rcx, [rsp+1F0h+var_1B0]
0x180036075  lea     rax, aBlock; "BLOCK"
0x18003607c  mov     [rsp+1F0h+var_1C0], r14
0x180036081  lea     r9, aOutbound; "OUTBOUND"
0x180036088  mov     [rsp+1F0h+var_1C8], rax
0x18003608d  lea     rdx, aMpssvcConstrai_1; "MPSSVC_CONSTRAINED_INTERFACE_RULE"
0x180036094  add     rcx, 10h
0x180036098  mov     [rsp+1F0h+var_1D0], r12
0x18003609d  mov     r8, r12
0x1800360a0  call    cs:__imp_FwStringBuild
0x1800360a6  mov     ebx, eax
0x1800360a8  test    eax, eax
0x1800360aa  jns     short loc_1800360D7
0x1800360ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360b3  lea     rax, WPP_GLOBAL_Control
0x1800360ba  cmp     rcx, rax
0x1800360bd  jz      loc_180036256
0x1800360c3  test    [rcx+1Ch], r15b
0x1800360c7  jz      loc_180036256
0x1800360cd  mov     edx, 10h
0x1800360d2  jmp     loc_180036243
0x1800360d7  mov     rax, [rsp+1F0h+var_1B0]
0x1800360dc  lea     rdx, [rsp+1F0h+var_1B0]
0x1800360e1  mov     r12d, 3
0x1800360e7  lea     rcx, [rsp+1F0h+var_1A0]
0x1800360ec  mov     [rax+24h], r13d
0x1800360f0  mov     rax, [rsp+1F0h+var_1B0]
0x1800360f5  mov     [rax], rdi
0x1800360f8  lea     rax, aMpssvcConstrai; "MPSSVC Constrained Interface Allow Rule"
0x1800360ff  mov     rdi, [rsp+1F0h+var_1B0]
0x180036104  mov     [rsp+1F0h+var_188], rax
0x180036109  lea     rax, [rbp+0F0h+var_50]
0x180036110  mov     [rbp+0F0h+var_E0], rax
0x180036114  lea     rax, [rbp+0F0h+var_70]
0x18003611b  mov     [rbp+0F0h+var_C0], rax
0x18003611f  mov     [rsp+1F0h+var_1B0], r14
0x180036124  mov     [rbp+0F0h+var_A0], r12d
0x180036128  mov     [rbp+0F0h+var_100], r15d
0x18003612c  mov     [rbp+0F0h+var_FC], r15d
0x180036130  mov     [rbp+0F0h+var_E8], r15d
0x180036134  mov     [rbp+0F0h+var_C8], r15d
0x180036138  mov     [rsp+1F0h+var_180], r15w
0x18003613e  call    cs:__imp_FwCopyHyperVRule
0x180036144  mov     ebx, eax
0x180036146  test    eax, eax
0x180036148  jns     short loc_180036175
0x18003614a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036151  lea     rax, WPP_GLOBAL_Control
0x180036158  cmp     rcx, rax
0x18003615b  jz      loc_180036256
0x180036161  test    [rcx+1Ch], r15b
0x180036165  jz      loc_180036256
0x18003616b  lea     edx, [r12+0Eh]
0x180036170  jmp     loc_180036243
0x180036175  mov     r8, [rsp+1F0h+var_1B0]
0x18003617a  mov     edx, r12d
0x18003617d  add     r8, 10h
0x180036181  mov     ecx, r15d
0x180036184  call    FwGetConstrainedInterfaceRuleId
0x180036189  mov     ebx, eax
0x18003618b  test    eax, eax
0x18003618d  jns     short loc_1800361BA
0x18003618f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036196  lea     rax, WPP_GLOBAL_Control
0x18003619d  cmp     rcx, rax
0x1800361a0  jz      loc_180036256
0x1800361a6  test    [rcx+1Ch], r15b
0x1800361aa  jz      loc_180036256
0x1800361b0  mov     edx, 12h
0x1800361b5  jmp     loc_180036243
0x1800361ba  mov     rax, [rsp+1F0h+var_1B0]
0x1800361bf  lea     rdx, [rsp+1F0h+var_1B0]
0x1800361c4  lea     rcx, [rsp+1F0h+var_1A0]
0x1800361c9  mov     [rax+24h], r15d
0x1800361cd  mov     rax, [rsp+1F0h+var_1B0]
0x1800361d2  mov     [rax], rdi
0x1800361d5  mov     rdi, [rsp+1F0h+var_1B0]
0x1800361da  mov     [rsp+1F0h+var_1B0], r14
0x1800361df  call    cs:__imp_FwCopyHyperVRule
0x1800361e5  mov     ebx, eax
0x1800361e7  test    eax, eax
0x1800361e9  jns     short loc_18003620B
0x1800361eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361f2  lea     rax, WPP_GLOBAL_Control
0x1800361f9  cmp     rcx, rax
0x1800361fc  jz      short loc_180036256
0x1800361fe  test    [rcx+1Ch], r15b
0x180036202  jz      short loc_180036256
0x180036204  mov     edx, 13h
0x180036209  jmp     short loc_180036243
0x18003620b  mov     r8, [rsp+1F0h+var_1B0]
0x180036210  mov     edx, r12d
0x180036213  add     r8, 10h
0x180036217  mov     ecx, r13d
0x18003621a  call    FwGetConstrainedInterfaceRuleId
0x18003621f  mov     ebx, eax
0x180036221  test    eax, eax
0x180036223  jns     short loc_18003626B
0x180036225  mov     rcx, cs:WPP_GLOBAL_Control
0x18003622c  lea     rax, WPP_GLOBAL_Control
0x180036233  cmp     rcx, rax
0x180036236  jz      short loc_180036256
0x180036238  test    [rcx+1Ch], r15b
0x18003623c  jz      short loc_180036256
0x18003623e  mov     edx, 14h
0x180036243  mov     rcx, [rcx+10h]
0x180036247  lea     r8, WPP_a1a9abb887e435996575206ee3f3f861_Traceguids
0x18003624e  mov     r9d, ebx
0x180036251  call    WPP_SF_d
0x180036256  test    rdi, rdi
0x180036259  jz      short loc_180036284
0x18003625b  mov     edx, 221h
0x180036260  mov     rcx, rdi
0x180036263  call    cs:__imp_FwFreeHyperVRulesBySchemaVersion
0x180036269  jmp     short loc_180036284
0x18003626b  mov     rax, [rsp+1F0h+var_1B0]
0x180036270  mov     [rax+24h], r13d
0x180036274  mov     rax, [rsp+1F0h+var_1B0]
0x180036279  mov     [rax], rdi
0x18003627c  mov     rax, [rsp+1F0h+var_1B0]
0x180036281  mov     [rsi], rax
0x180036284  mov     eax, ebx
0x180036286  mov     rcx, [rbp+0F0h+var_48]
0x18003628d  xor     rcx, rsp; StackCookie
0x180036290  call    __security_check_cookie
0x180036295  add     rsp, 1B8h
0x18003629c  pop     r15
0x18003629e  pop     r14
0x1800362a0  pop     r13
0x1800362a2  pop     r12
0x1800362a4  pop     rdi
0x1800362a5  pop     rsi
0x1800362a6  pop     rbx
0x1800362a7  pop     rbp
0x1800362a8  retn
```
