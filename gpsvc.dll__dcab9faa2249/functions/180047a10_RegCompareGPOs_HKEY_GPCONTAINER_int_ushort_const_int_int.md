# RegCompareGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *,int *,int *)

- ea: `0x180047a10`
- end: `0x180048007`
- name: `?RegCompareGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBGPEAH3@Z`
- size: `1527`
- prototype: `unsigned int(HKEY, struct _GPCONTAINER *, int, const unsigned __int16 *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800473b0`

## callees

- `0x180047a10`
- `0x18007d320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180047b39`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180047b39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047dc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047e13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047ee5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047f47`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047dc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047e13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047ee5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047f47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047bc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047bc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047fe0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047ff1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047fe0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047e99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047fb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ffc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047e99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047fb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ffc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047aba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047ba0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047aba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047ba0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047a68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047b58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047a68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047b58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047c0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047c6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047cbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047db1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047e00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047e5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047f31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047c0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047c6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047cbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047d69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047db1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047e00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047e5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047f31`

## string_xrefs

- `0x180047c9c`: `AccessDenied`

## pseudocode

```c
LSTATUS __fastcall RegCompareGPOs(
        HKEY a1,
        struct _GPCONTAINER *a2,
        int a3,
        const unsigned __int16 *a4,
        int *a5,
        int *a6)
{
  LSTATUS result; // eax
  LSTATUS v9; // ebx
  struct _GPCONTAINER *v10; // rcx
  int i; // eax
  int v12; // r14d
  _WORD *v13; // rsi
  wchar_t *v14; // rax
  DWORD v15; // r15d
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rax
  const WCHAR *v19; // r14
  const WCHAR *v20; // r14
  HKEY v21; // rcx
  HKEY v22; // rcx
  DWORD cbData; // [rsp+60h] [rbp-69h] BYREF
  DWORD Type; // [rsp+64h] [rbp-65h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-61h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-59h] BYREF
  int v27; // [rsp+78h] [rbp-51h]
  HKEY hKey; // [rsp+80h] [rbp-49h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-41h] BYREF
  DWORD cbMaxValueLen; // [rsp+8Ch] [rbp-3Dh] BYREF
  wchar_t Buffer[32]; // [rsp+90h] [rbp-39h] BYREF

  *a5 = 0;
  *a6 = 0;
  hKey = 0;
  result = RegOpenKeyExW(a1, a4, 0, 0xF003Fu, &hKey);
  if ( result )
  {
    *a5 = 1;
    return result;
  }
  cSubKeys = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v9 )
  {
    v21 = hKey;
    *a5 = 1;
    *a6 = 1;
    RegCloseKey(v21);
    return v9;
  }
  v10 = a2;
  for ( i = 0; v10; ++i )
    v10 = (struct _GPCONTAINER *)*((_QWORD *)v10 + 14);
  if ( i != cSubKeys )
  {
    v22 = hKey;
    *a5 = 1;
    *a6 = 1;
    RegCloseKey(v22);
    return 0;
  }
  v12 = 0;
  phkResult = 0;
  v13 = 0;
  v27 = 0;
  if ( !a2 )
    goto LABEL_42;
  while ( !v9 && !*a5 )
  {
    Type = 0;
    cbData = 0;
    *(_DWORD *)Data = 0;
    cbMaxValueLen = 0;
    if ( v13 )
    {
      LocalFree(v13);
      v13 = 0;
    }
    v14 = _itow(v12, Buffer, 16);
    v9 = RegOpenKeyExW(hKey, v14, 0, 0xF003Fu, &phkResult);
    if ( !v9 )
    {
      v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      if ( !v9 )
      {
        v15 = cbMaxValueLen + 2;
        if ( cbMaxValueLen + 2 < cbMaxValueLen )
        {
          v9 = 534;
        }
        else
        {
          v13 = LocalAlloc(0x40u, v15);
          if ( v13 )
          {
            cbData = 4;
            Type = 0;
            *(_DWORD *)Data = 0;
            v9 = RegQueryValueExW(phkResult, L"Version", 0, &Type, Data, &cbData);
            if ( !v9 )
            {
              v16 = 52;
              if ( !a3 )
                v16 = 48;
              if ( *(_DWORD *)Data == *(_DWORD *)((char *)a2 + v16) )
              {
                cbData = 4;
                Type = 0;
                *(_DWORD *)Data = 0;
                v9 = RegQueryValueExW(phkResult, L"WQLFilterPass", 0, &Type, Data, &cbData);
                if ( !v9 && *(_DWORD *)Data == *((_DWORD *)a2 + 17) )
                {
                  cbData = 4;
                  Type = 0;
                  *(_DWORD *)Data = 0;
                  v9 = RegQueryValueExW(phkResult, L"AccessDenied", 0, &Type, Data, &cbData);
                  if ( !v9 && *(_DWORD *)Data == *((_DWORD *)a2 + 9) )
                  {
                    cbData = 4;
                    Type = 0;
                    *(_DWORD *)Data = 0;
                    v9 = RegQueryValueExW(phkResult, L"GPO-Disabled", 0, &Type, Data, &cbData);
                    if ( !v9 )
                    {
                      v17 = 44;
                      if ( !a3 )
                        v17 = 40;
                      if ( *(_DWORD *)Data == *(_DWORD *)((char *)a2 + v17) )
                      {
                        cbData = 4;
                        Type = 0;
                        *(_DWORD *)Data = 0;
                        v9 = RegQueryValueExW(phkResult, L"Options", 0, &Type, Data, &cbData);
                        if ( !v9 && *(_DWORD *)Data == *((_DWORD *)a2 + 22) )
                        {
                          Type = 0;
                          *v13 = 0;
                          cbData = v15;
                          v9 = RegQueryValueExW(phkResult, L"GPOID", 0, &Type, (LPBYTE)v13, &cbData);
                          if ( !v9 && !(unsigned int)_o__wcsicmp(v13, *((_QWORD *)a2 + 1)) )
                          {
                            Type = 0;
                            *v13 = 0;
                            cbData = v15;
                            v9 = RegQueryValueExW(phkResult, L"SOM", 0, &Type, (LPBYTE)v13, &cbData);
                            if ( !v9 && !(unsigned int)_o__wcsicmp(v13, *((_QWORD *)a2 + 10)) )
                            {
                              v18 = (const WCHAR *)*((_QWORD *)a2 + 2);
                              v19 = &DomainName;
                              Type = 0;
                              if ( v18 )
                                v19 = v18;
                              *v13 = 0;
                              cbData = v15;
                              v9 = RegQueryValueExW(phkResult, L"DisplayName", 0, &Type, (LPBYTE)v13, &cbData);
                              if ( !v9 && !(unsigned int)_o__wcsicmp(v13, v19) )
                              {
                                v20 = &DomainName;
                                if ( *((_QWORD *)a2 + 9) )
                                  v20 = (const WCHAR *)*((_QWORD *)a2 + 9);
                                Type = 0;
                                *v13 = 0;
                                cbData = v15;
                                v9 = RegQueryValueExW(phkResult, L"WQL-Id", 0, &Type, (LPBYTE)v13, &cbData);
                                if ( !v9 && !(unsigned int)_o__wcsicmp(v13, v20) )
                                {
                                  RegCloseKey(phkResult);
                                  phkResult = 0;
                                  LocalFree(v13);
                                  v13 = 0;
                                  a2 = (struct _GPCONTAINER *)*((_QWORD *)a2 + 14);
                                  v12 = ++v27;
                                  goto LABEL_37;
                                }
                              }
                              v12 = v27;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    *a5 = 1;
LABEL_37:
    if ( !a2 )
      break;
  }
  if ( v13 )
    LocalFree(v13);
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_42:
  RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180047a10  push    rbp
0x180047a12  push    rsi
0x180047a13  push    rdi
0x180047a14  push    r12
0x180047a16  push    r13
0x180047a18  push    r15
0x180047a1a  lea     rbp, [rsp-1Fh]
0x180047a1f  sub     rsp, 0E8h
0x180047a26  mov     rax, cs:__security_cookie
0x180047a2d  xor     rax, rsp
0x180047a30  mov     [rbp+47h+var_40], rax
0x180047a34  mov     r12, [rbp+47h+arg_20]
0x180047a38  mov     rdi, rdx
0x180047a3b  mov     rsi, [rbp+47h+arg_28]
0x180047a3f  lea     rdx, [rbp+47h+hKey]
0x180047a43  mov     rax, r9
0x180047a46  mov     [rsp+110h+phkResult], rdx; phkResult
0x180047a4b  xor     r15d, r15d
0x180047a4e  mov     r13d, r8d
0x180047a51  mov     [r12], r15d
0x180047a55  mov     r9d, 0F003Fh; samDesired
0x180047a5b  xor     r8d, r8d; ulOptions
0x180047a5e  mov     [rsi], r15d
0x180047a61  mov     rdx, rax; lpSubKey
0x180047a64  mov     [rbp+47h+hKey], r15
0x180047a68  call    cs:__imp_RegOpenKeyExW
0x180047a6e  test    eax, eax
0x180047a70  jnz     loc_180047ED5
0x180047a76  mov     rcx, [rbp+47h+hKey]; hKey
0x180047a7a  lea     rax, [rbp+47h+cSubKeys]
0x180047a7e  mov     [rsp+110h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180047a83  xor     r9d, r9d; lpReserved
0x180047a86  mov     [rsp+110h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180047a8b  xor     r8d, r8d; lpcchClass
0x180047a8e  mov     [rsp+110h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180047a93  xor     edx, edx; lpClass
0x180047a95  mov     [rsp+110h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180047a9a  mov     [rsp+110h+lpcValues], r15; lpcValues
0x180047a9f  mov     [rsp+110h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180047aa4  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180047aa9  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x180047aae  mov     [rsp+110h+arg_10], rbx
0x180047ab6  mov     [rbp+47h+cSubKeys], r15d
0x180047aba  call    cs:__imp_RegQueryInfoKeyW
0x180047ac0  mov     ebx, eax
0x180047ac2  test    eax, eax
0x180047ac4  jnz     loc_180047FA1
0x180047aca  mov     rcx, rdi
0x180047acd  mov     eax, r15d
0x180047ad0  test    rdi, rdi
0x180047ad3  jnz     loc_180047F90
0x180047ad9  cmp     eax, [rbp+47h+cSubKeys]
0x180047adc  jnz     loc_180047FBE
0x180047ae2  mov     [rsp+110h+var_30], r14
0x180047aea  mov     r14d, r15d
0x180047aed  mov     [rbp+47h+var_A0], r15
0x180047af1  mov     rsi, r15
0x180047af4  mov     [rbp+47h+var_98], r15d
0x180047af8  test    rdi, rdi
0x180047afb  jz      loc_180047E95
0x180047b01  test    ebx, ebx
0x180047b03  jnz     loc_180047E7F
0x180047b09  cmp     [r12], ebx
0x180047b0d  jnz     loc_180047E7F
0x180047b13  mov     [rbp+47h+Type], r15d
0x180047b17  mov     [rbp+47h+cbData], r15d
0x180047b1b  mov     dword ptr [rbp+47h+Data], r15d
0x180047b1f  mov     [rbp+47h+cbMaxValueLen], r15d
0x180047b23  test    rsi, rsi
0x180047b26  jnz     loc_180047FDD
0x180047b2c  mov     r8d, 10h; Radix
0x180047b32  lea     rdx, [rbp+47h+Buffer]; Buffer
0x180047b36  mov     ecx, r14d; Value
0x180047b39  call    cs:__imp__itow
0x180047b3f  lea     rcx, [rbp+47h+var_A0]
0x180047b43  mov     r9d, 0F003Fh; samDesired
0x180047b49  mov     [rsp+110h+phkResult], rcx; phkResult
0x180047b4e  xor     r8d, r8d; ulOptions
0x180047b51  mov     rcx, [rbp+47h+hKey]; hKey
0x180047b55  mov     rdx, rax; lpSubKey
0x180047b58  call    cs:__imp_RegOpenKeyExW
0x180047b5e  mov     ebx, eax
0x180047b60  test    eax, eax
0x180047b62  jnz     loc_180047E6E
0x180047b68  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047b6c  lea     rax, [rbp+47h+cbMaxValueLen]
0x180047b70  mov     [rsp+110h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180047b75  xor     r9d, r9d; lpReserved
0x180047b78  mov     [rsp+110h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180047b7d  xor     r8d, r8d; lpcchClass
0x180047b80  mov     [rsp+110h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180047b85  xor     edx, edx; lpClass
0x180047b87  mov     [rsp+110h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180047b8c  mov     [rsp+110h+lpcValues], r15; lpcValues
0x180047b91  mov     [rsp+110h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180047b96  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180047b9b  mov     [rsp+110h+phkResult], r15; lpcSubKeys
0x180047ba0  call    cs:__imp_RegQueryInfoKeyW
0x180047ba6  mov     ebx, eax
0x180047ba8  test    eax, eax
0x180047baa  jnz     loc_180047E6E
0x180047bb0  mov     eax, [rbp+47h+cbMaxValueLen]
0x180047bb3  lea     r15d, [rax+2]
0x180047bb7  cmp     r15d, eax
0x180047bba  jb      loc_180047ECE
0x180047bc0  mov     edx, r15d; uBytes
0x180047bc3  mov     ecx, 40h ; '@'; uFlags
0x180047bc8  call    cs:__imp_LocalAlloc
0x180047bce  mov     rsi, rax
0x180047bd1  test    rax, rax
0x180047bd4  jz      loc_180047E6B
0x180047bda  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047bde  lea     r9, [rbp+47h+Type]; lpType
0x180047be2  xor     eax, eax
0x180047be4  mov     [rbp+47h+cbData], 4
0x180047beb  mov     [rbp+47h+Type], eax
0x180047bee  lea     rdx, aVersion_1; "Version"
0x180047bf5  mov     dword ptr [rbp+47h+Data], eax
0x180047bf8  xor     r8d, r8d; lpReserved
0x180047bfb  lea     rax, [rbp+47h+cbData]
0x180047bff  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047c04  lea     rax, [rbp+47h+Data]
0x180047c08  mov     [rsp+110h+phkResult], rax; lpData
0x180047c0d  call    cs:__imp_RegQueryValueExW
0x180047c13  mov     ebx, eax
0x180047c15  test    eax, eax
0x180047c17  jnz     loc_180047E6B
0x180047c1d  test    r13d, r13d
0x180047c20  mov     eax, 34h ; '4'
0x180047c25  mov     ecx, 30h ; '0'
0x180047c2a  cmovz   eax, ecx
0x180047c2d  mov     eax, [rax+rdi]
0x180047c30  cmp     dword ptr [rbp+47h+Data], eax
0x180047c33  jnz     loc_180047E6B
0x180047c39  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047c3d  lea     r9, [rbp+47h+Type]; lpType
0x180047c41  xor     eax, eax
0x180047c43  mov     [rbp+47h+cbData], 4
0x180047c4a  mov     [rbp+47h+Type], eax
0x180047c4d  lea     rdx, aWqlfilterpass; "WQLFilterPass"
0x180047c54  mov     dword ptr [rbp+47h+Data], eax
0x180047c57  xor     r8d, r8d; lpReserved
0x180047c5a  lea     rax, [rbp+47h+cbData]
0x180047c5e  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047c63  lea     rax, [rbp+47h+Data]
0x180047c67  mov     [rsp+110h+phkResult], rax; lpData
0x180047c6c  call    cs:__imp_RegQueryValueExW
0x180047c72  mov     ebx, eax
0x180047c74  test    eax, eax
0x180047c76  jnz     loc_180047E6B
0x180047c7c  mov     eax, [rdi+44h]
0x180047c7f  cmp     dword ptr [rbp+47h+Data], eax
0x180047c82  jnz     loc_180047E6B
0x180047c88  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047c8c  lea     r9, [rbp+47h+Type]; lpType
0x180047c90  xor     eax, eax
0x180047c92  mov     [rbp+47h+cbData], 4
0x180047c99  mov     [rbp+47h+Type], eax
0x180047c9c  lea     rdx, aAccessdenied; "AccessDenied"
0x180047ca3  mov     dword ptr [rbp+47h+Data], eax
0x180047ca6  xor     r8d, r8d; lpReserved
0x180047ca9  lea     rax, [rbp+47h+cbData]
0x180047cad  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047cb2  lea     rax, [rbp+47h+Data]
0x180047cb6  mov     [rsp+110h+phkResult], rax; lpData
0x180047cbb  call    cs:__imp_RegQueryValueExW
0x180047cc1  mov     ebx, eax
0x180047cc3  test    eax, eax
0x180047cc5  jnz     loc_180047E6B
0x180047ccb  mov     eax, [rdi+24h]
0x180047cce  cmp     dword ptr [rbp+47h+Data], eax
0x180047cd1  jnz     loc_180047E6B
0x180047cd7  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047cdb  lea     r9, [rbp+47h+Type]; lpType
0x180047cdf  xor     eax, eax
0x180047ce1  mov     [rbp+47h+cbData], 4
0x180047ce8  mov     [rbp+47h+Type], eax
0x180047ceb  lea     rdx, aGpoDisabled; "GPO-Disabled"
0x180047cf2  mov     dword ptr [rbp+47h+Data], eax
0x180047cf5  xor     r8d, r8d; lpReserved
0x180047cf8  lea     rax, [rbp+47h+cbData]
0x180047cfc  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047d01  lea     rax, [rbp+47h+Data]
0x180047d05  mov     [rsp+110h+phkResult], rax; lpData
0x180047d0a  call    cs:__imp_RegQueryValueExW
0x180047d10  mov     ebx, eax
0x180047d12  test    eax, eax
0x180047d14  jnz     loc_180047E6B
0x180047d1a  test    r13d, r13d
0x180047d1d  mov     eax, 2Ch ; ','
0x180047d22  mov     ecx, 28h ; '('
0x180047d27  cmovz   eax, ecx
0x180047d2a  mov     eax, [rax+rdi]
0x180047d2d  cmp     dword ptr [rbp+47h+Data], eax
0x180047d30  jnz     loc_180047E6B
0x180047d36  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047d3a  lea     r9, [rbp+47h+Type]; lpType
0x180047d3e  xor     eax, eax
0x180047d40  mov     [rbp+47h+cbData], 4
0x180047d47  mov     [rbp+47h+Type], eax
0x180047d4a  lea     rdx, aOptions; "Options"
0x180047d51  mov     dword ptr [rbp+47h+Data], eax
0x180047d54  xor     r8d, r8d; lpReserved
0x180047d57  lea     rax, [rbp+47h+cbData]
0x180047d5b  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047d60  lea     rax, [rbp+47h+Data]
0x180047d64  mov     [rsp+110h+phkResult], rax; lpData
0x180047d69  call    cs:__imp_RegQueryValueExW
0x180047d6f  mov     ebx, eax
0x180047d71  test    eax, eax
0x180047d73  jnz     loc_180047E6B
0x180047d79  mov     eax, [rdi+58h]
0x180047d7c  cmp     dword ptr [rbp+47h+Data], eax
0x180047d7f  jnz     loc_180047E6B
0x180047d85  xor     eax, eax
0x180047d87  mov     [rbp+47h+Type], ebx
0x180047d8a  mov     [rsi], ax
0x180047d8d  lea     r9, [rbp+47h+Type]; lpType
0x180047d91  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047d95  lea     rax, [rbp+47h+cbData]
0x180047d99  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047d9e  lea     rdx, aGpoid; "GPOID"
0x180047da5  xor     r8d, r8d; lpReserved
0x180047da8  mov     [rsp+110h+phkResult], rsi; lpData
0x180047dad  mov     [rbp+47h+cbData], r15d
0x180047db1  call    cs:__imp_RegQueryValueExW
0x180047db7  mov     ebx, eax
0x180047db9  test    eax, eax
0x180047dbb  jnz     loc_180047E6B
0x180047dc1  mov     rdx, [rdi+8]
0x180047dc5  mov     rcx, rsi
0x180047dc8  call    cs:__imp__o__wcsicmp
0x180047dce  test    eax, eax
0x180047dd0  jnz     loc_180047E6B
0x180047dd6  mov     [rbp+47h+Type], eax
0x180047dd9  lea     r9, [rbp+47h+Type]; lpType
0x180047ddd  mov     [rsi], ax
0x180047de0  lea     rdx, aSom; "SOM"
0x180047de7  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047deb  lea     rax, [rbp+47h+cbData]
0x180047def  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047df4  xor     r8d, r8d; lpReserved
0x180047df7  mov     [rsp+110h+phkResult], rsi; lpData
0x180047dfc  mov     [rbp+47h+cbData], r15d
0x180047e00  call    cs:__imp_RegQueryValueExW
0x180047e06  mov     ebx, eax
0x180047e08  test    eax, eax
0x180047e0a  jnz     short loc_180047E6B
0x180047e0c  mov     rdx, [rdi+50h]
0x180047e10  mov     rcx, rsi
0x180047e13  call    cs:__imp__o__wcsicmp
0x180047e19  test    eax, eax
0x180047e1b  jnz     short loc_180047E6B
0x180047e1d  mov     rax, [rdi+10h]
0x180047e21  lea     r14, DomainName
0x180047e28  test    rax, rax
0x180047e2b  mov     [rbp+47h+Type], ebx
0x180047e2e  lea     r9, [rbp+47h+Type]; lpType
0x180047e32  cmovnz  r14, rax
0x180047e36  lea     rdx, aDisplayname; "DisplayName"
0x180047e3d  xor     eax, eax
0x180047e3f  xor     r8d, r8d; lpReserved
0x180047e42  mov     [rsi], ax
0x180047e45  lea     rax, [rbp+47h+cbData]
0x180047e49  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047e4d  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047e52  mov     [rsp+110h+phkResult], rsi; lpData
0x180047e57  mov     [rbp+47h+cbData], r15d
0x180047e5b  call    cs:__imp_RegQueryValueExW
0x180047e61  mov     ebx, eax
0x180047e63  test    eax, eax
0x180047e65  jz      short loc_180047EDF
0x180047e67  mov     r14d, [rbp+47h+var_98]
0x180047e6b  xor     r15d, r15d
0x180047e6e  mov     dword ptr [r12], 1
0x180047e76  test    rdi, rdi
0x180047e79  jnz     loc_180047B01
0x180047e7f  test    rsi, rsi
0x180047e82  jnz     loc_180047FEE
0x180047e88  mov     rcx, [rbp+47h+var_A0]; hKey
0x180047e8c  test    rcx, rcx
0x180047e8f  jnz     loc_180047FFC
0x180047e95  mov     rcx, [rbp+47h+hKey]; hKey
0x180047e99  call    cs:__imp_RegCloseKey
0x180047e9f  mov     r14, [rsp+110h+var_30]
0x180047ea7  mov     eax, ebx
0x180047ea9  mov     rbx, [rsp+110h+arg_10]
0x180047eb1  mov     rcx, [rbp+47h+var_40]
0x180047eb5  xor     rcx, rsp; StackCookie
0x180047eb8  call    __security_check_cookie
0x180047ebd  add     rsp, 0E8h
0x180047ec4  pop     r15
0x180047ec6  pop     r13
0x180047ec8  pop     r12
0x180047eca  pop     rdi
0x180047ecb  pop     rsi
0x180047ecc  pop     rbp
0x180047ecd  retn
0x180047ece  mov     ebx, 216h
0x180047ed3  jmp     short loc_180047E6B
  ... truncated ...
```
