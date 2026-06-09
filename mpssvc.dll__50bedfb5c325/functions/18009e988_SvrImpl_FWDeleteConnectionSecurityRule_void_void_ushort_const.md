# SvrImpl_FWDeleteConnectionSecurityRule(void *,void *,ushort const *)

- ea: `0x18009e988`
- end: `0x18009edb1`
- name: `?SvrImpl_FWDeleteConnectionSecurityRule@@YAKPEAX0PEBG@Z`
- size: `1065`
- prototype: `unsigned int __fastcall(void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c7a10`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x180028474`
- `0x1800288b0`
- `0x18003ec48`
- `0x180059714`
- `0x18005e408`
- `0x180072050`
- `0x1800729c0`
- `0x18009a008`
- `0x18009e988`
- `0x1800a71c8`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009ec8c`
- `fwbase!FwHResultToWindowsError` at `0x18009ed14`
- `fwbase!FwHResultToWindowsError` at `0x18009ed89`
- `fwbase!FwHResultToWindowsError` at `0x18009ec8c`
- `fwbase!FwHResultToWindowsError` at `0x18009ed14`
- `fwbase!FwHResultToWindowsError` at `0x18009ed89`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009ea8b`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009ea8b`
- `fwbase!FwChangeSourceSignal` at `0x18009ec7e`
- `fwbase!FwChangeSourceSignal` at `0x18009ec7e`
- `fwbase!FwStringCopy` at `0x18009ebd1`
- `fwbase!FwStringCopy` at `0x18009ebd1`
- `fwbase!FwFree` at `0x18009ed4b`
- `fwbase!FwFree` at `0x18009ed5b`
- `fwbase!FwFree` at `0x18009ed6b`
- `fwbase!FwFree` at `0x18009ed7b`
- `fwbase!FwFree` at `0x18009ed4b`
- `fwbase!FwFree` at `0x18009ed5b`
- `fwbase!FwFree` at `0x18009ed6b`
- `fwbase!FwFree` at `0x18009ed7b`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009eb60`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009eb60`

## string_xrefs

- `0x18009e9fe`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x18009ea1d`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x18009ec5f`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x18009ec6e`: `SvrImpl_FWDeleteConnectionSecurityRule`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteConnectionSecurityRule(void *a1, _QWORD *a2, unsigned __int16 *a3)
{
  int v3; // r14d
  __int64 result; // rax
  int v8; // ebx
  int RPCClientSID; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  struct _tag_FW_BLOB_CONTAINER *v14; // rax
  struct _tag_FW_BLOB_CONTAINER *v15; // rdi
  char v16; // al
  unsigned __int16 *v17; // rsi
  unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rdx
  wchar_t *v20; // rcx
  unsigned __int16 *v21; // rbx
  int v22; // eax
  int v23; // r8d
  int v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  wchar_t **v26; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v28; // [rsp+60h] [rbp-10h] BYREF

  v3 = 0;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 259, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteConnectionSecurityRule");
  if ( (int)result >= 0 )
  {
    v8 = FwLock();
    if ( v8 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWDeleteConnectionSecurityRule");
      return (unsigned int)v8;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v26);
    v10 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 260;
      goto LABEL_11;
    }
    FwGetRpcCallersProcessImageName(a1, &v27);
    if ( *((_DWORD *)a2 + 6) == 2 )
    {
      if ( *((_DWORD *)a2 + 4) == 2 || *((_DWORD *)a2 + 4) == 5 )
      {
        if ( *a2 )
        {
          FwGetRuleName(*a2, 1, a3, &v25, &v24);
          RPCClientSID = FwDeleteRule(*a2, 1, a3);
          v10 = RPCClientSID;
          if ( RPCClientSID < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 264;
LABEL_11:
            v13 = (unsigned int)RPCClientSID;
LABEL_12:
            WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v13);
LABEL_40:
            FwUnlockInternal(a1, "SvrImpl_FWDeleteConnectionSecurityRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteConnectionSecurityRule");
            if ( (v10 & 0x80000000) == 0 )
              FwChangeSourceSignal();
            v16 = FwHResultToWindowsError(v10);
            v17 = (unsigned __int16 *)&qword_1800FBFF0;
            v18 = (unsigned __int16 *)&qword_1800FBFF0;
            v19 = (unsigned __int16 *)&qword_1800FBFF0;
            if ( v28 )
              v18 = v28;
            if ( !a3 )
              a3 = (unsigned __int16 *)&qword_1800FBFF0;
            if ( v27 )
              v19 = v27;
            if ( v26 )
              v20 = *v26;
            else
              v20 = L"S-1-0-0";
            FwEventCSRuleDeleted(v20, v19, a3, v18, v16);
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v21 = (unsigned __int16 *)&qword_1800FBFF0;
              if ( v28 )
                v21 = v28;
              if ( v27 )
                v17 = v27;
              v22 = FwHResultToWindowsError(v10);
              WPP_SF_DSSS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                266,
                v23,
                v22,
                (__int64)v17,
                (__int64)a3,
                (__int64)v21);
            }
            FwFree(v26);
            FwFree(v27);
            FwFree(v25);
            FwFree(v28);
            return FwHResultToWindowsError(v10);
          }
          v3 = v24;
        }
        if ( !v25 )
        {
          v14 = FwLookForBlobContainerWithID(
                  (struct _tag_FW_BLOB_MANIPULATOR *)&qword_18012A750,
                  (struct _tag_FW_BLOB_REPO *)(a2[1] + 24LL),
                  a3);
          v15 = v14;
          if ( v14 )
          {
            FwStringCopy(*(_QWORD *)(*(_QWORD *)v14 + 24LL), &v25);
            v3 = *(_DWORD *)(*(_QWORD *)v15 + 40LL);
          }
        }
        RPCClientSID = FwIncrmDeleteRule((struct _tag_FW_STORE *)a2[1], &v28, 0);
        v10 = RPCClientSID;
        if ( RPCClientSID >= 0 )
        {
          FwAuditLogRuleChange((unsigned int)*v26, v3, 1, 1, (__int64)a3, v25);
          FwUpdateConsecPresenceDataPoint();
          goto LABEL_40;
        }
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 265;
        goto LABEL_11;
      }
      v10 = -2147024846;
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 263;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 261);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = -2147024891;
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_40;
      v12 = 262;
    }
    v13 = v10;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009e988  push    rbp
0x18009e98a  push    rbx
0x18009e98b  push    rsi
0x18009e98c  push    rdi
0x18009e98d  push    r12
0x18009e98f  push    r14
0x18009e991  push    r15
0x18009e993  mov     rbp, rsp
0x18009e996  sub     rsp, 70h
0x18009e99a  mov     rax, cs:__security_cookie
0x18009e9a1  xor     rax, rsp
0x18009e9a4  mov     [rbp+var_8], rax
0x18009e9a8  xor     r14d, r14d
0x18009e9ab  mov     [rbp+var_20], 0
0x18009e9b3  mov     [rbp+var_30], r14d
0x18009e9b7  mov     r15, r8
0x18009e9ba  mov     [rbp+var_18], r14
0x18009e9be  mov     rsi, rdx
0x18009e9c1  mov     [rbp+var_10], r14
0x18009e9c5  mov     r12, rcx
0x18009e9c8  mov     [rbp+var_28], 0
0x18009e9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e9d7  lea     rax, WPP_GLOBAL_Control
0x18009e9de  cmp     rcx, rax
0x18009e9e1  jz      short loc_18009E9FE
0x18009e9e3  test    byte ptr [rcx+1Ch], 8
0x18009e9e7  jz      short loc_18009E9FE
0x18009e9e9  mov     rcx, [rcx+10h]
0x18009e9ed  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009e9f4  mov     edx, 103h
0x18009e9f9  call    WPP_SF_
0x18009e9fe  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x18009ea05  call    FwAcquireRPCSharedLock
0x18009ea0a  test    eax, eax
0x18009ea0c  js      loc_18009ED95
0x18009ea12  call    FwLock
0x18009ea17  mov     ebx, eax
0x18009ea19  test    eax, eax
0x18009ea1b  jns     short loc_18009EA30
0x18009ea1d  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x18009ea24  call    FwReleaseRPCSharedLock
0x18009ea29  mov     eax, ebx
0x18009ea2b  jmp     loc_18009ED95
0x18009ea30  lea     rdx, [rbp+var_20]
0x18009ea34  mov     rcx, r12
0x18009ea37  call    ExtractRPCClientSID
0x18009ea3c  mov     edi, eax
0x18009ea3e  test    eax, eax
0x18009ea40  jns     short loc_18009EA84
0x18009ea42  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ea49  lea     r14, WPP_GLOBAL_Control
0x18009ea50  cmp     rcx, r14
0x18009ea53  jz      loc_18009EC5F
0x18009ea59  mov     ebx, 1
0x18009ea5e  test    [rcx+1Ch], bl
0x18009ea61  jz      loc_18009EC5F
0x18009ea67  mov     edx, 104h
0x18009ea6c  mov     r9d, eax
0x18009ea6f  mov     rcx, [rcx+10h]
0x18009ea73  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009ea7a  call    WPP_SF_d
0x18009ea7f  jmp     loc_18009EC5F
0x18009ea84  lea     rdx, [rbp+var_18]
0x18009ea88  mov     rcx, r12
0x18009ea8b  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009ea92  nop     dword ptr [rax+rax+00h]
0x18009ea97  mov     r9d, [rsi+18h]
0x18009ea9b  cmp     r9d, 2
0x18009ea9f  jz      short loc_18009EAF7
0x18009eaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eaa8  lea     r14, WPP_GLOBAL_Control
0x18009eaaf  mov     ebx, 1
0x18009eab4  cmp     rcx, r14
0x18009eab7  jz      short loc_18009EAD3
0x18009eab9  test    [rcx+1Ch], bl
0x18009eabc  jz      short loc_18009EAD3
0x18009eabe  mov     rcx, [rcx+10h]
0x18009eac2  mov     edx, 105h
0x18009eac7  call    WPP_SF_l
0x18009eacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ead3  mov     edi, 80070005h
0x18009ead8  cmp     rcx, r14
0x18009eadb  jz      loc_18009EC5F
0x18009eae1  test    [rcx+1Ch], bl
0x18009eae4  jz      loc_18009EC5F
0x18009eaea  mov     edx, 106h
0x18009eaef  mov     r9d, edi
0x18009eaf2  jmp     loc_18009EA6F
0x18009eaf7  cmp     dword ptr [rsi+10h], 2
0x18009eafb  jz      short loc_18009EB34
0x18009eafd  cmp     dword ptr [rsi+10h], 5
0x18009eb01  jz      short loc_18009EB34
0x18009eb03  mov     edi, 80070032h
0x18009eb08  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eb0f  lea     r14, WPP_GLOBAL_Control
0x18009eb16  cmp     rcx, r14
0x18009eb19  jz      loc_18009EC5F
0x18009eb1f  mov     ebx, 1
0x18009eb24  test    [rcx+1Ch], bl
0x18009eb27  jz      loc_18009EC5F
0x18009eb2d  mov     edx, 107h
0x18009eb32  jmp     short loc_18009EAEF
0x18009eb34  mov     rcx, [rsi]
0x18009eb37  mov     ebx, 1
0x18009eb3c  test    rcx, rcx
0x18009eb3f  jz      short loc_18009EBA0
0x18009eb41  lea     rax, [rbp+var_30]
0x18009eb45  mov     r8, r15
0x18009eb48  lea     r9, [rbp+var_28]
0x18009eb4c  mov     [rsp+70h+var_50], rax
0x18009eb51  mov     edx, ebx
0x18009eb53  call    ?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z; FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)
0x18009eb58  mov     rcx, [rsi]
0x18009eb5b  mov     r8, r15
0x18009eb5e  mov     edx, ebx
0x18009eb60  call    cs:__imp_FwDeleteRule
0x18009eb67  nop     dword ptr [rax+rax+00h]
0x18009eb6c  mov     edi, eax
0x18009eb6e  test    eax, eax
0x18009eb70  jns     short loc_18009EB9C
0x18009eb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eb79  lea     r14, WPP_GLOBAL_Control
0x18009eb80  cmp     rcx, r14
0x18009eb83  jz      loc_18009EC5F
0x18009eb89  test    [rcx+1Ch], bl
0x18009eb8c  jz      loc_18009EC5F
0x18009eb92  mov     edx, 108h
0x18009eb97  jmp     loc_18009EA6C
0x18009eb9c  mov     r14d, [rbp+var_30]
0x18009eba0  cmp     [rbp+var_28], 0
0x18009eba5  jnz     short loc_18009EBE4
0x18009eba7  mov     rdx, [rsi+8]
0x18009ebab  lea     rcx, qword_18012A750; struct _tag_FW_BLOB_MANIPULATOR *
0x18009ebb2  add     rdx, 18h; struct _tag_FW_BLOB_REPO *
0x18009ebb6  mov     r8, r15; unsigned __int16 *
0x18009ebb9  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009ebbe  mov     rdi, rax
0x18009ebc1  test    rax, rax
0x18009ebc4  jz      short loc_18009EBE4
0x18009ebc6  mov     rcx, [rax]
0x18009ebc9  lea     rdx, [rbp+var_28]
0x18009ebcd  mov     rcx, [rcx+18h]
0x18009ebd1  call    cs:__imp_FwStringCopy
0x18009ebd8  nop     dword ptr [rax+rax+00h]
0x18009ebdd  mov     rax, [rdi]
0x18009ebe0  mov     r14d, [rax+28h]
0x18009ebe4  mov     edx, [rsi+10h]
0x18009ebe7  lea     rax, [rbp+var_10]
0x18009ebeb  mov     rcx, [rsi+8]; struct _tag_FW_STORE *
0x18009ebef  mov     r9, r15
0x18009ebf2  mov     [rsp+70h+var_48], 0; __int64
0x18009ebfb  mov     r8d, ebx
0x18009ebfe  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18009ec03  call    FwIncrmDeleteRule
0x18009ec08  mov     edi, eax
0x18009ec0a  test    eax, eax
0x18009ec0c  jns     short loc_18009EC30
0x18009ec0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ec15  lea     r14, WPP_GLOBAL_Control
0x18009ec1c  cmp     rcx, r14
0x18009ec1f  jz      short loc_18009EC5F
0x18009ec21  test    [rcx+1Ch], bl
0x18009ec24  jz      short loc_18009EC5F
0x18009ec26  mov     edx, 109h
0x18009ec2b  jmp     loc_18009EA6C
0x18009ec30  mov     rcx, [rbp+var_20]
0x18009ec34  mov     r9d, ebx
0x18009ec37  mov     rax, [rbp+var_28]
0x18009ec3b  mov     r8d, ebx
0x18009ec3e  mov     [rsp+70h+var_48], rax
0x18009ec43  mov     edx, r14d
0x18009ec46  mov     [rsp+70h+var_50], r15
0x18009ec4b  mov     rcx, [rcx]
0x18009ec4e  call    FwAuditLogRuleChange
0x18009ec53  call    FwUpdateConsecPresenceDataPoint
0x18009ec58  lea     r14, WPP_GLOBAL_Control
0x18009ec5f  lea     rdx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x18009ec66  mov     rcx, r12; void *
0x18009ec69  call    FwUnlockInternal
0x18009ec6e  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x18009ec75  call    FwReleaseRPCSharedLock
0x18009ec7a  test    edi, edi
0x18009ec7c  js      short loc_18009EC8A
0x18009ec7e  call    cs:__imp_FwChangeSourceSignal
0x18009ec85  nop     dword ptr [rax+rax+00h]
0x18009ec8a  mov     ecx, edi
0x18009ec8c  call    cs:__imp_FwHResultToWindowsError
0x18009ec93  nop     dword ptr [rax+rax+00h]
0x18009ec98  mov     rcx, [rbp+var_10]
0x18009ec9c  lea     rsi, qword_1800FBFF0
0x18009eca3  test    rcx, rcx
0x18009eca6  mov     r9, rsi
0x18009eca9  mov     r8d, eax
0x18009ecac  mov     rdx, rsi
0x18009ecaf  mov     rax, [rbp+var_18]
0x18009ecb3  cmovnz  r9, rcx; unsigned __int16 *
0x18009ecb7  mov     rcx, [rbp+var_20]
0x18009ecbb  test    r15, r15
0x18009ecbe  cmovz   r15, rsi
0x18009ecc2  test    rax, rax
0x18009ecc5  cmovnz  rdx, rax; unsigned __int16 *
0x18009ecc9  test    rcx, rcx
0x18009eccc  jz      short loc_18009ECD3
0x18009ecce  mov     rcx, [rcx]
0x18009ecd1  jmp     short loc_18009ECDA
0x18009ecd3  lea     rcx, aS100; "S-1-0-0"
0x18009ecda  mov     dword ptr [rsp+70h+var_50], r8d; char
0x18009ecdf  mov     r8, r15; unsigned __int16 *
0x18009ece2  call    FwEventCSRuleDeleted
0x18009ece7  mov     rax, cs:WPP_GLOBAL_Control
0x18009ecee  cmp     rax, r14
0x18009ecf1  jz      short loc_18009ED47
0x18009ecf3  test    byte ptr [rax+1Ch], 4
0x18009ecf7  jz      short loc_18009ED47
0x18009ecf9  mov     rax, [rbp+var_10]
0x18009ecfd  mov     rbx, rsi
0x18009ed00  test    rax, rax
0x18009ed03  mov     ecx, edi
0x18009ed05  cmovnz  rbx, rax
0x18009ed09  mov     rax, [rbp+var_18]
0x18009ed0d  test    rax, rax
0x18009ed10  cmovnz  rsi, rax
0x18009ed14  call    cs:__imp_FwHResultToWindowsError
0x18009ed1b  nop     dword ptr [rax+rax+00h]
0x18009ed20  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ed27  mov     edx, 10Ah
0x18009ed2c  mov     [rsp+70h+var_40], rbx
0x18009ed31  mov     r9d, eax
0x18009ed34  mov     [rsp+70h+var_48], r15
0x18009ed39  mov     [rsp+70h+var_50], rsi
0x18009ed3e  mov     rcx, [rcx+10h]
0x18009ed42  call    WPP_SF_DSSS
0x18009ed47  mov     rcx, [rbp+var_20]
0x18009ed4b  call    cs:__imp_FwFree
0x18009ed52  nop     dword ptr [rax+rax+00h]
0x18009ed57  mov     rcx, [rbp+var_18]
0x18009ed5b  call    cs:__imp_FwFree
0x18009ed62  nop     dword ptr [rax+rax+00h]
0x18009ed67  mov     rcx, [rbp+var_28]
0x18009ed6b  call    cs:__imp_FwFree
0x18009ed72  nop     dword ptr [rax+rax+00h]
0x18009ed77  mov     rcx, [rbp+var_10]
0x18009ed7b  call    cs:__imp_FwFree
0x18009ed82  nop     dword ptr [rax+rax+00h]
0x18009ed87  mov     ecx, edi
0x18009ed89  call    cs:__imp_FwHResultToWindowsError
0x18009ed90  nop     dword ptr [rax+rax+00h]
0x18009ed95  mov     rcx, [rbp+var_8]
0x18009ed99  xor     rcx, rsp; StackCookie
0x18009ed9c  call    __security_check_cookie
0x18009eda1  add     rsp, 70h
0x18009eda5  pop     r15
0x18009eda7  pop     r14
0x18009eda9  pop     r12
0x18009edab  pop     rdi
0x18009edac  pop     rsi
0x18009edad  pop     rbx
0x18009edae  pop     rbp
0x18009edaf  retn
```
