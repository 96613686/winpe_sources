# SvrImpl_FWDeleteCryptoSet(void *,void *,_tag_FW_IPSEC_PHASE,ushort const *)

- ea: `0x18009edb8`
- end: `0x18009f273`
- name: `?SvrImpl_FWDeleteCryptoSet@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@PEBG@Z`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c7af0`

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
- `0x1800715c4`
- `0x1800729c0`
- `0x18008cc98`
- `0x18008eb78`
- `0x18009a1e0`
- `0x18009edb8`
- `0x1800a7300`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009f12c`
- `fwbase!FwHResultToWindowsError` at `0x18009f1d1`
- `fwbase!FwHResultToWindowsError` at `0x18009f24b`
- `fwbase!FwHResultToWindowsError` at `0x18009f12c`
- `fwbase!FwHResultToWindowsError` at `0x18009f1d1`
- `fwbase!FwHResultToWindowsError` at `0x18009f24b`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009eeb9`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009eeb9`
- `fwbase!FwResolveIndirectString` at `0x18009f0ec`
- `fwbase!FwResolveIndirectString` at `0x18009f0ec`
- `fwbase!FwChangeSourceSignal` at `0x18009f11e`
- `fwbase!FwChangeSourceSignal` at `0x18009f11e`
- `fwbase!FwStringCopy` at `0x18009f05d`
- `fwbase!FwStringCopy` at `0x18009f05d`
- `fwbase!FwFree` at `0x18009f20d`
- `fwbase!FwFree` at `0x18009f21d`
- `fwbase!FwFree` at `0x18009f22d`
- `fwbase!FwFree` at `0x18009f23d`
- `fwbase!FwFree` at `0x18009f20d`
- `fwbase!FwFree` at `0x18009f21d`
- `fwbase!FwFree` at `0x18009f22d`
- `fwbase!FwFree` at `0x18009f23d`
- `FWPolicyIOMgr!FwDeleteSet` at `0x18009efe7`
- `FWPolicyIOMgr!FwDeleteSet` at `0x18009efe7`

## string_xrefs

- `0x18009ee32`: `SvrImpl_FWDeleteCryptoSet`
- `0x18009ee51`: `SvrImpl_FWDeleteCryptoSet`
- `0x18009f0ff`: `SvrImpl_FWDeleteCryptoSet`
- `0x18009f10e`: `SvrImpl_FWDeleteCryptoSet`

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
  char v20; // al
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rdi
  char v23; // r8
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 354, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v14);
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
                    (struct _tag_FW_BLOB_MANIPULATOR *)&qword_18012A7E0,
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
            v22 = (unsigned __int16 *)&qword_1800FBFF0;
            v23 = v20;
            if ( !v30 )
            {
              v21 = (unsigned __int16 *)&qword_1800FBFF0;
              if ( v29 )
                v21 = v29;
            }
            v24 = (unsigned __int16 *)&qword_1800FBFF0;
            if ( !a4 )
              a4 = (unsigned __int16 *)&qword_1800FBFF0;
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
                v26 = (unsigned __int16 *)&qword_1800FBFF0;
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
        WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v17);
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
0x18009edb8  push    rbp
0x18009edba  push    rbx
0x18009edbb  push    rsi
0x18009edbc  push    rdi
0x18009edbd  push    r12
0x18009edbf  push    r14
0x18009edc1  push    r15
0x18009edc3  mov     rbp, rsp
0x18009edc6  sub     rsp, 70h
0x18009edca  mov     rax, cs:__security_cookie
0x18009edd1  xor     rax, rsp
0x18009edd4  mov     [rbp+var_10], rax
0x18009edd8  mov     r14, r9
0x18009eddb  movsxd  r15, r8d
0x18009edde  mov     rsi, rdx
0x18009ede1  mov     [rbp+var_20], 0
0x18009ede9  mov     r12, rcx
0x18009edec  mov     [rbp+var_30], 0
0x18009edf4  mov     [rbp+var_18], 0
0x18009edfc  mov     [rbp+var_28], 0
0x18009ee04  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ee0b  lea     rdi, WPP_GLOBAL_Control
0x18009ee12  cmp     rcx, rdi
0x18009ee15  jz      short loc_18009EE32
0x18009ee17  test    byte ptr [rcx+1Ch], 8
0x18009ee1b  jz      short loc_18009EE32
0x18009ee1d  mov     rcx, [rcx+10h]
0x18009ee21  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009ee28  mov     edx, 162h
0x18009ee2d  call    WPP_SF_
0x18009ee32  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x18009ee39  call    FwAcquireRPCSharedLock
0x18009ee3e  test    eax, eax
0x18009ee40  js      loc_18009F257
0x18009ee46  call    FwLock
0x18009ee4b  mov     ebx, eax
0x18009ee4d  test    eax, eax
0x18009ee4f  jns     short loc_18009EE64
0x18009ee51  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x18009ee58  call    FwReleaseRPCSharedLock
0x18009ee5d  mov     eax, ebx
0x18009ee5f  jmp     loc_18009F257
0x18009ee64  lea     rdx, [rbp+var_20]
0x18009ee68  mov     rcx, r12
0x18009ee6b  call    ExtractRPCClientSID
0x18009ee70  mov     ebx, eax
0x18009ee72  test    eax, eax
0x18009ee74  jns     short loc_18009EEB2
0x18009ee76  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ee7d  cmp     rcx, rdi
0x18009ee80  jz      loc_18009F0F8
0x18009ee86  mov     edi, 1
0x18009ee8b  test    [rcx+1Ch], dil
0x18009ee8f  jz      loc_18009F0F8
0x18009ee95  mov     edx, 163h
0x18009ee9a  mov     r9d, eax
0x18009ee9d  mov     rcx, [rcx+10h]
0x18009eea1  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009eea8  call    WPP_SF_d
0x18009eead  jmp     loc_18009F0F8
0x18009eeb2  lea     rdx, [rbp+var_18]
0x18009eeb6  mov     rcx, r12
0x18009eeb9  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009eec0  nop     dword ptr [rax+rax+00h]
0x18009eec5  mov     r9d, [rsi+18h]
0x18009eec9  cmp     r9d, 2
0x18009eecd  jz      short loc_18009EF37
0x18009eecf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eed6  lea     rsi, WPP_GLOBAL_Control
0x18009eedd  mov     edi, 1
0x18009eee2  cmp     rcx, rsi
0x18009eee5  jz      short loc_18009EF02
0x18009eee7  test    [rcx+1Ch], dil
0x18009eeeb  jz      short loc_18009EF02
0x18009eeed  mov     rcx, [rcx+10h]
0x18009eef1  mov     edx, 164h
0x18009eef6  call    WPP_SF_l
0x18009eefb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ef02  mov     ebx, 80070005h
0x18009ef07  cmp     rcx, rsi
0x18009ef0a  jz      loc_18009F0FF
0x18009ef10  test    [rcx+1Ch], dil
0x18009ef14  jz      loc_18009F0FF
0x18009ef1a  mov     edx, 165h
0x18009ef1f  mov     r9d, ebx
0x18009ef22  mov     rcx, [rcx+10h]
0x18009ef26  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x18009ef2d  call    WPP_SF_d
0x18009ef32  jmp     loc_18009F0FF
0x18009ef37  cmp     dword ptr [rsi+10h], 2
0x18009ef3b  jz      short loc_18009EF74
0x18009ef3d  cmp     dword ptr [rsi+10h], 5
0x18009ef41  jz      short loc_18009EF74
0x18009ef43  mov     ebx, 80070032h
0x18009ef48  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ef4f  cmp     rcx, rdi
0x18009ef52  jz      loc_18009F0F8
0x18009ef58  mov     edi, 1
0x18009ef5d  test    [rcx+1Ch], dil
0x18009ef61  jz      loc_18009F0F8
0x18009ef67  mov     edx, 166h
0x18009ef6c  mov     r9d, ebx
0x18009ef6f  jmp     loc_18009EE9D
0x18009ef74  mov     rcx, [rsi+8]
0x18009ef78  mov     edi, 1
0x18009ef7d  mov     edx, edi
0x18009ef7f  mov     r9, r14
0x18009ef82  mov     r8d, r15d
0x18009ef85  call    FwSetIsInUse
0x18009ef8a  test    eax, eax
0x18009ef8c  jz      short loc_18009EFBE
0x18009ef8e  mov     ebx, 80070962h
0x18009ef93  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ef9a  lea     rsi, WPP_GLOBAL_Control
0x18009efa1  cmp     rcx, rsi
0x18009efa4  jz      loc_18009F0FF
0x18009efaa  test    [rcx+1Ch], dil
0x18009efae  jz      loc_18009F0FF
0x18009efb4  mov     edx, 167h
0x18009efb9  jmp     loc_18009EF1F
0x18009efbe  mov     rcx, [rsi]
0x18009efc1  test    rcx, rcx
0x18009efc4  jz      short loc_18009F027
0x18009efc6  lea     rax, [rbp+var_30]
0x18009efca  mov     r9, r14
0x18009efcd  mov     r8d, r15d
0x18009efd0  mov     [rsp+70h+lpString2], rax
0x18009efd5  mov     edx, edi
0x18009efd7  call    ?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z; FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)
0x18009efdc  mov     rcx, [rsi]
0x18009efdf  mov     r9, r14
0x18009efe2  mov     r8d, r15d
0x18009efe5  mov     edx, edi
0x18009efe7  call    cs:__imp_FwDeleteSet
0x18009efee  nop     dword ptr [rax+rax+00h]
0x18009eff3  mov     ebx, eax
0x18009eff5  test    eax, eax
0x18009eff7  jns     short loc_18009F027
0x18009eff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f000  lea     rsi, WPP_GLOBAL_Control
0x18009f007  cmp     rcx, rsi
0x18009f00a  jz      loc_18009F0FF
0x18009f010  test    [rcx+1Ch], dil
0x18009f014  jz      loc_18009F0FF
0x18009f01a  mov     edx, 168h
0x18009f01f  mov     r9d, eax
0x18009f022  jmp     loc_18009EF22
0x18009f027  cmp     [rbp+var_30], 0
0x18009f02c  jnz     short loc_18009F069
0x18009f02e  lea     rax, [r15+7]
0x18009f032  mov     r8, r14; unsigned __int16 *
0x18009f035  lea     rcx, [rax+rax*2]
0x18009f039  mov     rax, [rsi+8]
0x18009f03d  lea     rdx, [rax+rcx*8]; struct _tag_FW_BLOB_REPO *
0x18009f041  lea     rcx, qword_18012A7E0; struct _tag_FW_BLOB_MANIPULATOR *
0x18009f048  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009f04d  test    rax, rax
0x18009f050  jz      short loc_18009F069
0x18009f052  mov     rcx, [rax]
0x18009f055  lea     rdx, [rbp+var_30]
0x18009f059  mov     rcx, [rcx+18h]
0x18009f05d  call    cs:__imp_FwStringCopy
0x18009f064  nop     dword ptr [rax+rax+00h]
0x18009f069  mov     edx, [rsi+10h]; int
0x18009f06c  lea     rax, [rbp+var_28]
0x18009f070  mov     rcx, [rsi+8]; int
0x18009f074  mov     r9d, r15d; int
0x18009f077  mov     qword ptr [rsp+70h+var_48], rax; __int64
0x18009f07c  mov     r8d, edi; int
0x18009f07f  mov     [rsp+70h+lpString2], r14; lpString2
0x18009f084  call    FwIncrmDeleteSet
0x18009f089  mov     ebx, eax
0x18009f08b  test    eax, eax
0x18009f08d  jns     short loc_18009F0B2
0x18009f08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f096  lea     rsi, WPP_GLOBAL_Control
0x18009f09d  cmp     rcx, rsi
0x18009f0a0  jz      short loc_18009F0FF
0x18009f0a2  test    [rcx+1Ch], dil
0x18009f0a6  jz      short loc_18009F0FF
0x18009f0a8  mov     edx, 169h
0x18009f0ad  jmp     loc_18009F01F
0x18009f0b2  mov     rcx, [rbp+var_20]
0x18009f0b6  mov     r9d, edi
0x18009f0b9  mov     rax, [rbp+var_30]
0x18009f0bd  mov     edx, 7FFFFFFFh
0x18009f0c2  mov     qword ptr [rsp+70h+var_48], rax
0x18009f0c7  mov     r8d, 3
0x18009f0cd  mov     [rsp+70h+lpString2], r14
0x18009f0d2  mov     rcx, [rcx]
0x18009f0d5  call    FwAuditLogRuleChange
0x18009f0da  cmp     [rbp+var_28], 0
0x18009f0df  jnz     short loc_18009F0F8
0x18009f0e1  cmp     [rbp+var_30], 0
0x18009f0e6  jz      short loc_18009F0F8
0x18009f0e8  lea     rcx, [rbp+var_30]
0x18009f0ec  call    cs:__imp_FwResolveIndirectString
0x18009f0f3  nop     dword ptr [rax+rax+00h]
0x18009f0f8  lea     rsi, WPP_GLOBAL_Control
0x18009f0ff  lea     rdx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x18009f106  mov     rcx, r12; void *
0x18009f109  call    FwUnlockInternal
0x18009f10e  lea     rcx, aSvrimplFwdelet; "SvrImpl_FWDeleteCryptoSet"
0x18009f115  call    FwReleaseRPCSharedLock
0x18009f11a  test    ebx, ebx
0x18009f11c  js      short loc_18009F12A
0x18009f11e  call    cs:__imp_FwChangeSourceSignal
0x18009f125  nop     dword ptr [rax+rax+00h]
0x18009f12a  mov     ecx, ebx
0x18009f12c  call    cs:__imp_FwHResultToWindowsError
0x18009f133  nop     dword ptr [rax+rax+00h]
0x18009f138  mov     rcx, [rbp+var_28]
0x18009f13c  lea     rdi, qword_1800FBFF0
0x18009f143  mov     r8d, eax
0x18009f146  test    rcx, rcx
0x18009f149  jnz     short loc_18009F159
0x18009f14b  mov     rax, [rbp+var_30]
0x18009f14f  mov     rcx, rdi
0x18009f152  test    rax, rax
0x18009f155  cmovnz  rcx, rax
0x18009f159  mov     rax, [rbp+var_18]
0x18009f15d  test    r14, r14
0x18009f160  mov     rdx, rdi
0x18009f163  cmovz   r14, rdi
0x18009f167  test    rax, rax
0x18009f16a  cmovnz  rdx, rax; unsigned __int16 *
0x18009f16e  mov     rax, [rbp+var_20]
0x18009f172  test    rax, rax
0x18009f175  jz      short loc_18009F17C
0x18009f177  mov     rax, [rax]
0x18009f17a  jmp     short loc_18009F183
0x18009f17c  lea     rax, aS100; "S-1-0-0"
0x18009f183  mov     dword ptr [rsp+70h+var_48], r8d; char
0x18009f188  mov     r9, rcx; unsigned __int16 *
0x18009f18b  mov     r8, r14; unsigned __int16 *
0x18009f18e  mov     dword ptr [rsp+70h+lpString2], r15d; int
0x18009f193  mov     rcx, rax; void *
0x18009f196  call    FwEventCryptoSetDeleted
0x18009f19b  mov     rax, cs:WPP_GLOBAL_Control
0x18009f1a2  cmp     rax, rsi
0x18009f1a5  jz      short loc_18009F209
0x18009f1a7  test    byte ptr [rax+1Ch], 4
0x18009f1ab  jz      short loc_18009F209
0x18009f1ad  mov     rsi, [rbp+var_28]
0x18009f1b1  test    rsi, rsi
0x18009f1b4  jnz     short loc_18009F1C4
0x18009f1b6  mov     rax, [rbp+var_30]
0x18009f1ba  mov     rsi, rdi
0x18009f1bd  test    rax, rax
0x18009f1c0  cmovnz  rsi, rax
0x18009f1c4  mov     rax, [rbp+var_18]
0x18009f1c8  mov     ecx, ebx
0x18009f1ca  test    rax, rax
0x18009f1cd  cmovnz  rdi, rax
0x18009f1d1  call    cs:__imp_FwHResultToWindowsError
0x18009f1d8  nop     dword ptr [rax+rax+00h]
0x18009f1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f1e4  mov     edx, 16Ah
0x18009f1e9  mov     [rsp+70h+var_38], r15d
0x18009f1ee  mov     r9d, eax
0x18009f1f1  mov     [rsp+70h+var_40], rsi
0x18009f1f6  mov     qword ptr [rsp+70h+var_48], r14
0x18009f1fb  mov     rcx, [rcx+10h]
0x18009f1ff  mov     [rsp+70h+lpString2], rdi
0x18009f204  call    WPP_SF_DSSSD
0x18009f209  mov     rcx, [rbp+var_20]
0x18009f20d  call    cs:__imp_FwFree
0x18009f214  nop     dword ptr [rax+rax+00h]
0x18009f219  mov     rcx, [rbp+var_30]
0x18009f21d  call    cs:__imp_FwFree
0x18009f224  nop     dword ptr [rax+rax+00h]
0x18009f229  mov     rcx, [rbp+var_28]
0x18009f22d  call    cs:__imp_FwFree
0x18009f234  nop     dword ptr [rax+rax+00h]
0x18009f239  mov     rcx, [rbp+var_18]
0x18009f23d  call    cs:__imp_FwFree
0x18009f244  nop     dword ptr [rax+rax+00h]
0x18009f249  mov     ecx, ebx
0x18009f24b  call    cs:__imp_FwHResultToWindowsError
0x18009f252  nop     dword ptr [rax+rax+00h]
0x18009f257  mov     rcx, [rbp+var_10]
0x18009f25b  xor     rcx, rsp; StackCookie
0x18009f25e  call    __security_check_cookie
0x18009f263  add     rsp, 70h
0x18009f267  pop     r15
0x18009f269  pop     r14
0x18009f26b  pop     r12
0x18009f26d  pop     rdi
0x18009f26e  pop     rsi
0x18009f26f  pop     rbx
0x18009f270  pop     rbp
0x18009f271  retn
```
