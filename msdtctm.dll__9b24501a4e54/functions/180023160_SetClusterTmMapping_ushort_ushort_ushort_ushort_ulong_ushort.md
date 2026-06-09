# SetClusterTmMapping(ushort *,ushort *,ushort *,ushort *,ulong,ushort *)

- ea: `0x180023160`
- end: `0x1800235f9`
- name: `?SetClusterTmMapping@@YAJPEAG000K0@Z`
- size: `1177`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180083214`

## callees

- `0x1800063b0`
- `0x18001a134`
- `0x18001ebdc`
- `0x180023160`
- `0x180023b7c`
- `0x1800828a0`
- `0x1800846c0`
- `0x1800858a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002327e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002327e`
- `MTXCLU!MtxCluGetClusterResourceIdFromName` at `0x180023471`
- `MTXCLU!MtxCluGetClusterResourceIdFromName` at `0x180023471`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180023225`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180023225`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800233fb`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800235bc`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800235ca`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800233fb`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800235bc`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800235ca`
- `CLUSAPI!OpenClusterEx` at `0x1800231ee`
- `CLUSAPI!OpenClusterEx` at `0x1800231ee`
- `CLUSAPI!CloseCluster` at `0x1800235d9`
- `CLUSAPI!CloseCluster` at `0x1800235d9`
- `CLUSAPI!ClusterRegCreateKey` at `0x180023330`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002342b`
- `CLUSAPI!ClusterRegCreateKey` at `0x180023330`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002342b`
- `CLUSAPI!ClusterRegSetValue` at `0x1800234b4`
- `CLUSAPI!ClusterRegSetValue` at `0x1800234fe`
- `CLUSAPI!ClusterRegSetValue` at `0x18002354d`
- `CLUSAPI!ClusterRegSetValue` at `0x1800234b4`
- `CLUSAPI!ClusterRegSetValue` at `0x1800234fe`
- `CLUSAPI!ClusterRegSetValue` at `0x18002354d`
- `CLUSAPI!GetClusterKey` at `0x180023270`
- `CLUSAPI!GetClusterKey` at `0x180023270`

## string_xrefs

- `0x180023242`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800232d8`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18002357f`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18002322b`: `OpenClusterEx failed`
- `0x18002321e`: `OpenClusterEx`
- `0x180023571`: `ClusterRegSetValue %s failed`
- `0x18002334e`: `ClusterRegCreateKey %s failed`
- `0x180023449`: `ClusterRegCreateKey %s failed`
- `0x1800231a1`: `SetClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2724): SetClusterTmMapping: NULL != pwszMappingType`
- `0x1800231b3`: `SetClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2725): SetClusterTmMapping: NULL != pwszMappingName`
- `0x1800231c5`: `SetClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2726): SetClusterTmMapping: NULL != pwszNameOrId`
- `0x1800231d7`: `SetClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@2727): SetClusterTmMapping: NULL != pwszNameOrIdValue`
- `0x1800233e3`: `Before overwriting an existing TM mapping, DeleteTmMappingRegKey() failed`

## pseudocode

```c
__int64 __fastcall SetClusterTmMapping(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int Data,
        unsigned __int16 *a6)
{
  WCHAR *v9; // r13
  struct _HCLUSTER *v10; // rax
  HKEY ClusterKey; // r15
  signed int LastError; // eax
  signed int StringW; // ebx
  const wchar_t *v14; // rax
  __int64 v15; // r9
  signed int v16; // eax
  LONG v17; // eax
  LONG v18; // eax
  __int64 v19; // rsi
  __int64 v20; // rax
  signed int v21; // eax
  signed int v22; // eax
  DWORD v23; // eax
  LPCWSTR v24; // rsi
  signed int v25; // eax
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpszSubKey; // [rsp+48h] [rbp-18h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-10h] BYREF
  HCLUSTER hCluster; // [rsp+58h] [rbp-8h]
  DWORD dwDisposition; // [rsp+A0h] [rbp+40h] BYREF
  LPCWSTR lpszValueName; // [rsp+B0h] [rbp+50h]

  lpszValueName = a3;
  hKey = 0;
  lpszSubKey = 0;
  lpData = 0;
  dwDisposition = 0;
  v9 = 0;
  if ( !a1 )
    DtcInternalErrorW(
      L"SetClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2724): SetClusterTmMapping: NULL != pwszMappingType");
  if ( !a2 )
    DtcInternalErrorW(
      L"SetClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2725): SetClusterTmMapping: NULL != pwszMappingName");
  if ( !a3 )
    DtcInternalErrorW(
      L"SetClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2726): SetClusterTmMapping: NULL != pwszNameOrId");
  if ( !a4 )
    DtcInternalErrorW(
      L"SetClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@2727): SetClusterTmMapping: NULL != pwszNameOrIdValue");
  v10 = OpenClusterEx(0, 0x2000000u, 0);
  hCluster = v10;
  if ( !v10 )
  {
    ClusterKey = 0;
    LastError = GetLastError();
    StringW = LastError;
    if ( LastError > 0 )
      StringW = (unsigned __int16)LastError | 0x80070000;
    FailedClusterAPIToEventLog(L"OpenClusterEx", (unsigned int)StringW, L" ");
    v14 = L"OpenClusterEx failed";
    v15 = 2736;
    goto LABEL_13;
  }
  ClusterKey = GetClusterKey(v10, 0x20119u);
  if ( !ClusterKey )
  {
    v16 = GetLastError();
    StringW = v16;
    if ( v16 > 0 )
      StringW = (unsigned __int16)v16 | 0x80070000;
    v14 = L"GetClusterKey failed";
    v15 = 2744;
    goto LABEL_13;
  }
  StringW = MakeStringW((unsigned __int16 **)&lpszSubKey, L"%s\\%s\\%s", L"MSDTC\\TMMapping", a1, a2);
  if ( StringW < 0 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      2751,
      L"SetClusterTmMapping",
      StringW,
      L"MakeStringW failed");
    v9 = (WCHAR *)lpszSubKey;
    goto LABEL_60;
  }
  v9 = (WCHAR *)lpszSubKey;
  v17 = ClusterRegCreateKey(ClusterKey, lpszSubKey, 0, 0xF013Fu, 0, &hKey, &dwDisposition);
  if ( v17 )
  {
    if ( v17 > 0 )
      StringW = (unsigned __int16)v17 | 0x80070000;
    else
      StringW = v17;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      2759,
      L"SetClusterTmMapping",
      StringW,
      L"ClusterRegCreateKey %s failed",
      v9);
    goto LABEL_60;
  }
  if ( dwDisposition != 2 )
    goto LABEL_39;
  DisplayLocMessageToConsole(0x68u);
  StringW = DisplayClusterRegKeyInfo(ClusterKey, a1, a2);
  if ( StringW < 0 )
  {
    v14 = L"DisplayClusterRegKeyInfo failed";
    v15 = 2771;
LABEL_13:
    TraceStringInline(3, 1, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", v15, L"SetClusterTmMapping", StringW, v14);
    goto LABEL_60;
  }
  DisplayLocMessageToConsole(0x6Au);
  if ( !(unsigned int)GetUserResponseFromCmdLine() )
  {
    DisplayLocMessageToConsole(0x6Eu);
    StringW = -2147467259;
    goto LABEL_60;
  }
  StringW = DeleteTmMappingRegKey(ClusterKey, a1, a2, 1);
  if ( StringW < 0 )
  {
    v14 = L"Before overwriting an existing TM mapping, DeleteTmMappingRegKey() failed";
    v15 = 2791;
    goto LABEL_13;
  }
  if ( hKey )
  {
    ClusterRegCloseKey(hKey);
    hKey = 0;
  }
  v18 = ClusterRegCreateKey(ClusterKey, v9, 0, 0xF013Fu, 0, &hKey, &dwDisposition);
  if ( v18 )
  {
    if ( v18 > 0 )
      StringW = (unsigned __int16)v18 | 0x80070000;
    else
      StringW = v18;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      2806,
      L"SetClusterTmMapping",
      StringW,
      L"ClusterRegCreateKey %s failed",
      v9);
  }
  else
  {
LABEL_39:
    v19 = -1;
    if ( !a6 )
      goto LABEL_49;
    StringW = MtxCluGetClusterResourceIdFromName(0, a6, &lpData);
    if ( StringW < 0 )
    {
      v14 = L"GetResourceID failed";
      v15 = 2821;
      goto LABEL_13;
    }
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&lpData[2 * v20] );
    v21 = ClusterRegSetValue(hKey, L"ClusterResourceId", 1u, lpData, 2 * v20);
    if ( v21 )
    {
      if ( v21 > 0 )
        StringW = (unsigned __int16)v21 | 0x80070000;
      else
        StringW = v21;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        2829,
        L"SetClusterTmMapping",
        StringW,
        L"ClusterRegSetValue %s failed",
        L"ClusterResource");
    }
    else
    {
LABEL_49:
      v22 = ClusterRegSetValue(hKey, L"ApplicationType", 4u, (const BYTE *)&Data, 4u);
      if ( v22 )
      {
        if ( v22 > 0 )
          StringW = (unsigned __int16)v22 | 0x80070000;
        else
          StringW = v22;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          2839,
          L"SetClusterTmMapping",
          StringW,
          L"ClusterRegSetValue %s failed",
          L"ApplicationType");
      }
      else
      {
        do
          ++v19;
        while ( *(_WORD *)&a4[2 * v19] );
        v23 = 2 * v19;
        v24 = lpszValueName;
        v25 = ClusterRegSetValue(hKey, lpszValueName, 1u, a4, v23);
        if ( v25 )
        {
          if ( v25 > 0 )
            StringW = (unsigned __int16)v25 | 0x80070000;
          else
            StringW = v25;
          TraceStringInline(
            3,
            1,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            2847,
            L"SetClusterTmMapping",
            StringW,
            L"ClusterRegSetValue %s failed",
            v24);
        }
      }
    }
  }
LABEL_60:
  CoTaskMemFree(v9);
  CoTaskMemFree(lpData);
  if ( hKey )
    ClusterRegCloseKey(hKey);
  if ( ClusterKey )
    ClusterRegCloseKey(ClusterKey);
  if ( hCluster )
    CloseCluster(hCluster);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180023160  mov     [rsp-38h+arg_8], rbx
0x180023165  mov     [rsp-38h+lpszValueName], r8
0x18002316a  push    rbp
0x18002316b  push    rsi
0x18002316c  push    rdi
0x18002316d  push    r12
0x18002316f  push    r13
0x180023171  push    r14
0x180023173  push    r15
0x180023175  mov     rbp, rsp
0x180023178  sub     rsp, 60h
0x18002317c  xor     edi, edi
0x18002317e  mov     r12, r9
0x180023181  mov     [rbp+hKey], rdi
0x180023185  mov     rax, r8
0x180023188  mov     [rbp+lpszSubKey], rdi
0x18002318c  mov     rsi, rdx
0x18002318f  mov     [rbp+lpData], rdi
0x180023193  mov     r14, rcx
0x180023196  mov     [rbp+dwDisposition], edi
0x180023199  mov     r13d, edi
0x18002319c  test    rcx, rcx
0x18002319f  jnz     short loc_1800231AE
0x1800231a1  lea     rcx, aSetclustertmma_2; "SetClusterTmMapping (com\\complus\\dtc"...
0x1800231a8  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800231ae  test    rsi, rsi
0x1800231b1  jnz     short loc_1800231C0
0x1800231b3  lea     rcx, aSetclustertmma_1; "SetClusterTmMapping (com\\complus\\dtc"...
0x1800231ba  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800231c0  test    rax, rax
0x1800231c3  jnz     short loc_1800231D2
0x1800231c5  lea     rcx, aSetclustertmma; "SetClusterTmMapping (com\\complus\\dtc"...
0x1800231cc  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800231d2  test    r12, r12
0x1800231d5  jnz     short loc_1800231E4
0x1800231d7  lea     rcx, aSetclustertmma_0; "SetClusterTmMapping (com\\complus\\dtc"...
0x1800231de  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800231e4  xor     r8d, r8d; GrantedAccess
0x1800231e7  mov     edx, 2000000h; DesiredAccess
0x1800231ec  xor     ecx, ecx; lpszClusterName
0x1800231ee  call    cs:__imp_OpenClusterEx
0x1800231f4  mov     [rbp+hCluster], rax
0x1800231f8  test    rax, rax
0x1800231fb  jnz     short loc_180023268
0x1800231fd  mov     r15, rdi
0x180023200  call    cs:__imp_GetLastError
0x180023206  mov     ebx, eax
0x180023208  test    eax, eax
0x18002320a  jle     short loc_180023215
0x18002320c  movzx   ebx, ax
0x18002320f  or      ebx, 80070000h
0x180023215  lea     r8, asc_180127724; " "
0x18002321c  mov     edx, ebx
0x18002321e  lea     rcx, aOpenclusterex; "OpenClusterEx"
0x180023225  call    cs:__imp_FailedClusterAPIToEventLog
0x18002322b  lea     rax, aOpenclusterexF; "OpenClusterEx failed"
0x180023232  mov     r9d, 0AB0h
0x180023238  mov     edx, 1
0x18002323d  mov     [rsp+60h+lpdwDisposition], rax
0x180023242  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180023249  lea     rax, aSetclustertmma_3; "SetClusterTmMapping"
0x180023250  mov     dword ptr [rsp+60h+phkResult], ebx
0x180023254  mov     ecx, 3
0x180023259  mov     [rsp+60h+lpSecurityAttributes], rax
0x18002325e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180023263  jmp     loc_1800235A0
0x180023268  mov     edx, 20119h; samDesired
0x18002326d  mov     rcx, rax; hCluster
0x180023270  call    cs:__imp_GetClusterKey
0x180023276  mov     r15, rax
0x180023279  test    rax, rax
0x18002327c  jnz     short loc_1800232A2
0x18002327e  call    cs:__imp_GetLastError
0x180023284  mov     ebx, eax
0x180023286  test    eax, eax
0x180023288  jle     short loc_180023293
0x18002328a  movzx   ebx, ax
0x18002328d  or      ebx, 80070000h
0x180023293  lea     rax, aGetclusterkeyF; "GetClusterKey failed"
0x18002329a  mov     r9d, 0AB8h
0x1800232a0  jmp     short loc_180023238
0x1800232a2  mov     r9, r14
0x1800232a5  mov     [rsp+60h+lpSecurityAttributes], rsi
0x1800232aa  lea     r8, szSubKey; "MSDTC\\TMMapping"
0x1800232b1  lea     rdx, aSSS; "%s\\%s\\%s"
0x1800232b8  lea     rcx, [rbp+lpszSubKey]; unsigned __int16 **
0x1800232bc  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800232c1  mov     ebx, eax
0x1800232c3  test    eax, eax
0x1800232c5  jns     short loc_180023306
0x1800232c7  mov     edx, 1
0x1800232cc  lea     rax, aMakestringwFai; "MakeStringW failed"
0x1800232d3  mov     [rsp+60h+lpdwDisposition], rax
0x1800232d8  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800232df  lea     rax, aSetclustertmma_3; "SetClusterTmMapping"
0x1800232e6  mov     dword ptr [rsp+60h+phkResult], ebx
0x1800232ea  mov     r9d, 0ABFh
0x1800232f0  mov     [rsp+60h+lpSecurityAttributes], rax
0x1800232f5  lea     ecx, [rdx+2]
0x1800232f8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800232fd  mov     r13, [rbp+lpszSubKey]
0x180023301  jmp     loc_1800235A0
0x180023306  mov     r13, [rbp+lpszSubKey]
0x18002330a  lea     rax, [rbp+dwDisposition]
0x18002330e  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180023313  mov     r9d, 0F013Fh; samDesired
0x180023319  lea     rax, [rbp+hKey]
0x18002331d  xor     r8d, r8d; dwOptions
0x180023320  mov     [rsp+60h+phkResult], rax; phkResult
0x180023325  mov     rdx, r13; lpszSubKey
0x180023328  mov     rcx, r15; hKey
0x18002332b  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180023330  call    cs:__imp_ClusterRegCreateKey
0x180023336  test    eax, eax
0x180023338  jz      short loc_180023365
0x18002333a  jg      short loc_180023340
0x18002333c  mov     ebx, eax
0x18002333e  jmp     short loc_180023349
0x180023340  movzx   ebx, ax
0x180023343  or      ebx, 80070000h
0x180023349  mov     [rsp+60h+var_28], r13
0x18002334e  lea     rax, aClusterregcrea; "ClusterRegCreateKey %s failed"
0x180023355  mov     r9d, 0AC7h
0x18002335b  mov     edx, 1
0x180023360  jmp     loc_18002357A
0x180023365  cmp     [rbp+dwDisposition], 2
0x180023369  mov     edi, 1
0x18002336e  jnz     loc_18002345B
0x180023374  lea     ecx, [rdi+67h]; uID
0x180023377  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x18002337c  mov     r8, rsi; unsigned __int16 *
0x18002337f  mov     rdx, r14; unsigned __int16 *
0x180023382  mov     rcx, r15; hKey
0x180023385  call    ?DisplayClusterRegKeyInfo@@YAJPEAUHKEY__@@PEAG1@Z; DisplayClusterRegKeyInfo(HKEY__ *,ushort *,ushort *)
0x18002338a  mov     ebx, eax
0x18002338c  test    eax, eax
0x18002338e  jns     short loc_1800233A4
0x180023390  lea     rax, aDisplaycluster_0; "DisplayClusterRegKeyInfo failed"
0x180023397  mov     r9d, 0AD3h
0x18002339d  mov     edx, edi
0x18002339f  jmp     loc_18002323D
0x1800233a4  mov     ecx, 6Ah ; 'j'; uID
0x1800233a9  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x1800233ae  call    ?GetUserResponseFromCmdLine@@YAHXZ; GetUserResponseFromCmdLine(void)
0x1800233b3  test    eax, eax
0x1800233b5  jnz     short loc_1800233C9
0x1800233b7  lea     ecx, [rax+6Eh]; uID
0x1800233ba  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x1800233bf  mov     ebx, 80004005h
0x1800233c4  jmp     loc_1800235A0
0x1800233c9  mov     r9d, edi; int
0x1800233cc  mov     r8, rsi; unsigned __int16 *
0x1800233cf  mov     rdx, r14; unsigned __int16 *
0x1800233d2  mov     rcx, r15; hKey
0x1800233d5  call    ?DeleteTmMappingRegKey@@YAJPEAUHKEY__@@PEAG1H@Z; DeleteTmMappingRegKey(HKEY__ *,ushort *,ushort *,int)
0x1800233da  xor     r14d, r14d
0x1800233dd  mov     ebx, eax
0x1800233df  test    eax, eax
0x1800233e1  jns     short loc_1800233F2
0x1800233e3  lea     rax, aBeforeOverwrit; "Before overwriting an existing TM mappi"...
0x1800233ea  mov     r9d, 0AE7h
0x1800233f0  jmp     short loc_18002339D
0x1800233f2  mov     rcx, [rbp+hKey]; hKey
0x1800233f6  test    rcx, rcx
0x1800233f9  jz      short loc_180023405
0x1800233fb  call    cs:__imp_ClusterRegCloseKey
0x180023401  mov     [rbp+hKey], r14
0x180023405  lea     rax, [rbp+dwDisposition]
0x180023409  mov     r9d, 0F013Fh; samDesired
0x18002340f  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180023414  xor     r8d, r8d; dwOptions
0x180023417  lea     rax, [rbp+hKey]
0x18002341b  mov     rdx, r13; lpszSubKey
0x18002341e  mov     [rsp+60h+phkResult], rax; phkResult
0x180023423  mov     rcx, r15; hKey
0x180023426  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002342b  call    cs:__imp_ClusterRegCreateKey
0x180023431  test    eax, eax
0x180023433  jz      short loc_18002345E
0x180023435  jg      short loc_18002343B
0x180023437  mov     ebx, eax
0x180023439  jmp     short loc_180023444
0x18002343b  movzx   ebx, ax
0x18002343e  or      ebx, 80070000h
0x180023444  mov     [rsp+60h+var_28], r13
0x180023449  lea     rax, aClusterregcrea; "ClusterRegCreateKey %s failed"
0x180023450  mov     r9d, 0AF6h
0x180023456  jmp     loc_180023578
0x18002345b  xor     r14d, r14d
0x18002345e  mov     rdx, [rbp+arg_28]
0x180023462  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023466  test    rdx, rdx
0x180023469  jz      short loc_1800234E4
0x18002346b  lea     r8, [rbp+lpData]
0x18002346f  xor     ecx, ecx
0x180023471  call    cs:__imp_MtxCluGetClusterResourceIdFromName
0x180023477  mov     ebx, eax
0x180023479  test    eax, eax
0x18002347b  jns     short loc_18002348F
0x18002347d  lea     rax, aGetresourceidF; "GetResourceID failed"
0x180023484  mov     r9d, 0B05h
0x18002348a  jmp     loc_18002339D
0x18002348f  mov     r9, [rbp+lpData]; lpData
0x180023493  mov     rax, rsi
0x180023496  inc     rax
0x180023499  cmp     [r9+rax*2], r14w
0x18002349e  jnz     short loc_180023496
0x1800234a0  mov     rcx, [rbp+hKey]; hKey
0x1800234a4  lea     rdx, aClusterresourc_1; "ClusterResourceId"
0x1800234ab  add     eax, eax
0x1800234ad  mov     r8d, edi; dwType
0x1800234b0  mov     dword ptr [rsp+60h+lpSecurityAttributes], eax; cbData
0x1800234b4  call    cs:__imp_ClusterRegSetValue
0x1800234ba  test    eax, eax
0x1800234bc  jz      short loc_1800234E4
0x1800234be  jg      short loc_1800234C4
0x1800234c0  mov     ebx, eax
0x1800234c2  jmp     short loc_1800234CD
0x1800234c4  movzx   ebx, ax
0x1800234c7  or      ebx, 80070000h
0x1800234cd  lea     rax, aClusterresourc_2; "ClusterResource"
0x1800234d4  mov     r9d, 0B0Dh
0x1800234da  mov     [rsp+60h+var_28], rax
0x1800234df  jmp     loc_180023571
0x1800234e4  mov     rcx, [rbp+hKey]; hKey
0x1800234e8  lea     r9, [rbp+Data]; lpData
0x1800234ec  mov     r8d, 4; dwType
0x1800234f2  lea     rdx, aApplicationtyp; "ApplicationType"
0x1800234f9  mov     dword ptr [rsp+60h+lpSecurityAttributes], r8d; cbData
0x1800234fe  call    cs:__imp_ClusterRegSetValue
0x180023504  test    eax, eax
0x180023506  jz      short loc_18002352B
0x180023508  jg      short loc_18002350E
0x18002350a  mov     ebx, eax
0x18002350c  jmp     short loc_180023517
0x18002350e  movzx   ebx, ax
0x180023511  or      ebx, 80070000h
0x180023517  lea     rax, aApplicationtyp; "ApplicationType"
0x18002351e  mov     r9d, 0B17h
0x180023524  mov     [rsp+60h+var_28], rax
0x180023529  jmp     short loc_180023571
0x18002352b  inc     rsi
0x18002352e  cmp     [r12+rsi*2], r14w
0x180023533  jnz     short loc_18002352B
0x180023535  mov     rcx, [rbp+hKey]; hKey
0x180023539  lea     eax, [rsi+rsi]
0x18002353c  mov     rsi, [rbp+lpszValueName]
0x180023540  mov     r9, r12; lpData
0x180023543  mov     rdx, rsi; lpszValueName
0x180023546  mov     dword ptr [rsp+60h+lpSecurityAttributes], eax; cbData
0x18002354a  mov     r8d, edi; dwType
0x18002354d  call    cs:__imp_ClusterRegSetValue
0x180023553  test    eax, eax
0x180023555  jz      short loc_1800235A0
0x180023557  jg      short loc_18002355D
0x180023559  mov     ebx, eax
0x18002355b  jmp     short loc_180023566
0x18002355d  movzx   ebx, ax
0x180023560  or      ebx, 80070000h
0x180023566  mov     [rsp+60h+var_28], rsi
0x18002356b  mov     r9d, 0B1Fh
0x180023571  lea     rax, aClusterregsetv; "ClusterRegSetValue %s failed"
0x180023578  mov     edx, edi
0x18002357a  mov     [rsp+60h+lpdwDisposition], rax
0x18002357f  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180023586  lea     rax, aSetclustertmma_3; "SetClusterTmMapping"
0x18002358d  mov     dword ptr [rsp+60h+phkResult], ebx
0x180023591  mov     ecx, 3
0x180023596  mov     [rsp+60h+lpSecurityAttributes], rax
0x18002359b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800235a0  mov     rcx, r13; pv
0x1800235a3  call    cs:__imp_CoTaskMemFree
0x1800235a9  mov     rcx, [rbp+lpData]; pv
0x1800235ad  call    cs:__imp_CoTaskMemFree
0x1800235b3  mov     rcx, [rbp+hKey]; hKey
0x1800235b7  test    rcx, rcx
0x1800235ba  jz      short loc_1800235C2
0x1800235bc  call    cs:__imp_ClusterRegCloseKey
0x1800235c2  test    r15, r15
0x1800235c5  jz      short loc_1800235D0
0x1800235c7  mov     rcx, r15; hKey
0x1800235ca  call    cs:__imp_ClusterRegCloseKey
0x1800235d0  mov     rcx, [rbp+hCluster]; hCluster
0x1800235d4  test    rcx, rcx
0x1800235d7  jz      short loc_1800235DF
0x1800235d9  call    cs:__imp_CloseCluster
0x1800235df  mov     eax, ebx
0x1800235e1  mov     rbx, [rsp+60h+arg_8]
0x1800235e9  add     rsp, 60h
0x1800235ed  pop     r15
0x1800235ef  pop     r14
0x1800235f1  pop     r13
0x1800235f3  pop     r12
0x1800235f5  pop     rdi
0x1800235f6  pop     rsi
0x1800235f7  pop     rbp
0x1800235f8  retn
```
