# FwMoneisSetupAppContainerBinaries

- ea: `0x18003102c`
- end: `0x180031400`
- name: `FwMoneisSetupAppContainerBinaries`
- size: `980`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180031410`
- `0x1800b5890`

## callees

- `0x18000af3c`
- `0x18003102c`
- `0x1800620b8`
- `0x18006f520`
- `0x1800bacd0`
- `0x1800bb5b0`
- `0x1800bb620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031159`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003110b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003114f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003110b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003114f`
- `fwbase!FwHResultToWindowsError` at `0x1800311a3`
- `fwbase!FwHResultToWindowsError` at `0x1800311fa`
- `fwbase!FwHResultToWindowsError` at `0x18003130c`
- `fwbase!FwHResultToWindowsError` at `0x1800311a3`
- `fwbase!FwHResultToWindowsError` at `0x1800311fa`
- `fwbase!FwHResultToWindowsError` at `0x18003130c`
- `fwbase!FwStringBuild` at `0x18003119b`
- `fwbase!FwStringBuild` at `0x18003119b`
- `fwbase!FwFree` at `0x180031239`
- `fwbase!FwFree` at `0x180031253`
- `fwbase!FwFree` at `0x1800313be`
- `fwbase!FwFree` at `0x180031239`
- `fwbase!FwFree` at `0x180031253`
- `fwbase!FwFree` at `0x1800313be`
- `FWPolicyIOMgr!FwSetRule` at `0x180031304`
- `FWPolicyIOMgr!FwSetRule` at `0x180031304`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800312ca`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800312ca`
- `FWPolicyIOMgr!FwGetRule` at `0x1800311f2`
- `FWPolicyIOMgr!FwGetRule` at `0x1800311f2`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800313af`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800313af`

## pseudocode

```c
__int64 __fastcall FwMoneisSetupAppContainerBinaries(
        void *a1,
        int a2,
        SID *a3,
        SID *a4,
        __int64 a5,
        __int64 a6,
        WCHAR *a7,
        int a8,
        __int64 a9,
        int a10)
{
  int v10; // r14d
  DWORD LastError; // eax
  DWORD v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int Rule; // eax
  unsigned int v20; // eax
  struct _tag_FW_APPCONTAINER *v21; // rax
  int v23; // [rsp+30h] [rbp-61h] BYREF
  struct _INET_FIREWALL_AC_CHANGE v24; // [rsp+38h] [rbp-59h] BYREF
  struct _tag_FW_APPCONTAINER *v25; // [rsp+68h] [rbp-29h] BYREF
  __int64 v26; // [rsp+70h] [rbp-21h] BYREF
  LPWSTR v27; // [rsp+78h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp-11h] BYREF

  v10 = 0;
  v23 = 0;
  StringSid = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  *(&v24.binaries.count + 1) = 0;
  LastError = FwMoneisValidateAppContainerOperation(a1, a2, 0, a3, a4, &v23);
  v14 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v16 = 117;
LABEL_5:
      v17 = LastError;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v17);
    }
  }
  else
  {
    if ( !v23 )
    {
      v14 = 0;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v16 = 118;
        v17 = 0;
        goto LABEL_6;
      }
      goto LABEL_40;
    }
    if ( ConvertSidToStringSidW(a3, &StringSid) )
    {
      if ( ConvertSidToStringSidW(a4, &v27) )
      {
        v18 = FwStringBuild(&v26, v27, StringSid, 0);
        LastError = FwHResultToWindowsError(v18);
        v14 = LastError;
        if ( LastError )
        {
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v16 = 121;
            goto LABEL_5;
          }
        }
        else
        {
          Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 12), 3, v26, &v25);
          LastError = FwHResultToWindowsError(Rule);
          v14 = LastError;
          if ( !LastError )
          {
            FwFree(*((_QWORD *)v25 + 13));
            *((_QWORD *)v25 + 13) = a5;
            FwFree(*((_QWORD *)v25 + 12));
            *((_QWORD *)v25 + 12) = a6;
            if ( a8
              || (unsigned int)appIsolation::IsolationEvents::FwMoneisRegistrationsForceComputeBinaries(Block) != 1 )
            {
              FwBinariesFree(*((unsigned int *)v25 + 20), *((_QWORD *)v25 + 11));
              *((_DWORD *)v25 + 20) = a10;
              *((_QWORD *)v25 + 11) = a9;
              *((_DWORD *)v25 + 28) = a8;
            }
            else
            {
              LastError = FwMoneisReComputeAppContainerBinaries(v25);
              v14 = LastError;
              if ( LastError )
              {
                v15 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v16 = 123;
                  goto LABEL_5;
                }
                goto LABEL_40;
              }
              v10 = 1;
            }
            v20 = FwSetRule(*((_QWORD *)gFwIsolationManager + 12), 3, v25);
            LastError = FwHResultToWindowsError(v20);
            v14 = LastError;
            if ( LastError )
            {
              v15 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v16 = 124;
                goto LABEL_5;
              }
            }
            else
            {
              v24.changeType = INET_FIREWALL_AC_CHANGE_CREATE;
              v24.createType = INET_FIREWALL_AC_BINARY;
              v24.userSid = a3;
              v24.capabilities.count = *((_DWORD *)v25 + 20);
              v24.capabilities.capabilities = (SID_AND_ATTRIBUTES *)*((_QWORD *)v25 + 11);
              v24.appContainerSid = a4;
              v24.displayName = a7;
              appIsolation::IsolationEvents::FwMoneisSendNotification(Block, 0, &v24);
            }
            goto LABEL_40;
          }
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v16 = 122;
            goto LABEL_5;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v16 = 120;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v16 = 119;
        goto LABEL_5;
      }
    }
  }
LABEL_40:
  v21 = v25;
  if ( v25 )
  {
    if ( !v10 )
    {
      *((_OWORD *)v25 + 5) = 0;
      v21 = v25;
    }
    *((_QWORD *)v21 + 13) = 0;
    *((_QWORD *)v25 + 12) = 0;
    FwFreeRules(v25, 3);
  }
  if ( v26 )
    FwFree(v26);
  if ( v27 )
    LocalFree(v27);
  if ( StringSid )
    LocalFree(StringSid);
  return v14;
}

```

## disassembly

```asm
0x18003102c  push    rbp
0x18003102e  push    rbx
0x18003102f  push    rsi
0x180031030  push    rdi
0x180031031  push    r14
0x180031033  push    r15
0x180031035  lea     rbp, [rsp-7]
0x18003103a  sub     rsp, 98h
0x180031041  mov     rax, cs:__security_cookie
0x180031048  xor     rax, rsp
0x18003104b  mov     [rbp+2Fh+var_38], rax
0x18003104f  mov     r15, [rbp+2Fh+arg_30]
0x180031053  lea     rax, [rbp+2Fh+var_90]
0x180031057  xor     r14d, r14d
0x18003105a  mov     [rsp+0C0h+var_98], rax; int *
0x18003105f  mov     [rsp+0C0h+var_A0], r9; struct _SID *
0x180031064  mov     rsi, r9
0x180031067  mov     r9, r8; struct _SID *
0x18003106a  mov     [rbp+2Fh+var_90], 0
0x180031071  mov     rdi, r8
0x180031074  mov     [rbp+2Fh+StringSid], r14
0x180031078  xor     r8d, r8d; int
0x18003107b  mov     [rbp+2Fh+var_48], r14
0x18003107f  mov     [rbp+2Fh+var_50], r14
0x180031083  mov     [rbp+2Fh+var_58], r14
0x180031087  mov     dword ptr [rbp+2Fh+var_88.20h+4], r14d
0x18003108b  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180031090  mov     ebx, eax
0x180031092  test    eax, eax
0x180031094  jz      short loc_1800310D3
0x180031096  mov     rcx, cs:WPP_GLOBAL_Control
0x18003109d  lea     rdx, WPP_GLOBAL_Control
0x1800310a4  cmp     rcx, rdx
0x1800310a7  jz      loc_180031379
0x1800310ad  test    byte ptr [rcx+1Ch], 1
0x1800310b1  jz      loc_180031379
0x1800310b7  lea     edx, [r14+75h]
0x1800310bb  mov     r9d, eax
0x1800310be  mov     rcx, [rcx+10h]
0x1800310c2  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800310c9  call    WPP_SF_d
0x1800310ce  jmp     loc_180031379
0x1800310d3  cmp     [rbp+2Fh+var_90], r14d
0x1800310d7  jnz     short loc_180031104
0x1800310d9  xor     ebx, ebx
0x1800310db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310e2  lea     rdx, WPP_GLOBAL_Control
0x1800310e9  cmp     rcx, rdx
0x1800310ec  jz      loc_180031379
0x1800310f2  test    byte ptr [rcx+1Ch], 1
0x1800310f6  jz      loc_180031379
0x1800310fc  lea     edx, [rbx+76h]
0x1800310ff  xor     r9d, r9d
0x180031102  jmp     short loc_1800310BE
0x180031104  lea     rdx, [rbp+2Fh+StringSid]; StringSid
0x180031108  mov     rcx, rdi; Sid
0x18003110b  call    cs:__imp_ConvertSidToStringSidW
0x180031111  test    eax, eax
0x180031113  jnz     short loc_180031148
0x180031115  call    cs:__imp_GetLastError
0x18003111b  mov     ebx, eax
0x18003111d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031124  lea     rdx, WPP_GLOBAL_Control
0x18003112b  cmp     rcx, rdx
0x18003112e  jz      loc_180031379
0x180031134  test    byte ptr [rcx+1Ch], 1
0x180031138  jz      loc_180031379
0x18003113e  mov     edx, 77h ; 'w'
0x180031143  jmp     loc_1800310BB
0x180031148  lea     rdx, [rbp+2Fh+var_48]; StringSid
0x18003114c  mov     rcx, rsi; Sid
0x18003114f  call    cs:__imp_ConvertSidToStringSidW
0x180031155  test    eax, eax
0x180031157  jnz     short loc_18003118C
0x180031159  call    cs:__imp_GetLastError
0x18003115f  mov     ebx, eax
0x180031161  mov     rcx, cs:WPP_GLOBAL_Control
0x180031168  lea     rdx, WPP_GLOBAL_Control
0x18003116f  cmp     rcx, rdx
0x180031172  jz      loc_180031379
0x180031178  test    byte ptr [rcx+1Ch], 1
0x18003117c  jz      loc_180031379
0x180031182  mov     edx, 78h ; 'x'
0x180031187  jmp     loc_1800310BB
0x18003118c  mov     r8, [rbp+2Fh+StringSid]
0x180031190  lea     rcx, [rbp+2Fh+var_50]
0x180031194  mov     rdx, [rbp+2Fh+var_48]
0x180031198  xor     r9d, r9d
0x18003119b  call    cs:__imp_FwStringBuild
0x1800311a1  mov     ecx, eax
0x1800311a3  call    cs:__imp_FwHResultToWindowsError
0x1800311a9  mov     ebx, eax
0x1800311ab  test    eax, eax
0x1800311ad  jz      short loc_1800311DA
0x1800311af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311b6  lea     rdx, WPP_GLOBAL_Control
0x1800311bd  cmp     rcx, rdx
0x1800311c0  jz      loc_180031379
0x1800311c6  test    byte ptr [rcx+1Ch], 1
0x1800311ca  jz      loc_180031379
0x1800311d0  mov     edx, 79h ; 'y'
0x1800311d5  jmp     loc_1800310BB
0x1800311da  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800311e1  lea     r9, [rbp+2Fh+var_58]
0x1800311e5  mov     r8, [rbp+2Fh+var_50]
0x1800311e9  mov     edx, 3
0x1800311ee  mov     rcx, [rcx+60h]
0x1800311f2  call    cs:__imp_FwGetRule
0x1800311f8  mov     ecx, eax
0x1800311fa  call    cs:__imp_FwHResultToWindowsError
0x180031200  mov     ebx, eax
0x180031202  test    eax, eax
0x180031204  jz      short loc_180031231
0x180031206  mov     rcx, cs:WPP_GLOBAL_Control
0x18003120d  lea     rdx, WPP_GLOBAL_Control
0x180031214  cmp     rcx, rdx
0x180031217  jz      loc_180031379
0x18003121d  test    byte ptr [rcx+1Ch], 1
0x180031221  jz      loc_180031379
0x180031227  mov     edx, 7Ah ; 'z'
0x18003122c  jmp     loc_1800310BB
0x180031231  mov     rcx, [rbp+2Fh+var_58]
0x180031235  mov     rcx, [rcx+68h]
0x180031239  call    cs:__imp_FwFree
0x18003123f  mov     rax, [rbp+2Fh+var_58]
0x180031243  mov     rcx, [rbp+2Fh+arg_20]
0x180031247  mov     [rax+68h], rcx
0x18003124b  mov     rcx, [rbp+2Fh+var_58]
0x18003124f  mov     rcx, [rcx+60h]
0x180031253  call    cs:__imp_FwFree
0x180031259  mov     rax, [rbp+2Fh+var_58]
0x18003125d  mov     rcx, [rbp+2Fh+arg_28]
0x180031261  mov     ebx, [rbp+2Fh+arg_38]
0x180031264  mov     [rax+60h], rcx
0x180031268  test    ebx, ebx
0x18003126a  jnz     short loc_1800312BF
0x18003126c  mov     rcx, cs:Block; this
0x180031273  call    ?FwMoneisRegistrationsForceComputeBinaries@IsolationEvents@appIsolation@@QEAAHXZ; appIsolation::IsolationEvents::FwMoneisRegistrationsForceComputeBinaries(void)
0x180031278  cmp     eax, 1
0x18003127b  jnz     short loc_1800312BF
0x18003127d  mov     rcx, [rbp+2Fh+var_58]; struct _tag_FW_APPCONTAINER *
0x180031281  call    ?FwMoneisReComputeAppContainerBinaries@@YAKPEAU_tag_FW_APPCONTAINER@@@Z; FwMoneisReComputeAppContainerBinaries(_tag_FW_APPCONTAINER *)
0x180031286  mov     ebx, eax
0x180031288  test    eax, eax
0x18003128a  jz      short loc_1800312B7
0x18003128c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031293  lea     rdx, WPP_GLOBAL_Control
0x18003129a  cmp     rcx, rdx
0x18003129d  jz      loc_180031379
0x1800312a3  test    byte ptr [rcx+1Ch], 1
0x1800312a7  jz      loc_180031379
0x1800312ad  mov     edx, 7Bh ; '{'
0x1800312b2  jmp     loc_1800310BB
0x1800312b7  mov     r14d, 1
0x1800312bd  jmp     short loc_1800312F0
0x1800312bf  mov     rcx, [rbp+2Fh+var_58]
0x1800312c3  mov     rdx, [rcx+58h]
0x1800312c7  mov     ecx, [rcx+50h]
0x1800312ca  call    cs:__imp_FwBinariesFree
0x1800312d0  mov     rax, [rbp+2Fh+var_58]
0x1800312d4  mov     ecx, [rbp+2Fh+arg_48]
0x1800312da  mov     [rax+50h], ecx
0x1800312dd  mov     rax, [rbp+2Fh+var_58]
0x1800312e1  mov     rcx, [rbp+2Fh+arg_40]
0x1800312e5  mov     [rax+58h], rcx
0x1800312e9  mov     rax, [rbp+2Fh+var_58]
0x1800312ed  mov     [rax+70h], ebx
0x1800312f0  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800312f7  mov     edx, 3
0x1800312fc  mov     r8, [rbp+2Fh+var_58]
0x180031300  mov     rcx, [rcx+60h]
0x180031304  call    cs:__imp_FwSetRule
0x18003130a  mov     ecx, eax
0x18003130c  call    cs:__imp_FwHResultToWindowsError
0x180031312  mov     ebx, eax
0x180031314  test    eax, eax
0x180031316  jz      short loc_18003133B
0x180031318  mov     rcx, cs:WPP_GLOBAL_Control
0x18003131f  lea     rdx, WPP_GLOBAL_Control
0x180031326  cmp     rcx, rdx
0x180031329  jz      short loc_180031379
0x18003132b  test    byte ptr [rcx+1Ch], 1
0x18003132f  jz      short loc_180031379
0x180031331  mov     edx, 7Ch ; '|'
0x180031336  jmp     loc_1800310BB
0x18003133b  mov     rcx, [rbp+2Fh+var_58]
0x18003133f  lea     r8, [rbp+2Fh+var_88]; struct _INET_FIREWALL_AC_CHANGE *
0x180031343  xor     edx, edx; int
0x180031345  mov     [rbp+2Fh+var_88.changeType], 1
0x18003134c  mov     [rbp+2Fh+var_88.createType], 2
0x180031353  mov     [rbp+2Fh+var_88.userSid], rdi
0x180031357  mov     eax, [rcx+50h]
0x18003135a  mov     dword ptr [rbp+2Fh+var_88.20h], eax
0x18003135d  mov     rax, [rcx+58h]
0x180031361  mov     rcx, cs:Block; this
0x180031368  mov     qword ptr [rbp+2Fh+var_88.20h+8], rax
0x18003136c  mov     [rbp+2Fh+var_88.appContainerSid], rsi
0x180031370  mov     [rbp+2Fh+var_88.displayName], r15
0x180031374  call    ?FwMoneisSendNotification@IsolationEvents@appIsolation@@QEAAKHQEAU_INET_FIREWALL_AC_CHANGE@@@Z; appIsolation::IsolationEvents::FwMoneisSendNotification(int,_INET_FIREWALL_AC_CHANGE * const)
0x180031379  mov     rax, [rbp+2Fh+var_58]
0x18003137d  test    rax, rax
0x180031380  jz      short loc_1800313B5
0x180031382  test    r14d, r14d
0x180031385  jnz     short loc_180031392
0x180031387  xorps   xmm0, xmm0
0x18003138a  movups  xmmword ptr [rax+50h], xmm0
0x18003138e  mov     rax, [rbp+2Fh+var_58]
0x180031392  mov     qword ptr [rax+68h], 0
0x18003139a  mov     edx, 3
0x18003139f  mov     rax, [rbp+2Fh+var_58]
0x1800313a3  mov     qword ptr [rax+60h], 0
0x1800313ab  mov     rcx, [rbp+2Fh+var_58]
0x1800313af  call    cs:__imp_FwFreeRules
0x1800313b5  mov     rcx, [rbp+2Fh+var_50]
0x1800313b9  test    rcx, rcx
0x1800313bc  jz      short loc_1800313C4
0x1800313be  call    cs:__imp_FwFree
0x1800313c4  mov     rcx, [rbp+2Fh+var_48]; hMem
0x1800313c8  test    rcx, rcx
0x1800313cb  jz      short loc_1800313D3
0x1800313cd  call    cs:__imp_LocalFree
0x1800313d3  mov     rcx, [rbp+2Fh+StringSid]; hMem
0x1800313d7  test    rcx, rcx
0x1800313da  jz      short loc_1800313E2
0x1800313dc  call    cs:__imp_LocalFree
0x1800313e2  mov     eax, ebx
0x1800313e4  mov     rcx, [rbp+2Fh+var_38]
0x1800313e8  xor     rcx, rsp; StackCookie
0x1800313eb  call    __security_check_cookie
0x1800313f0  add     rsp, 98h
0x1800313f7  pop     r15
0x1800313f9  pop     r14
0x1800313fb  pop     rdi
0x1800313fc  pop     rsi
0x1800313fd  pop     rbx
0x1800313fe  pop     rbp
0x1800313ff  retn
```
