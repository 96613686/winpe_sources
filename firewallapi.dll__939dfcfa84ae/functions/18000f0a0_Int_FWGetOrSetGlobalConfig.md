# Int_FWGetOrSetGlobalConfig

- ea: `0x18000f0a0`
- end: `0x18000fc1d`
- name: `Int_FWGetOrSetGlobalConfig`
- size: `2941`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed70`
- `0x18000ef00`
- `0x180010990`
- `0x180053730`
- `0x180053880`

## callees

- `0x180005e0c`
- `0x18000e750`
- `0x18000ed70`
- `0x18000f0a0`
- `0x180026798`
- `0x180026c9c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180054d58`
- `0x180054db8`
- `0x180055378`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fafe`
- `RPCRT4!RpcExceptionFilter` at `0x18005fafe`
- `RPCRT4!RpcBindingFree` at `0x18000f5fa`
- `RPCRT4!RpcBindingFree` at `0x18000f5fa`
- `fwbase!FwBaseFree` at `0x18000f616`
- `fwbase!FwBaseFree` at `0x18000f616`
- `fwbase!FwHResultToWindowsError` at `0x18000fa13`
- `fwbase!FwHResultToWindowsError` at `0x18000fa75`
- `fwbase!FwHResultToWindowsError` at `0x18000fa13`
- `fwbase!FwHResultToWindowsError` at `0x18000fa75`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000fa67`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000fa67`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000fa05`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000fa05`

## pseudocode

```c
__int64 __fastcall Int_FWGetOrSetGlobalConfig(
        int a1,
        unsigned __int16 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        int *a9,
        _DWORD *a10)
{
  FwPolicy2 *v12; // rsi
  _BYTE *v13; // rbx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // edi
  int v18; // edx
  unsigned int v19; // eax
  int v20; // eax
  __int64 (__fastcall *v21)(int, int, int, int, int, __int64, int, __int64, __int64); // r10
  __int64 (__fastcall *v22)(int, int, int, int, int, __int64, int, __int64, __int64, __int64); // r11
  int v23; // eax
  unsigned int v24; // eax
  _DWORD *v25; // rcx
  __int64 (__fastcall *v26)(int, int, int, int, __int64, int); // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rcx
  bool v32; // zf
  __int64 v34; // rdx
  unsigned int v35; // eax
  unsigned __int16 v36; // ax
  __int64 v37; // r9
  unsigned int v38; // eax
  __int64 v39; // r8
  unsigned int GlobalConfig; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  int v45; // [rsp+A8h] [rbp-B0h] BYREF
  int v46; // [rsp+ACh] [rbp-ACh] BYREF
  __int64 v47; // [rsp+B0h] [rbp-A8h] BYREF
  int v48; // [rsp+B8h] [rbp-A0h] BYREF
  int v49; // [rsp+BCh] [rbp-9Ch] BYREF
  _BYTE v50[4]; // [rsp+C0h] [rbp-98h] BYREF
  int v51; // [rsp+C4h] [rbp-94h]

  v47 = a3;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  memset_0(v50, 0, 0x50u);
  v48 = 0;
  v45 = 0;
  v49 = 0;
  if ( a5 )
  {
    v13 = (_BYTE *)a5;
    a2 = *(_WORD *)(a5 + 2);
    a4 = *(_DWORD *)(a5 + 16);
  }
  else
  {
    v13 = v50;
  }
  if ( (unsigned __int16)(a2 - 512) > 0x21u )
  {
    v17 = 1306;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 254;
LABEL_162:
    v37 = v17;
    goto LABEL_163;
  }
  if ( a4 - 1 > 0xB )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 255;
    goto LABEL_162;
  }
  if ( a4 == 6 && (a7 & 1) != 0 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 256;
    goto LABEL_162;
  }
  if ( (unsigned int)(a6 - 1) > 0x11 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 257;
    goto LABEL_162;
  }
  if ( !a9 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 258;
    goto LABEL_162;
  }
  if ( !a8 && *a9 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 259;
    goto LABEL_162;
  }
  if ( (a7 & 0xFFFFFFFE) != 0 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 260;
    goto LABEL_162;
  }
  if ( a4 <= 0xB && (v14 = 2148, _bittest(&v14, a4)) )
  {
    if ( a6 == 1 )
      goto LABEL_80;
  }
  else if ( a6 == 1 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 261;
    goto LABEL_162;
  }
  if ( a6 != 11 )
  {
    v15 = a1;
    goto LABEL_16;
  }
LABEL_80:
  v15 = a1;
  if ( !a1 )
  {
    v17 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 262;
    goto LABEL_162;
  }
LABEL_16:
  if ( !a5 )
  {
    v16 = Int_FWCreateConnectionHandle(a2, v47, a4, 2 - (unsigned int)(v15 != 0), 0, v13);
    v17 = v16;
    if ( v16 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_95;
      v34 = 263;
      v37 = v16;
      goto LABEL_163;
    }
    v12 = WPP_GLOBAL_Control;
    if ( a2 > 0x200u && *((_DWORD *)v13 + 1) <= 1u )
    {
      v48 = 4;
      v35 = FWGetGlobalConfig(512, v47, 5, 11, 0, (__int64)&v45, (__int64)&v48);
      v17 = v35;
      if ( v35 == 1783 || v35 == 87 )
      {
        v17 = 0;
        v36 = 512;
        v45 = 512;
      }
      else
      {
        v36 = v45;
      }
      if ( v17 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v34 = 264;
        goto LABEL_162;
      }
      if ( a2 > v36 )
        a2 = v36;
      v12 = WPP_GLOBAL_Control;
    }
  }
  v18 = a6;
  if ( a6 >= 12 && a2 < 0x20Au )
  {
    v17 = 50;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 265;
    goto LABEL_162;
  }
  if ( a6 >= 14 && a2 < 0x214u )
  {
    v17 = 50;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 266;
    goto LABEL_162;
  }
  v19 = *((_DWORD *)v13 + 1);
  if ( v19 > 1 )
  {
    if ( v19 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v38 = Int_FWOpenGPOPolicyStore(v13);
    v17 = v38;
    if ( v38 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_95;
      v34 = 270;
      v37 = v38;
      goto LABEL_163;
    }
    if ( !*((_QWORD *)v13 + 6) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !*((_QWORD *)v13 + 5) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v39 = *((_QWORD *)v13 + 6);
    if ( a1 )
    {
      GlobalConfig = FwGetGlobalConfig(a2, a4, v39, (unsigned int)a6, a8, a9);
      v41 = FwHResultToWindowsError(GlobalConfig);
      v17 = v41;
      if ( v41 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v34 = 271;
        v37 = v41;
        goto LABEL_163;
      }
    }
    else
    {
      v42 = FwSetGlobalConfig(a2, a4, v39, (unsigned int)a6, a8, *a9);
      v43 = FwHResultToWindowsError(v42);
      v17 = v43;
      if ( v43 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v34 = 272;
        v37 = v43;
        goto LABEL_163;
      }
    }
    v44 = Int_FWCloseGPOPolicyStore(v13, a1 == 0);
    v17 = v44;
    if ( !v44 )
      goto LABEL_164;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_95;
    v34 = 273;
    v37 = v44;
LABEL_163:
    WPP_SF_d(*((_QWORD *)v12 + 2), v34, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v37);
LABEL_164:
    v12 = WPP_GLOBAL_Control;
LABEL_95:
    v25 = a10;
    goto LABEL_57;
  }
  if ( !*((_QWORD *)v13 + 4) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = a6;
  }
  if ( a1 )
  {
    v46 = 0;
    LODWORD(v47) = 0;
    v20 = *((_DWORD *)v13 + 1);
    v21 = RPC_FWGetGlobalConfig;
    if ( v20 )
      v21 = RRPC_FWGetGlobalConfig;
    v22 = RPC_FWGetGlobalConfig2_10;
    if ( v20 )
      v22 = RRPC_FWGetGlobalConfig2_10;
    v23 = *a9;
    if ( a2 >= 0x20Au )
      v24 = v22(*((_QWORD *)v13 + 4), a2, a4, v18, a7, a8, v23, (__int64)&v46, (__int64)&v47, (__int64)&v49);
    else
      v24 = v21(*((_QWORD *)v13 + 4), a2, a4, v18, a7, a8, v23, (__int64)&v46, (__int64)&v47);
    v17 = v24;
    if ( !v24 )
    {
      *a9 = v46;
LABEL_33:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    if ( v24 == 234 )
    {
      *a9 = v47;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v28 = 275;
LABEL_55:
        WPP_SF_d(*((_QWORD *)v12 + 2), v28, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v24);
        goto LABEL_33;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v28 = 276;
        goto LABEL_55;
      }
    }
LABEL_34:
    if ( v17 )
    {
      if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v12 + 2), 267, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
        v12 = WPP_GLOBAL_Control;
      }
      v25 = a10;
      goto LABEL_57;
    }
LABEL_56:
    v25 = a10;
    goto LABEL_57;
  }
  v26 = RRPC_FWSetGlobalConfig;
  if ( !v51 )
    v26 = RPC_FWSetGlobalConfig;
  v27 = v26(*((_QWORD *)v13 + 4), a2, a4, v18, a8, *a9);
  v17 = v27;
  if ( !v27 )
  {
    v12 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v27);
    v12 = WPP_GLOBAL_Control;
  }
  v25 = a10;
LABEL_57:
  if ( v25 )
  {
    *v25 = v49;
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a5 )
  {
    if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v12 + 2), 377, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v13 )
    {
      v29 = *((_DWORD *)v13 + 1);
      if ( v29 > 1 )
      {
        if ( v29 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        Int_FWCleanupGPOPolicyStore(v13);
      }
      else if ( *((_QWORD *)v13 + 4) )
      {
        v30 = RpcBindingFree((RPC_BINDING_HANDLE *)v13 + 4);
        if ( v30 )
          MicrosoftTelemetryAssertTriggeredArgs(v31, v30);
        *((_QWORD *)v13 + 4) = 0;
      }
      FwBaseFree(*((_QWORD *)v13 + 1));
      *((_QWORD *)v13 + 1) = 0;
      v12 = WPP_GLOBAL_Control;
    }
  }
  v32 = a2 == 545;
  if ( a2 < 0x221u )
  {
    if ( v17 == 1783 && !a1 )
    {
      v17 = 50;
      goto LABEL_74;
    }
    v32 = a2 == 545;
  }
  if ( v32 && v17 == 1783 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v12 = WPP_GLOBAL_Control;
  }
LABEL_74:
  if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v12 + 2), 274, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  return v17;
}

```

## disassembly

```asm
0x18000f0a0  mov     [rsp+arg_0], ecx
0x18000f0a4  push    rbx
0x18000f0a5  push    rsi
0x18000f0a6  push    rdi
0x18000f0a7  push    r12
0x18000f0a9  push    r13
0x18000f0ab  push    r14
0x18000f0ad  push    r15
0x18000f0af  sub     rsp, 120h
0x18000f0b6  mov     rax, cs:__security_cookie
0x18000f0bd  xor     rax, rsp
0x18000f0c0  mov     [rsp+158h+var_48], rax
0x18000f0c8  mov     r13d, r9d
0x18000f0cb  mov     [rsp+158h+var_A8], r8
0x18000f0d3  movzx   r14d, dx
0x18000f0d7  mov     [rsp+158h+var_F0], dx
0x18000f0dc  mov     r12, [rsp+158h+arg_20]
0x18000f0e4  mov     [rsp+158h+var_C0], r12
0x18000f0ec  mov     rax, [rsp+158h+arg_38]
0x18000f0f4  mov     [rsp+158h+var_E0], rax
0x18000f0f9  mov     rdi, [rsp+158h+arg_40]
0x18000f101  mov     [rsp+158h+var_D0], rdi
0x18000f109  mov     rax, [rsp+158h+arg_48]
0x18000f111  mov     [rsp+158h+var_F8], rax
0x18000f116  mov     [rsp+158h+var_B8], rax
0x18000f11e  lea     rax, WPP_GLOBAL_Control
0x18000f125  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f12c  cmp     rsi, rax
0x18000f12f  jnz     loc_18000F683
0x18000f135  xor     edx, edx; Val
0x18000f137  mov     r8d, 50h ; 'P'; Size
0x18000f13d  lea     rcx, [rsp+158h+var_98]; void *
0x18000f145  call    memset_0
0x18000f14a  xor     r15d, r15d
0x18000f14d  mov     [rsp+158h+var_A0], r15d
0x18000f155  mov     [rsp+158h+var_B0], r15d
0x18000f15d  mov     [rsp+158h+var_9C], r15d
0x18000f165  test    r12, r12
0x18000f168  jnz     loc_18000F807
0x18000f16e  lea     rbx, [rsp+158h+var_98]
0x18000f176  mov     [rsp+158h+var_C8], rbx
0x18000f17e  mov     edx, 200h
0x18000f183  movzx   eax, r14w
0x18000f187  sub     ax, dx
0x18000f18a  cmp     ax, 21h ; '!'
0x18000f18e  ja      loc_18000F759
0x18000f194  lea     eax, [r13-1]
0x18000f198  cmp     eax, 0Bh
0x18000f19b  ja      loc_18000FB3E
0x18000f1a1  mov     r8d, [rsp+158h+arg_30]
0x18000f1a9  cmp     r13d, 6
0x18000f1ad  jz      loc_18000F820
0x18000f1b3  mov     ecx, [rsp+158h+arg_28]
0x18000f1ba  lea     eax, [rcx-1]
0x18000f1bd  cmp     eax, 11h
0x18000f1c0  ja      loc_18000FB18
0x18000f1c6  test    rdi, rdi
0x18000f1c9  jz      loc_18000F853
0x18000f1cf  cmp     [rsp+158h+var_E0], r15
0x18000f1d4  jz      loc_18000F87C
0x18000f1da  test    r8d, 0FFFFFFFEh
0x18000f1e1  jnz     loc_18000F8AE
0x18000f1e7  cmp     r13d, 0Bh
0x18000f1eb  ja      loc_18000F8D7
0x18000f1f1  mov     eax, 864h
0x18000f1f6  bt      eax, r13d
0x18000f1fa  jnb     loc_18000F8D7
0x18000f200  cmp     ecx, 1
0x18000f203  jz      loc_18000F6AE
0x18000f209  cmp     ecx, 0Bh
0x18000f20c  jz      loc_18000F6AE
0x18000f212  mov     eax, [rsp+158h+arg_0]
0x18000f219  test    r12, r12
0x18000f21c  jnz     short loc_18000F26A
0x18000f21e  neg     eax
0x18000f220  sbb     r9d, r9d
0x18000f223  add     r9d, 2
0x18000f227  mov     [rsp+158h+var_130], rbx
0x18000f22c  mov     dword ptr [rsp+158h+var_138], r15d
0x18000f231  mov     r8d, r13d
0x18000f234  mov     rdx, [rsp+158h+var_A8]
0x18000f23c  movzx   ecx, r14w
0x18000f240  call    Int_FWCreateConnectionHandle
0x18000f245  mov     edi, eax
0x18000f247  test    eax, eax
0x18000f249  jnz     loc_18000F908
0x18000f24f  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f256  mov     edx, 200h
0x18000f25b  test    r12, r12
0x18000f25e  jnz     short loc_18000F26A
0x18000f260  cmp     r14w, dx
0x18000f264  ja      loc_18000F778
0x18000f26a  mov     edi, 20Ah
0x18000f26f  mov     edx, [rsp+158h+arg_28]
0x18000f276  cmp     edx, 0Ch
0x18000f279  jge     loc_18000F72E
0x18000f27f  mov     eax, 214h
0x18000f284  cmp     edx, 0Eh
0x18000f287  jge     loc_18000F703
0x18000f28d  mov     eax, [rbx+4]
0x18000f290  cmp     eax, 1
0x18000f293  ja      loc_18000F975
0x18000f299  cmp     [rbx+20h], r15
0x18000f29d  jz      loc_18000FB07
0x18000f2a3  mov     rsi, [rsp+158h+var_D0]
0x18000f2ab  mov     r9d, edx
0x18000f2ae  mov     r8d, r13d
0x18000f2b1  movzx   edx, r14w
0x18000f2b5  cmp     [rsp+158h+arg_0], 0
0x18000f2bd  jz      loc_18000F3B4
0x18000f2c3  mov     [rsp+158h+var_E8], r15d
0x18000f2c8  mov     [rsp+158h+var_AC], r15d
0x18000f2d0  mov     dword ptr [rsp+158h+var_A8], r15d
0x18000f2d8  mov     eax, [rbx+4]
0x18000f2db  lea     r10, RPC_FWGetGlobalConfig
0x18000f2e2  lea     rcx, RRPC_FWGetGlobalConfig
0x18000f2e9  test    eax, eax
0x18000f2eb  cmovnz  r10, rcx
0x18000f2ef  lea     r11, RPC_FWGetGlobalConfig2_10
0x18000f2f6  lea     rcx, RRPC_FWGetGlobalConfig2_10
0x18000f2fd  cmovnz  r11, rcx
0x18000f301  mov     eax, [rsi]
0x18000f303  cmp     r14w, di
0x18000f307  jnb     loc_18000F449
0x18000f30d  lea     rcx, [rsp+158h+var_A8]
0x18000f315  mov     [rsp+158h+var_118], rcx
0x18000f31a  lea     rcx, [rsp+158h+var_AC]
0x18000f322  mov     [rsp+158h+var_120], rcx
0x18000f327  mov     dword ptr [rsp+158h+var_128], eax
0x18000f32b  mov     rax, [rsp+158h+var_E0]
0x18000f330  mov     [rsp+158h+var_130], rax
0x18000f335  mov     eax, [rsp+158h+arg_30]
0x18000f33c  mov     dword ptr [rsp+158h+var_138], eax
0x18000f340  mov     rcx, [rbx+20h]
0x18000f344  mov     rax, r10
0x18000f347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f34c  mov     [rsp+158h+var_E8], eax
0x18000f350  mov     edi, eax
0x18000f352  test    eax, eax
0x18000f354  jnz     loc_18000F49A
0x18000f35a  mov     eax, [rsp+158h+var_AC]
0x18000f361  mov     [rsi], eax
0x18000f363  lea     r13, WPP_GLOBAL_Control
0x18000f36a  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f371  mov     [rsp+158h+var_D8], edi
0x18000f378  test    edi, edi
0x18000f37a  jz      loc_18000F519
0x18000f380  cmp     rsi, r13
0x18000f383  jz      short loc_18000F3AA
0x18000f385  test    byte ptr [rsi+1Ch], 1
0x18000f389  jz      short loc_18000F3AA
0x18000f38b  mov     edx, 10Bh
0x18000f390  mov     r9d, edi
0x18000f393  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f39a  mov     rcx, [rsi+10h]
0x18000f39e  call    WPP_SF_d
0x18000f3a3  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f3aa  mov     rcx, [rsp+158h+var_F8]
0x18000f3af  jmp     loc_18000F5C1
0x18000f3b4  lea     rax, RRPC_FWSetGlobalConfig
0x18000f3bb  lea     rcx, RPC_FWSetGlobalConfig
0x18000f3c2  cmp     [rsp+158h+var_94], 0
0x18000f3ca  cmovz   rax, rcx
0x18000f3ce  mov     ecx, [rsi]
0x18000f3d0  mov     dword ptr [rsp+158h+var_130], ecx
0x18000f3d4  mov     rcx, [rsp+158h+var_E0]
0x18000f3d9  mov     [rsp+158h+var_138], rcx
0x18000f3de  mov     rcx, [rbx+20h]
0x18000f3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3e7  mov     edi, eax
0x18000f3e9  mov     [rsp+158h+var_D8], eax
0x18000f3f0  test    eax, eax
0x18000f3f2  jz      short loc_18000F436
0x18000f3f4  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f3fb  lea     r13, WPP_GLOBAL_Control
0x18000f402  cmp     rsi, r13
0x18000f405  jz      short loc_18000F42C
0x18000f407  test    byte ptr [rsi+1Ch], 1
0x18000f40b  jz      short loc_18000F42C
0x18000f40d  mov     edx, 10Ch
0x18000f412  mov     r9d, eax
0x18000f415  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f41c  mov     rcx, [rsi+10h]
0x18000f420  call    WPP_SF_d
0x18000f425  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f42c  mov     rcx, [rsp+158h+var_F8]
0x18000f431  jmp     loc_18000F5C1
0x18000f436  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f43d  lea     r13, WPP_GLOBAL_Control
0x18000f444  jmp     loc_18000F519
0x18000f449  lea     rcx, [rsp+158h+var_9C]
0x18000f451  mov     [rsp+158h+var_110], rcx
0x18000f456  lea     rcx, [rsp+158h+var_A8]
0x18000f45e  mov     [rsp+158h+var_118], rcx
0x18000f463  lea     rcx, [rsp+158h+var_AC]
0x18000f46b  mov     [rsp+158h+var_120], rcx
0x18000f470  mov     dword ptr [rsp+158h+var_128], eax
0x18000f474  mov     rax, [rsp+158h+var_E0]
0x18000f479  mov     [rsp+158h+var_130], rax
0x18000f47e  mov     eax, [rsp+158h+arg_30]
0x18000f485  mov     dword ptr [rsp+158h+var_138], eax
0x18000f489  mov     rcx, [rbx+20h]
0x18000f48d  mov     rax, r11
0x18000f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f495  jmp     loc_18000F34C
0x18000f49a  cmp     edi, 0EAh
0x18000f4a0  jnz     short loc_18000F4D7
0x18000f4a2  mov     eax, dword ptr [rsp+158h+var_A8]
0x18000f4a9  mov     [rsi], eax
0x18000f4ab  mov     [rsp+158h+var_E8], edi
0x18000f4af  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f4b6  lea     r13, WPP_GLOBAL_Control
0x18000f4bd  cmp     rsi, r13
0x18000f4c0  jz      loc_18000F371
0x18000f4c6  test    byte ptr [rsi+1Ch], 1
0x18000f4ca  jz      loc_18000F371
0x18000f4d0  mov     edx, 113h
0x18000f4d5  jmp     short loc_18000F501
0x18000f4d7  mov     [rsp+158h+var_E8], edi
0x18000f4db  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f4e2  lea     r13, WPP_GLOBAL_Control
0x18000f4e9  cmp     rsi, r13
0x18000f4ec  jz      loc_18000F371
0x18000f4f2  test    byte ptr [rsi+1Ch], 1
0x18000f4f6  jz      loc_18000F371
0x18000f4fc  mov     edx, 114h
0x18000f501  mov     r9d, edi
0x18000f504  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f50b  mov     rcx, [rsi+10h]
0x18000f50f  call    WPP_SF_d
0x18000f514  jmp     loc_18000F36A
0x18000f519  mov     rcx, [rsp+158h+var_F8]
0x18000f51e  jmp     loc_18000F5C1
0x18000f523  mov     edi, eax
0x18000f525  mov     [rsp+158h+var_D8], eax
0x18000f52c  test    eax, eax
0x18000f52e  jz      short loc_18000F592
0x18000f530  lea     rax, WPP_GLOBAL_Control
0x18000f537  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f53e  cmp     rsi, rax
0x18000f541  jz      short loc_18000F568
0x18000f543  test    byte ptr [rsi+1Ch], 1
0x18000f547  jz      short loc_18000F568
0x18000f549  mov     edx, 10Dh
0x18000f54e  mov     r9d, edi
0x18000f551  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f558  mov     rcx, [rsi+10h]
0x18000f55c  call    WPP_SF_d
0x18000f561  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f568  lea     r13, WPP_GLOBAL_Control
0x18000f56f  xor     r15d, r15d
0x18000f572  mov     rbx, [rsp+158h+var_C8]
0x18000f57a  movzx   r14d, [rsp+158h+var_F0]
0x18000f580  mov     r12, [rsp+158h+var_C0]
0x18000f588  mov     rcx, [rsp+158h+var_B8]
0x18000f590  jmp     short loc_18000F5C1
0x18000f592  lea     r13, WPP_GLOBAL_Control
0x18000f599  xor     r15d, r15d
0x18000f59c  mov     rbx, [rsp+158h+var_C8]
0x18000f5a4  movzx   r14d, [rsp+158h+var_F0]
0x18000f5aa  mov     r12, [rsp+158h+var_C0]
0x18000f5b2  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f5b9  mov     rcx, [rsp+158h+var_B8]
0x18000f5c1  test    rcx, rcx
0x18000f5c4  jnz     loc_18000FB92
0x18000f5ca  test    r12, r12
0x18000f5cd  jnz     short loc_18000F62D
0x18000f5cf  cmp     rsi, r13
0x18000f5d2  jz      short loc_18000F5DE
0x18000f5d4  test    byte ptr [rsi+1Ch], 8
0x18000f5d8  jnz     loc_18000FBA7
0x18000f5de  test    rbx, rbx
0x18000f5e1  jz      short loc_18000F62D
0x18000f5e3  mov     eax, [rbx+4]
0x18000f5e6  cmp     eax, 1
0x18000f5e9  ja      loc_18000FBC8
0x18000f5ef  cmp     qword ptr [rbx+20h], 0
0x18000f5f4  jz      short loc_18000F612
0x18000f5f6  lea     rcx, [rbx+20h]; Binding
0x18000f5fa  call    cs:__imp_RpcBindingFree
0x18000f601  nop     dword ptr [rax+rax+00h]
0x18000f606  test    eax, eax
0x18000f608  jnz     loc_18000FBDF
0x18000f60e  mov     [rbx+20h], r15
0x18000f612  mov     rcx, [rbx+8]
0x18000f616  call    cs:__imp_FwBaseFree
0x18000f61d  nop     dword ptr [rax+rax+00h]
0x18000f622  mov     [rbx+8], r15
0x18000f626  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f62d  mov     eax, 221h
0x18000f632  cmp     r14w, ax
0x18000f636  jnb     short loc_18000F648
0x18000f638  cmp     edi, 6F7h
0x18000f63e  jz      loc_18000FBEB
0x18000f644  cmp     r14w, ax
0x18000f648  jz      loc_18000F6E6
0x18000f64e  cmp     rsi, r13
0x18000f651  jz      short loc_18000F65D
0x18000f653  test    byte ptr [rsi+1Ch], 8
0x18000f657  jnz     loc_18000FC03
  ... truncated ...
```
