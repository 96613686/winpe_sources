# ClusterCreateVMReservationExImp(_HCLUSTER *,_CLUS_VM_INFO_EX *,ulong,wchar_t const *,wchar_t const *,std::optional<ulong>,std::optional<ulong>,ulong *)

- ea: `0x18008263c`
- end: `0x180082f62`
- name: `?ClusterCreateVMReservationExImp@@YAKPEAU_HCLUSTER@@PEAU_CLUS_VM_INFO_EX@@KPEB_W2V?$optional@K@std@@3PEAK@Z`
- size: `2342`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800825a8`
- `0x180083640`
- `0x180083720`

## callees

- `0x180002f50`
- `0x180014638`
- `0x18001cc2c`
- `0x180029578`
- `0x1800538c0`
- `0x18006f910`
- `0x18008263c`
- `0x180082ffc`
- `0x18008652c`
- `0x180087120`
- `0x180094ce8`
- `0x180095144`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082701`

## string_xrefs

- `0x180082692`: `ClusterCreateVMReservationExImp: Invalid Cluster handle`
- `0x1800826a4`: `ClusterCreateVMReservationExImp`
- `0x1800826f0`: `ClusterCreateVMReservationExImp`
- `0x18008278b`: `ClusterCreateVMReservationExImp`
- `0x180082ebd`: `ClusterCreateVMReservationExImp`
- `0x180082f04`: `ClusterCreateVMReservationExImp`
- `0x180082f29`: `ClusterCreateVMReservationExImp`
- `0x1800826e0`: `ClusterCreateVMReservationExImp: Invalid availability set name`
- `0x1800827c9`: `ClusterCreateVMReservationExImp: Invalid parameter. If either fault domain or update domain are defined both must be defined. Fault domain defined: %d, Update domain defined: %d`
- `0x180082779`: `ClusterCreateVMReservationExImp: Invalid parameter. Fault domain or update domain value is too high. Fault domain: %d, Update domain: %d`
- `0x180082f17`: `ClusterCreateVMReservationExImp: Invalid parameter. An availablilty set must be specified to use fault domain and update domains.`
- `0x180082ef2`: `ClusterCreateVMReservationExImp: Invalid parameter. Memory: %d, VPCount: %d, reservationId: '%ws', timeSpan: %d`
- `0x18008294d`: `TempDiskSizeInMB`
- `0x180082c3c`: `UpdateDomain`
- `0x180082eab`: `ClusterCreateVMReservationExImp: Cluster control failed with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
DWORD __fastcall ClusterCreateVMReservationExImp(
        struct _HCLUSTER *a1,
        int *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  _DWORD *v12; // r13
  void *v14; // rbx
  unsigned __int8 v15; // al
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28; // eax
  int v29; // ebx
  unsigned int Hr; // eax
  int v31; // [rsp+28h] [rbp-120h]
  __int64 v32; // [rsp+28h] [rbp-120h]
  int v33; // [rsp+30h] [rbp-118h]
  int v34; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-F0h] BYREF
  __int64 *v36; // [rsp+60h] [rbp-E8h] BYREF
  __int64 *v37; // [rsp+68h] [rbp-E0h]
  __int64 v38; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v39[16]; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+88h] [rbp-C0h]
  int v41; // [rsp+90h] [rbp-B8h]
  cxl::Exception *v42; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v43[32]; // [rsp+A8h] [rbp-A0h] BYREF
  _BYTE v44[32]; // [rsp+C8h] [rbp-80h] BYREF
  ATL::CAtlException *v45; // [rsp+E8h] [rbp-60h] BYREF
  std::system_error *v46; // [rsp+F0h] [rbp-58h] BYREF
  std::bad_alloc *v47; // [rsp+F8h] [rbp-50h] BYREF
  std::exception *v48; // [rsp+100h] [rbp-48h] BYREF

  v12 = a8;
  if ( !a1 )
    return 87;
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    TraceMsg(2, 0, L"ClusterCreateVMReservationExImp", 30, L"ClusterCreateVMReservationExImp: Invalid Cluster handle");
    return 6;
  }
  if ( a5 )
  {
    v14 = (void *)OpenClusterGroupSet(a1, a5);
    v35 = (__int64)v14;
    if ( !v14 )
    {
      TraceMsg(
        2,
        0,
        L"ClusterCreateVMReservationExImp",
        39,
        L"ClusterCreateVMReservationExImp: Invalid availability set name");
      return GetLastError();
    }
    if ( BYTE4(a6) )
    {
      if ( BYTE4(a7) )
      {
        if ( *(_DWORD *)std::optional<unsigned long>::value(&a6) == -1
          || *(_DWORD *)std::optional<unsigned long>::value(&a7) == -1 )
        {
          v33 = *(_DWORD *)std::optional<unsigned long>::value(&a7);
          v31 = *(_DWORD *)std::optional<unsigned long>::value(&a6);
          TraceMsg(
            2,
            0,
            L"ClusterCreateVMReservationExImp",
            54,
            L"ClusterCreateVMReservationExImp: Invalid parameter. Fault domain or update domain value is too high. Fault d"
             "omain: %d, Update domain: %d",
            v31,
            v33);
LABEL_12:
          CloseClusterGroupSetCommon(v14, 1);
          return 87;
        }
        goto LABEL_16;
      }
      v15 = 0;
    }
    else
    {
      v15 = BYTE4(a7);
      if ( !BYTE4(a7) )
      {
LABEL_16:
        CloseClusterGroupSetCommon(v14, 1);
        goto LABEL_19;
      }
    }
    TraceMsg(
      2,
      0,
      L"ClusterCreateVMReservationExImp",
      47,
      L"ClusterCreateVMReservationExImp: Invalid parameter. If either fault domain or update domain are defined both must "
       "be defined. Fault domain defined: %d, Update domain defined: %d",
      BYTE4(a6),
      v15);
    goto LABEL_12;
  }
  if ( BYTE4(a6) || BYTE4(a7) )
  {
    TraceMsg(
      2,
      0,
      L"ClusterCreateVMReservationExImp",
      60,
      L"ClusterCreateVMReservationExImp: Invalid parameter. An availablilty set must be specified to use fault domain and update domains.");
    return 87;
  }
LABEL_19:
  if ( !*a2 || !a2[1] || !a4 || !a3 )
  {
    TraceMsg(
      2,
      0,
      L"ClusterCreateVMReservationExImp",
      69,
      L"ClusterCreateVMReservationExImp: Invalid parameter. Memory: %d, VPCount: %d, reservationId: '%ws', timeSpan: %d",
      *a2,
      a2[1],
      a4,
      a3);
    return 87;
  }
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v39);
  try
  {
    v16 = *a2;
    std::wstring::wstring(v44, L"Memory");
    v34 = v16;
    LODWORD(v35) = 65538;
    v36 = (__int64 *)&v34;
    v37 = &v35;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v44, &v36);
    std::wstring::_Tidy_deallocate(v44);
    v17 = a2[1];
    std::wstring::wstring(v44, L"VirtualProcessorCount");
    LODWORD(v35) = v17;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v44, &v36);
    std::wstring::_Tidy_deallocate(v44);
    v18 = a2[2];
    std::wstring::wstring(v44, L"CPUReserve");
    LODWORD(v35) = v18;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v44, &v36);
    std::wstring::_Tidy_deallocate(v44);
    v19 = a2[5];
    std::wstring::wstring(v44, L"TempDiskSizeInMB");
    LODWORD(v35) = v19;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v44, &v36);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::wstring(v43, a4);
    std::wstring::wstring(v44, L"VmReservationId");
    LODWORD(v35) = 65539;
    v36 = (__int64 *)v43;
    v37 = &v35;
    cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v39, v44, &v36);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v43);
    v20 = a2[4];
    std::wstring::wstring(v43, L"Flags");
    LODWORD(v35) = v20;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::wstring(v43, L"TimeSpan");
    LODWORD(v35) = a3;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
    std::wstring::_Tidy_deallocate(v43);
    v21 = a2[3];
    std::wstring::wstring(v43, L"Version");
    LODWORD(v35) = v21;
    v34 = 65538;
    v36 = &v35;
    v37 = (__int64 *)&v34;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
    std::wstring::_Tidy_deallocate(v43);
    if ( a5 )
    {
      std::wstring::wstring(v44, a5);
      std::wstring::wstring(v43, L"AvailabilitySetName");
      LODWORD(v35) = 65539;
      v36 = (__int64 *)v44;
      v37 = &v35;
      cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
      std::wstring::_Tidy_deallocate(v44);
    }
    if ( BYTE4(a6) )
    {
      v22 = *(_DWORD *)std::optional<unsigned long>::value(&a6);
      std::wstring::wstring(v43, L"FaultDomain");
      LODWORD(v35) = v22;
      v34 = 65538;
      v36 = &v35;
      v37 = (__int64 *)&v34;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
    }
    if ( BYTE4(a7) )
    {
      v23 = *(_DWORD *)std::optional<unsigned long>::value(&a7);
      std::wstring::wstring(v43, L"UpdateDomain");
      LODWORD(v35) = v23;
      v34 = 65538;
      v36 = &v35;
      v37 = (__int64 *)&v34;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
    }
    v24 = a2[6];
    if ( v24 )
    {
      std::wstring::wstring(v43, L"VirtualFunctionCount");
      LODWORD(v35) = v24;
      v34 = 65538;
      v36 = &v35;
      v37 = (__int64 *)&v34;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
    }
    v25 = a2[7];
    if ( v25 )
    {
      std::wstring::wstring(v43, L"QueuePairCount");
      LODWORD(v35) = v25;
      v34 = 65538;
      v36 = &v35;
      v37 = (__int64 *)&v34;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
    }
    v26 = *((_QWORD *)a2 + 5);
    if ( v26 )
    {
      std::wstring::wstring(v44, v26);
      std::wstring::wstring(v43, L"DdaInfo");
      LODWORD(v35) = 65539;
      v36 = (__int64 *)v44;
      v37 = &v35;
      cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
      std::wstring::_Tidy_deallocate(v44);
    }
    v27 = *((_QWORD *)a2 + 6);
    if ( v27 )
    {
      std::wstring::wstring(v44, v27);
      std::wstring::wstring(v43, L"GpupInfo");
      LODWORD(v35) = 65539;
      v36 = (__int64 *)v44;
      v37 = &v35;
      cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v39, v43, &v36);
      std::wstring::_Tidy_deallocate(v43);
      std::wstring::_Tidy_deallocate(v44);
    }
    LODWORD(v38) = 0;
    v28 = ClusterControlEx(a1, v41 - (int)v40, (__int64)&v38, 4, (__int64)&v35, 0);
  }
  catch ( cxl::Exception *v42 )
  {
    if ( *((_DWORD *)v42 + 23) == 2 )
      Hr = cxl::ErrorCode::GetHr((cxl::Exception *)((char *)v42 + 88));
    else
      Hr = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v42 + 88));
    if ( Hr )
      cxl::TraceManager::Instance();
    cxl::ExceptionManager::ClearCurrentException();
  }
  catch ( ATL::CAtlException *v45 )
  {
    cxl::TraceManager::Instance();
  }
  catch ( std::system_error *v46 )
  {
    cxl::TraceManager::Instance();
  }
  catch ( std::bad_alloc *v47 )
  {
    cxl::TraceManager::Instance();
  }
  catch ( std::exception *v48 )
  {
    cxl::TraceManager::Instance();
  }
  v29 = v28;
  if ( v28 )
  {
    LODWORD(v32) = v28;
    TraceMsg(
      2,
      0,
      L"ClusterCreateVMReservationExImp",
      120,
      L"ClusterCreateVMReservationExImp: Cluster control failed with error %d",
      v32);
  }
  else
  {
    *v12 = v38;
  }
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v39);
  return v29;
}

```

## disassembly

```asm
0x18008263c  push    rbx
0x18008263e  push    rsi
0x18008263f  push    rdi
0x180082640  push    r12
0x180082642  push    r13
0x180082644  push    r14
0x180082646  push    r15
0x180082648  sub     rsp, 110h
0x18008264f  mov     rax, cs:__security_cookie
0x180082656  xor     rax, rsp
0x180082659  mov     [rsp+148h+var_40], rax
0x180082661  mov     rsi, r9
0x180082664  mov     r15d, r8d
0x180082667  mov     rdi, rdx
0x18008266a  mov     r12, rcx
0x18008266d  mov     r14, [rsp+148h+arg_20]
0x180082675  mov     r13, [rsp+148h+arg_38]
0x18008267d  test    rcx, rcx
0x180082680  jz      loc_180082F3A
0x180082686  mov     rdx, rcx
0x180082689  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18008268e  test    al, al
0x180082690  jnz     short loc_1800826BF
0x180082692  lea     rax, aClustercreatev_9; "ClusterCreateVMReservationExImp: Invali"...
0x180082699  mov     qword ptr [rsp+148h+var_128], rax
0x18008269e  mov     r9d, 1Eh
0x1800826a4  lea     r8, aClustercreatev_10; "ClusterCreateVMReservationExImp"
0x1800826ab  xor     edx, edx
0x1800826ad  lea     ecx, [rdx+2]
0x1800826b0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800826b5  mov     eax, 6
0x1800826ba  jmp     loc_180082F3F
0x1800826bf  test    r14, r14
0x1800826c2  jz      loc_1800827E7
0x1800826c8  mov     rdx, r14
0x1800826cb  mov     rcx, r12
0x1800826ce  call    OpenClusterGroupSet
0x1800826d3  mov     rbx, rax
0x1800826d6  mov     [rsp+148h+var_F0], rax
0x1800826db  test    rax, rax
0x1800826de  jnz     short loc_18008270D
0x1800826e0  lea     rax, aClustercreatev_3; "ClusterCreateVMReservationExImp: Invali"...
0x1800826e7  mov     qword ptr [rsp+148h+var_128], rax
0x1800826ec  lea     r9d, [rbx+27h]
0x1800826f0  lea     r8, aClustercreatev_10; "ClusterCreateVMReservationExImp"
0x1800826f7  xor     edx, edx
0x1800826f9  lea     ecx, [rbx+2]
0x1800826fc  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180082701  call    cs:__imp_GetLastError
0x180082707  nop
0x180082708  jmp     loc_180082F3F
0x18008270d  movzx   ecx, [rsp+148h+arg_2C]
0x180082715  test    cl, cl
0x180082717  jz      loc_1800827B3
0x18008271d  cmp     [rsp+148h+arg_34], 0
0x180082725  jz      loc_1800827AF
0x18008272b  lea     rcx, [rsp+148h+arg_28]
0x180082733  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x180082738  cmp     dword ptr [rax], 0FFFFFFFFh
0x18008273b  jz      short loc_180082753
0x18008273d  lea     rcx, [rsp+148h+arg_30]
0x180082745  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x18008274a  cmp     dword ptr [rax], 0FFFFFFFFh
0x18008274d  jnz     loc_1800827D8
0x180082753  lea     rcx, [rsp+148h+arg_30]
0x18008275b  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x180082760  mov     edi, [rax]
0x180082762  lea     rcx, [rsp+148h+arg_28]
0x18008276a  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x18008276f  mov     [rsp+148h+var_118], edi
0x180082773  mov     eax, [rax]
0x180082775  mov     dword ptr [rsp+148h+var_120], eax
0x180082779  lea     rax, aClustercreatev_5; "ClusterCreateVMReservationExImp: Invali"...
0x180082780  mov     r9d, 36h ; '6'
0x180082786  mov     qword ptr [rsp+148h+var_128], rax
0x18008278b  lea     r8, aClustercreatev_10; "ClusterCreateVMReservationExImp"
0x180082792  xor     edx, edx
0x180082794  lea     ecx, [rdx+2]
0x180082797  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008279c  nop
0x18008279d  mov     edx, 1; int
0x1800827a2  mov     rcx, rbx; hMem
0x1800827a5  call    ?CloseClusterGroupSetCommon@@YAHPEAU_HGROUPSET@@H@Z; CloseClusterGroupSetCommon(_HGROUPSET *,int)
0x1800827aa  jmp     loc_180082F3A
0x1800827af  xor     al, al
0x1800827b1  jmp     short loc_1800827BE
0x1800827b3  mov     al, [rsp+148h+arg_34]
0x1800827ba  test    al, al
0x1800827bc  jz      short loc_1800827D8
0x1800827be  movzx   eax, al
0x1800827c1  mov     [rsp+148h+var_118], eax
0x1800827c5  mov     dword ptr [rsp+148h+var_120], ecx
0x1800827c9  lea     rax, aClustercreatev_6; "ClusterCreateVMReservationExImp: Invali"...
0x1800827d0  mov     r9d, 2Fh ; '/'
0x1800827d6  jmp     short loc_180082786
0x1800827d8  mov     edx, 1; int
0x1800827dd  mov     rcx, rbx; hMem
0x1800827e0  call    ?CloseClusterGroupSetCommon@@YAHPEAU_HGROUPSET@@H@Z; CloseClusterGroupSetCommon(_HGROUPSET *,int)
0x1800827e5  jmp     short loc_180082803
0x1800827e7  cmp     [rsp+148h+arg_2C], 0
0x1800827ef  jnz     loc_180082F17
0x1800827f5  cmp     [rsp+148h+arg_34], 0
0x1800827fd  jnz     loc_180082F17
0x180082803  mov     ecx, [rdi]
0x180082805  test    ecx, ecx
0x180082807  jz      loc_180082EDD
0x18008280d  cmp     dword ptr [rdi+4], 0
0x180082811  jz      loc_180082EDD
0x180082817  test    rsi, rsi
0x18008281a  jz      loc_180082EDD
0x180082820  test    r15d, r15d
0x180082823  jz      loc_180082EDD
0x180082829  lea     rcx, [rsp+148h+var_D0]; this
0x18008282e  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x180082833  nop
0x180082834  mov     ebx, [rdi]
0x180082836  lea     rdx, aMemory; "Memory"
0x18008283d  lea     rcx, [rsp+148h+var_80]
0x180082845  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008284a  nop
0x18008284b  mov     [rsp+148h+var_F8], ebx
0x18008284f  mov     dword ptr [rsp+148h+var_F0], 10002h
0x180082857  lea     rax, [rsp+148h+var_F8]
0x18008285c  mov     [rsp+148h+var_E8], rax
0x180082861  lea     rax, [rsp+148h+var_F0]
0x180082866  mov     [rsp+148h+var_E0], rax
0x18008286b  lea     r8, [rsp+148h+var_E8]
0x180082870  lea     rdx, [rsp+148h+var_80]
0x180082878  lea     rcx, [rsp+148h+var_D0]
0x18008287d  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180082882  nop
0x180082883  lea     rcx, [rsp+148h+var_80]
0x18008288b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082890  mov     ebx, [rdi+4]
0x180082893  lea     rdx, aVirtualprocess; "VirtualProcessorCount"
0x18008289a  lea     rcx, [rsp+148h+var_80]
0x1800828a2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800828a7  nop
0x1800828a8  mov     dword ptr [rsp+148h+var_F0], ebx
0x1800828ac  mov     [rsp+148h+var_F8], 10002h
0x1800828b4  lea     rax, [rsp+148h+var_F0]
0x1800828b9  mov     [rsp+148h+var_E8], rax
0x1800828be  lea     rax, [rsp+148h+var_F8]
0x1800828c3  mov     [rsp+148h+var_E0], rax
0x1800828c8  lea     r8, [rsp+148h+var_E8]
0x1800828cd  lea     rdx, [rsp+148h+var_80]
0x1800828d5  lea     rcx, [rsp+148h+var_D0]
0x1800828da  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x1800828df  nop
0x1800828e0  lea     rcx, [rsp+148h+var_80]
0x1800828e8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800828ed  mov     ebx, [rdi+8]
0x1800828f0  lea     rdx, aCpureserve; "CPUReserve"
0x1800828f7  lea     rcx, [rsp+148h+var_80]
0x1800828ff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082904  nop
0x180082905  mov     dword ptr [rsp+148h+var_F0], ebx
0x180082909  mov     [rsp+148h+var_F8], 10002h
0x180082911  lea     rax, [rsp+148h+var_F0]
0x180082916  mov     [rsp+148h+var_E8], rax
0x18008291b  lea     rax, [rsp+148h+var_F8]
0x180082920  mov     [rsp+148h+var_E0], rax
0x180082925  lea     r8, [rsp+148h+var_E8]
0x18008292a  lea     rdx, [rsp+148h+var_80]
0x180082932  lea     rcx, [rsp+148h+var_D0]
0x180082937  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x18008293c  nop
0x18008293d  lea     rcx, [rsp+148h+var_80]
0x180082945  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008294a  mov     ebx, [rdi+14h]
0x18008294d  lea     rdx, aTempdisksizein; "TempDiskSizeInMB"
0x180082954  lea     rcx, [rsp+148h+var_80]
0x18008295c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082961  nop
0x180082962  mov     dword ptr [rsp+148h+var_F0], ebx
0x180082966  mov     [rsp+148h+var_F8], 10002h
0x18008296e  lea     rax, [rsp+148h+var_F0]
0x180082973  mov     [rsp+148h+var_E8], rax
0x180082978  lea     rax, [rsp+148h+var_F8]
0x18008297d  mov     [rsp+148h+var_E0], rax
0x180082982  lea     r8, [rsp+148h+var_E8]
0x180082987  lea     rdx, [rsp+148h+var_80]
0x18008298f  lea     rcx, [rsp+148h+var_D0]
0x180082994  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180082999  nop
0x18008299a  lea     rcx, [rsp+148h+var_80]
0x1800829a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800829a7  mov     rdx, rsi
0x1800829aa  lea     rcx, [rsp+148h+var_A0]
0x1800829b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800829b7  nop
0x1800829b8  lea     rdx, aVmreservationi; "VmReservationId"
0x1800829bf  lea     rcx, [rsp+148h+var_80]
0x1800829c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800829cc  nop
0x1800829cd  mov     dword ptr [rsp+148h+var_F0], 10003h
0x1800829d5  lea     rax, [rsp+148h+var_A0]
0x1800829dd  mov     [rsp+148h+var_E8], rax
0x1800829e2  lea     rax, [rsp+148h+var_F0]
0x1800829e7  mov     [rsp+148h+var_E0], rax
0x1800829ec  lea     r8, [rsp+148h+var_E8]
0x1800829f1  lea     rdx, [rsp+148h+var_80]
0x1800829f9  lea     rcx, [rsp+148h+var_D0]
0x1800829fe  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x180082a03  nop
0x180082a04  lea     rcx, [rsp+148h+var_80]
0x180082a0c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082a11  nop
0x180082a12  lea     rcx, [rsp+148h+var_A0]
0x180082a1a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082a1f  mov     ebx, [rdi+10h]
0x180082a22  lea     rdx, aFlags; "Flags"
0x180082a29  lea     rcx, [rsp+148h+var_A0]
0x180082a31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082a36  nop
0x180082a37  mov     dword ptr [rsp+148h+var_F0], ebx
0x180082a3b  mov     [rsp+148h+var_F8], 10002h
0x180082a43  lea     rax, [rsp+148h+var_F0]
0x180082a48  mov     [rsp+148h+var_E8], rax
0x180082a4d  lea     rax, [rsp+148h+var_F8]
0x180082a52  mov     [rsp+148h+var_E0], rax
0x180082a57  lea     r8, [rsp+148h+var_E8]
0x180082a5c  lea     rdx, [rsp+148h+var_A0]
0x180082a64  lea     rcx, [rsp+148h+var_D0]
0x180082a69  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180082a6e  nop
0x180082a6f  lea     rcx, [rsp+148h+var_A0]
0x180082a77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082a7c  lea     rdx, aTimespan; "TimeSpan"
0x180082a83  lea     rcx, [rsp+148h+var_A0]
0x180082a8b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082a90  nop
0x180082a91  mov     dword ptr [rsp+148h+var_F0], r15d
0x180082a96  mov     r15d, 10002h
0x180082a9c  mov     [rsp+148h+var_F8], r15d
0x180082aa1  lea     rax, [rsp+148h+var_F0]
0x180082aa6  mov     [rsp+148h+var_E8], rax
0x180082aab  lea     rax, [rsp+148h+var_F8]
0x180082ab0  mov     [rsp+148h+var_E0], rax
0x180082ab5  lea     r8, [rsp+148h+var_E8]
0x180082aba  lea     rdx, [rsp+148h+var_A0]
0x180082ac2  lea     rcx, [rsp+148h+var_D0]
0x180082ac7  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180082acc  nop
0x180082acd  lea     rcx, [rsp+148h+var_A0]
0x180082ad5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082ada  mov     ebx, [rdi+0Ch]
0x180082add  lea     rdx, aVersion_0; "Version"
0x180082ae4  lea     rcx, [rsp+148h+var_A0]
0x180082aec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082af1  nop
0x180082af2  mov     dword ptr [rsp+148h+var_F0], ebx
0x180082af6  mov     [rsp+148h+var_F8], r15d
0x180082afb  lea     rax, [rsp+148h+var_F0]
0x180082b00  mov     [rsp+148h+var_E8], rax
0x180082b05  lea     rax, [rsp+148h+var_F8]
0x180082b0a  mov     [rsp+148h+var_E0], rax
0x180082b0f  lea     r8, [rsp+148h+var_E8]
0x180082b14  lea     rdx, [rsp+148h+var_A0]
0x180082b1c  lea     rcx, [rsp+148h+var_D0]
0x180082b21  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180082b26  nop
0x180082b27  lea     rcx, [rsp+148h+var_A0]
0x180082b2f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082b34  xor     esi, esi
0x180082b36  test    r14, r14
0x180082b39  jz      short loc_180082BB3
0x180082b3b  mov     rdx, r14
0x180082b3e  lea     rcx, [rsp+148h+var_80]
0x180082b46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082b4b  nop
0x180082b4c  lea     rdx, aAvailabilityse_0; "AvailabilitySetName"
0x180082b53  lea     rcx, [rsp+148h+var_A0]
0x180082b5b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082b60  nop
0x180082b61  mov     dword ptr [rsp+148h+var_F0], 10003h
0x180082b69  lea     rax, [rsp+148h+var_80]
0x180082b71  mov     [rsp+148h+var_E8], rax
0x180082b76  lea     rax, [rsp+148h+var_F0]
0x180082b7b  mov     [rsp+148h+var_E0], rax
0x180082b80  lea     r8, [rsp+148h+var_E8]
0x180082b85  lea     rdx, [rsp+148h+var_A0]
0x180082b8d  lea     rcx, [rsp+148h+var_D0]
0x180082b92  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x180082b97  nop
0x180082b98  lea     rcx, [rsp+148h+var_A0]
0x180082ba0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082ba5  nop
0x180082ba6  lea     rcx, [rsp+148h+var_80]
0x180082bae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082bb3  cmp     [rsp+148h+arg_2C], sil
0x180082bbb  jz      short loc_180082C23
0x180082bbd  lea     rcx, [rsp+148h+arg_28]
0x180082bc5  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x180082bca  mov     ebx, [rax]
0x180082bcc  lea     rdx, aFaultdomain; "FaultDomain"
0x180082bd3  lea     rcx, [rsp+148h+var_A0]
0x180082bdb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180082be0  nop
0x180082be1  mov     dword ptr [rsp+148h+var_F0], ebx
  ... truncated ...
```
