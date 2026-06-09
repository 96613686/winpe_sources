# ReadRegistryInfo

- ea: `0x180005908`
- end: `0x1800062e8`
- name: `ReadRegistryInfo`
- size: `2528`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800046e0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800049e4`
- `0x180005698`
- `0x180005908`
- `0x1800062f0`
- `0x1800073a8`
- `0x18001264c`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006229`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000627e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006229`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000627e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180005a8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180005a8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800059b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005a30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800059b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180005a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000623f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000623f`
- `rtutils!RouterLogEventA` at `0x180005ad3`
- `rtutils!RouterLogEventA` at `0x180005c3e`
- `rtutils!RouterLogEventA` at `0x180005ad3`
- `rtutils!RouterLogEventA` at `0x180005c3e`
- `rtutils!RouterLogEventStringA` at `0x1800059f1`
- `rtutils!RouterLogEventStringA` at `0x180005ce7`
- `rtutils!RouterLogEventStringA` at `0x18000604b`
- `rtutils!RouterLogEventStringA` at `0x1800060cd`
- `rtutils!RouterLogEventStringA` at `0x18000616e`
- `rtutils!RouterLogEventStringA` at `0x1800061cb`
- `rtutils!RouterLogEventStringA` at `0x1800059f1`
- `rtutils!RouterLogEventStringA` at `0x180005ce7`
- `rtutils!RouterLogEventStringA` at `0x18000604b`
- `rtutils!RouterLogEventStringA` at `0x1800060cd`
- `rtutils!RouterLogEventStringA` at `0x18000616e`
- `rtutils!RouterLogEventStringA` at `0x1800061cb`

## string_xrefs

- `0x180005a0a`: `Cannot open or obtain information about the PPP key or one of its subkeys. %d`
- `0x1800060e9`: `The Point to Point Protocol module %hs returned an error while initializing. %d`
- `0x1800061f7`: `The Point to Point Protocol module %hs returned an error while initializing. %d`
- `0x1800059a1`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp`
- `0x180005a26`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp\ControlProtocols`
- `0x180005af1`: `The Point to Point Protocol failed to load the required PAP and/or CHAP authentication modules. %d`
- `0x18000606c`: `The Control Protocol %hs in the Point to Point Protocol module %hs returned an error while initializing. %d`

## pseudocode

```c
__int64 __fastcall ReadRegistryInfo(PHKEY phkResult)
{
  DWORD dwErrorCode; // ebx
  const wchar_t *v3; // rdx
  unsigned __int64 v4; // rax
  LPVOID v5; // rcx
  DWORD LastError; // eax
  DWORD Info; // eax
  LPSTR v8; // r8
  __int64 v9; // r9
  DWORD v10; // r14d
  __int64 v11; // rsi
  unsigned int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rdi
  int v15; // eax
  __int64 v16; // rcx
  char *v17; // rax
  HRESULT v18; // eax
  __int64 v19; // rcx
  char *v20; // rax
  DWORD i; // edi
  void *v22; // r8
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v25; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG ulMinuend; // [rsp+68h] [rbp-98h] BYREF
  LPSTR plpszSubStringArray; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-74h] BYREF
  LPSTR v33[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+C0h] [rbp-40h]
  __int128 v37; // [rsp+D0h] [rbp-30h]
  __int128 v38; // [rsp+E0h] [rbp-20h]
  __int128 v39; // [rsp+F0h] [rbp-10h]
  __int128 v40; // [rsp+100h] [rbp+0h]
  __int128 v41; // [rsp+110h] [rbp+10h]
  __int128 v42; // [rsp+120h] [rbp+20h]
  __int128 v43; // [rsp+130h] [rbp+30h]
  __int128 v44; // [rsp+140h] [rbp+40h]
  _DWORD v45[20]; // [rsp+150h] [rbp+50h] BYREF
  int v46; // [rsp+1A0h] [rbp+A0h] BYREF
  char v47[2044]; // [rsp+1A4h] [rbp+A4h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v25 = 0;
  ulMinuend = 0;
  memset_0(&v34, 0, 0xB0u);
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
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
    if ( dword_18004DA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E65u, 0, 0, dwErrorCode, 0);
    if ( byte_18004DF33 >= 0 )
      goto LABEL_88;
    v3 = L"Cannot open or obtain information about the PPP key or one of its subkeys. %d";
    goto LABEL_13;
  }
  if ( !cSubKeys )
  {
    if ( dword_18004DA20 )
      RouterLogEventA(hLogHandle, 1u, 0x4E68u, 0, 0, 0);
    dwErrorCode = 1015;
    if ( byte_18004DF33 >= 0 )
      goto LABEL_88;
    v3 = L"The Point to Point Protocol failed to load the required PAP and/or CHAP authentication modules. %d";
LABEL_13:
    LOWORD(v46) = 0;
    FormatRRASErrorString((wchar_t *)&v46, v3, dwErrorCode);
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
  LODWORD(plpszSubStringArray) = 32 * (cSubKeys + 1);
  lpMem = HeapAlloc(hHeap, 8u, (unsigned int)v4);
  v5 = lpMem;
  if ( !lpMem )
    goto LABEL_22;
  *((_QWORD *)lpMem + 4 * cSubKeys + 3) = -1;
  dwErrorCode = LoadProtocolDlls((__int64)v5, cSubKeys, hKey, &ulMinuend);
  if ( dwErrorCode )
    goto LABEL_88;
  CpTable = HeapAlloc(hHeap, 8u, 176LL * (ulMinuend + 1));
  if ( !CpTable )
  {
LABEL_22:
    LastError = GetLastError();
    dwErrorCode = LastError;
    if ( dword_18004DA20 )
      RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString((wchar_t *)&v46, L"Memory allocation failure %d", dwErrorCode);
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    if ( dwErrorCode )
      goto LABEL_88;
    goto LABEL_90;
  }
  Info = LcpGetInfo();
  dwErrorCode = Info;
  if ( Info )
  {
    v8 = "LCP";
    plpszSubStringArray = "LCP";
    if ( dword_18004DA20 )
    {
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, &plpszSubStringArray, Info, 1u);
      v8 = plpszSubStringArray;
    }
    if ( byte_18004DF33 >= 0 )
      goto LABEL_88;
    LOWORD(v46) = 0;
    v9 = dwErrorCode;
    goto LABEL_86;
  }
  PppConfigInfo = 1;
  v10 = 0;
LABEL_35:
  if ( v10 >= cSubKeys )
    goto LABEL_90;
  v11 = 32LL * v10;
  dwErrorCode = (*(__int64 (__fastcall **)(_DWORD *, unsigned int *))((char *)lpMem + v11))(v45, &v25);
  if ( dwErrorCode )
  {
LABEL_77:
    if ( dword_18004DA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v11 + 16), dwErrorCode, 1u);
    if ( byte_18004DF33 >= 0 )
      goto LABEL_88;
    v9 = dwErrorCode;
LABEL_85:
    LOWORD(v46) = 0;
    v8 = *(LPSTR *)((char *)lpMem + v11 + 16);
LABEL_86:
    FormatRRASErrorString(
      (wchar_t *)&v46,
      L"The Point to Point Protocol module %hs returned an error while initializing. %d",
      v8,
      v9);
LABEL_14:
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    goto LABEL_88;
  }
  v12 = v25;
  if ( !v25 || v25 > 0x14 )
  {
    dwErrorCode = 87;
    if ( dword_18004DA20 )
      RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v11 + 16), 0x57u, 1u);
    if ( byte_18004DF33 >= 0 )
      goto LABEL_88;
    v9 = 87;
    goto LABEL_85;
  }
  while ( 1 )
  {
    v13 = v12;
    v14 = v12 - 1;
    v25 = v14;
    if ( !v13 )
      goto LABEL_66;
    memset_0(&v34, 0, 0xB0u);
    dwErrorCode = (*(__int64 (__fastcall **)(_QWORD, __int128 *))((char *)lpMem + v11 + 8))(
                    (unsigned int)v45[v14],
                    &v34);
    if ( dwErrorCode )
      goto LABEL_77;
    if ( (_DWORD)v34 == 32801 )
      qword_18004DAA8 = IpcpDhcpInform;
    if ( *((_QWORD *)&v35 + 1) && (_DWORD)v34 != 32801 && (_DWORD)v34 != 32855 )
      break;
LABEL_51:
    if ( (_QWORD)v44 )
    {
      v18 = ULongSub(ulMinuend, HIDWORD(PppConfigInfo), (ULONG *)&plpszSubStringArray);
      if ( v18 < 0 )
      {
        dwErrorCode = (unsigned __int16)v18;
        if ( (_WORD)v18 )
          goto LABEL_88;
LABEL_66:
        ++v10;
        goto LABEL_35;
      }
      v19 = 176LL * (unsigned int)plpszSubStringArray;
      v20 = (char *)CpTable;
      *(_OWORD *)((char *)CpTable + v19) = v34;
      *(_OWORD *)&v20[v19 + 16] = v35;
      *(_OWORD *)&v20[v19 + 32] = v36;
      *(_OWORD *)&v20[v19 + 48] = v37;
      *(_OWORD *)&v20[v19 + 64] = v38;
      *(_OWORD *)&v20[v19 + 80] = v39;
      *(_OWORD *)&v20[v19 + 96] = v40;
      *(_OWORD *)&v20[v19 + 112] = v41;
      *(_OWORD *)&v20[v19 + 128] = v42;
      *(_OWORD *)&v20[v19 + 144] = v43;
      *(_OWORD *)&v20[v19 + 160] = v44;
      ++HIDWORD(PppConfigInfo);
    }
    else
    {
      if ( !(_QWORD)v36
        || !*((_QWORD *)&v36 + 1)
        || !(_QWORD)v37
        || !(_QWORD)v40
        || !*((_QWORD *)&v40 + 1)
        || !(_QWORD)v41
        || !*((_QWORD *)&v41 + 1)
        || !(_QWORD)v42
        || (unsigned int)v35 > 0xC )
      {
        if ( dword_18004DA20 )
          RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)((char *)lpMem + v11 + 16), 0x57u, 1u);
        if ( byte_18004DF33 < 0 )
        {
          LOWORD(v46) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v46,
            L"The Point to Point Protocol module %hs returned an error while initializing. %d",
            *(_QWORD *)((char *)lpMem + v11 + 16),
            87);
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
        }
        dwErrorCode = 87;
        goto LABEL_88;
      }
      v16 = 176LL * (unsigned int)PppConfigInfo;
      v17 = (char *)CpTable;
      *(_OWORD *)((char *)CpTable + v16) = v34;
      *(_OWORD *)&v17[v16 + 16] = v35;
      *(_OWORD *)&v17[v16 + 32] = v36;
      *(_OWORD *)&v17[v16 + 48] = v37;
      *(_OWORD *)&v17[v16 + 64] = v38;
      *(_OWORD *)&v17[v16 + 80] = v39;
      *(_OWORD *)&v17[v16 + 96] = v40;
      *(_OWORD *)&v17[v16 + 112] = v41;
      *(_OWORD *)&v17[v16 + 128] = v42;
      *(_OWORD *)&v17[v16 + 144] = v43;
      *(_OWORD *)&v17[v16 + 160] = v44;
      LODWORD(PppConfigInfo) = PppConfigInfo + 1;
    }
    v12 = v25;
  }
  if ( byte_18004DF33 < 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString((wchar_t *)&v46, L"RasCpInit(%x, TRUE)");
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
  }
  dwErrorCode = (*((__int64 (__fastcall **)(__int64))&v35 + 1))(1);
  v15 = DWORD2(v44) | 1;
  DWORD2(v44) |= 1u;
  if ( !dwErrorCode )
  {
    DWORD2(v44) = v15 | 2;
    goto LABEL_51;
  }
  v33[0] = (char *)&v34 + 4;
  v33[1] = *(LPSTR *)((char *)lpMem + v11 + 16);
  if ( dword_18004DA20 )
    RouterLogEventStringA(hLogHandle, 1u, 0x4EB7u, 2u, v33, dwErrorCode, 2u);
  if ( byte_18004DF33 < 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v46,
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
      v22 = (void *)*((_QWORD *)lpMem + 4 * i + 2);
      if ( v22 )
        HeapFree(hHeap, 0, v22);
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
0x180005908  mov     [rsp-8+arg_8], rbx
0x18000590d  mov     [rsp-8+arg_10], rsi
0x180005912  push    rbp
0x180005913  push    rdi
0x180005914  push    r12
0x180005916  push    r14
0x180005918  push    r15
0x18000591a  lea     rbp, [rsp-8B0h]
0x180005922  sub     rsp, 9B0h
0x180005929  mov     rax, cs:__security_cookie
0x180005930  xor     rax, rsp
0x180005933  mov     [rbp+8D0h+var_30], rax
0x18000593a  xor     r15d, r15d
0x18000593d  mov     rdi, rcx
0x180005940  lea     rcx, [rbp+8D0h+var_930]; void *
0x180005944  mov     [rsp+9D0h+hKey], r15
0x180005949  xor     edx, edx; Val
0x18000594b  mov     [rsp+9D0h+cSubKeys], r15d
0x180005950  mov     r8d, 0B0h; Size
0x180005956  mov     [rbp+8D0h+cbMaxSubKeyLen], r15d
0x18000595a  mov     [rbp+8D0h+cValues], r15d
0x18000595e  mov     [rbp+8D0h+cbMaxValueNameLen], r15d
0x180005962  mov     [rbp+8D0h+cbMaxValueLen], r15d
0x180005966  mov     [rsp+9D0h+var_96C], r15d
0x18000596b  mov     [rsp+9D0h+ulMinuend], r15d
0x180005970  call    memset_0
0x180005975  xor     edx, edx; Val
0x180005977  mov     [rbp+8D0h+var_830], r15d
0x18000597e  mov     r8d, 7FCh; Size
0x180005984  lea     rcx, [rbp+8D0h+var_82C]; void *
0x18000598b  call    memset_0
0x180005990  mov     esi, 20019h
0x180005995  mov     [rsp+9D0h+phkResult], rdi; phkResult
0x18000599a  mov     r14, 0FFFFFFFF80000002h
0x1800059a1  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800059a8  mov     r9d, esi; samDesired
0x1800059ab  mov     rcx, r14; hKey
0x1800059ae  xor     r8d, r8d; ulOptions
0x1800059b1  call    cs:__imp_RegOpenKeyExA
0x1800059b8  nop     dword ptr [rax+rax+00h]
0x1800059bd  lea     r12d, [r15+1]
0x1800059c1  mov     ebx, eax
0x1800059c3  test    eax, eax
0x1800059c5  jz      short loc_180005A16
0x1800059c7  cmp     cs:dword_18004DA20, r15d
0x1800059ce  jbe     short loc_1800059FD
0x1800059d0  mov     rcx, cs:hLogHandle; hLogHandle
0x1800059d7  xor     r9d, r9d; dwSubStringCount
0x1800059da  mov     [rsp+9D0h+dwErrorIndex], r15d; dwErrorIndex
0x1800059df  mov     r8d, 4E65h; dwMessageId
0x1800059e5  mov     [rsp+9D0h+dwErrorCode], ebx; dwErrorCode
0x1800059e9  mov     edx, r12d; dwEventType
0x1800059ec  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x1800059f1  call    cs:__imp_RouterLogEventStringA
0x1800059f8  nop     dword ptr [rax+rax+00h]
0x1800059fd  cmp     cs:byte_18004DF33, r15b
0x180005a04  jge     loc_180006214
0x180005a0a  lea     rdx, aCannotOpenOrOb; "Cannot open or obtain information about"...
0x180005a11  jmp     loc_180005AF8
0x180005a16  lea     rax, [rsp+9D0h+hKey]
0x180005a1b  mov     r9d, esi; samDesired
0x180005a1e  xor     r8d, r8d; ulOptions
0x180005a21  mov     [rsp+9D0h+phkResult], rax; phkResult
0x180005a26  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180005a2d  mov     rcx, r14; hKey
0x180005a30  call    cs:__imp_RegOpenKeyExA
0x180005a37  nop     dword ptr [rax+rax+00h]
0x180005a3c  mov     ebx, eax
0x180005a3e  test    eax, eax
0x180005a40  jnz     short loc_1800059C7
0x180005a42  mov     rcx, [rsp+9D0h+hKey]; hKey
0x180005a47  lea     rax, [rbp+8D0h+cbMaxValueLen]
0x180005a4b  mov     [rsp+9D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005a50  xor     r9d, r9d; lpReserved
0x180005a53  mov     [rsp+9D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180005a58  xor     r8d, r8d; lpcchClass
0x180005a5b  mov     [rsp+9D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180005a60  xor     edx, edx; lpClass
0x180005a62  lea     rax, [rbp+8D0h+cbMaxValueNameLen]
0x180005a66  mov     [rsp+9D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180005a6b  lea     rax, [rbp+8D0h+cValues]
0x180005a6f  mov     [rsp+9D0h+lpcValues], rax; lpcValues
0x180005a74  lea     rax, [rbp+8D0h+cbMaxSubKeyLen]
0x180005a78  mov     qword ptr [rsp+9D0h+dwErrorIndex], r15; lpcbMaxClassLen
0x180005a7d  mov     qword ptr [rsp+9D0h+dwErrorCode], rax; lpcbMaxSubKeyLen
0x180005a82  lea     rax, [rsp+9D0h+cSubKeys]
0x180005a87  mov     [rsp+9D0h+phkResult], rax; lpcSubKeys
0x180005a8c  call    cs:__imp_RegQueryInfoKeyA
0x180005a93  nop     dword ptr [rax+rax+00h]
0x180005a98  mov     ebx, eax
0x180005a9a  test    eax, eax
0x180005a9c  jnz     loc_1800059C7
0x180005aa2  cmp     [rsp+9D0h+cSubKeys], r15d
0x180005aa7  jnz     loc_180005B3B
0x180005aad  cmp     cs:dword_18004DA20, r15d
0x180005ab4  jbe     short loc_180005ADF
0x180005ab6  mov     rcx, cs:hLogHandle; hLogHandle
0x180005abd  xor     r9d, r9d; dwSubStringCount
0x180005ac0  mov     [rsp+9D0h+dwErrorCode], r15d; dwErrorCode
0x180005ac5  mov     r8d, 4E68h; dwMessageId
0x180005acb  mov     edx, r12d; dwEventType
0x180005ace  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x180005ad3  call    cs:__imp_RouterLogEventA
0x180005ada  nop     dword ptr [rax+rax+00h]
0x180005adf  cmp     cs:byte_18004DF33, r15b
0x180005ae6  mov     ebx, 3F7h
0x180005aeb  jge     loc_180006214
0x180005af1  lea     rdx, aThePointToPoin_0; "The Point to Point Protocol failed to l"...
0x180005af8  mov     r8d, ebx
0x180005afb  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005b03  lea     rcx, [rbp+8D0h+var_830]
0x180005b0a  call    FormatRRASErrorString
0x180005b0f  cmp     cs:byte_18004DF33, r15b
0x180005b16  jge     loc_180006214
0x180005b1c  lea     r8, [rbp+8D0h+var_830]
0x180005b23  lea     rdx, RasPppTraceError
0x180005b2a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005b31  call    McTemplateU0z_EventWriteTransfer
0x180005b36  jmp     loc_180006214
0x180005b3b  mov     rcx, [rdi]; hKey
0x180005b3e  call    ReadPPPKeyValues
0x180005b43  mov     ebx, eax
0x180005b45  test    eax, eax
0x180005b47  jnz     loc_180006214
0x180005b4d  mov     rcx, cs:hKey; hKey
0x180005b54  call    LoadParserDll
0x180005b59  mov     eax, [rsp+9D0h+cSubKeys]
0x180005b5d  lea     ecx, [rax+1]
0x180005b60  cmp     ecx, eax
0x180005b62  jb      loc_18000620F
0x180005b68  mov     eax, ecx
0x180005b6a  mov     ecx, 0FFFFFFFFh
0x180005b6f  shl     rax, 5
0x180005b73  cmp     rax, rcx
0x180005b76  ja      loc_18000620F
0x180005b7c  mov     rcx, cs:hHeap; hHeap
0x180005b83  lea     edi, [rbx+8]
0x180005b86  mov     r8d, eax; dwBytes
0x180005b89  mov     edx, edi; dwFlags
0x180005b8b  mov     dword ptr [rsp+9D0h+plpszSubStringArray], r8d
0x180005b90  call    cs:__imp_HeapAlloc
0x180005b97  nop     dword ptr [rax+rax+00h]
0x180005b9c  mov     cs:lpMem, rax
0x180005ba3  mov     rcx, rax
0x180005ba6  test    rax, rax
0x180005ba9  jz      short loc_180005C0B
0x180005bab  mov     eax, [rsp+9D0h+cSubKeys]
0x180005baf  lea     r9, [rsp+9D0h+ulMinuend]
0x180005bb4  shl     rax, 5
0x180005bb8  mov     qword ptr [rax+rcx+18h], 0FFFFFFFFFFFFFFFFh
0x180005bc1  mov     r8, [rsp+9D0h+hKey]
0x180005bc6  mov     edx, [rsp+9D0h+cSubKeys]
0x180005bca  call    LoadProtocolDlls
0x180005bcf  mov     ebx, eax
0x180005bd1  test    eax, eax
0x180005bd3  jnz     loc_180006214
0x180005bd9  mov     ecx, [rsp+9D0h+ulMinuend]
0x180005bdd  mov     edx, edi; dwFlags
0x180005bdf  inc     ecx
0x180005be1  imul    r8, rcx, 0B0h; dwBytes
0x180005be8  mov     rcx, cs:hHeap; hHeap
0x180005bef  call    cs:__imp_HeapAlloc
0x180005bf6  nop     dword ptr [rax+rax+00h]
0x180005bfb  mov     cs:CpTable, rax
0x180005c02  test    rax, rax
0x180005c05  jnz     loc_180005CA1
0x180005c0b  call    cs:__imp_GetLastError
0x180005c12  nop     dword ptr [rax+rax+00h]
0x180005c17  cmp     cs:dword_18004DA20, r15d
0x180005c1e  mov     ebx, eax
0x180005c20  jbe     short loc_180005C4A
0x180005c22  mov     rcx, cs:hLogHandle; hLogHandle
0x180005c29  xor     r9d, r9d; dwSubStringCount
0x180005c2c  mov     [rsp+9D0h+dwErrorCode], eax; dwErrorCode
0x180005c30  mov     r8d, 4E88h; dwMessageId
0x180005c36  mov     edx, r12d; dwEventType
0x180005c39  mov     [rsp+9D0h+phkResult], r15; plpszSubStringArray
0x180005c3e  call    cs:__imp_RouterLogEventA
0x180005c45  nop     dword ptr [rax+rax+00h]
0x180005c4a  cmp     cs:byte_18004DF33, r15b
0x180005c51  jge     short loc_180005C94
0x180005c53  mov     r8d, ebx
0x180005c56  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005c5e  lea     rdx, aMemoryAllocati_1; "Memory allocation failure %d"
0x180005c65  lea     rcx, [rbp+8D0h+var_830]
0x180005c6c  call    FormatRRASErrorString
0x180005c71  cmp     cs:byte_18004DF33, r15b
0x180005c78  jge     short loc_180005C94
0x180005c7a  lea     r8, [rbp+8D0h+var_830]
0x180005c81  lea     rdx, RasPppTraceError
0x180005c88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005c8f  call    McTemplateU0z_EventWriteTransfer
0x180005c94  test    ebx, ebx
0x180005c96  jnz     loc_180006214
0x180005c9c  jmp     loc_180006235
0x180005ca1  call    LcpGetInfo
0x180005ca6  mov     ebx, eax
0x180005ca8  test    eax, eax
0x180005caa  jz      short loc_180005D15
0x180005cac  cmp     cs:dword_18004DA20, r15d
0x180005cb3  lea     r8, aLcp; "LCP"
0x180005cba  mov     [rsp+9D0h+plpszSubStringArray], r8
0x180005cbf  jbe     short loc_180005CF8
0x180005cc1  mov     rcx, cs:hLogHandle; hLogHandle
0x180005cc8  mov     r9d, r12d; dwSubStringCount
0x180005ccb  mov     [rsp+9D0h+dwErrorIndex], r12d; dwErrorIndex
0x180005cd0  mov     r8d, 4E67h; dwMessageId
0x180005cd6  mov     [rsp+9D0h+dwErrorCode], eax; dwErrorCode
0x180005cda  mov     edx, r12d; dwEventType
0x180005cdd  lea     rax, [rsp+9D0h+plpszSubStringArray]
0x180005ce2  mov     [rsp+9D0h+phkResult], rax; plpszSubStringArray
0x180005ce7  call    cs:__imp_RouterLogEventStringA
0x180005cee  nop     dword ptr [rax+rax+00h]
0x180005cf3  mov     r8, [rsp+9D0h+plpszSubStringArray]
0x180005cf8  cmp     cs:byte_18004DF33, r15b
0x180005cff  jge     loc_180006214
0x180005d05  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005d0d  mov     r9d, ebx
0x180005d10  jmp     loc_1800061F7
0x180005d15  mov     cs:PppConfigInfo, r12
0x180005d1c  mov     r14d, r15d
0x180005d1f  cmp     r14d, [rsp+9D0h+cSubKeys]
0x180005d24  jnb     loc_180006235
0x180005d2a  mov     rax, cs:lpMem
0x180005d31  lea     rdx, [rsp+9D0h+var_96C]
0x180005d36  mov     esi, r14d
0x180005d39  lea     rcx, [rbp+8D0h+var_880]
0x180005d3d  shl     rsi, 5
0x180005d41  mov     rax, [rsi+rax]
0x180005d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4a  mov     rbx, rax
0x180005d4d  test    eax, eax
0x180005d4f  jnz     loc_180006136
0x180005d55  mov     edi, [rsp+9D0h+var_96C]
0x180005d59  test    edi, edi
0x180005d5b  jz      loc_18000618C
0x180005d61  cmp     edi, 14h
0x180005d64  ja      loc_18000618C
0x180005d6a  mov     eax, edi
0x180005d6c  mov     ecx, 0FFFFFFFFh
0x180005d71  add     edi, ecx
0x180005d73  mov     [rsp+9D0h+var_96C], edi
0x180005d77  test    eax, eax
0x180005d79  jz      loc_180005FF7
0x180005d7f  xor     edx, edx; Val
0x180005d81  lea     rcx, [rbp+8D0h+var_930]; void *
0x180005d85  mov     r8d, 0B0h; Size
0x180005d8b  call    memset_0
0x180005d90  mov     rax, cs:lpMem
0x180005d97  lea     rdx, [rbp+8D0h+var_930]
0x180005d9b  mov     ecx, [rbp+rdi*4+8D0h+var_880]
0x180005d9f  mov     rax, [rsi+rax+8]
0x180005da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da9  mov     ebx, eax
0x180005dab  test    eax, eax
0x180005dad  jnz     loc_180006136
0x180005db3  mov     r8d, dword ptr [rbp+8D0h+var_930]
0x180005db7  cmp     r8d, 8021h
0x180005dbe  jnz     short loc_180005DCE
0x180005dc0  lea     rax, IpcpDhcpInform
0x180005dc7  mov     cs:qword_18004DAA8, rax
0x180005dce  cmp     qword ptr [rbp+8D0h+var_920+8], r15
0x180005dd2  jz      short loc_180005E52
0x180005dd4  cmp     r8d, 8021h
0x180005ddb  jz      short loc_180005E52
0x180005ddd  cmp     r8d, 8057h
0x180005de4  jz      short loc_180005E52
0x180005de6  cmp     cs:byte_18004DF33, r15b
0x180005ded  jge     short loc_180005E2D
0x180005def  lea     rdx, aRascpinitXTrue; "RasCpInit(%x, TRUE)"
0x180005df6  mov     word ptr [rbp+8D0h+var_830], r15w
0x180005dfe  lea     rcx, [rbp+8D0h+var_830]
0x180005e05  call    FormatRRASErrorString
0x180005e0a  cmp     cs:byte_18004DF33, r15b
0x180005e11  jge     short loc_180005E2D
0x180005e13  lea     r8, [rbp+8D0h+var_830]
0x180005e1a  lea     rdx, RasPppTraceError
0x180005e21  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005e28  call    McTemplateU0z_EventWriteTransfer
0x180005e2d  mov     rax, qword ptr [rbp+8D0h+var_920+8]
0x180005e31  mov     ecx, r12d
0x180005e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e39  mov     ebx, eax
0x180005e3b  mov     eax, dword ptr [rbp+8D0h+var_890+8]
0x180005e3e  or      eax, r12d
0x180005e41  mov     dword ptr [rbp+8D0h+var_890+8], eax
0x180005e44  test    ebx, ebx
0x180005e46  jnz     loc_180005FFF
0x180005e4c  or      eax, 2
0x180005e4f  mov     dword ptr [rbp+8D0h+var_890+8], eax
0x180005e52  cmp     qword ptr [rbp+8D0h+var_890], r15
0x180005e56  jnz     loc_180005F41
0x180005e5c  cmp     qword ptr [rbp+8D0h+var_910], r15
0x180005e60  jz      loc_180006090
0x180005e66  cmp     qword ptr [rbp+8D0h+var_910+8], r15
0x180005e6a  jz      loc_180006090
0x180005e70  cmp     qword ptr [rbp+8D0h+var_900], r15
0x180005e74  jz      loc_180006090
0x180005e7a  cmp     qword ptr [rbp+8D0h+var_8D0], r15
0x180005e7e  jz      loc_180006090
  ... truncated ...
```
