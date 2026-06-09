# DhcpPolicyCriteriaFeatureListInit

- ea: `0x1800ba924`
- end: `0x1800baadd`
- name: `DhcpPolicyCriteriaFeatureListInit`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025144`

## callees

- `0x1800932a8`
- `0x180096698`
- `0x1800ba924`
- `0x1800babf0`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndex2A` at `0x1800ba972`
- `ESENT!JetSetCurrentIndex2A` at `0x1800ba972`
- `ESENT!JetRetrieveColumn` at `0x1800ba9d0`
- `ESENT!JetRetrieveColumn` at `0x1800baa21`
- `ESENT!JetRetrieveColumn` at `0x1800ba9d0`
- `ESENT!JetRetrieveColumn` at `0x1800baa21`
- `ESENT!JetMove` at `0x1800baaa5`
- `ESENT!JetMove` at `0x1800baaa5`

## string_xrefs

- `0x1800baab1`: `DhcpPolicyCriteriaFeatureListInit:JetMove`

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
    v9 = JetRetrieveColumn(v2, PolicyConditionTableId, dword_1800F9580, &pvData, 4u, 0, 1u, 0);
    CriteriaFromConditionTableRecord = PolicyMapJetError(
                                         v9,
                                         "DhcpPolicyGetCriteriaFeaturesFromConditionTableRecord:RetrieveColumn1");
    if ( CriteriaFromConditionTableRecord )
      break;
    v10 = JetRetrieveColumn(v2, PolicyConditionTableId, dword_1800F95F8, &v17, 4u, 0, 1u, 0);
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
0x1800ba924  mov     [rsp-28h+arg_8], rdx
0x1800ba929  mov     [rsp-28h+pvData], rcx
0x1800ba92e  push    rbp
0x1800ba92f  push    rbx
0x1800ba930  push    rsi
0x1800ba931  push    rdi
0x1800ba932  push    r14
0x1800ba934  mov     rbp, rsp
0x1800ba937  sub     rsp, 50h
0x1800ba93b  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800ba942  lea     r8, aPolicyconditio_3; "PolicyConditionTable_Index7"
0x1800ba949  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba950  xor     ebx, ebx
0x1800ba952  mov     r14, cs:DhcpGlobalThisServer
0x1800ba959  xorps   xmm0, xmm0
0x1800ba95c  mov     rcx, rsi; sesid
0x1800ba95f  mov     dword ptr [rbp+arg_8], ebx
0x1800ba962  xor     r9d, r9d; grbit
0x1800ba965  mov     dword ptr [rbp+pvData], ebx
0x1800ba968  mov     edi, ebx
0x1800ba96a  mov     [rbp+arg_10], rbx
0x1800ba96e  movups  [rbp+var_10], xmm0
0x1800ba972  call    cs:__imp_JetSetCurrentIndex2A
0x1800ba979  nop     dword ptr [rax+rax+00h]
0x1800ba97e  lea     rdx, aDhcppolicycrit; "DhcpPolicyCriteriaFeatureListInit:SetCu"...
0x1800ba985  jmp     loc_1800BAAB8
0x1800ba98a  lea     r8, [rbp+var_10]
0x1800ba98e  mov     rdx, r14
0x1800ba991  mov     rcx, rsi; sesid
0x1800ba994  call    DhcpPolicyGetCriteriaFromConditionTableRecord
0x1800ba999  test    eax, eax
0x1800ba99b  jnz     loc_1800BAAC7
0x1800ba9a1  mov     r8d, cs:dword_1800F9580; columnid
0x1800ba9a8  lea     r9, [rbp+pvData]; pvData
0x1800ba9ac  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba9b3  mov     rcx, rsi; sesid
0x1800ba9b6  mov     [rsp+50h+pretinfo], rbx; pretinfo
0x1800ba9bb  mov     [rsp+50h+grbit], 1; grbit
0x1800ba9c3  mov     [rsp+50h+pcbActual], rbx; pcbActual
0x1800ba9c8  mov     [rsp+50h+cbData], 4; cbData
0x1800ba9d0  call    cs:__imp_JetRetrieveColumn
0x1800ba9d7  nop     dword ptr [rax+rax+00h]
0x1800ba9dc  mov     ecx, eax
0x1800ba9de  lea     rdx, aDhcppolicygetc_3; "DhcpPolicyGetCriteriaFeaturesFromCondit"...
0x1800ba9e5  call    PolicyMapJetError
0x1800ba9ea  test    eax, eax
0x1800ba9ec  jnz     loc_1800BAAC7
0x1800ba9f2  mov     r8d, cs:dword_1800F95F8; columnid
0x1800ba9f9  lea     r9, [rbp+arg_8]; pvData
0x1800ba9fd  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800baa04  mov     rcx, rsi; sesid
0x1800baa07  mov     [rsp+50h+pretinfo], rbx; pretinfo
0x1800baa0c  mov     [rsp+50h+grbit], 1; grbit
0x1800baa14  mov     [rsp+50h+pcbActual], rbx; pcbActual
0x1800baa19  mov     [rsp+50h+cbData], 4; cbData
0x1800baa21  call    cs:__imp_JetRetrieveColumn
0x1800baa28  nop     dword ptr [rax+rax+00h]
0x1800baa2d  mov     ecx, eax
0x1800baa2f  lea     rdx, aDhcppolicygetc_2; "DhcpPolicyGetCriteriaFeaturesFromCondit"...
0x1800baa36  call    PolicyMapJetError
0x1800baa3b  test    eax, eax
0x1800baa3d  jnz     loc_1800BAAC7
0x1800baa43  mov     edx, dword ptr [rbp+pvData]
0x1800baa46  test    edx, edx
0x1800baa48  jnz     short loc_1800BAA53
0x1800baa4a  lea     rcx, [r14+10D8h]
0x1800baa51  jmp     short loc_1800BAA85
0x1800baa53  test    rdi, rdi
0x1800baa56  jz      short loc_1800BAA5D
0x1800baa58  cmp     [rdi+8], edx
0x1800baa5b  jz      short loc_1800BAA7E
0x1800baa5d  mov     [rsp+50h+pcbActual], rbx
0x1800baa62  lea     r8, [rbp+arg_10]
0x1800baa66  xor     r9d, r9d
0x1800baa69  mov     qword ptr [rsp+50h+cbData], rbx
0x1800baa6e  mov     rcx, r14
0x1800baa71  call    MemServerGetUAddressInfo
0x1800baa76  mov     rdi, [rbp+arg_10]
0x1800baa7a  test    eax, eax
0x1800baa7c  jnz     short loc_1800BAA92
0x1800baa7e  lea     rcx, [rdi+1118h]
0x1800baa85  mov     r8d, dword ptr [rbp+arg_8]
0x1800baa89  lea     rdx, [rbp+var_10]
0x1800baa8d  call    MemAddCriteriaFeature
0x1800baa92  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800baa99  mov     r9d, 1; grbit
0x1800baa9f  mov     r8d, r9d; cRow
0x1800baaa2  mov     rcx, rsi; sesid
0x1800baaa5  call    cs:__imp_JetMove
0x1800baaac  nop     dword ptr [rax+rax+00h]
0x1800baab1  lea     rdx, aDhcppolicycrit_0; "DhcpPolicyCriteriaFeatureListInit:JetMo"...
0x1800baab8  mov     ecx, eax
0x1800baaba  call    PolicyMapJetError
0x1800baabf  test    eax, eax
0x1800baac1  jz      loc_1800BA98A
0x1800baac7  cmp     eax, 103h
0x1800baacc  cmovnz  ebx, eax
0x1800baacf  mov     eax, ebx
0x1800baad1  add     rsp, 50h
0x1800baad5  pop     r14
0x1800baad7  pop     rdi
0x1800baad8  pop     rsi
0x1800baad9  pop     rbx
0x1800baada  pop     rbp
0x1800baadb  retn
```
