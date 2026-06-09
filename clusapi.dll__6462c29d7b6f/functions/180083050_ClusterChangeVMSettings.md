# ClusterChangeVMSettings

- ea: `0x180083050`
- end: `0x1800835c6`
- name: `ClusterChangeVMSettings`
- size: `1398`
- prototype: `__int64 __fastcall(struct _HRESOURCE *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18001cc2c`
- `0x180029578`
- `0x18002a7a0`
- `0x18004b238`
- `0x18004b424`
- `0x18004bd10`
- `0x18004bed0`
- `0x180052d30`
- `0x180057c9c`
- `0x180058b90`
- `0x18006ccc0`
- `0x18006cf40`
- `0x18006f910`
- `0x180082f68`
- `0x180083050`
- `0x180095144`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834fe`

## string_xrefs

- `0x18008350a`: `OpenNodeById failed with status:%d`
- `0x1800834bd`: `OpenClusterGroup failed with status:%d`
- `0x1800834d6`: `MoveClusterGroup failed with status:%d`
- `0x18008348d`: `MoveClusterGroup succeeded for Group:%ws.`

## pseudocode

```c
__int64 __fastcall ClusterChangeVMSettings(struct _HRESOURCE *a1, _DWORD *a2, unsigned int *a3)
{
  struct _HCLUSTER *ClusterFromResource; // r13
  DWORD LastError; // edi
  struct _HGROUP *v8; // r14
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  unsigned int v13; // ebx
  struct _HNODE *v14; // rbx
  DWORD v15; // eax
  unsigned int v16; // r8d
  wchar_t *v18; // [rsp+28h] [rbp-D8h]
  wchar_t *v19; // [rsp+28h] [rbp-D8h]
  wchar_t *v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21[2]; // [rsp+30h] [rbp-D0h]
  int v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+38h] [rbp-C8h]
  unsigned int *v24; // [rsp+38h] [rbp-C8h]
  bool v25[4]; // [rsp+40h] [rbp-C0h]
  DWORD cchGroupName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchNodeName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch]
  DWORD *p_cchNodeName; // [rsp+68h] [rbp-98h] BYREF
  DWORD *p_cchGroupName; // [rsp+70h] [rbp-90h]
  _DWORD *v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[16]; // [rsp+80h] [rbp-80h] BYREF
  void *v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+98h] [rbp-68h]
  _BYTE v36[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR szGroupName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR szNodeName[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v32 = a2;
  v28 = 0;
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v33);
  if ( a1 && a2 && a3 )
  {
    *a3 = 0;
    ClusterFromResource = GetClusterFromResource(a1);
    if ( ClusterFromResource )
    {
      *(_DWORD *)v25 = a2[1];
      v23 = a2[2];
      v8 = 0;
      v22 = *a2;
      LastError = 0;
      v19 = (wchar_t *)*((_QWORD *)a1 + 6);
      v29 = 4;
      TraceMsg(
        4u,
        0,
        (__int64)L"ClusterChangeVMSettings",
        403,
        L"Resource:%ws Memory:%u MB  CPUReserve:%u VirtualCoreCount:%u",
        v19,
        v22,
        v23,
        *(_DWORD *)v25);
      v9 = *a2;
      std::wstring::wstring(v36, L"Memory");
      cchNodeName = v9;
      p_cchNodeName = &cchNodeName;
      cchGroupName = 65538;
      p_cchGroupName = &cchGroupName;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v33, v36, &p_cchNodeName);
      std::wstring::_Tidy_deallocate(v36);
      v10 = v32[2];
      std::wstring::wstring(v36, L"CPUReserve");
      cchGroupName = v10;
      p_cchNodeName = &cchGroupName;
      cchNodeName = 65538;
      p_cchGroupName = &cchNodeName;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v33, v36, &p_cchNodeName);
      std::wstring::_Tidy_deallocate(v36);
      v11 = v32[4];
      std::wstring::wstring(v36, L"Flags");
      cchGroupName = v11;
      p_cchNodeName = &cchGroupName;
      cchNodeName = 65538;
      p_cchGroupName = &cchNodeName;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v33, v36, &p_cchNodeName);
      std::wstring::_Tidy_deallocate(v36);
      v12 = v32[1];
      std::wstring::wstring(v36, L"VirtualProcessorCount");
      cchGroupName = v12;
      p_cchNodeName = &cchGroupName;
      cchNodeName = 65538;
      p_cchGroupName = &cchNodeName;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v33, v36, &p_cchNodeName);
      std::wstring::_Tidy_deallocate(v36);
      while ( 1 )
      {
        if ( !v29 )
          goto LABEL_23;
        cchGroupName = 0;
        LastError = ClusterpResourceControl(a1, 0, 0x740211Eu, v34, v35 - (_DWORD)v34, &v28, 4u, &cchGroupName, 0, 0);
        if ( LastError != 5956 )
          goto LABEL_23;
        v13 = v28;
        if ( v28 - 1 > 0xFFFFFFFD )
          break;
        memset_0(szNodeName, 0, 0x208u);
        cchNodeName = 260;
        memset_0(szGroupName, 0, 0x208u);
        cchGroupName = 260;
        v14 = OpenClusterNodeById(ClusterFromResource, v13);
        if ( !v14 )
        {
          LastError = GetLastError();
          LODWORD(v18) = LastError;
          TraceMsg(2u, 0, (__int64)L"ClusterChangeVMSettings", 442, L"OpenNodeById failed with status:%d", v18);
          goto LABEL_23;
        }
        if ( !v8 )
        {
          LODWORD(v24) = GetClusterResourceState(a1, szNodeName, &cchNodeName, szGroupName, &cchGroupName);
          TraceMsg(
            4u,
            0,
            (__int64)L"ClusterChangeVMSettings",
            450,
            L"GetClusterResourceState OwnerNode:%ws GroupName:%ws State:%d",
            szNodeName,
            szGroupName,
            v24);
          v8 = OpenClusterGroupImpl(ClusterFromResource, szGroupName, 0x10000000u, 0, 1);
          if ( !v8 )
          {
            LastError = GetLastError();
            LODWORD(v20) = LastError;
            TraceMsg(2u, 0, (__int64)L"ClusterChangeVMSettings", 455, L"OpenClusterGroup failed with status:%d", v20);
LABEL_20:
            CloseClusterNodeCommon(v14, 1);
            goto LABEL_23;
          }
        }
        v21[0] = v28;
        TraceMsg(
          4u,
          0,
          (__int64)L"ClusterChangeVMSettings",
          461,
          L"Moving Group:%ws to Node:%d",
          szGroupName,
          *(_QWORD *)v21);
        cchGroupName = GetClusterGroupState(v8, 0, 0);
        v15 = MoveClusterGroupEx2((int)v8, (int)v14, 0, 0, 0, 0);
        LastError = v15;
        if ( v15 == 997 )
        {
          LastError = WaitForGroupToReachState(v8, (enum CLUSTER_GROUP_STATE)cchGroupName, v16);
          if ( LastError )
            goto LABEL_20;
        }
        else if ( v15 )
        {
          LODWORD(v18) = v15;
          TraceMsg(2u, 0, (__int64)L"ClusterChangeVMSettings", 473, L"MoveClusterGroup failed with status:%d", v18);
          goto LABEL_20;
        }
        --v29;
        CloseClusterNodeCommon(v14, 1);
        TraceMsg(
          4u,
          0,
          (__int64)L"ClusterChangeVMSettings",
          483,
          L"MoveClusterGroup succeeded for Group:%ws.",
          szGroupName);
        *a3 = v28;
      }
      LODWORD(v18) = v28;
      TraceMsg(
        2u,
        0,
        (__int64)L"ClusterChangeVMSettings",
        430,
        L"ClusterResourceControl returned invalid NodeId:%u",
        v18);
LABEL_23:
      if ( v8 )
        CloseClusterGroupCommon(v8, 1);
      CloseCluster(ClusterFromResource);
    }
    else
    {
      LastError = GetLastError();
      TraceMsg(2u, 0, (__int64)L"ClusterChangeVMSettings", 399, L"GetClusterFromResource Failed GLE=%d", LastError);
    }
    v21[0] = *a3;
    LODWORD(v18) = LastError;
    TraceMsg(4u, 0, (__int64)L"ClusterChangeVMSettings", 499, L"Return Status:%u OutNodeID:%d", v18, *(_QWORD *)v21);
    cxl::PropertyList::~PropertyList((cxl::PropertyList *)v33);
    return LastError;
  }
  else
  {
    cxl::PropertyList::~PropertyList((cxl::PropertyList *)v33);
    return 87;
  }
}

```

## disassembly

```asm
0x180083050  mov     [rsp-8+arg_18], rbx
0x180083055  push    rbp
0x180083056  push    rsi
0x180083057  push    rdi
0x180083058  push    r12
0x18008305a  push    r13
0x18008305c  push    r14
0x18008305e  push    r15
0x180083060  lea     rbp, [rsp-400h]
0x180083068  sub     rsp, 500h
0x18008306f  mov     rax, cs:__security_cookie
0x180083076  xor     rax, rsp
0x180083079  mov     [rbp+430h+var_40], rax
0x180083080  mov     r15, rcx
0x180083083  mov     [rsp+530h+var_4B8], rdx
0x180083088  lea     rcx, [rbp+430h+var_4B0]; this
0x18008308c  mov     [rsp+530h+var_4D0], 0
0x180083094  mov     r12, r8
0x180083097  mov     rbx, rdx
0x18008309a  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18008309f  test    r15, r15
0x1800830a2  jz      loc_18008358E
0x1800830a8  test    rbx, rbx
0x1800830ab  jz      loc_18008358E
0x1800830b1  test    r12, r12
0x1800830b4  jz      loc_18008358E
0x1800830ba  mov     rcx, r15; hResource
0x1800830bd  mov     dword ptr [r12], 0
0x1800830c5  call    GetClusterFromResource
0x1800830ca  mov     r13, rax
0x1800830cd  mov     ecx, 4
0x1800830d2  test    rax, rax
0x1800830d5  jnz     short loc_18008310E
0x1800830d7  call    cs:__imp_GetLastError
0x1800830dd  mov     dword ptr [rsp+530h+var_508], eax
0x1800830e1  xor     edx, edx
0x1800830e3  mov     edi, eax
0x1800830e5  lea     rsi, aClusterchangev_0; "ClusterChangeVMSettings"
0x1800830ec  lea     rax, aGetclusterfrom_4; "GetClusterFromResource Failed GLE=%d"
0x1800830f3  mov     r9d, 18Fh
0x1800830f9  mov     r8, rsi
0x1800830fc  mov     [rsp+530h+lpcchGroupName], rax
0x180083101  lea     ecx, [rdx+2]
0x180083104  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180083109  jmp     loc_180083556
0x18008310e  mov     eax, [rbx+4]
0x180083111  lea     rsi, aClusterchangev_0; "ClusterChangeVMSettings"
0x180083118  mov     dword ptr [rsp+530h+var_4F0], eax
0x18008311c  mov     r9d, 193h
0x180083122  mov     eax, [rbx+8]
0x180083125  mov     r8, rsi
0x180083128  mov     dword ptr [rsp+530h+var_4F8], eax
0x18008312c  xor     edx, edx
0x18008312e  mov     eax, [rbx]
0x180083130  xor     r14d, r14d
0x180083133  mov     [rsp+530h+var_500], eax
0x180083137  xor     edi, edi
0x180083139  mov     rax, [r15+30h]
0x18008313d  mov     [rsp+530h+var_508], rax
0x180083142  lea     rax, aResourceWsMemo; "Resource:%ws Memory:%u MB  CPUReserve:%"...
0x180083149  mov     [rsp+530h+lpcchGroupName], rax
0x18008314e  mov     [rsp+530h+var_4CC], ecx
0x180083152  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180083157  mov     ebx, [rbx]
0x180083159  lea     rdx, aMemory; "Memory"
0x180083160  lea     rcx, [rbp+430h+var_488]
0x180083164  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180083169  lea     rax, [rsp+530h+cchNodeName]
0x18008316e  mov     [rsp+530h+cchNodeName], ebx
0x180083172  mov     [rsp+530h+var_4C8], rax
0x180083177  lea     r8, [rsp+530h+var_4C8]
0x18008317c  lea     rax, [rsp+530h+cchGroupName]
0x180083181  mov     [rsp+530h+cchGroupName], 10002h
0x180083189  lea     rdx, [rbp+430h+var_488]
0x18008318d  mov     [rsp+530h+var_4C0], rax
0x180083192  lea     rcx, [rbp+430h+var_4B0]
0x180083196  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x18008319b  lea     rcx, [rbp+430h+var_488]
0x18008319f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800831a4  mov     rbx, [rsp+530h+var_4B8]
0x1800831a9  lea     rdx, aCpureserve; "CPUReserve"
0x1800831b0  lea     rcx, [rbp+430h+var_488]
0x1800831b4  mov     ebx, [rbx+8]
0x1800831b7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800831bc  lea     rax, [rsp+530h+cchGroupName]
0x1800831c1  mov     [rsp+530h+cchGroupName], ebx
0x1800831c5  mov     [rsp+530h+var_4C8], rax
0x1800831ca  lea     r8, [rsp+530h+var_4C8]
0x1800831cf  lea     rax, [rsp+530h+cchNodeName]
0x1800831d4  mov     [rsp+530h+cchNodeName], 10002h
0x1800831dc  lea     rdx, [rbp+430h+var_488]
0x1800831e0  mov     [rsp+530h+var_4C0], rax
0x1800831e5  lea     rcx, [rbp+430h+var_4B0]
0x1800831e9  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x1800831ee  lea     rcx, [rbp+430h+var_488]
0x1800831f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800831f7  mov     rax, [rsp+530h+var_4B8]
0x1800831fc  lea     rdx, aFlags; "Flags"
0x180083203  lea     rcx, [rbp+430h+var_488]
0x180083207  mov     ebx, [rax+10h]
0x18008320a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008320f  lea     rax, [rsp+530h+cchGroupName]
0x180083214  mov     [rsp+530h+cchGroupName], ebx
0x180083218  mov     [rsp+530h+var_4C8], rax
0x18008321d  lea     r8, [rsp+530h+var_4C8]
0x180083222  lea     rax, [rsp+530h+cchNodeName]
0x180083227  mov     [rsp+530h+cchNodeName], 10002h
0x18008322f  lea     rdx, [rbp+430h+var_488]
0x180083233  mov     [rsp+530h+var_4C0], rax
0x180083238  lea     rcx, [rbp+430h+var_4B0]
0x18008323c  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180083241  lea     rcx, [rbp+430h+var_488]
0x180083245  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008324a  mov     rax, [rsp+530h+var_4B8]
0x18008324f  lea     rdx, aVirtualprocess; "VirtualProcessorCount"
0x180083256  lea     rcx, [rbp+430h+var_488]
0x18008325a  mov     ebx, [rax+4]
0x18008325d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180083262  lea     rax, [rsp+530h+cchGroupName]
0x180083267  mov     [rsp+530h+cchGroupName], ebx
0x18008326b  mov     [rsp+530h+var_4C8], rax
0x180083270  lea     r8, [rsp+530h+var_4C8]
0x180083275  lea     rax, [rsp+530h+cchNodeName]
0x18008327a  mov     [rsp+530h+cchNodeName], 10002h
0x180083282  mov     [rsp+530h+var_4C0], rax
0x180083287  lea     rdx, [rbp+430h+var_488]
0x18008328b  lea     rcx, [rbp+430h+var_4B0]
0x18008328f  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180083294  lea     rcx, [rbp+430h+var_488]
0x180083298  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008329d  cmp     [rsp+530h+var_4CC], 0
0x1800832a2  jbe     loc_18008353C
0x1800832a8  mov     r9, [rbp+430h+var_4A0]; void *
0x1800832ac  lea     rcx, [rsp+530h+cchGroupName]
0x1800832b1  mov     eax, [rbp+430h+var_498]
0x1800832b4  xor     edi, edi
0x1800832b6  mov     [rsp+530h+var_4E8], rdi; wchar_t *
0x1800832bb  sub     eax, r9d
0x1800832be  mov     [rsp+530h+var_4F0], dil; bool
0x1800832c3  xor     edx, edx; struct _HNODE *
0x1800832c5  mov     [rsp+530h+var_4F8], rcx; unsigned int *
0x1800832ca  mov     r8d, 740211Eh; unsigned int
0x1800832d0  lea     rcx, [rsp+530h+var_4D0]
0x1800832d5  mov     [rsp+530h+var_500], 4; unsigned int
0x1800832dd  mov     [rsp+530h+var_508], rcx; void *
0x1800832e2  mov     rcx, r15; struct _HRESOURCE *
0x1800832e5  mov     [rsp+530h+cchGroupName], edi
0x1800832e9  mov     dword ptr [rsp+530h+lpcchGroupName], eax; unsigned int
0x1800832ed  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x1800832f2  mov     edi, eax
0x1800832f4  cmp     eax, 1744h
0x1800832f9  jnz     loc_18008353C
0x1800832ff  mov     ebx, [rsp+530h+var_4D0]
0x180083303  lea     eax, [rbx-1]
0x180083306  cmp     eax, 0FFFFFFFDh
0x180083309  ja      loc_180083519
0x18008330f  mov     edi, 208h
0x180083314  lea     rcx, [rbp+430h+szNodeName]; void *
0x18008331b  mov     r8d, edi; Size
0x18008331e  xor     edx, edx; Val
0x180083320  call    memset_0
0x180083325  mov     r8d, edi; Size
0x180083328  mov     [rsp+530h+cchNodeName], 104h
0x180083330  xor     edx, edx; Val
0x180083332  lea     rcx, [rbp+430h+szGroupName]; void *
0x180083336  call    memset_0
0x18008333b  mov     edx, ebx
0x18008333d  mov     [rsp+530h+cchGroupName], 104h
0x180083345  mov     rcx, r13; struct _HCLUSTER *
0x180083348  call    OpenClusterNodeById
0x18008334d  mov     rbx, rax
0x180083350  test    rax, rax
0x180083353  jz      loc_1800834FE
0x180083359  test    r14, r14
0x18008335c  jnz     loc_1800833E3
0x180083362  lea     rax, [rsp+530h+cchGroupName]
0x180083367  mov     rcx, r15; hResource
0x18008336a  lea     r9, [rbp+430h+szGroupName]; lpszGroupName
0x18008336e  mov     [rsp+530h+lpcchGroupName], rax; lpcchGroupName
0x180083373  lea     r8, [rsp+530h+cchNodeName]; lpcchNodeName
0x180083378  lea     rdx, [rbp+430h+szNodeName]; lpszNodeName
0x18008337f  call    GetClusterResourceState
0x180083384  mov     dword ptr [rsp+530h+var_4F8], eax
0x180083388  lea     r9d, [rdi-46h]
0x18008338c  lea     rax, [rbp+430h+szGroupName]
0x180083390  xor     edx, edx
0x180083392  mov     qword ptr [rsp+530h+var_500], rax
0x180083397  mov     r8, rsi
0x18008339a  lea     rax, [rbp+430h+szNodeName]
0x1800833a1  mov     [rsp+530h+var_508], rax
0x1800833a6  lea     rax, aGetclusterreso_4; "GetClusterResourceState OwnerNode:%ws G"...
0x1800833ad  lea     ecx, [rdx+4]
0x1800833b0  mov     [rsp+530h+lpcchGroupName], rax
0x1800833b5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800833ba  xor     r9d, r9d; unsigned int *
0x1800833bd  mov     dword ptr [rsp+530h+lpcchGroupName], 1; int
0x1800833c5  mov     r8d, 10000000h; unsigned int
0x1800833cb  lea     rdx, [rbp+430h+szGroupName]; wchar_t *
0x1800833cf  mov     rcx, r13; struct _HCLUSTER *
0x1800833d2  call    ?OpenClusterGroupImpl@@YAPEAU_HGROUP@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterGroupImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x1800833d7  mov     r14, rax
0x1800833da  test    rax, rax
0x1800833dd  jz      loc_1800834B1
0x1800833e3  mov     ecx, [rsp+530h+var_4D0]
0x1800833e7  lea     rax, [rbp+430h+szGroupName]
0x1800833eb  mov     [rsp+530h+var_500], ecx
0x1800833ef  xor     edx, edx
0x1800833f1  mov     [rsp+530h+var_508], rax
0x1800833f6  mov     r9d, 1CDh
0x1800833fc  lea     rax, aMovingGroupWsT; "Moving Group:%ws to Node:%d"
0x180083403  mov     r8, rsi
0x180083406  mov     [rsp+530h+lpcchGroupName], rax
0x18008340b  lea     ecx, [rdx+4]
0x18008340e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180083413  xor     r8d, r8d; lpcchNodeName
0x180083416  xor     edx, edx; lpszNodeName
0x180083418  mov     rcx, r14; hGroup
0x18008341b  call    GetClusterGroupState
0x180083420  xor     r9d, r9d; int
0x180083423  mov     [rsp+530h+var_508], 0; wchar_t *
0x18008342c  xor     r8d, r8d; int
0x18008342f  mov     [rsp+530h+cchGroupName], eax
0x180083433  mov     rdx, rbx; int
0x180083436  mov     dword ptr [rsp+530h+lpcchGroupName], 0; int
0x18008343e  mov     rcx, r14; int
0x180083441  call    MoveClusterGroupEx2
0x180083446  mov     edi, eax
0x180083448  cmp     eax, 3E5h
0x18008344d  jnz     short loc_180083467
0x18008344f  mov     edx, [rsp+530h+cchGroupName]; enum CLUSTER_GROUP_STATE
0x180083453  mov     rcx, r14; hGroup
0x180083456  call    ?WaitForGroupToReachState@@YAKPEAU_HGROUP@@W4CLUSTER_GROUP_STATE@@K@Z; WaitForGroupToReachState(_HGROUP *,CLUSTER_GROUP_STATE,ulong)
0x18008345b  mov     edi, eax
0x18008345d  test    eax, eax
0x18008345f  jnz     loc_1800834EF
0x180083465  jmp     short loc_18008346B
0x180083467  test    eax, eax
0x180083469  jnz     short loc_1800834CC
0x18008346b  dec     [rsp+530h+var_4CC]
0x18008346f  mov     edx, 1; int
0x180083474  mov     rcx, rbx; hMem
0x180083477  call    ?CloseClusterNodeCommon@@YAHPEAU_HNODE@@H@Z; CloseClusterNodeCommon(_HNODE *,int)
0x18008347c  xor     edx, edx
0x18008347e  lea     rax, [rbp+430h+szGroupName]
0x180083482  mov     [rsp+530h+var_508], rax
0x180083487  mov     r9d, 1E3h
0x18008348d  lea     rax, aMoveclustergro_2; "MoveClusterGroup succeeded for Group:%w"...
0x180083494  mov     r8, rsi
0x180083497  mov     [rsp+530h+lpcchGroupName], rax
0x18008349c  lea     ecx, [rdx+4]
0x18008349f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800834a4  mov     eax, [rsp+530h+var_4D0]
0x1800834a8  mov     [r12], eax
0x1800834ac  jmp     loc_18008329D
0x1800834b1  call    cs:__imp_GetLastError
0x1800834b7  mov     edi, eax
0x1800834b9  mov     dword ptr [rsp+530h+var_508], eax
0x1800834bd  lea     rax, aOpenclustergro_2; "OpenClusterGroup failed with status:%d"
0x1800834c4  mov     r9d, 1C7h
0x1800834ca  jmp     short loc_1800834DD
0x1800834cc  mov     dword ptr [rsp+530h+var_508], eax
0x1800834d0  mov     r9d, 1D9h
0x1800834d6  lea     rax, aMoveclustergro_3; "MoveClusterGroup failed with status:%d"
0x1800834dd  xor     edx, edx
0x1800834df  mov     [rsp+530h+lpcchGroupName], rax
0x1800834e4  mov     r8, rsi
0x1800834e7  lea     ecx, [rdx+2]
0x1800834ea  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800834ef  mov     edx, 1; int
0x1800834f4  mov     rcx, rbx; hMem
0x1800834f7  call    ?CloseClusterNodeCommon@@YAHPEAU_HNODE@@H@Z; CloseClusterNodeCommon(_HNODE *,int)
0x1800834fc  jmp     short loc_18008353C
0x1800834fe  call    cs:__imp_GetLastError
0x180083504  mov     edi, eax
0x180083506  mov     dword ptr [rsp+530h+var_508], eax
0x18008350a  lea     rax, aOpennodebyidFa; "OpenNodeById failed with status:%d"
0x180083511  mov     r9d, 1BAh
0x180083517  jmp     short loc_18008352A
0x180083519  mov     dword ptr [rsp+530h+var_508], ebx
0x18008351d  lea     rax, aClusterresourc_20; "ClusterResourceControl returned invalid"...
0x180083524  mov     r9d, 1AEh
0x18008352a  xor     edx, edx
0x18008352c  mov     [rsp+530h+lpcchGroupName], rax
0x180083531  mov     r8, rsi
0x180083534  lea     ecx, [rdx+2]
0x180083537  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008353c  test    r14, r14
0x18008353f  jz      short loc_18008354E
0x180083541  mov     edx, 1; int
0x180083546  mov     rcx, r14; hMem
0x180083549  call    ?CloseClusterGroupCommon@@YAHPEAU_HGROUP@@H@Z; CloseClusterGroupCommon(_HGROUP *,int)
0x18008354e  mov     rcx, r13; hCluster
0x180083551  call    CloseCluster
0x180083556  mov     eax, [r12]
0x18008355a  xor     edx, edx
0x18008355c  mov     [rsp+530h+var_500], eax
0x180083560  mov     r9d, 1F3h
0x180083566  lea     rax, aReturnStatusUO; "Return Status:%u OutNodeID:%d"
0x18008356d  mov     dword ptr [rsp+530h+var_508], edi
0x180083571  mov     r8, rsi
  ... truncated ...
```
