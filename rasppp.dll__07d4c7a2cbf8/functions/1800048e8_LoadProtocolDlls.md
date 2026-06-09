# LoadProtocolDlls

- ea: `0x1800048e8`
- end: `0x180004ea3`
- name: `LoadProtocolDlls`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005704`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800048e8`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004af0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180004aa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180004aa4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800049b3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800049b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180004a47`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180004a47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800049ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800049ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ba2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004b89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004b28`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004b28`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004ad2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004b0d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004ad2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004b0d`
- `rtutils!RouterLogEventA` at `0x180004d28`
- `rtutils!RouterLogEventA` at `0x180004d73`
- `rtutils!RouterLogEventA` at `0x180004dc8`
- `rtutils!RouterLogEventA` at `0x180004d28`
- `rtutils!RouterLogEventA` at `0x180004d73`
- `rtutils!RouterLogEventA` at `0x180004dc8`
- `rtutils!RouterLogEventStringA` at `0x180004c0b`
- `rtutils!RouterLogEventStringA` at `0x180004c67`
- `rtutils!RouterLogEventStringA` at `0x180004ce0`
- `rtutils!RouterLogEventStringA` at `0x180004e09`
- `rtutils!RouterLogEventStringA` at `0x180004c0b`
- `rtutils!RouterLogEventStringA` at `0x180004c67`
- `rtutils!RouterLogEventStringA` at `0x180004ce0`
- `rtutils!RouterLogEventStringA` at `0x180004e09`

## string_xrefs

- `0x180004c1e`: `Cannot enumerate Registry key values %d`
- `0x180004e18`: `Cannot open or obtain information about the PPP key or one of its subkeys. %d`
- `0x180004d3b`: `Cannot access registry key values %d.`
- `0x180004cf3`: `Point to Point Protocol engine was unable to load the %hs module. %d`
- `0x180004b3a`: `RasCpEnumProtocolIds`
- `0x180004c7a`: `The Point to Point Protocol module %hs returned an error while initializing. %d`

## pseudocode

```c
__int64 __fastcall LoadProtocolDlls(__int64 a1, DWORD a2, HKEY a3, _DWORD *a4)
{
  char *v4; // r12
  DWORD v6; // esi
  DWORD v7; // ebx
  DWORD i; // r15d
  BYTE *v10; // rdi
  LSTATUS v11; // eax
  DWORD v12; // eax
  DWORD v13; // ebx
  CHAR *v14; // rax
  HMODULE Library; // rax
  HMODULE v16; // rsi
  FARPROC ProcAddress; // rax
  __int64 v18; // r14
  FARPROC v19; // rax
  HKEY v20; // rcx
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rdx
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD LastError; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR lpLibFileName; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  int v32; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cSubKeys; // [rsp+90h] [rbp-70h] BYREF
  DWORD v37; // [rsp+94h] [rbp-6Ch]
  _DWORD *v38; // [rsp+98h] [rbp-68h]
  char v39[80]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR Name[112]; // [rsp+F0h] [rbp-10h] BYREF
  int v41; // [rsp+160h] [rbp+60h] BYREF
  char v42[2044]; // [rsp+164h] [rbp+64h] BYREF

  v4 = (char *)lpMem;
  v37 = a2;
  phkResult = 0;
  v6 = a2;
  lpLibFileName = 0;
  cchName = 0;
  cSubKeys = 0;
  v7 = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v32 = 0;
  Type = 0;
  v41 = 0;
  v38 = a4;
  memset_0(v42, 0, sizeof(v42));
  *a4 = 0;
  for ( i = 0; ; ++i )
  {
    v10 = 0;
    if ( i >= v6 )
      goto LABEL_55;
    cchName = 100;
    v11 = RegEnumKeyExA(a3, i, Name, &cchName, 0, 0, 0, 0);
    v7 = v11;
    if ( v11 && v11 != 234 && v11 != 259 )
    {
      if ( dword_18004CA20 )
        RouterLogEventStringA(hLogHandle, 1u, 0x4E23u, 0, 0, v11, 0);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v21 = L"Cannot enumerate Registry key values %d";
      goto LABEL_52;
    }
    v7 = RegOpenKeyExA(a3, Name, 0, 1u, &phkResult);
    if ( v7
      || (v7 = RegQueryInfoKeyA(
                 phkResult,
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
        RouterLogEventStringA(hLogHandle, 1u, 0x4E65u, 0, 0, v7, 0);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v21 = L"Cannot open or obtain information about the PPP key or one of its subkeys. %d";
      goto LABEL_52;
    }
    v10 = (BYTE *)HeapAlloc(hHeap, 8u, ++cbMaxValueLen + 1);
    if ( !v10 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( dword_18004CA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v21 = L"Memory allocation failure %d";
      goto LABEL_52;
    }
    v7 = RegQueryValueExA(phkResult, "Path", 0, &Type, v10, &cbMaxValueLen);
    if ( v7 )
      goto LABEL_35;
    if ( Type - 1 > 1 )
    {
      v7 = 1015;
      goto LABEL_35;
    }
    v10[cbMaxValueLen] = 0;
    v12 = ExpandEnvironmentStringsA((LPCSTR)v10, 0, 0);
    if ( !v12 )
      goto LABEL_34;
    v13 = v12 + 1;
    v14 = (CHAR *)HeapAlloc(hHeap, 8u, v12 + 1);
    lpLibFileName = v14;
    if ( !v14 )
    {
      v24 = GetLastError();
      v7 = v24;
      if ( dword_18004CA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, v24);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v21 = L"Memory allocation failure %d.";
      goto LABEL_52;
    }
    if ( !ExpandEnvironmentStringsA((LPCSTR)v10, v14, v13) )
    {
LABEL_34:
      v7 = GetLastError();
LABEL_35:
      if ( dword_18004CA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E22u, 0, 0, v7);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v21 = L"Cannot access registry key values %d.";
LABEL_52:
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, v21, v7);
      goto LABEL_53;
    }
    Library = LoadLibraryExA(lpLibFileName, 0, 0x1000u);
    v16 = Library;
    if ( !Library )
    {
      v23 = GetLastError();
      v7 = v23;
      if ( dword_18004CA20 )
        RouterLogEventStringA(hLogHandle, 1u, 0x4E66u, 1u, (LPSTR *)&lpLibFileName, v23, 1u);
      if ( byte_18004CF33 >= 0 )
        goto LABEL_55;
      v22 = L"Point to Point Protocol engine was unable to load the %hs module. %d";
LABEL_28:
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, v22, lpLibFileName, v7);
LABEL_53:
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v41);
      goto LABEL_55;
    }
    ProcAddress = GetProcAddress(Library, "RasCpEnumProtocolIds");
    if ( !ProcAddress )
      break;
    v18 = 32LL * i;
    *(_QWORD *)&v4[v18] = ProcAddress;
    v7 = ((__int64 (__fastcall *)(char *, int *))ProcAddress)(v39, &v32);
    if ( v7 )
      goto LABEL_24;
    *v38 += v32;
    v19 = GetProcAddress(v16, "RasCpGetInfo");
    if ( !v19 )
      break;
    v20 = phkResult;
    *(_QWORD *)&v4[v18 + 8] = v19;
    RegCloseKey(v20);
    *(_QWORD *)&v4[v18 + 16] = lpLibFileName;
    *(_QWORD *)&v4[v18 + 24] = v16;
    phkResult = 0;
    HeapFree(hHeap, 0, v10);
    v6 = v37;
  }
  v7 = GetLastError();
LABEL_24:
  if ( dword_18004CA20 )
    RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)&lpLibFileName, v7, 1u);
  if ( byte_18004CF33 < 0 )
  {
    v22 = L"The Point to Point Protocol module %hs returned an error while initializing. %d";
    goto LABEL_28;
  }
LABEL_55:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v10 )
    HeapFree(hHeap, 0, v10);
  return v7;
}

```

## disassembly

```asm
0x1800048e8  mov     [rsp-8+arg_0], rbx
0x1800048ed  push    rbp
0x1800048ee  push    rsi
0x1800048ef  push    rdi
0x1800048f0  push    r12
0x1800048f2  push    r13
0x1800048f4  push    r14
0x1800048f6  push    r15
0x1800048f8  lea     rbp, [rsp-870h]
0x180004900  sub     rsp, 970h
0x180004907  mov     rax, cs:__security_cookie
0x18000490e  xor     rax, rsp
0x180004911  mov     [rbp+8A0h+var_40], rax
0x180004918  mov     r12, cs:lpMem
0x18000491f  lea     rcx, [rbp+8A0h+var_83C]; void *
0x180004923  xor     r14d, r14d
0x180004926  mov     [rbp+8A0h+var_90C], edx
0x180004929  mov     r13, r8
0x18000492c  mov     [rsp+9A0h+phkResult], r14
0x180004931  mov     esi, edx
0x180004933  mov     [rsp+9A0h+lpLibFileName], r14
0x180004938  xor     edx, edx; Val
0x18000493a  mov     [rsp+9A0h+cchName], r14d
0x18000493f  mov     r8d, 7FCh; Size
0x180004945  mov     [rbp+8A0h+cSubKeys], r14d
0x180004949  mov     ebx, r14d
0x18000494c  mov     [rbp+8A0h+cbMaxSubKeyLen], r14d
0x180004950  mov     [rbp+8A0h+cValues], r14d
0x180004954  mov     rdi, r9
0x180004957  mov     [rbp+8A0h+cbMaxValueNameLen], r14d
0x18000495b  mov     [rsp+9A0h+cbMaxValueLen], r14d
0x180004960  mov     [rbp+8A0h+var_920], r14d
0x180004964  mov     [rsp+9A0h+Type], r14d
0x180004969  mov     [rbp+8A0h+var_840], r14d
0x18000496d  mov     [rbp+8A0h+var_908], r9
0x180004971  call    memset_0
0x180004976  mov     [rdi], r14d
0x180004979  mov     r15d, r14d
0x18000497c  mov     rdi, r14
0x18000497f  cmp     r15d, esi
0x180004982  jnb     loc_180004E50
0x180004988  mov     [rsp+9A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000498d  lea     r9, [rsp+9A0h+cchName]; lpcchName
0x180004992  mov     [rsp+9A0h+lpcchClass], r14; lpcchClass
0x180004997  lea     r8, [rbp+8A0h+Name]; lpName
0x18000499b  mov     [rsp+9A0h+lpClass], r14; lpClass
0x1800049a0  mov     edx, r15d; dwIndex
0x1800049a3  mov     rcx, r13; hKey
0x1800049a6  mov     [rsp+9A0h+lpReserved], r14; lpReserved
0x1800049ab  mov     [rsp+9A0h+cchName], 64h ; 'd'
0x1800049b3  call    cs:__imp_RegEnumKeyExA
0x1800049b9  mov     ebx, eax
0x1800049bb  test    eax, eax
0x1800049bd  jz      short loc_1800049D1
0x1800049bf  cmp     eax, 0EAh
0x1800049c4  jz      short loc_1800049D1
0x1800049c6  cmp     eax, 103h
0x1800049cb  jnz     loc_180004BE0
0x1800049d1  lea     rax, [rsp+9A0h+phkResult]
0x1800049d6  mov     esi, 1
0x1800049db  mov     r9d, esi; samDesired
0x1800049de  mov     [rsp+9A0h+lpReserved], rax; phkResult
0x1800049e3  xor     r8d, r8d; ulOptions
0x1800049e6  lea     rdx, [rbp+8A0h+Name]; lpSubKey
0x1800049ea  mov     rcx, r13; hKey
0x1800049ed  call    cs:__imp_RegOpenKeyExA
0x1800049f3  mov     ebx, eax
0x1800049f5  test    eax, eax
0x1800049f7  jnz     loc_180004DE0
0x1800049fd  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004a02  lea     rax, [rsp+9A0h+cbMaxValueLen]
0x180004a07  mov     [rsp+9A0h+var_948], r14; lpftLastWriteTime
0x180004a0c  xor     r9d, r9d; lpReserved
0x180004a0f  mov     [rsp+9A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180004a14  xor     r8d, r8d; lpcchClass
0x180004a17  mov     [rsp+9A0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180004a1c  xor     edx, edx; lpClass
0x180004a1e  lea     rax, [rbp+8A0h+cbMaxValueNameLen]
0x180004a22  mov     [rsp+9A0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180004a27  lea     rax, [rbp+8A0h+cValues]
0x180004a2b  mov     [rsp+9A0h+lpftLastWriteTime], rax; lpcValues
0x180004a30  lea     rax, [rbp+8A0h+cbMaxSubKeyLen]
0x180004a34  mov     [rsp+9A0h+lpcchClass], r14; lpcbMaxClassLen
0x180004a39  mov     [rsp+9A0h+lpClass], rax; lpcbMaxSubKeyLen
0x180004a3e  lea     rax, [rbp+8A0h+cSubKeys]
0x180004a42  mov     [rsp+9A0h+lpReserved], rax; lpcSubKeys
0x180004a47  call    cs:__imp_RegQueryInfoKeyA
0x180004a4d  mov     ebx, eax
0x180004a4f  test    eax, eax
0x180004a51  jnz     loc_180004DE0
0x180004a57  mov     eax, [rsp+9A0h+cbMaxValueLen]
0x180004a5b  lea     edx, [rsi+7]; dwFlags
0x180004a5e  mov     rcx, cs:hHeap; hHeap
0x180004a65  add     eax, esi
0x180004a67  mov     [rsp+9A0h+cbMaxValueLen], eax
0x180004a6b  lea     r8d, [rax+1]; dwBytes
0x180004a6f  call    cs:__imp_HeapAlloc
0x180004a75  mov     rdi, rax
0x180004a78  test    rax, rax
0x180004a7b  jz      loc_180004D9C
0x180004a81  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004a86  lea     rax, [rsp+9A0h+cbMaxValueLen]
0x180004a8b  mov     [rsp+9A0h+lpClass], rax; lpcbData
0x180004a90  lea     r9, [rsp+9A0h+Type]; lpType
0x180004a95  xor     r8d, r8d; lpReserved
0x180004a98  mov     [rsp+9A0h+lpReserved], rdi; lpData
0x180004a9d  lea     rdx, ValueName; "Path"
0x180004aa4  call    cs:__imp_RegQueryValueExA
0x180004aaa  mov     ebx, eax
0x180004aac  test    eax, eax
0x180004aae  jnz     loc_180004D04
0x180004ab4  mov     eax, [rsp+9A0h+Type]
0x180004ab8  dec     eax
0x180004aba  cmp     eax, esi
0x180004abc  ja      loc_180004D92
0x180004ac2  mov     eax, [rsp+9A0h+cbMaxValueLen]
0x180004ac6  xor     r8d, r8d; nSize
0x180004ac9  xor     edx, edx; lpDst
0x180004acb  mov     rcx, rdi; lpSrc
0x180004ace  mov     [rax+rdi], r14b
0x180004ad2  call    cs:__imp_ExpandEnvironmentStringsA
0x180004ad8  test    eax, eax
0x180004ada  jz      loc_180004CFC
0x180004ae0  mov     rcx, cs:hHeap; hHeap
0x180004ae7  lea     ebx, [rax+1]
0x180004aea  mov     r8d, ebx; dwBytes
0x180004aed  lea     edx, [rsi+7]; dwFlags
0x180004af0  call    cs:__imp_HeapAlloc
0x180004af6  mov     [rsp+9A0h+lpLibFileName], rax
0x180004afb  test    rax, rax
0x180004afe  jz      loc_180004D47
0x180004b04  mov     r8d, ebx; nSize
0x180004b07  mov     rdx, rax; lpDst
0x180004b0a  mov     rcx, rdi; lpSrc
0x180004b0d  call    cs:__imp_ExpandEnvironmentStringsA
0x180004b13  test    eax, eax
0x180004b15  jz      loc_180004CFC
0x180004b1b  mov     rcx, [rsp+9A0h+lpLibFileName]; lpLibFileName
0x180004b20  xor     edx, edx; hFile
0x180004b22  mov     r8d, 1000h; dwFlags
0x180004b28  call    cs:__imp_LoadLibraryExA
0x180004b2e  mov     rsi, rax
0x180004b31  test    rax, rax
0x180004b34  jz      loc_180004CA6
0x180004b3a  lea     rdx, ProcName; "RasCpEnumProtocolIds"
0x180004b41  mov     rcx, rax; hModule
0x180004b44  call    cs:__imp_GetProcAddress
0x180004b4a  test    rax, rax
0x180004b4d  jz      loc_180004C9C
0x180004b53  mov     r14d, r15d
0x180004b56  lea     rdx, [rbp+8A0h+var_920]
0x180004b5a  shl     r14, 5
0x180004b5e  lea     rcx, [rbp+8A0h+var_900]
0x180004b62  mov     [r14+r12], rax
0x180004b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6b  mov     rbx, rax
0x180004b6e  test    eax, eax
0x180004b70  jnz     loc_180004C32
0x180004b76  mov     ecx, [rbp+8A0h+var_920]
0x180004b79  lea     rdx, aRascpgetinfo_0; "RasCpGetInfo"
0x180004b80  mov     rax, [rbp+8A0h+var_908]
0x180004b84  add     [rax], ecx
0x180004b86  mov     rcx, rsi; hModule
0x180004b89  call    cs:__imp_GetProcAddress
0x180004b8f  test    rax, rax
0x180004b92  jz      loc_180004C2A
0x180004b98  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004b9d  mov     [r14+r12+8], rax
0x180004ba2  call    cs:__imp_RegCloseKey
0x180004ba8  mov     rax, [rsp+9A0h+lpLibFileName]
0x180004bad  mov     r8, rdi; lpMem
0x180004bb0  mov     [r14+r12+10h], rax
0x180004bb5  xor     edx, edx; dwFlags
0x180004bb7  mov     [r14+r12+18h], rsi
0x180004bbc  mov     rcx, cs:hHeap; hHeap
0x180004bc3  mov     [rsp+9A0h+phkResult], 0
0x180004bcc  call    cs:__imp_HeapFree
0x180004bd2  mov     esi, [rbp+8A0h+var_90C]
0x180004bd5  inc     r15d
0x180004bd8  xor     r14d, r14d
0x180004bdb  jmp     loc_18000497C
0x180004be0  cmp     cs:dword_18004CA20, r14d
0x180004be7  jbe     short loc_180004C11
0x180004be9  mov     rcx, cs:hLogHandle; hLogHandle
0x180004bf0  xor     r9d, r9d; dwSubStringCount
0x180004bf3  mov     dword ptr [rsp+9A0h+lpcchClass], r14d; dwErrorIndex
0x180004bf8  mov     r8d, 4E23h; dwMessageId
0x180004bfe  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004c02  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004c07  lea     edx, [r9+1]; dwEventType
0x180004c0b  call    cs:__imp_RouterLogEventStringA
0x180004c11  cmp     cs:byte_18004CF33, r14b
0x180004c18  jge     loc_180004E50
0x180004c1e  lea     rdx, aCannotEnumerat; "Cannot enumerate Registry key values %d"
0x180004c25  jmp     loc_180004E1F
0x180004c2a  call    cs:__imp_GetLastError
0x180004c30  mov     ebx, eax
0x180004c32  xor     r14d, r14d
0x180004c35  cmp     cs:dword_18004CA20, r14d
0x180004c3c  jbe     short loc_180004C6D
0x180004c3e  mov     ecx, 1
0x180004c43  lea     rax, [rsp+9A0h+lpLibFileName]
0x180004c48  mov     dword ptr [rsp+9A0h+lpcchClass], ecx; dwErrorIndex
0x180004c4c  mov     r9d, ecx; dwSubStringCount
0x180004c4f  mov     edx, ecx; dwEventType
0x180004c51  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004c55  mov     rcx, cs:hLogHandle; hLogHandle
0x180004c5c  mov     r8d, 4E67h; dwMessageId
0x180004c62  mov     [rsp+9A0h+lpReserved], rax; plpszSubStringArray
0x180004c67  call    cs:__imp_RouterLogEventStringA
0x180004c6d  cmp     cs:byte_18004CF33, r14b
0x180004c74  jge     loc_180004E50
0x180004c7a  lea     rdx, aThePointToPoin; "The Point to Point Protocol module %hs "...
0x180004c81  mov     r8, [rsp+9A0h+lpLibFileName]
0x180004c86  lea     rcx, [rbp+8A0h+var_840]
0x180004c8a  mov     r9d, ebx
0x180004c8d  mov     word ptr [rbp+8A0h+var_840], r14w
0x180004c92  call    FormatRRASErrorString
0x180004c97  jmp     loc_180004E30
0x180004c9c  call    cs:__imp_GetLastError
0x180004ca2  mov     ebx, eax
0x180004ca4  jmp     short loc_180004C35
0x180004ca6  call    cs:__imp_GetLastError
0x180004cac  cmp     cs:dword_18004CA20, r14d
0x180004cb3  mov     ebx, eax
0x180004cb5  jbe     short loc_180004CE6
0x180004cb7  mov     ecx, 1
0x180004cbc  mov     r8d, 4E66h; dwMessageId
0x180004cc2  mov     dword ptr [rsp+9A0h+lpcchClass], ecx; dwErrorIndex
0x180004cc6  mov     r9d, ecx; dwSubStringCount
0x180004cc9  mov     dword ptr [rsp+9A0h+lpClass], eax; dwErrorCode
0x180004ccd  mov     edx, ecx; dwEventType
0x180004ccf  mov     rcx, cs:hLogHandle; hLogHandle
0x180004cd6  lea     rax, [rsp+9A0h+lpLibFileName]
0x180004cdb  mov     [rsp+9A0h+lpReserved], rax; plpszSubStringArray
0x180004ce0  call    cs:__imp_RouterLogEventStringA
0x180004ce6  cmp     cs:byte_18004CF33, r14b
0x180004ced  jge     loc_180004E50
0x180004cf3  lea     rdx, aPointToPointPr; "Point to Point Protocol engine was unab"...
0x180004cfa  jmp     short loc_180004C81
0x180004cfc  call    cs:__imp_GetLastError
0x180004d02  mov     ebx, eax
0x180004d04  cmp     cs:dword_18004CA20, r14d
0x180004d0b  jbe     short loc_180004D2E
0x180004d0d  mov     rcx, cs:hLogHandle; hLogHandle
0x180004d14  xor     r9d, r9d; dwSubStringCount
0x180004d17  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004d1b  mov     r8d, 4E22h; dwMessageId
0x180004d21  mov     edx, esi; dwEventType
0x180004d23  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004d28  call    cs:__imp_RouterLogEventA
0x180004d2e  cmp     cs:byte_18004CF33, r14b
0x180004d35  jge     loc_180004E50
0x180004d3b  lea     rdx, aCannotAccessRe; "Cannot access registry key values %d."
0x180004d42  jmp     loc_180004E1F
0x180004d47  call    cs:__imp_GetLastError
0x180004d4d  cmp     cs:dword_18004CA20, r14d
0x180004d54  mov     ebx, eax
0x180004d56  jbe     short loc_180004D79
0x180004d58  mov     rcx, cs:hLogHandle; hLogHandle
0x180004d5f  xor     r9d, r9d; dwSubStringCount
0x180004d62  mov     dword ptr [rsp+9A0h+lpClass], eax; dwErrorCode
0x180004d66  mov     r8d, 4E88h; dwMessageId
0x180004d6c  mov     edx, esi; dwEventType
0x180004d6e  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004d73  call    cs:__imp_RouterLogEventA
0x180004d79  cmp     cs:byte_18004CF33, r14b
0x180004d80  jge     loc_180004E50
0x180004d86  lea     rdx, aMemoryAllocati; "Memory allocation failure %d."
0x180004d8d  jmp     loc_180004E1F
0x180004d92  mov     ebx, 3F7h
0x180004d97  jmp     loc_180004D04
0x180004d9c  call    cs:__imp_GetLastError
0x180004da2  cmp     cs:dword_18004CA20, r14d
0x180004da9  mov     ebx, eax
0x180004dab  jbe     short loc_180004DCE
0x180004dad  mov     rcx, cs:hLogHandle; hLogHandle
0x180004db4  xor     r9d, r9d; dwSubStringCount
0x180004db7  mov     dword ptr [rsp+9A0h+lpClass], eax; dwErrorCode
0x180004dbb  mov     r8d, 4E88h; dwMessageId
0x180004dc1  mov     edx, esi; dwEventType
0x180004dc3  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004dc8  call    cs:__imp_RouterLogEventA
0x180004dce  cmp     cs:byte_18004CF33, r14b
0x180004dd5  jge     short loc_180004E50
0x180004dd7  lea     rdx, aMemoryAllocati_1; "Memory allocation failure %d"
0x180004dde  jmp     short loc_180004E1F
0x180004de0  cmp     cs:dword_18004CA20, r14d
0x180004de7  jbe     short loc_180004E0F
0x180004de9  mov     rcx, cs:hLogHandle; hLogHandle
0x180004df0  xor     r9d, r9d; dwSubStringCount
0x180004df3  mov     dword ptr [rsp+9A0h+lpcchClass], r14d; dwErrorIndex
0x180004df8  mov     r8d, 4E65h; dwMessageId
0x180004dfe  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004e02  mov     edx, esi; dwEventType
0x180004e04  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004e09  call    cs:__imp_RouterLogEventStringA
0x180004e0f  cmp     cs:byte_18004CF33, r14b
0x180004e16  jge     short loc_180004E50
0x180004e18  lea     rdx, aCannotOpenOrOb; "Cannot open or obtain information about"...
  ... truncated ...
```
