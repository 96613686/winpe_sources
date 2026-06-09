# SvrImpl_FWDeleteAuthenticationSet(void *,void *,_tag_FW_IPSEC_PHASE,ushort const *)

- ea: `0x18009934c`
- end: `0x180099768`
- name: `?SvrImpl_FWDeleteAuthenticationSet@@YAKPEAX0W4_tag_FW_IPSEC_PHASE@@PEBG@Z`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c0ab0`

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
- `0x18006f520`
- `0x180088554`
- `0x18008a390`
- `0x18008af7c`
- `0x180095308`
- `0x18009934c`
- `0x1800a1b4c`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099448`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180099448`
- `fwbase!FwResolveIndirectString` at `0x180099620`
- `fwbase!FwResolveIndirectString` at `0x180099620`
- `fwbase!FwChangeSourceSignal` at `0x180099645`
- `fwbase!FwChangeSourceSignal` at `0x180099645`
- `fwbase!FwHResultToWindowsError` at `0x18009964d`
- `fwbase!FwHResultToWindowsError` at `0x1800996eb`
- `fwbase!FwHResultToWindowsError` at `0x180099747`
- `fwbase!FwHResultToWindowsError` at `0x18009964d`
- `fwbase!FwHResultToWindowsError` at `0x1800996eb`
- `fwbase!FwHResultToWindowsError` at `0x180099747`
- `fwbase!FwStringCopy` at `0x18009959d`
- `fwbase!FwStringCopy` at `0x18009959d`
- `fwbase!FwFree` at `0x180099721`
- `fwbase!FwFree` at `0x18009972b`
- `fwbase!FwFree` at `0x180099735`
- `fwbase!FwFree` at `0x18009973f`
- `fwbase!FwFree` at `0x180099721`
- `fwbase!FwFree` at `0x18009972b`
- `fwbase!FwFree` at `0x180099735`
- `fwbase!FwFree` at `0x18009973f`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180099537`
- `FWPolicyIOMgr!FwDeleteSet` at `0x180099537`

## string_xrefs

- `0x1800993c6`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x1800993e5`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x180099626`: `SvrImpl_FWDeleteAuthenticationSet`
- `0x180099635`: `SvrImpl_FWDeleteAuthenticationSet`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 297, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
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
      WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v14);
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
                      (struct _tag_FW_BLOB_MANIPULATOR *)&qword_1801247B0,
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
              v18 = &qword_1800F5F90;
              if ( !v25 )
              {
                v17 = &qword_1800F5F90;
                if ( v24 )
                  v17 = v24;
              }
              v19 = &qword_1800F5F90;
              if ( !a4 )
                a4 = &qword_1800F5F90;
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
                  v21 = &qword_1800F5F90;
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
0x18009934c  push    rbp
0x18009934e  push    rbx
0x18009934f  push    rsi
0x180099350  push    rdi
0x180099351  push    r13
0x180099353  push    r14
0x180099355  push    r15
0x180099357  mov     rbp, rsp
0x18009935a  sub     rsp, 70h
0x18009935e  mov     rax, cs:__security_cookie
0x180099365  xor     rax, rsp
0x180099368  mov     [rbp+var_10], rax
0x18009936c  mov     r14, r9
0x18009936f  movsxd  r15, r8d
0x180099372  mov     rdi, rdx
0x180099375  mov     [rbp+var_20], 0
0x18009937d  mov     rsi, rcx
0x180099380  mov     [rbp+var_30], 0
0x180099388  mov     [rbp+var_18], 0
0x180099390  mov     [rbp+var_28], 0
0x180099398  mov     rcx, cs:WPP_GLOBAL_Control
0x18009939f  lea     r13, WPP_GLOBAL_Control
0x1800993a6  cmp     rcx, r13
0x1800993a9  jz      short loc_1800993C6
0x1800993ab  test    byte ptr [rcx+1Ch], 8
0x1800993af  jz      short loc_1800993C6
0x1800993b1  mov     rcx, [rcx+10h]
0x1800993b5  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800993bc  mov     edx, 129h
0x1800993c1  call    WPP_SF_
0x1800993c6  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x1800993cd  call    FwAcquireRPCSharedLock
0x1800993d2  test    eax, eax
0x1800993d4  js      loc_18009974D
0x1800993da  call    FwLock
0x1800993df  mov     ebx, eax
0x1800993e1  test    eax, eax
0x1800993e3  jns     short loc_1800993F8
0x1800993e5  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x1800993ec  call    FwReleaseRPCSharedLock
0x1800993f1  mov     eax, ebx
0x1800993f3  jmp     loc_18009974D
0x1800993f8  lea     rdx, [rbp+var_20]
0x1800993fc  mov     rcx, rsi
0x1800993ff  call    ExtractRPCClientSID
0x180099404  mov     ebx, eax
0x180099406  test    eax, eax
0x180099408  jns     short loc_180099441
0x18009940a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099411  cmp     rcx, r13
0x180099414  jz      loc_180099626
0x18009941a  test    byte ptr [rcx+1Ch], 1
0x18009941e  jz      loc_180099626
0x180099424  mov     edx, 12Ah
0x180099429  mov     r9d, eax
0x18009942c  mov     rcx, [rcx+10h]
0x180099430  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180099437  call    WPP_SF_d
0x18009943c  jmp     loc_180099626
0x180099441  lea     rdx, [rbp+var_18]
0x180099445  mov     rcx, rsi
0x180099448  call    cs:__imp_FwGetRpcCallersProcessImageName
0x18009944e  mov     r9d, [rdi+18h]
0x180099452  cmp     r9d, 2
0x180099456  jz      short loc_1800994A1
0x180099458  mov     rcx, cs:WPP_GLOBAL_Control
0x18009945f  cmp     rcx, r13
0x180099462  jz      short loc_18009947F
0x180099464  test    byte ptr [rcx+1Ch], 1
0x180099468  jz      short loc_18009947F
0x18009946a  mov     rcx, [rcx+10h]
0x18009946e  mov     edx, 12Bh
0x180099473  call    WPP_SF_l
0x180099478  mov     rcx, cs:WPP_GLOBAL_Control
0x18009947f  mov     ebx, 80070005h
0x180099484  cmp     rcx, r13
0x180099487  jz      loc_180099626
0x18009948d  test    byte ptr [rcx+1Ch], 1
0x180099491  jz      loc_180099626
0x180099497  mov     edx, 12Ch
0x18009949c  mov     r9d, ebx
0x18009949f  jmp     short loc_18009942C
0x1800994a1  cmp     dword ptr [rdi+10h], 2
0x1800994a5  jz      short loc_1800994D3
0x1800994a7  cmp     dword ptr [rdi+10h], 5
0x1800994ab  jz      short loc_1800994D3
0x1800994ad  mov     ebx, 80070032h
0x1800994b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800994b9  cmp     rcx, r13
0x1800994bc  jz      loc_180099626
0x1800994c2  test    byte ptr [rcx+1Ch], 1
0x1800994c6  jz      loc_180099626
0x1800994cc  mov     edx, 12Dh
0x1800994d1  jmp     short loc_18009949C
0x1800994d3  mov     rcx, [rdi+8]
0x1800994d7  mov     r9, r14
0x1800994da  mov     r8d, r15d
0x1800994dd  xor     edx, edx
0x1800994df  call    FwSetIsInUse
0x1800994e4  test    eax, eax
0x1800994e6  jz      short loc_18009950E
0x1800994e8  mov     ebx, 80070962h
0x1800994ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800994f4  cmp     rcx, r13
0x1800994f7  jz      loc_180099626
0x1800994fd  test    byte ptr [rcx+1Ch], 1
0x180099501  jz      loc_180099626
0x180099507  mov     edx, 12Eh
0x18009950c  jmp     short loc_18009949C
0x18009950e  mov     rcx, [rdi]
0x180099511  test    rcx, rcx
0x180099514  jz      short loc_180099567
0x180099516  lea     rax, [rbp+var_30]
0x18009951a  mov     r9, r14
0x18009951d  mov     r8d, r15d
0x180099520  mov     [rsp+70h+lpString2], rax
0x180099525  xor     edx, edx
0x180099527  call    ?FwGetSetName@@YAJPEAXW4FW_SET_TYPE@@W4_tag_FW_IPSEC_PHASE@@PEBGPEAPEAG@Z; FwGetSetName(void *,FW_SET_TYPE,_tag_FW_IPSEC_PHASE,ushort const *,ushort * *)
0x18009952c  mov     rcx, [rdi]
0x18009952f  mov     r9, r14
0x180099532  mov     r8d, r15d
0x180099535  xor     edx, edx
0x180099537  call    cs:__imp_FwDeleteSet
0x18009953d  mov     ebx, eax
0x18009953f  test    eax, eax
0x180099541  jns     short loc_180099567
0x180099543  mov     rcx, cs:WPP_GLOBAL_Control
0x18009954a  cmp     rcx, r13
0x18009954d  jz      loc_180099626
0x180099553  test    byte ptr [rcx+1Ch], 1
0x180099557  jz      loc_180099626
0x18009955d  mov     edx, 12Fh
0x180099562  jmp     loc_180099429
0x180099567  cmp     [rbp+var_30], 0
0x18009956c  jnz     short loc_1800995A3
0x18009956e  lea     rax, [r15+4]
0x180099572  mov     r8, r14; unsigned __int16 *
0x180099575  lea     rcx, [rax+rax*2]
0x180099579  mov     rax, [rdi+8]
0x18009957d  lea     rdx, [rax+rcx*8]; struct _tag_FW_BLOB_REPO *
0x180099581  lea     rcx, qword_1801247B0; struct _tag_FW_BLOB_MANIPULATOR *
0x180099588  call    ?FwLookForBlobContainerWithID@@YAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@PEAU_tag_FW_BLOB_REPO@@PEBG@Z; FwLookForBlobContainerWithID(_tag_FW_BLOB_MANIPULATOR *,_tag_FW_BLOB_REPO *,ushort const *)
0x18009958d  test    rax, rax
0x180099590  jz      short loc_1800995A3
0x180099592  mov     rcx, [rax]
0x180099595  lea     rdx, [rbp+var_30]
0x180099599  mov     rcx, [rcx+18h]
0x18009959d  call    cs:__imp_FwStringCopy
0x1800995a3  mov     edx, [rdi+10h]; int
0x1800995a6  lea     rax, [rbp+var_28]
0x1800995aa  mov     rcx, [rdi+8]; int
0x1800995ae  mov     r9d, r15d; int
0x1800995b1  mov     [rsp+70h+var_48], rax; __int64
0x1800995b6  xor     r8d, r8d; int
0x1800995b9  mov     [rsp+70h+lpString2], r14; lpString2
0x1800995be  call    FwIncrmDeleteSet
0x1800995c3  mov     ebx, eax
0x1800995c5  test    eax, eax
0x1800995c7  jns     short loc_1800995E5
0x1800995c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800995d0  cmp     rcx, r13
0x1800995d3  jz      short loc_180099626
0x1800995d5  test    byte ptr [rcx+1Ch], 1
0x1800995d9  jz      short loc_180099626
0x1800995db  mov     edx, 130h
0x1800995e0  jmp     loc_180099429
0x1800995e5  mov     rcx, [rbp+var_20]
0x1800995e9  mov     r9d, 1
0x1800995ef  mov     rax, [rbp+var_30]
0x1800995f3  mov     edx, 7FFFFFFFh
0x1800995f8  mov     [rsp+70h+var_48], rax
0x1800995fd  mov     [rsp+70h+lpString2], r14
0x180099602  mov     rcx, [rcx]
0x180099605  lea     r8d, [r9+3]
0x180099609  call    FwAuditLogRuleChange
0x18009960e  cmp     [rbp+var_28], 0
0x180099613  jnz     short loc_180099626
0x180099615  cmp     [rbp+var_30], 0
0x18009961a  jz      short loc_180099626
0x18009961c  lea     rcx, [rbp+var_30]
0x180099620  call    cs:__imp_FwResolveIndirectString
0x180099626  lea     rdx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009962d  mov     rcx, rsi; void *
0x180099630  call    FwUnlockInternal
0x180099635  lea     rcx, aSvrimplFwdelet_12; "SvrImpl_FWDeleteAuthenticationSet"
0x18009963c  call    FwReleaseRPCSharedLock
0x180099641  test    ebx, ebx
0x180099643  js      short loc_18009964B
0x180099645  call    cs:__imp_FwChangeSourceSignal
0x18009964b  mov     ecx, ebx
0x18009964d  call    cs:__imp_FwHResultToWindowsError
0x180099653  mov     rcx, [rbp+var_28]
0x180099657  lea     rdi, qword_1800F5F90
0x18009965e  mov     r9d, eax
0x180099661  test    rcx, rcx
0x180099664  jnz     short loc_180099674
0x180099666  mov     rax, [rbp+var_30]
0x18009966a  mov     rcx, rdi
0x18009966d  test    rax, rax
0x180099670  cmovnz  rcx, rax
0x180099674  mov     rax, [rbp+var_18]
0x180099678  test    r14, r14
0x18009967b  mov     rdx, [rbp+var_20]
0x18009967f  mov     r8, rdi
0x180099682  cmovz   r14, rdi
0x180099686  test    rax, rax
0x180099689  cmovnz  r8, rax
0x18009968d  test    rdx, rdx
0x180099690  jz      short loc_180099697
0x180099692  mov     rdx, [rdx]
0x180099695  jmp     short loc_18009969E
0x180099697  lea     rdx, aS100; "S-1-0-0"
0x18009969e  mov     dword ptr [rsp+70h+var_40], r9d
0x1800996a3  mov     r9, r14
0x1800996a6  mov     dword ptr [rsp+70h+var_48], r15d
0x1800996ab  mov     [rsp+70h+lpString2], rcx
0x1800996b0  call    ?FwLogAuthenticationSetDeleted@@YAKPEBU_EVENT_DESCRIPTOR@@PEAXPEBG22W4_tag_FW_IPSEC_PHASE@@K@Z; FwLogAuthenticationSetDeleted(_EVENT_DESCRIPTOR const *,void *,ushort const *,ushort const *,ushort const *,_tag_FW_IPSEC_PHASE,ulong)
0x1800996b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800996bc  cmp     rax, r13
0x1800996bf  jz      short loc_18009971D
0x1800996c1  test    byte ptr [rax+1Ch], 4
0x1800996c5  jz      short loc_18009971D
0x1800996c7  mov     rsi, [rbp+var_28]
0x1800996cb  test    rsi, rsi
0x1800996ce  jnz     short loc_1800996DE
0x1800996d0  mov     rax, [rbp+var_30]
0x1800996d4  mov     rsi, rdi
0x1800996d7  test    rax, rax
0x1800996da  cmovnz  rsi, rax
0x1800996de  mov     rax, [rbp+var_18]
0x1800996e2  mov     ecx, ebx
0x1800996e4  test    rax, rax
0x1800996e7  cmovnz  rdi, rax
0x1800996eb  call    cs:__imp_FwHResultToWindowsError
0x1800996f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800996f8  mov     edx, 131h
0x1800996fd  mov     [rsp+70h+var_38], r15d
0x180099702  mov     r9d, eax
0x180099705  mov     [rsp+70h+var_40], rsi
0x18009970a  mov     [rsp+70h+var_48], r14
0x18009970f  mov     rcx, [rcx+10h]
0x180099713  mov     [rsp+70h+lpString2], rdi
0x180099718  call    WPP_SF_DSSSD
0x18009971d  mov     rcx, [rbp+var_20]
0x180099721  call    cs:__imp_FwFree
0x180099727  mov     rcx, [rbp+var_30]
0x18009972b  call    cs:__imp_FwFree
0x180099731  mov     rcx, [rbp+var_28]
0x180099735  call    cs:__imp_FwFree
0x18009973b  mov     rcx, [rbp+var_18]
0x18009973f  call    cs:__imp_FwFree
0x180099745  mov     ecx, ebx
0x180099747  call    cs:__imp_FwHResultToWindowsError
0x18009974d  mov     rcx, [rbp+var_10]
0x180099751  xor     rcx, rsp; StackCookie
0x180099754  call    __security_check_cookie
0x180099759  add     rsp, 70h
0x18009975d  pop     r15
0x18009975f  pop     r14
0x180099761  pop     r13
0x180099763  pop     rdi
0x180099764  pop     rsi
0x180099765  pop     rbx
0x180099766  pop     rbp
0x180099767  retn
```
