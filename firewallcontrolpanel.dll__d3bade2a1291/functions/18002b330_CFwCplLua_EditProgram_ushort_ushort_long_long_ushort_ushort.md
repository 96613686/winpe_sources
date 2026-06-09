# CFwCplLua::EditProgram(ushort *,ushort *,long,long,ushort * *,ushort * *)

- ea: `0x18002b330`
- end: `0x18002b8b1`
- name: `?EditProgram@CFwCplLua@@UEAAJPEAG0JJPEAPEAG1@Z`
- size: `1409`
- prototype: `__int64 __fastcall(void **this, LPCWSTR lpString2, LPCWSTR, int, int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009924`
- `0x18000994c`
- `0x18002b330`
- `0x18002c2a0`
- `0x18002c2e0`
- `0x18002c3d8`
- `0x180030ea0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b6d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b820`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b6d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b820`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b864`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b872`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b864`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b872`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b5a2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b6e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b5a2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b6e6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b5e7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b72b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b5e7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b72b`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002b882`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002b882`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b4ee`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b552`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b4ee`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b552`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b68f`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b7e3`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b68f`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b7e3`
- `FirewallAPI!FwFree` at `0x18002b62c`
- `FirewallAPI!FwFree` at `0x18002b780`
- `FirewallAPI!FwFree` at `0x18002b62c`
- `FirewallAPI!FwFree` at `0x18002b780`
- `fwbase!FwStringCopy` at `0x18002b640`
- `fwbase!FwStringCopy` at `0x18002b794`
- `fwbase!FwStringCopy` at `0x18002b640`
- `fwbase!FwStringCopy` at `0x18002b794`

## pseudocode

```c
__int64 __fastcall CFwCplLua::EditProgram(
        void **this,
        LPCWSTR lpString2,
        LPCWSTR a3,
        int a4,
        int a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  CFwCplLua *v11; // rcx
  int FwRules; // eax
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  struct _tag_FW_RULE *v16; // r15
  struct _tag_FW_RULE *v17; // rdx
  int v18; // eax
  struct _tag_FW_RULE *v19; // r14
  struct _tag_FW_RULE *v20; // rdx
  int v21; // eax
  int v22; // eax
  BSTR *v23; // rdi
  CFwCplLua *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  BSTR v28; // rax
  struct _tag_FW_RULE *v30; // [rsp+28h] [rbp-89h] BYREF
  struct _tag_FW_RULE *v31; // [rsp+30h] [rbp-81h] BYREF
  struct _tag_FW_RULE *v32; // [rsp+38h] [rbp-79h] BYREF
  unsigned __int16 **v33; // [rsp+40h] [rbp-71h]
  GUID pguid; // [rsp+48h] [rbp-69h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-51h] BYREF

  v33 = a7;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  pguid = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !lpString2 || !a3 )
  {
    v13 = -2147024809;
    if ( v11 == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 101;
    v15 = 2147942487LL;
    goto LABEL_81;
  }
  FwRules = CFwCplLua::EnsurePolicyHandle((CFwCplLua *)this);
  v13 = FwRules;
  if ( FwRules < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 102;
    goto LABEL_10;
  }
  FwRules = GetFwRules(this[8], &v30);
  v13 = FwRules;
  if ( FwRules < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 103;
    goto LABEL_10;
  }
  FwRules = GetRuleByIDWithScopedProfiles(lpString2, v30, &v31);
  v13 = FwRules;
  if ( FwRules < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 104;
    goto LABEL_10;
  }
  FwRules = GetRuleByIDWithScopedProfiles(a3, v30, &v32);
  v13 = FwRules;
  if ( FwRules < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 105;
LABEL_10:
    v15 = (unsigned int)FwRules;
LABEL_81:
    WPP_SF_d(*((_QWORD *)v11 + 2), v14, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, v15);
LABEL_82:
    v23 = a6;
    goto LABEL_83;
  }
  if ( !a4 && !a5 )
    goto LABEL_87;
  v16 = v31;
  v17 = v31;
  *((_DWORD *)v31 + 10) = ~a5 & (*((_DWORD *)v31 + 10) | a4);
  v18 = FWSetFirewallRule(this[8], v17);
  v13 = v18;
  if ( v18 > 0 )
    v13 = (unsigned __int16)v18 | 0x80070000;
  if ( v13 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 106;
    goto LABEL_31;
  }
  v19 = v32;
  v20 = v32;
  *((_DWORD *)v32 + 10) = ~a5 & (*((_DWORD *)v32 + 10) | a4);
  v21 = FWSetFirewallRule(this[8], v20);
  v13 = v21;
  if ( v21 > 0 )
    v13 = (unsigned __int16)v21 | 0x80070000;
  if ( v13 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 107;
    goto LABEL_31;
  }
  if ( !a5 )
    goto LABEL_87;
  v13 = CoCreateGuid(&pguid);
  if ( v13 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 108;
    goto LABEL_31;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v15 = 2147942522LL;
    v13 = -2147024774;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 109;
    goto LABEL_81;
  }
  FwFree(*((_QWORD *)v16 + 2));
  *((_QWORD *)v16 + 2) = 0;
  v13 = FwStringCopy(sz, (char *)v16 + 16);
  if ( v13 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 110;
    goto LABEL_31;
  }
  *((_DWORD *)v16 + 10) = a5;
  *((_WORD *)v16 + 146) &= ~1u;
  v22 = FWAddFirewallRule(this[8], v16);
  v13 = v22;
  if ( v22 > 0 )
    v13 = (unsigned __int16)v22 | 0x80070000;
  if ( v13 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v14 = 111;
LABEL_31:
    v15 = (unsigned int)v13;
    goto LABEL_81;
  }
  v23 = a6;
  *a6 = SysAllocString(sz);
  v13 = CoCreateGuid(&pguid);
  if ( v13 >= 0 )
  {
    if ( !StringFromGUID2(&pguid, sz, 40) )
    {
      v26 = 2147942522LL;
      v13 = -2147024774;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_83;
      v25 = 113;
      goto LABEL_66;
    }
    FwFree(*((_QWORD *)v19 + 2));
    *((_QWORD *)v19 + 2) = 0;
    v13 = FwStringCopy(sz, (char *)v19 + 16);
    if ( v13 >= 0 )
    {
      *((_DWORD *)v19 + 10) = a5;
      *((_WORD *)v19 + 146) &= ~1u;
      v27 = FWAddFirewallRule(this[8], v19);
      v13 = v27;
      if ( v27 > 0 )
        v13 = (unsigned __int16)v27 | 0x80070000;
      if ( v13 >= 0 )
      {
        v28 = SysAllocString(sz);
        *v33 = v28;
        goto LABEL_87;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_83;
      v25 = 115;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_83;
      v25 = 114;
    }
  }
  else
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_83;
    v25 = 112;
  }
  v26 = (unsigned int)v13;
LABEL_66:
  WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, v26);
LABEL_83:
  if ( *v33 )
    SysFreeString(*v33);
  if ( *v23 )
    SysFreeString(*v23);
LABEL_87:
  if ( v30 )
    FWFreeFirewallRules(v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002b330  mov     [rsp-8+arg_18], rbx
0x18002b335  push    rbp
0x18002b336  push    rsi
0x18002b337  push    rdi
0x18002b338  push    r12
0x18002b33a  push    r13
0x18002b33c  push    r14
0x18002b33e  push    r15
0x18002b340  lea     rbp, [rsp-0Fh]
0x18002b345  sub     rsp, 0C0h
0x18002b34c  mov     rax, cs:__security_cookie
0x18002b353  xor     rax, rsp
0x18002b356  mov     [rbp+3Fh+var_40], rax
0x18002b35a  mov     rax, [rbp+3Fh+arg_28]
0x18002b35e  xorps   xmm0, xmm0
0x18002b361  mov     [rsp+0F0h+var_D0], rax
0x18002b366  mov     edi, r9d
0x18002b369  mov     rax, [rbp+3Fh+arg_30]
0x18002b36d  mov     r14, r8
0x18002b370  mov     [rbp+3Fh+var_B0], rax
0x18002b374  mov     rsi, rdx
0x18002b377  mov     r13, rcx
0x18002b37a  mov     [rsp+0F0h+var_C8], 0
0x18002b383  mov     [rsp+0F0h+var_C0], 0
0x18002b38c  mov     [rbp+3Fh+var_B8], 0
0x18002b394  movups  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x18002b398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b39f  lea     r15, WPP_GLOBAL_Control
0x18002b3a6  lea     r12, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002b3ad  cmp     rcx, r15
0x18002b3b0  jz      short loc_18002B3D0
0x18002b3b2  test    byte ptr [rcx+1Ch], 8
0x18002b3b6  jz      short loc_18002B3D0
0x18002b3b8  mov     rcx, [rcx+10h]
0x18002b3bc  mov     edx, 64h ; 'd'
0x18002b3c1  mov     r8, r12
0x18002b3c4  call    WPP_SF_
0x18002b3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3d0  test    rsi, rsi
0x18002b3d3  jz      loc_18002B82F
0x18002b3d9  test    r14, r14
0x18002b3dc  jz      loc_18002B82F
0x18002b3e2  mov     rcx, r13; this
0x18002b3e5  call    ?EnsurePolicyHandle@CFwCplLua@@AEAAJXZ; CFwCplLua::EnsurePolicyHandle(void)
0x18002b3ea  mov     ebx, eax
0x18002b3ec  test    eax, eax
0x18002b3ee  jns     short loc_18002B417
0x18002b3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3f7  cmp     rcx, r15
0x18002b3fa  jz      loc_18002B853
0x18002b400  test    byte ptr [rcx+1Ch], 1
0x18002b404  jz      loc_18002B853
0x18002b40a  mov     edx, 66h ; 'f'
0x18002b40f  mov     r9d, eax
0x18002b412  jmp     loc_18002B847
0x18002b417  mov     rcx, [r13+40h]; void *
0x18002b41b  lea     rdx, [rsp+0F0h+var_C8]; struct _tag_FW_RULE **
0x18002b420  call    ?GetFwRules@@YAJPEAXPEAPEAU_tag_FW_RULE@@@Z; GetFwRules(void *,_tag_FW_RULE * *)
0x18002b425  mov     ebx, eax
0x18002b427  test    eax, eax
0x18002b429  jns     short loc_18002B44C
0x18002b42b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b432  cmp     rcx, r15
0x18002b435  jz      loc_18002B853
0x18002b43b  test    byte ptr [rcx+1Ch], 1
0x18002b43f  jz      loc_18002B853
0x18002b445  mov     edx, 67h ; 'g'
0x18002b44a  jmp     short loc_18002B40F
0x18002b44c  mov     rdx, [rsp+0F0h+var_C8]; struct _tag_FW_RULE *
0x18002b451  lea     r8, [rsp+0F0h+var_C0]; struct _tag_FW_RULE **
0x18002b456  mov     rcx, rsi; lpString2
0x18002b459  call    ?GetRuleByIDWithScopedProfiles@@YAJPEAGPEAU_tag_FW_RULE@@PEAPEAU1@@Z; GetRuleByIDWithScopedProfiles(ushort *,_tag_FW_RULE *,_tag_FW_RULE * *)
0x18002b45e  mov     ebx, eax
0x18002b460  test    eax, eax
0x18002b462  jns     short loc_18002B485
0x18002b464  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b46b  cmp     rcx, r15
0x18002b46e  jz      loc_18002B853
0x18002b474  test    byte ptr [rcx+1Ch], 1
0x18002b478  jz      loc_18002B853
0x18002b47e  mov     edx, 68h ; 'h'
0x18002b483  jmp     short loc_18002B40F
0x18002b485  mov     rdx, [rsp+0F0h+var_C8]; struct _tag_FW_RULE *
0x18002b48a  lea     r8, [rbp+3Fh+var_B8]; struct _tag_FW_RULE **
0x18002b48e  mov     rcx, r14; lpString2
0x18002b491  call    ?GetRuleByIDWithScopedProfiles@@YAJPEAGPEAU_tag_FW_RULE@@PEAPEAU1@@Z; GetRuleByIDWithScopedProfiles(ushort *,_tag_FW_RULE *,_tag_FW_RULE * *)
0x18002b496  mov     ebx, eax
0x18002b498  test    eax, eax
0x18002b49a  jns     short loc_18002B4C0
0x18002b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4a3  cmp     rcx, r15
0x18002b4a6  jz      loc_18002B853
0x18002b4ac  test    byte ptr [rcx+1Ch], 1
0x18002b4b0  jz      loc_18002B853
0x18002b4b6  mov     edx, 69h ; 'i'
0x18002b4bb  jmp     loc_18002B40F
0x18002b4c0  mov     esi, [rbp+3Fh+arg_20]
0x18002b4c3  test    edi, edi
0x18002b4c5  jnz     short loc_18002B4CF
0x18002b4c7  test    esi, esi
0x18002b4c9  jz      loc_18002B878
0x18002b4cf  mov     r15, [rsp+0F0h+var_C0]
0x18002b4d4  mov     eax, edi
0x18002b4d6  mov     r12d, esi
0x18002b4d9  mov     rdx, r15
0x18002b4dc  not     r12d
0x18002b4df  or      eax, [r15+28h]
0x18002b4e3  and     eax, r12d
0x18002b4e6  mov     [r15+28h], eax
0x18002b4ea  mov     rcx, [r13+40h]
0x18002b4ee  call    cs:__imp_FWSetFirewallRule
0x18002b4f4  mov     ebx, eax
0x18002b4f6  test    eax, eax
0x18002b4f8  jle     short loc_18002B503
0x18002b4fa  movzx   ebx, ax
0x18002b4fd  or      ebx, 80070000h
0x18002b503  test    ebx, ebx
0x18002b505  jns     short loc_18002B53C
0x18002b507  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b50e  lea     rax, WPP_GLOBAL_Control
0x18002b515  cmp     rcx, rax
0x18002b518  jz      loc_18002B853
0x18002b51e  test    byte ptr [rcx+1Ch], 1
0x18002b522  jz      loc_18002B853
0x18002b528  mov     edx, 6Ah ; 'j'
0x18002b52d  mov     r9d, ebx
0x18002b530  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002b537  jmp     loc_18002B84A
0x18002b53c  mov     r14, [rbp+3Fh+var_B8]
0x18002b540  mov     rdx, r14
0x18002b543  or      edi, [r14+28h]
0x18002b547  and     edi, r12d
0x18002b54a  mov     [r14+28h], edi
0x18002b54e  mov     rcx, [r13+40h]
0x18002b552  call    cs:__imp_FWSetFirewallRule
0x18002b558  mov     ebx, eax
0x18002b55a  mov     r12d, 80070000h
0x18002b560  test    eax, eax
0x18002b562  jle     short loc_18002B56A
0x18002b564  movzx   ebx, ax
0x18002b567  or      ebx, r12d
0x18002b56a  test    ebx, ebx
0x18002b56c  jns     short loc_18002B596
0x18002b56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b575  lea     rax, WPP_GLOBAL_Control
0x18002b57c  cmp     rcx, rax
0x18002b57f  jz      loc_18002B853
0x18002b585  test    byte ptr [rcx+1Ch], 1
0x18002b589  jz      loc_18002B853
0x18002b58f  mov     edx, 6Bh ; 'k'
0x18002b594  jmp     short loc_18002B52D
0x18002b596  test    esi, esi
0x18002b598  jz      loc_18002B878
0x18002b59e  lea     rcx, [rbp+3Fh+pguid]; pguid
0x18002b5a2  call    cs:__imp_CoCreateGuid
0x18002b5a8  mov     ebx, eax
0x18002b5aa  test    eax, eax
0x18002b5ac  jns     short loc_18002B5D9
0x18002b5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5b5  lea     rax, WPP_GLOBAL_Control
0x18002b5bc  cmp     rcx, rax
0x18002b5bf  jz      loc_18002B853
0x18002b5c5  test    byte ptr [rcx+1Ch], 1
0x18002b5c9  jz      loc_18002B853
0x18002b5cf  mov     edx, 6Ch ; 'l'
0x18002b5d4  jmp     loc_18002B52D
0x18002b5d9  mov     r8d, 28h ; '('; cchMax
0x18002b5df  lea     rdx, [rbp+3Fh+sz]; lpsz
0x18002b5e3  lea     rcx, [rbp+3Fh+pguid]; rguid
0x18002b5e7  call    cs:__imp_StringFromGUID2
0x18002b5ed  test    eax, eax
0x18002b5ef  jnz     short loc_18002B625
0x18002b5f1  mov     r9d, 8007007Ah
0x18002b5f7  mov     ebx, r9d
0x18002b5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b601  lea     rax, WPP_GLOBAL_Control
0x18002b608  cmp     rcx, rax
0x18002b60b  jz      loc_18002B853
0x18002b611  test    byte ptr [rcx+1Ch], 1
0x18002b615  jz      loc_18002B853
0x18002b61b  mov     edx, 6Dh ; 'm'
0x18002b620  jmp     loc_18002B530
0x18002b625  lea     rbx, [r15+10h]
0x18002b629  mov     rcx, [rbx]
0x18002b62c  call    cs:__imp_FwFree
0x18002b632  mov     rdx, rbx
0x18002b635  mov     qword ptr [rbx], 0
0x18002b63c  lea     rcx, [rbp+3Fh+sz]
0x18002b640  call    cs:__imp_FwStringCopy
0x18002b646  mov     ebx, eax
0x18002b648  test    eax, eax
0x18002b64a  jns     short loc_18002B677
0x18002b64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b653  lea     rax, WPP_GLOBAL_Control
0x18002b65a  cmp     rcx, rax
0x18002b65d  jz      loc_18002B853
0x18002b663  test    byte ptr [rcx+1Ch], 1
0x18002b667  jz      loc_18002B853
0x18002b66d  mov     edx, 6Eh ; 'n'
0x18002b672  jmp     loc_18002B52D
0x18002b677  mov     [r15+28h], esi
0x18002b67b  mov     eax, 0FFFEh
0x18002b680  and     [r15+124h], ax
0x18002b688  mov     rdx, r15
0x18002b68b  mov     rcx, [r13+40h]
0x18002b68f  call    cs:__imp_FWAddFirewallRule
0x18002b695  mov     ebx, eax
0x18002b697  test    eax, eax
0x18002b699  jle     short loc_18002B6A1
0x18002b69b  movzx   ebx, ax
0x18002b69e  or      ebx, r12d
0x18002b6a1  test    ebx, ebx
0x18002b6a3  jns     short loc_18002B6D0
0x18002b6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6ac  lea     rax, WPP_GLOBAL_Control
0x18002b6b3  cmp     rcx, rax
0x18002b6b6  jz      loc_18002B853
0x18002b6bc  test    byte ptr [rcx+1Ch], 1
0x18002b6c0  jz      loc_18002B853
0x18002b6c6  mov     edx, 6Fh ; 'o'
0x18002b6cb  jmp     loc_18002B52D
0x18002b6d0  lea     rcx, [rbp+3Fh+sz]; psz
0x18002b6d4  call    cs:__imp_SysAllocString
0x18002b6da  mov     rdi, [rsp+0F0h+var_D0]
0x18002b6df  lea     rcx, [rbp+3Fh+pguid]; pguid
0x18002b6e3  mov     [rdi], rax
0x18002b6e6  call    cs:__imp_CoCreateGuid
0x18002b6ec  mov     ebx, eax
0x18002b6ee  test    eax, eax
0x18002b6f0  jns     short loc_18002B71D
0x18002b6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6f9  lea     rax, WPP_GLOBAL_Control
0x18002b700  cmp     rcx, rax
0x18002b703  jz      loc_18002B858
0x18002b709  test    byte ptr [rcx+1Ch], 1
0x18002b70d  jz      loc_18002B858
0x18002b713  mov     edx, 70h ; 'p'
0x18002b718  mov     r9d, ebx
0x18002b71b  jmp     short loc_18002B764
0x18002b71d  mov     r8d, 28h ; '('; cchMax
0x18002b723  lea     rdx, [rbp+3Fh+sz]; lpsz
0x18002b727  lea     rcx, [rbp+3Fh+pguid]; rguid
0x18002b72b  call    cs:__imp_StringFromGUID2
0x18002b731  test    eax, eax
0x18002b733  jnz     short loc_18002B779
0x18002b735  mov     r9d, 8007007Ah
0x18002b73b  mov     ebx, r9d
0x18002b73e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b745  lea     rax, WPP_GLOBAL_Control
0x18002b74c  cmp     rcx, rax
0x18002b74f  jz      loc_18002B858
0x18002b755  test    byte ptr [rcx+1Ch], 1
0x18002b759  jz      loc_18002B858
0x18002b75f  mov     edx, 71h ; 'q'
0x18002b764  mov     rcx, [rcx+10h]
0x18002b768  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002b76f  call    WPP_SF_d
0x18002b774  jmp     loc_18002B858
0x18002b779  lea     rbx, [r14+10h]
0x18002b77d  mov     rcx, [rbx]
0x18002b780  call    cs:__imp_FwFree
0x18002b786  mov     rdx, rbx
0x18002b789  mov     qword ptr [rbx], 0
0x18002b790  lea     rcx, [rbp+3Fh+sz]
0x18002b794  call    cs:__imp_FwStringCopy
0x18002b79a  mov     ebx, eax
0x18002b79c  test    eax, eax
0x18002b79e  jns     short loc_18002B7CB
0x18002b7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7a7  lea     rax, WPP_GLOBAL_Control
0x18002b7ae  cmp     rcx, rax
0x18002b7b1  jz      loc_18002B858
0x18002b7b7  test    byte ptr [rcx+1Ch], 1
0x18002b7bb  jz      loc_18002B858
0x18002b7c1  mov     edx, 72h ; 'r'
0x18002b7c6  jmp     loc_18002B718
0x18002b7cb  mov     [r14+28h], esi
0x18002b7cf  mov     eax, 0FFFEh
0x18002b7d4  and     [r14+124h], ax
0x18002b7dc  mov     rdx, r14
0x18002b7df  mov     rcx, [r13+40h]
0x18002b7e3  call    cs:__imp_FWAddFirewallRule
0x18002b7e9  mov     ebx, eax
0x18002b7eb  test    eax, eax
0x18002b7ed  jle     short loc_18002B7F5
0x18002b7ef  movzx   ebx, ax
0x18002b7f2  or      ebx, r12d
0x18002b7f5  test    ebx, ebx
0x18002b7f7  jns     short loc_18002B81C
0x18002b7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b800  lea     rax, WPP_GLOBAL_Control
0x18002b807  cmp     rcx, rax
0x18002b80a  jz      short loc_18002B858
0x18002b80c  test    byte ptr [rcx+1Ch], 1
0x18002b810  jz      short loc_18002B858
0x18002b812  mov     edx, 73h ; 's'
0x18002b817  jmp     loc_18002B718
0x18002b81c  lea     rcx, [rbp+3Fh+sz]; psz
0x18002b820  call    cs:__imp_SysAllocString
0x18002b826  mov     rcx, [rbp+3Fh+var_B0]
  ... truncated ...
```
