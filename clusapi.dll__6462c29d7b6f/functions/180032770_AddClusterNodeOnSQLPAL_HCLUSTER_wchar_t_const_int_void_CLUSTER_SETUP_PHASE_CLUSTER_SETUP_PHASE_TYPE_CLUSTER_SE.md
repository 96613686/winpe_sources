# AddClusterNodeOnSQLPAL(_HCLUSTER *,wchar_t const *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *)

- ea: `0x180032770`
- end: `0x180032bb8`
- name: `?AddClusterNodeOnSQLPAL@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WP6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@K1K@Z2@Z`
- size: `1096`
- prototype: `struct _HNODE *__fastcall(HCLUSTER hCluster, const wchar_t *, int (*)(void *, enum _CLUSTER_SETUP_PHASE, enum _CLUSTER_SETUP_PHASE_TYPE, enum _CLUSTER_SETUP_PHASE_SEVERITY, unsigned int, const wchar_t *, unsigned int), void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040790`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cf54`
- `0x18001feac`
- `0x180025478`
- `0x180029410`
- `0x18002acc0`
- `0x18002adc0`
- `0x18002c220`
- `0x18002f130`
- `0x18003180c`
- `0x180032770`
- `0x180038b2c`
- `0x180057f5c`
- `0x18006f910`
- `0x18009ff08`
- `0x1800a2c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800327f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800327f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003297d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003297d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800329d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800329d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800328a9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800328a9`

## string_xrefs

- `0x180032a62`: `There is already a fault domain with the same name as the node.`
- `0x180032b04`: `Node %ws is already a member of this cluster`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _HNODE *__fastcall AddClusterNodeOnSQLPAL(
        struct _HCLUSTER *hCluster,
        const wchar_t *a2,
        int (*a3)(void *, enum _CLUSTER_SETUP_PHASE, enum _CLUSTER_SETUP_PHASE_TYPE, enum _CLUSTER_SETUP_PHASE_SEVERITY, unsigned int, const wchar_t *, unsigned int),
        void *a4)
{
  wchar_t *v6; // rdi
  struct _HCLUSENUM *v7; // rbx
  DWORD i; // r14d
  int v9; // eax
  DWORD v10; // eax
  int v11; // eax
  DWORD EnumCount; // eax
  int v13; // eax
  struct _HNODE *v14; // rdi
  struct _HNODE *result; // rax
  DWORD LastError; // eax
  int v17; // edx
  int cchCount2[2]; // [rsp+28h] [rbp-C40h]
  DWORD dwErrCode; // [rsp+30h] [rbp-C38h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-C34h] BYREF
  int v21; // [rsp+38h] [rbp-C30h] BYREF
  int v22; // [rsp+3Ch] [rbp-C2Ch] BYREF
  DWORD dwType; // [rsp+40h] [rbp-C28h] BYREF
  _QWORD v24[7]; // [rsp+48h] [rbp-C20h] BYREF
  cxl::Exception *v25; // [rsp+80h] [rbp-BE8h] BYREF
  std::system_error *v26; // [rsp+88h] [rbp-BE0h] BYREF
  _QWORD v27[4]; // [rsp+90h] [rbp-BD8h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+B0h] [rbp-BB8h] BYREF
  _BYTE v29[272]; // [rsp+1C0h] [rbp-AA8h] BYREF
  _BYTE v30[272]; // [rsp+2D0h] [rbp-998h] BYREF
  _BYTE v31[272]; // [rsp+3E0h] [rbp-888h] BYREF
  _BYTE v32[272]; // [rsp+4F0h] [rbp-778h] BYREF
  _BYTE v33[272]; // [rsp+600h] [rbp-668h] BYREF
  _BYTE v34[272]; // [rsp+710h] [rbp-558h] BYREF
  _BYTE v35[272]; // [rsp+820h] [rbp-448h] BYREF
  _BYTE v36[272]; // [rsp+930h] [rbp-338h] BYREF
  WCHAR szName[256]; // [rsp+A40h] [rbp-228h] BYREF

  try
  {
    if ( !a2 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)pExceptionObject, 87, L"Missing newNodeName");
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    TraceMsg(4, 0, L"AddClusterNodeOnSQLPAL", 3935, L"Starting SQLPAL node add. New node name: %ws", a2);
    v6 = newdup(a2);
    dwErrCode = 0;
    v21 = 0;
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)hCluster + 2)) )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v29,
        87,
        L"New node name is the same as the cluster name");
      throw (ClusRtl::ExceptionMsg *)v29;
    }
    if ( FaultDomainExists(hCluster, v6) )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v30,
        183,
        L"There is already a fault domain with the same name as the node.");
      throw (ClusRtl::ExceptionMsg *)v30;
    }
    cchName = 256;
    v7 = ClusterOpenEnum(hCluster, 1u);
    v24[6] = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v31, LastError, L"Failed to get enumeration handle");
      throw (ClusRtl::ExceptionMsg *)v31;
    }
    for ( i = 0; !ClusterEnum(v7, i, &dwType, szName, &cchName); ++i )
    {
      v9 = MylstrlenW(v6, 0x100u, &dwErrCode);
      if ( v9 < 0 )
      {
        if ( (v9 & 0x1FFF0000) != 0x70000 || (v17 = (unsigned __int16)v9, !(_WORD)v9) )
          v17 = v9;
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v32, v17, L"Failed to calculate node label size");
        throw (ClusRtl::ExceptionMsg *)v32;
      }
      v10 = 256;
      if ( dwErrCode < 0x100 )
        v10 = dwErrCode;
      if ( CompareStringW(0x400u, 1u, szName, cchName, v6, v10) == 2 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v33,
          5065,
          L"Node %ws is already a member of this cluster",
          v6);
        throw (ClusRtl::ExceptionMsg *)v33;
      }
      cchName = 256;
    }
    cchName = -1;
    v11 = ComputeMaximumNumberOfNodes(0, &cchName);
    if ( v11 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v34,
        v11,
        L"Failed to obtain max number of nodes for node being added");
      throw (ClusRtl::ExceptionMsg *)v34;
    }
    EnumCount = ClusterGetEnumCount(v7);
    if ( EnumCount >= cchName )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v35, 5934, L"Cluster membership is full");
      throw (ClusRtl::ExceptionMsg *)v35;
    }
    v22 = 256;
    std::vector<unsigned char>::vector<unsigned char>(v27, 256);
    v24[0] = "ApiAddNode";
    v24[1] = (char *)hCluster + 40;
    v24[2] = v6;
    v24[3] = &v21;
    v24[4] = &v22;
    v24[5] = v27[0];
    v13 = ReconnectOnError<AddNodeFunctor>(v24, hCluster);
    if ( v13 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v36, v13, L"Failed to add node %ws to cluster", v6);
      throw (ClusRtl::ExceptionMsg *)v36;
    }
    v14 = OpenClusterNodeImpl(hCluster, v6, 0x10000000, 0, 1);
    if ( !v14 )
    {
      cchCount2[0] = GetLastError();
      TraceMsg(
        2,
        0,
        L"AddClusterNodeOnSQLPAL",
        4036,
        L"Failed to get a handle to the new node - %d",
        *(_QWORD *)cchCount2);
    }
    std::vector<unsigned char>::_Tidy(v27);
    if ( v7 != (struct _HCLUSENUM *)-1LL )
      ClusterCloseEnumCommon(v7, 1);
    result = v14;
  }
  catch ( cxl::Exception *v25 )
  {
    dwErrCode = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v25 + 88));
    goto LABEL_21;
  }
  catch ( std::system_error *v26 )
  {
    dwErrCode = *((_DWORD *)v26 + 6);
    goto LABEL_21;
  }
  catch ( std::bad_alloc )
  {
    dwErrCode = 14;
    goto LABEL_21;
  }
  catch ( std::exception )
  {
    dwErrCode = 1359;
    goto LABEL_21;
  }
  catch ( ... )
  {
    dwErrCode = 1359;
LABEL_21:
    SetLastError(dwErrCode);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180032770  mov     [rsp+arg_10], rbx
0x180032775  mov     [rsp+arg_18], rsi
0x18003277a  push    rdi
0x18003277b  push    r14
0x18003277d  push    r15
0x18003277f  sub     rsp, 0C50h
0x180032786  mov     rax, cs:__security_cookie
0x18003278d  xor     rax, rsp
0x180032790  mov     [rsp+0C68h+var_28], rax
0x180032798  mov     rbx, rdx
0x18003279b  mov     rsi, rcx
0x18003279e  test    rdx, rdx
0x1800327a1  jz      loc_180032A0C
0x1800327a7  mov     qword ptr [rsp+0C68h+cchCount2], rbx
0x1800327ac  lea     rax, aStartingSqlpal; "Starting SQLPAL node add. New node name"...
0x1800327b3  mov     [rsp+0C68h+lpcchName], rax
0x1800327b8  mov     r9d, 0F5Fh
0x1800327be  lea     r8, aAddclusternode_2; "AddClusterNodeOnSQLPAL"
0x1800327c5  xor     edx, edx
0x1800327c7  lea     ecx, [rdx+4]
0x1800327ca  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800327cf  mov     rcx, rbx; wchar_t *
0x1800327d2  call    ?newdup@@YAPEA_WPEB_W@Z; newdup(wchar_t const *)
0x1800327d7  mov     rdi, rax
0x1800327da  mov     [rsp+0C68h+dwErrCode], 0
0x1800327e2  mov     [rsp+0C68h+var_C30], 0
0x1800327ea  mov     rdx, rax
0x1800327ed  mov     rcx, [rsi+10h]
0x1800327f1  call    cs:__imp__o__wcsicmp
0x1800327f7  test    eax, eax
0x1800327f9  jz      loc_180032A37
0x1800327ff  mov     rdx, rdi; wchar_t *
0x180032802  mov     rcx, rsi; struct _HCLUSTER *
0x180032805  call    ?FaultDomainExists@@YA_NPEAU_HCLUSTER@@PEB_W@Z; FaultDomainExists(_HCLUSTER *,wchar_t const *)
0x18003280a  test    al, al
0x18003280c  jnz     loc_180032A62
0x180032812  mov     r15d, 100h
0x180032818  mov     [rsp+0C68h+cchName], r15d
0x18003281d  mov     edx, 1; dwType
0x180032822  mov     rcx, rsi; hCluster
0x180032825  call    ClusterOpenEnum
0x18003282a  mov     rbx, rax
0x18003282d  mov     [rsp+0C68h+var_BF0], rax
0x180032832  test    rax, rax
0x180032835  jz      loc_180032A90
0x18003283b  xor     r14d, r14d
0x18003283e  lea     rax, [rsp+0C68h+cchName]
0x180032843  mov     [rsp+0C68h+lpcchName], rax; lpcchName
0x180032848  lea     r9, [rsp+0C68h+szName]; lpszName
0x180032850  lea     r8, [rsp+0C68h+dwType]; lpdwType
0x180032855  mov     edx, r14d; dwIndex
0x180032858  mov     rcx, rbx; hEnum
0x18003285b  call    ClusterEnum
0x180032860  test    eax, eax
0x180032862  jnz     short loc_1800328C5
0x180032864  lea     r8, [rsp+0C68h+dwErrCode]; unsigned int *
0x180032869  mov     edx, r15d; unsigned int
0x18003286c  mov     rcx, rdi; wchar_t *
0x18003286f  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x180032874  test    eax, eax
0x180032876  js      loc_180032AC0
0x18003287c  mov     eax, r15d
0x18003287f  cmp     [rsp+0C68h+dwErrCode], r15d
0x180032884  cmovb   eax, [rsp+0C68h+dwErrCode]
0x180032889  mov     [rsp+0C68h+cchCount2], eax; cchCount2
0x18003288d  mov     [rsp+0C68h+lpcchName], rdi; lpString2
0x180032892  mov     r9d, [rsp+0C68h+cchName]; cchCount1
0x180032897  lea     r8, [rsp+0C68h+szName]; lpString1
0x18003289f  mov     edx, 1; dwCmpFlags
0x1800328a4  mov     ecx, 400h; Locale
0x1800328a9  call    cs:__imp_CompareStringW
0x1800328af  cmp     eax, 2
0x1800328b2  jz      loc_180032B01
0x1800328b8  mov     [rsp+0C68h+cchName], r15d
0x1800328bd  inc     r14d
0x1800328c0  jmp     loc_18003283E
0x1800328c5  mov     [rsp+0C68h+cchName], 0FFFFFFFFh
0x1800328cd  lea     rdx, [rsp+0C68h+cchName]; unsigned int *
0x1800328d2  xor     ecx, ecx; wchar_t *
0x1800328d4  call    ?ComputeMaximumNumberOfNodes@@YAKPEB_WPEAK@Z; ComputeMaximumNumberOfNodes(wchar_t const *,ulong *)
0x1800328d9  test    eax, eax
0x1800328db  jnz     loc_180032B31
0x1800328e1  mov     rcx, rbx; hEnum
0x1800328e4  call    ClusterGetEnumCount
0x1800328e9  cmp     eax, [rsp+0C68h+cchName]
0x1800328ed  jnb     loc_180032B5B
0x1800328f3  mov     [rsp+0C68h+var_C2C], r15d
0x1800328f8  mov     rdx, r15
0x1800328fb  lea     rcx, [rsp+0C68h+var_BD8]
0x180032903  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180032908  nop
0x180032909  lea     rax, aApiaddnode; "ApiAddNode"
0x180032910  mov     [rsp+0C68h+var_C20], rax
0x180032915  lea     rax, [rsi+28h]
0x180032919  mov     [rsp+0C68h+var_C18], rax
0x18003291e  mov     [rsp+0C68h+var_C10], rdi
0x180032923  lea     rax, [rsp+0C68h+var_C30]
0x180032928  mov     [rsp+0C68h+var_C08], rax
0x18003292d  lea     rax, [rsp+0C68h+var_C2C]
0x180032932  mov     [rsp+0C68h+var_C00], rax
0x180032937  mov     rax, [rsp+0C68h+var_BD8]
0x18003293f  mov     [rsp+0C68h+var_BF8], rax
0x180032944  mov     rdx, rsi
0x180032947  lea     rcx, [rsp+0C68h+var_C20]
0x18003294c  call    ??$ReconnectOnError@VAddNodeFunctor@@@@YAKAEAVAddNodeFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<AddNodeFunctor>(AddNodeFunctor &,_CLUSTER *)
0x180032951  test    eax, eax
0x180032953  jnz     loc_180032B89
0x180032959  mov     dword ptr [rsp+0C68h+lpcchName], 1; int
0x180032961  xor     r9d, r9d; unsigned int *
0x180032964  mov     r8d, 10000000h; unsigned int
0x18003296a  mov     rdx, rdi; wchar_t *
0x18003296d  mov     rcx, rsi; struct _HCLUSTER *
0x180032970  call    ?OpenClusterNodeImpl@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterNodeImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x180032975  mov     rdi, rax
0x180032978  test    rax, rax
0x18003297b  jnz     short loc_1800329AB
0x18003297d  call    cs:__imp_GetLastError
0x180032983  mov     [rsp+0C68h+cchCount2], eax
0x180032987  lea     rax, aFailedToGetAHa; "Failed to get a handle to the new node "...
0x18003298e  mov     [rsp+0C68h+lpcchName], rax
0x180032993  mov     r9d, 0FC4h
0x180032999  lea     r8, aAddclusternode_2; "AddClusterNodeOnSQLPAL"
0x1800329a0  xor     edx, edx
0x1800329a2  lea     ecx, [rdi+2]
0x1800329a5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800329aa  nop
0x1800329ab  lea     rcx, [rsp+0C68h+var_BD8]
0x1800329b3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800329b8  nop
0x1800329b9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800329bd  jz      short loc_1800329CC
0x1800329bf  mov     edx, 1; int
0x1800329c4  mov     rcx, rbx; struct _HCLUSENUM *
0x1800329c7  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x1800329cc  mov     rax, rdi
0x1800329cf  jmp     short loc_1800329DD
0x1800329d1  mov     ecx, [rsp+0C68h+dwErrCode]; dwErrCode
0x1800329d5  call    cs:__imp_SetLastError
0x1800329db  xor     eax, eax
0x1800329dd  mov     rcx, [rsp+0C68h+var_28]
0x1800329e5  xor     rcx, rsp; StackCookie
0x1800329e8  call    __security_check_cookie
0x1800329ed  lea     r11, [rsp+0C68h+var_18]
0x1800329f5  mov     rbx, [r11+30h]
0x1800329f9  mov     rsi, [r11+38h]
0x1800329fd  mov     rsp, r11
0x180032a00  pop     r15
0x180032a02  pop     r14
0x180032a04  pop     rdi
0x180032a05  retn
0x180032a06  jmp     short loc_1800329D1
0x180032a08  jmp     short loc_1800329D1
0x180032a0a  jmp     short loc_1800329D1
0x180032a0c  lea     r8, aMissingNewnode; "Missing newNodeName"
0x180032a13  lea     edx, [rbx+57h]; int
0x180032a16  lea     rcx, [rsp+0C68h+pExceptionObject]; this
0x180032a1e  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032a23  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032a2a  lea     rcx, [rsp+0C68h+pExceptionObject]; pExceptionObject
0x180032a32  call    _CxxThrowException_0
0x180032a37  lea     r8, aNewNodeNameIsT; "New node name is the same as the cluste"...
0x180032a3e  lea     edx, [rax+57h]; int
0x180032a41  lea     rcx, [rsp+0C68h+var_AA8]; this
0x180032a49  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032a4e  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032a55  lea     rcx, [rsp+0C68h+var_AA8]; pExceptionObject
0x180032a5d  call    _CxxThrowException_0
0x180032a62  lea     r8, aThereIsAlready_0; "There is already a fault domain with th"...
0x180032a69  mov     edx, 0B7h; int
0x180032a6e  lea     rcx, [rsp+0C68h+var_998]; this
0x180032a76  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032a7b  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032a82  lea     rcx, [rsp+0C68h+var_998]; pExceptionObject
0x180032a8a  call    _CxxThrowException_0
0x180032a90  call    cs:__imp_GetLastError
0x180032a96  mov     edx, eax; int
0x180032a98  lea     r8, aFailedToGetEnu; "Failed to get enumeration handle"
0x180032a9f  lea     rcx, [rsp+0C68h+var_888]; this
0x180032aa7  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032aac  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032ab3  lea     rcx, [rsp+0C68h+var_888]; pExceptionObject
0x180032abb  call    _CxxThrowException_0
0x180032ac0  mov     ecx, eax
0x180032ac2  and     ecx, 1FFF0000h
0x180032ac8  cmp     ecx, 70000h
0x180032ace  jnz     short loc_180032AD7
0x180032ad0  movzx   edx, ax
0x180032ad3  test    edx, edx
0x180032ad5  jnz     short loc_180032AD9
0x180032ad7  mov     edx, eax; int
0x180032ad9  lea     r8, aFailedToCalcul; "Failed to calculate node label size"
0x180032ae0  lea     rcx, [rsp+0C68h+var_778]; this
0x180032ae8  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032aed  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032af4  lea     rcx, [rsp+0C68h+var_778]; pExceptionObject
0x180032afc  call    _CxxThrowException_0
0x180032b01  mov     r9, rdi
0x180032b04  lea     r8, aNodeWsIsAlread; "Node %ws is already a member of this cl"...
0x180032b0b  mov     edx, 13C9h; int
0x180032b10  lea     rcx, [rsp+0C68h+var_668]; this
0x180032b18  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032b1d  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032b24  lea     rcx, [rsp+0C68h+var_668]; pExceptionObject
0x180032b2c  call    _CxxThrowException_0
0x180032b31  lea     r8, aFailedToObtain_3; "Failed to obtain max number of nodes fo"...
0x180032b38  mov     edx, eax; int
0x180032b3a  lea     rcx, [rsp+0C68h+var_558]; this
0x180032b42  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032b47  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032b4e  lea     rcx, [rsp+0C68h+var_558]; pExceptionObject
0x180032b56  call    _CxxThrowException_0
0x180032b5b  lea     r8, aClusterMembers; "Cluster membership is full"
0x180032b62  mov     edx, 172Eh; int
0x180032b67  lea     rcx, [rsp+0C68h+var_448]; this
0x180032b6f  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032b74  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032b7b  lea     rcx, [rsp+0C68h+var_448]; pExceptionObject
0x180032b83  call    _CxxThrowException_0
0x180032b89  mov     r9, rdi
0x180032b8c  lea     r8, aFailedToAddNod; "Failed to add node %ws to cluster"
0x180032b93  mov     edx, eax; int
0x180032b95  lea     rcx, [rsp+0C68h+var_338]; this
0x180032b9d  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032ba2  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032ba9  lea     rcx, [rsp+0C68h+var_338]; pExceptionObject
0x180032bb1  call    _CxxThrowException_0
```
