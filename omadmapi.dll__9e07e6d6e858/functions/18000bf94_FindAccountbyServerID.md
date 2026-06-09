# FindAccountbyServerID

- ea: `0x18000bf94`
- end: `0x18000c36e`
- name: `FindAccountbyServerID`
- size: `986`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD cbMaxSubKeyLen)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c814`

## callees

- `0x1800076ac`
- `0x180009bf4`
- `0x18000bf94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c18f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c246`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c255`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c18f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c246`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c255`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c323`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c323`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c028`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c13e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c176`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c028`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c13e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c176`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c078`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c078`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c10c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c10c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000bfe8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000bfe8`
- `DMCmnUtils!InvStrCmpW` at `0x18000c1fb`
- `DMCmnUtils!InvStrCmpW` at `0x18000c1fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FindAccountbyServerID(
        const unsigned __int16 *a1,
        REGSAM a2,
        HKEY *a3,
        _QWORD *a4,
        DWORD cbMaxSubKeyLen)
{
  DWORD v7; // esi
  unsigned __int8 *v8; // rdi
  WCHAR *v9; // r15
  int v10; // r14d
  HKEY *phkResult; // rbx
  char IsStateSeparationEnabled; // al
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  signed int v15; // ebx
  int v16; // ecx
  LSTATUS v17; // eax
  bool v18; // cc
  HKEY *v19; // rax
  HKEY *v20; // rax
  HKEY v22; // rax
  HKEY v23; // [rsp+68h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-15h] BYREF
  int v26; // [rsp+78h] [rbp-11h] BYREF
  HKEY v27; // [rsp+80h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int8 *v29; // [rsp+90h] [rbp+7h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+A0h] [rbp+17h]

  v7 = 0;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  cchName = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  v27 = 0;
  v10 = 0;
  while ( 1 )
  {
    phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v13 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    if ( !IsStateSeparationEnabled )
      v13 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    v31 = v10;
    if ( RegOpenKeyExW((HKEY)qword_18002A528[v10], v13, 0, 0x20119u, phkResult) )
      goto LABEL_20;
    v14 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      goto LABEL_22;
    }
    v16 = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
      v15 = -2147024362;
      goto LABEL_22;
    }
    ++cbMaxSubKeyLen;
    if ( v16 < 0 )
    {
      v15 = -2102788093;
      goto LABEL_22;
    }
    v9 = (WCHAR *)LocalAlloc(0, (unsigned int)(2 * v16));
    if ( !v9 )
    {
      v15 = -2147024882;
      goto LABEL_22;
    }
    if ( cSubKeys )
      break;
LABEL_19:
    v7 = 0;
LABEL_20:
    if ( (unsigned int)++v10 >= 2 )
    {
      v15 = -2147024894;
      goto LABEL_22;
    }
  }
  while ( 1 )
  {
    v23 = 0;
    cchName = cbMaxSubKeyLen;
    v17 = RegEnumKeyExW(hKey, v7, v9, &cchName, 0, 0, 0, 0);
    v15 = v17;
    v18 = v17 <= 0;
    if ( v17 )
      break;
    v19 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v27);
    v17 = RegOpenKeyExW(hKey, v9, 0, a2, v19);
    v15 = v17;
    v18 = v17 <= 0;
    if ( v17 )
      break;
    v20 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v23);
    v17 = RegOpenKeyExW(v27, L"Protected", 0, 0x20119u, v20);
    v15 = v17;
    v18 = v17 <= 0;
    if ( v17 )
      break;
    LocalFree(v8);
    v29 = 0;
    v15 = QueryRegValue(v23, L"ServerID", 0, 0, 0, 1u, &v29, &v30, &v26);
    if ( v15 < 0 )
    {
      if ( v23 )
        RegCloseKey(v23);
      v8 = v29;
      goto LABEL_22;
    }
    v8 = v29;
    if ( v26 && !InvStrCmpW(a1, (const unsigned __int16 *)v29) )
    {
      if ( a4 )
        *a4 = qword_18002A528[v31];
      if ( v23 )
        RegCloseKey(v23);
      v22 = v27;
      v27 = 0;
      *a3 = v22;
      goto LABEL_22;
    }
    if ( v23 )
      RegCloseKey(v23);
    if ( ++v7 >= cSubKeys )
      goto LABEL_19;
  }
  if ( !v18 )
    v15 = (unsigned __int16)v17 | 0x80070000;
  if ( v23 )
    RegCloseKey(v23);
LABEL_22:
  LocalFree(v8);
  LocalFree(v9);
  if ( v27 )
    RegCloseKey(v27);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000bf94  mov     rax, rsp
0x18000bf97  mov     [rax+18h], rbx
0x18000bf9b  mov     [rax+10h], edx
0x18000bf9e  mov     [rax+8], rcx
0x18000bfa2  push    rbp
0x18000bfa3  push    rsi
0x18000bfa4  push    rdi
0x18000bfa5  push    r12
0x18000bfa7  push    r13
0x18000bfa9  push    r14
0x18000bfab  push    r15
0x18000bfad  lea     rbp, [rax-57h]
0x18000bfb1  sub     rsp, 0A0h
0x18000bfb8  mov     r12, r9
0x18000bfbb  mov     r13, r8
0x18000bfbe  xor     esi, esi
0x18000bfc0  mov     edi, esi
0x18000bfc2  mov     [rbp+4Fh+var_60], esi
0x18000bfc5  mov     r15d, esi
0x18000bfc8  mov     [rbp+4Fh+cchName], esi
0x18000bfcb  mov     [rbp+4Fh+cSubKeys], esi
0x18000bfce  mov     [rbp+4Fh+cbMaxSubKeyLen], esi
0x18000bfd1  mov     [rbp+4Fh+hKey], rsi
0x18000bfd5  mov     [rbp+4Fh+var_58], rsi
0x18000bfd9  mov     r14d, esi
0x18000bfdc  lea     rcx, [rbp+4Fh+hKey]
0x18000bfe0  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000bfe5  mov     rbx, rax
0x18000bfe8  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000bfef  nop     dword ptr [rax+rax+00h]
0x18000bff4  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18000bffb  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x18000c002  test    al, al
0x18000c004  cmovz   rdx, rcx; lpSubKey
0x18000c008  movsxd  rax, r14d
0x18000c00b  mov     [rbp+4Fh+var_38], rax
0x18000c00f  lea     rcx, qword_18002A528
0x18000c016  mov     [rsp+0D0h+phkResult], rbx; phkResult
0x18000c01b  mov     r9d, 20119h; samDesired
0x18000c021  xor     r8d, r8d; ulOptions
0x18000c024  mov     rcx, [rcx+rax*8]; hKey
0x18000c028  call    cs:__imp_RegOpenKeyExW
0x18000c02f  nop     dword ptr [rax+rax+00h]
0x18000c034  test    eax, eax
0x18000c036  jnz     loc_18000C231
0x18000c03c  mov     [rsp+58h], rsi; lpftLastWriteTime
0x18000c041  mov     [rsp+0D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000c046  mov     [rsp+0D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000c04b  mov     [rsp+0D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18000c050  mov     [rsp+0D0h+lpcValues], rsi; lpcValues
0x18000c055  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000c05a  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x18000c05e  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000c063  lea     rax, [rbp+4Fh+cSubKeys]
0x18000c067  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x18000c06c  xor     r9d, r9d; lpReserved
0x18000c06f  xor     r8d, r8d; lpcchClass
0x18000c072  xor     edx, edx; lpClass
0x18000c074  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000c078  call    cs:__imp_RegQueryInfoKeyW
0x18000c07f  nop     dword ptr [rax+rax+00h]
0x18000c084  mov     ebx, eax
0x18000c086  test    eax, eax
0x18000c088  jnz     loc_18000C359
0x18000c08e  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x18000c091  lea     ecx, [rax+1]
0x18000c094  cmp     ecx, eax
0x18000c096  jb      loc_18000C348
0x18000c09c  mov     [rbp+4Fh+cbMaxSubKeyLen], ecx
0x18000c09f  test    ecx, ecx
0x18000c0a1  js      loc_18000C33E
0x18000c0a7  lea     edx, [rcx+rcx]; uBytes
0x18000c0aa  xor     ecx, ecx; uFlags
0x18000c0ac  call    cs:__imp_LocalAlloc
0x18000c0b3  nop     dword ptr [rax+rax+00h]
0x18000c0b8  mov     r15, rax
0x18000c0bb  test    rax, rax
0x18000c0be  jz      loc_18000C334
0x18000c0c4  cmp     [rbp+4Fh+cSubKeys], ebx
0x18000c0c7  jbe     loc_18000C22F
0x18000c0cd  mov     [rbp+4Fh+var_70], 0
0x18000c0d5  mov     ecx, [rbp+4Fh+cbMaxSubKeyLen]
0x18000c0d8  mov     [rbp+4Fh+cchName], ecx
0x18000c0db  mov     [rsp+0D0h+lpcValues], 0; lpftLastWriteTime
0x18000c0e4  mov     [rsp+0D0h+lpcbMaxClassLen], 0; lpcchClass
0x18000c0ed  mov     [rsp+0D0h+lpcbMaxSubKeyLen], 0; lpClass
0x18000c0f6  mov     [rsp+0D0h+phkResult], 0; lpReserved
0x18000c0ff  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x18000c103  mov     r8, r15; lpName
0x18000c106  mov     edx, esi; dwIndex
0x18000c108  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000c10c  call    cs:__imp_RegEnumKeyExW
0x18000c113  nop     dword ptr [rax+rax+00h]
0x18000c118  mov     ebx, eax
0x18000c11a  test    eax, eax
0x18000c11c  jnz     loc_18000C30B
0x18000c122  lea     rcx, [rbp+4Fh+var_58]
0x18000c126  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000c12b  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000c130  mov     r9d, [rbp+4Fh+samDesired]; samDesired
0x18000c134  xor     r8d, r8d; ulOptions
0x18000c137  mov     rdx, r15; lpSubKey
0x18000c13a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000c13e  call    cs:__imp_RegOpenKeyExW
0x18000c145  nop     dword ptr [rax+rax+00h]
0x18000c14a  mov     ebx, eax
0x18000c14c  test    eax, eax
0x18000c14e  jnz     loc_18000C30B
0x18000c154  lea     rcx, [rbp+4Fh+var_70]
0x18000c158  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000c15d  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000c162  mov     r9d, 20119h; samDesired
0x18000c168  xor     r8d, r8d; ulOptions
0x18000c16b  lea     rdx, aProtected; "Protected"
0x18000c172  mov     rcx, [rbp+4Fh+var_58]; hKey
0x18000c176  call    cs:__imp_RegOpenKeyExW
0x18000c17d  nop     dword ptr [rax+rax+00h]
0x18000c182  mov     ebx, eax
0x18000c184  test    eax, eax
0x18000c186  jnz     loc_18000C30B
0x18000c18c  mov     rcx, rdi; hMem
0x18000c18f  call    cs:__imp_LocalFree
0x18000c196  nop     dword ptr [rax+rax+00h]
0x18000c19b  mov     [rbp+4Fh+var_48], 0
0x18000c1a3  lea     rax, [rbp+4Fh+var_60]
0x18000c1a7  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; int *
0x18000c1ac  lea     rax, [rbp+4Fh+var_40]
0x18000c1b0  mov     [rsp+0D0h+lpcValues], rax; unsigned int *
0x18000c1b5  lea     rax, [rbp+4Fh+var_48]
0x18000c1b9  mov     [rsp+0D0h+lpcbMaxClassLen], rax; unsigned __int8 **
0x18000c1be  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 1; unsigned int
0x18000c1c6  mov     dword ptr [rsp+0D0h+phkResult], ebx; unsigned int
0x18000c1ca  xor     r9d, r9d; unsigned __int8 *
0x18000c1cd  xor     r8d, r8d; int
0x18000c1d0  lea     rdx, aServerid; "ServerID"
0x18000c1d7  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18000c1db  call    ?QueryRegValue@@YAJPEAUHKEY__@@PEBGHPEAEKKPEAPEAEPEAKPEAH@Z; QueryRegValue(HKEY__ *,ushort const *,int,uchar *,ulong,ulong,uchar * *,ulong *,int *)
0x18000c1e0  mov     ebx, eax
0x18000c1e2  test    eax, eax
0x18000c1e4  js      loc_18000C2ED
0x18000c1ea  mov     rdi, [rbp+4Fh+var_48]
0x18000c1ee  cmp     [rbp+4Fh+var_60], 0
0x18000c1f2  jz      short loc_18000C20F
0x18000c1f4  mov     rdx, rdi
0x18000c1f7  mov     rcx, [rbp+4Fh+arg_0]
0x18000c1fb  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x18000c202  nop     dword ptr [rax+rax+00h]
0x18000c207  test    eax, eax
0x18000c209  jz      loc_18000C2AB
0x18000c20f  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18000c213  test    rcx, rcx
0x18000c216  jz      short loc_18000C224
0x18000c218  call    cs:__imp_RegCloseKey
0x18000c21f  nop     dword ptr [rax+rax+00h]
0x18000c224  inc     esi
0x18000c226  cmp     esi, [rbp+4Fh+cSubKeys]
0x18000c229  jb      loc_18000C0CD
0x18000c22f  xor     esi, esi
0x18000c231  inc     r14d
0x18000c234  cmp     r14d, 2
0x18000c238  jb      loc_18000BFDC
0x18000c23e  mov     ebx, 80070002h
0x18000c243  mov     rcx, rdi; hMem
0x18000c246  call    cs:__imp_LocalFree
0x18000c24d  nop     dword ptr [rax+rax+00h]
0x18000c252  mov     rcx, r15; hMem
0x18000c255  call    cs:__imp_LocalFree
0x18000c25c  nop     dword ptr [rax+rax+00h]
0x18000c261  nop
0x18000c262  mov     rcx, [rbp+4Fh+var_58]; hKey
0x18000c266  test    rcx, rcx
0x18000c269  jz      short loc_18000C278
0x18000c26b  call    cs:__imp_RegCloseKey
0x18000c272  nop     dword ptr [rax+rax+00h]
0x18000c277  nop
0x18000c278  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18000c27c  test    rcx, rcx
0x18000c27f  jz      short loc_18000C28D
0x18000c281  call    cs:__imp_RegCloseKey
0x18000c288  nop     dword ptr [rax+rax+00h]
0x18000c28d  mov     eax, ebx
0x18000c28f  mov     rbx, [rsp+0D0h+arg_10]
0x18000c297  add     rsp, 0A0h
0x18000c29e  pop     r15
0x18000c2a0  pop     r14
0x18000c2a2  pop     r13
0x18000c2a4  pop     r12
0x18000c2a6  pop     rdi
0x18000c2a7  pop     rsi
0x18000c2a8  pop     rbp
0x18000c2a9  retn
0x18000c2ab  test    r12, r12
0x18000c2ae  jz      short loc_18000C2C3
0x18000c2b0  mov     rax, [rbp+4Fh+var_38]
0x18000c2b4  lea     rcx, qword_18002A528
0x18000c2bb  mov     rax, [rcx+rax*8]
0x18000c2bf  mov     [r12], rax
0x18000c2c3  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18000c2c7  test    rcx, rcx
0x18000c2ca  jz      short loc_18000C2D8
0x18000c2cc  call    cs:__imp_RegCloseKey
0x18000c2d3  nop     dword ptr [rax+rax+00h]
0x18000c2d8  mov     rax, [rbp+4Fh+var_58]
0x18000c2dc  mov     [rbp+4Fh+var_58], 0
0x18000c2e4  mov     [r13+0], rax
0x18000c2e8  jmp     loc_18000C243
0x18000c2ed  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18000c2f1  test    rcx, rcx
0x18000c2f4  jz      short loc_18000C302
0x18000c2f6  call    cs:__imp_RegCloseKey
0x18000c2fd  nop     dword ptr [rax+rax+00h]
0x18000c302  mov     rdi, [rbp+4Fh+var_48]
0x18000c306  jmp     loc_18000C243
0x18000c30b  jle     short loc_18000C316
0x18000c30d  movzx   ebx, ax
0x18000c310  or      ebx, 80070000h
0x18000c316  mov     rcx, [rbp+4Fh+var_70]; hKey
0x18000c31a  test    rcx, rcx
0x18000c31d  jz      loc_18000C243
0x18000c323  call    cs:__imp_RegCloseKey
0x18000c32a  nop     dword ptr [rax+rax+00h]
0x18000c32f  jmp     loc_18000C243
0x18000c334  mov     ebx, 8007000Eh
0x18000c339  jmp     loc_18000C243
0x18000c33e  mov     ebx, 82AA0003h
0x18000c343  jmp     loc_18000C243
0x18000c348  mov     [rbp+4Fh+cbMaxSubKeyLen], 0FFFFFFFFh
0x18000c34f  mov     ebx, 80070216h
0x18000c354  jmp     loc_18000C243
0x18000c359  jle     loc_18000C243
0x18000c35f  movzx   ebx, ax
0x18000c362  or      ebx, 80070000h
0x18000c368  jmp     loc_18000C243
```
