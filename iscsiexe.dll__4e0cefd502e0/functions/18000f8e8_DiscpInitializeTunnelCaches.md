# DiscpInitializeTunnelCaches

- ea: `0x18000f8e8`
- end: `0x18000fb21`
- name: `DiscpInitializeTunnelCaches`
- size: `569`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f7f8`

## callees

- `0x18000f8e8`
- `0x18000fb28`
- `0x180010b5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fa64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fa64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000fa50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000fa50`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f9b3`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f9e9`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f9b3`
- `ISCSIUM!DiscpAllocMemory` at `0x18000f9e9`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000f946`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000f946`
- `ISCSIUM!DiscpFreeMemory` at `0x18000facb`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fad4`
- `ISCSIUM!DiscpFreeMemory` at `0x18000faef`
- `ISCSIUM!DiscpFreeMemory` at `0x18000facb`
- `ISCSIUM!DiscpFreeMemory` at `0x18000fad4`
- `ISCSIUM!DiscpFreeMemory` at `0x18000faef`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fa3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fa3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fab7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f996`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb05`

## pseudocode

```c
__int64 __fastcall DiscpInitializeTunnelCaches(__int64 a1)
{
  __int64 v1; // r15
  __int64 v2; // r14
  int v3; // r13d
  unsigned int v4; // ebx
  BYTE *v5; // rdi
  DWORD v6; // eax
  unsigned __int64 v7; // rcx
  WCHAR *v8; // rbx
  DWORD i; // esi
  int v10; // eax
  DWORD cchValueName; // [rsp+60h] [rbp-19h] BYREF
  int v13; // [rsp+64h] [rbp-15h] BYREF
  DWORD Type; // [rsp+68h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-9h] BYREF
  __int64 v16; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v17[10]; // [rsp+80h] [rbp+7h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cValues; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  cValues = 0;
  v2 = -1;
  cbMaxValueNameLen = 0;
  v3 = a1;
  cbMaxValueLen = 0;
  hKey = 0;
  cbData = 0;
  cchValueName = 0;
  Type = 0;
  do
    ++v2;
  while ( *(_WORD *)(v1 + 2 * v2) );
  v4 = DiscpOpenRegistryKey(
         &hKey,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Tunnel Address",
         983103);
  if ( !v4 )
  {
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    if ( !v4 && cValues )
    {
      v5 = (BYTE *)DiscpAllocMemory(cbMaxValueLen);
      if ( v5 )
      {
        v6 = cbMaxValueNameLen + 1;
        if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen || (v7 = 2LL * v6, v7 > 0xFFFFFFFF) )
        {
          cbMaxValueNameLen = -1;
          RegCloseKey(hKey);
          DiscpFreeMemory(v5);
          return 534;
        }
        cbMaxValueNameLen = 2 * v6;
        v8 = (WCHAR *)DiscpAllocMemory(v7);
        if ( v8 )
        {
          for ( i = 0; i < cValues; ++i )
          {
            cbData = cbMaxValueLen;
            cchValueName = cbMaxValueNameLen;
            if ( !RegEnumValueW(hKey, i, v8, &cchValueName, 0, &Type, v5, &cbData)
              && (!(unsigned int)_o__wcsnicmp(v8, v1, (unsigned int)v2) || !(unsigned int)_o__wcsicmp(v8, L"All")) )
            {
              v13 = 0;
              v17[0] = 0;
              v16 = 0;
              v10 = DiscpParseCacheName(v8, v17, &v13, &v16);
              if ( !v10 )
                v10 = DiscpSetTunnelAddress(v3, v13, v16, (_DWORD)v5, 0);
              if ( v10 == -268500938 )
                RegDeleteValueW(hKey, v8);
            }
          }
          DiscpFreeMemory(v8);
        }
        DiscpFreeMemory(v5);
        v4 = 0;
      }
      else
      {
        v4 = 8;
      }
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f8e8  push    rbp
0x18000f8ea  push    rbx
0x18000f8eb  push    rsi
0x18000f8ec  push    rdi
0x18000f8ed  push    r12
0x18000f8ef  push    r13
0x18000f8f1  push    r14
0x18000f8f3  push    r15
0x18000f8f5  lea     rbp, [rsp-1Fh]
0x18000f8fa  sub     rsp, 98h
0x18000f901  mov     r15, [rcx+28h]
0x18000f905  xor     r12d, r12d
0x18000f908  mov     [rbp+57h+cValues], r12d
0x18000f90c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f910  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x18000f914  mov     r13, rcx
0x18000f917  mov     [rbp+57h+cbMaxValueLen], r12d
0x18000f91b  mov     [rbp+57h+hKey], r12
0x18000f91f  mov     [rbp+57h+cbData], r12d
0x18000f923  mov     [rbp+57h+cchValueName], r12d
0x18000f927  mov     [rbp+57h+Type], r12d
0x18000f92b  inc     r14
0x18000f92e  cmp     [r15+r14*2], r12w
0x18000f933  jnz     short loc_18000F92B
0x18000f935  mov     r8d, 0F003Fh
0x18000f93b  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000f942  lea     rcx, [rbp+57h+hKey]
0x18000f946  call    cs:__imp_DiscpOpenRegistryKey
0x18000f94c  mov     ebx, eax
0x18000f94e  test    eax, eax
0x18000f950  jnz     loc_18000FB0B
0x18000f956  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f95a  lea     rax, [rbp+57h+cbMaxValueLen]
0x18000f95e  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000f963  xor     r9d, r9d; lpReserved
0x18000f966  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000f96b  xor     r8d, r8d; lpcchClass
0x18000f96e  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000f973  xor     edx, edx; lpClass
0x18000f975  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000f979  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000f97e  lea     rax, [rbp+57h+cValues]
0x18000f982  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x18000f987  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000f98c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000f991  mov     [rsp+0D0h+lpcSubKeys], r12; lpcSubKeys
0x18000f996  call    cs:__imp_RegQueryInfoKeyW
0x18000f99c  mov     ebx, eax
0x18000f99e  test    eax, eax
0x18000f9a0  jnz     loc_18000FB01
0x18000f9a6  cmp     [rbp+57h+cValues], r12d
0x18000f9aa  jbe     loc_18000FB01
0x18000f9b0  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18000f9b3  call    cs:__imp_DiscpAllocMemory
0x18000f9b9  mov     rdi, rax
0x18000f9bc  test    rax, rax
0x18000f9bf  jz      loc_18000FAFC
0x18000f9c5  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000f9c8  mov     edx, 0FFFFFFFFh
0x18000f9cd  lea     eax, [rcx+1]
0x18000f9d0  cmp     eax, ecx
0x18000f9d2  jb      loc_18000FADF
0x18000f9d8  mov     ecx, eax
0x18000f9da  add     rcx, rcx
0x18000f9dd  cmp     rcx, rdx
0x18000f9e0  ja      loc_18000FADF
0x18000f9e6  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18000f9e9  call    cs:__imp_DiscpAllocMemory
0x18000f9ef  mov     rbx, rax
0x18000f9f2  test    rax, rax
0x18000f9f5  jz      loc_18000FAD1
0x18000f9fb  mov     esi, r12d
0x18000f9fe  cmp     [rbp+57h+cValues], r12d
0x18000fa02  jbe     loc_18000FAC8
0x18000fa08  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18000fa0b  lea     rax, [rbp+57h+cbData]
0x18000fa0f  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x18000fa14  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18000fa18  mov     [rbp+57h+cbData], ecx
0x18000fa1b  lea     rax, [rbp+57h+Type]
0x18000fa1f  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000fa22  mov     r8, rbx; lpValueName
0x18000fa25  mov     [rbp+57h+cchValueName], ecx
0x18000fa28  mov     edx, esi; dwIndex
0x18000fa2a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fa2e  mov     [rsp+0D0h+lpcbMaxClassLen], rdi; lpData
0x18000fa33  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x18000fa38  mov     [rsp+0D0h+lpcSubKeys], r12; lpReserved
0x18000fa3d  call    cs:__imp_RegEnumValueW
0x18000fa43  test    eax, eax
0x18000fa45  jnz     short loc_18000FABD
0x18000fa47  mov     r8d, r14d
0x18000fa4a  mov     rdx, r15
0x18000fa4d  mov     rcx, rbx
0x18000fa50  call    cs:__imp__o__wcsnicmp
0x18000fa56  test    eax, eax
0x18000fa58  jz      short loc_18000FA6E
0x18000fa5a  lea     rdx, aAll; "All"
0x18000fa61  mov     rcx, rbx
0x18000fa64  call    cs:__imp__o__wcsicmp
0x18000fa6a  test    eax, eax
0x18000fa6c  jnz     short loc_18000FABD
0x18000fa6e  lea     r9, [rbp+57h+var_58]
0x18000fa72  mov     [rbp+57h+var_6C], r12d
0x18000fa76  lea     r8, [rbp+57h+var_6C]
0x18000fa7a  mov     [rbp+57h+var_50], r12
0x18000fa7e  lea     rdx, [rbp+57h+var_50]
0x18000fa82  mov     [rbp+57h+var_58], r12
0x18000fa86  mov     rcx, rbx
0x18000fa89  call    DiscpParseCacheName
0x18000fa8e  test    eax, eax
0x18000fa90  jnz     short loc_18000FAA9
0x18000fa92  mov     r8, [rbp+57h+var_58]
0x18000fa96  mov     r9, rdi
0x18000fa99  mov     edx, [rbp+57h+var_6C]
0x18000fa9c  mov     rcx, r13
0x18000fa9f  mov     byte ptr [rsp+0D0h+lpcSubKeys], r12b
0x18000faa4  call    DiscpSetTunnelAddress
0x18000faa9  cmp     eax, 0EFFF0036h
0x18000faae  jnz     short loc_18000FABD
0x18000fab0  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fab4  mov     rdx, rbx; lpValueName
0x18000fab7  call    cs:__imp_RegDeleteValueW
0x18000fabd  inc     esi
0x18000fabf  cmp     esi, [rbp+57h+cValues]
0x18000fac2  jb      loc_18000FA08
0x18000fac8  mov     rcx, rbx
0x18000facb  call    cs:__imp_DiscpFreeMemory
0x18000fad1  mov     rcx, rdi
0x18000fad4  call    cs:__imp_DiscpFreeMemory
0x18000fada  mov     ebx, r12d
0x18000fadd  jmp     short loc_18000FB01
0x18000fadf  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fae3  mov     [rbp+57h+cbMaxValueNameLen], edx
0x18000fae6  call    cs:__imp_RegCloseKey
0x18000faec  mov     rcx, rdi
0x18000faef  call    cs:__imp_DiscpFreeMemory
0x18000faf5  mov     eax, 216h
0x18000fafa  jmp     short loc_18000FB0D
0x18000fafc  mov     ebx, 8
0x18000fb01  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fb05  call    cs:__imp_RegCloseKey
0x18000fb0b  mov     eax, ebx
0x18000fb0d  add     rsp, 98h
0x18000fb14  pop     r15
0x18000fb16  pop     r14
0x18000fb18  pop     r13
0x18000fb1a  pop     r12
0x18000fb1c  pop     rdi
0x18000fb1d  pop     rsi
0x18000fb1e  pop     rbx
0x18000fb1f  pop     rbp
0x18000fb20  retn
```
