# FwGetConstrainedInterfaceRules

- ea: `0x18000e964`
- end: `0x18000ee0c`
- name: `FwGetConstrainedInterfaceRules`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f4e0`

## callees

- `0x18000a710`
- `0x18000e964`
- `0x18005bbe0`
- `0x1800729c0`
- `0x180073488`

## import_xrefs

- `fwbase!FwStringBuild` at `0x18000eb23`
- `fwbase!FwStringBuild` at `0x18000ebea`
- `fwbase!FwStringBuild` at `0x18000eb23`
- `fwbase!FwStringBuild` at `0x18000ebea`
- `FWPolicyIOMgr!FwFreeHyperVRulesBySchemaVersion` at `0x18000edbf`
- `FWPolicyIOMgr!FwFreeHyperVRulesBySchemaVersion` at `0x18000edbf`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ea9d`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000eb7d`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ec8e`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ed35`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ea9d`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000eb7d`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ec8e`
- `FWPolicyIOMgr!FwCopyHyperVRule` at `0x18000ed35`

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
0x18000e964  push    rbp
0x18000e966  push    rbx
0x18000e967  push    rsi
0x18000e968  push    rdi
0x18000e969  push    r12
0x18000e96b  push    r13
0x18000e96d  push    r14
0x18000e96f  push    r15
0x18000e971  lea     rbp, [rsp-0B8h]
0x18000e979  sub     rsp, 1B8h
0x18000e980  mov     rax, cs:__security_cookie
0x18000e987  xor     rax, rsp
0x18000e98a  mov     [rbp+0F0h+var_48], rax
0x18000e991  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e998  xor     r14d, r14d
0x18000e99b  mov     eax, 221h
0x18000e9a0  mov     [rsp+1F0h+var_198], ax
0x18000e9a5  mov     rsi, rcx
0x18000e9a8  xor     eax, eax
0x18000e9aa  mov     [rsp+1F0h+var_1B0], r14
0x18000e9af  mov     [rsp+1F0h+var_196], eax
0x18000e9b3  lea     rcx, [rbp+0F0h+var_160]; void *
0x18000e9b7  mov     [rsp+1F0h+var_192], ax
0x18000e9bc  lea     r15d, [r14+1]
0x18000e9c0  mov     [rsp+1F0h+var_17E], ax
0x18000e9c5  xor     edx, edx; Val
0x18000e9c7  mov     eax, 100h
0x18000e9cc  mov     [rsp+1F0h+var_1A0], r14
0x18000e9d1  mov     [rbp+0F0h+var_168], ax
0x18000e9d5  xor     eax, eax
0x18000e9d7  mov     [rsp+1F0h+var_190], r14
0x18000e9dc  mov     [rsp+1F0h+var_17C], r15d
0x18000e9e1  movdqu  [rsp+1F0h+var_178], xmm0
0x18000e9e7  lea     ebx, [rax+48h]
0x18000e9ea  mov     [rbp+0F0h+var_166], eax
0x18000e9ed  mov     r8d, ebx; Size
0x18000e9f0  mov     [rbp+0F0h+var_162], ax
0x18000e9f4  call    memset_0
0x18000e9f9  xor     eax, eax
0x18000e9fb  lea     rcx, [rbp+0F0h+var_100]; void *
0x18000e9ff  xorps   xmm0, xmm0
0x18000ea02  mov     [rbp+0F0h+var_108], rax
0x18000ea06  mov     r8d, ebx; Size
0x18000ea09  xor     edx, edx; Val
0x18000ea0b  movups  [rbp+0F0h+var_118], xmm0
0x18000ea0f  call    memset_0
0x18000ea14  xor     eax, eax
0x18000ea16  mov     [rbp+0F0h+var_9C], 3
0x18000ea1d  xorps   xmm0, xmm0
0x18000ea20  mov     [rbp+0F0h+var_A8], rax
0x18000ea24  mov     [rbp+0F0h+var_80], rax
0x18000ea28  lea     r13d, [r14+2]
0x18000ea2c  lea     rax, aMpssvcConstrai_0; "MPSSVC Constrained Interface Block Rule"
0x18000ea33  mov     [rbp+0F0h+var_98], r15d
0x18000ea37  lea     rdx, [rsp+1F0h+var_1B0]
0x18000ea3c  mov     [rsp+1F0h+var_188], rax
0x18000ea41  lea     rcx, [rsp+1F0h+var_1A0]
0x18000ea46  mov     [rbp+0F0h+var_94], 5
0x18000ea4d  movups  [rbp+0F0h+var_B8], xmm0
0x18000ea51  mov     [rbp+0F0h+var_50], 7F000000h
0x18000ea5b  movups  [rbp+0F0h+var_90], xmm0
0x18000ea5f  mov     [rbp+0F0h+var_4C], 7FFFFFFFh
0x18000ea69  mov     [rbp+0F0h+var_70], r14
0x18000ea70  mov     [rbp+0F0h+var_68], r14d
0x18000ea77  mov     [rbp+0F0h+var_64], 1000000h
0x18000ea82  mov     [rbp+0F0h+var_5C], r14
0x18000ea89  mov     [rbp+0F0h+var_54], 1000000h
0x18000ea93  mov     [rbp+0F0h+var_A0], r13d
0x18000ea97  mov     [rsp+1F0h+var_180], r13w
0x18000ea9d  call    cs:__imp_FwCopyHyperVRule
0x18000eaa4  nop     dword ptr [rax+rax+00h]
0x18000eaa9  mov     ebx, eax
0x18000eaab  test    eax, eax
0x18000eaad  jns     short loc_18000EAEC
0x18000eaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eab6  lea     rax, WPP_GLOBAL_Control
0x18000eabd  cmp     rcx, rax
0x18000eac0  jz      loc_18000EDE6
0x18000eac6  test    [rcx+1Ch], r15b
0x18000eaca  jz      loc_18000EDE6
0x18000ead0  lea     edx, [r14+0Dh]
0x18000ead4  mov     rcx, [rcx+10h]
0x18000ead8  lea     r8, WPP_a1a9abb887e435996575206ee3f3f861_Traceguids
0x18000eadf  mov     r9d, ebx
0x18000eae2  call    WPP_SF_d
0x18000eae7  jmp     loc_18000EDE6
0x18000eaec  mov     rcx, [rsp+1F0h+var_1B0]
0x18000eaf1  lea     rax, aBlock; "BLOCK"
0x18000eaf8  lea     r12, asc_1800FE2BC; "_"
0x18000eaff  mov     [rsp+1F0h+var_1C0], r14
0x18000eb04  mov     [rsp+1F0h+var_1C8], rax
0x18000eb09  lea     r9, aInbound; "INBOUND"
0x18000eb10  add     rcx, 10h
0x18000eb14  mov     [rsp+1F0h+var_1D0], r12
0x18000eb19  mov     r8, r12
0x18000eb1c  lea     rdx, aMpssvcConstrai_1; "MPSSVC_CONSTRAINED_INTERFACE_RULE"
0x18000eb23  call    cs:__imp_FwStringBuild
0x18000eb2a  nop     dword ptr [rax+rax+00h]
0x18000eb2f  mov     ebx, eax
0x18000eb31  test    eax, eax
0x18000eb33  jns     short loc_18000EB60
0x18000eb35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb3c  lea     rax, WPP_GLOBAL_Control
0x18000eb43  cmp     rcx, rax
0x18000eb46  jz      loc_18000EDE6
0x18000eb4c  test    [rcx+1Ch], r15b
0x18000eb50  jz      loc_18000EDE6
0x18000eb56  mov     edx, 0Eh
0x18000eb5b  jmp     loc_18000EAD4
0x18000eb60  mov     rax, [rsp+1F0h+var_1B0]
0x18000eb65  lea     rdx, [rsp+1F0h+var_1B0]
0x18000eb6a  lea     rcx, [rsp+1F0h+var_1A0]
0x18000eb6f  mov     [rax+24h], r15d
0x18000eb73  mov     rdi, [rsp+1F0h+var_1B0]
0x18000eb78  mov     [rsp+1F0h+var_1B0], r14
0x18000eb7d  call    cs:__imp_FwCopyHyperVRule
0x18000eb84  nop     dword ptr [rax+rax+00h]
0x18000eb89  mov     ebx, eax
0x18000eb8b  test    eax, eax
0x18000eb8d  jns     short loc_18000EBBA
0x18000eb8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb96  lea     rax, WPP_GLOBAL_Control
0x18000eb9d  cmp     rcx, rax
0x18000eba0  jz      loc_18000EDB2
0x18000eba6  test    [rcx+1Ch], r15b
0x18000ebaa  jz      loc_18000EDB2
0x18000ebb0  mov     edx, 0Fh
0x18000ebb5  jmp     loc_18000ED9F
0x18000ebba  mov     rcx, [rsp+1F0h+var_1B0]
0x18000ebbf  lea     rax, aBlock; "BLOCK"
0x18000ebc6  mov     [rsp+1F0h+var_1C0], r14
0x18000ebcb  lea     r9, aOutbound; "OUTBOUND"
0x18000ebd2  mov     [rsp+1F0h+var_1C8], rax
0x18000ebd7  lea     rdx, aMpssvcConstrai_1; "MPSSVC_CONSTRAINED_INTERFACE_RULE"
0x18000ebde  add     rcx, 10h
0x18000ebe2  mov     [rsp+1F0h+var_1D0], r12
0x18000ebe7  mov     r8, r12
0x18000ebea  call    cs:__imp_FwStringBuild
0x18000ebf1  nop     dword ptr [rax+rax+00h]
0x18000ebf6  mov     ebx, eax
0x18000ebf8  test    eax, eax
0x18000ebfa  jns     short loc_18000EC27
0x18000ebfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec03  lea     rax, WPP_GLOBAL_Control
0x18000ec0a  cmp     rcx, rax
0x18000ec0d  jz      loc_18000EDB2
0x18000ec13  test    [rcx+1Ch], r15b
0x18000ec17  jz      loc_18000EDB2
0x18000ec1d  mov     edx, 10h
0x18000ec22  jmp     loc_18000ED9F
0x18000ec27  mov     rax, [rsp+1F0h+var_1B0]
0x18000ec2c  lea     rdx, [rsp+1F0h+var_1B0]
0x18000ec31  mov     r12d, 3
0x18000ec37  lea     rcx, [rsp+1F0h+var_1A0]
0x18000ec3c  mov     [rax+24h], r13d
0x18000ec40  mov     rax, [rsp+1F0h+var_1B0]
0x18000ec45  mov     [rax], rdi
0x18000ec48  lea     rax, aMpssvcConstrai; "MPSSVC Constrained Interface Allow Rule"
0x18000ec4f  mov     rdi, [rsp+1F0h+var_1B0]
0x18000ec54  mov     [rsp+1F0h+var_188], rax
0x18000ec59  lea     rax, [rbp+0F0h+var_50]
0x18000ec60  mov     [rbp+0F0h+var_E0], rax
0x18000ec64  lea     rax, [rbp+0F0h+var_70]
0x18000ec6b  mov     [rbp+0F0h+var_C0], rax
0x18000ec6f  mov     [rsp+1F0h+var_1B0], r14
0x18000ec74  mov     [rbp+0F0h+var_A0], r12d
0x18000ec78  mov     [rbp+0F0h+var_100], r15d
0x18000ec7c  mov     [rbp+0F0h+var_FC], r15d
0x18000ec80  mov     [rbp+0F0h+var_E8], r15d
0x18000ec84  mov     [rbp+0F0h+var_C8], r15d
0x18000ec88  mov     [rsp+1F0h+var_180], r15w
0x18000ec8e  call    cs:__imp_FwCopyHyperVRule
0x18000ec95  nop     dword ptr [rax+rax+00h]
0x18000ec9a  mov     ebx, eax
0x18000ec9c  test    eax, eax
0x18000ec9e  jns     short loc_18000ECCB
0x18000eca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eca7  lea     rax, WPP_GLOBAL_Control
0x18000ecae  cmp     rcx, rax
0x18000ecb1  jz      loc_18000EDB2
0x18000ecb7  test    [rcx+1Ch], r15b
0x18000ecbb  jz      loc_18000EDB2
0x18000ecc1  lea     edx, [r12+0Eh]
0x18000ecc6  jmp     loc_18000ED9F
0x18000eccb  mov     r8, [rsp+1F0h+var_1B0]
0x18000ecd0  mov     edx, r12d
0x18000ecd3  add     r8, 10h
0x18000ecd7  mov     ecx, r15d
0x18000ecda  call    FwGetConstrainedInterfaceRuleId
0x18000ecdf  mov     ebx, eax
0x18000ece1  test    eax, eax
0x18000ece3  jns     short loc_18000ED10
0x18000ece5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecec  lea     rax, WPP_GLOBAL_Control
0x18000ecf3  cmp     rcx, rax
0x18000ecf6  jz      loc_18000EDB2
0x18000ecfc  test    [rcx+1Ch], r15b
0x18000ed00  jz      loc_18000EDB2
0x18000ed06  mov     edx, 12h
0x18000ed0b  jmp     loc_18000ED9F
0x18000ed10  mov     rax, [rsp+1F0h+var_1B0]
0x18000ed15  lea     rdx, [rsp+1F0h+var_1B0]
0x18000ed1a  lea     rcx, [rsp+1F0h+var_1A0]
0x18000ed1f  mov     [rax+24h], r15d
0x18000ed23  mov     rax, [rsp+1F0h+var_1B0]
0x18000ed28  mov     [rax], rdi
0x18000ed2b  mov     rdi, [rsp+1F0h+var_1B0]
0x18000ed30  mov     [rsp+1F0h+var_1B0], r14
0x18000ed35  call    cs:__imp_FwCopyHyperVRule
0x18000ed3c  nop     dword ptr [rax+rax+00h]
0x18000ed41  mov     ebx, eax
0x18000ed43  test    eax, eax
0x18000ed45  jns     short loc_18000ED67
0x18000ed47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed4e  lea     rax, WPP_GLOBAL_Control
0x18000ed55  cmp     rcx, rax
0x18000ed58  jz      short loc_18000EDB2
0x18000ed5a  test    [rcx+1Ch], r15b
0x18000ed5e  jz      short loc_18000EDB2
0x18000ed60  mov     edx, 13h
0x18000ed65  jmp     short loc_18000ED9F
0x18000ed67  mov     r8, [rsp+1F0h+var_1B0]
0x18000ed6c  mov     edx, r12d
0x18000ed6f  add     r8, 10h
0x18000ed73  mov     ecx, r13d
0x18000ed76  call    FwGetConstrainedInterfaceRuleId
0x18000ed7b  mov     ebx, eax
0x18000ed7d  test    eax, eax
0x18000ed7f  jns     short loc_18000EDCD
0x18000ed81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed88  lea     rax, WPP_GLOBAL_Control
0x18000ed8f  cmp     rcx, rax
0x18000ed92  jz      short loc_18000EDB2
0x18000ed94  test    [rcx+1Ch], r15b
0x18000ed98  jz      short loc_18000EDB2
0x18000ed9a  mov     edx, 14h
0x18000ed9f  mov     rcx, [rcx+10h]
0x18000eda3  lea     r8, WPP_a1a9abb887e435996575206ee3f3f861_Traceguids
0x18000edaa  mov     r9d, ebx
0x18000edad  call    WPP_SF_d
0x18000edb2  test    rdi, rdi
0x18000edb5  jz      short loc_18000EDE6
0x18000edb7  mov     edx, 221h
0x18000edbc  mov     rcx, rdi
0x18000edbf  call    cs:__imp_FwFreeHyperVRulesBySchemaVersion
0x18000edc6  nop     dword ptr [rax+rax+00h]
0x18000edcb  jmp     short loc_18000EDE6
0x18000edcd  mov     rax, [rsp+1F0h+var_1B0]
0x18000edd2  mov     [rax+24h], r13d
0x18000edd6  mov     rax, [rsp+1F0h+var_1B0]
0x18000eddb  mov     [rax], rdi
0x18000edde  mov     rax, [rsp+1F0h+var_1B0]
0x18000ede3  mov     [rsi], rax
0x18000ede6  mov     eax, ebx
0x18000ede8  mov     rcx, [rbp+0F0h+var_48]
0x18000edef  xor     rcx, rsp; StackCookie
0x18000edf2  call    __security_check_cookie
0x18000edf7  add     rsp, 1B8h
0x18000edfe  pop     r15
0x18000ee00  pop     r14
0x18000ee02  pop     r13
0x18000ee04  pop     r12
0x18000ee06  pop     rdi
0x18000ee07  pop     rsi
0x18000ee08  pop     rbx
0x18000ee09  pop     rbp
0x18000ee0a  retn
```
