# RPC_FWIndicateTupleInUse

- ea: `0x180057170`
- end: `0x180057875`
- name: `RPC_FWIndicateTupleInUse`
- size: `1797`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, __int16, __int16, __int64, __int64, __int64, struct _tag_FW_INTERFACE_INDEXES *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180007b58`
- `0x1800089bc`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x180026cd0`
- `0x1800560f4`
- `0x180057170`
- `0x18005d5ec`
- `0x180071718`
- `0x1800729c0`
- `0x1800cc918`
- `0x1800cc9a4`
- `0x1800ccf38`
- `0x1800cd1c8`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800571ee`
- `fwbase!FwHResultToWindowsError` at `0x180057233`
- `fwbase!FwHResultToWindowsError` at `0x18005729d`
- `fwbase!FwHResultToWindowsError` at `0x180057416`
- `fwbase!FwHResultToWindowsError` at `0x18005746f`
- `fwbase!FwHResultToWindowsError` at `0x1800574cb`
- `fwbase!FwHResultToWindowsError` at `0x180057520`
- `fwbase!FwHResultToWindowsError` at `0x180057686`
- `fwbase!FwHResultToWindowsError` at `0x18005780b`
- `fwbase!FwHResultToWindowsError` at `0x1800571ee`
- `fwbase!FwHResultToWindowsError` at `0x180057233`
- `fwbase!FwHResultToWindowsError` at `0x18005729d`
- `fwbase!FwHResultToWindowsError` at `0x180057416`
- `fwbase!FwHResultToWindowsError` at `0x18005746f`
- `fwbase!FwHResultToWindowsError` at `0x1800574cb`
- `fwbase!FwHResultToWindowsError` at `0x180057520`
- `fwbase!FwHResultToWindowsError` at `0x180057686`
- `fwbase!FwHResultToWindowsError` at `0x18005780b`
- `fwbase!FwHashtableRemove` at `0x18005731f`
- `fwbase!FwHashtableRemove` at `0x18005731f`
- `fwbase!FwUpdateHash` at `0x1800575ea`
- `fwbase!FwUpdateHash` at `0x1800575ea`
- `fwbase!FwRestructureHashtable` at `0x180057332`
- `fwbase!FwRestructureHashtable` at `0x180057716`
- `fwbase!FwRestructureHashtable` at `0x180057332`
- `fwbase!FwRestructureHashtable` at `0x180057716`
- `fwbase!FwInitializeHashContext` at `0x1800575c7`
- `fwbase!FwInitializeHashContext` at `0x1800575c7`
- `fwbase!FwAddrChangeSourceSignal` at `0x180057378`
- `fwbase!FwAddrChangeSourceSignal` at `0x180057378`
- `fwbase!FwFinalHash` at `0x1800575fa`
- `fwbase!FwFinalHash` at `0x1800575fa`
- `fwbase!FwHashtableInsert` at `0x1800576fa`
- `fwbase!FwHashtableInsert` at `0x1800576fa`
- `fwbase!FwStringCopy` at `0x180057678`
- `fwbase!FwStringCopy` at `0x180057678`
- `fwbase!FwAlloc` at `0x180057390`
- `fwbase!FwAlloc` at `0x18005762b`
- `fwbase!FwAlloc` at `0x180057390`
- `fwbase!FwAlloc` at `0x18005762b`
- `fwbase!FwFree` at `0x180057341`
- `fwbase!FwFree` at `0x180057341`
- `FWPolicyIOMgr!FwCopyInterfaceLuids` at `0x1800574bd`
- `FWPolicyIOMgr!FwCopyInterfaceLuids` at `0x1800574bd`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180057408`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180057461`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180057408`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180057461`

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
  __int64 *v40; // rax
  __int64 v41; // rcx
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 (__fastcall *v44)(const struct _tag_FW_RULE *, const void *); // rdi
  unsigned int updated; // eax
  __int64 v46; // rax
  _QWORD *v47; // rcx
  int v49; // [rsp+48h] [rbp-41h]
  _QWORD *v51; // [rsp+50h] [rbp-39h]
  _QWORD *v52; // [rsp+58h] [rbp-31h] BYREF
  void *v53; // [rsp+60h] [rbp-29h]
  __int64 *v54; // [rsp+68h] [rbp-21h]
  unsigned int v55; // [rsp+70h] [rbp-19h] BYREF
  __int64 v56; // [rsp+78h] [rbp-11h] BYREF

  v53 = a1;
  *a12 = 0;
  v54 = a12;
  v52 = 0;
  v56 = 0;
  v55 = 0;
  v13 = FwAcquireRPCSharedLock("RPC_FWIndicateTupleInUse");
  if ( v13 < 0 )
    return FwHResultToWindowsError((unsigned int)v13);
  v15 = 0;
  v51 = 0;
  v49 = 0;
  v16 = FwLock();
  v18 = FwHResultToWindowsError(v16);
  if ( v18 )
  {
    v19 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v18);
    v20 = a2;
LABEL_16:
    FwTupleEntryFree((struct _tag_FW_RESRC_TUPLE_ENTRY *)v15);
    if ( v51 && v49 == 1 )
    {
      v25 = 96LL * (int)v20;
      FwHashtableRemove((char *)&TupleCollection + v25 + 32, v51);
      FwRestructureHashtable((char *)&TupleCollection + v25 + 32);
    }
    FwFree(v51);
    if ( !v19 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v21 = FwResrcIndicationTupleAccessCheckForClient(a2, v17, v53);
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
      WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v24);
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
    FwInitializeHashContext(&v56);
    v35 = -1;
    do
      ++v35;
    while ( *(_WORD *)(a3 + 2 * v35) );
    FwUpdateHash(a3, (unsigned int)(2 * v35), &v56);
    v36 = FwFinalHash(&v56);
    FwResrcPerPackageCollFindByPackageIdSignature(v36, a2, a3, &v52);
    v37 = v52;
    if ( !v52 )
    {
      v38 = FwAlloc(48);
      v51 = (_QWORD *)v38;
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
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v18);
        goto LABEL_15;
      }
      v51[5] = v51 + 4;
      v51[4] = v51 + 4;
      v51[2] = v36;
      if ( (unsigned int)FwHashtableInsert(&qword_18012FCD0[v31], v51) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      FwRestructureHashtable(&qword_18012FCD0[v31]);
      v37 = v51;
      v49 = 1;
    }
    v40 = v37 + 4;
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
      WPP_SF_d(*(_QWORD *)(v33 + 16), v34, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v32);
      goto LABEL_15;
    }
    v40 = &qword_18012FCD0[v31 + 6];
  }
  v41 = *v40;
  if ( *(__int64 **)(*v40 + 8) != v40 )
LABEL_86:
    __fastfail(3u);
  *(_QWORD *)v15 = v41;
  *(_QWORD *)(v15 + 8) = v40;
  *(_QWORD *)(v41 + 8) = v15;
  v42 = v54;
  *v40 = v15;
  v43 = qword_180130108 + 1;
  qword_180130108 = v43;
  *(_QWORD *)(v15 + 208) = v43;
  *v42 = v43;
  if ( *(_DWORD *)((char *)&TupleCollection + v31 * 8 + 8) )
  {
    v44 = FwFWRuleMatchesAddrKeywords;
    v55 = FwAddressKeywordFromTupleCollection(a2);
    FwDynDataNLADeleteAddressStoreByProfileAndAddressKeyword(0x7FFFFFFF, v55);
  }
  else
  {
    v44 = FwFWRuleMatchesTrustTupleKeywords;
    v55 = FwTupleKeywordFromTupleCollection(a2);
  }
  updated = FwUpdateAllWithCriteria((_DWORD)v44, 0, 0, (unsigned int)&v55, 0, 0, 0);
  v18 = FwHResultToWindowsError(updated);
  if ( v18 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v18);
    v46 = *(_QWORD *)v15;
    if ( *(_QWORD *)(*(_QWORD *)v15 + 8LL) == v15 )
    {
      v47 = *(_QWORD **)(v15 + 8);
      if ( *v47 == v15 )
      {
        *v47 = v46;
        *(_QWORD *)(v46 + 8) = v47;
        goto LABEL_15;
      }
    }
    goto LABEL_86;
  }
LABEL_20:
  FwUnlockInternal(v53, "RPC_FWIndicateTupleInUse");
LABEL_21:
  FwReleaseRPCSharedLock("RPC_FWIndicateTupleInUse");
  if ( !v18 && v20 == 7 )
    FwAddrChangeSourceSignal();
  return v18;
}

```

## disassembly

```asm
0x180057170  mov     [rsp-8+arg_18], rbx
0x180057175  push    rbp
0x180057176  push    rsi
0x180057177  push    rdi
0x180057178  push    r12
0x18005717a  push    r13
0x18005717c  push    r14
0x18005717e  push    r15
0x180057180  lea     rbp, [rsp-7]
0x180057185  sub     rsp, 90h
0x18005718c  mov     rax, cs:__security_cookie
0x180057193  xor     rax, rsp
0x180057196  mov     [rbp+37h+var_40], rax
0x18005719a  mov     rax, [rbp+37h+arg_58]
0x1800571a1  xor     edi, edi
0x1800571a3  mov     r15, [rbp+37h+arg_38]
0x1800571a7  mov     r14, r8
0x1800571aa  mov     rsi, [rbp+37h+arg_40]
0x1800571b1  mov     r12, [rbp+37h+arg_48]
0x1800571b8  mov     r13, [rbp+37h+arg_50]
0x1800571bf  mov     [rbp+37h+var_60], rcx
0x1800571c3  lea     rcx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x1800571ca  mov     [rax], rdi
0x1800571cd  mov     [rbp+37h+var_74], r9d
0x1800571d1  mov     [rbp+37h+var_7C], edx
0x1800571d4  mov     [rbp+37h+var_58], rax
0x1800571d8  mov     [rbp+37h+var_68], rdi
0x1800571dc  mov     [rbp+37h+var_48], rdi
0x1800571e0  mov     [rbp+37h+var_50], edi
0x1800571e3  call    FwAcquireRPCSharedLock
0x1800571e8  test    eax, eax
0x1800571ea  jns     short loc_180057222
0x1800571ec  mov     ecx, eax
0x1800571ee  call    cs:__imp_FwHResultToWindowsError
0x1800571f5  nop     dword ptr [rax+rax+00h]
0x1800571fa  mov     rcx, [rbp+37h+var_40]
0x1800571fe  xor     rcx, rsp; StackCookie
0x180057201  call    __security_check_cookie
0x180057206  mov     rbx, [rsp+0C0h+arg_18]
0x18005720e  add     rsp, 90h
0x180057215  pop     r15
0x180057217  pop     r14
0x180057219  pop     r13
0x18005721b  pop     r12
0x18005721d  pop     rdi
0x18005721e  pop     rsi
0x18005721f  pop     rbp
0x180057220  retn
0x180057222  mov     rbx, rdi
0x180057225  mov     [rbp+37h+var_70], rdi
0x180057229  mov     [rbp+37h+var_78], edi
0x18005722c  call    FwLock
0x180057231  mov     ecx, eax
0x180057233  call    cs:__imp_FwHResultToWindowsError
0x18005723a  nop     dword ptr [rax+rax+00h]
0x18005723f  mov     edi, eax
0x180057241  xor     eax, eax
0x180057243  test    edi, edi
0x180057245  jz      short loc_180057288
0x180057247  mov     r14d, eax
0x18005724a  mov     rax, cs:WPP_GLOBAL_Control
0x180057251  lea     rcx, WPP_GLOBAL_Control
0x180057258  cmp     rax, rcx
0x18005725b  jz      short loc_18005727B
0x18005725d  test    byte ptr [rax+1Ch], 1
0x180057261  jz      short loc_18005727B
0x180057263  mov     rcx, [rax+10h]
0x180057267  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x18005726e  mov     edx, 2Ch ; ','
0x180057273  mov     r9d, edi
0x180057276  call    WPP_SF_d
0x18005727b  mov     r12d, [rbp+37h+var_7C]
0x18005727f  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x180057286  jmp     short loc_1800572F3
0x180057288  mov     r8, [rbp+37h+var_60]
0x18005728c  mov     ecx, [rbp+37h+var_7C]
0x18005728f  mov     [rbp+37h+var_80], 1
0x180057296  call    ?FwResrcIndicationTupleAccessCheckForClient@@YAJW4_tag_FW_TUPLE_COLLECTION_TYPE@@KPEAX@Z; FwResrcIndicationTupleAccessCheckForClient(_tag_FW_TUPLE_COLLECTION_TYPE,ulong,void *)
0x18005729b  mov     ecx, eax
0x18005729d  call    cs:__imp_FwHResultToWindowsError
0x1800572a4  nop     dword ptr [rax+rax+00h]
0x1800572a9  mov     edi, eax
0x1800572ab  test    eax, eax
0x1800572ad  jz      loc_18005738B
0x1800572b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800572ba  lea     rcx, WPP_GLOBAL_Control
0x1800572c1  cmp     rax, rcx
0x1800572c4  jz      short loc_1800572E4
0x1800572c6  test    byte ptr [rax+1Ch], 1
0x1800572ca  jz      short loc_1800572E4
0x1800572cc  mov     edx, 2Dh ; '-'
0x1800572d1  mov     r9d, edi
0x1800572d4  mov     rcx, [rax+10h]
0x1800572d8  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x1800572df  call    WPP_SF_d
0x1800572e4  mov     r12d, [rbp+37h+var_7C]
0x1800572e8  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x1800572ef  mov     r14d, [rbp+37h+var_80]
0x1800572f3  mov     rcx, rbx; struct _tag_FW_RESRC_TUPLE_ENTRY *
0x1800572f6  call    ?FwTupleEntryFree@@YAXPEAU_tag_FW_RESRC_TUPLE_ENTRY@@@Z; FwTupleEntryFree(_tag_FW_RESRC_TUPLE_ENTRY *)
0x1800572fb  mov     rsi, [rbp+37h+var_70]
0x1800572ff  test    rsi, rsi
0x180057302  jz      short loc_18005733E
0x180057304  cmp     [rbp+37h+var_78], 1
0x180057308  jnz     short loc_18005733E
0x18005730a  movsxd  rax, r12d
0x18005730d  mov     rdx, rsi
0x180057310  lea     rbx, [rax+rax*2]
0x180057314  shl     rbx, 5
0x180057318  lea     rcx, [rbx+20h]
0x18005731c  add     rcx, r13
0x18005731f  call    cs:__imp_FwHashtableRemove
0x180057326  nop     dword ptr [rax+rax+00h]
0x18005732b  lea     rcx, [rbx+20h]
0x18005732f  add     rcx, r13
0x180057332  call    cs:__imp_FwRestructureHashtable
0x180057339  nop     dword ptr [rax+rax+00h]
0x18005733e  mov     rcx, rsi
0x180057341  call    cs:__imp_FwFree
0x180057348  nop     dword ptr [rax+rax+00h]
0x18005734d  test    r14d, r14d
0x180057350  jz      short loc_180057362
0x180057352  mov     rcx, [rbp+37h+var_60]; void *
0x180057356  lea     rdx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x18005735d  call    FwUnlockInternal
0x180057362  lea     rcx, aRpcFwindicatet; "RPC_FWIndicateTupleInUse"
0x180057369  call    FwReleaseRPCSharedLock
0x18005736e  test    edi, edi
0x180057370  jnz     short loc_180057384
0x180057372  cmp     r12d, 7
0x180057376  jnz     short loc_180057384
0x180057378  call    cs:__imp_FwAddrChangeSourceSignal
0x18005737f  nop     dword ptr [rax+rax+00h]
0x180057384  mov     eax, edi
0x180057386  jmp     loc_1800571FA
0x18005738b  mov     ecx, 0D8h
0x180057390  call    cs:__imp_FwAlloc
0x180057397  nop     dword ptr [rax+rax+00h]
0x18005739c  xor     edi, edi
0x18005739e  mov     rbx, rax
0x1800573a1  test    rax, rax
0x1800573a4  jnz     short loc_1800573D6
0x1800573a6  lea     r9d, [rax+0Eh]
0x1800573aa  mov     edi, r9d
0x1800573ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800573b4  lea     rcx, WPP_GLOBAL_Control
0x1800573bb  cmp     rax, rcx
0x1800573be  jz      loc_1800572E4
0x1800573c4  test    byte ptr [rax+1Ch], 1
0x1800573c8  jz      loc_1800572E4
0x1800573ce  lea     edx, [rbx+2Eh]
0x1800573d1  jmp     loc_1800572D4
0x1800573d6  mov     eax, [rbp+37h+var_74]
0x1800573d9  mov     [rbx+10h], eax
0x1800573dc  movzx   eax, [rbp+37h+arg_20]
0x1800573e0  mov     [rbx+14h], ax
0x1800573e4  movzx   eax, [rbp+37h+arg_28]
0x1800573e8  mov     [rbx+18h], ax
0x1800573ec  mov     [rbx+16h], ax
0x1800573f0  movzx   eax, [rbp+37h+arg_30]
0x1800573f4  mov     [rbx+1Ch], ax
0x1800573f8  mov     [rbx+1Ah], ax
0x1800573fc  test    r15, r15
0x1800573ff  jz      short loc_180057455
0x180057401  lea     rdx, [rbx+20h]
0x180057405  mov     rcx, r15
0x180057408  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18005740f  nop     dword ptr [rax+rax+00h]
0x180057414  mov     ecx, eax
0x180057416  call    cs:__imp_FwHResultToWindowsError
0x18005741d  nop     dword ptr [rax+rax+00h]
0x180057422  mov     edi, eax
0x180057424  test    eax, eax
0x180057426  jz      short loc_180057453
0x180057428  mov     rax, cs:WPP_GLOBAL_Control
0x18005742f  lea     rcx, WPP_GLOBAL_Control
0x180057436  cmp     rax, rcx
0x180057439  jz      loc_1800572E4
0x18005743f  test    byte ptr [rax+1Ch], 1
0x180057443  jz      loc_1800572E4
0x180057449  mov     edx, 2Fh ; '/'
0x18005744e  jmp     loc_1800572D1
0x180057453  xor     edi, edi
0x180057455  test    rsi, rsi
0x180057458  jz      short loc_1800574AE
0x18005745a  lea     rdx, [rbx+68h]
0x18005745e  mov     rcx, rsi
0x180057461  call    cs:__imp_FwPolioCopyWFAddressesContents
0x180057468  nop     dword ptr [rax+rax+00h]
0x18005746d  mov     ecx, eax
0x18005746f  call    cs:__imp_FwHResultToWindowsError
0x180057476  nop     dword ptr [rax+rax+00h]
0x18005747b  mov     edi, eax
0x18005747d  test    eax, eax
0x18005747f  jz      short loc_1800574AC
0x180057481  mov     rax, cs:WPP_GLOBAL_Control
0x180057488  lea     rcx, WPP_GLOBAL_Control
0x18005748f  cmp     rax, rcx
0x180057492  jz      loc_1800572E4
0x180057498  test    byte ptr [rax+1Ch], 1
0x18005749c  jz      loc_1800572E4
0x1800574a2  mov     edx, 30h ; '0'
0x1800574a7  jmp     loc_1800572D1
0x1800574ac  xor     edi, edi
0x1800574ae  test    r12, r12
0x1800574b1  jz      short loc_18005750A
0x1800574b3  lea     rdx, [rbx+0B0h]
0x1800574ba  mov     rcx, r12
0x1800574bd  call    cs:__imp_FwCopyInterfaceLuids
0x1800574c4  nop     dword ptr [rax+rax+00h]
0x1800574c9  mov     ecx, eax
0x1800574cb  call    cs:__imp_FwHResultToWindowsError
0x1800574d2  nop     dword ptr [rax+rax+00h]
0x1800574d7  mov     edi, eax
0x1800574d9  test    eax, eax
0x1800574db  jz      short loc_180057508
0x1800574dd  mov     rax, cs:WPP_GLOBAL_Control
0x1800574e4  lea     rcx, WPP_GLOBAL_Control
0x1800574eb  cmp     rax, rcx
0x1800574ee  jz      loc_1800572E4
0x1800574f4  test    byte ptr [rax+1Ch], 1
0x1800574f8  jz      loc_1800572E4
0x1800574fe  mov     edx, 31h ; '1'
0x180057503  jmp     loc_1800572D1
0x180057508  xor     edi, edi
0x18005750a  test    r13, r13
0x18005750d  jz      short loc_18005755F
0x18005750f  lea     rdx, [rbx+0C0h]; struct _tag_FW_INTERFACE_INDEXES *
0x180057516  mov     rcx, r13; struct _tag_FW_INTERFACE_INDEXES *
0x180057519  call    ?FwCopyInterfaceIndexesInt@@YAJPEBU_tag_FW_INTERFACE_INDEXES@@PEAU1@@Z; FwCopyInterfaceIndexesInt(_tag_FW_INTERFACE_INDEXES const *,_tag_FW_INTERFACE_INDEXES *)
0x18005751e  mov     ecx, eax
0x180057520  call    cs:__imp_FwHResultToWindowsError
0x180057527  nop     dword ptr [rax+rax+00h]
0x18005752c  mov     edi, eax
0x18005752e  test    eax, eax
0x180057530  jz      short loc_18005755D
0x180057532  mov     rax, cs:WPP_GLOBAL_Control
0x180057539  lea     rcx, WPP_GLOBAL_Control
0x180057540  cmp     rax, rcx
0x180057543  jz      loc_1800572E4
0x180057549  test    byte ptr [rax+1Ch], 1
0x18005754d  jz      loc_1800572E4
0x180057553  mov     edx, 32h ; '2'
0x180057558  jmp     loc_1800572D1
0x18005755d  xor     edi, edi
0x18005755f  movsxd  r12, [rbp+37h+var_7C]
0x180057563  lea     r13, ?TupleCollection@@3PAU_tag_FW_RESRC_TUPLE_COLLECTION@@A; _tag_FW_RESRC_TUPLE_COLLECTION near * TupleCollection
0x18005756a  lea     rsi, [r12+r12*2]
0x18005756e  shl     rsi, 5
0x180057572  cmp     [rsi+r13+0Ch], edi
0x180057577  jz      loc_18005773B
0x18005757d  test    r14, r14
0x180057580  jnz     short loc_1800575C3
0x180057582  lea     r9d, [r14+57h]
0x180057586  mov     edi, r9d
0x180057589  mov     rax, cs:WPP_GLOBAL_Control
0x180057590  lea     rcx, WPP_GLOBAL_Control
0x180057597  cmp     rax, rcx
0x18005759a  jz      loc_1800572EF
0x1800575a0  test    byte ptr [rax+1Ch], 1
0x1800575a4  jz      loc_1800572EF
0x1800575aa  lea     edx, [r14+33h]
0x1800575ae  mov     rcx, [rax+10h]
0x1800575b2  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x1800575b9  call    WPP_SF_d
0x1800575be  jmp     loc_1800572EF
0x1800575c3  lea     rcx, [rbp+37h+var_48]
0x1800575c7  call    cs:__imp_FwInitializeHashContext
0x1800575ce  nop     dword ptr [rax+rax+00h]
0x1800575d3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800575d7  inc     rdx
0x1800575da  cmp     [r14+rdx*2], di
0x1800575df  jnz     short loc_1800575D7
0x1800575e1  add     edx, edx
0x1800575e3  lea     r8, [rbp+37h+var_48]
0x1800575e7  mov     rcx, r14
0x1800575ea  call    cs:__imp_FwUpdateHash
0x1800575f1  nop     dword ptr [rax+rax+00h]
0x1800575f6  lea     rcx, [rbp+37h+var_48]
0x1800575fa  call    cs:__imp_FwFinalHash
0x180057601  nop     dword ptr [rax+rax+00h]
0x180057606  lea     r9, [rbp+37h+var_68]
0x18005760a  mov     r8, r14
0x18005760d  mov     rcx, rax
0x180057610  mov     edx, r12d
0x180057613  mov     r15, rax
0x180057616  call    ?FwResrcPerPackageCollFindByPackageIdSignature@@YAK_KW4_tag_FW_TUPLE_COLLECTION_TYPE@@PEBGPEAPEAU_tag_FW_RESRC_TUPLE_PER_PACKAGEID@@@Z; FwResrcPerPackageCollFindByPackageIdSignature(unsigned __int64,_tag_FW_TUPLE_COLLECTION_TYPE,ushort const *,_tag_FW_RESRC_TUPLE_PER_PACKAGEID * *)
0x18005761b  mov     rax, [rbp+37h+var_68]
0x18005761f  test    rax, rax
0x180057622  jnz     loc_180057735
0x180057628  lea     ecx, [rax+30h]
0x18005762b  call    cs:__imp_FwAlloc
0x180057632  nop     dword ptr [rax+rax+00h]
0x180057637  mov     [rbp+37h+var_70], rax
0x18005763b  test    rax, rax
0x18005763e  jnz     short loc_180057671
0x180057640  lea     r9d, [rax+0Eh]
0x180057644  mov     edi, r9d
0x180057647  mov     rax, cs:WPP_GLOBAL_Control
0x18005764e  lea     rcx, WPP_GLOBAL_Control
  ... truncated ...
```
