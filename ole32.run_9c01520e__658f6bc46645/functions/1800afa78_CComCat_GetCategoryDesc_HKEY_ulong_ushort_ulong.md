# CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)

- ea: `0x1800afa78`
- end: `0x1800afe0f`
- name: `?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z`
- size: `919`
- prototype: `HRESULT __fastcall(HKEY__ *hKey, unsigned int lcid, wchar_t **ppszDesc, unsigned int *plcid)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800afe20`
- `0x1800b5130`

## callees

- `0x180010fac`
- `0x180046460`
- `0x1800afa78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800afc4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800afd71`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800afc4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800afd71`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800afc74`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800afc74`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800afcd5`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800afcd5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afb3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afc30`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afd51`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afb3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afc30`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800afd51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afb8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afbee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afcc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afd1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afdbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afb8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afbee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afcc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afd1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800afdbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800afaf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800afaf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800afd85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800afd85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afdce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afdce`

## pseudocode

```c
HRESULT __fastcall CComCat::GetCategoryDesc(HKEY hKey, unsigned int lcid, LPVOID *ppszDesc, unsigned int *plcid)
{
  __int64 UserDefaultLCID; // rbx
  DWORD v8; // r14d
  HRESULT result; // eax
  __int16 v10; // r12
  wchar_t *v11; // rax
  unsigned int cb; // [rsp+60h] [rbp-49h] BYREF
  unsigned int dwSizeNameBuf; // [rsp+64h] [rbp-45h] BYREF
  unsigned int dwNumValues; // [rsp+68h] [rbp-41h] BYREF
  wchar_t *EndPtr; // [rsp+70h] [rbp-39h] BYREF
  wchar_t szLCID[32]; // [rsp+78h] [rbp-31h] BYREF

  LODWORD(UserDefaultLCID) = lcid;
  cb = 0;
  v8 = 0;
  dwNumValues = 0;
  dwSizeNameBuf = 16;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &dwNumValues, 0, 0, 0, 0) || !dwNumValues )
    return -2147221151;
  if ( dwNumValues == 1 )
  {
    RegEnumValueW(hKey, 0, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb);
LABEL_17:
    EndPtr = 0;
    LODWORD(UserDefaultLCID) = wcstoul(szLCID, &EndPtr, 16);
    goto $process;
  }
  result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", (unsigned int)UserDefaultLCID);
  if ( result < 0 )
    return result;
  if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
  {
    v10 = UserDefaultLCID & 0x3FF;
    LODWORD(UserDefaultLCID) = UserDefaultLCID & 0x3FF | 0x400;
    result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", (unsigned int)UserDefaultLCID);
    if ( result < 0 )
      return result;
    if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
    {
      while ( 1 )
      {
        dwSizeNameBuf = 16;
        if ( RegEnumValueW(hKey, v8, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb) )
          break;
        EndPtr = 0;
        LODWORD(UserDefaultLCID) = wcstoul(szLCID, &EndPtr, 16);
        if ( (UserDefaultLCID & 0x3FF) == v10 )
          goto $process;
        ++v8;
      }
      UserDefaultLCID = GetUserDefaultLCID();
      result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", UserDefaultLCID);
      if ( result < 0 )
        return result;
      if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
      {
        UserDefaultLCID = GetSystemDefaultLCID();
        result = StringCchPrintfW(szLCID, 0x1Eu, L"%#x", UserDefaultLCID);
        if ( result < 0 )
          return result;
        if ( RegQueryValueExW(hKey, szLCID, 0, 0, 0, &cb) )
        {
          if ( RegEnumValueW(hKey, 0, szLCID, &dwSizeNameBuf, 0, 0, 0, &cb) )
            return -2147221151;
          goto LABEL_17;
        }
      }
    }
  }
$process:
  v11 = (wchar_t *)CoTaskMemAlloc(2 * cb);
  *ppszDesc = v11;
  if ( !v11 )
    return -2147024882;
  if ( RegQueryValueExW(hKey, szLCID, 0, 0, (LPBYTE)v11, &cb) )
  {
    CoTaskMemFree(*ppszDesc);
    *ppszDesc = 0;
    return -2147221151;
  }
  if ( plcid )
    *plcid = UserDefaultLCID;
  return 0;
}

```

## disassembly

```asm
0x1800afa78  push    rbp
0x1800afa7a  push    rbx
0x1800afa7b  push    rsi
0x1800afa7c  push    rdi
0x1800afa7d  push    r12
0x1800afa7f  push    r13
0x1800afa81  push    r14
0x1800afa83  push    r15
0x1800afa85  lea     rbp, [rsp-1Fh]
0x1800afa8a  sub     rsp, 0C8h
0x1800afa91  mov     rax, cs:__security_cookie
0x1800afa98  xor     rax, rsp
0x1800afa9b  mov     [rbp+57h+var_48], rax
0x1800afa9f  xor     r13d, r13d
0x1800afaa2  lea     rax, [rbp+57h+dwNumValues]
0x1800afaa6  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800afaab  mov     r15, plcid
0x1800afaae  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800afab3  mov     rsi, ppszDesc
0x1800afab6  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800afabb  mov     ebx, lcid
0x1800afabd  mov     [rsp+100h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800afac2  lea     r12d, [r13+10h]
0x1800afac6  mov     [rsp+100h+lpcValues], rax; lpcValues
0x1800afacb  xor     r9d, r9d; lpReserved
0x1800aface  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800afad3  xor     r8d, r8d; lpcchClass
0x1800afad6  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800afadb  xor     lcid, lcid; lpClass
0x1800afadd  mov     [rsp+100h+lpcSubKeys], r13; lpcSubKeys
0x1800afae2  mov     rdi, hKey
0x1800afae5  mov     [rbp+57h+cb], r13d
0x1800afae9  mov     r14d, r13d
0x1800afaec  mov     [rbp+57h+dwNumValues], r13d
0x1800afaf0  mov     [rbp+57h+dwSizeNameBuf], r12d
0x1800afaf4  call    cs:__imp_RegQueryInfoKeyW
0x1800afafb  nop     dword ptr [rax+rax+00h]
0x1800afb00  test    eax, eax
0x1800afb02  jnz     loc_1800AFDDD
0x1800afb08  mov     eax, [rbp+57h+dwNumValues]
0x1800afb0b  test    eax, eax
0x1800afb0d  jz      loc_1800AFDDD
0x1800afb13  cmp     eax, 1
0x1800afb16  jnz     short loc_1800AFB51
0x1800afb18  lea     rax, [rbp+57h+cb]
0x1800afb1c  xor     lcid, lcid; dwIndex
0x1800afb1e  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800afb23  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800afb27  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800afb2c  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800afb30  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800afb35  mov     hKey, rdi; hKey
0x1800afb38  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800afb3d  call    cs:__imp_RegEnumValueW
0x1800afb44  nop     dword ptr [rax+rax+00h]
0x1800afb49  mov     r8d, r12d
0x1800afb4c  jmp     loc_1800AFD65
0x1800afb51  mov     r9d, ebx
0x1800afb54  lea     ppszDesc, asc_1800EAA20; "%#x"
0x1800afb5b  mov     lcid, 1Eh; cchDest
0x1800afb60  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800afb64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800afb69  test    eax, eax
0x1800afb6b  js      loc_1800AFDE2
0x1800afb71  lea     rax, [rbp+57h+cb]
0x1800afb75  xor     r9d, r9d; lpType
0x1800afb78  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800afb7d  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800afb81  xor     r8d, r8d; lpReserved
0x1800afb84  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800afb89  mov     hKey, rdi; hKey
0x1800afb8c  call    cs:__imp_RegQueryValueExW
0x1800afb93  nop     dword ptr [rax+rax+00h]
0x1800afb98  test    eax, eax
0x1800afb9a  jz      $process
0x1800afba0  mov     eax, 3FFh
0x1800afba5  lea     ppszDesc, asc_1800EAA20; "%#x"
0x1800afbac  and     bx, ax
0x1800afbaf  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800afbb3  movzx   r12d, bx
0x1800afbb7  mov     lcid, 1Eh; cchDest
0x1800afbbc  mov     ebx, r12d
0x1800afbbf  bts     ebx, 0Ah
0x1800afbc3  mov     r9d, ebx
0x1800afbc6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800afbcb  test    eax, eax
0x1800afbcd  js      loc_1800AFDE2
0x1800afbd3  lea     rax, [rbp+57h+cb]
0x1800afbd7  xor     r9d, r9d; lpType
0x1800afbda  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800afbdf  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800afbe3  xor     r8d, r8d; lpReserved
0x1800afbe6  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800afbeb  mov     hKey, rdi; hKey
0x1800afbee  call    cs:__imp_RegQueryValueExW
0x1800afbf5  nop     dword ptr [rax+rax+00h]
0x1800afbfa  test    eax, eax
0x1800afbfc  jz      $process
0x1800afc02  lea     rax, [rbp+57h+cb]
0x1800afc06  mov     ebx, 10h
0x1800afc0b  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800afc10  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800afc14  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800afc19  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800afc1d  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800afc22  mov     lcid, r14d; dwIndex
0x1800afc25  mov     hKey, rdi; hKey
0x1800afc28  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800afc2d  mov     [rbp+57h+dwSizeNameBuf], ebx
0x1800afc30  call    cs:__imp_RegEnumValueW
0x1800afc37  nop     dword ptr [rax+rax+00h]
0x1800afc3c  test    eax, eax
0x1800afc3e  jnz     short loc_1800AFC74
0x1800afc40  mov     r8d, ebx; Radix
0x1800afc43  mov     [rbp+57h+EndPtr], r13
0x1800afc47  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800afc4b  lea     hKey, [rbp+57h+szLCID]; String
0x1800afc4f  call    cs:__imp_wcstoul
0x1800afc56  nop     dword ptr [rax+rax+00h]
0x1800afc5b  mov     ecx, 3FFh
0x1800afc60  mov     ebx, eax
0x1800afc62  and     ax, cx
0x1800afc65  cmp     ax, r12w
0x1800afc69  jz      $process
0x1800afc6f  inc     r14d
0x1800afc72  jmp     short loc_1800AFC02
0x1800afc74  call    cs:__imp_GetUserDefaultLCID
0x1800afc7b  nop     dword ptr [rax+rax+00h]
0x1800afc80  mov     r14d, 1Eh
0x1800afc86  lea     ppszDesc, asc_1800EAA20; "%#x"
0x1800afc8d  mov     r9d, eax
0x1800afc90  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800afc94  mov     lcid, r14d; cchDest
0x1800afc97  mov     ebx, eax
0x1800afc99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800afc9e  test    eax, eax
0x1800afca0  js      loc_1800AFDE2
0x1800afca6  lea     rax, [rbp+57h+cb]
0x1800afcaa  xor     r9d, r9d; lpType
0x1800afcad  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800afcb2  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800afcb6  xor     r8d, r8d; lpReserved
0x1800afcb9  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800afcbe  mov     hKey, rdi; hKey
0x1800afcc1  call    cs:__imp_RegQueryValueExW
0x1800afcc8  nop     dword ptr [rax+rax+00h]
0x1800afccd  test    eax, eax
0x1800afccf  jz      $process
0x1800afcd5  call    cs:__imp_GetSystemDefaultLCID
0x1800afcdc  nop     dword ptr [rax+rax+00h]
0x1800afce1  lea     ppszDesc, asc_1800EAA20; "%#x"
0x1800afce8  mov     lcid, r14d; cchDest
0x1800afceb  mov     r9d, eax
0x1800afcee  lea     hKey, [rbp+57h+szLCID]; pszDest
0x1800afcf2  mov     ebx, eax
0x1800afcf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800afcf9  test    eax, eax
0x1800afcfb  js      loc_1800AFDE2
0x1800afd01  lea     rax, [rbp+57h+cb]
0x1800afd05  xor     r9d, r9d; lpType
0x1800afd08  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800afd0d  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800afd11  xor     r8d, r8d; lpReserved
0x1800afd14  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x1800afd19  mov     hKey, rdi; hKey
0x1800afd1c  call    cs:__imp_RegQueryValueExW
0x1800afd23  nop     dword ptr [rax+rax+00h]
0x1800afd28  test    eax, eax
0x1800afd2a  jz      short $process
0x1800afd2c  lea     rax, [rbp+57h+cb]
0x1800afd30  xor     lcid, lcid; dwIndex
0x1800afd32  mov     [rsp+100h+lpcValues], rax; lpcbData
0x1800afd37  lea     plcid, [rbp+57h+dwSizeNameBuf]; lpcchValueName
0x1800afd3b  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x1800afd40  lea     ppszDesc, [rbp+57h+szLCID]; lpValueName
0x1800afd44  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x1800afd49  mov     hKey, rdi; hKey
0x1800afd4c  mov     [rsp+100h+lpcSubKeys], r13; lpReserved
0x1800afd51  call    cs:__imp_RegEnumValueW
0x1800afd58  nop     dword ptr [rax+rax+00h]
0x1800afd5d  test    eax, eax
0x1800afd5f  jnz     short loc_1800AFDDD
0x1800afd61  lea     r8d, [r14-0Eh]; Radix
0x1800afd65  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800afd69  mov     [rbp+57h+EndPtr], r13
0x1800afd6d  lea     hKey, [rbp+57h+szLCID]; String
0x1800afd71  call    cs:__imp_wcstoul
0x1800afd78  nop     dword ptr [rax+rax+00h]
0x1800afd7d  mov     ebx, eax
0x1800afd7f  mov     eax, [rbp+57h+cb]
0x1800afd82  lea     ecx, [rax+rax]; cb
0x1800afd85  call    cs:__imp_CoTaskMemAlloc
0x1800afd8c  nop     dword ptr [rax+rax+00h]
0x1800afd91  mov     [rsi], rax
0x1800afd94  test    rax, rax
0x1800afd97  jnz     short loc_1800AFDA0
0x1800afd99  mov     eax, 8007000Eh
0x1800afd9e  jmp     short loc_1800AFDE2
0x1800afda0  lea     hKey, [rbp+57h+cb]
0x1800afda4  xor     r9d, r9d; lpType
0x1800afda7  mov     [rsp+100h+lpcbMaxSubKeyLen], hKey; lpcbData
0x1800afdac  lea     rdx, [rbp+57h+szLCID]; lpValueName
0x1800afdb0  mov     hKey, rdi; hKey
0x1800afdb3  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x1800afdb8  xor     r8d, r8d; lpReserved
0x1800afdbb  call    cs:__imp_RegQueryValueExW
0x1800afdc2  nop     dword ptr [rax+rax+00h]
0x1800afdc7  test    eax, eax
0x1800afdc9  jz      short loc_1800AFE03
0x1800afdcb  mov     hKey, [rsi]; pv
0x1800afdce  call    cs:__imp_CoTaskMemFree
0x1800afdd5  nop     dword ptr [rax+rax+00h]
0x1800afdda  mov     [rsi], r13
0x1800afddd  mov     eax, 80040161h
0x1800afde2  mov     hKey, [rbp+57h+var_48]
0x1800afde6  xor     hKey, rsp; StackCookie
0x1800afde9  call    __security_check_cookie
0x1800afdee  add     rsp, 0C8h
0x1800afdf5  pop     r15
0x1800afdf7  pop     r14
0x1800afdf9  pop     r13
0x1800afdfb  pop     r12
0x1800afdfd  pop     rdi
0x1800afdfe  pop     rsi
0x1800afdff  pop     rbx
0x1800afe00  pop     rbp
0x1800afe01  retn
0x1800afe03  test    r15, r15
0x1800afe06  jz      short loc_1800AFE0B
0x1800afe08  mov     [r15], ebx
0x1800afe0b  xor     eax, eax
0x1800afe0d  jmp     short loc_1800AFDE2
```
