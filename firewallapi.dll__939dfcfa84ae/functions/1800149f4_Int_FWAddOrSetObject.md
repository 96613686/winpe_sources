# Int_FWAddOrSetObject

- ea: `0x1800149f4`
- end: `0x180015642`
- name: `Int_FWAddOrSetObject`
- size: `3150`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, void *Src)`
- caller_count: `10`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014110`
- `0x180014720`
- `0x18004dbc0`
- `0x18004dd60`
- `0x18004df00`
- `0x18004e3c0`
- `0x180053270`
- `0x180053410`
- `0x1800535b0`
- `0x1800541c0`

## callees

- `0x180005e0c`
- `0x1800149f4`
- `0x180015648`
- `0x180026798`
- `0x180026c9c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180054d58`
- `0x180054db8`
- `0x180055378`
- `0x18005f898`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fb4e`
- `RPCRT4!RpcExceptionFilter` at `0x18005fb4e`
- `fwbase!Int_FwValidateComplianceAndReduceFirewallRuleToVersion` at `0x180014e79`
- `fwbase!Int_FwValidateComplianceAndReduceCryptoSetToVersion` at `0x180014f5d`
- `fwbase!Int_FwValidateComplianceAndReduceAuthSetToVersion` at `0x180015094`
- `fwbase!Int_FwValidateComplianceAndReduceMainModeRuleToVersion` at `0x180014b5d`
- `fwbase!Int_FwValidateComplianceAndReduceConnSecRuleToVersion` at `0x1800150ff`
- `fwbase!FwHResultToWindowsError` at `0x180014f9a`
- `fwbase!FwHResultToWindowsError` at `0x1800152bb`
- `fwbase!FwHResultToWindowsError` at `0x180015332`
- `fwbase!FwHResultToWindowsError` at `0x180014f9a`
- `fwbase!FwHResultToWindowsError` at `0x1800152bb`
- `fwbase!FwHResultToWindowsError` at `0x180015332`
- `FWPolicyIOMgr!FwAddRule` at `0x180015307`
- `FWPolicyIOMgr!FwCopyMMRule` at `0x180014b56`
- `FWPolicyIOMgr!FwCopyRule` at `0x180014e72`
- `FWPolicyIOMgr!FwSetRule` at `0x1800152fc`
- `FWPolicyIOMgr!FwSetSet` at `0x180015284`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800155dd`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800155dd`
- `FWPolicyIOMgr!FwAddSet` at `0x18001528f`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x180014f8c`
- `FWPolicyIOMgr!FwCopyAuthsetToHigherVersion` at `0x180014f8c`
- `FWPolicyIOMgr!FwFreeSets` at `0x180015486`
- `FWPolicyIOMgr!FwFreeSets` at `0x18001549c`
- `FWPolicyIOMgr!FwFreeSets` at `0x180015486`
- `FWPolicyIOMgr!FwFreeSets` at `0x18001549c`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180015502`
- `FWPolicyIOMgr!FwDownlevelAuthSetFree` at `0x180015502`
- `FWPolicyIOMgr!FwCopyCSRule` at `0x1800150f8`
- `FWPolicyIOMgr!FwCopyCryptoSet` at `0x180014f56`

## pseudocode

```c
__int64 __fastcall Int_FWAddOrSetObject(
        unsigned int a1,
        int a2,
        __int64 (__fastcall *a3)(_QWORD, __int128 *),
        _QWORD *a4,
        _QWORD *a5,
        unsigned __int16 *a6,
        _OWORD *Src)
{
  FwPolicy2 *v8; // rbx
  __int128 *v9; // rax
  __int128 *v10; // rcx
  __int64 v11; // rdx
  size_t v12; // rbx
  __int64 v13; // r13
  unsigned int SvrCompatibleObject; // esi
  _QWORD *v15; // r10
  unsigned int v16; // edx
  unsigned int v17; // ecx
  __int128 *v18; // r8
  __int64 v19; // rdx
  unsigned __int16 *v20; // r8
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // xmm1_8
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(_QWORD, bool, _QWORD, __int128 *); // rax
  unsigned int v28; // eax
  __int64 (__fastcall *v29)(_QWORD, __int64, __int128 *); // rax
  __int64 v30; // rdx
  unsigned int v31; // eax
  int v32; // ecx
  int v33; // eax
  __int64 v34; // rdx
  __int128 *v35; // rcx
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  __int64 v40; // rdx
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  unsigned __int16 *v46; // [rsp+48h] [rbp-2C0h]
  _DWORD v48[2]; // [rsp+60h] [rbp-2A8h] BYREF
  _QWORD *v49; // [rsp+68h] [rbp-2A0h]
  unsigned __int16 *v50; // [rsp+70h] [rbp-298h]
  _OWORD *v51; // [rsp+80h] [rbp-288h]
  __int64 (__fastcall *v52)(_QWORD, __int128 *); // [rsp+88h] [rbp-280h]
  _QWORD *v53; // [rsp+90h] [rbp-278h]
  __int128 *v54; // [rsp+98h] [rbp-270h] BYREF
  __int128 *v55; // [rsp+A0h] [rbp-268h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-258h] BYREF
  __int128 v57; // [rsp+C0h] [rbp-248h]
  __int128 v58; // [rsp+D0h] [rbp-238h]
  __int128 v59; // [rsp+E0h] [rbp-228h]
  __int128 v60; // [rsp+F0h] [rbp-218h]
  __int64 v61; // [rsp+100h] [rbp-208h]
  __int64 v62; // [rsp+108h] [rbp-200h]
  __int64 v63; // [rsp+1A8h] [rbp-160h]
  int v64; // [rsp+1B0h] [rbp-158h]
  int v65; // [rsp+200h] [rbp-108h]
  __int64 v66; // [rsp+208h] [rbp-100h]
  __int64 v67; // [rsp+228h] [rbp-E0h]
  int v68; // [rsp+230h] [rbp-D8h]
  int v69; // [rsp+2C0h] [rbp-48h] BYREF

  v53 = a4;
  v52 = a3;
  v49 = a5;
  v51 = Src;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v54 = 0;
  v69 = 0x10000;
  v55 = 0;
  v48[0] = 0;
  *(_QWORD *)&v56 = 0;
  memset_0((char *)&v56 + 8, 0, 0x200u);
  if ( !a6 || !Src )
  {
    v20 = 0;
    v46 = 0;
    SvrCompatibleObject = 87;
    if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 300, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
      v8 = WPP_GLOBAL_Control;
      v20 = 0;
    }
    goto LABEL_38;
  }
  v46 = a6;
  v50 = a6;
  switch ( a1 )
  {
    case 0u:
      if ( *a6 >= 0x20Au )
      {
        if ( *a6 >= 0x214u )
        {
          if ( *a6 >= 0x218u )
          {
            if ( *a6 >= 0x219u )
            {
              if ( *a6 >= 0x21Au )
              {
                if ( *a6 >= 0x21Bu )
                {
                  if ( *a6 >= 0x21Fu )
                  {
                    v12 = 504;
                    if ( *a6 < 0x221u )
                      v12 = 496;
                  }
                  else
                  {
                    v12 = 464;
                  }
                }
                else
                {
                  v12 = 448;
                }
              }
              else
              {
                v12 = 432;
              }
            }
            else
            {
              v12 = 424;
            }
          }
          else
          {
            v12 = 400;
          }
        }
        else
        {
          v12 = 368;
        }
      }
      else
      {
        v12 = 360;
      }
      memset_0(&v56, 0, 0x1F8u);
      memcpy_0(&v56, Src, v12);
      v66 = 0;
      LODWORD(v12) = (_DWORD)FwCopyRule;
      v13 = Int_FwValidateComplianceAndReduceFirewallRuleToVersion;
      goto LABEL_10;
    case 1u:
      if ( *a6 >= 0x20Au )
        v12 = (-(__int64)(*a6 < 0x214u) & 0xFFFFFFFFFFFFFF98uLL) + 520;
      else
        v12 = 392;
      memset_0(&v56, 0, 0x208u);
      memcpy_0(&v56, Src, v12);
      v67 = 0;
      LODWORD(v12) = FwCopyCSRule;
      v13 = Int_FwValidateComplianceAndReduceConnSecRuleToVersion;
      goto LABEL_10;
    case 2u:
      v9 = Src;
      v10 = &v56;
      v11 = 2;
      do
      {
        *v10 = *v9;
        v10[1] = v9[1];
        v10[2] = v9[2];
        v10[3] = v9[3];
        v10[4] = v9[4];
        v10[5] = v9[5];
        v10[6] = v9[6];
        v10[7] = v9[7];
        v10 += 8;
        v9 += 8;
        --v11;
      }
      while ( v11 );
      *v10 = *v9;
      v63 = 0;
      LODWORD(v12) = FwCopyMMRule;
      v13 = Int_FwValidateComplianceAndReduceMainModeRuleToVersion;
      goto LABEL_10;
    case 3u:
      if ( *a6 >= 0x214u )
      {
        v56 = *Src;
        v57 = Src[1];
        v58 = Src[2];
        v59 = Src[3];
        v60 = Src[4];
        v24 = *((_QWORD *)Src + 10);
      }
      else
      {
        v23 = FwCopyAuthsetToHigherVersion(522, Src, &v55);
        SvrCompatibleObject = FwHResultToWindowsError(v23);
        if ( SvrCompatibleObject )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              301,
              WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
              SvrCompatibleObject);
            v8 = WPP_GLOBAL_Control;
          }
          v20 = a6;
          goto LABEL_38;
        }
        v56 = *v55;
        v57 = v55[1];
        v58 = v55[2];
        v59 = v55[3];
        v60 = v55[4];
        v24 = *((_QWORD *)v55 + 10);
      }
      v61 = v24;
      *((_QWORD *)&v60 + 1) = 0;
      v12 = (size_t)FwCopyAuthSet;
      v13 = Int_FwValidateComplianceAndReduceAuthSetToVersion;
      goto LABEL_10;
    case 4u:
      v56 = *Src;
      v57 = Src[1];
      v58 = Src[2];
      v59 = Src[3];
      v60 = Src[4];
      v62 = *((_QWORD *)Src + 11);
      v61 = 0;
      LODWORD(v12) = FwCopyCryptoSet;
      v13 = Int_FwValidateComplianceAndReduceCryptoSetToVersion;
LABEL_10:
      *(_QWORD *)&v56 = 0;
      goto LABEL_11;
  }
  LODWORD(v12) = 0;
  v13 = 0;
  MicrosoftTelemetryAssertTriggeredArgs(a1 - 3, a1);
LABEL_11:
  SvrCompatibleObject = v52(*a6, &v56);
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 302;
    goto LABEL_82;
  }
  if ( *((_DWORD *)a6 + 1) > 1u )
  {
    if ( *((_DWORD *)a6 + 1) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    SvrCompatibleObject = Int_FWOpenGPOPolicyStore(a6);
    if ( SvrCompatibleObject )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 308;
      goto LABEL_82;
    }
    if ( !*((_QWORD *)a6 + 7) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( a1 <= 2 )
    {
      v29 = (__int64 (__fastcall *)(_QWORD, __int64, __int128 *))FwSetRule;
      if ( a2 )
        v29 = (__int64 (__fastcall *)(_QWORD, __int64, __int128 *))FwAddRule;
      v30 = 0;
      if ( a1 )
      {
        LOBYTE(v30) = a1 != 1;
        v30 = (unsigned int)(v30 + 1);
      }
      v31 = v29(*((_QWORD *)a6 + 7), v30, &v56);
      SvrCompatibleObject = FwHResultToWindowsError(v31);
      if ( !SvrCompatibleObject )
        goto LABEL_96;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 309;
    }
    else
    {
      v26 = a1 - 3;
      if ( (unsigned int)v26 >= 2 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(v26, a1);
LABEL_96:
        SvrCompatibleObject = Int_FWCloseGPOPolicyStore(a6, 1);
        if ( !SvrCompatibleObject )
          goto LABEL_84;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v22 = 311;
        goto LABEL_82;
      }
      v27 = (__int64 (__fastcall *)(_QWORD, bool, _QWORD, __int128 *))FwSetSet;
      if ( a2 )
        v27 = (__int64 (__fastcall *)(_QWORD, bool, _QWORD, __int128 *))FwAddSet;
      v28 = v27(*((_QWORD *)a6 + 7), a1 != 3, HIDWORD(v56), &v56);
      SvrCompatibleObject = FwHResultToWindowsError(v28);
      if ( !SvrCompatibleObject )
        goto LABEL_96;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v22 = 310;
    }
LABEL_82:
    v25 = SvrCompatibleObject;
LABEL_83:
    WPP_SF_d(*((_QWORD *)v8 + 2), v22, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v25);
LABEL_84:
    v8 = WPP_GLOBAL_Control;
LABEL_37:
    v20 = a6;
LABEL_38:
    v19 = a1;
    goto LABEL_32;
  }
  if ( !*((_QWORD *)a6 + 4) || !*((_QWORD *)a6 + 5) )
  {
    v25 = 87;
    SvrCompatibleObject = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 303;
    goto LABEL_83;
  }
  v15 = v53;
  if ( *((_DWORD *)a6 + 1) )
    v15 = v49;
  v16 = *(_DWORD *)v15;
  if ( *(_DWORD *)v15 )
  {
    v17 = 0;
    do
    {
      if ( *(_WORD *)(v15[1] + 16LL * v17 + 8) > a6[1] )
        break;
      v16 = v17++;
    }
    while ( v17 < *(_DWORD *)v15 );
  }
  if ( v16 == *(_DWORD *)v15 || (v49 = *(_QWORD **)(v15[1] + 16LL * v16)) == 0 )
  {
    SvrCompatibleObject = 50;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 304;
    goto LABEL_82;
  }
  SvrCompatibleObject = Int_FwMakeSvrCompatibleObject(
                          (unsigned int)&v56,
                          (unsigned int)&v54,
                          a6[24],
                          v12,
                          v13,
                          a6[1],
                          a1,
                          (__int64)v48);
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v22 = 305;
    goto LABEL_82;
  }
  v18 = &v56;
  if ( v54 )
    v18 = v54;
  SvrCompatibleObject = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *, int *))v49)(
                          *((_QWORD *)a6 + 4),
                          *((_QWORD *)a6 + 5),
                          v18,
                          &v69);
  v48[1] = SvrCompatibleObject;
  if ( SvrCompatibleObject )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        306,
        WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
        SvrCompatibleObject);
      v8 = WPP_GLOBAL_Control;
    }
    v19 = a1;
    v20 = a6;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    v19 = a1;
    v20 = a6;
  }
LABEL_32:
  if ( a6 && Src )
  {
    if ( (_DWORD)v19 )
    {
      if ( (_DWORD)v19 == 1 )
      {
        v41 = v69;
        v42 = v69;
        if ( v69 == 0x10000 )
          v42 = v68;
        *((_DWORD *)Src + 96) = v42;
        if ( !v54 )
          goto LABEL_167;
        if ( v41 == 0x10000 )
          *((_DWORD *)Src + 96) = 0x20000;
        v40 = 1;
      }
      else
      {
        if ( (_DWORD)v19 != 2 )
        {
          if ( (_DWORD)v19 == 3 )
          {
            v36 = v69;
            v37 = v69;
            if ( v69 == 0x10000 )
              v37 = v61;
            *((_DWORD *)Src + 20) = v37;
            if ( v54 )
            {
              if ( v36 == 0x10000 && (v20[1] >= 0x214u || v48[0] == 1) )
                *((_DWORD *)Src + 20) = 0x20000;
              if ( v20[1] >= 0x214u )
                FwFreeSets(v54, 0);
              else
                FwDownlevelAuthSetFree(522, v54);
            }
            v34 = 0;
            v35 = v55;
          }
          else
          {
            if ( (_DWORD)v19 != 4 )
            {
              MicrosoftTelemetryAssertTriggeredArgs((unsigned int)(v19 - 3), v19);
LABEL_167:
              v8 = WPP_GLOBAL_Control;
              goto LABEL_33;
            }
            v32 = v69;
            v33 = v69;
            if ( v69 == 0x10000 )
              v33 = v62;
            *((_DWORD *)Src + 22) = v33;
            if ( !v54 )
              goto LABEL_167;
            if ( v32 == 0x10000 )
              *((_DWORD *)Src + 22) = 0x20000;
            v34 = 1;
            v35 = v54;
          }
          FwFreeSets(v35, v34);
          goto LABEL_167;
        }
        v38 = v69;
        v39 = v69;
        if ( v69 == 0x10000 )
          v39 = v64;
        *((_DWORD *)Src + 64) = v39;
        if ( !v54 )
          goto LABEL_167;
        if ( v38 == 0x10000 )
          *((_DWORD *)Src + 64) = 0x20000;
        v40 = 2;
      }
    }
    else
    {
      v43 = v69;
      v44 = v69;
      if ( v69 == 0x10000 )
        v44 = v65;
      *((_DWORD *)Src + 84) = v44;
      if ( !v54 )
        goto LABEL_167;
      if ( v43 == 0x10000 )
        *((_DWORD *)Src + 84) = 0x20000;
      v40 = 0;
    }
    FwFreeRules(v54, v40);
    goto LABEL_167;
  }
LABEL_33:
  if ( SvrCompatibleObject && v46 && *((_DWORD *)v46 + 1) == 2 )
  {
    Int_FWCleanupGPOPolicyStore(v46);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v8 + 2), 312, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  return SvrCompatibleObject;
}

```

## disassembly

```asm
0x1800149f4  push    rbx
0x1800149f6  push    rsi
0x1800149f7  push    rdi
0x1800149f8  push    r12
0x1800149fa  push    r13
0x1800149fc  push    r14
0x1800149fe  push    r15
0x180014a00  sub     rsp, 2D0h
0x180014a07  mov     rax, cs:__security_cookie
0x180014a0e  xor     rax, rsp
0x180014a11  mov     [rsp+308h+var_40], rax
0x180014a19  mov     [rsp+308h+var_278], r9
0x180014a21  mov     [rsp+308h+var_280], r8
0x180014a29  mov     [rsp+308h+var_2B8], edx
0x180014a2d  mov     esi, ecx
0x180014a2f  mov     [rsp+308h+var_2C8], ecx
0x180014a33  mov     rax, [rsp+308h+arg_20]
0x180014a3b  mov     [rsp+308h+var_2A0], rax
0x180014a40  mov     r15, [rsp+308h+arg_28]
0x180014a48  mov     r14, [rsp+308h+Src]
0x180014a50  mov     [rsp+308h+var_2B0], ecx
0x180014a54  mov     [rsp+308h+var_288], r14
0x180014a5c  lea     r12, WPP_GLOBAL_Control
0x180014a63  mov     rbx, cs:WPP_GLOBAL_Control
0x180014a6a  cmp     rbx, r12
0x180014a6d  jnz     loc_180014EB0
0x180014a73  xor     edi, edi
0x180014a75  mov     [rsp+308h+var_270], rdi
0x180014a7d  mov     [rsp+308h+var_48], 10000h
0x180014a88  mov     [rsp+308h+var_268], rdi
0x180014a90  mov     [rsp+308h+var_2A8], edi
0x180014a94  mov     qword ptr [rsp+308h+var_258], rdi
0x180014a9c  xor     edx, edx; Val
0x180014a9e  mov     r8d, 200h; Size
0x180014aa4  lea     rcx, [rsp+308h+var_258+8]; void *
0x180014aac  call    memset_0
0x180014ab1  test    r15, r15
0x180014ab4  jz      loc_1800153B1
0x180014aba  test    r14, r14
0x180014abd  jz      loc_1800153B1
0x180014ac3  mov     rcx, r15
0x180014ac6  mov     [rsp+308h+var_2C0], rcx
0x180014acb  mov     [rsp+308h+var_298], rcx
0x180014ad0  mov     ecx, esi
0x180014ad2  test    esi, esi
0x180014ad4  jz      loc_180014E2A
0x180014ada  sub     ecx, 1
0x180014add  jz      loc_1800150A0
0x180014ae3  sub     ecx, 1
0x180014ae6  jnz     loc_180014EDB
0x180014aec  mov     rax, r14
0x180014aef  lea     rcx, [rsp+308h+var_258]
0x180014af7  lea     edx, [rdi+2]
0x180014afa  lea     r8d, [rdx+7Eh]
0x180014afe  movups  xmm0, xmmword ptr [rax]
0x180014b01  movups  xmmword ptr [rcx], xmm0
0x180014b04  movups  xmm1, xmmword ptr [rax+10h]
0x180014b08  movups  xmmword ptr [rcx+10h], xmm1
0x180014b0c  movups  xmm0, xmmword ptr [rax+20h]
0x180014b10  movups  xmmword ptr [rcx+20h], xmm0
0x180014b14  movups  xmm1, xmmword ptr [rax+30h]
0x180014b18  movups  xmmword ptr [rcx+30h], xmm1
0x180014b1c  movups  xmm0, xmmword ptr [rax+40h]
0x180014b20  movups  xmmword ptr [rcx+40h], xmm0
0x180014b24  movups  xmm1, xmmword ptr [rax+50h]
0x180014b28  movups  xmmword ptr [rcx+50h], xmm1
0x180014b2c  movups  xmm0, xmmword ptr [rax+60h]
0x180014b30  movups  xmmword ptr [rcx+60h], xmm0
0x180014b34  movups  xmm1, xmmword ptr [rax+70h]
0x180014b38  movups  xmmword ptr [rcx+70h], xmm1
0x180014b3c  add     rcx, r8
0x180014b3f  add     rax, r8
0x180014b42  sub     rdx, 1
0x180014b46  jnz     short loc_180014AFE
0x180014b48  movups  xmm0, xmmword ptr [rax]
0x180014b4b  movups  xmmword ptr [rcx], xmm0
0x180014b4e  mov     [rsp+308h+var_160], rdi
0x180014b56  mov     rbx, cs:__imp_FwCopyMMRule
0x180014b5d  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceMainModeRuleToVersion
0x180014b64  mov     r12d, 214h
0x180014b6a  mov     qword ptr [rsp+308h+var_258], rdi
0x180014b72  lea     rdx, [rsp+308h+var_258]
0x180014b7a  movzx   ecx, word ptr [r15]
0x180014b7e  mov     rax, [rsp+308h+var_280]
0x180014b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8b  mov     esi, eax
0x180014b8d  test    eax, eax
0x180014b8f  jnz     loc_180014E85
0x180014b95  cmp     dword ptr [r15+4], 1
0x180014b9a  ja      loc_1800151BE
0x180014ba0  cmp     [r15+20h], rdi
0x180014ba4  jz      loc_180015382
0x180014baa  cmp     [r15+28h], rdi
0x180014bae  jz      loc_180015382
0x180014bb4  cmp     [r15+4], edi
0x180014bb8  mov     r10, [rsp+308h+var_278]
0x180014bc0  cmovnz  r10, [rsp+308h+var_2A0]
0x180014bc6  mov     edx, [r10]
0x180014bc9  test    edx, edx
0x180014bcb  jz      short loc_180014BEE
0x180014bcd  mov     ecx, edi
0x180014bcf  movzx   r8d, word ptr [r15+2]
0x180014bd4  mov     r9, [r10+8]
0x180014bd8  mov     eax, ecx
0x180014bda  add     rax, rax
0x180014bdd  cmp     [r9+rax*8+8], r8w
0x180014be3  ja      short loc_180014BEE
0x180014be5  mov     edx, ecx
0x180014be7  inc     ecx
0x180014be9  cmp     ecx, [r10]
0x180014bec  jb      short loc_180014BD8
0x180014bee  cmp     edx, [r10]
0x180014bf1  jz      loc_180014DDC
0x180014bf7  mov     ecx, edx
0x180014bf9  add     rcx, rcx
0x180014bfc  mov     rax, [r10+8]
0x180014c00  mov     rax, [rax+rcx*8]
0x180014c04  mov     [rsp+308h+var_2A0], rax
0x180014c09  test    rax, rax
0x180014c0c  jz      loc_180014DDC
0x180014c12  lea     rax, [rsp+308h+var_2A8]
0x180014c17  mov     [rsp+308h+var_2D0], rax
0x180014c1c  mov     eax, [rsp+308h+var_2C8]
0x180014c20  mov     [rsp+308h+var_2D8], eax
0x180014c24  movzx   eax, word ptr [r15+2]
0x180014c29  mov     [rsp+308h+var_2E0], ax
0x180014c2e  mov     [rsp+308h+var_2E8], r13
0x180014c33  mov     r9, rbx
0x180014c36  movzx   r8d, word ptr [r15+30h]
0x180014c3b  lea     rdx, [rsp+308h+var_270]
0x180014c43  lea     rcx, [rsp+308h+var_258]
0x180014c4b  call    Int_FwMakeSvrCompatibleObject
0x180014c50  mov     esi, eax
0x180014c52  test    eax, eax
0x180014c54  jnz     loc_180014E07
0x180014c5a  lea     r8, [rsp+308h+var_258]
0x180014c62  cmp     [rsp+308h+var_270], rdi
0x180014c6a  cmovnz  r8, [rsp+308h+var_270]
0x180014c73  lea     r9, [rsp+308h+var_48]
0x180014c7b  mov     rdx, [r15+28h]
0x180014c7f  mov     rcx, [r15+20h]
0x180014c83  mov     rax, [rsp+308h+var_2A0]
0x180014c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c8d  mov     esi, eax
0x180014c8f  mov     [rsp+308h+var_2A4], eax
0x180014c93  test    eax, eax
0x180014c95  jz      short loc_180014CE3
0x180014c97  mov     rbx, cs:WPP_GLOBAL_Control
0x180014c9e  lea     rax, WPP_GLOBAL_Control
0x180014ca5  cmp     rbx, rax
0x180014ca8  jz      short loc_180014CCF
0x180014caa  test    byte ptr [rbx+1Ch], 1
0x180014cae  jz      short loc_180014CCF
0x180014cb0  mov     edx, 132h
0x180014cb5  mov     r9d, esi
0x180014cb8  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180014cbf  mov     rcx, [rbx+10h]
0x180014cc3  call    WPP_SF_d
0x180014cc8  mov     rbx, cs:WPP_GLOBAL_Control
0x180014ccf  mov     r13d, 20Ah
0x180014cd5  mov     edx, [rsp+308h+var_2C8]
0x180014cd9  mov     r8, [rsp+308h+var_2C0]
0x180014cde  jmp     loc_180014D95
0x180014ce3  mov     rbx, cs:WPP_GLOBAL_Control
0x180014cea  mov     r13d, 20Ah
0x180014cf0  mov     edx, [rsp+308h+var_2C8]
0x180014cf4  mov     r8, [rsp+308h+var_2C0]
0x180014cf9  jmp     loc_180014D95
0x180014cfe  mov     esi, eax
0x180014d00  mov     [rsp+308h+var_2A4], eax
0x180014d04  test    eax, eax
0x180014d06  jz      short loc_180014D68
0x180014d08  lea     rax, WPP_GLOBAL_Control
0x180014d0f  mov     rbx, cs:WPP_GLOBAL_Control
0x180014d16  cmp     rbx, rax
0x180014d19  jz      short loc_180014D40
0x180014d1b  test    byte ptr [rbx+1Ch], 1
0x180014d1f  jz      short loc_180014D40
0x180014d21  mov     edx, 133h
0x180014d26  mov     r9d, esi
0x180014d29  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180014d30  mov     rcx, [rbx+10h]
0x180014d34  call    WPP_SF_d
0x180014d39  mov     rbx, cs:WPP_GLOBAL_Control
0x180014d40  xor     edi, edi
0x180014d42  mov     r12d, 214h
0x180014d48  lea     r13d, [r12-0Ah]
0x180014d4d  mov     r8, [rsp+308h+var_298]
0x180014d52  mov     [rsp+308h+var_2C0], r8
0x180014d57  mov     edx, [rsp+308h+var_2B0]
0x180014d5b  mov     r15, r8
0x180014d5e  mov     r14, [rsp+308h+var_288]
0x180014d66  jmp     short loc_180014D95
0x180014d68  xor     edi, edi
0x180014d6a  mov     r12d, 214h
0x180014d70  lea     r13d, [r12-0Ah]
0x180014d75  mov     r8, [rsp+308h+var_298]
0x180014d7a  mov     [rsp+308h+var_2C0], r8
0x180014d7f  mov     rbx, cs:WPP_GLOBAL_Control
0x180014d86  mov     edx, [rsp+308h+var_2B0]
0x180014d8a  mov     r15, r8
0x180014d8d  mov     r14, [rsp+308h+var_288]
0x180014d95  test    r15, r15
0x180014d98  jnz     loc_1800153F7
0x180014d9e  test    esi, esi
0x180014da0  jnz     loc_1800155F5
0x180014da6  lea     rax, WPP_GLOBAL_Control
0x180014dad  cmp     rbx, rax
0x180014db0  jnz     loc_18001561E
0x180014db6  mov     eax, esi
0x180014db8  mov     rcx, [rsp+308h+var_40]
0x180014dc0  xor     rcx, rsp; StackCookie
0x180014dc3  call    __security_check_cookie
0x180014dc8  add     rsp, 2D0h
0x180014dcf  pop     r15
0x180014dd1  pop     r14
0x180014dd3  pop     r13
0x180014dd5  pop     r12
0x180014dd7  pop     rdi
0x180014dd8  pop     rsi
0x180014dd9  pop     rbx
0x180014dda  retn
0x180014ddc  mov     esi, 32h ; '2'
0x180014de1  mov     rbx, cs:WPP_GLOBAL_Control
0x180014de8  lea     rax, WPP_GLOBAL_Control
0x180014def  cmp     rbx, rax
0x180014df2  jnz     loc_180015373
0x180014df8  mov     r8, r15
0x180014dfb  mov     r13d, 20Ah
0x180014e01  mov     edx, [rsp+308h+var_2C8]
0x180014e05  jmp     short loc_180014D95
0x180014e07  mov     rbx, cs:WPP_GLOBAL_Control
0x180014e0e  lea     rax, WPP_GLOBAL_Control
0x180014e15  cmp     rbx, rax
0x180014e18  jz      short loc_180014DF8
0x180014e1a  test    byte ptr [rbx+1Ch], 1
0x180014e1e  jz      short loc_180014DF8
0x180014e20  mov     edx, 131h
0x180014e25  jmp     loc_180015198
0x180014e2a  mov     eax, 20Ah
0x180014e2f  lea     r12d, [rax+0Ah]
0x180014e33  cmp     [r15], ax
0x180014e37  jnb     loc_18001510B
0x180014e3d  mov     ebx, 168h
0x180014e42  xor     edx, edx; Val
0x180014e44  mov     r8d, 1F8h; Size
0x180014e4a  lea     rcx, [rsp+308h+var_258]; void *
0x180014e52  call    memset_0
0x180014e57  mov     r8, rbx; Size
0x180014e5a  mov     rdx, r14; Src
0x180014e5d  lea     rcx, [rsp+308h+var_258]; void *
0x180014e65  call    memcpy_0
0x180014e6a  mov     [rsp+308h+var_100], rdi
0x180014e72  mov     rbx, cs:__imp_FwCopyRule
0x180014e79  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceFirewallRuleToVersion
0x180014e80  jmp     loc_180014B6A
0x180014e85  mov     rbx, cs:WPP_GLOBAL_Control
0x180014e8c  lea     rax, WPP_GLOBAL_Control
0x180014e93  cmp     rbx, rax
0x180014e96  jz      loc_180014DF8
0x180014e9c  test    byte ptr [rbx+1Ch], 1
0x180014ea0  jz      loc_180014DF8
0x180014ea6  mov     edx, 12Eh
0x180014eab  jmp     loc_180015198
0x180014eb0  test    byte ptr [rbx+1Ch], 8
0x180014eb4  jz      loc_180014A73
0x180014eba  mov     edx, 12Bh
0x180014ebf  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180014ec6  mov     rcx, [rbx+10h]
0x180014eca  call    WPP_SF_
0x180014ecf  mov     rbx, cs:WPP_GLOBAL_Control
0x180014ed6  jmp     loc_180014A73
0x180014edb  sub     ecx, 1
0x180014ede  jz      loc_180014F69
0x180014ee4  cmp     ecx, 1
0x180014ee7  jz      short loc_180014F01
0x180014ee9  mov     rbx, rdi
0x180014eec  mov     r13, rdi
0x180014eef  mov     edx, esi; __annotation("Debug", "TelemetryAssert", "FALSE", "objectType is invalid")
0x180014ef1  call    MicrosoftTelemetryAssertTriggeredArgs
0x180014ef6  mov     r12d, 214h
0x180014efc  jmp     loc_180014B72
0x180014f01  movups  xmm0, xmmword ptr [r14]
0x180014f05  movaps  [rsp+308h+var_258], xmm0
0x180014f0d  movups  xmm1, xmmword ptr [r14+10h]
0x180014f12  movaps  [rsp+308h+var_248], xmm1
0x180014f1a  movups  xmm0, xmmword ptr [r14+20h]
0x180014f1f  movaps  [rsp+308h+var_238], xmm0
0x180014f27  movups  xmm1, xmmword ptr [r14+30h]
0x180014f2c  movaps  [rsp+308h+var_228], xmm1
0x180014f34  movups  xmm0, xmmword ptr [r14+40h]
0x180014f39  movaps  [rsp+308h+var_218], xmm0
0x180014f41  movups  xmm1, xmmword ptr [r14+50h]
0x180014f46  movaps  [rsp+308h+var_208], xmm1
0x180014f4e  mov     qword ptr [rsp+308h+var_208], rdi
0x180014f56  mov     rbx, cs:__imp_FwCopyCryptoSet
0x180014f5d  mov     r13, cs:__imp_Int_FwValidateComplianceAndReduceCryptoSetToVersion
0x180014f64  jmp     loc_180014B64
0x180014f69  mov     r12d, 214h
0x180014f6f  cmp     [r15], r12w
  ... truncated ...
```
