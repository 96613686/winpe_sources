# EvictClusterNodeEx2

- ea: `0x180058330`
- end: `0x180058985`
- name: `EvictClusterNodeEx2`
- size: `1621`
- prototype: `__int64 __fastcall(struct _CNODE *)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800386a0`
- `0x1800582f0`
- `0x180058320`

## callees

- `0x180002f50`
- `0x18001236c`
- `0x180014878`
- `0x18001d1e8`
- `0x18001e58c`
- `0x18001fe7c`
- `0x18001feac`
- `0x18001fff8`
- `0x18002139c`
- `0x1800240a8`
- `0x180026ef4`
- `0x180029410`
- `0x18002adc0`
- `0x18002c220`
- `0x180038494`
- `0x1800384b4`
- `0x18003acf0`
- `0x18003bb08`
- `0x180056438`
- `0x180056684`
- `0x180057b90`
- `0x180058330`
- `0x18006f910`
- `0x18008d258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005850b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005850b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800586b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800586b9`

## string_xrefs

- `0x1800584e6`: `ClusterOpenEnum: %d`
- `0x180058885`: `Failed to make a copy of node name: %d`
- `0x180058784`: `Node %ws was already evicted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EvictClusterNodeEx2(struct _CNODE *a1, unsigned int a2, _DWORD *a3, const wchar_t *a4)
{
  struct _HCLUSTER *v8; // rbx
  const WCHAR *v9; // rcx
  int *v10; // r8
  unsigned int LastError; // ebx
  int ClusterInstanceId; // eax
  struct _HCLUSENUM *v13; // rdi
  unsigned int v14; // r14d
  unsigned int v15; // ebx
  int v16; // eax
  signed int v17; // r14d
  unsigned __int64 v18; // r14
  wchar_t *v19; // rbx
  struct _HCLUSTER *v20; // rcx
  unsigned int v21; // r15d
  signed int v22; // eax
  __int64 v23; // [rsp+28h] [rbp-B1h]
  __int64 v24; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-91h] BYREF
  int NumericNodeId; // [rsp+50h] [rbp-89h] BYREF
  int v27; // [rsp+54h] [rbp-85h] BYREF
  struct _HRESOURCE *v28; // [rsp+58h] [rbp-81h] BYREF
  __int128 v29; // [rsp+60h] [rbp-79h] BYREF
  __int64 v30; // [rsp+70h] [rbp-69h]
  unsigned __int64 v31; // [rsp+78h] [rbp-61h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v33[5]; // [rsp+90h] [rbp-49h] BYREF
  char v34; // [rsp+B8h] [rbp-21h]
  _QWORD v35[4]; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v36; // [rsp+E0h] [rbp+7h] BYREF

  v25 = a2;
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HNODE *>(
                           a1,
                           a1) )
    return 6;
  LODWORD(v24) = 0;
  v8 = (struct _HCLUSTER *)*((_QWORD *)a1 + 4);
  NumericNodeId = 0;
  v27 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v36 = 0;
  v9 = a4;
  if ( !a4 )
    v9 = &base;
  TraceMsg(4u, 0xBu, (__int64)L"EvictClusterNodeEx2", 903, L"(%ws, %ws, %d)", *((_QWORD *)a1 + 5), v9, v25, v24);
  if ( (*((_BYTE *)a1 + 56) & 2) != 0 )
  {
    LastError = EvictClusterCapacityNode((struct _HCLUSTER **)a1, v25, v10, a4);
LABEL_57:
    std::vector<unsigned char>::_Tidy(&v29);
    if ( a3 )
      *a3 = -2147467260;
    return LastError;
  }
  ClusterInstanceId = GetClusterInstanceId(v8);
  LODWORD(v24) = ClusterInstanceId;
  if ( ClusterInstanceId )
  {
    LODWORD(v23) = ClusterInstanceId;
    TraceMsg(2u, 0, (__int64)L"EvictClusterNodeEx2", 914, L"Error getting Cluster Instance Id %d", v23);
  }
  NumericNodeId = GetNumericNodeId(a1);
  if ( NumericNodeId == -1 )
  {
    LODWORD(v24) = GetLastError();
    LODWORD(v23) = v24;
    TraceMsg(2u, 0, (__int64)L"EvictClusterNodeEx2", 921, L"Error getting Node Id %d", v23);
  }
  v33[0] = &v29;
  v33[1] = &v36;
  v33[2] = &NumericNodeId;
  v33[3] = &v25;
  v33[4] = &v24;
  v13 = ClusterOpenEnum(v8, 1u);
  if ( (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LODWORD(v24) = GetLastError();
    LODWORD(v23) = v24;
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 942, L"ClusterOpenEnum: %d", v23);
    LastError = GetLastError();
    if ( (unsigned __int64)v13 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
    goto LABEL_57;
  }
  if ( ClusterGetEnumCount(v13) == 1 )
  {
    v28 = 0;
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v28);
    LODWORD(v24) = GetCoreClusterNameResource(v8, &v28);
    if ( v28 )
      LODWORD(v24) = 5939;
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(&v28);
  }
  if ( (_DWORD)v24 )
  {
    LODWORD(v23) = v24;
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 971, L"GetCoreClusterNameResource: %d", v23);
    v14 = v24;
    if ( (int)v24 > 0 )
      v15 = (unsigned __int16)v24 | 0x80070000;
    else
      v15 = v24;
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
    std::vector<unsigned char>::_Tidy(&v29);
    if ( a3 )
      *a3 = v15;
    return v14;
  }
  v16 = ClusterEnumContainsNode(v13, a1, &v27);
  LODWORD(v24) = v16;
  if ( v16 )
  {
    LODWORD(v23) = v16;
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 987, L"ClusterEnumContainsNode: %d", v23);
    LastError = v24;
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
    goto LABEL_57;
  }
  if ( !v27 )
  {
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 981, L"Node not found in cluster: %ws", *((_QWORD *)a1 + 5));
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
    std::vector<unsigned char>::_Tidy(&v29);
    if ( a3 )
      *a3 = -2147467260;
    return 5042;
  }
  v17 = StringCchLengthW(*((const wchar_t **)a1 + 5), 0x7FFFFFFFu, &v31);
  if ( v17 < 0 )
  {
    v19 = 0;
    goto LABEL_50;
  }
  v18 = v31;
  v19 = (wchar_t *)LocalAlloc(0x40u, 2 * v31 + 2);
  CTSmartPtr_PolicyLocalMem::DestroyMem(0);
  if ( !v19 )
  {
    v17 = -2147024882;
    goto LABEL_50;
  }
  v17 = StringCchCopyW(v19, v18 + 1, *((const wchar_t **)a1 + 5));
  if ( v17 < 0 )
  {
LABEL_50:
    LODWORD(v23) = v17;
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 1012, L"Failed to make a copy of node name: %d", v23);
    v21 = (unsigned __int16)v17;
    if ( (v17 & 0x1FFF0000) != 0x70000 )
      v21 = v17;
    LODWORD(v24) = v21;
    CTSmartPtr_PolicyLocalMem::DestroyMem(v19);
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
    goto LABEL_53;
  }
  *((_WORD *)a1 + 28) |= 1u;
  if ( ClusterSupportsReasonString(*((const struct _CLUSTER *const *)a1 + 4)) )
  {
    ClusterReason::ClusterReason((ClusterReason *)&v31, v20, a4);
    v35[0] = "ApiEvictNodeEx";
    v35[1] = (char *)a1 + 48;
    v35[2] = v31;
    v35[3] = a1;
    LODWORD(v24) = ReconnectOnError<EvictNodeExFunctor>(v35, *((_QWORD *)a1 + 4));
    std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(v32);
    v21 = v24;
  }
  else
  {
    v31 = (unsigned __int64)"ApiEvictNode";
    v32[0] = (char *)a1 + 48;
    v32[1] = a1;
    v21 = ReconnectOnError<EvictNodeFunctor>(&v31, v20);
    LODWORD(v24) = v21;
  }
  if ( v21 == 5039 )
  {
    TraceMsg(4u, 0, (__int64)L"EvictClusterNodeEx2", 1032, L"Node %ws was already evicted", v19);
    v21 = 0;
    LODWORD(v24) = 0;
  }
  if ( v21 )
  {
    LODWORD(v23) = v21;
    TraceMsg(2u, 0xBu, (__int64)L"EvictClusterNodeEx2", 1037, L"ReconnectOnError: %d", v23);
    v21 = v24;
    CTSmartPtr_PolicyLocalMem::DestroyMem(v19);
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
  }
  else
  {
    if ( v25 != -2 )
    {
      v22 = DestroyNode((unsigned __int64)v19, v25, 1u);
      v17 = v22;
      if ( v22 > 0 )
        v17 = (unsigned __int16)v22 | 0x80070000;
      if ( v17 >= 0 )
      {
        v21 = v24;
      }
      else
      {
        v21 = 5896;
        LODWORD(v24) = 5896;
      }
    }
    CTSmartPtr_PolicyLocalMem::DestroyMem(v19);
    ClusterCloseEnumCommon(v13, 1);
    v34 = 1;
    lambda_1f4e26b8241f84095da9d8c716bb2bdc_::operator()(v33);
  }
LABEL_53:
  std::vector<unsigned char>::_Tidy(&v29);
  if ( a3 )
    *a3 = v17;
  return v21;
}

```

## disassembly

```asm
0x180058330  mov     [rsp-8+arg_10], rbx
0x180058335  push    rbp
0x180058336  push    rsi
0x180058337  push    rdi
0x180058338  push    r12
0x18005833a  push    r13
0x18005833c  push    r14
0x18005833e  push    r15
0x180058340  lea     rbp, [rsp-27h]
0x180058345  sub     rsp, 100h
0x18005834c  mov     rax, cs:__security_cookie
0x180058353  xor     rax, rsp
0x180058356  mov     [rbp+57h+var_40], rax
0x18005835a  mov     r13, r9
0x18005835d  mov     rsi, r8
0x180058360  mov     r15, rcx
0x180058363  mov     [rsp+130h+var_E8], edx
0x180058367  mov     rdx, rcx
0x18005836a  call    ??$Contains@PEAU_HNODE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HNODE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HNODE *>(_HNODE *)
0x18005836f  xor     r12d, r12d
0x180058372  test    al, al
0x180058374  jnz     short loc_180058380
0x180058376  lea     eax, [r12+6]
0x18005837b  jmp     loc_18005895E
0x180058380  mov     dword ptr [rsp+130h+var_F0], r12d
0x180058385  mov     rbx, [r15+20h]
0x180058389  mov     [rsp+130h+var_E0], r12d
0x18005838e  mov     [rsp+130h+var_DC], r12d
0x180058393  mov     [rbp+57h+var_B8], r12
0x180058397  xorps   xmm0, xmm0
0x18005839a  movdqu  [rbp+57h+var_D0], xmm0
0x18005839f  mov     [rbp+57h+var_C0], r12
0x1800583a3  movups  [rbp+57h+var_50], xmm0
0x1800583a7  lea     rax, base
0x1800583ae  mov     rcx, r13
0x1800583b1  test    r13, r13
0x1800583b4  cmovz   rcx, rax
0x1800583b8  mov     eax, [rsp+130h+var_E8]
0x1800583bc  mov     [rsp+130h+var_F8], eax
0x1800583c0  mov     [rsp+130h+var_100], rcx
0x1800583c5  mov     rax, [r15+28h]
0x1800583c9  mov     [rsp+130h+var_108], rax
0x1800583ce  lea     rax, aWsWsD; "(%ws, %ws, %d)"
0x1800583d5  mov     [rsp+130h+var_110], rax
0x1800583da  mov     r9d, 387h
0x1800583e0  lea     rdi, aEvictclusterno_3; "EvictClusterNodeEx2"
0x1800583e7  mov     r8, rdi
0x1800583ea  mov     edx, 0Bh
0x1800583ef  lea     ecx, [rdx-7]
0x1800583f2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800583f7  mov     r14d, 2
0x1800583fd  test    [r15+38h], r14b
0x180058401  jz      short loc_180058419
0x180058403  mov     r9, r13; wchar_t *
0x180058406  mov     edx, [rsp+130h+var_E8]; unsigned int
0x18005840a  mov     rcx, r15; struct _HNODE *
0x18005840d  call    ?EvictClusterCapacityNode@@YAKPEAU_HNODE@@KPEAJPEB_W@Z; EvictClusterCapacityNode(_HNODE *,ulong,long *,wchar_t const *)
0x180058412  mov     ebx, eax
0x180058414  jmp     loc_180058948
0x180058419  lea     rdx, [rbp+57h+var_D0]
0x18005841d  mov     rcx, rbx; hCluster
0x180058420  call    ?GetClusterInstanceId@@YAKPEAU_HCLUSTER@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; GetClusterInstanceId(_HCLUSTER *,std::vector<uchar> &)
0x180058425  mov     dword ptr [rsp+130h+var_F0], eax
0x180058429  test    eax, eax
0x18005842b  jz      short loc_180058450
0x18005842d  mov     dword ptr [rsp+130h+var_108], eax
0x180058431  lea     rax, aErrorGettingCl; "Error getting Cluster Instance Id %d"
0x180058438  mov     [rsp+130h+var_110], rax
0x18005843d  mov     r9d, 392h
0x180058443  mov     r8, rdi
0x180058446  xor     edx, edx
0x180058448  mov     ecx, r14d
0x18005844b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058450  mov     rcx, r15; struct _HNODE *
0x180058453  call    ?GetNumericNodeId@@YAHPEAU_HNODE@@@Z; GetNumericNodeId(_HNODE *)
0x180058458  mov     [rsp+130h+var_E0], eax
0x18005845c  cmp     eax, 0FFFFFFFFh
0x18005845f  jnz     short loc_18005848E
0x180058461  call    cs:__imp_GetLastError
0x180058467  mov     dword ptr [rsp+130h+var_F0], eax
0x18005846b  mov     dword ptr [rsp+130h+var_108], eax
0x18005846f  lea     rax, aErrorGettingNo; "Error getting Node Id %d"
0x180058476  mov     [rsp+130h+var_110], rax
0x18005847b  mov     r9d, 399h
0x180058481  mov     r8, rdi
0x180058484  xor     edx, edx
0x180058486  mov     ecx, r14d
0x180058489  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005848e  lea     rax, [rbp+57h+var_D0]
0x180058492  mov     [rbp+57h+var_A0], rax
0x180058496  lea     rax, [rbp+57h+var_50]
0x18005849a  mov     [rbp+57h+var_98], rax
0x18005849e  lea     rax, [rsp+130h+var_E0]
0x1800584a3  mov     [rbp+57h+var_90], rax
0x1800584a7  lea     rax, [rsp+130h+var_E8]
0x1800584ac  mov     [rbp+57h+var_88], rax
0x1800584b0  lea     rax, [rsp+130h+var_F0]
0x1800584b5  mov     [rbp+57h+var_80], rax
0x1800584b9  mov     r14d, 1
0x1800584bf  mov     edx, r14d; dwType
0x1800584c2  mov     rcx, rbx; hCluster
0x1800584c5  call    ClusterOpenEnum
0x1800584ca  mov     rdi, rax
0x1800584cd  inc     rax
0x1800584d0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800584d6  jnz     short loc_18005853C
0x1800584d8  call    cs:__imp_GetLastError
0x1800584de  mov     dword ptr [rsp+130h+var_F0], eax
0x1800584e2  mov     dword ptr [rsp+130h+var_108], eax
0x1800584e6  lea     rax, aClusteropenenu_1; "ClusterOpenEnum: %d"
0x1800584ed  mov     [rsp+130h+var_110], rax
0x1800584f2  mov     r9d, 3AEh
0x1800584f8  lea     r8, aEvictclusterno_3; "EvictClusterNodeEx2"
0x1800584ff  lea     edx, [r14+0Ah]
0x180058503  lea     ecx, [rdx-9]
0x180058506  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005850b  call    cs:__imp_GetLastError
0x180058511  mov     ebx, eax
0x180058513  lea     rcx, [rdi-1]
0x180058517  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005851b  ja      short loc_180058529
0x18005851d  mov     edx, r14d; int
0x180058520  mov     rcx, rdi; struct _HCLUSENUM *
0x180058523  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058528  nop
0x180058529  mov     [rbp+57h+var_78], r14b
0x18005852d  lea     rcx, [rbp+57h+var_A0]
0x180058531  call    _lambda_1f4e26b8241f84095da9d8c716bb2bdc___operator__
0x180058536  nop
0x180058537  jmp     loc_180058948
0x18005853c  mov     rcx, rdi; hEnum
0x18005853f  call    ClusterGetEnumCount
0x180058544  cmp     eax, r14d
0x180058547  jnz     short loc_180058582
0x180058549  mov     [rsp+130h+var_D8], r12
0x18005854e  lea     rcx, [rsp+130h+var_D8]
0x180058553  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180058558  lea     rdx, [rsp+130h+var_D8]; struct _HRESOURCE **
0x18005855d  mov     rcx, rbx; hCluster
0x180058560  call    ?GetCoreClusterNameResource@@YAKPEAU_HCLUSTER@@PEAPEAU_HRESOURCE@@@Z; GetCoreClusterNameResource(_HCLUSTER *,_HRESOURCE * *)
0x180058565  mov     dword ptr [rsp+130h+var_F0], eax
0x180058569  cmp     [rsp+130h+var_D8], r12
0x18005856e  jz      short loc_180058578
0x180058570  mov     dword ptr [rsp+130h+var_F0], 1733h
0x180058578  lea     rcx, [rsp+130h+var_D8]
0x18005857d  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180058582  mov     eax, dword ptr [rsp+130h+var_F0]
0x180058586  test    eax, eax
0x180058588  jz      short loc_180058605
0x18005858a  mov     dword ptr [rsp+130h+var_108], eax
0x18005858e  lea     rax, aGetcorecluster; "GetCoreClusterNameResource: %d"
0x180058595  mov     [rsp+130h+var_110], rax
0x18005859a  mov     r9d, 3CBh
0x1800585a0  lea     r8, aEvictclusterno_3; "EvictClusterNodeEx2"
0x1800585a7  mov     edx, 0Bh
0x1800585ac  lea     ecx, [rdx-9]
0x1800585af  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800585b4  mov     r14d, dword ptr [rsp+130h+var_F0]
0x1800585b9  test    r14d, r14d
0x1800585bc  jg      short loc_1800585C3
0x1800585be  mov     ebx, r14d
0x1800585c1  jmp     short loc_1800585CD
0x1800585c3  movzx   ebx, r14w
0x1800585c7  or      ebx, 80070000h
0x1800585cd  mov     r15d, 1
0x1800585d3  mov     edx, r15d; int
0x1800585d6  mov     rcx, rdi; struct _HCLUSENUM *
0x1800585d9  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x1800585de  nop
0x1800585df  mov     [rbp+57h+var_78], r15b
0x1800585e3  lea     rcx, [rbp+57h+var_A0]
0x1800585e7  call    _lambda_1f4e26b8241f84095da9d8c716bb2bdc___operator__
0x1800585ec  nop
0x1800585ed  lea     rcx, [rbp+57h+var_D0]
0x1800585f1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800585f6  test    rsi, rsi
0x1800585f9  jz      short loc_1800585FD
0x1800585fb  mov     [rsi], ebx
0x1800585fd  mov     eax, r14d
0x180058600  jmp     loc_18005895E
0x180058605  lea     r8, [rsp+130h+var_DC]; int *
0x18005860a  mov     rdx, r15; struct _CNODE *
0x18005860d  mov     rcx, rdi; hEnum
0x180058610  call    ?ClusterEnumContainsNode@@YAKPEAU_HCLUSENUM@@PEAU_CNODE@@PEAH@Z; ClusterEnumContainsNode(_HCLUSENUM *,_CNODE *,int *)
0x180058615  mov     dword ptr [rsp+130h+var_F0], eax
0x180058619  test    eax, eax
0x18005861b  jnz     loc_180058900
0x180058621  mov     rcx, [r15+28h]; wchar_t *
0x180058625  cmp     [rsp+130h+var_DC], r12d
0x18005862a  jnz     short loc_18005868F
0x18005862c  mov     [rsp+130h+var_108], rcx
0x180058631  lea     rax, aNodeNotFoundIn; "Node not found in cluster: %ws"
0x180058638  mov     [rsp+130h+var_110], rax
0x18005863d  mov     r9d, 3D5h
0x180058643  lea     r8, aEvictclusterno_3; "EvictClusterNodeEx2"
0x18005864a  mov     edx, 0Bh
0x18005864f  lea     ecx, [rdx-9]
0x180058652  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058657  mov     edx, r14d; int
0x18005865a  mov     rcx, rdi; struct _HCLUSENUM *
0x18005865d  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x180058662  nop
0x180058663  mov     [rbp+57h+var_78], r14b
0x180058667  lea     rcx, [rbp+57h+var_A0]
0x18005866b  call    _lambda_1f4e26b8241f84095da9d8c716bb2bdc___operator__
0x180058670  nop
0x180058671  lea     rcx, [rbp+57h+var_D0]
0x180058675  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005867a  test    rsi, rsi
0x18005867d  jz      short loc_180058685
0x18005867f  mov     dword ptr [rsi], 80004004h
0x180058685  mov     eax, 13B2h
0x18005868a  jmp     loc_18005895E
0x18005868f  lea     r8, [rbp+57h+var_B8]; unsigned __int64 *
0x180058693  mov     edx, 7FFFFFFFh; unsigned __int64
0x180058698  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18005869d  mov     r14d, eax
0x1800586a0  test    eax, eax
0x1800586a2  js      loc_18005887D
0x1800586a8  mov     r14, [rbp+57h+var_B8]
0x1800586ac  lea     rdx, ds:2[r14*2]; uBytes
0x1800586b4  mov     ecx, 40h ; '@'; uFlags
0x1800586b9  call    cs:__imp_LocalAlloc
0x1800586bf  mov     rbx, rax
0x1800586c2  xor     ecx, ecx; void *
0x1800586c4  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800586c9  test    rbx, rbx
0x1800586cc  jz      loc_180058875
0x1800586d2  lea     rdx, [r14+1]; unsigned __int64
0x1800586d6  mov     r8, [r15+28h]; wchar_t *
0x1800586da  mov     rcx, rbx; wchar_t *
0x1800586dd  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800586e2  mov     r14d, eax
0x1800586e5  test    eax, eax
0x1800586e7  js      loc_180058880
0x1800586ed  mov     eax, 1
0x1800586f2  or      [r15+38h], ax
0x1800586f7  mov     rcx, [r15+20h]; struct _CLUSTER *
0x1800586fb  lea     r12, [r15+30h]
0x1800586ff  call    ?ClusterSupportsReasonString@@YA_NQEBU_CLUSTER@@@Z; ClusterSupportsReasonString(_CLUSTER const * const)
0x180058704  mov     rdx, rcx; struct _HCLUSTER *
0x180058707  test    al, al
0x180058709  jz      short loc_180058753
0x18005870b  mov     r8, r13; wchar_t *
0x18005870e  lea     rcx, [rbp+57h+var_B8]; this
0x180058712  call    ??0ClusterReason@@QEAA@PEAU_HCLUSTER@@PEB_W@Z; ClusterReason::ClusterReason(_HCLUSTER *,wchar_t const *)
0x180058717  lea     rax, aApievictnodeex; "ApiEvictNodeEx"
0x18005871e  mov     [rbp+57h+var_70], rax
0x180058722  mov     [rbp+57h+var_68], r12
0x180058726  mov     rax, [rbp+57h+var_B8]
0x18005872a  mov     [rbp+57h+var_60], rax
0x18005872e  mov     [rbp+57h+var_58], r15
0x180058732  mov     rdx, [r15+20h]
0x180058736  lea     rcx, [rbp+57h+var_70]
0x18005873a  call    ??$ReconnectOnError@VEvictNodeExFunctor@@@@YAKAEAVEvictNodeExFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<EvictNodeExFunctor>(EvictNodeExFunctor &,_CLUSTER *)
0x18005873f  mov     dword ptr [rsp+130h+var_F0], eax
0x180058743  lea     rcx, [rbp+57h+var_B0]
0x180058747  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x18005874c  mov     r15d, dword ptr [rsp+130h+var_F0]
0x180058751  jmp     short loc_180058776
0x180058753  lea     rax, aApievictnode; "ApiEvictNode"
0x18005875a  mov     [rbp+57h+var_B8], rax
0x18005875e  mov     [rbp+57h+var_B0], r12
0x180058762  mov     [rbp+57h+var_A8], r15
0x180058766  lea     rcx, [rbp+57h+var_B8]
0x18005876a  call    ??$ReconnectOnError@VEvictNodeFunctor@@@@YAKAEAVEvictNodeFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<EvictNodeFunctor>(EvictNodeFunctor &,_CLUSTER *)
0x18005876f  mov     r15d, eax
0x180058772  mov     dword ptr [rsp+130h+var_F0], eax
0x180058776  cmp     r15d, 13AFh
0x18005877d  jnz     short loc_1800587AF
0x18005877f  mov     [rsp+130h+var_108], rbx
0x180058784  lea     rax, aNodeWsWasAlrea; "Node %ws was already evicted"
0x18005878b  mov     [rsp+130h+var_110], rax
0x180058790  mov     r9d, 408h
0x180058796  lea     r8, aEvictclusterno_3; "EvictClusterNodeEx2"
0x18005879d  xor     edx, edx
0x18005879f  lea     ecx, [rdx+4]
0x1800587a2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800587a7  xor     r15d, r15d
0x1800587aa  mov     dword ptr [rsp+130h+var_F0], r15d
0x1800587af  test    r15d, r15d
0x1800587b2  jz      short loc_18005880E
0x1800587b4  mov     dword ptr [rsp+130h+var_108], r15d
0x1800587b9  lea     rax, aReconnectonerr; "ReconnectOnError: %d"
0x1800587c0  mov     [rsp+130h+var_110], rax
0x1800587c5  mov     r9d, 40Dh
0x1800587cb  lea     r8, aEvictclusterno_3; "EvictClusterNodeEx2"
0x1800587d2  mov     edx, 0Bh
0x1800587d7  lea     ecx, [rdx-9]
0x1800587da  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800587df  mov     r15d, dword ptr [rsp+130h+var_F0]
0x1800587e4  mov     rcx, rbx; void *
0x1800587e7  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800587ec  mov     ebx, 1
0x1800587f1  mov     edx, ebx; int
0x1800587f3  mov     rcx, rdi; struct _HCLUSENUM *
0x1800587f6  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x1800587fb  nop
0x1800587fc  mov     [rbp+57h+var_78], bl
0x1800587ff  lea     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
