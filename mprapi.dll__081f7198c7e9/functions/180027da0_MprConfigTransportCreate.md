# MprConfigTransportCreate

- ea: `0x180027da0`
- end: `0x1800280ef`
- name: `MprConfigTransportCreate`
- size: `847`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwTransportId, LPWSTR lpwsTransportName, LPBYTE pGlobalInfo, DWORD dwGlobalInfoSize, LPBYTE pClientInterfaceInfo, DWORD dwClientInterfaceInfoSize, LPWSTR lpwsDLLPath, HANDLE *phRouterTransport)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003628c`

## callees

- `0x180009868`
- `0x180017700`
- `0x180018470`
- `0x180022be8`
- `0x180027d5c`
- `0x180027da0`
- `0x180028100`
- `0x180028700`
- `0x1800291b4`
- `0x180029414`
- `0x18002998c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027fef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027fef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027e24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027ed4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027ed4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027ee3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027ee3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028053`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028053`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027fdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027fdc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027f46`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027f46`

## string_xrefs

- `0x18002802b`: `ProtocolId`

## pseudocode

```c
DWORD __stdcall MprConfigTransportCreate(
        HANDLE hMprConfig,
        DWORD dwTransportId,
        LPWSTR lpwsTransportName,
        LPBYTE pGlobalInfo,
        DWORD dwGlobalInfoSize,
        LPBYTE pClientInterfaceInfo,
        DWORD dwClientInterfaceInfoSize,
        LPWSTR lpwsDLLPath,
        HANDLE *phRouterTransport)
{
  BYTE *v9; // rdi
  DWORD result; // eax
  DWORD Transports; // edi
  _QWORD *v14; // r14
  _DWORD *v15; // rdx
  DWORD v16; // esi
  HANDLE ProcessHeap; // rax
  _OWORD *v18; // rax
  _OWORD *v19; // rdi
  HKEY *v20; // r15
  PWSTR v21; // rax
  _QWORD *v22; // rcx
  BYTE Data[8]; // [rsp+50h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-90h] BYREF
  LPBYTE pGlobalInfoa; // [rsp+60h] [rbp-88h]
  LPWSTR v26; // [rsp+68h] [rbp-80h]
  LPBYTE v27; // [rsp+70h] [rbp-78h]
  wchar_t pszDest[12]; // [rsp+78h] [rbp-70h] BYREF

  v9 = pGlobalInfo;
  pGlobalInfoa = pGlobalInfo;
  *(_DWORD *)Data = dwTransportId;
  v27 = pClientInterfaceInfo;
  v26 = lpwsDLLPath;
  if ( !phRouterTransport )
    return 87;
  *phRouterTransport = 0;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( !*((_DWORD *)hMprConfig + 24)
      || (unsigned int)TimeStampChanged(*((_QWORD *)hMprConfig + 5), (char *)hMprConfig + 48) )
    {
      Transports = LoadTransports(hMprConfig);
      if ( Transports )
      {
        LeaveCriticalSection(&CfgLock);
        return Transports;
      }
      v9 = pGlobalInfoa;
      *((_DWORD *)hMprConfig + 24) = 1;
    }
    v14 = (_QWORD *)*((_QWORD *)hMprConfig + 10);
    if ( v14 == (_QWORD *)((char *)hMprConfig + 80) )
      goto LABEL_16;
    do
    {
      v15 = v14 - 4;
      if ( !*((_DWORD *)v14 - 2) && *v15 >= *(_DWORD *)Data )
        break;
      v14 = (_QWORD *)*v14;
    }
    while ( v14 != (_QWORD *)((char *)hMprConfig + 80) );
    if ( v15 && *v15 == *(_DWORD *)Data )
    {
      *phRouterTransport = v15;
      v16 = MprConfigTransportSetInfo(
              hMprConfig,
              v15,
              v9,
              dwGlobalInfoSize,
              pClientInterfaceInfo,
              dwClientInterfaceInfoSize,
              lpwsDLLPath);
    }
    else
    {
LABEL_16:
      ProcessHeap = GetProcessHeap();
      v18 = HeapAlloc(ProcessHeap, 0, 0x30u);
      v19 = v18;
      if ( v18 )
      {
        dwDisposition = 0;
        *v18 = 0;
        v20 = (HKEY *)((char *)hMprConfig + 40);
        v18[1] = 0;
        v18[2] = 0;
        *(_DWORD *)v18 = *(_DWORD *)Data;
        if ( *((_QWORD *)hMprConfig + 5)
          || (v16 = AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"RouterManagers", 1, (HKEY *)hMprConfig + 5)) == 0 )
        {
          if ( !lpwsTransportName || !lstrlenW(lpwsTransportName) )
          {
            if ( *(_DWORD *)Data == 33 )
            {
              lpwsTransportName = L"IP";
            }
            else if ( *(_DWORD *)Data == 87 )
            {
              lpwsTransportName = L"Ipv6";
            }
            else
            {
              StringCbPrintfW(pszDest, 0x14u, L"%d");
              lpwsTransportName = pszDest;
            }
          }
          v21 = StrDupW(lpwsTransportName);
          *((_QWORD *)v19 + 1) = v21;
          if ( v21 )
          {
            v16 = RegCreateKeyExW(*v20, lpwsTransportName, 0, 0, 0, 0x3001Fu, 0, (PHKEY)v19 + 2, &dwDisposition);
            if ( !v16 )
            {
              UpdateTimeStamp(*v20, (PFILETIME)hMprConfig + 6);
              v22 = (_QWORD *)v14[1];
              if ( (_QWORD *)*v22 != v14 )
                __fastfail(3u);
              *((_QWORD *)v19 + 4) = v14;
              *((_QWORD *)v19 + 5) = v22;
              *v22 = v19 + 2;
              v14[1] = v19 + 2;
              v16 = RegSetValueExW(*((HKEY *)v19 + 2), L"ProtocolId", 0, 4u, Data, 4u);
              if ( !v16 )
              {
                v16 = MprConfigTransportSetInfo(
                        hMprConfig,
                        v19,
                        pGlobalInfoa,
                        dwGlobalInfoSize,
                        v27,
                        dwClientInterfaceInfoSize,
                        v26);
                if ( !v16 )
                {
                  *phRouterTransport = v19;
                  LeaveCriticalSection(&CfgLock);
                  return 0;
                }
              }
              MprConfigTransportDelete(hMprConfig, v19);
              goto LABEL_37;
            }
          }
          else
          {
            v16 = 8;
          }
        }
        LeaveCriticalSection(&CfgLock);
        FreeTransport(v19);
        return v16;
      }
      v16 = 8;
    }
LABEL_37:
    LeaveCriticalSection(&CfgLock);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x180027da0  push    rbx
0x180027da2  push    rbp
0x180027da3  push    rsi
0x180027da4  push    rdi
0x180027da5  push    r12
0x180027da7  push    r13
0x180027da9  push    r14
0x180027dab  push    r15
0x180027dad  sub     rsp, 0A8h
0x180027db4  mov     rax, cs:__security_cookie
0x180027dbb  xor     rax, rsp
0x180027dbe  mov     [rsp+0E8h+var_58], rax
0x180027dc6  mov     r12, [rsp+0E8h+phRouterTransport]
0x180027dce  xor     r13d, r13d
0x180027dd1  mov     rsi, [rsp+0E8h+pClientInterfaceInfo]
0x180027dd9  mov     rdi, r9
0x180027ddc  mov     r15, [rsp+0E8h+lpwsDLLPath]
0x180027de4  mov     rbp, r8
0x180027de7  mov     [rsp+0E8h+pGlobalInfo], r9
0x180027dec  mov     rbx, rcx
0x180027def  mov     dword ptr [rsp+0E8h+Data], edx
0x180027df3  mov     [rsp+0E8h+var_78], rsi
0x180027df8  mov     [rsp+0E8h+var_80], r15
0x180027dfd  test    r12, r12
0x180027e00  jnz     short loc_180027E0C
0x180027e02  lea     eax, [r12+57h]
0x180027e07  jmp     loc_1800280CB
0x180027e0c  mov     [r12], r13
0x180027e10  call    MprConfigServerValidateCb
0x180027e15  test    eax, eax
0x180027e17  jnz     loc_1800280CB
0x180027e1d  lea     rcx, CfgLock; lpCriticalSection
0x180027e24  call    cs:__imp_EnterCriticalSection
0x180027e2a  cmp     [rbx+60h], r13d
0x180027e2e  jz      short loc_180027E41
0x180027e30  mov     rcx, [rbx+28h]
0x180027e34  lea     rdx, [rbx+30h]
0x180027e38  call    TimeStampChanged
0x180027e3d  test    eax, eax
0x180027e3f  jz      short loc_180027E6F
0x180027e41  mov     rcx, rbx
0x180027e44  call    LoadTransports
0x180027e49  mov     edi, eax
0x180027e4b  test    eax, eax
0x180027e4d  jz      short loc_180027E63
0x180027e4f  lea     rcx, CfgLock; lpCriticalSection
0x180027e56  call    cs:__imp_LeaveCriticalSection
0x180027e5c  mov     eax, edi
0x180027e5e  jmp     loc_1800280CB
0x180027e63  mov     rdi, [rsp+0E8h+pGlobalInfo]
0x180027e68  mov     dword ptr [rbx+60h], 1
0x180027e6f  lea     rax, [rbx+50h]
0x180027e73  mov     r14, [rax]
0x180027e76  cmp     r14, rax
0x180027e79  jz      short loc_180027ED4
0x180027e7b  mov     r9d, dword ptr [rsp+0E8h+Data]
0x180027e80  lea     rdx, [r14-20h]; hRouterTransport
0x180027e84  cmp     [rdx+18h], r13d
0x180027e88  jnz     short loc_180027E8F
0x180027e8a  cmp     [rdx], r9d
0x180027e8d  jnb     short loc_180027E97
0x180027e8f  mov     r14, [r14]
0x180027e92  cmp     r14, rax
0x180027e95  jnz     short loc_180027E80
0x180027e97  test    rdx, rdx
0x180027e9a  jz      short loc_180027ED4
0x180027e9c  cmp     [rdx], r9d
0x180027e9f  jnz     short loc_180027ED4
0x180027ea1  mov     eax, [rsp+0E8h+dwClientInterfaceInfoSize]
0x180027ea8  mov     r8, rdi; pGlobalInfo
0x180027eab  mov     r9d, [rsp+0E8h+dwGlobalInfoSize]; dwGlobalInfoSize
0x180027eb3  mov     rcx, rbx; hMprConfig
0x180027eb6  mov     [rsp+0E8h+var_B8], r15; lpwsDLLPath
0x180027ebb  mov     [rsp+0E8h+samDesired], eax; dwClientInterfaceInfoSize
0x180027ebf  mov     [rsp+0E8h+lpData], rsi; pClientInterfaceInfo
0x180027ec4  mov     [r12], rdx
0x180027ec8  call    MprConfigTransportSetInfo
0x180027ecd  mov     esi, eax
0x180027ecf  jmp     loc_1800280BC
0x180027ed4  call    cs:__imp_GetProcessHeap
0x180027eda  xor     edx, edx; dwFlags
0x180027edc  mov     rcx, rax; hHeap
0x180027edf  lea     r8d, [rdx+30h]; dwBytes
0x180027ee3  call    cs:__imp_HeapAlloc
0x180027ee9  mov     rdi, rax
0x180027eec  test    rax, rax
0x180027eef  jnz     short loc_180027EF9
0x180027ef1  lea     esi, [rax+8]
0x180027ef4  jmp     loc_1800280BC
0x180027ef9  xorps   xmm0, xmm0
0x180027efc  mov     [rsp+0E8h+dwDisposition], r13d
0x180027f01  movups  xmmword ptr [rax], xmm0
0x180027f04  lea     r15, [rbx+28h]
0x180027f08  movups  xmmword ptr [rax+10h], xmm0
0x180027f0c  movups  xmmword ptr [rax+20h], xmm0
0x180027f10  mov     eax, dword ptr [rsp+0E8h+Data]
0x180027f14  mov     [rdi], eax
0x180027f16  cmp     [r15], r13
0x180027f19  jnz     short loc_180027F3E
0x180027f1b  mov     rcx, [rbx+10h]; hKey
0x180027f1f  lea     rdx, c_szRouterManagers; "RouterManagers"
0x180027f26  mov     r9, r15
0x180027f29  mov     r8d, 1
0x180027f2f  call    AccessRouterSubkey
0x180027f34  mov     esi, eax
0x180027f36  test    eax, eax
0x180027f38  jnz     loc_180027FE8
0x180027f3e  test    rbp, rbp
0x180027f41  jz      short loc_180027F50
0x180027f43  mov     rcx, rbp; lpString
0x180027f46  call    cs:__imp_lstrlenW
0x180027f4c  test    eax, eax
0x180027f4e  jnz     short loc_180027F8E
0x180027f50  mov     r9d, dword ptr [rsp+0E8h+Data]
0x180027f55  cmp     r9d, 21h ; '!'
0x180027f59  jnz     short loc_180027F64
0x180027f5b  lea     rbp, c_szIP; "IP"
0x180027f62  jmp     short loc_180027F8E
0x180027f64  cmp     r9d, 57h ; 'W'
0x180027f68  jnz     short loc_180027F73
0x180027f6a  lea     rbp, c_szIPv6; "Ipv6"
0x180027f71  jmp     short loc_180027F8E
0x180027f73  lea     r8, aD; "%d"
0x180027f7a  mov     edx, 14h; cbDest
0x180027f7f  lea     rcx, [rsp+0E8h+pszDest]; pszDest
0x180027f84  call    StringCbPrintfW
0x180027f89  lea     rbp, [rsp+0E8h+pszDest]
0x180027f8e  mov     rcx, rbp; pszSrch
0x180027f91  call    StrDupW
0x180027f96  mov     [rdi+8], rax
0x180027f9a  test    rax, rax
0x180027f9d  jnz     short loc_180027FA4
0x180027f9f  lea     esi, [rax+8]
0x180027fa2  jmp     short loc_180027FE8
0x180027fa4  mov     rcx, [r15]; hKey
0x180027fa7  lea     rax, [rsp+0E8h+dwDisposition]
0x180027fac  mov     [rsp+0E8h+lpdwDisposition], rax; lpdwDisposition
0x180027fb1  lea     r13, [rdi+10h]
0x180027fb5  mov     [rsp+0E8h+phkResult], r13; phkResult
0x180027fba  xor     r9d, r9d; lpClass
0x180027fbd  mov     [rsp+0E8h+var_B8], 0; lpSecurityAttributes
0x180027fc6  xor     r8d, r8d; Reserved
0x180027fc9  mov     [rsp+0E8h+samDesired], 3001Fh; samDesired
0x180027fd1  mov     rdx, rbp; lpSubKey
0x180027fd4  mov     dword ptr [rsp+0E8h+lpData], 0; dwOptions
0x180027fdc  call    cs:__imp_RegCreateKeyExW
0x180027fe2  mov     esi, eax
0x180027fe4  test    eax, eax
0x180027fe6  jz      short loc_180028002
0x180027fe8  lea     rcx, CfgLock; lpCriticalSection
0x180027fef  call    cs:__imp_LeaveCriticalSection
0x180027ff5  mov     rcx, rdi
0x180027ff8  call    FreeTransport
0x180027ffd  jmp     loc_1800280C9
0x180028002  mov     rcx, [r15]; hKey
0x180028005  lea     rdx, [rbx+30h]; lpftLastWriteTime
0x180028009  call    UpdateTimeStamp
0x18002800e  mov     rcx, [r14+8]
0x180028012  cmp     [rcx], r14
0x180028015  jz      short loc_18002801E
0x180028017  mov     ecx, 3
0x18002801c  int     29h; Win8: RtlFailFast(ecx)
0x18002801e  lea     rax, [rdi+20h]
0x180028022  mov     r9d, 4; dwType
0x180028028  mov     [rax], r14
0x18002802b  lea     rdx, c_szProtocolId; "ProtocolId"
0x180028032  mov     [rax+8], rcx
0x180028036  xor     r8d, r8d; Reserved
0x180028039  mov     [rcx], rax
0x18002803c  mov     [r14+8], rax
0x180028040  lea     rax, [rsp+0E8h+Data]
0x180028045  mov     rcx, [r13+0]; hKey
0x180028049  mov     [rsp+0E8h+samDesired], r9d; cbData
0x18002804e  mov     [rsp+0E8h+lpData], rax; lpData
0x180028053  call    cs:__imp_RegSetValueExW
0x180028059  mov     esi, eax
0x18002805b  test    eax, eax
0x18002805d  jnz     short loc_1800280B1
0x18002805f  mov     rax, [rsp+0E8h+var_80]
0x180028064  mov     rdx, rdi; hRouterTransport
0x180028067  mov     r9d, [rsp+0E8h+dwGlobalInfoSize]; dwGlobalInfoSize
0x18002806f  mov     rcx, rbx; hMprConfig
0x180028072  mov     r8, [rsp+0E8h+pGlobalInfo]; pGlobalInfo
0x180028077  mov     [rsp+0E8h+var_B8], rax; lpwsDLLPath
0x18002807c  mov     eax, [rsp+0E8h+dwClientInterfaceInfoSize]
0x180028083  mov     [rsp+0E8h+samDesired], eax; dwClientInterfaceInfoSize
0x180028087  mov     rax, [rsp+0E8h+var_78]
0x18002808c  mov     [rsp+0E8h+lpData], rax; pClientInterfaceInfo
0x180028091  call    MprConfigTransportSetInfo
0x180028096  mov     esi, eax
0x180028098  test    eax, eax
0x18002809a  jnz     short loc_1800280B1
0x18002809c  lea     rcx, CfgLock; lpCriticalSection
0x1800280a3  mov     [r12], rdi
0x1800280a7  call    cs:__imp_LeaveCriticalSection
0x1800280ad  xor     eax, eax
0x1800280af  jmp     short loc_1800280CB
0x1800280b1  mov     rdx, rdi; hRouterTransport
0x1800280b4  mov     rcx, rbx; hMprConfig
0x1800280b7  call    MprConfigTransportDelete
0x1800280bc  lea     rcx, CfgLock; lpCriticalSection
0x1800280c3  call    cs:__imp_LeaveCriticalSection
0x1800280c9  mov     eax, esi
0x1800280cb  mov     rcx, [rsp+0E8h+var_58]
0x1800280d3  xor     rcx, rsp; StackCookie
0x1800280d6  call    __security_check_cookie
0x1800280db  add     rsp, 0A8h
0x1800280e2  pop     r15
0x1800280e4  pop     r14
0x1800280e6  pop     r13
0x1800280e8  pop     r12
0x1800280ea  pop     rdi
0x1800280eb  pop     rsi
0x1800280ec  pop     rbp
0x1800280ed  pop     rbx
0x1800280ee  retn
```
