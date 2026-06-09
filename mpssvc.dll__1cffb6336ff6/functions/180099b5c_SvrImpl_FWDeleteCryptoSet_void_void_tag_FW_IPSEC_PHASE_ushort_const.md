# SvrImpl_FWDeleteCryptoSet(void *,void *,_tag_FW_IPSEC_PHASE,ushort const *)

- ea: `0x180099b5c`
- end: `0x180099fce`
- name: `?SvrImpl_FWDeleteCryptoSet@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@PEBG@Z`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c0c50`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180026310`
- `0x18003e798`
- `0x18005441c`
- `0x18006e1c0`
- `0x18006f520`
- `0x180088554`
- `0x18008a390`
- `0x180095308`
- `0x180099b5c`
- `0x1800a1b4c`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099c5d`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099c5d`
- `fwbase!FwResolveIndirectString` at `0x180099e7e`
- `fwbase!FwResolveIndirectString` at `0x180099e7e`
- `fwbase!FwChangeSourceSignal` at `0x180099eaa`
- `fwbase!FwChangeSourceSignal` at `0x180099eaa`
- `fwbase!FwHResultToWindowsError` at `0x180099eb2`
- `fwbase!FwHResultToWindowsError` at `0x180099f51`
- `fwbase!FwHResultToWindowsError` at `0x180099fad`
- `fwbase!FwHResultToWindowsError` at `0x180099eb2`
- `fwbase!FwHResultToWindowsError` at `0x180099f51`
- `fwbase!FwHResultToWindowsError` at `0x180099fad`
- `fwbase!FwStringCopy` at `0x180099df5`
- `fwbase!FwStringCopy` at `0x180099df5`
- `fwbase!FwFree` at `0x180099f87`
- `fwbase!FwFree` at `0x180099f91`
- `fwbase!FwFree` at `0x180099f9b`
- `fwbase!FwFree` at `0x180099fa5`
- `fwbase!FwFree` at `0x180099f87`
- `fwbase!FwFree` at `0x180099f91`
- `fwbase!FwFree` at `0x180099f9b`
- `fwbase!FwFree` at `0x180099fa5`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180099d85`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180099d85`

## string_xrefs

- `0x180099bd6`: `SvrImpl_FWDeleteCryptoSet`
- `0x180099bf5`: `SvrImpl_FWDeleteCryptoSet`
- `0x180099e8b`: `SvrImpl_FWDeleteCryptoSet`
- `0x180099e9a`: `SvrImpl_FWDeleteCryptoSet`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWDeleteCryptoSet(void *a1, __int64 a2, int a3, unsigned __int16 *a4)
{
  __int64 v5; // r15
  __int64 result; // rax
  int v9; // ebx
  int RPCClientSID; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // eax
  struct _tag_FW_BLOB_CONTAINER *v19; // rax
  unsigned int v20; // eax
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rdi
  unsigned int v23; // r8d
  unsigned __int16 *v24; // rdx
  wchar_t *v25; // rax
  unsigned __int16 *v26; // rsi
  int v27; // eax
  int v28; // r8d
  unsigned __int16 *v29; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-28h] BYREF
  wchar_t **v31; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v32; // [rsp+58h] [rbp-18h] BYREF

  v5 = a3;
  v31 = 0;
  v29 = 0;
  v32 = 0;
  v30 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 354, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWDeleteCryptoSet");
  if ( (int)result >= 0 )
  {
    v9 = FwLock();
    if ( v9 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWDeleteCryptoSet");
      return (unsigned int)v9;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v31);
    v11 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_46;
      v13 = 355;
      v14 = (unsigned int)RPCClientSID;
      goto LABEL_11;
    }
    FwGetRpcCallersProcessImageName(a1, &v32);
    if ( *(_DWORD *)(a2 + 24) == 2 )
    {
      if ( *(_DWORD *)(a2 + 16) != 2 && *(_DWORD *)(a2 + 16) != 5 )
      {
        v11 = -2147024846;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_46;
        v13 = 358;
        v14 = 2147942450LL;
LABEL_11:
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v14);
        goto LABEL_46;
      }
      if ( !(unsigned int)FwSetIsInUse(*(_QWORD *)(a2 + 8), 1, (unsigned int)v5, a4) )
      {
        if ( *(_QWORD *)a2
          && (FwGetSetName(*(_QWORD *)a2, 1, (unsigned int)v5, a4, &v29),
              v18 = FwDeleteSet(*(_QWORD *)a2, 1, (unsigned int)v5, a4),
              v11 = v18,
              v18 < 0) )
        {
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_46;
          v16 = 360;
        }
        else
        {
          if ( !v29 )
          {
            v19 = FwLookForBlobContainerWithID(
                    (struct _tag_FW_BLOB_MANIPULATOR *)&qword_1801247E0,
                    (struct _tag_FW_BLOB_REPO *)(*(_QWORD *)(a2 + 8) + 24 * (v5 + 7)),
                    a4);
            if ( v19 )
              FwStringCopy(*(_QWORD *)(*(_QWORD *)v19 + 24LL), &v29);
          }
          v18 = FwIncrmDeleteSet(*(_QWORD *)(a2 + 8), *(_DWORD *)(a2 + 16), 1, v5, a4, (__int64)&v30);
          v11 = v18;
          if ( v18 >= 0 )
          {
            FwAuditLogRuleChange((unsigned int)*v31, 0x7FFFFFFF, 3, 1, (__int64)a4, (__int64)v29);
            if ( !v30 && v29 )
              FwResolveIndirectString(&v29);
            goto LABEL_46;
          }
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          {
LABEL_46:
            FwUnlockInternal(a1, "SvrImpl_FWDeleteCryptoSet");
            FwReleaseRPCSharedLock("SvrImpl_FWDeleteCryptoSet");
            if ( (v11 & 0x80000000) == 0 )
              FwChangeSourceSignal();
            v20 = FwHResultToWindowsError(v11);
            v21 = v30;
            v22 = (unsigned __int16 *)&qword_1800F5F90;
            v23 = v20;
            if ( !v30 )
            {
              v21 = (unsigned __int16 *)&qword_1800F5F90;
              if ( v29 )
                v21 = v29;
            }
            v24 = (unsigned __int16 *)&qword_1800F5F90;
            if ( !a4 )
              a4 = (unsigned __int16 *)&qword_1800F5F90;
            if ( v32 )
              v24 = v32;
            if ( v31 )
              v25 = *v31;
            else
              v25 = L"S-1-0-0";
            FwEventCryptoSetDeleted(v25, v24, a4, v21, v5, v23);
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v26 = v30;
              if ( !v30 )
              {
                v26 = (unsigned __int16 *)&qword_1800F5F90;
                if ( v29 )
                  v26 = v29;
              }
              if ( v32 )
                v22 = v32;
              v27 = FwHResultToWindowsError(v11);
              WPP_SF_DSSSD(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                362,
                v28,
                v27,
                (__int64)v22,
                (__int64)a4,
                (__int64)v26,
                v5);
            }
            FwFree(v31);
            FwFree(v29);
            FwFree(v30);
            FwFree(v32);
            return FwHResultToWindowsError(v11);
          }
          v16 = 361;
        }
        v17 = (unsigned int)v18;
LABEL_20:
        WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v17);
        goto LABEL_46;
      }
      v11 = -2147022494;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_46;
      v16 = 359;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 356);
        v15 = WPP_GLOBAL_Control;
      }
      v11 = -2147024891;
      if ( (_UNKNOWN *)v15 == &WPP_GLOBAL_Control || (*(_BYTE *)(v15 + 28) & 1) == 0 )
        goto LABEL_46;
      v16 = 357;
    }
    v17 = v11;
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180099b5c  push    rbp
0x180099b5e  push    rbx
0x180099b5f  push    rsi
0x180099b60  push    rdi
0x180099b61  push    r12
0x180099b63  push    r14
0x180099b65  push    r15
0x180099b67  mov     rbp, rsp
0x180099b6a  sub     rsp, 70h
0x180099b6e  mov     rax, cs:__security_cookie
0x180099b75  xor     rax, rsp
0x180099b78  mov     [rbp+var_10], rax
0x180099b7c  mov     r14, r9
0x180099b7f  movsxd  r15, r8d
0x180099b82  mov     rsi, rdx
0x180099b85  mov     [rbp+var_20], 0
0x180099b8d  mov     r12, rcx
0x180099b90  mov     [rbp+var_30], 0
0x180099b98  mov     [rbp+var_18], 0
0x180099ba0  mov     [rbp+var_28], 0
0x180099ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180099baf  lea     rdi, WPP_GLOBAL_Control
0x180099bb6  cmp     rcx, rdi
0x180099bb9  jz      short loc_180099BD6
0x180099bbb  test    byte ptr [rcx+1Ch], 8
0x180099bbf  jz      short loc_180099BD6
0x180099bc1  mov     rcx, [rcx+10h]
0x180099bc5  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099bcc  mov     edx, 162h
0x180099bd1  call    WPP_SF_
0x180099bd6  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x180099bdd  call    FwAcquireRPCSharedLock
0x180099be2  test    eax, eax
0x180099be4  js      loc_180099FB3
0x180099bea  call    FwLock
0x180099bef  mov     ebx, eax
0x180099bf1  test    eax, eax
0x180099bf3  jns     short loc_180099C08
0x180099bf5  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x180099bfc  call    FwReleaseRPCSharedLock
0x180099c01  mov     eax, ebx
0x180099c03  jmp     loc_180099FB3
0x180099c08  lea     rdx, [rbp+var_20]
0x180099c0c  mov     rcx, r12
0x180099c0f  call    ExtractRPCClientSID
0x180099c14  mov     ebx, eax
0x180099c16  test    eax, eax
0x180099c18  jns     short loc_180099C56
0x180099c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c21  cmp     rcx, rdi
0x180099c24  jz      loc_180099E84
0x180099c2a  mov     edi, 1
0x180099c2f  test    [rcx+1Ch], dil
0x180099c33  jz      loc_180099E84
0x180099c39  mov     edx, 163h
0x180099c3e  mov     r9d, eax
0x180099c41  mov     rcx, [rcx+10h]
0x180099c45  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099c4c  call    WPP_SF_d
0x180099c51  jmp     loc_180099E84
0x180099c56  lea     rdx, [rbp+var_18]
0x180099c5a  mov     rcx, r12
0x180099c5d  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180099c63  mov     r9d, [rsi+18h]
0x180099c67  cmp     r9d, 2
0x180099c6b  jz      short loc_180099CD5
0x180099c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c74  lea     rsi, WPP_GLOBAL_Control
0x180099c7b  mov     edi, 1
0x180099c80  cmp     rcx, rsi
0x180099c83  jz      short loc_180099CA0
0x180099c85  test    [rcx+1Ch], dil
0x180099c89  jz      short loc_180099CA0
0x180099c8b  mov     rcx, [rcx+10h]
0x180099c8f  mov     edx, 164h
0x180099c94  call    WPP_SF_l
0x180099c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ca0  mov     ebx, 80070005h
0x180099ca5  cmp     rcx, rsi
0x180099ca8  jz      loc_180099E8B
0x180099cae  test    [rcx+1Ch], dil
0x180099cb2  jz      loc_180099E8B
0x180099cb8  mov     edx, 165h
0x180099cbd  mov     r9d, ebx
0x180099cc0  mov     rcx, [rcx+10h]
0x180099cc4  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099ccb  call    WPP_SF_d
0x180099cd0  jmp     loc_180099E8B
0x180099cd5  cmp     dword ptr [rsi+10h], 2
0x180099cd9  jz      short loc_180099D12
0x180099cdb  cmp     dword ptr [rsi+10h], 5
0x180099cdf  jz      short loc_180099D12
0x180099ce1  mov     ebx, 80070032h
0x180099ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ced  cmp     rcx, rdi
0x180099cf0  jz      loc_180099E84
0x180099cf6  mov     edi, 1
0x180099cfb  test    [rcx+1Ch], dil
0x180099cff  jz      loc_180099E84
0x180099d05  mov     edx, 166h
0x180099d0a  mov     r9d, ebx
0x180099d0d  jmp     loc_180099C41
0x180099d12  mov     rcx, [rsi+8]
0x180099d16  mov     edi, 1
0x180099d1b  mov     edx, edi
0x180099d1d  mov     r9, r14
0x180099d20  mov     r8d, r15d
0x180099d23  call    FwSetIsInUse
0x180099d28  test    eax, eax
0x180099d2a  jz      short loc_180099D5C
0x180099d2c  mov     ebx, 80070962h
0x180099d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d38  lea     rsi, WPP_GLOBAL_Control
0x180099d3f  cmp     rcx, rsi
0x180099d42  jz      loc_180099E8B
0x180099d48  test    [rcx+1Ch], dil
0x180099d4c  jz      loc_180099E8B
0x180099d52  mov     edx, 167h
0x180099d57  jmp     loc_180099CBD
0x180099d5c  mov     rcx, [rsi]
0x180099d5f  test    rcx, rcx
0x180099d62  jz      short loc_180099DBF
0x180099d64  lea     rax, [rbp+var_30]
0x180099d68  mov     r9, r14
0x180099d6b  mov     r8d, r15d
0x180099d6e  mov     [rsp+70h+lpString2], rax
0x180099d73  mov     edx, edi
0x180099d75  call    ?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z; FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)
0x180099d7a  mov     rcx, [rsi]
0x180099d7d  mov     r9, r14
0x180099d80  mov     r8d, r15d
0x180099d83  mov     edx, edi
0x180099d85  call    cs:__imp_FwDeleteSet
0x180099d8b  mov     ebx, eax
0x180099d8d  test    eax, eax
0x180099d8f  jns     short loc_180099DBF
0x180099d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d98  lea     rsi, WPP_GLOBAL_Control
0x180099d9f  cmp     rcx, rsi
0x180099da2  jz      loc_180099E8B
0x180099da8  test    [rcx+1Ch], dil
0x180099dac  jz      loc_180099E8B
0x180099db2  mov     edx, 168h
0x180099db7  mov     r9d, eax
0x180099dba  jmp     loc_180099CC0
0x180099dbf  cmp     [rbp+var_30], 0
0x180099dc4  jnz     short loc_180099DFB
0x180099dc6  lea     rax, [r15+7]
0x180099dca  mov     r8, r14; unsigned __int16 *
0x180099dcd  lea     rcx, [rax+rax*2]
0x180099dd1  mov     rax, [rsi+8]
0x180099dd5  lea     rdx, [rax+rcx*8]; struct _tag_FW_BLOB_REPO *
0x180099dd9  lea     rcx, qword_1801247E0; struct _tag_FW_BLOB_MANIPULATOR *
0x180099de0  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x180099de5  test    rax, rax
0x180099de8  jz      short loc_180099DFB
0x180099dea  mov     rcx, [rax]
0x180099ded  lea     rdx, [rbp+var_30]
0x180099df1  mov     rcx, [rcx+18h]
0x180099df5  call    cs:__imp_FwStringCopy
0x180099dfb  mov     edx, [rsi+10h]; int
0x180099dfe  lea     rax, [rbp+var_28]
0x180099e02  mov     rcx, [rsi+8]; int
0x180099e06  mov     r9d, r15d; int
0x180099e09  mov     qword ptr [rsp+70h+var_48], rax; __int64
0x180099e0e  mov     r8d, edi; int
0x180099e11  mov     [rsp+70h+lpString2], r14; lpString2
0x180099e16  call    FwIncrmDeleteSet
0x180099e1b  mov     ebx, eax
0x180099e1d  test    eax, eax
0x180099e1f  jns     short loc_180099E44
0x180099e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e28  lea     rsi, WPP_GLOBAL_Control
0x180099e2f  cmp     rcx, rsi
0x180099e32  jz      short loc_180099E8B
0x180099e34  test    [rcx+1Ch], dil
0x180099e38  jz      short loc_180099E8B
0x180099e3a  mov     edx, 169h
0x180099e3f  jmp     loc_180099DB7
0x180099e44  mov     rcx, [rbp+var_20]
0x180099e48  mov     r9d, edi
0x180099e4b  mov     rax, [rbp+var_30]
0x180099e4f  mov     edx, 7FFFFFFFh
0x180099e54  mov     qword ptr [rsp+70h+var_48], rax
0x180099e59  mov     r8d, 3
0x180099e5f  mov     [rsp+70h+lpString2], r14
0x180099e64  mov     rcx, [rcx]
0x180099e67  call    FwAuditLogRuleChange
0x180099e6c  cmp     [rbp+var_28], 0
0x180099e71  jnz     short loc_180099E84
0x180099e73  cmp     [rbp+var_30], 0
0x180099e78  jz      short loc_180099E84
0x180099e7a  lea     rcx, [rbp+var_30]
0x180099e7e  call    cs:__imp_FwResolveIndirectString
0x180099e84  lea     rsi, WPP_GLOBAL_Control
0x180099e8b  lea     rdx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x180099e92  mov     rcx, r12; void *
0x180099e95  call    FwUnlockInternal
0x180099e9a  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x180099ea1  call    FwReleaseRPCSharedLock
0x180099ea6  test    ebx, ebx
0x180099ea8  js      short loc_180099EB0
0x180099eaa  call    cs:__imp_FwChangeSourceSignal
0x180099eb0  mov     ecx, ebx
0x180099eb2  call    cs:__imp_FwHResultToWindowsError
0x180099eb8  mov     rcx, [rbp+var_28]
0x180099ebc  lea     rdi, qword_1800F5F90
0x180099ec3  mov     r8d, eax
0x180099ec6  test    rcx, rcx
0x180099ec9  jnz     short loc_180099ED9
0x180099ecb  mov     rax, [rbp+var_30]
0x180099ecf  mov     rcx, rdi
0x180099ed2  test    rax, rax
0x180099ed5  cmovnz  rcx, rax
0x180099ed9  mov     rax, [rbp+var_18]
0x180099edd  test    r14, r14
0x180099ee0  mov     rdx, rdi
0x180099ee3  cmovz   r14, rdi
0x180099ee7  test    rax, rax
0x180099eea  cmovnz  rdx, rax; unsigned __int16 *
0x180099eee  mov     rax, [rbp+var_20]
0x180099ef2  test    rax, rax
0x180099ef5  jz      short loc_180099EFC
0x180099ef7  mov     rax, [rax]
0x180099efa  jmp     short loc_180099F03
0x180099efc  lea     rax, aS100; "S-1-0-0"
0x180099f03  mov     [rsp+70h+var_48], r8d; unsigned int
0x180099f08  mov     r9, rcx; unsigned __int16 *
0x180099f0b  mov     r8, r14; unsigned __int16 *
0x180099f0e  mov     dword ptr [rsp+70h+lpString2], r15d; int
0x180099f13  mov     rcx, rax; void *
0x180099f16  call    FwEventCryptoSetDeleted
0x180099f1b  mov     rax, cs:WPP_GLOBAL_Control
0x180099f22  cmp     rax, rsi
0x180099f25  jz      short loc_180099F83
0x180099f27  test    byte ptr [rax+1Ch], 4
0x180099f2b  jz      short loc_180099F83
0x180099f2d  mov     rsi, [rbp+var_28]
0x180099f31  test    rsi, rsi
0x180099f34  jnz     short loc_180099F44
0x180099f36  mov     rax, [rbp+var_30]
0x180099f3a  mov     rsi, rdi
0x180099f3d  test    rax, rax
0x180099f40  cmovnz  rsi, rax
0x180099f44  mov     rax, [rbp+var_18]
0x180099f48  mov     ecx, ebx
0x180099f4a  test    rax, rax
0x180099f4d  cmovnz  rdi, rax
0x180099f51  call    cs:__imp_FwHResultToWindowsError
0x180099f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f5e  mov     edx, 16Ah
0x180099f63  mov     [rsp+70h+var_38], r15d
0x180099f68  mov     r9d, eax
0x180099f6b  mov     [rsp+70h+var_40], rsi
0x180099f70  mov     qword ptr [rsp+70h+var_48], r14
0x180099f75  mov     rcx, [rcx+10h]
0x180099f79  mov     [rsp+70h+lpString2], rdi
0x180099f7e  call    WPP_SF_DSSSD
0x180099f83  mov     rcx, [rbp+var_20]
0x180099f87  call    cs:__imp_FwFree
0x180099f8d  mov     rcx, [rbp+var_30]
0x180099f91  call    cs:__imp_FwFree
0x180099f97  mov     rcx, [rbp+var_28]
0x180099f9b  call    cs:__imp_FwFree
0x180099fa1  mov     rcx, [rbp+var_18]
0x180099fa5  call    cs:__imp_FwFree
0x180099fab  mov     ecx, ebx
0x180099fad  call    cs:__imp_FwHResultToWindowsError
0x180099fb3  mov     rcx, [rbp+var_10]
0x180099fb7  xor     rcx, rsp; StackCookie
0x180099fba  call    __security_check_cookie
0x180099fbf  add     rsp, 70h
0x180099fc3  pop     r15
0x180099fc5  pop     r14
0x180099fc7  pop     r12
0x180099fc9  pop     rdi
0x180099fca  pop     rsi
0x180099fcb  pop     rbx
0x180099fcc  pop     rbp
0x180099fcd  retn
```
