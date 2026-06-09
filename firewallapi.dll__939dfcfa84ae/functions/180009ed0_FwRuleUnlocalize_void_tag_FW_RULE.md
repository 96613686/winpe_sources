# FwRuleUnlocalize(void *,_tag_FW_RULE *)

- ea: `0x180009ed0`
- end: `0x18000a3da`
- name: `?FwRuleUnlocalize@@YAJPEAXPEAU_tag_FW_RULE@@@Z`
- size: `1290`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800143d8`

## callees

- `0x180005e0c`
- `0x180009780`
- `0x180009ed0`
- `0x18000a3e0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `fwbase!FwBaseFree` at `0x18000a2a1`
- `fwbase!FwBaseFree` at `0x18000a2f4`
- `fwbase!FwBaseFree` at `0x18000a384`
- `fwbase!FwBaseFree` at `0x18000a2a1`
- `fwbase!FwBaseFree` at `0x18000a2f4`
- `fwbase!FwBaseFree` at `0x18000a384`
- `fwbase!FwReportReturnError` at `0x180009fc0`
- `fwbase!FwReportReturnError` at `0x180009fd5`
- `fwbase!FwReportReturnError` at `0x18000a0a2`
- `fwbase!FwReportReturnError` at `0x18000a0b7`
- `fwbase!FwReportReturnError` at `0x180009fc0`
- `fwbase!FwReportReturnError` at `0x180009fd5`
- `fwbase!FwReportReturnError` at `0x18000a0a2`
- `fwbase!FwReportReturnError` at `0x18000a0b7`
- `fwbase!FwStringCopy` at `0x18000a2bd`
- `fwbase!FwStringCopy` at `0x18000a319`
- `fwbase!FwStringCopy` at `0x18000a3a0`
- `fwbase!FwStringCopy` at `0x18000a2bd`
- `fwbase!FwStringCopy` at `0x18000a319`
- `fwbase!FwStringCopy` at `0x18000a3a0`

## pseudocode

```c
__int64 __fastcall FwRuleUnlocalize(void *a1, struct _tag_FW_RULE *a2)
{
  __int64 v2; // rbx
  int v4; // esi
  _QWORD *v5; // r15
  int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // r14
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r10
  unsigned __int16 *v16; // rax
  __int64 v17; // r10
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // r10
  unsigned __int16 *v22; // rax
  __int64 v23; // r10
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // ebx
  FwPolicy2 *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned __int16 *v31; // rax
  __int64 v32; // r9
  int v33; // edx
  int v34; // r8d
  _QWORD *v35; // [rsp+30h] [rbp-79h] BYREF
  _QWORD *v36; // [rsp+38h] [rbp-71h] BYREF
  int v37; // [rsp+40h] [rbp-69h] BYREF
  int v38; // [rsp+44h] [rbp-65h]
  __int128 *v39; // [rsp+48h] [rbp-61h]
  __int64 v40; // [rsp+50h] [rbp-59h]
  int v41; // [rsp+58h] [rbp-51h] BYREF
  int v42; // [rsp+5Ch] [rbp-4Dh]
  __int128 *v43; // [rsp+60h] [rbp-49h]
  __int64 v44; // [rsp+68h] [rbp-41h]
  __int128 v45; // [rsp+70h] [rbp-39h] BYREF
  __int64 v46; // [rsp+80h] [rbp-29h]
  __int128 v47; // [rsp+88h] [rbp-21h] BYREF
  __int64 v48; // [rsp+98h] [rbp-11h]
  __int128 v49; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v50; // [rsp+B0h] [rbp+7h] BYREF
  int v51; // [rsp+C0h] [rbp+17h] BYREF
  int v52; // [rsp+C4h] [rbp+1Bh] BYREF

  v2 = *((_QWORD *)a2 + 2);
  v35 = 0;
  v51 = 0;
  v46 = 0;
  v4 = (int)a1;
  v37 = 545;
  v5 = 0;
  v38 = 1;
  v45 = 0;
  v39 = 0;
  v49 = 0;
  v40 = 0x10000;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids);
  *(_QWORD *)&v45 = 2;
  *((_QWORD *)&v49 + 1) = &v45;
  DWORD2(v45) = 5;
  v39 = &v49;
  v46 = v2;
  LODWORD(v49) = 1;
  v38 = 1;
  v6 = FWQueryFirewallRules(v4, (unsigned int)&v37, 7, (unsigned int)&v51, (__int64)&v35);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( (v7 & 0x80000000) == 0 )
  {
    if ( v51 )
    {
      v8 = v35;
      v35 = 0;
      goto LABEL_6;
    }
    v7 = -2147023728;
  }
  v8 = 0;
  FwReportReturnError("FwRuleLookup", v7);
  v9 = FwReportReturnError("FwRuleLookup", v7);
  v10 = v9;
  if ( v9 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v29 = 61;
    goto LABEL_54;
  }
LABEL_6:
  v11 = *((_QWORD *)a2 + 2);
  v36 = 0;
  v47 = 0;
  v48 = 0;
  v50 = 0;
  v52 = 0;
  v41 = 545;
  v42 = 1;
  v43 = 0;
  v44 = 0x10000;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids);
  *(_QWORD *)&v47 = 2;
  *((_QWORD *)&v50 + 1) = &v47;
  DWORD2(v47) = 5;
  v43 = &v50;
  v48 = v11;
  LODWORD(v50) = 1;
  v42 = 1;
  v12 = FWQueryFirewallRules(v4, (unsigned int)&v41, 0, (unsigned int)&v52, (__int64)&v36);
  v10 = v12;
  if ( v12 > 0 )
    v10 = (unsigned __int16)v12 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_10;
  if ( !v52 )
  {
    v10 = -2147023728;
LABEL_10:
    FwReportReturnError("FwRuleLookup", v10);
    v9 = FwReportReturnError("FwRuleLookup", v10);
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_11;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v29 = 62;
LABEL_54:
    WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v9);
    goto LABEL_24;
  }
  v5 = v36;
  v36 = 0;
LABEL_11:
  v13 = *((_QWORD *)a2 + 3);
  if ( !v13 )
    goto LABEL_12;
  v30 = v8[3];
  if ( !v30 )
    goto LABEL_12;
  v31 = (unsigned __int16 *)*((_QWORD *)a2 + 3);
  v32 = v30 - v13;
  do
  {
    v33 = *(unsigned __int16 *)((char *)v31 + v32);
    v34 = *v31 - v33;
    if ( v34 )
      break;
    ++v31;
  }
  while ( v33 );
  if ( !v34 && (FwBaseFree(v13), *((_QWORD *)a2 + 3) = 0, v9 = FwStringCopy(v5[3], (char *)a2 + 24), v10 = v9, v9 < 0) )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v29 = 63;
      goto LABEL_54;
    }
  }
  else
  {
LABEL_12:
    v14 = *((_QWORD *)a2 + 4);
    if ( !v14 )
      goto LABEL_18;
    v15 = v8[4];
    if ( !v15 )
      goto LABEL_18;
    v16 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
    v17 = v15 - v14;
    do
    {
      v18 = *(unsigned __int16 *)((char *)v16 + v17);
      v19 = *v16 - v18;
      if ( v19 )
        break;
      ++v16;
    }
    while ( v18 );
    if ( v19 || (FwBaseFree(v14), *((_QWORD *)a2 + 4) = 0, v9 = FwStringCopy(v5[4], (char *)a2 + 32), v10 = v9, v9 >= 0) )
    {
LABEL_18:
      v20 = *((_QWORD *)a2 + 39);
      if ( !v20 )
        goto LABEL_24;
      v21 = v8[39];
      if ( !v21 )
        goto LABEL_24;
      v22 = (unsigned __int16 *)*((_QWORD *)a2 + 39);
      v23 = v21 - v20;
      do
      {
        v24 = *(unsigned __int16 *)((char *)v22 + v23);
        v25 = *v22 - v24;
        if ( v25 )
          break;
        ++v22;
      }
      while ( v24 );
      if ( v25 )
        goto LABEL_24;
      FwBaseFree(v20);
      *((_QWORD *)a2 + 39) = 0;
      v9 = FwStringCopy(v5[39], (char *)a2 + 312);
      v10 = v9;
      if ( v9 >= 0 )
        goto LABEL_24;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v29 = 65;
      goto LABEL_54;
    }
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v29 = 64;
      goto LABEL_54;
    }
  }
LABEL_24:
  v26 = 0;
  if ( v10 != -2147023728 )
    v26 = v10;
  FWFreeFirewallRules(v8);
  FWFreeFirewallRules(v5);
  return v26;
}

```

## disassembly

```asm
0x180009ed0  mov     [rsp-8+arg_10], rbx
0x180009ed5  push    rbp
0x180009ed6  push    rsi
0x180009ed7  push    rdi
0x180009ed8  push    r12
0x180009eda  push    r13
0x180009edc  push    r14
0x180009ede  push    r15
0x180009ee0  lea     rbp, [rsp-27h]
0x180009ee5  sub     rsp, 0D0h
0x180009eec  mov     rax, cs:__security_cookie
0x180009ef3  xor     rax, rsp
0x180009ef6  mov     [rbp+57h+var_38], rax
0x180009efa  mov     rbx, [rdx+10h]
0x180009efe  xor     edi, edi
0x180009f00  xorps   xmm0, xmm0
0x180009f03  mov     [rbp+57h+var_D0], rdi
0x180009f07  xor     eax, eax
0x180009f09  mov     [rbp+57h+var_40], edi
0x180009f0c  mov     [rbp+57h+var_80], rax
0x180009f10  mov     r13, rdx
0x180009f13  mov     rsi, rcx
0x180009f16  mov     [rbp+57h+var_C0], 221h
0x180009f1d  mov     r15d, edi
0x180009f20  mov     [rbp+57h+var_BC], 1
0x180009f27  movups  [rbp+57h+var_90], xmm0
0x180009f2b  mov     [rbp+57h+var_B8], rdi
0x180009f2f  movups  [rbp+57h+var_60], xmm0
0x180009f33  mov     [rbp+57h+var_B0], 10000h
0x180009f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f42  lea     rax, WPP_GLOBAL_Control
0x180009f49  cmp     rcx, rax
0x180009f4c  jnz     loc_18000A195
0x180009f52  lea     rax, [rbp+57h+var_90]
0x180009f56  mov     qword ptr [rbp+57h+var_90], 2
0x180009f5e  mov     qword ptr [rbp+57h+var_60+8], rax
0x180009f62  lea     r9, [rbp+57h+var_40]
0x180009f66  lea     rax, [rbp+57h+var_60]
0x180009f6a  mov     dword ptr [rbp+57h+var_90+8], 5
0x180009f71  mov     [rbp+57h+var_B8], rax
0x180009f75  lea     rdx, [rbp+57h+var_C0]
0x180009f79  lea     rax, [rbp+57h+var_D0]
0x180009f7d  mov     [rbp+57h+var_80], rbx
0x180009f81  mov     r8d, 7
0x180009f87  mov     [rsp+100h+var_E0], rax
0x180009f8c  mov     rcx, rsi
0x180009f8f  mov     dword ptr [rbp+57h+var_60], 1
0x180009f96  mov     [rbp+57h+var_BC], 1
0x180009f9d  call    FWQueryFirewallRules
0x180009fa2  mov     ebx, eax
0x180009fa4  test    eax, eax
0x180009fa6  jg      loc_18000A204
0x180009fac  test    ebx, ebx
0x180009fae  jns     loc_18000A1DD
0x180009fb4  mov     edx, ebx
0x180009fb6  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x180009fbd  mov     r14, rdi
0x180009fc0  call    cs:__imp_FwReportReturnError
0x180009fc7  nop     dword ptr [rax+rax+00h]
0x180009fcc  mov     edx, ebx
0x180009fce  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x180009fd5  call    cs:__imp_FwReportReturnError
0x180009fdc  nop     dword ptr [rax+rax+00h]
0x180009fe1  mov     edi, eax
0x180009fe3  test    eax, eax
0x180009fe5  js      loc_18000A220
0x180009feb  xor     edi, edi
0x180009fed  mov     rbx, [r13+10h]
0x180009ff1  xorps   xmm0, xmm0
0x180009ff4  xor     eax, eax
0x180009ff6  mov     [rbp+57h+var_C8], rdi
0x180009ffa  movups  [rbp+57h+var_78], xmm0
0x180009ffe  mov     [rbp+57h+var_68], rax
0x18000a002  movups  [rbp+57h+var_50], xmm0
0x18000a006  mov     [rbp+57h+var_3C], edi
0x18000a009  mov     [rbp+57h+var_A8], 221h
0x18000a010  mov     [rbp+57h+var_A4], 1
0x18000a017  mov     [rbp+57h+var_A0], rdi
0x18000a01b  mov     [rbp+57h+var_98], 10000h
0x18000a023  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a02a  lea     r12, WPP_GLOBAL_Control
0x18000a031  cmp     rcx, r12
0x18000a034  jnz     loc_18000A1B9
0x18000a03a  lea     rax, [rbp+57h+var_78]
0x18000a03e  mov     qword ptr [rbp+57h+var_78], 2
0x18000a046  mov     qword ptr [rbp+57h+var_50+8], rax
0x18000a04a  lea     r9, [rbp+57h+var_3C]
0x18000a04e  lea     rax, [rbp+57h+var_50]
0x18000a052  mov     dword ptr [rbp+57h+var_78+8], 5
0x18000a059  mov     [rbp+57h+var_A0], rax
0x18000a05d  lea     rdx, [rbp+57h+var_A8]
0x18000a061  lea     rax, [rbp+57h+var_C8]
0x18000a065  mov     [rbp+57h+var_68], rbx
0x18000a069  xor     r8d, r8d
0x18000a06c  mov     [rsp+100h+var_E0], rax
0x18000a071  mov     rcx, rsi
0x18000a074  mov     dword ptr [rbp+57h+var_50], 1
0x18000a07b  mov     [rbp+57h+var_A4], 1
0x18000a082  call    FWQueryFirewallRules
0x18000a087  mov     edi, eax
0x18000a089  test    eax, eax
0x18000a08b  jg      loc_18000A212
0x18000a091  test    edi, edi
0x18000a093  jns     loc_18000A1F0
0x18000a099  mov     edx, edi
0x18000a09b  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18000a0a2  call    cs:__imp_FwReportReturnError
0x18000a0a9  nop     dword ptr [rax+rax+00h]
0x18000a0ae  mov     edx, edi
0x18000a0b0  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18000a0b7  call    cs:__imp_FwReportReturnError
0x18000a0be  nop     dword ptr [rax+rax+00h]
0x18000a0c3  mov     edi, eax
0x18000a0c5  test    eax, eax
0x18000a0c7  js      loc_18000A24B
0x18000a0cd  mov     rcx, [r13+18h]
0x18000a0d1  test    rcx, rcx
0x18000a0d4  jnz     loc_18000A26F
0x18000a0da  mov     rcx, [r13+20h]
0x18000a0de  test    rcx, rcx
0x18000a0e1  jz      short loc_18000A112
0x18000a0e3  mov     r10, [r14+20h]
0x18000a0e7  test    r10, r10
0x18000a0ea  jz      short loc_18000A112
0x18000a0ec  mov     rax, rcx
0x18000a0ef  sub     r10, rcx
0x18000a0f2  movzx   r9d, word ptr [rax]
0x18000a0f6  movzx   r8d, word ptr [rax+r10]
0x18000a0fb  sub     r9d, r8d
0x18000a0fe  jnz     short loc_18000A109
0x18000a100  add     rax, 2
0x18000a104  test    r8d, r8d
0x18000a107  jnz     short loc_18000A0F2
0x18000a109  test    r9d, r9d
0x18000a10c  jz      loc_18000A384
0x18000a112  mov     rcx, [r13+138h]
0x18000a119  test    rcx, rcx
0x18000a11c  jz      short loc_18000A150
0x18000a11e  mov     r10, [r14+138h]
0x18000a125  test    r10, r10
0x18000a128  jz      short loc_18000A150
0x18000a12a  mov     rax, rcx
0x18000a12d  sub     r10, rcx
0x18000a130  movzx   r9d, word ptr [rax]
0x18000a134  movzx   r8d, word ptr [rax+r10]
0x18000a139  sub     r9d, r8d
0x18000a13c  jnz     short loc_18000A147
0x18000a13e  add     rax, 2
0x18000a142  test    r8d, r8d
0x18000a145  jnz     short loc_18000A130
0x18000a147  test    r9d, r9d
0x18000a14a  jz      loc_18000A2F4
0x18000a150  xor     ebx, ebx
0x18000a152  mov     rcx, r14
0x18000a155  cmp     edi, 80070490h
0x18000a15b  cmovnz  ebx, edi
0x18000a15e  call    FWFreeFirewallRules
0x18000a163  mov     rcx, r15
0x18000a166  call    FWFreeFirewallRules
0x18000a16b  mov     eax, ebx
0x18000a16d  mov     rcx, [rbp+57h+var_38]
0x18000a171  xor     rcx, rsp; StackCookie
0x18000a174  call    __security_check_cookie
0x18000a179  mov     rbx, [rsp+100h+arg_10]
0x18000a181  add     rsp, 0D0h
0x18000a188  pop     r15
0x18000a18a  pop     r14
0x18000a18c  pop     r13
0x18000a18e  pop     r12
0x18000a190  pop     rdi
0x18000a191  pop     rsi
0x18000a192  pop     rbp
0x18000a193  retn
0x18000a195  test    byte ptr [rcx+1Ch], 8
0x18000a199  jz      loc_180009F52
0x18000a19f  mov     rcx, [rcx+10h]
0x18000a1a3  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18000a1aa  mov     edx, 3Ch ; '<'
0x18000a1af  call    WPP_SF_
0x18000a1b4  jmp     loc_180009F52
0x18000a1b9  test    byte ptr [rcx+1Ch], 8
0x18000a1bd  jz      loc_18000A03A
0x18000a1c3  mov     rcx, [rcx+10h]
0x18000a1c7  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18000a1ce  mov     edx, 3Ch ; '<'
0x18000a1d3  call    WPP_SF_
0x18000a1d8  jmp     loc_18000A03A
0x18000a1dd  cmp     [rbp+57h+var_40], edi
0x18000a1e0  ja      loc_18000A366
0x18000a1e6  mov     ebx, 80070490h
0x18000a1eb  jmp     loc_180009FB4
0x18000a1f0  cmp     [rbp+57h+var_3C], r15d
0x18000a1f4  ja      loc_18000A373
0x18000a1fa  mov     edi, 80070490h
0x18000a1ff  jmp     loc_18000A099
0x18000a204  movzx   ebx, ax
0x18000a207  or      ebx, 80070000h
0x18000a20d  jmp     loc_180009FAC
0x18000a212  movzx   edi, ax
0x18000a215  or      edi, 80070000h
0x18000a21b  jmp     loc_18000A091
0x18000a220  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a227  lea     r12, WPP_GLOBAL_Control
0x18000a22e  cmp     rcx, r12
0x18000a231  jz      loc_18000A150
0x18000a237  test    byte ptr [rcx+1Ch], 1
0x18000a23b  jz      loc_18000A150
0x18000a241  mov     edx, 3Dh ; '='
0x18000a246  jmp     loc_18000A34E
0x18000a24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a252  cmp     rcx, r12
0x18000a255  jz      loc_18000A150
0x18000a25b  test    byte ptr [rcx+1Ch], 1
0x18000a25f  jz      loc_18000A150
0x18000a265  mov     edx, 3Eh ; '>'
0x18000a26a  jmp     loc_18000A34E
0x18000a26f  mov     r9, [r14+18h]
0x18000a273  test    r9, r9
0x18000a276  jz      loc_18000A0DA
0x18000a27c  mov     rax, rcx
0x18000a27f  sub     r9, rcx
0x18000a282  movzx   r8d, word ptr [rax]
0x18000a286  movzx   edx, word ptr [rax+r9]
0x18000a28b  sub     r8d, edx
0x18000a28e  jnz     short loc_18000A298
0x18000a290  add     rax, 2
0x18000a294  test    edx, edx
0x18000a296  jnz     short loc_18000A282
0x18000a298  test    r8d, r8d
0x18000a29b  jnz     loc_18000A0DA
0x18000a2a1  call    cs:__imp_FwBaseFree
0x18000a2a8  nop     dword ptr [rax+rax+00h]
0x18000a2ad  mov     qword ptr [r13+18h], 0
0x18000a2b5  lea     rdx, [r13+18h]
0x18000a2b9  mov     rcx, [r15+18h]
0x18000a2bd  call    cs:__imp_FwStringCopy
0x18000a2c4  nop     dword ptr [rax+rax+00h]
0x18000a2c9  mov     edi, eax
0x18000a2cb  test    eax, eax
0x18000a2cd  jns     loc_18000A0DA
0x18000a2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2da  cmp     rcx, r12
0x18000a2dd  jz      loc_18000A150
0x18000a2e3  test    byte ptr [rcx+1Ch], 1
0x18000a2e7  jz      loc_18000A150
0x18000a2ed  mov     edx, 3Fh ; '?'
0x18000a2f2  jmp     short loc_18000A34E
0x18000a2f4  call    cs:__imp_FwBaseFree
0x18000a2fb  nop     dword ptr [rax+rax+00h]
0x18000a300  mov     qword ptr [r13+138h], 0
0x18000a30b  lea     rdx, [r13+138h]
0x18000a312  mov     rcx, [r15+138h]
0x18000a319  call    cs:__imp_FwStringCopy
0x18000a320  nop     dword ptr [rax+rax+00h]
0x18000a325  mov     edi, eax
0x18000a327  test    eax, eax
0x18000a329  jns     loc_18000A150
0x18000a32f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a336  cmp     rcx, r12
0x18000a339  jz      loc_18000A150
0x18000a33f  test    byte ptr [rcx+1Ch], 1
0x18000a343  jz      loc_18000A150
0x18000a349  mov     edx, 41h ; 'A'
0x18000a34e  mov     rcx, [rcx+10h]
0x18000a352  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18000a359  mov     r9d, eax
0x18000a35c  call    WPP_SF_d
0x18000a361  jmp     loc_18000A150
0x18000a366  mov     r14, [rbp+57h+var_D0]
0x18000a36a  mov     [rbp+57h+var_D0], rdi
0x18000a36e  jmp     loc_180009FED
0x18000a373  mov     r15, [rbp+57h+var_C8]
0x18000a377  mov     [rbp+57h+var_C8], 0
0x18000a37f  jmp     loc_18000A0CD
0x18000a384  call    cs:__imp_FwBaseFree
0x18000a38b  nop     dword ptr [rax+rax+00h]
0x18000a390  mov     qword ptr [r13+20h], 0
0x18000a398  lea     rdx, [r13+20h]
0x18000a39c  mov     rcx, [r15+20h]
0x18000a3a0  call    cs:__imp_FwStringCopy
0x18000a3a7  nop     dword ptr [rax+rax+00h]
0x18000a3ac  mov     edi, eax
0x18000a3ae  test    eax, eax
0x18000a3b0  jns     loc_18000A112
0x18000a3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3bd  cmp     rcx, r12
0x18000a3c0  jz      loc_18000A150
0x18000a3c6  test    byte ptr [rcx+1Ch], 1
0x18000a3ca  jz      loc_18000A150
0x18000a3d0  mov     edx, 40h ; '@'
0x18000a3d5  jmp     loc_18000A34E
```
