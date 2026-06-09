# MtxCluGetNodesW(ushort * * *,ulong *)

- ea: `0x180018188`
- end: `0x180018613`
- name: `?MtxCluGetNodesW@@YAJPEAPEAPEAGPEAK@Z`
- size: `1163`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800722c4`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x1800092f4`
- `0x18000d5f4`
- `0x18000f8d0`
- `0x18001156c`
- `0x180018188`
- `0x18007198c`
- `0x180081d9e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800183ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018245`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001837b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001837b`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x1800183e4`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x1800183e4`
- `CLUSAPI!ClusterEnum` at `0x180018522`
- `CLUSAPI!ClusterEnum` at `0x180018522`
- `CLUSAPI!ClusterOpenEnum` at `0x180018369`
- `CLUSAPI!ClusterOpenEnum` at `0x180018369`
- `CLUSAPI!ClusterGetEnumCount` at `0x180018440`
- `CLUSAPI!ClusterGetEnumCount` at `0x180018440`

## string_xrefs

- `0x1800181e8`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800183ba`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180018471`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x180018566`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800185bc`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x1800181b8`: `MtxCluGetNodesW (com\complus\dtc\shared\util\clusterutilbasic.cpp@778): MtxCluGetNodesW, ppClusterNodes != NULL`
- `0x1800181ca`: `MtxCluGetNodesW (com\complus\dtc\shared\util\clusterutilbasic.cpp@779): MtxCluGetNodesW, pdwClusterNodes != NULL`
- `0x180018253`: `MtxCluGetNodesW, CoTaskMemAlloc(dwClusterNodes*LPWSTR) failed`
- `0x180018465`: `MtxCluGetNodesW, CoTaskMemAlloc(dwClusterNodes*LPWSTR) failed`
- `0x18001832d`: `ClusterOpenEnum - CLUSTER_ENUM_NODE`
- `0x1800183db`: `ClusterOpenEnum`
- `0x1800183f3`: `MtxCluGetNodesW, ClusterOpenEnum failed`

## pseudocode

```c
__int64 __fastcall MtxCluGetNodesW(unsigned __int16 ***a1, unsigned int *a2)
{
  signed int PhysicalNodeNameW; // edi
  _QWORD *v5; // rax
  void *v6; // rsi
  unsigned int v7; // r15d
  int i; // ebx
  __int64 j; // r14
  LPVOID *v10; // r12
  struct _HCLUSTER *LocalClusterHandle; // rbx
  signed int LastError; // eax
  const wchar_t *v13; // rax
  __int64 v14; // r9
  struct _HCLUSENUM *v15; // rax
  struct _HCLUSENUM *v16; // r14
  signed int v17; // eax
  int StringW; // eax
  void *v19; // rbx
  DWORD EnumCount; // eax
  SIZE_T v21; // rbx
  void *v22; // rax
  __int64 k; // rbx
  LPVOID v24; // rax
  __int64 m; // rbx
  signed int v26; // eax
  __int64 v28; // [rsp+28h] [rbp-60h]
  DWORD dwType[18]; // [rsp+40h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+A8h] [rbp+20h] BYREF

  dwType[0] = 0;
  cchName = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"MtxCluGetNodesW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@778): MtxCluGetNodesW, ppClusterNodes != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"MtxCluGetNodesW (com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp@779): MtxCluGetNodesW, pdwClusterNodes != NULL");
  PhysicalNodeNameW = 0;
  TraceStringInline(7, 6, L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp", 781, L"MtxCluGetNodesW", 0, L"In");
  *a1 = 0;
  *a2 = 0;
  LOBYTE(pv) = 0;
  MtxCluIsClusterPresentNonAdmin(0, (bool *)&pv);
  if ( !(_BYTE)pv )
  {
    v5 = CoTaskMemAlloc(8u);
    v6 = v5;
    if ( !v5 )
    {
      LODWORD(v28) = -2147024882;
      PhysicalNodeNameW = -2147024882;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        794,
        L"MtxCluGetNodesW",
        v28,
        L"MtxCluGetNodesW, CoTaskMemAlloc(dwClusterNodes*LPWSTR) failed");
LABEL_46:
      CoTaskMemFree(v6);
      v6 = 0;
      v7 = 0;
      goto LABEL_48;
    }
    *v5 = 0;
    v7 = 1;
    for ( i = 0; !i; i = 1 )
    {
      PhysicalNodeNameW = GetPhysicalNodeNameW((unsigned __int16 **)v6);
      if ( PhysicalNodeNameW < 0 )
      {
        LODWORD(v28) = PhysicalNodeNameW;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
          807,
          L"MtxCluGetNodesW",
          v28,
          L"MtxCluGetNodesW, GetPhysicalNodeNameW failed.");
        j = 0;
        v10 = (LPVOID *)v6;
        goto LABEL_45;
      }
    }
    goto LABEL_24;
  }
  v6 = 0;
  v7 = 0;
  LocalClusterHandle = GetLocalClusterHandle();
  if ( !LocalClusterHandle )
  {
    LastError = GetLastError();
    PhysicalNodeNameW = LastError;
    if ( LastError > 0 )
      PhysicalNodeNameW = (unsigned __int16)LastError | 0x80070000;
    v13 = L"GetLocalClusterHandle failed";
    v14 = 818;
LABEL_23:
    LODWORD(v28) = PhysicalNodeNameW;
    TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp", v14, L"MtxCluGetNodesW", v28, v13);
LABEL_24:
    if ( PhysicalNodeNameW < 0 )
    {
      v10 = (LPVOID *)v6;
      if ( v6 )
      {
LABEL_44:
        for ( j = 0; (unsigned int)j < v7; j = (unsigned int)(j + 1) )
        {
LABEL_45:
          CoTaskMemFree(v10[j]);
          v10[j] = 0;
        }
      }
      goto LABEL_46;
    }
    goto LABEL_48;
  }
  TraceStringInline(
    7,
    4,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    822,
    L"MtxCluGetNodesW",
    0,
    L"ClusterOpenEnum - CLUSTER_ENUM_NODE");
  v15 = ClusterOpenEnum(LocalClusterHandle, 1u);
  v16 = v15;
  if ( !v15 )
  {
    v17 = GetLastError();
    PhysicalNodeNameW = v17;
    if ( v17 > 0 )
      PhysicalNodeNameW = (unsigned __int16)v17 | 0x80070000;
    pv = 0;
    StringW = MakeStringW((unsigned __int16 **)&pv, L"hCluster: %x dwType: %d", LocalClusterHandle, 1);
    v19 = pv;
    if ( StringW >= 0 )
      TraceFileW(
        PhysicalNodeNameW,
        (unsigned __int16 *)pv,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        0x342u);
    FailedClusterAPIToEventLog(L"ClusterOpenEnum", (unsigned int)PhysicalNodeNameW, v19);
    CoTaskMemFree(v19);
    v13 = L"MtxCluGetNodesW, ClusterOpenEnum failed";
    v14 = 840;
    goto LABEL_23;
  }
  EnumCount = ClusterGetEnumCount(v15);
  v21 = 8LL * EnumCount;
  v7 = EnumCount;
  v22 = CoTaskMemAlloc(v21);
  v6 = v22;
  if ( !v22 )
  {
    LODWORD(v28) = -2147024882;
    PhysicalNodeNameW = -2147024882;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      850,
      L"MtxCluGetNodesW",
      v28,
      L"MtxCluGetNodesW, CoTaskMemAlloc(dwClusterNodes*LPWSTR) failed");
    goto LABEL_46;
  }
  v10 = (LPVOID *)v22;
  if ( v7 )
    memset_0(v22, 0, v21 & 0xFFFFFFFFFFFFFFF8uLL);
  for ( k = 0; (unsigned int)k < v7; k = (unsigned int)(k + 1) )
  {
    v24 = CoTaskMemAlloc(0x202u);
    *((_QWORD *)v6 + k) = v24;
    if ( !v24 )
    {
      PhysicalNodeNameW = -2147024882;
      LODWORD(v28) = -2147024882;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        863,
        L"MtxCluGetNodesW",
        v28,
        L"MtxCluGetNodesW, unable to allocate space for node names.");
      goto LABEL_44;
    }
  }
  for ( m = 0; (unsigned int)m < v7; m = (unsigned int)(m + 1) )
  {
    cchName = 257;
    v26 = ClusterEnum(v16, m, dwType, *((LPWSTR *)v6 + m), &cchName);
    PhysicalNodeNameW = v26;
    if ( v26 > 0 )
      PhysicalNodeNameW = (unsigned __int16)v26 | 0x80070000;
    if ( PhysicalNodeNameW == -2147024637 )
    {
      PhysicalNodeNameW = 0;
      break;
    }
    if ( PhysicalNodeNameW < 0 )
    {
      LODWORD(v28) = PhysicalNodeNameW;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
        885,
        L"MtxCluGetNodesW",
        v28,
        L"MtxCluGetNodesW, ClusterEnum failed");
      goto LABEL_44;
    }
  }
LABEL_48:
  *a2 = v7;
  *a1 = (unsigned __int16 **)v6;
  LODWORD(v28) = PhysicalNodeNameW;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
    911,
    L"MtxCluGetNodesW",
    v28,
    L"Out");
  return (unsigned int)PhysicalNodeNameW;
}

```

## disassembly

```asm
0x180018188  mov     rax, rsp
0x18001818b  mov     [rax+10h], rbx
0x18001818f  mov     [rax+8], rcx
0x180018193  push    rbp
0x180018194  push    rsi
0x180018195  push    rdi
0x180018196  push    r12
0x180018198  push    r13
0x18001819a  push    r14
0x18001819c  push    r15
0x18001819e  sub     rsp, 50h
0x1800181a2  xor     r12d, r12d
0x1800181a5  mov     r13, rdx
0x1800181a8  mov     [rax-48h], r12d
0x1800181ac  mov     rbx, rcx
0x1800181af  mov     [rax+20h], r12d
0x1800181b3  test    rcx, rcx
0x1800181b6  jnz     short loc_1800181C5
0x1800181b8  lea     rcx, aMtxclugetnodes_3; "MtxCluGetNodesW (com\\complus\\dtc\\sha"...
0x1800181bf  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800181c5  test    r13, r13
0x1800181c8  jnz     short loc_1800181D7
0x1800181ca  lea     rcx, aMtxclugetnodes; "MtxCluGetNodesW (com\\complus\\dtc\\sha"...
0x1800181d1  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800181d7  mov     edx, 6
0x1800181dc  lea     rax, aIn_0; "In"
0x1800181e3  mov     [rsp+88h+var_58], rax
0x1800181e8  lea     r14, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800181ef  lea     r15, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x1800181f6  mov     [rsp+88h+var_60], r12
0x1800181fb  mov     r9d, 30Dh
0x180018201  mov     [rsp+88h+lpcchName], r15
0x180018206  lea     ebp, [rdx+1]
0x180018209  mov     r8, r14
0x18001820c  mov     ecx, ebp
0x18001820e  mov     edi, r12d
0x180018211  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180018216  lea     rdx, [rsp+88h+pv]; bool *
0x18001821e  mov     [rbx], r12
0x180018221  xor     ecx, ecx; unsigned __int16 *
0x180018223  mov     [r13+0], r12d
0x180018227  mov     byte ptr [rsp+88h+pv], r12b
0x18001822f  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180018234  cmp     byte ptr [rsp+88h+pv], r12b
0x18001823c  jnz     loc_1800182EE
0x180018242  lea     ecx, [rbp+1]; cb
0x180018245  call    cs:__imp_CoTaskMemAlloc
0x18001824b  mov     rsi, rax
0x18001824e  test    rax, rax
0x180018251  jnz     short loc_180018287
0x180018253  lea     rcx, aMtxclugetnodes_6; "MtxCluGetNodesW, CoTaskMemAlloc(dwClust"...
0x18001825a  mov     eax, 8007000Eh
0x18001825f  mov     [rsp+88h+var_58], rcx
0x180018264  lea     edx, [rbp-6]
0x180018267  mov     dword ptr [rsp+88h+var_60], eax
0x18001826b  mov     edi, eax
0x18001826d  mov     [rsp+88h+lpcchName], r15
0x180018272  mov     r9d, 31Ah
0x180018278  mov     r8, r14
0x18001827b  mov     ecx, ebp
0x18001827d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180018282  jmp     loc_1800185A1
0x180018287  mov     ebp, 1
0x18001828c  mov     [rax], r12
0x18001828f  mov     r15d, ebp
0x180018292  mov     ebx, r12d
0x180018295  cmp     ebx, ebp
0x180018297  jnb     loc_180018424
0x18001829d  mov     eax, ebx
0x18001829f  lea     rcx, [rsi+rax*8]; unsigned __int16 **
0x1800182a3  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x1800182a8  mov     edi, eax
0x1800182aa  test    eax, eax
0x1800182ac  js      short loc_1800182B2
0x1800182ae  add     ebx, ebp
0x1800182b0  jmp     short loc_180018295
0x1800182b2  lea     rax, aMtxclugetnodes_1; "MtxCluGetNodesW, GetPhysicalNodeNameW f"...
0x1800182b9  mov     r9d, 327h
0x1800182bf  mov     [rsp+88h+var_58], rax
0x1800182c4  mov     r8, r14
0x1800182c7  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x1800182ce  mov     dword ptr [rsp+88h+var_60], edi
0x1800182d2  mov     edx, ebp
0x1800182d4  mov     [rsp+88h+lpcchName], rax
0x1800182d9  mov     ecx, 7
0x1800182de  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800182e3  xor     r14d, r14d
0x1800182e6  mov     r12, rsi
0x1800182e9  jmp     loc_180018584
0x1800182ee  mov     rsi, r12
0x1800182f1  mov     r15d, r12d
0x1800182f4  call    ?GetLocalClusterHandle@@YAPEAU_HCLUSTER@@XZ; GetLocalClusterHandle(void)
0x1800182f9  mov     rbx, rax
0x1800182fc  test    rax, rax
0x1800182ff  jnz     short loc_18001832D
0x180018301  call    cs:__imp_GetLastError
0x180018307  mov     edi, eax
0x180018309  test    eax, eax
0x18001830b  jle     short loc_180018316
0x18001830d  movzx   edi, ax
0x180018310  or      edi, 80070000h
0x180018316  lea     rax, aGetlocalcluste; "GetLocalClusterHandle failed"
0x18001831d  mov     r9d, 332h
0x180018323  mov     ebp, 1
0x180018328  jmp     loc_180018400
0x18001832d  lea     rax, aClusteropenenu; "ClusterOpenEnum - CLUSTER_ENUM_NODE"
0x180018334  mov     r9d, 336h
0x18001833a  mov     [rsp+88h+var_58], rax
0x18001833f  mov     r8, r14
0x180018342  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x180018349  mov     [rsp+88h+var_60], r12
0x18001834e  mov     edx, 4
0x180018353  mov     [rsp+88h+lpcchName], rax
0x180018358  mov     ecx, ebp
0x18001835a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001835f  mov     ebp, 1
0x180018364  mov     rcx, rbx; hCluster
0x180018367  mov     edx, ebp; dwType
0x180018369  call    cs:__imp_ClusterOpenEnum
0x18001836f  mov     r14, rax
0x180018372  test    rax, rax
0x180018375  jnz     loc_18001843D
0x18001837b  call    cs:__imp_GetLastError
0x180018381  mov     edi, eax
0x180018383  test    eax, eax
0x180018385  jle     short loc_180018390
0x180018387  movzx   edi, ax
0x18001838a  or      edi, 80070000h
0x180018390  mov     r9d, ebp
0x180018393  mov     [rsp+88h+pv], r12
0x18001839b  mov     r8, rbx
0x18001839e  lea     rdx, aHclusterXDwtyp; "hCluster: %x dwType: %d"
0x1800183a5  lea     rcx, [rsp+88h+pv]; unsigned __int16 **
0x1800183ad  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800183b2  mov     rbx, [rsp+88h+pv]
0x1800183ba  lea     r14, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800183c1  test    eax, eax
0x1800183c3  js      short loc_1800183D8
0x1800183c5  mov     r9d, 342h; unsigned int
0x1800183cb  mov     r8, r14; unsigned __int16 *
0x1800183ce  mov     rdx, rbx; unsigned __int16 *
0x1800183d1  mov     ecx, edi; int
0x1800183d3  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800183d8  mov     r8, rbx
0x1800183db  lea     rcx, aClusteropenenu_0; "ClusterOpenEnum"
0x1800183e2  mov     edx, edi
0x1800183e4  call    cs:__imp_FailedClusterAPIToEventLog
0x1800183ea  mov     rcx, rbx; pv
0x1800183ed  call    cs:__imp_CoTaskMemFree
0x1800183f3  lea     rax, aMtxclugetnodes_4; "MtxCluGetNodesW, ClusterOpenEnum failed"
0x1800183fa  mov     r9d, 348h
0x180018400  mov     [rsp+88h+var_58], rax
0x180018405  mov     r8, r14
0x180018408  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x18001840f  mov     dword ptr [rsp+88h+var_60], edi
0x180018413  mov     edx, ebp
0x180018415  mov     [rsp+88h+lpcchName], rax
0x18001841a  mov     ecx, 7
0x18001841f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180018424  test    edi, edi
0x180018426  jns     loc_1800185B4
0x18001842c  mov     r12, rsi
0x18001842f  test    rsi, rsi
0x180018432  jz      loc_18001859E
0x180018438  jmp     loc_18001857C
0x18001843d  mov     rcx, r14; hEnum
0x180018440  call    cs:__imp_ClusterGetEnumCount
0x180018446  mov     ebx, eax
0x180018448  shl     rbx, 3
0x18001844c  mov     rcx, rbx; cb
0x18001844f  mov     r15d, eax
0x180018452  call    cs:__imp_CoTaskMemAlloc
0x180018458  mov     rsi, rax
0x18001845b  test    rax, rax
0x18001845e  jnz     short loc_18001849A
0x180018460  mov     eax, 8007000Eh
0x180018465  lea     rcx, aMtxclugetnodes_6; "MtxCluGetNodesW, CoTaskMemAlloc(dwClust"...
0x18001846c  mov     [rsp+88h+var_58], rcx
0x180018471  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180018478  mov     dword ptr [rsp+88h+var_60], eax
0x18001847c  lea     ecx, [rsi+7]
0x18001847f  mov     edi, eax
0x180018481  mov     r9d, 352h
0x180018487  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x18001848e  mov     edx, ebp
0x180018490  mov     [rsp+88h+lpcchName], rax
0x180018495  jmp     loc_18001827D
0x18001849a  mov     r12, rsi
0x18001849d  test    r15d, r15d
0x1800184a0  jz      short loc_1800184B3
0x1800184a2  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1800184a6  xor     edx, edx; Val
0x1800184a8  mov     r8, rbx; Size
0x1800184ab  mov     rcx, rsi; void *
0x1800184ae  call    memset_0
0x1800184b3  xor     ebx, ebx
0x1800184b5  cmp     ebx, r15d
0x1800184b8  jnb     short loc_1800184F1
0x1800184ba  mov     ecx, 202h; cb
0x1800184bf  call    cs:__imp_CoTaskMemAlloc
0x1800184c5  mov     [rsi+rbx*8], rax
0x1800184c9  test    rax, rax
0x1800184cc  jz      short loc_1800184D2
0x1800184ce  add     ebx, ebp
0x1800184d0  jmp     short loc_1800184B5
0x1800184d2  mov     eax, 8007000Eh
0x1800184d7  lea     rcx, aMtxclugetnodes_0; "MtxCluGetNodesW, unable to allocate spa"...
0x1800184de  mov     [rsp+88h+var_58], rcx
0x1800184e3  mov     edi, eax
0x1800184e5  mov     dword ptr [rsp+88h+var_60], eax
0x1800184e9  mov     r9d, 35Fh
0x1800184ef  jmp     short loc_18001855D
0x1800184f1  xor     ebx, ebx
0x1800184f3  cmp     ebx, r15d
0x1800184f6  jnb     loc_1800185B4
0x1800184fc  mov     [rsp+88h+cchName], 101h
0x180018507  lea     rax, [rsp+88h+cchName]
0x18001850f  mov     r9, [rsi+rbx*8]; lpszName
0x180018513  lea     r8, [rsp+88h+dwType]; lpdwType
0x180018518  mov     edx, ebx; dwIndex
0x18001851a  mov     [rsp+88h+lpcchName], rax; lpcchName
0x18001851f  mov     rcx, r14; hEnum
0x180018522  call    cs:__imp_ClusterEnum
0x180018528  mov     edi, eax
0x18001852a  test    eax, eax
0x18001852c  jle     short loc_180018537
0x18001852e  movzx   edi, ax
0x180018531  or      edi, 80070000h
0x180018537  cmp     edi, 80070103h
0x18001853d  jz      short loc_1800185B2
0x18001853f  test    edi, edi
0x180018541  js      short loc_180018547
0x180018543  add     ebx, ebp
0x180018545  jmp     short loc_1800184F3
0x180018547  lea     rax, aMtxclugetnodes_2; "MtxCluGetNodesW, ClusterEnum failed"
0x18001854e  mov     r9d, 375h
0x180018554  mov     [rsp+88h+var_58], rax
0x180018559  mov     dword ptr [rsp+88h+var_60], edi
0x18001855d  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x180018564  mov     edx, ebp
0x180018566  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x18001856d  mov     [rsp+88h+lpcchName], rax
0x180018572  mov     ecx, 7
0x180018577  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001857c  xor     r14d, r14d
0x18001857f  test    r15d, r15d
0x180018582  jz      short loc_18001859E
0x180018584  mov     rcx, [r12+r14*8]; pv
0x180018588  call    cs:__imp_CoTaskMemFree
0x18001858e  mov     qword ptr [r12+r14*8], 0
0x180018596  add     r14d, ebp
0x180018599  cmp     r14d, r15d
0x18001859c  jb      short loc_180018584
0x18001859e  xor     r12d, r12d
0x1800185a1  mov     rcx, rsi; pv
0x1800185a4  call    cs:__imp_CoTaskMemFree
0x1800185aa  mov     rsi, r12
0x1800185ad  mov     r15d, r12d
0x1800185b0  jmp     short loc_1800185B4
0x1800185b2  xor     edi, edi
0x1800185b4  mov     rax, [rsp+88h+arg_0]
0x1800185bc  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\util\\cluste"...
0x1800185c3  mov     edx, 6
0x1800185c8  mov     [r13+0], r15d
0x1800185cc  mov     r9d, 38Fh
0x1800185d2  mov     [rax], rsi
0x1800185d5  lea     rax, aOut; "Out"
0x1800185dc  mov     [rsp+88h+var_58], rax
0x1800185e1  lea     ecx, [rdx+1]
0x1800185e4  lea     rax, aMtxclugetnodes_5; "MtxCluGetNodesW"
0x1800185eb  mov     dword ptr [rsp+88h+var_60], edi
0x1800185ef  mov     [rsp+88h+lpcchName], rax
0x1800185f4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800185f9  mov     rbx, [rsp+88h+arg_8]
0x180018601  mov     eax, edi
0x180018603  add     rsp, 50h
0x180018607  pop     r15
0x180018609  pop     r14
0x18001860b  pop     r13
0x18001860d  pop     r12
0x18001860f  pop     rdi
0x180018610  pop     rsi
0x180018611  pop     rbp
0x180018612  retn
```
