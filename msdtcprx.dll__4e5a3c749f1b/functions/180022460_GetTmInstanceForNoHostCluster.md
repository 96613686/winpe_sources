# GetTmInstanceForNoHostCluster

- ea: `0x180022460`
- end: `0x1800227fd`
- name: `GetTmInstanceForNoHostCluster`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018098`

## callees

- `0x180003cf0`
- `0x180006214`
- `0x18000d5f4`
- `0x180022460`
- `0x180022928`
- `0x180081d92`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227d9`
- `RPCRT4!UuidEqual` at `0x1800225c7`
- `RPCRT4!UuidEqual` at `0x1800225c7`
- `RPCRT4!UuidFromStringW` at `0x180022568`
- `RPCRT4!UuidFromStringW` at `0x180022568`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x180022687`
- `MTXCLU!MtxCluCreateClusterProxyTmInstance` at `0x180022687`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x18002253a`
- `MTXCLU!MtxCluGetDefaultClusterResourceNonAdmin` at `0x18002253a`

## string_xrefs

- `0x180022504`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x1800225a7`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180022653`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180022705`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x1800226b6`: `CreateLocalTmInstance failed`
- `0x180022730`: `CreateLocalTmInstance failed`
- `0x180022693`: `MtxCluCreateClusterProxyTmInstance failed`
- `0x1800224b3`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1098): GetTmInstanceForNoHostCluster - NULL != o_ppTmInstance`
- `0x1800224c5`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1099): GetTmInstanceForNoHostCluster - NULL != o_ppLocalTmInstance`
- `0x180022629`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1170): GetTmInstanceForNoHostCluster - NULL != wszVirtualServerName`
- `0x1800226db`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1196): GetTmInstanceForNoHost - NULL == wszVirtualServerName`
- `0x180022762`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1211): GetTmInstanceForNoHostCluster - NULL != pTmInstance`
- `0x180022774`: `GetTmInstanceForNoHostCluster (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@1212): GetTmInstanceForNoHostCluster - NULL != pLocalTmInstance`

## pseudocode

```c
__int64 __fastcall GetTmInstanceForNoHostCluster(char *a1, char a2, struct ITmInstance **a3, struct ITmInstance **a4)
{
  int TmInstanceInfoFromTm; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // r9
  RPC_STATUS v10; // eax
  __int64 v11; // r9
  const wchar_t *v12; // rax
  int v13; // eax
  struct ITmInstance *v14; // rax
  struct ITmInstance *v15; // rcx
  __int64 v17; // [rsp+28h] [rbp-51h]
  RPC_STATUS v18; // [rsp+38h] [rbp-41h]
  struct ITmInstance *v19; // [rsp+40h] [rbp-39h] BYREF
  RPC_STATUS Status; // [rsp+48h] [rbp-31h] BYREF
  struct ITmInstance *v21; // [rsp+50h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-21h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-19h] BYREF
  LPVOID v24; // [rsp+68h] [rbp-11h] BYREF
  UUID Uuid2; // [rsp+70h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+80h] [rbp+7h] BYREF

  pv = 0;
  v24 = 0;
  StringUuid = 0;
  v19 = 0;
  v21 = 0;
  Uuid2 = GUID_NULL;
  if ( !a3 )
    DtcInternalErrorW(
      L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1098): GetTmInstanceForNoHo"
       "stCluster - NULL != o_ppTmInstance");
  if ( !a4 )
    DtcInternalErrorW(
      L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1099): GetTmInstanceForNoHo"
       "stCluster - NULL != o_ppLocalTmInstance");
  *a3 = 0;
  *a4 = 0;
  TmInstanceInfoFromTm = GetTmInstanceInfoFromTm(a1, a2, &Uuid2, (unsigned __int16 **)&pv);
  if ( TmInstanceInfoFromTm < 0 )
  {
    v8 = L"GetTmInstanceInfoFromTm failed";
    v9 = 1113;
LABEL_7:
    LODWORD(v17) = TmInstanceInfoFromTm;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      v9,
      L"GetTmInstanceForNoHostCluster",
      v17,
      v8);
    goto LABEL_36;
  }
  if ( (a2 & 2) != 0 )
  {
    TmInstanceInfoFromTm = MtxCluGetDefaultClusterResourceNonAdmin(0, &StringUuid, &v24);
    if ( TmInstanceInfoFromTm < 0 )
    {
      v8 = L"MtxCluGetDefaultClusterResourceNonAdmin failed";
      v9 = 1130;
      goto LABEL_7;
    }
    Uuid = 0;
    v10 = UuidFromStringW(StringUuid, &Uuid);
    Status = v10;
    if ( v10 )
    {
      v18 = v10;
      v11 = 1141;
      v12 = L"UuidFromStringW failed: RPC error = %d";
LABEL_13:
      LODWORD(v17) = -2147467259;
      TmInstanceInfoFromTm = -2147467259;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
        v11,
        L"GetTmInstanceForNoHostCluster",
        v17,
        v12,
        v18);
      goto LABEL_36;
    }
    v13 = UuidEqual(&Uuid, &Uuid2, &Status);
    if ( Status )
    {
      v18 = Status;
      v12 = L"UuidEqual failed: RPC error = %d";
      v11 = 1154;
      goto LABEL_13;
    }
    if ( !v13 )
    {
      TmInstanceInfoFromTm = -2147168229;
      v8 = L"GetTmInstanceInfoFromTm does not match the default TM instance when OLE_TM_FLAG_NOAGILERECOVERY is set";
      v9 = 1161;
      goto LABEL_7;
    }
  }
  if ( !memcmp_0(&GUID_NULL, &Uuid2, 0x10u) )
  {
    if ( pv )
      DtcInternalErrorW(
        L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1196): GetTmInstanceForNo"
         "Host - NULL == wszVirtualServerName");
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      1198,
      L"GetTmInstanceForNoHostCluster",
      0,
      L"The response from the TM indicates that we should use the LOCAL TM");
    TmInstanceInfoFromTm = CreateLocalTmInstance(0, &v19);
    if ( TmInstanceInfoFromTm < 0 )
    {
      v8 = L"CreateLocalTmInstance failed";
      v9 = 1203;
      goto LABEL_7;
    }
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v19 + 8LL))(v19);
    v14 = v19;
    v15 = v19;
    v21 = v19;
  }
  else
  {
    if ( !pv )
      DtcInternalErrorW(
        L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1170): GetTmInstanceForNo"
         "HostCluster - NULL != wszVirtualServerName");
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
      1172,
      L"GetTmInstanceForNoHostCluster",
      0,
      L"The response from the TM indicates that we should use TM with Virtual Server Name %s",
      pv);
    Uuid = Uuid2;
    TmInstanceInfoFromTm = MtxCluCreateClusterProxyTmInstance(pv, &Uuid, &v19);
    if ( TmInstanceInfoFromTm < 0 )
    {
      v8 = L"MtxCluCreateClusterProxyTmInstance failed";
      v9 = 1181;
      goto LABEL_7;
    }
    TmInstanceInfoFromTm = CreateLocalTmInstance(0, &v21);
    if ( TmInstanceInfoFromTm < 0 )
    {
      v8 = L"CreateLocalTmInstance failed";
      v9 = 1190;
      goto LABEL_7;
    }
    v14 = v19;
    v15 = v21;
  }
  if ( !v14 )
    DtcInternalErrorW(
      L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1211): GetTmInstanceForNoHo"
       "stCluster - NULL != pTmInstance");
  if ( !v15 )
    DtcInternalErrorW(
      L"GetTmInstanceForNoHostCluster (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@1212): GetTmInstanceForNoHo"
       "stCluster - NULL != pLocalTmInstance");
  *a3 = v14;
  *a4 = v15;
  v19 = 0;
  v21 = 0;
LABEL_36:
  if ( v19 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v24);
  CoTaskMemFree(StringUuid);
  return (unsigned int)TmInstanceInfoFromTm;
}

```

## disassembly

```asm
0x180022460  push    rbp
0x180022462  push    rbx
0x180022463  push    rsi
0x180022464  push    rdi
0x180022465  push    r14
0x180022467  push    r15
0x180022469  lea     rbp, [rsp-2Fh]
0x18002246e  sub     rsp, 0A8h
0x180022475  mov     rax, cs:__security_cookie
0x18002247c  xor     rax, rsp
0x18002247f  mov     [rbp+57h+var_40], rax
0x180022483  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002248a  xor     r15d, r15d
0x18002248d  mov     rsi, r9
0x180022490  mov     [rbp+57h+pv], r15
0x180022494  mov     r14, r8
0x180022497  mov     [rbp+57h+var_68], r15
0x18002249b  mov     edi, edx
0x18002249d  mov     [rbp+57h+StringUuid], r15
0x1800224a1  mov     [rbp+57h+var_90], r15
0x1800224a5  mov     [rbp+57h+var_80], r15
0x1800224a9  movdqu  xmmword ptr [rbp+57h+Uuid2.Data1], xmm0
0x1800224ae  test    r8, r8
0x1800224b1  jnz     short loc_1800224C0
0x1800224b3  lea     rcx, aGettminstancef_3; "GetTmInstanceForNoHostCluster (com\\com"...
0x1800224ba  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800224c0  test    rsi, rsi
0x1800224c3  jnz     short loc_1800224D2
0x1800224c5  lea     rcx, aGettminstancef_16; "GetTmInstanceForNoHostCluster (com\\com"...
0x1800224cc  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800224d2  mov     [r8], r15
0x1800224d5  lea     r8, [rbp+57h+Uuid2]; struct _GUID *
0x1800224d9  mov     [r9], r15
0x1800224dc  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x1800224e0  call    ?GetTmInstanceInfoFromTm@@YAJPEAXKPEAU_GUID@@PEAPEAG@Z; GetTmInstanceInfoFromTm(void *,ulong,_GUID *,ushort * *)
0x1800224e5  mov     ebx, eax
0x1800224e7  test    eax, eax
0x1800224e9  jns     short loc_180022526
0x1800224eb  lea     rax, aGettminstancei_0; "GetTmInstanceInfoFromTm failed"
0x1800224f2  mov     r9d, 459h
0x1800224f8  lea     rdi, aGettminstancef_5; "GetTmInstanceForNoHostCluster"
0x1800224ff  mov     [rsp+0D0h+var_A0], rax
0x180022504  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18002250b  mov     edx, 1
0x180022510  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x180022514  mov     [rsp+0D0h+var_B0], rdi
0x180022519  lea     ecx, [rdx+0Eh]
0x18002251c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022521  jmp     loc_18002278F
0x180022526  test    dil, 2
0x18002252a  jz      loc_180022602
0x180022530  lea     r8, [rbp+57h+var_68]
0x180022534  xor     ecx, ecx
0x180022536  lea     rdx, [rbp+57h+StringUuid]
0x18002253a  call    cs:__imp_MtxCluGetDefaultClusterResourceNonAdmin
0x180022540  mov     ebx, eax
0x180022542  test    eax, eax
0x180022544  jns     short loc_180022555
0x180022546  lea     rax, aMtxclugetdefau_3; "MtxCluGetDefaultClusterResourceNonAdmin"...
0x18002254d  mov     r9d, 46Ah
0x180022553  jmp     short loc_1800224F8
0x180022555  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x180022559  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002255d  xorps   xmm0, xmm0
0x180022560  mov     [rbp+57h+Status], r15d
0x180022564  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180022568  call    cs:__imp_UuidFromStringW
0x18002256e  mov     [rbp+57h+Status], eax
0x180022571  test    eax, eax
0x180022573  jz      short loc_1800225BB
0x180022575  mov     dword ptr [rsp+0D0h+var_98], eax
0x180022579  mov     r9d, 475h
0x18002257f  lea     rax, aUuidfromstring; "UuidFromStringW failed: RPC error = %d"
0x180022586  mov     ecx, 80004005h
0x18002258b  mov     [rsp+0D0h+var_A0], rax
0x180022590  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x180022594  lea     rdi, aGettminstancef_5; "GetTmInstanceForNoHostCluster"
0x18002259b  mov     edx, 1
0x1800225a0  mov     [rsp+0D0h+var_B0], rdi
0x1800225a5  mov     ebx, ecx
0x1800225a7  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800225ae  lea     ecx, [rdx+0Eh]
0x1800225b1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800225b6  jmp     loc_18002278F
0x1800225bb  lea     r8, [rbp+57h+Status]; Status
0x1800225bf  lea     rdx, [rbp+57h+Uuid2]; Uuid2
0x1800225c3  lea     rcx, [rbp+57h+Uuid]; Uuid1
0x1800225c7  call    cs:__imp_UuidEqual
0x1800225cd  mov     edx, [rbp+57h+Status]
0x1800225d0  test    edx, edx
0x1800225d2  jz      short loc_1800225E7
0x1800225d4  mov     dword ptr [rsp+0D0h+var_98], edx
0x1800225d8  lea     rax, aUuidequalFaile; "UuidEqual failed: RPC error = %d"
0x1800225df  mov     r9d, 482h
0x1800225e5  jmp     short loc_180022586
0x1800225e7  test    eax, eax
0x1800225e9  jnz     short loc_180022602
0x1800225eb  mov     ebx, 8004D01Bh
0x1800225f0  lea     rax, aGettminstancei_1; "GetTmInstanceInfoFromTm does not match "...
0x1800225f7  mov     r9d, 489h
0x1800225fd  jmp     loc_1800224F8
0x180022602  mov     r8d, 10h; Size
0x180022608  lea     rdx, [rbp+57h+Uuid2]; Buf2
0x18002260c  lea     rcx, GUID_NULL; Buf1
0x180022613  call    memcmp_0
0x180022618  test    eax, eax
0x18002261a  jz      loc_1800226D5
0x180022620  mov     rax, [rbp+57h+pv]
0x180022624  test    rax, rax
0x180022627  jnz     short loc_180022636
0x180022629  lea     rcx, aGettminstancef_11; "GetTmInstanceForNoHostCluster (com\\com"...
0x180022630  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180022636  mov     [rsp+0D0h+var_98], rax
0x18002263b  lea     rdi, aGettminstancef_5; "GetTmInstanceForNoHostCluster"
0x180022642  mov     edx, 4
0x180022647  lea     rax, aTheResponseFro_0; "The response from the TM indicates that"...
0x18002264e  mov     [rsp+0D0h+var_A0], rax
0x180022653  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18002265a  mov     [rsp+0D0h+var_A8], r15
0x18002265f  mov     r9d, 494h
0x180022665  mov     [rsp+0D0h+var_B0], rdi
0x18002266a  lea     ecx, [rdx+0Bh]
0x18002266d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180022672  movaps  xmm0, xmmword ptr [rbp+57h+Uuid2.Data1]
0x180022676  lea     r8, [rbp+57h+var_90]
0x18002267a  mov     rcx, [rbp+57h+pv]
0x18002267e  lea     rdx, [rbp+57h+Uuid]
0x180022682  movdqa  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180022687  call    cs:__imp_MtxCluCreateClusterProxyTmInstance
0x18002268d  mov     ebx, eax
0x18002268f  test    eax, eax
0x180022691  jns     short loc_1800226A5
0x180022693  lea     rax, aMtxclucreatecl_0; "MtxCluCreateClusterProxyTmInstance fail"...
0x18002269a  mov     r9d, 49Dh
0x1800226a0  jmp     loc_1800224FF
0x1800226a5  lea     rdx, [rbp+57h+var_80]; struct ITmInstance **
0x1800226a9  xor     ecx, ecx; unsigned __int16 *
0x1800226ab  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x1800226b0  mov     ebx, eax
0x1800226b2  test    eax, eax
0x1800226b4  jns     short loc_1800226C8
0x1800226b6  lea     rax, aCreatelocaltmi_1; "CreateLocalTmInstance failed"
0x1800226bd  mov     r9d, 4A6h
0x1800226c3  jmp     loc_1800224FF
0x1800226c8  mov     rax, [rbp+57h+var_90]
0x1800226cc  mov     rcx, [rbp+57h+var_80]
0x1800226d0  jmp     loc_18002275D
0x1800226d5  cmp     [rbp+57h+pv], r15
0x1800226d9  jz      short loc_1800226E8
0x1800226db  lea     rcx, aGettminstancef_4; "GetTmInstanceForNoHostCluster (com\\com"...
0x1800226e2  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800226e8  mov     edx, 4
0x1800226ed  lea     rax, aTheResponseFro; "The response from the TM indicates that"...
0x1800226f4  mov     [rsp+0D0h+var_A0], rax
0x1800226f9  lea     rdi, aGettminstancef_5; "GetTmInstanceForNoHostCluster"
0x180022700  mov     [rsp+0D0h+var_A8], r15
0x180022705  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18002270c  mov     r9d, 4AEh
0x180022712  mov     [rsp+0D0h+var_B0], rdi
0x180022717  lea     ecx, [rdx+0Bh]
0x18002271a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002271f  lea     rdx, [rbp+57h+var_90]; struct ITmInstance **
0x180022723  xor     ecx, ecx; unsigned __int16 *
0x180022725  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x18002272a  mov     ebx, eax
0x18002272c  test    eax, eax
0x18002272e  jns     short loc_180022742
0x180022730  lea     rax, aCreatelocaltmi_1; "CreateLocalTmInstance failed"
0x180022737  mov     r9d, 4B3h
0x18002273d  jmp     loc_1800224FF
0x180022742  mov     rcx, [rbp+57h+var_90]
0x180022746  mov     rax, [rcx]
0x180022749  mov     rax, [rax+8]
0x18002274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022752  mov     rax, [rbp+57h+var_90]
0x180022756  mov     rcx, rax
0x180022759  mov     [rbp+57h+var_80], rax
0x18002275d  test    rax, rax
0x180022760  jnz     short loc_18002276F
0x180022762  lea     rcx, aGettminstancef_13; "GetTmInstanceForNoHostCluster (com\\com"...
0x180022769  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002276f  test    rcx, rcx
0x180022772  jnz     short loc_180022781
0x180022774  lea     rcx, aGettminstancef_19; "GetTmInstanceForNoHostCluster (com\\com"...
0x18002277b  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180022781  mov     [r14], rax
0x180022784  mov     [rsi], rcx
0x180022787  mov     [rbp+57h+var_90], r15
0x18002278b  mov     [rbp+57h+var_80], r15
0x18002278f  mov     rcx, [rbp+57h+var_90]
0x180022793  test    rcx, rcx
0x180022796  jz      short loc_1800227A8
0x180022798  mov     rax, [rcx]
0x18002279b  mov     rax, [rax+10h]
0x18002279f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a4  mov     [rbp+57h+var_90], r15
0x1800227a8  mov     rcx, [rbp+57h+var_80]
0x1800227ac  test    rcx, rcx
0x1800227af  jz      short loc_1800227C1
0x1800227b1  mov     rax, [rcx]
0x1800227b4  mov     rax, [rax+10h]
0x1800227b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227bd  mov     [rbp+57h+var_80], r15
0x1800227c1  mov     rcx, [rbp+57h+pv]; pv
0x1800227c5  call    cs:__imp_CoTaskMemFree
0x1800227cb  mov     rcx, [rbp+57h+var_68]; pv
0x1800227cf  call    cs:__imp_CoTaskMemFree
0x1800227d5  mov     rcx, [rbp+57h+StringUuid]; pv
0x1800227d9  call    cs:__imp_CoTaskMemFree
0x1800227df  mov     eax, ebx
0x1800227e1  mov     rcx, [rbp+57h+var_40]
0x1800227e5  xor     rcx, rsp; StackCookie
0x1800227e8  call    __security_check_cookie
0x1800227ed  add     rsp, 0A8h
0x1800227f4  pop     r15
0x1800227f6  pop     r14
0x1800227f8  pop     rdi
0x1800227f9  pop     rsi
0x1800227fa  pop     rbx
0x1800227fb  pop     rbp
0x1800227fc  retn
```
