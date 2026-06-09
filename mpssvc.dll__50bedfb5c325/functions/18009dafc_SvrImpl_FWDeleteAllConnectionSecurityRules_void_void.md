# SvrImpl_FWDeleteAllConnectionSecurityRules(void *,void *)

- ea: `0x18009dafc`
- end: `0x18009de41`
- name: `?SvrImpl_FWDeleteAllConnectionSecurityRules@@YAKPEAX0@Z`
- size: `837`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c75f0`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18003ec48`
- `0x1800481ac`
- `0x180059714`
- `0x18005e408`
- `0x180060ef8`
- `0x18006e578`
- `0x1800729c0`
- `0x18009dafc`
- `0x1800a700c`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009dd57`
- `fwbase!FwHResultToWindowsError` at `0x18009ddc2`
- `fwbase!FwHResultToWindowsError` at `0x18009de13`
- `fwbase!FwHResultToWindowsError` at `0x18009dd57`
- `fwbase!FwHResultToWindowsError` at `0x18009ddc2`
- `fwbase!FwHResultToWindowsError` at `0x18009de13`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009dbe6`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009dbe6`
- `fwbase!FwChangeSourceSignal` at `0x18009dd49`
- `fwbase!FwChangeSourceSignal` at `0x18009dd49`
- `fwbase!FwFree` at `0x18009ddf4`
- `fwbase!FwFree` at `0x18009de05`
- `fwbase!FwFree` at `0x18009ddf4`
- `fwbase!FwFree` at `0x18009de05`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009dc85`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x18009dc85`

## string_xrefs

- `0x18009db64`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x18009db83`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x18009dd2a`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x18009dd39`: `SvrImpl_FWDeleteAllConnectionSecurityRules`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAllConnectionSecurityRules(void *a1, _DWORD *a2)
{
  __int64 result; // rax
  int v5; // ebx
  unsigned int v6; // esi
  int RPCClientSID; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdi
  const unsigned __int16 *v15; // r8
  const wchar_t *v16; // rdx
  int v17; // eax
  int v18; // r8d
  const wchar_t **v19; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-40h] BYREF

  v19 = 0;
  v20 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 267, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAllConnectionSecurityRules");
  if ( (int)result >= 0 )
  {
    v5 = FwLock();
    if ( v5 < 0 )
    {
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllConnectionSecurityRules");
      return (unsigned int)v5;
    }
    v6 = 0;
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v19);
    v8 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_36;
      v10 = 268;
LABEL_11:
      v11 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v11);
LABEL_36:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllConnectionSecurityRules");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllConnectionSecurityRules");
      if ( (v8 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v13 = FwHResultToWindowsError(v8);
      v14 = &qword_1800FBFF0;
      v15 = &qword_1800FBFF0;
      if ( v20 )
        v15 = v20;
      if ( v19 )
        v16 = *v19;
      else
        v16 = L"S-1-0-0";
      FwLogBatchUpdate(WFAllCSRulesDeletedEvent0, v16, v15, v6, v13);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v20 )
          v14 = v20;
        v17 = FwHResultToWindowsError(v8);
        WPP_SF_DSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 274, v18, v17, (__int64)v14, v6);
      }
      FwFree(v19);
      FwFree(v20);
      return FwHResultToWindowsError(v8);
    }
    FwGetRpcCallersProcessImageName(a1, &v20);
    if ( a2[6] == 2 )
    {
      v6 = a2[4];
      if ( v6 == 2 || v6 == 5 )
      {
        if ( *(_QWORD *)a2 && (RPCClientSID = FwDeleteAllRules(*(_QWORD *)a2, 1), v8 = RPCClientSID, RPCClientSID < 0) )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v10 = 272;
        }
        else
        {
          RPCClientSID = FwIncrmDeleteAllRules(*((_QWORD *)a2 + 1), (unsigned int)a2[4], 1);
          v8 = RPCClientSID;
          if ( RPCClientSID >= 0 )
          {
            v12 = FwStringTableFind(&dword_1801341D0, 23173);
            FwAuditLogRuleChange((unsigned int)*v19, 0x7FFFFFFF, 1, 1, v12, 0);
            FwUpdateConsecPresenceDataPoint();
            goto LABEL_36;
          }
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_36;
          v10 = 273;
        }
        goto LABEL_11;
      }
      v8 = -2147024846;
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_36;
      v10 = 271;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 269);
        v9 = WPP_GLOBAL_Control;
      }
      v8 = -2147024891;
      if ( (_UNKNOWN *)v9 == &WPP_GLOBAL_Control || (*(_BYTE *)(v9 + 28) & 1) == 0 )
        goto LABEL_36;
      v10 = 270;
    }
    v11 = v8;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009dafc  mov     [rsp+arg_10], rbx
0x18009db01  push    rbp
0x18009db02  push    rsi
0x18009db03  push    rdi
0x18009db04  push    r12
0x18009db06  push    r15
0x18009db08  sub     rsp, 50h
0x18009db0c  mov     rax, cs:__security_cookie
0x18009db13  xor     rax, rsp
0x18009db16  mov     [rsp+78h+var_38], rax
0x18009db1b  mov     rdi, rdx
0x18009db1e  mov     [rsp+78h+var_48], 0
0x18009db27  mov     rbp, rcx
0x18009db2a  mov     [rsp+78h+var_40], 0
0x18009db33  mov     rcx, cs:WPP_GLOBAL_Control
0x18009db3a  lea     r15, WPP_GLOBAL_Control
0x18009db41  lea     r12, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009db48  cmp     rcx, r15
0x18009db4b  jz      short loc_18009DB64
0x18009db4d  test    byte ptr [rcx+1Ch], 8
0x18009db51  jz      short loc_18009DB64
0x18009db53  mov     rcx, [rcx+10h]
0x18009db57  mov     edx, 10Bh
0x18009db5c  mov     r8, r12
0x18009db5f  call    WPP_SF_
0x18009db64  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x18009db6b  call    FwAcquireRPCSharedLock
0x18009db70  test    eax, eax
0x18009db72  js      loc_18009DE1F
0x18009db78  call    FwLock
0x18009db7d  mov     ebx, eax
0x18009db7f  test    eax, eax
0x18009db81  jns     short loc_18009DB96
0x18009db83  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x18009db8a  call    FwReleaseRPCSharedLock
0x18009db8f  mov     eax, ebx
0x18009db91  jmp     loc_18009DE1F
0x18009db96  lea     rdx, [rsp+78h+var_48]
0x18009db9b  mov     rcx, rbp
0x18009db9e  xor     esi, esi
0x18009dba0  call    ExtractRPCClientSID
0x18009dba5  mov     ebx, eax
0x18009dba7  test    eax, eax
0x18009dba9  jns     short loc_18009DBDE
0x18009dbab  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dbb2  cmp     rcx, r15
0x18009dbb5  jz      loc_18009DD2A
0x18009dbbb  test    byte ptr [rcx+1Ch], 1
0x18009dbbf  jz      loc_18009DD2A
0x18009dbc5  mov     edx, 10Ch
0x18009dbca  mov     r9d, eax
0x18009dbcd  mov     rcx, [rcx+10h]
0x18009dbd1  mov     r8, r12
0x18009dbd4  call    WPP_SF_d
0x18009dbd9  jmp     loc_18009DD2A
0x18009dbde  lea     rdx, [rsp+78h+var_40]
0x18009dbe3  mov     rcx, rbp
0x18009dbe6  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009dbed  nop     dword ptr [rax+rax+00h]
0x18009dbf2  mov     r9d, [rdi+18h]
0x18009dbf6  cmp     r9d, 2
0x18009dbfa  jz      short loc_18009DC45
0x18009dbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc03  cmp     rcx, r15
0x18009dc06  jz      short loc_18009DC23
0x18009dc08  test    byte ptr [rcx+1Ch], 1
0x18009dc0c  jz      short loc_18009DC23
0x18009dc0e  mov     rcx, [rcx+10h]
0x18009dc12  mov     edx, 10Dh
0x18009dc17  call    WPP_SF_l
0x18009dc1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc23  mov     ebx, 80070005h
0x18009dc28  cmp     rcx, r15
0x18009dc2b  jz      loc_18009DD2A
0x18009dc31  test    byte ptr [rcx+1Ch], 1
0x18009dc35  jz      loc_18009DD2A
0x18009dc3b  mov     edx, 10Eh
0x18009dc40  mov     r9d, ebx
0x18009dc43  jmp     short loc_18009DBCD
0x18009dc45  mov     esi, [rdi+10h]
0x18009dc48  cmp     esi, 2
0x18009dc4b  jz      short loc_18009DC78
0x18009dc4d  cmp     esi, 5
0x18009dc50  jz      short loc_18009DC78
0x18009dc52  mov     ebx, 80070032h
0x18009dc57  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc5e  cmp     rcx, r15
0x18009dc61  jz      loc_18009DD2A
0x18009dc67  test    byte ptr [rcx+1Ch], 1
0x18009dc6b  jz      loc_18009DD2A
0x18009dc71  mov     edx, 10Fh
0x18009dc76  jmp     short loc_18009DC40
0x18009dc78  mov     rcx, [rdi]
0x18009dc7b  test    rcx, rcx
0x18009dc7e  jz      short loc_18009DCB7
0x18009dc80  mov     edx, 1
0x18009dc85  call    cs:__imp_FwDeleteAllRules
0x18009dc8c  nop     dword ptr [rax+rax+00h]
0x18009dc91  mov     ebx, eax
0x18009dc93  test    eax, eax
0x18009dc95  jns     short loc_18009DCB7
0x18009dc97  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc9e  cmp     rcx, r15
0x18009dca1  jz      loc_18009DD2A
0x18009dca7  test    byte ptr [rcx+1Ch], 1
0x18009dcab  jz      short loc_18009DD2A
0x18009dcad  mov     edx, 110h
0x18009dcb2  jmp     loc_18009DBCA
0x18009dcb7  mov     edx, [rdi+10h]
0x18009dcba  mov     r8d, 1
0x18009dcc0  mov     rcx, [rdi+8]
0x18009dcc4  call    FwIncrmDeleteAllRules
0x18009dcc9  mov     ebx, eax
0x18009dccb  test    eax, eax
0x18009dccd  jns     short loc_18009DCEB
0x18009dccf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dcd6  cmp     rcx, r15
0x18009dcd9  jz      short loc_18009DD2A
0x18009dcdb  test    byte ptr [rcx+1Ch], 1
0x18009dcdf  jz      short loc_18009DD2A
0x18009dce1  mov     edx, 111h
0x18009dce6  jmp     loc_18009DBCA
0x18009dceb  mov     edx, 5A85h
0x18009dcf0  lea     rcx, dword_1801341D0
0x18009dcf7  call    FwStringTableFind
0x18009dcfc  mov     rcx, [rsp+78h+var_48]
0x18009dd01  mov     r9d, 1
0x18009dd07  mov     [rsp+78h+var_50], 0
0x18009dd10  mov     edx, 7FFFFFFFh
0x18009dd15  mov     r8d, r9d
0x18009dd18  mov     [rsp+78h+var_58], rax
0x18009dd1d  mov     rcx, [rcx]
0x18009dd20  call    FwAuditLogRuleChange
0x18009dd25  call    FwUpdateConsecPresenceDataPoint
0x18009dd2a  lea     rdx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x18009dd31  mov     rcx, rbp; void *
0x18009dd34  call    FwUnlockInternal
0x18009dd39  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x18009dd40  call    FwReleaseRPCSharedLock
0x18009dd45  test    ebx, ebx
0x18009dd47  js      short loc_18009DD55
0x18009dd49  call    cs:__imp_FwChangeSourceSignal
0x18009dd50  nop     dword ptr [rax+rax+00h]
0x18009dd55  mov     ecx, ebx
0x18009dd57  call    cs:__imp_FwHResultToWindowsError
0x18009dd5e  nop     dword ptr [rax+rax+00h]
0x18009dd63  mov     rcx, [rsp+78h+var_40]
0x18009dd68  lea     rdi, qword_1800FBFF0
0x18009dd6f  mov     rdx, [rsp+78h+var_48]
0x18009dd74  test    rcx, rcx
0x18009dd77  mov     r8, rdi
0x18009dd7a  cmovnz  r8, rcx
0x18009dd7e  test    rdx, rdx
0x18009dd81  jz      short loc_18009DD88
0x18009dd83  mov     rdx, [rdx]
0x18009dd86  jmp     short loc_18009DD8F
0x18009dd88  lea     rdx, aS100; "S-1-0-0"
0x18009dd8f  mov     r9d, esi
0x18009dd92  mov     dword ptr [rsp+78h+var_58], eax
0x18009dd96  lea     rcx, WFAllCSRulesDeletedEvent0
0x18009dd9d  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x18009dda2  mov     rax, cs:WPP_GLOBAL_Control
0x18009dda9  cmp     rax, r15
0x18009ddac  jz      short loc_18009DDEF
0x18009ddae  test    byte ptr [rax+1Ch], 4
0x18009ddb2  jz      short loc_18009DDEF
0x18009ddb4  mov     rax, [rsp+78h+var_40]
0x18009ddb9  mov     ecx, ebx
0x18009ddbb  test    rax, rax
0x18009ddbe  cmovnz  rdi, rax
0x18009ddc2  call    cs:__imp_FwHResultToWindowsError
0x18009ddc9  nop     dword ptr [rax+rax+00h]
0x18009ddce  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ddd5  mov     edx, 112h
0x18009ddda  mov     dword ptr [rsp+78h+var_50], esi
0x18009ddde  mov     r9d, eax
0x18009dde1  mov     [rsp+78h+var_58], rdi
0x18009dde6  mov     rcx, [rcx+10h]
0x18009ddea  call    WPP_SF_DSD
0x18009ddef  mov     rcx, [rsp+78h+var_48]
0x18009ddf4  call    cs:__imp_FwFree
0x18009ddfb  nop     dword ptr [rax+rax+00h]
0x18009de00  mov     rcx, [rsp+78h+var_40]
0x18009de05  call    cs:__imp_FwFree
0x18009de0c  nop     dword ptr [rax+rax+00h]
0x18009de11  mov     ecx, ebx
0x18009de13  call    cs:__imp_FwHResultToWindowsError
0x18009de1a  nop     dword ptr [rax+rax+00h]
0x18009de1f  mov     rcx, [rsp+78h+var_38]
0x18009de24  xor     rcx, rsp; StackCookie
0x18009de27  call    __security_check_cookie
0x18009de2c  mov     rbx, [rsp+78h+arg_10]
0x18009de34  add     rsp, 50h
0x18009de38  pop     r15
0x18009de3a  pop     r12
0x18009de3c  pop     rdi
0x18009de3d  pop     rsi
0x18009de3e  pop     rbp
0x18009de3f  retn
```
