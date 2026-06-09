# FwPolicy2::get_LocalPolicyModifyState(NET_FW_MODIFY_STATE_ *)

- ea: `0x18000bea0`
- end: `0x18000c3e7`
- name: `?get_LocalPolicyModifyState@FwPolicy2@@UEAAJPEAW4NET_FW_MODIFY_STATE_@@@Z`
- size: `1351`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_MODIFY_STATE_ *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x180009210`
- `0x18000bea0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x18000ed70`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c1a1`
- `ntdll!EtwEventWrite` at `0x18000c230`
- `ntdll!EtwEventWrite` at `0x18000c1a1`
- `ntdll!EtwEventWrite` at `0x18000c230`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c1ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c1ca`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000bf7b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000c137`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000bf7b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000c137`
- `fwbase!FwReportErrorAsWinError` at `0x18000c057`
- `fwbase!FwReportErrorAsWinError` at `0x18000c2ef`
- `fwbase!FwReportErrorAsWinError` at `0x18000c3d4`
- `fwbase!FwReportErrorAsWinError` at `0x18000c057`
- `fwbase!FwReportErrorAsWinError` at `0x18000c2ef`
- `fwbase!FwReportErrorAsWinError` at `0x18000c3d4`
- `fwbase!FwReportReturnError` at `0x18000c30b`
- `fwbase!FwReportReturnError` at `0x18000c30b`

## string_xrefs

- `0x18000c2de`: `FWOpenPolicyStore`
- `0x18000c049`: `FWGetGlobalConfig`
- `0x18000c364`: `FWGetConfig`
- `0x18000c3c6`: `FWGetConfig`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_LocalPolicyModifyState(FwPolicy2 *this, enum NET_FW_MODIFY_STATE_ *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int i; // ebx
  int ProfileTypeFromProfileIndex; // eax
  int v10; // edi
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // r13d
  enum NET_FW_MODIFY_STATE_ v16; // r14d
  unsigned int j; // edi
  int v19; // r15d
  int v20; // r12d
  unsigned int v21; // r15d
  const char *v22; // rdx
  int v23; // [rsp+48h] [rbp-9h]
  __int64 v24; // [rsp+58h] [rbp+7h] BYREF
  int v25; // [rsp+60h] [rbp+Fh] BYREF
  int v26; // [rsp+64h] [rbp+13h] BYREF
  int v27; // [rsp+68h] [rbp+17h] BYREF
  int v28; // [rsp+6Ch] [rbp+1Bh] BYREF
  __int64 v29; // [rsp+70h] [rbp+1Fh]
  int v30; // [rsp+78h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v26 = 4;
  v24 = 0;
  v29 = 0;
  v30 = 0;
  v28 = 0;
  v3 = FWGetGlobalConfig(545, 0, 5, 2, 0, (__int64)&v28, (__int64)&v26);
  if ( v3 )
  {
    v12 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWGetGlobalConfig", v3);
    goto LABEL_23;
  }
  v4 = FWOpenPolicyStore(0x221u, 0, 1u, 1u, 0, &v24);
  if ( v4 == 2 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  }
  else
  {
    if ( v4 )
    {
LABEL_49:
      v22 = "FWOpenPolicyStore";
LABEL_50:
      v12 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", v22, v4);
      goto LABEL_23;
    }
    for ( i = 0; i < 3; ++i )
    {
      ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(i);
      v10 = ProfileTypeFromProfileIndex;
      if ( (ProfileTypeFromProfileIndex & v28) != 0 )
      {
        v25 = 0;
        v26 = 4;
        v27 = 0;
        v4 = FWGetConfig2(v24, 3, ProfileTypeFromProfileIndex, 0, (__int64)&v25, (__int64)&v26, (__int64)&v27);
        if ( v4 == 2 )
        {
          v25 = 0;
        }
        else
        {
          if ( v4 )
            goto LABEL_56;
          if ( v25 )
            *((_DWORD *)&v29 + i) = 1;
        }
        v27 = 0;
        v4 = FWGetConfig2(v24, 13, v10, 0, (__int64)&v25, (__int64)&v26, (__int64)&v27);
        if ( v4 == 2 )
        {
          v25 = 1;
        }
        else
        {
          if ( v4 )
          {
LABEL_56:
            v22 = "FWGetConfig";
            goto LABEL_50;
          }
          if ( !v25 )
            *((_DWORD *)&v29 + i) = 1;
        }
      }
    }
    FWClosePolicyStore(v24, v5, v6, v7);
    v24 = 0;
  }
  v4 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v24);
  if ( v4 )
    goto LABEL_49;
  v12 = 0;
  v15 = 0;
  v16 = NET_FW_MODIFY_STATE_OK;
  for ( j = 0; ; ++j )
  {
    if ( j >= 3 )
    {
      *a2 = v16;
      goto LABEL_23;
    }
    v19 = FwGetProfileTypeFromProfileIndex(j);
    if ( (v19 & v28) != 0 )
      break;
LABEL_42:
    ;
  }
  v20 = *((_DWORD *)&v29 + j);
  if ( v20 == 1 )
  {
LABEL_40:
    if ( v15 )
    {
      if ( v20 != v16 )
      {
        if ( v16 == NET_FW_MODIFY_STATE_INBOUND_BLOCKED )
        {
          v16 = v20;
        }
        else if ( !v20 )
        {
          v16 = NET_FW_MODIFY_STATE_OK;
        }
        v12 = 1;
      }
    }
    else
    {
      v15 = 1;
      v16 = v20;
      v12 = 0;
    }
    goto LABEL_42;
  }
  v25 = 0;
  v26 = 4;
  v23 = v24;
  v27 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v21 = Int_FWGetOrSetConfig(1, v23, 3, v19, 1, (__int64)&v25, (__int64)&v26, (__int64)&v27);
  if ( v21 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v21);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  if ( !v21 )
  {
    if ( v25 )
    {
      v20 = 2;
      *((_DWORD *)&v29 + j) = 2;
    }
    goto LABEL_40;
  }
  v12 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWGetConfig", v21);
LABEL_23:
  if ( v24 )
    FWClosePolicyStore(v24, v11, v13, v14);
  if ( v12 < 0 )
    return FwReportReturnError("FwPolicy2::get_LocalPolicyModifyState", (unsigned int)v12);
  else
    return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000bea0  mov     r11, rsp
0x18000bea3  push    rbp
0x18000bea4  push    rbx
0x18000bea5  lea     rbp, [r11-5Fh]
0x18000bea9  sub     rsp, 98h
0x18000beb0  mov     rax, cs:__security_cookie
0x18000beb7  xor     rax, rsp
0x18000beba  mov     [rbp+57h+var_28], rax
0x18000bebe  mov     [r11+8], rsi
0x18000bec2  mov     rsi, rdx
0x18000bec5  mov     [r11-28h], r15
0x18000bec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bed0  lea     rbx, WPP_GLOBAL_Control
0x18000bed7  cmp     rcx, rbx
0x18000beda  jnz     loc_18000C26A
0x18000bee0  xor     r15d, r15d
0x18000bee3  mov     [rbp+57h+var_44], 4
0x18000beea  lea     rax, [rbp+57h+var_44]
0x18000beee  mov     [rbp+57h+var_50], r15
0x18000bef2  mov     [rsp+0A0h+var_70], rax
0x18000bef7  mov     ecx, 221h
0x18000befc  lea     rax, [rbp+57h+var_3C]
0x18000bf00  mov     [rbp+57h+var_38], r15
0x18000bf04  mov     [rsp+0A0h+var_78], rax
0x18000bf09  xor     edx, edx
0x18000bf0b  mov     r9d, 2
0x18000bf11  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000bf16  mov     r8d, 5
0x18000bf1c  mov     [rbp+57h+var_30], r15d
0x18000bf20  mov     [rbp+57h+var_3C], r15d
0x18000bf24  call    FWGetGlobalConfig
0x18000bf29  test    eax, eax
0x18000bf2b  jnz     loc_18000C046
0x18000bf31  lea     rax, [rbp+57h+var_50]
0x18000bf35  mov     [rsp+0A0h+arg_10], rdi
0x18000bf3d  mov     r9d, 1
0x18000bf43  mov     [rsp+0A0h+var_78], rax
0x18000bf48  mov     r8d, r9d
0x18000bf4b  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000bf50  mov     ecx, 221h
0x18000bf55  xor     edx, edx
0x18000bf57  call    FWOpenPolicyStore
0x18000bf5c  cmp     eax, 2
0x18000bf5f  jz      loc_18000C06A
0x18000bf65  test    eax, eax
0x18000bf67  jnz     loc_18000C2DE
0x18000bf6d  mov     ebx, r15d
0x18000bf70  cmp     ebx, 3
0x18000bf73  jnb     loc_18000C2CC
0x18000bf79  mov     ecx, ebx
0x18000bf7b  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000bf82  nop     dword ptr [rax+rax+00h]
0x18000bf87  mov     edi, eax
0x18000bf89  test    [rbp+57h+var_3C], eax
0x18000bf8c  jz      loc_18000C03F
0x18000bf92  mov     rcx, [rbp+57h+var_50]
0x18000bf96  lea     rax, [rbp+57h+var_40]
0x18000bf9a  mov     [rsp+0A0h+var_70], rax
0x18000bf9f  xor     r9d, r9d
0x18000bfa2  lea     rax, [rbp+57h+var_44]
0x18000bfa6  mov     [rbp+57h+var_48], r15d
0x18000bfaa  mov     [rsp+0A0h+var_78], rax
0x18000bfaf  mov     r8d, edi
0x18000bfb2  lea     rax, [rbp+57h+var_48]
0x18000bfb6  mov     [rbp+57h+var_44], 4
0x18000bfbd  mov     edx, 3
0x18000bfc2  mov     [rsp+0A0h+var_80], rax
0x18000bfc7  mov     [rbp+57h+var_40], r15d
0x18000bfcb  call    FWGetConfig2
0x18000bfd0  cmp     eax, 2
0x18000bfd3  jz      loc_18000C340
0x18000bfd9  test    eax, eax
0x18000bfdb  jnz     loc_18000C364
0x18000bfe1  cmp     [rbp+57h+var_48], r15d
0x18000bfe5  jnz     loc_18000C349
0x18000bfeb  mov     rcx, [rbp+57h+var_50]
0x18000bfef  lea     rax, [rbp+57h+var_40]
0x18000bff3  mov     [rsp+0A0h+var_70], rax
0x18000bff8  xor     r9d, r9d
0x18000bffb  lea     rax, [rbp+57h+var_44]
0x18000bfff  mov     [rbp+57h+var_40], r15d
0x18000c003  mov     [rsp+0A0h+var_78], rax
0x18000c008  mov     r8d, edi
0x18000c00b  lea     rax, [rbp+57h+var_48]
0x18000c00f  mov     edx, 0Dh
0x18000c014  mov     [rsp+0A0h+var_80], rax
0x18000c019  call    FWGetConfig2
0x18000c01e  cmp     eax, 2
0x18000c021  jz      loc_18000C358
0x18000c027  test    eax, eax
0x18000c029  jnz     loc_18000C364
0x18000c02f  cmp     [rbp+57h+var_48], r15d
0x18000c033  jnz     short loc_18000C03F
0x18000c035  mov     eax, ebx
0x18000c037  mov     dword ptr [rbp+rax*4+57h+var_38], 1
0x18000c03f  inc     ebx
0x18000c041  jmp     loc_18000BF70
0x18000c046  mov     r8d, eax
0x18000c049  lea     rdx, aFwgetglobalcon_4; "FWGetGlobalConfig"
0x18000c050  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000c057  call    cs:__imp_FwReportErrorAsWinError
0x18000c05e  nop     dword ptr [rax+rax+00h]
0x18000c063  mov     ebx, eax
0x18000c065  jmp     loc_18000C0F4
0x18000c06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c071  cmp     rcx, rbx
0x18000c074  jnz     loc_18000C31C
0x18000c07a  lea     rax, [rbp+57h+var_50]
0x18000c07e  mov     ecx, 221h
0x18000c083  mov     [rsp+0A0h+var_78], rax
0x18000c088  xor     edx, edx
0x18000c08a  mov     r9d, 1
0x18000c090  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000c095  mov     r8d, 5
0x18000c09b  call    FWOpenPolicyStore
0x18000c0a0  test    eax, eax
0x18000c0a2  jnz     loc_18000C2DE
0x18000c0a8  mov     [rsp+90h], r13
0x18000c0b0  mov     ebx, r15d
0x18000c0b3  mov     [rsp+0A0h+var_18], r14
0x18000c0bb  mov     r13d, r15d
0x18000c0be  mov     r14d, r15d
0x18000c0c1  mov     [rsp+0A0h+arg_18], r12
0x18000c0c9  mov     edi, r15d
0x18000c0cc  cmp     edi, 3
0x18000c0cf  jb      short loc_18000C135
0x18000c0d1  mov     [rsi], r14d
0x18000c0d4  mov     r12, [rsp+0A0h+arg_18]
0x18000c0dc  mov     r13, [rsp+90h]
0x18000c0e4  mov     r14, [rsp+0A0h+var_18]
0x18000c0ec  mov     rdi, [rsp+0A0h+arg_10]
0x18000c0f4  mov     rcx, [rbp+57h+var_50]
0x18000c0f8  mov     r15, [rsp+0A0h+var_20]
0x18000c100  mov     rsi, [rsp+0A0h+arg_0]
0x18000c108  test    rcx, rcx
0x18000c10b  jnz     short loc_18000C12E
0x18000c10d  test    ebx, ebx
0x18000c10f  js      loc_18000C302
0x18000c115  mov     eax, ebx
0x18000c117  mov     rcx, [rbp+57h+var_28]
0x18000c11b  xor     rcx, rsp; StackCookie
0x18000c11e  call    __security_check_cookie
0x18000c123  add     rsp, 98h
0x18000c12a  pop     rbx
0x18000c12b  pop     rbp
0x18000c12c  retn
0x18000c12e  call    FWClosePolicyStore
0x18000c133  jmp     short loc_18000C10D
0x18000c135  mov     ecx, edi
0x18000c137  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000c13e  nop     dword ptr [rax+rax+00h]
0x18000c143  mov     r15d, eax
0x18000c146  test    [rbp+57h+var_3C], eax
0x18000c149  jz      loc_18000C263
0x18000c14f  mov     ecx, edi
0x18000c151  lea     rax, [rbp+57h+var_38]
0x18000c155  mov     r12d, [rax+rcx*4]
0x18000c159  lea     rax, [rax+rcx*4]
0x18000c15d  mov     [rbp+57h+var_58], rax
0x18000c161  cmp     r12d, 1
0x18000c165  jz      loc_18000C24F
0x18000c16b  mov     rcx, cs:g_Provider
0x18000c172  mov     rax, [rbp+57h+var_50]
0x18000c176  mov     [rbp+57h+var_48], 0
0x18000c17d  mov     [rbp+57h+var_44], 4
0x18000c184  mov     [rbp+57h+var_60], rax
0x18000c188  mov     [rbp+57h+var_40], 0
0x18000c18f  test    rcx, rcx
0x18000c192  jz      short loc_18000C1AD
0x18000c194  xor     r9d, r9d
0x18000c197  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000c19e  xor     r8d, r8d
0x18000c1a1  call    cs:__imp_EtwEventWrite
0x18000c1a8  nop     dword ptr [rax+rax+00h]
0x18000c1ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1b4  lea     rax, WPP_GLOBAL_Control
0x18000c1bb  cmp     rcx, rax
0x18000c1be  jz      short loc_18000C1CA
0x18000c1c0  test    byte ptr [rcx+1Ch], 8
0x18000c1c4  jnz     loc_18000C370
0x18000c1ca  call    cs:__imp_GetTickCount64
0x18000c1d1  nop     dword ptr [rax+rax+00h]
0x18000c1d6  mov     rdx, [rbp+57h+var_60]
0x18000c1da  lea     rax, [rbp+57h+var_40]
0x18000c1de  mov     [rsp+38h], rax
0x18000c1e3  mov     r9d, r15d
0x18000c1e6  lea     rax, [rbp+57h+var_44]
0x18000c1ea  mov     r8d, 3
0x18000c1f0  mov     [rsp+0A0h+var_70], rax
0x18000c1f5  mov     ecx, 1
0x18000c1fa  lea     rax, [rbp+57h+var_48]
0x18000c1fe  mov     [rsp+0A0h+var_78], rax
0x18000c203  mov     dword ptr [rsp+0A0h+var_80], 1
0x18000c20b  call    Int_FWGetOrSetConfig
0x18000c210  mov     r15d, eax
0x18000c213  test    eax, eax
0x18000c215  jnz     short loc_18000C28E
0x18000c217  mov     rcx, cs:g_Provider
0x18000c21e  test    rcx, rcx
0x18000c221  jz      short loc_18000C23C
0x18000c223  xor     r9d, r9d
0x18000c226  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000c22d  xor     r8d, r8d
0x18000c230  call    cs:__imp_EtwEventWrite
0x18000c237  nop     dword ptr [rax+rax+00h]
0x18000c23c  test    r15d, r15d
0x18000c23f  jnz     loc_18000C3C3
0x18000c245  cmp     [rbp+57h+var_48], r15d
0x18000c249  jnz     loc_18000C38A
0x18000c24f  test    r13d, r13d
0x18000c252  jnz     loc_18000C39C
0x18000c258  mov     r13d, 1
0x18000c25e  mov     r14d, r12d
0x18000c261  xor     ebx, ebx
0x18000c263  inc     edi
0x18000c265  jmp     loc_18000C0CC
0x18000c26a  test    byte ptr [rcx+1Ch], 8
0x18000c26e  jz      loc_18000BEE0
0x18000c274  mov     rcx, [rcx+10h]
0x18000c278  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000c27f  mov     edx, 31h ; '1'
0x18000c284  call    WPP_SF_
0x18000c289  jmp     loc_18000BEE0
0x18000c28e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c295  lea     rax, WPP_GLOBAL_Control
0x18000c29c  cmp     rcx, rax
0x18000c29f  jz      loc_18000C217
0x18000c2a5  test    byte ptr [rcx+1Ch], 1
0x18000c2a9  jz      loc_18000C217
0x18000c2af  mov     rcx, [rcx+10h]
0x18000c2b3  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000c2ba  mov     edx, 6Ah ; 'j'
0x18000c2bf  mov     r9d, r15d
0x18000c2c2  call    WPP_SF_d
0x18000c2c7  jmp     loc_18000C217
0x18000c2cc  mov     rcx, [rbp+57h+var_50]
0x18000c2d0  call    FWClosePolicyStore
0x18000c2d5  mov     [rbp+57h+var_50], r15
0x18000c2d9  jmp     loc_18000C07A
0x18000c2de  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x18000c2e5  mov     r8d, eax
0x18000c2e8  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000c2ef  call    cs:__imp_FwReportErrorAsWinError
0x18000c2f6  nop     dword ptr [rax+rax+00h]
0x18000c2fb  mov     ebx, eax
0x18000c2fd  jmp     loc_18000C0EC
0x18000c302  mov     edx, ebx
0x18000c304  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000c30b  call    cs:__imp_FwReportReturnError
0x18000c312  nop     dword ptr [rax+rax+00h]
0x18000c317  jmp     loc_18000C117
0x18000c31c  test    byte ptr [rcx+1Ch], 4
0x18000c320  jz      loc_18000C07A
0x18000c326  mov     rcx, [rcx+10h]
0x18000c32a  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000c331  mov     edx, 32h ; '2'
0x18000c336  call    WPP_SF_
0x18000c33b  jmp     loc_18000C07A
0x18000c340  mov     [rbp+57h+var_48], r15d
0x18000c344  jmp     loc_18000BFEB
0x18000c349  mov     eax, ebx
0x18000c34b  mov     dword ptr [rbp+rax*4+57h+var_38], 1
0x18000c353  jmp     loc_18000BFEB
0x18000c358  mov     [rbp+57h+var_48], 1
0x18000c35f  jmp     loc_18000C03F
0x18000c364  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x18000c36b  jmp     loc_18000C2E5
0x18000c370  mov     rcx, [rcx+10h]
0x18000c374  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000c37b  mov     edx, 69h ; 'i'
0x18000c380  call    WPP_SF_
0x18000c385  jmp     loc_18000C1CA
0x18000c38a  mov     rax, [rbp+57h+var_58]
0x18000c38e  mov     r12d, 2
0x18000c394  mov     [rax], r12d
0x18000c397  jmp     loc_18000C24F
0x18000c39c  cmp     r12d, r14d
0x18000c39f  jz      loc_18000C263
0x18000c3a5  cmp     r14d, 2
0x18000c3a9  jnz     short loc_18000C3B0
0x18000c3ab  mov     r14d, r12d
0x18000c3ae  jmp     short loc_18000C3B9
0x18000c3b0  xor     eax, eax
0x18000c3b2  test    r12d, r12d
0x18000c3b5  cmovz   r14d, eax
0x18000c3b9  mov     ebx, 1
0x18000c3be  jmp     loc_18000C263
0x18000c3c3  mov     r8d, r15d
0x18000c3c6  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x18000c3cd  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000c3d4  call    cs:__imp_FwReportErrorAsWinError
0x18000c3db  nop     dword ptr [rax+rax+00h]
0x18000c3e0  mov     ebx, eax
0x18000c3e2  jmp     loc_18000C0D4
```
