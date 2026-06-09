# CCertTypeInfo::_BaseUpdateToReg(HKEY__ *)

- ea: `0x180003be0`
- end: `0x180004b8d`
- name: `?_BaseUpdateToReg@CCertTypeInfo@@IEAAJPEAUHKEY__@@@Z`
- size: `4013`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this, HKEY hKey)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800056f0`
- `0x180031a2c`

## callees

- `0x180002ef0`
- `0x180003be0`
- `0x180004ba0`
- `0x180004c30`
- `0x180005944`
- `0x180008610`
- `0x18000a3b0`
- `0x18000ce90`
- `0x180013a86`
- `0x180038286`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004174`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003cdd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000431d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004353`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004386`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000448e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004631`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003cdd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800042ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000431d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004353`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004386`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800043f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000448e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004631`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003c52`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003c52`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000445c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000445c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180004447`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180004447`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003de1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003fd1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800041c1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003de1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003fd1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800041c1`

## string_xrefs

- `0x180004b43`: `msPKI-Template-Schema-Version`
- `0x1800044cd`: `msPKI-Template-Minor-Revision`
- `0x180004100`: `pKICriticalExtensions`
- `0x1800041a5`: `pKICriticalExtensions`
- `0x1800043bc`: `PathLen`
- `0x18000446e`: `Security`
- `0x180004287`: `CriticalExtensions`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_BaseUpdateToReg(CCertTypeInfo *this, HKEY hKey)
{
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  unsigned int Property; // esi
  const BYTE *lpData; // rcx
  __int64 v8; // rax
  bool v9; // zf
  unsigned __int64 v10; // rax
  LSTATUS v11; // eax
  struct CCAProperty *v12; // rbx
  const WCHAR *v13; // rax
  CCAProperty *v14; // rcx
  HKEY v15; // r14
  const void **v16; // rax
  _WORD *v17; // rcx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rdi
  __int64 v21; // rsi
  _DWORD *v22; // rax
  BYTE *v23; // rdi
  __int64 v24; // rdx
  const void **v25; // rbx
  _WORD *v26; // rsi
  _WORD *i; // rax
  __int64 v28; // r8
  __int64 v29; // rax
  LSTATUS v30; // eax
  struct CCAProperty *v31; // rbx
  const WCHAR *v32; // rax
  CCAProperty *v33; // rcx
  HKEY v34; // r14
  const void **v35; // rax
  _WORD *v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rdi
  __int64 v40; // rsi
  _DWORD *v41; // rax
  BYTE *v42; // rdi
  __int64 v43; // rdx
  const void **v44; // rbx
  _WORD *v45; // rsi
  _WORD *j; // rax
  __int64 v47; // r8
  __int64 v48; // rax
  LSTATUS v49; // eax
  struct CCAProperty *v50; // rbx
  const WCHAR *v51; // rax
  CCAProperty *v52; // rcx
  HKEY v53; // r14
  const void **v54; // rax
  _WORD *v55; // rcx
  __int64 v56; // r8
  unsigned int v57; // eax
  __int64 v58; // rdi
  __int64 v59; // rsi
  _DWORD *v60; // rax
  BYTE *v61; // rdi
  __int64 v62; // rdx
  const void **v63; // rbx
  _WORD *v64; // rsi
  _WORD *k; // rax
  __int64 v66; // r8
  __int64 v67; // rax
  LSTATUS v68; // eax
  LSTATUS v69; // eax
  bool v70; // cc
  void *v71; // rcx
  DWORD SecurityDescriptorLength; // eax
  unsigned int m; // r12d
  struct _CERT_TYPE_PROP_INFO near **v74; // rbx
  const wchar_t *v75; // rbx
  __int64 n; // rcx
  int v77; // edx
  __int64 v78; // rax
  int v79; // edx
  __int64 ii; // rcx
  int v81; // edx
  __int64 v82; // rcx
  int v83; // edx
  __int64 jj; // rcx
  int v85; // edx
  int v86; // eax
  HKEY v88; // r15
  const WCHAR *v89; // r14
  struct CCAProperty *v90; // rbx
  const char **v91; // rax
  const char *v92; // rcx
  __int64 kk; // r8
  unsigned int v94; // edx
  unsigned __int16 *v95; // rax
  BYTE *v96; // rdi
  const void **v97; // rbx
  unsigned __int16 *v98; // rsi
  _WORD *mm; // rax
  __int64 v100; // r8
  __int64 v101; // rax
  LSTATUS v102; // eax
  __int64 v103; // rdx
  unsigned int v104; // edx
  unsigned int v105; // edx
  unsigned int v106; // edx
  HKEY hKeya; // [rsp+58h] [rbp+17h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+1Fh] BYREF
  int Data; // [rsp+A8h] [rbp+67h] BYREF
  DWORD v110; // [rsp+B8h] [rbp+77h] BYREF
  struct CCAProperty *v111; // [rsp+C0h] [rbp+7Fh] BYREF

  v111 = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 1);
  Data = 0;
  hMem = 0;
  hKeya = 0;
  v110 = 0;
  v5 = RegCreateKeyExW(hKey, v4, 0, (LPWSTR)&Class, 0, 0xF003Fu, 0, &hKeya, &v110);
  Property = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      Property = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_154;
  }
  Property = CCertTypeInfo::GetProperty(this, L"dsDisplayName", (unsigned __int16 ***)&hMem);
  if ( Property )
    goto LABEL_154;
  if ( !hMem || (lpData = *(const BYTE **)hMem) == 0 )
    lpData = (const BYTE *)&Class;
  v8 = -1;
  do
    v9 = *(_WORD *)&lpData[2 * v8++ + 2] == 0;
  while ( !v9 );
  v10 = 2 * v8 + 2;
  if ( v10 > 0x10000 )
  {
    Property = -2147024362;
    CSPrintErrorLineFileData2(0, 0xD3A0328u, -2147024362, 0);
    goto LABEL_154;
  }
  v11 = RegSetValueExW(hKeya, L"DisplayName", 0, 1u, lpData, v10);
  Property = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      Property = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_154;
  }
  v12 = (struct CCAProperty *)*((_QWORD *)this + 12);
  if ( !v12 )
    goto LABEL_225;
  v13 = (const WCHAR *)*((_QWORD *)v12 + 1);
  if ( v13 && CompareStringW(0x7Fu, 1u, L"pKIDefaultCSPs", -1, v13, -1) == 2 )
  {
    v111 = v12;
  }
  else
  {
    v14 = (CCAProperty *)*((_QWORD *)v12 + 2);
    if ( !v14 )
      goto LABEL_240;
    Property = CCAProperty::Find(v14, L"pKIDefaultCSPs", &v111);
    if ( Property )
      goto LABEL_154;
    v12 = v111;
  }
  v15 = hKeya;
  if ( !hKeya )
  {
LABEL_225:
    Property = -2147467261;
    goto LABEL_154;
  }
  v16 = *(const void ***)v12;
  if ( !*(_QWORD *)v12 )
  {
    v23 = (BYTE *)CertAllocString(&Class);
    if ( !v23 )
    {
      Property = -2147024882;
      goto LABEL_40;
    }
    goto LABEL_36;
  }
  v17 = *v16;
  v18 = 0;
  if ( *v16 )
  {
    do
    {
      v24 = -1;
      do
        ++v24;
      while ( v17[v24] );
      v17 = v16[1];
      ++v16;
      v18 += v24 + 1;
    }
    while ( v17 );
  }
  v19 = v18 + 1;
  if ( (unsigned __int64)(v18 + 1) > 0x10000 )
  {
    Property = -2147024362;
    CSPrintErrorLineFileData2(0, 0x3850326u, -2147024362, 0);
    goto LABEL_40;
  }
  if ( v19 > 0x30D4000 )
  {
    v104 = 64488230;
LABEL_192:
    CSPrintErrorLineFileData2(0, v104, -2147024362, 0);
LABEL_22:
    Property = -2147024882;
    goto LABEL_40;
  }
  v20 = 2 * v19;
  if ( (unsigned int)v20 > 0x61A8000 )
  {
    v104 = 66061094;
    goto LABEL_192;
  }
  v21 = (unsigned int)v20;
  v22 = LocalAlloc(0, v20 + 6);
  if ( !v22 )
    goto LABEL_22;
  *v22 = v20;
  v23 = (BYTE *)(v22 + 1);
  *(_WORD *)((char *)v22 + v21 + 4) = 0;
  if ( v22 == (_DWORD *)-4LL )
    goto LABEL_22;
  v25 = *(const void ***)v12;
  v26 = v22 + 1;
  for ( i = *v25; *v25; i = *v25 )
  {
    v28 = -1;
    do
      v9 = i[++v28] == 0;
    while ( !v9 );
    memcpy_0(v26, i, 2 * v28 + 2);
    v29 = -1;
    do
      v9 = *((_WORD *)*v25 + ++v29) == 0;
    while ( !v9 );
    ++v25;
    v26 += v29 + 1;
  }
  *v26 = 0;
LABEL_36:
  Property = 0;
  v30 = RegSetValueExW(v15, L"SupportedCSPs", 0, 7u, v23, *((_DWORD *)v23 - 1));
  if ( v30 )
    Property = myHError(v30);
  if ( v23 )
    CertFreeString((unsigned __int16 *)v23);
LABEL_40:
  if ( Property )
    goto LABEL_154;
  v31 = (struct CCAProperty *)*((_QWORD *)this + 12);
  if ( !v31 )
  {
    Property = -2147467261;
    goto LABEL_154;
  }
  v32 = (const WCHAR *)*((_QWORD *)v31 + 1);
  if ( v32 && CompareStringW(0x7Fu, 1u, L"pKIExtendedKeyUsage", -1, v32, -1) == 2 )
  {
    v111 = v31;
  }
  else
  {
    v33 = (CCAProperty *)*((_QWORD *)v31 + 2);
    if ( !v33 )
      goto LABEL_240;
    Property = CCAProperty::Find(v33, L"pKIExtendedKeyUsage", &v111);
    if ( Property )
      goto LABEL_154;
    v31 = v111;
  }
  v34 = hKeya;
  if ( !hKeya )
    goto LABEL_225;
  v35 = *(const void ***)v31;
  if ( !*(_QWORD *)v31 )
  {
    v42 = (BYTE *)CertAllocString(&Class);
    if ( !v42 )
    {
      Property = -2147024882;
      goto LABEL_72;
    }
    goto LABEL_68;
  }
  v36 = *v35;
  v37 = 0;
  if ( *v35 )
  {
    do
    {
      v43 = -1;
      do
        ++v43;
      while ( v36[v43] );
      v36 = v35[1];
      ++v35;
      v37 += v43 + 1;
    }
    while ( v36 );
  }
  v38 = v37 + 1;
  if ( (unsigned __int64)(v37 + 1) > 0x10000 )
  {
    Property = -2147024362;
    CSPrintErrorLineFileData2(0, 0x3850326u, -2147024362, 0);
    goto LABEL_72;
  }
  if ( v38 > 0x30D4000 )
  {
    v105 = 64488230;
LABEL_194:
    CSPrintErrorLineFileData2(0, v105, -2147024362, 0);
LABEL_54:
    Property = -2147024882;
    goto LABEL_72;
  }
  v39 = 2 * v38;
  if ( (unsigned int)v39 > 0x61A8000 )
  {
    v105 = 66061094;
    goto LABEL_194;
  }
  v40 = (unsigned int)v39;
  v41 = LocalAlloc(0, v39 + 6);
  if ( !v41 )
    goto LABEL_54;
  *v41 = v39;
  v42 = (BYTE *)(v41 + 1);
  *(_WORD *)((char *)v41 + v40 + 4) = 0;
  if ( v41 == (_DWORD *)-4LL )
    goto LABEL_54;
  v44 = *(const void ***)v31;
  v45 = v41 + 1;
  for ( j = *v44; *v44; j = *v44 )
  {
    v47 = -1;
    do
      v9 = j[++v47] == 0;
    while ( !v9 );
    memcpy_0(v45, j, 2 * v47 + 2);
    v48 = -1;
    do
      v9 = *((_WORD *)*v44 + ++v48) == 0;
    while ( !v9 );
    ++v44;
    v45 += v48 + 1;
  }
  *v45 = 0;
LABEL_68:
  Property = 0;
  v49 = RegSetValueExW(v34, L"ExtKeyUsageSyntax", 0, 7u, v42, *((_DWORD *)v42 - 1));
  if ( v49 )
    Property = myHError(v49);
  if ( v42 )
    CertFreeString((unsigned __int16 *)v42);
LABEL_72:
  if ( Property )
    goto LABEL_154;
  v50 = (struct CCAProperty *)*((_QWORD *)this + 12);
  if ( !v50 )
  {
    Property = -2147467261;
    goto LABEL_154;
  }
  v51 = (const WCHAR *)*((_QWORD *)v50 + 1);
  if ( v51 && CompareStringW(0x7Fu, 1u, L"pKICriticalExtensions", -1, v51, -1) == 2 )
  {
    v111 = v50;
    goto LABEL_78;
  }
  v52 = (CCAProperty *)*((_QWORD *)v50 + 2);
  if ( !v52 )
  {
LABEL_240:
    v111 = 0;
    Property = -2147023728;
    goto LABEL_154;
  }
  Property = CCAProperty::Find(v52, L"pKICriticalExtensions", &v111);
  if ( Property )
    goto LABEL_154;
  v50 = v111;
LABEL_78:
  v53 = hKeya;
  if ( !hKeya )
    goto LABEL_225;
  v54 = *(const void ***)v50;
  if ( !*(_QWORD *)v50 )
  {
    v61 = (BYTE *)CertAllocString(&Class);
    if ( !v61 )
    {
      Property = -2147024882;
      goto LABEL_104;
    }
    goto LABEL_100;
  }
  v55 = *v54;
  v56 = 0;
  if ( *v54 )
  {
    do
    {
      v62 = -1;
      do
        ++v62;
      while ( v55[v62] );
      v55 = v54[1];
      ++v54;
      v56 += v62 + 1;
    }
    while ( v55 );
  }
  v57 = v56 + 1;
  if ( (unsigned __int64)(v56 + 1) > 0x10000 )
  {
    Property = -2147024362;
    CSPrintErrorLineFileData2(0, 0x3850326u, -2147024362, 0);
    goto LABEL_104;
  }
  if ( v57 > 0x30D4000 )
  {
    v106 = 64488230;
LABEL_196:
    CSPrintErrorLineFileData2(0, v106, -2147024362, 0);
LABEL_86:
    Property = -2147024882;
    goto LABEL_104;
  }
  v58 = 2 * v57;
  if ( (unsigned int)v58 > 0x61A8000 )
  {
    v106 = 66061094;
    goto LABEL_196;
  }
  v59 = (unsigned int)v58;
  v60 = LocalAlloc(0, v58 + 6);
  if ( !v60 )
    goto LABEL_86;
  *v60 = v58;
  v61 = (BYTE *)(v60 + 1);
  *(_WORD *)((char *)v60 + v59 + 4) = 0;
  if ( v60 == (_DWORD *)-4LL )
    goto LABEL_86;
  v63 = *(const void ***)v50;
  v64 = v60 + 1;
  for ( k = *v63; *v63; k = *v63 )
  {
    v66 = -1;
    do
      v9 = k[++v66] == 0;
    while ( !v9 );
    memcpy_0(v64, k, 2 * v66 + 2);
    v67 = -1;
    do
      v9 = *((_WORD *)*v63 + ++v67) == 0;
    while ( !v9 );
    ++v63;
    v64 += v67 + 1;
  }
  *v64 = 0;
LABEL_100:
  Property = 0;
  v68 = RegSetValueExW(v53, L"CriticalExtensions", 0, 7u, v61, *((_DWORD *)v61 - 1));
  if ( v68 )
    Property = myHError(v68);
  if ( v61 )
    CertFreeString((unsigned __int16 *)v61);
LABEL_104:
  if ( Property )
    goto LABEL_154;
  v69 = RegSetValueExW(hKeya, L"KeyUsage", 0, 3u, *((const BYTE **)this + 5), *((_DWORD *)this + 8));
  v70 = v69 <= 0;
  if ( v69 )
  {
LABEL_152:
    if ( v70 )
    {
      Property = v69;
      goto LABEL_154;
    }
LABEL_153:
    Property = (unsigned __int16)v69 | 0x80070000;
    goto LABEL_154;
  }
  v69 = RegSetValueExW(hKeya, L"Flags", 0, 4u, (const BYTE *)this + 56, 4u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v69 = RegSetValueExW(hKeya, L"Revision", 0, 4u, (const BYTE *)this + 144, 4u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v69 = RegSetValueExW(hKeya, L"KeySpec", 0, 4u, (const BYTE *)this + 60, 4u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  if ( !*((_DWORD *)this + 5) )
    *((_DWORD *)this + 6) = -(*((_DWORD *)this + 4) != 0);
  v69 = RegSetValueExW(hKeya, L"PathLen", 0, 4u, (const BYTE *)this + 24, 4u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v69 = RegSetValueExW(hKeya, L"ValidityPeriod", 0, 3u, (const BYTE *)this + 104, 8u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v69 = RegSetValueExW(hKeya, L"RenewalOverlap", 0, 3u, (const BYTE *)this + 112, 8u);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v71 = (void *)*((_QWORD *)this + 17);
  if ( !v71
    || !IsValidSecurityDescriptor(v71)
    || (SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 17))) == 0 )
  {
    Property = -2147023558;
    goto LABEL_154;
  }
  v69 = RegSetValueExW(hKeya, L"Security", 0, 3u, *((const BYTE **)this + 17), SecurityDescriptorLength);
  if ( v69 )
  {
    if ( v69 <= 0 )
    {
      Property = v69;
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  if ( *((_DWORD *)this + 22) )
  {
    v111 = 0;
    Data = 0;
    for ( m = 0; ; ++m )
    {
      while ( 1 )
      {
        if ( m >= 0xD )
          goto LABEL_154;
        v74 = &g_CTV2Properties + 2 * m;
        if ( *((_DWORD *)v74 + 2) )
          break;
        v75 = (const wchar_t *)*v74;
        for ( n = 0; n != 30; n += 2 )
        {
          v77 = v75[n] - aMspkiTemplateM[n];
          if ( v77 )
            break;
          v77 = v75[n + 1] - aMspkiTemplateM[n + 1];
          if ( v77 )
            break;
        }
        if ( v77 )
        {
          v78 = -1;
          do
          {
            v79 = v75[v78 + 1] - aMspkiRaSignatu[v78 + 1];
            if ( v79 )
              break;
            v78 += 2;
            if ( v78 == 19 )
              break;
            v79 = v75[v78] - aMspkiRaSignatu[v78];
          }
          while ( !v79 );
          if ( v79 )
          {
            for ( ii = 0; ii != 22; ii += 2 )
            {
              v81 = v75[ii] - aMspkiEnrollmen[ii];
              if ( v81 )
                break;
              v81 = v75[ii + 1] - aMspkiEnrollmen[ii + 1];
              if ( v81 )
                break;
            }
            if ( v81 )
            {
              v82 = -1;
              do
              {
                v83 = v75[v82 + 1] - aMspkiPrivateKe[v82 + 1];
                if ( v83 )
                  break;
                v82 += 2;
                if ( v82 == 23 )
                  break;
                v83 = v75[v82] - aMspkiPrivateKe[v82];
              }
              while ( !v83 );
              if ( v83 )
              {
                for ( jj = 0; jj != 28; jj += 2 )
                {
                  v85 = v75[jj] - aMspkiCertifica_1[jj];
                  if ( v85 )
                    break;
                  v85 = v75[jj + 1] - aMspkiCertifica_1[jj + 1];
                  if ( v85 )
                    break;
                }
                if ( v85 )
                {
                  if ( !wcscmp_0(v75, L"msPKI-Minimal-Key-Size") )
                  {
                    v86 = *((_DWORD *)this + 20);
                  }
                  else
                  {
                    if ( wcscmp_0(v75, L"msPKI-Template-Schema-Version") )
                    {
                      Property = -2147418113;
                      goto LABEL_154;
                    }
                    v86 = *((_DWORD *)this + 22);
                  }
                }
                else
                {
                  v86 = *((_DWORD *)this + 19);
                }
              }
              else
              {
                v86 = *((_DWORD *)this + 18);
              }
            }
            else
            {
              v86 = *((_DWORD *)this + 17);
            }
          }
          else
          {
            v86 = *((_DWORD *)this + 21);
          }
        }
        else
        {
          v86 = *((_DWORD *)this + 16);
        }
        Data = v86;
        v69 = RegSetValueExW(hKeya, v75, 0, 4u, (const BYTE *)&Data, 4u);
        v70 = v69 <= 0;
        if ( v69 )
          goto LABEL_152;
        ++m;
      }
      Property = CCAProperty::Find(*((CCAProperty **)this + 12), (const unsigned __int16 *)*v74, &v111);
      if ( Property )
        break;
      v88 = hKeya;
      if ( !hKeya )
        goto LABEL_225;
      v89 = (const WCHAR *)*v74;
      if ( !*v74 )
        goto LABEL_225;
      v90 = v111;
      v91 = *(const char ***)v111;
      if ( *(_QWORD *)v111 )
      {
        v92 = *v91;
        for ( kk = 0; v92; kk += v103 + 1 )
        {
          v103 = -1;
          do
            ++v103;
          while ( *(_WORD *)&v92[2 * v103] );
          v92 = v91[1];
          ++v91;
        }
        v94 = kk + 1;
        if ( (unsigned __int64)(kk + 1) > 0x10000 )
        {
          Property = -2147024362;
          CSPrintErrorLineFileData2(0, 0x3850326u, -2147024362, 0);
          goto LABEL_182;
        }
        if ( v94 > 0x30D4000 )
        {
          CSPrintErrorLineFileData2(0, 0x3D80326u, -2147024362, 0);
          Property = -2147024882;
          goto LABEL_182;
        }
        v95 = CertAllocStringByteLen(v92, 2 * v94);
        v96 = (BYTE *)v95;
        if ( !v95 )
        {
          Property = -2147024882;
          goto LABEL_182;
        }
        v97 = *(const void ***)v90;
        v98 = v95;
        for ( mm = *v97; *v97; mm = *v97 )
        {
          v100 = -1;
          do
            v9 = mm[++v100] == 0;
          while ( !v9 );
          memcpy_0(v98, mm, 2 * v100 + 2);
          v101 = -1;
          do
            v9 = *((_WORD *)*v97 + ++v101) == 0;
          while ( !v9 );
          ++v97;
          v98 += v101 + 1;
        }
        *v98 = 0;
      }
      else
      {
        v96 = (BYTE *)CertAllocString(&Class);
        if ( !v96 )
        {
          Property = -2147024882;
          goto LABEL_182;
        }
      }
      Property = 0;
      v102 = RegSetValueExW(v88, v89, 0, 7u, v96, *((_DWORD *)v96 - 1));
      if ( v102 )
        Property = myHError(v102);
      if ( v96 )
        CertFreeString((unsigned __int16 *)v96);
LABEL_182:
      if ( Property )
        break;
      v111 = 0;
    }
  }
LABEL_154:
  if ( hMem )
    LocalFree(hMem);
  if ( hKeya )
    RegCloseKey(hKeya);
  return Property;
}

```

## disassembly

```asm
0x180003be0  mov     r11, rsp
0x180003be3  push    rbp
0x180003be4  push    rsi
0x180003be5  lea     rbp, [r11-5Fh]
0x180003be9  sub     rsp, 88h
0x180003bf0  mov     [r11-18h], rdi
0x180003bf4  lea     r9, Class; lpClass
0x180003bfb  mov     [r11-20h], r12
0x180003bff  mov     rax, rdx
0x180003c02  mov     [r11-28h], r13
0x180003c06  xor     r8d, r8d; Reserved
0x180003c09  mov     r13, rcx
0x180003c0c  mov     [r11-30h], r14
0x180003c10  lea     rcx, [rbp+57h+arg_10]
0x180003c14  mov     [r11-38h], r15
0x180003c18  mov     [r11-58h], rcx
0x180003c1c  xor     r15d, r15d
0x180003c1f  lea     rcx, [rbp+57h+hKey]
0x180003c23  mov     [rbp+57h+arg_18], r15
0x180003c27  mov     rdx, [r13+8]; lpSubKey
0x180003c2b  mov     [r11-60h], rcx
0x180003c2f  mov     rcx, rax; hKey
0x180003c32  mov     [r11-68h], r15
0x180003c36  mov     dword ptr [rsp+28h], 0F003Fh; samDesired
0x180003c3e  mov     [r11-78h], r15d
0x180003c42  mov     [rbp+57h+Data], r15d
0x180003c46  mov     [rbp+57h+hMem], r15
0x180003c4a  mov     [rbp+57h+hKey], r15
0x180003c4e  mov     [rbp+57h+arg_10], r15d
0x180003c52  call    cs:__imp_RegCreateKeyExW
0x180003c58  mov     esi, eax
0x180003c5a  test    eax, eax
0x180003c5c  jnz     loc_1800049A2
0x180003c62  lea     r8, [rbp+57h+hMem]; unsigned __int16 ***
0x180003c66  mov     rcx, r13; this
0x180003c69  lea     rdx, aDsdisplayname; "dsDisplayName"
0x180003c70  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180003c75  mov     esi, eax
0x180003c77  test    eax, eax
0x180003c79  jnz     loc_180004677
0x180003c7f  mov     rcx, [rbp+57h+hMem]
0x180003c83  test    rcx, rcx
0x180003c86  jnz     loc_180004A18
0x180003c8c  lea     rcx, Class
0x180003c93  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003c9a  nop     word ptr [rax+rax+00h]
0x180003ca0  cmp     [rcx+rax*2+2], r15w
0x180003ca6  lea     rax, [rax+1]
0x180003caa  jnz     short loc_180003CA0
0x180003cac  lea     rax, ds:2[rax*2]
0x180003cb4  cmp     rax, 10000h
0x180003cba  ja      loc_180004A29
0x180003cc0  mov     [rsp+28h], eax; cbData
0x180003cc4  lea     rdx, ValueName; "DisplayName"
0x180003ccb  mov     [rsp+90h+lpData], rcx; lpData
0x180003cd0  mov     r9d, 1; dwType
0x180003cd6  mov     rcx, [rbp+57h+hKey]; hKey
0x180003cda  xor     r8d, r8d; Reserved
0x180003cdd  call    cs:__imp_RegSetValueExW
0x180003ce3  mov     esi, eax
0x180003ce5  test    eax, eax
0x180003ce7  jnz     loc_1800049B6
0x180003ced  mov     [rsp+90h+arg_8], rbx
0x180003cf5  mov     rbx, [r13+60h]
0x180003cf9  test    rbx, rbx
0x180003cfc  jz      loc_180004A45
0x180003d02  mov     rax, [rbx+8]
0x180003d06  test    rax, rax
0x180003d09  jnz     loc_180003DBD
0x180003d0f  mov     rcx, [rbx+10h]; this
0x180003d13  test    rcx, rcx
0x180003d16  jz      loc_180004B69
0x180003d1c  lea     r8, [rbp+57h+arg_18]; struct CCAProperty **
0x180003d20  lea     rdx, aPkidefaultcsps; "pKIDefaultCSPs"
0x180003d27  call    ?Find@CCAProperty@@QEAAJPEBGPEAPEAV1@@Z; CCAProperty::Find(ushort const *,CCAProperty * *)
0x180003d2c  mov     esi, eax
0x180003d2e  test    eax, eax
0x180003d30  jnz     loc_18000466F
0x180003d36  mov     rbx, [rbp+57h+arg_18]
0x180003d3a  mov     r14, [rbp+57h+hKey]
0x180003d3e  test    r14, r14
0x180003d41  jz      loc_180004A45
0x180003d47  mov     rax, [rbx]
0x180003d4a  test    rax, rax
0x180003d4d  jz      loc_18000491A
0x180003d53  mov     rcx, [rax]
0x180003d56  mov     r8, r15
0x180003d59  test    rcx, rcx
0x180003d5c  jnz     loc_180003E00
0x180003d62  lea     rax, [r8+1]
0x180003d66  cmp     rax, 10000h
0x180003d6c  ja      loc_180004A4F
0x180003d72  cmp     eax, 30D4000h
0x180003d77  ja      loc_1800048A0
0x180003d7d  lea     edi, [rax+rax]
0x180003d80  cmp     edi, 61A8000h
0x180003d86  ja      loc_180004A6B
0x180003d8c  lea     rdx, [rdi+6]; uBytes
0x180003d90  mov     esi, edi
0x180003d92  xor     ecx, ecx; uFlags
0x180003d94  call    cs:__imp_LocalAlloc
0x180003d9a  test    rax, rax
0x180003d9d  jz      short loc_180003DB3
0x180003d9f  mov     [rax], edi
0x180003da1  lea     rdi, [rax+4]
0x180003da5  mov     [rdi+rsi], r15w
0x180003daa  test    rdi, rdi
0x180003dad  jnz     loc_180003E33
0x180003db3  mov     esi, 8007000Eh
0x180003db8  jmp     loc_180003EDD
0x180003dbd  mov     dword ptr [rsp+28h], 0FFFFFFFFh; cchCount2
0x180003dc5  lea     r8, aPkidefaultcsps; "pKIDefaultCSPs"
0x180003dcc  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003dd2  mov     [rsp+90h+lpData], rax; lpString2
0x180003dd7  mov     edx, 1; dwCmpFlags
0x180003ddc  mov     ecx, 7Fh; Locale
0x180003de1  call    cs:__imp_CompareStringW
0x180003de7  cmp     eax, 2
0x180003dea  jnz     loc_180003D0F
0x180003df0  mov     [rbp+57h+arg_18], rbx
0x180003df4  jmp     loc_180003D3A
0x180003e00  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180003e07  nop     word ptr [rax+rax+00000000h]
0x180003e10  inc     rdx
0x180003e13  cmp     [rcx+rdx*2], r15w
0x180003e18  jnz     short loc_180003E10
0x180003e1a  mov     rcx, [rax+8]
0x180003e1e  add     rax, 8
0x180003e22  inc     r8
0x180003e25  add     r8, rdx
0x180003e28  test    rcx, rcx
0x180003e2b  jz      loc_180003D62
0x180003e31  jmp     short loc_180003E00
0x180003e33  mov     rbx, [rbx]
0x180003e36  mov     rsi, rdi
0x180003e39  mov     rax, [rbx]
0x180003e3c  test    rax, rax
0x180003e3f  jz      short loc_180003EA0
0x180003e41  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180003e48  nop     dword ptr [rax+rax+00000000h]
0x180003e50  cmp     [rax+r8*2+2], r15w
0x180003e56  lea     r8, [r8+1]
0x180003e5a  jnz     short loc_180003E50
0x180003e5c  lea     r8, ds:2[r8*2]; Size
0x180003e64  mov     rdx, rax; Src
0x180003e67  mov     rcx, rsi; void *
0x180003e6a  call    memcpy_0
0x180003e6f  mov     rcx, [rbx]
0x180003e72  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003e79  nop     dword ptr [rax+00000000h]
0x180003e80  cmp     [rcx+rax*2+2], r15w
0x180003e86  lea     rax, [rax+1]
0x180003e8a  jnz     short loc_180003E80
0x180003e8c  add     rbx, 8
0x180003e90  lea     rsi, [rsi+rax*2]
0x180003e94  add     rsi, 2
0x180003e98  mov     rax, [rbx]
0x180003e9b  test    rax, rax
0x180003e9e  jnz     short loc_180003E41
0x180003ea0  mov     [rsi], r15w
0x180003ea4  mov     eax, [rdi-4]
0x180003ea7  lea     rdx, aSupportedcsps; "SupportedCSPs"
0x180003eae  mov     [rsp+28h], eax; cbData
0x180003eb2  mov     r9d, 7; dwType
0x180003eb8  xor     r8d, r8d; Reserved
0x180003ebb  mov     [rsp+90h+lpData], rdi; lpData
0x180003ec0  mov     rcx, r14; hKey
0x180003ec3  mov     esi, r15d
0x180003ec6  call    cs:__imp_RegSetValueExW
0x180003ecc  test    eax, eax
0x180003ece  jnz     loc_180004A78
0x180003ed4  test    rdi, rdi
0x180003ed7  jnz     loc_18000486C
0x180003edd  test    esi, esi
0x180003edf  jnz     loc_18000466F
0x180003ee5  mov     rbx, [r13+60h]
0x180003ee9  test    rbx, rbx
0x180003eec  jz      loc_180004A86
0x180003ef2  mov     rax, [rbx+8]
0x180003ef6  test    rax, rax
0x180003ef9  jnz     loc_180003FAD
0x180003eff  mov     rcx, [rbx+10h]; this
0x180003f03  test    rcx, rcx
0x180003f06  jz      loc_180004B69
0x180003f0c  lea     r8, [rbp+57h+arg_18]; struct CCAProperty **
0x180003f10  lea     rdx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x180003f17  call    ?Find@CCAProperty@@QEAAJPEBGPEAPEAV1@@Z; CCAProperty::Find(ushort const *,CCAProperty * *)
0x180003f1c  mov     esi, eax
0x180003f1e  test    eax, eax
0x180003f20  jnz     loc_18000466F
0x180003f26  mov     rbx, [rbp+57h+arg_18]
0x180003f2a  mov     r14, [rbp+57h+hKey]
0x180003f2e  test    r14, r14
0x180003f31  jz      loc_180004A45
0x180003f37  mov     rax, [rbx]
0x180003f3a  test    rax, rax
0x180003f3d  jz      loc_18000493C
0x180003f43  mov     rcx, [rax]
0x180003f46  mov     r8, r15
0x180003f49  test    rcx, rcx
0x180003f4c  jnz     loc_180003FF0
0x180003f52  lea     rax, [r8+1]
0x180003f56  cmp     rax, 10000h
0x180003f5c  ja      loc_180004A90
0x180003f62  cmp     eax, 30D4000h
0x180003f67  ja      loc_1800048BA
0x180003f6d  lea     edi, [rax+rax]
0x180003f70  cmp     edi, 61A8000h
0x180003f76  ja      loc_180004AAC
0x180003f7c  lea     rdx, [rdi+6]; uBytes
0x180003f80  mov     esi, edi
0x180003f82  xor     ecx, ecx; uFlags
0x180003f84  call    cs:__imp_LocalAlloc
0x180003f8a  test    rax, rax
0x180003f8d  jz      short loc_180003FA3
0x180003f8f  mov     [rax], edi
0x180003f91  lea     rdi, [rax+4]
0x180003f95  mov     [rdi+rsi], r15w
0x180003f9a  test    rdi, rdi
0x180003f9d  jnz     loc_180004023
0x180003fa3  mov     esi, 8007000Eh
0x180003fa8  jmp     loc_1800040CD
0x180003fad  mov     dword ptr [rsp+28h], 0FFFFFFFFh; cchCount2
0x180003fb5  lea     r8, aPkiextendedkey; "pKIExtendedKeyUsage"
0x180003fbc  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003fc2  mov     [rsp+90h+lpData], rax; lpString2
0x180003fc7  mov     edx, 1; dwCmpFlags
0x180003fcc  mov     ecx, 7Fh; Locale
0x180003fd1  call    cs:__imp_CompareStringW
0x180003fd7  cmp     eax, 2
0x180003fda  jnz     loc_180003EFF
0x180003fe0  mov     [rbp+57h+arg_18], rbx
0x180003fe4  jmp     loc_180003F2A
0x180003ff0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180003ff7  nop     word ptr [rax+rax+00000000h]
0x180004000  inc     rdx
0x180004003  cmp     [rcx+rdx*2], r15w
0x180004008  jnz     short loc_180004000
0x18000400a  mov     rcx, [rax+8]
0x18000400e  add     rax, 8
0x180004012  inc     r8
0x180004015  add     r8, rdx
0x180004018  test    rcx, rcx
0x18000401b  jz      loc_180003F52
0x180004021  jmp     short loc_180003FF0
0x180004023  mov     rbx, [rbx]
0x180004026  mov     rsi, rdi
0x180004029  mov     rax, [rbx]
0x18000402c  test    rax, rax
0x18000402f  jz      short loc_180004090
0x180004031  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004038  nop     dword ptr [rax+rax+00000000h]
0x180004040  cmp     [rax+r8*2+2], r15w
0x180004046  lea     r8, [r8+1]
0x18000404a  jnz     short loc_180004040
0x18000404c  lea     r8, ds:2[r8*2]; Size
0x180004054  mov     rdx, rax; Src
0x180004057  mov     rcx, rsi; void *
0x18000405a  call    memcpy_0
0x18000405f  mov     rcx, [rbx]
0x180004062  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004069  nop     dword ptr [rax+00000000h]
0x180004070  cmp     [rcx+rax*2+2], r15w
0x180004076  lea     rax, [rax+1]
0x18000407a  jnz     short loc_180004070
0x18000407c  add     rbx, 8
0x180004080  lea     rsi, [rsi+rax*2]
0x180004084  add     rsi, 2
0x180004088  mov     rax, [rbx]
0x18000408b  test    rax, rax
0x18000408e  jnz     short loc_180004031
0x180004090  mov     [rsi], r15w
0x180004094  mov     eax, [rdi-4]
0x180004097  lea     rdx, aExtkeyusagesyn; "ExtKeyUsageSyntax"
0x18000409e  mov     [rsp+28h], eax; cbData
0x1800040a2  mov     r9d, 7; dwType
0x1800040a8  xor     r8d, r8d; Reserved
0x1800040ab  mov     [rsp+90h+lpData], rdi; lpData
0x1800040b0  mov     rcx, r14; hKey
0x1800040b3  mov     esi, r15d
0x1800040b6  call    cs:__imp_RegSetValueExW
0x1800040bc  test    eax, eax
0x1800040be  jnz     loc_180004AB9
0x1800040c4  test    rdi, rdi
0x1800040c7  jnz     loc_180004879
0x1800040cd  test    esi, esi
0x1800040cf  jnz     loc_18000466F
0x1800040d5  mov     rbx, [r13+60h]
0x1800040d9  test    rbx, rbx
0x1800040dc  jz      loc_180004AC7
0x1800040e2  mov     rax, [rbx+8]
0x1800040e6  test    rax, rax
0x1800040e9  jnz     loc_18000419D
0x1800040ef  mov     rcx, [rbx+10h]; this
0x1800040f3  test    rcx, rcx
0x1800040f6  jz      loc_180004B69
0x1800040fc  lea     r8, [rbp+57h+arg_18]; struct CCAProperty **
0x180004100  lea     rdx, aPkicriticalext; "pKICriticalExtensions"
0x180004107  call    ?Find@CCAProperty@@QEAAJPEBGPEAPEAV1@@Z; CCAProperty::Find(ushort const *,CCAProperty * *)
0x18000410c  mov     esi, eax
  ... truncated ...
```
