# CDimSetup::RConfigTransportCreate(ulong,ushort *,uchar *,ulong,uchar *,ulong,ushort *,int)

- ea: `0x1800318a4`
- end: `0x180031dab`
- name: `?RConfigTransportCreate@CDimSetup@@AEAAKKPEAGPEAEK1K0H@Z`
- size: `1287`
- prototype: `unsigned int(CDimSetup *__hidden this, unsigned int, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030b90`

## callees

- `0x18001851c`
- `0x1800318a4`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003198e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003198e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031d6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031d6d`
- `KERNEL32!lstrcmpiW` at `0x180031a7d`
- `KERNEL32!lstrcmpiW` at `0x180031a7d`
- `ADVAPI32!RegOpenKeyExW` at `0x180031a54`
- `ADVAPI32!RegOpenKeyExW` at `0x180031a54`
- `ADVAPI32!RegSetValueExW` at `0x180031ace`
- `ADVAPI32!RegSetValueExW` at `0x180031afc`
- `ADVAPI32!RegSetValueExW` at `0x180031b3f`
- `ADVAPI32!RegSetValueExW` at `0x180031bab`
- `ADVAPI32!RegSetValueExW` at `0x180031c6f`
- `ADVAPI32!RegSetValueExW` at `0x180031c9d`
- `ADVAPI32!RegSetValueExW` at `0x180031ce0`
- `ADVAPI32!RegSetValueExW` at `0x180031d13`
- `ADVAPI32!RegSetValueExW` at `0x180031d45`
- `ADVAPI32!RegSetValueExW` at `0x180031ace`
- `ADVAPI32!RegSetValueExW` at `0x180031afc`
- `ADVAPI32!RegSetValueExW` at `0x180031b3f`
- `ADVAPI32!RegSetValueExW` at `0x180031bab`
- `ADVAPI32!RegSetValueExW` at `0x180031c6f`
- `ADVAPI32!RegSetValueExW` at `0x180031c9d`
- `ADVAPI32!RegSetValueExW` at `0x180031ce0`
- `ADVAPI32!RegSetValueExW` at `0x180031d13`
- `ADVAPI32!RegSetValueExW` at `0x180031d45`
- `ADVAPI32!RegCloseKey` at `0x180031a69`
- `ADVAPI32!RegCloseKey` at `0x180031d56`
- `ADVAPI32!RegCloseKey` at `0x180031d7c`
- `ADVAPI32!RegCloseKey` at `0x180031a69`
- `ADVAPI32!RegCloseKey` at `0x180031d56`
- `ADVAPI32!RegCloseKey` at `0x180031d7c`
- `ADVAPI32!RegQueryValueExW` at `0x180031b6f`
- `ADVAPI32!RegQueryValueExW` at `0x180031bdb`
- `ADVAPI32!RegQueryValueExW` at `0x180031b6f`
- `ADVAPI32!RegQueryValueExW` at `0x180031bdb`
- `ADVAPI32!RegEnumKeyExW` at `0x180031a2f`
- `ADVAPI32!RegEnumKeyExW` at `0x180031a2f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180031967`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180031967`
- `ADVAPI32!RegOpenKeyW` at `0x18003191b`
- `ADVAPI32!RegOpenKeyW` at `0x180031a9a`
- `ADVAPI32!RegOpenKeyW` at `0x18003191b`
- `ADVAPI32!RegOpenKeyW` at `0x180031a9a`
- `ADVAPI32!RegCreateKeyExW` at `0x180031c3e`
- `ADVAPI32!RegCreateKeyExW` at `0x180031c3e`

## string_xrefs

- `0x1800318e3`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`
- `0x180031b2a`: `DLLPath`
- `0x180031ccb`: `DLLPath`
- `0x180031aea`: `ProtocolId`
- `0x180031c8b`: `ProtocolId`

## pseudocode

```c
__int64 __fastcall CDimSetup::RConfigTransportCreate(
        CDimSetup *this,
        int a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbData,
        unsigned __int8 *a6,
        DWORD a7,
        BYTE *lpData,
        int a9)
{
  DWORD v9; // r14d
  WCHAR *v11; // r12
  unsigned int v13; // ebx
  __int64 v14; // rsi
  __int64 v15; // rax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  bool v18; // zf
  DWORD cchName; // [rsp+60h] [rbp-69h] BYREF
  HKEY v21; // [rsp+68h] [rbp-61h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-59h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-51h] BYREF
  BYTE v24[8]; // [rsp+80h] [rbp-49h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-41h] BYREF
  DWORD Type; // [rsp+8Ch] [rbp-3Dh] BYREF
  BYTE Data[4]; // [rsp+90h] [rbp-39h] BYREF
  DWORD dwDisposition; // [rsp+94h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-31h] BYREF
  BYTE *v30; // [rsp+A0h] [rbp-29h]
  wchar_t pszDest[12]; // [rsp+A8h] [rbp-21h] BYREF

  v9 = 0;
  *(_DWORD *)v24 = a2;
  v30 = a6;
  phkResult = 0;
  hKey = 0;
  v11 = 0;
  v21 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  Type = 0;
  cchName = 0;
  *(_DWORD *)Data = 0;
  v13 = RegOpenKeyW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers",
          &phkResult);
  if ( !v13 )
  {
    v13 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v13 )
    {
      v11 = (WCHAR *)HeapAlloc(hHeap, 8u, 2 * cbMaxSubKeyLen + 2);
      if ( v11 )
      {
        v14 = -1;
        if ( !a3 )
          goto LABEL_9;
        v15 = -1;
        do
          ++v15;
        while ( a3[v15] );
        if ( !v15 )
        {
LABEL_9:
          if ( *(_DWORD *)v24 == 33 )
          {
            a3 = L"Ip";
          }
          else if ( *(_DWORD *)v24 == 87 )
          {
            a3 = L"Ipv6";
          }
          else
          {
            StringCbPrintfW(pszDest, 0x14u, L"%d");
            a3 = pszDest;
          }
        }
        while ( v9 < cSubKeys )
        {
          cchName = cbMaxSubKeyLen + 1;
          v13 = RegEnumKeyExW(phkResult, v9, v11, &cchName, 0, 0, 0, 0);
          if ( !v13 )
          {
            v13 = RegOpenKeyExW(phkResult, v11, 0, 0x3001Fu, &hKey);
            if ( !v13 )
            {
              if ( hKey )
              {
                RegCloseKey(hKey);
                hKey = 0;
              }
              if ( !lstrcmpiW(v11, a3) )
              {
                v13 = RegOpenKeyW(phkResult, a3, &v21);
                if ( v13 )
                  goto LABEL_47;
                v13 = RegSetValueExW(phkResult, L"Stamp", 0, 4u, Data, 4u);
                if ( v13 )
                  goto LABEL_47;
                v13 = RegSetValueExW(v21, L"ProtocolId", 0, 4u, v24, 4u);
                if ( v13 )
                  goto LABEL_47;
                if ( lpData )
                {
                  do
                    ++v14;
                  while ( *(_WORD *)&lpData[2 * v14] );
                  v13 = RegSetValueExW(v21, L"DLLPath", 0, 2u, lpData, 2 * v14 + 2);
                  if ( v13 )
                    goto LABEL_47;
                }
                if ( (v16 = RegQueryValueExW(v21, L"GlobalInfo", 0, &Type, 0, &cchName)) == 0 && !cchName || v16 == 2 )
                {
                  if ( a4 )
                  {
                    v13 = RegSetValueExW(v21, L"GlobalInfo", 0, 3u, a4, cbData);
                    if ( v13 )
                      goto LABEL_47;
                  }
                }
                v17 = RegQueryValueExW(v21, L"GlobalInterfaceInfo", 0, &Type, 0, &cchName);
                v13 = v17;
                if ( v17 || cchName )
                {
                  v18 = v17 == 2;
                  goto LABEL_44;
                }
                goto LABEL_45;
              }
            }
          }
          ++v9;
        }
        if ( a9 != 1 )
          goto LABEL_47;
        dwDisposition = 0;
        v13 = RegCreateKeyExW(phkResult, a3, 0, 0, 0, 0x3001Fu, 0, &v21, &dwDisposition);
        if ( v13 )
          goto LABEL_47;
        v13 = RegSetValueExW(phkResult, L"Stamp", 0, 4u, Data, 4u);
        if ( v13 )
          goto LABEL_47;
        v13 = RegSetValueExW(v21, L"ProtocolId", 0, 4u, v24, 4u);
        if ( v13 )
          goto LABEL_47;
        if ( lpData )
        {
          do
            ++v14;
          while ( *(_WORD *)&lpData[2 * v14] );
          v13 = RegSetValueExW(v21, L"DLLPath", 0, 2u, lpData, 2 * v14 + 2);
          if ( v13 )
            goto LABEL_47;
        }
        if ( a4 )
        {
          v13 = RegSetValueExW(v21, L"GlobalInfo", 0, 3u, a4, cbData);
          v18 = v13 == 0;
LABEL_44:
          if ( !v18 )
            goto LABEL_47;
        }
LABEL_45:
        if ( v30 )
          v13 = RegSetValueExW(v21, L"GlobalInterfaceInfo", 0, 3u, v30, a7);
      }
      else
      {
        v13 = 8;
      }
    }
  }
LABEL_47:
  if ( v21 )
    RegCloseKey(v21);
  if ( v11 )
    HeapFree(hHeap, 0, v11);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v13;
}

```

## disassembly

```asm
0x1800318a4  mov     [rsp-8+arg_0], rbx
0x1800318a9  push    rbp
0x1800318aa  push    rsi
0x1800318ab  push    rdi
0x1800318ac  push    r12
0x1800318ae  push    r13
0x1800318b0  push    r14
0x1800318b2  push    r15
0x1800318b4  lea     rbp, [rsp-7]
0x1800318b9  sub     rsp, 0D0h
0x1800318c0  mov     rax, cs:__security_cookie
0x1800318c7  xor     rax, rsp
0x1800318ca  mov     [rbp+37h+var_40], rax
0x1800318ce  mov     rax, [rbp+37h+arg_28]
0x1800318d2  xor     r14d, r14d
0x1800318d5  mov     r15, [rbp+37h+lpData]
0x1800318d9  mov     rdi, r8
0x1800318dc  mov     dword ptr [rbp+37h+var_80], edx
0x1800318df  lea     r8, [rbp+37h+phkResult]; phkResult
0x1800318e3  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x1800318ea  mov     [rbp+37h+var_60], rax
0x1800318ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800318f5  mov     [rbp+37h+phkResult], r14
0x1800318f9  mov     [rbp+37h+hKey], r14
0x1800318fd  mov     r12d, r14d
0x180031900  mov     [rbp+37h+var_98], r14
0x180031904  mov     r13, r9
0x180031907  mov     [rbp+37h+cSubKeys], r14d
0x18003190b  mov     [rbp+37h+cbMaxSubKeyLen], r14d
0x18003190f  mov     [rbp+37h+Type], r14d
0x180031913  mov     [rbp+37h+cchName], r14d
0x180031917  mov     dword ptr [rbp+37h+Data], r14d
0x18003191b  call    cs:__imp_RegOpenKeyW
0x180031921  mov     ebx, eax
0x180031923  test    eax, eax
0x180031925  jnz     loc_180031D4D
0x18003192b  mov     rcx, [rbp+37h+phkResult]; hKey
0x18003192f  lea     rax, [rbp+37h+cbMaxSubKeyLen]
0x180031933  mov     [rsp+100h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180031938  xor     r9d, r9d; lpReserved
0x18003193b  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180031940  xor     r8d, r8d; lpcchClass
0x180031943  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180031948  xor     edx, edx; lpClass
0x18003194a  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18003194f  mov     [rsp+100h+lpcValues], r14; lpcValues
0x180031954  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180031959  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003195e  lea     rax, [rbp+37h+cSubKeys]
0x180031962  mov     [rsp+100h+lpcSubKeys], rax; lpcSubKeys
0x180031967  call    cs:__imp_RegQueryInfoKeyW
0x18003196d  mov     ebx, eax
0x18003196f  test    eax, eax
0x180031971  jnz     loc_180031D4D
0x180031977  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x18003197a  lea     esi, [rbx+8]
0x18003197d  mov     rcx, cs:hHeap; hHeap
0x180031984  mov     edx, esi; dwFlags
0x180031986  lea     r8d, ds:2[rax*2]; dwBytes
0x18003198e  call    cs:__imp_HeapAlloc
0x180031994  mov     r12, rax
0x180031997  test    rax, rax
0x18003199a  jnz     short loc_1800319A3
0x18003199c  mov     ebx, esi
0x18003199e  jmp     loc_180031D4D
0x1800319a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800319a7  test    rdi, rdi
0x1800319aa  jz      short loc_1800319BE
0x1800319ac  mov     rax, rsi
0x1800319af  inc     rax
0x1800319b2  cmp     [rdi+rax*2], r14w
0x1800319b7  jnz     short loc_1800319AF
0x1800319b9  test    rax, rax
0x1800319bc  jnz     short loc_1800319F9
0x1800319be  mov     r9d, dword ptr [rbp+37h+var_80]
0x1800319c2  cmp     r9d, 21h ; '!'
0x1800319c6  jnz     short loc_1800319D1
0x1800319c8  lea     rdi, aIp; "Ip"
0x1800319cf  jmp     short loc_1800319F9
0x1800319d1  cmp     r9d, 57h ; 'W'
0x1800319d5  jnz     short loc_1800319E0
0x1800319d7  lea     rdi, aIpv6_0; "Ipv6"
0x1800319de  jmp     short loc_1800319F9
0x1800319e0  lea     r8, aD; "%d"
0x1800319e7  mov     edx, 14h; cbDest
0x1800319ec  lea     rcx, [rbp+37h+pszDest]; pszDest
0x1800319f0  call    StringCbPrintfW
0x1800319f5  lea     rdi, [rbp+37h+pszDest]
0x1800319f9  cmp     r14d, [rbp+37h+cSubKeys]
0x1800319fd  jnb     loc_180031BF9
0x180031a03  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x180031a06  lea     r9, [rbp+37h+cchName]; lpcchName
0x180031a0a  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031a0e  inc     eax
0x180031a10  mov     [rbp+37h+cchName], eax
0x180031a13  mov     r8, r12; lpName
0x180031a16  xor     eax, eax
0x180031a18  mov     edx, r14d; dwIndex
0x180031a1b  mov     [rsp+100h+lpcValues], rax; lpftLastWriteTime
0x180031a20  mov     [rsp+100h+lpcbMaxClassLen], rax; lpcchClass
0x180031a25  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpClass
0x180031a2a  mov     [rsp+100h+lpcSubKeys], rax; lpReserved
0x180031a2f  call    cs:__imp_RegEnumKeyExW
0x180031a35  mov     ebx, eax
0x180031a37  test    eax, eax
0x180031a39  jnz     short loc_180031A87
0x180031a3b  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031a3f  lea     rax, [rbp+37h+hKey]
0x180031a43  mov     r9d, 3001Fh; samDesired
0x180031a49  mov     [rsp+100h+lpcSubKeys], rax; phkResult
0x180031a4e  xor     r8d, r8d; ulOptions
0x180031a51  mov     rdx, r12; lpSubKey
0x180031a54  call    cs:__imp_RegOpenKeyExW
0x180031a5a  mov     ebx, eax
0x180031a5c  test    eax, eax
0x180031a5e  jnz     short loc_180031A87
0x180031a60  mov     rcx, [rbp+37h+hKey]; hKey
0x180031a64  test    rcx, rcx
0x180031a67  jz      short loc_180031A77
0x180031a69  call    cs:__imp_RegCloseKey
0x180031a6f  mov     [rbp+37h+hKey], 0
0x180031a77  mov     rdx, rdi; lpString2
0x180031a7a  mov     rcx, r12; lpString1
0x180031a7d  call    cs:__imp_lstrcmpiW
0x180031a83  test    eax, eax
0x180031a85  jz      short loc_180031A8F
0x180031a87  inc     r14d
0x180031a8a  jmp     loc_1800319F9
0x180031a8f  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031a93  lea     r8, [rbp+37h+var_98]; phkResult
0x180031a97  mov     rdx, rdi; lpSubKey
0x180031a9a  call    cs:__imp_RegOpenKeyW
0x180031aa0  xor     r14d, r14d
0x180031aa3  mov     ebx, eax
0x180031aa5  test    eax, eax
0x180031aa7  jnz     loc_180031D4D
0x180031aad  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031ab1  lea     edi, [rax+4]
0x180031ab4  lea     rax, [rbp+37h+Data]
0x180031ab8  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], edi; cbData
0x180031abc  mov     r9d, edi; dwType
0x180031abf  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x180031ac4  xor     r8d, r8d; Reserved
0x180031ac7  lea     rdx, aStamp; "Stamp"
0x180031ace  call    cs:__imp_RegSetValueExW
0x180031ad4  mov     ebx, eax
0x180031ad6  test    eax, eax
0x180031ad8  jnz     loc_180031D4D
0x180031ade  mov     rcx, [rbp+37h+var_98]; hKey
0x180031ae2  lea     rax, [rbp+37h+var_80]
0x180031ae6  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], edi; cbData
0x180031aea  lea     rdx, aProtocolid_0; "ProtocolId"
0x180031af1  mov     r9d, edi; dwType
0x180031af4  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x180031af9  xor     r8d, r8d; Reserved
0x180031afc  call    cs:__imp_RegSetValueExW
0x180031b02  mov     ebx, eax
0x180031b04  test    eax, eax
0x180031b06  jnz     loc_180031D4D
0x180031b0c  test    r15, r15
0x180031b0f  jz      short loc_180031B4F
0x180031b11  inc     rsi
0x180031b14  cmp     [r15+rsi*2], r14w
0x180031b19  jnz     short loc_180031B11
0x180031b1b  mov     rcx, [rbp+37h+var_98]; hKey
0x180031b1f  lea     eax, ds:2[rsi*2]
0x180031b26  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], eax; cbData
0x180031b2a  lea     rdx, aDllpath_0; "DLLPath"
0x180031b31  mov     r9d, 2; dwType
0x180031b37  mov     [rsp+100h+lpcSubKeys], r15; lpData
0x180031b3c  xor     r8d, r8d; Reserved
0x180031b3f  call    cs:__imp_RegSetValueExW
0x180031b45  mov     ebx, eax
0x180031b47  test    eax, eax
0x180031b49  jnz     loc_180031D4D
0x180031b4f  mov     rcx, [rbp+37h+var_98]; hKey
0x180031b53  lea     rax, [rbp+37h+cchName]
0x180031b57  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x180031b5c  lea     r9, [rbp+37h+Type]; lpType
0x180031b60  xor     r8d, r8d; lpReserved
0x180031b63  mov     [rsp+100h+lpcSubKeys], r14; lpData
0x180031b68  lea     rdx, aGlobalinfo_0; "GlobalInfo"
0x180031b6f  call    cs:__imp_RegQueryValueExW
0x180031b75  mov     edi, 3
0x180031b7a  test    eax, eax
0x180031b7c  jnz     short loc_180031B84
0x180031b7e  cmp     [rbp+37h+cchName], r14d
0x180031b82  jz      short loc_180031B89
0x180031b84  cmp     eax, 2
0x180031b87  jnz     short loc_180031BBB
0x180031b89  test    r13, r13
0x180031b8c  jz      short loc_180031BBB
0x180031b8e  mov     eax, [rbp+37h+cbData]
0x180031b91  lea     rdx, aGlobalinfo_0; "GlobalInfo"
0x180031b98  mov     rcx, [rbp+37h+var_98]; hKey
0x180031b9c  mov     r9d, edi; dwType
0x180031b9f  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], eax; cbData
0x180031ba3  xor     r8d, r8d; Reserved
0x180031ba6  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x180031bab  call    cs:__imp_RegSetValueExW
0x180031bb1  mov     ebx, eax
0x180031bb3  test    eax, eax
0x180031bb5  jnz     loc_180031D4D
0x180031bbb  mov     rcx, [rbp+37h+var_98]; hKey
0x180031bbf  lea     rax, [rbp+37h+cchName]
0x180031bc3  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x180031bc8  lea     r9, [rbp+37h+Type]; lpType
0x180031bcc  xor     r8d, r8d; lpReserved
0x180031bcf  mov     [rsp+100h+lpcSubKeys], r14; lpData
0x180031bd4  lea     rdx, aGlobalinterfac_0; "GlobalInterfaceInfo"
0x180031bdb  call    cs:__imp_RegQueryValueExW
0x180031be1  mov     ebx, eax
0x180031be3  test    eax, eax
0x180031be5  jnz     short loc_180031BF1
0x180031be7  cmp     [rbp+37h+cchName], r14d
0x180031beb  jz      loc_180031D1F
0x180031bf1  cmp     eax, 2
0x180031bf4  jmp     loc_180031D1D
0x180031bf9  cmp     [rbp+37h+arg_40], 1
0x180031c00  jnz     loc_180031D4D
0x180031c06  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031c0a  lea     rax, [rbp+37h+dwDisposition]
0x180031c0e  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x180031c13  xor     r14d, r14d
0x180031c16  lea     rax, [rbp+37h+var_98]
0x180031c1a  mov     [rbp+37h+dwDisposition], r14d
0x180031c1e  mov     [rsp+100h+lpcValues], rax; phkResult
0x180031c23  xor     r9d, r9d; lpClass
0x180031c26  mov     [rsp+100h+lpcbMaxClassLen], r14; lpSecurityAttributes
0x180031c2b  xor     r8d, r8d; Reserved
0x180031c2e  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], 3001Fh; samDesired
0x180031c36  mov     rdx, rdi; lpSubKey
0x180031c39  mov     dword ptr [rsp+100h+lpcSubKeys], r14d; dwOptions
0x180031c3e  call    cs:__imp_RegCreateKeyExW
0x180031c44  mov     ebx, eax
0x180031c46  test    eax, eax
0x180031c48  jnz     loc_180031D4D
0x180031c4e  mov     rcx, [rbp+37h+phkResult]; hKey
0x180031c52  lea     edi, [rax+4]
0x180031c55  lea     rax, [rbp+37h+Data]
0x180031c59  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], edi; cbData
0x180031c5d  mov     r9d, edi; dwType
0x180031c60  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x180031c65  xor     r8d, r8d; Reserved
0x180031c68  lea     rdx, aStamp; "Stamp"
0x180031c6f  call    cs:__imp_RegSetValueExW
0x180031c75  mov     ebx, eax
0x180031c77  test    eax, eax
0x180031c79  jnz     loc_180031D4D
0x180031c7f  mov     rcx, [rbp+37h+var_98]; hKey
0x180031c83  lea     rax, [rbp+37h+var_80]
0x180031c87  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], edi; cbData
0x180031c8b  lea     rdx, aProtocolid_0; "ProtocolId"
0x180031c92  mov     r9d, edi; dwType
0x180031c95  mov     [rsp+100h+lpcSubKeys], rax; lpData
0x180031c9a  xor     r8d, r8d; Reserved
0x180031c9d  call    cs:__imp_RegSetValueExW
0x180031ca3  mov     ebx, eax
0x180031ca5  test    eax, eax
0x180031ca7  jnz     loc_180031D4D
0x180031cad  test    r15, r15
0x180031cb0  jz      short loc_180031CEC
0x180031cb2  inc     rsi
0x180031cb5  cmp     [r15+rsi*2], r14w
0x180031cba  jnz     short loc_180031CB2
0x180031cbc  mov     rcx, [rbp+37h+var_98]; hKey
0x180031cc0  lea     eax, ds:2[rsi*2]
0x180031cc7  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], eax; cbData
0x180031ccb  lea     rdx, aDllpath_0; "DLLPath"
0x180031cd2  mov     r9d, 2; dwType
0x180031cd8  mov     [rsp+100h+lpcSubKeys], r15; lpData
0x180031cdd  xor     r8d, r8d; Reserved
0x180031ce0  call    cs:__imp_RegSetValueExW
0x180031ce6  mov     ebx, eax
0x180031ce8  test    eax, eax
0x180031cea  jnz     short loc_180031D4D
0x180031cec  mov     edi, 3
0x180031cf1  test    r13, r13
0x180031cf4  jz      short loc_180031D1F
0x180031cf6  mov     eax, [rbp+37h+cbData]
0x180031cf9  lea     rdx, aGlobalinfo_0; "GlobalInfo"
0x180031d00  mov     rcx, [rbp+37h+var_98]; hKey
0x180031d04  mov     r9d, edi; dwType
0x180031d07  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], eax; cbData
0x180031d0b  xor     r8d, r8d; Reserved
0x180031d0e  mov     [rsp+100h+lpcSubKeys], r13; lpData
0x180031d13  call    cs:__imp_RegSetValueExW
0x180031d19  mov     ebx, eax
0x180031d1b  test    eax, eax
0x180031d1d  jnz     short loc_180031D4D
0x180031d1f  mov     rcx, [rbp+37h+var_60]
0x180031d23  test    rcx, rcx
0x180031d26  jz      short loc_180031D4D
0x180031d28  mov     eax, [rbp+37h+arg_30]
0x180031d2b  lea     rdx, aGlobalinterfac_0; "GlobalInterfaceInfo"
0x180031d32  mov     dword ptr [rsp+100h+lpcbMaxSubKeyLen], eax; cbData
0x180031d36  mov     r9d, edi; dwType
0x180031d39  mov     [rsp+100h+lpcSubKeys], rcx; lpData
0x180031d3e  xor     r8d, r8d; Reserved
0x180031d41  mov     rcx, [rbp+37h+var_98]; hKey
  ... truncated ...
```
