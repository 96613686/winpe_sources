# NgscbpCheckHSTIPrerequisitesVerified

- ea: `0x1800362e4`
- end: `0x1800369ea`
- name: `NgscbpCheckHSTIPrerequisitesVerified`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800361f8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x1800362e4`
- `0x1800369f0`
- `0x180036f08`
- `0x180037794`
- `0x1800379e4`
- `0x180037d4c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036508`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036508`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800366e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800366d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800366f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800364f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800366d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800366f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003656b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003656b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180036448`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180036448`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800364c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800369d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800364c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800369d5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800365dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800365dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003663c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800363f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003663c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036613`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036613`

## pseudocode

```c
__int64 __fastcall NgscbpCheckHSTIPrerequisitesVerified(_BYTE *a1, void *a2)
{
  WCHAR *v2; // r12
  unsigned int CpuVendorA; // eax
  signed int v4; // ebx
  unsigned int CpuVendorHash; // eax
  int v6; // eax
  WCHAR *v7; // r15
  int v8; // eax
  LSTATUS v9; // eax
  PVOID *v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // r13d
  __int64 v13; // r9
  HANDLE v14; // rax
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v18; // r15
  DWORD v19; // ebx
  DWORD v20; // r13d
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  int v23; // edx
  int v24; // r8d
  PVOID *v25; // rcx
  unsigned int v26; // eax
  HANDLE v27; // rax
  HANDLE v28; // rax
  __int64 v29; // rdx
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-29h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-11h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-Dh] BYREF
  DWORD v35; // [rsp+80h] [rbp-9h]
  _BYTE *v36; // [rsp+88h] [rbp-1h]
  HKEY hKey; // [rsp+90h] [rbp+7h] BYREF
  LPVOID lpMem[2]; // [rsp+98h] [rbp+Fh] BYREF
  GUID pclsid; // [rsp+A8h] [rbp+1Fh] BYREF

  lpMem[1] = a2;
  v36 = a1;
  lpMem[0] = 0;
  lpSubKey = 0;
  v2 = 0;
  hKey = 0;
  phkResult = 0;
  hkey = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  pclsid = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v4;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147500035LL);
    goto LABEL_19;
  }
  *a1 = 1;
  if ( !a2 )
  {
    v4 = -2147024809;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_18;
    v29 = 120;
    v13 = 2147942487LL;
    goto LABEL_62;
  }
  CpuVendorA = NgscbGetCpuVendorA((char **)lpMem);
  v4 = CpuVendorA;
  if ( CpuVendorA )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, CpuVendorA);
    if ( v4 < 0 )
      goto LABEL_18;
  }
  CpuVendorHash = NgscbGetCpuVendorHash((unsigned __int16 **)&lpSubKey);
  v4 = CpuVendorHash;
  if ( CpuVendorHash )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        CpuVendorHash);
    if ( v4 < 0 )
      goto LABEL_18;
  }
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\BitLocker\\AutoDE\\HSTI",
         0,
         0x20019u,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v6 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    v4 = 0;
    goto LABEL_18;
  }
  v7 = (WCHAR *)lpSubKey;
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, lpMem[0]);
    v4 = 0;
    *v36 = 0;
    goto LABEL_20;
  }
  v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v4 = v9;
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  if ( v4 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        (unsigned int)v4);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 < 0 )
      goto LABEL_18;
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = 2LL * cbMaxSubKeyLen;
  if ( v11 > 0xFFFFFFFF )
  {
    v13 = 2147942934LL;
    v4 = -2147024362;
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
      goto LABEL_18;
    v29 = 130;
    goto LABEL_62;
  }
  v12 = v11 + 2;
  if ( (int)v11 + 2 < (unsigned int)v11 )
  {
    v13 = 2147942934LL;
    v4 = -2147024362;
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
      goto LABEL_18;
    v29 = 131;
    goto LABEL_62;
  }
  if ( v12 < 2 )
  {
    v4 = -2147024809;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v18 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v12);
    if ( v18 )
    {
      v19 = 0;
      v20 = v12 >> 1;
      while ( 1 )
      {
        v35 = v19;
        if ( hkey )
        {
          RegCloseKey(hkey);
          hkey = 0;
        }
        cchName = v20;
        v21 = RegEnumKeyExW(phkResult, v19, v18, &cchName, 0, 0, 0, 0);
        v4 = v21;
        if ( v21 > 0 )
          v4 = (unsigned __int16)v21 | 0x80070000;
        if ( v4 == -2147024637 )
          break;
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
              (unsigned int)v4);
          v2 = v18;
          if ( v4 < 0 )
            goto LABEL_18;
        }
        if ( CLSIDFromString(v18, &pclsid) >= 0 )
        {
          v22 = RegOpenKeyExW(phkResult, v18, 0, 0x20019u, &hkey);
          v4 = v22;
          if ( v22 > 0 )
            v4 = (unsigned __int16)v22 | 0x80070000;
          if ( v4 )
          {
            v25 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                134,
                &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                (unsigned int)v4);
              v25 = (PVOID *)WPP_GLOBAL_Control;
            }
            v2 = v18;
            if ( v4 < 0 )
              goto LABEL_18;
          }
          else
          {
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 8) != 0 )
            WPP_SF_Ss((unsigned int)v25[2], v23, v24, (_DWORD)v18, (__int64)lpMem[0]);
          v26 = NgscbpCheckHSTIPrerequisitesProfile(hkey);
          v4 = v26;
          if ( v26 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v26);
            v2 = v18;
            if ( v4 < 0 )
              goto LABEL_18;
          }
        }
        v19 = v35 + 1;
      }
      v4 = 0;
      v2 = v18;
      goto LABEL_19;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v4 = -2147024882;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
  {
    v29 = 132;
    v13 = (unsigned int)v4;
LABEL_62:
    WPP_SF_d(v10[2], v29, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v13);
  }
LABEL_18:
  *v36 = 0;
LABEL_19:
  v7 = (WCHAR *)lpSubKey;
LABEL_20:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v2);
  }
  if ( v7 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v7);
  }
  v15 = lpMem[0];
  if ( lpMem[0] )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v15);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800362e4  mov     [rsp-8+arg_10], rbx
0x1800362e9  mov     [rsp-8+arg_18], rdi
0x1800362ee  push    rbp
0x1800362ef  push    r12
0x1800362f1  push    r13
0x1800362f3  push    r14
0x1800362f5  push    r15
0x1800362f7  lea     rbp, [rsp-37h]
0x1800362fc  sub     rsp, 0C0h
0x180036303  mov     rax, cs:__security_cookie
0x18003630a  xor     rax, rsp
0x18003630d  mov     [rbp+57h+var_28], rax
0x180036311  xor     r13d, r13d
0x180036314  mov     [rbp+57h+var_40], rdx
0x180036318  mov     [rbp+57h+var_58], rcx
0x18003631c  xorps   xmm0, xmm0
0x18003631f  mov     [rbp+57h+lpMem], r13
0x180036323  mov     rax, rdx
0x180036326  mov     [rbp+57h+lpSubKey], r13
0x18003632a  mov     r12d, r13d
0x18003632d  mov     [rbp+57h+hKey], r13
0x180036331  mov     [rbp+57h+var_70], r13
0x180036335  mov     [rbp+57h+hkey], r13
0x180036339  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18003633d  mov     [rbp+57h+cchName], r13d
0x180036341  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180036345  test    rcx, rcx
0x180036348  jz      loc_18003673A
0x18003634e  mov     byte ptr [rcx], 1
0x180036351  test    rax, rax
0x180036354  jz      loc_18003677D
0x18003635a  lea     rcx, [rbp+57h+lpMem]; char **
0x18003635e  call    ?NgscbGetCpuVendorA@@YAJPEAPEAD@Z; NgscbGetCpuVendorA(char * *)
0x180036363  lea     rdi, WPP_GLOBAL_Control
0x18003636a  mov     ebx, eax
0x18003636c  lea     r14, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180036373  test    eax, eax
0x180036375  jnz     loc_1800367CA
0x18003637b  lea     rcx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x18003637f  call    ?NgscbGetCpuVendorHash@@YAJPEAPEAG@Z; NgscbGetCpuVendorHash(ushort * *)
0x180036384  mov     ebx, eax
0x180036386  test    eax, eax
0x180036388  jnz     loc_1800367FD
0x18003638e  lea     rax, [rbp+57h+hKey]
0x180036392  mov     r15d, 20019h
0x180036398  mov     r9d, r15d; samDesired
0x18003639b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800363a0  xor     r8d, r8d; ulOptions
0x1800363a3  lea     rdx, ?NGSCB_AUTODE_HSTI_PREREQS@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x1800363aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800363b1  call    cs:__imp_RegOpenKeyExW
0x1800363b8  nop     dword ptr [rax+rax+00h]
0x1800363bd  test    eax, eax
0x1800363bf  jle     short loc_1800363C9
0x1800363c1  movzx   eax, ax
0x1800363c4  or      eax, 80070000h
0x1800363c9  mov     ebx, 80070002h
0x1800363ce  cmp     eax, ebx
0x1800363d0  jz      loc_180036830
0x1800363d6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800363da  lea     rax, [rbp+57h+var_70]
0x1800363de  mov     r9d, r15d; samDesired
0x1800363e1  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800363e6  mov     r15, [rbp+57h+lpSubKey]
0x1800363ea  xor     r8d, r8d; ulOptions
0x1800363ed  mov     rdx, r15; lpSubKey
0x1800363f0  call    cs:__imp_RegOpenKeyExW
0x1800363f7  nop     dword ptr [rax+rax+00h]
0x1800363fc  test    eax, eax
0x1800363fe  jle     short loc_180036408
0x180036400  movzx   eax, ax
0x180036403  or      eax, 80070000h
0x180036408  cmp     eax, ebx
0x18003640a  jz      loc_18003685B
0x180036410  mov     rcx, [rbp+57h+var_70]; hKey
0x180036414  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180036418  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003641d  xor     r9d, r9d; lpReserved
0x180036420  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180036425  xor     r8d, r8d; lpcchClass
0x180036428  mov     [rsp+0E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18003642d  xor     edx, edx; lpClass
0x18003642f  mov     [rsp+0E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180036434  mov     [rsp+0E0h+lpcValues], r13; lpcValues
0x180036439  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18003643e  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180036443  mov     [rsp+0E0h+phkResult], r13; lpcSubKeys
0x180036448  call    cs:__imp_RegQueryInfoKeyW
0x18003644f  nop     dword ptr [rax+rax+00h]
0x180036454  mov     ebx, eax
0x180036456  test    eax, eax
0x180036458  jle     short loc_180036463
0x18003645a  movzx   ebx, ax
0x18003645d  or      ebx, 80070000h
0x180036463  test    ebx, ebx
0x180036465  jnz     loc_180036891
0x18003646b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036472  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180036475  mov     edx, 0FFFFFFFFh
0x18003647a  add     rax, rax
0x18003647d  cmp     rax, rdx
0x180036480  ja      loc_1800369B4
0x180036486  lea     r13d, [rax+2]
0x18003648a  cmp     r13d, eax
0x18003648d  jnb     loc_18003654D
0x180036493  mov     r9d, 80070216h
0x180036499  mov     ebx, r9d
0x18003649c  cmp     rcx, rdi
0x18003649f  jnz     loc_1800369A5
0x1800364a5  xor     r13d, r13d
0x1800364a8  mov     rax, [rbp+57h+var_58]
0x1800364ac  mov     [rax], r13b
0x1800364af  mov     r15, [rbp+57h+lpSubKey]
0x1800364b3  mov     rcx, [rbp+57h+hkey]; hKey
0x1800364b7  test    rcx, rcx
0x1800364ba  jnz     loc_1800369D5
0x1800364c0  mov     rcx, [rbp+57h+var_70]; hKey
0x1800364c4  test    rcx, rcx
0x1800364c7  jz      short loc_1800364D9
0x1800364c9  call    cs:__imp_RegCloseKey
0x1800364d0  nop     dword ptr [rax+rax+00h]
0x1800364d5  mov     [rbp+57h+var_70], r13
0x1800364d9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800364dd  test    rcx, rcx
0x1800364e0  jnz     loc_1800366BB
0x1800364e6  test    r12, r12
0x1800364e9  jnz     loc_1800366F5
0x1800364ef  test    r15, r15
0x1800364f2  jz      short loc_180036514
0x1800364f4  call    cs:__imp_GetProcessHeap
0x1800364fb  nop     dword ptr [rax+rax+00h]
0x180036500  mov     r8, r15; lpMem
0x180036503  xor     edx, edx; dwFlags
0x180036505  mov     rcx, rax; hHeap
0x180036508  call    cs:__imp_HeapFree
0x18003650f  nop     dword ptr [rax+rax+00h]
0x180036514  mov     rdi, [rbp+57h+lpMem]
0x180036518  test    rdi, rdi
0x18003651b  jnz     loc_1800366D0
0x180036521  mov     eax, ebx
0x180036523  mov     rcx, [rbp+57h+var_28]
0x180036527  xor     rcx, rsp; StackCookie
0x18003652a  call    __security_check_cookie
0x18003652f  lea     r11, [rsp+0E0h+var_20]
0x180036537  mov     rbx, [r11+40h]
0x18003653b  mov     rdi, [r11+48h]
0x18003653f  mov     rsp, r11
0x180036542  pop     r15
0x180036544  pop     r14
0x180036546  pop     r13
0x180036548  pop     r12
0x18003654a  pop     rbp
0x18003654b  retn
0x18003654d  cmp     r13d, 2
0x180036551  jb      loc_1800368CB
0x180036557  call    cs:__imp_GetProcessHeap
0x18003655e  nop     dword ptr [rax+rax+00h]
0x180036563  mov     r8d, r13d; dwBytes
0x180036566  xor     edx, edx; dwFlags
0x180036568  mov     rcx, rax; hHeap
0x18003656b  call    cs:__imp_HeapAlloc
0x180036572  nop     dword ptr [rax+rax+00h]
0x180036577  mov     r15, rax
0x18003657a  test    rax, rax
0x18003657d  jz      loc_1800368D5
0x180036583  xor     ebx, ebx
0x180036585  shr     r13d, 1
0x180036588  mov     rcx, [rbp+57h+hkey]; hKey
0x18003658c  mov     [rbp+57h+var_60], ebx
0x18003658f  test    rcx, rcx
0x180036592  jz      short loc_1800365A8
0x180036594  call    cs:__imp_RegCloseKey
0x18003659b  nop     dword ptr [rax+rax+00h]
0x1800365a0  mov     [rbp+57h+hkey], 0
0x1800365a8  mov     rcx, [rbp+57h+var_70]; hKey
0x1800365ac  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800365b0  mov     [rsp+0E0h+lpcValues], 0; lpftLastWriteTime
0x1800365b9  mov     r8, r15; lpName
0x1800365bc  mov     [rsp+0E0h+lpcbMaxClassLen], 0; lpcchClass
0x1800365c5  mov     edx, ebx; dwIndex
0x1800365c7  mov     [rsp+0E0h+lpcbMaxSubKeyLen], 0; lpClass
0x1800365d0  mov     [rsp+0E0h+phkResult], 0; lpReserved
0x1800365d9  mov     [rbp+57h+cchName], r13d
0x1800365dd  call    cs:__imp_RegEnumKeyExW
0x1800365e4  nop     dword ptr [rax+rax+00h]
0x1800365e9  mov     ebx, eax
0x1800365eb  test    eax, eax
0x1800365ed  jle     short loc_1800365F8
0x1800365ef  movzx   ebx, ax
0x1800365f2  or      ebx, 80070000h
0x1800365f8  cmp     ebx, 80070103h
0x1800365fe  jz      loc_1800366AD
0x180036604  test    ebx, ebx
0x180036606  jnz     loc_1800368FC
0x18003660c  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180036610  mov     rcx, r15; lpsz
0x180036613  call    cs:__imp_CLSIDFromString
0x18003661a  nop     dword ptr [rax+rax+00h]
0x18003661f  test    eax, eax
0x180036621  js      short loc_18003668C
0x180036623  mov     rcx, [rbp+57h+var_70]; hKey
0x180036627  lea     rax, [rbp+57h+hkey]
0x18003662b  mov     r9d, 20019h; samDesired
0x180036631  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180036636  xor     r8d, r8d; ulOptions
0x180036639  mov     rdx, r15; lpSubKey
0x18003663c  call    cs:__imp_RegOpenKeyExW
0x180036643  nop     dword ptr [rax+rax+00h]
0x180036648  mov     ebx, eax
0x18003664a  test    eax, eax
0x18003664c  jle     short loc_180036657
0x18003664e  movzx   ebx, ax
0x180036651  or      ebx, 80070000h
0x180036657  test    ebx, ebx
0x180036659  jnz     loc_180036932
0x18003665f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036666  cmp     rcx, rdi
0x180036669  jz      short loc_180036671
0x18003666b  test    byte ptr [rcx+1Ch], 8
0x18003666f  jnz     short loc_180036696
0x180036671  mov     r8, [rbp+57h+var_40]
0x180036675  mov     rdx, [rbp+57h+var_58]
0x180036679  mov     rcx, [rbp+57h+hkey]; hkey
0x18003667d  call    NgscbpCheckHSTIPrerequisitesProfile
0x180036682  mov     ebx, eax
0x180036684  test    eax, eax
0x180036686  jnz     loc_18003696F
0x18003668c  mov     ebx, [rbp+57h+var_60]
0x18003668f  inc     ebx
0x180036691  jmp     loc_180036588
0x180036696  mov     rax, [rbp+57h+lpMem]
0x18003669a  mov     r9, r15
0x18003669d  mov     rcx, [rcx+10h]
0x1800366a1  mov     [rsp+0E0h+phkResult], rax
0x1800366a6  call    WPP_SF_Ss
0x1800366ab  jmp     short loc_180036671
0x1800366ad  xor     r13d, r13d
0x1800366b0  mov     ebx, r13d
0x1800366b3  mov     r12, r15
0x1800366b6  jmp     loc_1800364AF
0x1800366bb  call    cs:__imp_RegCloseKey
0x1800366c2  nop     dword ptr [rax+rax+00h]
0x1800366c7  mov     [rbp+57h+hKey], r13
0x1800366cb  jmp     loc_1800364E6
0x1800366d0  call    cs:__imp_GetProcessHeap
0x1800366d7  nop     dword ptr [rax+rax+00h]
0x1800366dc  mov     r8, rdi; lpMem
0x1800366df  xor     edx, edx; dwFlags
0x1800366e1  mov     rcx, rax; hHeap
0x1800366e4  call    cs:__imp_HeapFree
0x1800366eb  nop     dword ptr [rax+rax+00h]
0x1800366f0  jmp     loc_180036521
0x1800366f5  call    cs:__imp_GetProcessHeap
0x1800366fc  nop     dword ptr [rax+rax+00h]
0x180036701  mov     r8, r12; lpMem
0x180036704  xor     edx, edx; dwFlags
0x180036706  mov     rcx, rax; hHeap
0x180036709  call    cs:__imp_HeapFree
0x180036710  nop     dword ptr [rax+rax+00h]
0x180036715  jmp     loc_1800364EF
0x18003671a  cmp     rcx, rdi
0x18003671d  jz      loc_1800364A5
0x180036723  test    byte ptr [rcx+1Ch], 40h
0x180036727  jz      loc_1800364A5
0x18003672d  mov     edx, 84h
0x180036732  mov     r9d, ebx
0x180036735  jmp     loc_1800368EB
0x18003673a  mov     ebx, 80004003h
0x18003673f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036746  lea     rdi, WPP_GLOBAL_Control
0x18003674d  cmp     rcx, rdi
0x180036750  jz      loc_180036521
0x180036756  test    byte ptr [rcx+1Ch], 40h
0x18003675a  jz      loc_180036521
0x180036760  mov     rcx, [rcx+10h]
0x180036764  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18003676b  mov     edx, 77h ; 'w'
0x180036770  mov     r9d, ebx
0x180036773  call    WPP_SF_d
0x180036778  jmp     loc_1800364AF
0x18003677d  mov     ebx, 80070057h
0x180036782  mov     rcx, cs:WPP_GLOBAL_Control
0x180036789  lea     rdi, WPP_GLOBAL_Control
0x180036790  cmp     rcx, rdi
0x180036793  jz      loc_1800364A8
0x180036799  test    byte ptr [rcx+1Ch], 40h
0x18003679d  jz      loc_1800364A8
0x1800367a3  mov     edx, 78h ; 'x'
0x1800367a8  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800367af  mov     r9d, ebx
0x1800367b2  jmp     short loc_1800367BC
0x1800367b4  mov     edx, 82h
0x1800367b9  mov     r8, r14
0x1800367bc  mov     rcx, [rcx+10h]
0x1800367c0  call    WPP_SF_d
0x1800367c5  jmp     loc_1800364A8
0x1800367ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367d1  cmp     rcx, rdi
0x1800367d4  jz      short loc_1800367F0
0x1800367d6  test    byte ptr [rcx+1Ch], 40h
  ... truncated ...
```
