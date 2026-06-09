# RegScanUtil::GetSupportDll(ushort * *)

- ea: `0x180052840`
- end: `0x180052c89`
- name: `?GetSupportDll@RegScanUtil@@SAJPEAPEAG@Z`
- size: `1097`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000eaf8`

## callees

- `0x180001e60`
- `0x180052840`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005298e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800529e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005298e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800529e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052943`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800528bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800528bd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180052afb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180052afb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c56`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005290d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005290d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052934`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052934`

## string_xrefs

- `0x1800528af`: `SOFTWARE\Microsoft\COM3\RegistrationSupportDlls`
- `0x18005292d`: `%systemroot%\system32\ATL.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegScanUtil::GetSupportDll(unsigned __int16 **a1)
{
  __int64 v2; // rax
  DWORD v3; // ecx
  DWORD v4; // ecx
  void *v5; // rcx
  unsigned int v6; // ebx
  DWORD j; // ebx
  void *v8; // rax
  unsigned __int64 v9; // rcx
  void *v10; // rcx
  DWORD v11; // edx
  __int64 v12; // r14
  int v13; // eax
  unsigned int v14; // eax
  DWORD i; // ecx
  unsigned int v16; // edx
  DWORD k; // edi
  void *v18; // rcx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Dst[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    goto LABEL_47;
  }
  *a1 = 0;
  if ( qword_180075388 )
  {
    v6 = 0;
LABEL_34:
    v14 = -1;
    while ( 2 )
    {
      for ( i = 0; i < cValues; ++i )
      {
        v16 = *((_DWORD *)qword_180075380 + i);
        if ( v16 )
        {
          if ( v16 == dword_180075374 )
          {
            *((_DWORD *)qword_180075380 + i) = 0;
            *a1 = (unsigned __int16 *)*((_QWORD *)qword_180075388 + i);
            return v6;
          }
          if ( v14 >= v16 )
            v14 = *((_DWORD *)qword_180075380 + i);
        }
      }
      if ( dword_180075374 < v14 && v14 != -1 )
      {
        dword_180075374 = v14;
        continue;
      }
      break;
    }
    goto LABEL_47;
  }
  cbMaxValueNameLen = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3\\RegistrationSupportDlls", 0, 0x20019u, &hKey)
    && RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0) )
  {
    cValues = 0;
    cbMaxValueNameLen = 0;
  }
  if ( ExpandEnvironmentStringsW(L"%systemroot%\\system32\\ATL.DLL", Dst, 0x105u) - 1 > 0x104 )
    GetLastError();
  v2 = -1;
  do
    ++v2;
  while ( Dst[v2] );
  v3 = cbMaxValueNameLen;
  if ( cbMaxValueNameLen <= (unsigned int)v2 )
    v3 = v2;
  v4 = v3 + 1;
  if ( v4 )
  {
    cbMaxValueNameLen = v4;
    v5 = CoTaskMemAlloc(saturated_mul(cValues + 1, 8u));
    qword_180075388 = v5;
    if ( !v5 )
      goto LABEL_14;
    memset_0(v5, 0, 8LL * (cValues + 1));
    for ( j = 0; j < cValues + 1; ++j )
    {
      v8 = CoTaskMemAlloc(saturated_mul(cbMaxValueNameLen, 2u));
      *((_QWORD *)qword_180075388 + j) = v8;
      if ( !v8 )
        goto LABEL_14;
      v9 = 2LL * cbMaxValueNameLen;
      if ( v9 > 0xFFFFFFFF )
        goto LABEL_32;
      memset_0(v8, 0, (unsigned int)v9);
    }
    v10 = CoTaskMemAlloc(saturated_mul(cValues + 1, 4u));
    qword_180075380 = v10;
    if ( !v10 )
    {
LABEL_14:
      v6 = -2147024882;
      goto LABEL_47;
    }
    memset_0(v10, 0, 4LL * (cValues + 1));
    v6 = StringCchCopyW(*(unsigned __int16 **)qword_180075388, cbMaxValueNameLen, Dst);
    if ( v6 )
      goto LABEL_47;
    *(_DWORD *)qword_180075380 = 1;
    dword_180075374 = 1;
    v11 = 0;
    if ( cValues )
    {
      do
      {
        cchValueName = cbMaxValueNameLen;
        Type = 0;
        cbData = 4;
        v12 = v11 + 1;
        if ( RegEnumValueW(
               hKey,
               v11,
               *((LPWSTR *)qword_180075388 + v12),
               &cchValueName,
               0,
               &Type,
               (LPBYTE)qword_180075380 + 4 * v12,
               &cbData)
          || Type != 4 )
        {
          *((_DWORD *)qword_180075380 + v12) = 0;
        }
        else
        {
          v13 = *((_DWORD *)qword_180075380 + v12);
          if ( v13 )
            *((_DWORD *)qword_180075380 + v12) = v13 + 1;
        }
        v11 = v12;
      }
      while ( (unsigned int)v12 < cValues );
    }
    ++cValues;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    goto LABEL_34;
  }
  cbMaxValueNameLen = -1;
LABEL_32:
  v6 = -2147024362;
LABEL_47:
  if ( qword_180075388 )
  {
    for ( k = 0; k < cValues; ++k )
    {
      v18 = (void *)*((_QWORD *)qword_180075388 + k);
      if ( v18 )
      {
        CoTaskMemFree(v18);
        *((_QWORD *)qword_180075388 + k) = 0;
      }
    }
    CoTaskMemFree(qword_180075388);
    qword_180075388 = 0;
  }
  if ( qword_180075380 )
  {
    CoTaskMemFree(qword_180075380);
    qword_180075380 = 0;
  }
  dword_180075374 = 0;
  cValues = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180052840  mov     [rsp-8+arg_8], rbx
0x180052845  mov     [rsp-8+arg_10], rsi
0x18005284a  push    rbp
0x18005284b  push    rdi
0x18005284c  push    r13
0x18005284e  push    r14
0x180052850  push    r15
0x180052852  lea     rbp, [rsp-1A0h]
0x18005285a  sub     rsp, 2A0h
0x180052861  mov     rax, cs:__security_cookie
0x180052868  xor     rax, rsp
0x18005286b  mov     [rbp+1C0h+var_30], rax
0x180052872  mov     rsi, rcx
0x180052875  xor     r15d, r15d
0x180052878  mov     [rsp+2C0h+hKey], r15
0x18005287d  test    rcx, rcx
0x180052880  jz      loc_180052BC7
0x180052886  mov     [rcx], r15
0x180052889  mov     r13d, 0FFFFFFFFh
0x18005288f  cmp     cs:qword_180075388, r15
0x180052896  jnz     loc_180052B67
0x18005289c  lea     rax, [rsp+2C0h+hKey]
0x1800528a1  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800528a6  mov     r9d, 20019h; samDesired
0x1800528ac  xor     r8d, r8d; ulOptions
0x1800528af  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\COM3\\Registration"...
0x1800528b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800528bd  call    cs:__imp_RegOpenKeyExW
0x1800528c3  mov     [rsp+2C0h+cbMaxValueNameLen], r15d
0x1800528c8  test    eax, eax
0x1800528ca  jnz     short loc_180052923
0x1800528cc  mov     [rsp+2C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800528d1  mov     [rsp+2C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800528d6  mov     [rsp+2C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800528db  lea     rax, [rsp+2C0h+cbMaxValueNameLen]
0x1800528e0  mov     [rsp+2C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800528e5  lea     rax, cValues
0x1800528ec  mov     [rsp+2C0h+lpcValues], rax; lpcValues
0x1800528f1  mov     [rsp+2C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800528f6  mov     [rsp+2C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800528fb  mov     [rsp+2C0h+phkResult], r15; lpcSubKeys
0x180052900  xor     r9d, r9d; lpReserved
0x180052903  xor     r8d, r8d; lpcchClass
0x180052906  xor     edx, edx; lpClass
0x180052908  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18005290d  call    cs:__imp_RegQueryInfoKeyW
0x180052913  test    eax, eax
0x180052915  jz      short loc_180052923
0x180052917  mov     cs:cValues, r15d
0x18005291e  mov     [rsp+2C0h+cbMaxValueNameLen], r15d
0x180052923  mov     r8d, 105h; nSize
0x180052929  lea     rdx, [rbp+1C0h+Dst]; lpDst
0x18005292d  lea     rcx, aSystemrootSyst; "%systemroot%\\system32\\ATL.DLL"
0x180052934  call    cs:__imp_ExpandEnvironmentStringsW
0x18005293a  dec     eax
0x18005293c  cmp     eax, 104h
0x180052941  jbe     short loc_180052949
0x180052943  call    cs:__imp_GetLastError
0x180052949  lea     rcx, [rbp+1C0h+Dst]
0x18005294d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180052951  mov     rax, rdi
0x180052954  inc     rax
0x180052957  cmp     [rcx+rax*2], r15w
0x18005295c  jnz     short loc_180052954
0x18005295e  mov     ecx, [rsp+2C0h+cbMaxValueNameLen]
0x180052962  cmp     ecx, eax
0x180052964  ja      short loc_180052968
0x180052966  mov     ecx, eax
0x180052968  inc     ecx
0x18005296a  cmp     ecx, 1
0x18005296d  jb      loc_180052B5B
0x180052973  mov     [rsp+2C0h+cbMaxValueNameLen], ecx
0x180052977  mov     ecx, cs:cValues
0x18005297d  inc     ecx
0x18005297f  mov     eax, 8
0x180052984  mul     rcx
0x180052987  cmovb   rax, rdi
0x18005298b  mov     rcx, rax; cb
0x18005298e  call    cs:__imp_CoTaskMemAlloc
0x180052994  mov     rcx, rax; void *
0x180052997  mov     cs:qword_180075388, rax
0x18005299e  test    rax, rax
0x1800529a1  jnz     short loc_1800529AD
0x1800529a3  mov     ebx, 8007000Eh
0x1800529a8  jmp     loc_180052BCC
0x1800529ad  mov     r8d, cs:cValues
0x1800529b4  inc     r8d
0x1800529b7  shl     r8, 3; Size
0x1800529bb  xor     edx, edx; Val
0x1800529bd  call    memset_0
0x1800529c2  mov     ebx, r15d
0x1800529c5  mov     eax, cs:cValues
0x1800529cb  inc     eax
0x1800529cd  cmp     ebx, eax
0x1800529cf  jnb     short loc_180052A1D
0x1800529d1  mov     ecx, [rsp+2C0h+cbMaxValueNameLen]
0x1800529d5  mov     eax, 2
0x1800529da  mul     rcx
0x1800529dd  cmovb   rax, rdi
0x1800529e1  mov     rcx, rax; cb
0x1800529e4  call    cs:__imp_CoTaskMemAlloc
0x1800529ea  mov     edx, ebx
0x1800529ec  mov     rcx, cs:qword_180075388
0x1800529f3  mov     [rcx+rdx*8], rax
0x1800529f7  test    rax, rax
0x1800529fa  jz      short loc_1800529A3
0x1800529fc  mov     ecx, [rsp+2C0h+cbMaxValueNameLen]
0x180052a00  add     rcx, rcx
0x180052a03  cmp     rcx, r13
0x180052a06  ja      loc_180052B60
0x180052a0c  mov     r8d, ecx; Size
0x180052a0f  xor     edx, edx; Val
0x180052a11  mov     rcx, rax; void *
0x180052a14  call    memset_0
0x180052a19  inc     ebx
0x180052a1b  jmp     short loc_1800529C5
0x180052a1d  mov     ecx, eax
0x180052a1f  mov     eax, 4
0x180052a24  mul     rcx
0x180052a27  cmovb   rax, rdi
0x180052a2b  mov     rcx, rax; cb
0x180052a2e  call    cs:__imp_CoTaskMemAlloc
0x180052a34  mov     rcx, rax; void *
0x180052a37  mov     cs:qword_180075380, rax
0x180052a3e  test    rax, rax
0x180052a41  jz      loc_1800529A3
0x180052a47  mov     r8d, cs:cValues
0x180052a4e  inc     r8d
0x180052a51  shl     r8, 2; Size
0x180052a55  xor     edx, edx; Val
0x180052a57  call    memset_0
0x180052a5c  mov     edx, [rsp+2C0h+cbMaxValueNameLen]; unsigned __int64
0x180052a60  lea     r8, [rbp+1C0h+Dst]; unsigned __int16 *
0x180052a64  mov     rcx, cs:qword_180075388
0x180052a6b  mov     rcx, [rcx]; unsigned __int16 *
0x180052a6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052a73  mov     ebx, eax
0x180052a75  test    eax, eax
0x180052a77  jnz     loc_180052BCC
0x180052a7d  mov     rcx, cs:qword_180075380
0x180052a84  mov     dword ptr [rcx], 1
0x180052a8a  mov     cs:dword_180075374, 1
0x180052a94  mov     edx, r15d; dwIndex
0x180052a97  cmp     cs:cValues, r15d
0x180052a9e  jbe     loc_180052B3E
0x180052aa4  mov     ecx, [rsp+2C0h+cbMaxValueNameLen]
0x180052aa8  mov     [rsp+2C0h+cchValueName], ecx
0x180052aac  mov     [rsp+2C0h+Type], r15d
0x180052ab1  mov     [rsp+2C0h+cbData], 4
0x180052ab9  lea     r14d, [rdx+1]
0x180052abd  mov     rax, cs:qword_180075380
0x180052ac4  lea     rcx, [rax+r14*4]
0x180052ac8  lea     rax, [rsp+2C0h+cbData]
0x180052acd  mov     [rsp+2C0h+lpcValues], rax; lpcbData
0x180052ad2  mov     [rsp+2C0h+lpcbMaxClassLen], rcx; lpData
0x180052ad7  lea     rax, [rsp+2C0h+Type]
0x180052adc  mov     [rsp+2C0h+lpcbMaxSubKeyLen], rax; lpType
0x180052ae1  mov     [rsp+2C0h+phkResult], r15; lpReserved
0x180052ae6  lea     r9, [rsp+2C0h+cchValueName]; lpcchValueName
0x180052aeb  mov     r8, cs:qword_180075388
0x180052af2  mov     r8, [r8+r14*8]; lpValueName
0x180052af6  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180052afb  call    cs:__imp_RegEnumValueW
0x180052b01  test    eax, eax
0x180052b03  jnz     short loc_180052B23
0x180052b05  cmp     [rsp+2C0h+Type], 4
0x180052b0a  jnz     short loc_180052B23
0x180052b0c  mov     rcx, cs:qword_180075380
0x180052b13  mov     eax, [rcx+r14*4]
0x180052b17  test    eax, eax
0x180052b19  jz      short loc_180052B2E
0x180052b1b  inc     eax
0x180052b1d  mov     [rcx+r14*4], eax
0x180052b21  jmp     short loc_180052B2E
0x180052b23  mov     rax, cs:qword_180075380
0x180052b2a  mov     [rax+r14*4], r15d
0x180052b2e  mov     edx, r14d
0x180052b31  cmp     r14d, cs:cValues
0x180052b38  jb      loc_180052AA4
0x180052b3e  inc     cs:cValues
0x180052b44  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180052b49  test    rcx, rcx
0x180052b4c  jz      short loc_180052B6A
0x180052b4e  call    cs:__imp_RegCloseKey
0x180052b54  mov     [rsp+2C0h+hKey], r15
0x180052b59  jmp     short loc_180052B6A
0x180052b5b  mov     [rsp+2C0h+cbMaxValueNameLen], r13d
0x180052b60  mov     ebx, 80070216h
0x180052b65  jmp     short loc_180052BCC
0x180052b67  mov     ebx, r15d
0x180052b6a  mov     eax, r13d
0x180052b6d  mov     ecx, r15d
0x180052b70  cmp     ecx, cs:cValues
0x180052b76  jnb     short loc_180052B9B
0x180052b78  mov     r8d, ecx
0x180052b7b  mov     r9, cs:qword_180075380
0x180052b82  mov     edx, [r9+r8*4]
0x180052b86  test    edx, edx
0x180052b88  jz      short loc_180052B97
0x180052b8a  cmp     edx, cs:dword_180075374
0x180052b90  jz      short loc_180052BB0
0x180052b92  cmp     eax, edx
0x180052b94  cmovnb  eax, edx
0x180052b97  inc     ecx
0x180052b99  jmp     short loc_180052B70
0x180052b9b  cmp     cs:dword_180075374, eax
0x180052ba1  jnb     short loc_180052BCC
0x180052ba3  cmp     eax, r13d
0x180052ba6  jz      short loc_180052BCC
0x180052ba8  mov     cs:dword_180075374, eax
0x180052bae  jmp     short loc_180052B6D
0x180052bb0  mov     [r9+r8*4], r15d
0x180052bb4  mov     rax, cs:qword_180075388
0x180052bbb  mov     rcx, [rax+r8*8]
0x180052bbf  mov     [rsi], rcx
0x180052bc2  jmp     loc_180052C5C
0x180052bc7  mov     ebx, 80004003h
0x180052bcc  cmp     cs:qword_180075388, r15
0x180052bd3  jz      short loc_180052C24
0x180052bd5  mov     edi, r15d
0x180052bd8  cmp     cs:cValues, r15d
0x180052bdf  jbe     short loc_180052C0F
0x180052be1  mov     esi, edi
0x180052be3  mov     rax, cs:qword_180075388
0x180052bea  mov     rcx, [rax+rsi*8]; pv
0x180052bee  test    rcx, rcx
0x180052bf1  jz      short loc_180052C05
0x180052bf3  call    cs:__imp_CoTaskMemFree
0x180052bf9  nop
0x180052bfa  mov     rax, cs:qword_180075388
0x180052c01  mov     [rax+rsi*8], r15
0x180052c05  inc     edi
0x180052c07  cmp     edi, cs:cValues
0x180052c0d  jb      short loc_180052BE1
0x180052c0f  mov     rcx, cs:qword_180075388; pv
0x180052c16  call    cs:__imp_CoTaskMemFree
0x180052c1c  nop
0x180052c1d  mov     cs:qword_180075388, r15
0x180052c24  mov     rcx, cs:qword_180075380; pv
0x180052c2b  test    rcx, rcx
0x180052c2e  jz      short loc_180052C3E
0x180052c30  call    cs:__imp_CoTaskMemFree
0x180052c36  nop
0x180052c37  mov     cs:qword_180075380, r15
0x180052c3e  mov     cs:dword_180075374, r15d
0x180052c45  mov     cs:cValues, r15d
0x180052c4c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180052c51  test    rcx, rcx
0x180052c54  jz      short loc_180052C5C
0x180052c56  call    cs:__imp_RegCloseKey
0x180052c5c  mov     eax, ebx
0x180052c5e  mov     rcx, [rbp+1C0h+var_30]
0x180052c65  xor     rcx, rsp; StackCookie
0x180052c68  call    __security_check_cookie
0x180052c6d  lea     r11, [rsp+2C0h+var_20]
0x180052c75  mov     rbx, [r11+38h]
0x180052c79  mov     rsi, [r11+40h]
0x180052c7d  mov     rsp, r11
0x180052c80  pop     r15
0x180052c82  pop     r14
0x180052c84  pop     r13
0x180052c86  pop     rdi
0x180052c87  pop     rbp
0x180052c88  retn
```
