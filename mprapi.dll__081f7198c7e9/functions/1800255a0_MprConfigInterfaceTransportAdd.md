# MprConfigInterfaceTransportAdd

- ea: `0x1800255a0`
- end: `0x18002586e`
- name: `MprConfigInterfaceTransportAdd`
- size: `718`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, HANDLE hRouterInterface, DWORD dwTransportId, LPWSTR lpwsTransportName, LPBYTE pInterfaceInfo, DWORD dwInterfaceInfoSize, HANDLE *phRouterIfTransport)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180036158`

## callees

- `0x180009868`
- `0x180018470`
- `0x18002201c`
- `0x1800255a0`
- `0x180025cb0`
- `0x180025d60`
- `0x180027d5c`
- `0x1800291b4`
- `0x180029414`
- `0x18002998c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025792`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025792`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025610`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002569a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002569a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800256a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800256a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800257cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800257cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025777`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025777`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800256e0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800256e0`

## string_xrefs

- `0x1800257bb`: `ProtocolId`

## pseudocode

```c
DWORD __stdcall MprConfigInterfaceTransportAdd(
        HANDLE hMprConfig,
        HANDLE hRouterInterface,
        DWORD dwTransportId,
        LPWSTR lpwsTransportName,
        LPBYTE pInterfaceInfo,
        DWORD dwInterfaceInfoSize,
        HANDLE *phRouterIfTransport)
{
  DWORD result; // eax
  DWORD IfTransports; // ebx
  _QWORD *v12; // r14
  _DWORD *v13; // r8
  HANDLE ProcessHeap; // rax
  _OWORD *v15; // rax
  _OWORD *v16; // rbx
  PWSTR v17; // rax
  LSTATUS v18; // esi
  _QWORD *v19; // rcx
  DWORD v20; // esi
  BYTE Data[8]; // [rsp+50h] [rbp-68h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-60h] BYREF
  wchar_t pszDest[12]; // [rsp+60h] [rbp-58h] BYREF

  *(_DWORD *)Data = dwTransportId;
  if ( hRouterInterface && phRouterIfTransport )
  {
    *phRouterIfTransport = 0;
    result = MprConfigServerValidateCb(hMprConfig);
    if ( result )
      return result;
    EnterCriticalSection(&CfgLock);
    if ( !*((_DWORD *)hRouterInterface + 24)
      || (unsigned int)TimeStampChanged(*((_QWORD *)hRouterInterface + 5), (char *)hRouterInterface + 48) )
    {
      IfTransports = LoadIfTransports(hRouterInterface);
      if ( IfTransports )
        goto LABEL_33;
      *((_DWORD *)hRouterInterface + 24) = 1;
    }
    v12 = (_QWORD *)*((_QWORD *)hRouterInterface + 10);
    if ( v12 == (_QWORD *)((char *)hRouterInterface + 80) )
      goto LABEL_15;
    do
    {
      v13 = v12 - 4;
      if ( !*((_DWORD *)v12 - 2) && *v13 >= *(_DWORD *)Data )
        break;
      v12 = (_QWORD *)*v12;
    }
    while ( v12 != (_QWORD *)((char *)hRouterInterface + 80) );
    if ( v13 && *v13 == *(_DWORD *)Data )
    {
      *phRouterIfTransport = v13;
      IfTransports = MprConfigInterfaceTransportSetInfo(
                       hMprConfig,
                       hRouterInterface,
                       v13,
                       pInterfaceInfo,
                       dwInterfaceInfoSize);
    }
    else
    {
LABEL_15:
      ProcessHeap = GetProcessHeap();
      v15 = HeapAlloc(ProcessHeap, 0, 0x30u);
      v16 = v15;
      if ( v15 )
      {
        dwDisposition = 0;
        *v15 = 0;
        v15[1] = 0;
        v15[2] = 0;
        *(_DWORD *)v15 = *(_DWORD *)Data;
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
        v17 = StrDupW(lpwsTransportName);
        *((_QWORD *)v16 + 1) = v17;
        if ( v17 )
        {
          v18 = RegCreateKeyExW(
                  *((HKEY *)hRouterInterface + 5),
                  lpwsTransportName,
                  0,
                  0,
                  0,
                  0x3001Fu,
                  0,
                  (PHKEY)v16 + 2,
                  &dwDisposition);
          if ( !v18 )
          {
            UpdateTimeStamp(*((HKEY *)hRouterInterface + 5), (PFILETIME)hRouterInterface + 6);
            RegSetValueExW(*((HKEY *)v16 + 2), L"ProtocolId", 0, 4u, Data, 4u);
            v19 = (_QWORD *)v12[1];
            if ( (_QWORD *)*v19 != v12 )
              __fastfail(3u);
            *((_QWORD *)v16 + 5) = v19;
            *((_QWORD *)v16 + 4) = v12;
            *v19 = v16 + 2;
            v12[1] = v16 + 2;
            v20 = MprConfigInterfaceTransportSetInfo(
                    hMprConfig,
                    hRouterInterface,
                    v16,
                    pInterfaceInfo,
                    dwInterfaceInfoSize);
            if ( v20 )
            {
              MprConfigInterfaceTransportRemove(hMprConfig, hRouterInterface, v16);
              IfTransports = v20;
            }
            else
            {
              *phRouterIfTransport = v16;
              IfTransports = 0;
            }
            goto LABEL_33;
          }
        }
        else
        {
          v18 = 8;
        }
        FreeTransport(v16);
        LeaveCriticalSection(&CfgLock);
        return v18;
      }
      IfTransports = 8;
    }
LABEL_33:
    LeaveCriticalSection(&CfgLock);
    return IfTransports;
  }
  return 87;
}

```

## disassembly

```asm
0x1800255a0  mov     [rsp+arg_0], rbx
0x1800255a5  push    rbp
0x1800255a6  push    rsi
0x1800255a7  push    rdi
0x1800255a8  push    r12
0x1800255aa  push    r13
0x1800255ac  push    r14
0x1800255ae  push    r15
0x1800255b0  sub     rsp, 80h
0x1800255b7  mov     rax, cs:__security_cookie
0x1800255be  xor     rax, rsp
0x1800255c1  mov     [rsp+0B8h+var_40], rax
0x1800255c6  mov     r13, [rsp+0B8h+pInterfaceInfo]
0x1800255ce  xor     r12d, r12d
0x1800255d1  mov     r15, [rsp+0B8h+phRouterIfTransport]
0x1800255d9  mov     rsi, r9
0x1800255dc  mov     dword ptr [rsp+0B8h+Data], r8d
0x1800255e1  mov     rdi, rdx
0x1800255e4  mov     rbp, rcx
0x1800255e7  test    rdx, rdx
0x1800255ea  jz      loc_180025841
0x1800255f0  test    r15, r15
0x1800255f3  jz      loc_180025841
0x1800255f9  mov     [r15], r12
0x1800255fc  call    MprConfigServerValidateCb
0x180025601  test    eax, eax
0x180025603  jnz     loc_180025846
0x180025609  lea     rcx, CfgLock; lpCriticalSection
0x180025610  call    cs:__imp_EnterCriticalSection
0x180025616  cmp     [rdi+60h], r12d
0x18002561a  jz      short loc_18002562D
0x18002561c  mov     rcx, [rdi+28h]
0x180025620  lea     rdx, [rdi+30h]
0x180025624  call    TimeStampChanged
0x180025629  test    eax, eax
0x18002562b  jz      short loc_180025646
0x18002562d  mov     rcx, rdi
0x180025630  call    LoadIfTransports
0x180025635  mov     ebx, eax
0x180025637  test    eax, eax
0x180025639  jnz     loc_180025830
0x18002563f  mov     dword ptr [rdi+60h], 1
0x180025646  lea     rax, [rdi+50h]
0x18002564a  mov     r14, [rax]
0x18002564d  cmp     r14, rax
0x180025650  jz      short loc_18002569A
0x180025652  mov     ecx, dword ptr [rsp+0B8h+Data]
0x180025656  lea     r8, [r14-20h]; hRouterIfTransport
0x18002565a  cmp     [r8+18h], r12d
0x18002565e  jnz     short loc_180025665
0x180025660  cmp     [r8], ecx
0x180025663  jnb     short loc_18002566D
0x180025665  mov     r14, [r14]
0x180025668  cmp     r14, rax
0x18002566b  jnz     short loc_180025656
0x18002566d  test    r8, r8
0x180025670  jz      short loc_18002569A
0x180025672  cmp     [r8], ecx
0x180025675  jnz     short loc_18002569A
0x180025677  mov     eax, [rsp+0B8h+dwInterfaceInfoSize]
0x18002567e  mov     r9, r13; pInterfaceInfo
0x180025681  mov     rdx, rdi; hRouterInterface
0x180025684  mov     [rsp+0B8h+dwOptions], eax; dwInterfaceInfoSize
0x180025688  mov     rcx, rbp; hMprConfig
0x18002568b  mov     [r15], r8
0x18002568e  call    MprConfigInterfaceTransportSetInfo
0x180025693  mov     ebx, eax
0x180025695  jmp     loc_180025830
0x18002569a  call    cs:__imp_GetProcessHeap
0x1800256a0  xor     edx, edx; dwFlags
0x1800256a2  mov     rcx, rax; hHeap
0x1800256a5  lea     r8d, [rdx+30h]; dwBytes
0x1800256a9  call    cs:__imp_HeapAlloc
0x1800256af  mov     rbx, rax
0x1800256b2  test    rax, rax
0x1800256b5  jnz     short loc_1800256BF
0x1800256b7  lea     ebx, [rax+8]
0x1800256ba  jmp     loc_180025830
0x1800256bf  mov     [rsp+0B8h+dwDisposition], r12d
0x1800256c4  xorps   xmm0, xmm0
0x1800256c7  movups  xmmword ptr [rax], xmm0
0x1800256ca  movups  xmmword ptr [rax+10h], xmm0
0x1800256ce  movups  xmmword ptr [rax+20h], xmm0
0x1800256d2  mov     eax, dword ptr [rsp+0B8h+Data]
0x1800256d6  mov     [rbx], eax
0x1800256d8  test    rsi, rsi
0x1800256db  jz      short loc_1800256EA
0x1800256dd  mov     rcx, rsi; lpString
0x1800256e0  call    cs:__imp_lstrlenW
0x1800256e6  test    eax, eax
0x1800256e8  jnz     short loc_180025728
0x1800256ea  mov     r9d, dword ptr [rsp+0B8h+Data]
0x1800256ef  cmp     r9d, 21h ; '!'
0x1800256f3  jnz     short loc_1800256FE
0x1800256f5  lea     rsi, c_szIP; "IP"
0x1800256fc  jmp     short loc_180025728
0x1800256fe  cmp     r9d, 57h ; 'W'
0x180025702  jnz     short loc_18002570D
0x180025704  lea     rsi, c_szIPv6; "Ipv6"
0x18002570b  jmp     short loc_180025728
0x18002570d  lea     r8, aD; "%d"
0x180025714  mov     edx, 14h; cbDest
0x180025719  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x18002571e  call    StringCbPrintfW
0x180025723  lea     rsi, [rsp+0B8h+pszDest]
0x180025728  mov     rcx, rsi; pszSrch
0x18002572b  call    StrDupW
0x180025730  mov     [rbx+8], rax
0x180025734  test    rax, rax
0x180025737  jnz     short loc_18002573E
0x180025739  lea     esi, [rax+8]
0x18002573c  jmp     short loc_180025783
0x18002573e  mov     rcx, [rdi+28h]; hKey
0x180025742  lea     rax, [rsp+0B8h+dwDisposition]
0x180025747  mov     [rsp+0B8h+lpdwDisposition], rax; lpdwDisposition
0x18002574c  lea     r12, [rbx+10h]
0x180025750  mov     [rsp+0B8h+phkResult], r12; phkResult
0x180025755  xor     r9d, r9d; lpClass
0x180025758  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180025761  xor     r8d, r8d; Reserved
0x180025764  mov     [rsp+0B8h+samDesired], 3001Fh; samDesired
0x18002576c  mov     rdx, rsi; lpSubKey
0x18002576f  mov     [rsp+0B8h+dwOptions], 0; dwOptions
0x180025777  call    cs:__imp_RegCreateKeyExW
0x18002577d  mov     esi, eax
0x18002577f  test    eax, eax
0x180025781  jz      short loc_18002579F
0x180025783  mov     rcx, rbx
0x180025786  call    FreeTransport
0x18002578b  lea     rcx, CfgLock; lpCriticalSection
0x180025792  call    cs:__imp_LeaveCriticalSection
0x180025798  mov     eax, esi
0x18002579a  jmp     loc_180025846
0x18002579f  mov     rcx, [rdi+28h]; hKey
0x1800257a3  lea     rdx, [rdi+30h]; lpftLastWriteTime
0x1800257a7  call    UpdateTimeStamp
0x1800257ac  mov     rcx, [r12]; hKey
0x1800257b0  lea     rax, [rsp+0B8h+Data]
0x1800257b5  mov     r9d, 4; dwType
0x1800257bb  lea     rdx, c_szProtocolId; "ProtocolId"
0x1800257c2  mov     [rsp+0B8h+samDesired], r9d; cbData
0x1800257c7  xor     r8d, r8d; Reserved
0x1800257ca  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x1800257cf  call    cs:__imp_RegSetValueExW
0x1800257d5  mov     rcx, [r14+8]
0x1800257d9  cmp     [rcx], r14
0x1800257dc  jz      short loc_1800257E5
0x1800257de  mov     ecx, 3
0x1800257e3  int     29h; Win8: RtlFailFast(ecx)
0x1800257e5  lea     rax, [rbx+20h]
0x1800257e9  mov     r9, r13; pInterfaceInfo
0x1800257ec  mov     [rax+8], rcx
0x1800257f0  mov     r8, rbx; hRouterIfTransport
0x1800257f3  mov     [rax], r14
0x1800257f6  mov     rdx, rdi; hRouterInterface
0x1800257f9  mov     [rcx], rax
0x1800257fc  mov     rcx, rbp; hMprConfig
0x1800257ff  mov     [r14+8], rax
0x180025803  mov     eax, [rsp+0B8h+dwInterfaceInfoSize]
0x18002580a  mov     [rsp+0B8h+dwOptions], eax; dwInterfaceInfoSize
0x18002580e  call    MprConfigInterfaceTransportSetInfo
0x180025813  mov     esi, eax
0x180025815  test    eax, eax
0x180025817  jz      short loc_18002582B
0x180025819  mov     r8, rbx; hRouterIfTransport
0x18002581c  mov     rdx, rdi; hRouterInterface
0x18002581f  mov     rcx, rbp; hMprConfig
0x180025822  call    MprConfigInterfaceTransportRemove
0x180025827  mov     ebx, esi
0x180025829  jmp     short loc_180025830
0x18002582b  mov     [r15], rbx
0x18002582e  xor     ebx, ebx
0x180025830  lea     rcx, CfgLock; lpCriticalSection
0x180025837  call    cs:__imp_LeaveCriticalSection
0x18002583d  mov     eax, ebx
0x18002583f  jmp     short loc_180025846
0x180025841  mov     eax, 57h ; 'W'
0x180025846  mov     rcx, [rsp+0B8h+var_40]
0x18002584b  xor     rcx, rsp; StackCookie
0x18002584e  call    __security_check_cookie
0x180025853  mov     rbx, [rsp+0B8h+arg_0]
0x18002585b  add     rsp, 80h
0x180025862  pop     r15
0x180025864  pop     r14
0x180025866  pop     r13
0x180025868  pop     r12
0x18002586a  pop     rdi
0x18002586b  pop     rsi
0x18002586c  pop     rbp
0x18002586d  retn
```
