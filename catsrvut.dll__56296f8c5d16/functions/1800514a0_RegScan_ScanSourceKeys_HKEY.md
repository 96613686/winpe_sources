# RegScan::ScanSourceKeys(HKEY__ *)

- ea: `0x1800514a0`
- end: `0x180051df4`
- name: `?ScanSourceKeys@RegScan@@QEAAJPEAUHKEY__@@@Z`
- size: `2388`
- prototype: `__int64 __fastcall(RegScan *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eaf8`
- `0x1800514a0`

## callees

- `0x180001e60`
- `0x180005944`
- `0x18004fc3c`
- `0x1800514a0`
- `0x180051dfc`
- `0x180052490`
- `0x180052734`
- `0x18005583a`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051ae1`
- `msvcrt!_wcsicmp` at `0x180051ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800518e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800518e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051d4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005176a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180051bc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005176a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180051bc3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800519ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800519ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051748`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051748`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051734`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180051734`

## string_xrefs

- `0x1800514dd`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800518bd`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051949`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051a6d`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051aca`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051b31`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051c15`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051c70`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051cf6`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051508`: `m_hkeySource != HKEY_CURRENT_CONFIG`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall RegScan::ScanSourceKeys(RegScan *this, HKEY a2)
{
  HKEY *v3; // rdi
  unsigned int v4; // r13d
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  int v7; // esi
  LSTATUS result; // eax
  bool v9; // cc
  unsigned int v10; // edx
  DWORD v11; // ecx
  DWORD v12; // eax
  unsigned __int64 v13; // rcx
  unsigned int v14; // r15d
  _QWORD *v15; // rax
  _QWORD *v16; // r14
  unsigned int v17; // esi
  __int64 v18; // rcx
  unsigned int v19; // r14d
  __int64 v20; // rsi
  DWORD v21; // edx
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  void *v24; // rsp
  WCHAR *v25; // r12
  DWORD v26; // esi
  unsigned int v27; // r14d
  const wchar_t *v28; // r12
  __int64 v29; // rax
  RegScan *v30; // rcx
  wchar_t *v31; // r14
  __int64 v32; // r12
  RegScan *v33; // rax
  RegScan *v34; // rcx
  __int64 v35; // rcx
  unsigned __int16 *v36; // rax
  void *v37; // r10
  int v38; // r14d
  WCHAR Name[2]; // [rsp+60h] [rbp+0h] BYREF
  __int16 v40; // [rsp+64h] [rbp+4h]
  int v41; // [rsp+68h] [rbp+8h]
  const unsigned __int16 *v42; // [rsp+70h] [rbp+10h]
  __int64 v43; // [rsp+78h] [rbp+18h]
  __int64 v44; // [rsp+80h] [rbp+20h]
  int v45; // [rsp+88h] [rbp+28h]
  int v46; // [rsp+8Ch] [rbp+2Ch]
  DWORD cbMaxSubKeyLen; // [rsp+90h] [rbp+30h] BYREF
  DWORD cSubKeys; // [rsp+94h] [rbp+34h] BYREF
  unsigned int v49; // [rsp+98h] [rbp+38h]
  DWORD cbMaxValueNameLen; // [rsp+9Ch] [rbp+3Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+A0h] [rbp+40h] BYREF
  DWORD cValues; // [rsp+A4h] [rbp+44h] BYREF
  unsigned int v53; // [rsp+A8h] [rbp+48h]
  DWORD cchName; // [rsp+ACh] [rbp+4Ch] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp+50h] BYREF
  wchar_t *String2; // [rsp+B8h] [rbp+58h]
  RegScan *v57; // [rsp+C0h] [rbp+60h]

  v3 = (HKEY *)((char *)this + 40);
  v4 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    if ( !a2 || a2 == *v3 )
      goto LABEL_18;
    v5 = L"(NULL == i_hkeySource) || (i_hkeySource == m_hkeySource)";
    v6 = 1928;
  }
  else
  {
    *v3 = a2;
    if ( a2 == HKEY_CURRENT_CONFIG )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_hkeySource != HKEY_CURRENT_CONFIG";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x77Du,
        L"m_hkeySource != HKEY_CURRENT_CONFIG");
    }
    if ( *v3 == HKEY_CURRENT_USER )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_hkeySource != HKEY_CURRENT_USER";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x77Eu,
        L"m_hkeySource != HKEY_CURRENT_USER");
    }
    if ( *v3 == HKEY_DYN_DATA )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_hkeySource != HKEY_DYN_DATA";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x77Fu,
        L"m_hkeySource != HKEY_DYN_DATA");
    }
    if ( *v3 == HKEY_LOCAL_MACHINE )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_hkeySource != HKEY_LOCAL_MACHINE";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x780u,
        L"m_hkeySource != HKEY_LOCAL_MACHINE");
    }
    if ( *v3 == HKEY_PERFORMANCE_DATA )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_hkeySource != HKEY_PERFORMANCE_DATA";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x781u,
        L"m_hkeySource != HKEY_PERFORMANCE_DATA");
    }
    if ( *v3 != HKEY_USERS )
      goto LABEL_18;
    v5 = L"m_hkeySource != HKEY_USERS";
    v6 = 1922;
  }
  *(_DWORD *)Name = 0;
  v40 = 21;
  v41 = -1073605930;
  v42 = v5;
  v43 = 0;
  v44 = 0;
  v46 = 1;
  v45 = 1;
  CError::WriteToLog((CError *)Name, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", v6, v5);
LABEL_18:
  if ( !*v3 )
  {
    *(_DWORD *)Name = 0;
    v40 = 21;
    v41 = -1073605930;
    v42 = L"m_hkeySource";
    v43 = 0;
    v44 = 0;
    v46 = 1;
    v45 = 1;
    CError::WriteToLog((CError *)Name, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x78Bu, L"m_hkeySource");
  }
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  cSubKeys = 0;
  v7 = 1;
  while ( 1 )
  {
    result = RegQueryInfoKeyW(
               *v3,
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
               0);
    if ( !result )
      break;
    if ( v7 )
    {
      v7 = 0;
      RegCloseKey(*v3);
      *v3 = 0;
      result = RegOpenKeyExW(HKEY_CLASSES_ROOT, *((LPCWSTR *)this + 10), 0, 0x2001Fu, v3);
      if ( !result )
        continue;
    }
    v9 = result <= 0;
    goto LABEL_25;
  }
  ++cbMaxSubKeyLen;
  v10 = ++cbMaxValueNameLen;
  v11 = cbMaxValueLen + 1;
  cbMaxValueLen = v11;
  v12 = *((_DWORD *)this + 15);
  if ( v12 <= v11 )
    v12 = v11;
  *((_DWORD *)this + 15) = v12;
  result = RegScan::ScanSourceValues(this, v10, cValues);
  if ( !result )
  {
    v13 = cSubKeys;
    if ( *((_DWORD *)this + 2) > cSubKeys )
    {
      *(_DWORD *)Name = 0;
      v40 = 21;
      v41 = -1073605930;
      v42 = L"m_cSubKeys <= cSubKeys";
      v43 = 0;
      v44 = 0;
      v46 = 1;
      v45 = 1;
      CError::WriteToLog(
        (CError *)Name,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x7D9u,
        L"m_cSubKeys <= cSubKeys");
      v13 = cSubKeys;
    }
    if ( (unsigned int)v13 >= *(_DWORD *)(*((_QWORD *)this + 12) + 120LL) )
      return -2147024892;
    v14 = *((_DWORD *)this + 2);
    v49 = v14;
    if ( (unsigned int)v13 > v14 )
    {
      v15 = CoTaskMemAlloc(saturated_mul(v13, 8u));
      v16 = v15;
      if ( !v15 )
        return -2147024882;
      memset_0(v15, 0, 8LL * cSubKeys);
      if ( *(_QWORD *)this )
      {
        v17 = 0;
        if ( *((_DWORD *)this + 2) )
        {
          do
          {
            v18 = *(_QWORD *)(*(_QWORD *)this + 8LL * v17);
            v16[v17] = v18;
            if ( !v18 )
            {
              *(_DWORD *)Name = 0;
              v40 = 21;
              v41 = -1073605930;
              v42 = L"apRegScanNew[dwRS]";
              v43 = 0;
              v44 = 0;
              v46 = 1;
              v45 = 1;
              CError::WriteToLog(
                (CError *)Name,
                L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
                0x7FDu,
                L"apRegScanNew[dwRS]");
            }
            ++v17;
          }
          while ( v17 < *((_DWORD *)this + 2) );
          v3 = (HKEY *)((char *)this + 40);
          v14 = v49;
        }
      }
      *((_DWORD *)this + 2) = cSubKeys;
      CoTaskMemFree(*(LPVOID *)this);
      *(_QWORD *)this = v16;
    }
    if ( *(_QWORD *)this )
    {
      v19 = 0;
      if ( v14 )
      {
        v20 = 0;
        do
        {
          if ( !*(_QWORD *)(*(_QWORD *)this + 8 * v20) )
          {
            *(_DWORD *)Name = 0;
            v40 = 21;
            v41 = -1073605930;
            v42 = L"m_apRegScan[dwRS]";
            v43 = 0;
            v44 = 0;
            v46 = 1;
            v45 = 1;
            CError::WriteToLog(
              (CError *)Name,
              L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
              0x80Eu,
              L"m_apRegScan[dwRS]");
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8 * v20) + 56LL) = 0;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8 * v20) + 72LL) = 0;
          ++v19;
          ++v20;
        }
        while ( v19 < v14 );
        v3 = (HKEY *)((char *)this + 40);
      }
    }
    v21 = cbMaxSubKeyLen;
    v22 = 2LL * (cbMaxSubKeyLen + 1);
    v23 = v22 + 15;
    if ( v22 + 15 < v22 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
    v25 = Name;
    String2 = Name;
    v53 = v14;
    v26 = 0;
    while ( 2 )
    {
      v49 = v26;
      if ( v26 >= *((_DWORD *)this + 2) )
        return 0;
      cchName = v21;
      result = RegEnumKeyExW(*v3, v26, v25, &cchName, 0, 0, 0, 0);
      if ( result == 259 )
        return 0;
      v9 = result <= 0;
      if ( result )
        goto LABEL_25;
      v27 = 0;
      if ( v14 )
        v27 = v26 % v14;
      while ( v4 < v14 )
      {
        if ( !*(_QWORD *)(*(_QWORD *)this + 8LL * v27) )
        {
          *(_DWORD *)Name = 0;
          v40 = 21;
          v41 = -1073605930;
          v42 = L"m_apRegScan[dwRealKeyIndex]";
          v43 = 0;
          v44 = 0;
          v46 = 1;
          v45 = 1;
          CError::WriteToLog(
            (CError *)Name,
            L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
            0x845u,
            L"m_apRegScan[dwRealKeyIndex]");
        }
        v28 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)this + 8LL * v27) + 32LL);
        if ( !v28 )
        {
          *(_DWORD *)Name = 0;
          v40 = 21;
          v41 = -1073605930;
          v42 = L"lpExistingKeyName";
          v43 = 0;
          v44 = 0;
          v46 = 1;
          v45 = 1;
          CError::WriteToLog(
            (CError *)Name,
            L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
            0x849u,
            L"lpExistingKeyName");
        }
        if ( !_wcsicmp(v28, String2) )
        {
          v4 = 0;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL * v27) + 56LL) = 0;
          result = RegScan::ScanSourceKeys(*(RegScan **)(*(_QWORD *)this + 8LL * v27), 0);
          if ( result )
            return result;
          goto LABEL_88;
        }
        if ( !v14 )
        {
          *(_DWORD *)Name = 0;
          v40 = 21;
          v41 = -1073605930;
          v42 = L"cOldSubKeys";
          v43 = 0;
          v44 = 0;
          v46 = 1;
          v45 = 1;
          CError::WriteToLog((CError *)Name, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x858u, L"cOldSubKeys");
        }
        v27 = (v27 + 1) % v14;
        ++v4;
      }
      v29 = *((_QWORD *)this + 8);
      v4 = 0;
      if ( v29 )
      {
        *(_DWORD *)(v29 + 72) = 1;
        v30 = *(RegScan **)(v29 + 64);
        if ( v30 )
          RegScan::SetScanIsRequired(v30, 1);
      }
      phkResult = 0;
      v31 = String2;
      result = RegOpenKeyExW(*v3, String2, 0, 0x2001Fu, &phkResult);
      v9 = result <= 0;
      if ( result )
      {
LABEL_25:
        if ( !v9 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
      if ( !phkResult )
      {
        *(_DWORD *)Name = 0;
        v40 = 21;
        v41 = -1073605930;
        v42 = L"hkEnumKey";
        v43 = 0;
        v44 = 0;
        v46 = 1;
        v45 = 1;
        CError::WriteToLog((CError *)Name, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x889u, L"hkEnumKey");
      }
      v32 = v53;
      if ( *(_QWORD *)(*(_QWORD *)this + 8LL * v53) )
      {
        *(_DWORD *)Name = 0;
        v40 = 21;
        v41 = -1073605930;
        v42 = L"NULL == m_apRegScan[dwNextIndex]";
        v43 = 0;
        v44 = 0;
        v46 = 1;
        v45 = 1;
        CError::WriteToLog(
          (CError *)Name,
          L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
          0x88Du,
          L"NULL == m_apRegScan[dwNextIndex]");
      }
      v33 = (RegScan *)CoTaskMemAlloc(0x98u);
      v57 = v33;
      if ( v33 )
        v34 = RegScan::RegScan(v33, *((struct RegScan **)this + 12));
      else
        v34 = 0;
      *(_QWORD *)(*(_QWORD *)this + 8 * v32) = v34;
      if ( !*(_QWORD *)(*(_QWORD *)this + 8 * v32) )
      {
        *(_DWORD *)Name = 0;
        v40 = 21;
        v41 = -1073605930;
        v42 = L"m_apRegScan[dwNextIndex]";
        v43 = 0;
        v44 = 0;
        v46 = 1;
        v45 = 1;
        CError::WriteToLog(
          (CError *)Name,
          L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
          0x891u,
          L"m_apRegScan[dwNextIndex]");
      }
      v35 = *(_QWORD *)(*(_QWORD *)this + 8 * v32);
      if ( v35 )
      {
        *(_DWORD *)(v35 + 56) = 1;
        *(_DWORD *)(v35 + 72) = 1;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8 * v32) + 64LL) = this;
        v36 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(cbMaxSubKeyLen + 1, 2u));
        if ( v36 )
        {
          v38 = StringCchCopyW(v36, cbMaxSubKeyLen + 1, v31);
          if ( v38 < 0 )
          {
            CoTaskMemFree(v37);
            return v38;
          }
          else
          {
            result = RegScan::SetKeyName(
                       *(RegScan **)(*(_QWORD *)this + 8 * v32),
                       *((unsigned __int16 **)this + 10),
                       (unsigned __int16 *)v37);
            if ( !result )
            {
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8 * v32) + 88LL) |= *((_DWORD *)this + 22);
              result = RegScan::ScanSourceKeys(*(RegScan **)(*(_QWORD *)this + 8 * v32), phkResult);
              if ( !result )
              {
                v53 = v32 + 1;
LABEL_88:
                v26 = v49 + 1;
                v21 = cbMaxSubKeyLen;
                v25 = String2;
                continue;
              }
            }
          }
          return result;
        }
      }
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800514a0  push    rbp
0x1800514a2  push    rbx
0x1800514a3  push    rsi
0x1800514a4  push    rdi
0x1800514a5  push    r12
0x1800514a7  push    r13
0x1800514a9  push    r14
0x1800514ab  push    r15
0x1800514ad  sub     rsp, 0D8h
0x1800514b4  lea     rbp, [rsp+60h]
0x1800514b9  mov     rax, cs:__security_cookie
0x1800514c0  xor     rax, rbp
0x1800514c3  mov     [rbp+0B0h+var_48], rax
0x1800514c7  mov     rbx, rcx
0x1800514ca  lea     rdi, [rcx+28h]
0x1800514ce  mov     esi, 15h
0x1800514d3  mov     r14d, 0C00212D6h
0x1800514d9  lea     r12d, [rsi-14h]
0x1800514dd  lea     r15, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800514e4  xor     r13d, r13d
0x1800514e7  cmp     [rdi], r13
0x1800514ea  jnz     loc_180051655
0x1800514f0  mov     [rdi], rdx
0x1800514f3  cmp     rdx, 0FFFFFFFF80000005h
0x1800514fa  jnz     short loc_180051535
0x1800514fc  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051500  mov     [rbp+0B0h+var_AC], si
0x180051504  mov     [rbp+0B0h+var_A8], r14d
0x180051508  lea     r9, aMHkeysourceHke; "m_hkeySource != HKEY_CURRENT_CONFIG"
0x18005150f  mov     [rbp+0B0h+var_A0], r9
0x180051513  mov     [rbp+0B0h+var_98], r13
0x180051517  mov     [rbp+0B0h+var_90], r13
0x18005151b  mov     [rbp+0B0h+var_84], r12d
0x18005151f  mov     [rbp+0B0h+var_88], r12d
0x180051523  mov     r8d, 77Dh; unsigned int
0x180051529  mov     rdx, r15; unsigned __int16 *
0x18005152c  lea     rcx, [rbp+0B0h+Name]; this
0x180051530  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051535  cmp     qword ptr [rdi], 0FFFFFFFF80000001h
0x18005153c  jnz     short loc_180051577
0x18005153e  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051542  mov     [rbp+0B0h+var_AC], si
0x180051546  mov     [rbp+0B0h+var_A8], r14d
0x18005154a  lea     r9, aMHkeysourceHke_2; "m_hkeySource != HKEY_CURRENT_USER"
0x180051551  mov     [rbp+0B0h+var_A0], r9
0x180051555  mov     [rbp+0B0h+var_98], r13
0x180051559  mov     [rbp+0B0h+var_90], r13
0x18005155d  mov     [rbp+0B0h+var_84], r12d
0x180051561  mov     [rbp+0B0h+var_88], r12d
0x180051565  mov     r8d, 77Eh; unsigned int
0x18005156b  mov     rdx, r15; unsigned __int16 *
0x18005156e  lea     rcx, [rbp+0B0h+Name]; this
0x180051572  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051577  cmp     qword ptr [rdi], 0FFFFFFFF80000006h
0x18005157e  jnz     short loc_1800515B9
0x180051580  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051584  mov     [rbp+0B0h+var_AC], si
0x180051588  mov     [rbp+0B0h+var_A8], r14d
0x18005158c  lea     r9, aMHkeysourceHke_4; "m_hkeySource != HKEY_DYN_DATA"
0x180051593  mov     [rbp+0B0h+var_A0], r9
0x180051597  mov     [rbp+0B0h+var_98], r13
0x18005159b  mov     [rbp+0B0h+var_90], r13
0x18005159f  mov     [rbp+0B0h+var_84], r12d
0x1800515a3  mov     [rbp+0B0h+var_88], r12d
0x1800515a7  mov     r8d, 77Fh; unsigned int
0x1800515ad  mov     rdx, r15; unsigned __int16 *
0x1800515b0  lea     rcx, [rbp+0B0h+Name]; this
0x1800515b4  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800515b9  cmp     qword ptr [rdi], 0FFFFFFFF80000002h
0x1800515c0  jnz     short loc_1800515FB
0x1800515c2  mov     dword ptr [rbp+0B0h+Name], r13d
0x1800515c6  mov     [rbp+0B0h+var_AC], si
0x1800515ca  mov     [rbp+0B0h+var_A8], r14d
0x1800515ce  lea     r9, aMHkeysourceHke_3; "m_hkeySource != HKEY_LOCAL_MACHINE"
0x1800515d5  mov     [rbp+0B0h+var_A0], r9
0x1800515d9  mov     [rbp+0B0h+var_98], r13
0x1800515dd  mov     [rbp+0B0h+var_90], r13
0x1800515e1  mov     [rbp+0B0h+var_84], r12d
0x1800515e5  mov     [rbp+0B0h+var_88], r12d
0x1800515e9  mov     r8d, 780h; unsigned int
0x1800515ef  mov     rdx, r15; unsigned __int16 *
0x1800515f2  lea     rcx, [rbp+0B0h+Name]; this
0x1800515f6  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800515fb  cmp     qword ptr [rdi], 0FFFFFFFF80000004h
0x180051602  jnz     short loc_18005163D
0x180051604  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051608  mov     [rbp+0B0h+var_AC], si
0x18005160c  mov     [rbp+0B0h+var_A8], r14d
0x180051610  lea     r9, aMHkeysourceHke_1; "m_hkeySource != HKEY_PERFORMANCE_DATA"
0x180051617  mov     [rbp+0B0h+var_A0], r9
0x18005161b  mov     [rbp+0B0h+var_98], r13
0x18005161f  mov     [rbp+0B0h+var_90], r13
0x180051623  mov     [rbp+0B0h+var_84], r12d
0x180051627  mov     [rbp+0B0h+var_88], r12d
0x18005162b  mov     r8d, 781h; unsigned int
0x180051631  mov     rdx, r15; unsigned __int16 *
0x180051634  lea     rcx, [rbp+0B0h+Name]; this
0x180051638  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18005163d  cmp     qword ptr [rdi], 0FFFFFFFF80000003h
0x180051644  jnz     short loc_180051698
0x180051646  lea     r9, aMHkeysourceHke_0; "m_hkeySource != HKEY_USERS"
0x18005164d  mov     r8d, 782h
0x180051653  jmp     short loc_18005166C
0x180051655  test    rdx, rdx
0x180051658  jz      short loc_180051698
0x18005165a  cmp     rdx, [rdi]
0x18005165d  jz      short loc_180051698
0x18005165f  lea     r9, aNullIHkeysourc; "(NULL == i_hkeySource) || (i_hkeySource"...
0x180051666  mov     r8d, 788h; unsigned int
0x18005166c  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051670  mov     [rbp+0B0h+var_AC], si
0x180051674  mov     [rbp+0B0h+var_A8], r14d
0x180051678  mov     [rbp+0B0h+var_A0], r9
0x18005167c  mov     [rbp+0B0h+var_98], r13
0x180051680  mov     [rbp+0B0h+var_90], r13
0x180051684  mov     [rbp+0B0h+var_84], r12d
0x180051688  mov     [rbp+0B0h+var_88], r12d
0x18005168c  mov     rdx, r15; unsigned __int16 *
0x18005168f  lea     rcx, [rbp+0B0h+Name]; this
0x180051693  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051698  cmp     [rdi], r13
0x18005169b  jnz     short loc_1800516D6
0x18005169d  mov     dword ptr [rbp+0B0h+Name], r13d
0x1800516a1  mov     [rbp+0B0h+var_AC], si
0x1800516a5  mov     [rbp+0B0h+var_A8], r14d
0x1800516a9  lea     r9, aMHkeysource; "m_hkeySource"
0x1800516b0  mov     [rbp+0B0h+var_A0], r9
0x1800516b4  mov     [rbp+0B0h+var_98], r13
0x1800516b8  mov     [rbp+0B0h+var_90], r13
0x1800516bc  mov     [rbp+0B0h+var_84], r12d
0x1800516c0  mov     [rbp+0B0h+var_88], r12d
0x1800516c4  mov     r8d, 78Bh; unsigned int
0x1800516ca  mov     rdx, r15; unsigned __int16 *
0x1800516cd  lea     rcx, [rbp+0B0h+Name]; this
0x1800516d1  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800516d6  mov     [rbp+0B0h+cbMaxSubKeyLen], r13d
0x1800516da  mov     [rbp+0B0h+cbMaxValueNameLen], r13d
0x1800516de  mov     [rbp+0B0h+cbMaxValueLen], r13d
0x1800516e2  mov     [rbp+0B0h+cValues], r13d
0x1800516e6  mov     [rbp+0B0h+cSubKeys], r13d
0x1800516ea  mov     esi, r12d
0x1800516ed  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800516f2  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800516f7  lea     rax, [rbp+0B0h+cbMaxValueLen]
0x1800516fb  mov     [rsp+110h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180051700  lea     rax, [rbp+0B0h+cbMaxValueNameLen]
0x180051704  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180051709  lea     rax, [rbp+0B0h+cValues]
0x18005170d  mov     [rsp+110h+lpcValues], rax; lpcValues
0x180051712  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180051717  lea     rax, [rbp+0B0h+cbMaxSubKeyLen]
0x18005171b  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180051720  lea     rax, [rbp+0B0h+cSubKeys]
0x180051724  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x180051729  xor     r9d, r9d; lpReserved
0x18005172c  xor     r8d, r8d; lpcchClass
0x18005172f  xor     edx, edx; lpClass
0x180051731  mov     rcx, [rdi]; hKey
0x180051734  call    cs:__imp_RegQueryInfoKeyW
0x18005173a  test    eax, eax
0x18005173c  jz      short loc_18005178D
0x18005173e  test    esi, esi
0x180051740  jz      short loc_180051778
0x180051742  mov     esi, r13d
0x180051745  mov     rcx, [rdi]; hKey
0x180051748  call    cs:__imp_RegCloseKey
0x18005174e  mov     [rdi], r13
0x180051751  mov     [rsp+110h+lpcSubKeys], rdi; phkResult
0x180051756  mov     r9d, 2001Fh; samDesired
0x18005175c  xor     r8d, r8d; ulOptions
0x18005175f  mov     rdx, [rbx+50h]; lpSubKey
0x180051763  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005176a  call    cs:__imp_RegOpenKeyExW
0x180051770  test    eax, eax
0x180051772  jz      loc_1800516ED
0x180051778  test    eax, eax
0x18005177a  jle     loc_180051DD7
0x180051780  movzx   eax, ax
0x180051783  or      eax, 80070000h
0x180051788  jmp     loc_180051DD7
0x18005178d  add     [rbp+0B0h+cbMaxSubKeyLen], r12d
0x180051791  mov     edx, [rbp+0B0h+cbMaxValueNameLen]
0x180051794  add     edx, r12d; unsigned int
0x180051797  mov     [rbp+0B0h+cbMaxValueNameLen], edx
0x18005179a  mov     ecx, [rbp+0B0h+cbMaxValueLen]
0x18005179d  add     ecx, r12d
0x1800517a0  mov     [rbp+0B0h+cbMaxValueLen], ecx
0x1800517a3  mov     eax, [rbx+3Ch]
0x1800517a6  cmp     eax, ecx
0x1800517a8  cmovbe  eax, ecx
0x1800517ab  mov     [rbx+3Ch], eax
0x1800517ae  mov     r8d, [rbp+0B0h+cValues]; unsigned int
0x1800517b2  mov     rcx, rbx; this
0x1800517b5  call    ?ScanSourceValues@RegScan@@AEAAJKK@Z; RegScan::ScanSourceValues(ulong,ulong)
0x1800517ba  test    eax, eax
0x1800517bc  jnz     loc_180051DD7
0x1800517c2  mov     ecx, [rbp+0B0h+cSubKeys]
0x1800517c5  cmp     [rbx+8], ecx
0x1800517c8  jbe     short loc_18005180B
0x1800517ca  mov     dword ptr [rbp+0B0h+Name], r13d
0x1800517ce  mov     eax, 15h
0x1800517d3  mov     [rbp+0B0h+var_AC], ax
0x1800517d7  mov     [rbp+0B0h+var_A8], r14d
0x1800517db  lea     r9, aMCsubkeysCsubk; "m_cSubKeys <= cSubKeys"
0x1800517e2  mov     [rbp+0B0h+var_A0], r9
0x1800517e6  mov     [rbp+0B0h+var_98], r13
0x1800517ea  mov     [rbp+0B0h+var_90], r13
0x1800517ee  mov     [rbp+0B0h+var_84], r12d
0x1800517f2  mov     [rbp+0B0h+var_88], r12d
0x1800517f6  mov     r8d, 7D9h; unsigned int
0x1800517fc  mov     rdx, r15; unsigned __int16 *
0x1800517ff  lea     rcx, [rbp+0B0h+Name]; this
0x180051803  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051808  mov     ecx, [rbp+0B0h+cSubKeys]
0x18005180b  mov     rax, [rbx+60h]
0x18005180f  cmp     ecx, [rax+78h]
0x180051812  jb      short loc_18005181E
0x180051814  mov     eax, 80070004h
0x180051819  jmp     loc_180051DD7
0x18005181e  mov     r15d, [rbx+8]
0x180051822  mov     [rbp+0B0h+var_78], r15d
0x180051826  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005182a  cmp     ecx, r15d
0x18005182d  jbe     loc_1800518F0
0x180051833  lea     eax, [r8+9]
0x180051837  mul     rcx
0x18005183a  cmovb   rax, r8
0x18005183e  mov     rcx, rax; cb
0x180051841  call    cs:__imp_CoTaskMemAlloc
0x180051847  mov     r14, rax
0x18005184a  test    rax, rax
0x18005184d  jz      loc_180051DCE
0x180051853  mov     r8d, [rbp+0B0h+cSubKeys]
0x180051857  shl     r8, 3; Size
0x18005185b  xor     edx, edx; Val
0x18005185d  mov     rcx, rax; void *
0x180051860  call    memset_0
0x180051865  cmp     [rbx], r13
0x180051868  jz      short loc_1800518DD
0x18005186a  mov     esi, r13d
0x18005186d  cmp     [rbx+8], r13d
0x180051871  jbe     short loc_1800518DD
0x180051873  lea     r15, aApregscannewDw; "apRegScanNew[dwRS]"
0x18005187a  mov     edi, 15h
0x18005187f  mov     edx, esi
0x180051881  mov     rax, [rbx]
0x180051884  mov     rcx, [rax+rdx*8]
0x180051888  mov     [r14+rdx*8], rcx
0x18005188c  test    rcx, rcx
0x18005188f  jnz     short loc_1800518CD
0x180051891  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051895  mov     [rbp+0B0h+var_AC], di
0x180051899  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x1800518a0  mov     [rbp+0B0h+var_A0], r15
0x1800518a4  mov     [rbp+0B0h+var_98], r13
0x1800518a8  mov     [rbp+0B0h+var_90], r13
0x1800518ac  mov     [rbp+0B0h+var_84], r12d
0x1800518b0  mov     [rbp+0B0h+var_88], r12d
0x1800518b4  mov     r9, r15; unsigned __int16 *
0x1800518b7  mov     r8d, 7FDh; unsigned int
0x1800518bd  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800518c4  lea     rcx, [rbp+0B0h+Name]; this
0x1800518c8  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800518cd  add     esi, r12d
0x1800518d0  cmp     esi, [rbx+8]
0x1800518d3  jb      short loc_18005187F
0x1800518d5  lea     rdi, [rbx+28h]
0x1800518d9  mov     r15d, [rbp+0B0h+var_78]
0x1800518dd  mov     eax, [rbp+0B0h+cSubKeys]
0x1800518e0  mov     [rbx+8], eax
0x1800518e3  mov     rcx, [rbx]; pv
0x1800518e6  call    cs:__imp_CoTaskMemFree
0x1800518ec  nop
0x1800518ed  mov     [rbx], r14
0x1800518f0  cmp     [rbx], r13
0x1800518f3  jz      loc_180051985
0x1800518f9  mov     r14d, r13d
0x1800518fc  test    r15d, r15d
0x1800518ff  jz      loc_180051985
0x180051905  mov     rsi, r13
0x180051908  lea     rcx, aMApregscanDwrs; "m_apRegScan[dwRS]"
0x18005190f  mov     edi, 15h
0x180051914  mov     rax, [rbx]
0x180051917  cmp     [rax+rsi*8], r13
0x18005191b  jnz     short loc_180051959
0x18005191d  mov     dword ptr [rbp+0B0h+Name], r13d
0x180051921  mov     [rbp+0B0h+var_AC], di
0x180051925  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x18005192c  mov     [rbp+0B0h+var_A0], rcx
0x180051930  mov     [rbp+0B0h+var_98], r13
0x180051934  mov     [rbp+0B0h+var_90], r13
0x180051938  mov     [rbp+0B0h+var_84], r12d
0x18005193c  mov     [rbp+0B0h+var_88], r12d
0x180051940  mov     r9, rcx; unsigned __int16 *
0x180051943  mov     r8d, 80Eh; unsigned int
0x180051949  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051950  lea     rcx, [rbp+0B0h+Name]; this
0x180051954  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051959  mov     rax, [rbx]
0x18005195c  mov     rcx, [rax+rsi*8]
  ... truncated ...
```
