# IcfGetProfile

- ea: `0x180035500`
- end: `0x180035840`
- name: `IcfGetProfile`
- size: `832`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task`

## callees

- `0x180009780`
- `0x18000c3f0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x180019b34`
- `0x1800294b0`
- `0x18003336c`
- `0x180033600`
- `0x180033af8`
- `0x180033f10`
- `0x1800340d8`
- `0x180034574`
- `0x180034660`
- `0x180034b70`
- `0x180034f30`
- `0x180035500`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x1800355fb`
- `fwbase!FwBaseAlloc` at `0x180035657`
- `fwbase!FwBaseAlloc` at `0x1800355fb`
- `fwbase!FwBaseAlloc` at `0x180035657`
- `fwbase!FwHResultToWindowsError` at `0x180035816`
- `fwbase!FwHResultToWindowsError` at `0x180035816`
- `fwbase!FwReportErrorAsWinError` at `0x180035624`
- `fwbase!FwReportErrorAsWinError` at `0x180035624`
- `fwbase!FwReportReturnError` at `0x180035595`
- `fwbase!FwReportReturnError` at `0x180035595`

## string_xrefs

- `0x180035649`: `FWOpenPolicyStore`
- `0x1800356a8`: `CopyConfigToProfile`
- `0x18003570d`: `CopyRemoteAdminSettingsToProfile`
- `0x18003572c`: `CopyServicesSettingsToProfile`
- `0x180035751`: `CopyPortsSettingsToProfile`
- `0x180035778`: `CopyAuthAppsSettingsToProfile`

## pseudocode

```c
__int64 __fastcall IcfGetProfile(__int64 a1, int a2, int a3, __int64 *a4)
{
  __int16 v7; // r13
  int v8; // edi
  unsigned int v9; // r14d
  unsigned int v10; // edi
  unsigned int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r8
  const char *v14; // rdx
  _DWORD *v16; // rax
  __int64 v17; // rbx
  unsigned int CurrentProfileType; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  _DWORD *v25; // [rsp+30h] [rbp-38h] BYREF
  struct _tag_FW_RULE *v26; // [rsp+38h] [rbp-30h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h] BYREF
  int v28; // [rsp+48h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v7 = 1;
  switch ( a2 )
  {
    case 0:
      v9 = 1;
LABEL_11:
      if ( a3 )
      {
        if ( a3 == 1 )
        {
          v10 = 2;
        }
        else
        {
          if ( a3 != 2 )
            break;
          v10 = 0x80000000;
        }
      }
      else
      {
        v10 = 1;
      }
      v11 = FWOpenPolicyStore(0x221u, 0, v9, 1u, 0, &v27);
      if ( v11 == 2 )
      {
        v12 = FwBaseAlloc(240);
        v25 = (_DWORD *)v12;
        if ( v12 )
        {
          *a4 = v12;
          return 0;
        }
      }
      else
      {
        if ( v11 )
        {
          v13 = v11;
          v14 = "FWOpenPolicyStore";
          goto LABEL_20;
        }
        v16 = (_DWORD *)FwBaseAlloc(240);
        v25 = v16;
        v17 = (__int64)v16;
        if ( v16 )
        {
          if ( a3 == 2 )
          {
            CurrentProfileType = IcfGetCurrentProfileType(0, v16);
            if ( CurrentProfileType )
            {
              v13 = CurrentProfileType;
              v14 = "IcfGetCurrentProfileType";
              goto LABEL_20;
            }
          }
          else
          {
            *v16 = a3;
          }
          v19 = CopyConfigToProfile(v27, v10, v9, v17);
          if ( v19 )
          {
            v13 = v19;
            v14 = "CopyConfigToProfile";
          }
          else
          {
            v20 = FWEnumFirewallRules(v27, 196608, v10, v7, (__int64)&v28, (__int64)&v26);
            if ( v20 )
            {
              v13 = v20;
              v14 = "FWEnumFirewallRules";
            }
            else
            {
              CopyICMPSettingsToProfile(v26, (struct ICF_PROFILE_ *)v17);
              v21 = CopyRemoteAdminSettingsToProfile(v26, (struct ICF_PROFILE_ *)v17);
              if ( v21 )
              {
                v13 = v21;
                v14 = "CopyRemoteAdminSettingsToProfile";
              }
              else
              {
                v22 = CopyServicesSettingsToProfile(v26, (struct ICF_PROFILE_ *)v17);
                if ( v22 )
                {
                  v13 = v22;
                  v14 = "CopyServicesSettingsToProfile";
                }
                else
                {
                  v23 = CopyPortsSettingsToProfile(v27, v10, (__int64 *)v26, v17);
                  if ( v23 )
                  {
                    v13 = v23;
                    v14 = "CopyPortsSettingsToProfile";
                  }
                  else
                  {
                    v24 = CopyAuthAppsSettingsToProfile(v27, v10, (__int64 *)v26, v17);
                    if ( !v24 )
                    {
                      *a4 = v17;
                      v8 = 0;
                      if ( a2
                        || (*(_DWORD *)(v17 + 4) = 0, v28)
                        || *(_DWORD *)(v17 + 8)
                        || *(_DWORD *)(v17 + 12)
                        || *(_DWORD *)(v17 + 16)
                        || *(_DWORD *)(v17 + 20)
                        || *(_DWORD *)(v17 + 124)
                        || *(_DWORD *)(v17 + 128)
                        || !*(_DWORD *)(v17 + 120)
                        || !*(_QWORD *)(v17 + 112)
                        || *(_DWORD *)(v17 + 196)
                        || *(_DWORD *)(v17 + 236) )
                      {
                        *(_DWORD *)(v17 + 4) = 2;
                      }
                      goto LABEL_54;
                    }
                    v13 = v24;
                    v14 = "CopyAuthAppsSettingsToProfile";
                  }
                }
              }
            }
          }
          goto LABEL_20;
        }
      }
      v13 = 8;
      v14 = "FwAlloc";
LABEL_20:
      v8 = FwReportErrorAsWinError("IcfGetProfile", v14, v13);
      goto LABEL_54;
    case 1:
      v9 = 2;
      goto LABEL_11;
    case 2:
      v9 = 5;
      v7 = 9;
      goto LABEL_11;
  }
  v8 = -2147024809;
  FwReportReturnError("IcfGetProfile", 2147942487LL);
LABEL_54:
  if ( v27 )
    FWClosePolicyStore(v27);
  if ( v26 )
    FWFreeFirewallRules((__int64)v26);
  if ( v8 < 0 )
    IcfFreeProfile(&v25);
  if ( (unsigned int)IsRpcError(v8) )
    v8 = -2147023174;
  return FwHResultToWindowsError((unsigned int)v8);
}

```

## disassembly

```asm
0x180035500  push    rbp
0x180035502  push    rbx
0x180035503  push    rsi
0x180035504  push    rdi
0x180035505  push    r12
0x180035507  push    r13
0x180035509  push    r14
0x18003550b  push    r15
0x18003550d  mov     rbp, rsp
0x180035510  sub     rsp, 68h
0x180035514  mov     rax, cs:__security_cookie
0x18003551b  xor     rax, rsp
0x18003551e  mov     [rbp+var_18], rax
0x180035522  mov     r12, r9
0x180035525  mov     esi, r8d
0x180035528  mov     r15d, edx
0x18003552b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035532  lea     rax, WPP_GLOBAL_Control
0x180035539  cmp     rcx, rax
0x18003553c  jz      short loc_180035559
0x18003553e  test    byte ptr [rcx+1Ch], 8
0x180035542  jz      short loc_180035559
0x180035544  mov     rcx, [rcx+10h]
0x180035548  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003554f  mov     edx, 25h ; '%'
0x180035554  call    WPP_SF_
0x180035559  xor     edx, edx
0x18003555b  mov     ecx, r15d
0x18003555e  mov     [rbp+var_28], rdx
0x180035562  mov     [rbp+var_38], rdx
0x180035566  mov     [rbp+var_30], rdx
0x18003556a  mov     [rbp+var_20], edx
0x18003556d  lea     r9d, [rdx+1]
0x180035571  lea     ebx, [rdx+2]
0x180035574  movzx   r13d, r9w
0x180035578  test    r15d, r15d
0x18003557b  jz      short loc_1800355B7
0x18003557d  sub     ecx, r9d
0x180035580  jz      short loc_1800355B2
0x180035582  cmp     ecx, r9d
0x180035585  jz      short loc_1800355A6
0x180035587  mov     edx, 80070057h
0x18003558c  lea     rcx, aIcfgetprofile_0; "IcfGetProfile"
0x180035593  mov     edi, edx
0x180035595  call    cs:__imp_FwReportReturnError
0x18003559c  nop     dword ptr [rax+rax+00h]
0x1800355a1  jmp     loc_1800357DA
0x1800355a6  mov     r14d, 5
0x1800355ac  lea     r13d, [r14+4]
0x1800355b0  jmp     short loc_1800355BA
0x1800355b2  mov     r14d, ebx
0x1800355b5  jmp     short loc_1800355BA
0x1800355b7  mov     r14d, r9d
0x1800355ba  mov     ecx, esi
0x1800355bc  test    esi, esi
0x1800355be  jz      short loc_1800355D5
0x1800355c0  sub     ecx, r9d
0x1800355c3  jz      short loc_1800355D1
0x1800355c5  cmp     ecx, r9d
0x1800355c8  jnz     short loc_180035587
0x1800355ca  mov     edi, 80000000h
0x1800355cf  jmp     short loc_1800355D8
0x1800355d1  mov     edi, ebx
0x1800355d3  jmp     short loc_1800355D8
0x1800355d5  mov     edi, r9d
0x1800355d8  lea     rax, [rbp+var_28]
0x1800355dc  mov     ecx, 221h
0x1800355e1  mov     [rsp+68h+var_40], rax
0x1800355e6  mov     r8d, r14d
0x1800355e9  mov     dword ptr [rsp+68h+var_48], edx
0x1800355ed  call    FWOpenPolicyStore
0x1800355f2  cmp     eax, ebx
0x1800355f4  jnz     short loc_180035642
0x1800355f6  mov     ecx, 0F0h
0x1800355fb  call    cs:__imp_FwBaseAlloc
0x180035602  nop     dword ptr [rax+rax+00h]
0x180035607  mov     [rbp+var_38], rax
0x18003560b  test    rax, rax
0x18003560e  jnz     short loc_180035637
0x180035610  mov     r8d, 8
0x180035616  lea     rdx, aFwalloc_0; "FwAlloc"
0x18003561d  lea     rcx, aIcfgetprofile_0; "IcfGetProfile"
0x180035624  call    cs:__imp_FwReportErrorAsWinError
0x18003562b  nop     dword ptr [rax+rax+00h]
0x180035630  mov     edi, eax
0x180035632  jmp     loc_1800357DA
0x180035637  mov     [r12], rax
0x18003563b  xor     eax, eax
0x18003563d  jmp     loc_180035822
0x180035642  test    eax, eax
0x180035644  jz      short loc_180035652
0x180035646  mov     r8d, eax
0x180035649  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x180035650  jmp     short loc_18003561D
0x180035652  mov     ecx, 0F0h
0x180035657  call    cs:__imp_FwBaseAlloc
0x18003565e  nop     dword ptr [rax+rax+00h]
0x180035663  mov     [rbp+var_38], rax
0x180035667  mov     rbx, rax
0x18003566a  test    rax, rax
0x18003566d  jz      short loc_180035610
0x18003566f  cmp     esi, 2
0x180035672  jnz     short loc_18003568E
0x180035674  mov     rdx, rax
0x180035677  xor     ecx, ecx
0x180035679  call    IcfGetCurrentProfileType
0x18003567e  test    eax, eax
0x180035680  jz      short loc_180035690
0x180035682  mov     r8d, eax
0x180035685  lea     rdx, aIcfgetcurrentp_0; "IcfGetCurrentProfileType"
0x18003568c  jmp     short loc_18003561D
0x18003568e  mov     [rax], esi
0x180035690  mov     rcx, [rbp+var_28]
0x180035694  mov     r9, rbx
0x180035697  mov     r8d, r14d
0x18003569a  mov     edx, edi
0x18003569c  call    ?CopyConfigToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@W4_tag_FW_STORE_TYPE@@PEAUICF_PROFILE_@@@Z; CopyConfigToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_STORE_TYPE,ICF_PROFILE_ *)
0x1800356a1  test    eax, eax
0x1800356a3  jz      short loc_1800356B4
0x1800356a5  mov     r8d, eax
0x1800356a8  lea     rdx, aCopyconfigtopr; "CopyConfigToProfile"
0x1800356af  jmp     loc_18003561D
0x1800356b4  mov     rcx, [rbp+var_28]
0x1800356b8  lea     rax, [rbp+var_30]
0x1800356bc  mov     [rsp+68h+var_40], rax
0x1800356c1  movzx   r9d, r13w
0x1800356c5  lea     rax, [rbp+var_20]
0x1800356c9  mov     r8d, edi
0x1800356cc  mov     edx, 30000h
0x1800356d1  mov     [rsp+68h+var_48], rax
0x1800356d6  call    FWEnumFirewallRules
0x1800356db  test    eax, eax
0x1800356dd  jz      short loc_1800356EE
0x1800356df  mov     r8d, eax
0x1800356e2  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x1800356e9  jmp     loc_18003561D
0x1800356ee  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x1800356f2  mov     rdx, rbx; struct ICF_PROFILE_ *
0x1800356f5  call    ?CopyICMPSettingsToProfile@@YAXPEAU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyICMPSettingsToProfile(_tag_FW_RULE *,ICF_PROFILE_ *)
0x1800356fa  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x1800356fe  mov     rdx, rbx; struct ICF_PROFILE_ *
0x180035701  call    ?CopyRemoteAdminSettingsToProfile@@YAKPEAU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyRemoteAdminSettingsToProfile(_tag_FW_RULE *,ICF_PROFILE_ *)
0x180035706  test    eax, eax
0x180035708  jz      short loc_180035719
0x18003570a  mov     r8d, eax
0x18003570d  lea     rdx, aCopyremoteadmi; "CopyRemoteAdminSettingsToProfile"
0x180035714  jmp     loc_18003561D
0x180035719  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x18003571d  mov     rdx, rbx; struct ICF_PROFILE_ *
0x180035720  call    ?CopyServicesSettingsToProfile@@YAKPEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyServicesSettingsToProfile(_tag_FW_RULE const *,ICF_PROFILE_ *)
0x180035725  test    eax, eax
0x180035727  jz      short loc_180035738
0x180035729  mov     r8d, eax
0x18003572c  lea     rdx, aCopyservicesse; "CopyServicesSettingsToProfile"
0x180035733  jmp     loc_18003561D
0x180035738  mov     r8, [rbp+var_30]
0x18003573c  mov     r9, rbx
0x18003573f  mov     rcx, [rbp+var_28]
0x180035743  mov     edx, edi
0x180035745  call    ?CopyPortsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyPortsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)
0x18003574a  test    eax, eax
0x18003574c  jz      short loc_18003575D
0x18003574e  mov     r8d, eax
0x180035751  lea     rdx, aCopyportssetti; "CopyPortsSettingsToProfile"
0x180035758  jmp     loc_18003561D
0x18003575d  mov     r8, [rbp+var_30]
0x180035761  mov     r9, rbx
0x180035764  mov     rcx, [rbp+var_28]
0x180035768  mov     edx, edi
0x18003576a  call    ?CopyAuthAppsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyAuthAppsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)
0x18003576f  xor     ecx, ecx
0x180035771  test    eax, eax
0x180035773  jz      short loc_180035784
0x180035775  mov     r8d, eax
0x180035778  lea     rdx, aCopyauthappsse; "CopyAuthAppsSettingsToProfile"
0x18003577f  jmp     loc_18003561D
0x180035784  mov     [r12], rbx
0x180035788  mov     edi, ecx
0x18003578a  test    r15d, r15d
0x18003578d  jnz     short loc_1800357D3
0x18003578f  mov     [rbx+4], ecx
0x180035792  cmp     [rbp+var_20], ecx
0x180035795  jnz     short loc_1800357D3
0x180035797  cmp     [rbx+8], ecx
0x18003579a  jnz     short loc_1800357D3
0x18003579c  cmp     [rbx+0Ch], ecx
0x18003579f  jnz     short loc_1800357D3
0x1800357a1  cmp     [rbx+10h], ecx
0x1800357a4  jnz     short loc_1800357D3
0x1800357a6  cmp     [rbx+14h], ecx
0x1800357a9  jnz     short loc_1800357D3
0x1800357ab  cmp     [rbx+7Ch], ecx
0x1800357ae  jnz     short loc_1800357D3
0x1800357b0  cmp     [rbx+80h], ecx
0x1800357b6  jnz     short loc_1800357D3
0x1800357b8  cmp     [rbx+78h], ecx
0x1800357bb  jz      short loc_1800357D3
0x1800357bd  cmp     [rbx+70h], rcx
0x1800357c1  jz      short loc_1800357D3
0x1800357c3  cmp     [rbx+0C4h], ecx
0x1800357c9  jnz     short loc_1800357D3
0x1800357cb  cmp     [rbx+0ECh], ecx
0x1800357d1  jz      short loc_1800357DA
0x1800357d3  mov     dword ptr [rbx+4], 2
0x1800357da  mov     rcx, [rbp+var_28]
0x1800357de  test    rcx, rcx
0x1800357e1  jz      short loc_1800357E8
0x1800357e3  call    FWClosePolicyStore
0x1800357e8  mov     rcx, [rbp+var_30]
0x1800357ec  test    rcx, rcx
0x1800357ef  jz      short loc_1800357F6
0x1800357f1  call    FWFreeFirewallRules
0x1800357f6  test    edi, edi
0x1800357f8  jns     short loc_180035803
0x1800357fa  lea     rcx, [rbp+var_38]
0x1800357fe  call    IcfFreeProfile
0x180035803  mov     ecx, edi; int
0x180035805  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x18003580a  mov     ecx, 800706BAh
0x18003580f  test    eax, eax
0x180035811  cmovnz  edi, ecx
0x180035814  mov     ecx, edi
0x180035816  call    cs:__imp_FwHResultToWindowsError
0x18003581d  nop     dword ptr [rax+rax+00h]
0x180035822  mov     rcx, [rbp+var_18]
0x180035826  xor     rcx, rsp; StackCookie
0x180035829  call    __security_check_cookie
0x18003582e  add     rsp, 68h
0x180035832  pop     r15
0x180035834  pop     r14
0x180035836  pop     r13
0x180035838  pop     r12
0x18003583a  pop     rdi
0x18003583b  pop     rsi
0x18003583c  pop     rbx
0x18003583d  pop     rbp
0x18003583e  retn
```
