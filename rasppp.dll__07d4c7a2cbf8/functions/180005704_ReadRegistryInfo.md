# ReadRegistryInfo

- ea: `0x180005704`
- end: `0x180006077`
- name: `ReadRegistryInfo`
- size: `2419`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004630`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800048e8`
- `0x1800054a8`
- `0x180005704`
- `0x180006080`
- `0x1800070e4`
- `0x180012024`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000601a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000603d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000601a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000603d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000596e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000596e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180005876`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180005876`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800057ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005820`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800057ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005820`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005fe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005fe1`
- `rtutils!RouterLogEventA` at `0x1800058b7`
- `rtutils!RouterLogEventA` at `0x180005a0a`
- `rtutils!RouterLogEventA` at `0x1800058b7`
- `rtutils!RouterLogEventA` at `0x180005a0a`
- `rtutils!RouterLogEventStringA` at `0x1800057e7`
- `rtutils!RouterLogEventStringA` at `0x180005aad`
- `rtutils!RouterLogEventStringA` at `0x180005e0b`
- `rtutils!RouterLogEventStringA` at `0x180005e87`
- `rtutils!RouterLogEventStringA` at `0x180005f22`
- `rtutils!RouterLogEventStringA` at `0x180005f79`
- `rtutils!RouterLogEventStringA` at `0x1800057e7`
- `rtutils!RouterLogEventStringA` at `0x180005aad`
- `rtutils!RouterLogEventStringA` at `0x180005e0b`
- `rtutils!RouterLogEventStringA` at `0x180005e87`
- `rtutils!RouterLogEventStringA` at `0x180005f22`
- `rtutils!RouterLogEventStringA` at `0x180005f79`

## string_xrefs

- `0x1800057fa`: `Cannot open or obtain information about the PPP key or one of its subkeys. %d`
- `0x180005e9d`: `The Point to Point Protocol module %hs returned an error while initializing. %d`
- `0x180005f9f`: `The Point to Point Protocol module %hs returned an error while initializing. %d`
- `0x18000579d`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp`
- `0x180005816`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp\ControlProtocols`
- `0x1800058cf`: `The Point to Point Protocol failed to load the required PAP and/or CHAP authentication modules. %d`
- `0x180005e26`: `The Control Protocol %hs in the Point to Point Protocol module %hs returned an error while initializing. %d`

## pseudocode

```c
__int64 __fastcall ReadRegistryInfo(PHKEY phkResult)
{
  unsigned int dwErrorCode; // ebx
  const wchar_t *v3; // rdx
  unsigned __int64 v4; // rax
  DWORD v5; // edi
  LPVOID v6; // rcx
  DWORD LastError; // eax
  DWORD Info; // eax
  LPSTR v9; // r8
  __int64 v10; // r9
  DWORD v11; // r14d
  __int64 v12; // rsi
  unsigned int v13; // edi
  unsigned int v14; // eax
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  char *v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rcx
  char *v21; // rax
  DWORD i; // edi
  void *v23; // r8
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v26; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG ulMinuend; // [rsp+68h] [rbp-98h] BYREF
  LPSTR plpszSubStringArray; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-74h] BYREF
  LPSTR v34[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v35; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-50h]
  __int128 v37; // [rsp+C0h] [rbp-40h]
  __int128 v38; // [rsp+D0h] [rbp-30h]
  __int128 v39; // [rsp+E0h] [rbp-20h]
  __int128 v40; // [rsp+F0h] [rbp-10h]
  __int128 v41; // [rsp+100h] [rbp+0h]
  __int128 v42; // [rsp+110h] [rbp+10h]
  __int128 v43; // [rsp+120h] [rbp+20h]
  __int128 v44; // [rsp+130h] [rbp+30h]
  __int128 v45; // [rsp+140h] [rbp+40h]
  _DWORD v46[20]; // [rsp+150h] [rbp+50h] BYREF
  int v47; // [rsp+1A0h] [rbp+A0h] BYREF
  char v48[2044]; // [rsp+1A4h] [rbp+A4h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v26 = 0;
  ulMinuend = 0;
  memset_0(&v35, 0, 0xB0u);
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  dwErrorCode = RegOpenKeyExA(
                  HKEY_LOCAL_MACHINE,
                  "SYSTEM\\CurrentControlSet\\Services\\RasMan\\ppp",
                  0,
                  0x20019u,
                  phkResult);
  if ( dwErrorCode
    || (dwErrorCode = RegOpenKeyExA(
                        HKEY_LOCAL_MACHINE,
                        "SYSTEM\\CurrentControlSet\\Services\\RasMan\\ppp\\ControlProtocols",
                        0,
                        0x20019u,
                        &hKey)) != 0
    || (dwErrorCode = RegQueryInfoKeyA(
                        hKey,
                        0,
                        0,
                        0,
                        &cSubKeys,
                        &cbMaxSubKeyLen,
                        0,
                        &cValues,
                        &cbMaxValueNameLen,
                        &cbMaxValueLen,
                        0,
                        0)) != 0 )
  {
    if ( dword_18004CA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E65u, 0, 0, dwErrorCode, 0);
    if ( byte_18004CF33 >= 0 )
      goto LABEL_88;
    v3 = L"Cannot open or obtain information about the PPP key or one of its subkeys. %d";
    goto LABEL_13;
  }
  if ( !cSubKeys )
  {
    if ( dword_18004CA20 )
      RouterLogEventA(hLogHandle, 1u, 0x4E68u, 0, 0, 0);
    dwErrorCode = 1015;
    if ( byte_18004CF33 >= 0 )
      goto LABEL_88;
    v3 = L"The Point to Point Protocol failed to load the required PAP and/or CHAP authentication modules. %d";
LABEL_13:
    LOWORD(v47) = 0;
    FormatRRASErrorString(&v47, v3, dwErrorCode);
    goto LABEL_14;
  }
  dwErrorCode = ReadPPPKeyValues(*phkResult);
  if ( dwErrorCode )
    goto LABEL_88;
  LoadParserDll(::hKey);
  if ( cSubKeys + 1 < cSubKeys || (v4 = 32LL * (cSubKeys + 1), v4 > 0xFFFFFFFF) )
  {
    dwErrorCode = 534;
    goto LABEL_88;
  }
  v5 = dwErrorCode + 8;
  LODWORD(plpszSubStringArray) = 32 * (cSubKeys + 1);
  lpMem = HeapAlloc(hHeap, dwErrorCode + 8, (unsigned int)v4);
  v6 = lpMem;
  if ( !lpMem )
    goto LABEL_22;
  *((_QWORD *)lpMem + 4 * cSubKeys + 3) = -1;
  dwErrorCode = LoadProtocolDlls(v6, cSubKeys, hKey, &ulMinuend);
  if ( dwErrorCode )
    goto LABEL_88;
  CpTable = HeapAlloc(hHeap, v5, 176LL * (ulMinuend + 1));
  if ( !CpTable )
  {
LABEL_22:
    LastError = GetLastError();
    dwErrorCode = LastError;
    if ( dword_18004CA20 )
      RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v47) = 0;
      FormatRRASErrorString(&v47, L"Memory allocation failure %d", dwErrorCode);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v47);
    }
    if ( dwErrorCode )
      goto LABEL_88;
    goto LABEL_90;
  }
  Info = LcpGetInfo();
  dwErrorCode = Info;
  if ( Info )
  {
    v9 = "LCP";
    plpszSubStringArray = "LCP";
    if ( dword_18004CA20 )
    {
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, &plpszSubStringArray, Info, 1u);
      v9 = plpszSubStringArray;
    }
    if ( byte_18004CF33 >= 0 )
      goto LABEL_88;
    LOWORD(v47) = 0;
    v10 = dwErrorCode;
    goto LABEL_86;
  }
  PppConfigInfo = 1;
  v11 = 0;
LABEL_35:
  if ( v11 >= cSubKeys )
    goto LABEL_90;
  v12 = 32LL * v11;
  dwErrorCode = (*(__int64 (__fastcall **)(_DWORD *, unsigned int *))((char *)lpMem + v12))(v46, &v26);
  if ( dwErrorCode )
  {
LABEL_77:
    if ( dword_18004CA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v12 + 16), dwErrorCode, 1u);
    if ( byte_18004CF33 >= 0 )
      goto LABEL_88;
    v10 = dwErrorCode;
LABEL_85:
    LOWORD(v47) = 0;
    v9 = *(LPSTR *)((char *)lpMem + v12 + 16);
LABEL_86:
    FormatRRASErrorString(
      &v47,
      L"The Point to Point Protocol module %hs returned an error while initializing. %d",
      v9,
      v10);
LABEL_14:
    if ( byte_18004CF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v47);
    goto LABEL_88;
  }
  v13 = v26;
  if ( !v26 || v26 > 0x14 )
  {
    dwErrorCode = 87;
    if ( dword_18004CA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v12 + 16), 0x57u, 1u);
    if ( byte_18004CF33 >= 0 )
      goto LABEL_88;
    v10 = 87;
    goto LABEL_85;
  }
  while ( 1 )
  {
    v14 = v13;
    v15 = v13 - 1;
    v26 = v15;
    if ( !v14 )
      goto LABEL_66;
    memset_0(&v35, 0, 0xB0u);
    dwErrorCode = (*(__int64 (__fastcall **)(_QWORD, __int128 *))((char *)lpMem + v12 + 8))(
                    (unsigned int)v46[v15],
                    &v35);
    if ( dwErrorCode )
      goto LABEL_77;
    if ( (_DWORD)v35 == 32801 )
      qword_18004CAA8 = (__int64)IpcpDhcpInform;
    if ( *((_QWORD *)&v36 + 1) && (_DWORD)v35 != 32801 && (_DWORD)v35 != 32855 )
      break;
LABEL_51:
    if ( (_QWORD)v45 )
    {
      v19 = ULongSub(ulMinuend, HIDWORD(PppConfigInfo), (ULONG *)&plpszSubStringArray);
      if ( v19 < 0 )
      {
        dwErrorCode = (unsigned __int16)v19;
        if ( (_WORD)v19 )
          goto LABEL_88;
LABEL_66:
        ++v11;
        goto LABEL_35;
      }
      v20 = 176LL * (unsigned int)plpszSubStringArray;
      v21 = (char *)CpTable;
      *(_OWORD *)((char *)CpTable + v20) = v35;
      *(_OWORD *)&v21[v20 + 16] = v36;
      *(_OWORD *)&v21[v20 + 32] = v37;
      *(_OWORD *)&v21[v20 + 48] = v38;
      *(_OWORD *)&v21[v20 + 64] = v39;
      *(_OWORD *)&v21[v20 + 80] = v40;
      *(_OWORD *)&v21[v20 + 96] = v41;
      *(_OWORD *)&v21[v20 + 112] = v42;
      *(_OWORD *)&v21[v20 + 128] = v43;
      *(_OWORD *)&v21[v20 + 144] = v44;
      *(_OWORD *)&v21[v20 + 160] = v45;
      ++HIDWORD(PppConfigInfo);
    }
    else
    {
      if ( !(_QWORD)v37
        || !*((_QWORD *)&v37 + 1)
        || !(_QWORD)v38
        || !(_QWORD)v41
        || !*((_QWORD *)&v41 + 1)
        || !(_QWORD)v42
        || !*((_QWORD *)&v42 + 1)
        || !(_QWORD)v43
        || (unsigned int)v36 > 0xC )
      {
        if ( dword_18004CA20 )
          RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v12 + 16), 0x57u, 1u);
        if ( byte_18004CF33 < 0 )
        {
          LOWORD(v47) = 0;
          FormatRRASErrorString(
            &v47,
            L"The Point to Point Protocol module %hs returned an error while initializing. %d",
            *(_QWORD *)((char *)lpMem + v12 + 16),
            87);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v47);
        }
        dwErrorCode = 87;
        goto LABEL_88;
      }
      v17 = 176LL * (unsigned int)PppConfigInfo;
      v18 = (char *)CpTable;
      *(_OWORD *)((char *)CpTable + v17) = v35;
      *(_OWORD *)&v18[v17 + 16] = v36;
      *(_OWORD *)&v18[v17 + 32] = v37;
      *(_OWORD *)&v18[v17 + 48] = v38;
      *(_OWORD *)&v18[v17 + 64] = v39;
      *(_OWORD *)&v18[v17 + 80] = v40;
      *(_OWORD *)&v18[v17 + 96] = v41;
      *(_OWORD *)&v18[v17 + 112] = v42;
      *(_OWORD *)&v18[v17 + 128] = v43;
      *(_OWORD *)&v18[v17 + 144] = v44;
      *(_OWORD *)&v18[v17 + 160] = v45;
      LODWORD(PppConfigInfo) = PppConfigInfo + 1;
    }
    v13 = v26;
  }
  if ( byte_18004CF33 < 0 )
  {
    LOWORD(v47) = 0;
    FormatRRASErrorString(&v47, L"RasCpInit(%x, TRUE)");
    if ( byte_18004CF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v47);
  }
  dwErrorCode = (*((__int64 (__fastcall **)(__int64))&v36 + 1))(1);
  v16 = DWORD2(v45) | 1;
  DWORD2(v45) |= 1u;
  if ( !dwErrorCode )
  {
    DWORD2(v45) = v16 | 2;
    goto LABEL_51;
  }
  v34[0] = (char *)&v35 + 4;
  v34[1] = *(LPSTR *)((char *)lpMem + v12 + 16);
  if ( dword_18004CA20 )
    RouterLogEventStringA(hLogHandle, 1u, 0x4EB7u, 2u, v34, dwErrorCode, 2u);
  if ( byte_18004CF33 < 0 )
  {
    LOWORD(v47) = 0;
    FormatRRASErrorString(
      &v47,
      L"The Control Protocol %hs in the Point to Point Protocol module %hs returned an error while initializing. %d");
    goto LABEL_14;
  }
LABEL_88:
  if ( CpTable )
    HeapFree(hHeap, 0, CpTable);
LABEL_90:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpMem )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      v23 = (void *)*((_QWORD *)lpMem + 4 * i + 2);
      if ( v23 )
        HeapFree(hHeap, 0, v23);
    }
    if ( dwErrorCode )
    {
      HeapFree(hHeap, 0, lpMem);
      lpMem = 0;
    }
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x180005704  mov     [rsp-8+arg_8], rbx
0x180005709  mov     [rsp-8+arg_10], rsi
0x18000570e  push    rbp
0x18000570f  push    rdi
0x180005710  push    r12
0x180005712  push    r14
0x180005714  push    r15
0x180005716  lea     rbp, [rsp-8B0h]
0x18000571e  sub     rsp, 9B0h
0x180005725  mov     rax, cs:__security_cookie
0x18000572c  xor     rax, rsp
0x18000572f  mov     [rbp+8D0h+var_30], rax
0x180005736  xor     r15d, r15d
0x180005739  mov     rdi, rcx
0x18000573c  lea     rcx, [rbp+8D0h+var_930]; void *
0x180005740  mov     [rsp+9D0h+hKey], r15
0x180005745  xor     edx, edx; Val
0x180005747  mov     [rsp+9D0h+cSubKeys], r15d
0x18000574c  mov     r8d, 0B0h; Size
0x180005752  mov     [rbp+8D0h+cbMaxSubKeyLen], r15d
0x180005756  mov     [rbp+8D0h+cValues], r15d
0x18000575a  mov     [rbp+8D0h+cbMaxValueNameLen], r15d
0x18000575e  mov     [rbp+8D0h+cbMaxValueLen], r15d
0x180005762  mov     [rsp+9D0h+var_96C], r15d
0x180005767  mov     [rsp+9D0h+ulMinuend], r15d
0x18000576c  call    memset_0
0x180005771  xor     edx, edx; Val
0x180005773  mov     [rbp+8D0h+var_830], r15d
0x18000577a  mov     r8d, 7FCh; Size
0x180005780  lea     rcx, [rbp+8D0h+var_82C]; void *
0x180005787  call    memset_0
0x18000578c  mov     esi, 20019h
0x180005791  mov     [rsp+9D0h+phkResult], rdi; phkResult
0x180005796  mov     r14, 0FFFFFFFF80000002h
0x18000579d  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800057a4  mov     r9d, esi; samDesired
0x1800057a7  mov     rcx, r14; hKey
0x1800057aa  xor     r8d, r8d; ulOptions
0x1800057ad  call    cs:__imp_RegOpenKeyExA
0x1800057b3  lea     r12d, [r15+1]
0x1800057b7  mov     ebx, eax
0x1800057b9  test    eax, eax
0x1800057bb  jz      short loc_180005806
0x1800057bd  cmp     cs:dword_18004CA20, r15d
0x1800057c4  jbe     short loc_1800057ED
0x1800057c6  mov     rcx, cs:hLogHandle; hLogHandle
0x1800057cd  xor     r9d, r9d; dwSubStringCount
0x1800057d0  mov     [rsp+9D0h+dwErrorIndex], r15d; dwErrorIndex
0x1800057d5  mov     r8d, 4E65h; dwMessageId
0x1800057db  mov     [rsp+9D0h+dwErrorCode], ebx; dwErrorCode
0x1800057df  mov     edx, r12d; dwEventType
0x1800057e2  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x1800057e7  call    cs:__imp_RouterLogEventStringA
0x1800057ed  cmp     cs:byte_18004CF33, r15b
0x1800057f4  jge     loc_180005FBC
0x1800057fa  lea     rdx, aCannotOpenOrOb; "Cannot open or obtain information about"...
0x180005801  jmp     loc_1800058D6
0x180005806  lea     rax, [rsp+9D0h+hKey]
0x18000580b  mov     r9d, esi; samDesired
0x18000580e  xor     r8d, r8d; ulOptions
0x180005811  mov     [rsp+9D0h+phkResult], rax; phkResult
0x180005816  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000581d  mov     rcx, r14; hKey
0x180005820  call    cs:__imp_RegOpenKeyExA
0x180005826  mov     ebx, eax
0x180005828  test    eax, eax
0x18000582a  jnz     short loc_1800057BD
0x18000582c  mov     rcx, [rsp+9D0h+hKey]; hKey
0x180005831  lea     rax, [rbp+8D0h+cbMaxValueLen]
0x180005835  mov     [rsp+9D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000583a  xor     r9d, r9d; lpReserved
0x18000583d  mov     [rsp+9D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180005842  xor     r8d, r8d; lpcchClass
0x180005845  mov     [rsp+9D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000584a  xor     edx, edx; lpClass
0x18000584c  lea     rax, [rbp+8D0h+cbMaxValueNameLen]
0x180005850  mov     [rsp+9D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180005855  lea     rax, [rbp+8D0h+cValues]
0x180005859  mov     [rsp+9D0h+lpcValues], rax; lpcValues
0x18000585e  lea     rax, [rbp+8D0h+cbMaxSubKeyLen]
0x180005862  mov     qword ptr [rsp+9D0h+dwErrorIndex], r15; lpcbMaxClassLen
0x180005867  mov     qword ptr [rsp+9D0h+dwErrorCode], rax; lpcbMaxSubKeyLen
0x18000586c  lea     rax, [rsp+9D0h+cSubKeys]
0x180005871  mov     [rsp+9D0h+phkResult], rax; lpcSubKeys
0x180005876  call    cs:__imp_RegQueryInfoKeyA
0x18000587c  mov     ebx, eax
0x18000587e  test    eax, eax
0x180005880  jnz     loc_1800057BD
0x180005886  cmp     [rsp+9D0h+cSubKeys], r15d
0x18000588b  jnz     loc_180005919
0x180005891  cmp     cs:dword_18004CA20, r15d
0x180005898  jbe     short loc_1800058BD
0x18000589a  mov     rcx, cs:hLogHandle; hLogHandle
0x1800058a1  xor     r9d, r9d; dwSubStringCount
0x1800058a4  mov     [rsp+9D0h+dwErrorCode], r15d; dwErrorCode
0x1800058a9  mov     r8d, 4E68h; dwMessageId
0x1800058af  mov     edx, r12d; dwEventType
0x1800058b2  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x1800058b7  call    cs:__imp_RouterLogEventA
0x1800058bd  cmp     cs:byte_18004CF33, r15b
0x1800058c4  mov     ebx, 3F7h
0x1800058c9  jge     loc_180005FBC
0x1800058cf  lea     rdx, aThePointToPoin_0; "The Point to Point Protocol failed to l"...
0x1800058d6  mov     r8d, ebx
0x1800058d9  mov     word ptr [rbp+8D0h+var_830], r15w
0x1800058e1  lea     rcx, [rbp+8D0h+var_830]
0x1800058e8  call    FormatRRASErrorString
0x1800058ed  cmp     cs:byte_18004CF33, r15b
0x1800058f4  jge     loc_180005FBC
0x1800058fa  lea     r8, [rbp+8D0h+var_830]
0x180005901  lea     rdx, RasPppTraceError
0x180005908  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000590f  call    McTemplateU0z_EventWriteTransfer
0x180005914  jmp     loc_180005FBC
0x180005919  mov     rcx, [rdi]; hKey
0x18000591c  call    ReadPPPKeyValues
0x180005921  mov     ebx, eax
0x180005923  test    eax, eax
0x180005925  jnz     loc_180005FBC
0x18000592b  mov     rcx, cs:hKey; hKey
0x180005932  call    LoadParserDll
0x180005937  mov     eax, [rsp+9D0h+cSubKeys]
0x18000593b  lea     ecx, [rax+1]
0x18000593e  cmp     ecx, eax
0x180005940  jb      loc_180005FB7
0x180005946  mov     eax, ecx
0x180005948  mov     ecx, 0FFFFFFFFh
0x18000594d  shl     rax, 5
0x180005951  cmp     rax, rcx
0x180005954  ja      loc_180005FB7
0x18000595a  mov     rcx, cs:hHeap; hHeap
0x180005961  lea     edi, [rbx+8]
0x180005964  mov     r8d, eax; dwBytes
0x180005967  mov     edx, edi; dwFlags
0x180005969  mov     dword ptr [rsp+9D0h+plpszSubStringArray], r8d
0x18000596e  call    cs:__imp_HeapAlloc
0x180005974  mov     cs:lpMem, rax
0x18000597b  mov     rcx, rax
0x18000597e  test    rax, rax
0x180005981  jz      short loc_1800059DD
0x180005983  mov     eax, [rsp+9D0h+cSubKeys]
0x180005987  lea     r9, [rsp+9D0h+ulMinuend]
0x18000598c  shl     rax, 5
0x180005990  mov     qword ptr [rax+rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180005999  mov     r8, [rsp+9D0h+hKey]
0x18000599e  mov     edx, [rsp+9D0h+cSubKeys]
0x1800059a2  call    LoadProtocolDlls
0x1800059a7  mov     ebx, eax
0x1800059a9  test    eax, eax
0x1800059ab  jnz     loc_180005FBC
0x1800059b1  mov     ecx, [rsp+9D0h+ulMinuend]
0x1800059b5  mov     edx, edi; dwFlags
0x1800059b7  inc     ecx
0x1800059b9  imul    r8, rcx, 0B0h; dwBytes
0x1800059c0  mov     rcx, cs:hHeap; hHeap
0x1800059c7  call    cs:__imp_HeapAlloc
0x1800059cd  mov     cs:CpTable, rax
0x1800059d4  test    rax, rax
0x1800059d7  jnz     loc_180005A67
0x1800059dd  call    cs:__imp_GetLastError
0x1800059e3  cmp     cs:dword_18004CA20, r15d
0x1800059ea  mov     ebx, eax
0x1800059ec  jbe     short loc_180005A10
0x1800059ee  mov     rcx, cs:hLogHandle; hLogHandle
0x1800059f5  xor     r9d, r9d; dwSubStringCount
0x1800059f8  mov     [rsp+9D0h+dwErrorCode], eax; dwErrorCode
0x1800059fc  mov     r8d, 4E88h; dwMessageId
0x180005a02  mov     edx, r12d; dwEventType
0x180005a05  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x180005a0a  call    cs:__imp_RouterLogEventA
0x180005a10  cmp     cs:byte_18004CF33, r15b
0x180005a17  jge     short loc_180005A5A
0x180005a19  mov     r8d, ebx
0x180005a1c  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005a24  lea     rdx, aMemoryAllocati_1; "Memory allocation failure %d"
0x180005a2b  lea     rcx, [rbp+8D0h+var_830]
0x180005a32  call    FormatRRASErrorString
0x180005a37  cmp     cs:byte_18004CF33, r15b
0x180005a3e  jge     short loc_180005A5A
0x180005a40  lea     r8, [rbp+8D0h+var_830]
0x180005a47  lea     rdx, RasPppTraceError
0x180005a4e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005a55  call    McTemplateU0z_EventWriteTransfer
0x180005a5a  test    ebx, ebx
0x180005a5c  jnz     loc_180005FBC
0x180005a62  jmp     loc_180005FD7
0x180005a67  call    LcpGetInfo
0x180005a6c  mov     ebx, eax
0x180005a6e  test    eax, eax
0x180005a70  jz      short loc_180005AD5
0x180005a72  cmp     cs:dword_18004CA20, r15d
0x180005a79  lea     r8, aLcp; "LCP"
0x180005a80  mov     [rsp+9D0h+plpszSubStringArray], r8
0x180005a85  jbe     short loc_180005AB8
0x180005a87  mov     rcx, cs:hLogHandle; hLogHandle
0x180005a8e  mov     r9d, r12d; dwSubStringCount
0x180005a91  mov     [rsp+9D0h+dwErrorIndex], r12d; dwErrorIndex
0x180005a96  mov     r8d, 4E67h; dwMessageId
0x180005a9c  mov     [rsp+9D0h+dwErrorCode], eax; dwErrorCode
0x180005aa0  mov     edx, r12d; dwEventType
0x180005aa3  lea     rax, [rsp+9D0h+plpszSubStringArray]
0x180005aa8  mov     [rsp+9D0h+phkResult], rax; plpszSubStringArray
0x180005aad  call    cs:__imp_RouterLogEventStringA
0x180005ab3  mov     r8, [rsp+9D0h+plpszSubStringArray]
0x180005ab8  cmp     cs:byte_18004CF33, r15b
0x180005abf  jge     loc_180005FBC
0x180005ac5  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005acd  mov     r9d, ebx
0x180005ad0  jmp     loc_180005F9F
0x180005ad5  mov     cs:PppConfigInfo, r12
0x180005adc  mov     r14d, r15d
0x180005adf  cmp     r14d, [rsp+9D0h+cSubKeys]
0x180005ae4  jnb     loc_180005FD7
0x180005aea  mov     rax, cs:lpMem
0x180005af1  lea     rdx, [rsp+9D0h+var_96C]
0x180005af6  mov     esi, r14d
0x180005af9  lea     rcx, [rbp+8D0h+var_880]
0x180005afd  shl     rsi, 5
0x180005b01  mov     rax, [rsi+rax]
0x180005b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0a  mov     rbx, rax
0x180005b0d  test    eax, eax
0x180005b0f  jnz     loc_180005EEA
0x180005b15  mov     edi, [rsp+9D0h+var_96C]
0x180005b19  test    edi, edi
0x180005b1b  jz      loc_180005F3A
0x180005b21  cmp     edi, 14h
0x180005b24  ja      loc_180005F3A
0x180005b2a  mov     eax, edi
0x180005b2c  mov     ecx, 0FFFFFFFFh
0x180005b31  add     edi, ecx
0x180005b33  mov     [rsp+9D0h+var_96C], edi
0x180005b37  test    eax, eax
0x180005b39  jz      loc_180005DB7
0x180005b3f  xor     edx, edx; Val
0x180005b41  lea     rcx, [rbp+8D0h+var_930]; void *
0x180005b45  mov     r8d, 0B0h; Size
0x180005b4b  call    memset_0
0x180005b50  mov     rax, cs:lpMem
0x180005b57  lea     rdx, [rbp+8D0h+var_930]
0x180005b5b  mov     ecx, [rbp+rdi*4+8D0h+var_880]
0x180005b5f  mov     rax, [rsi+rax+8]
0x180005b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b69  mov     ebx, eax
0x180005b6b  test    eax, eax
0x180005b6d  jnz     loc_180005EEA
0x180005b73  mov     r8d, dword ptr [rbp+8D0h+var_930]
0x180005b77  cmp     r8d, 8021h
0x180005b7e  jnz     short loc_180005B8E
0x180005b80  lea     rax, IpcpDhcpInform
0x180005b87  mov     cs:qword_18004CAA8, rax
0x180005b8e  cmp     qword ptr [rbp+8D0h+var_920+8], r15
0x180005b92  jz      short loc_180005C12
0x180005b94  cmp     r8d, 8021h
0x180005b9b  jz      short loc_180005C12
0x180005b9d  cmp     r8d, 8057h
0x180005ba4  jz      short loc_180005C12
0x180005ba6  cmp     cs:byte_18004CF33, r15b
0x180005bad  jge     short loc_180005BED
0x180005baf  lea     rdx, aRascpinitXTrue; "RasCpInit(%x, TRUE)"
0x180005bb6  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005bbe  lea     rcx, [rbp+8D0h+var_830]
0x180005bc5  call    FormatRRASErrorString
0x180005bca  cmp     cs:byte_18004CF33, r15b
0x180005bd1  jge     short loc_180005BED
0x180005bd3  lea     r8, [rbp+8D0h+var_830]
0x180005bda  lea     rdx, RasPppTraceError
0x180005be1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005be8  call    McTemplateU0z_EventWriteTransfer
0x180005bed  mov     rax, qword ptr [rbp+8D0h+var_920+8]
0x180005bf1  mov     ecx, r12d
0x180005bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf9  mov     ebx, eax
0x180005bfb  mov     eax, dword ptr [rbp+8D0h+var_890+8]
0x180005bfe  or      eax, r12d
0x180005c01  mov     dword ptr [rbp+8D0h+var_890+8], eax
0x180005c04  test    ebx, ebx
0x180005c06  jnz     loc_180005DBF
0x180005c0c  or      eax, 2
0x180005c0f  mov     dword ptr [rbp+8D0h+var_890+8], eax
0x180005c12  cmp     qword ptr [rbp+8D0h+var_890], r15
0x180005c16  jnz     loc_180005D01
0x180005c1c  cmp     qword ptr [rbp+8D0h+var_910], r15
0x180005c20  jz      loc_180005E4A
0x180005c26  cmp     qword ptr [rbp+8D0h+var_910+8], r15
0x180005c2a  jz      loc_180005E4A
0x180005c30  cmp     qword ptr [rbp+8D0h+var_900], r15
0x180005c34  jz      loc_180005E4A
0x180005c3a  cmp     qword ptr [rbp+8D0h+var_8D0], r15
0x180005c3e  jz      loc_180005E4A
0x180005c44  cmp     qword ptr [rbp+8D0h+var_8D0+8], r15
0x180005c48  jz      loc_180005E4A
0x180005c4e  cmp     qword ptr [rbp+8D0h+var_8C0], r15
0x180005c52  jz      loc_180005E4A
0x180005c58  cmp     qword ptr [rbp+8D0h+var_8C0+8], r15
0x180005c5c  jz      loc_180005E4A
0x180005c62  cmp     qword ptr [rbp+8D0h+var_8B0], r15
0x180005c66  jz      loc_180005E4A
0x180005c6c  cmp     dword ptr [rbp+8D0h+var_920], 0Ch
0x180005c70  ja      loc_180005E4A
  ... truncated ...
```
