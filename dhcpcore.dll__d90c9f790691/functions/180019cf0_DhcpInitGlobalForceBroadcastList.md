# DhcpInitGlobalForceBroadcastList

- ea: `0x180019cf0`
- end: `0x18001a14c`
- name: `DhcpInitGlobalForceBroadcastList`
- size: `1116`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003619c`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x180019cf0`
- `0x18001d826`
- `0x18004b4bc`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a063`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a06f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a063`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001a06f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a130`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a130`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019d5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019d5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ee9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a007`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a007`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019ea0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019ea0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019dcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019f57`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019dcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019f57`

## pseudocode

```c
__int64 DhcpInitGlobalForceBroadcastList()
{
  void *v0; // rsi
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  void *v4; // r12
  __int64 v5; // rdx
  DWORD i; // edi
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  DWORD v10; // r14d
  LSTATUS v11; // eax
  _OWORD *v12; // rax
  _OWORD *v13; // r15
  _QWORD *v14; // rcx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-29h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-25h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-11h] BYREF
  LPVOID v21; // [rsp+80h] [rbp-9h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-1h] BYREF
  LPVOID v23[10]; // [rsp+90h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+F0h] [rbp+67h] BYREF
  DWORD cSubKeys; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+100h] [rbp+77h] BYREF
  DWORD cValues; // [rsp+108h] [rbp+7Fh] BYREF

  cbData = 4;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  v0 = 0;
  cValues = 0;
  v21 = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  *(_DWORD *)Data = 0;
  v1 = RegOpenKeyExW(DhcpGlobalParametersKey, L"DhcpGlobalForceBroadcastFlag", 0, 0xDu, &hKey);
  v2 = v1;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 52, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v1);
  if ( !v2 )
  {
    v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v2 = v3;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 53, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v3);
    if ( !v2 && cSubKeys )
    {
      v23[0] = DhcpAlloc(2LL * (cbMaxSubKeyLen + 1));
      v4 = v23[0];
      if ( v23[0] )
      {
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = 2 * cbMaxSubKeyLen;
          memset_0(v4, 0, 2 * cbMaxSubKeyLen);
          if ( v0 )
          {
            DhcpPunycodeFree(&v21);
            v0 = 0;
            v21 = 0;
          }
          if ( phkResult )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
          }
          v7 = RegEnumKeyExW(hKey, i, (LPWSTR)v4, &cchName, 0, 0, 0, &ftLastWriteTime);
          v2 = v7;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_Dd(1028, 55, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, i, v7);
          if ( v2 )
            break;
          v8 = RegOpenKeyExW(hKey, (LPCWSTR)v4, 0, 0xDu, &phkResult);
          v2 = v8;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_Dd(1028, 56, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, i, v8);
          if ( v2 )
            break;
          v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
          v2 = v9;
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_Dd(1028, 57, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, i, v9);
          if ( v2 )
            break;
          if ( cValues )
          {
            v21 = DhcpAlloc(2LL * (cbMaxValueNameLen + 1));
            v0 = v21;
            if ( !v21 )
            {
              if ( (xmmword_1800616A0 & 2) == 0 )
                goto LABEL_44;
              v5 = 58;
              goto LABEL_43;
            }
            v10 = 0;
            while ( v10 < cValues )
            {
              cchName = 2 * cbMaxValueNameLen;
              memset_0(v0, 0, 2 * cbMaxValueNameLen);
              *(_DWORD *)Data = 0;
              cbData = 4;
              v11 = RegEnumValueW(phkResult, v10, (LPWSTR)v0, &cchName, 0, 0, Data, &cbData);
              v2 = v11;
              if ( (xmmword_1800616A0 & 0x10) != 0 )
                WPP_SF_ddD(1028, 59, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, i, v10, v11);
              if ( v2 == 259 )
                break;
              if ( v2 )
                goto LABEL_45;
              v12 = DhcpAlloc(0x20u);
              v13 = v12;
              if ( !v12 )
              {
                if ( (xmmword_1800616A0 & 2) == 0 )
                  goto LABEL_44;
                v5 = 60;
                goto LABEL_43;
              }
              *v12 = 0;
              v12[1] = 0;
              *(_DWORD *)v12 = _o__wtol(v4);
              *((_DWORD *)v13 + 1) = _o__wtol(v0);
              *((_DWORD *)v13 + 2) = *(_DWORD *)Data;
              v14 = off_180061028[0];
              if ( *(_UNKNOWN ***)off_180061028[0] != &DhcpGlobalForceBroadcastMediaList )
                __fastfail(3u);
              ++v10;
              *((_QWORD *)v13 + 2) = &DhcpGlobalForceBroadcastMediaList;
              *((_QWORD *)v13 + 3) = v14;
              *v14 = v13 + 1;
              off_180061028[0] = (_UNKNOWN **)(v13 + 1);
            }
          }
        }
      }
      else
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v5 = 54;
LABEL_43:
          WPP_SF_(1025, v5, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
        }
LABEL_44:
        v2 = 14;
      }
LABEL_45:
      if ( v4 )
        DhcpPunycodeFree(v23);
      if ( v0 )
        DhcpPunycodeFree(&v21);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v2;
}

```

## disassembly

```asm
0x180019cf0  push    rbp
0x180019cf2  push    rbx
0x180019cf3  push    rsi
0x180019cf4  push    rdi
0x180019cf5  push    r12
0x180019cf7  push    r13
0x180019cf9  push    r14
0x180019cfb  push    r15
0x180019cfd  lea     rbp, [rsp-1Fh]
0x180019d02  sub     rsp, 0A8h
0x180019d09  mov     rcx, cs:DhcpGlobalParametersKey; hKey
0x180019d10  lea     rax, [rbp+57h+hKey]
0x180019d14  xor     r13d, r13d
0x180019d17  mov     [rbp+57h+cbData], 4
0x180019d1e  xor     r8d, r8d; ulOptions
0x180019d21  mov     [rbp+57h+hKey], r13
0x180019d25  lea     rdx, aDhcpglobalforc; "DhcpGlobalForceBroadcastFlag"
0x180019d2c  mov     [rbp+57h+var_70], r13
0x180019d30  mov     [rbp+57h+cSubKeys], r13d
0x180019d34  mov     esi, r13d
0x180019d37  lea     r9d, [r13+0Dh]; samDesired
0x180019d3b  mov     [rbp+57h+cValues], r13d
0x180019d3f  mov     [rbp+57h+var_60], r13
0x180019d43  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x180019d47  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x180019d4b  mov     [rbp+57h+cchName], r13d
0x180019d4f  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r13
0x180019d53  mov     dword ptr [rbp+57h+Data], r13d
0x180019d57  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180019d5c  call    cs:__imp_RegOpenKeyExW
0x180019d62  mov     ebx, eax
0x180019d64  test    byte ptr cs:xmmword_1800616A0, 10h
0x180019d6b  lea     r15, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180019d72  jz      short loc_180019D88
0x180019d74  lea     edx, [r13+34h]
0x180019d78  mov     ecx, 404h
0x180019d7d  mov     r9d, eax
0x180019d80  mov     r8, r15
0x180019d83  call    WPP_SF_D
0x180019d88  test    ebx, ebx
0x180019d8a  jnz     loc_18001A118
0x180019d90  mov     rcx, [rbp+57h+hKey]; hKey
0x180019d94  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180019d98  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180019d9d  xor     r9d, r9d; lpReserved
0x180019da0  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180019da5  xor     r8d, r8d; lpcchClass
0x180019da8  mov     [rsp+0E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180019dad  xor     edx, edx; lpClass
0x180019daf  mov     [rsp+0E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180019db4  mov     [rsp+0E0h+lpcValues], r13; lpcValues
0x180019db9  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180019dbe  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180019dc3  lea     rax, [rbp+57h+cSubKeys]
0x180019dc7  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x180019dcc  call    cs:__imp_RegQueryInfoKeyW
0x180019dd2  mov     ebx, eax
0x180019dd4  test    byte ptr cs:xmmword_1800616A0, 10h
0x180019ddb  jz      short loc_180019DF2
0x180019ddd  mov     edx, 35h ; '5'
0x180019de2  mov     ecx, 404h
0x180019de7  mov     r9d, eax
0x180019dea  mov     r8, r15
0x180019ded  call    WPP_SF_D
0x180019df2  test    ebx, ebx
0x180019df4  jnz     loc_18001A118
0x180019dfa  cmp     [rbp+57h+cSubKeys], r13d
0x180019dfe  jz      loc_18001A118
0x180019e04  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x180019e07  inc     ecx
0x180019e09  add     rcx, rcx
0x180019e0c  call    DhcpAlloc
0x180019e11  mov     [rbp+57h+var_50], rax
0x180019e15  mov     r12, rax
0x180019e18  test    rax, rax
0x180019e1b  jnz     short loc_180019E32
0x180019e1d  test    byte ptr cs:xmmword_1800616A0, 2
0x180019e24  jz      loc_18001A0F7
0x180019e2a  lea     edx, [rbx+36h]
0x180019e2d  jmp     loc_18001A0EA
0x180019e32  mov     edi, r13d
0x180019e35  cmp     edi, [rbp+57h+cSubKeys]
0x180019e38  jnb     loc_18001A0FC
0x180019e3e  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180019e41  xor     edx, edx; Val
0x180019e43  add     eax, eax
0x180019e45  mov     rcx, r12; void *
0x180019e48  mov     r8d, eax; Size
0x180019e4b  mov     [rbp+57h+cchName], eax
0x180019e4e  call    memset_0
0x180019e53  test    rsi, rsi
0x180019e56  jz      short loc_180019E68
0x180019e58  lea     rcx, [rbp+57h+var_60]
0x180019e5c  call    DhcpPunycodeFree
0x180019e61  mov     rsi, r13
0x180019e64  mov     [rbp+57h+var_60], r13
0x180019e68  mov     rcx, [rbp+57h+var_70]; hKey
0x180019e6c  test    rcx, rcx
0x180019e6f  jz      short loc_180019E7B
0x180019e71  call    cs:__imp_RegCloseKey
0x180019e77  mov     [rbp+57h+var_70], r13
0x180019e7b  mov     rcx, [rbp+57h+hKey]; hKey
0x180019e7f  lea     rax, [rbp+57h+ftLastWriteTime]
0x180019e83  mov     [rsp+0E0h+lpcValues], rax; lpftLastWriteTime
0x180019e88  lea     r9, [rbp+57h+cchName]; lpcchName
0x180019e8c  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcchClass
0x180019e91  mov     r8, r12; lpName
0x180019e94  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r13; lpClass
0x180019e99  mov     edx, edi; dwIndex
0x180019e9b  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x180019ea0  call    cs:__imp_RegEnumKeyExW
0x180019ea6  mov     ebx, eax
0x180019ea8  test    byte ptr cs:xmmword_1800616A0, 10h
0x180019eaf  jz      short loc_180019ECA
0x180019eb1  mov     edx, 37h ; '7'
0x180019eb6  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180019eba  mov     ecx, 404h
0x180019ebf  mov     r9d, edi
0x180019ec2  mov     r8, r15
0x180019ec5  call    WPP_SF_Dd
0x180019eca  test    ebx, ebx
0x180019ecc  jnz     loc_18001A0FC
0x180019ed2  mov     rcx, [rbp+57h+hKey]; hKey
0x180019ed6  lea     rax, [rbp+57h+var_70]
0x180019eda  lea     r9d, [rbx+0Dh]; samDesired
0x180019ede  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180019ee3  xor     r8d, r8d; ulOptions
0x180019ee6  mov     rdx, r12; lpSubKey
0x180019ee9  call    cs:__imp_RegOpenKeyExW
0x180019eef  mov     ebx, eax
0x180019ef1  test    byte ptr cs:xmmword_1800616A0, 10h
0x180019ef8  jz      short loc_180019F13
0x180019efa  mov     edx, 38h ; '8'
0x180019eff  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180019f03  mov     ecx, 404h
0x180019f08  mov     r9d, edi
0x180019f0b  mov     r8, r15
0x180019f0e  call    WPP_SF_Dd
0x180019f13  test    ebx, ebx
0x180019f15  jnz     loc_18001A0FC
0x180019f1b  mov     rcx, [rbp+57h+var_70]; hKey
0x180019f1f  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180019f23  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180019f28  xor     r9d, r9d; lpReserved
0x180019f2b  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180019f30  xor     r8d, r8d; lpcchClass
0x180019f33  mov     [rsp+0E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180019f38  xor     edx, edx; lpClass
0x180019f3a  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180019f3f  lea     rax, [rbp+57h+cValues]
0x180019f43  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x180019f48  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180019f4d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180019f52  mov     [rsp+0E0h+phkResult], r13; lpcSubKeys
0x180019f57  call    cs:__imp_RegQueryInfoKeyW
0x180019f5d  mov     ebx, eax
0x180019f5f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180019f66  jz      short loc_180019F81
0x180019f68  mov     edx, 39h ; '9'
0x180019f6d  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180019f71  mov     ecx, 404h
0x180019f76  mov     r9d, edi
0x180019f79  mov     r8, r15
0x180019f7c  call    WPP_SF_Dd
0x180019f81  test    ebx, ebx
0x180019f83  jnz     loc_18001A0FC
0x180019f89  cmp     [rbp+57h+cValues], r13d
0x180019f8d  jz      loc_18001A0B7
0x180019f93  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180019f96  inc     ecx
0x180019f98  add     rcx, rcx
0x180019f9b  call    DhcpAlloc
0x180019fa0  mov     [rbp+57h+var_60], rax
0x180019fa4  mov     rsi, rax
0x180019fa7  test    rax, rax
0x180019faa  jz      loc_18001A0DC
0x180019fb0  mov     r14d, r13d
0x180019fb3  cmp     r14d, [rbp+57h+cValues]
0x180019fb7  jnb     loc_18001A0B7
0x180019fbd  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180019fc0  xor     edx, edx; Val
0x180019fc2  add     ecx, ecx
0x180019fc4  mov     [rbp+57h+cchName], ecx
0x180019fc7  mov     r8d, ecx; Size
0x180019fca  mov     rcx, rsi; void *
0x180019fcd  call    memset_0
0x180019fd2  mov     rcx, [rbp+57h+var_70]; hKey
0x180019fd6  lea     rax, [rbp+57h+cbData]
0x180019fda  mov     [rsp+0E0h+lpcValues], rax; lpcbData
0x180019fdf  lea     r9, [rbp+57h+cchName]; lpcchValueName
0x180019fe3  lea     rax, [rbp+57h+Data]
0x180019fe7  mov     dword ptr [rbp+57h+Data], r13d
0x180019feb  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpData
0x180019ff0  mov     r8, rsi; lpValueName
0x180019ff3  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r13; lpType
0x180019ff8  mov     edx, r14d; dwIndex
0x180019ffb  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x18001a000  mov     [rbp+57h+cbData], 4
0x18001a007  call    cs:__imp_RegEnumValueW
0x18001a00d  mov     ebx, eax
0x18001a00f  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001a016  jz      short loc_18001A036
0x18001a018  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], eax
0x18001a01c  mov     edx, 3Bh ; ';'
0x18001a021  mov     ecx, 404h
0x18001a026  mov     dword ptr [rsp+0E0h+phkResult], r14d
0x18001a02b  mov     r9d, edi
0x18001a02e  mov     r8, r15
0x18001a031  call    WPP_SF_ddD
0x18001a036  cmp     ebx, 103h
0x18001a03c  jz      short loc_18001A0B7
0x18001a03e  test    ebx, ebx
0x18001a040  jnz     loc_18001A0FC
0x18001a046  lea     ecx, [rbx+20h]
0x18001a049  call    DhcpAlloc
0x18001a04e  mov     r15, rax
0x18001a051  test    rax, rax
0x18001a054  jz      short loc_18001A0C5
0x18001a056  xorps   xmm0, xmm0
0x18001a059  mov     rcx, r12
0x18001a05c  movups  xmmword ptr [rax], xmm0
0x18001a05f  movups  xmmword ptr [rax+10h], xmm0
0x18001a063  call    cs:__imp__o__wtol
0x18001a069  mov     rcx, rsi
0x18001a06c  mov     [r15], eax
0x18001a06f  call    cs:__imp__o__wtol
0x18001a075  mov     [r15+4], eax
0x18001a079  lea     rdx, DhcpGlobalForceBroadcastMediaList
0x18001a080  mov     eax, dword ptr [rbp+57h+Data]
0x18001a083  mov     [r15+8], eax
0x18001a087  mov     rcx, cs:off_180061028
0x18001a08e  cmp     [rcx], rdx
0x18001a091  jnz     short loc_18001A0BE
0x18001a093  lea     rax, [r15+10h]
0x18001a097  inc     r14d
0x18001a09a  mov     [rax], rdx
0x18001a09d  lea     r15, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001a0a4  mov     [rax+8], rcx
0x18001a0a8  mov     [rcx], rax
0x18001a0ab  mov     cs:off_180061028, rax
0x18001a0b2  jmp     loc_180019FB3
0x18001a0b7  inc     edi
0x18001a0b9  jmp     loc_180019E35
0x18001a0be  mov     ecx, 3
0x18001a0c3  int     29h; Win8: RtlFailFast(ecx)
0x18001a0c5  test    byte ptr cs:xmmword_1800616A0, 2
0x18001a0cc  jz      short loc_18001A0F7
0x18001a0ce  mov     edx, 3Ch ; '<'
0x18001a0d3  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001a0da  jmp     short loc_18001A0ED
0x18001a0dc  test    byte ptr cs:xmmword_1800616A0, 2
0x18001a0e3  jz      short loc_18001A0F7
0x18001a0e5  mov     edx, 3Ah ; ':'
0x18001a0ea  mov     r8, r15
0x18001a0ed  mov     ecx, 401h
0x18001a0f2  call    WPP_SF_
0x18001a0f7  mov     ebx, 0Eh
0x18001a0fc  test    r12, r12
0x18001a0ff  jz      short loc_18001A10A
0x18001a101  lea     rcx, [rbp+57h+var_50]
0x18001a105  call    DhcpPunycodeFree
0x18001a10a  test    rsi, rsi
0x18001a10d  jz      short loc_18001A118
0x18001a10f  lea     rcx, [rbp+57h+var_60]
0x18001a113  call    DhcpPunycodeFree
0x18001a118  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a11c  test    rcx, rcx
0x18001a11f  jz      short loc_18001A127
0x18001a121  call    cs:__imp_RegCloseKey
0x18001a127  mov     rcx, [rbp+57h+var_70]; hKey
0x18001a12b  test    rcx, rcx
0x18001a12e  jz      short loc_18001A136
0x18001a130  call    cs:__imp_RegCloseKey
0x18001a136  mov     eax, ebx
0x18001a138  add     rsp, 0A8h
0x18001a13f  pop     r15
0x18001a141  pop     r14
0x18001a143  pop     r13
0x18001a145  pop     r12
0x18001a147  pop     rdi
0x18001a148  pop     rsi
0x18001a149  pop     rbx
0x18001a14a  pop     rbp
0x18001a14b  retn
```
