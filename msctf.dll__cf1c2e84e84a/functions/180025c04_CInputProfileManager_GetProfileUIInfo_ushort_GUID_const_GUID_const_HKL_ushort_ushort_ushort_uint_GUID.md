# CInputProfileManager::GetProfileUIInfo(ushort,_GUID const &,_GUID const &,HKL__ *,ushort * *,ushort * *,ushort * *,uint *,_GUID *)

- ea: `0x180025c04`
- end: `0x18002657a`
- name: `?GetProfileUIInfo@CInputProfileManager@@QEAAJGAEBU_GUID@@0PEAUHKL__@@PEAPEAG22PEAIPEAU2@@Z`
- size: `2422`
- prototype: `__int64 __usercall@<rax>(CInputProfileManager *__hidden this@<rcx>, unsigned __int16@<dx>, const struct _GUID *@<r8>, const struct _GUID *@<r9>, HKL, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025ba0`

## callees

- `0x18000fac0`
- `0x180011000`
- `0x1800139a4`
- `0x180020884`
- `0x180025c04`
- `0x180026580`
- `0x180026624`
- `0x180026684`
- `0x1800267c0`
- `0x1800690f0`
- `0x18008e6dc`
- `0x1800946fc`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800261bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026217`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026308`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025f3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800261bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026217`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026308`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026016`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026016`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002602d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002622d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002623b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002602d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002622d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002623b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025ff1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025ff1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800263b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800263b4`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002648e`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800264f3`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18002648e`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x1800264f3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025eda`
- `OLEAUT32!__imp_SysAllocString` at `0x1800260bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002626e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002642e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002645b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002656c`
- `OLEAUT32!__imp_SysAllocString` at `0x180025eda`
- `OLEAUT32!__imp_SysAllocString` at `0x1800260bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18002626e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002642e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002645b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002656c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026512`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026512`
- `IMM32!ImmGetIMEFileNameW` at `0x180026446`
- `IMM32!ImmGetIMEFileNameW` at `0x180026446`
- `Bcp47Langs!Bcp47FromCompactTagInternal` at `0x180026479`
- `Bcp47Langs!Bcp47FromCompactTagInternal` at `0x180026479`

## pseudocode

```c
__int64 __fastcall CInputProfileManager::GetProfileUIInfo(
        CInputProfileManager *this,
        unsigned __int16 a2,
        const struct _GUID *a3,
        struct _GUID *a4,
        HKL a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8,
        unsigned int *a9,
        struct _GUID *a10)
{
  HKEY v11; // rdi
  const struct _GUID *v12; // r12
  int v14; // r15d
  __int64 v15; // rax
  unsigned __int64 v16; // r8
  int j; // edx
  __int64 v18; // r9
  HKL v19; // r8
  int k; // r10d
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v24; // rax
  bool v25; // zf
  __int64 v26; // rbx
  LSTATUS v27; // eax
  void **v28; // r9
  int IndirectString; // ebx
  BYTE *v30; // r14
  BSTR v31; // rax
  HKEY v32; // rcx
  LSTATUS v33; // eax
  unsigned __int16 **v34; // rbx
  unsigned __int16 **v35; // r14
  LPBYTE v36; // rbx
  HSTRING v37; // rbx
  LSTATUS v38; // ebx
  unsigned __int16 **v39; // r15
  HKEY v40; // rbx
  unsigned __int16 **v41; // r15
  BYTE *v42; // r12
  LSTATUS Value; // edx
  BSTR v44; // rax
  __int64 v45; // rcx
  LSTATUS v46; // eax
  bool SessionProfile; // al
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned __int64 v50; // rax
  int v51; // eax
  int v52; // ebx
  PCWSTR StringRawBuffer; // rax
  int v54; // eax
  int v55; // ebx
  WCHAR *v56; // rcx
  unsigned int i; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData[2]; // [rsp+30h] [rbp-D0h] BYREF
  bool v61; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v63; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE lpData; // [rsp+50h] [rbp-B0h]
  void **v65; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v66; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v67; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v68; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v69; // [rsp+78h] [rbp-88h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v71[40]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v72[40]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int64 retaddr; // [rsp+388h] [rbp+288h]

  v11 = 0;
  v12 = a4;
  lpData = (LPBYTE)a9;
  v14 = a2;
  v65 = (void **)a4;
  v67 = a6;
  v69 = a7;
  v68 = a8;
  if ( a10 )
    *a10 = GUID_NULL;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  v61 = v15 == 0;
  cbData[0] = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
  {
    LODWORD(hKey) = 0;
    if ( a5 )
      SessionProfile = CInputProfileManager::_FindSessionProfile(this, (unsigned int)a5, (unsigned int *)&hKey);
    else
      SessionProfile = CInputProfileManager::_FindSessionProfile(this, v14, v16, a3, v12, (unsigned int *)&hKey);
    if ( !SessionProfile )
      return 2147500037LL;
    v48 = 88LL * (unsigned int)hKey;
    v49 = *((_QWORD *)this + 15);
    v26 = *(_QWORD *)(v48 + v49 + 8);
    LODWORD(v63) = *(_DWORD *)(v48 + v49 + 72);
    v12 = (const struct _GUID *)v65;
LABEL_34:
    v66 = 0;
    v65 = &CRegKeyMUI::`vftable';
    memset_0(SubKey, 0, 0x208u);
    if ( !v61 )
    {
      CLSIDToStringW(a3, v72);
      CLSIDToStringW(v12, v71);
      if ( v26 )
      {
        *(_QWORD *)cbData = 0;
        v51 = Bcp47FromCompactTagInternal(v26, cbData);
        v52 = v51;
        if ( v51 )
        {
          if ( v51 == -2147024882 )
            TerminateProcessOnMemoryExhaustion(0);
          FailFastWithHR(v52, retaddr, 0x648u);
        }
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)cbData, 0);
        v54 = StringCchPrintfW(
                SubKey,
                0x104u,
                L"Software\\Microsoft\\CTF\\TIP\\%s\\LanguageProfile\\%s\\%s",
                v72,
                StringRawBuffer,
                v71);
        v55 = v54;
        if ( v54 )
        {
          if ( v54 == -2147024882 )
            TerminateProcessOnMemoryExhaustion(0);
          FailFastWithHR(v55, retaddr, 0x64Fu);
        }
        WindowsDeleteString(*(HSTRING *)cbData);
      }
      else
      {
        LODWORD(phkResult) = v14;
        StringCchPrintfW(
          SubKey,
          0x104u,
          L"Software\\Microsoft\\CTF\\TIP\\%s\\LanguageProfile\\0x0000%04x\\%s",
          v72,
          phkResult,
          v71);
      }
      hKey = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        return 2147500037LL;
      v39 = v67;
      v40 = hKey;
      if ( !v67
        || (unsigned int)LoadRegUIStringW(hKey, L"Display Description", SubKey, 0x104u)
        && (cbData[0] = 520,
            LODWORD(v63) = 0,
            v46 = RegQueryValueExW(v40, L"Description", 0, (LPDWORD)&v63, (LPBYTE)SubKey, cbData),
            *(WCHAR *)((char *)SubKey + (-(__int64)(v46 == 0) & 0x206)) = 0,
            v46)
        || (v44 = SysAllocString(SubKey), (*v39 = v44) != 0) )
      {
        v41 = v68;
        if ( v68 )
        {
          v42 = lpData;
          if ( lpData )
          {
            cbData[0] = 520;
            LODWORD(v63) = 0;
            Value = RegQueryValueExW(v40, L"IconFile", 0, (LPDWORD)&v63, (LPBYTE)SubKey, cbData);
            *(WCHAR *)((char *)SubKey + (-(__int64)(Value == 0) & 0x206)) = 0;
            if ( !Value )
            {
              if ( SubKey[0] == 64 )
              {
                v56 = SubKey;
                for ( i = 0; i < 0x104 && *v56; ++i )
                {
                  if ( *v56 == 44 )
                  {
                    Value = LoadRegUIStringW(v40, L"IconFile", SubKey, 0x104u);
                    break;
                  }
                  ++v56;
                }
              }
              if ( !Value )
              {
                LODWORD(v63) = 0;
                cbData[0] = 4;
                if ( !RegQueryValueExW(v40, L"IconIndex", 0, (LPDWORD)&v63, v42, cbData) )
                  *v41 = SysAllocString(SubKey);
              }
            }
          }
        }
        if ( !v40 )
          return 0;
        RegCloseKey(v40);
LABEL_82:
        if ( v11 )
          RegCloseKey(v11);
        return 0;
      }
      if ( v40 )
      {
        v32 = v40;
        goto LABEL_48;
      }
      return 2147942414LL;
    }
    if ( !a6 )
    {
LABEL_54:
      v35 = v68;
      if ( v68 )
      {
        v36 = lpData;
        if ( lpData )
        {
          if ( ((unsigned int)a5 & 0xF0000000) == 0xE0000000 )
          {
            if ( ImmGetIMEFileNameW(a5, SubKey, 0x104u) )
            {
              *v35 = SysAllocString(SubKey);
              *(_DWORD *)v36 = 0;
            }
          }
          else
          {
            LODWORD(lpcbData) = (_DWORD)v63;
            LODWORD(phkResult) = v14;
            StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%04x\\%08x",
              L"Software\\Microsoft\\CTF\\LayoutIcon",
              phkResult,
              lpcbData);
            v63 = 0;
            *(_QWORD *)cbData = 0;
            v37 = (HSTRING)-2147483647LL;
            if ( !RegOpenCurrentUser(0x20019u, (PHKEY)cbData) )
              v37 = *(HSTRING *)cbData;
            v38 = RegOpenKeyExW((HKEY)v37, SubKey, 0, 0x20019u, &v63);
            if ( !v38 )
            {
              v38 = 0;
              if ( v11 )
                v38 = RegCloseKey(v11);
              v11 = v63;
              v66 = v63;
            }
            if ( *(_QWORD *)cbData )
              RegCloseKey(*(HKEY *)cbData);
            if ( !v38 && !CRegKeyMUI::QueryValueCch((CRegKeyMUI *)&v65, SubKey, L"IconFile", 0x104u) )
            {
              LODWORD(v63) = 0;
              cbData[0] = 4;
              if ( !RegQueryValueExW(v11, L"IconIndex", 0, (LPDWORD)&v63, lpData, cbData) )
                *v35 = SysAllocString(SubKey);
            }
          }
        }
      }
      goto LABEL_82;
    }
    LODWORD(phkResult) = (_DWORD)v63;
    StringCchPrintfW(SubKey, 0x104u, L"%s\\%08x", L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts", phkResult);
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
      return 2147500037LL;
    v11 = hKey;
    SubKey[0] = 0;
    v66 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_51;
    LODWORD(hKey) = 520;
    v27 = RegQueryValueExW(v11, L"Layout Display Name", 0, 0, (LPBYTE)SubKey, (LPDWORD)&hKey);
    if ( v27 )
    {
      if ( v27 != 234 )
        goto LABEL_51;
    }
    IndirectString = -2147467259;
    if ( v27 == 234 )
    {
      v50 = 2 * ((unsigned __int64)(unsigned int)((_DWORD)hKey + 1) >> 1);
      if ( !is_mul_ok((unsigned __int64)(unsigned int)((_DWORD)hKey + 1) >> 1, 2u) )
        LODWORD(v50) = -1;
      v30 = (BYTE *)LocalAlloc(0x40u, (unsigned int)v50);
      if ( !v30 )
      {
LABEL_51:
        cbData[0] = 520;
        LODWORD(hKey) = 0;
        v33 = RegQueryValueExW(v11, L"layout text", 0, (LPDWORD)&hKey, (LPBYTE)SubKey, cbData);
        *(WCHAR *)((char *)SubKey + (-(__int64)(v33 == 0) & 0x206)) = 0;
        if ( v33 )
          goto LABEL_52;
LABEL_45:
        v31 = SysAllocString(SubKey);
        *v67 = v31;
        if ( v31 )
        {
LABEL_52:
          v34 = v69;
          if ( v69
            && (_WORD)v14 == 3072
            && !(unsigned int)CRegKeyMUI::QueryMUIValue(
                                (CRegKeyMUI *)&v65,
                                SubKey,
                                L"Custom Language Name",
                                L"Custom Language Display Name",
                                (unsigned int)phkResult) )
          {
            *v34 = SysAllocString(SubKey);
          }
          goto LABEL_54;
        }
        if ( v11 )
        {
          v32 = v11;
LABEL_48:
          RegCloseKey(v32);
          return 2147942414LL;
        }
        return 2147942414LL;
      }
      v27 = RegQueryValueExW(v11, L"Layout Display Name", 0, 0, v30, (LPDWORD)&hKey);
    }
    else
    {
      v30 = (BYTE *)SubKey;
      cbData[0] = 0;
    }
    if ( !v27 )
      IndirectString = LoadIndirectString((const unsigned __int16 *)v30, SubKey, 0x104u, v28);
    if ( cbData[0] && v30 )
      cicMemFree(v30);
    if ( !IndirectString )
      goto LABEL_45;
    goto LABEL_51;
  }
  if ( !(_WORD)v14 || (_WORD)v14 == (v14 & 0x3FF) )
  {
    v18 = *((_QWORD *)this + 5);
    if ( !v18 )
      return 2147500037LL;
  }
  else
  {
    for ( j = 0; ; ++j )
    {
      if ( j >= *((_DWORD *)this + 6) )
        return 2147500037LL;
      v18 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * j);
      if ( *(_WORD *)v18 == (_WORD)v14 )
        break;
    }
  }
  v19 = a5;
  if ( a5 )
  {
    v45 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a3->Data1 )
      v45 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a3->Data4;
    if ( v45 )
      v19 = 0;
  }
  for ( k = 0; k < *(_DWORD *)(v18 + 40); ++k )
  {
    v21 = *(_QWORD *)(v18 + 32) + *(_DWORD *)(v18 + 44) * k;
    if ( v19 )
    {
      v25 = *(int *)(v21 + 56) == (_QWORD)v19;
    }
    else
    {
      v22 = *(_QWORD *)(v21 + 8) - *(_QWORD *)&a3->Data1;
      if ( !v22 )
        v22 = *(_QWORD *)(v21 + 16) - *(_QWORD *)a3->Data4;
      if ( v22 )
        continue;
      v24 = *(_QWORD *)(v21 + 40) - *(_QWORD *)&v12->Data1;
      if ( !v24 )
        v24 = *(_QWORD *)(v21 + 48) - *(_QWORD *)v12->Data4;
      v25 = v24 == 0;
    }
    if ( v25 )
      goto LABEL_32;
  }
  v21 = 0;
LABEL_32:
  if ( v21 )
  {
    v26 = 0;
    LODWORD(v63) = *(_DWORD *)(v21 + 4);
    goto LABEL_34;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180025c04  push    rbp
0x180025c06  push    rbx
0x180025c07  push    rsi
0x180025c08  push    rdi
0x180025c09  push    r12
0x180025c0b  push    r13
0x180025c0d  push    r14
0x180025c0f  push    r15
0x180025c11  lea     rbp, [rsp-248h]
0x180025c19  sub     rsp, 348h
0x180025c20  mov     rax, cs:__security_cookie
0x180025c27  xor     rax, rsp
0x180025c2a  mov     [rbp+280h+var_50], rax
0x180025c31  mov     rax, [rbp+280h+arg_40]
0x180025c38  mov     rbx, rcx
0x180025c3b  mov     r14, [rbp+280h+arg_28]
0x180025c42  xor     edi, edi
0x180025c44  mov     rcx, [rbp+280h+arg_38]
0x180025c4b  mov     r12, r9
0x180025c4e  mov     r13, [rbp+280h+arg_20]
0x180025c55  mov     rsi, r8
0x180025c58  mov     [rsp+380h+lpData], rax
0x180025c5d  mov     rax, [rbp+280h+arg_48]
0x180025c64  movzx   r15d, dx
0x180025c68  mov     rdx, [rbp+280h+arg_30]
0x180025c6f  mov     [rsp+380h+var_328], r9
0x180025c74  mov     [rsp+380h+var_318], r14
0x180025c79  mov     [rsp+380h+var_308], rdx
0x180025c7e  mov     [rsp+380h+var_310], rcx
0x180025c83  test    rax, rax
0x180025c86  jz      short loc_180025C93
0x180025c88  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180025c8f  movdqu  xmmword ptr [rax], xmm0
0x180025c93  test    r14, r14
0x180025c96  jz      short loc_180025C9B
0x180025c98  mov     [r14], rdi
0x180025c9b  test    rdx, rdx
0x180025c9e  jz      short loc_180025CA3
0x180025ca0  mov     [rdx], rdi
0x180025ca3  test    rcx, rcx
0x180025ca6  jz      short loc_180025CAB
0x180025ca8  mov     [rcx], rdi
0x180025cab  mov     rax, [r8]
0x180025cae  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180025cb5  jnz     short loc_180025CC2
0x180025cb7  mov     rax, [r8+8]
0x180025cbb  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180025cc2  test    rax, rax
0x180025cc5  setz    [rsp+380h+var_348]
0x180025cca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x180025cd1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x180025cd6  mov     r11d, 1
0x180025cdc  mov     [rsp+380h+cbData], r11d
0x180025ce1  test    al, al
0x180025ce3  jnz     loc_18002632E
0x180025ce9  test    r15w, r15w
0x180025ced  jz      short loc_180025D1E
0x180025cef  movzx   eax, r15w
0x180025cf3  mov     ecx, 3FFh
0x180025cf8  and     ax, cx
0x180025cfb  cmp     r15w, ax
0x180025cff  jz      short loc_180025D1E
0x180025d01  mov     edx, edi
0x180025d03  cmp     edx, [rbx+18h]
0x180025d06  jge     short loc_180025D73
0x180025d08  mov     rax, [rbx+10h]
0x180025d0c  movsxd  rcx, edx
0x180025d0f  mov     r9, [rax+rcx*8]
0x180025d13  cmp     [r9], r15w
0x180025d17  jz      short loc_180025D27
0x180025d19  add     edx, r11d
0x180025d1c  jmp     short loc_180025D03
0x180025d1e  mov     r9, [rbx+28h]
0x180025d22  test    r9, r9
0x180025d25  jz      short loc_180025D73
0x180025d27  mov     r8, r13
0x180025d2a  test    r13, r13
0x180025d2d  jnz     loc_180026291
0x180025d33  mov     r10d, edi
0x180025d36  cmp     r10d, [r9+28h]
0x180025d3a  jge     loc_180026248
0x180025d40  mov     eax, r10d
0x180025d43  imul    eax, [r9+2Ch]
0x180025d48  movsxd  rdx, eax
0x180025d4b  add     rdx, [r9+20h]
0x180025d4f  test    r8, r8
0x180025d52  jnz     loc_1800262CA
0x180025d58  mov     rax, [rdx+8]
0x180025d5c  sub     rax, [rsi]
0x180025d5f  jnz     short loc_180025D69
0x180025d61  mov     rax, [rdx+10h]
0x180025d65  sub     rax, [rsi+8]
0x180025d69  test    rax, rax
0x180025d6c  jz      short loc_180025D9B
0x180025d6e  add     r10d, r11d
0x180025d71  jmp     short loc_180025D36
0x180025d73  mov     eax, 80004005h
0x180025d78  mov     rcx, [rbp+280h+var_50]
0x180025d7f  xor     rcx, rsp; StackCookie
0x180025d82  call    __security_check_cookie
0x180025d87  add     rsp, 348h
0x180025d8e  pop     r15
0x180025d90  pop     r14
0x180025d92  pop     r13
0x180025d94  pop     r12
0x180025d96  pop     rdi
0x180025d97  pop     rsi
0x180025d98  pop     rbx
0x180025d99  pop     rbp
0x180025d9a  retn
0x180025d9b  mov     rax, [rdx+28h]
0x180025d9f  sub     rax, [r12]
0x180025da3  jnz     short loc_180025DAE
0x180025da5  mov     rax, [rdx+30h]
0x180025da9  sub     rax, [r12+8]
0x180025dae  test    rax, rax
0x180025db1  jnz     short loc_180025D6E
0x180025db3  test    rdx, rdx
0x180025db6  jz      short loc_180025D73
0x180025db8  mov     eax, [rdx+4]
0x180025dbb  mov     rbx, rdi
0x180025dbe  mov     dword ptr [rsp+380h+var_338], eax
0x180025dc2  lea     rax, ??_7CRegKeyMUI@@6B@; const CRegKeyMUI::`vftable'
0x180025dc9  mov     [rsp+380h+var_320], rdi
0x180025dce  xor     edx, edx; Val
0x180025dd0  mov     [rsp+380h+var_328], rax
0x180025dd5  mov     r8d, 208h; Size
0x180025ddb  lea     rcx, [rbp+280h+SubKey]; void *
0x180025ddf  call    memset_0
0x180025de4  cmp     [rsp+380h+var_348], dil
0x180025de9  jz      loc_1800260CA
0x180025def  mov     esi, 104h
0x180025df4  mov     r12d, 20019h
0x180025dfa  test    r14, r14
0x180025dfd  jz      loc_180025F7F
0x180025e03  mov     eax, dword ptr [rsp+380h+var_338]
0x180025e07  lea     r9, ?c_szLayoutPath@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Key"...
0x180025e0e  lea     r8, aS08x; "%s\\%08x"
0x180025e15  mov     dword ptr [rsp+380h+phkResult], eax
0x180025e19  mov     edx, esi; unsigned __int64
0x180025e1b  lea     rcx, [rbp+280h+SubKey]; unsigned __int16 *
0x180025e1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025e24  lea     rax, [rsp+380h+hKey]
0x180025e29  mov     [rsp+380h+hKey], rdi
0x180025e2e  mov     r9d, r12d; samDesired
0x180025e31  mov     [rsp+380h+phkResult], rax; phkResult
0x180025e36  xor     r8d, r8d; ulOptions
0x180025e39  lea     rdx, [rbp+280h+SubKey]; lpSubKey
0x180025e3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025e44  call    cs:__imp_RegOpenKeyExW
0x180025e4a  test    eax, eax
0x180025e4c  jnz     loc_180025D73
0x180025e52  mov     rdi, [rsp+380h+hKey]
0x180025e57  mov     [rbp+280h+SubKey], ax
0x180025e5b  mov     [rsp+380h+var_320], rdi
0x180025e60  lea     rax, [rdi-1]
0x180025e64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025e68  ja      loc_180025F09
0x180025e6e  lea     rax, [rsp+380h+hKey]
0x180025e73  mov     dword ptr [rsp+380h+hKey], 208h
0x180025e7b  mov     [rsp+380h+lpcbData], rax; lpcbData
0x180025e80  lea     rdx, ?c_szMUILayoutText@@3QBGB; "Layout Display Name"
0x180025e87  lea     rax, [rbp+280h+SubKey]
0x180025e8b  xor     r9d, r9d; lpType
0x180025e8e  xor     r8d, r8d; lpReserved
0x180025e91  mov     [rsp+380h+phkResult], rax; lpData
0x180025e96  mov     rcx, rdi; hKey
0x180025e99  call    cs:__imp_RegQueryValueExW
0x180025e9f  lea     ecx, [rsi-1Ah]
0x180025ea2  test    eax, eax
0x180025ea4  jnz     short loc_180025F05
0x180025ea6  mov     ebx, 80004005h
0x180025eab  cmp     eax, ecx
0x180025ead  jz      loc_180026391
0x180025eb3  lea     r14, [rbp+280h+SubKey]
0x180025eb7  mov     [rsp+380h+cbData], 0
0x180025ebf  test    eax, eax
0x180025ec1  jz      loc_1800262B4
0x180025ec7  cmp     [rsp+380h+cbData], 0
0x180025ecc  jnz     loc_1800263F0
0x180025ed2  test    ebx, ebx
0x180025ed4  jnz     short loc_180025F09
0x180025ed6  lea     rcx, [rbp+280h+SubKey]; psz
0x180025eda  call    cs:__imp_SysAllocString
0x180025ee0  mov     rcx, [rsp+380h+var_318]
0x180025ee5  mov     [rcx], rax
0x180025ee8  test    rax, rax
0x180025eeb  jnz     short loc_180025F66
0x180025eed  test    rdi, rdi
0x180025ef0  jz      short loc_180025EFB
0x180025ef2  mov     rcx, rdi; hKey
0x180025ef5  call    cs:__imp_RegCloseKey
0x180025efb  mov     eax, 8007000Eh
0x180025f00  jmp     loc_180025D78
0x180025f05  cmp     eax, ecx
0x180025f07  jz      short loc_180025EA6
0x180025f09  lea     rax, [rsp+380h+cbData]
0x180025f0e  mov     [rsp+380h+cbData], 208h
0x180025f16  mov     [rsp+380h+lpcbData], rax; lpcbData
0x180025f1b  lea     r9, [rsp+380h+hKey]; lpType
0x180025f20  lea     rax, [rbp+280h+SubKey]
0x180025f24  mov     dword ptr [rsp+380h+hKey], 0
0x180025f2c  xor     r8d, r8d; lpReserved
0x180025f2f  mov     [rsp+380h+phkResult], rax; unsigned int
0x180025f34  lea     rdx, ?c_szLayoutText@@3QBGB; "layout text"
0x180025f3b  mov     rcx, rdi; hKey
0x180025f3e  call    cs:__imp_RegQueryValueExW
0x180025f44  mov     ecx, eax
0x180025f46  mov     r14d, 206h
0x180025f4c  neg     ecx
0x180025f4e  sbb     rdx, rdx
0x180025f51  xor     ecx, ecx
0x180025f53  not     rdx
0x180025f56  and     rdx, r14
0x180025f59  mov     [rbp+rdx+280h+SubKey], cx
0x180025f5e  test    eax, eax
0x180025f60  jz      loc_180025ED6
0x180025f66  mov     rbx, [rsp+380h+var_308]
0x180025f6b  test    rbx, rbx
0x180025f6e  jz      short loc_180025F7F
0x180025f70  mov     eax, 0C00h
0x180025f75  cmp     r15w, ax
0x180025f79  jz      loc_180026406
0x180025f7f  mov     r14, [rsp+380h+var_310]
0x180025f84  test    r14, r14
0x180025f87  jz      loc_180026233
0x180025f8d  mov     rbx, [rsp+380h+lpData]
0x180025f92  test    rbx, rbx
0x180025f95  jz      loc_180026233
0x180025f9b  mov     eax, r13d
0x180025f9e  and     eax, 0F0000000h
0x180025fa3  cmp     eax, 0E0000000h
0x180025fa8  jz      loc_18002643C
0x180025fae  mov     ecx, dword ptr [rsp+380h+var_338]
0x180025fb2  lea     r9, ?c_szCtfLayoutIcon@@3QBGB; "Software\\Microsoft\\CTF\\LayoutIcon"
0x180025fb9  mov     dword ptr [rsp+380h+lpcbData], ecx
0x180025fbd  lea     r8, aS04x08x; "%s\\%04x\\%08x"
0x180025fc4  lea     rcx, [rbp+280h+SubKey]; unsigned __int16 *
0x180025fc8  mov     dword ptr [rsp+380h+phkResult], r15d
0x180025fcd  mov     rdx, rsi; unsigned __int64
0x180025fd0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025fd5  xor     r13d, r13d
0x180025fd8  lea     rdx, [rsp+380h+cbData]; phkResult
0x180025fdd  mov     ecx, r12d; samDesired
0x180025fe0  mov     [rsp+380h+var_338], r13
0x180025fe5  mov     qword ptr [rsp+380h+cbData], r13
0x180025fea  mov     rbx, 0FFFFFFFF80000001h
0x180025ff1  call    cs:__imp_RegOpenCurrentUser
0x180025ff7  mov     r9d, r12d; samDesired
0x180025ffa  lea     rdx, [rbp+280h+SubKey]; lpSubKey
0x180025ffe  test    eax, eax
0x180026000  lea     rax, [rsp+380h+var_338]
0x180026005  mov     [rsp+380h+phkResult], rax; phkResult
0x18002600a  cmovz   rbx, qword ptr [rsp+380h+cbData]
0x180026010  xor     r8d, r8d; ulOptions
0x180026013  mov     rcx, rbx; hKey
0x180026016  call    cs:__imp_RegOpenKeyExW
0x18002601c  mov     ebx, eax
0x18002601e  test    eax, eax
0x180026020  jnz     short loc_18002603F
0x180026022  mov     ebx, r13d
0x180026025  test    rdi, rdi
0x180026028  jz      short loc_180026035
0x18002602a  mov     rcx, rdi; hKey
0x18002602d  call    cs:__imp_RegCloseKey
0x180026033  mov     ebx, eax
0x180026035  mov     rdi, [rsp+380h+var_338]
0x18002603a  mov     [rsp+380h+var_320], rdi
0x18002603f  mov     rcx, qword ptr [rsp+380h+cbData]; hKey
0x180026044  test    rcx, rcx
0x180026047  jz      short loc_18002604F
0x180026049  call    cs:__imp_RegCloseKey
0x18002604f  test    ebx, ebx
0x180026051  jnz     loc_180026233
0x180026057  mov     r9d, esi; unsigned int
0x18002605a  lea     r8, ?c_szIconFile@@3QBGB; "IconFile"
0x180026061  lea     rdx, [rbp+280h+SubKey]; unsigned __int16 *
0x180026065  lea     rcx, [rsp+380h+var_328]; this
0x18002606a  call    ?QueryValueCch@CRegKeyMUI@@UEAAJPEAGPEBGK@Z; CRegKeyMUI::QueryValueCch(ushort *,ushort const *,ulong)
0x18002606f  test    eax, eax
0x180026071  jnz     loc_180026233
0x180026077  mov     r12, [rsp+380h+lpData]
0x18002607c  lea     rax, [rsp+380h+cbData]
0x180026081  mov     [rsp+380h+lpcbData], rax; lpcbData
0x180026086  lea     r9, [rsp+380h+var_338]; lpType
0x18002608b  xor     r8d, r8d; lpReserved
0x18002608e  mov     [rsp+380h+phkResult], r12; lpData
0x180026093  lea     rdx, ?c_szIconIndex@@3QBGB; "IconIndex"
0x18002609a  mov     dword ptr [rsp+380h+var_338], r13d
0x18002609f  mov     rcx, rdi; hKey
0x1800260a2  mov     [rsp+380h+cbData], 4
0x1800260aa  call    cs:__imp_RegQueryValueExW
0x1800260b0  test    eax, eax
0x1800260b2  jnz     loc_180026233
0x1800260b8  lea     rcx, [rbp+280h+SubKey]; psz
0x1800260bc  call    cs:__imp_SysAllocString
0x1800260c2  mov     [r14], rax
0x1800260c5  jmp     loc_180026233
0x1800260ca  lea     rdx, [rbp+280h+var_A0]; unsigned __int16 *
0x1800260d1  mov     rcx, rsi; struct _GUID *
  ... truncated ...
```
