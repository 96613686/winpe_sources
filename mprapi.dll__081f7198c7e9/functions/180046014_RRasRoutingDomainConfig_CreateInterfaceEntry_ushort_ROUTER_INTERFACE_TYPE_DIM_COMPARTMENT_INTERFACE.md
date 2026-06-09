# RRasRoutingDomainConfig::CreateInterfaceEntry(ushort *,_ROUTER_INTERFACE_TYPE,_DIM_COMPARTMENT_INTERFACE *)

- ea: `0x180046014`
- end: `0x180046410`
- name: `?CreateInterfaceEntry@RRasRoutingDomainConfig@@QEAAKPEAGW4_ROUTER_INTERFACE_TYPE@@PEAU_DIM_COMPARTMENT_INTERFACE@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, BYTE *lpData, enum _ROUTER_INTERFACE_TYPE, struct _DIM_COMPARTMENT_INTERFACE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045e68`
- `0x180046644`

## callees

- `0x180009868`
- `0x180043498`
- `0x180046014`
- `0x180046418`
- `0x18004a364`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004610a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800461d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004610a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800461d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046202`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800462bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046301`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046263`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800462bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046301`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004616a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004616a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800461f2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800461f2`

## string_xrefs

- `0x1800460c8`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x180046183`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x1800460da`: `Error %d occurred while opening interfaces key under registry key %s. #1`
- `0x180046191`: `Failed to create sub-key '%s' under '%s': %d`
- `0x180046287`: `RRasRoutingDomainConfig::CreateInterfaceEntry`
- `0x18004639c`: `RRasRoutingDomainConfig::CreateInterfaceEntry`
- `0x18004628e`: `%s: Couldn't write value %ws: %d`
- `0x18004638a`: `%s: Couldn't write domain specific info to registry : %d`
- `0x1800463d7`: `%s: Couldn't create IPv4 transport : %d`
- `0x180046407`: `%s: Couldn't create IPv6 transport : %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CreateInterfaceEntry(
        RRasRoutingDomainConfig *this,
        BYTE *lpData,
        enum _ROUTER_INTERFACE_TYPE a3,
        struct _DIM_COMPARTMENT_INTERFACE *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  __int64 i; // r9
  LSTATUS v10; // eax
  const WCHAR *v11; // r9
  wchar_t *v12; // r8
  const wchar_t *v13; // rdx
  __int64 v15; // rax
  LSTATUS v16; // eax
  unsigned int InterfaceTransportEntry; // eax
  RRasRoutingDomainConfig *v18; // rcx
  const wchar_t *v19; // rdx
  RRasRoutingDomainConfig *v20; // rcx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v25; // [rsp+68h] [rbp-98h] BYREF
  BYTE v26[16]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[24]; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+ACh] [rbp-54h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  wchar_t pszDest[8]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v33; // [rsp+360h] [rbp+260h]
  int v34; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v35[2044]; // [rsp+374h] [rbp+274h] BYREF

  *(_DWORD *)Data = a3;
  hKey = 0;
  dwDisposition = 0;
  v27 = 0;
  v33 = 0;
  *(_OWORD *)pszDest = 0;
  memset_0(v28, 0, 0x2C4u);
  *(_DWORD *)v26 = 1;
  v25 = 0;
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v6 = RRasRoutingDomainConfig::OpenInterfacesKey(this, &v25);
  v7 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_12;
    LOWORD(v34) = 0;
    FormatRRASErrorString(
      &v34,
      L"Error %d occurred while opening interfaces key under registry key %s. #1",
      v6,
      L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
    goto LABEL_11;
  }
  v8 = 0;
  for ( i = 0; ; i = v8 )
  {
    StringCbPrintfW(pszDest, 0x18u, L"%d", i);
    v10 = RegCreateKeyExW(v25, pszDest, 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
    v7 = v10;
    if ( v10 )
    {
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_12;
      dwOptions[0] = v10;
      v11 = L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
      v12 = pszDest;
      v13 = L"Failed to create sub-key '%s' under '%s': %d";
      goto LABEL_10;
    }
    if ( dwDisposition == 1 )
      break;
    RegCloseKey(hKey);
    ++v8;
    hKey = 0;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)&lpData[2 * v15] );
  v16 = RegSetValueExW(hKey, L"InterfaceName", 0, 1u, lpData, 2 * v15 + 2);
  v7 = v16;
  if ( !v16 )
  {
    v16 = RegSetValueExW(hKey, L"Type", 0, 4u, Data, 4u);
    v7 = v16;
    if ( v16 )
    {
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_12;
      v11 = L"Type";
    }
    else
    {
      v16 = RegSetValueExW(hKey, L"Enabled", 0, 4u, v26, 4u);
      v7 = v16;
      if ( !v16 )
      {
        memset_0(&v27, 0, 0x2C8u);
        v29 = *(_OWORD *)((char *)this + 516);
        if ( *(_DWORD *)Data == 3 )
        {
          v30 = MEMORY[0];
          v31 = MEMORY[8];
        }
        InterfaceTransportEntry = WriteInterfaceExtraInfo(hKey);
        v7 = InterfaceTransportEntry;
        if ( InterfaceTransportEntry )
        {
          if ( !(_QWORD)xmmword_180078C50 )
            goto LABEL_12;
          v19 = L"%s: Couldn't write domain specific info to registry : %d";
        }
        else
        {
          InterfaceTransportEntry = RRasRoutingDomainConfig::CreateInterfaceTransportEntry(v18, hKey, 0x21u);
          v7 = InterfaceTransportEntry;
          if ( InterfaceTransportEntry )
          {
            if ( !(_QWORD)xmmword_180078C50 )
              goto LABEL_12;
            v19 = L"%s: Couldn't create IPv4 transport : %d";
          }
          else
          {
            InterfaceTransportEntry = RRasRoutingDomainConfig::CreateInterfaceTransportEntry(v20, hKey, 0x57u);
            v7 = InterfaceTransportEntry;
            if ( !InterfaceTransportEntry || !(_QWORD)xmmword_180078C50 )
              goto LABEL_12;
            v19 = L"%s: Couldn't create IPv6 transport : %d";
          }
        }
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v34, v19, L"RRasRoutingDomainConfig::CreateInterfaceEntry", InterfaceTransportEntry);
LABEL_11:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C50,
          &v34);
        goto LABEL_12;
      }
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_12;
      v11 = L"Enabled";
    }
LABEL_24:
    dwOptions[0] = v16;
    v12 = L"RRasRoutingDomainConfig::CreateInterfaceEntry";
    v13 = L"%s: Couldn't write value %ws: %d";
LABEL_10:
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v34, v13, v12, v11, *(_QWORD *)dwOptions);
    goto LABEL_11;
  }
  if ( (_QWORD)xmmword_180078C50 )
  {
    v11 = L"InterfaceName";
    goto LABEL_24;
  }
LABEL_12:
  if ( hKey && (RegCloseKey(hKey), v7) )
  {
    if ( v25 )
    {
      RegDeleteKeyW(v25, pszDest);
      goto LABEL_16;
    }
  }
  else
  {
LABEL_16:
    if ( v25 )
      RegCloseKey(v25);
  }
  return v7;
}

```

## disassembly

```asm
0x180046014  mov     [rsp-8+arg_18], rbx
0x180046019  push    rbp
0x18004601a  push    rsi
0x18004601b  push    rdi
0x18004601c  push    r14
0x18004601e  push    r15
0x180046020  lea     rbp, [rsp-0A80h]
0x180046028  sub     rsp, 0B80h
0x18004602f  mov     rax, cs:__security_cookie
0x180046036  xor     rax, rsp
0x180046039  mov     [rbp+0AA0h+var_30], rax
0x180046040  xor     r15d, r15d
0x180046043  mov     dword ptr [rsp+0BA0h+Data], r8d
0x180046048  mov     rsi, rdx
0x18004604b  mov     [rsp+0BA0h+hKey], r15
0x180046050  mov     r14, rcx
0x180046053  mov     [rsp+0BA0h+dwDisposition], r15d
0x180046058  xorps   xmm0, xmm0
0x18004605b  mov     [rbp+0AA0h+var_B20], r15d
0x18004605f  xor     eax, eax
0x180046061  lea     rcx, [rbp+0AA0h+var_B1C]; void *
0x180046065  xor     edx, edx; Val
0x180046067  mov     [rbp+0AA0h+var_840], rax
0x18004606e  mov     r8d, 2C4h; Size
0x180046074  movups  xmmword ptr [rbp+0AA0h+pszDest], xmm0
0x18004607b  call    memset_0
0x180046080  xor     edx, edx; Val
0x180046082  mov     dword ptr [rsp+0BA0h+var_B30], 1
0x18004608a  mov     r8d, 7FCh; Size
0x180046090  mov     [rsp+0BA0h+var_B38], r15
0x180046095  lea     rcx, [rbp+0AA0h+var_82C]; void *
0x18004609c  mov     [rbp+0AA0h+var_830], r15d
0x1800460a3  call    memset_0
0x1800460a8  lea     rdx, [rsp+0BA0h+var_B38]; HKEY *
0x1800460ad  mov     rcx, r14; this
0x1800460b0  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x1800460b5  mov     ebx, eax
0x1800460b7  test    eax, eax
0x1800460b9  jz      short loc_1800460F2
0x1800460bb  cmp     qword ptr cs:xmmword_180078C50, r15
0x1800460c2  jz      loc_1800461CD
0x1800460c8  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x1800460cf  mov     word ptr [rbp+0AA0h+var_830], r15w
0x1800460d7  mov     r8d, eax
0x1800460da  lea     rdx, aErrorDOccurred; "Error %d occurred while opening interfa"...
0x1800460e1  lea     rcx, [rbp+0AA0h+var_830]
0x1800460e8  call    FormatRRASErrorString
0x1800460ed  jmp     loc_1800461AC
0x1800460f2  mov     edi, r15d
0x1800460f5  xor     r9d, r9d
0x1800460f8  jmp     short loc_18004611A
0x1800460fa  cmp     [rsp+0BA0h+dwDisposition], 1
0x1800460ff  jz      loc_180046230
0x180046105  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x18004610a  call    cs:__imp_RegCloseKey
0x180046110  inc     edi
0x180046112  mov     [rsp+0BA0h+hKey], r15
0x180046117  mov     r9d, edi
0x18004611a  lea     r8, aD; "%d"
0x180046121  mov     edx, 18h; cbDest
0x180046126  lea     rcx, [rbp+0AA0h+pszDest]; pszDest
0x18004612d  call    StringCbPrintfW
0x180046132  mov     rcx, [rsp+0BA0h+var_B38]; hKey
0x180046137  lea     rax, [rsp+0BA0h+dwDisposition]
0x18004613c  mov     [rsp+0BA0h+lpdwDisposition], rax; lpdwDisposition
0x180046141  lea     rdx, [rbp+0AA0h+pszDest]; lpSubKey
0x180046148  lea     rax, [rsp+0BA0h+hKey]
0x18004614d  xor     r9d, r9d; lpClass
0x180046150  mov     [rsp+0BA0h+phkResult], rax; phkResult
0x180046155  xor     r8d, r8d; Reserved
0x180046158  mov     [rsp+0BA0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18004615d  mov     [rsp+0BA0h+samDesired], 3001Fh; samDesired
0x180046165  mov     [rsp+0BA0h+dwOptions], r15d; dwOptions
0x18004616a  call    cs:__imp_RegCreateKeyExW
0x180046170  mov     ebx, eax
0x180046172  test    eax, eax
0x180046174  jz      short loc_1800460FA
0x180046176  cmp     qword ptr cs:xmmword_180078C50, r15
0x18004617d  jz      short loc_1800461CD
0x18004617f  mov     [rsp+0BA0h+dwOptions], eax
0x180046183  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x18004618a  lea     r8, [rbp+0AA0h+pszDest]
0x180046191  lea     rdx, aFailedToCreate; "Failed to create sub-key '%s' under '%s"...
0x180046198  lea     rcx, [rbp+0AA0h+var_830]
0x18004619f  mov     word ptr [rbp+0AA0h+var_830], r15w
0x1800461a7  call    FormatRRASErrorString
0x1800461ac  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800461b3  lea     r8, [rbp+0AA0h+var_830]
0x1800461ba  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800461c1  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800461c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461cd  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x1800461d2  test    rcx, rcx
0x1800461d5  jz      short loc_1800461F8
0x1800461d7  call    cs:__imp_RegCloseKey
0x1800461dd  test    ebx, ebx
0x1800461df  jz      short loc_1800461F8
0x1800461e1  mov     rcx, [rsp+0BA0h+var_B38]; hKey
0x1800461e6  test    rcx, rcx
0x1800461e9  jz      short loc_180046208
0x1800461eb  lea     rdx, [rbp+0AA0h+pszDest]; lpSubKey
0x1800461f2  call    cs:__imp_RegDeleteKeyW
0x1800461f8  mov     rcx, [rsp+0BA0h+var_B38]; hKey
0x1800461fd  test    rcx, rcx
0x180046200  jz      short loc_180046208
0x180046202  call    cs:__imp_RegCloseKey
0x180046208  mov     eax, ebx
0x18004620a  mov     rcx, [rbp+0AA0h+var_30]
0x180046211  xor     rcx, rsp; StackCookie
0x180046214  call    __security_check_cookie
0x180046219  mov     rbx, [rsp+0BA0h+arg_18]
0x180046221  add     rsp, 0B80h
0x180046228  pop     r15
0x18004622a  pop     r14
0x18004622c  pop     rdi
0x18004622d  pop     rsi
0x18004622e  pop     rbp
0x18004622f  retn
0x180046230  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046234  inc     rax
0x180046237  cmp     [rsi+rax*2], r15w
0x18004623c  jnz     short loc_180046234
0x18004623e  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x180046243  lea     eax, ds:2[rax*2]
0x18004624a  mov     [rsp+0BA0h+samDesired], eax; cbData
0x18004624e  lea     rdx, aInterfacename; "InterfaceName"
0x180046255  mov     r9d, 1; dwType
0x18004625b  mov     qword ptr [rsp+0BA0h+dwOptions], rsi; lpData
0x180046260  xor     r8d, r8d; Reserved
0x180046263  call    cs:__imp_RegSetValueExW
0x180046269  mov     ebx, eax
0x18004626b  test    eax, eax
0x18004626d  jz      short loc_18004629A
0x18004626f  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046276  jz      loc_1800461CD
0x18004627c  lea     r9, aInterfacename; "InterfaceName"
0x180046283  mov     [rsp+0BA0h+dwOptions], eax
0x180046287  lea     r8, aRrasroutingdom_25; "RRasRoutingDomainConfig::CreateInterfac"...
0x18004628e  lea     rdx, aSCouldnTWriteV; "%s: Couldn't write value %ws: %d"
0x180046295  jmp     loc_180046198
0x18004629a  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x18004629f  lea     rax, [rsp+0BA0h+Data]
0x1800462a4  mov     edi, 4
0x1800462a9  lea     rdx, aType; "Type"
0x1800462b0  mov     [rsp+0BA0h+samDesired], edi; cbData
0x1800462b4  mov     r9d, edi; dwType
0x1800462b7  xor     r8d, r8d; Reserved
0x1800462ba  mov     qword ptr [rsp+0BA0h+dwOptions], rax; lpData
0x1800462bf  call    cs:__imp_RegSetValueExW
0x1800462c5  mov     ebx, eax
0x1800462c7  test    eax, eax
0x1800462c9  jz      short loc_1800462E1
0x1800462cb  cmp     qword ptr cs:xmmword_180078C50, r15
0x1800462d2  jz      loc_1800461CD
0x1800462d8  lea     r9, aType; "Type"
0x1800462df  jmp     short loc_180046283
0x1800462e1  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x1800462e6  lea     rax, [rsp+0BA0h+var_B30]
0x1800462eb  mov     [rsp+0BA0h+samDesired], edi; cbData
0x1800462ef  lea     rdx, aEnabled; "Enabled"
0x1800462f6  mov     r9d, edi; dwType
0x1800462f9  mov     qword ptr [rsp+0BA0h+dwOptions], rax; lpData
0x1800462fe  xor     r8d, r8d; Reserved
0x180046301  call    cs:__imp_RegSetValueExW
0x180046307  mov     ebx, eax
0x180046309  test    eax, eax
0x18004630b  jz      short loc_180046326
0x18004630d  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046314  jz      loc_1800461CD
0x18004631a  lea     r9, aEnabled; "Enabled"
0x180046321  jmp     loc_180046283
0x180046326  xor     edx, edx; Val
0x180046328  lea     rcx, [rbp+0AA0h+var_B20]; void *
0x18004632c  mov     r8d, 2C8h; Size
0x180046332  call    memset_0
0x180046337  movups  xmm0, xmmword ptr [r14+204h]
0x18004633f  mov     edx, dword ptr [rsp+0BA0h+Data]
0x180046343  movdqu  [rbp+0AA0h+var_B04], xmm0
0x180046348  cmp     edx, 3
0x18004634b  jnz     short loc_180046363
0x18004634d  mov     eax, ds:0
0x180046354  mov     [rbp+0AA0h+var_AF4], eax
0x180046357  mov     rax, ds:8
0x18004635f  mov     [rbp+0AA0h+var_AF0], rax
0x180046363  mov     rcx, [rsp+0BA0h+hKey]; hKey
0x180046368  lea     r9, [rbp+0AA0h+var_B20]
0x18004636c  mov     r8d, 1
0x180046372  call    WriteInterfaceExtraInfo
0x180046377  mov     ebx, eax
0x180046379  test    eax, eax
0x18004637b  jz      short loc_1800463B4
0x18004637d  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046384  jz      loc_1800461CD
0x18004638a  lea     rdx, aSCouldnTWriteD; "%s: Couldn't write domain specific info"...
0x180046391  mov     r9d, eax
0x180046394  mov     word ptr [rbp+0AA0h+var_830], r15w
0x18004639c  lea     r8, aRrasroutingdom_25; "RRasRoutingDomainConfig::CreateInterfac"...
0x1800463a3  lea     rcx, [rbp+0AA0h+var_830]
0x1800463aa  call    FormatRRASErrorString
0x1800463af  jmp     loc_1800461AC
0x1800463b4  mov     rdx, [rsp+0BA0h+hKey]; HKEY
0x1800463b9  mov     r8d, 21h ; '!'; unsigned int
0x1800463bf  call    ?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z; RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)
0x1800463c4  mov     ebx, eax
0x1800463c6  test    eax, eax
0x1800463c8  jz      short loc_1800463E0
0x1800463ca  cmp     qword ptr cs:xmmword_180078C50, r15
0x1800463d1  jz      loc_1800461CD
0x1800463d7  lea     rdx, aSCouldnTCreate_0; "%s: Couldn't create IPv4 transport : %d"
0x1800463de  jmp     short loc_180046391
0x1800463e0  mov     rdx, [rsp+0BA0h+hKey]; HKEY
0x1800463e5  mov     r8d, 57h ; 'W'; unsigned int
0x1800463eb  call    ?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z; RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)
0x1800463f0  mov     ebx, eax
0x1800463f2  test    eax, eax
0x1800463f4  jz      loc_1800461CD
0x1800463fa  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046401  jz      loc_1800461CD
0x180046407  lea     rdx, aSCouldnTCreate; "%s: Couldn't create IPv6 transport : %d"
0x18004640e  jmp     short loc_180046391
```
