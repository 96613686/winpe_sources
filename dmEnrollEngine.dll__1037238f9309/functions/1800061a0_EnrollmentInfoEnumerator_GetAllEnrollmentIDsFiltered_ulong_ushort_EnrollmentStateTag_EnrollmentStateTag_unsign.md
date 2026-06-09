# EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(ulong *,ushort * * *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)

- ea: `0x1800061a0`
- end: `0x18000678b`
- name: `?GetAllEnrollmentIDsFiltered@EnrollmentInfoEnumerator@@AEAAJPEAKPEAPEAPEAGW4EnrollmentStateTag@@2_KPEBGHH@Z`
- size: `1515`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003fb4`
- `0x1800041c0`
- `0x180004380`
- `0x1800044c0`
- `0x180005b10`
- `0x180005c60`

## callees

- `0x1800061a0`
- `0x1800067a0`
- `0x18000dd4c`
- `0x18002e1a0`
- `0x18002ec8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006750`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006750`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006778`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006778`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000620a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000643a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000620a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000643a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000642a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000642a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800062cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800062cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000624e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000624e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000652a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006570`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000652a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000636d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000638b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800064d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000636d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000638b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800064d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006357`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063d2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800065f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800065f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006683`
- `OLEAUT32!__imp_SysFreeString` at `0x180006683`

## pseudocode

```c
int __fastcall EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  __int64 v9; // r14
  HKEY v10; // rdi
  char IsStateSeparationEnabled; // al
  const WCHAR *v12; // rdx
  int result; // eax
  HKEY v14; // rbx
  LSTATUS v15; // eax
  signed int v16; // esi
  unsigned __int64 v17; // rax
  DWORD v18; // esi
  _QWORD *v19; // rax
  _QWORD *v20; // r12
  WCHAR *v21; // r13
  unsigned __int64 v22; // rax
  DWORD v23; // r15d
  LSTATUS v24; // eax
  char v25; // al
  const wchar_t *v26; // r9
  LSTATUS v27; // eax
  HKEY v28; // rcx
  HKEY v29; // r12
  DWORD LastError; // r14d
  unsigned __int16 *v31; // r12
  unsigned __int8 v32; // r14
  HANDLE ProcessHeap; // rax
  BSTR v35; // rax
  unsigned int v36; // r14d
  OLECHAR *v37; // rcx
  HANDLE v38; // rax
  const WCHAR *v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // [rsp+60h] [rbp-A0h]
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  int pvData; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h]
  _QWORD *v48; // [rsp+88h] [rbp-78h]
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v51; // [rsp+98h] [rbp-68h] BYREF
  int v52; // [rsp+9Ch] [rbp-64h]
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v54; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v55; // [rsp+B0h] [rbp-50h]
  unsigned int *v56; // [rsp+B8h] [rbp-48h]
  _QWORD *v57; // [rsp+C0h] [rbp-40h]
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF

  v9 = a7;
  v10 = 0;
  v52 = a4;
  v57 = a3;
  v56 = a2;
  v47 = a7;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  hkey = 0;
  SubKey[0] = 0;
  if ( !a2 || !a3 )
    return -2147024809;
  *a2 = 0;
  *a3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v12 = L"OSData\\Software\\Microsoft\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v12 = L"Software\\Microsoft\\Enrollments";
  result = RegOpenKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), v12, 0, 0x20119u, &hKey);
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147024894 )
    return 0;
  if ( result >= 0 )
  {
    v14 = hKey;
    v55 = hKey;
    v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v16 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_19;
    }
    v17 = 8LL * cSubKeys;
    if ( v17 > 0xFFFFFFFF )
    {
      v16 = -2147024362;
      goto LABEL_19;
    }
    v18 = 8 * cSubKeys;
    v19 = CoTaskMemAlloc((unsigned int)v17);
    v48 = v19;
    v20 = v19;
    if ( !v19 )
    {
      v16 = -2147024882;
      goto LABEL_19;
    }
    v21 = 0;
    memset_0(v19, 0, v18);
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
LABEL_14:
      v16 = -2147024362;
      goto LABEL_15;
    }
    v22 = 2LL * ++cbMaxSubKeyLen;
    if ( v22 > 0xFFFFFFFF )
      goto LABEL_14;
    v21 = (WCHAR *)CoTaskMemAlloc((unsigned int)v22);
    if ( !v21 )
    {
      v16 = -2147024882;
      goto LABEL_15;
    }
    v41 = 0;
    v23 = 0;
    v16 = 0;
    while ( 1 )
    {
      if ( v23 >= cSubKeys )
      {
        *v56 = v41;
        *v57 = v48;
        goto LABEL_16;
      }
      cchName = cbMaxSubKeyLen;
      *v21 = 0;
      v24 = RegEnumKeyExW(v14, v23, v21, &cchName, 0, 0, 0, 0);
      v16 = v24;
      if ( v24 )
      {
        if ( v24 > 0 )
          v16 = (unsigned __int16)v24 | 0x80070000;
LABEL_55:
        v36 = 0;
        v20 = v48;
        if ( v41 )
        {
          do
          {
            v37 = (OLECHAR *)v20[v36];
            if ( v37 )
            {
              SysFreeString(v37);
              v20[v36] = 0;
            }
            ++v36;
          }
          while ( v36 < v41 );
          v14 = v55;
        }
LABEL_15:
        CoTaskMemFree(v20);
        if ( v21 )
LABEL_16:
          CoTaskMemFree(v21);
        if ( v10 )
          RegCloseKey(v10);
LABEL_19:
        if ( v14 )
          RegCloseKey(v14);
        return v16;
      }
      v25 = RtlIsStateSeparationEnabled();
      v26 = L"OSData\\Software\\Microsoft\\Enrollments";
      if ( !v25 )
        v26 = L"Software\\Microsoft\\Enrollments";
      v16 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v26, v21);
      if ( v16 < 0 )
        goto LABEL_55;
      v27 = RegOpenKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), SubKey, 0, 0x20119u, &hkey);
      v16 = v27;
      if ( v27 > 0 )
        v16 = (unsigned __int16)v27 | 0x80070000;
      if ( v16 >= 0 )
      {
        v28 = hkey;
        v29 = hkey;
        if ( v10 )
        {
          LastError = GetLastError();
          RegCloseKey(v10);
          SetLastError(LastError);
          v28 = hkey;
          v9 = v47;
        }
        pcbData = 4;
        v10 = v29;
        v31 = 0;
        pvData = 0;
        if ( !RegGetValueW(v28, 0, L"EnrollmentState", 0x18u, 0, &pvData, &pcbData) )
          break;
      }
LABEL_47:
      ++v23;
    }
    v45 = 0;
    v51 = 4;
    RegGetValueW(hkey, 0, L"EnrollmentType", 0x18u, 0, &v45, &v51);
    v54 = 0;
    if ( v9 )
    {
      v39 = L"PartnerOpaqueID";
      if ( !a8 )
        v39 = L"AADOpaqueID";
      AllocAndGetEnrollmentString(hkey, v39, &v54);
      v31 = v54;
    }
    if ( pvData == 63 )
    {
LABEL_45:
      if ( v31 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v31);
      }
      goto LABEL_47;
    }
    v32 = 0;
    if ( pvData != a5 )
    {
      v32 = _bittest64(&a6, v45);
      if ( pvData == v52 )
        v32 = 1;
    }
    if ( v47 && v31 )
    {
      if ( a9 )
      {
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(v47 + 2 * v40) );
        if ( !(unsigned int)_o__wcsnicmp(v31) )
          goto LABEL_48;
      }
      else if ( !(unsigned int)_o__wcsicmp(v31, v47) )
      {
        goto LABEL_48;
      }
    }
    if ( !v32 )
    {
LABEL_44:
      v9 = v47;
      goto LABEL_45;
    }
LABEL_48:
    v35 = SysAllocString(v21);
    v48[v41] = v35;
    if ( !v35 )
    {
      v16 = -2147024882;
      if ( v31 )
      {
        v38 = GetProcessHeap();
        HeapFree(v38, 0, v31);
      }
      goto LABEL_55;
    }
    ++v41;
    goto LABEL_44;
  }
  return result;
}

```

## disassembly

```asm
0x1800061a0  push    rbp
0x1800061a2  push    rdi
0x1800061a3  push    r14
0x1800061a5  lea     rbp, [rsp-210h]
0x1800061ad  sub     rsp, 310h
0x1800061b4  mov     rax, cs:__security_cookie
0x1800061bb  xor     rax, rsp
0x1800061be  mov     [rbp+220h+var_40], rax
0x1800061c5  mov     r14, [rbp+220h+arg_30]
0x1800061cc  xor     edi, edi
0x1800061ce  mov     [rbp+220h+var_284], r9d
0x1800061d2  mov     [rbp+220h+var_260], r8
0x1800061d6  mov     [rbp+220h+var_268], rdx
0x1800061da  mov     [rbp+220h+var_2A0], r14
0x1800061de  mov     [rsp+320h+cSubKeys], edi
0x1800061e2  mov     [rsp+320h+cbMaxSubKeyLen], edi
0x1800061e6  mov     [rbp+220h+hKey], rdi
0x1800061ea  mov     [rsp+320h+hkey], rdi
0x1800061ef  mov     [rbp+220h+SubKey], di
0x1800061f3  test    rdx, rdx
0x1800061f6  jz      loc_180006646
0x1800061fc  test    r8, r8
0x1800061ff  jz      loc_180006646
0x180006205  mov     [rdx], edi
0x180006207  mov     [r8], rdi
0x18000620a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006210  lea     rcx, SubKey; "Software\\Microsoft\\Enrollments"
0x180006217  mov     r9d, 20119h; samDesired
0x18000621d  test    al, al
0x18000621f  lea     rdx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180006226  mov     eax, 2000h
0x18000622b  cmovz   rdx, rcx; lpSubKey
0x18000622f  cmp     cs:word_1800AFC84, ax
0x180006236  mov     ecx, edi
0x180006238  lea     rax, [rbp+220h+hKey]
0x18000623c  setnz   cl
0x18000623f  mov     [rsp+320h+phkResult], rax; phkResult
0x180006244  add     rcx, 0FFFFFFFF80000001h; hKey
0x18000624b  xor     r8d, r8d; ulOptions
0x18000624e  call    cs:__imp_RegOpenKeyExW
0x180006254  test    eax, eax
0x180006256  jg      loc_1800066CB
0x18000625c  cmp     eax, 80070002h
0x180006261  jz      loc_1800066E8
0x180006267  test    eax, eax
0x180006269  js      loc_1800063A3
0x18000626f  mov     [rsp+320h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180006274  lea     rax, [rsp+320h+cbMaxSubKeyLen]
0x180006279  mov     [rsp+320h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18000627e  xor     r9d, r9d; lpReserved
0x180006281  mov     [rsp+320h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180006286  xor     r8d, r8d; lpcchClass
0x180006289  mov     [rsp+320h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18000628e  xor     edx, edx; lpClass
0x180006290  mov     [rsp+320h+lpcValues], rdi; lpcValues
0x180006295  mov     [rsp+320h+arg_0], rbx
0x18000629d  mov     rbx, [rbp+220h+hKey]
0x1800062a1  mov     [rsp+320h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800062a6  mov     rcx, rbx; hKey
0x1800062a9  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800062ae  lea     rax, [rsp+320h+cSubKeys]
0x1800062b3  mov     [rsp+320h+var_18], rsi
0x1800062bb  mov     [rsp+320h+phkResult], rax; lpcSubKeys
0x1800062c0  mov     [rsp+320h+var_20], r12
0x1800062c8  mov     [rbp+220h+var_270], rbx
0x1800062cc  call    cs:__imp_RegQueryInfoKeyW
0x1800062d2  mov     esi, eax
0x1800062d4  test    eax, eax
0x1800062d6  jnz     loc_1800066A1
0x1800062dc  mov     eax, [rsp+320h+cSubKeys]
0x1800062e0  mov     [rsp+320h+var_30], r15
0x1800062e8  mov     r15d, 0FFFFFFFFh
0x1800062ee  shl     rax, 3
0x1800062f2  cmp     rax, r15
0x1800062f5  ja      loc_18000663C
0x1800062fb  mov     ecx, eax; cb
0x1800062fd  mov     esi, eax
0x1800062ff  call    cs:__imp_CoTaskMemAlloc
0x180006305  mov     [rbp+220h+var_298], rax
0x180006309  mov     r12, rax
0x18000630c  test    rax, rax
0x18000630f  jz      loc_1800066EF
0x180006315  mov     [rsp+320h+var_28], r13
0x18000631d  mov     r8d, esi; Size
0x180006320  xor     edx, edx; Val
0x180006322  mov     rcx, rax; void *
0x180006325  mov     r13, rdi
0x180006328  call    memset_0
0x18000632d  mov     eax, [rsp+320h+cbMaxSubKeyLen]
0x180006331  lea     ecx, [rax+1]
0x180006334  cmp     ecx, eax
0x180006336  jnb     loc_1800063BE
0x18000633c  mov     [rsp+320h+cbMaxSubKeyLen], r15d
0x180006341  mov     esi, 80070216h
0x180006346  mov     rcx, r12; pv
0x180006349  call    cs:__imp_CoTaskMemFree
0x18000634f  test    r13, r13
0x180006352  jz      short loc_18000635D
0x180006354  mov     rcx, r13; pv
0x180006357  call    cs:__imp_CoTaskMemFree
0x18000635d  mov     r13, [rsp+320h+var_28]
0x180006365  test    rdi, rdi
0x180006368  jz      short loc_180006373
0x18000636a  mov     rcx, rdi; hKey
0x18000636d  call    cs:__imp_RegCloseKey
0x180006373  mov     r15, [rsp+320h+var_30]
0x18000637b  mov     r12, [rsp+320h+var_20]
0x180006383  test    rbx, rbx
0x180006386  jz      short loc_180006391
0x180006388  mov     rcx, rbx; hKey
0x18000638b  call    cs:__imp_RegCloseKey
0x180006391  mov     rbx, [rsp+320h+arg_0]
0x180006399  mov     eax, esi
0x18000639b  mov     rsi, [rsp+320h+var_18]
0x1800063a3  mov     rcx, [rbp+220h+var_40]
0x1800063aa  xor     rcx, rsp; StackCookie
0x1800063ad  call    __security_check_cookie
0x1800063b2  add     rsp, 310h
0x1800063b9  pop     r14
0x1800063bb  pop     rdi
0x1800063bc  pop     rbp
0x1800063bd  retn
0x1800063be  mov     eax, ecx
0x1800063c0  add     rax, rax
0x1800063c3  mov     [rsp+320h+cbMaxSubKeyLen], ecx
0x1800063c7  cmp     rax, r15
0x1800063ca  ja      loc_180006341
0x1800063d0  mov     ecx, eax; cb
0x1800063d2  call    cs:__imp_CoTaskMemAlloc
0x1800063d8  mov     r13, rax
0x1800063db  test    rax, rax
0x1800063de  jz      loc_1800066F9
0x1800063e4  xor     r12d, r12d
0x1800063e7  mov     [rsp+320h+var_2C0], r12d
0x1800063ec  mov     r15d, r12d
0x1800063ef  mov     esi, r12d
0x1800063f2  cmp     r15d, [rsp+320h+cSubKeys]
0x1800063f7  jnb     loc_180006614
0x1800063fd  mov     eax, [rsp+320h+cbMaxSubKeyLen]
0x180006401  lea     r9, [rbp+220h+cchName]; lpcchName
0x180006405  mov     [rsp+320h+lpcValues], r12; lpftLastWriteTime
0x18000640a  mov     r8, r13; lpName
0x18000640d  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcchClass
0x180006412  mov     edx, r15d; dwIndex
0x180006415  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpClass
0x18000641a  mov     rcx, rbx; hKey
0x18000641d  mov     [rsp+320h+phkResult], r12; lpReserved
0x180006422  mov     [rbp+220h+cchName], eax
0x180006425  mov     [r13+0], r12w
0x18000642a  call    cs:__imp_RegEnumKeyExW
0x180006430  mov     esi, eax
0x180006432  test    eax, eax
0x180006434  jnz     loc_1800066D8
0x18000643a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006440  lea     r9, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180006447  mov     [rsp+320h+phkResult], r13
0x18000644c  test    al, al
0x18000644e  lea     r8, aSS_0; "%s\\%s"
0x180006455  lea     rax, SubKey; "Software\\Microsoft\\Enrollments"
0x18000645c  mov     edx, 104h; unsigned __int64
0x180006461  cmovz   r9, rax
0x180006465  lea     rcx, [rbp+220h+SubKey]; unsigned __int16 *
0x180006469  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000646e  mov     esi, eax
0x180006470  test    eax, eax
0x180006472  js      loc_18000665D
0x180006478  mov     eax, 2000h
0x18000647d  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x180006481  cmp     cs:word_1800AFC84, ax
0x180006488  mov     rcx, r12
0x18000648b  lea     rax, [rsp+320h+hkey]
0x180006490  mov     r9d, 20119h; samDesired
0x180006496  setnz   cl
0x180006499  mov     [rsp+320h+phkResult], rax; phkResult
0x18000649e  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800064a5  xor     r8d, r8d; ulOptions
0x1800064a8  call    cs:__imp_RegOpenKeyExW
0x1800064ae  mov     esi, eax
0x1800064b0  test    eax, eax
0x1800064b2  jg      loc_18000662E
0x1800064b8  test    esi, esi
0x1800064ba  js      loc_1800065D1
0x1800064c0  mov     rcx, [rsp+320h+hkey]
0x1800064c5  mov     r12, rcx
0x1800064c8  test    rdi, rdi
0x1800064cb  jz      short loc_1800064F1
0x1800064cd  call    cs:__imp_GetLastError
0x1800064d3  mov     rcx, rdi; hKey
0x1800064d6  mov     r14d, eax
0x1800064d9  call    cs:__imp_RegCloseKey
0x1800064df  mov     ecx, r14d; dwErrCode
0x1800064e2  call    cs:__imp_SetLastError
0x1800064e8  mov     rcx, [rsp+320h+hkey]; hkey
0x1800064ed  mov     r14, [rbp+220h+var_2A0]
0x1800064f1  lea     rax, [rbp+220h+pcbData]
0x1800064f5  mov     [rbp+220h+pcbData], 4
0x1800064fc  mov     [rsp+320h+lpcbMaxClassLen], rax; pcbData
0x180006501  lea     r8, Value; "EnrollmentState"
0x180006508  lea     rax, [rsp+320h+pvData]
0x18000650d  mov     rdi, r12
0x180006510  xor     r12d, r12d
0x180006513  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; pvData
0x180006518  mov     r9d, 18h; dwFlags
0x18000651e  mov     [rsp+320h+phkResult], r12; pdwType
0x180006523  xor     edx, edx; lpSubKey
0x180006525  mov     [rsp+320h+pvData], r12d
0x18000652a  call    cs:__imp_RegGetValueW
0x180006530  test    eax, eax
0x180006532  jnz     loc_1800065D1
0x180006538  mov     rcx, [rsp+320h+hkey]; hkey
0x18000653d  lea     rax, [rbp+220h+var_288]
0x180006541  mov     [rsp+320h+lpcbMaxClassLen], rax; pcbData
0x180006546  lea     r8, aEnrollmenttype; "EnrollmentType"
0x18000654d  lea     rax, [rsp+320h+var_2B0]
0x180006552  mov     [rsp+320h+var_2B0], r12d
0x180006557  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; pvData
0x18000655c  mov     r9d, 18h; dwFlags
0x180006562  xor     edx, edx; lpSubKey
0x180006564  mov     [rsp+320h+phkResult], r12; pdwType
0x180006569  mov     [rbp+220h+var_288], 4
0x180006570  call    cs:__imp_RegGetValueW
0x180006576  mov     [rbp+220h+var_278], r12
0x18000657a  test    r14, r14
0x18000657d  jnz     loc_180006703
0x180006583  mov     ecx, [rsp+320h+pvData]
0x180006587  cmp     ecx, 3Fh ; '?'
0x18000658a  jz      short loc_1800065C9
0x18000658c  xor     r14b, r14b
0x18000658f  cmp     ecx, [rbp+220h+arg_20]
0x180006595  jz      short loc_1800065B3
0x180006597  mov     eax, [rsp+320h+var_2B0]
0x18000659b  mov     rdx, [rbp+220h+arg_28]
0x1800065a2  bt      rdx, rax
0x1800065a6  setb    r14b
0x1800065aa  cmp     ecx, [rbp+220h+var_284]
0x1800065ad  jz      loc_180006733
0x1800065b3  mov     rdx, [rbp+220h+var_2A0]
0x1800065b7  test    rdx, rdx
0x1800065ba  jnz     loc_18000673B
0x1800065c0  test    r14b, r14b
0x1800065c3  jnz     short loc_1800065EF
0x1800065c5  mov     r14, [rbp+220h+var_2A0]
0x1800065c9  test    r12, r12
0x1800065cc  jnz     short loc_1800065D9
0x1800065ce  xor     r12d, r12d
0x1800065d1  inc     r15d
0x1800065d4  jmp     loc_1800063F2
0x1800065d9  call    cs:__imp_GetProcessHeap
0x1800065df  mov     r8, r12; lpMem
0x1800065e2  xor     edx, edx; dwFlags
0x1800065e4  mov     rcx, rax; hHeap
0x1800065e7  call    cs:__imp_HeapFree
0x1800065ed  jmp     short loc_1800065CE
0x1800065ef  mov     rcx, r13; psz
0x1800065f2  call    cs:__imp_SysAllocString
0x1800065f8  mov     rdx, [rbp+220h+var_298]
0x1800065fc  mov     r14d, [rsp+320h+var_2C0]
0x180006601  mov     [rdx+r14*8], rax
0x180006605  test    rax, rax
0x180006608  jz      short loc_180006650
0x18000660a  inc     r14d
0x18000660d  mov     [rsp+320h+var_2C0], r14d
0x180006612  jmp     short loc_1800065C5
0x180006614  mov     rax, [rbp+220h+var_268]
0x180006618  mov     ecx, [rsp+320h+var_2C0]
0x18000661c  mov     [rax], ecx
0x18000661e  mov     rcx, [rbp+220h+var_260]
0x180006622  mov     rax, [rbp+220h+var_298]
0x180006626  mov     [rcx], rax
0x180006629  jmp     loc_180006354
0x18000662e  movzx   esi, ax
0x180006631  or      esi, 80070000h
0x180006637  jmp     loc_1800064B8
0x18000663c  mov     esi, 80070216h
0x180006641  jmp     loc_180006373
0x180006646  mov     eax, 80070057h
0x18000664b  jmp     loc_1800063A3
0x180006650  mov     esi, 8007000Eh
0x180006655  test    r12, r12
0x180006658  jnz     short loc_1800066B5
0x18000665a  xor     r12d, r12d
0x18000665d  cmp     [rsp+320h+var_2C0], 0
0x180006662  mov     r14d, r12d
0x180006665  mov     r12, [rbp+220h+var_298]
0x180006669  jz      loc_180006346
0x18000666f  mov     ebx, [rsp+320h+var_2C0]
0x180006673  mov     eax, r14d
0x180006676  mov     rcx, [r12+rax*8]; bstrString
0x18000667a  lea     r15, [r12+rax*8]
0x18000667e  test    rcx, rcx
0x180006681  jz      short loc_180006690
0x180006683  call    cs:__imp_SysFreeString
0x180006689  mov     qword ptr [r15], 0
0x180006690  inc     r14d
0x180006693  cmp     r14d, ebx
0x180006696  jb      short loc_180006673
0x180006698  mov     rbx, [rbp+220h+var_270]
0x18000669c  jmp     loc_180006346
0x1800066a1  jle     loc_18000637B
0x1800066a7  movzx   esi, ax
  ... truncated ...
```
