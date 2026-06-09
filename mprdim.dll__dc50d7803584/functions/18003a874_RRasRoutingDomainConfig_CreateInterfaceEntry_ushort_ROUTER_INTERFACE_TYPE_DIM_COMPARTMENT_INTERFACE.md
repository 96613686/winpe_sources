# RRasRoutingDomainConfig::CreateInterfaceEntry(ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)

- ea: `0x18003a874`
- end: `0x18003ac55`
- name: `?CreateInterfaceEntry@RRasRoutingDomainConfig@@QEAAKPEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, BYTE *lpData, enum _ROUTER_INTERFACE_TYPE, struct _DIM_COMPARTMENT_INTERFACE *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a4d8`
- `0x18003a684`
- `0x18003ae88`

## callees

- `0x18001851c`
- `0x180037e0c`
- `0x18003a874`
- `0x18003ac5c`
- `0x18003eda8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18003aa08`
- `ADVAPI32!RegSetValueExW` at `0x18003aa60`
- `ADVAPI32!RegSetValueExW` at `0x18003aaa2`
- `ADVAPI32!RegSetValueExW` at `0x18003aa08`
- `ADVAPI32!RegSetValueExW` at `0x18003aa60`
- `ADVAPI32!RegSetValueExW` at `0x18003aaa2`
- `ADVAPI32!RegCloseKey` at `0x18003a9c6`
- `ADVAPI32!RegCloseKey` at `0x18003ac01`
- `ADVAPI32!RegCloseKey` at `0x18003ac2c`
- `ADVAPI32!RegCloseKey` at `0x18003a9c6`
- `ADVAPI32!RegCloseKey` at `0x18003ac01`
- `ADVAPI32!RegCloseKey` at `0x18003ac2c`
- `ADVAPI32!RegCreateKeyExW` at `0x18003a9aa`
- `ADVAPI32!RegCreateKeyExW` at `0x18003a9aa`
- `ADVAPI32!RegDeleteKeyW` at `0x18003ac1c`
- `ADVAPI32!RegDeleteKeyW` at `0x18003ac1c`

## string_xrefs

- `0x18003a92a`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003aba9`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003a93c`: `Error %d occurred while opening interfaces key under registry key %s. #1`
- `0x18003abb7`: `Failed to create sub-key '%s' under '%s': %d`
- `0x18003aa28`: `RRasRoutingDomainConfig::CreateInterfaceEntry`
- `0x18003ab34`: `RRasRoutingDomainConfig::CreateInterfaceEntry`
- `0x18003aa2f`: `%s: Couldn't write value %ws: %d`
- `0x18003ab22`: `%s: Couldn't write domain specific info to registry : %d`
- `0x18003ab6f`: `%s: Couldn't create IPv4 transport : %d`
- `0x18003ab97`: `%s: Couldn't create IPv6 transport : %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CreateInterfaceEntry(
        RRasRoutingDomainConfig *this,
        BYTE *lpData,
        enum _ROUTER_INTERFACE_TYPE a3,
        struct _DIM_COMPARTMENT_INTERFACE *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int i; // edi
  LSTATUS v10; // eax
  __int64 v11; // rax
  const WCHAR *v12; // r9
  wchar_t *v13; // r8
  const wchar_t *v14; // rdx
  unsigned int InterfaceTransportEntry; // eax
  RRasRoutingDomainConfig *v16; // rcx
  const wchar_t *v17; // rdx
  RRasRoutingDomainConfig *v18; // rcx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v25[16]; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[24]; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v28; // [rsp+9Ch] [rbp-64h]
  int v29; // [rsp+ACh] [rbp-54h]
  __int64 v30; // [rsp+B0h] [rbp-50h]
  wchar_t pszDest[8]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v32; // [rsp+360h] [rbp+260h]
  int v33; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v34[2044]; // [rsp+374h] [rbp+274h] BYREF

  *(_DWORD *)Data = a3;
  phkResult = 0;
  dwDisposition = 0;
  v26 = 0;
  v32 = 0;
  *(_OWORD *)pszDest = 0;
  memset_0(v27, 0, 0x2C4u);
  *(_DWORD *)v25 = 1;
  hKey = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v7 = RRasRoutingDomainConfig::OpenInterfacesKey(this, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v33) = 0;
      FormatRRASErrorString(
        &v33,
        L"Error %d occurred while opening interfaces key under registry key %s. #1",
        v7,
        L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
      goto LABEL_35;
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      StringCbPrintfW(pszDest, 0x18u, L"%d", i);
      v10 = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x3001Fu, 0, &phkResult, &dwDisposition);
      v8 = v10;
      if ( v10 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          v12 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
          v13 = pszDest;
          v14 = L"Failed to create sub-key '%s' under '%s': %d";
          goto LABEL_34;
        }
        goto LABEL_36;
      }
      if ( dwDisposition == 1 )
        break;
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&lpData[2 * v11] );
    v10 = RegSetValueExW(phkResult, L"InterfaceName", 0, 1u, lpData, 2 * v11 + 2);
    v8 = v10;
    if ( v10 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_36;
      v12 = L"InterfaceName";
      goto LABEL_13;
    }
    v10 = RegSetValueExW(phkResult, L"Type", 0, 4u, Data, 4u);
    v8 = v10;
    if ( v10 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_36;
      v12 = L"Type";
      goto LABEL_13;
    }
    v10 = RegSetValueExW(phkResult, L"Enabled", 0, 4u, v25, 4u);
    v8 = v10;
    if ( !v10 )
    {
      memset_0(&v26, 0, 0x2C8u);
      v28 = *(_OWORD *)((char *)this + 516);
      if ( *(_DWORD *)Data == 3 )
      {
        v29 = *(_DWORD *)a4;
        v30 = *((_QWORD *)a4 + 1);
      }
      InterfaceTransportEntry = WriteInterfaceExtraInfo(phkResult);
      v8 = InterfaceTransportEntry;
      if ( InterfaceTransportEntry )
      {
        if ( !(_QWORD)xmmword_180071090 )
          goto LABEL_36;
        v17 = L"%s: Couldn't write domain specific info to registry : %d";
      }
      else
      {
        InterfaceTransportEntry = RRasRoutingDomainConfig::CreateInterfaceTransportEntry(v16, phkResult, 0x21u);
        v8 = InterfaceTransportEntry;
        if ( InterfaceTransportEntry )
        {
          if ( !(_QWORD)xmmword_180071090 )
            goto LABEL_36;
          v17 = L"%s: Couldn't create IPv4 transport : %d";
        }
        else
        {
          InterfaceTransportEntry = RRasRoutingDomainConfig::CreateInterfaceTransportEntry(v18, phkResult, 0x57u);
          v8 = InterfaceTransportEntry;
          if ( !InterfaceTransportEntry || !(_QWORD)xmmword_180071090 )
            goto LABEL_36;
          v17 = L"%s: Couldn't create IPv6 transport : %d";
        }
      }
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v33, v17, L"RRasRoutingDomainConfig::CreateInterfaceEntry", InterfaceTransportEntry);
      goto LABEL_35;
    }
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_36;
    v12 = L"Enabled";
LABEL_13:
    v13 = L"RRasRoutingDomainConfig::CreateInterfaceEntry";
    v14 = L"%s: Couldn't write value %ws: %d";
LABEL_34:
    dwOptions[0] = v10;
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, v14, v13, v12, *(_QWORD *)dwOptions);
LABEL_35:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v33);
  }
LABEL_36:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    if ( v8 )
    {
      if ( !hKey )
        return v8;
      RegDeleteKeyW(hKey, pszDest);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18003a874  push    rbp
0x18003a876  push    rbx
0x18003a877  push    rsi
0x18003a878  push    rdi
0x18003a879  push    r12
0x18003a87b  push    r14
0x18003a87d  push    r15
0x18003a87f  lea     rbp, [rsp-0A80h]
0x18003a887  sub     rsp, 0B80h
0x18003a88e  mov     rax, cs:__security_cookie
0x18003a895  xor     rax, rsp
0x18003a898  mov     [rbp+0AB0h+var_40], rax
0x18003a89f  xor     r12d, r12d
0x18003a8a2  mov     dword ptr [rsp+0BB0h+Data], r8d
0x18003a8a7  mov     r14, rdx
0x18003a8aa  mov     [rsp+0BB0h+var_B60], r12
0x18003a8af  mov     r15, rcx
0x18003a8b2  mov     [rsp+0BB0h+dwDisposition], r12d
0x18003a8b7  xorps   xmm0, xmm0
0x18003a8ba  mov     [rbp+0AB0h+var_B30], r12d
0x18003a8be  xor     eax, eax
0x18003a8c0  lea     rcx, [rbp+0AB0h+var_B2C]; void *
0x18003a8c4  xor     edx, edx; Val
0x18003a8c6  mov     [rbp+0AB0h+var_850], rax
0x18003a8cd  mov     r8d, 2C4h; Size
0x18003a8d3  mov     rsi, r9
0x18003a8d6  movups  xmmword ptr [rbp+0AB0h+pszDest], xmm0
0x18003a8dd  call    memset_0
0x18003a8e2  xor     edx, edx; Val
0x18003a8e4  mov     dword ptr [rsp+0BB0h+var_B40], 1
0x18003a8ec  mov     r8d, 7FCh; Size
0x18003a8f2  mov     [rsp+0BB0h+hKey], r12
0x18003a8f7  lea     rcx, [rbp+0AB0h+var_83C]; void *
0x18003a8fe  mov     [rbp+0AB0h+var_840], r12d
0x18003a905  call    memset_0
0x18003a90a  lea     rdx, [rsp+0BB0h+hKey]; HKEY *
0x18003a90f  mov     rcx, r15; this
0x18003a912  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18003a917  mov     ebx, eax
0x18003a919  test    eax, eax
0x18003a91b  jz      short loc_18003A954
0x18003a91d  cmp     qword ptr cs:xmmword_180071090, r12
0x18003a924  jz      loc_18003ABF7
0x18003a92a  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003a931  mov     word ptr [rbp+0AB0h+var_840], r12w
0x18003a939  mov     r8d, eax
0x18003a93c  lea     rdx, aErrorDOccurred; "Error %d occurred while opening interfa"...
0x18003a943  lea     rcx, [rbp+0AB0h+var_840]
0x18003a94a  call    FormatRRASErrorString
0x18003a94f  jmp     loc_18003ABD6
0x18003a954  mov     edi, r12d
0x18003a957  mov     r9d, edi
0x18003a95a  lea     r8, aD; "%d"
0x18003a961  mov     edx, 18h; cbDest
0x18003a966  lea     rcx, [rbp+0AB0h+pszDest]; pszDest
0x18003a96d  call    StringCbPrintfW
0x18003a972  mov     rcx, [rsp+0BB0h+hKey]; hKey
0x18003a977  lea     rax, [rsp+0BB0h+dwDisposition]
0x18003a97c  mov     [rsp+0BB0h+lpdwDisposition], rax; lpdwDisposition
0x18003a981  lea     rdx, [rbp+0AB0h+pszDest]; lpSubKey
0x18003a988  lea     rax, [rsp+0BB0h+var_B60]
0x18003a98d  xor     r9d, r9d; lpClass
0x18003a990  mov     [rsp+0BB0h+phkResult], rax; phkResult
0x18003a995  xor     r8d, r8d; Reserved
0x18003a998  mov     [rsp+0BB0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003a99d  mov     [rsp+0BB0h+samDesired], 3001Fh; samDesired
0x18003a9a5  mov     [rsp+0BB0h+dwOptions], r12d; dwOptions
0x18003a9aa  call    cs:__imp_RegCreateKeyExW
0x18003a9b0  mov     ebx, eax
0x18003a9b2  test    eax, eax
0x18003a9b4  jnz     loc_18003ABA0
0x18003a9ba  cmp     [rsp+0BB0h+dwDisposition], 1
0x18003a9bf  jz      short loc_18003A9D5
0x18003a9c1  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003a9c6  call    cs:__imp_RegCloseKey
0x18003a9cc  inc     edi
0x18003a9ce  mov     [rsp+0BB0h+var_B60], r12
0x18003a9d3  jmp     short loc_18003A957
0x18003a9d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a9d9  inc     rax
0x18003a9dc  cmp     [r14+rax*2], r12w
0x18003a9e1  jnz     short loc_18003A9D9
0x18003a9e3  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003a9e8  lea     eax, ds:2[rax*2]
0x18003a9ef  mov     [rsp+0BB0h+samDesired], eax; cbData
0x18003a9f3  lea     rdx, ValueName; "InterfaceName"
0x18003a9fa  mov     r9d, 1; dwType
0x18003aa00  mov     qword ptr [rsp+0BB0h+dwOptions], r14; lpData
0x18003aa05  xor     r8d, r8d; Reserved
0x18003aa08  call    cs:__imp_RegSetValueExW
0x18003aa0e  mov     ebx, eax
0x18003aa10  test    eax, eax
0x18003aa12  jz      short loc_18003AA3B
0x18003aa14  cmp     qword ptr cs:xmmword_180071090, r12
0x18003aa1b  jz      loc_18003ABF7
0x18003aa21  lea     r9, ValueName; "InterfaceName"
0x18003aa28  lea     r8, aRrasroutingdom_25; "RRasRoutingDomainConfig::CreateInterfac"...
0x18003aa2f  lea     rdx, aSCouldnTWriteV; "%s: Couldn't write value %ws: %d"
0x18003aa36  jmp     loc_18003ABBE
0x18003aa3b  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003aa40  lea     rax, [rsp+0BB0h+Data]
0x18003aa45  mov     edi, 4
0x18003aa4a  lea     rdx, aType; "Type"
0x18003aa51  mov     [rsp+0BB0h+samDesired], edi; cbData
0x18003aa55  mov     r9d, edi; dwType
0x18003aa58  xor     r8d, r8d; Reserved
0x18003aa5b  mov     qword ptr [rsp+0BB0h+dwOptions], rax; lpData
0x18003aa60  call    cs:__imp_RegSetValueExW
0x18003aa66  mov     ebx, eax
0x18003aa68  test    eax, eax
0x18003aa6a  jz      short loc_18003AA82
0x18003aa6c  cmp     qword ptr cs:xmmword_180071090, r12
0x18003aa73  jz      loc_18003ABF7
0x18003aa79  lea     r9, aType; "Type"
0x18003aa80  jmp     short loc_18003AA28
0x18003aa82  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003aa87  lea     rax, [rsp+0BB0h+var_B40]
0x18003aa8c  mov     [rsp+0BB0h+samDesired], edi; cbData
0x18003aa90  lea     rdx, aEnabled; "Enabled"
0x18003aa97  mov     r9d, edi; dwType
0x18003aa9a  mov     qword ptr [rsp+0BB0h+dwOptions], rax; lpData
0x18003aa9f  xor     r8d, r8d; Reserved
0x18003aaa2  call    cs:__imp_RegSetValueExW
0x18003aaa8  mov     ebx, eax
0x18003aaaa  test    eax, eax
0x18003aaac  jz      short loc_18003AAC7
0x18003aaae  cmp     qword ptr cs:xmmword_180071090, r12
0x18003aab5  jz      loc_18003ABF7
0x18003aabb  lea     r9, aEnabled; "Enabled"
0x18003aac2  jmp     loc_18003AA28
0x18003aac7  xor     edx, edx; Val
0x18003aac9  lea     rcx, [rbp+0AB0h+var_B30]; void *
0x18003aacd  mov     r8d, 2C8h; Size
0x18003aad3  call    memset_0
0x18003aad8  movups  xmm0, xmmword ptr [r15+204h]
0x18003aae0  mov     edx, dword ptr [rsp+0BB0h+Data]
0x18003aae4  movdqu  [rbp+0AB0h+var_B14], xmm0
0x18003aae9  cmp     edx, 3
0x18003aaec  jnz     short loc_18003AAFB
0x18003aaee  mov     eax, [rsi]
0x18003aaf0  mov     [rbp+0AB0h+var_B04], eax
0x18003aaf3  mov     rax, [rsi+8]
0x18003aaf7  mov     [rbp+0AB0h+var_B00], rax
0x18003aafb  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003ab00  lea     r9, [rbp+0AB0h+var_B30]
0x18003ab04  mov     r8d, 1
0x18003ab0a  call    WriteInterfaceExtraInfo
0x18003ab0f  mov     ebx, eax
0x18003ab11  test    eax, eax
0x18003ab13  jz      short loc_18003AB4C
0x18003ab15  cmp     qword ptr cs:xmmword_180071090, r12
0x18003ab1c  jz      loc_18003ABF7
0x18003ab22  lea     rdx, aSCouldnTWriteD; "%s: Couldn't write domain specific info"...
0x18003ab29  mov     r9d, eax
0x18003ab2c  mov     word ptr [rbp+0AB0h+var_840], r12w
0x18003ab34  lea     r8, aRrasroutingdom_25; "RRasRoutingDomainConfig::CreateInterfac"...
0x18003ab3b  lea     rcx, [rbp+0AB0h+var_840]
0x18003ab42  call    FormatRRASErrorString
0x18003ab47  jmp     loc_18003ABD6
0x18003ab4c  mov     rdx, [rsp+0BB0h+var_B60]; HKEY
0x18003ab51  mov     r8d, 21h ; '!'; unsigned int
0x18003ab57  call    ?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z; RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)
0x18003ab5c  mov     ebx, eax
0x18003ab5e  test    eax, eax
0x18003ab60  jz      short loc_18003AB78
0x18003ab62  cmp     qword ptr cs:xmmword_180071090, r12
0x18003ab69  jz      loc_18003ABF7
0x18003ab6f  lea     rdx, aSCouldnTCreate_0; "%s: Couldn't create IPv4 transport : %d"
0x18003ab76  jmp     short loc_18003AB29
0x18003ab78  mov     rdx, [rsp+0BB0h+var_B60]; HKEY
0x18003ab7d  mov     r8d, 57h ; 'W'; unsigned int
0x18003ab83  call    ?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z; RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)
0x18003ab88  mov     ebx, eax
0x18003ab8a  test    eax, eax
0x18003ab8c  jz      short loc_18003ABF7
0x18003ab8e  cmp     qword ptr cs:xmmword_180071090, r12
0x18003ab95  jz      short loc_18003ABF7
0x18003ab97  lea     rdx, aSCouldnTCreate; "%s: Couldn't create IPv6 transport : %d"
0x18003ab9e  jmp     short loc_18003AB29
0x18003aba0  cmp     qword ptr cs:xmmword_180071090, r12
0x18003aba7  jz      short loc_18003ABF7
0x18003aba9  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003abb0  lea     r8, [rbp+0AB0h+pszDest]
0x18003abb7  lea     rdx, aFailedToCreate; "Failed to create sub-key '%s' under '%s"...
0x18003abbe  lea     rcx, [rbp+0AB0h+var_840]
0x18003abc5  mov     [rsp+0BB0h+dwOptions], eax
0x18003abc9  mov     word ptr [rbp+0AB0h+var_840], r12w
0x18003abd1  call    FormatRRASErrorString
0x18003abd6  mov     rdx, qword ptr cs:xmmword_180071090
0x18003abdd  lea     r8, [rbp+0AB0h+var_840]
0x18003abe4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003abeb  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abf7  mov     rcx, [rsp+0BB0h+var_B60]; hKey
0x18003abfc  test    rcx, rcx
0x18003abff  jz      short loc_18003AC22
0x18003ac01  call    cs:__imp_RegCloseKey
0x18003ac07  test    ebx, ebx
0x18003ac09  jz      short loc_18003AC22
0x18003ac0b  mov     rcx, [rsp+0BB0h+hKey]; hKey
0x18003ac10  test    rcx, rcx
0x18003ac13  jz      short loc_18003AC32
0x18003ac15  lea     rdx, [rbp+0AB0h+pszDest]; lpSubKey
0x18003ac1c  call    cs:__imp_RegDeleteKeyW
0x18003ac22  mov     rcx, [rsp+0BB0h+hKey]; hKey
0x18003ac27  test    rcx, rcx
0x18003ac2a  jz      short loc_18003AC32
0x18003ac2c  call    cs:__imp_RegCloseKey
0x18003ac32  mov     eax, ebx
0x18003ac34  mov     rcx, [rbp+0AB0h+var_40]
0x18003ac3b  xor     rcx, rsp; StackCookie
0x18003ac3e  call    __security_check_cookie
0x18003ac43  add     rsp, 0B80h
0x18003ac4a  pop     r15
0x18003ac4c  pop     r14
0x18003ac4e  pop     r12
0x18003ac50  pop     rdi
0x18003ac51  pop     rsi
0x18003ac52  pop     rbx
0x18003ac53  pop     rbp
0x18003ac54  retn
```
