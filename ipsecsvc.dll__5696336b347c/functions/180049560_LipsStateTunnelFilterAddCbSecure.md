# LipsStateTunnelFilterAddCbSecure

- ea: `0x180049560`
- end: `0x180049894`
- name: `LipsStateTunnelFilterAddCbSecure`
- size: `820`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180049008`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x1800487ac`
- `0x180048de0`
- `0x180048e20`
- `0x180048f1c`
- `0x180049560`
- `0x180049dec`
- `0x18004c358`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180049656`
- `RPCRT4!UuidCreate` at `0x18004978f`
- `RPCRT4!UuidCreate` at `0x180049656`
- `RPCRT4!UuidCreate` at `0x18004978f`

## pseudocode

```c
__int64 __fastcall LipsStateTunnelFilterAddCbSecure(__int64 a1, __int64 a2)
{
  int v2; // esi
  __int64 v5; // rdx
  __int128 *v6; // rcx
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 *v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int128 *v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // eax
  FWP_CONDITION_VALUE0 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  FWPM_PROVIDER_CONTEXT0 v22; // [rsp+70h] [rbp-90h] BYREF
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v24[8]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v25; // [rsp+138h] [rbp+38h]

  v2 = *(_DWORD *)(a1 + 236);
  v21 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset_0(&Uuid, 0, sizeof(Uuid));
  memset_0(&v22, 0, sizeof(v22));
  memset_0(v24, 0, 0x48u);
  v5 = *(_QWORD *)(a1 + 280);
  v6 = *(__int128 **)(*(_QWORD *)(a1 + 272) + 56LL);
  v19 = *v6;
  v20 = v6[1];
  v21 = *((_QWORD *)v6 + 4);
  *((_QWORD *)&v19 + 1) = **(_QWORD **)(v5 + 40);
  LODWORD(v6) = *(_DWORD *)(*(_QWORD *)(v5 + 40) + 8LL);
  Uuid.displayData.name = *(wchar_t **)(a1 + 24);
  Uuid.displayData.description = L"Tunnel rule";
  DWORD1(v19) = (_DWORD)v6;
  Uuid.keyingPolicy = (IPSEC_KEYING_POLICY0 *)&v19;
  Uuid.type = FWPM_IPSEC_IKE_MM_CONTEXT;
  v7 = UuidCreate(&Uuid.providerContextKey);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = 27;
LABEL_5:
      WPP_SF_d(v8[2], v9, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v7);
    }
  }
  else
  {
    v10 = &v18;
    v11 = a1 + 40;
    if ( v2 == 8 )
      v10 = (__int128 *)&v17;
    if ( *(_DWORD *)(a1 + 44) )
      v12 = LipsBfeIpTunnelAddressV6Fill(v11, v10);
    else
      v12 = LipsBfeIpTunnelAddressV4Fill(v11, v10);
    v7 = v12;
    if ( v12 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v9 = 28;
        goto LABEL_5;
      }
    }
    else
    {
      v13 = (__int128 *)&v17;
      v14 = a1 + 80;
      if ( v2 == 8 )
        v13 = &v18;
      if ( *(_DWORD *)(a1 + 84) )
        v15 = LipsBfeIpTunnelAddressV6Fill(v14, v13);
      else
        v15 = LipsBfeIpTunnelAddressV4Fill(v14, v13);
      v7 = v15;
      if ( v15 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v9 = 29;
          goto LABEL_5;
        }
      }
      else
      {
        v7 = LipsTunnelPolicyCreate(a1, v24);
        if ( v7 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v9 = 30;
            goto LABEL_5;
          }
        }
        else
        {
          v7 = UuidCreate(&v22.providerContextKey);
          if ( v7 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v9 = 31;
              goto LABEL_5;
            }
          }
          else
          {
            v22.displayData.name = *(wchar_t **)(a1 + 24);
            v22.type = FWPM_IPSEC_IKE_QM_TUNNEL_CONTEXT;
            v22.keyingPolicy = (IPSEC_KEYING_POLICY0 *)v24;
            v7 = LipsBfeTunnelAdd(&Uuid, &v22, &v17, &v18);
            if ( v7 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v9 = 32;
                goto LABEL_5;
              }
            }
            else
            {
              *(GUID *)(*(_QWORD *)a2 + 4LL) = v22.providerContextKey;
              **(_DWORD **)a2 = 1;
            }
          }
        }
      }
    }
  }
  if ( v25 )
    LipsIpsecPolicyProposalsDestroy(&v22.keyingPolicy->keyModKeys, *(&v22.keyingPolicy->numKeyMods + 1));
  LipsBfeConditionDelete((__int64)&v17);
  LipsBfeConditionDelete((__int64)&v18);
  if ( v7 )
    return LipsReportError(v7, (int)"LipsStateTunnelFilterAddCbSecure");
  else
    return 0;
}

```

## disassembly

```asm
0x180049560  mov     [rsp-8+arg_10], rbx
0x180049565  mov     [rsp-8+arg_18], rsi
0x18004956a  push    rbp
0x18004956b  push    rdi
0x18004956c  push    r14
0x18004956e  lea     rbp, [rsp-90h]
0x180049576  sub     rsp, 190h
0x18004957d  mov     rax, cs:__security_cookie
0x180049584  xor     rax, rsp
0x180049587  mov     [rbp+0A0h+var_20], rax
0x18004958e  mov     esi, [rcx+0ECh]
0x180049594  xorps   xmm0, xmm0
0x180049597  xor     eax, eax
0x180049599  mov     r14, rdx
0x18004959c  mov     rdi, rcx
0x18004959f  mov     [rsp+1A0h+var_140], rax
0x1800495a4  xorps   xmm1, xmm1
0x1800495a7  lea     rcx, [rbp+0A0h+Uuid]; void *
0x1800495ab  xor     edx, edx; Val
0x1800495ad  lea     ebx, [rax+58h]
0x1800495b0  mov     r8d, ebx; Size
0x1800495b3  movups  [rsp+1A0h+var_180], xmm0
0x1800495b8  movups  [rsp+1A0h+var_170], xmm1
0x1800495bd  movups  [rsp+1A0h+var_160], xmm0
0x1800495c2  movups  [rsp+1A0h+var_150], xmm0
0x1800495c7  call    memset_0
0x1800495cc  mov     r8d, ebx; Size
0x1800495cf  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800495d4  xor     edx, edx; Val
0x1800495d6  call    memset_0
0x1800495db  xor     edx, edx; Val
0x1800495dd  lea     r8d, [rbx-10h]; Size
0x1800495e1  lea     rcx, [rbp+0A0h+var_70]; void *
0x1800495e5  call    memset_0
0x1800495ea  mov     rax, [rdi+110h]
0x1800495f1  mov     rdx, [rdi+118h]
0x1800495f8  mov     rcx, [rax+38h]
0x1800495fc  movups  xmm0, xmmword ptr [rcx]
0x1800495ff  movups  [rsp+1A0h+var_160], xmm0
0x180049604  movups  xmm1, xmmword ptr [rcx+10h]
0x180049608  movups  [rsp+1A0h+var_150], xmm1
0x18004960d  movsd   xmm0, qword ptr [rcx+20h]
0x180049612  movsd   [rsp+1A0h+var_140], xmm0
0x180049618  mov     rax, [rdx+28h]
0x18004961c  mov     rcx, [rax]
0x18004961f  mov     qword ptr [rsp+1A0h+var_160+8], rcx
0x180049624  mov     rax, [rdx+28h]
0x180049628  mov     ecx, [rax+8]
0x18004962b  mov     rax, [rdi+18h]
0x18004962f  mov     [rbp+0A0h+var_C0], rax
0x180049633  lea     rax, aTunnelRule; "Tunnel rule"
0x18004963a  mov     [rbp+0A0h+var_B8], rax
0x18004963e  lea     rax, [rsp+1A0h+var_160]
0x180049643  mov     dword ptr [rsp+1A0h+var_160+4], ecx
0x180049647  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x18004964b  mov     [rbp+0A0h+var_88], rax
0x18004964f  mov     [rbp+0A0h+var_90], 5
0x180049656  call    cs:__imp_UuidCreate
0x18004965c  mov     ebx, eax
0x18004965e  test    eax, eax
0x180049660  jz      short loc_1800496A0
0x180049662  mov     rcx, cs:WPP_GLOBAL_Control
0x180049669  lea     rax, WPP_GLOBAL_Control
0x180049670  cmp     rcx, rax
0x180049673  jz      loc_18004982C
0x180049679  test    byte ptr [rcx+1Ch], 10h
0x18004967d  jz      loc_18004982C
0x180049683  mov     edx, 1Bh
0x180049688  mov     rcx, [rcx+10h]
0x18004968c  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049693  mov     r9d, ebx
0x180049696  call    WPP_SF_d
0x18004969b  jmp     loc_18004982C
0x1800496a0  cmp     esi, 8
0x1800496a3  lea     rdx, [rsp+1A0h+var_170]
0x1800496a8  lea     rax, [rsp+1A0h+var_180]
0x1800496ad  lea     rcx, [rdi+28h]
0x1800496b1  cmovz   rdx, rax
0x1800496b5  cmp     dword ptr [rcx+4], 0
0x1800496b9  jnz     short loc_1800496C2
0x1800496bb  call    LipsBfeIpTunnelAddressV4Fill
0x1800496c0  jmp     short loc_1800496C7
0x1800496c2  call    LipsBfeIpTunnelAddressV6Fill
0x1800496c7  mov     ebx, eax
0x1800496c9  test    eax, eax
0x1800496cb  jz      short loc_1800496F5
0x1800496cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800496d4  lea     rax, WPP_GLOBAL_Control
0x1800496db  cmp     rcx, rax
0x1800496de  jz      loc_18004982C
0x1800496e4  test    byte ptr [rcx+1Ch], 10h
0x1800496e8  jz      loc_18004982C
0x1800496ee  mov     edx, 1Ch
0x1800496f3  jmp     short loc_180049688
0x1800496f5  cmp     esi, 8
0x1800496f8  lea     rdx, [rsp+1A0h+var_180]
0x1800496fd  lea     rax, [rsp+1A0h+var_170]
0x180049702  lea     rcx, [rdi+50h]
0x180049706  cmovz   rdx, rax
0x18004970a  cmp     dword ptr [rcx+4], 0
0x18004970e  jnz     short loc_180049717
0x180049710  call    LipsBfeIpTunnelAddressV4Fill
0x180049715  jmp     short loc_18004971C
0x180049717  call    LipsBfeIpTunnelAddressV6Fill
0x18004971c  mov     ebx, eax
0x18004971e  test    eax, eax
0x180049720  jz      short loc_18004974D
0x180049722  mov     rcx, cs:WPP_GLOBAL_Control
0x180049729  lea     rax, WPP_GLOBAL_Control
0x180049730  cmp     rcx, rax
0x180049733  jz      loc_18004982C
0x180049739  test    byte ptr [rcx+1Ch], 10h
0x18004973d  jz      loc_18004982C
0x180049743  mov     edx, 1Dh
0x180049748  jmp     loc_180049688
0x18004974d  lea     rdx, [rbp+0A0h+var_70]
0x180049751  mov     rcx, rdi
0x180049754  call    LipsTunnelPolicyCreate
0x180049759  mov     ebx, eax
0x18004975b  test    eax, eax
0x18004975d  jz      short loc_18004978A
0x18004975f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049766  lea     rax, WPP_GLOBAL_Control
0x18004976d  cmp     rcx, rax
0x180049770  jz      loc_18004982C
0x180049776  test    byte ptr [rcx+1Ch], 10h
0x18004977a  jz      loc_18004982C
0x180049780  mov     edx, 1Eh
0x180049785  jmp     loc_180049688
0x18004978a  lea     rcx, [rsp+1A0h+var_130]; Uuid
0x18004978f  call    cs:__imp_UuidCreate
0x180049795  mov     ebx, eax
0x180049797  test    eax, eax
0x180049799  jz      short loc_1800497BE
0x18004979b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497a2  lea     rax, WPP_GLOBAL_Control
0x1800497a9  cmp     rcx, rax
0x1800497ac  jz      short loc_18004982C
0x1800497ae  test    byte ptr [rcx+1Ch], 10h
0x1800497b2  jz      short loc_18004982C
0x1800497b4  mov     edx, 1Fh
0x1800497b9  jmp     loc_180049688
0x1800497be  mov     rax, [rdi+18h]
0x1800497c2  lea     r9, [rsp+1A0h+var_170]
0x1800497c7  mov     [rbp+0A0h+var_120], rax
0x1800497cb  lea     r8, [rsp+1A0h+var_180]
0x1800497d0  lea     rax, [rbp+0A0h+var_70]
0x1800497d4  mov     [rbp+0A0h+var_F0], 2
0x1800497db  lea     rdx, [rsp+1A0h+var_130]; tunnelPolicy
0x1800497e0  mov     [rbp+0A0h+var_E8], rax
0x1800497e4  lea     rcx, [rbp+0A0h+Uuid]; mainModePolicy
0x1800497e8  call    LipsBfeTunnelAdd
0x1800497ed  mov     ebx, eax
0x1800497ef  test    eax, eax
0x1800497f1  jz      short loc_180049816
0x1800497f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497fa  lea     rax, WPP_GLOBAL_Control
0x180049801  cmp     rcx, rax
0x180049804  jz      short loc_18004982C
0x180049806  test    byte ptr [rcx+1Ch], 10h
0x18004980a  jz      short loc_18004982C
0x18004980c  mov     edx, 20h ; ' '
0x180049811  jmp     loc_180049688
0x180049816  mov     rax, [r14]
0x180049819  movaps  xmm0, xmmword ptr [rsp+1A0h+var_130.Data1]
0x18004981e  movdqu  xmmword ptr [rax+4], xmm0
0x180049823  mov     rax, [r14]
0x180049826  mov     dword ptr [rax], 1
0x18004982c  cmp     [rbp+0A0h+var_68], 0
0x180049831  jz      short loc_180049843
0x180049833  mov     rdx, [rbp+0A0h+var_E8]
0x180049837  lea     rcx, [rdx+8]
0x18004983b  mov     edx, [rdx+4]
0x18004983e  call    LipsIpsecPolicyProposalsDestroy
0x180049843  lea     rcx, [rsp+1A0h+var_180]
0x180049848  call    LipsBfeConditionDelete
0x18004984d  lea     rcx, [rsp+1A0h+var_170]
0x180049852  call    LipsBfeConditionDelete
0x180049857  test    ebx, ebx
0x180049859  jnz     short loc_18004985F
0x18004985b  xor     eax, eax
0x18004985d  jmp     short loc_18004986D
0x18004985f  lea     rdx, aLipsstatetunne; "LipsStateTunnelFilterAddCbSecure"
0x180049866  mov     ecx, ebx
0x180049868  call    LipsReportError
0x18004986d  mov     rcx, [rbp+0A0h+var_20]
0x180049874  xor     rcx, rsp; StackCookie
0x180049877  call    __security_check_cookie
0x18004987c  lea     r11, [rsp+1A0h+var_10]
0x180049884  mov     rbx, [r11+30h]
0x180049888  mov     rsi, [r11+38h]
0x18004988c  mov     rsp, r11
0x18004988f  pop     r14
0x180049891  pop     rdi
0x180049892  pop     rbp
0x180049893  retn
```
