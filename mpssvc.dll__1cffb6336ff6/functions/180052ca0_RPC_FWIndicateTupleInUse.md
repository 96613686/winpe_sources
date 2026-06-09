# RPC_FWIndicateTupleInUse

- ea: `0x180052ca0`
- end: `0x180053314`
- name: `RPC_FWIndicateTupleInUse`
- size: `1652`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, __int16, __int16, __int64, __int64, __int64, struct _tag_FW_INTERFACE_INDEXES *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180008618`
- `0x1800093b0`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x1800247d0`
- `0x180051d10`
- `0x180052ca0`
- `0x1800585b4`
- `0x18006e30c`
- `0x18006f520`
- `0x1800c5584`
- `0x1800c5600`
- `0x1800c5a88`
- `0x1800c5cf8`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180052d1e`
- `fwbase!FwHResultToWindowsError` at `0x180052d5c`
- `fwbase!FwHResultToWindowsError` at `0x180052dc0`
- `fwbase!FwHResultToWindowsError` at `0x180052f0f`
- `fwbase!FwHResultToWindowsError` at `0x180052f5c`
- `fwbase!FwHResultToWindowsError` at `0x180052fac`
- `fwbase!FwHResultToWindowsError` at `0x180052ffb`
- `fwbase!FwHResultToWindowsError` at `0x18005313d`
- `fwbase!FwHResultToWindowsError` at `0x1800532b0`
- `fwbase!FwHResultToWindowsError` at `0x180052d1e`
- `fwbase!FwHResultToWindowsError` at `0x180052d5c`
- `fwbase!FwHResultToWindowsError` at `0x180052dc0`
- `fwbase!FwHResultToWindowsError` at `0x180052f0f`
- `fwbase!FwHResultToWindowsError` at `0x180052f5c`
- `fwbase!FwHResultToWindowsError` at `0x180052fac`
- `fwbase!FwHResultToWindowsError` at `0x180052ffb`
- `fwbase!FwHResultToWindowsError` at `0x18005313d`
- `fwbase!FwHResultToWindowsError` at `0x1800532b0`
- `fwbase!FwHashtableRemove` at `0x180052e3c`
- `fwbase!FwHashtableRemove` at `0x180052e3c`
- `fwbase!FwUpdateHash` at `0x1800530b9`
- `fwbase!FwUpdateHash` at `0x1800530b9`
- `fwbase!FwRestructureHashtable` at `0x180052e49`
- `fwbase!FwRestructureHashtable` at `0x1800531c1`
- `fwbase!FwRestructureHashtable` at `0x180052e49`
- `fwbase!FwRestructureHashtable` at `0x1800531c1`
- `fwbase!FwInitializeHashContext` at `0x18005309c`
- `fwbase!FwInitializeHashContext` at `0x18005309c`
- `fwbase!FwFinalHash` at `0x1800530c3`
- `fwbase!FwFinalHash` at `0x1800530c3`
- `fwbase!FwAddrChangeSourceSignal` at `0x180052e83`
- `fwbase!FwAddrChangeSourceSignal` at `0x180052e83`
- `fwbase!FwHashtableInsert` at `0x1800531ab`
- `fwbase!FwHashtableInsert` at `0x1800531ab`
- `fwbase!FwStringCopy` at `0x180053135`
- `fwbase!FwStringCopy` at `0x180053135`
- `fwbase!FwAlloc` at `0x180052e95`
- `fwbase!FwAlloc` at `0x1800530ee`
- `fwbase!FwAlloc` at `0x180052e95`
- `fwbase!FwAlloc` at `0x1800530ee`
- `fwbase!FwFree` at `0x180052e52`
- `fwbase!FwFree` at `0x180052e52`
- `FWPolicyIOMgr!FwCopyInterfaceLuids` at `0x180052fa4`
- `FWPolicyIOMgr!FwCopyInterfaceLuids` at `0x180052fa4`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180052f07`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180052f54`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180052f07`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180052f54`

## pseudocode

```c
__int64 __fastcall RPC_FWIndicateTupleInUse(
        void *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        struct _tag_FW_INTERFACE_INDEXES *a11,
        __int64 *a12)
{
  int v13; // eax
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // edi
  int v19; // r14d
  unsigned int v20; // r12d
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rbx
  __int64 v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // r15
  _QWORD *v37; // rax
  __int64 v38; // rax
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rax
  __int64 v45; // rcx
  __int64 *v46; // rcx
  __int64 v47; // rax
  __int64 (__fastcall *v48)(const struct _tag_FW_RULE *, const void *); // rdi
  unsigned int updated; // eax
  __int64 v50; // rax
  _QWORD *v51; // rcx
  int v53; // [rsp+48h] [rbp-41h]
  _QWORD *v55; // [rsp+50h] [rbp-39h]
  _QWORD *v56; // [rsp+58h] [rbp-31h] BYREF
  void *v57; // [rsp+60h] [rbp-29h]
  __int64 *v58; // [rsp+68h] [rbp-21h]
  unsigned int v59; // [rsp+70h] [rbp-19h] BYREF
  __int64 v60; // [rsp+78h] [rbp-11h] BYREF

  v57 = a1;
  *a12 = 0;
  v58 = a12;
  v56 = 0;
  v60 = 0;
  v59 = 0;
  v13 = FwAcquireRPCSharedLock("RPC_FWIndicateTupleInUse");
  if ( v13 < 0 )
    return FwHResultToWindowsError((unsigned int)v13);
  v15 = 0;
  v55 = 0;
  v53 = 0;
  v16 = FwLock();
  v18 = FwHResultToWindowsError(v16);
  if ( v18 )
  {
    v19 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v18);
    v20 = a2;
LABEL_16:
    FwTupleEntryFree((struct _tag_FW_RESRC_TUPLE_ENTRY *)v15);
    if ( v55 && v53 == 1 )
    {
      v25 = 96LL * (int)v20;
      FwHashtableRemove((char *)&TupleCollection + v25 + 32, v55);
      FwRestructureHashtable((char *)&TupleCollection + v25 + 32);
    }
    FwFree(v55);
    if ( !v19 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v21 = FwResrcIndicationTupleAccessCheckForClient(a2, v17, v57);
  v18 = FwHResultToWindowsError(v21);
  if ( v18 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v23 = 45;
    goto LABEL_12;
  }
  v26 = FwAlloc(216);
  v15 = v26;
  if ( !v26 )
  {
    v24 = 14;
    v18 = 14;
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v23 = 46;
    goto LABEL_13;
  }
  *(_DWORD *)(v26 + 16) = a4;
  *(_WORD *)(v26 + 20) = a5;
  *(_WORD *)(v26 + 24) = a6;
  *(_WORD *)(v26 + 22) = a6;
  *(_WORD *)(v26 + 28) = a7;
  *(_WORD *)(v26 + 26) = a7;
  if ( a8 )
  {
    v27 = FwPolioCopyWFAddressesContents(a8, v26 + 32);
    v18 = FwHResultToWindowsError(v27);
    if ( v18 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v23 = 47;
      goto LABEL_12;
    }
  }
  if ( a9 )
  {
    v28 = FwPolioCopyWFAddressesContents(a9, v15 + 104);
    v18 = FwHResultToWindowsError(v28);
    if ( v18 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v23 = 48;
      goto LABEL_12;
    }
  }
  if ( a10 )
  {
    v29 = FwCopyInterfaceLuids(a10, v15 + 176);
    v18 = FwHResultToWindowsError(v29);
    if ( v18 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v23 = 49;
      goto LABEL_12;
    }
  }
  if ( a11 )
  {
    v30 = FwCopyInterfaceIndexesInt(a11, (struct _tag_FW_INTERFACE_INDEXES *)(v15 + 192));
    v18 = FwHResultToWindowsError(v30);
    if ( v18 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_14;
      v23 = 50;
LABEL_12:
      v24 = v18;
LABEL_13:
      WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v24);
LABEL_14:
      v20 = a2;
LABEL_15:
      v19 = 1;
      goto LABEL_16;
    }
  }
  v20 = a2;
  v31 = 12LL * (int)a2;
  if ( *(_DWORD *)((char *)&TupleCollection + v31 * 8 + 12) )
  {
    if ( !a3 )
    {
      v32 = 87;
      v18 = 87;
      v33 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_15;
      v34 = 51;
      goto LABEL_54;
    }
    FwInitializeHashContext(&v60);
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)(a3 + 2 * v35) );
    FwUpdateHash(a3, (unsigned int)(2 * v35), &v60);
    v36 = FwFinalHash(&v60);
    FwResrcPerPackageCollFindByPackageIdSignature(v36, a2, a3, &v56);
    v37 = v56;
    if ( !v56 )
    {
      v38 = FwAlloc(48);
      v55 = (_QWORD *)v38;
      if ( !v38 )
      {
        v32 = 14;
        v18 = 14;
        v33 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_15;
        v34 = 52;
        goto LABEL_54;
      }
      v39 = FwStringCopy(a3, v38 + 24);
      v18 = FwHResultToWindowsError(v39);
      if ( v18 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v18);
        goto LABEL_15;
      }
      v55[5] = v55 + 4;
      v55[4] = v55 + 4;
      v55[2] = v36;
      if ( (unsigned int)FwHashtableInsert(&qword_180129BE0[v31], v55) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v41, v40, v42, v43);
      FwRestructureHashtable(&qword_180129BE0[v31]);
      v37 = v55;
      v53 = 1;
    }
    v44 = v37 + 4;
  }
  else
  {
    if ( a3 )
    {
      v32 = 87;
      v18 = 87;
      v33 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_15;
      v34 = 54;
LABEL_54:
      WPP_SF_d(*(_QWORD *)(v33 + 16), v34, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v32);
      goto LABEL_15;
    }
    v44 = &qword_180129BE0[v31 + 6];
  }
  v45 = *v44;
  if ( *(__int64 **)(*v44 + 8) != v44 )
LABEL_86:
    __fastfail(3u);
  *(_QWORD *)v15 = v45;
  *(_QWORD *)(v15 + 8) = v44;
  *(_QWORD *)(v45 + 8) = v15;
  v46 = v58;
  *v44 = v15;
  v47 = qword_18012A018 + 1;
  qword_18012A018 = v47;
  *(_QWORD *)(v15 + 208) = v47;
  *v46 = v47;
  if ( *(_DWORD *)((char *)&TupleCollection + v31 * 8 + 8) )
  {
    v48 = FwFWRuleMatchesAddrKeywords;
    v59 = FwAddressKeywordFromTupleCollection(a2);
    FwDynDataNLADeleteAddressStoreByProfileAndAddressKeyword(0x7FFFFFFF, v59);
  }
  else
  {
    v48 = FwFWRuleMatchesTrustTupleKeywords;
    v59 = FwTupleKeywordFromTupleCollection(a2);
  }
  updated = FwUpdateAllWithCriteria((_DWORD)v48, 0, 0, (unsigned int)&v59, 0, 0, 0);
  v18 = FwHResultToWindowsError(updated);
  if ( v18 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v18);
    v50 = *(_QWORD *)v15;
    if ( *(_QWORD *)(*(_QWORD *)v15 + 8LL) == v15 )
    {
      v51 = *(_QWORD **)(v15 + 8);
      if ( *v51 == v15 )
      {
        *v51 = v50;
        *(_QWORD *)(v50 + 8) = v51;
        goto LABEL_15;
      }
    }
    goto LABEL_86;
  }
LABEL_20:
  FwUnlockInternal(v57, "RPC_FWIndicateTupleInUse");
LABEL_21:
  FwReleaseRPCSharedLock("RPC_FWIndicateTupleInUse");
  if ( !v18 && v20 == 7 )
    FwAddrChangeSourceSignal();
  return v18;
}

```

## disassembly

```asm
0x180052ca0  mov     [rsp-8+arg_18], rbx
0x180052ca5  push    rbp
0x180052ca6  push    rsi
0x180052ca7  push    rdi
0x180052ca8  push    r12
0x180052caa  push    r13
0x180052cac  push    r14
0x180052cae  push    r15
0x180052cb0  lea     rbp, [rsp-7]
0x180052cb5  sub     rsp, 90h
0x180052cbc  mov     rax, cs:__security_cookie
0x180052cc3  xor     rax, rsp
0x180052cc6  mov     [rbp+37h+var_40], rax
0x180052cca  mov     rax, [rbp+37h+arg_58]
0x180052cd1  xor     edi, edi
0x180052cd3  mov     r15, [rbp+37h+arg_38]
0x180052cd7  mov     r14, r8
0x180052cda  mov     rsi, [rbp+37h+arg_40]
0x180052ce1  mov     r12, [rbp+37h+arg_48]
0x180052ce8  mov     r13, [rbp+37h+arg_50]
0x180052cef  mov     [rbp+37h+var_60], rcx
0x180052cf3  lea     rcx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x180052cfa  mov     [rax], rdi
0x180052cfd  mov     [rbp+37h+var_74], r9d
0x180052d01  mov     [rbp+37h+var_7C], edx
0x180052d04  mov     [rbp+37h+var_58], rax
0x180052d08  mov     [rbp+37h+var_68], rdi
0x180052d0c  mov     [rbp+37h+var_48], rdi
0x180052d10  mov     [rbp+37h+var_50], edi
0x180052d13  call    FwAcquireRPCSharedLock
0x180052d18  test    eax, eax
0x180052d1a  jns     short loc_180052D4B
0x180052d1c  mov     ecx, eax
0x180052d1e  call    cs:__imp_FwHResultToWindowsError
0x180052d24  mov     rcx, [rbp+37h+var_40]
0x180052d28  xor     rcx, rsp; StackCookie
0x180052d2b  call    __security_check_cookie
0x180052d30  mov     rbx, [rsp+0C0h+arg_18]
0x180052d38  add     rsp, 90h
0x180052d3f  pop     r15
0x180052d41  pop     r14
0x180052d43  pop     r13
0x180052d45  pop     r12
0x180052d47  pop     rdi
0x180052d48  pop     rsi
0x180052d49  pop     rbp
0x180052d4a  retn
0x180052d4b  mov     rbx, rdi
0x180052d4e  mov     [rbp+37h+var_70], rdi
0x180052d52  mov     [rbp+37h+var_78], edi
0x180052d55  call    FwLock
0x180052d5a  mov     ecx, eax
0x180052d5c  call    cs:__imp_FwHResultToWindowsError
0x180052d62  mov     edi, eax
0x180052d64  xor     eax, eax
0x180052d66  test    edi, edi
0x180052d68  jz      short loc_180052DAB
0x180052d6a  mov     r14d, eax
0x180052d6d  mov     rax, cs:WPP_GLOBAL_Control
0x180052d74  lea     rcx, WPP_GLOBAL_Control
0x180052d7b  cmp     rax, rcx
0x180052d7e  jz      short loc_180052D9E
0x180052d80  test    byte ptr [rax+1Ch], 1
0x180052d84  jz      short loc_180052D9E
0x180052d86  mov     rcx, [rax+10h]
0x180052d8a  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x180052d91  mov     edx, 2Ch ; ','
0x180052d96  mov     r9d, edi
0x180052d99  call    WPP_SF_d
0x180052d9e  mov     r12d, [rbp+37h+var_7C]
0x180052da2  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x180052da9  jmp     short loc_180052E10
0x180052dab  mov     r8, [rbp+37h+var_60]
0x180052daf  mov     ecx, [rbp+37h+var_7C]
0x180052db2  mov     [rbp+37h+var_80], 1
0x180052db9  call    ?FwResrcIndicationTupleAccessCheckForClient@@YAJW4_tag_FW_TUPLE_COLLECTION_TYPE@@KPEAX@Z; FwResrcIndicationTupleAccessCheckForClient(_tag_FW_TUPLE_COLLECTION_TYPE,ulong,void *)
0x180052dbe  mov     ecx, eax
0x180052dc0  call    cs:__imp_FwHResultToWindowsError
0x180052dc6  mov     edi, eax
0x180052dc8  test    eax, eax
0x180052dca  jz      loc_180052E90
0x180052dd0  mov     rax, cs:WPP_GLOBAL_Control
0x180052dd7  lea     rcx, WPP_GLOBAL_Control
0x180052dde  cmp     rax, rcx
0x180052de1  jz      short loc_180052E01
0x180052de3  test    byte ptr [rax+1Ch], 1
0x180052de7  jz      short loc_180052E01
0x180052de9  mov     edx, 2Dh ; '-'
0x180052dee  mov     r9d, edi
0x180052df1  mov     rcx, [rax+10h]
0x180052df5  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x180052dfc  call    WPP_SF_d
0x180052e01  mov     r12d, [rbp+37h+var_7C]
0x180052e05  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x180052e0c  mov     r14d, [rbp+37h+var_80]
0x180052e10  mov     rcx, rbx; struct _tag_FW_RESRC_TUPLE_ENTRY *
0x180052e13  call    ?FwTupleEntryFree@@YAXPEAU_tag_FW_RESRC_TUPLE_ENTRY@@@Z; FwTupleEntryFree(_tag_FW_RESRC_TUPLE_ENTRY *)
0x180052e18  mov     rsi, [rbp+37h+var_70]
0x180052e1c  test    rsi, rsi
0x180052e1f  jz      short loc_180052E4F
0x180052e21  cmp     [rbp+37h+var_78], 1
0x180052e25  jnz     short loc_180052E4F
0x180052e27  movsxd  rax, r12d
0x180052e2a  mov     rdx, rsi
0x180052e2d  lea     rbx, [rax+rax*2]
0x180052e31  shl     rbx, 5
0x180052e35  lea     rcx, [rbx+20h]
0x180052e39  add     rcx, r13
0x180052e3c  call    cs:__imp_FwHashtableRemove
0x180052e42  lea     rcx, [rbx+20h]
0x180052e46  add     rcx, r13
0x180052e49  call    cs:__imp_FwRestructureHashtable
0x180052e4f  mov     rcx, rsi
0x180052e52  call    cs:__imp_FwFree
0x180052e58  test    r14d, r14d
0x180052e5b  jz      short loc_180052E6D
0x180052e5d  mov     rcx, [rbp+37h+var_60]; void *
0x180052e61  lea     rdx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x180052e68  call    FwUnlockInternal
0x180052e6d  lea     rcx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x180052e74  call    FwReleaseRPCSharedLock
0x180052e79  test    edi, edi
0x180052e7b  jnz     short loc_180052E89
0x180052e7d  cmp     r12d, 7
0x180052e81  jnz     short loc_180052E89
0x180052e83  call    cs:__imp_FwAddrChangeSourceSignal
0x180052e89  mov     eax, edi
0x180052e8b  jmp     loc_180052D24
0x180052e90  mov     ecx, 0D8h
0x180052e95  call    cs:__imp_FwAlloc
0x180052e9b  xor     edi, edi
0x180052e9d  mov     rbx, rax
0x180052ea0  test    rax, rax
0x180052ea3  jnz     short loc_180052ED5
0x180052ea5  lea     r9d, [rax+0Eh]
0x180052ea9  mov     edi, r9d
0x180052eac  mov     rax, cs:WPP_GLOBAL_Control
0x180052eb3  lea     rcx, WPP_GLOBAL_Control
0x180052eba  cmp     rax, rcx
0x180052ebd  jz      loc_180052E01
0x180052ec3  test    byte ptr [rax+1Ch], 1
0x180052ec7  jz      loc_180052E01
0x180052ecd  lea     edx, [rbx+2Eh]
0x180052ed0  jmp     loc_180052DF1
0x180052ed5  mov     eax, [rbp+37h+var_74]
0x180052ed8  mov     [rbx+10h], eax
0x180052edb  movzx   eax, [rbp+37h+arg_20]
0x180052edf  mov     [rbx+14h], ax
0x180052ee3  movzx   eax, [rbp+37h+arg_28]
0x180052ee7  mov     [rbx+18h], ax
0x180052eeb  mov     [rbx+16h], ax
0x180052eef  movzx   eax, [rbp+37h+arg_30]
0x180052ef3  mov     [rbx+1Ch], ax
0x180052ef7  mov     [rbx+1Ah], ax
0x180052efb  test    r15, r15
0x180052efe  jz      short loc_180052F48
0x180052f00  lea     rdx, [rbx+20h]
0x180052f04  mov     rcx, r15
0x180052f07  call    cs:__imp_FwPolioCopyWFAddressesContents
0x180052f0d  mov     ecx, eax
0x180052f0f  call    cs:__imp_FwHResultToWindowsError
0x180052f15  mov     edi, eax
0x180052f17  test    eax, eax
0x180052f19  jz      short loc_180052F46
0x180052f1b  mov     rax, cs:WPP_GLOBAL_Control
0x180052f22  lea     rcx, WPP_GLOBAL_Control
0x180052f29  cmp     rax, rcx
0x180052f2c  jz      loc_180052E01
0x180052f32  test    byte ptr [rax+1Ch], 1
0x180052f36  jz      loc_180052E01
0x180052f3c  mov     edx, 2Fh ; '/'
0x180052f41  jmp     loc_180052DEE
0x180052f46  xor     edi, edi
0x180052f48  test    rsi, rsi
0x180052f4b  jz      short loc_180052F95
0x180052f4d  lea     rdx, [rbx+68h]
0x180052f51  mov     rcx, rsi
0x180052f54  call    cs:__imp_FwPolioCopyWFAddressesContents
0x180052f5a  mov     ecx, eax
0x180052f5c  call    cs:__imp_FwHResultToWindowsError
0x180052f62  mov     edi, eax
0x180052f64  test    eax, eax
0x180052f66  jz      short loc_180052F93
0x180052f68  mov     rax, cs:WPP_GLOBAL_Control
0x180052f6f  lea     rcx, WPP_GLOBAL_Control
0x180052f76  cmp     rax, rcx
0x180052f79  jz      loc_180052E01
0x180052f7f  test    byte ptr [rax+1Ch], 1
0x180052f83  jz      loc_180052E01
0x180052f89  mov     edx, 30h ; '0'
0x180052f8e  jmp     loc_180052DEE
0x180052f93  xor     edi, edi
0x180052f95  test    r12, r12
0x180052f98  jz      short loc_180052FE5
0x180052f9a  lea     rdx, [rbx+0B0h]
0x180052fa1  mov     rcx, r12
0x180052fa4  call    cs:__imp_FwCopyInterfaceLuids
0x180052faa  mov     ecx, eax
0x180052fac  call    cs:__imp_FwHResultToWindowsError
0x180052fb2  mov     edi, eax
0x180052fb4  test    eax, eax
0x180052fb6  jz      short loc_180052FE3
0x180052fb8  mov     rax, cs:WPP_GLOBAL_Control
0x180052fbf  lea     rcx, WPP_GLOBAL_Control
0x180052fc6  cmp     rax, rcx
0x180052fc9  jz      loc_180052E01
0x180052fcf  test    byte ptr [rax+1Ch], 1
0x180052fd3  jz      loc_180052E01
0x180052fd9  mov     edx, 31h ; '1'
0x180052fde  jmp     loc_180052DEE
0x180052fe3  xor     edi, edi
0x180052fe5  test    r13, r13
0x180052fe8  jz      short loc_180053034
0x180052fea  lea     rdx, [rbx+0C0h]; struct _tag_FW_INTERFACE_INDEXES *
0x180052ff1  mov     rcx, r13; struct _tag_FW_INTERFACE_INDEXES *
0x180052ff4  call    ?FwCopyInterfaceIndexesInt@@YAJPEBU_tag_FW_INTERFACE_INDEXES@@PEAU1@@Z; FwCopyInterfaceIndexesInt(_tag_FW_INTERFACE_INDEXES const *,_tag_FW_INTERFACE_INDEXES *)
0x180052ff9  mov     ecx, eax
0x180052ffb  call    cs:__imp_FwHResultToWindowsError
0x180053001  mov     edi, eax
0x180053003  test    eax, eax
0x180053005  jz      short loc_180053032
0x180053007  mov     rax, cs:WPP_GLOBAL_Control
0x18005300e  lea     rcx, WPP_GLOBAL_Control
0x180053015  cmp     rax, rcx
0x180053018  jz      loc_180052E01
0x18005301e  test    byte ptr [rax+1Ch], 1
0x180053022  jz      loc_180052E01
0x180053028  mov     edx, 32h ; '2'
0x18005302d  jmp     loc_180052DEE
0x180053032  xor     edi, edi
0x180053034  movsxd  r12, [rbp+37h+var_7C]
0x180053038  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x18005303f  lea     rsi, [r12+r12*2]
0x180053043  shl     rsi, 5
0x180053047  cmp     [rsi+r13+0Ch], edi
0x18005304c  jz      loc_1800531E0
0x180053052  test    r14, r14
0x180053055  jnz     short loc_180053098
0x180053057  lea     r9d, [r14+57h]
0x18005305b  mov     edi, r9d
0x18005305e  mov     rax, cs:WPP_GLOBAL_Control
0x180053065  lea     rcx, WPP_GLOBAL_Control
0x18005306c  cmp     rax, rcx
0x18005306f  jz      loc_180052E0C
0x180053075  test    byte ptr [rax+1Ch], 1
0x180053079  jz      loc_180052E0C
0x18005307f  lea     edx, [r14+33h]
0x180053083  mov     rcx, [rax+10h]
0x180053087  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x18005308e  call    WPP_SF_d
0x180053093  jmp     loc_180052E0C
0x180053098  lea     rcx, [rbp+37h+var_48]
0x18005309c  call    cs:__imp_FwInitializeHashContext
0x1800530a2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800530a6  inc     rdx
0x1800530a9  cmp     [r14+rdx*2], di
0x1800530ae  jnz     short loc_1800530A6
0x1800530b0  add     edx, edx
0x1800530b2  lea     r8, [rbp+37h+var_48]
0x1800530b6  mov     rcx, r14
0x1800530b9  call    cs:__imp_FwUpdateHash
0x1800530bf  lea     rcx, [rbp+37h+var_48]
0x1800530c3  call    cs:__imp_FwFinalHash
0x1800530c9  lea     r9, [rbp+37h+var_68]
0x1800530cd  mov     r8, r14
0x1800530d0  mov     rcx, rax
0x1800530d3  mov     edx, r12d
0x1800530d6  mov     r15, rax
0x1800530d9  call    ?FwResrcPerPackageCollFindByPackageIdSignature@@YAK_KW4_tag_FW_TUPLE_COLLECTION_TYPE@@PEBGPEAPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwResrcPerPackageCollFindByPackageIdSignature(unsigned __int64,_tag_FW_TUPLE_COLLECTION_TYPE,ushort const *,_tag_FW_RESRC_TUPLE_PER_PACKAGEID * *)
0x1800530de  mov     rax, [rbp+37h+var_68]
0x1800530e2  test    rax, rax
0x1800530e5  jnz     loc_1800531DA
0x1800530eb  lea     ecx, [rax+30h]
0x1800530ee  call    cs:__imp_FwAlloc
0x1800530f4  mov     [rbp+37h+var_70], rax
0x1800530f8  test    rax, rax
0x1800530fb  jnz     short loc_18005312E
0x1800530fd  lea     r9d, [rax+0Eh]
0x180053101  mov     edi, r9d
0x180053104  mov     rax, cs:WPP_GLOBAL_Control
0x18005310b  lea     rcx, WPP_GLOBAL_Control
0x180053112  cmp     rax, rcx
0x180053115  jz      loc_180052E0C
0x18005311b  test    byte ptr [rax+1Ch], 1
0x18005311f  jz      loc_180052E0C
0x180053125  lea     edx, [r9+26h]
0x180053129  jmp     loc_180053083
0x18005312e  lea     rdx, [rax+18h]
0x180053132  mov     rcx, r14
0x180053135  call    cs:__imp_FwStringCopy
0x18005313b  mov     ecx, eax
0x18005313d  call    cs:__imp_FwHResultToWindowsError
0x180053143  mov     edi, eax
0x180053145  test    eax, eax
0x180053147  jz      short loc_180053187
0x180053149  mov     rax, cs:WPP_GLOBAL_Control
0x180053150  lea     rcx, WPP_GLOBAL_Control
0x180053157  cmp     rax, rcx
0x18005315a  jz      loc_180052E05
0x180053160  test    byte ptr [rax+1Ch], 1
  ... truncated ...
```
