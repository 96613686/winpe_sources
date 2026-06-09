# LoadProtocolDlls

- ea: `0x1800049e4`
- end: `0x18000504b`
- name: `LoadProtocolDlls`
- size: `1639`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005908`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800049e4`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005012`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180004bb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180004bb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180004aaf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180004aaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180004b4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180004b4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180004aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180004aef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ff5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004c54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180004c54`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004bec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004c33`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004bec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180004c33`
- `rtutils!RouterLogEventA` at `0x180004e9f`
- `rtutils!RouterLogEventA` at `0x180004ef6`
- `rtutils!RouterLogEventA` at `0x180004f57`
- `rtutils!RouterLogEventA` at `0x180004e9f`
- `rtutils!RouterLogEventA` at `0x180004ef6`
- `rtutils!RouterLogEventA` at `0x180004f57`
- `rtutils!RouterLogEventStringA` at `0x180004d55`
- `rtutils!RouterLogEventStringA` at `0x180004dbd`
- `rtutils!RouterLogEventStringA` at `0x180004e48`
- `rtutils!RouterLogEventStringA` at `0x180004f9e`
- `rtutils!RouterLogEventStringA` at `0x180004d55`
- `rtutils!RouterLogEventStringA` at `0x180004dbd`
- `rtutils!RouterLogEventStringA` at `0x180004e48`
- `rtutils!RouterLogEventStringA` at `0x180004f9e`

## string_xrefs

- `0x180004d6e`: `Cannot enumerate Registry key values %d`
- `0x180004fb3`: `Cannot open or obtain information about the PPP key or one of its subkeys. %d`
- `0x180004eb8`: `Cannot access registry key values %d.`
- `0x180004e61`: `Point to Point Protocol engine was unable to load the %hs module. %d`
- `0x180004c6c`: `RasCpEnumProtocolIds`
- `0x180004dd6`: `The Point to Point Protocol module %hs returned an error while initializing. %d`

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
      if ( dword_18004DA20 )
        RouterLogEventStringA(hLogHandle, 1u, 0x4E23u, 0, 0, v11, 0);
      if ( byte_18004DF33 >= 0 )
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
      if ( dword_18004DA20 )
        RouterLogEventStringA(hLogHandle, 1u, 0x4E65u, 0, 0, v7, 0);
      if ( byte_18004DF33 >= 0 )
        goto LABEL_55;
      v21 = L"Cannot open or obtain information about the PPP key or one of its subkeys. %d";
      goto LABEL_52;
    }
    v10 = (BYTE *)HeapAlloc(hHeap, 8u, ++cbMaxValueLen + 1);
    if ( !v10 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( dword_18004DA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
      if ( byte_18004DF33 >= 0 )
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
      if ( dword_18004DA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E88u, 0, 0, v24);
      if ( byte_18004DF33 >= 0 )
        goto LABEL_55;
      v21 = L"Memory allocation failure %d.";
      goto LABEL_52;
    }
    if ( !ExpandEnvironmentStringsA((LPCSTR)v10, v14, v13) )
    {
LABEL_34:
      v7 = GetLastError();
LABEL_35:
      if ( dword_18004DA20 )
        RouterLogEventA(hLogHandle, 1u, 0x4E22u, 0, 0, v7);
      if ( byte_18004DF33 >= 0 )
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
      if ( dword_18004DA20 )
        RouterLogEventStringA(hLogHandle, 1u, 0x4E66u, 1u, (LPSTR *)&lpLibFileName, v23, 1u);
      if ( byte_18004DF33 >= 0 )
        goto LABEL_55;
      v22 = L"Point to Point Protocol engine was unable to load the %hs module. %d";
LABEL_28:
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, v22, lpLibFileName, v7);
LABEL_53:
      if ( byte_18004DF33 < 0 )
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
  if ( dword_18004DA20 )
    RouterLogEventStringA(hLogHandle, 1u, 0x4E67u, 1u, (LPSTR *)&lpLibFileName, v7, 1u);
  if ( byte_18004DF33 < 0 )
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
0x1800049e4  mov     [rsp-8+arg_0], rbx
0x1800049e9  push    rbp
0x1800049ea  push    rsi
0x1800049eb  push    rdi
0x1800049ec  push    r12
0x1800049ee  push    r13
0x1800049f0  push    r14
0x1800049f2  push    r15
0x1800049f4  lea     rbp, [rsp-870h]
0x1800049fc  sub     rsp, 970h
0x180004a03  mov     rax, cs:__security_cookie
0x180004a0a  xor     rax, rsp
0x180004a0d  mov     [rbp+8A0h+var_40], rax
0x180004a14  mov     r12, cs:lpMem
0x180004a1b  lea     rcx, [rbp+8A0h+var_83C]; void *
0x180004a1f  xor     r14d, r14d
0x180004a22  mov     [rbp+8A0h+var_90C], edx
0x180004a25  mov     r13, r8
0x180004a28  mov     [rsp+9A0h+phkResult], r14
0x180004a2d  mov     esi, edx
0x180004a2f  mov     [rsp+9A0h+lpLibFileName], r14
0x180004a34  xor     edx, edx; Val
0x180004a36  mov     [rsp+9A0h+cchName], r14d
0x180004a3b  mov     r8d, 7FCh; Size
0x180004a41  mov     [rbp+8A0h+cSubKeys], r14d
0x180004a45  mov     ebx, r14d
0x180004a48  mov     [rbp+8A0h+cbMaxSubKeyLen], r14d
0x180004a4c  mov     [rbp+8A0h+cValues], r14d
0x180004a50  mov     rdi, r9
0x180004a53  mov     [rbp+8A0h+cbMaxValueNameLen], r14d
0x180004a57  mov     [rsp+9A0h+cbMaxValueLen], r14d
0x180004a5c  mov     [rbp+8A0h+var_920], r14d
0x180004a60  mov     [rsp+9A0h+Type], r14d
0x180004a65  mov     [rbp+8A0h+var_840], r14d
0x180004a69  mov     [rbp+8A0h+var_908], r9
0x180004a6d  call    memset_0
0x180004a72  mov     [rdi], r14d
0x180004a75  mov     r15d, r14d
0x180004a78  mov     rdi, r14
0x180004a7b  cmp     r15d, esi
0x180004a7e  jnb     loc_180004FEB
0x180004a84  mov     [rsp+9A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180004a89  lea     r9, [rsp+9A0h+cchName]; lpcchName
0x180004a8e  mov     [rsp+9A0h+lpcchClass], r14; lpcchClass
0x180004a93  lea     r8, [rbp+8A0h+Name]; lpName
0x180004a97  mov     [rsp+9A0h+lpClass], r14; lpClass
0x180004a9c  mov     edx, r15d; dwIndex
0x180004a9f  mov     rcx, r13; hKey
0x180004aa2  mov     [rsp+9A0h+lpReserved], r14; lpReserved
0x180004aa7  mov     [rsp+9A0h+cchName], 64h ; 'd'
0x180004aaf  call    cs:__imp_RegEnumKeyExA
0x180004ab6  nop     dword ptr [rax+rax+00h]
0x180004abb  mov     ebx, eax
0x180004abd  test    eax, eax
0x180004abf  jz      short loc_180004AD3
0x180004ac1  cmp     eax, 0EAh
0x180004ac6  jz      short loc_180004AD3
0x180004ac8  cmp     eax, 103h
0x180004acd  jnz     loc_180004D2A
0x180004ad3  lea     rax, [rsp+9A0h+phkResult]
0x180004ad8  mov     esi, 1
0x180004add  mov     r9d, esi; samDesired
0x180004ae0  mov     [rsp+9A0h+lpReserved], rax; phkResult
0x180004ae5  xor     r8d, r8d; ulOptions
0x180004ae8  lea     rdx, [rbp+8A0h+Name]; lpSubKey
0x180004aec  mov     rcx, r13; hKey
0x180004aef  call    cs:__imp_RegOpenKeyExA
0x180004af6  nop     dword ptr [rax+rax+00h]
0x180004afb  mov     ebx, eax
0x180004afd  test    eax, eax
0x180004aff  jnz     loc_180004F75
0x180004b05  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004b0a  lea     rax, [rsp+9A0h+cbMaxValueLen]
0x180004b0f  mov     [rsp+9A0h+var_948], r14; lpftLastWriteTime
0x180004b14  xor     r9d, r9d; lpReserved
0x180004b17  mov     [rsp+9A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180004b1c  xor     r8d, r8d; lpcchClass
0x180004b1f  mov     [rsp+9A0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180004b24  xor     edx, edx; lpClass
0x180004b26  lea     rax, [rbp+8A0h+cbMaxValueNameLen]
0x180004b2a  mov     [rsp+9A0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180004b2f  lea     rax, [rbp+8A0h+cValues]
0x180004b33  mov     [rsp+9A0h+lpftLastWriteTime], rax; lpcValues
0x180004b38  lea     rax, [rbp+8A0h+cbMaxSubKeyLen]
0x180004b3c  mov     [rsp+9A0h+lpcchClass], r14; lpcbMaxClassLen
0x180004b41  mov     [rsp+9A0h+lpClass], rax; lpcbMaxSubKeyLen
0x180004b46  lea     rax, [rbp+8A0h+cSubKeys]
0x180004b4a  mov     [rsp+9A0h+lpReserved], rax; lpcSubKeys
0x180004b4f  call    cs:__imp_RegQueryInfoKeyA
0x180004b56  nop     dword ptr [rax+rax+00h]
0x180004b5b  mov     ebx, eax
0x180004b5d  test    eax, eax
0x180004b5f  jnz     loc_180004F75
0x180004b65  mov     eax, [rsp+9A0h+cbMaxValueLen]
0x180004b69  lea     edx, [rsi+7]; dwFlags
0x180004b6c  mov     rcx, cs:hHeap; hHeap
0x180004b73  add     eax, esi
0x180004b75  mov     [rsp+9A0h+cbMaxValueLen], eax
0x180004b79  lea     r8d, [rax+1]; dwBytes
0x180004b7d  call    cs:__imp_HeapAlloc
0x180004b84  nop     dword ptr [rax+rax+00h]
0x180004b89  mov     rdi, rax
0x180004b8c  test    rax, rax
0x180004b8f  jz      loc_180004F25
0x180004b95  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004b9a  lea     rax, [rsp+9A0h+cbMaxValueLen]
0x180004b9f  mov     [rsp+9A0h+lpClass], rax; lpcbData
0x180004ba4  lea     r9, [rsp+9A0h+Type]; lpType
0x180004ba9  xor     r8d, r8d; lpReserved
0x180004bac  mov     [rsp+9A0h+lpReserved], rdi; lpData
0x180004bb1  lea     rdx, ValueName; "Path"
0x180004bb8  call    cs:__imp_RegQueryValueExA
0x180004bbf  nop     dword ptr [rax+rax+00h]
0x180004bc4  mov     ebx, eax
0x180004bc6  test    eax, eax
0x180004bc8  jnz     loc_180004E7B
0x180004bce  mov     eax, [rsp+9A0h+Type]
0x180004bd2  dec     eax
0x180004bd4  cmp     eax, esi
0x180004bd6  ja      loc_180004F1B
0x180004bdc  mov     eax, [rsp+9A0h+cbMaxValueLen]
0x180004be0  xor     r8d, r8d; nSize
0x180004be3  xor     edx, edx; lpDst
0x180004be5  mov     rcx, rdi; lpSrc
0x180004be8  mov     [rax+rdi], r14b
0x180004bec  call    cs:__imp_ExpandEnvironmentStringsA
0x180004bf3  nop     dword ptr [rax+rax+00h]
0x180004bf8  test    eax, eax
0x180004bfa  jz      loc_180004E6D
0x180004c00  mov     rcx, cs:hHeap; hHeap
0x180004c07  lea     ebx, [rax+1]
0x180004c0a  mov     r8d, ebx; dwBytes
0x180004c0d  lea     edx, [rsi+7]; dwFlags
0x180004c10  call    cs:__imp_HeapAlloc
0x180004c17  nop     dword ptr [rax+rax+00h]
0x180004c1c  mov     [rsp+9A0h+lpLibFileName], rax
0x180004c21  test    rax, rax
0x180004c24  jz      loc_180004EC4
0x180004c2a  mov     r8d, ebx; nSize
0x180004c2d  mov     rdx, rax; lpDst
0x180004c30  mov     rcx, rdi; lpSrc
0x180004c33  call    cs:__imp_ExpandEnvironmentStringsA
0x180004c3a  nop     dword ptr [rax+rax+00h]
0x180004c3f  test    eax, eax
0x180004c41  jz      loc_180004E6D
0x180004c47  mov     rcx, [rsp+9A0h+lpLibFileName]; lpLibFileName
0x180004c4c  xor     edx, edx; hFile
0x180004c4e  mov     r8d, 1000h; dwFlags
0x180004c54  call    cs:__imp_LoadLibraryExA
0x180004c5b  nop     dword ptr [rax+rax+00h]
0x180004c60  mov     rsi, rax
0x180004c63  test    rax, rax
0x180004c66  jz      loc_180004E08
0x180004c6c  lea     rdx, ProcName; "RasCpEnumProtocolIds"
0x180004c73  mov     rcx, rax; hModule
0x180004c76  call    cs:__imp_GetProcAddress
0x180004c7d  nop     dword ptr [rax+rax+00h]
0x180004c82  test    rax, rax
0x180004c85  jz      loc_180004DF8
0x180004c8b  mov     r14d, r15d
0x180004c8e  lea     rdx, [rbp+8A0h+var_920]
0x180004c92  shl     r14, 5
0x180004c96  lea     rcx, [rbp+8A0h+var_900]
0x180004c9a  mov     [r14+r12], rax
0x180004c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca3  mov     rbx, rax
0x180004ca6  test    eax, eax
0x180004ca8  jnz     loc_180004D88
0x180004cae  mov     ecx, [rbp+8A0h+var_920]
0x180004cb1  lea     rdx, aRascpgetinfo_0; "RasCpGetInfo"
0x180004cb8  mov     rax, [rbp+8A0h+var_908]
0x180004cbc  add     [rax], ecx
0x180004cbe  mov     rcx, rsi; hModule
0x180004cc1  call    cs:__imp_GetProcAddress
0x180004cc8  nop     dword ptr [rax+rax+00h]
0x180004ccd  test    rax, rax
0x180004cd0  jz      loc_180004D7A
0x180004cd6  mov     rcx, [rsp+9A0h+phkResult]; hKey
0x180004cdb  mov     [r14+r12+8], rax
0x180004ce0  call    cs:__imp_RegCloseKey
0x180004ce7  nop     dword ptr [rax+rax+00h]
0x180004cec  mov     rax, [rsp+9A0h+lpLibFileName]
0x180004cf1  mov     r8, rdi; lpMem
0x180004cf4  mov     [r14+r12+10h], rax
0x180004cf9  xor     edx, edx; dwFlags
0x180004cfb  mov     [r14+r12+18h], rsi
0x180004d00  mov     rcx, cs:hHeap; hHeap
0x180004d07  mov     [rsp+9A0h+phkResult], 0
0x180004d10  call    cs:__imp_HeapFree
0x180004d17  nop     dword ptr [rax+rax+00h]
0x180004d1c  mov     esi, [rbp+8A0h+var_90C]
0x180004d1f  inc     r15d
0x180004d22  xor     r14d, r14d
0x180004d25  jmp     loc_180004A78
0x180004d2a  cmp     cs:dword_18004DA20, r14d
0x180004d31  jbe     short loc_180004D61
0x180004d33  mov     rcx, cs:hLogHandle; hLogHandle
0x180004d3a  xor     r9d, r9d; dwSubStringCount
0x180004d3d  mov     dword ptr [rsp+9A0h+lpcchClass], r14d; dwErrorIndex
0x180004d42  mov     r8d, 4E23h; dwMessageId
0x180004d48  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004d4c  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004d51  lea     edx, [r9+1]; dwEventType
0x180004d55  call    cs:__imp_RouterLogEventStringA
0x180004d5c  nop     dword ptr [rax+rax+00h]
0x180004d61  cmp     cs:byte_18004DF33, r14b
0x180004d68  jge     loc_180004FEB
0x180004d6e  lea     rdx, aCannotEnumerat; "Cannot enumerate Registry key values %d"
0x180004d75  jmp     loc_180004FBA
0x180004d7a  call    cs:__imp_GetLastError
0x180004d81  nop     dword ptr [rax+rax+00h]
0x180004d86  mov     ebx, eax
0x180004d88  xor     r14d, r14d
0x180004d8b  cmp     cs:dword_18004DA20, r14d
0x180004d92  jbe     short loc_180004DC9
0x180004d94  mov     ecx, 1
0x180004d99  lea     rax, [rsp+9A0h+lpLibFileName]
0x180004d9e  mov     dword ptr [rsp+9A0h+lpcchClass], ecx; dwErrorIndex
0x180004da2  mov     r9d, ecx; dwSubStringCount
0x180004da5  mov     edx, ecx; dwEventType
0x180004da7  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004dab  mov     rcx, cs:hLogHandle; hLogHandle
0x180004db2  mov     r8d, 4E67h; dwMessageId
0x180004db8  mov     [rsp+9A0h+lpReserved], rax; plpszSubStringArray
0x180004dbd  call    cs:__imp_RouterLogEventStringA
0x180004dc4  nop     dword ptr [rax+rax+00h]
0x180004dc9  cmp     cs:byte_18004DF33, r14b
0x180004dd0  jge     loc_180004FEB
0x180004dd6  lea     rdx, aThePointToPoin; "The Point to Point Protocol module %hs "...
0x180004ddd  mov     r8, [rsp+9A0h+lpLibFileName]
0x180004de2  lea     rcx, [rbp+8A0h+var_840]
0x180004de6  mov     r9d, ebx
0x180004de9  mov     word ptr [rbp+8A0h+var_840], r14w
0x180004dee  call    FormatRRASErrorString
0x180004df3  jmp     loc_180004FCB
0x180004df8  call    cs:__imp_GetLastError
0x180004dff  nop     dword ptr [rax+rax+00h]
0x180004e04  mov     ebx, eax
0x180004e06  jmp     short loc_180004D8B
0x180004e08  call    cs:__imp_GetLastError
0x180004e0f  nop     dword ptr [rax+rax+00h]
0x180004e14  cmp     cs:dword_18004DA20, r14d
0x180004e1b  mov     ebx, eax
0x180004e1d  jbe     short loc_180004E54
0x180004e1f  mov     ecx, 1
0x180004e24  mov     r8d, 4E66h; dwMessageId
0x180004e2a  mov     dword ptr [rsp+9A0h+lpcchClass], ecx; dwErrorIndex
0x180004e2e  mov     r9d, ecx; dwSubStringCount
0x180004e31  mov     dword ptr [rsp+9A0h+lpClass], eax; dwErrorCode
0x180004e35  mov     edx, ecx; dwEventType
0x180004e37  mov     rcx, cs:hLogHandle; hLogHandle
0x180004e3e  lea     rax, [rsp+9A0h+lpLibFileName]
0x180004e43  mov     [rsp+9A0h+lpReserved], rax; plpszSubStringArray
0x180004e48  call    cs:__imp_RouterLogEventStringA
0x180004e4f  nop     dword ptr [rax+rax+00h]
0x180004e54  cmp     cs:byte_18004DF33, r14b
0x180004e5b  jge     loc_180004FEB
0x180004e61  lea     rdx, aPointToPointPr; "Point to Point Protocol engine was unab"...
0x180004e68  jmp     loc_180004DDD
0x180004e6d  call    cs:__imp_GetLastError
0x180004e74  nop     dword ptr [rax+rax+00h]
0x180004e79  mov     ebx, eax
0x180004e7b  cmp     cs:dword_18004DA20, r14d
0x180004e82  jbe     short loc_180004EAB
0x180004e84  mov     rcx, cs:hLogHandle; hLogHandle
0x180004e8b  xor     r9d, r9d; dwSubStringCount
0x180004e8e  mov     dword ptr [rsp+9A0h+lpClass], ebx; dwErrorCode
0x180004e92  mov     r8d, 4E22h; dwMessageId
0x180004e98  mov     edx, esi; dwEventType
0x180004e9a  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004e9f  call    cs:__imp_RouterLogEventA
0x180004ea6  nop     dword ptr [rax+rax+00h]
0x180004eab  cmp     cs:byte_18004DF33, r14b
0x180004eb2  jge     loc_180004FEB
0x180004eb8  lea     rdx, aCannotAccessRe; "Cannot access registry key values %d."
0x180004ebf  jmp     loc_180004FBA
0x180004ec4  call    cs:__imp_GetLastError
0x180004ecb  nop     dword ptr [rax+rax+00h]
0x180004ed0  cmp     cs:dword_18004DA20, r14d
0x180004ed7  mov     ebx, eax
0x180004ed9  jbe     short loc_180004F02
0x180004edb  mov     rcx, cs:hLogHandle; hLogHandle
0x180004ee2  xor     r9d, r9d; dwSubStringCount
0x180004ee5  mov     dword ptr [rsp+9A0h+lpClass], eax; dwErrorCode
0x180004ee9  mov     r8d, 4E88h; dwMessageId
0x180004eef  mov     edx, esi; dwEventType
0x180004ef1  mov     [rsp+9A0h+lpReserved], r14; plpszSubStringArray
0x180004ef6  call    cs:__imp_RouterLogEventA
0x180004efd  nop     dword ptr [rax+rax+00h]
0x180004f02  cmp     cs:byte_18004DF33, r14b
0x180004f09  jge     loc_180004FEB
0x180004f0f  lea     rdx, aMemoryAllocati; "Memory allocation failure %d."
0x180004f16  jmp     loc_180004FBA
0x180004f1b  mov     ebx, 3F7h
0x180004f20  jmp     loc_180004E7B
0x180004f25  call    cs:__imp_GetLastError
0x180004f2c  nop     dword ptr [rax+rax+00h]
0x180004f31  cmp     cs:dword_18004DA20, r14d
0x180004f38  mov     ebx, eax
0x180004f3a  jbe     short loc_180004F63
  ... truncated ...
```
