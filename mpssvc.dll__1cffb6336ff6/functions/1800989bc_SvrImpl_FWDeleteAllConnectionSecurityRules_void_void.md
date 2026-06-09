# SvrImpl_FWDeleteAllConnectionSecurityRules(void *,void *)

- ea: `0x1800989bc`
- end: `0x180098cd0`
- name: `?SvrImpl_FWDeleteAllConnectionSecurityRules@@YAKPEAX0@Z`
- size: `788`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c07b0`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18003e798`
- `0x18005441c`
- `0x180054a90`
- `0x180059384`
- `0x18005c294`
- `0x18006b5d8`
- `0x18006f520`
- `0x1800989bc`
- `0x1800a1868`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098aa6`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180098aa6`
- `fwbase!FwChangeSourceSignal` at `0x180098bfd`
- `fwbase!FwChangeSourceSignal` at `0x180098bfd`
- `fwbase!FwHResultToWindowsError` at `0x180098c05`
- `fwbase!FwHResultToWindowsError` at `0x180098c6a`
- `fwbase!FwHResultToWindowsError` at `0x180098ca9`
- `fwbase!FwHResultToWindowsError` at `0x180098c05`
- `fwbase!FwHResultToWindowsError` at `0x180098c6a`
- `fwbase!FwHResultToWindowsError` at `0x180098ca9`
- `fwbase!FwFree` at `0x180098c96`
- `fwbase!FwFree` at `0x180098ca1`
- `fwbase!FwFree` at `0x180098c96`
- `fwbase!FwFree` at `0x180098ca1`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180098b3f`
- `FWPolicyIOMgr!FwDeleteAllRules` at `0x180098b3f`

## string_xrefs

- `0x180098a24`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x180098a43`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x180098bde`: `SvrImpl_FWDeleteAllConnectionSecurityRules`
- `0x180098bed`: `SvrImpl_FWDeleteAllConnectionSecurityRules`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 267, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v11);
LABEL_36:
      FwUnlockInternal(a1, "SvrImpl_FWDeleteAllConnectionSecurityRules");
      FwReleaseRPCSharedLock((__int64)"SvrImpl_FWDeleteAllConnectionSecurityRules");
      if ( (v8 & 0x80000000) == 0 )
        FwChangeSourceSignal();
      v13 = FwHResultToWindowsError(v8);
      v14 = &qword_1800F5F90;
      v15 = &qword_1800F5F90;
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
            v12 = FwStringTableFind(&dword_18012E020, 23173);
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
0x1800989bc  mov     [rsp+arg_10], rbx
0x1800989c1  push    rbp
0x1800989c2  push    rsi
0x1800989c3  push    rdi
0x1800989c4  push    r12
0x1800989c6  push    r15
0x1800989c8  sub     rsp, 50h
0x1800989cc  mov     rax, cs:__security_cookie
0x1800989d3  xor     rax, rsp
0x1800989d6  mov     [rsp+78h+var_38], rax
0x1800989db  mov     rdi, rdx
0x1800989de  mov     [rsp+78h+var_48], 0
0x1800989e7  mov     rbp, rcx
0x1800989ea  mov     [rsp+78h+var_40], 0
0x1800989f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800989fa  lea     r15, WPP_GLOBAL_Control
0x180098a01  lea     r12, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180098a08  cmp     rcx, r15
0x180098a0b  jz      short loc_180098A24
0x180098a0d  test    byte ptr [rcx+1Ch], 8
0x180098a11  jz      short loc_180098A24
0x180098a13  mov     rcx, [rcx+10h]
0x180098a17  mov     edx, 10Bh
0x180098a1c  mov     r8, r12
0x180098a1f  call    WPP_SF_
0x180098a24  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x180098a2b  call    FwAcquireRPCSharedLock
0x180098a30  test    eax, eax
0x180098a32  js      loc_180098CAF
0x180098a38  call    FwLock
0x180098a3d  mov     ebx, eax
0x180098a3f  test    eax, eax
0x180098a41  jns     short loc_180098A56
0x180098a43  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x180098a4a  call    FwReleaseRPCSharedLock
0x180098a4f  mov     eax, ebx
0x180098a51  jmp     loc_180098CAF
0x180098a56  lea     rdx, [rsp+78h+var_48]
0x180098a5b  mov     rcx, rbp
0x180098a5e  xor     esi, esi
0x180098a60  call    ExtractRPCClientSID
0x180098a65  mov     ebx, eax
0x180098a67  test    eax, eax
0x180098a69  jns     short loc_180098A9E
0x180098a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180098a72  cmp     rcx, r15
0x180098a75  jz      loc_180098BDE
0x180098a7b  test    byte ptr [rcx+1Ch], 1
0x180098a7f  jz      loc_180098BDE
0x180098a85  mov     edx, 10Ch
0x180098a8a  mov     r9d, eax
0x180098a8d  mov     rcx, [rcx+10h]
0x180098a91  mov     r8, r12
0x180098a94  call    WPP_SF_d
0x180098a99  jmp     loc_180098BDE
0x180098a9e  lea     rdx, [rsp+78h+var_40]
0x180098aa3  mov     rcx, rbp
0x180098aa6  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180098aac  mov     r9d, [rdi+18h]
0x180098ab0  cmp     r9d, 2
0x180098ab4  jz      short loc_180098AFF
0x180098ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180098abd  cmp     rcx, r15
0x180098ac0  jz      short loc_180098ADD
0x180098ac2  test    byte ptr [rcx+1Ch], 1
0x180098ac6  jz      short loc_180098ADD
0x180098ac8  mov     rcx, [rcx+10h]
0x180098acc  mov     edx, 10Dh
0x180098ad1  call    WPP_SF_l
0x180098ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180098add  mov     ebx, 80070005h
0x180098ae2  cmp     rcx, r15
0x180098ae5  jz      loc_180098BDE
0x180098aeb  test    byte ptr [rcx+1Ch], 1
0x180098aef  jz      loc_180098BDE
0x180098af5  mov     edx, 10Eh
0x180098afa  mov     r9d, ebx
0x180098afd  jmp     short loc_180098A8D
0x180098aff  mov     esi, [rdi+10h]
0x180098b02  cmp     esi, 2
0x180098b05  jz      short loc_180098B32
0x180098b07  cmp     esi, 5
0x180098b0a  jz      short loc_180098B32
0x180098b0c  mov     ebx, 80070032h
0x180098b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180098b18  cmp     rcx, r15
0x180098b1b  jz      loc_180098BDE
0x180098b21  test    byte ptr [rcx+1Ch], 1
0x180098b25  jz      loc_180098BDE
0x180098b2b  mov     edx, 10Fh
0x180098b30  jmp     short loc_180098AFA
0x180098b32  mov     rcx, [rdi]
0x180098b35  test    rcx, rcx
0x180098b38  jz      short loc_180098B6B
0x180098b3a  mov     edx, 1
0x180098b3f  call    cs:__imp_FwDeleteAllRules
0x180098b45  mov     ebx, eax
0x180098b47  test    eax, eax
0x180098b49  jns     short loc_180098B6B
0x180098b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180098b52  cmp     rcx, r15
0x180098b55  jz      loc_180098BDE
0x180098b5b  test    byte ptr [rcx+1Ch], 1
0x180098b5f  jz      short loc_180098BDE
0x180098b61  mov     edx, 110h
0x180098b66  jmp     loc_180098A8A
0x180098b6b  mov     edx, [rdi+10h]
0x180098b6e  mov     r8d, 1
0x180098b74  mov     rcx, [rdi+8]
0x180098b78  call    FwIncrmDeleteAllRules
0x180098b7d  mov     ebx, eax
0x180098b7f  test    eax, eax
0x180098b81  jns     short loc_180098B9F
0x180098b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180098b8a  cmp     rcx, r15
0x180098b8d  jz      short loc_180098BDE
0x180098b8f  test    byte ptr [rcx+1Ch], 1
0x180098b93  jz      short loc_180098BDE
0x180098b95  mov     edx, 111h
0x180098b9a  jmp     loc_180098A8A
0x180098b9f  mov     edx, 5A85h
0x180098ba4  lea     rcx, dword_18012E020
0x180098bab  call    FwStringTableFind
0x180098bb0  mov     rcx, [rsp+78h+var_48]
0x180098bb5  mov     r9d, 1
0x180098bbb  mov     [rsp+78h+var_50], 0
0x180098bc4  mov     edx, 7FFFFFFFh
0x180098bc9  mov     r8d, r9d
0x180098bcc  mov     [rsp+78h+var_58], rax
0x180098bd1  mov     rcx, [rcx]
0x180098bd4  call    FwAuditLogRuleChange
0x180098bd9  call    FwUpdateConsecPresenceDataPoint
0x180098bde  lea     rdx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x180098be5  mov     rcx, rbp; void *
0x180098be8  call    FwUnlockInternal
0x180098bed  lea     rcx, aSvrimplFwdelet_10; "SvrImpl_FWDeleteAllConnectionSecurityRu"...
0x180098bf4  call    FwReleaseRPCSharedLock
0x180098bf9  test    ebx, ebx
0x180098bfb  js      short loc_180098C03
0x180098bfd  call    cs:__imp_FwChangeSourceSignal
0x180098c03  mov     ecx, ebx
0x180098c05  call    cs:__imp_FwHResultToWindowsError
0x180098c0b  mov     rcx, [rsp+78h+var_40]
0x180098c10  lea     rdi, qword_1800F5F90
0x180098c17  mov     rdx, [rsp+78h+var_48]
0x180098c1c  test    rcx, rcx
0x180098c1f  mov     r8, rdi
0x180098c22  cmovnz  r8, rcx
0x180098c26  test    rdx, rdx
0x180098c29  jz      short loc_180098C30
0x180098c2b  mov     rdx, [rdx]
0x180098c2e  jmp     short loc_180098C37
0x180098c30  lea     rdx, aS100; "S-1-0-0"
0x180098c37  mov     r9d, esi
0x180098c3a  mov     dword ptr [rsp+78h+var_58], eax
0x180098c3e  lea     rcx, WFAllCSRulesDeletedEvent0
0x180098c45  call    ?FwLogBatchUpdate@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBGW4_tag_FW_STORE_TYPE@@K@Z; FwLogBatchUpdate(_EVENT_DESCRIPTOR const *,void *,ushort const *,_tag_FW_STORE_TYPE,ulong)
0x180098c4a  mov     rax, cs:WPP_GLOBAL_Control
0x180098c51  cmp     rax, r15
0x180098c54  jz      short loc_180098C91
0x180098c56  test    byte ptr [rax+1Ch], 4
0x180098c5a  jz      short loc_180098C91
0x180098c5c  mov     rax, [rsp+78h+var_40]
0x180098c61  mov     ecx, ebx
0x180098c63  test    rax, rax
0x180098c66  cmovnz  rdi, rax
0x180098c6a  call    cs:__imp_FwHResultToWindowsError
0x180098c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180098c77  mov     edx, 112h
0x180098c7c  mov     dword ptr [rsp+78h+var_50], esi
0x180098c80  mov     r9d, eax
0x180098c83  mov     [rsp+78h+var_58], rdi
0x180098c88  mov     rcx, [rcx+10h]
0x180098c8c  call    WPP_SF_DSD
0x180098c91  mov     rcx, [rsp+78h+var_48]
0x180098c96  call    cs:__imp_FwFree
0x180098c9c  mov     rcx, [rsp+78h+var_40]
0x180098ca1  call    cs:__imp_FwFree
0x180098ca7  mov     ecx, ebx
0x180098ca9  call    cs:__imp_FwHResultToWindowsError
0x180098caf  mov     rcx, [rsp+78h+var_38]
0x180098cb4  xor     rcx, rsp; StackCookie
0x180098cb7  call    __security_check_cookie
0x180098cbc  mov     rbx, [rsp+78h+arg_10]
0x180098cc4  add     rsp, 50h
0x180098cc8  pop     r15
0x180098cca  pop     r12
0x180098ccc  pop     rdi
0x180098ccd  pop     rsi
0x180098cce  pop     rbp
0x180098ccf  retn
```
