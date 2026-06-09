# SvrImpl_FWDeleteMainModeRule(void *,void *,ushort const *)

- ea: `0x18009a6a0`
- end: `0x18009aa4b`
- name: `?SvrImpl_FWDeleteMainModeRule@@YAKPEAX0PEBG@Z`
- size: `939`
- prototype: `unsigned int __fastcall(void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c0fa0`

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
- `0x18006e644`
- `0x18006f520`
- `0x180095170`
- `0x18009a6a0`
- `0x1800a1a18`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009a796`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009a796`
- `fwbase!FwChangeSourceSignal` at `0x18009a949`
- `fwbase!FwChangeSourceSignal` at `0x18009a949`
- `fwbase!FwHResultToWindowsError` at `0x18009a951`
- `fwbase!FwHResultToWindowsError` at `0x18009a9d3`
- `fwbase!FwHResultToWindowsError` at `0x18009aa2a`
- `fwbase!FwHResultToWindowsError` at `0x18009a951`
- `fwbase!FwHResultToWindowsError` at `0x18009a9d3`
- `fwbase!FwHResultToWindowsError` at `0x18009aa2a`
- `fwbase!FwStringCopy` at `0x18009a8af`
- `fwbase!FwStringCopy` at `0x18009a8af`
- `fwbase!FwFree` at `0x18009aa04`
- `fwbase!FwFree` at `0x18009aa0e`
- `fwbase!FwFree` at `0x18009aa18`
- `fwbase!FwFree` at `0x18009aa22`
- `fwbase!FwFree` at `0x18009aa04`
- `fwbase!FwFree` at `0x18009aa0e`
- `fwbase!FwFree` at `0x18009aa18`
- `fwbase!FwFree` at `0x18009aa22`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009a84b`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009a84b`

## string_xrefs

- `0x18009a714`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009a733`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009a92a`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009a939`: `SvrImpl_FWDeleteMainModeRule`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteMainModeRule(void *a1, _QWORD *a2, unsigned __int16 *a3)
{
  int v3; // esi
  __int64 result; // rax
  int v8; // edi
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
  v28 = 0;
  v27 = 0;
  v25 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 419, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteMainModeRule");
  if ( (int)result >= 0 )
  {
    v8 = FwLock();
    if ( v8 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWDeleteMainModeRule");
      return (unsigned int)v8;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v26);
    v10 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 420;
      goto LABEL_11;
    }
    FwGetRpcCallersProcessImageName(a1, &v28);
    if ( *((_DWORD *)a2 + 6) == 2 )
    {
      if ( *((_DWORD *)a2 + 4) == 2 || *((_DWORD *)a2 + 4) == 5 )
      {
        if ( *a2 )
        {
          FwGetRuleName(*a2, 2, a3, &v25, &v24);
          RPCClientSID = FwDeleteRule(*a2, 2, a3);
          v10 = RPCClientSID;
          if ( RPCClientSID < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_40;
            }
            v12 = 424;
LABEL_11:
            v13 = (unsigned int)RPCClientSID;
LABEL_12:
            WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v13);
LABEL_40:
            FwUnlockInternal(a1, "SvrImpl_FWDeleteMainModeRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteMainModeRule");
            if ( (v10 & 0x80000000) == 0 )
              FwChangeSourceSignal();
            v16 = FwHResultToWindowsError(v10);
            v17 = (unsigned __int16 *)&qword_1800F5F90;
            v18 = (unsigned __int16 *)&qword_1800F5F90;
            v19 = (unsigned __int16 *)&qword_1800F5F90;
            if ( v27 )
              v18 = v27;
            if ( !a3 )
              a3 = (unsigned __int16 *)&qword_1800F5F90;
            if ( v28 )
              v19 = v28;
            if ( v26 )
              v20 = *v26;
            else
              v20 = L"S-1-0-0";
            FwEventMMRuleDeleted(v20, v19, a3, v18, v16);
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v21 = (unsigned __int16 *)&qword_1800F5F90;
              if ( v27 )
                v21 = v27;
              if ( v28 )
                v17 = v28;
              v22 = FwHResultToWindowsError(v10);
              WPP_SF_DSSS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                426,
                v23,
                v22,
                (__int64)v17,
                (__int64)a3,
                (__int64)v21);
            }
            FwFree(v26);
            FwFree(v25);
            FwFree(v27);
            FwFree(v28);
            return FwHResultToWindowsError(v10);
          }
          v3 = v24;
        }
        if ( !v25 )
        {
          v14 = FwLookForBlobContainerWithID(
                  (struct _tag_FW_BLOB_MANIPULATOR *)&qword_180124780,
                  (struct _tag_FW_BLOB_REPO *)(a2[1] + 48LL),
                  a3);
          v15 = v14;
          if ( v14 )
          {
            FwStringCopy(*(_QWORD *)(*(_QWORD *)v14 + 24LL), &v25);
            v3 = *(_DWORD *)(*(_QWORD *)v15 + 40LL);
          }
        }
        RPCClientSID = FwIncrmDeleteRule((struct _tag_FW_STORE *)a2[1], &v27, 0);
        v10 = RPCClientSID;
        if ( RPCClientSID >= 0 )
        {
          FwAuditLogRuleChange((unsigned int)*v26, v3, 2, 1, (__int64)a3, v25);
          goto LABEL_40;
        }
        v11 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_40;
        v12 = 425;
        goto LABEL_11;
      }
      v10 = -2147024846;
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v12 = 423;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 421);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = -2147024891;
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_40;
      v12 = 422;
    }
    v13 = v10;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009a6a0  push    rbp
0x18009a6a2  push    rbx
0x18009a6a3  push    rsi
0x18009a6a4  push    rdi
0x18009a6a5  push    r13
0x18009a6a7  push    r14
0x18009a6a9  push    r15
0x18009a6ab  mov     rbp, rsp
0x18009a6ae  sub     rsp, 70h
0x18009a6b2  mov     rax, cs:__security_cookie
0x18009a6b9  xor     rax, rsp
0x18009a6bc  mov     [rbp+var_8], rax
0x18009a6c0  xor     esi, esi
0x18009a6c2  mov     [rbp+var_20], 0
0x18009a6ca  mov     [rbp+var_30], esi
0x18009a6cd  mov     r14, r8
0x18009a6d0  mov     [rbp+var_10], rsi
0x18009a6d4  mov     rbx, rdx
0x18009a6d7  mov     [rbp+var_18], rsi
0x18009a6db  mov     r15, rcx
0x18009a6de  mov     [rbp+var_28], 0
0x18009a6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a6ed  lea     r13, WPP_GLOBAL_Control
0x18009a6f4  cmp     rcx, r13
0x18009a6f7  jz      short loc_18009A714
0x18009a6f9  test    byte ptr [rcx+1Ch], 8
0x18009a6fd  jz      short loc_18009A714
0x18009a6ff  mov     rcx, [rcx+10h]
0x18009a703  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009a70a  mov     edx, 1A3h
0x18009a70f  call    WPP_SF_
0x18009a714  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009a71b  call    FwAcquireRPCSharedLock
0x18009a720  test    eax, eax
0x18009a722  js      loc_18009AA30
0x18009a728  call    FwLock
0x18009a72d  mov     edi, eax
0x18009a72f  test    eax, eax
0x18009a731  jns     short loc_18009A746
0x18009a733  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009a73a  call    FwReleaseRPCSharedLock
0x18009a73f  mov     eax, edi
0x18009a741  jmp     loc_18009AA30
0x18009a746  lea     rdx, [rbp+var_20]
0x18009a74a  mov     rcx, r15
0x18009a74d  call    ExtractRPCClientSID
0x18009a752  mov     edi, eax
0x18009a754  test    eax, eax
0x18009a756  jns     short loc_18009A78F
0x18009a758  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a75f  cmp     rcx, r13
0x18009a762  jz      loc_18009A92A
0x18009a768  test    byte ptr [rcx+1Ch], 1
0x18009a76c  jz      loc_18009A92A
0x18009a772  mov     edx, 1A4h
0x18009a777  mov     r9d, eax
0x18009a77a  mov     rcx, [rcx+10h]
0x18009a77e  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009a785  call    WPP_SF_d
0x18009a78a  jmp     loc_18009A92A
0x18009a78f  lea     rdx, [rbp+var_10]
0x18009a793  mov     rcx, r15
0x18009a796  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009a79c  mov     r9d, [rbx+18h]
0x18009a7a0  mov     edi, 2
0x18009a7a5  cmp     r9d, edi
0x18009a7a8  jz      short loc_18009A7F3
0x18009a7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a7b1  cmp     rcx, r13
0x18009a7b4  jz      short loc_18009A7D1
0x18009a7b6  test    byte ptr [rcx+1Ch], 1
0x18009a7ba  jz      short loc_18009A7D1
0x18009a7bc  mov     rcx, [rcx+10h]
0x18009a7c0  mov     edx, 1A5h
0x18009a7c5  call    WPP_SF_l
0x18009a7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a7d1  mov     edi, 80070005h
0x18009a7d6  cmp     rcx, r13
0x18009a7d9  jz      loc_18009A92A
0x18009a7df  test    byte ptr [rcx+1Ch], 1
0x18009a7e3  jz      loc_18009A92A
0x18009a7e9  mov     edx, 1A6h
0x18009a7ee  mov     r9d, edi
0x18009a7f1  jmp     short loc_18009A77A
0x18009a7f3  cmp     [rbx+10h], edi
0x18009a7f6  jz      short loc_18009A824
0x18009a7f8  cmp     dword ptr [rbx+10h], 5
0x18009a7fc  jz      short loc_18009A824
0x18009a7fe  mov     edi, 80070032h
0x18009a803  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a80a  cmp     rcx, r13
0x18009a80d  jz      loc_18009A92A
0x18009a813  test    byte ptr [rcx+1Ch], 1
0x18009a817  jz      loc_18009A92A
0x18009a81d  mov     edx, 1A7h
0x18009a822  jmp     short loc_18009A7EE
0x18009a824  mov     rcx, [rbx]
0x18009a827  test    rcx, rcx
0x18009a82a  jz      short loc_18009A87E
0x18009a82c  lea     rax, [rbp+var_30]
0x18009a830  mov     r8, r14
0x18009a833  lea     r9, [rbp+var_28]
0x18009a837  mov     [rsp+70h+var_50], rax
0x18009a83c  mov     edx, edi
0x18009a83e  call    ?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z; FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)
0x18009a843  mov     rcx, [rbx]
0x18009a846  mov     r8, r14
0x18009a849  mov     edx, edi
0x18009a84b  call    cs:__imp_FwDeleteRule
0x18009a851  mov     edi, eax
0x18009a853  test    eax, eax
0x18009a855  jns     short loc_18009A87B
0x18009a857  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a85e  cmp     rcx, r13
0x18009a861  jz      loc_18009A92A
0x18009a867  test    byte ptr [rcx+1Ch], 1
0x18009a86b  jz      loc_18009A92A
0x18009a871  mov     edx, 1A8h
0x18009a876  jmp     loc_18009A777
0x18009a87b  mov     esi, [rbp+var_30]
0x18009a87e  cmp     [rbp+var_28], 0
0x18009a883  jnz     short loc_18009A8BB
0x18009a885  mov     rdx, [rbx+8]
0x18009a889  lea     rcx, qword_180124780; struct _tag_FW_BLOB_MANIPULATOR *
0x18009a890  add     rdx, 30h ; '0'; struct _tag_FW_BLOB_REPO *
0x18009a894  mov     r8, r14; unsigned __int16 *
0x18009a897  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009a89c  mov     rdi, rax
0x18009a89f  test    rax, rax
0x18009a8a2  jz      short loc_18009A8BB
0x18009a8a4  mov     rcx, [rax]
0x18009a8a7  lea     rdx, [rbp+var_28]
0x18009a8ab  mov     rcx, [rcx+18h]
0x18009a8af  call    cs:__imp_FwStringCopy
0x18009a8b5  mov     rax, [rdi]
0x18009a8b8  mov     esi, [rax+28h]
0x18009a8bb  mov     edx, [rbx+10h]
0x18009a8be  lea     rax, [rbp+var_18]
0x18009a8c2  mov     rcx, [rbx+8]; struct _tag_FW_STORE *
0x18009a8c6  mov     r9, r14
0x18009a8c9  mov     [rsp+70h+var_48], 0; __int64
0x18009a8d2  mov     r8d, 2
0x18009a8d8  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18009a8dd  call    FwIncrmDeleteRule
0x18009a8e2  mov     edi, eax
0x18009a8e4  test    eax, eax
0x18009a8e6  jns     short loc_18009A904
0x18009a8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a8ef  cmp     rcx, r13
0x18009a8f2  jz      short loc_18009A92A
0x18009a8f4  test    byte ptr [rcx+1Ch], 1
0x18009a8f8  jz      short loc_18009A92A
0x18009a8fa  mov     edx, 1A9h
0x18009a8ff  jmp     loc_18009A777
0x18009a904  mov     rcx, [rbp+var_20]
0x18009a908  mov     r9d, 1
0x18009a90e  mov     rax, [rbp+var_28]
0x18009a912  mov     edx, esi
0x18009a914  mov     [rsp+70h+var_48], rax
0x18009a919  mov     [rsp+70h+var_50], r14
0x18009a91e  mov     rcx, [rcx]
0x18009a921  lea     r8d, [r9+1]
0x18009a925  call    FwAuditLogRuleChange
0x18009a92a  lea     rdx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009a931  mov     rcx, r15; void *
0x18009a934  call    FwUnlockInternal
0x18009a939  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009a940  call    FwReleaseRPCSharedLock
0x18009a945  test    edi, edi
0x18009a947  js      short loc_18009A94F
0x18009a949  call    cs:__imp_FwChangeSourceSignal
0x18009a94f  mov     ecx, edi
0x18009a951  call    cs:__imp_FwHResultToWindowsError
0x18009a957  mov     rcx, [rbp+var_18]
0x18009a95b  lea     rsi, qword_1800F5F90
0x18009a962  test    rcx, rcx
0x18009a965  mov     r9, rsi
0x18009a968  mov     r8d, eax
0x18009a96b  mov     rdx, rsi
0x18009a96e  mov     rax, [rbp+var_10]
0x18009a972  cmovnz  r9, rcx; unsigned __int16 *
0x18009a976  mov     rcx, [rbp+var_20]
0x18009a97a  test    r14, r14
0x18009a97d  cmovz   r14, rsi
0x18009a981  test    rax, rax
0x18009a984  cmovnz  rdx, rax; unsigned __int16 *
0x18009a988  test    rcx, rcx
0x18009a98b  jz      short loc_18009A992
0x18009a98d  mov     rcx, [rcx]
0x18009a990  jmp     short loc_18009A999
0x18009a992  lea     rcx, aS100; "S-1-0-0"
0x18009a999  mov     dword ptr [rsp+70h+var_50], r8d; unsigned int
0x18009a99e  mov     r8, r14; unsigned __int16 *
0x18009a9a1  call    FwEventMMRuleDeleted
0x18009a9a6  mov     rax, cs:WPP_GLOBAL_Control
0x18009a9ad  cmp     rax, r13
0x18009a9b0  jz      short loc_18009AA00
0x18009a9b2  test    byte ptr [rax+1Ch], 4
0x18009a9b6  jz      short loc_18009AA00
0x18009a9b8  mov     rax, [rbp+var_18]
0x18009a9bc  mov     rbx, rsi
0x18009a9bf  test    rax, rax
0x18009a9c2  mov     ecx, edi
0x18009a9c4  cmovnz  rbx, rax
0x18009a9c8  mov     rax, [rbp+var_10]
0x18009a9cc  test    rax, rax
0x18009a9cf  cmovnz  rsi, rax
0x18009a9d3  call    cs:__imp_FwHResultToWindowsError
0x18009a9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a9e0  mov     edx, 1AAh
0x18009a9e5  mov     [rsp+70h+var_40], rbx
0x18009a9ea  mov     r9d, eax
0x18009a9ed  mov     [rsp+70h+var_48], r14
0x18009a9f2  mov     [rsp+70h+var_50], rsi
0x18009a9f7  mov     rcx, [rcx+10h]
0x18009a9fb  call    WPP_SF_DSSS
0x18009aa00  mov     rcx, [rbp+var_20]
0x18009aa04  call    cs:__imp_FwFree
0x18009aa0a  mov     rcx, [rbp+var_28]
0x18009aa0e  call    cs:__imp_FwFree
0x18009aa14  mov     rcx, [rbp+var_18]
0x18009aa18  call    cs:__imp_FwFree
0x18009aa1e  mov     rcx, [rbp+var_10]
0x18009aa22  call    cs:__imp_FwFree
0x18009aa28  mov     ecx, edi
0x18009aa2a  call    cs:__imp_FwHResultToWindowsError
0x18009aa30  mov     rcx, [rbp+var_8]
0x18009aa34  xor     rcx, rsp; StackCookie
0x18009aa37  call    __security_check_cookie
0x18009aa3c  add     rsp, 70h
0x18009aa40  pop     r15
0x18009aa42  pop     r14
0x18009aa44  pop     r13
0x18009aa46  pop     rdi
0x18009aa47  pop     rsi
0x18009aa48  pop     rbx
0x18009aa49  pop     rbp
0x18009aa4a  retn
```
