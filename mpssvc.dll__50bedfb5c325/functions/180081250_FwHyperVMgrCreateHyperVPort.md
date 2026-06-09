# FwHyperVMgrCreateHyperVPort

- ea: `0x180081250`
- end: `0x18008173b`
- name: `FwHyperVMgrCreateHyperVPort`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009d5b8`

## callees

- `0x1800089bc`
- `0x180008a80`
- `0x1800097b0`
- `0x18000a66c`
- `0x18000a710`
- `0x180011098`
- `0x180011100`
- `0x18006a5d4`
- `0x18006f620`
- `0x1800729c0`
- `0x18008030c`
- `0x180081250`
- `0x180082d70`
- `0x180084b6c`
- `0x180084e38`
- `0x1800b0f34`
- `0x1800b11d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180081451`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180081451`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180081684`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180081684`
- `fwbase!FwAlloc` at `0x1800812cc`
- `fwbase!FwAlloc` at `0x1800812cc`
- `FWPolicyIOMgr!FwCopyHyperVPort` at `0x180081326`
- `FWPolicyIOMgr!FwCopyHyperVPort` at `0x180081326`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x180081711`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x180081711`

## string_xrefs

- `0x180081356`: `FwHyperVMgrCreateHyperVPort:FwHyperVMgrCopyHyperVPort`
- `0x18008148b`: `FwHyperVMgrCreateHyperVPort:FwInitializeVfpPort`
- `0x1800814e3`: `FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock`
- `0x1800815d5`: `FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock`
- `0x1800816f9`: `FwHyperVMgrCreateHyperVPort`

## pseudocode

```c
__int64 __fastcall FwHyperVMgrCreateHyperVPort(__int64 a1)
{
  int updated; // ebx
  int PortProfile; // eax
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  const std::exception *v11; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v13[2]; // [rsp+50h] [rbp-28h] BYREF

  v12 = 0;
  updated = FwHyperVMgrValidatePort();
  if ( updated >= 0 )
  {
    v12 = FwAlloc(96);
    if ( v12 )
    {
      updated = FwCopyHyperVPort(a1, &v12);
      if ( updated >= 0 )
      {
        *(_QWORD *)v12 = 0;
        updated = FwLock();
        if ( updated >= 0 )
        {
          PortProfile = FwHyperVMgrGetPortProfile(a1);
          *(_DWORD *)(v12 + 76) = PortProfile;
          updated = FwHyperVMgrLock();
          if ( updated >= 0 )
          {
            updated = FwHyperVMgrInitializeVMCreator(a1 + 24, 0);
            if ( updated >= 0 )
            {
              if ( !*(_DWORD *)off_18012C498 )
                SubmitThreadpoolWork((PTP_WORK)(*off_18012C498)[1]);
              updated = FwInitializeVfpPort(v12);
              if ( updated >= 0 )
              {
                updated = FwSetVfpPortBlock(v12, 1);
                if ( updated >= 0 )
                {
                  updated = FwHyperVMgrUpdateAllRulesForAllStores(FwIP_HTTPS_InIsPortAllowed, 0, v12, 1);
                  if ( updated >= 0 )
                  {
                    updated = FwApplyHyperVVMConfigs(v12);
                    if ( updated >= 0 )
                    {
                      v4 = FwSetVfpPortBlock(v12, 0);
                      updated = v4;
                      if ( v4 >= 0 )
                      {
                        if ( qword_180132B38 == qword_180132B40 )
                        {
                          try
                          {
                            std::vector<_tag_FW_HYPERV_PORT1 *>::_Emplace_reallocate<_tag_FW_HYPERV_PORT1 * const &>(
                              &qword_180132B30,
                              qword_180132B38,
                              &v12);
                            v6 = qword_180132B38;
                          }
                          catch ( const std::exception *v11 )
                          {
                            v9 = WPP_GLOBAL_Control;
                            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                            {
                              v10 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v11 + 8LL))(v11);
                              WPP_SF_s(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                117,
                                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                                v10);
                              v9 = WPP_GLOBAL_Control;
                            }
                            if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
                              WPP_SF_d(
                                *(_QWORD *)(v9 + 16),
                                118,
                                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                                2147942414LL);
                            updated = -2147024882;
                            goto LABEL_67;
                          }
                        }
                        else
                        {
                          *(_QWORD *)qword_180132B38 = v12;
                          v6 = qword_180132B38 + 8;
                          qword_180132B38 += 8;
                        }
                        if ( v6 - (_QWORD)qword_180132B30 != 8 )
                          goto LABEL_66;
                        v13[0] = FwHyperVSleepNotificationHandler;
                        v13[1] = 0;
                        if ( (_QWORD)xmmword_180133290 )
                          MicrosoftTelemetryAssertTriggeredNoArgs(v5);
                        v7 = PowerRegisterSuspendResumeNotification(2, v13, &xmmword_180133290);
                        updated = v7;
                        if ( v7 > 0 )
                          updated = (unsigned __int16)v7 | 0x80070000;
                        if ( updated < 0 )
                        {
                          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                          {
                            WPP_SF_d(
                              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                              116,
                              WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                              (unsigned int)updated);
                          }
                        }
                        else
                        {
LABEL_66:
                          v12 = 0;
                        }
                      }
                      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                      {
                        WPP_SF_Ds(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          115,
                          (unsigned int)WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                          v4,
                          (__int64)"FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock");
                      }
                    }
                    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        114,
                        WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                        (unsigned int)updated);
                    }
                  }
                  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      113,
                      WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                      (unsigned int)updated);
                  }
                }
                else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_Ds(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    112,
                    (unsigned int)WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                    updated,
                    (__int64)"FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock");
                }
              }
              else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_Ds(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  111,
                  (unsigned int)WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                  updated,
                  (__int64)"FwHyperVMgrCreateHyperVPort:FwInitializeVfpPort");
              }
            }
            else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                110,
                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                (unsigned int)updated);
            }
LABEL_67:
            FwHyperVMgrUnlock();
          }
          FwUnlockInternal(0, "FwHyperVMgrCreateHyperVPort");
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            109,
            WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
            (unsigned int)updated);
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          108,
          (unsigned int)WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
          updated,
          (__int64)"FwHyperVMgrCreateHyperVPort:FwHyperVMgrCopyHyperVPort");
      }
    }
    else
    {
      updated = -2147024882;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          107,
          WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
          2147942414LL);
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      106,
      WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
      (unsigned int)updated);
  }
  FwFreeHyperVPortsBySchemaVersion(v12, 545);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180081250  mov     [rsp+arg_8], rbx
0x180081255  push    rsi
0x180081256  sub     rsp, 70h
0x18008125a  mov     rax, cs:__security_cookie
0x180081261  xor     rax, rsp
0x180081264  mov     [rsp+78h+var_18], rax
0x180081269  mov     rsi, rcx
0x18008126c  mov     [rsp+78h+var_30], 0
0x180081275  mov     [rsp+78h+var_40], 0
0x18008127d  mov     [rsp+78h+var_48], 0
0x180081285  call    FwHyperVMgrValidatePort
0x18008128a  mov     ebx, eax
0x18008128c  test    eax, eax
0x18008128e  jns     short loc_1800812C7
0x180081290  lea     rax, WPP_GLOBAL_Control
0x180081297  mov     rcx, cs:WPP_GLOBAL_Control
0x18008129e  cmp     rcx, rax
0x1800812a1  jz      short loc_1800812C2
0x1800812a3  test    byte ptr [rcx+1Ch], 1
0x1800812a7  jz      short loc_1800812C2
0x1800812a9  mov     edx, 6Ah ; 'j'
0x1800812ae  mov     r9d, ebx
0x1800812b1  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800812b8  mov     rcx, [rcx+10h]
0x1800812bc  call    WPP_SF_d
0x1800812c1  nop
0x1800812c2  jmp     loc_180081707
0x1800812c7  mov     ecx, 60h ; '`'
0x1800812cc  call    cs:__imp_FwAlloc
0x1800812d3  nop     dword ptr [rax+rax+00h]
0x1800812d8  mov     [rsp+78h+var_30], rax
0x1800812dd  test    rax, rax
0x1800812e0  jnz     short loc_18008131E
0x1800812e2  mov     ebx, 8007000Eh
0x1800812e7  lea     rax, WPP_GLOBAL_Control
0x1800812ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812f5  cmp     rcx, rax
0x1800812f8  jz      short loc_180081319
0x1800812fa  test    byte ptr [rcx+1Ch], 1
0x1800812fe  jz      short loc_180081319
0x180081300  mov     edx, 6Bh ; 'k'
0x180081305  mov     r9d, ebx
0x180081308  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18008130f  mov     rcx, [rcx+10h]
0x180081313  call    WPP_SF_d
0x180081318  nop
0x180081319  jmp     loc_180081707
0x18008131e  lea     rdx, [rsp+78h+var_30]
0x180081323  mov     rcx, rsi
0x180081326  call    cs:__imp_FwCopyHyperVPort
0x18008132d  nop     dword ptr [rax+rax+00h]
0x180081332  mov     ebx, eax
0x180081334  test    eax, eax
0x180081336  jns     short loc_18008137B
0x180081338  lea     rax, WPP_GLOBAL_Control
0x18008133f  mov     rcx, cs:WPP_GLOBAL_Control
0x180081346  cmp     rcx, rax
0x180081349  jz      short loc_180081376
0x18008134b  test    byte ptr [rcx+1Ch], 1
0x18008134f  jz      short loc_180081376
0x180081351  mov     edx, 6Ch ; 'l'
0x180081356  lea     rax, aFwhypervmgrcre; "FwHyperVMgrCreateHyperVPort:FwHyperVMgr"...
0x18008135d  mov     [rsp+78h+var_58], rax
0x180081362  mov     r9d, ebx
0x180081365  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18008136c  mov     rcx, [rcx+10h]
0x180081370  call    WPP_SF_Ds
0x180081375  nop
0x180081376  jmp     loc_180081707
0x18008137b  mov     rax, [rsp+78h+var_30]
0x180081380  mov     qword ptr [rax], 0
0x180081387  call    FwLock
0x18008138c  mov     ebx, eax
0x18008138e  test    eax, eax
0x180081390  jns     short loc_1800813C9
0x180081392  lea     rax, WPP_GLOBAL_Control
0x180081399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800813a0  cmp     rcx, rax
0x1800813a3  jz      short loc_1800813C4
0x1800813a5  test    byte ptr [rcx+1Ch], 1
0x1800813a9  jz      short loc_1800813C4
0x1800813ab  mov     edx, 6Dh ; 'm'
0x1800813b0  mov     r9d, ebx
0x1800813b3  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800813ba  mov     rcx, [rcx+10h]
0x1800813be  call    WPP_SF_d
0x1800813c3  nop
0x1800813c4  jmp     loc_180081707
0x1800813c9  mov     [rsp+78h+var_40], 1
0x1800813d1  mov     rcx, rsi
0x1800813d4  call    FwHyperVMgrGetPortProfile
0x1800813d9  mov     rcx, [rsp+78h+var_30]
0x1800813de  mov     [rcx+4Ch], eax
0x1800813e1  call    FwHyperVMgrLock
0x1800813e6  mov     ebx, eax
0x1800813e8  test    eax, eax
0x1800813ea  jns     short loc_1800813F1
0x1800813ec  jmp     loc_1800816F9
0x1800813f1  mov     [rsp+78h+var_48], 1
0x1800813f9  lea     rcx, [rsi+18h]
0x1800813fd  xor     edx, edx
0x1800813ff  call    FwHyperVMgrInitializeVMCreator
0x180081404  mov     ebx, eax
0x180081406  test    eax, eax
0x180081408  jns     short loc_180081441
0x18008140a  lea     rax, WPP_GLOBAL_Control
0x180081411  mov     rcx, cs:WPP_GLOBAL_Control
0x180081418  cmp     rcx, rax
0x18008141b  jz      short loc_18008143C
0x18008141d  test    byte ptr [rcx+1Ch], 1
0x180081421  jz      short loc_18008143C
0x180081423  mov     edx, 6Eh ; 'n'
0x180081428  mov     r9d, ebx
0x18008142b  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x180081432  mov     rcx, [rcx+10h]
0x180081436  call    WPP_SF_d
0x18008143b  nop
0x18008143c  jmp     loc_1800816ED
0x180081441  mov     rcx, cs:off_18012C498
0x180081448  cmp     dword ptr [rcx], 0
0x18008144b  jnz     short loc_18008145D
0x18008144d  mov     rcx, [rcx+8]; pwk
0x180081451  call    cs:__imp_SubmitThreadpoolWork
0x180081458  nop     dword ptr [rax+rax+00h]
0x18008145d  mov     rcx, [rsp+78h+var_30]
0x180081462  call    FwInitializeVfpPort
0x180081467  mov     ebx, eax
0x180081469  test    eax, eax
0x18008146b  jns     short loc_1800814B0
0x18008146d  lea     rax, WPP_GLOBAL_Control
0x180081474  mov     rcx, cs:WPP_GLOBAL_Control
0x18008147b  cmp     rcx, rax
0x18008147e  jz      short loc_1800814AB
0x180081480  test    byte ptr [rcx+1Ch], 1
0x180081484  jz      short loc_1800814AB
0x180081486  mov     edx, 6Fh ; 'o'
0x18008148b  lea     rax, aFwhypervmgrcre_1; "FwHyperVMgrCreateHyperVPort:FwInitializ"...
0x180081492  mov     [rsp+78h+var_58], rax
0x180081497  mov     r9d, ebx
0x18008149a  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800814a1  mov     rcx, [rcx+10h]
0x1800814a5  call    WPP_SF_Ds
0x1800814aa  nop
0x1800814ab  jmp     loc_1800816ED
0x1800814b0  mov     edx, 1
0x1800814b5  mov     rcx, [rsp+78h+var_30]
0x1800814ba  call    FwSetVfpPortBlock
0x1800814bf  mov     ebx, eax
0x1800814c1  test    eax, eax
0x1800814c3  jns     short loc_180081508
0x1800814c5  lea     rax, WPP_GLOBAL_Control
0x1800814cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800814d3  cmp     rcx, rax
0x1800814d6  jz      short loc_180081503
0x1800814d8  test    byte ptr [rcx+1Ch], 1
0x1800814dc  jz      short loc_180081503
0x1800814de  mov     edx, 70h ; 'p'
0x1800814e3  lea     rax, aFwhypervmgrcre_0; "FwHyperVMgrCreateHyperVPort:FwSetVfpPor"...
0x1800814ea  mov     [rsp+78h+var_58], rax
0x1800814ef  mov     r9d, ebx
0x1800814f2  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800814f9  mov     rcx, [rcx+10h]
0x1800814fd  call    WPP_SF_Ds
0x180081502  nop
0x180081503  jmp     loc_1800816ED
0x180081508  mov     r9d, 1
0x18008150e  mov     r8, [rsp+78h+var_30]
0x180081513  xor     edx, edx
0x180081515  lea     rcx, ?FwIP_HTTPS_InIsPortAllowed@@YAHG@Z; FwIP_HTTPS_InIsPortAllowed(ushort)
0x18008151c  call    FwHyperVMgrUpdateAllRulesForAllStores
0x180081521  mov     ebx, eax
0x180081523  test    eax, eax
0x180081525  jns     short loc_18008155E
0x180081527  lea     rax, WPP_GLOBAL_Control
0x18008152e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081535  cmp     rcx, rax
0x180081538  jz      short loc_180081559
0x18008153a  test    byte ptr [rcx+1Ch], 1
0x18008153e  jz      short loc_180081559
0x180081540  mov     edx, 71h ; 'q'
0x180081545  mov     r9d, ebx
0x180081548  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18008154f  mov     rcx, [rcx+10h]
0x180081553  call    WPP_SF_d
0x180081558  nop
0x180081559  jmp     loc_1800816ED
0x18008155e  mov     rcx, [rsp+78h+var_30]
0x180081563  call    FwApplyHyperVVMConfigs
0x180081568  mov     ebx, eax
0x18008156a  test    eax, eax
0x18008156c  jns     short loc_1800815A5
0x18008156e  lea     rax, WPP_GLOBAL_Control
0x180081575  mov     rcx, cs:WPP_GLOBAL_Control
0x18008157c  cmp     rcx, rax
0x18008157f  jz      short loc_1800815A0
0x180081581  test    byte ptr [rcx+1Ch], 1
0x180081585  jz      short loc_1800815A0
0x180081587  mov     edx, 72h ; 'r'
0x18008158c  mov     r9d, ebx
0x18008158f  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x180081596  mov     rcx, [rcx+10h]
0x18008159a  call    WPP_SF_d
0x18008159f  nop
0x1800815a0  jmp     loc_1800816ED
0x1800815a5  xor     edx, edx
0x1800815a7  mov     rcx, [rsp+78h+var_30]
0x1800815ac  call    FwSetVfpPortBlock
0x1800815b1  mov     ebx, eax
0x1800815b3  test    eax, eax
0x1800815b5  jns     short loc_1800815FA
0x1800815b7  lea     rax, WPP_GLOBAL_Control
0x1800815be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800815c5  cmp     rcx, rax
0x1800815c8  jz      short loc_1800815F5
0x1800815ca  test    byte ptr [rcx+1Ch], 1
0x1800815ce  jz      short loc_1800815F5
0x1800815d0  mov     edx, 73h ; 's'
0x1800815d5  lea     rax, aFwhypervmgrcre_0; "FwHyperVMgrCreateHyperVPort:FwSetVfpPor"...
0x1800815dc  mov     [rsp+78h+var_58], rax
0x1800815e1  mov     r9d, ebx
0x1800815e4  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800815eb  mov     rcx, [rcx+10h]
0x1800815ef  call    WPP_SF_Ds
0x1800815f4  nop
0x1800815f5  jmp     loc_1800816ED
0x1800815fa  mov     rdx, cs:qword_180132B38
0x180081601  cmp     rdx, cs:qword_180132B40
0x180081608  jz      short loc_180081626
0x18008160a  mov     rax, [rsp+78h+var_30]
0x18008160f  mov     [rdx], rax
0x180081612  mov     rax, cs:qword_180132B38
0x180081619  add     rax, 8
0x18008161d  mov     cs:qword_180132B38, rax
0x180081624  jmp     short loc_18008163E
0x180081626  lea     r8, [rsp+78h+var_30]
0x18008162b  lea     rcx, qword_180132B30
0x180081632  call    ??$_Emplace_reallocate@AEBQEAU_tag_FW_HYPERV_PORT1@@@?$vector@PEAU_tag_FW_HYPERV_PORT1@@V?$allocator@PEAU_tag_FW_HYPERV_PORT1@@@std@@@std@@AEAAPEAPEAU_tag_FW_HYPERV_PORT1@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_tag_FW_HYPERV_PORT1 *>::_Emplace_reallocate<_tag_FW_HYPERV_PORT1 * const &>(_tag_FW_HYPERV_PORT1 * * const,_tag_FW_HYPERV_PORT1 * const &)
0x180081637  mov     rax, cs:qword_180132B38
0x18008163e  sub     rax, cs:qword_180132B30
0x180081645  cmp     rax, 8
0x180081649  jnz     loc_1800816D7
0x18008164f  lea     rax, FwHyperVSleepNotificationHandler
0x180081656  mov     [rsp+78h+var_28], rax
0x18008165b  mov     [rsp+78h+var_20], 0
0x180081664  cmp     qword ptr cs:xmmword_180133290, 0
0x18008166c  jz      short loc_180081673
0x18008166e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!gFwHyperVMgr.goalStateDriver.sleepNotificationHandle")
0x180081673  lea     r8, xmmword_180133290
0x18008167a  lea     rdx, [rsp+78h+var_28]
0x18008167f  mov     ecx, 2
0x180081684  call    cs:__imp_PowerRegisterSuspendResumeNotification
0x18008168b  nop     dword ptr [rax+rax+00h]
0x180081690  mov     ebx, eax
0x180081692  test    eax, eax
0x180081694  jle     short loc_18008169F
0x180081696  movzx   ebx, ax
0x180081699  or      ebx, 80070000h
0x18008169f  test    ebx, ebx
0x1800816a1  jns     short loc_1800816D7
0x1800816a3  lea     rax, WPP_GLOBAL_Control
0x1800816aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800816b1  cmp     rcx, rax
0x1800816b4  jz      short loc_1800816D5
0x1800816b6  test    byte ptr [rcx+1Ch], 1
0x1800816ba  jz      short loc_1800816D5
0x1800816bc  mov     edx, 74h ; 't'
0x1800816c1  mov     r9d, ebx
0x1800816c4  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800816cb  mov     rcx, [rcx+10h]
0x1800816cf  call    WPP_SF_d
0x1800816d4  nop
0x1800816d5  jmp     short loc_1800816ED
0x1800816d7  mov     [rsp+78h+var_30], 0
0x1800816e0  jmp     short loc_1800816ED
0x1800816e2  mov     ebx, [rsp+78h+var_44]
0x1800816e6  cmp     [rsp+78h+var_48], 1
0x1800816eb  jnz     short loc_1800816F2
0x1800816ed  call    FwHyperVMgrUnlock
0x1800816f2  cmp     [rsp+78h+var_40], 0
0x1800816f7  jz      short loc_180081707
0x1800816f9  lea     rdx, aFwhypervmgrcre_2; "FwHyperVMgrCreateHyperVPort"
0x180081700  xor     ecx, ecx; void *
0x180081702  call    FwUnlockInternal
0x180081707  mov     edx, 221h
0x18008170c  mov     rcx, [rsp+78h+var_30]
0x180081711  call    cs:__imp_FwFreeHyperVPortsBySchemaVersion
0x180081718  nop     dword ptr [rax+rax+00h]
0x18008171d  mov     eax, ebx
0x18008171f  mov     rcx, [rsp+78h+var_18]
0x180081724  xor     rcx, rsp; StackCookie
0x180081727  call    __security_check_cookie
0x18008172c  mov     rbx, [rsp+78h+arg_8]
0x180081734  add     rsp, 70h
0x180081738  pop     rsi
0x180081739  retn
```
