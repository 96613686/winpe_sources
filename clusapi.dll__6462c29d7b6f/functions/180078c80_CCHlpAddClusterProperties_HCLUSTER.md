# CCHlpAddClusterProperties(_HCLUSTER *)

- ea: `0x180078c80`
- end: `0x180078e8c`
- name: `?CCHlpAddClusterProperties@@YAXPEAU_HCLUSTER@@@Z`
- size: `524`
- prototype: `void __fastcall(HCLUSTER hCluster)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003359c`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18003180c`
- `0x180063cb0`
- `0x180064f20`
- `0x180065190`
- `0x18006f910`
- `0x180078c80`
- `0x18009f6fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180078d32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180078d32`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180078d42`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180078d42`

## string_xrefs

- `0x180078cf6`: `Security Descriptor`
- `0x180078d85`: `CCHlpAddClusterProperties failed to write RecentEventsResetTime property - status = %d`
- `0x180078db3`: `CCHlpAddClusterProperties failed to write default cluster security descriptor - status = %d`
- `0x180078df4`: `CCHlpAddClusterProperties failed to open root key - status = %d`
- `0x180078e28`: `CCHlpAddClusterProperties failed to create default cluster security descriptor - status = %d`

## pseudocode

```c
void __fastcall CCHlpAddClusterProperties(HCLUSTER hCluster)
{
  DWORD v2; // eax
  DWORD LastError; // ebx
  HKEY ClusterKey; // rax
  HKEY v5; // rsi
  DWORD v6; // eax
  DWORD v7; // eax
  wchar_t *v8; // [rsp+28h] [rbp-D8h]
  wchar_t *v9; // [rsp+28h] [rbp-D8h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+50h] [rbp-B0h] BYREF

  hMem = 0;
  FileTime.dwLowDateTime = 0;
  v2 = ClRtlBuildDefaultClusterApiSD((__int64)hCluster, &hMem, (DWORD *)&FileTime);
  LastError = v2;
  if ( v2 )
  {
    TraceMsg(
      2u,
      0,
      (__int64)L"CCHlpAddClusterProperties",
      1024,
      L"CCHlpAddClusterProperties failed to create default cluster security descriptor - status = %d",
      v2);
  }
  else
  {
    ClusterKey = GetClusterKey(hCluster, 2u);
    v5 = ClusterKey;
    if ( ClusterKey )
    {
      v6 = ClusterRegSetValueEx(
             (int)ClusterKey,
             (int)L"Security Descriptor",
             LastError + 3,
             (int)hMem,
             FileTime.dwLowDateTime,
             0);
      LastError = v6;
      if ( v6 )
      {
        LODWORD(v8) = v6;
        TraceMsg(
          2u,
          0,
          (__int64)L"CCHlpAddClusterProperties",
          1009,
          L"CCHlpAddClusterProperties failed to write default cluster security descriptor - status = %d",
          v8);
      }
      else
      {
        FileTime = 0;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
        {
          v7 = ClusterRegSetValueEx((int)v5, (int)L"RecentEventsResetTime", LastError + 11, (int)&FileTime, 8, 0);
          LastError = v7;
          if ( v7 )
          {
            LODWORD(v9) = v7;
            TraceMsg(
              2u,
              0,
              (__int64)L"CCHlpAddClusterProperties",
              998,
              L"CCHlpAddClusterProperties failed to write RecentEventsResetTime property - status = %d",
              v9);
          }
        }
        else
        {
          LastError = GetLastError();
          LODWORD(v8) = LastError;
          TraceMsg(
            2u,
            0,
            (__int64)L"CCHlpAddClusterProperties",
            1004,
            L"CCHlpAddClusterProperties failed to convert system time to file time - status = %d",
            v8);
        }
      }
      ClusterRegCloseKeyCommon(v5, 1);
    }
    else
    {
      LastError = GetLastError();
      TraceMsg(
        2u,
        0,
        (__int64)L"CCHlpAddClusterProperties",
        1017,
        L"CCHlpAddClusterProperties failed to open root key - status = %d",
        LastError);
    }
    LocalFree(hMem);
  }
  if ( LastError )
  {
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      LastError,
      L"Failed to add cluster level properties.");
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180078c80  mov     [rsp-8+arg_8], rbx
0x180078c85  mov     [rsp-8+arg_10], rsi
0x180078c8a  push    rbp
0x180078c8b  lea     rbp, [rsp-70h]
0x180078c90  sub     rsp, 170h
0x180078c97  mov     rax, cs:__security_cookie
0x180078c9e  xor     rax, rsp
0x180078ca1  mov     [rbp+70h+var_10], rax
0x180078ca5  lea     r8, [rsp+170h+FileTime]
0x180078caa  mov     [rsp+170h+hMem], 0
0x180078cb3  lea     rdx, [rsp+170h+hMem]
0x180078cb8  mov     [rsp+170h+FileTime.dwLowDateTime], 0
0x180078cc0  mov     rsi, rcx
0x180078cc3  call    ClRtlBuildDefaultClusterApiSD
0x180078cc8  mov     ebx, eax
0x180078cca  test    eax, eax
0x180078ccc  jnz     loc_180078E1B
0x180078cd2  lea     edx, [rax+2]; samDesired
0x180078cd5  mov     rcx, rsi; hCluster
0x180078cd8  call    GetClusterKey
0x180078cdd  mov     rsi, rax
0x180078ce0  test    rax, rax
0x180078ce3  jz      loc_180078DDF
0x180078ce9  mov     ecx, [rsp+170h+FileTime.dwLowDateTime]
0x180078ced  lea     r8d, [rbx+3]; int
0x180078cf1  mov     r9, [rsp+170h+hMem]; int
0x180078cf6  lea     rdx, aSecurityDescri; "Security Descriptor"
0x180078cfd  mov     [rsp+170h+var_148], 0; wchar_t *
0x180078d06  mov     [rsp+170h+var_150], ecx; int
0x180078d0a  mov     rcx, rax; int
0x180078d0d  call    ClusterRegSetValueEx
0x180078d12  mov     ebx, eax
0x180078d14  test    eax, eax
0x180078d16  jnz     loc_180078DA9
0x180078d1c  xorps   xmm0, xmm0
0x180078d1f  mov     qword ptr [rsp+170h+FileTime.dwLowDateTime], 0
0x180078d28  lea     rcx, [rsp+170h+SystemTime]; lpSystemTime
0x180078d2d  movups  xmmword ptr [rsp+170h+SystemTime.wYear], xmm0
0x180078d32  call    cs:__imp_GetSystemTime
0x180078d38  lea     rdx, [rsp+170h+FileTime]; lpFileTime
0x180078d3d  lea     rcx, [rsp+170h+SystemTime]; lpSystemTime
0x180078d42  call    cs:__imp_SystemTimeToFileTime
0x180078d48  test    eax, eax
0x180078d4a  jz      short loc_180078D8E
0x180078d4c  mov     [rsp+170h+var_148], 0; wchar_t *
0x180078d55  lea     r9, [rsp+170h+FileTime]; int
0x180078d5a  lea     r8d, [rbx+0Bh]; int
0x180078d5e  mov     [rsp+170h+var_150], 8; int
0x180078d66  lea     rdx, aRecenteventsre; "RecentEventsResetTime"
0x180078d6d  mov     rcx, rsi; int
0x180078d70  call    ClusterRegSetValueEx
0x180078d75  mov     ebx, eax
0x180078d77  test    eax, eax
0x180078d79  jz      short loc_180078DD0
0x180078d7b  mov     dword ptr [rsp+170h+var_148], eax
0x180078d7f  mov     r9d, 3E6h
0x180078d85  lea     rax, aCchlpaddcluste_1; "CCHlpAddClusterProperties failed to wri"...
0x180078d8c  jmp     short loc_180078DBA
0x180078d8e  call    cs:__imp_GetLastError
0x180078d94  mov     ebx, eax
0x180078d96  mov     dword ptr [rsp+170h+var_148], eax
0x180078d9a  lea     rax, aCchlpaddcluste_3; "CCHlpAddClusterProperties failed to con"...
0x180078da1  mov     r9d, 3ECh
0x180078da7  jmp     short loc_180078DBA
0x180078da9  mov     dword ptr [rsp+170h+var_148], eax
0x180078dad  mov     r9d, 3F1h
0x180078db3  lea     rax, aCchlpaddcluste; "CCHlpAddClusterProperties failed to wri"...
0x180078dba  xor     edx, edx
0x180078dbc  mov     qword ptr [rsp+170h+var_150], rax
0x180078dc1  lea     r8, aCchlpaddcluste_0; "CCHlpAddClusterProperties"
0x180078dc8  lea     ecx, [rdx+2]
0x180078dcb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180078dd0  mov     edx, 1; int
0x180078dd5  mov     rcx, rsi; HKEY
0x180078dd8  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180078ddd  jmp     short loc_180078E0E
0x180078ddf  call    cs:__imp_GetLastError
0x180078de5  mov     dword ptr [rsp+170h+var_148], eax
0x180078de9  xor     edx, edx
0x180078deb  mov     ebx, eax
0x180078ded  lea     r8, aCchlpaddcluste_0; "CCHlpAddClusterProperties"
0x180078df4  lea     rax, aCchlpaddcluste_4; "CCHlpAddClusterProperties failed to ope"...
0x180078dfb  mov     r9d, 3F9h
0x180078e01  mov     qword ptr [rsp+170h+var_150], rax
0x180078e06  lea     ecx, [rdx+2]
0x180078e09  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180078e0e  mov     rcx, [rsp+170h+hMem]; hMem
0x180078e13  call    cs:__imp_LocalFree
0x180078e19  jmp     short loc_180078E42
0x180078e1b  mov     dword ptr [rsp+170h+var_148], eax
0x180078e1f  lea     r8, aCchlpaddcluste_0; "CCHlpAddClusterProperties"
0x180078e26  xor     edx, edx
0x180078e28  lea     rax, aCchlpaddcluste_2; "CCHlpAddClusterProperties failed to cre"...
0x180078e2f  mov     r9d, 400h
0x180078e35  mov     qword ptr [rsp+170h+var_150], rax
0x180078e3a  lea     ecx, [rdx+2]
0x180078e3d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180078e42  test    ebx, ebx
0x180078e44  jz      short loc_180078E6B
0x180078e46  lea     r8, aFailedToAddClu; "Failed to add cluster level properties."
0x180078e4d  mov     edx, ebx; int
0x180078e4f  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180078e54  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180078e59  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180078e60  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180078e65  call    _CxxThrowException_0
0x180078e6b  mov     rcx, [rbp+70h+var_10]
0x180078e6f  xor     rcx, rsp; StackCookie
0x180078e72  call    __security_check_cookie
0x180078e77  lea     r11, [rsp+170h+var_s0]
0x180078e7f  mov     rbx, [r11+18h]
0x180078e83  mov     rsi, [r11+20h]
0x180078e87  mov     rsp, r11
0x180078e8a  pop     rbp
0x180078e8b  retn
```
