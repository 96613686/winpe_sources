# FwMoneisInboxAppCServicingUpdate(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800bc0b0`
- end: `0x1800bc435`
- name: `?FwMoneisInboxAppCServicingUpdate@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `901`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a710`
- `0x1800350b4`
- `0x180037aa0`
- `0x180057bd0`
- `0x1800729c0`
- `0x1800bc0b0`
- `0x1800bc43c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800bc1ec`
- `ntdll!RtlEqualSid` at `0x1800bc1ec`
- `fwbase!FwTriggerRearm` at `0x1800bc104`
- `fwbase!FwTriggerRearm` at `0x1800bc104`
- `fwbase!FwCriticalSectionEnter` at `0x1800bc0ee`
- `fwbase!FwCriticalSectionEnter` at `0x1800bc0ee`
- `fwbase!FwCriticalSectionLeave` at `0x1800bc3dd`
- `fwbase!FwCriticalSectionLeave` at `0x1800bc3dd`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800bc2f8`
- `FWPolicyIOMgr!FwDeleteRule` at `0x1800bc2f8`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800bc11f`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800bc11f`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800bc409`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x1800bc409`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bc3f3`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800bc3f3`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800bc17f`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800bc17f`

## pseudocode

```c
void __fastcall FwMoneisInboxAppCServicingUpdate(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_WAIT *a3)
{
  signed int AppContainer; // eax
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
  __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 *v16; // [rsp+58h] [rbp-20h] BYREF
  int v17; // [rsp+60h] [rbp-18h] BYREF

  v17 = 0;
  v15 = 0;
  v16 = 0;
  FwCriticalSectionEnter(qword_18012FBE8);
  FwTriggerRearm(*(_QWORD *)Block);
  AppContainer = FwOpenAppCDbPolicyStore(1, 2, &v15);
  if ( AppContainer < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 10;
    goto LABEL_45;
  }
  AppContainer = FwEnumRules(v15, 3, &v16, &v17, -1, -1, 0);
  if ( AppContainer < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_47;
    v5 = 11;
LABEL_45:
    v9 = (unsigned int)AppContainer;
LABEL_46:
    WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v9);
    goto LABEL_47;
  }
  v6 = v16;
  if ( v16 )
  {
    while ( 1 )
    {
      v7 = (void *)v6[4];
      if ( v7 && v6[3] )
      {
        if ( RtlEqualSid(v7, Sid2) == 1 )
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
                           v6[4],
                           v6[3],
                           v6[5],
                           v6[6],
                           v6[7],
                           v6[9],
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
          LODWORD(v14) = 1;
          AppContainer = FwMoneisSetupAppContainerBinaries(
                           0,
                           1,
                           v6[4],
                           v6[3],
                           v6[13],
                           v6[12],
                           v6[6],
                           v14,
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
        AppContainer = FwDeleteRule(v15, 3, v6[2]);
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
  FwCriticalSectionLeave(qword_18012FBE8);
  FwFreeRules(v16, 3);
  if ( v15 )
    FwClosePolicyStore(v15);
}

```

## disassembly

```asm
0x1800bc0b0  mov     r11, rsp
0x1800bc0b3  mov     [r11+8], rbx
0x1800bc0b7  mov     [r11+10h], rbp
0x1800bc0bb  push    rsi
0x1800bc0bc  sub     rsp, 70h
0x1800bc0c0  mov     rax, cs:__security_cookie
0x1800bc0c7  xor     rax, rsp
0x1800bc0ca  mov     [rsp+78h+var_10], rax
0x1800bc0cf  lea     rcx, qword_18012FBE8
0x1800bc0d6  mov     [rsp+78h+var_18], 0
0x1800bc0de  mov     qword ptr [r11-28h], 0
0x1800bc0e6  mov     qword ptr [r11-20h], 0
0x1800bc0ee  call    cs:__imp_FwCriticalSectionEnter
0x1800bc0f5  nop     dword ptr [rax+rax+00h]
0x1800bc0fa  mov     rcx, cs:Block
0x1800bc101  mov     rcx, [rcx]
0x1800bc104  call    cs:__imp_FwTriggerRearm
0x1800bc10b  nop     dword ptr [rax+rax+00h]
0x1800bc110  mov     edx, 2
0x1800bc115  lea     r8, [rsp+78h+var_28]
0x1800bc11a  lea     esi, [rdx-1]
0x1800bc11d  mov     ecx, esi
0x1800bc11f  call    cs:__imp_FwOpenAppCDbPolicyStore
0x1800bc126  nop     dword ptr [rax+rax+00h]
0x1800bc12b  test    eax, eax
0x1800bc12d  jns     short loc_1800BC158
0x1800bc12f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc136  lea     rdx, WPP_GLOBAL_Control
0x1800bc13d  cmp     rcx, rdx
0x1800bc140  jz      loc_1800BC3D6
0x1800bc146  test    [rcx+1Ch], sil
0x1800bc14a  jz      loc_1800BC3D6
0x1800bc150  lea     edx, [rsi+9]
0x1800bc153  jmp     loc_1800BC3C3
0x1800bc158  mov     rcx, [rsp+78h+var_28]
0x1800bc15d  lea     r9, [rsp+78h+var_18]
0x1800bc162  or      eax, 0FFFFFFFFh
0x1800bc165  mov     dword ptr [rsp+78h+var_48], 0
0x1800bc16d  mov     dword ptr [rsp+78h+var_50], eax
0x1800bc171  lea     r8, [rsp+78h+var_20]
0x1800bc176  mov     edx, 3
0x1800bc17b  mov     dword ptr [rsp+78h+var_58], eax
0x1800bc17f  call    cs:__imp_FwEnumRules
0x1800bc186  nop     dword ptr [rax+rax+00h]
0x1800bc18b  test    eax, eax
0x1800bc18d  jns     short loc_1800BC1BA
0x1800bc18f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc196  lea     rdx, WPP_GLOBAL_Control
0x1800bc19d  cmp     rcx, rdx
0x1800bc1a0  jz      loc_1800BC3D6
0x1800bc1a6  test    [rcx+1Ch], sil
0x1800bc1aa  jz      loc_1800BC3D6
0x1800bc1b0  mov     edx, 0Bh
0x1800bc1b5  jmp     loc_1800BC3C3
0x1800bc1ba  mov     rbx, [rsp+78h+var_20]
0x1800bc1bf  test    rbx, rbx
0x1800bc1c2  jz      loc_1800BC3D6
0x1800bc1c8  mov     ebp, 80070000h
0x1800bc1cd  mov     rcx, [rbx+20h]; Sid1
0x1800bc1d1  test    rcx, rcx
0x1800bc1d4  jz      loc_1800BC30C
0x1800bc1da  cmp     qword ptr [rbx+18h], 0
0x1800bc1df  jz      loc_1800BC30C
0x1800bc1e5  mov     rdx, cs:Sid2; Sid2
0x1800bc1ec  call    cs:__imp_RtlEqualSid
0x1800bc1f3  nop     dword ptr [rax+rax+00h]
0x1800bc1f8  cmp     al, sil
0x1800bc1fb  jnz     loc_1800BC2EA
0x1800bc201  mov     rax, [rbx+30h]
0x1800bc205  mov     edx, esi; int
0x1800bc207  mov     r9, [rbx+18h]; struct _SID *
0x1800bc20b  xor     ecx, ecx; void *
0x1800bc20d  mov     r8, [rbx+20h]; struct _SID *
0x1800bc211  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800bc216  call    FwMoneisDeleteAppContainer
0x1800bc21b  xor     r9d, r9d
0x1800bc21e  cmp     eax, 2
0x1800bc221  cmovnz  r9d, eax
0x1800bc225  test    r9d, r9d
0x1800bc228  jle     short loc_1800BC234
0x1800bc22a  movzx   r9d, r9w
0x1800bc22e  or      r9d, ebp
0x1800bc231  test    r9d, r9d
0x1800bc234  js      loc_1800BC385
0x1800bc23a  mov     eax, [rbx+40h]
0x1800bc23d  mov     edx, esi
0x1800bc23f  mov     r9, [rbx+18h]
0x1800bc243  xor     ecx, ecx
0x1800bc245  mov     r8, [rbx+20h]
0x1800bc249  mov     dword ptr [rsp+78h+var_38], eax
0x1800bc24d  mov     rax, [rbx+48h]
0x1800bc251  mov     [rsp+78h+var_40], rax
0x1800bc256  mov     rax, [rbx+38h]
0x1800bc25a  mov     [rsp+78h+var_48], rax
0x1800bc25f  mov     rax, [rbx+30h]
0x1800bc263  mov     [rsp+78h+var_50], rax
0x1800bc268  mov     rax, [rbx+28h]
0x1800bc26c  mov     [rsp+78h+var_58], rax
0x1800bc271  call    FwMoneisCreateAppContainer
0x1800bc276  test    eax, eax
0x1800bc278  jle     short loc_1800BC281
0x1800bc27a  movzx   eax, ax
0x1800bc27d  or      eax, ebp
0x1800bc27f  test    eax, eax
0x1800bc281  js      loc_1800BC365
0x1800bc287  mov     eax, [rbx+50h]
0x1800bc28a  mov     edx, esi
0x1800bc28c  mov     r9, [rbx+18h]
0x1800bc290  xor     ecx, ecx
0x1800bc292  mov     r8, [rbx+20h]
0x1800bc296  mov     [rsp+78h+var_30], eax
0x1800bc29a  mov     rax, [rbx+58h]
0x1800bc29e  mov     [rsp+78h+var_38], rax
0x1800bc2a3  mov     rax, [rbx+30h]
0x1800bc2a7  mov     dword ptr [rsp+78h+var_40], esi
0x1800bc2ab  mov     [rsp+78h+var_48], rax
0x1800bc2b0  mov     rax, [rbx+60h]
0x1800bc2b4  mov     [rsp+78h+var_50], rax
0x1800bc2b9  mov     rax, [rbx+68h]
0x1800bc2bd  mov     [rsp+78h+var_58], rax
0x1800bc2c2  call    FwMoneisSetupAppContainerBinaries
0x1800bc2c7  test    eax, eax
0x1800bc2c9  jle     short loc_1800BC2D2
0x1800bc2cb  movzx   eax, ax
0x1800bc2ce  or      eax, ebp
0x1800bc2d0  test    eax, eax
0x1800bc2d2  js      short loc_1800BC345
0x1800bc2d4  mov     rcx, [rbx+18h]; void *
0x1800bc2d8  call    ?FwMoneisInboxAppCsUpdateList@@YAKPEAX@Z; FwMoneisInboxAppCsUpdateList(void *)
0x1800bc2dd  test    eax, eax
0x1800bc2df  jle     short loc_1800BC2E8
0x1800bc2e1  movzx   eax, ax
0x1800bc2e4  or      eax, ebp
0x1800bc2e6  test    eax, eax
0x1800bc2e8  js      short loc_1800BC31D
0x1800bc2ea  mov     r8, [rbx+10h]
0x1800bc2ee  mov     edx, 3
0x1800bc2f3  mov     rcx, [rsp+78h+var_28]
0x1800bc2f8  call    cs:__imp_FwDeleteRule
0x1800bc2ff  nop     dword ptr [rax+rax+00h]
0x1800bc304  test    eax, eax
0x1800bc306  js      loc_1800BC3A5
0x1800bc30c  mov     rbx, [rbx]
0x1800bc30f  test    rbx, rbx
0x1800bc312  jnz     loc_1800BC1CD
0x1800bc318  jmp     loc_1800BC3D6
0x1800bc31d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc324  lea     rdx, WPP_GLOBAL_Control
0x1800bc32b  cmp     rcx, rdx
0x1800bc32e  jz      loc_1800BC3D6
0x1800bc334  test    [rcx+1Ch], sil
0x1800bc338  jz      loc_1800BC3D6
0x1800bc33e  mov     edx, 0Fh
0x1800bc343  jmp     short loc_1800BC3C3
0x1800bc345  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc34c  lea     rdx, WPP_GLOBAL_Control
0x1800bc353  cmp     rcx, rdx
0x1800bc356  jz      short loc_1800BC3D6
0x1800bc358  test    [rcx+1Ch], sil
0x1800bc35c  jz      short loc_1800BC3D6
0x1800bc35e  mov     edx, 0Eh
0x1800bc363  jmp     short loc_1800BC3C3
0x1800bc365  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc36c  lea     rdx, WPP_GLOBAL_Control
0x1800bc373  cmp     rcx, rdx
0x1800bc376  jz      short loc_1800BC3D6
0x1800bc378  test    [rcx+1Ch], sil
0x1800bc37c  jz      short loc_1800BC3D6
0x1800bc37e  mov     edx, 0Dh
0x1800bc383  jmp     short loc_1800BC3C3
0x1800bc385  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc38c  lea     rdx, WPP_GLOBAL_Control
0x1800bc393  cmp     rcx, rdx
0x1800bc396  jz      short loc_1800BC3D6
0x1800bc398  test    [rcx+1Ch], sil
0x1800bc39c  jz      short loc_1800BC3D6
0x1800bc39e  mov     edx, 0Ch
0x1800bc3a3  jmp     short loc_1800BC3C6
0x1800bc3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc3ac  lea     rdx, WPP_GLOBAL_Control
0x1800bc3b3  cmp     rcx, rdx
0x1800bc3b6  jz      short loc_1800BC3D6
0x1800bc3b8  test    [rcx+1Ch], sil
0x1800bc3bc  jz      short loc_1800BC3D6
0x1800bc3be  mov     edx, 10h
0x1800bc3c3  mov     r9d, eax
0x1800bc3c6  mov     rcx, [rcx+10h]
0x1800bc3ca  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bc3d1  call    WPP_SF_d
0x1800bc3d6  lea     rcx, qword_18012FBE8
0x1800bc3dd  call    cs:__imp_FwCriticalSectionLeave
0x1800bc3e4  nop     dword ptr [rax+rax+00h]
0x1800bc3e9  mov     rcx, [rsp+78h+var_20]
0x1800bc3ee  mov     edx, 3
0x1800bc3f3  call    cs:__imp_FwFreeRules
0x1800bc3fa  nop     dword ptr [rax+rax+00h]
0x1800bc3ff  mov     rcx, [rsp+78h+var_28]
0x1800bc404  test    rcx, rcx
0x1800bc407  jz      short loc_1800BC415
0x1800bc409  call    cs:__imp_FwClosePolicyStore
0x1800bc410  nop     dword ptr [rax+rax+00h]
0x1800bc415  mov     rcx, [rsp+78h+var_10]
0x1800bc41a  xor     rcx, rsp; StackCookie
0x1800bc41d  call    __security_check_cookie
0x1800bc422  lea     r11, [rsp+78h+var_8]
0x1800bc427  mov     rbx, [r11+10h]
0x1800bc42b  mov     rbp, [r11+18h]
0x1800bc42f  mov     rsp, r11
0x1800bc432  pop     rsi
0x1800bc433  retn
```
