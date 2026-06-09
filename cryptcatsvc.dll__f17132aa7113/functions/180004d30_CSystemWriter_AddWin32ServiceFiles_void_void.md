# CSystemWriter::AddWin32ServiceFiles(void *,void *)

- ea: `0x180004d30`
- end: `0x1800050d2`
- name: `?AddWin32ServiceFiles@CSystemWriter@@AEAA_NPEAX0@Z`
- size: `930`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, void *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001e1d4`
- `0x18001e39c`

## callees

- `0x180004d30`
- `0x180005640`
- `0x180005fc0`
- `0x180006e54`
- `0x18000be40`
- `0x18001eea0`
- `0x1800207d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180004e78`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180004e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005031`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004f0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ff5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004f0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fdc`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180004ddd`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180004ddd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004e2a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180004e2a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004f38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800050b9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800050c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180004f38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800050b9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800050c7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004d92`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004d92`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004e5b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180004e5b`

## string_xrefs

- `0x180004fc3`: `AddWin32ServiceFiles: OpenSCManager API for service enumeration failed`
- `0x180005010`: `AddWin32ServiceFiles: EnumServicesStatusEx API for service enumeration failed`
- `0x18000503b`: `AddWin32ServiceFiles: Unable to back up image of service %ws since OpenService API failed`
- `0x180005086`: `AddWin32ServiceFiles: Unable to back up image of service %ws since QueryServiceConfig API failed`

## pseudocode

```c
bool __fastcall CSystemWriter::AddWin32ServiceFiles(CSystemWriter *this, void *a2, void *a3)
{
  DWORD v3; // esi
  DWORD v4; // ebx
  int v5; // r14d
  BYTE *v6; // r12
  SC_HANDLE v7; // r15
  struct _QUERY_SERVICE_CONFIGW *v8; // rdi
  SC_HANDLE v9; // r13
  DWORD v10; // eax
  unsigned int v11; // ebx
  DWORD v12; // ebx
  BYTE *v13; // rsi
  DWORD i; // r14d
  BOOL v15; // eax
  char v16; // dl
  __int16 v17; // r8
  int v18; // r9d
  LPWSTR lpBinaryPathName; // rcx
  const unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // rax
  LPWSTR v22; // rdx
  __int64 v23; // rcx
  bool v24; // zf
  DWORD LastError; // eax
  DWORD v27; // ebx
  wchar_t lpServices; // [rsp+20h] [rbp-E0h]
  long double cbBufSize; // [rsp+28h] [rbp-D8h]
  DWORD v30; // [rsp+54h] [rbp-ACh]
  int v31; // [rsp+58h] [rbp-A8h]
  DWORD pcbBytesNeeded; // [rsp+70h] [rbp-90h] BYREF
  DWORD ServicesReturned; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD ResumeHandle; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v37[336]; // [rsp+80h] [rbp-80h] BYREF

  v3 = 0;
  LOBYTE(v4) = 0;
  ResumeHandle = 0;
  v5 = 5;
  ServicesReturned = 0;
  pcbBytesNeeded = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = OpenSCManagerW(0, 0, 5u);
  if ( !v9 )
  {
    LastError = GetLastError();
    CSystemWriter::LogSystemErrorEvent(
      0x201u,
      L"AddWin32ServiceFiles: OpenSCManager API for service enumeration failed",
      LastError);
    goto LABEL_30;
  }
  while ( 1 )
  {
    if ( EnumServicesStatusExW(
           v9,
           SC_ENUM_PROCESS_INFO,
           0x30u,
           3u,
           v6,
           v3,
           &pcbBytesNeeded,
           &ServicesReturned,
           &ResumeHandle,
           0) )
    {
      goto LABEL_5;
    }
    v10 = GetLastError();
    v11 = v10;
    if ( v10 != 234 )
    {
      if ( v10 )
      {
LABEL_38:
        CSystemWriter::LogSystemErrorEvent(
          0x201u,
          L"AddWin32ServiceFiles: EnumServicesStatusEx API for service enumeration failed",
          v11);
        goto LABEL_39;
      }
LABEL_5:
      v12 = 512;
      v13 = v6;
      v30 = 512;
      for ( i = 0; ; ++i )
      {
        if ( i >= ServicesReturned )
        {
          LOBYTE(v4) = 1;
          goto LABEL_30;
        }
        v7 = OpenServiceW(v9, *(LPCWSTR *)v13, 1u);
        if ( v7 )
          break;
        v27 = GetLastError();
        StringCchPrintfW(
          v37,
          0x14Bu,
          L"AddWin32ServiceFiles: Unable to back up image of service %ws since OpenService API failed",
          *((_QWORD *)v13 + 1));
        CSystemWriter::LogSystemErrorEvent(0x201u, v37, v27);
LABEL_27:
        v12 = v30;
        v13 += 56;
      }
      v31 = 5;
      if ( !v8 )
      {
LABEL_22:
        v8 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, v12);
        if ( !v8 )
        {
          GetLastError();
          LOBYTE(v4) = 0;
          goto LABEL_30;
        }
      }
      v15 = QueryServiceConfigW(v7, v8, v12, &pcbBytesNeeded);
      v4 = 0;
      if ( v15 )
      {
        lpBinaryPathName = v8->lpBinaryPathName;
        if ( !lpBinaryPathName )
          goto LABEL_26;
        o((wchar_t)lpBinaryPathName, v16, v17, v18, lpServices, cbBufSize);
        v21 = wcsstr(v8->lpBinaryPathName, v20);
        if ( !v21 )
          goto LABEL_26;
        v22 = v8->lpBinaryPathName;
        if ( *v22 == 34 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v22[v23] );
          if ( v21 + 4 < &v22[v23] )
            v8->lpBinaryPathName = v22 + 1;
        }
        v21[4] = 0;
        if ( a2 )
        {
          if ( (unsigned int)pSetupStringTableLookUpString(a2, v8->lpBinaryPathName) != -1 )
          {
LABEL_26:
            CloseServiceHandle(v7);
            v7 = 0;
            goto LABEL_27;
          }
        }
        if ( (unsigned int)pSetupStringTableAddString(a3, v8->lpBinaryPathName) == -1 )
          goto LABEL_30;
      }
      else
      {
        v4 = GetLastError();
      }
      if ( v4 == 122 )
      {
        LocalFree(v8);
        v8 = 0;
        v24 = v31-- == 1;
        v30 = pcbBytesNeeded;
        if ( !v24 )
        {
          v12 = pcbBytesNeeded;
          goto LABEL_22;
        }
      }
      if ( v4 )
      {
        StringCchPrintfW(
          v37,
          0x14Bu,
          L"AddWin32ServiceFiles: Unable to back up image of service %ws since QueryServiceConfig API failed",
          *((_QWORD *)v13 + 1));
        CSystemWriter::LogSystemErrorEvent(0x201u, v37, v4);
      }
      goto LABEL_26;
    }
    LocalFree(v6);
    ResumeHandle = 0;
    ServicesReturned = 0;
    v3 = pcbBytesNeeded;
    v6 = (BYTE *)LocalAlloc(0x40u, pcbBytesNeeded);
    if ( !v6 )
      break;
    if ( !--v5 )
      goto LABEL_38;
  }
  GetLastError();
LABEL_39:
  LOBYTE(v4) = 0;
LABEL_30:
  LocalFree(v6);
  LocalFree(v8);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( v7 )
    CloseServiceHandle(v7);
  return v4;
}

```

## disassembly

```asm
0x180004d30  mov     [rsp-8+arg_0], rbx
0x180004d35  push    rbp
0x180004d36  push    rsi
0x180004d37  push    rdi
0x180004d38  push    r12
0x180004d3a  push    r13
0x180004d3c  push    r14
0x180004d3e  push    r15
0x180004d40  lea     rbp, [rsp-230h]
0x180004d48  sub     rsp, 330h
0x180004d4f  mov     rax, cs:__security_cookie
0x180004d56  xor     rax, rsp
0x180004d59  mov     [rbp+260h+var_40], rax
0x180004d60  xor     esi, esi
0x180004d62  mov     [rsp+360h+var_2F8], r8
0x180004d67  mov     [rsp+360h+var_300], rdx
0x180004d6c  mov     bl, sil
0x180004d6f  xor     edx, edx; lpDatabaseName
0x180004d71  mov     [rsp+360h+var_310], bl
0x180004d75  xor     ecx, ecx; lpMachineName
0x180004d77  mov     [rsp+360h+ResumeHandle], esi
0x180004d7b  lea     r14d, [rsi+5]
0x180004d7f  mov     [rsp+360h+ServicesReturned], esi
0x180004d83  mov     r8d, r14d; dwDesiredAccess
0x180004d86  mov     [rsp+360h+var_2F0], esi
0x180004d8a  mov     r12d, esi
0x180004d8d  mov     r15d, esi
0x180004d90  mov     edi, esi
0x180004d92  call    cs:__imp_OpenSCManagerW
0x180004d98  mov     r13, rax
0x180004d9b  test    rax, rax
0x180004d9e  jz      loc_180004FBD
0x180004da4  mov     [rsp+360h+pszGroupName], rdi; pszGroupName
0x180004da9  lea     rax, [rsp+360h+ResumeHandle]
0x180004dae  mov     [rsp+360h+lpResumeHandle], rax; lpResumeHandle
0x180004db3  xor     edx, edx; InfoLevel
0x180004db5  lea     rax, [rsp+360h+ServicesReturned]
0x180004dba  mov     rcx, r13; hSCManager
0x180004dbd  mov     [rsp+360h+lpServicesReturned], rax; lpServicesReturned
0x180004dc2  lea     rax, [rsp+360h+var_2F0]
0x180004dc7  mov     [rsp+360h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180004dcc  mov     dword ptr [rsp+360h+cbBufSize], esi; cbBufSize
0x180004dd0  lea     r9d, [rdx+3]; dwServiceState
0x180004dd4  lea     r8d, [rdx+30h]; dwServiceType
0x180004dd8  mov     [rsp+360h+lpServices], r12; lpServices
0x180004ddd  call    cs:__imp_EnumServicesStatusExW
0x180004de3  xor     esi, esi
0x180004de5  test    eax, eax
0x180004de7  jnz     short loc_180004E04
0x180004de9  call    cs:__imp_GetLastError
0x180004def  mov     ebx, eax
0x180004df1  cmp     eax, 0EAh
0x180004df6  jz      loc_180004FD9
0x180004dfc  test    eax, eax
0x180004dfe  jnz     loc_18000500D
0x180004e04  mov     ebx, 200h
0x180004e09  mov     rsi, r12
0x180004e0c  mov     [rsp+360h+var_30C], ebx
0x180004e10  xor     r14d, r14d
0x180004e13  cmp     r14d, [rsp+360h+ServicesReturned]
0x180004e18  jnb     loc_180004F6B
0x180004e1e  mov     rdx, [rsi]; lpServiceName
0x180004e21  mov     r8d, 1; dwDesiredAccess
0x180004e27  mov     rcx, r13; hSCManager
0x180004e2a  call    cs:__imp_OpenServiceW
0x180004e30  mov     r15, rax
0x180004e33  test    rax, rax
0x180004e36  jz      loc_180005031
0x180004e3c  mov     [rsp+360h+var_308], 5
0x180004e44  test    rdi, rdi
0x180004e47  jz      loc_180004F06
0x180004e4d  lea     r9, [rsp+360h+var_2F0]; pcbBytesNeeded
0x180004e52  mov     r8d, ebx; cbBufSize
0x180004e55  mov     rdx, rdi; lpServiceConfig
0x180004e58  mov     rcx, r15; hService
0x180004e5b  call    cs:__imp_QueryServiceConfigW
0x180004e61  xor     ebx, ebx
0x180004e63  test    eax, eax
0x180004e65  jz      loc_180004F5E
0x180004e6b  mov     rcx, [rdi+10h]
0x180004e6f  test    rcx, rcx
0x180004e72  jz      loc_180004F35
0x180004e78  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180004e7e  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180004e82  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x180004e87  mov     r8, rax
0x180004e8a  test    rax, rax
0x180004e8d  jz      loc_180004F35
0x180004e93  mov     rdx, [rdi+10h]
0x180004e97  cmp     word ptr [rdx], 22h ; '"'
0x180004e9b  jnz     short loc_180004EBB
0x180004e9d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004ea1  inc     rcx
0x180004ea4  cmp     [rdx+rcx*2], bx
0x180004ea8  jnz     short loc_180004EA1
0x180004eaa  lea     rcx, [rdx+rcx*2]
0x180004eae  add     rax, 8
0x180004eb2  cmp     rax, rcx
0x180004eb5  jb      loc_180004F51
0x180004ebb  mov     rax, [rsp+360h+var_300]
0x180004ec0  mov     [r8+8], bx
0x180004ec5  test    rax, rax
0x180004ec8  jnz     loc_180005068
0x180004ece  mov     rdx, [rdi+10h]
0x180004ed2  mov     rcx, [rsp+360h+var_2F8]
0x180004ed7  call    pSetupStringTableAddString
0x180004edc  cmp     eax, 0FFFFFFFFh
0x180004edf  jz      loc_1800050B1
0x180004ee5  cmp     ebx, 7Ah ; 'z'
0x180004ee8  jnz     short loc_180004F2B
0x180004eea  mov     rcx, rdi; hMem
0x180004eed  call    cs:__imp_LocalFree
0x180004ef3  mov     eax, [rsp+360h+var_2F0]
0x180004ef7  xor     edi, edi
0x180004ef9  add     [rsp+360h+var_308], 0FFFFFFFFh
0x180004efe  mov     [rsp+360h+var_30C], eax
0x180004f02  jz      short loc_180004F2B
0x180004f04  mov     ebx, eax
0x180004f06  mov     edx, ebx; uBytes
0x180004f08  mov     ecx, 40h ; '@'; uFlags
0x180004f0d  call    cs:__imp_LocalAlloc
0x180004f13  mov     rdi, rax
0x180004f16  test    rax, rax
0x180004f19  jnz     loc_180004E4D
0x180004f1f  call    cs:__imp_GetLastError
0x180004f25  mov     bl, [rsp+360h+var_310]
0x180004f29  jmp     short loc_180004F6D
0x180004f2b  test    ebx, ebx
0x180004f2d  jnz     loc_180005082
0x180004f33  xor     ebx, ebx
0x180004f35  mov     rcx, r15; hSCObject
0x180004f38  call    cs:__imp_CloseServiceHandle
0x180004f3e  mov     r15, rbx
0x180004f41  mov     ebx, [rsp+360h+var_30C]
0x180004f45  inc     r14d
0x180004f48  add     rsi, 38h ; '8'
0x180004f4c  jmp     loc_180004E13
0x180004f51  lea     rax, [rdx+2]
0x180004f55  mov     [rdi+10h], rax
0x180004f59  jmp     loc_180004EBB
0x180004f5e  call    cs:__imp_GetLastError
0x180004f64  mov     ebx, eax
0x180004f66  jmp     loc_180004EE5
0x180004f6b  mov     bl, 1
0x180004f6d  mov     rcx, r12; hMem
0x180004f70  call    cs:__imp_LocalFree
0x180004f76  mov     rcx, rdi; hMem
0x180004f79  call    cs:__imp_LocalFree
0x180004f7f  test    r13, r13
0x180004f82  jnz     loc_1800050B6
0x180004f88  test    r15, r15
0x180004f8b  jnz     loc_1800050C4
0x180004f91  mov     al, bl
0x180004f93  mov     rcx, [rbp+260h+var_40]
0x180004f9a  xor     rcx, rsp; StackCookie
0x180004f9d  call    __security_check_cookie
0x180004fa2  mov     rbx, [rsp+360h+arg_0]
0x180004faa  add     rsp, 330h
0x180004fb1  pop     r15
0x180004fb3  pop     r14
0x180004fb5  pop     r13
0x180004fb7  pop     r12
0x180004fb9  pop     rdi
0x180004fba  pop     rsi
0x180004fbb  pop     rbp
0x180004fbc  retn
0x180004fbd  call    cs:__imp_GetLastError
0x180004fc3  lea     rdx, aAddwin32servic_0; "AddWin32ServiceFiles: OpenSCManager API"...
0x180004fca  mov     ecx, 201h; unsigned int
0x180004fcf  mov     r8d, eax; unsigned int
0x180004fd2  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180004fd7  jmp     short loc_180004F6D
0x180004fd9  mov     rcx, r12; hMem
0x180004fdc  call    cs:__imp_LocalFree
0x180004fe2  mov     [rsp+360h+ResumeHandle], esi
0x180004fe6  mov     ecx, 40h ; '@'; uFlags
0x180004feb  mov     [rsp+360h+ServicesReturned], esi
0x180004fef  mov     esi, [rsp+360h+var_2F0]
0x180004ff3  mov     edx, esi; uBytes
0x180004ff5  call    cs:__imp_LocalAlloc
0x180004ffb  mov     r12, rax
0x180004ffe  test    rax, rax
0x180005001  jz      short loc_180005029
0x180005003  add     r14d, 0FFFFFFFFh
0x180005007  jnz     loc_180004DA4
0x18000500d  mov     r8d, ebx; unsigned int
0x180005010  lea     rdx, aAddwin32servic_1; "AddWin32ServiceFiles: EnumServicesStatu"...
0x180005017  mov     ecx, 201h; unsigned int
0x18000501c  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005021  mov     bl, dil
0x180005024  jmp     loc_180004F6D
0x180005029  call    cs:__imp_GetLastError
0x18000502f  jmp     short loc_180005021
0x180005031  call    cs:__imp_GetLastError
0x180005037  mov     r9, [rsi+8]
0x18000503b  lea     r8, aAddwin32servic_2; "AddWin32ServiceFiles: Unable to back up"...
0x180005042  mov     edx, 14Bh; unsigned __int64
0x180005047  lea     rcx, [rbp+260h+var_2E0]; unsigned __int16 *
0x18000504b  mov     ebx, eax
0x18000504d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005052  mov     r8d, ebx; unsigned int
0x180005055  lea     rdx, [rbp+260h+var_2E0]; unsigned __int16 *
0x180005059  mov     ecx, 201h; unsigned int
0x18000505e  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005063  jmp     loc_180004F41
0x180005068  mov     rdx, [rdi+10h]
0x18000506c  mov     rcx, rax
0x18000506f  call    pSetupStringTableLookUpString
0x180005074  cmp     eax, 0FFFFFFFFh
0x180005077  jnz     loc_180004F35
0x18000507d  jmp     loc_180004ECE
0x180005082  mov     r9, [rsi+8]
0x180005086  lea     r8, aAddwin32servic; "AddWin32ServiceFiles: Unable to back up"...
0x18000508d  mov     edx, 14Bh; unsigned __int64
0x180005092  lea     rcx, [rbp+260h+var_2E0]; unsigned __int16 *
0x180005096  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000509b  mov     r8d, ebx; unsigned int
0x18000509e  lea     rdx, [rbp+260h+var_2E0]; unsigned __int16 *
0x1800050a2  mov     ecx, 201h; unsigned int
0x1800050a7  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800050ac  jmp     loc_180004F33
0x1800050b1  jmp     loc_180004F6D
0x1800050b6  mov     rcx, r13; hSCObject
0x1800050b9  call    cs:__imp_CloseServiceHandle
0x1800050bf  jmp     loc_180004F88
0x1800050c4  mov     rcx, r15; hSCObject
0x1800050c7  call    cs:__imp_CloseServiceHandle
0x1800050cd  jmp     loc_180004F91
```
