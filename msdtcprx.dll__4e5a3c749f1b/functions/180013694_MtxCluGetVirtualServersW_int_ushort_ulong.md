# MtxCluGetVirtualServersW(int,ushort * * *,ulong *)

- ea: `0x180013694`
- end: `0x180013d01`
- name: `?MtxCluGetVirtualServersW@@YAJHPEAPEAPEAGPEAK@Z`
- size: `1645`
- prototype: `__int64 __fastcall(int, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800726d0`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x1800092f4`
- `0x18000d5f4`
- `0x18000f8d0`
- `0x18001156c`
- `0x180013694`
- `0x18001a9b8`
- `0x18007198c`
- `0x180071fc8`
- `0x18007975c`
- `0x180081d9e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001398d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001398d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001390a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001390a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b11`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x1800138c7`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180013b6f`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x1800138c7`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180013b6f`
- `CLUSAPI!ClusterResourceTypeGetEnumCount` at `0x1800138f8`
- `CLUSAPI!ClusterResourceTypeGetEnumCount` at `0x1800138f8`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x180013852`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x180013852`
- `CLUSAPI!OpenClusterResourceEx` at `0x180013a22`
- `CLUSAPI!OpenClusterResourceEx` at `0x180013a22`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x180013c0f`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x180013c0f`
- `CLUSAPI!CloseClusterResource` at `0x1800139e5`
- `CLUSAPI!CloseClusterResource` at `0x180013c58`
- `CLUSAPI!CloseClusterResource` at `0x1800139e5`
- `CLUSAPI!CloseClusterResource` at `0x180013c58`

## string_xrefs

- `0x1800136fc`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18001377f`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800137c7`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800138aa`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013942`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800139b8`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013a39`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013a90`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013b52`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013b8b`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013bcc`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013c2b`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180013cc2`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800138be`: `ClusterResourceTypeOpenEnum`
- `0x1800138d6`: `ClusterResourceTypeOpenEnum failed`
- `0x180013b66`: `OpenClusterResourceEx`
- `0x180013b7e`: `OpenClusterResourceEx failed`
- `0x180013a40`: `After OpenClusterResourceEx, hResource = 0x%x`
- `0x1800136cc`: `MtxCluGetVirtualServersW (com\complus\dtc\shared\util\clusterutilbasic.cpp@992): MtxCluGetVirtualServersW, pppArgVirtualServers != NULL`
- `0x1800136de`: `MtxCluGetVirtualServersW (com\complus\dtc\shared\util\clusterutilbasic.cpp@993): MtxCluGetVirtualServersW, pdwVirtualServers != NULL`
- `0x18001375b`: `MtxCluGetVirtualServersW, CoTaskMemAlloc(dwVirtualServers*LPWSTR) failed`
- `0x180013918`: `MtxCluGetVirtualServersW, CoTaskMemAlloc(ppVirtualServers*LPWSTR) failed`

## pseudocode

```c
__int64 __fastcall MtxCluGetVirtualServersW(unsigned int a1, unsigned __int16 ***a2, unsigned int *a3)
{
  struct _HRESOURCE *v3; // r15
  WCHAR *v6; // r14
  unsigned __int16 **v7; // rax
  unsigned __int16 **v8; // rsi
  signed int PhysicalNodeNameW; // edi
  unsigned __int16 **v10; // r15
  struct _HCLUSTER *LocalClusterHandle; // rax
  struct _HCLUSTER *v12; // rbx
  signed int v13; // eax
  struct _HRESTYPEENUM *v14; // rax
  signed int v15; // eax
  int v16; // eax
  void *v17; // rbx
  DWORD EnumCount; // eax
  SIZE_T v19; // rbx
  unsigned int v20; // ebx
  DWORD v21; // eax
  DWORD i; // ebx
  HCLUSTER v23; // rbx
  HRESOURCE v24; // rax
  unsigned __int16 *v25; // rbx
  unsigned int v26; // ecx
  const wchar_t *v27; // rax
  __int64 v28; // r9
  signed int LastError; // eax
  int StringW; // eax
  void *v31; // rbx
  unsigned int v32; // r12d
  __int64 v34; // [rsp+20h] [rbp-50h]
  __int64 v35; // [rsp+28h] [rbp-48h]
  __int64 dwType; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpszResourceName; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v38; // [rsp+50h] [rbp-20h] BYREF
  HRESTYPEENUM hResTypeEnum; // [rsp+58h] [rbp-18h]
  HCLUSTER hCluster; // [rsp+60h] [rbp-10h]
  unsigned int v41; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF
  DWORD v43; // [rsp+C8h] [rbp+58h]

  v41 = a1;
  v3 = 0;
  lpszResourceName = 0;
  v38 = 0;
  v6 = 0;
  LODWORD(dwType) = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluGetVirtualServersW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@992): MtxCluGetVirtualServersW, pp"
       "pArgVirtualServers != NULL");
  if ( !a3 )
    DtcInternalErrorW(
      L"MtxCluGetVirtualServersW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@993): MtxCluGetVirtualServersW, pd"
       "wVirtualServers != NULL");
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    995,
    L"MtxCluGetVirtualServersW",
    0,
    L"In");
  *a2 = 0;
  *a3 = 0;
  LOBYTE(v41) = 0;
  MtxCluIsClusterPresentNonAdmin(0, (bool *)&v41);
  if ( !(_BYTE)v41 )
  {
    v7 = (unsigned __int16 **)CoTaskMemAlloc(8u);
    v8 = v7;
    if ( !v7 )
    {
      PhysicalNodeNameW = -2147024882;
      LODWORD(v35) = -2147024882;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        1008,
        L"MtxCluGetVirtualServersW",
        v35,
        L"MtxCluGetVirtualServersW, CoTaskMemAlloc(dwVirtualServers*LPWSTR) failed");
      goto LABEL_58;
    }
    *v7 = 0;
    PhysicalNodeNameW = GetPhysicalNodeNameW(v7);
    if ( PhysicalNodeNameW >= 0 )
    {
      *a2 = v8;
      *a3 = 1;
      goto LABEL_58;
    }
    v41 = 1;
    LODWORD(v35) = PhysicalNodeNameW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      1017,
      L"MtxCluGetVirtualServersW",
      v35,
      L"MtxCluGetVirtualServersW, GetPhysicalNodeNameW failed");
    v10 = v8;
    goto LABEL_55;
  }
  LocalClusterHandle = GetLocalClusterHandle();
  hCluster = LocalClusterHandle;
  v12 = LocalClusterHandle;
  if ( LocalClusterHandle )
  {
    v14 = ClusterResourceTypeOpenEnum(LocalClusterHandle, L"Network Name", 2u);
    hResTypeEnum = v14;
    if ( v14 )
    {
      v41 = 0;
      EnumCount = ClusterResourceTypeGetEnumCount(v14);
      v19 = 8LL * EnumCount;
      LODWORD(pv) = EnumCount;
      v8 = (unsigned __int16 **)CoTaskMemAlloc(v19);
      if ( !v8 )
      {
        LODWORD(v35) = -2147024882;
        PhysicalNodeNameW = -2147024882;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          1068,
          L"MtxCluGetVirtualServersW",
          v35,
          L"MtxCluGetVirtualServersW, CoTaskMemAlloc(ppVirtualServers*LPWSTR) failed");
        v20 = 0;
        goto LABEL_47;
      }
      v21 = (unsigned int)pv;
      PhysicalNodeNameW = 0;
      if ( (_DWORD)pv )
      {
        memset_0(v8, 0, v19 & 0xFFFFFFFFFFFFFFF8uLL);
        v21 = (unsigned int)pv;
      }
      for ( i = 0; ; i = v43 + 1 )
      {
        v43 = i;
        if ( i >= v21 )
          break;
        if ( v6 )
        {
          CoTaskMemFree(v6);
          lpszResourceName = 0;
        }
        if ( v3 )
        {
          TraceStringInline(
            7,
            240,
            L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
            1088,
            L"MtxCluGetVirtualServersW",
            0,
            L"Closing hResource = 0x%x",
            v3,
            dwType);
          CloseClusterResource(v3);
          v3 = 0;
        }
        PhysicalNodeNameW = ClusterResourceTypeEnumHelper(
                              hResTypeEnum,
                              i,
                              (LPDWORD)&dwType,
                              (unsigned __int16 **)&lpszResourceName);
        if ( PhysicalNodeNameW < 0 )
        {
          LODWORD(v35) = PhysicalNodeNameW;
          TraceStringInline(
            7,
            1,
            L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
            1096,
            L"MtxCluGetVirtualServersW",
            v35,
            L"Error enumerating cluster");
          v6 = (WCHAR *)lpszResourceName;
          v20 = v41;
          goto LABEL_47;
        }
        v6 = (WCHAR *)lpszResourceName;
        v23 = hCluster;
        v24 = OpenClusterResourceEx(hCluster, lpszResourceName, 0x2000000u, 0);
        v3 = v24;
        if ( !v24 )
        {
          LastError = GetLastError();
          PhysicalNodeNameW = LastError;
          if ( LastError > 0 )
            PhysicalNodeNameW = (unsigned __int16)LastError | 0x80070000;
          pv = 0;
          StringW = MakeStringW((unsigned __int16 **)&pv, L"hCluster: %x lpszResourceName: %s", v23, v6);
          v31 = pv;
          if ( StringW >= 0 )
            TraceFileW(
              PhysicalNodeNameW,
              (unsigned __int16 *)pv,
              L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
              0x458u);
          FailedClusterAPIToEventLog(L"OpenClusterResourceEx", (unsigned int)PhysicalNodeNameW, v31);
          CoTaskMemFree(v31);
          v27 = L"OpenClusterResourceEx failed";
          v28 = 1118;
          goto LABEL_43;
        }
        TraceStringInline(
          7,
          240,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          1122,
          L"MtxCluGetVirtualServersW",
          0,
          L"After OpenClusterResourceEx, hResource = 0x%x",
          v24);
        if ( (unsigned int)IsResourceOnLocalNode(v3) )
        {
          PhysicalNodeNameW = GetActualNameOfNetworkNameResource(v3, &v38);
          if ( PhysicalNodeNameW < 0 )
          {
            v27 = L"GetActualNameOfNetworkNameResource failed";
            v28 = 1133;
LABEL_43:
            LODWORD(v35) = PhysicalNodeNameW;
            TraceStringInline(
              7,
              1,
              L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
              v28,
              L"MtxCluGetVirtualServersW",
              v35,
              v27);
            v20 = v41;
            goto LABEL_47;
          }
          v25 = v38;
          TraceStringInline(
            7,
            240,
            L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
            1137,
            L"MtxCluGetVirtualServersW",
            0,
            L"Actual resource name = %s",
            v38);
          v26 = v41;
          v38 = 0;
          v8[v41] = v25;
          v41 = v26 + 1;
        }
        v21 = (unsigned int)pv;
      }
      v20 = v41;
      if ( v41 )
      {
        *a2 = v8;
        v8 = 0;
        *a3 = v20;
      }
LABEL_47:
      ClusterResourceTypeCloseEnum(hResTypeEnum);
      if ( v3 )
      {
        TraceStringInline(
          7,
          240,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          1164,
          L"MtxCluGetVirtualServersW",
          0,
          L"Closing hResource = 0x%x",
          v3);
        CloseClusterResource(v3);
      }
      if ( v6 )
        CoTaskMemFree(v6);
      if ( v38 )
        CoTaskMemFree(v38);
      if ( v8 )
      {
        v6 = 0;
        v10 = v8;
        if ( !v20 )
        {
LABEL_57:
          CoTaskMemFree(v8);
          goto LABEL_58;
        }
LABEL_55:
        v32 = v41;
        do
        {
          CoTaskMemFree(v10[(_QWORD)v6]);
          v10[(_QWORD)v6] = 0;
          v6 = (WCHAR *)(unsigned int)((_DWORD)v6 + 1);
        }
        while ( (unsigned int)v6 < v32 );
        goto LABEL_57;
      }
    }
    else
    {
      v15 = GetLastError();
      PhysicalNodeNameW = v15;
      if ( v15 > 0 )
        PhysicalNodeNameW = (unsigned __int16)v15 | 0x80070000;
      pv = 0;
      LODWORD(v34) = 2;
      v16 = MakeStringW(
              (unsigned __int16 **)&pv,
              L"hCluster: %x lpszResourceTypeName: %s lpcchNodeName: %d",
              v12,
              L"Network Name",
              v34);
      v17 = pv;
      if ( v16 >= 0 )
        TraceFileW(
          PhysicalNodeNameW,
          (unsigned __int16 *)pv,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          0x417u);
      FailedClusterAPIToEventLog(L"ClusterResourceTypeOpenEnum", (unsigned int)PhysicalNodeNameW, v17);
      CoTaskMemFree(v17);
      LODWORD(v35) = PhysicalNodeNameW;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        1053,
        L"MtxCluGetVirtualServersW",
        v35,
        L"ClusterResourceTypeOpenEnum failed");
    }
  }
  else
  {
    v13 = GetLastError();
    PhysicalNodeNameW = v13;
    if ( v13 > 0 )
      PhysicalNodeNameW = (unsigned __int16)v13 | 0x80070000;
    LODWORD(v35) = PhysicalNodeNameW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      1032,
      L"MtxCluGetVirtualServersW",
      v35,
      L"GetLocalClusterHandle failed");
  }
LABEL_58:
  LODWORD(v35) = PhysicalNodeNameW;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    1196,
    L"MtxCluGetVirtualServersW",
    v35,
    L"Out");
  return (unsigned int)PhysicalNodeNameW;
}

```

## disassembly

```asm
0x180013694  mov     [rsp-38h+arg_10], rbx
0x180013699  mov     [rsp-38h+arg_0], ecx
0x18001369d  push    rbp
0x18001369e  push    rsi
0x18001369f  push    rdi
0x1800136a0  push    r12
0x1800136a2  push    r13
0x1800136a4  push    r14
0x1800136a6  push    r15
0x1800136a8  mov     rbp, rsp
0x1800136ab  sub     rsp, 70h
0x1800136af  xor     r15d, r15d
0x1800136b2  mov     r12, r8
0x1800136b5  mov     [rbp+lpszResourceName], r15
0x1800136b9  mov     r13, rdx
0x1800136bc  mov     [rbp+var_20], r15
0x1800136c0  mov     r14d, r15d
0x1800136c3  mov     dword ptr [rbp+dwType], r15d
0x1800136c7  test    rdx, rdx
0x1800136ca  jnz     short loc_1800136D9
0x1800136cc  lea     rcx, aMtxclugetvirtu_3; "MtxCluGetVirtualServersW (com\\complus"...
0x1800136d3  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800136d9  test    r12, r12
0x1800136dc  jnz     short loc_1800136EB
0x1800136de  lea     rcx, aMtxclugetvirtu_0; "MtxCluGetVirtualServersW (com\\complus"...
0x1800136e5  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800136eb  mov     edx, 6
0x1800136f0  lea     rax, aIn_0; "In"
0x1800136f7  mov     [rsp+70h+var_40], rax
0x1800136fc  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013703  lea     rax, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x18001370a  mov     [rsp+70h+var_48], r15
0x18001370f  mov     r9d, 3E3h
0x180013715  mov     [rsp+70h+var_50], rax
0x18001371a  lea     ecx, [rdx+1]
0x18001371d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013722  lea     rdx, [rbp+arg_0]; bool *
0x180013726  mov     [r13+0], r15
0x18001372a  xor     ecx, ecx; unsigned __int16 *
0x18001372c  mov     [r12], r15d
0x180013730  mov     byte ptr [rbp+arg_0], r15b
0x180013734  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180013739  cmp     byte ptr [rbp+arg_0], r15b
0x18001373d  jnz     loc_1800137FF
0x180013743  mov     ecx, 8; cb
0x180013748  call    cs:__imp_CoTaskMemAlloc
0x18001374e  mov     rsi, rax
0x180013751  test    rax, rax
0x180013754  jnz     short loc_180013798
0x180013756  mov     eax, 8007000Eh
0x18001375b  lea     rcx, aMtxclugetvirtu_1; "MtxCluGetVirtualServersW, CoTaskMemAllo"...
0x180013762  mov     [rsp+70h+var_40], rcx
0x180013767  mov     edi, eax
0x180013769  mov     dword ptr [rsp+70h+var_48], eax
0x18001376d  mov     r9d, 3F0h
0x180013773  mov     edx, 1
0x180013778  lea     rax, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x18001377f  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013786  mov     [rsp+70h+var_50], rax
0x18001378b  lea     ecx, [rdx+6]
0x18001378e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013793  jmp     loc_180013CB1
0x180013798  mov     rcx, rsi; unsigned __int16 **
0x18001379b  mov     [rax], r15
0x18001379e  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x1800137a3  mov     edi, eax
0x1800137a5  test    eax, eax
0x1800137a7  jns     short loc_1800137EE
0x1800137a9  mov     edx, 1
0x1800137ae  mov     [rbp+arg_0], 1
0x1800137b5  lea     rax, aMtxclugetvirtu; "MtxCluGetVirtualServersW, GetPhysicalNo"...
0x1800137bc  mov     r9d, 3F9h
0x1800137c2  mov     [rsp+70h+var_40], rax
0x1800137c7  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800137ce  lea     rax, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x1800137d5  mov     dword ptr [rsp+70h+var_48], edi
0x1800137d9  lea     ecx, [rdx+6]
0x1800137dc  mov     [rsp+70h+var_50], rax
0x1800137e1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800137e6  mov     r15, rsi
0x1800137e9  jmp     loc_180013C8A
0x1800137ee  mov     [r13+0], rsi
0x1800137f2  mov     dword ptr [r12], 1
0x1800137fa  jmp     loc_180013CB1
0x1800137ff  call    ?GetLocalClusterHandle@@YAPEAU_HCLUSTER@@XZ; GetLocalClusterHandle(void)
0x180013804  mov     [rbp+hCluster], rax
0x180013808  mov     rbx, rax
0x18001380b  test    rax, rax
0x18001380e  jnz     short loc_180013840
0x180013810  call    cs:__imp_GetLastError
0x180013816  mov     edi, eax
0x180013818  test    eax, eax
0x18001381a  jle     short loc_180013825
0x18001381c  movzx   edi, ax
0x18001381f  or      edi, 80070000h
0x180013825  lea     rax, aGetlocalcluste; "GetLocalClusterHandle failed"
0x18001382c  mov     r9d, 408h
0x180013832  mov     [rsp+70h+var_40], rax
0x180013837  mov     dword ptr [rsp+70h+var_48], edi
0x18001383b  jmp     loc_180013773
0x180013840  mov     esi, 2
0x180013845  lea     rdx, szResourceTypeName; "Network Name"
0x18001384c  mov     r8d, esi; dwType
0x18001384f  mov     rcx, rbx; hCluster
0x180013852  call    cs:__imp_ClusterResourceTypeOpenEnum
0x180013858  mov     [rbp+hResTypeEnum], rax
0x18001385c  test    rax, rax
0x18001385f  jnz     loc_1800138F1
0x180013865  call    cs:__imp_GetLastError
0x18001386b  mov     edi, eax
0x18001386d  test    eax, eax
0x18001386f  jle     short loc_18001387A
0x180013871  movzx   edi, ax
0x180013874  or      edi, 80070000h
0x18001387a  lea     r9, szResourceTypeName; "Network Name"
0x180013881  mov     [rbp+pv], r15
0x180013885  mov     r8, rbx
0x180013888  mov     dword ptr [rsp+70h+var_50], esi
0x18001388c  lea     rdx, aHclusterXLpszr; "hCluster: %x lpszResourceTypeName: %s l"...
0x180013893  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180013897  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18001389c  mov     rbx, [rbp+pv]
0x1800138a0  test    eax, eax
0x1800138a2  js      short loc_1800138BB
0x1800138a4  mov     r9d, 417h; unsigned int
0x1800138aa  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800138b1  mov     rdx, rbx; unsigned __int16 *
0x1800138b4  mov     ecx, edi; int
0x1800138b6  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800138bb  mov     r8, rbx
0x1800138be  lea     rcx, aClusterresourc_1; "ClusterResourceTypeOpenEnum"
0x1800138c5  mov     edx, edi
0x1800138c7  call    cs:__imp_FailedClusterAPIToEventLog
0x1800138cd  mov     rcx, rbx; pv
0x1800138d0  call    cs:__imp_CoTaskMemFree
0x1800138d6  lea     rax, aClusterresourc_2; "ClusterResourceTypeOpenEnum failed"
0x1800138dd  mov     r9d, 41Dh
0x1800138e3  mov     [rsp+70h+var_40], rax
0x1800138e8  mov     dword ptr [rsp+70h+var_48], edi
0x1800138ec  jmp     loc_180013773
0x1800138f1  mov     rcx, rax; hResTypeEnum
0x1800138f4  mov     [rbp+arg_0], r14d
0x1800138f8  call    cs:__imp_ClusterResourceTypeGetEnumCount
0x1800138fe  mov     ebx, eax
0x180013900  shl     rbx, 3
0x180013904  mov     rcx, rbx; cb
0x180013907  mov     dword ptr [rbp+pv], eax
0x18001390a  call    cs:__imp_CoTaskMemAlloc
0x180013910  mov     rsi, rax
0x180013913  test    rax, rax
0x180013916  jnz     short loc_18001395B
0x180013918  lea     rcx, aMtxclugetvirtu_2; "MtxCluGetVirtualServersW, CoTaskMemAllo"...
0x18001391f  mov     eax, 8007000Eh
0x180013924  mov     [rsp+70h+var_40], rcx
0x180013929  lea     r12, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x180013930  mov     dword ptr [rsp+70h+var_48], eax
0x180013934  lea     ecx, [rsi+7]
0x180013937  mov     r9d, 42Ch
0x18001393d  mov     [rsp+70h+var_50], r12
0x180013942  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013949  mov     edi, eax
0x18001394b  lea     edx, [rsi+1]
0x18001394e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013953  mov     ebx, r14d
0x180013956  jmp     loc_180013C0B
0x18001395b  mov     eax, dword ptr [rbp+pv]
0x18001395e  xor     edi, edi
0x180013960  test    eax, eax
0x180013962  jz      short loc_180013978
0x180013964  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180013968  xor     edx, edx; Val
0x18001396a  mov     r8, rbx; Size
0x18001396d  mov     rcx, rsi; void *
0x180013970  call    memset_0
0x180013975  mov     eax, dword ptr [rbp+pv]
0x180013978  xor     ebx, ebx
0x18001397a  mov     [rbp+arg_18], ebx
0x18001397d  cmp     ebx, eax
0x18001397f  jnb     loc_180013BF3
0x180013985  test    r14, r14
0x180013988  jz      short loc_18001399B
0x18001398a  mov     rcx, r14; pv
0x18001398d  call    cs:__imp_CoTaskMemFree
0x180013993  mov     [rbp+lpszResourceName], 0
0x18001399b  lea     r14, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x1800139a2  test    r15, r15
0x1800139a5  jz      short loc_1800139EE
0x1800139a7  mov     [rsp+70h+var_38], r15
0x1800139ac  lea     rax, aClosingHresour; "Closing hResource = 0x%x"
0x1800139b3  mov     [rsp+70h+var_40], rax
0x1800139b8  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800139bf  mov     [rsp+70h+var_48], 0
0x1800139c8  mov     r9d, 440h
0x1800139ce  mov     edx, 0F0h
0x1800139d3  mov     [rsp+70h+var_50], r14
0x1800139d8  mov     ecx, 7
0x1800139dd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800139e2  mov     rcx, r15; hResource
0x1800139e5  call    cs:__imp_CloseClusterResource
0x1800139eb  xor     r15d, r15d
0x1800139ee  mov     rcx, [rbp+hResTypeEnum]; hResTypeEnum
0x1800139f2  lea     r9, [rbp+lpszResourceName]; unsigned __int16 **
0x1800139f6  lea     r8, [rbp+dwType]; lpdwType
0x1800139fa  mov     edx, ebx; dwIndex
0x1800139fc  call    ?ClusterResourceTypeEnumHelper@@YAJPEAU_HRESTYPEENUM@@KPEAKPEAPEAG@Z; ClusterResourceTypeEnumHelper(_HRESTYPEENUM *,ulong,ulong *,ushort * *)
0x180013a01  mov     edi, eax
0x180013a03  test    eax, eax
0x180013a05  js      loc_180013BBB
0x180013a0b  mov     r14, [rbp+lpszResourceName]
0x180013a0f  xor     r9d, r9d; lpdwGrantedAccess
0x180013a12  mov     rbx, [rbp+hCluster]
0x180013a16  mov     rdx, r14; lpszResourceName
0x180013a19  mov     rcx, rbx; hCluster
0x180013a1c  mov     r8d, 2000000h; dwDesiredAccess
0x180013a22  call    cs:__imp_OpenClusterResourceEx
0x180013a28  mov     r15, rax
0x180013a2b  test    rax, rax
0x180013a2e  jz      loc_180013B11
0x180013a34  mov     [rsp+70h+var_38], rax
0x180013a39  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013a40  lea     rax, aAfterOpenclust; "After OpenClusterResourceEx, hResource "...
0x180013a47  mov     ebx, 7
0x180013a4c  mov     [rsp+70h+var_40], rax
0x180013a51  mov     r9d, 462h
0x180013a57  lea     rax, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x180013a5e  mov     [rsp+70h+var_48], 0
0x180013a67  mov     edx, 0F0h
0x180013a6c  mov     [rsp+70h+var_50], rax
0x180013a71  mov     ecx, ebx
0x180013a73  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013a78  mov     rcx, r15; hResource
0x180013a7b  call    ?IsResourceOnLocalNode@@YAHPEAU_HRESOURCE@@@Z; IsResourceOnLocalNode(_HRESOURCE *)
0x180013a80  test    eax, eax
0x180013a82  jz      short loc_180013AF0
0x180013a84  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180013a88  mov     rcx, r15; hResource
0x180013a8b  call    ?GetActualNameOfNetworkNameResource@@YAJPEAU_HRESOURCE@@PEAPEAG@Z; GetActualNameOfNetworkNameResource(_HRESOURCE *,ushort * *)
0x180013a90  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013a97  mov     edi, eax
0x180013a99  test    eax, eax
0x180013a9b  js      short loc_180013AFD
0x180013a9d  mov     rbx, [rbp+var_20]
0x180013aa1  lea     rax, aActualResource; "Actual resource name = %s"
0x180013aa8  mov     [rsp+70h+var_38], rbx
0x180013aad  mov     r9d, 471h
0x180013ab3  mov     [rsp+70h+var_40], rax
0x180013ab8  mov     edx, 0F0h
0x180013abd  lea     rax, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x180013ac4  mov     [rsp+70h+var_48], 0
0x180013acd  mov     ecx, 7
0x180013ad2  mov     [rsp+70h+var_50], rax
0x180013ad7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013adc  mov     ecx, [rbp+arg_0]
0x180013adf  mov     [rbp+var_20], 0
0x180013ae7  mov     [rsi+rcx*8], rbx
0x180013aeb  inc     ecx
0x180013aed  mov     [rbp+arg_0], ecx
0x180013af0  mov     ebx, [rbp+arg_18]
0x180013af3  mov     eax, dword ptr [rbp+pv]
0x180013af6  inc     ebx
0x180013af8  jmp     loc_18001397A
0x180013afd  lea     rax, aGetactualnameo_6; "GetActualNameOfNetworkNameResource fail"...
0x180013b04  mov     r9d, 46Dh
0x180013b0a  mov     ecx, ebx
0x180013b0c  jmp     loc_180013B97
0x180013b11  call    cs:__imp_GetLastError
0x180013b17  mov     edi, eax
0x180013b19  test    eax, eax
0x180013b1b  jle     short loc_180013B26
0x180013b1d  movzx   edi, ax
0x180013b20  or      edi, 80070000h
0x180013b26  mov     r9, r14
0x180013b29  mov     [rbp+pv], 0
0x180013b31  mov     r8, rbx
0x180013b34  lea     rdx, aHclusterXLpszr_0; "hCluster: %x lpszResourceName: %s"
0x180013b3b  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180013b3f  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180013b44  mov     rbx, [rbp+pv]
0x180013b48  test    eax, eax
0x180013b4a  js      short loc_180013B63
0x180013b4c  mov     r9d, 458h; unsigned int
0x180013b52  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013b59  mov     rdx, rbx; unsigned __int16 *
0x180013b5c  mov     ecx, edi; int
0x180013b5e  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180013b63  mov     r8, rbx
0x180013b66  lea     rcx, aOpenclusterres; "OpenClusterResourceEx"
0x180013b6d  mov     edx, edi
0x180013b6f  call    cs:__imp_FailedClusterAPIToEventLog
0x180013b75  mov     rcx, rbx; pv
0x180013b78  call    cs:__imp_CoTaskMemFree
0x180013b7e  lea     rax, aOpenclusterres_0; "OpenClusterResourceEx failed"
0x180013b85  mov     r9d, 45Eh
0x180013b8b  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180013b92  mov     ecx, 7
0x180013b97  mov     [rsp+70h+var_40], rax
0x180013b9c  lea     r12, aMtxclugetvirtu_4; "MtxCluGetVirtualServersW"
0x180013ba3  mov     dword ptr [rsp+70h+var_48], edi
0x180013ba7  mov     edx, 1
0x180013bac  mov     [rsp+70h+var_50], r12
  ... truncated ...
```
