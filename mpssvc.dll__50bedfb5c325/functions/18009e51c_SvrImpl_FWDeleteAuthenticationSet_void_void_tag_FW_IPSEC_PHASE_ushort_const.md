# SvrImpl_FWDeleteAuthenticationSet(void *,void *,_tag_FW_IPSEC_PHASE,ushort const *)

- ea: `0x18009e51c`
- end: `0x18009e981`
- name: `?SvrImpl_FWDeleteAuthenticationSet@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@PEBG@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c7930`

## callees

- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x1800288b0`
- `0x18003ec48`
- `0x180059714`
- `0x1800729c0`
- `0x18008cc98`
- `0x18008eb78`
- `0x18008f7ac`
- `0x18009a1e0`
- `0x18009e51c`
- `0x1800a7300`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009e83b`
- `fwbase!FwHResultToWindowsError` at `0x18009e8df`
- `fwbase!FwHResultToWindowsError` at `0x18009e959`
- `fwbase!FwHResultToWindowsError` at `0x18009e83b`
- `fwbase!FwHResultToWindowsError` at `0x18009e8df`
- `fwbase!FwHResultToWindowsError` at `0x18009e959`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009e618`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009e618`
- `fwbase!FwResolveIndirectString` at `0x18009e802`
- `fwbase!FwResolveIndirectString` at `0x18009e802`
- `fwbase!FwChangeSourceSignal` at `0x18009e82d`
- `fwbase!FwChangeSourceSignal` at `0x18009e82d`
- `fwbase!FwStringCopy` at `0x18009e779`
- `fwbase!FwStringCopy` at `0x18009e779`
- `fwbase!FwFree` at `0x18009e91b`
- `fwbase!FwFree` at `0x18009e92b`
- `fwbase!FwFree` at `0x18009e93b`
- `fwbase!FwFree` at `0x18009e94b`
- `fwbase!FwFree` at `0x18009e91b`
- `fwbase!FwFree` at `0x18009e92b`
- `fwbase!FwFree` at `0x18009e93b`
- `fwbase!FwFree` at `0x18009e94b`
- `FWPolicyIOMgr!FwDeleteSet` at `0x18009e70d`
- `FWPolicyIOMgr!FwDeleteSet` at `0x18009e70d`

## string_xrefs

- `0x18009e596`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x18009e5b5`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x18009e80e`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x18009e81d`: `SvrImpl_FWDeleteAuthenticationSet`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteAuthenticationSet(void *a1, __int64 a2, int a3, const unsigned __int16 *a4)
{
  __int64 v5; // r15
  __int64 result; // rax
  int v9; // ebx
  int RPCClientSID; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  struct _tag_FW_BLOB_CONTAINER *v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rcx
  const unsigned __int16 *v18; // rdi
  const unsigned __int16 *v19; // r8
  const wchar_t *v20; // rdx
  const unsigned __int16 *v21; // rsi
  int v22; // eax
  int v23; // r8d
  const unsigned __int16 *v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  const wchar_t **v26; // [rsp+50h] [rbp-20h] BYREF
  const unsigned __int16 *v27; // [rsp+58h] [rbp-18h] BYREF

  v5 = a3;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  v25 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 297, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteAuthenticationSet");
  if ( (int)result >= 0 )
  {
    v9 = FwLock();
    if ( v9 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWDeleteAuthenticationSet");
      return (unsigned int)v9;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v26);
    v11 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_45;
      v13 = 298;
LABEL_11:
      v14 = (unsigned int)RPCClientSID;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v14);
      goto LABEL_45;
    }
    FwGetRpcCallersProcessImageName(a1, &v27);
    if ( *(_DWORD *)(a2 + 24) == 2 )
    {
      if ( *(_DWORD *)(a2 + 16) == 2 || *(_DWORD *)(a2 + 16) == 5 )
      {
        if ( !(unsigned int)FwSetIsInUse(*(_QWORD *)(a2 + 8), 0, (unsigned int)v5, a4) )
        {
          if ( *(_QWORD *)a2
            && (FwGetSetName(*(_QWORD *)a2, 0, (unsigned int)v5, a4, &v24),
                RPCClientSID = FwDeleteSet(*(_QWORD *)a2, 0, (unsigned int)v5, a4),
                v11 = RPCClientSID,
                RPCClientSID < 0) )
          {
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_45;
            }
            v13 = 303;
          }
          else
          {
            if ( !v24 )
            {
              v15 = FwLookForBlobContainerWithID(
                      (struct _tag_FW_BLOB_MANIPULATOR *)&qword_18012A7B0,
                      (struct _tag_FW_BLOB_REPO *)(*(_QWORD *)(a2 + 8) + 24 * (v5 + 4)),
                      a4);
              if ( v15 )
                FwStringCopy(*(_QWORD *)(*(_QWORD *)v15 + 24LL), &v24);
            }
            RPCClientSID = FwIncrmDeleteSet(*(_QWORD *)(a2 + 8), *(_DWORD *)(a2 + 16), 0, v5, a4, (__int64)&v25);
            v11 = RPCClientSID;
            if ( RPCClientSID >= 0 )
            {
              FwAuditLogRuleChange((unsigned int)*v26, 0x7FFFFFFF, 4, 1, (__int64)a4, (__int64)v24);
              if ( !v25 && v24 )
                FwResolveIndirectString(&v24);
              goto LABEL_45;
            }
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
LABEL_45:
              FwUnlockInternal(a1, "SvrImpl_FWDeleteAuthenticationSet");
              FwReleaseRPCSharedLock("SvrImpl_FWDeleteAuthenticationSet");
              if ( (v11 & 0x80000000) == 0 )
                FwChangeSourceSignal();
              v16 = FwHResultToWindowsError(v11);
              v17 = (const unsigned __int16 *)v25;
              v18 = &qword_1800FBFF0;
              if ( !v25 )
              {
                v17 = &qword_1800FBFF0;
                if ( v24 )
                  v17 = v24;
              }
              v19 = &qword_1800FBFF0;
              if ( !a4 )
                a4 = &qword_1800FBFF0;
              if ( v27 )
                v19 = v27;
              if ( v26 )
                v20 = *v26;
              else
                v20 = L"S-1-0-0";
              FwLogAuthenticationSetDeleted(v17, v20, v19, a4, v17, v5, v16);
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                v21 = (const unsigned __int16 *)v25;
                if ( !v25 )
                {
                  v21 = &qword_1800FBFF0;
                  if ( v24 )
                    v21 = v24;
                }
                if ( v27 )
                  v18 = v27;
                v22 = FwHResultToWindowsError(v11);
                WPP_SF_DSSSD(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  305,
                  v23,
                  v22,
                  (__int64)v18,
                  (__int64)a4,
                  (__int64)v21,
                  v5);
              }
              FwFree(v26);
              FwFree(v24);
              FwFree(v25);
              FwFree(v27);
              return FwHResultToWindowsError(v11);
            }
            v13 = 304;
          }
          goto LABEL_11;
        }
        v11 = -2147022494;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_45;
        v13 = 302;
      }
      else
      {
        v11 = -2147024846;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_45;
        v13 = 301;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 299);
        v12 = WPP_GLOBAL_Control;
      }
      v11 = -2147024891;
      if ( (_UNKNOWN *)v12 == &WPP_GLOBAL_Control || (*(_BYTE *)(v12 + 28) & 1) == 0 )
        goto LABEL_45;
      v13 = 300;
    }
    v14 = v11;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009e51c  push    rbp
0x18009e51e  push    rbx
0x18009e51f  push    rsi
0x18009e520  push    rdi
0x18009e521  push    r13
0x18009e523  push    r14
0x18009e525  push    r15
0x18009e527  mov     rbp, rsp
0x18009e52a  sub     rsp, 70h
0x18009e52e  mov     rax, cs:__security_cookie
0x18009e535  xor     rax, rsp
0x18009e538  mov     [rbp+var_10], rax
0x18009e53c  mov     r14, r9
0x18009e53f  movsxd  r15, r8d
0x18009e542  mov     rdi, rdx
0x18009e545  mov     [rbp+var_20], 0
0x18009e54d  mov     rsi, rcx
0x18009e550  mov     [rbp+var_30], 0
0x18009e558  mov     [rbp+var_18], 0
0x18009e560  mov     [rbp+var_28], 0
0x18009e568  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e56f  lea     r13, WPP_GLOBAL_Control
0x18009e576  cmp     rcx, r13
0x18009e579  jz      short loc_18009E596
0x18009e57b  test    byte ptr [rcx+1Ch], 8
0x18009e57f  jz      short loc_18009E596
0x18009e581  mov     rcx, [rcx+10h]
0x18009e585  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009e58c  mov     edx, 129h
0x18009e591  call    WPP_SF_
0x18009e596  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009e59d  call    FwAcquireRPCSharedLock
0x18009e5a2  test    eax, eax
0x18009e5a4  js      loc_18009E965
0x18009e5aa  call    FwLock
0x18009e5af  mov     ebx, eax
0x18009e5b1  test    eax, eax
0x18009e5b3  jns     short loc_18009E5C8
0x18009e5b5  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009e5bc  call    FwReleaseRPCSharedLock
0x18009e5c1  mov     eax, ebx
0x18009e5c3  jmp     loc_18009E965
0x18009e5c8  lea     rdx, [rbp+var_20]
0x18009e5cc  mov     rcx, rsi
0x18009e5cf  call    ExtractRPCClientSID
0x18009e5d4  mov     ebx, eax
0x18009e5d6  test    eax, eax
0x18009e5d8  jns     short loc_18009E611
0x18009e5da  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e5e1  cmp     rcx, r13
0x18009e5e4  jz      loc_18009E80E
0x18009e5ea  test    byte ptr [rcx+1Ch], 1
0x18009e5ee  jz      loc_18009E80E
0x18009e5f4  mov     edx, 12Ah
0x18009e5f9  mov     r9d, eax
0x18009e5fc  mov     rcx, [rcx+10h]
0x18009e600  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009e607  call    WPP_SF_d
0x18009e60c  jmp     loc_18009E80E
0x18009e611  lea     rdx, [rbp+var_18]
0x18009e615  mov     rcx, rsi
0x18009e618  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009e61f  nop     dword ptr [rax+rax+00h]
0x18009e624  mov     r9d, [rdi+18h]
0x18009e628  cmp     r9d, 2
0x18009e62c  jz      short loc_18009E677
0x18009e62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e635  cmp     rcx, r13
0x18009e638  jz      short loc_18009E655
0x18009e63a  test    byte ptr [rcx+1Ch], 1
0x18009e63e  jz      short loc_18009E655
0x18009e640  mov     rcx, [rcx+10h]
0x18009e644  mov     edx, 12Bh
0x18009e649  call    WPP_SF_l
0x18009e64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e655  mov     ebx, 80070005h
0x18009e65a  cmp     rcx, r13
0x18009e65d  jz      loc_18009E80E
0x18009e663  test    byte ptr [rcx+1Ch], 1
0x18009e667  jz      loc_18009E80E
0x18009e66d  mov     edx, 12Ch
0x18009e672  mov     r9d, ebx
0x18009e675  jmp     short loc_18009E5FC
0x18009e677  cmp     dword ptr [rdi+10h], 2
0x18009e67b  jz      short loc_18009E6A9
0x18009e67d  cmp     dword ptr [rdi+10h], 5
0x18009e681  jz      short loc_18009E6A9
0x18009e683  mov     ebx, 80070032h
0x18009e688  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e68f  cmp     rcx, r13
0x18009e692  jz      loc_18009E80E
0x18009e698  test    byte ptr [rcx+1Ch], 1
0x18009e69c  jz      loc_18009E80E
0x18009e6a2  mov     edx, 12Dh
0x18009e6a7  jmp     short loc_18009E672
0x18009e6a9  mov     rcx, [rdi+8]
0x18009e6ad  mov     r9, r14
0x18009e6b0  mov     r8d, r15d
0x18009e6b3  xor     edx, edx
0x18009e6b5  call    FwSetIsInUse
0x18009e6ba  test    eax, eax
0x18009e6bc  jz      short loc_18009E6E4
0x18009e6be  mov     ebx, 80070962h
0x18009e6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e6ca  cmp     rcx, r13
0x18009e6cd  jz      loc_18009E80E
0x18009e6d3  test    byte ptr [rcx+1Ch], 1
0x18009e6d7  jz      loc_18009E80E
0x18009e6dd  mov     edx, 12Eh
0x18009e6e2  jmp     short loc_18009E672
0x18009e6e4  mov     rcx, [rdi]
0x18009e6e7  test    rcx, rcx
0x18009e6ea  jz      short loc_18009E743
0x18009e6ec  lea     rax, [rbp+var_30]
0x18009e6f0  mov     r9, r14
0x18009e6f3  mov     r8d, r15d
0x18009e6f6  mov     [rsp+70h+lpString2], rax
0x18009e6fb  xor     edx, edx
0x18009e6fd  call    ?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z; FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)
0x18009e702  mov     rcx, [rdi]
0x18009e705  mov     r9, r14
0x18009e708  mov     r8d, r15d
0x18009e70b  xor     edx, edx
0x18009e70d  call    cs:__imp_FwDeleteSet
0x18009e714  nop     dword ptr [rax+rax+00h]
0x18009e719  mov     ebx, eax
0x18009e71b  test    eax, eax
0x18009e71d  jns     short loc_18009E743
0x18009e71f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e726  cmp     rcx, r13
0x18009e729  jz      loc_18009E80E
0x18009e72f  test    byte ptr [rcx+1Ch], 1
0x18009e733  jz      loc_18009E80E
0x18009e739  mov     edx, 12Fh
0x18009e73e  jmp     loc_18009E5F9
0x18009e743  cmp     [rbp+var_30], 0
0x18009e748  jnz     short loc_18009E785
0x18009e74a  lea     rax, [r15+4]
0x18009e74e  mov     r8, r14; unsigned __int16 *
0x18009e751  lea     rcx, [rax+rax*2]
0x18009e755  mov     rax, [rdi+8]
0x18009e759  lea     rdx, [rax+rcx*8]; struct _tag_FW_BLOB_REPO *
0x18009e75d  lea     rcx, qword_18012A7B0; struct _tag_FW_BLOB_MANIPULATOR *
0x18009e764  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009e769  test    rax, rax
0x18009e76c  jz      short loc_18009E785
0x18009e76e  mov     rcx, [rax]
0x18009e771  lea     rdx, [rbp+var_30]
0x18009e775  mov     rcx, [rcx+18h]
0x18009e779  call    cs:__imp_FwStringCopy
0x18009e780  nop     dword ptr [rax+rax+00h]
0x18009e785  mov     edx, [rdi+10h]; int
0x18009e788  lea     rax, [rbp+var_28]
0x18009e78c  mov     rcx, [rdi+8]; int
0x18009e790  mov     r9d, r15d; int
0x18009e793  mov     [rsp+70h+var_48], rax; __int64
0x18009e798  xor     r8d, r8d; int
0x18009e79b  mov     [rsp+70h+lpString2], r14; lpString2
0x18009e7a0  call    FwIncrmDeleteSet
0x18009e7a5  mov     ebx, eax
0x18009e7a7  test    eax, eax
0x18009e7a9  jns     short loc_18009E7C7
0x18009e7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e7b2  cmp     rcx, r13
0x18009e7b5  jz      short loc_18009E80E
0x18009e7b7  test    byte ptr [rcx+1Ch], 1
0x18009e7bb  jz      short loc_18009E80E
0x18009e7bd  mov     edx, 130h
0x18009e7c2  jmp     loc_18009E5F9
0x18009e7c7  mov     rcx, [rbp+var_20]
0x18009e7cb  mov     r9d, 1
0x18009e7d1  mov     rax, [rbp+var_30]
0x18009e7d5  mov     edx, 7FFFFFFFh
0x18009e7da  mov     [rsp+70h+var_48], rax
0x18009e7df  mov     [rsp+70h+lpString2], r14
0x18009e7e4  mov     rcx, [rcx]
0x18009e7e7  lea     r8d, [r9+3]
0x18009e7eb  call    FwAuditLogRuleChange
0x18009e7f0  cmp     [rbp+var_28], 0
0x18009e7f5  jnz     short loc_18009E80E
0x18009e7f7  cmp     [rbp+var_30], 0
0x18009e7fc  jz      short loc_18009E80E
0x18009e7fe  lea     rcx, [rbp+var_30]
0x18009e802  call    cs:__imp_FwResolveIndirectString
0x18009e809  nop     dword ptr [rax+rax+00h]
0x18009e80e  lea     rdx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009e815  mov     rcx, rsi; void *
0x18009e818  call    FwUnlockInternal
0x18009e81d  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009e824  call    FwReleaseRPCSharedLock
0x18009e829  test    ebx, ebx
0x18009e82b  js      short loc_18009E839
0x18009e82d  call    cs:__imp_FwChangeSourceSignal
0x18009e834  nop     dword ptr [rax+rax+00h]
0x18009e839  mov     ecx, ebx
0x18009e83b  call    cs:__imp_FwHResultToWindowsError
0x18009e842  nop     dword ptr [rax+rax+00h]
0x18009e847  mov     rcx, [rbp+var_28]
0x18009e84b  lea     rdi, qword_1800FBFF0
0x18009e852  mov     r9d, eax
0x18009e855  test    rcx, rcx
0x18009e858  jnz     short loc_18009E868
0x18009e85a  mov     rax, [rbp+var_30]
0x18009e85e  mov     rcx, rdi
0x18009e861  test    rax, rax
0x18009e864  cmovnz  rcx, rax
0x18009e868  mov     rax, [rbp+var_18]
0x18009e86c  test    r14, r14
0x18009e86f  mov     rdx, [rbp+var_20]
0x18009e873  mov     r8, rdi
0x18009e876  cmovz   r14, rdi
0x18009e87a  test    rax, rax
0x18009e87d  cmovnz  r8, rax
0x18009e881  test    rdx, rdx
0x18009e884  jz      short loc_18009E88B
0x18009e886  mov     rdx, [rdx]
0x18009e889  jmp     short loc_18009E892
0x18009e88b  lea     rdx, aS100; "S-1-0-0"
0x18009e892  mov     dword ptr [rsp+70h+var_40], r9d
0x18009e897  mov     r9, r14
0x18009e89a  mov     dword ptr [rsp+70h+var_48], r15d
0x18009e89f  mov     [rsp+70h+lpString2], rcx
0x18009e8a4  call    ?FwLogAuthenticationSetDeleted@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBG22W4_tag_FW_IPSEC_PHASE@@K@Z; FwLogAuthenticationSetDeleted(_EVENT_DESCRIPTOR const *,void *,ushort const *,ushort const *,ushort const *,_tag_FW_IPSEC_PHASE,ulong)
0x18009e8a9  mov     rax, cs:WPP_GLOBAL_Control
0x18009e8b0  cmp     rax, r13
0x18009e8b3  jz      short loc_18009E917
0x18009e8b5  test    byte ptr [rax+1Ch], 4
0x18009e8b9  jz      short loc_18009E917
0x18009e8bb  mov     rsi, [rbp+var_28]
0x18009e8bf  test    rsi, rsi
0x18009e8c2  jnz     short loc_18009E8D2
0x18009e8c4  mov     rax, [rbp+var_30]
0x18009e8c8  mov     rsi, rdi
0x18009e8cb  test    rax, rax
0x18009e8ce  cmovnz  rsi, rax
0x18009e8d2  mov     rax, [rbp+var_18]
0x18009e8d6  mov     ecx, ebx
0x18009e8d8  test    rax, rax
0x18009e8db  cmovnz  rdi, rax
0x18009e8df  call    cs:__imp_FwHResultToWindowsError
0x18009e8e6  nop     dword ptr [rax+rax+00h]
0x18009e8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e8f2  mov     edx, 131h
0x18009e8f7  mov     [rsp+70h+var_38], r15d
0x18009e8fc  mov     r9d, eax
0x18009e8ff  mov     [rsp+70h+var_40], rsi
0x18009e904  mov     [rsp+70h+var_48], r14
0x18009e909  mov     rcx, [rcx+10h]
0x18009e90d  mov     [rsp+70h+lpString2], rdi
0x18009e912  call    WPP_SF_DSSSD
0x18009e917  mov     rcx, [rbp+var_20]
0x18009e91b  call    cs:__imp_FwFree
0x18009e922  nop     dword ptr [rax+rax+00h]
0x18009e927  mov     rcx, [rbp+var_30]
0x18009e92b  call    cs:__imp_FwFree
0x18009e932  nop     dword ptr [rax+rax+00h]
0x18009e937  mov     rcx, [rbp+var_28]
0x18009e93b  call    cs:__imp_FwFree
0x18009e942  nop     dword ptr [rax+rax+00h]
0x18009e947  mov     rcx, [rbp+var_18]
0x18009e94b  call    cs:__imp_FwFree
0x18009e952  nop     dword ptr [rax+rax+00h]
0x18009e957  mov     ecx, ebx
0x18009e959  call    cs:__imp_FwHResultToWindowsError
0x18009e960  nop     dword ptr [rax+rax+00h]
0x18009e965  mov     rcx, [rbp+var_10]
0x18009e969  xor     rcx, rsp; StackCookie
0x18009e96c  call    __security_check_cookie
0x18009e971  add     rsp, 70h
0x18009e975  pop     r15
0x18009e977  pop     r14
0x18009e979  pop     r13
0x18009e97b  pop     rdi
0x18009e97c  pop     rsi
0x18009e97d  pop     rbx
0x18009e97e  pop     rbp
0x18009e97f  retn
```
