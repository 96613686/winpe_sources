# RasEnumAutodialAddressesW

- ea: `0x18006cbf0`
- end: `0x18006d312`
- name: `RasEnumAutodialAddressesW`
- size: `1826`
- prototype: `DWORD __stdcall(LPWSTR *lppRasAutodialAddresses, LPDWORD lpdwcbRasAutodialAddresses, LPDWORD lpdwcRasAutodialAddresses)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c880`

## callees

- `0x180006afc`
- `0x18000b0f4`
- `0x18000f31c`
- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x18006cbf0`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd88`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006ce37`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006ce37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cdd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d22e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d23d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cdd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d22e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d23d`
- `ntdll!DbgPrint` at `0x18006d071`
- `ntdll!DbgPrint` at `0x18006d071`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006ce95`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006cf76`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006d05c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006ce95`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006cf76`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006d05c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d25a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d26a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d25a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d26a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d044`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006d044`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18006cfed`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18006cfed`

## pseudocode

```c
DWORD __stdcall RasEnumAutodialAddressesW(
        LPWSTR *lppRasAutodialAddresses,
        LPDWORD lpdwcbRasAutodialAddresses,
        LPDWORD lpdwcRasAutodialAddresses)
{
  LPDWORD v4; // r15
  LPWSTR *v5; // r13
  DWORD v6; // esi
  wchar_t *v7; // rdi
  WCHAR *v8; // r14
  _QWORD *v9; // r12
  unsigned int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  SIZE_T v18; // rbx
  _QWORD *v19; // rax
  DWORD v20; // ebx
  unsigned __int64 v21; // rax
  unsigned int v22; // edx
  unsigned int v23; // r13d
  DWORD v24; // r15d
  _QWORD *v25; // rcx
  int v26; // eax
  wchar_t *v27; // rax
  __int64 v28; // rax
  DWORD v29; // edi
  unsigned int v30; // r14d
  wchar_t *v31; // r15
  unsigned int v32; // edi
  __int64 v33; // rsi
  unsigned int v34; // eax
  HKEY v35; // rcx
  DWORD i; // edi
  void *v37; // rcx
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  DWORD cSubKeys; // [rsp+68h] [rbp-39h] BYREF
  DWORD v42; // [rsp+6Ch] [rbp-35h]
  WCHAR *v43; // [rsp+70h] [rbp-31h]
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-29h] BYREF
  int v45; // [rsp+7Ch] [rbp-25h]
  HKEY v46; // [rsp+80h] [rbp-21h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+88h] [rbp-19h] BYREF
  DWORD cbMaxValueLen; // [rsp+8Ch] [rbp-15h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+90h] [rbp-11h] BYREF
  DWORD cValues; // [rsp+94h] [rbp-Dh] BYREF
  DWORD cbMaxClassLen; // [rsp+98h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+7h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+B0h] [rbp+Fh] BYREF
  unsigned int v58; // [rsp+120h] [rbp+7Fh]

  v4 = lpdwcbRasAutodialAddresses;
  v5 = lppRasAutodialAddresses;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 784, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v6 = 0;
  phkResult = 0;
  v46 = 0;
  hKey = 0;
  v45 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  DebugInit();
  if ( v4 && lpdwcRasAutodialAddresses )
  {
    v42 = 0;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = DwOpenUsersRegistry(&hKey);
    v11 = v10;
    if ( v10 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 787;
        v14 = v10;
LABEL_12:
        WPP_SF_d(v12[2], v13, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v14);
        goto LABEL_89;
      }
      goto LABEL_89;
    }
    v15 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0x20019u, &phkResult);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 788, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v15);
      }
      v11 = 0;
      goto LABEL_89;
    }
    v16 = RegOpenKeyExW(phkResult, L"Addresses", 0, 0x20019u, &v46);
    if ( v16
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 789, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v16);
    }
    RegCloseKey(phkResult);
    if ( v16 )
    {
      v11 = 0;
      goto LABEL_89;
    }
    v17 = RegQueryInfoKeyW(
            v46,
            0,
            0,
            0,
            &cSubKeys,
            &cbMaxSubKeyLen,
            &cbMaxClassLen,
            &cValues,
            &cbMaxValueNameLen,
            &cbMaxValueLen,
            &cbSecurityDescriptor,
            &ftLastWriteTime);
    v11 = v17;
    if ( v17 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 790;
        v14 = v17;
        goto LABEL_12;
      }
LABEL_89:
      *lpdwcbRasAutodialAddresses = v42;
      v35 = v46;
      *lpdwcRasAutodialAddresses = (unsigned int)v7;
      if ( v35 )
        RegCloseKey(v35);
      if ( v45 )
        RegCloseKey(hKey);
      if ( v9 )
      {
        for ( i = 0; i < cSubKeys; ++i )
        {
          v37 = (void *)v9[i];
          if ( v37 )
            GlobalFree(v37);
        }
        GlobalFree(v9);
      }
      Free0(v8);
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v39 = 798;
LABEL_111:
        WPP_SF_d(v38[2], v39, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
        return v11;
      }
      return v11;
    }
    if ( !cSubKeys )
      goto LABEL_89;
    v42 = 8 * cSubKeys;
    v18 = 8 * cSubKeys;
    v19 = GlobalAlloc(0x40u, v18);
    v9 = v19;
    if ( !v19 )
    {
      v14 = 8;
      v11 = 8;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 791;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    memset_0(v19, 0, v18);
    v20 = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      v20 = -1;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 792, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 2147942934LL);
    }
    v12 = WPP_GLOBAL_Control;
LABEL_43:
    v21 = 2LL * v20;
    if ( v21 > 0xFFFFFFFF )
    {
      v11 = -2147024362;
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      {
        v13 = 793;
        v14 = 2147942934LL;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    v43 = (WCHAR *)GlobalAlloc(0x40u, (unsigned int)v21);
    v8 = v43;
    if ( !v43 )
    {
      v14 = 8;
      v11 = 8;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 794;
        goto LABEL_12;
      }
      goto LABEL_89;
    }
    v22 = 0;
    v11 = 0;
    v58 = 0;
    if ( !cSubKeys )
    {
      v25 = WPP_GLOBAL_Control;
LABEL_65:
      if ( v5 && (v29 = *v4, *v4 >= v42) )
      {
        v30 = 0;
        v31 = (wchar_t *)&v5[v22];
        v32 = v29 - 8 * v22;
        while ( 1 )
        {
          if ( v30 >= v22 )
          {
LABEL_88:
            v8 = v43;
            LODWORD(v7) = v58;
            goto LABEL_89;
          }
          v33 = -1;
          v5[v30] = v31;
          do
            ++v33;
          while ( *(_WORD *)(v9[v30] + 2 * v33) );
          v34 = StringCchCopyWrapW(v31);
          v11 = v34;
          if ( v34 )
            break;
          v32 += -2 - 2 * v33;
          if ( v32 < 2 )
            goto LABEL_88;
          v22 = v58;
          v31 += (unsigned int)(v33 + 1);
          ++v30;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 797, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v34);
        }
        LODWORD(v7) = v58;
        v8 = v43;
      }
      else
      {
        v11 = 603;
        if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 7) & 0x800) != 0 && *((_BYTE *)v25 + 25) >= 2u )
          WPP_SF_d(v25[2], 796, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 603);
        LODWORD(v7) = v58;
      }
      goto LABEL_89;
    }
    v23 = 0;
    while ( 1 )
    {
      v24 = cbMaxSubKeyLen + 1;
      v11 = RegEnumKeyW(v46, v6, v8, cbMaxSubKeyLen + 1);
      if ( v11 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 795, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
      }
      else
      {
        v26 = lstrlenW(v8);
        if ( v26 )
        {
          v27 = (wchar_t *)GlobalAlloc(0x40u, 2LL * (v26 + 1));
          v7 = v27;
          if ( v27 )
            StringCchCopyWrapW(v27);
          else
            DbgPrint("strdupW: LocalAlloc failed\n");
        }
        v8 = v43;
        v28 = v23++;
        v9[v28] = v7;
        v42 += 2 * v24 + 2;
        v7 = 0;
      }
      v25 = WPP_GLOBAL_Control;
LABEL_62:
      if ( ++v6 >= cSubKeys )
      {
        v4 = lpdwcbRasAutodialAddresses;
        v58 = v23;
        v22 = v23;
        v5 = lppRasAutodialAddresses;
        goto LABEL_65;
      }
    }
  }
  v38 = WPP_GLOBAL_Control;
  v11 = 87;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 785, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
      v38 = WPP_GLOBAL_Control;
    }
    if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x800) != 0 && *((_BYTE *)v38 + 25) >= 6u )
    {
      v39 = 786;
      goto LABEL_111;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18006cbf0  mov     rax, rsp
0x18006cbf3  mov     [rax+18h], r8
0x18006cbf7  mov     [rax+10h], rdx
0x18006cbfb  mov     [rax+8], rcx
0x18006cbff  push    rbp
0x18006cc00  push    rbx
0x18006cc01  push    rsi
0x18006cc02  push    rdi
0x18006cc03  push    r12
0x18006cc05  push    r13
0x18006cc07  push    r14
0x18006cc09  push    r15
0x18006cc0b  lea     rbp, [rax-5Fh]
0x18006cc0f  sub     rsp, 0B8h
0x18006cc16  mov     rbx, r8
0x18006cc19  mov     r15, rdx
0x18006cc1c  mov     r13, rcx
0x18006cc1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc26  lea     r14, WPP_GLOBAL_Control
0x18006cc2d  lea     r12, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006cc34  mov     edi, 800h
0x18006cc39  cmp     rcx, r14
0x18006cc3c  jz      short loc_18006CC5A
0x18006cc3e  test    [rcx+1Ch], edi
0x18006cc41  jz      short loc_18006CC5A
0x18006cc43  cmp     byte ptr [rcx+19h], 6
0x18006cc47  jb      short loc_18006CC5A
0x18006cc49  mov     rcx, [rcx+10h]
0x18006cc4d  mov     edx, 310h
0x18006cc52  mov     r8, r12
0x18006cc55  call    WPP_SF_
0x18006cc5a  xor     esi, esi
0x18006cc5c  mov     [rbp+57h+var_58], rsi
0x18006cc60  mov     [rbp+57h+var_78], rsi
0x18006cc64  mov     [rbp+57h+hKey], rsi
0x18006cc68  mov     [rbp+57h+var_7C], esi
0x18006cc6b  mov     [rbp+57h+cSubKeys], esi
0x18006cc6e  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x18006cc71  mov     [rbp+57h+cbMaxClassLen], esi
0x18006cc74  mov     [rbp+57h+cValues], esi
0x18006cc77  mov     [rbp+57h+cbMaxValueNameLen], esi
0x18006cc7a  mov     [rbp+57h+cbMaxValueLen], esi
0x18006cc7d  mov     [rbp+57h+cbSecurityDescriptor], esi
0x18006cc80  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rsi
0x18006cc84  call    DebugInit
0x18006cc89  test    r15, r15
0x18006cc8c  jz      loc_18006D2A1
0x18006cc92  test    rbx, rbx
0x18006cc95  jz      loc_18006D2A1
0x18006cc9b  lea     rdx, [rbp+57h+var_7C]
0x18006cc9f  mov     [rbp+57h+var_8C], esi
0x18006cca2  lea     rcx, [rbp+57h+hKey]; phkResult
0x18006cca6  mov     edi, esi
0x18006cca8  mov     r14d, esi
0x18006ccab  mov     r12d, esi
0x18006ccae  call    DwOpenUsersRegistry
0x18006ccb3  mov     ebx, eax
0x18006ccb5  test    eax, eax
0x18006ccb7  jz      short loc_18006CD04
0x18006ccb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ccc0  lea     rdx, WPP_GLOBAL_Control
0x18006ccc7  cmp     rcx, rdx
0x18006ccca  jz      loc_18006D20F
0x18006ccd0  test    dword ptr [rcx+1Ch], 800h
0x18006ccd7  jz      loc_18006D20F
0x18006ccdd  cmp     byte ptr [rcx+19h], 2
0x18006cce1  jb      loc_18006D20F
0x18006cce7  mov     edx, 313h
0x18006ccec  mov     r9d, eax
0x18006ccef  mov     rcx, [rcx+10h]
0x18006ccf3  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ccfa  call    WPP_SF_d
0x18006ccff  jmp     loc_18006D20F
0x18006cd04  mov     rcx, [rbp+57h+hKey]; hKey
0x18006cd08  lea     rax, [rbp+57h+var_58]
0x18006cd0c  mov     ebx, 20019h
0x18006cd11  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18006cd16  mov     r9d, ebx; samDesired
0x18006cd19  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18006cd20  xor     r8d, r8d; ulOptions
0x18006cd23  call    cs:__imp_RegOpenKeyExW
0x18006cd29  test    eax, eax
0x18006cd2b  jz      short loc_18006CD6E
0x18006cd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd34  lea     r15, WPP_GLOBAL_Control
0x18006cd3b  cmp     rcx, r15
0x18006cd3e  jz      short loc_18006CD67
0x18006cd40  test    dword ptr [rcx+1Ch], 800h
0x18006cd47  jz      short loc_18006CD67
0x18006cd49  cmp     byte ptr [rcx+19h], 2
0x18006cd4d  jb      short loc_18006CD67
0x18006cd4f  mov     rcx, [rcx+10h]
0x18006cd53  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006cd5a  mov     edx, 314h
0x18006cd5f  mov     r9d, eax
0x18006cd62  call    WPP_SF_d
0x18006cd67  mov     ebx, esi
0x18006cd69  jmp     loc_18006D216
0x18006cd6e  mov     rcx, [rbp+57h+var_58]; hKey
0x18006cd72  lea     rax, [rbp+57h+var_78]
0x18006cd76  mov     r9d, ebx; samDesired
0x18006cd79  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18006cd7e  xor     r8d, r8d; ulOptions
0x18006cd81  lea     rdx, aAddresses; "Addresses"
0x18006cd88  call    cs:__imp_RegOpenKeyExW
0x18006cd8e  mov     ebx, eax
0x18006cd90  test    eax, eax
0x18006cd92  jz      short loc_18006CDCE
0x18006cd94  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd9b  lea     rax, WPP_GLOBAL_Control
0x18006cda2  cmp     rcx, rax
0x18006cda5  jz      short loc_18006CDCE
0x18006cda7  test    dword ptr [rcx+1Ch], 800h
0x18006cdae  jz      short loc_18006CDCE
0x18006cdb0  cmp     byte ptr [rcx+19h], 2
0x18006cdb4  jb      short loc_18006CDCE
0x18006cdb6  mov     rcx, [rcx+10h]
0x18006cdba  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006cdc1  mov     edx, 315h
0x18006cdc6  mov     r9d, ebx
0x18006cdc9  call    WPP_SF_d
0x18006cdce  mov     rcx, [rbp+57h+var_58]; hKey
0x18006cdd2  call    cs:__imp_RegCloseKey
0x18006cdd8  test    ebx, ebx
0x18006cdda  jz      short loc_18006CDE3
0x18006cddc  mov     ebx, esi
0x18006cdde  jmp     loc_18006D20F
0x18006cde3  mov     rcx, [rbp+57h+var_78]; hKey
0x18006cde7  lea     rax, [rbp+57h+ftLastWriteTime]
0x18006cdeb  mov     [rsp+58h], rax; lpftLastWriteTime
0x18006cdf0  xor     r9d, r9d; lpReserved
0x18006cdf3  lea     rax, [rbp+57h+cbSecurityDescriptor]
0x18006cdf7  xor     r8d, r8d; lpcchClass
0x18006cdfa  mov     [rsp+0F0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x18006cdff  xor     edx, edx; lpClass
0x18006ce01  lea     rax, [rbp+57h+cbMaxValueLen]
0x18006ce05  mov     [rsp+0F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18006ce0a  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18006ce0e  mov     [rsp+0F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18006ce13  lea     rax, [rbp+57h+cValues]
0x18006ce17  mov     [rsp+0F0h+lpcValues], rax; lpcValues
0x18006ce1c  lea     rax, [rbp+57h+cbMaxClassLen]
0x18006ce20  mov     [rsp+0F0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18006ce25  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18006ce29  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18006ce2e  lea     rax, [rbp+57h+cSubKeys]
0x18006ce32  mov     [rsp+0F0h+phkResult], rax; lpcSubKeys
0x18006ce37  call    cs:__imp_RegQueryInfoKeyW
0x18006ce3d  mov     ebx, eax
0x18006ce3f  test    eax, eax
0x18006ce41  jz      short loc_18006CE7B
0x18006ce43  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ce4a  lea     r15, WPP_GLOBAL_Control
0x18006ce51  cmp     rcx, r15
0x18006ce54  jz      loc_18006D216
0x18006ce5a  test    dword ptr [rcx+1Ch], 800h
0x18006ce61  jz      loc_18006D216
0x18006ce67  cmp     byte ptr [rcx+19h], 2
0x18006ce6b  jb      loc_18006D216
0x18006ce71  mov     edx, 316h
0x18006ce76  mov     r9d, eax
0x18006ce79  jmp     short loc_18006CEDD
0x18006ce7b  mov     eax, [rbp+57h+cSubKeys]
0x18006ce7e  test    eax, eax
0x18006ce80  jz      loc_18006D20F
0x18006ce86  shl     eax, 3
0x18006ce89  mov     ecx, 40h ; '@'; uFlags
0x18006ce8e  mov     edx, eax; dwBytes
0x18006ce90  mov     [rbp+57h+var_8C], eax
0x18006ce93  mov     ebx, eax
0x18006ce95  call    cs:__imp_GlobalAlloc
0x18006ce9b  mov     r12, rax
0x18006ce9e  test    rax, rax
0x18006cea1  jnz     short loc_18006CEF2
0x18006cea3  lea     r9d, [rax+8]
0x18006cea7  mov     ebx, r9d
0x18006ceaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ceb1  lea     r15, WPP_GLOBAL_Control
0x18006ceb8  cmp     rcx, r15
0x18006cebb  jz      loc_18006D216
0x18006cec1  test    dword ptr [rcx+1Ch], 800h
0x18006cec8  jz      loc_18006D216
0x18006cece  cmp     byte ptr [rcx+19h], 2
0x18006ced2  jb      loc_18006D216
0x18006ced8  mov     edx, 317h
0x18006cedd  mov     rcx, [rcx+10h]
0x18006cee1  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006cee8  call    WPP_SF_d
0x18006ceed  jmp     loc_18006D216
0x18006cef2  mov     r8, rbx; Size
0x18006cef5  xor     edx, edx; Val
0x18006cef7  mov     rcx, r12; void *
0x18006cefa  call    memset_0
0x18006ceff  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18006cf02  mov     ecx, 0FFFFFFFFh
0x18006cf07  lea     ebx, [rax+1]
0x18006cf0a  cmp     ebx, eax
0x18006cf0c  jnb     short loc_18006CF4D
0x18006cf0e  mov     ebx, ecx
0x18006cf10  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf17  lea     rdx, WPP_GLOBAL_Control
0x18006cf1e  cmp     rcx, rdx
0x18006cf21  jz      short loc_18006CF5B
0x18006cf23  test    dword ptr [rcx+1Ch], 800h
0x18006cf2a  jz      short loc_18006CF5B
0x18006cf2c  cmp     byte ptr [rcx+19h], 2
0x18006cf30  jb      short loc_18006CF5B
0x18006cf32  mov     rcx, [rcx+10h]
0x18006cf36  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006cf3d  mov     edx, 318h
0x18006cf42  mov     r9d, 80070216h
0x18006cf48  call    WPP_SF_d
0x18006cf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf54  lea     rdx, WPP_GLOBAL_Control
0x18006cf5b  mov     eax, ebx
0x18006cf5d  mov     r8d, 0FFFFFFFFh
0x18006cf63  add     rax, rax
0x18006cf66  cmp     rax, r8
0x18006cf69  ja      loc_18006D1DD
0x18006cf6f  mov     edx, eax; dwBytes
0x18006cf71  mov     ecx, 40h ; '@'; uFlags
0x18006cf76  call    cs:__imp_GlobalAlloc
0x18006cf7c  mov     [rbp+57h+var_88], rax
0x18006cf80  mov     r14, rax
0x18006cf83  test    rax, rax
0x18006cf86  jnz     short loc_18006CFC7
0x18006cf88  lea     r9d, [rax+8]
0x18006cf8c  mov     ebx, r9d
0x18006cf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cf96  lea     r15, WPP_GLOBAL_Control
0x18006cf9d  cmp     rcx, r15
0x18006cfa0  jz      loc_18006D216
0x18006cfa6  test    dword ptr [rcx+1Ch], 800h
0x18006cfad  jz      loc_18006D216
0x18006cfb3  cmp     byte ptr [rcx+19h], 2
0x18006cfb7  jb      loc_18006D216
0x18006cfbd  mov     edx, 31Ah
0x18006cfc2  jmp     loc_18006CEDD
0x18006cfc7  mov     edx, edi
0x18006cfc9  mov     ebx, esi
0x18006cfcb  mov     [rbp+57h+arg_18], edx
0x18006cfce  cmp     [rbp+57h+cSubKeys], edi
0x18006cfd1  jbe     loc_18006D0C8
0x18006cfd7  mov     r13d, edx
0x18006cfda  mov     r15d, [rbp+57h+cbMaxSubKeyLen]
0x18006cfde  mov     r8, r14; lpName
0x18006cfe1  mov     rcx, [rbp+57h+var_78]; hKey
0x18006cfe5  inc     r15d
0x18006cfe8  mov     r9d, r15d; cchName
0x18006cfeb  mov     edx, esi; dwIndex
0x18006cfed  call    cs:__imp_RegEnumKeyW
0x18006cff3  mov     ebx, eax
0x18006cff5  test    eax, eax
0x18006cff7  jz      short loc_18006D041
0x18006cff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d000  lea     rax, WPP_GLOBAL_Control
0x18006d007  cmp     rcx, rax
0x18006d00a  jz      loc_18006D0AC
0x18006d010  test    dword ptr [rcx+1Ch], 800h
0x18006d017  jz      loc_18006D0AC
0x18006d01d  cmp     byte ptr [rcx+19h], 2
0x18006d021  jb      loc_18006D0AC
0x18006d027  mov     rcx, [rcx+10h]
0x18006d02b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006d032  mov     edx, 31Bh
0x18006d037  mov     r9d, ebx
0x18006d03a  call    WPP_SF_d
0x18006d03f  jmp     short loc_18006D0A5
0x18006d041  mov     rcx, r14; lpString
0x18006d044  call    cs:__imp_lstrlenW
0x18006d04a  test    eax, eax
0x18006d04c  jz      short loc_18006D088
0x18006d04e  inc     eax
0x18006d050  mov     ecx, 40h ; '@'; uFlags
0x18006d055  movsxd  r14, eax
0x18006d058  lea     rdx, [r14+r14]; dwBytes
0x18006d05c  call    cs:__imp_GlobalAlloc
0x18006d062  mov     rdi, rax
0x18006d065  test    rax, rax
0x18006d068  jnz     short loc_18006D079
0x18006d06a  lea     rcx, aStrdupwLocalal; "strdupW: LocalAlloc failed\n"
0x18006d071  call    cs:__imp_DbgPrint
0x18006d077  jmp     short loc_18006D088
0x18006d079  mov     r8, [rbp+57h+var_88]
0x18006d07d  mov     rdx, r14
0x18006d080  mov     rcx, rax; pszDest
0x18006d083  call    StringCchCopyWrapW
0x18006d088  mov     r14, [rbp+57h+var_88]
0x18006d08c  mov     eax, r13d
0x18006d08f  inc     r13d
0x18006d092  mov     [r12+rax*8], rdi
0x18006d096  mov     eax, [rbp+57h+var_8C]
0x18006d099  lea     eax, [rax+r15*2]
0x18006d09d  add     eax, 2
0x18006d0a0  mov     [rbp+57h+var_8C], eax
0x18006d0a3  xor     edi, edi
0x18006d0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d0ac  inc     esi
0x18006d0ae  cmp     esi, [rbp+57h+cSubKeys]
0x18006d0b1  jb      loc_18006CFDA
  ... truncated ...
```
