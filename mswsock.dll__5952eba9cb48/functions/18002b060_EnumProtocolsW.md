# EnumProtocolsW

- ea: `0x18002b060`
- end: `0x18002b807`
- name: `EnumProtocolsW`
- size: `1959`
- prototype: `INT __stdcall(LPINT lpiProtocols, LPVOID lpProtocolBuffer, LPDWORD lpdwBufferLength)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002afc0`
- `0x18002c660`

## callees

- `0x18000c8c0`
- `0x1800119a0`
- `0x18001757c`
- `0x1800222f0`
- `0x180022bd2`
- `0x18002b060`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002b21f`
- `ntdll!RtlFreeHeap` at `0x18002b2be`
- `ntdll!RtlFreeHeap` at `0x18002b2ed`
- `ntdll!RtlFreeHeap` at `0x18002b3e7`
- `ntdll!RtlFreeHeap` at `0x18002b420`
- `ntdll!RtlFreeHeap` at `0x18002b438`
- `ntdll!RtlFreeHeap` at `0x18002b450`
- `ntdll!RtlFreeHeap` at `0x18002b47b`
- `ntdll!RtlFreeHeap` at `0x18002b493`
- `ntdll!RtlFreeHeap` at `0x18002b4ab`
- `ntdll!RtlFreeHeap` at `0x18002b4c7`
- `ntdll!RtlFreeHeap` at `0x18002b4df`
- `ntdll!RtlFreeHeap` at `0x18002b4fc`
- `ntdll!RtlFreeHeap` at `0x18002b519`
- `ntdll!RtlFreeHeap` at `0x18002b540`
- `ntdll!RtlFreeHeap` at `0x18002b7b4`
- `ntdll!RtlFreeHeap` at `0x18002b21f`
- `ntdll!RtlFreeHeap` at `0x18002b2be`
- `ntdll!RtlFreeHeap` at `0x18002b2ed`
- `ntdll!RtlFreeHeap` at `0x18002b3e7`
- `ntdll!RtlFreeHeap` at `0x18002b420`
- `ntdll!RtlFreeHeap` at `0x18002b438`
- `ntdll!RtlFreeHeap` at `0x18002b450`
- `ntdll!RtlFreeHeap` at `0x18002b47b`
- `ntdll!RtlFreeHeap` at `0x18002b493`
- `ntdll!RtlFreeHeap` at `0x18002b4ab`
- `ntdll!RtlFreeHeap` at `0x18002b4c7`
- `ntdll!RtlFreeHeap` at `0x18002b4df`
- `ntdll!RtlFreeHeap` at `0x18002b4fc`
- `ntdll!RtlFreeHeap` at `0x18002b519`
- `ntdll!RtlFreeHeap` at `0x18002b540`
- `ntdll!RtlFreeHeap` at `0x18002b7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b3ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b52a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b0e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b52a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b293`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002b293`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b2d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b2d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b320`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b320`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b334`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b39c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b334`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b39c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b2fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b461`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b2fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b461`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b203`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b203`
- `WS2_32!WSAEnumProtocolsW` at `0x18002b582`
- `WS2_32!WSAEnumProtocolsW` at `0x18002b5db`
- `WS2_32!WSAEnumProtocolsW` at `0x18002b582`
- `WS2_32!WSAEnumProtocolsW` at `0x18002b5db`
- `WS2_32!__imp_WSAGetLastError` at `0x18002b594`
- `WS2_32!__imp_WSAGetLastError` at `0x18002b5ed`
- `WS2_32!__imp_WSAGetLastError` at `0x18002b594`
- `WS2_32!__imp_WSAGetLastError` at `0x18002b5ed`
- `WS2_32!__imp_WSAStartup` at `0x18002b555`
- `WS2_32!__imp_WSAStartup` at `0x18002b555`
- `WS2_32!__imp_WSACleanup` at `0x18002b604`
- `WS2_32!__imp_WSACleanup` at `0x18002b604`

## string_xrefs

- `0x18002b1b3`: `System\CurrentControlSet\Services\`
- `0x18002b253`: `HelperDllName`
- `0x18002b316`: `WSHEnumProtocols`

## pseudocode

```c
INT __stdcall EnumProtocolsW(LPINT lpiProtocols, LPVOID lpProtocolBuffer, LPDWORD lpdwBufferLength)
{
  DWORD v5; // eax
  int LastError; // edi
  INT v8; // r12d
  DWORD v9; // r14d
  struct _WSAPROTOCOL_INFOW *v10; // rsi
  const wchar_t *v11; // r13
  struct _WSAPROTOCOL_INFOW *v12; // r15
  __int64 v13; // rax
  HANDLE v14; // rcx
  struct _WSAPROTOCOL_INFOW *v15; // r15
  struct _WSAPROTOCOL_INFOW *v16; // r12
  __int64 v17; // rax
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  DWORD v20; // eax
  HMODULE Library; // r15
  FARPROC ProcAddress; // rax
  __int64 v23; // rax
  DWORD v24; // ecx
  int v25; // eax
  struct _WSAPROTOCOL_INFOW *v26; // r8
  DWORD v27; // ecx
  struct _WSAPROTOCOL_INFOW *v28; // r8
  int *v29; // r13
  int v30; // esi
  struct _WSAPROTOCOL_INFOW *v31; // rax
  LPDWORD v32; // r8
  int v33; // edx
  int v34; // eax
  struct _WSAPROTOCOL_INFOW *v35; // rdi
  int v36; // r13d
  int v37; // r15d
  _DWORD *v38; // rcx
  INT v39; // edx
  __int64 v40; // rax
  unsigned int v41; // r11d
  DWORD v42; // ecx
  _DWORD *v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  WCHAR *szProtocol; // rcx
  __int64 v47; // rax
  DWORD v48; // eax
  INT v49; // [rsp+30h] [rbp-D0h]
  int v50; // [rsp+30h] [rbp-D0h]
  size_t cbDest; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v52; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwBufferLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPDWORD v57; // [rsp+60h] [rbp-A0h]
  LPINT lpiProtocolsa; // [rsp+68h] [rbp-98h]
  _DWORD *v59; // [rsp+70h] [rbp-90h]
  struct _WSAPROTOCOL_INFOW *v60; // [rsp+78h] [rbp-88h]
  struct WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF

  *(_QWORD *)dwBufferLength = lpProtocolBuffer;
  lpiProtocolsa = lpiProtocols;
  v57 = lpdwBufferLength;
  cbDest = 0;
  cbData = 0;
  hKey = 0;
  Type = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v52 = *lpdwBufferLength;
  v5 = SockLoadTransportList(&cbDest);
  LastError = v5;
  if ( v5 )
  {
    SetLastError(v5);
    return -1;
  }
  v8 = 0;
  v49 = 0;
  v9 = 0;
  v59 = lpProtocolBuffer;
  v10 = (struct _WSAPROTOCOL_INFOW *)cbDest;
  v11 = (const wchar_t *)cbDest;
  v12 = 0;
  while ( *v11 )
  {
    v13 = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 520);
    v14 = SockPrivateHeap;
    v15 = (struct _WSAPROTOCOL_INFOW *)v13;
    if ( !v13 )
    {
      v28 = v10;
      goto LABEL_38;
    }
    v16 = (struct _WSAPROTOCOL_INFOW *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                                         SockPrivateHeap,
                                         0,
                                         520);
    if ( !v16 )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v10);
      v28 = v15;
LABEL_36:
      v14 = SockPrivateHeap;
LABEL_38:
      RtlFreeHeap(v14, 0, v28);
      v27 = 8;
LABEL_39:
      SetLastError(v27);
      return -1;
    }
    v17 = -1;
    do
      ++v17;
    while ( v11[v17] );
    cbDest = (unsigned int)(2 * v17 + 108);
    v18 = (wchar_t *)((__int64 (__fastcall *)(HANDLE, _QWORD, size_t))SockAllocateHeapRoutine)(
                       SockPrivateHeap,
                       0,
                       cbDest);
    v19 = v18;
    if ( !v18 )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v10);
      RtlFreeHeap(SockPrivateHeap, 0, v15);
      v28 = v16;
      goto LABEL_36;
    }
    StringCbCopyW(v18, cbDest, L"System\\CurrentControlSet\\Services\\");
    StringCbCatW(v19, cbDest, v11);
    StringCbCatW(v19, cbDest, L"\\Parameters\\Winsock");
    LODWORD(cbDest) = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey);
    RtlFreeHeap(SockPrivateHeap, 0, v19);
    LastError = cbDest;
    if ( (_DWORD)cbDest )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v10);
      RtlFreeHeap(SockPrivateHeap, 0, v15);
      v26 = v16;
      goto LABEL_32;
    }
    cbData = 520;
    LastError = RegQueryValueExW(hKey, L"HelperDllName", 0, &Type, (LPBYTE)v15, &cbData);
    if ( Type - 1 > 1 )
    {
      LastError = 1804;
LABEL_30:
      RtlFreeHeap(SockPrivateHeap, 0, v10);
      RtlFreeHeap(SockPrivateHeap, 0, v15);
      RtlFreeHeap(SockPrivateHeap, 0, v16);
      RegCloseKey(hKey);
      goto LABEL_33;
    }
    if ( LastError )
      goto LABEL_30;
    v20 = ExpandEnvironmentStringsW((LPCWSTR)v15, (LPWSTR)v16, 0x104u);
    if ( !v20 )
    {
      LastError = GetLastError();
      goto LABEL_30;
    }
    if ( v20 > 0x104 )
    {
      LastError = 122;
      goto LABEL_30;
    }
    RtlFreeHeap(SockPrivateHeap, 0, v15);
    Library = LoadLibraryExW((LPCWSTR)v16, 0, 0);
    RtlFreeHeap(SockPrivateHeap, 0, v16);
    RegCloseKey(hKey);
    if ( !Library )
    {
      RtlFreeHeap(SockPrivateHeap, 0, v10);
      return -1;
    }
    ProcAddress = GetProcAddress(Library, "WSHEnumProtocols");
    if ( ProcAddress )
    {
      v24 = *v57 - v9;
      if ( v9 > *v57 )
        v24 = 0;
      v52 = v24;
      v25 = ((__int64 (__fastcall *)(LPINT, const wchar_t *, _QWORD, DWORD *))ProcAddress)(
              lpiProtocolsa,
              v11,
              *(_QWORD *)dwBufferLength,
              &v52);
      v9 += v52;
      LODWORD(cbDest) = v25;
      FreeLibrary(Library);
      v12 = 0;
      if ( (int)cbDest > 0 )
      {
        v8 = cbDest + v49;
        v49 += cbDest;
        *(_QWORD *)dwBufferLength += 40LL * (int)cbDest;
        v12 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      FreeLibrary(Library);
      v12 = 0;
    }
    v8 = v49;
LABEL_19:
    v23 = -1;
    do
      ++v23;
    while ( v11[v23] );
    v11 += v23 + 1;
  }
  RtlFreeHeap(SockPrivateHeap, 0, v10);
  if ( !WSAStartup(0x101u, &WSAData) )
  {
    v29 = lpiProtocolsa;
    dwBufferLength[0] = 0;
    v60 = 0;
    v30 = WSAEnumProtocolsW(lpiProtocolsa, 0, dwBufferLength);
    if ( v30 == -1 )
    {
      LastError = WSAGetLastError();
      if ( LastError == 10055 )
      {
        v31 = (struct _WSAPROTOCOL_INFOW *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                                             SockPrivateHeap,
                                             0,
                                             dwBufferLength[0]);
        v60 = v31;
        v12 = v31;
        if ( v31 )
        {
          v30 = WSAEnumProtocolsW(v29, v31, dwBufferLength);
          if ( v30 == -1 )
            LastError = WSAGetLastError();
        }
        else
        {
          v30 = -1;
          LastError = 10055;
        }
      }
    }
    WSACleanup();
    if ( v30 == -1 )
    {
      if ( v12 )
      {
        v26 = v12;
LABEL_32:
        RtlFreeHeap(SockPrivateHeap, 0, v26);
      }
LABEL_33:
      v27 = LastError;
      goto LABEL_39;
    }
    v32 = v57;
    v33 = 0;
    if ( v9 > *v57 )
    {
      v9 += 40 * v30;
      if ( v30 > 0 )
      {
        szProtocol = v12->szProtocol;
        do
        {
          v47 = -1;
          do
            ++v47;
          while ( szProtocol[v47] );
          ++v33;
          v9 += 2 * v47 + 2;
          szProtocol += 314;
        }
        while ( v33 < v30 );
      }
    }
    else
    {
      v50 = 0;
      v34 = 0;
      v35 = v12;
      v36 = 0;
      if ( v30 > 0 )
      {
        v37 = 0;
        do
        {
          if ( v8 <= 0 )
          {
LABEL_61:
            v40 = -1;
            do
              ++v40;
            while ( v35->szProtocol[v40] );
            v41 = 2 * v40 + 2;
            v42 = *v32 - v9;
            v33 += v41 + 40;
            v50 = v33;
            if ( v9 > *v32 )
              v42 = 0;
            v52 = v42;
            if ( v42 >= v33 )
            {
              v43 = v59;
              v44 = 10 * (v8 + (__int64)v37);
              v59[v44] = v35->dwServiceFlags1;
              v43[v44 + 1] = v35->iAddressFamily;
              v43[v44 + 2] = v35->iMaxSockAddr;
              v43[v44 + 3] = v35->iMinSockAddr;
              v43[v44 + 4] = v35->iSocketType;
              v43[v44 + 5] = v35->iProtocol;
              v43[v44 + 6] = v35->dwMessageSize;
              v45 = (wchar_t *)((char *)&v43[v44] + v52 - (unsigned __int64)v41);
              *(_QWORD *)&v43[v44 + 8] = v45;
              StringCbCopyW(v45, v41, v35->szProtocol);
              v33 = v50;
              ++v37;
              v32 = v57;
            }
            v9 += v33;
          }
          else
          {
            v38 = v59;
            v39 = 0;
            while ( v35->iAddressFamily != v38[1] || v35->iSocketType != v38[4] || v35->iProtocol != v38[5] )
            {
              ++v39;
              v38 += 10;
              if ( v39 >= v8 )
              {
                v33 = v50;
                goto LABEL_61;
              }
            }
            v33 = v50;
          }
          ++v36;
          ++v35;
        }
        while ( v36 < v30 );
        LODWORD(cbDest) = v37;
        v12 = v60;
        v34 = cbDest;
      }
      v8 += v34;
    }
    if ( v12 )
      RtlFreeHeap(SockPrivateHeap, 0, v12);
  }
  v48 = *v57;
  *v57 = v9;
  if ( v9 > v48 )
  {
    v27 = 122;
    goto LABEL_39;
  }
  return v8;
}

```

## disassembly

```asm
0x18002b060  mov     [rsp-8+arg_18], rbx
0x18002b065  push    rbp
0x18002b066  push    rsi
0x18002b067  push    rdi
0x18002b068  push    r12
0x18002b06a  push    r13
0x18002b06c  push    r14
0x18002b06e  push    r15
0x18002b070  lea     rbp, [rsp-130h]
0x18002b078  sub     rsp, 230h
0x18002b07f  mov     rax, cs:__security_cookie
0x18002b086  xor     rax, rsp
0x18002b089  mov     [rbp+160h+var_40], rax
0x18002b090  xor     esi, esi
0x18002b092  mov     qword ptr [rsp+260h+dwBufferLength], rdx
0x18002b097  mov     rbx, r8
0x18002b09a  mov     [rsp+260h+lpiProtocols], rcx
0x18002b09f  mov     r15, rdx
0x18002b0a2  mov     [rsp+260h+var_200], rbx
0x18002b0a7  xor     edx, edx; Val
0x18002b0a9  mov     [rsp+260h+cbDest], rsi
0x18002b0ae  mov     r8d, 198h; Size
0x18002b0b4  mov     [rsp+260h+cbData], esi
0x18002b0b8  lea     rcx, [rbp+160h+WSAData]; void *
0x18002b0bc  mov     [rsp+260h+hKey], rsi
0x18002b0c1  mov     [rsp+260h+Type], esi
0x18002b0c5  call    memset_0
0x18002b0ca  mov     eax, [rbx]
0x18002b0cc  lea     rcx, [rsp+260h+cbDest]
0x18002b0d1  mov     [rsp+260h+var_220], eax
0x18002b0d5  call    SockLoadTransportList
0x18002b0da  mov     edi, eax
0x18002b0dc  test    eax, eax
0x18002b0de  jz      short loc_18002B0F7
0x18002b0e0  mov     ecx, eax; dwErrCode
0x18002b0e2  call    cs:__imp_SetLastError
0x18002b0e9  nop     dword ptr [rax+rax+00h]
0x18002b0ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b0f2  jmp     loc_18002B7DC
0x18002b0f7  mov     r12d, esi
0x18002b0fa  mov     [rsp+260h+var_230], esi
0x18002b0fe  mov     r14d, esi
0x18002b101  mov     [rsp+260h+var_1F0], r15
0x18002b106  mov     rsi, [rsp+260h+cbDest]
0x18002b10b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b10f  mov     r13, rsi
0x18002b112  xor     r15d, r15d
0x18002b115  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b11c  xor     edx, edx; Flags
0x18002b11e  cmp     [r13+0], r15w
0x18002b123  jz      loc_18002B53D
0x18002b129  mov     rax, cs:SockAllocateHeapRoutine
0x18002b130  mov     r8d, 208h
0x18002b136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b13b  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b142  xor     edx, edx; Flags
0x18002b144  xor     edi, edi
0x18002b146  mov     r15, rax
0x18002b149  test    rax, rax
0x18002b14c  jz      loc_18002B516
0x18002b152  mov     rax, cs:SockAllocateHeapRoutine
0x18002b159  mov     r8d, 208h
0x18002b15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b164  mov     r12, rax
0x18002b167  test    rax, rax
0x18002b16a  jz      loc_18002B4F0
0x18002b170  mov     rax, rbx
0x18002b173  inc     rax
0x18002b176  cmp     [r13+rax*2+0], di
0x18002b17c  jnz     short loc_18002B173
0x18002b17e  mov     rcx, cs:SockPrivateHeap
0x18002b185  lea     eax, ds:6Ch[rax*2]
0x18002b18c  mov     [rsp+260h+cbDest], rax
0x18002b191  mov     r8d, eax
0x18002b194  mov     rax, cs:SockAllocateHeapRoutine
0x18002b19b  xor     edx, edx
0x18002b19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1a2  mov     rdi, rax
0x18002b1a5  test    rax, rax
0x18002b1a8  jz      loc_18002B4BB
0x18002b1ae  mov     rdx, [rsp+260h+cbDest]; cbDest
0x18002b1b3  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\"
0x18002b1ba  mov     rcx, rax; pszDest
0x18002b1bd  call    StringCbCopyW
0x18002b1c2  mov     rdx, [rsp+260h+cbDest]; cbDest
0x18002b1c7  mov     r8, r13; pszSrc
0x18002b1ca  mov     rcx, rdi; pszDest
0x18002b1cd  call    StringCbCatW
0x18002b1d2  mov     rdx, [rsp+260h+cbDest]; cbDest
0x18002b1d7  lea     r8, aParametersWins; "\\Parameters\\Winsock"
0x18002b1de  mov     rcx, rdi; pszDest
0x18002b1e1  call    StringCbCatW
0x18002b1e6  lea     rax, [rsp+260h+hKey]
0x18002b1eb  mov     r9d, 20019h; samDesired
0x18002b1f1  xor     r8d, r8d; ulOptions
0x18002b1f4  mov     [rsp+260h+phkResult], rax; phkResult
0x18002b1f9  mov     rdx, rdi; lpSubKey
0x18002b1fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b203  call    cs:__imp_RegOpenKeyExW
0x18002b20a  nop     dword ptr [rax+rax+00h]
0x18002b20f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b216  mov     r8, rdi; P
0x18002b219  xor     edx, edx; Flags
0x18002b21b  mov     dword ptr [rsp+260h+cbDest], eax
0x18002b21f  call    cs:__imp_RtlFreeHeap
0x18002b226  nop     dword ptr [rax+rax+00h]
0x18002b22b  mov     edi, dword ptr [rsp+260h+cbDest]
0x18002b22f  test    edi, edi
0x18002b231  jnz     loc_18002B46F
0x18002b237  mov     rcx, [rsp+260h+hKey]; hKey
0x18002b23c  lea     rax, [rsp+260h+cbData]
0x18002b241  mov     [rsp+260h+lpcbData], rax; lpcbData
0x18002b246  lea     r9, [rsp+260h+Type]; lpType
0x18002b24b  xor     r8d, r8d; lpReserved
0x18002b24e  mov     [rsp+260h+phkResult], r15; lpData
0x18002b253  lea     rdx, aHelperdllname; "HelperDllName"
0x18002b25a  mov     [rsp+260h+cbData], 208h
0x18002b262  call    cs:__imp_RegQueryValueExW
0x18002b269  nop     dword ptr [rax+rax+00h]
0x18002b26e  mov     edi, eax
0x18002b270  mov     eax, [rsp+260h+Type]
0x18002b274  dec     eax
0x18002b276  cmp     eax, 1
0x18002b279  ja      loc_18002B40F
0x18002b27f  test    edi, edi
0x18002b281  jnz     loc_18002B414
0x18002b287  mov     r8d, 104h; nSize
0x18002b28d  mov     rdx, r12; lpDst
0x18002b290  mov     rcx, r15; lpSrc
0x18002b293  call    cs:__imp_ExpandEnvironmentStringsW
0x18002b29a  nop     dword ptr [rax+rax+00h]
0x18002b29f  test    eax, eax
0x18002b2a1  jz      loc_18002B3FF
0x18002b2a7  cmp     eax, 104h
0x18002b2ac  ja      loc_18002B3F8
0x18002b2b2  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b2b9  mov     r8, r15; P
0x18002b2bc  xor     edx, edx; Flags
0x18002b2be  call    cs:__imp_RtlFreeHeap
0x18002b2c5  nop     dword ptr [rax+rax+00h]
0x18002b2ca  xor     r8d, r8d; dwFlags
0x18002b2cd  xor     edx, edx; hFile
0x18002b2cf  mov     rcx, r12; lpLibFileName
0x18002b2d2  call    cs:__imp_LoadLibraryExW
0x18002b2d9  nop     dword ptr [rax+rax+00h]
0x18002b2de  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b2e5  mov     r8, r12; P
0x18002b2e8  xor     edx, edx; Flags
0x18002b2ea  mov     r15, rax
0x18002b2ed  call    cs:__imp_RtlFreeHeap
0x18002b2f4  nop     dword ptr [rax+rax+00h]
0x18002b2f9  mov     rcx, [rsp+260h+hKey]; hKey
0x18002b2fe  call    cs:__imp_RegCloseKey
0x18002b305  nop     dword ptr [rax+rax+00h]
0x18002b30a  xor     r12d, r12d
0x18002b30d  test    r15, r15
0x18002b310  jz      loc_18002B3DB
0x18002b316  lea     rdx, aWshenumprotoco; "WSHEnumProtocols"
0x18002b31d  mov     rcx, r15; hModule
0x18002b320  call    cs:__imp_GetProcAddress
0x18002b327  nop     dword ptr [rax+rax+00h]
0x18002b32c  test    rax, rax
0x18002b32f  jnz     short loc_18002B364
0x18002b331  mov     rcx, r15; hLibModule
0x18002b334  call    cs:__imp_FreeLibrary
0x18002b33b  nop     dword ptr [rax+rax+00h]
0x18002b340  xor     r15d, r15d
0x18002b343  mov     r12d, [rsp+260h+var_230]
0x18002b348  mov     rax, rbx
0x18002b34b  inc     rax
0x18002b34e  cmp     [r13+rax*2+0], r15w
0x18002b354  jnz     short loc_18002B34B
0x18002b356  lea     r13, [r13+rax*2+0]
0x18002b35b  add     r13, 2
0x18002b35f  jmp     loc_18002B115
0x18002b364  mov     rdx, [rsp+260h+var_200]
0x18002b369  lea     r9, [rsp+260h+var_220]
0x18002b36e  mov     r8, qword ptr [rsp+260h+dwBufferLength]
0x18002b373  mov     ecx, [rdx]
0x18002b375  sub     ecx, r14d
0x18002b378  cmp     r14d, [rdx]
0x18002b37b  mov     rdx, r13
0x18002b37e  cmova   ecx, r12d
0x18002b382  mov     [rsp+260h+var_220], ecx
0x18002b386  mov     rcx, [rsp+260h+lpiProtocols]
0x18002b38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b390  add     r14d, [rsp+260h+var_220]
0x18002b395  mov     rcx, r15; hLibModule
0x18002b398  mov     dword ptr [rsp+260h+cbDest], eax
0x18002b39c  call    cs:__imp_FreeLibrary
0x18002b3a3  nop     dword ptr [rax+rax+00h]
0x18002b3a8  movsxd  rax, dword ptr [rsp+260h+cbDest]
0x18002b3ad  xor     r15d, r15d
0x18002b3b0  test    eax, eax
0x18002b3b2  jle     short loc_18002B343
0x18002b3b4  mov     r15, qword ptr [rsp+260h+dwBufferLength]
0x18002b3b9  lea     rcx, [rax+rax*4]
0x18002b3bd  mov     r12d, [rsp+260h+var_230]
0x18002b3c2  add     r12d, eax
0x18002b3c5  mov     [rsp+260h+var_230], r12d
0x18002b3ca  lea     r15, [r15+rcx*8]
0x18002b3ce  mov     qword ptr [rsp+260h+dwBufferLength], r15
0x18002b3d3  xor     r15d, r15d
0x18002b3d6  jmp     loc_18002B348
0x18002b3db  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b3e2  mov     r8, rsi; P
0x18002b3e5  xor     edx, edx; Flags
0x18002b3e7  call    cs:__imp_RtlFreeHeap
0x18002b3ee  nop     dword ptr [rax+rax+00h]
0x18002b3f3  jmp     loc_18002B536
0x18002b3f8  mov     edi, 7Ah ; 'z'
0x18002b3fd  jmp     short loc_18002B414
0x18002b3ff  call    cs:__imp_GetLastError
0x18002b406  nop     dword ptr [rax+rax+00h]
0x18002b40b  mov     edi, eax
0x18002b40d  jmp     short loc_18002B414
0x18002b40f  mov     edi, 70Ch
0x18002b414  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b41b  mov     r8, rsi; P
0x18002b41e  xor     edx, edx; Flags
0x18002b420  call    cs:__imp_RtlFreeHeap
0x18002b427  nop     dword ptr [rax+rax+00h]
0x18002b42c  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b433  mov     r8, r15; P
0x18002b436  xor     edx, edx; Flags
0x18002b438  call    cs:__imp_RtlFreeHeap
0x18002b43f  nop     dword ptr [rax+rax+00h]
0x18002b444  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b44b  mov     r8, r12; P
0x18002b44e  xor     edx, edx; Flags
0x18002b450  call    cs:__imp_RtlFreeHeap
0x18002b457  nop     dword ptr [rax+rax+00h]
0x18002b45c  mov     rcx, [rsp+260h+hKey]; hKey
0x18002b461  call    cs:__imp_RegCloseKey
0x18002b468  nop     dword ptr [rax+rax+00h]
0x18002b46d  jmp     short loc_18002B4B7
0x18002b46f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b476  mov     r8, rsi; P
0x18002b479  xor     edx, edx; Flags
0x18002b47b  call    cs:__imp_RtlFreeHeap
0x18002b482  nop     dword ptr [rax+rax+00h]
0x18002b487  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b48e  mov     r8, r15; P
0x18002b491  xor     edx, edx; Flags
0x18002b493  call    cs:__imp_RtlFreeHeap
0x18002b49a  nop     dword ptr [rax+rax+00h]
0x18002b49f  mov     r8, r12; P
0x18002b4a2  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b4a9  xor     edx, edx; Flags
0x18002b4ab  call    cs:__imp_RtlFreeHeap
0x18002b4b2  nop     dword ptr [rax+rax+00h]
0x18002b4b7  mov     ecx, edi
0x18002b4b9  jmp     short loc_18002B52A
0x18002b4bb  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b4c2  mov     r8, rsi; P
0x18002b4c5  xor     edx, edx; Flags
0x18002b4c7  call    cs:__imp_RtlFreeHeap
0x18002b4ce  nop     dword ptr [rax+rax+00h]
0x18002b4d3  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b4da  mov     r8, r15; P
0x18002b4dd  xor     edx, edx; Flags
0x18002b4df  call    cs:__imp_RtlFreeHeap
0x18002b4e6  nop     dword ptr [rax+rax+00h]
0x18002b4eb  mov     r8, r12
0x18002b4ee  jmp     short loc_18002B50B
0x18002b4f0  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002b4f7  mov     r8, rsi; P
0x18002b4fa  xor     edx, edx; Flags
0x18002b4fc  call    cs:__imp_RtlFreeHeap
0x18002b503  nop     dword ptr [rax+rax+00h]
0x18002b508  mov     r8, r15
0x18002b50b  mov     rcx, cs:SockPrivateHeap
0x18002b512  xor     edx, edx
0x18002b514  jmp     short loc_18002B519
0x18002b516  mov     r8, rsi; P
0x18002b519  call    cs:__imp_RtlFreeHeap
0x18002b520  nop     dword ptr [rax+rax+00h]
0x18002b525  mov     ecx, 8; dwErrCode
0x18002b52a  call    cs:__imp_SetLastError
0x18002b531  nop     dword ptr [rax+rax+00h]
0x18002b536  mov     eax, ebx
0x18002b538  jmp     loc_18002B7DC
0x18002b53d  mov     r8, rsi; P
0x18002b540  call    cs:__imp_RtlFreeHeap
0x18002b547  nop     dword ptr [rax+rax+00h]
0x18002b54c  mov     ecx, 101h; wVersionRequested
0x18002b551  lea     rdx, [rbp+160h+WSAData]; lpWSAData
0x18002b555  call    cs:__imp_WSAStartup
0x18002b55c  nop     dword ptr [rax+rax+00h]
0x18002b561  test    eax, eax
0x18002b563  jnz     loc_18002B7C0
0x18002b569  mov     r13, [rsp+260h+lpiProtocols]
0x18002b56e  lea     r8, [rsp+260h+dwBufferLength]; lpdwBufferLength
0x18002b573  mov     rcx, r13; lpiProtocols
0x18002b576  mov     [rsp+260h+dwBufferLength], r15d
0x18002b57b  xor     edx, edx; lpProtocolBuffer
0x18002b57d  mov     [rsp+260h+var_1E8], r15
0x18002b582  call    cs:__imp_WSAEnumProtocolsW
0x18002b589  nop     dword ptr [rax+rax+00h]
0x18002b58e  mov     esi, eax
  ... truncated ...
```
