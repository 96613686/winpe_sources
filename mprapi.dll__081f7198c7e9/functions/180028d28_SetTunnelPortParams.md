# SetTunnelPortParams

- ea: `0x180028d28`
- end: `0x1800291ae`
- name: `SetTunnelPortParams`
- size: `1158`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027b90`
- `0x180027c90`

## callees

- `0x180028898`
- `0x180028d28`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028ee8`
- `msvcrt!_wcsicmp` at `0x180028f22`
- `msvcrt!_wcsicmp` at `0x180028f5c`
- `msvcrt!_wcsicmp` at `0x180028f93`
- `msvcrt!_wcsicmp` at `0x180028fc4`
- `msvcrt!_wcsicmp` at `0x180028ee8`
- `msvcrt!_wcsicmp` at `0x180028f22`
- `msvcrt!_wcsicmp` at `0x180028f5c`
- `msvcrt!_wcsicmp` at `0x180028f93`
- `msvcrt!_wcsicmp` at `0x180028fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028e09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028e09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029158`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028e17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028e17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002912f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002912f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002913d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002917c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002918b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002913d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002917c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002918b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180028dd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180028dd6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028e68`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180028e68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002910d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800290d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002910d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028e91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028e91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002903b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002903b`

## string_xrefs

- `0x180028eba`: `ComponentId`

## pseudocode

```c
__int64 __fastcall SetTunnelPortParams(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // edi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rbx
  DWORD i; // r13d
  LSTATUS v10; // eax
  unsigned int Value; // eax
  wchar_t *v12; // r12
  int v13; // eax
  unsigned int v14; // ebx
  HKEY v15; // r15
  HANDLE v16; // rax
  HANDLE v17; // rax
  BYTE v19[8]; // [rsp+60h] [rbp-9h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-1h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+80h] [rbp+17h] BYREF
  WCHAR *v25; // [rsp+88h] [rbp+1Fh]
  DWORD cchName; // [rsp+D0h] [rbp+67h] BYREF
  wchar_t *String1; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  phkResult = 0;
  String1 = 0;
  cSubKeys = 0;
  cchName = 0;
  cbMaxSubKeyLen = 0;
  if ( a3 )
    *a3 = 0;
  v5 = RegOpenKeyExW(
         *(HKEY *)(a1 + 16),
         L"SYSTEM\\CurrentControlSet\\Control\\Class\\{4D36E972-E325-11CE-BFC1-08002bE10318}",
         0,
         0x20019u,
         &hKey);
  if ( !v5 )
  {
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v5 )
    {
      if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen || 2 * (unsigned __int64)(cbMaxSubKeyLen + 1) > 0xFFFFFFFF )
      {
        v5 = 534;
      }
      else
      {
        v6 = 2 * (cbMaxSubKeyLen + 1);
        ProcessHeap = GetProcessHeap();
        v25 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v6);
        v8 = v25;
        if ( !v25 )
        {
          v5 = 8;
          goto LABEL_55;
        }
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen + 1;
          v5 = RegEnumKeyExW(hKey, i, v8, &cchName, 0, 0, 0, 0);
          if ( v5 )
            continue;
          v10 = RegOpenKeyExW(hKey, v8, 0, 0x2001Fu, &phkResult);
          v5 = v10;
          if ( v10 )
          {
            if ( v10 == 5 )
              v5 = 0;
            continue;
          }
          Value = QueryValue(phkResult, L"ComponentId");
          v12 = String1;
          v5 = Value;
          if ( !Value && cchName )
          {
            if ( _wcsicmp(String1, L"ms_pptpminiport") )
            {
              if ( _wcsicmp(v12, L"ms_l2tpminiport") )
              {
                if ( _wcsicmp(v12, L"ms_sstpminiport") )
                {
                  if ( _wcsicmp(v12, L"ms_agilevpnminiport") )
                  {
                    if ( _wcsicmp(v12, L"ms_greminiport") || *(_BYTE *)a2 < 4u || (*(_BYTE *)(a2 + 4) & 0x10) == 0 )
                      goto LABEL_49;
                    if ( a3 )
                      *a3 |= 0x10u;
                    v13 = *(_DWORD *)(a2 + 224);
                    v14 = *(_DWORD *)(a2 + 228);
                  }
                  else
                  {
                    if ( (*(_BYTE *)(a2 + 4) & 8) == 0 )
                      goto LABEL_49;
                    if ( a3 )
                      *a3 |= 8u;
                    v13 = *(_DWORD *)(a2 + 8);
                    v14 = *(_DWORD *)(a2 + 12);
                  }
                }
                else
                {
                  if ( (*(_BYTE *)(a2 + 4) & 4) == 0 )
                    goto LABEL_49;
                  if ( a3 )
                    *a3 |= 4u;
                  v13 = *(_DWORD *)(a2 + 184);
                  v14 = *(_DWORD *)(a2 + 188);
                }
              }
              else
              {
                if ( (*(_BYTE *)(a2 + 4) & 2) == 0 )
                  goto LABEL_49;
                if ( a3 )
                  *a3 |= 2u;
                v13 = *(_DWORD *)(a2 + 136);
                v14 = *(_DWORD *)(a2 + 140);
              }
            }
            else
            {
              if ( (*(_BYTE *)(a2 + 4) & 1) == 0 )
                goto LABEL_49;
              if ( a3 )
                *a3 |= 1u;
              v13 = *(_DWORD *)(a2 + 128);
              v14 = *(_DWORD *)(a2 + 132);
            }
            v15 = phkResult;
            *(_DWORD *)v19 = v13;
            LODWORD(String1) = 0;
            *(_DWORD *)Data = 0;
            cbData = 4;
            v5 = RegQueryValueExW(phkResult, L"MaxWanEndpoints", 0, 0, Data, &cbData);
            if ( !v5
              && (*(_DWORD *)Data >= *(_DWORD *)v19
               || (v5 = RegSetValueExW(v15, L"MaxWanEndpoints", 0, 4u, v19, 4u)) == 0) )
            {
              v5 = RegSetValueExW(v15, L"WanEndpoints", 0, 4u, v19, 4u);
              if ( !v5 )
              {
                LODWORD(String1) = v14 & 1;
                v5 = RegSetValueExW(v15, L"EnableForRas", 0, 4u, (const BYTE *)&String1, 4u);
                if ( !v5 )
                {
                  LODWORD(String1) = (v14 >> 1) & 1;
                  v5 = RegSetValueExW(v15, L"EnableForRouting", 0, 4u, (const BYTE *)&String1, 4u);
                }
              }
            }
            v8 = v25;
          }
LABEL_49:
          if ( v12 )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v12);
          }
          String1 = 0;
          RegCloseKey(phkResult);
          phkResult = 0;
          if ( v5 )
            break;
        }
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v8);
      }
    }
  }
LABEL_55:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180028d28  mov     [rsp-8+arg_8], rbx
0x180028d2d  push    rbp
0x180028d2e  push    rsi
0x180028d2f  push    rdi
0x180028d30  push    r12
0x180028d32  push    r13
0x180028d34  push    r14
0x180028d36  push    r15
0x180028d38  lea     rbp, [rsp-27h]
0x180028d3d  sub     rsp, 90h
0x180028d44  xor     r15d, r15d
0x180028d47  mov     rsi, r8
0x180028d4a  mov     [rbp+57h+hKey], r15
0x180028d4e  mov     r14, rdx
0x180028d51  mov     [rbp+57h+var_48], r15
0x180028d55  mov     [rbp+57h+String1], r15
0x180028d59  mov     [rbp+57h+cSubKeys], r15d
0x180028d5d  mov     [rbp+57h+cchName], r15d
0x180028d61  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x180028d65  test    r8, r8
0x180028d68  jz      short loc_180028D6D
0x180028d6a  mov     [r8], r15d
0x180028d6d  mov     rcx, [rcx+10h]; hKey
0x180028d71  lea     rax, [rbp+57h+hKey]
0x180028d75  mov     r9d, 20019h; samDesired
0x180028d7b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180028d80  xor     r8d, r8d; ulOptions
0x180028d83  lea     rdx, c_szVPNPortDevices; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x180028d8a  call    cs:__imp_RegOpenKeyExW
0x180028d90  mov     edi, eax
0x180028d92  test    eax, eax
0x180028d94  jnz     loc_180029173
0x180028d9a  mov     rcx, [rbp+57h+hKey]; hKey
0x180028d9e  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180028da2  mov     [rsp+0C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180028da7  xor     r9d, r9d; lpReserved
0x180028daa  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180028daf  xor     r8d, r8d; lpcchClass
0x180028db2  mov     [rsp+0C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180028db7  xor     edx, edx; lpClass
0x180028db9  mov     [rsp+0C0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180028dbe  mov     [rsp+0C0h+lpcValues], r15; lpcValues
0x180028dc3  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180028dc8  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180028dcd  lea     rax, [rbp+57h+cSubKeys]
0x180028dd1  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x180028dd6  call    cs:__imp_RegQueryInfoKeyW
0x180028ddc  mov     edi, eax
0x180028dde  test    eax, eax
0x180028de0  jnz     loc_180029173
0x180028de6  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180028de9  lea     ecx, [rax+1]
0x180028dec  cmp     ecx, eax
0x180028dee  jb      loc_18002916E
0x180028df4  mov     eax, ecx
0x180028df6  mov     ecx, 0FFFFFFFFh
0x180028dfb  add     rax, rax
0x180028dfe  cmp     rax, rcx
0x180028e01  ja      loc_18002916E
0x180028e07  mov     ebx, eax
0x180028e09  call    cs:__imp_GetProcessHeap
0x180028e0f  mov     r8d, ebx; dwBytes
0x180028e12  xor     edx, edx; dwFlags
0x180028e14  mov     rcx, rax; hHeap
0x180028e17  call    cs:__imp_HeapAlloc
0x180028e1d  mov     [rbp+57h+var_38], rax
0x180028e21  mov     rbx, rax
0x180028e24  test    rax, rax
0x180028e27  jnz     short loc_180028E31
0x180028e29  lea     edi, [rax+8]
0x180028e2c  jmp     loc_180029173
0x180028e31  mov     r13d, r15d
0x180028e34  cmp     [rbp+57h+cSubKeys], r15d
0x180028e38  jbe     loc_180029158
0x180028e3e  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180028e41  lea     r9, [rbp+57h+cchName]; lpcchName
0x180028e45  mov     rcx, [rbp+57h+hKey]; hKey
0x180028e49  inc     eax
0x180028e4b  mov     [rsp+0C0h+lpcValues], r15; lpftLastWriteTime
0x180028e50  mov     r8, rbx; lpName
0x180028e53  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcchClass
0x180028e58  mov     edx, r13d; dwIndex
0x180028e5b  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpClass
0x180028e60  mov     [rbp+57h+cchName], eax
0x180028e63  mov     [rsp+0C0h+phkResult], r15; lpReserved
0x180028e68  call    cs:__imp_RegEnumKeyExW
0x180028e6e  mov     edi, eax
0x180028e70  test    eax, eax
0x180028e72  jnz     loc_18002914B
0x180028e78  mov     rcx, [rbp+57h+hKey]; hKey
0x180028e7c  lea     rax, [rbp+57h+var_48]
0x180028e80  mov     r9d, 2001Fh; samDesired
0x180028e86  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180028e8b  xor     r8d, r8d; ulOptions
0x180028e8e  mov     rdx, rbx; lpSubKey
0x180028e91  call    cs:__imp_RegOpenKeyExW
0x180028e97  mov     edi, eax
0x180028e99  test    eax, eax
0x180028e9b  jz      short loc_180028EAE
0x180028e9d  cmp     eax, 5
0x180028ea0  jnz     loc_18002914B
0x180028ea6  mov     edi, r15d
0x180028ea9  jmp     loc_18002914B
0x180028eae  mov     rcx, [rbp+57h+var_48]; hKey
0x180028eb2  lea     r9, [rbp+57h+cchName]
0x180028eb6  lea     r8, [rbp+57h+String1]
0x180028eba  lea     rdx, c_szComponentId; "ComponentId"
0x180028ec1  call    QueryValue
0x180028ec6  mov     r12, [rbp+57h+String1]
0x180028eca  mov     edi, eax
0x180028ecc  test    eax, eax
0x180028ece  jnz     loc_18002911C
0x180028ed4  cmp     [rbp+57h+cchName], r15d
0x180028ed8  jz      loc_18002911C
0x180028ede  lea     rdx, c_szPptp; "ms_pptpminiport"
0x180028ee5  mov     rcx, r12; String1
0x180028ee8  call    cs:__imp__wcsicmp
0x180028eee  test    eax, eax
0x180028ef0  jnz     short loc_180028F18
0x180028ef2  test    byte ptr [r14+4], 1
0x180028ef7  jz      loc_18002911C
0x180028efd  test    rsi, rsi
0x180028f00  jz      short loc_180028F05
0x180028f02  or      dword ptr [rsi], 1
0x180028f05  mov     eax, [r14+80h]
0x180028f0c  mov     ebx, [r14+84h]
0x180028f13  jmp     loc_180028FFD
0x180028f18  lea     rdx, c_szL2tp; "ms_l2tpminiport"
0x180028f1f  mov     rcx, r12; String1
0x180028f22  call    cs:__imp__wcsicmp
0x180028f28  test    eax, eax
0x180028f2a  jnz     short loc_180028F52
0x180028f2c  test    byte ptr [r14+4], 2
0x180028f31  jz      loc_18002911C
0x180028f37  test    rsi, rsi
0x180028f3a  jz      short loc_180028F3F
0x180028f3c  or      dword ptr [rsi], 2
0x180028f3f  mov     eax, [r14+88h]
0x180028f46  mov     ebx, [r14+8Ch]
0x180028f4d  jmp     loc_180028FFD
0x180028f52  lea     rdx, c_szSstp; "ms_sstpminiport"
0x180028f59  mov     rcx, r12; String1
0x180028f5c  call    cs:__imp__wcsicmp
0x180028f62  test    eax, eax
0x180028f64  jnz     short loc_180028F89
0x180028f66  test    byte ptr [r14+4], 4
0x180028f6b  jz      loc_18002911C
0x180028f71  test    rsi, rsi
0x180028f74  jz      short loc_180028F79
0x180028f76  or      dword ptr [rsi], 4
0x180028f79  mov     eax, [r14+0B8h]
0x180028f80  mov     ebx, [r14+0BCh]
0x180028f87  jmp     short loc_180028FFD
0x180028f89  lea     rdx, c_szIkev2; "ms_agilevpnminiport"
0x180028f90  mov     rcx, r12; String1
0x180028f93  call    cs:__imp__wcsicmp
0x180028f99  test    eax, eax
0x180028f9b  jnz     short loc_180028FBA
0x180028f9d  test    byte ptr [r14+4], 8
0x180028fa2  jz      loc_18002911C
0x180028fa8  test    rsi, rsi
0x180028fab  jz      short loc_180028FB0
0x180028fad  or      dword ptr [rsi], 8
0x180028fb0  mov     eax, [r14+8]
0x180028fb4  mov     ebx, [r14+0Ch]
0x180028fb8  jmp     short loc_180028FFD
0x180028fba  lea     rdx, c_szGRE; "ms_greminiport"
0x180028fc1  mov     rcx, r12; String1
0x180028fc4  call    cs:__imp__wcsicmp
0x180028fca  test    eax, eax
0x180028fcc  jnz     loc_18002911C
0x180028fd2  cmp     byte ptr [r14], 4
0x180028fd6  jb      loc_18002911C
0x180028fdc  test    byte ptr [r14+4], 10h
0x180028fe1  jz      loc_18002911C
0x180028fe7  test    rsi, rsi
0x180028fea  jz      short loc_180028FEF
0x180028fec  or      dword ptr [rsi], 10h
0x180028fef  mov     eax, [r14+0E0h]
0x180028ff6  mov     ebx, [r14+0E4h]
0x180028ffd  mov     r15, [rbp+57h+var_48]
0x180029001  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180029008  mov     dword ptr [rbp+57h+var_60], eax
0x18002900b  xor     r9d, r9d; lpType
0x18002900e  lea     rax, [rbp+57h+cbData]
0x180029012  mov     dword ptr [rbp+57h+String1], 0
0x180029019  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18002901e  xor     r8d, r8d; lpReserved
0x180029021  lea     rax, [rbp+57h+Data]
0x180029025  mov     dword ptr [rbp+57h+Data], 0
0x18002902c  mov     rcx, r15; hKey
0x18002902f  mov     [rsp+0C0h+phkResult], rax; lpData
0x180029034  mov     [rbp+57h+cbData], 4
0x18002903b  call    cs:__imp_RegQueryValueExW
0x180029041  mov     edi, eax
0x180029043  test    eax, eax
0x180029045  jnz     loc_180029115
0x18002904b  mov     eax, dword ptr [rbp+57h+var_60]
0x18002904e  cmp     dword ptr [rbp+57h+Data], eax
0x180029051  jnb     short loc_180029083
0x180029053  lea     ecx, [rdi+4]
0x180029056  xor     r8d, r8d; Reserved
0x180029059  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ecx; cbData
0x18002905d  lea     rax, [rbp+57h+var_60]
0x180029061  mov     r9d, ecx; dwType
0x180029064  mov     [rsp+0C0h+phkResult], rax; lpData
0x180029069  mov     rcx, r15; hKey
0x18002906c  lea     rdx, c_szMaxWanEndPoints; "MaxWanEndpoints"
0x180029073  call    cs:__imp_RegSetValueExW
0x180029079  mov     edi, eax
0x18002907b  test    eax, eax
0x18002907d  jnz     loc_180029115
0x180029083  mov     ecx, 4
0x180029088  lea     rax, [rbp+57h+var_60]
0x18002908c  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ecx; cbData
0x180029090  lea     rdx, c_szWanEndPoints; "WanEndpoints"
0x180029097  mov     r9d, ecx; dwType
0x18002909a  mov     [rsp+0C0h+phkResult], rax; lpData
0x18002909f  mov     rcx, r15; hKey
0x1800290a2  xor     r8d, r8d; Reserved
0x1800290a5  call    cs:__imp_RegSetValueExW
0x1800290ab  mov     edi, eax
0x1800290ad  test    eax, eax
0x1800290af  jnz     short loc_180029115
0x1800290b1  lea     ecx, [rdi+4]
0x1800290b4  mov     eax, ebx
0x1800290b6  and     eax, 1
0x1800290b9  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ecx; cbData
0x1800290bd  mov     dword ptr [rbp+57h+String1], eax
0x1800290c0  lea     rdx, c_szEnableForRas; "EnableForRas"
0x1800290c7  lea     rax, [rbp+57h+String1]
0x1800290cb  mov     r9d, ecx; dwType
0x1800290ce  xor     r8d, r8d; Reserved
0x1800290d1  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800290d6  mov     rcx, r15; hKey
0x1800290d9  call    cs:__imp_RegSetValueExW
0x1800290df  mov     edi, eax
0x1800290e1  test    eax, eax
0x1800290e3  jnz     short loc_180029115
0x1800290e5  lea     ecx, [rax+4]
0x1800290e8  shr     ebx, 1
0x1800290ea  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], ecx; cbData
0x1800290ee  lea     rax, [rbp+57h+String1]
0x1800290f2  and     ebx, 1
0x1800290f5  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800290fa  mov     r9d, ecx; dwType
0x1800290fd  mov     dword ptr [rbp+57h+String1], ebx
0x180029100  mov     rcx, r15; hKey
0x180029103  lea     rdx, c_szEnableForRouting; "EnableForRouting"
0x18002910a  xor     r8d, r8d; Reserved
0x18002910d  call    cs:__imp_RegSetValueExW
0x180029113  mov     edi, eax
0x180029115  mov     rbx, [rbp+57h+var_38]
0x180029119  xor     r15d, r15d
0x18002911c  test    r12, r12
0x18002911f  jz      short loc_180029135
0x180029121  call    cs:__imp_GetProcessHeap
0x180029127  mov     r8, r12; lpMem
0x18002912a  xor     edx, edx; dwFlags
0x18002912c  mov     rcx, rax; hHeap
0x18002912f  call    cs:__imp_HeapFree
0x180029135  mov     rcx, [rbp+57h+var_48]; hKey
0x180029139  mov     [rbp+57h+String1], r15
0x18002913d  call    cs:__imp_RegCloseKey
0x180029143  mov     [rbp+57h+var_48], r15
0x180029147  test    edi, edi
0x180029149  jnz     short loc_180029158
0x18002914b  inc     r13d
0x18002914e  cmp     r13d, [rbp+57h+cSubKeys]
0x180029152  jb      loc_180028E3E
0x180029158  call    cs:__imp_GetProcessHeap
0x18002915e  mov     r8, rbx; lpMem
0x180029161  xor     edx, edx; dwFlags
0x180029163  mov     rcx, rax; hHeap
0x180029166  call    cs:__imp_HeapFree
0x18002916c  jmp     short loc_180029173
0x18002916e  mov     edi, 216h
0x180029173  mov     rcx, [rbp+57h+var_48]; hKey
0x180029177  test    rcx, rcx
0x18002917a  jz      short loc_180029182
0x18002917c  call    cs:__imp_RegCloseKey
0x180029182  mov     rcx, [rbp+57h+hKey]; hKey
0x180029186  test    rcx, rcx
0x180029189  jz      short loc_180029191
0x18002918b  call    cs:__imp_RegCloseKey
0x180029191  mov     rbx, [rsp+0C0h+arg_8]
0x180029199  mov     eax, edi
0x18002919b  add     rsp, 90h
0x1800291a2  pop     r15
0x1800291a4  pop     r14
0x1800291a6  pop     r13
0x1800291a8  pop     r12
0x1800291aa  pop     rdi
0x1800291ab  pop     rsi
0x1800291ac  pop     rbp
0x1800291ad  retn
```
