# DhcpPolicyCriteriaFeatureListInit

- ea: `0x1800b9a0c`
- end: `0x1800b9bc5`
- name: `DhcpPolicyCriteriaFeatureListInit`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025bf4`

## callees

- `0x1800930bc`
- `0x180096450`
- `0x1800b9a0c`
- `0x1800b9cdc`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndex2A` at `0x1800b9a5a`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b9a5a`
- `ESENT!JetRetrieveColumn` at `0x1800b9ab8`
- `ESENT!JetRetrieveColumn` at `0x1800b9b09`
- `ESENT!JetRetrieveColumn` at `0x1800b9ab8`
- `ESENT!JetRetrieveColumn` at `0x1800b9b09`
- `ESENT!JetMove` at `0x1800b9b8d`
- `ESENT!JetMove` at `0x1800b9b8d`

## string_xrefs

- `0x1800b9b99`: `DhcpPolicyCriteriaFeatureListInit:JetMove`

## pseudocode

```c
__int64 __fastcall DhcpPolicyCriteriaFeatureListInit(__int64 a1, __int64 a2)
{
  JET_SESID v2; // rsi
  unsigned int v3; // ebx
  char *v4; // r14
  __int64 v5; // rdi
  unsigned int v6; // eax
  const char *i; // rdx
  unsigned int CriteriaFromConditionTableRecord; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  char *v11; // rcx
  int UAddressInfo; // eax
  __int128 v14; // [rsp+40h] [rbp-10h] BYREF
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  int pvData_4; // [rsp+84h] [rbp+34h]
  unsigned int v17; // [rsp+88h] [rbp+38h] BYREF
  int v18; // [rsp+8Ch] [rbp+3Ch]
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF

  v18 = HIDWORD(a2);
  pvData_4 = HIDWORD(a1);
  v2 = DhcpGlobalJetServerSession;
  v3 = 0;
  v4 = (char *)DhcpGlobalThisServer;
  v17 = 0;
  pvData = 0;
  v5 = 0;
  v19 = 0;
  v14 = 0;
  v6 = JetSetCurrentIndex2A(DhcpGlobalJetServerSession, PolicyConditionTableId, "PolicyConditionTable_Index7", 0);
  for ( i = "DhcpPolicyCriteriaFeatureListInit:SetCurrentIndex2"; ; i = "DhcpPolicyCriteriaFeatureListInit:JetMove" )
  {
    CriteriaFromConditionTableRecord = PolicyMapJetError(v6, i);
    if ( CriteriaFromConditionTableRecord )
      break;
    CriteriaFromConditionTableRecord = DhcpPolicyGetCriteriaFromConditionTableRecord(v2);
    if ( CriteriaFromConditionTableRecord )
      break;
    v9 = JetRetrieveColumn(v2, PolicyConditionTableId, dword_1800F7770, &pvData, 4u, 0, 1u, 0);
    CriteriaFromConditionTableRecord = PolicyMapJetError(
                                         v9,
                                         "DhcpPolicyGetCriteriaFeaturesFromConditionTableRecord:RetrieveColumn1");
    if ( CriteriaFromConditionTableRecord )
      break;
    v10 = JetRetrieveColumn(v2, PolicyConditionTableId, dword_1800F77E8, &v17, 4u, 0, 1u, 0);
    CriteriaFromConditionTableRecord = PolicyMapJetError(
                                         v10,
                                         "DhcpPolicyGetCriteriaFeaturesFromConditionTableRecord:RetrieveColumn2");
    if ( CriteriaFromConditionTableRecord )
      break;
    if ( !pvData )
    {
      v11 = v4 + 4312;
LABEL_11:
      MemAddCriteriaFeature(v11, &v14, v17);
      goto LABEL_12;
    }
    if ( v5 && *(_DWORD *)(v5 + 8) == pvData
      || (UAddressInfo = MemServerGetUAddressInfo((_DWORD)v4, pvData, (unsigned int)&v19, 0, 0, 0),
          v5 = v19,
          !UAddressInfo) )
    {
      v11 = (char *)(v5 + 4376);
      goto LABEL_11;
    }
LABEL_12:
    v6 = JetMove(v2, PolicyConditionTableId, 1, 1u);
  }
  if ( CriteriaFromConditionTableRecord != 259 )
    return CriteriaFromConditionTableRecord;
  return v3;
}

```

## disassembly

```asm
0x1800b9a0c  mov     [rsp-28h+arg_8], rdx
0x1800b9a11  mov     [rsp-28h+pvData], rcx
0x1800b9a16  push    rbp
0x1800b9a17  push    rbx
0x1800b9a18  push    rsi
0x1800b9a19  push    rdi
0x1800b9a1a  push    r14
0x1800b9a1c  mov     rbp, rsp
0x1800b9a1f  sub     rsp, 50h
0x1800b9a23  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800b9a2a  lea     r8, aPolicyconditio_3; "PolicyConditionTable_Index7"
0x1800b9a31  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9a38  xor     ebx, ebx
0x1800b9a3a  mov     r14, cs:DhcpGlobalThisServer
0x1800b9a41  xorps   xmm0, xmm0
0x1800b9a44  mov     rcx, rsi; sesid
0x1800b9a47  mov     dword ptr [rbp+arg_8], ebx
0x1800b9a4a  xor     r9d, r9d; grbit
0x1800b9a4d  mov     dword ptr [rbp+pvData], ebx
0x1800b9a50  mov     edi, ebx
0x1800b9a52  mov     [rbp+arg_10], rbx
0x1800b9a56  movups  [rbp+var_10], xmm0
0x1800b9a5a  call    cs:__imp_JetSetCurrentIndex2A
0x1800b9a61  nop     dword ptr [rax+rax+00h]
0x1800b9a66  lea     rdx, aDhcppolicycrit; "DhcpPolicyCriteriaFeatureListInit:SetCu"...
0x1800b9a6d  jmp     loc_1800B9BA0
0x1800b9a72  lea     r8, [rbp+var_10]
0x1800b9a76  mov     rdx, r14
0x1800b9a79  mov     rcx, rsi; sesid
0x1800b9a7c  call    DhcpPolicyGetCriteriaFromConditionTableRecord
0x1800b9a81  test    eax, eax
0x1800b9a83  jnz     loc_1800B9BAF
0x1800b9a89  mov     r8d, cs:dword_1800F7770; columnid
0x1800b9a90  lea     r9, [rbp+pvData]; pvData
0x1800b9a94  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9a9b  mov     rcx, rsi; sesid
0x1800b9a9e  mov     [rsp+50h+pretinfo], rbx; pretinfo
0x1800b9aa3  mov     [rsp+50h+grbit], 1; grbit
0x1800b9aab  mov     [rsp+50h+pcbActual], rbx; pcbActual
0x1800b9ab0  mov     [rsp+50h+cbData], 4; cbData
0x1800b9ab8  call    cs:__imp_JetRetrieveColumn
0x1800b9abf  nop     dword ptr [rax+rax+00h]
0x1800b9ac4  mov     ecx, eax
0x1800b9ac6  lea     rdx, aDhcppolicygetc_3; "DhcpPolicyGetCriteriaFeaturesFromCondit"...
0x1800b9acd  call    PolicyMapJetError
0x1800b9ad2  test    eax, eax
0x1800b9ad4  jnz     loc_1800B9BAF
0x1800b9ada  mov     r8d, cs:dword_1800F77E8; columnid
0x1800b9ae1  lea     r9, [rbp+arg_8]; pvData
0x1800b9ae5  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9aec  mov     rcx, rsi; sesid
0x1800b9aef  mov     [rsp+50h+pretinfo], rbx; pretinfo
0x1800b9af4  mov     [rsp+50h+grbit], 1; grbit
0x1800b9afc  mov     [rsp+50h+pcbActual], rbx; pcbActual
0x1800b9b01  mov     [rsp+50h+cbData], 4; cbData
0x1800b9b09  call    cs:__imp_JetRetrieveColumn
0x1800b9b10  nop     dword ptr [rax+rax+00h]
0x1800b9b15  mov     ecx, eax
0x1800b9b17  lea     rdx, aDhcppolicygetc_2; "DhcpPolicyGetCriteriaFeaturesFromCondit"...
0x1800b9b1e  call    PolicyMapJetError
0x1800b9b23  test    eax, eax
0x1800b9b25  jnz     loc_1800B9BAF
0x1800b9b2b  mov     edx, dword ptr [rbp+pvData]
0x1800b9b2e  test    edx, edx
0x1800b9b30  jnz     short loc_1800B9B3B
0x1800b9b32  lea     rcx, [r14+10D8h]
0x1800b9b39  jmp     short loc_1800B9B6D
0x1800b9b3b  test    rdi, rdi
0x1800b9b3e  jz      short loc_1800B9B45
0x1800b9b40  cmp     [rdi+8], edx
0x1800b9b43  jz      short loc_1800B9B66
0x1800b9b45  mov     [rsp+50h+pcbActual], rbx
0x1800b9b4a  lea     r8, [rbp+arg_10]
0x1800b9b4e  xor     r9d, r9d
0x1800b9b51  mov     qword ptr [rsp+50h+cbData], rbx
0x1800b9b56  mov     rcx, r14
0x1800b9b59  call    MemServerGetUAddressInfo
0x1800b9b5e  mov     rdi, [rbp+arg_10]
0x1800b9b62  test    eax, eax
0x1800b9b64  jnz     short loc_1800B9B7A
0x1800b9b66  lea     rcx, [rdi+1118h]
0x1800b9b6d  mov     r8d, dword ptr [rbp+arg_8]
0x1800b9b71  lea     rdx, [rbp+var_10]
0x1800b9b75  call    MemAddCriteriaFeature
0x1800b9b7a  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9b81  mov     r9d, 1; grbit
0x1800b9b87  mov     r8d, r9d; cRow
0x1800b9b8a  mov     rcx, rsi; sesid
0x1800b9b8d  call    cs:__imp_JetMove
0x1800b9b94  nop     dword ptr [rax+rax+00h]
0x1800b9b99  lea     rdx, aDhcppolicycrit_0; "DhcpPolicyCriteriaFeatureListInit:JetMo"...
0x1800b9ba0  mov     ecx, eax
0x1800b9ba2  call    PolicyMapJetError
0x1800b9ba7  test    eax, eax
0x1800b9ba9  jz      loc_1800B9A72
0x1800b9baf  cmp     eax, 103h
0x1800b9bb4  cmovnz  ebx, eax
0x1800b9bb7  mov     eax, ebx
0x1800b9bb9  add     rsp, 50h
0x1800b9bbd  pop     r14
0x1800b9bbf  pop     rdi
0x1800b9bc0  pop     rsi
0x1800b9bc1  pop     rbx
0x1800b9bc2  pop     rbp
0x1800b9bc3  retn
```
