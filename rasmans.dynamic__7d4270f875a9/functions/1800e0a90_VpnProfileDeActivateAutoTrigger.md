# VpnProfileDeActivateAutoTrigger

- ea: `0x1800e0a90`
- end: `0x1800e0e2b`
- name: `VpnProfileDeActivateAutoTrigger`
- size: `923`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cf37c`
- `0x1800d9a60`
- `0x1800dcc40`
- `0x1800dd940`
- `0x1800df33c`
- `0x1800e1f2c`

## callees

- `0x180005bfc`
- `0x180033b38`
- `0x18005bfd8`
- `0x1800acc68`
- `0x1800b06e4`
- `0x1800d9770`
- `0x1800de24c`
- `0x1800de658`
- `0x1800e0a90`

## import_xrefs

- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800e0d68`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800e0d68`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800e0bb2`
- `fwpuclnt!FwpiVpnTriggerSetStateDisconnected` at `0x1800e0bb2`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800e0c2b`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800e0c2b`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800e0cb6`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800e0cb6`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800e0c79`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800e0c79`

## pseudocode

```c
__int64 __fastcall VpnProfileDeActivateAutoTrigger(int a1, int a2, unsigned int a3, __int64 a4)
{
  __int64 *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  int *v11; // rax
  __int64 *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rax
  LPCWSTR v15; // r8
  unsigned int v16; // eax
  int v17; // ebx
  struct _LIST_ENTRY *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rax
  unsigned int appended; // eax

  v7 = (__int64 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_cc(WPP_GLOBAL_Control[1].Flink, 660, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, a4, a2 != 0);
  }
  if ( a1 )
  {
    v8 = dword_18010EF60;
    if ( !a2 )
      v8 = dword_18010F1C0;
    if ( v8 == 1 )
    {
      v7 = (__int64 *)qword_18010EF68;
      if ( !a2 )
        v7 = (__int64 *)qword_18010F1C8;
      if ( v7 )
      {
        int_ScheduleDisconnect(v7, 0, a3);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v9 = InterfaceIndex;
          v10 = (unsigned int)dword_18010EF60;
          if ( !a2 )
          {
            v9 = dword_18010F3E4;
            v10 = (unsigned int)dword_18010F1C0;
          }
          WPP_SF_ddd(WPP_GLOBAL_Control[1].Flink, 661, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v10, 0, v9);
        }
        v11 = &dword_18010EF60;
        if ( !a2 )
          v11 = &dword_18010F1C0;
        v7 = &qword_18010F1C8;
        *v11 = 0;
        v12 = &qword_18010EF68;
        if ( !a2 )
          v12 = &qword_18010F1C8;
        *v12 = 0;
        if ( a2 )
        {
          v13 = FwpiVpnTriggerSetStateDisconnected(g_FwpEngineHandle, 0);
          if ( v13 )
          {
            v7 = (__int64 *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 662, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
            }
          }
        }
      }
    }
  }
  v14 = qword_18010F190;
  if ( !a2 )
    v14 = qword_18010F3F0;
  if ( v14 && (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    v15 = qword_18010EF48;
    if ( !a2 )
      v15 = qword_18010F1A8;
    McTemplateU0z_EventWriteTransfer(v7, VpnAutoTriggerProfileDeactivated, v15);
  }
  v16 = FwpiVpnTriggerRemoveAppSids(g_FwpEngineHandle);
  v17 = v16;
  if ( !v16 )
    goto LABEL_36;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 663, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v16);
LABEL_36:
    v18 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v19 = FwpiVpnTriggerRemoveFilePaths(g_FwpEngineHandle);
    if ( v19
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 664, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v19);
    }
    v20 = FwpiVpnTriggerRemoveSecurityDescriptor(g_FwpEngineHandle);
    v17 = v20;
    if ( v20
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 665, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v20);
    }
    int_VpnProfileUnPlumbWfpFilter();
    v18 = WPP_GLOBAL_Control;
  }
  v21 = qword_18010F190;
  if ( !a2 )
    v21 = qword_18010F3F0;
  if ( v21 && *(_QWORD *)(v21 + 16) )
  {
    v22 = RasRemoveNrptRules(*(_QWORD *)(v21 + 16), 1);
    v17 = v22;
    if ( !v22 )
    {
LABEL_55:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 666, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v22);
      goto LABEL_55;
    }
  }
LABEL_56:
  if ( !a2 )
    goto LABEL_62;
  int_VpnProfileUnPlumbWfpFilter();
  v23 = FwpiVpnTriggerResetNrptTriggering(g_FwpEngineHandle);
  v17 = v23;
  if ( !v23 )
    goto LABEL_61;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 667, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v23);
LABEL_61:
    v18 = WPP_GLOBAL_Control;
  }
LABEL_62:
  v24 = qword_18010F190;
  if ( !a2 )
    v24 = qword_18010F3F0;
  if ( v24 )
  {
    appended = AppendDnsSuffixSearchListToGlobalList(0, 0);
    v17 = appended;
    if ( !appended )
    {
LABEL_69:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_70;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 668, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, appended);
      goto LABEL_69;
    }
  }
LABEL_70:
  if ( v17 < 0 && v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 8) != 0 )
    WPP_SF_d(v18[1].Flink, 669, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800e0a90  push    rbx
0x1800e0a92  push    rsi
0x1800e0a93  push    rdi
0x1800e0a94  push    r12
0x1800e0a96  push    r15
0x1800e0a98  sub     rsp, 30h
0x1800e0a9c  mov     esi, r8d
0x1800e0a9f  mov     edi, edx
0x1800e0aa1  mov     ebx, ecx
0x1800e0aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0aaa  lea     r15, WPP_GLOBAL_Control
0x1800e0ab1  lea     r12, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e0ab8  cmp     rcx, r15
0x1800e0abb  jz      short loc_1800E0AE3
0x1800e0abd  test    byte ptr [rcx+1Ch], 8
0x1800e0ac1  jz      short loc_1800E0AE3
0x1800e0ac3  mov     rcx, [rcx+10h]
0x1800e0ac7  test    edx, edx
0x1800e0ac9  mov     edx, 294h
0x1800e0ace  mov     r8, r12
0x1800e0ad1  setnz   al
0x1800e0ad4  test    ebx, ebx
0x1800e0ad6  mov     byte ptr [rsp+58h+var_38], al
0x1800e0ada  setnz   r9b
0x1800e0ade  call    WPP_SF_cc
0x1800e0ae3  test    ebx, ebx
0x1800e0ae5  jz      loc_1800E0BE8
0x1800e0aeb  mov     eax, cs:dword_18010EF60
0x1800e0af1  test    edi, edi
0x1800e0af3  cmovz   eax, cs:dword_18010F1C0
0x1800e0afa  cmp     eax, 1
0x1800e0afd  jnz     loc_1800E0BE8
0x1800e0b03  mov     rcx, cs:qword_18010EF68
0x1800e0b0a  test    edi, edi
0x1800e0b0c  cmovz   rcx, cs:qword_18010F1C8
0x1800e0b14  test    rcx, rcx
0x1800e0b17  jz      loc_1800E0BE8
0x1800e0b1d  mov     r8d, esi
0x1800e0b20  xor     edx, edx
0x1800e0b22  call    ?int_ScheduleDisconnect@@YAKPEAUHRASCONN__@@HW4_SCHEDULED_DISCONNECT_REASON@@@Z; int_ScheduleDisconnect(HRASCONN__ *,int,_SCHEDULED_DISCONNECT_REASON)
0x1800e0b27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0b2e  cmp     rcx, r15
0x1800e0b31  jz      short loc_1800E0B74
0x1800e0b33  test    byte ptr [rcx+1Ch], 4
0x1800e0b37  jz      short loc_1800E0B74
0x1800e0b39  mov     eax, cs:InterfaceIndex
0x1800e0b3f  test    edi, edi
0x1800e0b41  mov     r9d, cs:dword_18010EF60
0x1800e0b48  mov     edx, 295h
0x1800e0b4d  cmovz   eax, cs:dword_18010F3E4
0x1800e0b54  mov     r8, r12
0x1800e0b57  cmovz   r9d, cs:dword_18010F1C0
0x1800e0b5f  mov     rcx, [rcx+10h]
0x1800e0b63  mov     [rsp+58h+var_30], eax
0x1800e0b67  mov     [rsp+58h+var_38], 0
0x1800e0b6f  call    WPP_SF_ddd
0x1800e0b74  test    edi, edi
0x1800e0b76  lea     rcx, dword_18010F1C0
0x1800e0b7d  lea     rax, dword_18010EF60
0x1800e0b84  cmovz   rax, rcx
0x1800e0b88  lea     rcx, qword_18010F1C8
0x1800e0b8f  mov     dword ptr [rax], 0
0x1800e0b95  lea     rax, qword_18010EF68
0x1800e0b9c  cmovz   rax, rcx
0x1800e0ba0  mov     qword ptr [rax], 0
0x1800e0ba7  jz      short loc_1800E0BE8
0x1800e0ba9  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e0bb0  xor     edx, edx
0x1800e0bb2  call    cs:__imp_FwpiVpnTriggerSetStateDisconnected
0x1800e0bb9  nop     dword ptr [rax+rax+00h]
0x1800e0bbe  test    eax, eax
0x1800e0bc0  jz      short loc_1800E0BE8
0x1800e0bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0bc9  cmp     rcx, r15
0x1800e0bcc  jz      short loc_1800E0BE8
0x1800e0bce  test    byte ptr [rcx+1Ch], 1
0x1800e0bd2  jz      short loc_1800E0BE8
0x1800e0bd4  mov     rcx, [rcx+10h]
0x1800e0bd8  mov     edx, 296h
0x1800e0bdd  mov     r9d, eax
0x1800e0be0  mov     r8, r12
0x1800e0be3  call    WPP_SF_d
0x1800e0be8  mov     rax, cs:qword_18010F190
0x1800e0bef  test    edi, edi
0x1800e0bf1  cmovz   rax, cs:qword_18010F3F0
0x1800e0bf9  test    rax, rax
0x1800e0bfc  jz      short loc_1800E0C24
0x1800e0bfe  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800e0c05  jz      short loc_1800E0C24
0x1800e0c07  mov     r8, cs:qword_18010EF48
0x1800e0c0e  lea     rdx, VpnAutoTriggerProfileDeactivated
0x1800e0c15  test    edi, edi
0x1800e0c17  cmovz   r8, cs:qword_18010F1A8
0x1800e0c1f  call    McTemplateU0z_EventWriteTransfer
0x1800e0c24  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e0c2b  call    cs:__imp_FwpiVpnTriggerRemoveAppSids
0x1800e0c32  nop     dword ptr [rax+rax+00h]
0x1800e0c37  mov     ebx, eax
0x1800e0c39  test    eax, eax
0x1800e0c3b  jz      short loc_1800E0C63
0x1800e0c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0c44  cmp     rcx, r15
0x1800e0c47  jz      short loc_1800E0C6A
0x1800e0c49  test    byte ptr [rcx+1Ch], 1
0x1800e0c4d  jz      short loc_1800E0C6A
0x1800e0c4f  mov     rcx, [rcx+10h]
0x1800e0c53  mov     edx, 297h
0x1800e0c58  mov     r9d, eax
0x1800e0c5b  mov     r8, r12
0x1800e0c5e  call    WPP_SF_d
0x1800e0c63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0c6a  test    edi, edi
0x1800e0c6c  jz      loc_1800E0CFA
0x1800e0c72  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e0c79  call    cs:__imp_FwpiVpnTriggerRemoveFilePaths
0x1800e0c80  nop     dword ptr [rax+rax+00h]
0x1800e0c85  test    eax, eax
0x1800e0c87  jz      short loc_1800E0CAF
0x1800e0c89  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0c90  cmp     rcx, r15
0x1800e0c93  jz      short loc_1800E0CAF
0x1800e0c95  test    byte ptr [rcx+1Ch], 1
0x1800e0c99  jz      short loc_1800E0CAF
0x1800e0c9b  mov     rcx, [rcx+10h]
0x1800e0c9f  mov     edx, 298h
0x1800e0ca4  mov     r9d, eax
0x1800e0ca7  mov     r8, r12
0x1800e0caa  call    WPP_SF_d
0x1800e0caf  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e0cb6  call    cs:__imp_FwpiVpnTriggerRemoveSecurityDescriptor
0x1800e0cbd  nop     dword ptr [rax+rax+00h]
0x1800e0cc2  mov     ebx, eax
0x1800e0cc4  test    eax, eax
0x1800e0cc6  jz      short loc_1800E0CEE
0x1800e0cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0ccf  cmp     rcx, r15
0x1800e0cd2  jz      short loc_1800E0CEE
0x1800e0cd4  test    byte ptr [rcx+1Ch], 1
0x1800e0cd8  jz      short loc_1800E0CEE
0x1800e0cda  mov     rcx, [rcx+10h]
0x1800e0cde  mov     edx, 299h
0x1800e0ce3  mov     r9d, eax
0x1800e0ce6  mov     r8, r12
0x1800e0ce9  call    WPP_SF_d
0x1800e0cee  call    ?int_VpnProfileUnPlumbWfpFilter@@YAXXZ; int_VpnProfileUnPlumbWfpFilter(void)
0x1800e0cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0cfa  mov     rax, cs:qword_18010F190
0x1800e0d01  test    edi, edi
0x1800e0d03  cmovz   rax, cs:qword_18010F3F0
0x1800e0d0b  test    rax, rax
0x1800e0d0e  jz      short loc_1800E0D58
0x1800e0d10  cmp     qword ptr [rax+10h], 0
0x1800e0d15  jz      short loc_1800E0D58
0x1800e0d17  mov     rcx, [rax+10h]
0x1800e0d1b  mov     edx, 1
0x1800e0d20  call    RasRemoveNrptRules
0x1800e0d25  mov     ebx, eax
0x1800e0d27  test    eax, eax
0x1800e0d29  jz      short loc_1800E0D51
0x1800e0d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0d32  cmp     rcx, r15
0x1800e0d35  jz      short loc_1800E0D58
0x1800e0d37  test    byte ptr [rcx+1Ch], 1
0x1800e0d3b  jz      short loc_1800E0D58
0x1800e0d3d  mov     rcx, [rcx+10h]
0x1800e0d41  mov     edx, 29Ah
0x1800e0d46  mov     r9d, eax
0x1800e0d49  mov     r8, r12
0x1800e0d4c  call    WPP_SF_d
0x1800e0d51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0d58  test    edi, edi
0x1800e0d5a  jz      short loc_1800E0DA7
0x1800e0d5c  call    ?int_VpnProfileUnPlumbWfpFilter@@YAXXZ; int_VpnProfileUnPlumbWfpFilter(void)
0x1800e0d61  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800e0d68  call    cs:__imp_FwpiVpnTriggerResetNrptTriggering
0x1800e0d6f  nop     dword ptr [rax+rax+00h]
0x1800e0d74  mov     ebx, eax
0x1800e0d76  test    eax, eax
0x1800e0d78  jz      short loc_1800E0DA0
0x1800e0d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0d81  cmp     rcx, r15
0x1800e0d84  jz      short loc_1800E0DA7
0x1800e0d86  test    byte ptr [rcx+1Ch], 1
0x1800e0d8a  jz      short loc_1800E0DA7
0x1800e0d8c  mov     rcx, [rcx+10h]
0x1800e0d90  mov     edx, 29Bh
0x1800e0d95  mov     r9d, eax
0x1800e0d98  mov     r8, r12
0x1800e0d9b  call    WPP_SF_d
0x1800e0da0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0da7  mov     rax, cs:qword_18010F190
0x1800e0dae  test    edi, edi
0x1800e0db0  cmovz   rax, cs:qword_18010F3F0
0x1800e0db8  test    rax, rax
0x1800e0dbb  jz      short loc_1800E0DF9
0x1800e0dbd  xor     edx, edx
0x1800e0dbf  xor     ecx, ecx
0x1800e0dc1  call    AppendDnsSuffixSearchListToGlobalList
0x1800e0dc6  mov     ebx, eax
0x1800e0dc8  test    eax, eax
0x1800e0dca  jz      short loc_1800E0DF2
0x1800e0dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0dd3  cmp     rcx, r15
0x1800e0dd6  jz      short loc_1800E0DF9
0x1800e0dd8  test    byte ptr [rcx+1Ch], 1
0x1800e0ddc  jz      short loc_1800E0DF9
0x1800e0dde  mov     rcx, [rcx+10h]
0x1800e0de2  mov     edx, 29Ch
0x1800e0de7  mov     r9d, eax
0x1800e0dea  mov     r8, r12
0x1800e0ded  call    WPP_SF_d
0x1800e0df2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0df9  test    ebx, ebx
0x1800e0dfb  jns     short loc_1800E0E1C
0x1800e0dfd  cmp     rcx, r15
0x1800e0e00  jz      short loc_1800E0E1C
0x1800e0e02  test    byte ptr [rcx+1Ch], 8
0x1800e0e06  jz      short loc_1800E0E1C
0x1800e0e08  mov     rcx, [rcx+10h]
0x1800e0e0c  mov     edx, 29Dh
0x1800e0e11  mov     r9d, ebx
0x1800e0e14  mov     r8, r12
0x1800e0e17  call    WPP_SF_d
0x1800e0e1c  mov     eax, ebx
0x1800e0e1e  add     rsp, 30h
0x1800e0e22  pop     r15
0x1800e0e24  pop     r12
0x1800e0e26  pop     rdi
0x1800e0e27  pop     rsi
0x1800e0e28  pop     rbx
0x1800e0e29  retn
```
