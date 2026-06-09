# EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(ulong *,ushort * * *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)

- ea: `0x18003d94c`
- end: `0x18003deaa`
- name: `?GetAllEnrollmentIDsFiltered@EnrollmentInfoEnumerator@@AEAAJPEAKPEAPEAPEAGW4EnrollmentStateTag@@2_KPEBGHH@Z`
- size: `1374`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003deb0`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000bd7c`
- `0x18003cd7c`
- `0x18003d170`
- `0x18003d830`
- `0x18003d94c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003dcf8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003dcf8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003dd17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003dd17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dd6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ddc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dd6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ddc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dd5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ddae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dd5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ddae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dba3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dbc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dbc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003da31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003da31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dc0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dc57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dc0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dc57`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003db32`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003db32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dbb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003de4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003de68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dbb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003de4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003de68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003da75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003da75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003de24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003de38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003de24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003de38`
- `OLEAUT32!__imp_SysAllocString` at `0x18003dd34`
- `OLEAUT32!__imp_SysAllocString` at `0x18003dd34`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dde6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dde6`

## pseudocode

```c
__int64 __fastcall EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(
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
  const WCHAR *EnrollmentsRootKey; // rax
  int v10; // eax
  signed int v11; // r14d
  HKEY v12; // rdi
  LSTATUS v13; // eax
  unsigned __int64 v14; // rax
  size_t v15; // rsi
  void *v16; // r13
  _WORD *v17; // r15
  HKEY v18; // rbx
  unsigned __int64 v19; // rax
  unsigned __int16 *v20; // rsi
  DWORD v21; // ecx
  unsigned int v22; // r12d
  LSTATUS v23; // eax
  const unsigned __int16 *v24; // rax
  HKEY v25; // rcx
  HKEY v26; // rax
  DWORD LastError; // esi
  __int64 v28; // rdx
  const WCHAR *v29; // rdx
  int v31; // eax
  int v32; // eax
  __int64 v33; // r8
  BSTR v34; // rax
  HANDLE v35; // rax
  HANDLE ProcessHeap; // rax
  unsigned int v37; // eax
  OLECHAR *v38; // rcx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v42; // [rsp+68h] [rbp-98h]
  int pvData; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+74h] [rbp-8Ch]
  DWORD v46; // [rsp+78h] [rbp-88h]
  HKEY hkey; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v48; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v51; // [rsp+98h] [rbp-68h] BYREF
  int v52; // [rsp+9Ch] [rbp-64h]
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h]
  unsigned int *v55; // [rsp+B8h] [rbp-48h]
  _QWORD *v56; // [rsp+C0h] [rbp-40h]
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF

  v52 = a4;
  v56 = a3;
  v55 = a2;
  v54 = a7;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  hkey = 0;
  SubKey[0] = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  *a3 = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v10 = EEDBManager::OpenHKEY(EnrollmentsRootKey, 0x20019u, &hKey);
  v11 = v10;
  if ( v10 == -2147024894 )
    return 0;
  if ( v10 < 0 )
    return (unsigned int)v11;
  v12 = hKey;
  v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v11 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_66;
  }
  v14 = 8LL * cSubKeys;
  if ( v14 <= 0xFFFFFFFF )
  {
    v15 = (unsigned int)v14;
    v16 = CoTaskMemAlloc((unsigned int)v14);
    if ( !v16 )
    {
      v11 = -2147024882;
      goto LABEL_66;
    }
    v17 = 0;
    v18 = 0;
    memset_0(v16, 0, v15);
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
    }
    else
    {
      v19 = 2LL * ++cbMaxSubKeyLen;
      if ( v19 <= 0xFFFFFFFF )
      {
        v20 = 0;
        v17 = CoTaskMemAlloc((unsigned int)v19);
        if ( v17 )
        {
          v21 = 0;
          v22 = 0;
          v11 = 0;
          v46 = 0;
          v42 = 0;
          if ( !cSubKeys )
          {
LABEL_47:
            *v55 = v22;
            *v56 = v16;
LABEL_62:
            CoTaskMemFree(v17);
LABEL_63:
            if ( v18 )
              RegCloseKey(v18);
            goto LABEL_66;
          }
          while ( 1 )
          {
            cchName = cbMaxSubKeyLen;
            *v17 = 0;
            v23 = RegEnumKeyExW(v12, v21, v17, &cchName, 0, 0, 0, 0);
            v11 = v23;
            if ( v23 )
              break;
            v24 = EEDBManager::GetEnrollmentsRootKey();
            v11 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v24, v17);
            if ( v11 < 0 )
              goto LABEL_51;
            v11 = EEDBManager::OpenHKEY(SubKey, 0x20019u, &hkey);
            if ( v11 >= 0 )
            {
              v25 = hkey;
              v48 = (unsigned __int16 *)hkey;
              v26 = hkey;
              if ( v18 )
              {
                LastError = GetLastError();
                RegCloseKey(v18);
                SetLastError(LastError);
                v25 = hkey;
                v20 = 0;
                v26 = (HKEY)v48;
              }
              v18 = v26;
              pvData = 0;
              pcbData = 4;
              if ( !RegGetValueW(v25, 0, L"EnrollmentState", 0x18u, 0, &pvData, &pcbData) )
              {
                v44 = 0;
                v51 = 4;
                RegGetValueW(hkey, 0, L"EnrollmentType", 0x18u, 0, &v44, &v51);
                v28 = v54;
                v48 = 0;
                if ( v54 )
                {
                  v29 = L"PartnerOpaqueID";
                  if ( !a8 )
                    v29 = L"AADOpaqueID";
                  AllocAndGetEnrollmentString(hkey, v29, &v48);
                  v28 = v54;
                  v20 = v48;
                }
                if ( pvData != 63 )
                {
                  LOBYTE(v45) = 0;
                  if ( pvData != a5 )
                  {
                    v31 = _bittest64(&a6, v44);
                    if ( pvData == v52 )
                      v31 = 1;
                    v45 = v31;
                  }
                  if ( v28 && v20 )
                  {
                    if ( a9 )
                    {
                      v33 = -1;
                      do
                        ++v33;
                      while ( *(_WORD *)(v28 + 2 * v33) );
                      v32 = _o__wcsnicmp(v20, v28, v33, 0);
                    }
                    else
                    {
                      v32 = _o__wcsicmp(v20, v28);
                    }
                    if ( !v32 )
                      goto LABEL_41;
                  }
                  if ( (_BYTE)v45 )
                  {
LABEL_41:
                    v34 = SysAllocString(v17);
                    *((_QWORD *)v16 + v22) = v34;
                    if ( !v34 )
                    {
                      v11 = -2147024882;
                      if ( v20 )
                      {
                        ProcessHeap = GetProcessHeap();
                        HeapFree(ProcessHeap, 0, v20);
                      }
                      LODWORD(v20) = 0;
                      goto LABEL_51;
                    }
                    v42 = ++v22;
                  }
                }
                if ( v20 )
                {
                  v35 = GetProcessHeap();
                  HeapFree(v35, 0, v20);
                }
                v20 = 0;
              }
            }
            v21 = v46 + 1;
            v46 = v21;
            if ( v21 >= cSubKeys )
              goto LABEL_47;
          }
          if ( v23 > 0 )
            v11 = (unsigned __int16)v23 | 0x80070000;
LABEL_51:
          if ( v22 )
          {
            v37 = v42;
            do
            {
              v38 = (OLECHAR *)*((_QWORD *)v16 + (unsigned int)v20);
              if ( v38 )
              {
                SysFreeString(v38);
                v37 = v42;
                *((_QWORD *)v16 + (unsigned int)v20) = 0;
              }
              LODWORD(v20) = (_DWORD)v20 + 1;
            }
            while ( (unsigned int)v20 < v37 );
          }
        }
        else
        {
          v11 = -2147024882;
        }
LABEL_61:
        CoTaskMemFree(v16);
        if ( !v17 )
          goto LABEL_63;
        goto LABEL_62;
      }
    }
    v11 = -2147024362;
    goto LABEL_61;
  }
  v11 = -2147024362;
LABEL_66:
  if ( v12 )
    RegCloseKey(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003d94c  mov     [rsp-8+arg_0], rbx
0x18003d951  push    rbp
0x18003d952  push    rsi
0x18003d953  push    rdi
0x18003d954  push    r12
0x18003d956  push    r13
0x18003d958  push    r14
0x18003d95a  push    r15
0x18003d95c  lea     rbp, [rsp-1F0h]
0x18003d964  sub     rsp, 2F0h
0x18003d96b  mov     rax, cs:__security_cookie
0x18003d972  xor     rax, rsp
0x18003d975  mov     [rbp+220h+var_40], rax
0x18003d97c  mov     rax, [rbp+220h+arg_30]
0x18003d983  xor     esi, esi
0x18003d985  mov     [rbp+220h+var_284], r9d
0x18003d989  mov     [rbp+220h+var_260], r8
0x18003d98d  mov     [rbp+220h+var_268], rdx
0x18003d991  mov     [rbp+220h+var_278], rax
0x18003d995  mov     [rsp+320h+cSubKeys], esi
0x18003d999  mov     [rsp+320h+cbMaxSubKeyLen], esi
0x18003d99d  mov     [rbp+220h+hKey], rsi
0x18003d9a1  mov     [rbp+220h+hkey], rsi
0x18003d9a5  mov     [rbp+220h+SubKey], si
0x18003d9a9  test    rdx, rdx
0x18003d9ac  jz      loc_18003DE76
0x18003d9b2  test    r8, r8
0x18003d9b5  jz      loc_18003DE76
0x18003d9bb  mov     [rdx], esi
0x18003d9bd  mov     [r8], rsi
0x18003d9c0  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003d9c5  mov     rcx, rax; lpSubKey
0x18003d9c8  lea     r8, [rbp+220h+hKey]; HKEY *
0x18003d9cc  mov     edx, 20019h; unsigned int
0x18003d9d1  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18003d9d6  mov     r14d, eax
0x18003d9d9  cmp     eax, 80070002h
0x18003d9de  jnz     short loc_18003D9E8
0x18003d9e0  mov     r14d, esi
0x18003d9e3  jmp     loc_18003DE7C
0x18003d9e8  test    eax, eax
0x18003d9ea  js      loc_18003DE7C
0x18003d9f0  mov     rdi, [rbp+220h+hKey]
0x18003d9f4  lea     rax, [rsp+320h+cbMaxSubKeyLen]
0x18003d9f9  mov     [rsp+320h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003d9fe  xor     r9d, r9d; lpReserved
0x18003da01  mov     [rsp+320h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18003da06  xor     r8d, r8d; lpcchClass
0x18003da09  mov     [rsp+320h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18003da0e  xor     edx, edx; lpClass
0x18003da10  mov     [rsp+320h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18003da15  mov     rcx, rdi; hKey
0x18003da18  mov     [rsp+320h+lpcValues], rsi; lpcValues
0x18003da1d  mov     [rsp+320h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18003da22  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003da27  lea     rax, [rsp+320h+cSubKeys]
0x18003da2c  mov     [rsp+320h+lpcSubKeys], rax; lpcSubKeys
0x18003da31  call    cs:__imp_RegQueryInfoKeyW
0x18003da38  nop     dword ptr [rax+rax+00h]
0x18003da3d  mov     r14d, eax
0x18003da40  test    eax, eax
0x18003da42  jz      short loc_18003DA5A
0x18003da44  jle     loc_18003DE60
0x18003da4a  movzx   r14d, ax
0x18003da4e  or      r14d, 80070000h
0x18003da55  jmp     loc_18003DE60
0x18003da5a  mov     eax, [rsp+320h+cSubKeys]
0x18003da5e  mov     r14d, 0FFFFFFFFh
0x18003da64  shl     rax, 3
0x18003da68  cmp     rax, r14
0x18003da6b  ja      loc_18003DE5A
0x18003da71  mov     ecx, eax; cb
0x18003da73  mov     esi, eax
0x18003da75  call    cs:__imp_CoTaskMemAlloc
0x18003da7c  nop     dword ptr [rax+rax+00h]
0x18003da81  mov     r13, rax
0x18003da84  xor     eax, eax
0x18003da86  test    r13, r13
0x18003da89  jnz     short loc_18003DA96
0x18003da8b  mov     r14d, 8007000Eh
0x18003da91  jmp     loc_18003DE60
0x18003da96  mov     r8, rsi; Size
0x18003da99  xor     edx, edx; Val
0x18003da9b  mov     rcx, r13; void *
0x18003da9e  mov     r15, rax
0x18003daa1  mov     rbx, rax
0x18003daa4  call    memset_0
0x18003daa9  mov     eax, [rsp+320h+cbMaxSubKeyLen]
0x18003daad  lea     ecx, [rax+1]
0x18003dab0  cmp     ecx, eax
0x18003dab2  jb      loc_18003DE16
0x18003dab8  mov     eax, ecx
0x18003daba  add     rax, rax
0x18003dabd  mov     [rsp+320h+cbMaxSubKeyLen], ecx
0x18003dac1  cmp     rax, r14
0x18003dac4  ja      loc_18003DE1B
0x18003daca  mov     ecx, eax; cb
0x18003dacc  call    cs:__imp_CoTaskMemAlloc
0x18003dad3  nop     dword ptr [rax+rax+00h]
0x18003dad8  xor     esi, esi
0x18003dada  mov     r15, rax
0x18003dadd  test    rax, rax
0x18003dae0  jnz     short loc_18003DAED
0x18003dae2  mov     r14d, 8007000Eh
0x18003dae8  jmp     loc_18003DE21
0x18003daed  mov     ecx, esi
0x18003daef  mov     r12d, esi
0x18003daf2  mov     r14d, esi
0x18003daf5  mov     [rsp+320h+var_2A8], ecx
0x18003daf9  mov     [rsp+320h+var_2B8], esi
0x18003dafd  cmp     [rsp+320h+cSubKeys], esi
0x18003db01  jbe     loc_18003DD90
0x18003db07  mov     eax, [rsp+320h+cbMaxSubKeyLen]
0x18003db0b  lea     r9, [rbp+220h+cchName]; lpcchName
0x18003db0f  mov     [rsp+320h+lpcValues], rsi; lpftLastWriteTime
0x18003db14  mov     edx, ecx; dwIndex
0x18003db16  mov     [rsp+320h+lpcbMaxClassLen], rsi; lpcchClass
0x18003db1b  mov     r8, r15; lpName
0x18003db1e  mov     [rsp+320h+lpcbMaxSubKeyLen], rsi; lpClass
0x18003db23  mov     rcx, rdi; hKey
0x18003db26  mov     [rsp+320h+lpcSubKeys], rsi; lpReserved
0x18003db2b  mov     [rbp+220h+cchName], eax
0x18003db2e  mov     [r15], si
0x18003db32  call    cs:__imp_RegEnumKeyExW
0x18003db39  nop     dword ptr [rax+rax+00h]
0x18003db3e  mov     r14d, eax
0x18003db41  test    eax, eax
0x18003db43  jnz     loc_18003DE07
0x18003db49  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003db4e  mov     r9, rax
0x18003db51  mov     [rsp+320h+lpcSubKeys], r15
0x18003db56  lea     r8, aSS; "%s\\%s"
0x18003db5d  mov     edx, 104h; unsigned __int64
0x18003db62  lea     rcx, [rbp+220h+SubKey]; unsigned __int16 *
0x18003db66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003db6b  mov     r14d, eax
0x18003db6e  test    eax, eax
0x18003db70  js      loc_18003DDD0
0x18003db76  lea     r8, [rbp+220h+hkey]; HKEY *
0x18003db7a  mov     edx, 20019h; unsigned int
0x18003db7f  lea     rcx, [rbp+220h+SubKey]; lpSubKey
0x18003db83  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18003db88  mov     r14d, eax
0x18003db8b  test    eax, eax
0x18003db8d  js      loc_18003DD7C
0x18003db93  mov     rcx, [rbp+220h+hkey]
0x18003db97  mov     [rbp+220h+var_298], rcx
0x18003db9b  mov     rax, rcx
0x18003db9e  test    rbx, rbx
0x18003dba1  jz      short loc_18003DBD8
0x18003dba3  call    cs:__imp_GetLastError
0x18003dbaa  nop     dword ptr [rax+rax+00h]
0x18003dbaf  mov     rcx, rbx; hKey
0x18003dbb2  mov     esi, eax
0x18003dbb4  call    cs:__imp_RegCloseKey
0x18003dbbb  nop     dword ptr [rax+rax+00h]
0x18003dbc0  mov     ecx, esi; dwErrCode
0x18003dbc2  call    cs:__imp_SetLastError
0x18003dbc9  nop     dword ptr [rax+rax+00h]
0x18003dbce  mov     rcx, [rbp+220h+hkey]; hkey
0x18003dbd2  xor     esi, esi
0x18003dbd4  mov     rax, [rbp+220h+var_298]
0x18003dbd8  mov     rbx, rax
0x18003dbdb  mov     [rsp+320h+pvData], esi
0x18003dbdf  lea     rax, [rbp+220h+pcbData]
0x18003dbe3  mov     [rbp+220h+pcbData], 4
0x18003dbea  mov     [rsp+320h+lpcbMaxClassLen], rax; pcbData
0x18003dbef  lea     r8, aEnrollmentstat; "EnrollmentState"
0x18003dbf6  lea     rax, [rsp+320h+pvData]
0x18003dbfb  mov     r9d, 18h; dwFlags
0x18003dc01  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; pvData
0x18003dc06  xor     edx, edx; lpSubKey
0x18003dc08  mov     [rsp+320h+lpcSubKeys], rsi; pdwType
0x18003dc0d  call    cs:__imp_RegGetValueW
0x18003dc14  nop     dword ptr [rax+rax+00h]
0x18003dc19  test    eax, eax
0x18003dc1b  jnz     loc_18003DD7C
0x18003dc21  mov     rcx, [rbp+220h+hkey]; hkey
0x18003dc25  lea     rax, [rbp+220h+var_288]
0x18003dc29  mov     [rsp+320h+lpcbMaxClassLen], rax; pcbData
0x18003dc2e  lea     r8, aEnrollmenttype; "EnrollmentType"
0x18003dc35  lea     rax, [rsp+320h+var_2B0]
0x18003dc3a  mov     [rsp+320h+var_2B0], esi
0x18003dc3e  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; pvData
0x18003dc43  mov     r9d, 18h; dwFlags
0x18003dc49  xor     edx, edx; lpSubKey
0x18003dc4b  mov     [rsp+320h+lpcSubKeys], rsi; pdwType
0x18003dc50  mov     [rbp+220h+var_288], 4
0x18003dc57  call    cs:__imp_RegGetValueW
0x18003dc5e  nop     dword ptr [rax+rax+00h]
0x18003dc63  mov     rdx, [rbp+220h+var_278]
0x18003dc67  xor     r9d, r9d
0x18003dc6a  mov     [rbp+220h+var_298], rsi
0x18003dc6e  test    rdx, rdx
0x18003dc71  jz      short loc_18003DCA4
0x18003dc73  cmp     [rbp+220h+arg_38], r9d
0x18003dc7a  lea     rax, aAadopaqueid; "AADOpaqueID"
0x18003dc81  mov     rcx, [rbp+220h+hkey]; hkey
0x18003dc85  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x18003dc8c  cmovz   rdx, rax; lpValue
0x18003dc90  lea     r8, [rbp+220h+var_298]; unsigned __int16 **
0x18003dc94  call    ?AllocAndGetEnrollmentString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; AllocAndGetEnrollmentString(HKEY__ *,ushort const *,ushort * *)
0x18003dc99  mov     rdx, [rbp+220h+var_278]
0x18003dc9d  xor     r9d, r9d
0x18003dca0  mov     rsi, [rbp+220h+var_298]
0x18003dca4  mov     ecx, [rsp+320h+pvData]
0x18003dca8  cmp     ecx, 3Fh ; '?'
0x18003dcab  jz      loc_18003DD55
0x18003dcb1  mov     byte ptr [rsp+320h+var_2AC], r9b
0x18003dcb6  cmp     ecx, [rbp+220h+arg_20]
0x18003dcbc  jz      short loc_18003DCE2
0x18003dcbe  mov     eax, [rsp+320h+var_2B0]
0x18003dcc2  mov     r8, [rbp+220h+arg_28]
0x18003dcc9  bt      r8, rax
0x18003dccd  setb    al
0x18003dcd0  cmp     ecx, [rbp+220h+var_284]
0x18003dcd3  movzx   eax, al
0x18003dcd6  mov     ecx, 1
0x18003dcdb  cmovz   eax, ecx
0x18003dcde  mov     [rsp+320h+var_2AC], eax
0x18003dce2  test    rdx, rdx
0x18003dce5  jz      short loc_18003DD2A
0x18003dce7  test    rsi, rsi
0x18003dcea  jz      short loc_18003DD2A
0x18003dcec  cmp     [rbp+220h+arg_40], r9d
0x18003dcf3  jnz     short loc_18003DD06
0x18003dcf5  mov     rcx, rsi
0x18003dcf8  call    cs:__imp__o__wcsicmp
0x18003dcff  nop     dword ptr [rax+rax+00h]
0x18003dd04  jmp     short loc_18003DD23
0x18003dd06  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003dd0a  inc     r8
0x18003dd0d  cmp     [rdx+r8*2], r9w
0x18003dd12  jnz     short loc_18003DD0A
0x18003dd14  mov     rcx, rsi
0x18003dd17  call    cs:__imp__o__wcsnicmp
0x18003dd1e  nop     dword ptr [rax+rax+00h]
0x18003dd23  xor     r9d, r9d
0x18003dd26  test    eax, eax
0x18003dd28  jz      short loc_18003DD31
0x18003dd2a  cmp     byte ptr [rsp+320h+var_2AC], r9b
0x18003dd2f  jz      short loc_18003DD55
0x18003dd31  mov     rcx, r15; psz
0x18003dd34  call    cs:__imp_SysAllocString
0x18003dd3b  nop     dword ptr [rax+rax+00h]
0x18003dd40  mov     ecx, r12d
0x18003dd43  mov     [r13+rcx*8+0], rax
0x18003dd48  test    rax, rax
0x18003dd4b  jz      short loc_18003DDA3
0x18003dd4d  inc     r12d
0x18003dd50  mov     [rsp+320h+var_2B8], r12d
0x18003dd55  test    rsi, rsi
0x18003dd58  jz      short loc_18003DD7A
0x18003dd5a  call    cs:__imp_GetProcessHeap
0x18003dd61  nop     dword ptr [rax+rax+00h]
0x18003dd66  mov     r8, rsi; lpMem
0x18003dd69  xor     edx, edx; dwFlags
0x18003dd6b  mov     rcx, rax; hHeap
0x18003dd6e  call    cs:__imp_HeapFree
0x18003dd75  nop     dword ptr [rax+rax+00h]
0x18003dd7a  xor     esi, esi
0x18003dd7c  mov     ecx, [rsp+320h+var_2A8]
0x18003dd80  inc     ecx
0x18003dd82  mov     [rsp+320h+var_2A8], ecx
0x18003dd86  cmp     ecx, [rsp+320h+cSubKeys]
0x18003dd8a  jb      loc_18003DB07
0x18003dd90  mov     rax, [rbp+220h+var_268]
0x18003dd94  mov     [rax], r12d
0x18003dd97  mov     rax, [rbp+220h+var_260]
0x18003dd9b  mov     [rax], r13
0x18003dd9e  jmp     loc_18003DE35
0x18003dda3  mov     r14d, 8007000Eh
0x18003dda9  test    rsi, rsi
0x18003ddac  jz      short loc_18003DDCE
0x18003ddae  call    cs:__imp_GetProcessHeap
0x18003ddb5  nop     dword ptr [rax+rax+00h]
0x18003ddba  mov     r8, rsi; lpMem
0x18003ddbd  xor     edx, edx; dwFlags
0x18003ddbf  mov     rcx, rax; hHeap
0x18003ddc2  call    cs:__imp_HeapFree
0x18003ddc9  nop     dword ptr [rax+rax+00h]
0x18003ddce  xor     esi, esi
0x18003ddd0  test    r12d, r12d
0x18003ddd3  jz      short loc_18003DE21
0x18003ddd5  mov     eax, [rsp+320h+var_2B8]
0x18003ddd9  mov     r12d, esi
0x18003dddc  mov     rcx, [r13+r12*8+0]; bstrString
0x18003dde1  test    rcx, rcx
0x18003dde4  jz      short loc_18003DDFF
0x18003dde6  call    cs:__imp_SysFreeString
0x18003dded  nop     dword ptr [rax+rax+00h]
0x18003ddf2  mov     eax, [rsp+320h+var_2B8]
0x18003ddf6  mov     qword ptr [r13+r12*8+0], 0
0x18003ddff  inc     esi
0x18003de01  cmp     esi, eax
0x18003de03  jb      short loc_18003DDD9
0x18003de05  jmp     short loc_18003DE21
0x18003de07  jle     short loc_18003DDD0
0x18003de09  movzx   r14d, ax
0x18003de0d  or      r14d, 80070000h
  ... truncated ...
```
