# FwQueryRulesInRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)

- ea: `0x18000b290`
- end: `0x18000b4a6`
- name: `?FwQueryRulesInRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int16, unsigned __int16 *, unsigned int *, struct _tag_FW_RULE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180007e30`
- `0x180009a50`

## callees

- `0x180005e0c`
- `0x18000a530`
- `0x18000b290`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000b345`
- `ntdll!EtwEventWrite` at `0x18000b3f2`
- `ntdll!EtwEventWrite` at `0x18000b345`
- `ntdll!EtwEventWrite` at `0x18000b3f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b36e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b36e`
- `fwbase!FwReportReturnError` at `0x18000b495`
- `fwbase!FwReportReturnError` at `0x18000b495`

## pseudocode

```c
__int64 __fastcall FwQueryRulesInRuleGroup(
        __int64 a1,
        int a2,
        __int16 a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _tag_FW_RULE **a6)
{
  unsigned int v8; // eax
  signed int v9; // ebx
  bool v10; // sf
  _DWORD v12[2]; // [rsp+60h] [rbp-69h] BYREF
  int *v13; // [rsp+68h] [rbp-61h]
  __int64 v14; // [rsp+70h] [rbp-59h]
  int v15; // [rsp+78h] [rbp-51h] BYREF
  __int64 *v16; // [rsp+80h] [rbp-49h]
  __int64 v17; // [rsp+90h] [rbp-39h] BYREF
  int v18; // [rsp+98h] [rbp-31h]
  int v19; // [rsp+A0h] [rbp-29h]
  __int64 v20; // [rsp+A8h] [rbp-21h]
  int v21; // [rsp+B0h] [rbp-19h]
  int v22; // [rsp+B8h] [rbp-11h]
  int v23; // [rsp+C0h] [rbp-9h]
  int v24; // [rsp+C4h] [rbp-5h]
  int v25; // [rsp+C8h] [rbp-1h]
  unsigned __int16 *v26; // [rsp+D0h] [rbp+7h]

  v16 = &v17;
  v15 = 3;
  v18 = 3;
  v21 = 3;
  v12[0] = 545;
  v12[1] = 1;
  v13 = &v15;
  v14 = 0x10000;
  v17 = 0;
  v19 = a2;
  v20 = 1;
  v22 = 196608;
  v23 = 8;
  v24 = 1;
  v25 = 5;
  v26 = a4;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v8 = Int_FWQueryObject(
         0,
         (unsigned int)FWVerifyFirewallRuleQuery,
         (unsigned int)RPC_FWQueryFirewallRules,
         (unsigned int)RRPC_FWQueryFirewallRules,
         (__int64)Int_RPC_FWEnumFirewallRules2_0,
         (__int64)Int_RRPC_FWEnumFirewallRules2_0,
         a1,
         (__int64)v12,
         a3,
         (__int64)a5,
         (__int64)a6,
         0);
  v9 = v8;
  if ( v8 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v8);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v10 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v10 = v9 < 0;
  }
  if ( v10 )
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b290  mov     [rsp-8+arg_8], rbx
0x18000b295  push    rbp
0x18000b296  push    rsi
0x18000b297  push    rdi
0x18000b298  push    r12
0x18000b29a  push    r14
0x18000b29c  lea     rbp, [rsp-27h]
0x18000b2a1  sub     rsp, 0F0h
0x18000b2a8  mov     rax, cs:__security_cookie
0x18000b2af  xor     rax, rsp
0x18000b2b2  mov     [rbp+47h+var_30], rax
0x18000b2b6  mov     rsi, [rbp+47h+arg_20]
0x18000b2ba  lea     rax, [rbp+47h+var_80]
0x18000b2be  mov     r14, [rbp+47h+arg_28]
0x18000b2c2  mov     rbx, rcx
0x18000b2c5  mov     ecx, 3
0x18000b2ca  mov     [rbp+47h+var_90], rax
0x18000b2ce  mov     [rbp+47h+var_98], ecx
0x18000b2d1  lea     rax, [rbp+47h+var_98]
0x18000b2d5  mov     [rbp+47h+var_78], ecx
0x18000b2d8  movzx   edi, r8w
0x18000b2dc  mov     [rbp+47h+var_60], ecx
0x18000b2df  mov     rcx, cs:g_Provider
0x18000b2e6  mov     [rbp+47h+var_B0], 221h
0x18000b2ed  mov     [rbp+47h+var_AC], 1
0x18000b2f4  mov     [rbp+47h+var_A8], rax
0x18000b2f8  mov     [rbp+47h+var_A0], 10000h
0x18000b300  mov     [rbp+47h+var_80], 0
0x18000b308  mov     [rbp+47h+var_70], edx
0x18000b30b  mov     [rbp+47h+var_68], 1
0x18000b313  mov     [rbp+47h+var_58], 30000h
0x18000b31a  mov     [rbp+47h+var_50], 8
0x18000b321  mov     [rbp+47h+var_4C], 1
0x18000b328  mov     [rbp+47h+var_48], 5
0x18000b32f  mov     [rbp+47h+var_40], r9
0x18000b333  test    rcx, rcx
0x18000b336  jz      short loc_18000B351
0x18000b338  xor     r9d, r9d
0x18000b33b  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000b342  xor     r8d, r8d
0x18000b345  call    cs:__imp_EtwEventWrite
0x18000b34c  nop     dword ptr [rax+rax+00h]
0x18000b351  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b358  lea     r12, WPP_GLOBAL_Control
0x18000b35f  cmp     rcx, r12
0x18000b362  jz      short loc_18000B36E
0x18000b364  test    byte ptr [rcx+1Ch], 8
0x18000b368  jnz     loc_18000B43B
0x18000b36e  call    cs:__imp_GetTickCount64
0x18000b375  nop     dword ptr [rax+rax+00h]
0x18000b37a  mov     [rsp+110h+var_B8], 0
0x18000b382  lea     rax, [rbp+47h+var_B0]
0x18000b386  mov     [rsp+110h+var_C0], r14
0x18000b38b  lea     r9, RRPC_FWQueryFirewallRules
0x18000b392  mov     [rsp+110h+var_C8], rsi
0x18000b397  lea     r8, RPC_FWQueryFirewallRules
0x18000b39e  mov     [rsp+110h+var_D0], di
0x18000b3a3  lea     rdx, FWVerifyFirewallRuleQuery
0x18000b3aa  mov     [rsp+110h+var_D8], rax
0x18000b3af  xor     ecx, ecx
0x18000b3b1  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b3b8  mov     [rsp+110h+var_E0], rbx
0x18000b3bd  mov     [rsp+110h+var_E8], rax
0x18000b3c2  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b3c9  mov     [rsp+110h+var_F0], rax
0x18000b3ce  call    Int_FWQueryObject
0x18000b3d3  mov     ebx, eax
0x18000b3d5  test    eax, eax
0x18000b3d7  jnz     short loc_18000B455
0x18000b3d9  mov     rcx, cs:g_Provider
0x18000b3e0  test    rcx, rcx
0x18000b3e3  jz      short loc_18000B3FE
0x18000b3e5  xor     r9d, r9d
0x18000b3e8  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000b3ef  xor     r8d, r8d
0x18000b3f2  call    cs:__imp_EtwEventWrite
0x18000b3f9  nop     dword ptr [rax+rax+00h]
0x18000b3fe  test    ebx, ebx
0x18000b400  jg      short loc_18000B42E
0x18000b402  js      loc_18000B48C
0x18000b408  mov     eax, ebx
0x18000b40a  mov     rcx, [rbp+47h+var_30]
0x18000b40e  xor     rcx, rsp; StackCookie
0x18000b411  call    __security_check_cookie
0x18000b416  mov     rbx, [rsp+110h+arg_8]
0x18000b41e  add     rsp, 0F0h
0x18000b425  pop     r14
0x18000b427  pop     r12
0x18000b429  pop     rdi
0x18000b42a  pop     rsi
0x18000b42b  pop     rbp
0x18000b42c  retn
0x18000b42e  movzx   ebx, bx
0x18000b431  or      ebx, 80070000h
0x18000b437  test    ebx, ebx
0x18000b439  jmp     short loc_18000B402
0x18000b43b  mov     rcx, [rcx+10h]
0x18000b43f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b446  mov     edx, 0B6h
0x18000b44b  call    WPP_SF_
0x18000b450  jmp     loc_18000B36E
0x18000b455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b45c  cmp     rcx, r12
0x18000b45f  jz      loc_18000B3D9
0x18000b465  test    byte ptr [rcx+1Ch], 1
0x18000b469  jz      loc_18000B3D9
0x18000b46f  mov     rcx, [rcx+10h]
0x18000b473  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b47a  mov     edx, 0B7h
0x18000b47f  mov     r9d, ebx
0x18000b482  call    WPP_SF_d
0x18000b487  jmp     loc_18000B3D9
0x18000b48c  mov     edx, ebx
0x18000b48e  lea     rcx, aFwqueryrulesin; "FwQueryRulesInRuleGroup"
0x18000b495  call    cs:__imp_FwReportReturnError
0x18000b49c  nop     dword ptr [rax+rax+00h]
0x18000b4a1  jmp     loc_18000B408
```
