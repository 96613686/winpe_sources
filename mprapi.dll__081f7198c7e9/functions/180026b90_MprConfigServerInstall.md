# MprConfigServerInstall

- ea: `0x180026b90`
- end: `0x1800274c9`
- name: `MprConfigServerInstall`
- size: `2361`
- prototype: `DWORD __stdcall(DWORD dwLevel, PVOID pBuffer)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000aafc`
- `0x180014148`
- `0x1800151cc`
- `0x1800153c8`
- `0x18001555c`
- `0x180015828`
- `0x180015994`
- `0x180016308`
- `0x180016438`
- `0x180026b90`
- `0x1800295e4`
- `0x1800356d0`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027499`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026e2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800270d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026e2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800270d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026dfc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800270a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800270a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026cee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180026cee`
- `OLE32!CoInitialize` at `0x180026cd7`
- `OLE32!CoInitialize` at `0x180026cd7`
- `rtutils!TraceRegisterExW` at `0x180026bfd`
- `rtutils!TraceRegisterExW` at `0x180026bfd`
- `rtutils!TraceDeregisterW` at `0x180027489`
- `rtutils!TraceDeregisterW` at `0x180027489`

## string_xrefs

- `0x180026dee`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18002706e`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x180026d09`: `UpgradeRouterConfigHelper failed :Error code : %d`
- `0x180026d7d`: `UpgradeRouterConfigHelper passed : Error code: %d`
- `0x1800271a4`: `InstallGlobalSettings passed :Error code:%d`
- `0x1800271e7`: `InstallGlobalSettings failed :Error code:%d`
- `0x18002725e`: `SetDefaultSecuritySettings passed :Error code:%d`
- `0x1800272a1`: `SetDefaultSecuritySettings failed :Error code:%d`

## pseudocode

```c
DWORD __stdcall MprConfigServerInstall(DWORD dwLevel, PVOID pBuffer)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 *v8; // rdx
  int v9; // edi
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 *v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rax
  __int64 *v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 *v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 *v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 *v53; // rdx
  DWORD v54; // eax
  DWORD v55; // edi
  int *v56; // r8
  __int64 *v57; // rdx
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v61[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v63; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v64[16]; // [rsp+70h] [rbp-90h] BYREF
  int *v65; // [rsp+80h] [rbp-80h]
  int v66; // [rsp+88h] [rbp-78h]
  int v67; // [rsp+8Ch] [rbp-74h]
  int v68; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v69[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  *(_DWORD *)Data = 7;
  hKey = 0;
  v68 = 0;
  memset_0(v69, 0, sizeof(v69));
  if ( dwLevel || pBuffer )
    return 87;
  g_dwTraceHandle = TraceRegisterExW(L"MPRAPI", 0);
  v4 = UnSetMultiTenancySettings();
  v5 = -1;
  if ( v4 )
  {
    if ( byte_180078D92 < 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"UnSetMultiTenancySettings failed :Error code:%d", v4);
      if ( byte_180078D92 < 0 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v69[2 * v7 - 4] );
        v8 = RRAS_MPRAPI_TRACE_ERROR;
        goto LABEL_14;
      }
    }
  }
  else if ( (byte_180078D93 & 1) != 0 )
  {
    LOWORD(v68) = 0;
    FormatRRASErrorString(&v68, L"UnSetMultiTenancySettings passed :Error code:%d", v4);
    if ( (byte_180078D93 & 1) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&v69[2 * v7 - 4] );
      v8 = RRAS_MPRAPI_TRACE_INFO;
LABEL_14:
      v67 = 0;
      v66 = 2 * v7 + 2;
      v65 = &v68;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v8, v6, 2, v64);
    }
  }
  if ( CoInitialize(0) )
    goto LABEL_27;
  v9 = UpgradeRouterConfigHelper(0);
  CoUninitialize();
  if ( v9 >= 0 )
  {
    if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"UpgradeRouterConfigHelper passed : Error code: %d", (unsigned __int16)v9);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v69[2 * v13 - 4] );
        v67 = 0;
        v66 = 2 * v13 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RRAS_MPRAPI_TRACE_INFO,
          v12,
          2,
          v64);
      }
    }
LABEL_27:
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
            0,
            0x20006u,
            &hKey) )
      RegSetValueExW(hKey, L"RouterType", 0, 4u, Data, 4u);
    v14 = SaveDefaultIPv4Settings();
    v17 = v14;
    if ( v14 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"SaveDefaultIPv4Settings failed :Error code:%d", v14);
        if ( byte_180078D92 < 0 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&v69[2 * v18 - 4] );
          v19 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_40;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SaveDefaultIPv4Settings passed :Error code:%d", v14);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v69[2 * v18 - 4] );
        v19 = RRAS_MPRAPI_TRACE_INFO;
LABEL_40:
        v67 = 0;
        v66 = 2 * v18 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v19, v17, 2, v64);
      }
    }
    v20 = SaveDefaultIPv6Settings(v16, v15, v17);
    v23 = v20;
    if ( v20 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"SaveDefaultIPv6Settings failed :Error code:%d", v20);
        if ( byte_180078D92 < 0 )
        {
          v24 = -1;
          do
            ++v24;
          while ( *(_WORD *)&v69[2 * v24 - 4] );
          v25 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_52;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SaveDefaultIPv6Settings passed :Error code:%d", v20);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&v69[2 * v24 - 4] );
        v25 = RRAS_MPRAPI_TRACE_INFO;
LABEL_52:
        v67 = 0;
        v66 = 2 * v24 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v25, v23, 2, v64);
      }
    }
    v26 = SaveDefaultAuthAndAccSettings(v22, v21, v23);
    if ( v26 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"SaveDefaultAuthAndAccSettings failed :Error code:%d", v26);
        if ( byte_180078D92 < 0 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)&v69[2 * v28 - 4] );
          v29 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_64;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SaveDefaultAuthAndAccSettings passed :Error code:%d", v26);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)&v69[2 * v28 - 4] );
        v29 = RRAS_MPRAPI_TRACE_INFO;
LABEL_64:
        v67 = 0;
        v66 = 2 * v28 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v29, v27, 2, v64);
      }
    }
    v63 = 0;
    dwDisposition = 0;
    *(_DWORD *)v61 = 2;
    v30 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &v63,
            &dwDisposition);
    v33 = v30;
    if ( v30 || (v34 = RegSetValueExW(v63, L"LoggingFlags", 0, 4u, v61, 4u), (v33 = v34) != 0) )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"SaveDefaultErrLogSettings failed :Error code:%d", v33);
        if ( byte_180078D92 < 0 )
        {
          v35 = -1;
          do
            ++v35;
          while ( *(_WORD *)&v69[2 * v35 - 4] );
          v36 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_77;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SaveDefaultErrLogSettings passed :Error code:%d", v34);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)&v69[2 * v35 - 4] );
        v36 = RRAS_MPRAPI_TRACE_INFO;
LABEL_77:
        v67 = 0;
        v66 = 2 * v35 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v36, v33, 2, v64);
      }
    }
    v37 = InstallGlobalSettings(v32, v31, v33);
    v40 = v37;
    if ( v37 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"InstallGlobalSettings failed :Error code:%d", v37);
        if ( byte_180078D92 < 0 )
        {
          v41 = -1;
          do
            ++v41;
          while ( *(_WORD *)&v69[2 * v41 - 4] );
          v42 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_89;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"InstallGlobalSettings passed :Error code:%d", v37);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v41 = -1;
        do
          ++v41;
        while ( *(_WORD *)&v69[2 * v41 - 4] );
        v42 = RRAS_MPRAPI_TRACE_INFO;
LABEL_89:
        v67 = 0;
        v66 = 2 * v41 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v42, v40, 2, v64);
      }
    }
    v43 = SetDefaultSecuritySettings(v39, v38, v40);
    v45 = v43;
    if ( v43 )
    {
      if ( byte_180078D92 < 0 )
      {
        LOWORD(v68) = 0;
        FormatRRASErrorString(&v68, L"SetDefaultSecuritySettings failed :Error code:%d", v43);
        if ( byte_180078D92 < 0 )
        {
          v46 = -1;
          do
            ++v46;
          while ( *(_WORD *)&v69[2 * v46 - 4] );
          v47 = RRAS_MPRAPI_TRACE_ERROR;
          goto LABEL_101;
        }
      }
    }
    else if ( (byte_180078D93 & 1) != 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SetDefaultSecuritySettings passed :Error code:%d", v43);
      if ( (byte_180078D93 & 1) != 0 )
      {
        v46 = -1;
        do
          ++v46;
        while ( *(_WORD *)&v69[2 * v46 - 4] );
        v47 = RRAS_MPRAPI_TRACE_INFO;
LABEL_101:
        v67 = 0;
        v66 = 2 * v46 + 2;
        v65 = &v68;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v47, v45, 2, v64);
      }
    }
    v48 = SetDefaultPortSettings(*(unsigned int *)Data, v44, v45);
    v51 = v48;
    if ( v48 )
    {
      if ( byte_180078D92 >= 0 )
        goto LABEL_114;
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SetDefaultPortSettings failed :Error code:%d", v48);
      if ( byte_180078D92 >= 0 )
        goto LABEL_114;
      v52 = -1;
      do
        ++v52;
      while ( *(_WORD *)&v69[2 * v52 - 4] );
      v53 = RRAS_MPRAPI_TRACE_ERROR;
    }
    else
    {
      if ( (byte_180078D93 & 1) == 0 )
        goto LABEL_114;
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"SetDefaultPortSettings passed :Error code:%d", v48);
      if ( (byte_180078D93 & 1) == 0 )
        goto LABEL_114;
      v52 = -1;
      do
        ++v52;
      while ( *(_WORD *)&v69[2 * v52 - 4] );
      v53 = RRAS_MPRAPI_TRACE_INFO;
    }
    v67 = 0;
    v66 = 2 * v52 + 2;
    v65 = &v68;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v53, v51, 2, v64);
LABEL_114:
    RegisterRouterInDomain(v50, v49, v51);
    goto LABEL_115;
  }
  if ( byte_180078D92 < 0 )
  {
    LOWORD(v68) = 0;
    FormatRRASErrorString(&v68, L"UpgradeRouterConfigHelper failed :Error code : %d", (unsigned __int16)v9);
    if ( byte_180078D92 < 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v69[2 * v11 - 4] );
      v67 = 0;
      v66 = 2 * v11 + 2;
      v65 = &v68;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_MPRAPI_TRACE_ERROR, v10, 2, v64);
    }
  }
LABEL_115:
  v54 = CleanUpSettings();
  v55 = v54;
  if ( v54 )
  {
    if ( byte_180078D92 < 0 )
    {
      LOWORD(v68) = 0;
      FormatRRASErrorString(&v68, L"CleanUp failed :Error code:%d", v54);
      if ( byte_180078D92 < 0 )
      {
        do
          ++v5;
        while ( *(_WORD *)&v69[2 * v5 - 4] );
        v65 = &v68;
        v57 = RRAS_MPRAPI_TRACE_ERROR;
        goto LABEL_124;
      }
    }
  }
  else if ( (byte_180078D93 & 1) != 0 )
  {
    LOWORD(v68) = 0;
    FormatRRASErrorString(&v68, L"CleanUp passed :Error code:%d", 0);
    if ( (byte_180078D93 & 1) != 0 )
    {
      do
        ++v5;
      while ( *(_WORD *)&v69[2 * v5 - 4] );
      v56 = &v68;
      v65 = &v68;
      v57 = RRAS_MPRAPI_TRACE_INFO;
LABEL_124:
      v67 = 0;
      v66 = 2 * v5 + 2;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v57, v56, 2, v64);
    }
  }
  TraceDeregisterW(g_dwTraceHandle);
  if ( hKey )
    RegCloseKey(hKey);
  return v55;
}

```

## disassembly

```asm
0x180026b90  push    rbp
0x180026b92  push    rbx
0x180026b93  push    rsi
0x180026b94  push    rdi
0x180026b95  push    r12
0x180026b97  push    r14
0x180026b99  push    r15
0x180026b9b  lea     rbp, [rsp-7A0h]
0x180026ba3  sub     rsp, 8A0h
0x180026baa  mov     rax, cs:__security_cookie
0x180026bb1  xor     rax, rsp
0x180026bb4  mov     [rbp+7D0h+var_40], rax
0x180026bbb  mov     rdi, rdx
0x180026bbe  mov     dword ptr [rsp+8D0h+Data], 7
0x180026bc6  mov     ebx, ecx
0x180026bc8  xor     esi, esi
0x180026bca  xor     edx, edx; Val
0x180026bcc  mov     [rsp+8D0h+hKey], rsi
0x180026bd1  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180026bd5  mov     [rbp+7D0h+var_840], esi
0x180026bd8  mov     r8d, 7FCh; Size
0x180026bde  call    memset_0
0x180026be3  test    ebx, ebx
0x180026be5  jnz     loc_1800274A3
0x180026beb  test    rdi, rdi
0x180026bee  jnz     loc_1800274A3
0x180026bf4  xor     edx, edx; dwFlags
0x180026bf6  lea     rcx, aMprapi; "MPRAPI"
0x180026bfd  call    cs:__imp_TraceRegisterExW
0x180026c03  mov     cs:g_dwTraceHandle, eax
0x180026c09  call    UnSetMultiTenancySettings
0x180026c0e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026c12  lea     r15d, [rsi+2]
0x180026c16  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026c1d  mov     r8d, eax
0x180026c20  mov     r14b, 1
0x180026c23  test    eax, eax
0x180026c25  jnz     short loc_180026C6E
0x180026c27  test    cs:byte_180078D93, r14b
0x180026c2e  jz      loc_180026CD5
0x180026c34  lea     rdx, aUnsetmultitena_2; "UnSetMultiTenancySettings passed :Error"...
0x180026c3b  mov     word ptr [rbp+7D0h+var_840], si
0x180026c3f  lea     rcx, [rbp+7D0h+var_840]
0x180026c43  call    FormatRRASErrorString
0x180026c48  test    cs:byte_180078D93, r14b
0x180026c4f  jz      loc_180026CD5
0x180026c55  lea     rcx, [rbp+7D0h+var_840]
0x180026c59  mov     rax, rbx
0x180026c5c  inc     rax
0x180026c5f  cmp     [rcx+rax*2], si
0x180026c63  jnz     short loc_180026C5C
0x180026c65  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180026c6c  jmp     short loc_180026CAB
0x180026c6e  cmp     cs:byte_180078D92, sil
0x180026c75  jge     short loc_180026CD5
0x180026c77  lea     rdx, aUnsetmultitena; "UnSetMultiTenancySettings failed :Error"...
0x180026c7e  mov     word ptr [rbp+7D0h+var_840], si
0x180026c82  lea     rcx, [rbp+7D0h+var_840]
0x180026c86  call    FormatRRASErrorString
0x180026c8b  cmp     cs:byte_180078D92, sil
0x180026c92  jge     short loc_180026CD5
0x180026c94  lea     rcx, [rbp+7D0h+var_840]
0x180026c98  mov     rax, rbx
0x180026c9b  inc     rax
0x180026c9e  cmp     [rcx+rax*2], si
0x180026ca2  jnz     short loc_180026C9B
0x180026ca4  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180026cab  lea     eax, ds:2[rax*2]
0x180026cb2  mov     [rbp+7D0h+var_844], esi
0x180026cb5  lea     rcx, [rbp+7D0h+var_840]
0x180026cb9  mov     [rbp+7D0h+var_848], eax
0x180026cbc  lea     rax, [rsp+8D0h+var_860]
0x180026cc1  mov     [rbp+7D0h+var_850], rcx
0x180026cc5  mov     r9d, r15d
0x180026cc8  mov     [rsp+8D0h+phkResult], rax
0x180026ccd  mov     rcx, r12
0x180026cd0  call    McGenEventWrite_EventWriteTransfer
0x180026cd5  xor     ecx, ecx; pvReserved
0x180026cd7  call    cs:__imp_CoInitialize
0x180026cdd  test    eax, eax
0x180026cdf  jnz     loc_180026DDB
0x180026ce5  xor     ecx, ecx; struct INetCfg *
0x180026ce7  call    UpgradeRouterConfigHelper
0x180026cec  mov     edi, eax
0x180026cee  call    cs:__imp_CoUninitialize
0x180026cf4  test    edi, edi
0x180026cf6  jns     short loc_180026D70
0x180026cf8  cmp     cs:byte_180078D92, sil
0x180026cff  jge     loc_1800273C2
0x180026d05  movzx   r8d, di
0x180026d09  lea     rdx, aUpgraderouterc; "UpgradeRouterConfigHelper failed :Error"...
0x180026d10  lea     rcx, [rbp+7D0h+var_840]
0x180026d14  mov     word ptr [rbp+7D0h+var_840], si
0x180026d18  call    FormatRRASErrorString
0x180026d1d  cmp     cs:byte_180078D92, sil
0x180026d24  jge     loc_1800273C2
0x180026d2a  lea     rcx, [rbp+7D0h+var_840]
0x180026d2e  mov     rax, rbx
0x180026d31  inc     rax
0x180026d34  cmp     [rcx+rax*2], si
0x180026d38  jnz     short loc_180026D31
0x180026d3a  lea     eax, ds:2[rax*2]
0x180026d41  mov     [rbp+7D0h+var_844], esi
0x180026d44  lea     rcx, [rbp+7D0h+var_840]
0x180026d48  mov     [rbp+7D0h+var_848], eax
0x180026d4b  lea     rax, [rsp+8D0h+var_860]
0x180026d50  mov     [rbp+7D0h+var_850], rcx
0x180026d54  mov     r9d, r15d
0x180026d57  mov     [rsp+8D0h+phkResult], rax
0x180026d5c  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180026d63  mov     rcx, r12
0x180026d66  call    McGenEventWrite_EventWriteTransfer
0x180026d6b  jmp     loc_1800273C2
0x180026d70  test    cs:byte_180078D93, r14b
0x180026d77  jz      short loc_180026DDB
0x180026d79  movzx   r8d, di
0x180026d7d  lea     rdx, aUpgraderouterc_0; "UpgradeRouterConfigHelper passed : Erro"...
0x180026d84  lea     rcx, [rbp+7D0h+var_840]
0x180026d88  mov     word ptr [rbp+7D0h+var_840], si
0x180026d8c  call    FormatRRASErrorString
0x180026d91  test    cs:byte_180078D93, r14b
0x180026d98  jz      short loc_180026DDB
0x180026d9a  lea     rcx, [rbp+7D0h+var_840]
0x180026d9e  mov     rax, rbx
0x180026da1  inc     rax
0x180026da4  cmp     [rcx+rax*2], si
0x180026da8  jnz     short loc_180026DA1
0x180026daa  lea     eax, ds:2[rax*2]
0x180026db1  mov     [rbp+7D0h+var_844], esi
0x180026db4  lea     rcx, [rbp+7D0h+var_840]
0x180026db8  mov     [rbp+7D0h+var_848], eax
0x180026dbb  lea     rax, [rsp+8D0h+var_860]
0x180026dc0  mov     [rbp+7D0h+var_850], rcx
0x180026dc4  mov     r9d, r15d
0x180026dc7  mov     [rsp+8D0h+phkResult], rax
0x180026dcc  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180026dd3  mov     rcx, r12
0x180026dd6  call    McGenEventWrite_EventWriteTransfer
0x180026ddb  lea     rax, [rsp+8D0h+hKey]
0x180026de0  mov     r9d, 20006h; samDesired
0x180026de6  xor     r8d, r8d; ulOptions
0x180026de9  mov     [rsp+8D0h+phkResult], rax; phkResult
0x180026dee  lea     rdx, c_szRegKeyRemoteAccessParameters; "System\\CurrentControlSet\\Services\\Re"...
0x180026df5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026dfc  call    cs:__imp_RegOpenKeyExW
0x180026e02  mov     edi, 4
0x180026e07  test    eax, eax
0x180026e09  jnz     short loc_180026E31
0x180026e0b  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180026e10  lea     rax, [rsp+8D0h+Data]
0x180026e15  mov     [rsp+8D0h+cbData], edi; cbData
0x180026e19  lea     rdx, c_szRouterType; "RouterType"
0x180026e20  mov     r9d, edi; dwType
0x180026e23  mov     [rsp+8D0h+phkResult], rax; lpData
0x180026e28  xor     r8d, r8d; Reserved
0x180026e2b  call    cs:__imp_RegSetValueExW
0x180026e31  call    SaveDefaultIPv4Settings
0x180026e36  mov     r8d, eax
0x180026e39  test    eax, eax
0x180026e3b  jnz     short loc_180026E84
0x180026e3d  test    cs:byte_180078D93, r14b
0x180026e44  jz      loc_180026EEB
0x180026e4a  lea     rdx, aSavedefaultipv_1; "SaveDefaultIPv4Settings passed :Error c"...
0x180026e51  mov     word ptr [rbp+7D0h+var_840], si
0x180026e55  lea     rcx, [rbp+7D0h+var_840]
0x180026e59  call    FormatRRASErrorString
0x180026e5e  test    cs:byte_180078D93, r14b
0x180026e65  jz      loc_180026EEB
0x180026e6b  lea     rcx, [rbp+7D0h+var_840]
0x180026e6f  mov     rax, rbx
0x180026e72  inc     rax
0x180026e75  cmp     [rcx+rax*2], si
0x180026e79  jnz     short loc_180026E72
0x180026e7b  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180026e82  jmp     short loc_180026EC1
0x180026e84  cmp     cs:byte_180078D92, sil
0x180026e8b  jge     short loc_180026EEB
0x180026e8d  lea     rdx, aSavedefaultipv_2; "SaveDefaultIPv4Settings failed :Error c"...
0x180026e94  mov     word ptr [rbp+7D0h+var_840], si
0x180026e98  lea     rcx, [rbp+7D0h+var_840]
0x180026e9c  call    FormatRRASErrorString
0x180026ea1  cmp     cs:byte_180078D92, sil
0x180026ea8  jge     short loc_180026EEB
0x180026eaa  lea     rcx, [rbp+7D0h+var_840]
0x180026eae  mov     rax, rbx
0x180026eb1  inc     rax
0x180026eb4  cmp     [rcx+rax*2], si
0x180026eb8  jnz     short loc_180026EB1
0x180026eba  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180026ec1  lea     eax, ds:2[rax*2]
0x180026ec8  mov     [rbp+7D0h+var_844], esi
0x180026ecb  lea     rcx, [rbp+7D0h+var_840]
0x180026ecf  mov     [rbp+7D0h+var_848], eax
0x180026ed2  lea     rax, [rsp+8D0h+var_860]
0x180026ed7  mov     [rbp+7D0h+var_850], rcx
0x180026edb  mov     r9d, r15d
0x180026ede  mov     [rsp+8D0h+phkResult], rax
0x180026ee3  mov     rcx, r12
0x180026ee6  call    McGenEventWrite_EventWriteTransfer
0x180026eeb  call    SaveDefaultIPv6Settings
0x180026ef0  mov     r8d, eax
0x180026ef3  test    eax, eax
0x180026ef5  jnz     short loc_180026F3E
0x180026ef7  test    cs:byte_180078D93, r14b
0x180026efe  jz      loc_180026FA5
0x180026f04  lea     rdx, aSavedefaultipv_0; "SaveDefaultIPv6Settings passed :Error c"...
0x180026f0b  mov     word ptr [rbp+7D0h+var_840], si
0x180026f0f  lea     rcx, [rbp+7D0h+var_840]
0x180026f13  call    FormatRRASErrorString
0x180026f18  test    cs:byte_180078D93, r14b
0x180026f1f  jz      loc_180026FA5
0x180026f25  lea     rcx, [rbp+7D0h+var_840]
0x180026f29  mov     rax, rbx
0x180026f2c  inc     rax
0x180026f2f  cmp     [rcx+rax*2], si
0x180026f33  jnz     short loc_180026F2C
0x180026f35  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180026f3c  jmp     short loc_180026F7B
0x180026f3e  cmp     cs:byte_180078D92, sil
0x180026f45  jge     short loc_180026FA5
0x180026f47  lea     rdx, aSavedefaultipv; "SaveDefaultIPv6Settings failed :Error c"...
0x180026f4e  mov     word ptr [rbp+7D0h+var_840], si
0x180026f52  lea     rcx, [rbp+7D0h+var_840]
0x180026f56  call    FormatRRASErrorString
0x180026f5b  cmp     cs:byte_180078D92, sil
0x180026f62  jge     short loc_180026FA5
0x180026f64  lea     rcx, [rbp+7D0h+var_840]
0x180026f68  mov     rax, rbx
0x180026f6b  inc     rax
0x180026f6e  cmp     [rcx+rax*2], si
0x180026f72  jnz     short loc_180026F6B
0x180026f74  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180026f7b  lea     eax, ds:2[rax*2]
0x180026f82  mov     [rbp+7D0h+var_844], esi
0x180026f85  lea     rcx, [rbp+7D0h+var_840]
0x180026f89  mov     [rbp+7D0h+var_848], eax
0x180026f8c  lea     rax, [rsp+8D0h+var_860]
0x180026f91  mov     [rbp+7D0h+var_850], rcx
0x180026f95  mov     r9d, r15d
0x180026f98  mov     [rsp+8D0h+phkResult], rax
0x180026f9d  mov     rcx, r12
0x180026fa0  call    McGenEventWrite_EventWriteTransfer
0x180026fa5  call    SaveDefaultAuthAndAccSettings
0x180026faa  mov     r8d, eax
0x180026fad  test    eax, eax
0x180026faf  jnz     short loc_180026FF8
0x180026fb1  test    cs:byte_180078D93, r14b
0x180026fb8  jz      loc_18002705F
0x180026fbe  lea     rdx, aSavedefaultaut; "SaveDefaultAuthAndAccSettings passed :E"...
0x180026fc5  mov     word ptr [rbp+7D0h+var_840], si
0x180026fc9  lea     rcx, [rbp+7D0h+var_840]
0x180026fcd  call    FormatRRASErrorString
0x180026fd2  test    cs:byte_180078D93, r14b
0x180026fd9  jz      loc_18002705F
0x180026fdf  lea     rcx, [rbp+7D0h+var_840]
0x180026fe3  mov     rax, rbx
0x180026fe6  inc     rax
0x180026fe9  cmp     [rcx+rax*2], si
0x180026fed  jnz     short loc_180026FE6
0x180026fef  lea     rdx, RRAS_MPRAPI_TRACE_INFO
0x180026ff6  jmp     short loc_180027035
0x180026ff8  cmp     cs:byte_180078D92, sil
0x180026fff  jge     short loc_18002705F
0x180027001  lea     rdx, aSavedefaultaut_0; "SaveDefaultAuthAndAccSettings failed :E"...
0x180027008  mov     word ptr [rbp+7D0h+var_840], si
0x18002700c  lea     rcx, [rbp+7D0h+var_840]
0x180027010  call    FormatRRASErrorString
0x180027015  cmp     cs:byte_180078D92, sil
0x18002701c  jge     short loc_18002705F
0x18002701e  lea     rcx, [rbp+7D0h+var_840]
0x180027022  mov     rax, rbx
0x180027025  inc     rax
0x180027028  cmp     [rcx+rax*2], si
0x18002702c  jnz     short loc_180027025
0x18002702e  lea     rdx, RRAS_MPRAPI_TRACE_ERROR
0x180027035  lea     eax, ds:2[rax*2]
0x18002703c  mov     [rbp+7D0h+var_844], esi
0x18002703f  lea     rcx, [rbp+7D0h+var_840]
0x180027043  mov     [rbp+7D0h+var_848], eax
0x180027046  lea     rax, [rsp+8D0h+var_860]
0x18002704b  mov     [rbp+7D0h+var_850], rcx
0x18002704f  mov     r9d, r15d
0x180027052  mov     [rsp+8D0h+phkResult], rax
0x180027057  mov     rcx, r12
0x18002705a  call    McGenEventWrite_EventWriteTransfer
0x18002705f  lea     rax, [rsp+8D0h+dwDisposition]
0x180027064  mov     [rsp+8D0h+var_868], rsi
0x180027069  mov     [rsp+8D0h+lpdwDisposition], rax; lpdwDisposition
0x18002706e  lea     rdx, c_szRegKeyRemoteAccessParameters; "System\\CurrentControlSet\\Services\\Re"...
0x180027075  lea     rax, [rsp+8D0h+var_868]
0x18002707a  mov     [rsp+8D0h+dwDisposition], esi
0x18002707e  mov     [rsp+8D0h+var_898], rax; phkResult
0x180027083  xor     r9d, r9d; lpClass
0x180027086  mov     [rsp+8D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002708b  xor     r8d, r8d; Reserved
0x18002708e  mov     [rsp+8D0h+cbData], 0F003Fh; samDesired
0x180027096  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002709d  mov     dword ptr [rsp+8D0h+phkResult], esi; dwOptions
0x1800270a1  mov     dword ptr [rsp+8D0h+var_878], r15d
0x1800270a6  call    cs:__imp_RegCreateKeyExW
  ... truncated ...
```
