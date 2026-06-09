# SvrImpl_FWDeleteMainModeRule(void *,void *,ushort const *)

- ea: `0x18009f98c`
- end: `0x18009fd7a`
- name: `?SvrImpl_FWDeleteMainModeRule@@YAKPEAX0PEBG@Z`
- size: `1006`
- prototype: `unsigned int __fastcall(void *, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c7e80`

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
- `0x180071a80`
- `0x1800729c0`
- `0x18009a008`
- `0x18009f98c`
- `0x1800a71c8`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009fc55`
- `fwbase!FwHResultToWindowsError` at `0x18009fcdd`
- `fwbase!FwHResultToWindowsError` at `0x18009fd52`
- `fwbase!FwHResultToWindowsError` at `0x18009fc55`
- `fwbase!FwHResultToWindowsError` at `0x18009fcdd`
- `fwbase!FwHResultToWindowsError` at `0x18009fd52`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009fa82`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009fa82`
- `fwbase!FwChangeSourceSignal` at `0x18009fc47`
- `fwbase!FwChangeSourceSignal` at `0x18009fc47`
- `fwbase!FwStringCopy` at `0x18009fba7`
- `fwbase!FwStringCopy` at `0x18009fba7`
- `fwbase!FwFree` at `0x18009fd14`
- `fwbase!FwFree` at `0x18009fd24`
- `fwbase!FwFree` at `0x18009fd34`
- `fwbase!FwFree` at `0x18009fd44`
- `fwbase!FwFree` at `0x18009fd14`
- `fwbase!FwFree` at `0x18009fd24`
- `fwbase!FwFree` at `0x18009fd34`
- `fwbase!FwFree` at `0x18009fd44`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009fb3d`
- `FWPolicyIOMgr!FwDeleteRule` at `0x18009fb3d`

## string_xrefs

- `0x18009fa00`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009fa1f`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009fc28`: `SvrImpl_FWDeleteMainModeRule`
- `0x18009fc37`: `SvrImpl_FWDeleteMainModeRule`

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
  v28 = 0;
  v27 = 0;
  v25 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 419, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
            WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v13);
LABEL_40:
            FwUnlockInternal(a1, "SvrImpl_FWDeleteMainModeRule");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteMainModeRule");
            if ( (v10 & 0x80000000) == 0 )
              FwChangeSourceSignal();
            v16 = FwHResultToWindowsError(v10);
            v17 = (unsigned __int16 *)&qword_1800FBFF0;
            v18 = (unsigned __int16 *)&qword_1800FBFF0;
            v19 = (unsigned __int16 *)&qword_1800FBFF0;
            if ( v27 )
              v18 = v27;
            if ( !a3 )
              a3 = (unsigned __int16 *)&qword_1800FBFF0;
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
              v21 = (unsigned __int16 *)&qword_1800FBFF0;
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
                  (struct _tag_FW_BLOB_MANIPULATOR *)&qword_18012A780,
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
0x18009f98c  push    rbp
0x18009f98e  push    rbx
0x18009f98f  push    rsi
0x18009f990  push    rdi
0x18009f991  push    r13
0x18009f993  push    r14
0x18009f995  push    r15
0x18009f997  mov     rbp, rsp
0x18009f99a  sub     rsp, 70h
0x18009f99e  mov     rax, cs:__security_cookie
0x18009f9a5  xor     rax, rsp
0x18009f9a8  mov     [rbp+var_8], rax
0x18009f9ac  xor     esi, esi
0x18009f9ae  mov     [rbp+var_20], 0
0x18009f9b6  mov     [rbp+var_30], esi
0x18009f9b9  mov     r14, r8
0x18009f9bc  mov     [rbp+var_10], rsi
0x18009f9c0  mov     rbx, rdx
0x18009f9c3  mov     [rbp+var_18], rsi
0x18009f9c7  mov     r15, rcx
0x18009f9ca  mov     [rbp+var_28], 0
0x18009f9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f9d9  lea     r13, WPP_GLOBAL_Control
0x18009f9e0  cmp     rcx, r13
0x18009f9e3  jz      short loc_18009FA00
0x18009f9e5  test    byte ptr [rcx+1Ch], 8
0x18009f9e9  jz      short loc_18009FA00
0x18009f9eb  mov     rcx, [rcx+10h]
0x18009f9ef  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009f9f6  mov     edx, 1A3h
0x18009f9fb  call    WPP_SF_
0x18009fa00  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009fa07  call    FwAcquireRPCSharedLock
0x18009fa0c  test    eax, eax
0x18009fa0e  js      loc_18009FD5E
0x18009fa14  call    FwLock
0x18009fa19  mov     edi, eax
0x18009fa1b  test    eax, eax
0x18009fa1d  jns     short loc_18009FA32
0x18009fa1f  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009fa26  call    FwReleaseRPCSharedLock
0x18009fa2b  mov     eax, edi
0x18009fa2d  jmp     loc_18009FD5E
0x18009fa32  lea     rdx, [rbp+var_20]
0x18009fa36  mov     rcx, r15
0x18009fa39  call    ExtractRPCClientSID
0x18009fa3e  mov     edi, eax
0x18009fa40  test    eax, eax
0x18009fa42  jns     short loc_18009FA7B
0x18009fa44  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fa4b  cmp     rcx, r13
0x18009fa4e  jz      loc_18009FC28
0x18009fa54  test    byte ptr [rcx+1Ch], 1
0x18009fa58  jz      loc_18009FC28
0x18009fa5e  mov     edx, 1A4h
0x18009fa63  mov     r9d, eax
0x18009fa66  mov     rcx, [rcx+10h]
0x18009fa6a  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009fa71  call    WPP_SF_d
0x18009fa76  jmp     loc_18009FC28
0x18009fa7b  lea     rdx, [rbp+var_10]
0x18009fa7f  mov     rcx, r15
0x18009fa82  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009fa89  nop     dword ptr [rax+rax+00h]
0x18009fa8e  mov     r9d, [rbx+18h]
0x18009fa92  mov     edi, 2
0x18009fa97  cmp     r9d, edi
0x18009fa9a  jz      short loc_18009FAE5
0x18009fa9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009faa3  cmp     rcx, r13
0x18009faa6  jz      short loc_18009FAC3
0x18009faa8  test    byte ptr [rcx+1Ch], 1
0x18009faac  jz      short loc_18009FAC3
0x18009faae  mov     rcx, [rcx+10h]
0x18009fab2  mov     edx, 1A5h
0x18009fab7  call    WPP_SF_l
0x18009fabc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fac3  mov     edi, 80070005h
0x18009fac8  cmp     rcx, r13
0x18009facb  jz      loc_18009FC28
0x18009fad1  test    byte ptr [rcx+1Ch], 1
0x18009fad5  jz      loc_18009FC28
0x18009fadb  mov     edx, 1A6h
0x18009fae0  mov     r9d, edi
0x18009fae3  jmp     short loc_18009FA66
0x18009fae5  cmp     [rbx+10h], edi
0x18009fae8  jz      short loc_18009FB16
0x18009faea  cmp     dword ptr [rbx+10h], 5
0x18009faee  jz      short loc_18009FB16
0x18009faf0  mov     edi, 80070032h
0x18009faf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fafc  cmp     rcx, r13
0x18009faff  jz      loc_18009FC28
0x18009fb05  test    byte ptr [rcx+1Ch], 1
0x18009fb09  jz      loc_18009FC28
0x18009fb0f  mov     edx, 1A7h
0x18009fb14  jmp     short loc_18009FAE0
0x18009fb16  mov     rcx, [rbx]
0x18009fb19  test    rcx, rcx
0x18009fb1c  jz      short loc_18009FB76
0x18009fb1e  lea     rax, [rbp+var_30]
0x18009fb22  mov     r8, r14
0x18009fb25  lea     r9, [rbp+var_28]
0x18009fb29  mov     [rsp+70h+var_50], rax
0x18009fb2e  mov     edx, edi
0x18009fb30  call    ?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z; FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)
0x18009fb35  mov     rcx, [rbx]
0x18009fb38  mov     r8, r14
0x18009fb3b  mov     edx, edi
0x18009fb3d  call    cs:__imp_FwDeleteRule
0x18009fb44  nop     dword ptr [rax+rax+00h]
0x18009fb49  mov     edi, eax
0x18009fb4b  test    eax, eax
0x18009fb4d  jns     short loc_18009FB73
0x18009fb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb56  cmp     rcx, r13
0x18009fb59  jz      loc_18009FC28
0x18009fb5f  test    byte ptr [rcx+1Ch], 1
0x18009fb63  jz      loc_18009FC28
0x18009fb69  mov     edx, 1A8h
0x18009fb6e  jmp     loc_18009FA63
0x18009fb73  mov     esi, [rbp+var_30]
0x18009fb76  cmp     [rbp+var_28], 0
0x18009fb7b  jnz     short loc_18009FBB9
0x18009fb7d  mov     rdx, [rbx+8]
0x18009fb81  lea     rcx, qword_18012A780; struct _tag_FW_BLOB_MANIPULATOR *
0x18009fb88  add     rdx, 30h ; '0'; struct _tag_FW_BLOB_REPO *
0x18009fb8c  mov     r8, r14; unsigned __int16 *
0x18009fb8f  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009fb94  mov     rdi, rax
0x18009fb97  test    rax, rax
0x18009fb9a  jz      short loc_18009FBB9
0x18009fb9c  mov     rcx, [rax]
0x18009fb9f  lea     rdx, [rbp+var_28]
0x18009fba3  mov     rcx, [rcx+18h]
0x18009fba7  call    cs:__imp_FwStringCopy
0x18009fbae  nop     dword ptr [rax+rax+00h]
0x18009fbb3  mov     rax, [rdi]
0x18009fbb6  mov     esi, [rax+28h]
0x18009fbb9  mov     edx, [rbx+10h]
0x18009fbbc  lea     rax, [rbp+var_18]
0x18009fbc0  mov     rcx, [rbx+8]; struct _tag_FW_STORE *
0x18009fbc4  mov     r9, r14
0x18009fbc7  mov     [rsp+70h+var_48], 0; __int64
0x18009fbd0  mov     r8d, 2
0x18009fbd6  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18009fbdb  call    FwIncrmDeleteRule
0x18009fbe0  mov     edi, eax
0x18009fbe2  test    eax, eax
0x18009fbe4  jns     short loc_18009FC02
0x18009fbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fbed  cmp     rcx, r13
0x18009fbf0  jz      short loc_18009FC28
0x18009fbf2  test    byte ptr [rcx+1Ch], 1
0x18009fbf6  jz      short loc_18009FC28
0x18009fbf8  mov     edx, 1A9h
0x18009fbfd  jmp     loc_18009FA63
0x18009fc02  mov     rcx, [rbp+var_20]
0x18009fc06  mov     r9d, 1
0x18009fc0c  mov     rax, [rbp+var_28]
0x18009fc10  mov     edx, esi
0x18009fc12  mov     [rsp+70h+var_48], rax
0x18009fc17  mov     [rsp+70h+var_50], r14
0x18009fc1c  mov     rcx, [rcx]
0x18009fc1f  lea     r8d, [r9+1]
0x18009fc23  call    FwAuditLogRuleChange
0x18009fc28  lea     rdx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009fc2f  mov     rcx, r15; void *
0x18009fc32  call    FwUnlockInternal
0x18009fc37  lea     rcx, aSvrimplFwdelet_8; "SvrImpl_FWDeleteMainModeRule"
0x18009fc3e  call    FwReleaseRPCSharedLock
0x18009fc43  test    edi, edi
0x18009fc45  js      short loc_18009FC53
0x18009fc47  call    cs:__imp_FwChangeSourceSignal
0x18009fc4e  nop     dword ptr [rax+rax+00h]
0x18009fc53  mov     ecx, edi
0x18009fc55  call    cs:__imp_FwHResultToWindowsError
0x18009fc5c  nop     dword ptr [rax+rax+00h]
0x18009fc61  mov     rcx, [rbp+var_18]
0x18009fc65  lea     rsi, qword_1800FBFF0
0x18009fc6c  test    rcx, rcx
0x18009fc6f  mov     r9, rsi
0x18009fc72  mov     r8d, eax
0x18009fc75  mov     rdx, rsi
0x18009fc78  mov     rax, [rbp+var_10]
0x18009fc7c  cmovnz  r9, rcx; unsigned __int16 *
0x18009fc80  mov     rcx, [rbp+var_20]
0x18009fc84  test    r14, r14
0x18009fc87  cmovz   r14, rsi
0x18009fc8b  test    rax, rax
0x18009fc8e  cmovnz  rdx, rax; unsigned __int16 *
0x18009fc92  test    rcx, rcx
0x18009fc95  jz      short loc_18009FC9C
0x18009fc97  mov     rcx, [rcx]
0x18009fc9a  jmp     short loc_18009FCA3
0x18009fc9c  lea     rcx, aS100; "S-1-0-0"
0x18009fca3  mov     dword ptr [rsp+70h+var_50], r8d; char
0x18009fca8  mov     r8, r14; unsigned __int16 *
0x18009fcab  call    FwEventMMRuleDeleted
0x18009fcb0  mov     rax, cs:WPP_GLOBAL_Control
0x18009fcb7  cmp     rax, r13
0x18009fcba  jz      short loc_18009FD10
0x18009fcbc  test    byte ptr [rax+1Ch], 4
0x18009fcc0  jz      short loc_18009FD10
0x18009fcc2  mov     rax, [rbp+var_18]
0x18009fcc6  mov     rbx, rsi
0x18009fcc9  test    rax, rax
0x18009fccc  mov     ecx, edi
0x18009fcce  cmovnz  rbx, rax
0x18009fcd2  mov     rax, [rbp+var_10]
0x18009fcd6  test    rax, rax
0x18009fcd9  cmovnz  rsi, rax
0x18009fcdd  call    cs:__imp_FwHResultToWindowsError
0x18009fce4  nop     dword ptr [rax+rax+00h]
0x18009fce9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fcf0  mov     edx, 1AAh
0x18009fcf5  mov     [rsp+70h+var_40], rbx
0x18009fcfa  mov     r9d, eax
0x18009fcfd  mov     [rsp+70h+var_48], r14
0x18009fd02  mov     [rsp+70h+var_50], rsi
0x18009fd07  mov     rcx, [rcx+10h]
0x18009fd0b  call    WPP_SF_DSSS
0x18009fd10  mov     rcx, [rbp+var_20]
0x18009fd14  call    cs:__imp_FwFree
0x18009fd1b  nop     dword ptr [rax+rax+00h]
0x18009fd20  mov     rcx, [rbp+var_28]
0x18009fd24  call    cs:__imp_FwFree
0x18009fd2b  nop     dword ptr [rax+rax+00h]
0x18009fd30  mov     rcx, [rbp+var_18]
0x18009fd34  call    cs:__imp_FwFree
0x18009fd3b  nop     dword ptr [rax+rax+00h]
0x18009fd40  mov     rcx, [rbp+var_10]
0x18009fd44  call    cs:__imp_FwFree
0x18009fd4b  nop     dword ptr [rax+rax+00h]
0x18009fd50  mov     ecx, edi
0x18009fd52  call    cs:__imp_FwHResultToWindowsError
0x18009fd59  nop     dword ptr [rax+rax+00h]
0x18009fd5e  mov     rcx, [rbp+var_8]
0x18009fd62  xor     rcx, rsp; StackCookie
0x18009fd65  call    __security_check_cookie
0x18009fd6a  add     rsp, 70h
0x18009fd6e  pop     r15
0x18009fd70  pop     r14
0x18009fd72  pop     r13
0x18009fd74  pop     rdi
0x18009fd75  pop     rsi
0x18009fd76  pop     rbx
0x18009fd77  pop     rbp
0x18009fd78  retn
```
