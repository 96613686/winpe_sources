# FwMoneisSetupAppContainerBinaries

- ea: `0x1800350b4`
- end: `0x1800354ef`
- name: `FwMoneisSetupAppContainerBinaries`
- size: `1083`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180035500`
- `0x1800bc0b0`

## callees

- `0x18000a710`
- `0x1800350b4`
- `0x1800511b4`
- `0x1800729c0`
- `0x1800c1cb8`
- `0x1800c27e0`
- `0x1800c2860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800354c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035193`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800351e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035193`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800351e3`
- `fwbase!FwHResultToWindowsError` at `0x180035249`
- `fwbase!FwHResultToWindowsError` at `0x1800352ac`
- `fwbase!FwHResultToWindowsError` at `0x1800353dc`
- `fwbase!FwHResultToWindowsError` at `0x180035249`
- `fwbase!FwHResultToWindowsError` at `0x1800352ac`
- `fwbase!FwHResultToWindowsError` at `0x1800353dc`
- `fwbase!FwStringBuild` at `0x18003523b`
- `fwbase!FwStringBuild` at `0x18003523b`
- `fwbase!FwFree` at `0x1800352f1`
- `fwbase!FwFree` at `0x180035311`
- `fwbase!FwFree` at `0x18003549a`
- `fwbase!FwFree` at `0x1800352f1`
- `fwbase!FwFree` at `0x180035311`
- `fwbase!FwFree` at `0x18003549a`
- `FWPolicyIOMgr!FwGetRule` at `0x18003529e`
- `FWPolicyIOMgr!FwGetRule` at `0x18003529e`
- `FWPolicyIOMgr!FwSetRule` at `0x1800353ce`
- `FWPolicyIOMgr!FwSetRule` at `0x1800353ce`
- `FWPolicyIOMgr!FwFreeRules` at `0x180035485`
- `FWPolicyIOMgr!FwFreeRules` at `0x180035485`
- `FWPolicyIOMgr!FwBinariesFree` at `0x18003538e`
- `FWPolicyIOMgr!FwBinariesFree` at `0x18003538e`

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
  unsigned int LastError; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int Rule; // eax
  unsigned int v20; // eax
  struct _tag_FW_APPCONTAINER *v21; // rax
  int v23; // [rsp+30h] [rbp-61h] BYREF
  _INET_FIREWALL_AC_CHANGE v24; // [rsp+38h] [rbp-59h] BYREF
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
      v16 = 122;
LABEL_5:
      v17 = LastError;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v17);
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
        v16 = 123;
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
            v16 = 126;
            goto LABEL_5;
          }
        }
        else
        {
          Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 9), 3, v26, &v25);
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
                  v16 = 128;
                  goto LABEL_5;
                }
                goto LABEL_40;
              }
              v10 = 1;
            }
            v20 = FwSetRule(*((_QWORD *)gFwIsolationManager + 9), 3, v25);
            LastError = FwHResultToWindowsError(v20);
            v14 = LastError;
            if ( LastError )
            {
              v15 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v16 = 129;
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
            v16 = 127;
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
          v16 = 125;
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
        v16 = 124;
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
0x1800350b4  push    rbp
0x1800350b6  push    rbx
0x1800350b7  push    rsi
0x1800350b8  push    rdi
0x1800350b9  push    r14
0x1800350bb  push    r15
0x1800350bd  lea     rbp, [rsp-7]
0x1800350c2  sub     rsp, 98h
0x1800350c9  mov     rax, cs:__security_cookie
0x1800350d0  xor     rax, rsp
0x1800350d3  mov     [rbp+2Fh+var_38], rax
0x1800350d7  mov     r15, [rbp+2Fh+arg_30]
0x1800350db  lea     rax, [rbp+2Fh+var_90]
0x1800350df  xor     r14d, r14d
0x1800350e2  mov     [rsp+0C0h+var_98], rax; int *
0x1800350e7  mov     [rsp+0C0h+var_A0], r9; struct _SID *
0x1800350ec  mov     rsi, r9
0x1800350ef  mov     r9, r8; struct _SID *
0x1800350f2  mov     [rbp+2Fh+var_90], 0
0x1800350f9  mov     rdi, r8
0x1800350fc  mov     [rbp+2Fh+StringSid], r14
0x180035100  xor     r8d, r8d; int
0x180035103  mov     [rbp+2Fh+var_48], r14
0x180035107  mov     [rbp+2Fh+var_50], r14
0x18003510b  mov     [rbp+2Fh+var_58], r14
0x18003510f  mov     dword ptr [rbp+2Fh+var_88.20h+4], r14d
0x180035113  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180035118  mov     ebx, eax
0x18003511a  test    eax, eax
0x18003511c  jz      short loc_18003515B
0x18003511e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035125  lea     rdx, WPP_GLOBAL_Control
0x18003512c  cmp     rcx, rdx
0x18003512f  jz      loc_18003544F
0x180035135  test    byte ptr [rcx+1Ch], 1
0x180035139  jz      loc_18003544F
0x18003513f  lea     edx, [r14+7Ah]
0x180035143  mov     r9d, eax
0x180035146  mov     rcx, [rcx+10h]
0x18003514a  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180035151  call    WPP_SF_d
0x180035156  jmp     loc_18003544F
0x18003515b  cmp     [rbp+2Fh+var_90], r14d
0x18003515f  jnz     short loc_18003518C
0x180035161  xor     ebx, ebx
0x180035163  mov     rcx, cs:WPP_GLOBAL_Control
0x18003516a  lea     rdx, WPP_GLOBAL_Control
0x180035171  cmp     rcx, rdx
0x180035174  jz      loc_18003544F
0x18003517a  test    byte ptr [rcx+1Ch], 1
0x18003517e  jz      loc_18003544F
0x180035184  lea     edx, [rbx+7Bh]
0x180035187  xor     r9d, r9d
0x18003518a  jmp     short loc_180035146
0x18003518c  lea     rdx, [rbp+2Fh+StringSid]; StringSid
0x180035190  mov     rcx, rdi; Sid
0x180035193  call    cs:__imp_ConvertSidToStringSidW
0x18003519a  nop     dword ptr [rax+rax+00h]
0x18003519f  test    eax, eax
0x1800351a1  jnz     short loc_1800351DC
0x1800351a3  call    cs:__imp_GetLastError
0x1800351aa  nop     dword ptr [rax+rax+00h]
0x1800351af  mov     ebx, eax
0x1800351b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351b8  lea     rdx, WPP_GLOBAL_Control
0x1800351bf  cmp     rcx, rdx
0x1800351c2  jz      loc_18003544F
0x1800351c8  test    byte ptr [rcx+1Ch], 1
0x1800351cc  jz      loc_18003544F
0x1800351d2  mov     edx, 7Ch ; '|'
0x1800351d7  jmp     loc_180035143
0x1800351dc  lea     rdx, [rbp+2Fh+var_48]; StringSid
0x1800351e0  mov     rcx, rsi; Sid
0x1800351e3  call    cs:__imp_ConvertSidToStringSidW
0x1800351ea  nop     dword ptr [rax+rax+00h]
0x1800351ef  test    eax, eax
0x1800351f1  jnz     short loc_18003522C
0x1800351f3  call    cs:__imp_GetLastError
0x1800351fa  nop     dword ptr [rax+rax+00h]
0x1800351ff  mov     ebx, eax
0x180035201  mov     rcx, cs:WPP_GLOBAL_Control
0x180035208  lea     rdx, WPP_GLOBAL_Control
0x18003520f  cmp     rcx, rdx
0x180035212  jz      loc_18003544F
0x180035218  test    byte ptr [rcx+1Ch], 1
0x18003521c  jz      loc_18003544F
0x180035222  mov     edx, 7Dh ; '}'
0x180035227  jmp     loc_180035143
0x18003522c  mov     r8, [rbp+2Fh+StringSid]
0x180035230  lea     rcx, [rbp+2Fh+var_50]
0x180035234  mov     rdx, [rbp+2Fh+var_48]
0x180035238  xor     r9d, r9d
0x18003523b  call    cs:__imp_FwStringBuild
0x180035242  nop     dword ptr [rax+rax+00h]
0x180035247  mov     ecx, eax
0x180035249  call    cs:__imp_FwHResultToWindowsError
0x180035250  nop     dword ptr [rax+rax+00h]
0x180035255  mov     ebx, eax
0x180035257  test    eax, eax
0x180035259  jz      short loc_180035286
0x18003525b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035262  lea     rdx, WPP_GLOBAL_Control
0x180035269  cmp     rcx, rdx
0x18003526c  jz      loc_18003544F
0x180035272  test    byte ptr [rcx+1Ch], 1
0x180035276  jz      loc_18003544F
0x18003527c  mov     edx, 7Eh ; '~'
0x180035281  jmp     loc_180035143
0x180035286  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18003528d  lea     r9, [rbp+2Fh+var_58]
0x180035291  mov     r8, [rbp+2Fh+var_50]
0x180035295  mov     edx, 3
0x18003529a  mov     rcx, [rcx+48h]
0x18003529e  call    cs:__imp_FwGetRule
0x1800352a5  nop     dword ptr [rax+rax+00h]
0x1800352aa  mov     ecx, eax
0x1800352ac  call    cs:__imp_FwHResultToWindowsError
0x1800352b3  nop     dword ptr [rax+rax+00h]
0x1800352b8  mov     ebx, eax
0x1800352ba  test    eax, eax
0x1800352bc  jz      short loc_1800352E9
0x1800352be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800352c5  lea     rdx, WPP_GLOBAL_Control
0x1800352cc  cmp     rcx, rdx
0x1800352cf  jz      loc_18003544F
0x1800352d5  test    byte ptr [rcx+1Ch], 1
0x1800352d9  jz      loc_18003544F
0x1800352df  mov     edx, 7Fh
0x1800352e4  jmp     loc_180035143
0x1800352e9  mov     rcx, [rbp+2Fh+var_58]
0x1800352ed  mov     rcx, [rcx+68h]
0x1800352f1  call    cs:__imp_FwFree
0x1800352f8  nop     dword ptr [rax+rax+00h]
0x1800352fd  mov     rax, [rbp+2Fh+var_58]
0x180035301  mov     rcx, [rbp+2Fh+arg_20]
0x180035305  mov     [rax+68h], rcx
0x180035309  mov     rcx, [rbp+2Fh+var_58]
0x18003530d  mov     rcx, [rcx+60h]
0x180035311  call    cs:__imp_FwFree
0x180035318  nop     dword ptr [rax+rax+00h]
0x18003531d  mov     rax, [rbp+2Fh+var_58]
0x180035321  mov     rcx, [rbp+2Fh+arg_28]
0x180035325  mov     ebx, [rbp+2Fh+arg_38]
0x180035328  mov     [rax+60h], rcx
0x18003532c  test    ebx, ebx
0x18003532e  jnz     short loc_180035383
0x180035330  mov     rcx, cs:Block; this
0x180035337  call    ?FwMoneisRegistrationsForceComputeBinaries@IsolationEvents@appIsolation@@QEAAHXZ; appIsolation::IsolationEvents::FwMoneisRegistrationsForceComputeBinaries(void)
0x18003533c  cmp     eax, 1
0x18003533f  jnz     short loc_180035383
0x180035341  mov     rcx, [rbp+2Fh+var_58]; struct _tag_FW_APPCONTAINER *
0x180035345  call    ?FwMoneisReComputeAppContainerBinaries@@YAKPEAU_tag_FW_APPCONTAINER@@@Z; FwMoneisReComputeAppContainerBinaries(_tag_FW_APPCONTAINER *)
0x18003534a  mov     ebx, eax
0x18003534c  test    eax, eax
0x18003534e  jz      short loc_18003537B
0x180035350  mov     rcx, cs:WPP_GLOBAL_Control
0x180035357  lea     rdx, WPP_GLOBAL_Control
0x18003535e  cmp     rcx, rdx
0x180035361  jz      loc_18003544F
0x180035367  test    byte ptr [rcx+1Ch], 1
0x18003536b  jz      loc_18003544F
0x180035371  mov     edx, 80h
0x180035376  jmp     loc_180035143
0x18003537b  mov     r14d, 1
0x180035381  jmp     short loc_1800353BA
0x180035383  mov     rcx, [rbp+2Fh+var_58]
0x180035387  mov     rdx, [rcx+58h]
0x18003538b  mov     ecx, [rcx+50h]
0x18003538e  call    cs:__imp_FwBinariesFree
0x180035395  nop     dword ptr [rax+rax+00h]
0x18003539a  mov     rax, [rbp+2Fh+var_58]
0x18003539e  mov     ecx, [rbp+2Fh+arg_48]
0x1800353a4  mov     [rax+50h], ecx
0x1800353a7  mov     rax, [rbp+2Fh+var_58]
0x1800353ab  mov     rcx, [rbp+2Fh+arg_40]
0x1800353af  mov     [rax+58h], rcx
0x1800353b3  mov     rax, [rbp+2Fh+var_58]
0x1800353b7  mov     [rax+70h], ebx
0x1800353ba  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800353c1  mov     edx, 3
0x1800353c6  mov     r8, [rbp+2Fh+var_58]
0x1800353ca  mov     rcx, [rcx+48h]
0x1800353ce  call    cs:__imp_FwSetRule
0x1800353d5  nop     dword ptr [rax+rax+00h]
0x1800353da  mov     ecx, eax
0x1800353dc  call    cs:__imp_FwHResultToWindowsError
0x1800353e3  nop     dword ptr [rax+rax+00h]
0x1800353e8  mov     ebx, eax
0x1800353ea  test    eax, eax
0x1800353ec  jz      short loc_180035411
0x1800353ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353f5  lea     rdx, WPP_GLOBAL_Control
0x1800353fc  cmp     rcx, rdx
0x1800353ff  jz      short loc_18003544F
0x180035401  test    byte ptr [rcx+1Ch], 1
0x180035405  jz      short loc_18003544F
0x180035407  mov     edx, 81h
0x18003540c  jmp     loc_180035143
0x180035411  mov     rcx, [rbp+2Fh+var_58]
0x180035415  lea     r8, [rbp+2Fh+var_88]; struct _INET_FIREWALL_AC_CHANGE *
0x180035419  xor     edx, edx; int
0x18003541b  mov     [rbp+2Fh+var_88.changeType], 1
0x180035422  mov     [rbp+2Fh+var_88.createType], 2
0x180035429  mov     [rbp+2Fh+var_88.userSid], rdi
0x18003542d  mov     eax, [rcx+50h]
0x180035430  mov     dword ptr [rbp+2Fh+var_88.20h], eax
0x180035433  mov     rax, [rcx+58h]
0x180035437  mov     rcx, cs:Block; this
0x18003543e  mov     qword ptr [rbp+2Fh+var_88.20h+8], rax
0x180035442  mov     [rbp+2Fh+var_88.appContainerSid], rsi
0x180035446  mov     [rbp+2Fh+var_88.displayName], r15
0x18003544a  call    ?FwMoneisSendNotification@IsolationEvents@appIsolation@@QEAAKHQEAU_INET_FIREWALL_AC_CHANGE@@@Z; appIsolation::IsolationEvents::FwMoneisSendNotification(int,_INET_FIREWALL_AC_CHANGE * const)
0x18003544f  mov     rax, [rbp+2Fh+var_58]
0x180035453  test    rax, rax
0x180035456  jz      short loc_180035491
0x180035458  test    r14d, r14d
0x18003545b  jnz     short loc_180035468
0x18003545d  xorps   xmm0, xmm0
0x180035460  movups  xmmword ptr [rax+50h], xmm0
0x180035464  mov     rax, [rbp+2Fh+var_58]
0x180035468  mov     qword ptr [rax+68h], 0
0x180035470  mov     edx, 3
0x180035475  mov     rax, [rbp+2Fh+var_58]
0x180035479  mov     qword ptr [rax+60h], 0
0x180035481  mov     rcx, [rbp+2Fh+var_58]
0x180035485  call    cs:__imp_FwFreeRules
0x18003548c  nop     dword ptr [rax+rax+00h]
0x180035491  mov     rcx, [rbp+2Fh+var_50]
0x180035495  test    rcx, rcx
0x180035498  jz      short loc_1800354A6
0x18003549a  call    cs:__imp_FwFree
0x1800354a1  nop     dword ptr [rax+rax+00h]
0x1800354a6  mov     rcx, [rbp+2Fh+var_48]; hMem
0x1800354aa  test    rcx, rcx
0x1800354ad  jz      short loc_1800354BB
0x1800354af  call    cs:__imp_LocalFree
0x1800354b6  nop     dword ptr [rax+rax+00h]
0x1800354bb  mov     rcx, [rbp+2Fh+StringSid]; hMem
0x1800354bf  test    rcx, rcx
0x1800354c2  jz      short loc_1800354D0
0x1800354c4  call    cs:__imp_LocalFree
0x1800354cb  nop     dword ptr [rax+rax+00h]
0x1800354d0  mov     eax, ebx
0x1800354d2  mov     rcx, [rbp+2Fh+var_38]
0x1800354d6  xor     rcx, rsp; StackCookie
0x1800354d9  call    __security_check_cookie
0x1800354de  add     rsp, 98h
0x1800354e5  pop     r15
0x1800354e7  pop     r14
0x1800354e9  pop     rdi
0x1800354ea  pop     rsi
0x1800354eb  pop     rbx
0x1800354ec  pop     rbp
0x1800354ed  retn
```
