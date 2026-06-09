# FwEnumRulesFromRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)

- ea: `0x180009a50`
- end: `0x180009ebe`
- name: `?FwEnumRulesFromRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `1134`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, unsigned int *, struct _tag_FW_RULE **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180015fb0`

## callees

- `0x180005e0c`
- `0x180006e14`
- `0x180009780`
- `0x180009a50`
- `0x18000a530`
- `0x18000b290`
- `0x18000c3f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180009ab8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180009ab8`
- `ntdll!EtwEventWrite` at `0x180009b51`
- `ntdll!EtwEventWrite` at `0x180009c09`
- `ntdll!EtwEventWrite` at `0x180009b51`
- `ntdll!EtwEventWrite` at `0x180009c09`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009b7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009b7a`
- `fwbase!FwBaseFree` at `0x180009c50`
- `fwbase!FwBaseFree` at `0x180009d93`
- `fwbase!FwBaseFree` at `0x180009e92`
- `fwbase!FwBaseFree` at `0x180009c50`
- `fwbase!FwBaseFree` at `0x180009d93`
- `fwbase!FwBaseFree` at `0x180009e92`
- `fwbase!FwLoadIndirectString` at `0x180009cd4`
- `fwbase!FwLoadIndirectString` at `0x180009cd4`
- `fwbase!FwReportReturnError` at `0x180009d6e`
- `fwbase!FwReportReturnError` at `0x180009da8`
- `fwbase!FwReportReturnError` at `0x180009e21`
- `fwbase!FwReportReturnError` at `0x180009e6d`
- `fwbase!FwReportReturnError` at `0x180009d6e`
- `fwbase!FwReportReturnError` at `0x180009da8`
- `fwbase!FwReportReturnError` at `0x180009e21`
- `fwbase!FwReportReturnError` at `0x180009e6d`
- `fwbase!FwStringCopy` at `0x180009e3c`
- `fwbase!FwStringCopy` at `0x180009e58`
- `fwbase!FwStringCopy` at `0x180009e3c`
- `fwbase!FwStringCopy` at `0x180009e58`

## string_xrefs

- `0x180009aa5`: `@FirewallAPI.dll,-`

## pseudocode

```c
__int64 __fastcall FwEnumRulesFromRuleGroup(
        void *a1,
        unsigned int a2,
        unsigned __int16 a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _tag_FW_RULE **a6)
{
  unsigned int v10; // eax
  signed int v11; // ebx
  bool v12; // sf
  int v14; // eax
  int v15; // eax
  struct _tag_FW_RULE *v16; // rdi
  struct _tag_FW_RULE **v17; // rsi
  __int64 v18; // rdx
  unsigned int v19; // eax
  struct _tag_FW_RULE *v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-98h] BYREF
  struct _tag_FW_RULE *v22; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v23[2]; // [rsp+78h] [rbp-88h] BYREF
  int *v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  unsigned int v26; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+94h] [rbp-6Ch] BYREF
  int v28; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+B0h] [rbp-50h] BYREF
  int v31; // [rsp+B8h] [rbp-48h]
  unsigned int v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+E4h] [rbp-1Ch]
  int v38; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v39; // [rsp+F0h] [rbp-10h]

  v21 = 0;
  v22 = 0;
  v20 = 0;
  v27 = 0;
  v26 = 0;
  if ( !(unsigned int)_o__wcsnicmp(a4, L"@FirewallAPI.dll,-", 18) )
  {
    v29 = &v30;
    v24 = &v28;
    v28 = 3;
    v23[0] = 545;
    v23[1] = 1;
    v25 = 0x10000;
    v30 = 0;
    v31 = 3;
    v32 = a2;
    v33 = 1;
    v34 = 3;
    v35 = 196608;
    v36 = 8;
    v37 = 1;
    v38 = 5;
    v39 = a4;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v10 = Int_FWQueryObject(
            0,
            (unsigned int)FWVerifyFirewallRuleQuery,
            (unsigned int)RPC_FWQueryFirewallRules,
            (unsigned int)RRPC_FWQueryFirewallRules,
            (__int64)Int_RPC_FWEnumFirewallRules2_0,
            (__int64)Int_RRPC_FWEnumFirewallRules2_0,
            (__int64)a1,
            (__int64)v23,
            a3,
            (__int64)&v26,
            (__int64)&v20,
            0);
    v11 = v10;
    if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
    v12 = v11 < 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v12 = v11 < 0;
    }
    if ( !v12 )
      goto LABEL_13;
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v11);
    goto LABEL_33;
  }
  v14 = FwQueryRulesInRuleGroup(a1, a2, a3, a4, &v26, &v20);
  v11 = v14;
  if ( v14 < 0 )
  {
    v18 = (unsigned int)v14;
LABEL_27:
    FwReportReturnError("FwEnumRulesFromRuleGroup", v18);
    FWFreeFirewallRules(v22);
    FWFreeFirewallRules(v20);
    FwBaseFree(v21);
    return FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v11);
  }
  if ( v26 )
    goto LABEL_13;
  if ( (int)FwLoadIndirectString(a4, &v21) < 0 && (int)FwStringCopy(a4, &v21) < 0 )
  {
    v19 = FwStringCopy(a4, &v21);
    FwReportReturnError("FwEnumRulesFromRuleGroup", v19);
    FWFreeFirewallRules(v22);
    FWFreeFirewallRules(v20);
    FwBaseFree(v21);
    return (unsigned int)v11;
  }
  v15 = FWEnumFirewallRules((_DWORD)a1, 196608, a2, a3, (__int64)&v27, (__int64)&v22);
  v11 = v15;
  if ( v15 > 0 )
    v11 = (unsigned __int16)v15 | 0x80070000;
  if ( v11 < 0 )
  {
LABEL_33:
    v18 = (unsigned int)v11;
    goto LABEL_27;
  }
  v16 = v22;
  v17 = &v22;
  if ( v22 )
  {
    do
    {
      if ( FwRuleInGroup(v16, v21) )
      {
        *v17 = *(struct _tag_FW_RULE **)v16;
        *(_QWORD *)v16 = v20;
        ++v26;
        v20 = v16;
      }
      else
      {
        v17 = (struct _tag_FW_RULE **)v16;
      }
      v16 = *v17;
    }
    while ( *v17 );
  }
LABEL_13:
  *a6 = v20;
  *a5 = v26;
  v26 = 0;
  v20 = 0;
  FWFreeFirewallRules(v22);
  FWFreeFirewallRules(v20);
  FwBaseFree(v21);
  if ( v11 >= 0 )
    return (unsigned int)v11;
  return FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v11);
}

```

## disassembly

```asm
0x180009a50  push    rbp
0x180009a52  push    rbx
0x180009a53  push    rsi
0x180009a54  push    rdi
0x180009a55  push    r12
0x180009a57  push    r13
0x180009a59  push    r14
0x180009a5b  push    r15
0x180009a5d  lea     rbp, [rsp-18h]
0x180009a62  sub     rsp, 118h
0x180009a69  mov     rax, cs:__security_cookie
0x180009a70  xor     rax, rsp
0x180009a73  mov     [rbp+50h+var_50], rax
0x180009a77  mov     r14, [rbp+50h+arg_20]
0x180009a7e  xor     ebx, ebx
0x180009a80  mov     r15, [rbp+50h+arg_28]
0x180009a87  movzx   r13d, r8w
0x180009a8b  mov     esi, edx
0x180009a8d  mov     [rsp+150h+var_E8], rbx
0x180009a92  mov     r12, rcx
0x180009a95  mov     [rsp+150h+var_E0], rbx
0x180009a9a  mov     r8d, 12h
0x180009aa0  mov     [rsp+150h+var_F0], rbx
0x180009aa5  lea     rdx, aFirewallapiDll_14; "@FirewallAPI.dll,-"
0x180009aac  mov     [rbp+50h+var_BC], ebx
0x180009aaf  mov     rcx, r9
0x180009ab2  mov     [rbp+50h+var_C0], ebx
0x180009ab5  mov     rdi, r9
0x180009ab8  call    cs:__imp__o__wcsnicmp
0x180009abf  nop     dword ptr [rax+rax+00h]
0x180009ac4  test    eax, eax
0x180009ac6  jnz     loc_180009C94
0x180009acc  mov     rcx, cs:g_Provider
0x180009ad3  lea     rax, [rbp+50h+var_A0]
0x180009ad7  mov     [rbp+50h+var_B0], rax
0x180009adb  lea     rax, [rbp+50h+var_B8]
0x180009adf  mov     [rbp+50h+var_D0], rax
0x180009ae3  mov     [rbp+50h+var_B8], 3
0x180009aea  mov     [rsp+150h+var_D8], 221h
0x180009af2  mov     [rsp+150h+var_D4], 1
0x180009afa  mov     [rbp+50h+var_C8], 10000h
0x180009b02  mov     [rbp+50h+var_A0], rbx
0x180009b06  mov     [rbp+50h+var_98], 3
0x180009b0d  mov     [rbp+50h+var_90], esi
0x180009b10  mov     [rbp+50h+var_88], 1
0x180009b18  mov     [rbp+50h+var_80], 3
0x180009b1f  mov     [rbp+50h+var_78], 30000h
0x180009b26  mov     [rbp+50h+var_70], 8
0x180009b2d  mov     [rbp+50h+var_6C], 1
0x180009b34  mov     [rbp+50h+var_68], 5
0x180009b3b  mov     [rbp+50h+var_60], rdi
0x180009b3f  test    rcx, rcx
0x180009b42  jz      short loc_180009B5D
0x180009b44  xor     r9d, r9d
0x180009b47  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180009b4e  xor     r8d, r8d
0x180009b51  call    cs:__imp_EtwEventWrite
0x180009b58  nop     dword ptr [rax+rax+00h]
0x180009b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b64  lea     rdi, WPP_GLOBAL_Control
0x180009b6b  cmp     rcx, rdi
0x180009b6e  jz      short loc_180009B7A
0x180009b70  test    byte ptr [rcx+1Ch], 8
0x180009b74  jnz     loc_180009DC7
0x180009b7a  call    cs:__imp_GetTickCount64
0x180009b81  nop     dword ptr [rax+rax+00h]
0x180009b86  mov     [rsp+150h+var_F8], ebx
0x180009b8a  lea     rax, [rsp+150h+var_F0]
0x180009b8f  mov     [rsp+150h+var_100], rax
0x180009b94  lea     r9, RRPC_FWQueryFirewallRules
0x180009b9b  lea     rax, [rbp+50h+var_C0]
0x180009b9f  xor     ecx, ecx
0x180009ba1  mov     [rsp+150h+var_108], rax
0x180009ba6  lea     r8, RPC_FWQueryFirewallRules
0x180009bad  mov     [rsp+150h+var_110], r13w
0x180009bb3  lea     rax, [rsp+150h+var_D8]
0x180009bb8  mov     [rsp+150h+var_118], rax
0x180009bbd  lea     rdx, FWVerifyFirewallRuleQuery
0x180009bc4  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009bcb  mov     [rsp+150h+var_120], r12
0x180009bd0  mov     [rsp+150h+var_128], rax
0x180009bd5  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009bdc  mov     [rsp+150h+var_130], rax
0x180009be1  call    Int_FWQueryObject
0x180009be6  mov     ebx, eax
0x180009be8  test    eax, eax
0x180009bea  jnz     loc_180009DE1
0x180009bf0  mov     rcx, cs:g_Provider
0x180009bf7  test    rcx, rcx
0x180009bfa  jz      short loc_180009C15
0x180009bfc  xor     r9d, r9d
0x180009bff  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x180009c06  xor     r8d, r8d
0x180009c09  call    cs:__imp_EtwEventWrite
0x180009c10  nop     dword ptr [rax+rax+00h]
0x180009c15  test    ebx, ebx
0x180009c17  jg      short loc_180009C87
0x180009c19  js      loc_180009E18
0x180009c1f  mov     rax, [rsp+150h+var_F0]
0x180009c24  xor     ecx, ecx
0x180009c26  mov     [r15], rax
0x180009c29  mov     eax, [rbp+50h+var_C0]
0x180009c2c  mov     [r14], eax
0x180009c2f  mov     [rbp+50h+var_C0], ecx
0x180009c32  mov     [rsp+150h+var_F0], rcx
0x180009c37  mov     rcx, [rsp+150h+var_E0]
0x180009c3c  call    FWFreeFirewallRules
0x180009c41  mov     rcx, [rsp+150h+var_F0]
0x180009c46  call    FWFreeFirewallRules
0x180009c4b  mov     rcx, [rsp+150h+var_E8]
0x180009c50  call    cs:__imp_FwBaseFree
0x180009c57  nop     dword ptr [rax+rax+00h]
0x180009c5c  test    ebx, ebx
0x180009c5e  js      loc_180009D9F
0x180009c64  mov     eax, ebx
0x180009c66  mov     rcx, [rbp+50h+var_50]
0x180009c6a  xor     rcx, rsp; StackCookie
0x180009c6d  call    __security_check_cookie
0x180009c72  add     rsp, 118h
0x180009c79  pop     r15
0x180009c7b  pop     r14
0x180009c7d  pop     r13
0x180009c7f  pop     r12
0x180009c81  pop     rdi
0x180009c82  pop     rsi
0x180009c83  pop     rbx
0x180009c84  pop     rbp
0x180009c85  retn
0x180009c87  movzx   ebx, bx
0x180009c8a  or      ebx, 80070000h
0x180009c90  test    ebx, ebx
0x180009c92  jmp     short loc_180009C19
0x180009c94  lea     rax, [rsp+150h+var_F0]
0x180009c99  mov     r9, rdi; unsigned __int16 *
0x180009c9c  mov     [rsp+150h+var_128], rax; struct _tag_FW_RULE **
0x180009ca1  movzx   r8d, r13w; unsigned __int16
0x180009ca5  lea     rax, [rbp+50h+var_C0]
0x180009ca9  mov     edx, esi; unsigned int
0x180009cab  mov     rcx, r12; void *
0x180009cae  mov     [rsp+150h+var_130], rax; unsigned int *
0x180009cb3  call    ?FwQueryRulesInRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z; FwQueryRulesInRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)
0x180009cb8  mov     ebx, eax
0x180009cba  test    eax, eax
0x180009cbc  js      loc_180009D65
0x180009cc2  cmp     [rbp+50h+var_C0], 0
0x180009cc6  jnz     loc_180009C1F
0x180009ccc  lea     rdx, [rsp+150h+var_E8]
0x180009cd1  mov     rcx, rdi
0x180009cd4  call    cs:__imp_FwLoadIndirectString
0x180009cdb  nop     dword ptr [rax+rax+00h]
0x180009ce0  test    eax, eax
0x180009ce2  js      loc_180009E34
0x180009ce8  lea     rax, [rsp+150h+var_E0]
0x180009ced  movzx   r9d, r13w
0x180009cf1  mov     [rsp+150h+var_128], rax
0x180009cf6  mov     r8d, esi
0x180009cf9  lea     rax, [rbp+50h+var_BC]
0x180009cfd  mov     edx, 30000h
0x180009d02  mov     rcx, r12
0x180009d05  mov     [rsp+150h+var_130], rax
0x180009d0a  call    FWEnumFirewallRules
0x180009d0f  mov     ebx, eax
0x180009d11  test    eax, eax
0x180009d13  jg      loc_180009DB9
0x180009d19  test    ebx, ebx
0x180009d1b  js      loc_180009E2D
0x180009d21  mov     rdi, [rsp+150h+var_E0]
0x180009d26  lea     rsi, [rsp+150h+var_E0]
0x180009d2b  test    rdi, rdi
0x180009d2e  jz      loc_180009C1F
0x180009d34  nop     dword ptr [rax+00h]
0x180009d38  nop     dword ptr [rax+rax+00000000h]
0x180009d40  mov     rdx, [rsp+150h+var_E8]; unsigned __int16 *
0x180009d45  mov     rcx, rdi; struct _tag_FW_RULE *
0x180009d48  call    ?FwRuleInGroup@@YAHPEBU_tag_FW_RULE@@PEBG@Z; FwRuleInGroup(_tag_FW_RULE const *,ushort const *)
0x180009d4d  test    eax, eax
0x180009d4f  jnz     loc_180009EA3
0x180009d55  mov     rsi, rdi
0x180009d58  mov     rdi, [rsi]
0x180009d5b  test    rdi, rdi
0x180009d5e  jnz     short loc_180009D40
0x180009d60  jmp     loc_180009C1F
0x180009d65  mov     edx, eax
0x180009d67  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x180009d6e  call    cs:__imp_FwReportReturnError
0x180009d75  nop     dword ptr [rax+rax+00h]
0x180009d7a  mov     rcx, [rsp+150h+var_E0]
0x180009d7f  call    FWFreeFirewallRules
0x180009d84  mov     rcx, [rsp+150h+var_F0]
0x180009d89  call    FWFreeFirewallRules
0x180009d8e  mov     rcx, [rsp+150h+var_E8]
0x180009d93  call    cs:__imp_FwBaseFree
0x180009d9a  nop     dword ptr [rax+rax+00h]
0x180009d9f  mov     edx, ebx
0x180009da1  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x180009da8  call    cs:__imp_FwReportReturnError
0x180009daf  nop     dword ptr [rax+rax+00h]
0x180009db4  jmp     loc_180009C66
0x180009db9  movzx   ebx, ax
0x180009dbc  or      ebx, 80070000h
0x180009dc2  jmp     loc_180009D19
0x180009dc7  mov     rcx, [rcx+10h]
0x180009dcb  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180009dd2  mov     edx, 0B6h
0x180009dd7  call    WPP_SF_
0x180009ddc  jmp     loc_180009B7A
0x180009de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009de8  cmp     rcx, rdi
0x180009deb  jz      loc_180009BF0
0x180009df1  test    byte ptr [rcx+1Ch], 1
0x180009df5  jz      loc_180009BF0
0x180009dfb  mov     rcx, [rcx+10h]
0x180009dff  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180009e06  mov     edx, 0B7h
0x180009e0b  mov     r9d, ebx
0x180009e0e  call    WPP_SF_d
0x180009e13  jmp     loc_180009BF0
0x180009e18  mov     edx, ebx
0x180009e1a  lea     rcx, aFwqueryrulesin; "FwQueryRulesInRuleGroup"
0x180009e21  call    cs:__imp_FwReportReturnError
0x180009e28  nop     dword ptr [rax+rax+00h]
0x180009e2d  mov     edx, ebx
0x180009e2f  jmp     loc_180009D67
0x180009e34  lea     rdx, [rsp+150h+var_E8]
0x180009e39  mov     rcx, rdi
0x180009e3c  call    cs:__imp_FwStringCopy
0x180009e43  nop     dword ptr [rax+rax+00h]
0x180009e48  test    eax, eax
0x180009e4a  jns     loc_180009CE8
0x180009e50  lea     rdx, [rsp+150h+var_E8]
0x180009e55  mov     rcx, rdi
0x180009e58  call    cs:__imp_FwStringCopy
0x180009e5f  nop     dword ptr [rax+rax+00h]
0x180009e64  mov     edx, eax
0x180009e66  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x180009e6d  call    cs:__imp_FwReportReturnError
0x180009e74  nop     dword ptr [rax+rax+00h]
0x180009e79  mov     rcx, [rsp+150h+var_E0]
0x180009e7e  call    FWFreeFirewallRules
0x180009e83  mov     rcx, [rsp+150h+var_F0]
0x180009e88  call    FWFreeFirewallRules
0x180009e8d  mov     rcx, [rsp+150h+var_E8]
0x180009e92  call    cs:__imp_FwBaseFree
0x180009e99  nop     dword ptr [rax+rax+00h]
0x180009e9e  jmp     loc_180009C64
0x180009ea3  mov     rax, [rdi]
0x180009ea6  mov     [rsi], rax
0x180009ea9  mov     rax, [rsp+150h+var_F0]
0x180009eae  mov     [rdi], rax
0x180009eb1  inc     [rbp+50h+var_C0]
0x180009eb4  mov     [rsp+150h+var_F0], rdi
0x180009eb9  jmp     loc_180009D58
```
