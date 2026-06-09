# SvrImpl_FWDeleteConnectionSecurityRule(void *,void *,ushort const *)

- ea: `0x180099770`
- end: `0x180099b53`
- name: `?SvrImpl_FWDeleteConnectionSecurityRule@@YAKPEAX0PEBG@Z`
- size: `995`
- prototype: `unsigned int __fastcall(void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c0b80`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180025ed0`
- `0x180026310`
- `0x18003e798`
- `0x18005441c`
- `0x180059384`
- `0x18006ebe8`
- `0x18006f520`
- `0x180095170`
- `0x180099770`
- `0x1800a1a18`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099873`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099873`
- `fwbase!FwChangeSourceSignal` at `0x180099a51`
- `fwbase!FwChangeSourceSignal` at `0x180099a51`
- `fwbase!FwHResultToWindowsError` at `0x180099a59`
- `fwbase!FwHResultToWindowsError` at `0x180099adb`
- `fwbase!FwHResultToWindowsError` at `0x180099b32`
- `fwbase!FwHResultToWindowsError` at `0x180099a59`
- `fwbase!FwHResultToWindowsError` at `0x180099adb`
- `fwbase!FwHResultToWindowsError` at `0x180099b32`
- `fwbase!FwStringCopy` at `0x1800999aa`
- `fwbase!FwStringCopy` at `0x1800999aa`
- `fwbase!FwFree` at `0x180099b0c`
- `fwbase!FwFree` at `0x180099b16`
- `fwbase!FwFree` at `0x180099b20`
- `fwbase!FwFree` at `0x180099b2a`
- `fwbase!FwFree` at `0x180099b0c`
- `fwbase!FwFree` at `0x180099b16`
- `fwbase!FwFree` at `0x180099b20`
- `fwbase!FwFree` at `0x180099b2a`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009993f`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009993f`

## string_xrefs

- `0x1800997e6`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x180099805`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x180099a32`: `SvrImpl_FWDeleteConnectionSecurityRule`
- `0x180099a41`: `SvrImpl_FWDeleteConnectionSecurityRule`

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
  unsigned int v16; // eax
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 259, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
            WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v13);
LABEL_40:
            FwUnlockInternal(a1, "SvrImpl_FWDeleteConnectionSecurityRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteConnectionSecurityRule");
            if ( (v10 & 0x80000000) == 0 )
              FwChangeSourceSignal();
            v16 = FwHResultToWindowsError(v10);
            v17 = (unsigned __int16 *)&qword_1800F5F90;
            v18 = (unsigned __int16 *)&qword_1800F5F90;
            v19 = (unsigned __int16 *)&qword_1800F5F90;
            if ( v28 )
              v18 = v28;
            if ( !a3 )
              a3 = (unsigned __int16 *)&qword_1800F5F90;
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
              v21 = (unsigned __int16 *)&qword_1800F5F90;
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
                  (struct _tag_FW_BLOB_MANIPULATOR *)&qword_180124750,
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
0x180099770  push    rbp
0x180099772  push    rbx
0x180099773  push    rsi
0x180099774  push    rdi
0x180099775  push    r12
0x180099777  push    r14
0x180099779  push    r15
0x18009977b  mov     rbp, rsp
0x18009977e  sub     rsp, 70h
0x180099782  mov     rax, cs:__security_cookie
0x180099789  xor     rax, rsp
0x18009978c  mov     [rbp+var_8], rax
0x180099790  xor     r14d, r14d
0x180099793  mov     [rbp+var_20], 0
0x18009979b  mov     [rbp+var_30], r14d
0x18009979f  mov     r15, r8
0x1800997a2  mov     [rbp+var_18], r14
0x1800997a6  mov     rsi, rdx
0x1800997a9  mov     [rbp+var_10], r14
0x1800997ad  mov     r12, rcx
0x1800997b0  mov     [rbp+var_28], 0
0x1800997b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800997bf  lea     rax, WPP_GLOBAL_Control
0x1800997c6  cmp     rcx, rax
0x1800997c9  jz      short loc_1800997E6
0x1800997cb  test    byte ptr [rcx+1Ch], 8
0x1800997cf  jz      short loc_1800997E6
0x1800997d1  mov     rcx, [rcx+10h]
0x1800997d5  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800997dc  mov     edx, 103h
0x1800997e1  call    WPP_SF_
0x1800997e6  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x1800997ed  call    FwAcquireRPCSharedLock
0x1800997f2  test    eax, eax
0x1800997f4  js      loc_180099B38
0x1800997fa  call    FwLock
0x1800997ff  mov     ebx, eax
0x180099801  test    eax, eax
0x180099803  jns     short loc_180099818
0x180099805  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x18009980c  call    FwReleaseRPCSharedLock
0x180099811  mov     eax, ebx
0x180099813  jmp     loc_180099B38
0x180099818  lea     rdx, [rbp+var_20]
0x18009981c  mov     rcx, r12
0x18009981f  call    ExtractRPCClientSID
0x180099824  mov     edi, eax
0x180099826  test    eax, eax
0x180099828  jns     short loc_18009986C
0x18009982a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099831  lea     r14, WPP_GLOBAL_Control
0x180099838  cmp     rcx, r14
0x18009983b  jz      loc_180099A32
0x180099841  mov     ebx, 1
0x180099846  test    [rcx+1Ch], bl
0x180099849  jz      loc_180099A32
0x18009984f  mov     edx, 104h
0x180099854  mov     r9d, eax
0x180099857  mov     rcx, [rcx+10h]
0x18009985b  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099862  call    WPP_SF_d
0x180099867  jmp     loc_180099A32
0x18009986c  lea     rdx, [rbp+var_18]
0x180099870  mov     rcx, r12
0x180099873  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180099879  mov     r9d, [rsi+18h]
0x18009987d  cmp     r9d, 2
0x180099881  jz      short loc_1800998D6
0x180099883  mov     rcx, cs:WPP_GLOBAL_Control
0x18009988a  lea     r14, WPP_GLOBAL_Control
0x180099891  mov     ebx, 1
0x180099896  cmp     rcx, r14
0x180099899  jz      short loc_1800998B5
0x18009989b  test    [rcx+1Ch], bl
0x18009989e  jz      short loc_1800998B5
0x1800998a0  mov     rcx, [rcx+10h]
0x1800998a4  mov     edx, 105h
0x1800998a9  call    WPP_SF_l
0x1800998ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800998b5  mov     edi, 80070005h
0x1800998ba  cmp     rcx, r14
0x1800998bd  jz      loc_180099A32
0x1800998c3  test    [rcx+1Ch], bl
0x1800998c6  jz      loc_180099A32
0x1800998cc  mov     edx, 106h
0x1800998d1  mov     r9d, edi
0x1800998d4  jmp     short loc_180099857
0x1800998d6  cmp     dword ptr [rsi+10h], 2
0x1800998da  jz      short loc_180099913
0x1800998dc  cmp     dword ptr [rsi+10h], 5
0x1800998e0  jz      short loc_180099913
0x1800998e2  mov     edi, 80070032h
0x1800998e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800998ee  lea     r14, WPP_GLOBAL_Control
0x1800998f5  cmp     rcx, r14
0x1800998f8  jz      loc_180099A32
0x1800998fe  mov     ebx, 1
0x180099903  test    [rcx+1Ch], bl
0x180099906  jz      loc_180099A32
0x18009990c  mov     edx, 107h
0x180099911  jmp     short loc_1800998D1
0x180099913  mov     rcx, [rsi]
0x180099916  mov     ebx, 1
0x18009991b  test    rcx, rcx
0x18009991e  jz      short loc_180099979
0x180099920  lea     rax, [rbp+var_30]
0x180099924  mov     r8, r15
0x180099927  lea     r9, [rbp+var_28]
0x18009992b  mov     [rsp+70h+var_50], rax
0x180099930  mov     edx, ebx
0x180099932  call    ?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z; FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)
0x180099937  mov     rcx, [rsi]
0x18009993a  mov     r8, r15
0x18009993d  mov     edx, ebx
0x18009993f  call    cs:__imp_FwDeleteRule
0x180099945  mov     edi, eax
0x180099947  test    eax, eax
0x180099949  jns     short loc_180099975
0x18009994b  mov     rcx, cs:WPP_GLOBAL_Control
0x180099952  lea     r14, WPP_GLOBAL_Control
0x180099959  cmp     rcx, r14
0x18009995c  jz      loc_180099A32
0x180099962  test    [rcx+1Ch], bl
0x180099965  jz      loc_180099A32
0x18009996b  mov     edx, 108h
0x180099970  jmp     loc_180099854
0x180099975  mov     r14d, [rbp+var_30]
0x180099979  cmp     [rbp+var_28], 0
0x18009997e  jnz     short loc_1800999B7
0x180099980  mov     rdx, [rsi+8]
0x180099984  lea     rcx, qword_180124750; struct _tag_FW_BLOB_MANIPULATOR *
0x18009998b  add     rdx, 18h; struct _tag_FW_BLOB_REPO *
0x18009998f  mov     r8, r15; unsigned __int16 *
0x180099992  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x180099997  mov     rdi, rax
0x18009999a  test    rax, rax
0x18009999d  jz      short loc_1800999B7
0x18009999f  mov     rcx, [rax]
0x1800999a2  lea     rdx, [rbp+var_28]
0x1800999a6  mov     rcx, [rcx+18h]
0x1800999aa  call    cs:__imp_FwStringCopy
0x1800999b0  mov     rax, [rdi]
0x1800999b3  mov     r14d, [rax+28h]
0x1800999b7  mov     edx, [rsi+10h]
0x1800999ba  lea     rax, [rbp+var_10]
0x1800999be  mov     rcx, [rsi+8]; struct _tag_FW_STORE *
0x1800999c2  mov     r9, r15
0x1800999c5  mov     [rsp+70h+var_48], 0; __int64
0x1800999ce  mov     r8d, ebx
0x1800999d1  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x1800999d6  call    FwIncrmDeleteRule
0x1800999db  mov     edi, eax
0x1800999dd  test    eax, eax
0x1800999df  jns     short loc_180099A03
0x1800999e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800999e8  lea     r14, WPP_GLOBAL_Control
0x1800999ef  cmp     rcx, r14
0x1800999f2  jz      short loc_180099A32
0x1800999f4  test    [rcx+1Ch], bl
0x1800999f7  jz      short loc_180099A32
0x1800999f9  mov     edx, 109h
0x1800999fe  jmp     loc_180099854
0x180099a03  mov     rcx, [rbp+var_20]
0x180099a07  mov     r9d, ebx
0x180099a0a  mov     rax, [rbp+var_28]
0x180099a0e  mov     r8d, ebx
0x180099a11  mov     [rsp+70h+var_48], rax
0x180099a16  mov     edx, r14d
0x180099a19  mov     [rsp+70h+var_50], r15
0x180099a1e  mov     rcx, [rcx]
0x180099a21  call    FwAuditLogRuleChange
0x180099a26  call    FwUpdateConsecPresenceDataPoint
0x180099a2b  lea     r14, WPP_GLOBAL_Control
0x180099a32  lea     rdx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x180099a39  mov     rcx, r12; void *
0x180099a3c  call    FwUnlockInternal
0x180099a41  lea     rcx, aSvrimplFwdelet_0; "SvrImpl_FWDeleteConnectionSecurityRule"
0x180099a48  call    FwReleaseRPCSharedLock
0x180099a4d  test    edi, edi
0x180099a4f  js      short loc_180099A57
0x180099a51  call    cs:__imp_FwChangeSourceSignal
0x180099a57  mov     ecx, edi
0x180099a59  call    cs:__imp_FwHResultToWindowsError
0x180099a5f  mov     rcx, [rbp+var_10]
0x180099a63  lea     rsi, qword_1800F5F90
0x180099a6a  test    rcx, rcx
0x180099a6d  mov     r9, rsi
0x180099a70  mov     r8d, eax
0x180099a73  mov     rdx, rsi
0x180099a76  mov     rax, [rbp+var_18]
0x180099a7a  cmovnz  r9, rcx; unsigned __int16 *
0x180099a7e  mov     rcx, [rbp+var_20]
0x180099a82  test    r15, r15
0x180099a85  cmovz   r15, rsi
0x180099a89  test    rax, rax
0x180099a8c  cmovnz  rdx, rax; unsigned __int16 *
0x180099a90  test    rcx, rcx
0x180099a93  jz      short loc_180099A9A
0x180099a95  mov     rcx, [rcx]
0x180099a98  jmp     short loc_180099AA1
0x180099a9a  lea     rcx, aS100; "S-1-0-0"
0x180099aa1  mov     dword ptr [rsp+70h+var_50], r8d; unsigned int
0x180099aa6  mov     r8, r15; unsigned __int16 *
0x180099aa9  call    FwEventCSRuleDeleted
0x180099aae  mov     rax, cs:WPP_GLOBAL_Control
0x180099ab5  cmp     rax, r14
0x180099ab8  jz      short loc_180099B08
0x180099aba  test    byte ptr [rax+1Ch], 4
0x180099abe  jz      short loc_180099B08
0x180099ac0  mov     rax, [rbp+var_10]
0x180099ac4  mov     rbx, rsi
0x180099ac7  test    rax, rax
0x180099aca  mov     ecx, edi
0x180099acc  cmovnz  rbx, rax
0x180099ad0  mov     rax, [rbp+var_18]
0x180099ad4  test    rax, rax
0x180099ad7  cmovnz  rsi, rax
0x180099adb  call    cs:__imp_FwHResultToWindowsError
0x180099ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ae8  mov     edx, 10Ah
0x180099aed  mov     [rsp+70h+var_40], rbx
0x180099af2  mov     r9d, eax
0x180099af5  mov     [rsp+70h+var_48], r15
0x180099afa  mov     [rsp+70h+var_50], rsi
0x180099aff  mov     rcx, [rcx+10h]
0x180099b03  call    WPP_SF_DSSS
0x180099b08  mov     rcx, [rbp+var_20]
0x180099b0c  call    cs:__imp_FwFree
0x180099b12  mov     rcx, [rbp+var_18]
0x180099b16  call    cs:__imp_FwFree
0x180099b1c  mov     rcx, [rbp+var_28]
0x180099b20  call    cs:__imp_FwFree
0x180099b26  mov     rcx, [rbp+var_10]
0x180099b2a  call    cs:__imp_FwFree
0x180099b30  mov     ecx, edi
0x180099b32  call    cs:__imp_FwHResultToWindowsError
0x180099b38  mov     rcx, [rbp+var_8]
0x180099b3c  xor     rcx, rsp; StackCookie
0x180099b3f  call    __security_check_cookie
0x180099b44  add     rsp, 70h
0x180099b48  pop     r15
0x180099b4a  pop     r14
0x180099b4c  pop     r12
0x180099b4e  pop     rdi
0x180099b4f  pop     rsi
0x180099b50  pop     rbx
0x180099b51  pop     rbp
0x180099b52  retn
```
