# FwMoneisInboxAppCServicingUpdate(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800b5890`
- end: `0x1800b5be1`
- name: `?FwMoneisInboxAppCServicingUpdate@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `849`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000af3c`
- `0x18002f7d4`
- `0x18003102c`
- `0x180033b28`
- `0x18006f520`
- `0x1800b5890`
- `0x1800b5be8`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800b59b8`
- `ntdll!RtlEqualSid` at `0x1800b59b8`
- `fwbase!FwTriggerRearm` at `0x1800b58de`
- `fwbase!FwTriggerRearm` at `0x1800b58de`
- `fwbase!FwCriticalSectionEnter` at `0x1800b58ce`
- `fwbase!FwCriticalSectionEnter` at `0x1800b58ce`
- `fwbase!FwCriticalSectionLeave` at `0x1800b5b9c`
- `fwbase!FwCriticalSectionLeave` at `0x1800b5b9c`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800b58f3`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800b58f3`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800b5abd`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800b5abd`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800b5bbc`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800b5bbc`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b5bac`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800b5bac`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800b594d`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800b594d`

## pseudocode

```c
void __fastcall FwMoneisInboxAppCServicingUpdate(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_WAIT *a3)
{
  int AppContainer; // eax
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rbx
  void *v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // r9
  bool v10; // sf
  bool v11; // sf
  bool v12; // sf
  bool v13; // sf
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-20h] BYREF
  int v16; // [rsp+60h] [rbp-18h] BYREF

  v16 = 0;
  v14 = 0;
  v15 = 0;
  FwCriticalSectionEnter(gInboxAppContainerManager);
  FwTriggerRearm(*(_QWORD *)Block);
  AppContainer = FwOpenAppCDbPolicyStore(1, 2, &v14);
  if ( AppContainer < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 10;
    goto LABEL_45;
  }
  AppContainer = FwEnumRules(v14, 3, &v15, &v16, -1, -1, 0);
  if ( AppContainer < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 11;
LABEL_45:
    v9 = (unsigned int)AppContainer;
LABEL_46:
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v9);
    goto LABEL_47;
  }
  v6 = v15;
  if ( v15 )
  {
    while ( 1 )
    {
      v7 = (void *)v6[4];
      if ( v7 && v6[3] )
      {
        if ( RtlEqualSid(v7, gSidManager[1]) )
        {
          v8 = FwMoneisDeleteAppContainer(0, 1, (struct _SID *)v6[4], (struct _SID *)v6[3], (unsigned __int16 *)v6[6]);
          v9 = 0;
          if ( v8 != 2 )
            v9 = v8;
          v10 = (int)v9 < 0;
          if ( (int)v9 > 0 )
          {
            v9 = (unsigned __int16)v9 | 0x80070000;
            v10 = (int)v9 < 0;
          }
          if ( v10 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v5 = 12;
              goto LABEL_46;
            }
            goto LABEL_47;
          }
          AppContainer = FwMoneisCreateAppContainer(
                           0,
                           1,
                           (SID *)v6[4],
                           (SID *)v6[3],
                           v6[5],
                           (unsigned __int16 *)v6[6],
                           v6[7],
                           (struct _SID_AND_ATTRIBUTES *)v6[9],
                           *((_DWORD *)v6 + 16));
          v11 = AppContainer < 0;
          if ( AppContainer > 0 )
          {
            AppContainer = (unsigned __int16)AppContainer | 0x80070000;
            v11 = AppContainer < 0;
          }
          if ( v11 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v5 = 13;
              goto LABEL_45;
            }
            goto LABEL_47;
          }
          AppContainer = FwMoneisSetupAppContainerBinaries(
                           0,
                           1,
                           v6[4],
                           v6[3],
                           v6[13],
                           v6[12],
                           v6[6],
                           1,
                           v6[11],
                           *((_DWORD *)v6 + 20));
          v12 = AppContainer < 0;
          if ( AppContainer > 0 )
          {
            AppContainer = (unsigned __int16)AppContainer | 0x80070000;
            v12 = AppContainer < 0;
          }
          if ( v12 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v5 = 14;
              goto LABEL_45;
            }
            goto LABEL_47;
          }
          AppContainer = FwMoneisInboxAppCsUpdateList((void *)v6[3]);
          v13 = AppContainer < 0;
          if ( AppContainer > 0 )
          {
            AppContainer = (unsigned __int16)AppContainer | 0x80070000;
            v13 = AppContainer < 0;
          }
          if ( v13 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v5 = 15;
              goto LABEL_45;
            }
            goto LABEL_47;
          }
        }
        AppContainer = FwDeleteRule(v14, 3, v6[2]);
        if ( AppContainer < 0 )
          break;
      }
      v6 = (__int64 *)*v6;
      if ( !v6 )
        goto LABEL_47;
    }
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v5 = 16;
      goto LABEL_45;
    }
  }
LABEL_47:
  FwCriticalSectionLeave(gInboxAppContainerManager);
  FwFreeRules(v15, 3);
  if ( v14 )
    FwClosePolicyStore(v14);
}

```

## disassembly

```asm
0x1800b5890  mov     r11, rsp
0x1800b5893  mov     [r11+8], rbx
0x1800b5897  mov     [r11+10h], rbp
0x1800b589b  push    rsi
0x1800b589c  sub     rsp, 70h
0x1800b58a0  mov     rax, cs:__security_cookie
0x1800b58a7  xor     rax, rsp
0x1800b58aa  mov     [rsp+78h+var_10], rax
0x1800b58af  mov     rcx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x1800b58b6  mov     [rsp+78h+var_18], 0
0x1800b58be  mov     qword ptr [r11-28h], 0
0x1800b58c6  mov     qword ptr [r11-20h], 0
0x1800b58ce  call    cs:__imp_FwCriticalSectionEnter
0x1800b58d4  mov     rcx, cs:Block
0x1800b58db  mov     rcx, [rcx]
0x1800b58de  call    cs:__imp_FwTriggerRearm
0x1800b58e4  mov     edx, 2
0x1800b58e9  lea     r8, [rsp+78h+var_28]
0x1800b58ee  lea     esi, [rdx-1]
0x1800b58f1  mov     ecx, esi
0x1800b58f3  call    cs:__imp_FwOpenAppCDbPolicyStore
0x1800b58f9  test    eax, eax
0x1800b58fb  jns     short loc_1800B5926
0x1800b58fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5904  lea     rdx, WPP_GLOBAL_Control
0x1800b590b  cmp     rcx, rdx
0x1800b590e  jz      loc_1800B5B95
0x1800b5914  test    [rcx+1Ch], sil
0x1800b5918  jz      loc_1800B5B95
0x1800b591e  lea     edx, [rsi+9]
0x1800b5921  jmp     loc_1800B5B82
0x1800b5926  mov     rcx, [rsp+78h+var_28]
0x1800b592b  lea     r9, [rsp+78h+var_18]
0x1800b5930  or      eax, 0FFFFFFFFh
0x1800b5933  mov     dword ptr [rsp+78h+var_48], 0
0x1800b593b  mov     dword ptr [rsp+78h+var_50], eax
0x1800b593f  lea     r8, [rsp+78h+var_20]
0x1800b5944  mov     edx, 3
0x1800b5949  mov     dword ptr [rsp+78h+var_58], eax
0x1800b594d  call    cs:__imp_FwEnumRules
0x1800b5953  test    eax, eax
0x1800b5955  jns     short loc_1800B5982
0x1800b5957  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b595e  lea     rdx, WPP_GLOBAL_Control
0x1800b5965  cmp     rcx, rdx
0x1800b5968  jz      loc_1800B5B95
0x1800b596e  test    [rcx+1Ch], sil
0x1800b5972  jz      loc_1800B5B95
0x1800b5978  mov     edx, 0Bh
0x1800b597d  jmp     loc_1800B5B82
0x1800b5982  mov     rbx, [rsp+78h+var_20]
0x1800b5987  test    rbx, rbx
0x1800b598a  jz      loc_1800B5B95
0x1800b5990  mov     ebp, 80070000h
0x1800b5995  mov     rcx, [rbx+20h]; Sid1
0x1800b5999  test    rcx, rcx
0x1800b599c  jz      loc_1800B5ACB
0x1800b59a2  cmp     qword ptr [rbx+18h], 0
0x1800b59a7  jz      loc_1800B5ACB
0x1800b59ad  mov     rdx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b59b4  mov     rdx, [rdx+8]; Sid2
0x1800b59b8  call    cs:__imp_RtlEqualSid
0x1800b59be  test    al, al
0x1800b59c0  jz      loc_1800B5AAF
0x1800b59c6  mov     rax, [rbx+30h]
0x1800b59ca  mov     edx, esi; int
0x1800b59cc  mov     r9, [rbx+18h]; struct _SID *
0x1800b59d0  xor     ecx, ecx; void *
0x1800b59d2  mov     r8, [rbx+20h]; struct _SID *
0x1800b59d6  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800b59db  call    FwMoneisDeleteAppContainer
0x1800b59e0  xor     r9d, r9d
0x1800b59e3  cmp     eax, 2
0x1800b59e6  cmovnz  r9d, eax
0x1800b59ea  test    r9d, r9d
0x1800b59ed  jle     short loc_1800B59F9
0x1800b59ef  movzx   r9d, r9w
0x1800b59f3  or      r9d, ebp
0x1800b59f6  test    r9d, r9d
0x1800b59f9  js      loc_1800B5B44
0x1800b59ff  mov     eax, [rbx+40h]
0x1800b5a02  mov     edx, esi
0x1800b5a04  mov     r9, [rbx+18h]
0x1800b5a08  xor     ecx, ecx
0x1800b5a0a  mov     r8, [rbx+20h]
0x1800b5a0e  mov     dword ptr [rsp+78h+var_38], eax
0x1800b5a12  mov     rax, [rbx+48h]
0x1800b5a16  mov     [rsp+78h+var_40], rax
0x1800b5a1b  mov     rax, [rbx+38h]
0x1800b5a1f  mov     [rsp+78h+var_48], rax
0x1800b5a24  mov     rax, [rbx+30h]
0x1800b5a28  mov     [rsp+78h+var_50], rax
0x1800b5a2d  mov     rax, [rbx+28h]
0x1800b5a31  mov     [rsp+78h+var_58], rax
0x1800b5a36  call    FwMoneisCreateAppContainer
0x1800b5a3b  test    eax, eax
0x1800b5a3d  jle     short loc_1800B5A46
0x1800b5a3f  movzx   eax, ax
0x1800b5a42  or      eax, ebp
0x1800b5a44  test    eax, eax
0x1800b5a46  js      loc_1800B5B24
0x1800b5a4c  mov     eax, [rbx+50h]
0x1800b5a4f  mov     edx, esi
0x1800b5a51  mov     r9, [rbx+18h]
0x1800b5a55  xor     ecx, ecx
0x1800b5a57  mov     r8, [rbx+20h]
0x1800b5a5b  mov     [rsp+78h+var_30], eax
0x1800b5a5f  mov     rax, [rbx+58h]
0x1800b5a63  mov     [rsp+78h+var_38], rax
0x1800b5a68  mov     rax, [rbx+30h]
0x1800b5a6c  mov     dword ptr [rsp+78h+var_40], esi
0x1800b5a70  mov     [rsp+78h+var_48], rax
0x1800b5a75  mov     rax, [rbx+60h]
0x1800b5a79  mov     [rsp+78h+var_50], rax
0x1800b5a7e  mov     rax, [rbx+68h]
0x1800b5a82  mov     [rsp+78h+var_58], rax
0x1800b5a87  call    FwMoneisSetupAppContainerBinaries
0x1800b5a8c  test    eax, eax
0x1800b5a8e  jle     short loc_1800B5A97
0x1800b5a90  movzx   eax, ax
0x1800b5a93  or      eax, ebp
0x1800b5a95  test    eax, eax
0x1800b5a97  js      short loc_1800B5B04
0x1800b5a99  mov     rcx, [rbx+18h]; void *
0x1800b5a9d  call    ?FwMoneisInboxAppCsUpdateList@@YAKPEAX@Z; FwMoneisInboxAppCsUpdateList(void *)
0x1800b5aa2  test    eax, eax
0x1800b5aa4  jle     short loc_1800B5AAD
0x1800b5aa6  movzx   eax, ax
0x1800b5aa9  or      eax, ebp
0x1800b5aab  test    eax, eax
0x1800b5aad  js      short loc_1800B5ADC
0x1800b5aaf  mov     r8, [rbx+10h]
0x1800b5ab3  mov     edx, 3
0x1800b5ab8  mov     rcx, [rsp+78h+var_28]
0x1800b5abd  call    cs:__imp_FwDeleteRule
0x1800b5ac3  test    eax, eax
0x1800b5ac5  js      loc_1800B5B64
0x1800b5acb  mov     rbx, [rbx]
0x1800b5ace  test    rbx, rbx
0x1800b5ad1  jnz     loc_1800B5995
0x1800b5ad7  jmp     loc_1800B5B95
0x1800b5adc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ae3  lea     rdx, WPP_GLOBAL_Control
0x1800b5aea  cmp     rcx, rdx
0x1800b5aed  jz      loc_1800B5B95
0x1800b5af3  test    [rcx+1Ch], sil
0x1800b5af7  jz      loc_1800B5B95
0x1800b5afd  mov     edx, 0Fh
0x1800b5b02  jmp     short loc_1800B5B82
0x1800b5b04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b0b  lea     rdx, WPP_GLOBAL_Control
0x1800b5b12  cmp     rcx, rdx
0x1800b5b15  jz      short loc_1800B5B95
0x1800b5b17  test    [rcx+1Ch], sil
0x1800b5b1b  jz      short loc_1800B5B95
0x1800b5b1d  mov     edx, 0Eh
0x1800b5b22  jmp     short loc_1800B5B82
0x1800b5b24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b2b  lea     rdx, WPP_GLOBAL_Control
0x1800b5b32  cmp     rcx, rdx
0x1800b5b35  jz      short loc_1800B5B95
0x1800b5b37  test    [rcx+1Ch], sil
0x1800b5b3b  jz      short loc_1800B5B95
0x1800b5b3d  mov     edx, 0Dh
0x1800b5b42  jmp     short loc_1800B5B82
0x1800b5b44  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b4b  lea     rdx, WPP_GLOBAL_Control
0x1800b5b52  cmp     rcx, rdx
0x1800b5b55  jz      short loc_1800B5B95
0x1800b5b57  test    [rcx+1Ch], sil
0x1800b5b5b  jz      short loc_1800B5B95
0x1800b5b5d  mov     edx, 0Ch
0x1800b5b62  jmp     short loc_1800B5B85
0x1800b5b64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b6b  lea     rdx, WPP_GLOBAL_Control
0x1800b5b72  cmp     rcx, rdx
0x1800b5b75  jz      short loc_1800B5B95
0x1800b5b77  test    [rcx+1Ch], sil
0x1800b5b7b  jz      short loc_1800B5B95
0x1800b5b7d  mov     edx, 10h
0x1800b5b82  mov     r9d, eax
0x1800b5b85  mov     rcx, [rcx+10h]
0x1800b5b89  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b5b90  call    WPP_SF_d
0x1800b5b95  mov     rcx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x1800b5b9c  call    cs:__imp_FwCriticalSectionLeave
0x1800b5ba2  mov     rcx, [rsp+78h+var_20]
0x1800b5ba7  mov     edx, 3
0x1800b5bac  call    cs:__imp_FwFreeRules
0x1800b5bb2  mov     rcx, [rsp+78h+var_28]
0x1800b5bb7  test    rcx, rcx
0x1800b5bba  jz      short loc_1800B5BC2
0x1800b5bbc  call    cs:__imp_FwClosePolicyStore
0x1800b5bc2  mov     rcx, [rsp+78h+var_10]
0x1800b5bc7  xor     rcx, rsp; StackCookie
0x1800b5bca  call    __security_check_cookie
0x1800b5bcf  lea     r11, [rsp+78h+var_8]
0x1800b5bd4  mov     rbx, [r11+10h]
0x1800b5bd8  mov     rbp, [r11+18h]
0x1800b5bdc  mov     rsp, r11
0x1800b5bdf  pop     rsi
0x1800b5be0  retn
```
