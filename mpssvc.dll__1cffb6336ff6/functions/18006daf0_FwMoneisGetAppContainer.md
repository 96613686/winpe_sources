# FwMoneisGetAppContainer

- ea: `0x18006daf0`
- end: `0x18006de0a`
- name: `FwMoneisGetAppContainer`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006d9f0`

## callees

- `0x18000af3c`
- `0x1800620b8`
- `0x18006daf0`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dbe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dbe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dc25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ddeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006dddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ddeb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dbd7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dc1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dbd7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dc1b`
- `fwbase!FwHResultToWindowsError` at `0x18006dc6f`
- `fwbase!FwHResultToWindowsError` at `0x18006dcd3`
- `fwbase!FwHResultToWindowsError` at `0x18006dc6f`
- `fwbase!FwHResultToWindowsError` at `0x18006dcd3`
- `fwbase!FwStringBuild` at `0x18006dc67`
- `fwbase!FwStringBuild` at `0x18006dc67`
- `fwbase!FwAlloc` at `0x18006dd36`
- `fwbase!FwAlloc` at `0x18006dd36`
- `fwbase!FwCriticalSectionEnter` at `0x18006dcad`
- `fwbase!FwCriticalSectionEnter` at `0x18006dcad`
- `fwbase!FwCriticalSectionLeave` at `0x18006dd17`
- `fwbase!FwCriticalSectionLeave` at `0x18006dd29`
- `fwbase!FwCriticalSectionLeave` at `0x18006dd17`
- `fwbase!FwCriticalSectionLeave` at `0x18006dd29`
- `fwbase!FwFree` at `0x18006ddcd`
- `fwbase!FwFree` at `0x18006ddcd`
- `FWPolicyIOMgr!FwGetRule` at `0x18006dccb`
- `FWPolicyIOMgr!FwGetRule` at `0x18006dccb`
- `FWPolicyIOMgr!FwFreeRules` at `0x18006ddbe`
- `FWPolicyIOMgr!FwFreeRules` at `0x18006ddbe`

## pseudocode

```c
__int64 __fastcall FwMoneisGetAppContainer(
        void *a1,
        int a2,
        __int64 a3,
        struct _SID *a4,
        struct _SID *Sid,
        __int64 *a6)
{
  DWORD LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  unsigned int Rule; // eax
  unsigned int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rax
  int v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR v21; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-10h] BYREF

  v18 = 0;
  *a6 = 0;
  StringSid = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  LastError = FwMoneisValidateAppContainerOperation(a1, a2, 0, a4, Sid, &v18);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 125;
LABEL_5:
      v11 = LastError;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v11);
    }
  }
  else if ( v18 )
  {
    if ( ConvertSidToStringSidW(a4, &StringSid) )
    {
      if ( ConvertSidToStringSidW(Sid, &v21) )
      {
        v12 = FwStringBuild(&v20, v21, StringSid, 0);
        LastError = FwHResultToWindowsError(v12);
        v8 = LastError;
        if ( LastError )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v10 = 129;
            goto LABEL_5;
          }
        }
        else
        {
          FwCriticalSectionEnter(gFwIsolationManager);
          Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 12), 3, v20, &v19);
          v14 = FwHResultToWindowsError(Rule);
          v8 = v14;
          if ( v14 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                130,
                WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
                v14);
            }
            FwCriticalSectionLeave(gFwIsolationManager);
          }
          else
          {
            FwCriticalSectionLeave(gFwIsolationManager);
            v15 = FwAlloc(88);
            if ( v15 )
            {
              v16 = v19;
              *(_OWORD *)v15 = *(_OWORD *)(v19 + 24);
              *(_OWORD *)(v15 + 16) = *(_OWORD *)(v16 + 40);
              *(_OWORD *)(v15 + 32) = *(_OWORD *)(v16 + 56);
              *(_OWORD *)(v15 + 48) = *(_OWORD *)(v16 + 72);
              *(_OWORD *)(v15 + 64) = *(_OWORD *)(v16 + 88);
              *(_QWORD *)(v15 + 80) = *(_QWORD *)(v16 + 104);
              memset_0((void *)(v19 + 24), 0, 0x58u);
              *a6 = v15;
            }
            else
            {
              v8 = 14;
              v9 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v10 = 131;
                v11 = 14;
                goto LABEL_6;
              }
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v10 = 128;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v10 = 127;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 126;
      v11 = 0;
      goto LABEL_6;
    }
  }
  FwFreeRules(v19, 3);
  if ( v20 )
    FwFree(v20);
  if ( v21 )
    LocalFree(v21);
  if ( StringSid )
    LocalFree(StringSid);
  return v8;
}

```

## disassembly

```asm
0x18006daf0  push    rbp
0x18006daf2  push    rbx
0x18006daf3  push    rsi
0x18006daf4  push    rdi
0x18006daf5  push    r14
0x18006daf7  mov     rbp, rsp
0x18006dafa  sub     rsp, 60h
0x18006dafe  mov     rax, cs:__security_cookie
0x18006db05  xor     rax, rsp
0x18006db08  mov     [rbp+var_8], rax
0x18006db0c  mov     r14, [rbp+arg_28]
0x18006db10  lea     rax, [rbp+var_30]
0x18006db14  mov     rsi, [rbp+Sid]
0x18006db18  xor     r8d, r8d; int
0x18006db1b  mov     [rsp+60h+var_38], rax; int *
0x18006db20  mov     rdi, r9
0x18006db23  mov     [rbp+var_30], 0
0x18006db2a  mov     qword ptr [r14], 0
0x18006db31  mov     [rbp+StringSid], 0
0x18006db39  mov     [rbp+var_18], 0
0x18006db41  mov     [rbp+var_20], 0
0x18006db49  mov     [rbp+var_28], 0
0x18006db51  mov     [rsp+60h+var_40], rsi; struct _SID *
0x18006db56  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x18006db5b  mov     ebx, eax
0x18006db5d  test    eax, eax
0x18006db5f  jz      short loc_18006DB9F
0x18006db61  mov     rcx, cs:WPP_GLOBAL_Control
0x18006db68  lea     rdx, WPP_GLOBAL_Control
0x18006db6f  cmp     rcx, rdx
0x18006db72  jz      loc_18006DDB5
0x18006db78  test    byte ptr [rcx+1Ch], 1
0x18006db7c  jz      loc_18006DDB5
0x18006db82  mov     edx, 7Dh ; '}'
0x18006db87  mov     r9d, eax
0x18006db8a  mov     rcx, [rcx+10h]
0x18006db8e  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18006db95  call    WPP_SF_d
0x18006db9a  jmp     loc_18006DDB5
0x18006db9f  cmp     [rbp+var_30], 0
0x18006dba3  jnz     short loc_18006DBD0
0x18006dba5  xor     ebx, ebx
0x18006dba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbae  lea     rdx, WPP_GLOBAL_Control
0x18006dbb5  cmp     rcx, rdx
0x18006dbb8  jz      loc_18006DDB5
0x18006dbbe  test    byte ptr [rcx+1Ch], 1
0x18006dbc2  jz      loc_18006DDB5
0x18006dbc8  lea     edx, [rbx+7Eh]
0x18006dbcb  xor     r9d, r9d
0x18006dbce  jmp     short loc_18006DB8A
0x18006dbd0  lea     rdx, [rbp+StringSid]; StringSid
0x18006dbd4  mov     rcx, rdi; Sid
0x18006dbd7  call    cs:__imp_ConvertSidToStringSidW
0x18006dbdd  test    eax, eax
0x18006dbdf  jnz     short loc_18006DC14
0x18006dbe1  call    cs:__imp_GetLastError
0x18006dbe7  mov     ebx, eax
0x18006dbe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbf0  lea     rdx, WPP_GLOBAL_Control
0x18006dbf7  cmp     rcx, rdx
0x18006dbfa  jz      loc_18006DDB5
0x18006dc00  test    byte ptr [rcx+1Ch], 1
0x18006dc04  jz      loc_18006DDB5
0x18006dc0a  mov     edx, 7Fh
0x18006dc0f  jmp     loc_18006DB87
0x18006dc14  lea     rdx, [rbp+var_18]; StringSid
0x18006dc18  mov     rcx, rsi; Sid
0x18006dc1b  call    cs:__imp_ConvertSidToStringSidW
0x18006dc21  test    eax, eax
0x18006dc23  jnz     short loc_18006DC58
0x18006dc25  call    cs:__imp_GetLastError
0x18006dc2b  mov     ebx, eax
0x18006dc2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc34  lea     rdx, WPP_GLOBAL_Control
0x18006dc3b  cmp     rcx, rdx
0x18006dc3e  jz      loc_18006DDB5
0x18006dc44  test    byte ptr [rcx+1Ch], 1
0x18006dc48  jz      loc_18006DDB5
0x18006dc4e  mov     edx, 80h
0x18006dc53  jmp     loc_18006DB87
0x18006dc58  mov     r8, [rbp+StringSid]
0x18006dc5c  lea     rcx, [rbp+var_20]
0x18006dc60  mov     rdx, [rbp+var_18]
0x18006dc64  xor     r9d, r9d
0x18006dc67  call    cs:__imp_FwStringBuild
0x18006dc6d  mov     ecx, eax
0x18006dc6f  call    cs:__imp_FwHResultToWindowsError
0x18006dc75  mov     ebx, eax
0x18006dc77  test    eax, eax
0x18006dc79  jz      short loc_18006DCA6
0x18006dc7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc82  lea     rdx, WPP_GLOBAL_Control
0x18006dc89  cmp     rcx, rdx
0x18006dc8c  jz      loc_18006DDB5
0x18006dc92  test    byte ptr [rcx+1Ch], 1
0x18006dc96  jz      loc_18006DDB5
0x18006dc9c  mov     edx, 81h
0x18006dca1  jmp     loc_18006DB87
0x18006dca6  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18006dcad  call    cs:__imp_FwCriticalSectionEnter
0x18006dcb3  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18006dcba  lea     r9, [rbp+var_28]
0x18006dcbe  mov     r8, [rbp+var_20]
0x18006dcc2  mov     edx, 3
0x18006dcc7  mov     rcx, [rcx+60h]
0x18006dccb  call    cs:__imp_FwGetRule
0x18006dcd1  mov     ecx, eax
0x18006dcd3  call    cs:__imp_FwHResultToWindowsError
0x18006dcd9  mov     ebx, eax
0x18006dcdb  test    eax, eax
0x18006dcdd  jz      short loc_18006DD22
0x18006dcdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dce6  lea     rdx, WPP_GLOBAL_Control
0x18006dced  cmp     rcx, rdx
0x18006dcf0  jz      short loc_18006DD10
0x18006dcf2  test    byte ptr [rcx+1Ch], 1
0x18006dcf6  jz      short loc_18006DD10
0x18006dcf8  mov     rcx, [rcx+10h]
0x18006dcfc  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x18006dd03  mov     edx, 82h
0x18006dd08  mov     r9d, eax
0x18006dd0b  call    WPP_SF_d
0x18006dd10  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18006dd17  call    cs:__imp_FwCriticalSectionLeave
0x18006dd1d  jmp     loc_18006DDB5
0x18006dd22  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18006dd29  call    cs:__imp_FwCriticalSectionLeave
0x18006dd2f  mov     esi, 58h ; 'X'
0x18006dd34  mov     ecx, esi
0x18006dd36  call    cs:__imp_FwAlloc
0x18006dd3c  mov     rdi, rax
0x18006dd3f  test    rax, rax
0x18006dd42  jnz     short loc_18006DD6B
0x18006dd44  lea     ebx, [rsi-4Ah]
0x18006dd47  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd4e  lea     rdx, WPP_GLOBAL_Control
0x18006dd55  cmp     rcx, rdx
0x18006dd58  jz      short loc_18006DDB5
0x18006dd5a  test    byte ptr [rcx+1Ch], 1
0x18006dd5e  jz      short loc_18006DDB5
0x18006dd60  lea     edx, [rsi+2Bh]
0x18006dd63  mov     r9d, ebx
0x18006dd66  jmp     loc_18006DB8A
0x18006dd6b  mov     rax, [rbp+var_28]
0x18006dd6f  mov     r8, rsi; Size
0x18006dd72  xor     edx, edx; Val
0x18006dd74  movups  xmm0, xmmword ptr [rax+18h]
0x18006dd78  movups  xmmword ptr [rdi], xmm0
0x18006dd7b  movups  xmm1, xmmword ptr [rax+28h]
0x18006dd7f  movups  xmmword ptr [rdi+10h], xmm1
0x18006dd83  movups  xmm0, xmmword ptr [rax+38h]
0x18006dd87  movups  xmmword ptr [rdi+20h], xmm0
0x18006dd8b  movups  xmm1, xmmword ptr [rax+48h]
0x18006dd8f  movups  xmmword ptr [rdi+30h], xmm1
0x18006dd93  movups  xmm0, xmmword ptr [rax+58h]
0x18006dd97  movups  xmmword ptr [rdi+40h], xmm0
0x18006dd9b  movsd   xmm1, qword ptr [rax+68h]
0x18006dda0  movsd   qword ptr [rdi+50h], xmm1
0x18006dda5  mov     rcx, [rbp+var_28]
0x18006dda9  add     rcx, 18h; void *
0x18006ddad  call    memset_0
0x18006ddb2  mov     [r14], rdi
0x18006ddb5  mov     rcx, [rbp+var_28]
0x18006ddb9  mov     edx, 3
0x18006ddbe  call    cs:__imp_FwFreeRules
0x18006ddc4  mov     rcx, [rbp+var_20]
0x18006ddc8  test    rcx, rcx
0x18006ddcb  jz      short loc_18006DDD3
0x18006ddcd  call    cs:__imp_FwFree
0x18006ddd3  mov     rcx, [rbp+var_18]; hMem
0x18006ddd7  test    rcx, rcx
0x18006ddda  jz      short loc_18006DDE2
0x18006dddc  call    cs:__imp_LocalFree
0x18006dde2  mov     rcx, [rbp+StringSid]; hMem
0x18006dde6  test    rcx, rcx
0x18006dde9  jz      short loc_18006DDF1
0x18006ddeb  call    cs:__imp_LocalFree
0x18006ddf1  mov     eax, ebx
0x18006ddf3  mov     rcx, [rbp+var_8]
0x18006ddf7  xor     rcx, rsp; StackCookie
0x18006ddfa  call    __security_check_cookie
0x18006ddff  add     rsp, 60h
0x18006de03  pop     r14
0x18006de05  pop     rdi
0x18006de06  pop     rsi
0x18006de07  pop     rbx
0x18006de08  pop     rbp
0x18006de09  retn
```
