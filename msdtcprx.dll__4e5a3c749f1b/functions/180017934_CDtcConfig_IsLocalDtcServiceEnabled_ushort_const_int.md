# CDtcConfig::IsLocalDtcServiceEnabled(ushort const *,int *)

- ea: `0x180017934`
- end: `0x180017bff`
- name: `?IsLocalDtcServiceEnabled@CDtcConfig@@AEAAJPEBGPEAH@Z`
- size: `715`
- prototype: `int(CDtcConfig *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015414`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180017934`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017a74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017a74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b70`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017aea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017b68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017aea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017b68`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800179d9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800179d9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800179ba`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800179ba`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800179f8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x1800179f8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180017aa9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180017aa9`

## string_xrefs

- `0x18001796a`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001797c`: `CDtcConfig::IsLocalDtcServiceEnabled`
- `0x180017a1c`: `CDtcConfig::IsLocalDtcServiceEnabled`
- `0x180017af0`: `CDtcConfig::IsLocalDtcServiceEnabled`
- `0x180017b4c`: `CDtcConfig::IsLocalDtcServiceEnabled`
- `0x180017ac8`: `QueryServiceConfigW failed.`
- `0x180017b33`: `QueryServiceConfigW failed.`
- `0x180017b85`: `OpenSCManagerW failed.`
- `0x18001799d`: `CDtcConfig::IsLocalDtcServiceEnabled (com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp@2011): pbLocalDtcEnabled shouldn't be NULL`
- `0x180017a07`: `QueryServiceConfig failed.`
- `0x180017b0a`: `Service is not installed.`

## pseudocode

```c
__int64 __fastcall CDtcConfig::IsLocalDtcServiceEnabled(CDtcConfig *this, const unsigned __int16 *a2, int *a3)
{
  struct _QUERY_SERVICE_CONFIGW *v5; // rbp
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r14
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  unsigned int v10; // ebx
  const wchar_t *v11; // rax
  __int64 v12; // r9
  signed int v13; // eax
  struct _QUERY_SERVICE_CONFIGW *v14; // rax
  signed int v15; // eax
  signed int LastError; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  signed int v19; // eax
  __int64 v21; // [rsp+28h] [rbp-40h]
  const wchar_t *v22; // [rsp+30h] [rbp-38h]
  DWORD pcbBytesNeeded; // [rsp+70h] [rbp+8h] BYREF
  int v24; // [rsp+74h] [rbp+Ch]

  v24 = HIDWORD(this);
  pcbBytesNeeded = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    2009,
    L"CDtcConfig::IsLocalDtcServiceEnabled",
    0,
    L"In");
  if ( !a3 )
    DtcInternalErrorW(
      L"CDtcConfig::IsLocalDtcServiceEnabled (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp@2011): pbLocalDtcEnable"
       "d shouldn't be NULL");
  v5 = 0;
  *a3 = 0;
  v6 = OpenSCManagerW(a2, 0, 1u);
  v7 = v6;
  if ( v6 )
  {
    v8 = OpenServiceW(v6, L"MSDTC", 1u);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError == 1060 )
      {
        v10 = 0;
        v22 = L"Service is not installed.";
        v17 = 2069;
        v21 = 0;
        v18 = 3;
      }
      else
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v17 = 2073;
        v22 = L"QueryServiceConfigW failed.";
        v18 = 1;
        LODWORD(v21) = v10;
      }
      TraceStringInline(
        15,
        v18,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        v17,
        L"CDtcConfig::IsLocalDtcServiceEnabled",
        v21,
        v22);
      goto LABEL_28;
    }
    if ( QueryServiceConfigA(v8, 0, 0, &pcbBytesNeeded) )
    {
      v10 = -2147418113;
      v11 = L"QueryServiceConfig failed.";
      v12 = 2030;
    }
    else
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 == 122 )
      {
        v14 = (struct _QUERY_SERVICE_CONFIGW *)CoTaskMemAlloc(pcbBytesNeeded);
        v5 = v14;
        if ( v14 )
        {
          if ( QueryServiceConfigW(v9, v14, pcbBytesNeeded, &pcbBytesNeeded) )
          {
            v10 = 0;
            *a3 = v5->dwStartType != 4;
            goto LABEL_21;
          }
          v15 = GetLastError();
          v10 = v15;
          if ( v15 > 0 )
            v10 = (unsigned __int16)v15 | 0x80070000;
          v11 = L"QueryServiceConfigW failed.";
          v12 = 2059;
        }
        else
        {
          v10 = -2147024882;
          v11 = L"Low memory.";
          v12 = 2052;
        }
      }
      else
      {
        if ( v13 )
        {
          if ( v13 > 0 )
            v10 = (unsigned __int16)v13 | 0x80070000;
        }
        else
        {
          v10 = -2147418113;
        }
        v11 = L"GetProcAddress failed.";
        v12 = 2044;
      }
    }
    LODWORD(v21) = v10;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v12,
      L"CDtcConfig::IsLocalDtcServiceEnabled",
      v21,
      v11);
LABEL_21:
    CloseServiceHandle(v9);
LABEL_28:
    CloseServiceHandle(v7);
    goto LABEL_32;
  }
  v19 = GetLastError();
  v10 = v19;
  if ( v19 > 0 )
    v10 = (unsigned __int16)v19 | 0x80070000;
  LODWORD(v21) = v10;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    2080,
    L"CDtcConfig::IsLocalDtcServiceEnabled",
    v21,
    L"OpenSCManagerW failed.");
LABEL_32:
  CoTaskMemFree(v5);
  LODWORD(v21) = v10;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    2098,
    L"CDtcConfig::IsLocalDtcServiceEnabled",
    v21,
    L"Out");
  return v10;
}

```

## disassembly

```asm
0x180017934  mov     r11, rsp
0x180017937  mov     [r11+10h], rbx
0x18001793b  mov     [r11+18h], rbp
0x18001793f  mov     [r11+8], rcx
0x180017943  push    rsi
0x180017944  push    rdi
0x180017945  push    r12
0x180017947  push    r13
0x180017949  push    r14
0x18001794b  sub     rsp, 40h
0x18001794f  mov     rbx, rdx
0x180017952  mov     [rsp+68h+pcbBytesNeeded], 0
0x18001795a  mov     edx, 6
0x18001795f  lea     rax, aIn_0; "In"
0x180017966  mov     [r11-38h], rax
0x18001796a  lea     r13, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180017971  mov     rdi, r8
0x180017974  mov     qword ptr [r11-40h], 0
0x18001797c  lea     rsi, aCdtcconfigIslo; "CDtcConfig::IsLocalDtcServiceEnabled"
0x180017983  mov     r9d, 7D9h
0x180017989  lea     ecx, [rdx+9]
0x18001798c  mov     [r11-48h], rsi
0x180017990  mov     r8, r13
0x180017993  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017998  test    rdi, rdi
0x18001799b  jnz     short loc_1800179AA
0x18001799d  lea     rcx, aCdtcconfigIslo_0; "CDtcConfig::IsLocalDtcServiceEnabled (c"...
0x1800179a4  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800179aa  xor     ebp, ebp
0x1800179ac  xor     edx, edx; lpDatabaseName
0x1800179ae  mov     rcx, rbx; lpMachineName
0x1800179b1  mov     [rdi], ebp
0x1800179b3  lea     r12d, [rbp+1]
0x1800179b7  mov     r8d, r12d; dwDesiredAccess
0x1800179ba  call    cs:__imp_OpenSCManagerW
0x1800179c0  mov     r14, rax
0x1800179c3  test    rax, rax
0x1800179c6  jz      loc_180017B70
0x1800179cc  mov     r8d, r12d; dwDesiredAccess
0x1800179cf  lea     rdx, aMsdtc; "MSDTC"
0x1800179d6  mov     rcx, rax; hSCManager
0x1800179d9  call    cs:__imp_OpenServiceW
0x1800179df  mov     rsi, rax
0x1800179e2  test    rax, rax
0x1800179e5  jz      loc_180017AF9
0x1800179eb  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800179f0  xor     r8d, r8d; cbBufSize
0x1800179f3  xor     edx, edx; lpServiceConfig
0x1800179f5  mov     rcx, rax; hService
0x1800179f8  call    cs:__imp_QueryServiceConfigA
0x1800179fe  test    eax, eax
0x180017a00  jz      short loc_180017A3E
0x180017a02  mov     ebx, 8000FFFFh
0x180017a07  lea     rax, aQueryserviceco_0; "QueryServiceConfig failed."
0x180017a0e  mov     r9d, 7EEh
0x180017a14  mov     [rsp+68h+var_38], rax
0x180017a19  mov     r8, r13
0x180017a1c  lea     rax, aCdtcconfigIslo; "CDtcConfig::IsLocalDtcServiceEnabled"
0x180017a23  mov     dword ptr [rsp+68h+var_40], ebx
0x180017a27  mov     edx, r12d
0x180017a2a  mov     [rsp+68h+var_48], rax
0x180017a2f  mov     ecx, 0Fh
0x180017a34  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017a39  jmp     loc_180017AE7
0x180017a3e  call    cs:__imp_GetLastError
0x180017a44  mov     ebx, eax
0x180017a46  cmp     eax, 7Ah ; 'z'
0x180017a49  jz      short loc_180017A70
0x180017a4b  test    eax, eax
0x180017a4d  jnz     short loc_180017A56
0x180017a4f  mov     ebx, 8000FFFFh
0x180017a54  jmp     short loc_180017A61
0x180017a56  jle     short loc_180017A61
0x180017a58  movzx   ebx, ax
0x180017a5b  or      ebx, 80070000h
0x180017a61  lea     rax, aGetprocaddress_0; "GetProcAddress failed."
0x180017a68  mov     r9d, 7FCh
0x180017a6e  jmp     short loc_180017A14
0x180017a70  mov     ecx, [rsp+68h+pcbBytesNeeded]; cb
0x180017a74  call    cs:__imp_CoTaskMemAlloc
0x180017a7a  mov     rbp, rax
0x180017a7d  test    rax, rax
0x180017a80  jnz     short loc_180017A99
0x180017a82  mov     ebx, 8007000Eh
0x180017a87  lea     rax, aLowMemory; "Low memory."
0x180017a8e  mov     r9d, 804h
0x180017a94  jmp     loc_180017A14
0x180017a99  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x180017a9e  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x180017aa3  mov     rdx, rbp; lpServiceConfig
0x180017aa6  mov     rcx, rsi; hService
0x180017aa9  call    cs:__imp_QueryServiceConfigW
0x180017aaf  test    eax, eax
0x180017ab1  jnz     short loc_180017ADA
0x180017ab3  call    cs:__imp_GetLastError
0x180017ab9  mov     ebx, eax
0x180017abb  test    eax, eax
0x180017abd  jle     short loc_180017AC8
0x180017abf  movzx   ebx, ax
0x180017ac2  or      ebx, 80070000h
0x180017ac8  lea     rax, aQueryserviceco; "QueryServiceConfigW failed."
0x180017acf  mov     r9d, 80Bh
0x180017ad5  jmp     loc_180017A14
0x180017ada  xor     eax, eax
0x180017adc  xor     ebx, ebx
0x180017ade  cmp     dword ptr [rbp+4], 4
0x180017ae2  setnz   al
0x180017ae5  mov     [rdi], eax
0x180017ae7  mov     rcx, rsi; hSCObject
0x180017aea  call    cs:__imp_CloseServiceHandle
0x180017af0  lea     rsi, aCdtcconfigIslo; "CDtcConfig::IsLocalDtcServiceEnabled"
0x180017af7  jmp     short loc_180017B65
0x180017af9  call    cs:__imp_GetLastError
0x180017aff  mov     ebx, eax
0x180017b01  cmp     eax, 424h
0x180017b06  jnz     short loc_180017B26
0x180017b08  xor     ebx, ebx
0x180017b0a  lea     rax, aServiceIsNotIn; "Service is not installed."
0x180017b11  mov     [rsp+68h+var_38], rax
0x180017b16  mov     r9d, 815h
0x180017b1c  mov     [rsp+68h+var_40], rbx
0x180017b21  lea     edx, [rbx+3]
0x180017b24  jmp     short loc_180017B4C
0x180017b26  test    eax, eax
0x180017b28  jle     short loc_180017B33
0x180017b2a  movzx   ebx, ax
0x180017b2d  or      ebx, 80070000h
0x180017b33  lea     rax, aQueryserviceco; "QueryServiceConfigW failed."
0x180017b3a  mov     r9d, 819h
0x180017b40  mov     [rsp+68h+var_38], rax
0x180017b45  mov     edx, r12d
0x180017b48  mov     dword ptr [rsp+68h+var_40], ebx
0x180017b4c  lea     rsi, aCdtcconfigIslo; "CDtcConfig::IsLocalDtcServiceEnabled"
0x180017b53  mov     r8, r13
0x180017b56  mov     ecx, 0Fh
0x180017b5b  mov     [rsp+68h+var_48], rsi
0x180017b60  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017b65  mov     rcx, r14; hSCObject
0x180017b68  call    cs:__imp_CloseServiceHandle
0x180017b6e  jmp     short loc_180017BB0
0x180017b70  call    cs:__imp_GetLastError
0x180017b76  mov     ebx, eax
0x180017b78  test    eax, eax
0x180017b7a  jle     short loc_180017B85
0x180017b7c  movzx   ebx, ax
0x180017b7f  or      ebx, 80070000h
0x180017b85  lea     rax, aOpenscmanagerw; "OpenSCManagerW failed."
0x180017b8c  mov     r9d, 820h
0x180017b92  mov     [rsp+68h+var_38], rax
0x180017b97  mov     r8, r13
0x180017b9a  mov     dword ptr [rsp+68h+var_40], ebx
0x180017b9e  mov     edx, r12d
0x180017ba1  mov     ecx, 0Fh
0x180017ba6  mov     [rsp+68h+var_48], rsi
0x180017bab  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017bb0  mov     rcx, rbp; pv
0x180017bb3  call    cs:__imp_CoTaskMemFree
0x180017bb9  mov     edx, 6
0x180017bbe  lea     rax, aOut; "Out"
0x180017bc5  mov     [rsp+68h+var_38], rax
0x180017bca  mov     r9d, 832h
0x180017bd0  mov     dword ptr [rsp+68h+var_40], ebx
0x180017bd4  mov     r8, r13
0x180017bd7  mov     [rsp+68h+var_48], rsi
0x180017bdc  lea     ecx, [rdx+9]
0x180017bdf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180017be4  lea     r11, [rsp+68h+var_28]
0x180017be9  mov     eax, ebx
0x180017beb  mov     rbx, [r11+38h]
0x180017bef  mov     rbp, [r11+40h]
0x180017bf3  mov     rsp, r11
0x180017bf6  pop     r14
0x180017bf8  pop     r13
0x180017bfa  pop     r12
0x180017bfc  pop     rdi
0x180017bfd  pop     rsi
0x180017bfe  retn
```
