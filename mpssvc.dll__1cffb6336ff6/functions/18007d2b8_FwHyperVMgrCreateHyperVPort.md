# FwHyperVMgrCreateHyperVPort

- ea: `0x18007d2b8`
- end: `0x18007d784`
- name: `FwHyperVMgrCreateHyperVPort`
- size: `1228`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800984b4`

## callees

- `0x1800093b0`
- `0x180009460`
- `0x18000a0c0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x1800384a4`
- `0x180038504`
- `0x180066f84`
- `0x18006c658`
- `0x18006f520`
- `0x18007c3cc`
- `0x18007d2b8`
- `0x18007ed10`
- `0x180080aa0`
- `0x180080d6c`
- `0x1800aacac`
- `0x1800aaf48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007d4ad`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007d4ad`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x18007d6da`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x18007d6da`
- `fwbase!FwAlloc` at `0x18007d334`
- `fwbase!FwAlloc` at `0x18007d334`
- `FWPolicyIOMgr!FwCopyHyperVPort` at `0x18007d388`
- `FWPolicyIOMgr!FwCopyHyperVPort` at `0x18007d388`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x18007d761`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x18007d761`

## string_xrefs

- `0x18007d3b2`: `FwHyperVMgrCreateHyperVPort:FwHyperVMgrCopyHyperVPort`
- `0x18007d4e1`: `FwHyperVMgrCreateHyperVPort:FwInitializeVfpPort`
- `0x18007d539`: `FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock`
- `0x18007d62b`: `FwHyperVMgrCreateHyperVPort:FwSetVfpPortBlock`
- `0x18007d749`: `FwHyperVMgrCreateHyperVPort`

## pseudocode

```c
__int64 __fastcall FwHyperVMgrCreateHyperVPort(__int64 a1)
{
  int updated; // ebx
  int PortProfile; // eax
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  const std::exception *v14; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-28h] BYREF

  v15 = 0;
  updated = FwHyperVMgrValidatePort();
  if ( updated >= 0 )
  {
    v15 = FwAlloc(96);
    if ( v15 )
    {
      updated = FwCopyHyperVPort(a1, &v15);
      if ( updated >= 0 )
      {
        *(_QWORD *)v15 = 0;
        updated = FwLock();
        if ( updated >= 0 )
        {
          PortProfile = FwHyperVMgrGetPortProfile(a1);
          *(_DWORD *)(v15 + 76) = PortProfile;
          updated = FwHyperVMgrLock();
          if ( updated >= 0 )
          {
            updated = FwHyperVMgrInitializeVMCreator(a1 + 24, 0);
            if ( updated >= 0 )
            {
              if ( !*(_DWORD *)off_180126498 )
                SubmitThreadpoolWork((PTP_WORK)(*off_180126498)[1]);
              updated = FwInitializeVfpPort(v15);
              if ( updated >= 0 )
              {
                updated = FwSetVfpPortBlock(v15, 1);
                if ( updated >= 0 )
                {
                  updated = FwHyperVMgrUpdateAllRulesForAllStores(FwIP_HTTPS_InIsPortAllowed, 0, v15, 1);
                  if ( updated >= 0 )
                  {
                    updated = FwApplyHyperVVMConfigs(v15);
                    if ( updated >= 0 )
                    {
                      v4 = FwSetVfpPortBlock(v15, 0);
                      updated = v4;
                      if ( v4 >= 0 )
                      {
                        v8 = qword_18012C968;
                        if ( qword_18012C968 == qword_18012C970 )
                        {
                          try
                          {
                            std::vector<_tag_FW_HYPERV_PORT1 *>::_Emplace_reallocate<_tag_FW_HYPERV_PORT1 * const &>(
                              &qword_18012C960,
                              qword_18012C968,
                              &v15);
                            v9 = qword_18012C968;
                          }
                          catch ( const std::exception *v14 )
                          {
                            v12 = WPP_GLOBAL_Control;
                            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                            {
                              v13 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v14 + 8LL))(v14);
                              WPP_SF_s(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                117,
                                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                                v13);
                              v12 = WPP_GLOBAL_Control;
                            }
                            if ( (_UNKNOWN *)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 1) != 0 )
                              WPP_SF_d(
                                *(_QWORD *)(v12 + 16),
                                118,
                                WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids,
                                2147942414LL);
                            updated = -2147024882;
                            goto LABEL_67;
                          }
                        }
                        else
                        {
                          *(_QWORD *)qword_18012C968 = v15;
                          v9 = qword_18012C968 + 8;
                          qword_18012C968 += 8;
                        }
                        if ( v9 - (_QWORD)qword_18012C960 != 8 )
                          goto LABEL_66;
                        v16[0] = FwHyperVSleepNotificationHandler;
                        v16[1] = 0;
                        if ( (_QWORD)xmmword_18012D0C0 )
                          MicrosoftTelemetryAssertTriggeredNoArgs(v5, v8, v6, v7);
                        v10 = PowerRegisterSuspendResumeNotification(2, v16, &xmmword_18012D0C0);
                        updated = v10;
                        if ( v10 > 0 )
                          updated = (unsigned __int16)v10 | 0x80070000;
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
                          v15 = 0;
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
  FwFreeHyperVPortsBySchemaVersion(v15, 545);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18007d2b8  mov     [rsp+arg_8], rbx
0x18007d2bd  push    rsi
0x18007d2be  sub     rsp, 70h
0x18007d2c2  mov     rax, cs:__security_cookie
0x18007d2c9  xor     rax, rsp
0x18007d2cc  mov     [rsp+78h+var_18], rax
0x18007d2d1  mov     rsi, rcx
0x18007d2d4  mov     [rsp+78h+var_30], 0
0x18007d2dd  mov     [rsp+78h+var_40], 0
0x18007d2e5  mov     [rsp+78h+var_48], 0
0x18007d2ed  call    FwHyperVMgrValidatePort
0x18007d2f2  mov     ebx, eax
0x18007d2f4  test    eax, eax
0x18007d2f6  jns     short loc_18007D32F
0x18007d2f8  lea     rax, WPP_GLOBAL_Control
0x18007d2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d306  cmp     rcx, rax
0x18007d309  jz      short loc_18007D32A
0x18007d30b  test    byte ptr [rcx+1Ch], 1
0x18007d30f  jz      short loc_18007D32A
0x18007d311  mov     edx, 6Ah ; 'j'
0x18007d316  mov     r9d, ebx
0x18007d319  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d320  mov     rcx, [rcx+10h]
0x18007d324  call    WPP_SF_d
0x18007d329  nop
0x18007d32a  jmp     loc_18007D757
0x18007d32f  mov     ecx, 60h ; '`'
0x18007d334  call    cs:__imp_FwAlloc
0x18007d33a  mov     [rsp+78h+var_30], rax
0x18007d33f  test    rax, rax
0x18007d342  jnz     short loc_18007D380
0x18007d344  mov     ebx, 8007000Eh
0x18007d349  lea     rax, WPP_GLOBAL_Control
0x18007d350  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d357  cmp     rcx, rax
0x18007d35a  jz      short loc_18007D37B
0x18007d35c  test    byte ptr [rcx+1Ch], 1
0x18007d360  jz      short loc_18007D37B
0x18007d362  mov     edx, 6Bh ; 'k'
0x18007d367  mov     r9d, ebx
0x18007d36a  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d371  mov     rcx, [rcx+10h]
0x18007d375  call    WPP_SF_d
0x18007d37a  nop
0x18007d37b  jmp     loc_18007D757
0x18007d380  lea     rdx, [rsp+78h+var_30]
0x18007d385  mov     rcx, rsi
0x18007d388  call    cs:__imp_FwCopyHyperVPort
0x18007d38e  mov     ebx, eax
0x18007d390  test    eax, eax
0x18007d392  jns     short loc_18007D3D7
0x18007d394  lea     rax, WPP_GLOBAL_Control
0x18007d39b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3a2  cmp     rcx, rax
0x18007d3a5  jz      short loc_18007D3D2
0x18007d3a7  test    byte ptr [rcx+1Ch], 1
0x18007d3ab  jz      short loc_18007D3D2
0x18007d3ad  mov     edx, 6Ch ; 'l'
0x18007d3b2  lea     rax, aFwhypervmgrcre; "FwHyperVMgrCreateHyperVPort:FwHyperVMgr"...
0x18007d3b9  mov     [rsp+78h+var_58], rax
0x18007d3be  mov     r9d, ebx
0x18007d3c1  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d3c8  mov     rcx, [rcx+10h]
0x18007d3cc  call    WPP_SF_Ds
0x18007d3d1  nop
0x18007d3d2  jmp     loc_18007D757
0x18007d3d7  mov     rax, [rsp+78h+var_30]
0x18007d3dc  mov     qword ptr [rax], 0
0x18007d3e3  call    FwLock
0x18007d3e8  mov     ebx, eax
0x18007d3ea  test    eax, eax
0x18007d3ec  jns     short loc_18007D425
0x18007d3ee  lea     rax, WPP_GLOBAL_Control
0x18007d3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3fc  cmp     rcx, rax
0x18007d3ff  jz      short loc_18007D420
0x18007d401  test    byte ptr [rcx+1Ch], 1
0x18007d405  jz      short loc_18007D420
0x18007d407  mov     edx, 6Dh ; 'm'
0x18007d40c  mov     r9d, ebx
0x18007d40f  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d416  mov     rcx, [rcx+10h]
0x18007d41a  call    WPP_SF_d
0x18007d41f  nop
0x18007d420  jmp     loc_18007D757
0x18007d425  mov     [rsp+78h+var_40], 1
0x18007d42d  mov     rcx, rsi
0x18007d430  call    FwHyperVMgrGetPortProfile
0x18007d435  mov     rcx, [rsp+78h+var_30]
0x18007d43a  mov     [rcx+4Ch], eax
0x18007d43d  call    FwHyperVMgrLock
0x18007d442  mov     ebx, eax
0x18007d444  test    eax, eax
0x18007d446  jns     short loc_18007D44D
0x18007d448  jmp     loc_18007D749
0x18007d44d  mov     [rsp+78h+var_48], 1
0x18007d455  lea     rcx, [rsi+18h]
0x18007d459  xor     edx, edx
0x18007d45b  call    FwHyperVMgrInitializeVMCreator
0x18007d460  mov     ebx, eax
0x18007d462  test    eax, eax
0x18007d464  jns     short loc_18007D49D
0x18007d466  lea     rax, WPP_GLOBAL_Control
0x18007d46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d474  cmp     rcx, rax
0x18007d477  jz      short loc_18007D498
0x18007d479  test    byte ptr [rcx+1Ch], 1
0x18007d47d  jz      short loc_18007D498
0x18007d47f  mov     edx, 6Eh ; 'n'
0x18007d484  mov     r9d, ebx
0x18007d487  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d48e  mov     rcx, [rcx+10h]
0x18007d492  call    WPP_SF_d
0x18007d497  nop
0x18007d498  jmp     loc_18007D73D
0x18007d49d  mov     rcx, cs:off_180126498
0x18007d4a4  cmp     dword ptr [rcx], 0
0x18007d4a7  jnz     short loc_18007D4B3
0x18007d4a9  mov     rcx, [rcx+8]; pwk
0x18007d4ad  call    cs:__imp_SubmitThreadpoolWork
0x18007d4b3  mov     rcx, [rsp+78h+var_30]
0x18007d4b8  call    FwInitializeVfpPort
0x18007d4bd  mov     ebx, eax
0x18007d4bf  test    eax, eax
0x18007d4c1  jns     short loc_18007D506
0x18007d4c3  lea     rax, WPP_GLOBAL_Control
0x18007d4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4d1  cmp     rcx, rax
0x18007d4d4  jz      short loc_18007D501
0x18007d4d6  test    byte ptr [rcx+1Ch], 1
0x18007d4da  jz      short loc_18007D501
0x18007d4dc  mov     edx, 6Fh ; 'o'
0x18007d4e1  lea     rax, aFwhypervmgrcre_1; "FwHyperVMgrCreateHyperVPort:FwInitializ"...
0x18007d4e8  mov     [rsp+78h+var_58], rax
0x18007d4ed  mov     r9d, ebx
0x18007d4f0  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d4f7  mov     rcx, [rcx+10h]
0x18007d4fb  call    WPP_SF_Ds
0x18007d500  nop
0x18007d501  jmp     loc_18007D73D
0x18007d506  mov     edx, 1
0x18007d50b  mov     rcx, [rsp+78h+var_30]
0x18007d510  call    FwSetVfpPortBlock
0x18007d515  mov     ebx, eax
0x18007d517  test    eax, eax
0x18007d519  jns     short loc_18007D55E
0x18007d51b  lea     rax, WPP_GLOBAL_Control
0x18007d522  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d529  cmp     rcx, rax
0x18007d52c  jz      short loc_18007D559
0x18007d52e  test    byte ptr [rcx+1Ch], 1
0x18007d532  jz      short loc_18007D559
0x18007d534  mov     edx, 70h ; 'p'
0x18007d539  lea     rax, aFwhypervmgrcre_0; "FwHyperVMgrCreateHyperVPort:FwSetVfpPor"...
0x18007d540  mov     [rsp+78h+var_58], rax
0x18007d545  mov     r9d, ebx
0x18007d548  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d54f  mov     rcx, [rcx+10h]
0x18007d553  call    WPP_SF_Ds
0x18007d558  nop
0x18007d559  jmp     loc_18007D73D
0x18007d55e  mov     r9d, 1
0x18007d564  mov     r8, [rsp+78h+var_30]
0x18007d569  xor     edx, edx
0x18007d56b  lea     rcx, ?FwIP_HTTPS_InIsPortAllowed@@YAHG@Z; FwIP_HTTPS_InIsPortAllowed(ushort)
0x18007d572  call    FwHyperVMgrUpdateAllRulesForAllStores
0x18007d577  mov     ebx, eax
0x18007d579  test    eax, eax
0x18007d57b  jns     short loc_18007D5B4
0x18007d57d  lea     rax, WPP_GLOBAL_Control
0x18007d584  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d58b  cmp     rcx, rax
0x18007d58e  jz      short loc_18007D5AF
0x18007d590  test    byte ptr [rcx+1Ch], 1
0x18007d594  jz      short loc_18007D5AF
0x18007d596  mov     edx, 71h ; 'q'
0x18007d59b  mov     r9d, ebx
0x18007d59e  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d5a5  mov     rcx, [rcx+10h]
0x18007d5a9  call    WPP_SF_d
0x18007d5ae  nop
0x18007d5af  jmp     loc_18007D73D
0x18007d5b4  mov     rcx, [rsp+78h+var_30]
0x18007d5b9  call    FwApplyHyperVVMConfigs
0x18007d5be  mov     ebx, eax
0x18007d5c0  test    eax, eax
0x18007d5c2  jns     short loc_18007D5FB
0x18007d5c4  lea     rax, WPP_GLOBAL_Control
0x18007d5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5d2  cmp     rcx, rax
0x18007d5d5  jz      short loc_18007D5F6
0x18007d5d7  test    byte ptr [rcx+1Ch], 1
0x18007d5db  jz      short loc_18007D5F6
0x18007d5dd  mov     edx, 72h ; 'r'
0x18007d5e2  mov     r9d, ebx
0x18007d5e5  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d5ec  mov     rcx, [rcx+10h]
0x18007d5f0  call    WPP_SF_d
0x18007d5f5  nop
0x18007d5f6  jmp     loc_18007D73D
0x18007d5fb  xor     edx, edx
0x18007d5fd  mov     rcx, [rsp+78h+var_30]
0x18007d602  call    FwSetVfpPortBlock
0x18007d607  mov     ebx, eax
0x18007d609  test    eax, eax
0x18007d60b  jns     short loc_18007D650
0x18007d60d  lea     rax, WPP_GLOBAL_Control
0x18007d614  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d61b  cmp     rcx, rax
0x18007d61e  jz      short loc_18007D64B
0x18007d620  test    byte ptr [rcx+1Ch], 1
0x18007d624  jz      short loc_18007D64B
0x18007d626  mov     edx, 73h ; 's'
0x18007d62b  lea     rax, aFwhypervmgrcre_0; "FwHyperVMgrCreateHyperVPort:FwSetVfpPor"...
0x18007d632  mov     [rsp+78h+var_58], rax
0x18007d637  mov     r9d, ebx
0x18007d63a  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d641  mov     rcx, [rcx+10h]
0x18007d645  call    WPP_SF_Ds
0x18007d64a  nop
0x18007d64b  jmp     loc_18007D73D
0x18007d650  mov     rdx, cs:qword_18012C968
0x18007d657  cmp     rdx, cs:qword_18012C970
0x18007d65e  jz      short loc_18007D67C
0x18007d660  mov     rax, [rsp+78h+var_30]
0x18007d665  mov     [rdx], rax
0x18007d668  mov     rax, cs:qword_18012C968
0x18007d66f  add     rax, 8
0x18007d673  mov     cs:qword_18012C968, rax
0x18007d67a  jmp     short loc_18007D694
0x18007d67c  lea     r8, [rsp+78h+var_30]
0x18007d681  lea     rcx, qword_18012C960
0x18007d688  call    ??$_Emplace_reallocate@AEBQEAU_tag_FW_HYPERV_PORT1@@@?$vector@PEAU_tag_FW_HYPERV_PORT1@@V?$allocator@PEAU_tag_FW_HYPERV_PORT1@@@std@@@std@@AEAAPEAPEAU_tag_FW_HYPERV_PORT1@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_tag_FW_HYPERV_PORT1 *>::_Emplace_reallocate<_tag_FW_HYPERV_PORT1 * const &>(_tag_FW_HYPERV_PORT1 * * const,_tag_FW_HYPERV_PORT1 * const &)
0x18007d68d  mov     rax, cs:qword_18012C968
0x18007d694  sub     rax, cs:qword_18012C960
0x18007d69b  cmp     rax, 8
0x18007d69f  jnz     loc_18007D727
0x18007d6a5  lea     rax, FwHyperVSleepNotificationHandler
0x18007d6ac  mov     [rsp+78h+var_28], rax
0x18007d6b1  mov     [rsp+78h+var_20], 0
0x18007d6ba  cmp     qword ptr cs:xmmword_18012D0C0, 0
0x18007d6c2  jz      short loc_18007D6C9
0x18007d6c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007d6c9  lea     r8, xmmword_18012D0C0
0x18007d6d0  lea     rdx, [rsp+78h+var_28]
0x18007d6d5  mov     ecx, 2
0x18007d6da  call    cs:__imp_PowerRegisterSuspendResumeNotification
0x18007d6e0  mov     ebx, eax
0x18007d6e2  test    eax, eax
0x18007d6e4  jle     short loc_18007D6EF
0x18007d6e6  movzx   ebx, ax
0x18007d6e9  or      ebx, 80070000h
0x18007d6ef  test    ebx, ebx
0x18007d6f1  jns     short loc_18007D727
0x18007d6f3  lea     rax, WPP_GLOBAL_Control
0x18007d6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d701  cmp     rcx, rax
0x18007d704  jz      short loc_18007D725
0x18007d706  test    byte ptr [rcx+1Ch], 1
0x18007d70a  jz      short loc_18007D725
0x18007d70c  mov     edx, 74h ; 't'
0x18007d711  mov     r9d, ebx
0x18007d714  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18007d71b  mov     rcx, [rcx+10h]
0x18007d71f  call    WPP_SF_d
0x18007d724  nop
0x18007d725  jmp     short loc_18007D73D
0x18007d727  mov     [rsp+78h+var_30], 0
0x18007d730  jmp     short loc_18007D73D
0x18007d732  mov     ebx, [rsp+78h+var_44]
0x18007d736  cmp     [rsp+78h+var_48], 1
0x18007d73b  jnz     short loc_18007D742
0x18007d73d  call    FwHyperVMgrUnlock
0x18007d742  cmp     [rsp+78h+var_40], 0
0x18007d747  jz      short loc_18007D757
0x18007d749  lea     rdx, aFwhypervmgrcre_2; "FwHyperVMgrCreateHyperVPort"
0x18007d750  xor     ecx, ecx; void *
0x18007d752  call    FwUnlockInternal
0x18007d757  mov     edx, 221h
0x18007d75c  mov     rcx, [rsp+78h+var_30]
0x18007d761  call    cs:__imp_FwFreeHyperVPortsBySchemaVersion
0x18007d767  mov     eax, ebx
0x18007d769  mov     rcx, [rsp+78h+var_18]
0x18007d76e  xor     rcx, rsp; StackCookie
0x18007d771  call    __security_check_cookie
0x18007d776  mov     rbx, [rsp+78h+arg_8]
0x18007d77e  add     rsp, 70h
0x18007d782  pop     rsi
0x18007d783  retn
```
