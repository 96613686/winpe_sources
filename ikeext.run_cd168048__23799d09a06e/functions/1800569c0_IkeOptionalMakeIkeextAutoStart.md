# IkeOptionalMakeIkeextAutoStart

- ea: `0x1800569c0`
- end: `0x180056c57`
- name: `IkeOptionalMakeIkeextAutoStart`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180054bf4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x1800569c0`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b2f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180056a04`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180056a04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056c0a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056c18`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056c0a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180056c18`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180056a44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180056a44`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180056a70`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180056ab1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180056a70`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180056ab1`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180056b25`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180056b25`

## string_xrefs

- `0x180056a1a`: `OpenSCManagerW`
- `0x180056a58`: `OpenServiceW`
- `0x180056ac1`: `QueryServiceConfigW`
- `0x180056b35`: `ChangeServiceConfigW`
- `0x180056bc2`: `Set IKEEXT as auto-start service`

## pseudocode

```c
__int64 IkeOptionalMakeIkeextAutoStart()
{
  LPQUERY_SERVICE_CONFIGW v0; // rbx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // r15
  SC_HANDLE v3; // rsi
  DWORD LastError; // eax
  __int64 v5; // rcx
  const char *v6; // rdx
  __int64 v7; // r14
  SC_HANDLE v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 TlsPeerAddr; // rbx
  int TlsMmLuid; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+60h] [rbp-59h] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp-51h] BYREF
  __int64 v20; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-39h] BYREF
  __int64 *v22; // [rsp+A0h] [rbp-19h]
  __int64 v23; // [rsp+A8h] [rbp-11h]
  _BYTE v24[16]; // [rsp+B0h] [rbp-9h] BYREF
  const char *v25; // [rsp+C0h] [rbp+7h]
  __int64 v26; // [rsp+C8h] [rbp+Fh]

  v0 = 0;
  lpServiceConfig = 0;
  pcbBytesNeeded = 0;
  TraceLogHelper("IkeOptionalMakeIkeextAutoStart", 1);
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
  {
    v3 = 0;
    LastError = GetLastError();
    v6 = "OpenSCManagerW";
LABEL_3:
    v7 = WfpReportSysErrorAsWinError(v5, v6, LastError, 1);
    goto LABEL_20;
  }
  v8 = OpenServiceW(v1, L"ikeext", 3u);
  v3 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    v6 = "OpenServiceW";
    goto LABEL_3;
  }
  v7 = 0;
  if ( QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
  {
LABEL_11:
    if ( v0->dwStartType == 3 )
    {
      if ( !ChangeServiceConfigW(v3, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        LastError = GetLastError();
        v6 = "ChangeServiceConfigW";
        goto LABEL_3;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(v9);
        TlsMmLuid = IkeGetTlsMmLuid();
        WPP_SF_iS(v10, 84, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v20 = IkeGetTlsMmLuid();
        v22 = &v20;
        v23 = 8;
        v14 = IkeGetTlsPeerAddr(v13);
        tlgCreate1Sz_wchar_t(v24, v14);
        v26 = 33;
        v25 = "Set IKEEXT as auto-start service";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&byte_18014E297,
          v15,
          v16,
          5,
          (__int64)v21);
      }
    }
    goto LABEL_20;
  }
  if ( GetLastError() != 122 )
  {
LABEL_10:
    LastError = GetLastError();
    v6 = "QueryServiceConfigW";
    goto LABEL_3;
  }
  v7 = WfpMemAlloc(pcbBytesNeeded, 0);
  if ( !v7 )
  {
    v0 = lpServiceConfig;
    if ( !QueryServiceConfigW(v3, lpServiceConfig, pcbBytesNeeded, &pcbBytesNeeded) )
      goto LABEL_10;
    goto LABEL_11;
  }
LABEL_20:
  WfpMemFree(&lpServiceConfig);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v3 )
    CloseServiceHandle(v3);
  TraceLogHelper("IkeOptionalMakeIkeextAutoStart", 0);
  return IkeReturnError(v7, "IkeOptionalMakeIkeextAutoStart");
}

```

## disassembly

```asm
0x1800569c0  push    rbp
0x1800569c2  push    rbx
0x1800569c3  push    rsi
0x1800569c4  push    rdi
0x1800569c5  push    r14
0x1800569c7  push    r15
0x1800569c9  lea     rbp, [rsp-2Fh]
0x1800569ce  sub     rsp, 0E8h
0x1800569d5  mov     rax, cs:__security_cookie
0x1800569dc  xor     rax, rsp
0x1800569df  mov     [rbp+57h+var_40], rax
0x1800569e3  xor     ebx, ebx
0x1800569e5  lea     rcx, aIkeoptionalmak; "IkeOptionalMakeIkeextAutoStart"
0x1800569ec  mov     [rbp+57h+lpServiceConfig], rbx
0x1800569f0  mov     [rbp+57h+pcbBytesNeeded], ebx
0x1800569f3  lea     edi, [rbx+1]
0x1800569f6  mov     edx, edi
0x1800569f8  call    TraceLogHelper
0x1800569fd  mov     r8d, edi; dwDesiredAccess
0x180056a00  xor     edx, edx; lpDatabaseName
0x180056a02  xor     ecx, ecx; lpMachineName
0x180056a04  call    cs:__imp_OpenSCManagerW
0x180056a0a  mov     r15, rax
0x180056a0d  test    rax, rax
0x180056a10  jnz     short loc_180056A34
0x180056a12  xor     esi, esi
0x180056a14  call    cs:__imp_GetLastError
0x180056a1a  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x180056a21  mov     r9d, edi
0x180056a24  mov     r8d, eax
0x180056a27  call    WfpReportSysErrorAsWinError
0x180056a2c  mov     r14, rax
0x180056a2f  jmp     loc_180056BF9
0x180056a34  mov     r8d, 3; dwDesiredAccess
0x180056a3a  lea     rdx, ServiceName; "ikeext"
0x180056a41  mov     rcx, r15; hSCManager
0x180056a44  call    cs:__imp_OpenServiceW
0x180056a4a  mov     rsi, rax
0x180056a4d  test    rax, rax
0x180056a50  jnz     short loc_180056A61
0x180056a52  call    cs:__imp_GetLastError
0x180056a58  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x180056a5f  jmp     short loc_180056A21
0x180056a61  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180056a65  xor     r8d, r8d; cbBufSize
0x180056a68  xor     edx, edx; lpServiceConfig
0x180056a6a  mov     rcx, rsi; hService
0x180056a6d  xor     r14d, r14d
0x180056a70  call    cs:__imp_QueryServiceConfigW
0x180056a76  test    eax, eax
0x180056a78  jnz     short loc_180056ACD
0x180056a7a  call    cs:__imp_GetLastError
0x180056a80  cmp     eax, 7Ah ; 'z'
0x180056a83  jnz     short loc_180056ABB
0x180056a85  mov     ecx, [rbp+57h+pcbBytesNeeded]; dwBytes
0x180056a88  lea     r8, [rbp+57h+lpServiceConfig]
0x180056a8c  xor     edx, edx; dwFlags
0x180056a8e  call    WfpMemAlloc
0x180056a93  mov     r14, rax
0x180056a96  test    rax, rax
0x180056a99  jnz     loc_180056BF9
0x180056a9f  mov     rbx, [rbp+57h+lpServiceConfig]
0x180056aa3  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180056aa7  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x180056aab  mov     rdx, rbx; lpServiceConfig
0x180056aae  mov     rcx, rsi; hService
0x180056ab1  call    cs:__imp_QueryServiceConfigW
0x180056ab7  test    eax, eax
0x180056ab9  jnz     short loc_180056ACD
0x180056abb  call    cs:__imp_GetLastError
0x180056ac1  lea     rdx, aQueryserviceco_0; "QueryServiceConfigW"
0x180056ac8  jmp     loc_180056A21
0x180056acd  cmp     dword ptr [rbx+4], 3
0x180056ad1  jnz     loc_180056BF9
0x180056ad7  mov     [rsp+110h+lpDisplayName], 0; lpDisplayName
0x180056ae0  or      edx, 0FFFFFFFFh; dwServiceType
0x180056ae3  mov     [rsp+110h+lpPassword], 0; lpPassword
0x180056aec  mov     r9d, edx; dwErrorControl
0x180056aef  mov     [rsp+110h+lpServiceStartName], 0; lpServiceStartName
0x180056af8  mov     r8d, 2; dwStartType
0x180056afe  mov     [rsp+110h+lpDependencies], 0; lpDependencies
0x180056b07  mov     rcx, rsi; hService
0x180056b0a  mov     [rsp+110h+lpdwTagId], 0; lpdwTagId
0x180056b13  mov     [rsp+110h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180056b1c  mov     [rsp+110h+lpBinaryPathName], 0; lpBinaryPathName
0x180056b25  call    cs:__imp_ChangeServiceConfigW
0x180056b2b  test    eax, eax
0x180056b2d  jnz     short loc_180056B41
0x180056b2f  call    cs:__imp_GetLastError
0x180056b35  lea     rdx, aChangeservicec_0; "ChangeServiceConfigW"
0x180056b3c  jmp     loc_180056A21
0x180056b41  mov     rdi, cs:WPP_GLOBAL_Control
0x180056b48  lea     rax, WPP_GLOBAL_Control
0x180056b4f  cmp     rdi, rax
0x180056b52  jz      short loc_180056B8D
0x180056b54  cmp     byte ptr [rdi+19h], 4
0x180056b58  jb      short loc_180056B8D
0x180056b5a  test    byte ptr [rdi+1Ch], 10h
0x180056b5e  jz      short loc_180056B8D
0x180056b60  mov     rdi, [rdi+10h]
0x180056b64  call    IkeGetTlsPeerAddr
0x180056b69  mov     rbx, rax
0x180056b6c  call    IkeGetTlsMmLuid
0x180056b71  mov     r9, rax
0x180056b74  mov     [rsp+110h+lpBinaryPathName], rbx
0x180056b79  mov     edx, 54h ; 'T'
0x180056b7e  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180056b85  mov     rcx, rdi
0x180056b88  call    WPP_SF_iS
0x180056b8d  mov     eax, cs:dword_180173278
0x180056b93  cmp     eax, 4
0x180056b96  jbe     short loc_180056BF9
0x180056b98  call    IkeGetTlsMmLuid
0x180056b9d  mov     [rbp+57h+var_A0], rax
0x180056ba1  lea     rax, [rbp+57h+var_A0]
0x180056ba5  mov     [rbp+57h+var_70], rax
0x180056ba9  mov     [rbp+57h+var_68], 8
0x180056bb1  call    IkeGetTlsPeerAddr
0x180056bb6  mov     rdx, rax
0x180056bb9  lea     rcx, [rbp+57h+var_60]
0x180056bbd  call    _tlgCreate1Sz_wchar_t
0x180056bc2  lea     rcx, aSetIkeextAsAut; "Set IKEEXT as auto-start service"
0x180056bc9  mov     [rbp+57h+var_48], 21h ; '!'
0x180056bd1  lea     rax, [rbp+57h+var_90]
0x180056bd5  mov     [rbp+57h+var_50], rcx
0x180056bd9  mov     [rsp+110h+lpLoadOrderGroup], rax
0x180056bde  lea     rcx, dword_180173278
0x180056be5  lea     rdx, byte_18014E297
0x180056bec  mov     dword ptr [rsp+110h+lpBinaryPathName], 5
0x180056bf4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180056bf9  lea     rcx, [rbp+57h+lpServiceConfig]
0x180056bfd  call    WfpMemFree
0x180056c02  test    r15, r15
0x180056c05  jz      short loc_180056C10
0x180056c07  mov     rcx, r15; hSCObject
0x180056c0a  call    cs:__imp_CloseServiceHandle
0x180056c10  test    rsi, rsi
0x180056c13  jz      short loc_180056C1E
0x180056c15  mov     rcx, rsi; hSCObject
0x180056c18  call    cs:__imp_CloseServiceHandle
0x180056c1e  xor     edx, edx
0x180056c20  lea     rcx, aIkeoptionalmak; "IkeOptionalMakeIkeextAutoStart"
0x180056c27  call    TraceLogHelper
0x180056c2c  lea     rdx, aIkeoptionalmak; "IkeOptionalMakeIkeextAutoStart"
0x180056c33  mov     rcx, r14
0x180056c36  call    IkeReturnError
0x180056c3b  mov     rcx, [rbp+57h+var_40]
0x180056c3f  xor     rcx, rsp; StackCookie
0x180056c42  call    __security_check_cookie
0x180056c47  add     rsp, 0E8h
0x180056c4e  pop     r15
0x180056c50  pop     r14
0x180056c52  pop     rdi
0x180056c53  pop     rsi
0x180056c54  pop     rbx
0x180056c55  pop     rbp
0x180056c56  retn
```
