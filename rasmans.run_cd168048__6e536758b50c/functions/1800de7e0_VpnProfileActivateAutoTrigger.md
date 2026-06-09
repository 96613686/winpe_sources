# VpnProfileActivateAutoTrigger

- ea: `0x1800de7e0`
- end: `0x1800def8a`
- name: `VpnProfileActivateAutoTrigger`
- size: `1962`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d9a60`
- `0x1800dcc40`
- `0x1800dd940`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x18000ebe8`
- `0x1800ac78c`
- `0x1800ac87c`
- `0x1800acc68`
- `0x1800b06e4`
- `0x1800de24c`
- `0x1800de658`
- `0x1800de7e0`
- `0x1800e3fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deb7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deb7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dec30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dec30`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800de841`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800de841`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800dee34`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800dee34`
- `fwpuclnt!FwpiVpnTriggerAddAppSids` at `0x1800de989`
- `fwpuclnt!FwpiVpnTriggerAddAppSids` at `0x1800de989`
- `fwpuclnt!FwpiVpnTriggerConfigureParameters` at `0x1800de894`
- `fwpuclnt!FwpiVpnTriggerConfigureParameters` at `0x1800de894`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800de9f4`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800de9f4`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800dec7f`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800dec7f`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800deadd`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800deadd`
- `fwpuclnt!FwpiVpnTriggerAddSecurityDescriptor` at `0x1800debcb`
- `fwpuclnt!FwpiVpnTriggerAddSecurityDescriptor` at `0x1800debcb`
- `fwpuclnt!FwpiVpnTriggerAddFilePaths` at `0x1800dea72`
- `fwpuclnt!FwpiVpnTriggerAddFilePaths` at `0x1800dea72`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800deb70`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800deb70`

## string_xrefs

- `0x1800de8d1`: `FwpiVpnTriggerConfigureParameters`
- `0x1800dec50`: `FwpiVpnTriggerAddSecurityDescriptor`
- `0x1800de9c5`: `FwpiVpnTriggerAddAppSids`
- `0x1800deaae`: `FwpiVpnTriggerAddFilePaths`

## pseudocode

```c
__int64 __fastcall VpnProfileActivateAutoTrigger(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  struct _LIST_ENTRY *v6; // rcx
  int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  const char *v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  unsigned int v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // rcx
  DWORD LastError; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v25; // r8d
  unsigned int v26; // eax
  unsigned int v27; // eax
  struct _LIST_ENTRY *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned int v31; // eax
  unsigned int appended; // eax
  struct _LIST_ENTRY *v33; // rcx
  __int64 v34; // rdx
  ULONG SecurityDescriptorSize; // [rsp+68h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+18h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 670, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, a4);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v7 = *(_DWORD *)(a1 + 24);
    if ( v7 != WTSGetActiveConsoleSessionId() )
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 672, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      }
      return v8;
    }
    v9 = FwpiVpnTriggerConfigureParameters(g_FwpEngineHandle, *(unsigned int *)(*(_QWORD *)(a1 + 592) + 124LL));
    v8 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 673, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v9);
      }
      v10 = "FwpiVpnTriggerConfigureParameters";
      goto LABEL_14;
    }
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
  {
    WPP_SF_S(v6[1].Flink, 674, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, *(_QWORD *)(a1 + 8));
    v6 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v6, VpnAutoTriggerProfileActivated, *(_QWORD *)(a1 + 8));
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v11 = *(unsigned int *)(*(_QWORD *)(a1 + 592) + 24LL);
    if ( (_DWORD)v11 )
    {
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
        WPP_SF_d(v6[1].Flink, 675, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v11);
      v12 = FwpiVpnTriggerAddAppSids(
              g_FwpEngineHandle,
              *(unsigned int *)(*(_QWORD *)(a1 + 592) + 24LL),
              *(_QWORD *)(*(_QWORD *)(a1 + 592) + 32LL));
      v8 = v12;
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 676, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v12);
        }
        v10 = "FwpiVpnTriggerAddAppSids";
        goto LABEL_14;
      }
    }
    else
    {
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
        WPP_SF_(v6[1].Flink, 677, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      v13 = FwpiVpnTriggerRemoveAppSids(g_FwpEngineHandle);
      if ( v13 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
LABEL_39:
          v15 = *(unsigned int *)(*(_QWORD *)(a1 + 592) + 40LL);
          if ( (_DWORD)v15 )
          {
            if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v14[1].Blink) & 4) != 0 )
              WPP_SF_d(v14[1].Flink, 679, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v15);
            v16 = FwpiVpnTriggerAddFilePaths(
                    g_FwpEngineHandle,
                    *(unsigned int *)(*(_QWORD *)(a1 + 592) + 40LL),
                    *(_QWORD *)(*(_QWORD *)(a1 + 592) + 48LL));
            v8 = v16;
            if ( v16 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 680, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v16);
              }
              v10 = "FwpiVpnTriggerAddFilePaths";
              goto LABEL_14;
            }
          }
          else
          {
            if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v14[1].Blink) & 4) != 0 )
              WPP_SF_(v14[1].Flink, 681, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
            v17 = FwpiVpnTriggerRemoveFilePaths(g_FwpEngineHandle);
            if ( v17 )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              {
LABEL_56:
                if ( !*(_QWORD *)(*(_QWORD *)(a1 + 592) + 56LL) )
                {
                  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
                    WPP_SF_(v18[1].Flink, 687, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                  v22 = FwpiVpnTriggerRemoveSecurityDescriptor(g_FwpEngineHandle);
                  if ( v22 )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
                    {
                      goto LABEL_87;
                    }
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 688, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v22);
                  }
                  v6 = WPP_GLOBAL_Control;
                  goto LABEL_87;
                }
                if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
                  WPP_SF_(v18[1].Flink, 683, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                v19 = *(_QWORD *)(a1 + 592);
                SecurityDescriptor = 0;
                SecurityDescriptorSize = 0;
                ConvertStringSecurityDescriptorToSecurityDescriptorW(
                  *(LPCWSTR *)(v19 + 56),
                  1u,
                  &SecurityDescriptor,
                  &SecurityDescriptorSize);
                LastError = GetLastError();
                v8 = LastError;
                if ( LastError == 1332 )
                {
                  v8 = 0;
LABEL_74:
                  v6 = WPP_GLOBAL_Control;
                  goto LABEL_75;
                }
                if ( LastError )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    v21 = 686;
                    goto LABEL_73;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 684, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
                  }
                  LastError = FwpiVpnTriggerAddSecurityDescriptor(g_FwpEngineHandle, SecurityDescriptor);
                  v8 = LastError;
                  if ( !LastError )
                    goto LABEL_74;
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    v21 = 685;
LABEL_73:
                    WPP_SF_d(v6[1].Flink, v21, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
                    goto LABEL_74;
                  }
                }
LABEL_75:
                if ( SecurityDescriptor )
                {
                  LocalFree(SecurityDescriptor);
                  v6 = WPP_GLOBAL_Control;
                  SecurityDescriptor = 0;
                }
                if ( v8 )
                {
                  v10 = "FwpiVpnTriggerAddSecurityDescriptor";
LABEL_14:
                  VpnReportError("VpnProfileActivateAutoTrigger", v10, v8);
LABEL_138:
                  v33 = WPP_GLOBAL_Control;
                  goto LABEL_139;
                }
                goto LABEL_87;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 682, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v17);
            }
          }
          v18 = WPP_GLOBAL_Control;
          goto LABEL_56;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 678, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
      }
    }
    v14 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
LABEL_87:
  if ( **(_DWORD **)(a1 + 592) )
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
      WPP_SF_(v6[1].Flink, 689, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    v23 = qword_18010F190;
    if ( !a2 )
      v23 = qword_18010F3F0;
    v24 = RasRemoveNrptRules(*(_QWORD *)(v23 + 16));
    if ( v24
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 690, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v24);
    }
    v26 = RasAddNrptRulesEx(*(_QWORD *)(*(_QWORD *)(a1 + 592) + 8LL), **(_DWORD **)(a1 + 592), v25, 0, 0, 1);
    if ( v26
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 691, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v26);
    }
    v27 = RasAddNrptRules(*(_QWORD *)(*(_QWORD *)(a1 + 592) + 112LL), *(unsigned int *)(*(_QWORD *)(a1 + 592) + 120LL));
    if ( !v27 )
      goto LABEL_121;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v29 = 692;
LABEL_120:
      WPP_SF_d(v28[1].Flink, v29, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v27);
LABEL_121:
      v28 = WPP_GLOBAL_Control;
      goto LABEL_122;
    }
    goto LABEL_122;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
    WPP_SF_(v6[1].Flink, 693, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  v30 = qword_18010F190;
  if ( !a2 )
    v30 = qword_18010F3F0;
  v31 = RasRemoveNrptRules(*(_QWORD *)(v30 + 16));
  if ( !v31 )
    goto LABEL_114;
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 694, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v31);
LABEL_114:
    v28 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_122;
  int_VpnProfileUnPlumbWfpFilter();
  v27 = FwpiVpnTriggerResetNrptTriggering(g_FwpEngineHandle);
  if ( !v27 )
    goto LABEL_121;
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v29 = 695;
    goto LABEL_120;
  }
LABEL_122:
  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 592) + 80LL) )
  {
    if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v28[1].Blink) & 4) != 0 )
      WPP_SF_(v28[1].Flink, 698, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    appended = AppendDnsSuffixSearchListToGlobalList(0, 0);
    v8 = appended;
    if ( !appended )
      goto LABEL_142;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_143;
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      goto LABEL_139;
    v34 = 699;
LABEL_137:
    WPP_SF_d(v33[1].Flink, v34, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, appended);
    goto LABEL_138;
  }
  if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v28[1].Blink) & 4) != 0 )
    WPP_SF_(v28[1].Flink, 696, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  appended = AppendDnsSuffixSearchListToGlobalList(
               *(_QWORD *)(*(_QWORD *)(a1 + 592) + 88LL),
               *(unsigned int *)(*(_QWORD *)(a1 + 592) + 80LL));
  v8 = appended;
  if ( !appended )
    goto LABEL_142;
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
LABEL_139:
      if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v33[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(v33[1].Flink, 700, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v8);
LABEL_142:
        v33 = WPP_GLOBAL_Control;
        goto LABEL_143;
      }
      goto LABEL_143;
    }
    v34 = 697;
    goto LABEL_137;
  }
LABEL_143:
  if ( (v8 & 0x80000000) != 0 && v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v33[1].Blink) & 8) != 0 )
    WPP_SF_d(v33[1].Flink, 701, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800de7e0  mov     [rsp+arg_0], rbx
0x1800de7e5  push    rbp
0x1800de7e6  push    rdi
0x1800de7e7  push    r13
0x1800de7e9  push    r14
0x1800de7eb  push    r15
0x1800de7ed  sub     rsp, 30h
0x1800de7f1  mov     r14d, edx
0x1800de7f4  mov     rbp, rcx
0x1800de7f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de7fe  lea     r15, WPP_GLOBAL_Control
0x1800de805  lea     r13, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800de80c  cmp     rcx, r15
0x1800de80f  jz      short loc_1800DE835
0x1800de811  test    byte ptr [rcx+1Ch], 8
0x1800de815  jz      short loc_1800DE835
0x1800de817  mov     rcx, [rcx+10h]
0x1800de81b  test    edx, edx
0x1800de81d  mov     edx, 29Eh
0x1800de822  mov     r8, r13
0x1800de825  setnz   r9b
0x1800de829  call    WPP_SF_c
0x1800de82e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de835  test    r14d, r14d
0x1800de838  jz      loc_1800DE8F3
0x1800de83e  mov     ebx, [rbp+18h]
0x1800de841  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800de848  nop     dword ptr [rax+rax+00h]
0x1800de84d  cmp     ebx, eax
0x1800de84f  jz      short loc_1800DE883
0x1800de851  xor     ebx, ebx
0x1800de853  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de85a  cmp     rcx, r15
0x1800de85d  jz      loc_1800DEF75
0x1800de863  test    byte ptr [rcx+1Ch], 4
0x1800de867  jz      loc_1800DEF75
0x1800de86d  mov     rcx, [rcx+10h]
0x1800de871  mov     edx, 2A0h
0x1800de876  mov     r8, r13
0x1800de879  call    WPP_SF_
0x1800de87e  jmp     loc_1800DEF75
0x1800de883  mov     rdx, [rbp+250h]
0x1800de88a  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de891  mov     edx, [rdx+7Ch]
0x1800de894  call    cs:__imp_FwpiVpnTriggerConfigureParameters
0x1800de89b  nop     dword ptr [rax+rax+00h]
0x1800de8a0  mov     ebx, eax
0x1800de8a2  test    eax, eax
0x1800de8a4  jz      short loc_1800DE8EC
0x1800de8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de8ad  mov     edi, 1
0x1800de8b2  cmp     rcx, r15
0x1800de8b5  jz      short loc_1800DE8D1
0x1800de8b7  test    [rcx+1Ch], dil
0x1800de8bb  jz      short loc_1800DE8D1
0x1800de8bd  mov     rcx, [rcx+10h]
0x1800de8c1  mov     edx, 2A1h
0x1800de8c6  mov     r9d, eax
0x1800de8c9  mov     r8, r13
0x1800de8cc  call    WPP_SF_d
0x1800de8d1  lea     rdx, aFwpivpntrigger_2; "FwpiVpnTriggerConfigureParameters"
0x1800de8d8  mov     r8d, ebx
0x1800de8db  lea     rcx, aVpnprofileacti_0; "VpnProfileActivateAutoTrigger"
0x1800de8e2  call    VpnReportError
0x1800de8e7  jmp     loc_1800DEF25
0x1800de8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de8f3  cmp     rcx, r15
0x1800de8f6  jz      short loc_1800DE91A
0x1800de8f8  test    byte ptr [rcx+1Ch], 4
0x1800de8fc  jz      short loc_1800DE91A
0x1800de8fe  mov     r9, [rbp+8]
0x1800de902  mov     edx, 2A2h
0x1800de907  mov     rcx, [rcx+10h]
0x1800de90b  mov     r8, r13
0x1800de90e  call    WPP_SF_S
0x1800de913  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de91a  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800de921  jz      short loc_1800DE93A
0x1800de923  mov     r8, [rbp+8]
0x1800de927  lea     rdx, VpnAutoTriggerProfileActivated
0x1800de92e  call    McTemplateU0z_EventWriteTransfer
0x1800de933  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de93a  mov     edi, 1
0x1800de93f  test    r14d, r14d
0x1800de942  jz      loc_1800DECBC
0x1800de948  mov     rax, [rbp+250h]
0x1800de94f  mov     r9d, [rax+18h]
0x1800de953  test    r9d, r9d
0x1800de956  jz      short loc_1800DE9D1
0x1800de958  cmp     rcx, r15
0x1800de95b  jz      short loc_1800DE974
0x1800de95d  test    byte ptr [rcx+1Ch], 4
0x1800de961  jz      short loc_1800DE974
0x1800de963  mov     rcx, [rcx+10h]
0x1800de967  mov     edx, 2A3h
0x1800de96c  mov     r8, r13
0x1800de96f  call    WPP_SF_d
0x1800de974  mov     rdx, [rbp+250h]
0x1800de97b  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de982  mov     r8, [rdx+20h]
0x1800de986  mov     edx, [rdx+18h]
0x1800de989  call    cs:__imp_FwpiVpnTriggerAddAppSids
0x1800de990  nop     dword ptr [rax+rax+00h]
0x1800de995  mov     ebx, eax
0x1800de997  test    eax, eax
0x1800de999  jz      loc_1800DEA2A
0x1800de99f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800de9a6  cmp     rcx, r15
0x1800de9a9  jz      short loc_1800DE9C5
0x1800de9ab  test    [rcx+1Ch], dil
0x1800de9af  jz      short loc_1800DE9C5
0x1800de9b1  mov     rcx, [rcx+10h]
0x1800de9b5  mov     edx, 2A4h
0x1800de9ba  mov     r9d, eax
0x1800de9bd  mov     r8, r13
0x1800de9c0  call    WPP_SF_d
0x1800de9c5  lea     rdx, aFwpivpntrigger; "FwpiVpnTriggerAddAppSids"
0x1800de9cc  jmp     loc_1800DE8D8
0x1800de9d1  cmp     rcx, r15
0x1800de9d4  jz      short loc_1800DE9ED
0x1800de9d6  test    byte ptr [rcx+1Ch], 4
0x1800de9da  jz      short loc_1800DE9ED
0x1800de9dc  mov     rcx, [rcx+10h]
0x1800de9e0  mov     edx, 2A5h
0x1800de9e5  mov     r8, r13
0x1800de9e8  call    WPP_SF_
0x1800de9ed  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800de9f4  call    cs:__imp_FwpiVpnTriggerRemoveAppSids
0x1800de9fb  nop     dword ptr [rax+rax+00h]
0x1800dea00  test    eax, eax
0x1800dea02  jz      short loc_1800DEA2A
0x1800dea04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dea0b  cmp     rcx, r15
0x1800dea0e  jz      short loc_1800DEA31
0x1800dea10  test    [rcx+1Ch], dil
0x1800dea14  jz      short loc_1800DEA31
0x1800dea16  mov     rcx, [rcx+10h]
0x1800dea1a  mov     edx, 2A6h
0x1800dea1f  mov     r9d, eax
0x1800dea22  mov     r8, r13
0x1800dea25  call    WPP_SF_d
0x1800dea2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dea31  mov     rax, [rbp+250h]
0x1800dea38  mov     r9d, [rax+28h]
0x1800dea3c  test    r9d, r9d
0x1800dea3f  jz      short loc_1800DEABA
0x1800dea41  cmp     rcx, r15
0x1800dea44  jz      short loc_1800DEA5D
0x1800dea46  test    byte ptr [rcx+1Ch], 4
0x1800dea4a  jz      short loc_1800DEA5D
0x1800dea4c  mov     rcx, [rcx+10h]
0x1800dea50  mov     edx, 2A7h
0x1800dea55  mov     r8, r13
0x1800dea58  call    WPP_SF_d
0x1800dea5d  mov     rdx, [rbp+250h]
0x1800dea64  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800dea6b  mov     r8, [rdx+30h]
0x1800dea6f  mov     edx, [rdx+28h]
0x1800dea72  call    cs:__imp_FwpiVpnTriggerAddFilePaths
0x1800dea79  nop     dword ptr [rax+rax+00h]
0x1800dea7e  mov     ebx, eax
0x1800dea80  test    eax, eax
0x1800dea82  jz      loc_1800DEB13
0x1800dea88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dea8f  cmp     rcx, r15
0x1800dea92  jz      short loc_1800DEAAE
0x1800dea94  test    [rcx+1Ch], dil
0x1800dea98  jz      short loc_1800DEAAE
0x1800dea9a  mov     rcx, [rcx+10h]
0x1800dea9e  mov     edx, 2A8h
0x1800deaa3  mov     r9d, eax
0x1800deaa6  mov     r8, r13
0x1800deaa9  call    WPP_SF_d
0x1800deaae  lea     rdx, aFwpivpntrigger_3; "FwpiVpnTriggerAddFilePaths"
0x1800deab5  jmp     loc_1800DE8D8
0x1800deaba  cmp     rcx, r15
0x1800deabd  jz      short loc_1800DEAD6
0x1800deabf  test    byte ptr [rcx+1Ch], 4
0x1800deac3  jz      short loc_1800DEAD6
0x1800deac5  mov     rcx, [rcx+10h]
0x1800deac9  mov     edx, 2A9h
0x1800deace  mov     r8, r13
0x1800dead1  call    WPP_SF_
0x1800dead6  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800deadd  call    cs:__imp_FwpiVpnTriggerRemoveFilePaths
0x1800deae4  nop     dword ptr [rax+rax+00h]
0x1800deae9  test    eax, eax
0x1800deaeb  jz      short loc_1800DEB13
0x1800deaed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800deaf4  cmp     rcx, r15
0x1800deaf7  jz      short loc_1800DEB1A
0x1800deaf9  test    [rcx+1Ch], dil
0x1800deafd  jz      short loc_1800DEB1A
0x1800deaff  mov     rcx, [rcx+10h]
0x1800deb03  mov     edx, 2AAh
0x1800deb08  mov     r9d, eax
0x1800deb0b  mov     r8, r13
0x1800deb0e  call    WPP_SF_d
0x1800deb13  mov     rcx, cs:WPP_GLOBAL_Control
0x1800deb1a  mov     rax, [rbp+250h]
0x1800deb21  cmp     qword ptr [rax+38h], 0
0x1800deb26  jz      loc_1800DEC5C
0x1800deb2c  cmp     rcx, r15
0x1800deb2f  jz      short loc_1800DEB48
0x1800deb31  test    byte ptr [rcx+1Ch], 4
0x1800deb35  jz      short loc_1800DEB48
0x1800deb37  mov     rcx, [rcx+10h]
0x1800deb3b  mov     edx, 2ABh
0x1800deb40  mov     r8, r13
0x1800deb43  call    WPP_SF_
0x1800deb48  mov     rcx, [rbp+250h]
0x1800deb4f  lea     r9, [rsp+58h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800deb54  mov     [rsp+58h+SecurityDescriptor], 0
0x1800deb5d  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800deb62  mov     [rsp+58h+SecurityDescriptorSize], 0
0x1800deb6a  mov     edx, edi; StringSDRevision
0x1800deb6c  mov     rcx, [rcx+38h]; StringSecurityDescriptor
0x1800deb70  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800deb77  nop     dword ptr [rax+rax+00h]
0x1800deb7c  call    cs:__imp_GetLastError
0x1800deb83  nop     dword ptr [rax+rax+00h]
0x1800deb88  mov     ebx, eax
0x1800deb8a  cmp     eax, 534h
0x1800deb8f  jnz     short loc_1800DEB98
0x1800deb91  xor     ebx, ebx
0x1800deb93  jmp     loc_1800DEC1C
0x1800deb98  test    eax, eax
0x1800deb9a  jnz     short loc_1800DEBF6
0x1800deb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800deba3  cmp     rcx, r15
0x1800deba6  jz      short loc_1800DEBBF
0x1800deba8  test    byte ptr [rcx+1Ch], 4
0x1800debac  jz      short loc_1800DEBBF
0x1800debae  mov     rcx, [rcx+10h]
0x1800debb2  mov     edx, 2ACh
0x1800debb7  mov     r8, r13
0x1800debba  call    WPP_SF_
0x1800debbf  mov     rdx, [rsp+58h+SecurityDescriptor]
0x1800debc4  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800debcb  call    cs:__imp_FwpiVpnTriggerAddSecurityDescriptor
0x1800debd2  nop     dword ptr [rax+rax+00h]
0x1800debd7  mov     ebx, eax
0x1800debd9  test    eax, eax
0x1800debdb  jz      short loc_1800DEC1C
0x1800debdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800debe4  cmp     rcx, r15
0x1800debe7  jz      short loc_1800DEC23
0x1800debe9  test    [rcx+1Ch], dil
0x1800debed  jz      short loc_1800DEC23
0x1800debef  mov     edx, 2ADh
0x1800debf4  jmp     short loc_1800DEC0D
0x1800debf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800debfd  cmp     rcx, r15
0x1800dec00  jz      short loc_1800DEC23
0x1800dec02  test    [rcx+1Ch], dil
0x1800dec06  jz      short loc_1800DEC23
0x1800dec08  mov     edx, 2AEh
0x1800dec0d  mov     rcx, [rcx+10h]
0x1800dec11  mov     r9d, eax
0x1800dec14  mov     r8, r13
0x1800dec17  call    WPP_SF_d
0x1800dec1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dec23  mov     rax, [rsp+58h+SecurityDescriptor]
0x1800dec28  test    rax, rax
0x1800dec2b  jz      short loc_1800DEC4C
0x1800dec2d  mov     rcx, rax; hMem
0x1800dec30  call    cs:__imp_LocalFree
0x1800dec37  nop     dword ptr [rax+rax+00h]
0x1800dec3c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dec43  mov     [rsp+58h+SecurityDescriptor], 0
0x1800dec4c  test    ebx, ebx
0x1800dec4e  jz      short loc_1800DECBC
0x1800dec50  lea     rdx, aFwpivpntrigger_0; "FwpiVpnTriggerAddSecurityDescriptor"
0x1800dec57  jmp     loc_1800DE8D8
0x1800dec5c  cmp     rcx, r15
0x1800dec5f  jz      short loc_1800DEC78
0x1800dec61  test    byte ptr [rcx+1Ch], 4
0x1800dec65  jz      short loc_1800DEC78
0x1800dec67  mov     rcx, [rcx+10h]
0x1800dec6b  mov     edx, 2AFh
0x1800dec70  mov     r8, r13
0x1800dec73  call    WPP_SF_
0x1800dec78  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800dec7f  call    cs:__imp_FwpiVpnTriggerRemoveSecurityDescriptor
0x1800dec86  nop     dword ptr [rax+rax+00h]
0x1800dec8b  test    eax, eax
0x1800dec8d  jz      short loc_1800DECB5
0x1800dec8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dec96  cmp     rcx, r15
0x1800dec99  jz      short loc_1800DECBC
0x1800dec9b  test    [rcx+1Ch], dil
0x1800dec9f  jz      short loc_1800DECBC
0x1800deca1  mov     rcx, [rcx+10h]
0x1800deca5  mov     edx, 2B0h
0x1800decaa  mov     r9d, eax
0x1800decad  mov     r8, r13
0x1800decb0  call    WPP_SF_d
0x1800decb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800decbc  mov     rax, [rbp+250h]
0x1800decc3  cmp     dword ptr [rax], 0
  ... truncated ...
```
