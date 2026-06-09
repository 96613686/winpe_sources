# ClearOrViewAllClusterTmMappings(int)

- ea: `0x180019c70`
- end: `0x18001a12d`
- name: `?ClearOrViewAllClusterTmMappings@@YAJH@Z`
- size: `1213`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800830c4`

## callees

- `0x1800063b0`
- `0x180019c70`
- `0x18001a134`
- `0x18001ebdc`
- `0x180023b7c`
- `0x18008353c`
- `0x1800858a4`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d7b`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180019d3f`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x180019d3f`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001a0dd`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001a0f4`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001a0dd`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001a0f4`
- `CLUSAPI!ClusterRegDeleteKey` at `0x180019f43`
- `CLUSAPI!ClusterRegDeleteKey` at `0x18001a026`
- `CLUSAPI!ClusterRegDeleteKey` at `0x180019f43`
- `CLUSAPI!ClusterRegDeleteKey` at `0x18001a026`
- `CLUSAPI!OpenClusterEx` at `0x180019d07`
- `CLUSAPI!OpenClusterEx` at `0x180019d07`
- `CLUSAPI!ClusterRegOpenKey` at `0x180019e23`
- `CLUSAPI!ClusterRegOpenKey` at `0x180019e23`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x180019e8a`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x180019e8a`
- `CLUSAPI!CloseCluster` at `0x18001a104`
- `CLUSAPI!CloseCluster` at `0x18001a104`
- `CLUSAPI!ClusterRegEnumKey` at `0x180019ec3`
- `CLUSAPI!ClusterRegEnumKey` at `0x180019ec3`
- `CLUSAPI!GetClusterKey` at `0x180019d6d`
- `CLUSAPI!GetClusterKey` at `0x180019d6d`

## string_xrefs

- `0x180019d59`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180019dac`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001a056`: `There is no TMMapping reg key to delete`
- `0x180019d45`: `OpenClusterEx failed`
- `0x180019d38`: `OpenClusterEx`
- `0x180019cea`: `Service`
- `0x180019cfc`: `ComplusApp`
- `0x180019f5d`: `DeleteTmMappingRegKey failed`

## pseudocode

```c
__int64 __fastcall ClearOrViewAllClusterTmMappings(int a1)
{
  int v1; // r14d
  struct _HCLUSTER *v2; // rax
  HKEY ClusterKey; // r13
  signed int v4; // eax
  signed int StringW; // ebx
  signed int LastError; // eax
  int i; // eax
  __int64 v8; // r14
  HKEY *v9; // r9
  unsigned __int16 *v10; // r14
  LONG v11; // eax
  DWORD v12; // r14d
  LONG v13; // eax
  wchar_t v14; // dx
  DWORD v15; // r9d
  unsigned __int16 *v16; // r14
  LONG v17; // eax
  int v18; // r14d
  __int64 j; // r14
  HKEY v20; // rcx
  DWORD cSubKeys; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h]
  int v26; // [rsp+50h] [rbp-B0h]
  HKEY *v27; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v28; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v29; // [rsp+68h] [rbp-98h]
  HCLUSTER hCluster; // [rsp+70h] [rbp-90h]
  _QWORD v31[3]; // [rsp+78h] [rbp-88h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  HKEY hKey[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h]
  WCHAR szName[256]; // [rsp+C0h] [rbp-40h] BYREF

  v23 = a1;
  v1 = a1;
  v35 = 0;
  v33 = 0;
  cSubKeys = 0;
  szName[0] = 0;
  *(_OWORD *)hKey = 0;
  *(_OWORD *)pv = 0;
  memset_0(&szName[1], 0, 0x1FCu);
  cchName = 255;
  v31[0] = L"Exe";
  v31[1] = L"Service";
  v31[2] = L"ComplusApp";
  v2 = OpenClusterEx(0, 0x2000000u, 0);
  hCluster = v2;
  if ( v2 )
  {
    ClusterKey = GetClusterKey(v2, 0x20119u);
    if ( ClusterKey )
    {
      StringW = 0;
      v26 = 0;
      for ( i = 0; ; i = v25 + 1 )
      {
        v25 = i;
        if ( i >= 3 )
          break;
        v8 = i;
        v28 = (unsigned __int16 *)v31[i];
        v29 = (unsigned __int16 **)&pv[i];
        StringW = MakeStringW(v29, L"%s\\%s", L"MSDTC\\TMMapping", v28);
        if ( StringW < 0 )
        {
          TraceStringInline(
            3,
            1,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            2913,
            L"ClearOrViewAllClusterTmMappings",
            StringW,
            L"MakeStringW failed");
          goto LABEL_50;
        }
        v9 = &hKey[v8];
        v27 = v9;
        v10 = *v29;
        if ( ClusterRegOpenKey(ClusterKey, *v29, 0x109u, v9) )
        {
          TraceStringInline(
            3,
            4,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            2921,
            L"ClearOrViewAllClusterTmMappings",
            0,
            L"ClusterRegQueryInfoKey failed. Check if the key %s mapping exists",
            v10);
        }
        else
        {
          v11 = ClusterRegQueryInfoKey(*v27, &cSubKeys, 0, 0, 0, 0, 0, 0);
          if ( v11 )
          {
            if ( v11 > 0 )
              StringW = (unsigned __int16)v11 | 0x80070000;
            else
              StringW = v11;
            TraceStringInline(
              3,
              1,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              2930,
              L"ClearOrViewAllClusterTmMappings",
              StringW,
              L"ClusterRegQueryInfoKey failed");
            goto LABEL_50;
          }
          v12 = 0;
          while ( v12 < cSubKeys )
          {
            v13 = ClusterRegEnumKey(*v27, v12, szName, &cchName, 0);
            StringW = v13;
            if ( v13 )
            {
              if ( v13 > 0 )
                StringW = (unsigned __int16)v13 | 0x80070000;
              TraceStringInline(
                3,
                1,
                L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                2941,
                L"ClearOrViewAllClusterTmMappings",
                StringW,
                L"ClusterRegEnumKey failed");
              goto LABEL_50;
            }
            if ( v23 )
            {
              StringW = DeleteTmMappingRegKey(ClusterKey, v28, szName, 0);
              if ( StringW < 0 )
              {
                TraceStringInline(
                  3,
                  1,
                  L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                  2949,
                  L"ClearOrViewAllClusterTmMappings",
                  StringW,
                  L"DeleteTmMappingRegKey failed");
                goto LABEL_50;
              }
              --cSubKeys;
            }
            else
            {
              StringW = DisplayClusterRegKeyInfo(ClusterKey, v28, szName);
              if ( StringW < 0 )
              {
                TraceStringInline(
                  3,
                  1,
                  L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                  2959,
                  L"ClearOrViewAllClusterTmMappings",
                  StringW,
                  L"DisplayClusterRegKeyInfo failed");
                goto LABEL_50;
              }
              ++v12;
            }
            v26 = 1;
            wmemset(szName, v14, 0xFFu);
            cchName = v15;
          }
          v1 = v23;
          if ( !v23 )
            continue;
          v16 = *v29;
          v17 = ClusterRegDeleteKey(ClusterKey, *v29);
          if ( v17 )
          {
            if ( v17 > 0 )
            {
              StringW = (unsigned __int16)v17 | 0x80070000;
              v17 = StringW;
            }
            else
            {
              StringW = v17;
            }
            TraceStringInline(
              3,
              1,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              2976,
              L"ClearOrViewAllClusterTmMappings",
              v17,
              L"Error occured while deleting mapping type %s reg key",
              v16);
            goto LABEL_50;
          }
        }
        v1 = v23;
      }
      if ( v1 )
      {
        v18 = ClusterRegDeleteKey(ClusterKey, L"MSDTC\\TMMapping");
        if ( v18 )
        {
          DisplayLocMessageToConsole(0x69u);
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          TraceStringInline(
            3,
            1,
            L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            2989,
            L"ClearOrViewAllClusterTmMappings",
            v18,
            L"There is no TMMapping reg key to delete");
          StringW = -2147467259;
        }
      }
      else if ( !v26 )
      {
        DisplayLocMessageToConsole(0x69u);
        StringW = -2147467259;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          3000,
          L"ClearOrViewAllClusterTmMappings",
          -2147467259,
          L"No such transaction mapping found");
      }
    }
    else
    {
      LastError = GetLastError();
      StringW = LastError;
      if ( LastError > 0 )
        StringW = (unsigned __int16)LastError | 0x80070000;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        2904,
        L"ClearOrViewAllClusterTmMappings",
        StringW,
        L"GetClusterKey failed");
    }
  }
  else
  {
    ClusterKey = 0;
    v4 = GetLastError();
    StringW = v4;
    if ( v4 > 0 )
      StringW = (unsigned __int16)v4 | 0x80070000;
    FailedClusterAPIToEventLog(L"OpenClusterEx", (unsigned int)StringW, L" ");
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      2896,
      L"ClearOrViewAllClusterTmMappings",
      StringW,
      L"OpenClusterEx failed");
  }
LABEL_50:
  for ( j = 0; j != 3; ++j )
  {
    CoTaskMemFree(pv[j]);
    v20 = hKey[j];
    if ( v20 )
      ClusterRegCloseKey(v20);
  }
  if ( ClusterKey )
    ClusterRegCloseKey(ClusterKey);
  if ( hCluster )
    CloseCluster(hCluster);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180019c70  push    rbp
0x180019c72  push    rbx
0x180019c73  push    r12
0x180019c75  push    r13
0x180019c77  push    r14
0x180019c79  push    r15
0x180019c7b  lea     rbp, [rsp-1D8h]
0x180019c83  sub     rsp, 2D8h
0x180019c8a  mov     rax, cs:__security_cookie
0x180019c91  xor     rax, rsp
0x180019c94  mov     [rbp+200h+var_40], rax
0x180019c9b  xor     eax, eax
0x180019c9d  mov     [rsp+300h+var_2BC], ecx
0x180019ca1  mov     r14d, ecx
0x180019ca4  mov     [rbp+200h+var_248], rax
0x180019ca8  xorps   xmm0, xmm0
0x180019cab  mov     [rbp+200h+var_260], rax
0x180019caf  xorps   xmm1, xmm1
0x180019cb2  mov     [rsp+300h+cSubKeys], eax
0x180019cb6  lea     rcx, [rbp+200h+var_23E]; void *
0x180019cba  mov     [rbp+200h+szName], ax
0x180019cbe  xor     edx, edx; Val
0x180019cc0  mov     r8d, 1FCh; Size
0x180019cc6  movups  xmmword ptr [rbp+200h+hKey], xmm0
0x180019cca  movups  xmmword ptr [rbp+200h+pv], xmm1
0x180019cce  call    memset_0
0x180019cd3  lea     rax, aExe; "Exe"
0x180019cda  mov     [rsp+300h+cchName], 0FFh
0x180019ce2  mov     [rsp+300h+var_288], rax
0x180019ce7  xor     r8d, r8d; GrantedAccess
0x180019cea  lea     rax, aService; "Service"
0x180019cf1  mov     edx, 2000000h; DesiredAccess
0x180019cf6  mov     [rbp+200h+var_280], rax
0x180019cfa  xor     ecx, ecx; lpszClusterName
0x180019cfc  lea     rax, aComplusapp; "ComplusApp"
0x180019d03  mov     [rbp+200h+var_278], rax
0x180019d07  call    cs:__imp_OpenClusterEx
0x180019d0d  mov     [rsp+300h+hCluster], rax
0x180019d12  test    rax, rax
0x180019d15  jnz     short loc_180019D65
0x180019d17  xor     r13d, r13d
0x180019d1a  call    cs:__imp_GetLastError
0x180019d20  mov     ebx, eax
0x180019d22  test    eax, eax
0x180019d24  jle     short loc_180019D2F
0x180019d26  movzx   ebx, ax
0x180019d29  or      ebx, 80070000h
0x180019d2f  lea     r8, asc_180127724; " "
0x180019d36  mov     edx, ebx
0x180019d38  lea     rcx, aOpenclusterex; "OpenClusterEx"
0x180019d3f  call    cs:__imp_FailedClusterAPIToEventLog
0x180019d45  lea     rax, aOpenclusterexF; "OpenClusterEx failed"
0x180019d4c  mov     r9d, 0B50h
0x180019d52  lea     r12, aClearorviewall; "ClearOrViewAllClusterTmMappings"
0x180019d59  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180019d60  jmp     loc_18001A0AA
0x180019d65  mov     edx, 20119h; samDesired
0x180019d6a  mov     rcx, rax; hCluster
0x180019d6d  call    cs:__imp_GetClusterKey
0x180019d73  mov     r13, rax
0x180019d76  test    rax, rax
0x180019d79  jnz     short loc_180019D9F
0x180019d7b  call    cs:__imp_GetLastError
0x180019d81  mov     ebx, eax
0x180019d83  test    eax, eax
0x180019d85  jle     short loc_180019D90
0x180019d87  movzx   ebx, ax
0x180019d8a  or      ebx, 80070000h
0x180019d90  lea     rax, aGetclusterkeyF; "GetClusterKey failed"
0x180019d97  mov     r9d, 0B58h
0x180019d9d  jmp     short loc_180019D52
0x180019d9f  xor     ebx, ebx
0x180019da1  lea     r12, aClearorviewall; "ClearOrViewAllClusterTmMappings"
0x180019da8  mov     [rsp+300h+var_2B0], ebx
0x180019dac  lea     r15, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180019db3  xor     eax, eax
0x180019db5  mov     [rsp+300h+var_2B4], eax
0x180019db9  cmp     eax, 3
0x180019dbc  jge     loc_18001A017
0x180019dc2  movsxd  r14, eax
0x180019dc5  lea     r8, szSubKey; "MSDTC\\TMMapping"
0x180019dcc  lea     rax, [rbp+200h+pv]
0x180019dd0  lea     rdx, aSS_1; "%s\\%s"
0x180019dd7  mov     rcx, [rsp+r14*8+300h+var_288]
0x180019ddc  lea     rax, [rax+r14*8]
0x180019de0  mov     [rsp+300h+var_2A0], rcx
0x180019de5  mov     r9, rcx
0x180019de8  mov     rcx, rax; unsigned __int16 **
0x180019deb  mov     [rsp+300h+var_298], rax
0x180019df0  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180019df5  mov     ebx, eax
0x180019df7  test    eax, eax
0x180019df9  js      loc_18001A005
0x180019dff  lea     rax, [rbp+200h+hKey]
0x180019e03  mov     r8d, 109h; samDesired
0x180019e09  lea     rax, [rax+r14*8]
0x180019e0d  mov     rcx, r13; hKey
0x180019e10  mov     r14, [rsp+300h+var_298]
0x180019e15  mov     r9, rax; phkResult
0x180019e18  mov     [rsp+300h+var_2A8], rax
0x180019e1d  mov     r14, [r14]
0x180019e20  mov     rdx, r14; lpszSubKey
0x180019e23  call    cs:__imp_ClusterRegOpenKey
0x180019e29  xor     ecx, ecx
0x180019e2b  test    eax, eax
0x180019e2d  jz      short loc_180019E63
0x180019e2f  mov     [rsp+300h+lpftLastWriteTime], r14
0x180019e34  lea     rax, aClusterregquer; "ClusterRegQueryInfoKey failed. Check if"...
0x180019e3b  mov     [rsp+300h+lpcbSecurityDescriptor], rax
0x180019e40  lea     edx, [rcx+4]
0x180019e43  mov     [rsp+300h+lpcbMaxValueLen], rcx
0x180019e48  mov     r9d, 0B69h
0x180019e4e  lea     ecx, [rdx-1]
0x180019e51  mov     [rsp+300h+lpcchMaxValueNameLen], r12
0x180019e56  mov     r8, r15
0x180019e59  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180019e5e  jmp     loc_180019F4D
0x180019e63  mov     [rsp+300h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180019e68  lea     rdx, [rsp+300h+cSubKeys]; lpcSubKeys
0x180019e6d  mov     [rsp+300h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x180019e72  xor     r9d, r9d; lpcValues
0x180019e75  mov     [rsp+300h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x180019e7a  xor     r8d, r8d; lpcchMaxSubKeyLen
0x180019e7d  mov     [rsp+300h+lpcchMaxValueNameLen], rcx; lpcchMaxValueNameLen
0x180019e82  mov     rcx, [rsp+300h+var_2A8]
0x180019e87  mov     rcx, [rcx]; hKey
0x180019e8a  call    cs:__imp_ClusterRegQueryInfoKey
0x180019e90  test    eax, eax
0x180019e92  jnz     loc_180019FE4
0x180019e98  xor     r14d, r14d
0x180019e9b  cmp     r14d, [rsp+300h+cSubKeys]
0x180019ea0  jnb     loc_180019F2B
0x180019ea6  mov     rax, [rsp+300h+var_2A8]
0x180019eab  lea     r9, [rsp+300h+cchName]; lpcchName
0x180019eb0  lea     r8, [rbp+200h+szName]; lpszName
0x180019eb4  mov     [rsp+300h+lpcchMaxValueNameLen], 0; lpftLastWriteTime
0x180019ebd  mov     edx, r14d; dwIndex
0x180019ec0  mov     rcx, [rax]; hKey
0x180019ec3  call    cs:__imp_ClusterRegEnumKey
0x180019ec9  mov     ebx, eax
0x180019ecb  test    eax, eax
0x180019ecd  jnz     loc_180019F81
0x180019ed3  lea     r8, [rbp+200h+szName]; unsigned __int16 *
0x180019ed7  mov     rdx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180019edc  mov     rcx, r13; hKey
0x180019edf  cmp     [rsp+300h+var_2BC], eax
0x180019ee3  jz      short loc_180019EF9
0x180019ee5  xor     r9d, r9d; int
0x180019ee8  call    ?DeleteTmMappingRegKey@@YAJPEAUHKEY__@@PEAG1H@Z; DeleteTmMappingRegKey(HKEY__ *,ushort *,ushort *,int)
0x180019eed  mov     ebx, eax
0x180019eef  test    eax, eax
0x180019ef1  js      short loc_180019F5D
0x180019ef3  dec     [rsp+300h+cSubKeys]
0x180019ef7  jmp     short loc_180019F07
0x180019ef9  call    ?DisplayClusterRegKeyInfo@@YAJPEAUHKEY__@@PEAG1@Z; DisplayClusterRegKeyInfo(HKEY__ *,ushort *,ushort *)
0x180019efe  mov     ebx, eax
0x180019f00  test    eax, eax
0x180019f02  js      short loc_180019F6F
0x180019f04  inc     r14d
0x180019f07  mov     r9d, 0FFh
0x180019f0d  mov     [rsp+300h+var_2B0], 1
0x180019f15  mov     r8d, r9d; N
0x180019f18  lea     rcx, [rbp+200h+szName]; S
0x180019f1c  call    wmemset
0x180019f21  mov     [rsp+300h+cchName], r9d
0x180019f26  jmp     loc_180019E9B
0x180019f2b  mov     r14d, [rsp+300h+var_2BC]
0x180019f30  test    r14d, r14d
0x180019f33  jz      short loc_180019F52
0x180019f35  mov     rax, [rsp+300h+var_298]
0x180019f3a  mov     rcx, r13; hKey
0x180019f3d  mov     r14, [rax]
0x180019f40  mov     rdx, r14; lpszSubKey
0x180019f43  call    cs:__imp_ClusterRegDeleteKey
0x180019f49  test    eax, eax
0x180019f4b  jnz     short loc_180019F9E
0x180019f4d  mov     r14d, [rsp+300h+var_2BC]
0x180019f52  mov     eax, [rsp+300h+var_2B4]
0x180019f56  inc     eax
0x180019f58  jmp     loc_180019DB5
0x180019f5d  lea     rax, aDeletetmmappin_2; "DeleteTmMappingRegKey failed"
0x180019f64  mov     r9d, 0B85h
0x180019f6a  jmp     loc_18001A0A7
0x180019f6f  lea     rax, aDisplaycluster_0; "DisplayClusterRegKeyInfo failed"
0x180019f76  mov     r9d, 0B8Fh
0x180019f7c  jmp     loc_18001A0A7
0x180019f81  jle     short loc_180019F8C
0x180019f83  movzx   ebx, ax
0x180019f86  or      ebx, 80070000h
0x180019f8c  lea     rax, aClusterregenum; "ClusterRegEnumKey failed"
0x180019f93  mov     r9d, 0B7Dh
0x180019f99  jmp     loc_18001A0A7
0x180019f9e  jg      short loc_180019FA4
0x180019fa0  mov     ebx, eax
0x180019fa2  jmp     short loc_180019FAF
0x180019fa4  movzx   ebx, ax
0x180019fa7  or      ebx, 80070000h
0x180019fad  mov     eax, ebx
0x180019faf  lea     rcx, aErrorOccuredWh; "Error occured while deleting mapping ty"...
0x180019fb6  mov     [rsp+300h+lpftLastWriteTime], r14
0x180019fbb  mov     [rsp+300h+lpcbSecurityDescriptor], rcx
0x180019fc0  mov     edx, 1
0x180019fc5  mov     dword ptr [rsp+300h+lpcbMaxValueLen], eax
0x180019fc9  mov     r9d, 0BA0h
0x180019fcf  mov     r8, r15
0x180019fd2  mov     [rsp+300h+lpcchMaxValueNameLen], r12
0x180019fd7  lea     ecx, [rdx+2]
0x180019fda  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180019fdf  jmp     loc_18001A0C5
0x180019fe4  jg      short loc_180019FEA
0x180019fe6  mov     ebx, eax
0x180019fe8  jmp     short loc_180019FF3
0x180019fea  movzx   ebx, ax
0x180019fed  or      ebx, 80070000h
0x180019ff3  lea     rax, aClusterregquer_0; "ClusterRegQueryInfoKey failed"
0x180019ffa  mov     r9d, 0B72h
0x18001a000  jmp     loc_18001A0A7
0x18001a005  lea     rax, aMakestringwFai; "MakeStringW failed"
0x18001a00c  mov     r9d, 0B61h
0x18001a012  jmp     loc_18001A0A7
0x18001a017  test    r14d, r14d
0x18001a01a  jz      short loc_18001A084
0x18001a01c  lea     rdx, szSubKey; "MSDTC\\TMMapping"
0x18001a023  mov     rcx, r13; hKey
0x18001a026  call    cs:__imp_ClusterRegDeleteKey
0x18001a02c  mov     r14d, eax
0x18001a02f  test    eax, eax
0x18001a031  jz      loc_18001A0C5
0x18001a037  mov     ecx, 69h ; 'i'; uID
0x18001a03c  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x18001a041  test    r14d, r14d
0x18001a044  jle     short loc_18001A051
0x18001a046  movzx   r14d, r14w
0x18001a04a  or      r14d, 80070000h
0x18001a051  mov     edx, 1
0x18001a056  lea     rax, aThereIsNoTmmap; "There is no TMMapping reg key to delete"
0x18001a05d  mov     [rsp+300h+lpcbSecurityDescriptor], rax
0x18001a062  mov     r9d, 0BADh
0x18001a068  mov     dword ptr [rsp+300h+lpcbMaxValueLen], r14d
0x18001a06d  mov     r8, r15
0x18001a070  mov     [rsp+300h+lpcchMaxValueNameLen], r12
0x18001a075  lea     ecx, [rdx+2]
0x18001a078  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a07d  mov     ebx, 80004005h
0x18001a082  jmp     short loc_18001A0C5
0x18001a084  cmp     [rsp+300h+var_2B0], 0
0x18001a089  jnz     short loc_18001A0C5
0x18001a08b  mov     ecx, 69h ; 'i'; uID
0x18001a090  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x18001a095  lea     rax, aNoSuchTransact; "No such transaction mapping found"
0x18001a09c  mov     r9d, 0BB8h
0x18001a0a2  mov     ebx, 80004005h
0x18001a0a7  mov     r8, r15
0x18001a0aa  mov     [rsp+300h+lpcbSecurityDescriptor], rax
0x18001a0af  mov     edx, 1
0x18001a0b4  mov     dword ptr [rsp+300h+lpcbMaxValueLen], ebx
0x18001a0b8  mov     [rsp+300h+lpcchMaxValueNameLen], r12
0x18001a0bd  lea     ecx, [rdx+2]
0x18001a0c0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a0c5  xor     r14d, r14d
0x18001a0c8  mov     rcx, [rbp+r14*8+200h+pv]; pv
0x18001a0cd  call    cs:__imp_CoTaskMemFree
0x18001a0d3  mov     rcx, [rbp+r14*8+200h+hKey]; hKey
0x18001a0d8  test    rcx, rcx
0x18001a0db  jz      short loc_18001A0E3
0x18001a0dd  call    cs:__imp_ClusterRegCloseKey
0x18001a0e3  inc     r14
0x18001a0e6  cmp     r14, 3
0x18001a0ea  jnz     short loc_18001A0C8
0x18001a0ec  test    r13, r13
0x18001a0ef  jz      short loc_18001A0FA
0x18001a0f1  mov     rcx, r13; hKey
0x18001a0f4  call    cs:__imp_ClusterRegCloseKey
0x18001a0fa  mov     rcx, [rsp+300h+hCluster]; hCluster
0x18001a0ff  test    rcx, rcx
0x18001a102  jz      short loc_18001A10A
0x18001a104  call    cs:__imp_CloseCluster
0x18001a10a  mov     eax, ebx
0x18001a10c  mov     rcx, [rbp+200h+var_40]
0x18001a113  xor     rcx, rsp; StackCookie
0x18001a116  call    __security_check_cookie
0x18001a11b  add     rsp, 2D8h
0x18001a122  pop     r15
0x18001a124  pop     r14
0x18001a126  pop     r13
0x18001a128  pop     r12
0x18001a12a  pop     rbx
0x18001a12b  pop     rbp
0x18001a12c  retn
```
