# GetGenIdFromQueueId(ulong,ushort * *)

- ea: `0x180012bec`
- end: `0x180012e1e`
- name: `?GetGenIdFromQueueId@@YAJKPEAPEAG@Z`
- size: `562`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180012bec`
- `0x1800132fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012d51`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012d51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012cdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012cdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012c56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012c93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012c56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012c93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ddd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ddd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012d09`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180012d73`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180012d73`

## pseudocode

```c
__int64 __fastcall GetGenIdFromQueueId(int a1, unsigned __int16 **a2)
{
  WCHAR *v4; // rsi
  unsigned __int16 *v5; // r14
  LSTATUS v6; // eax
  signed int v7; // ebx
  bool v8; // cc
  signed int v9; // ecx
  DWORD v10; // edi
  unsigned int v12; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cSubKeys; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+D8h] [rbp+58h] BYREF

  *a2 = 0;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v14 = 0;
  v4 = 0;
  v12 = 0;
  v5 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\PushRouter\\Registrations\\ByGenericId",
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_szAppRegistrationByGenIdStateSep, 0, 0x20019u, &phkResult);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  v9 = cbMaxSubKeyLen + 1;
  if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
  {
    cbMaxSubKeyLen = -1;
    goto LABEL_21;
  }
  ++cbMaxSubKeyLen;
  if ( v9 < 0 )
  {
LABEL_21:
    v7 = -2147024362;
    goto LABEL_22;
  }
  v4 = (WCHAR *)LocalAlloc(0, (unsigned int)(2 * v9));
  if ( !v4 )
  {
    v7 = -2147024882;
    goto LABEL_22;
  }
  v10 = 0;
  if ( !cSubKeys )
  {
LABEL_15:
    v7 = 0;
    if ( !*a2 )
      v7 = -2147023728;
    goto LABEL_22;
  }
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    v6 = RegEnumKeyExW(hKey, v10, v4, &cchName, 0, 0, 0, 0);
    v7 = v6;
    v8 = v6 <= 0;
    if ( v6 )
      break;
    if ( (int)OmaDmRegistryGetDWORD(phkResult, v4, L"QueueId", &v12) >= 0 && v12 == a1 )
    {
      v7 = QueryStringValue(hKey, v4, L"GenId", &v14);
      if ( v7 >= 0 )
      {
        *a2 = v14;
        goto LABEL_15;
      }
      v5 = v14;
      goto LABEL_22;
    }
    if ( ++v10 >= cSubKeys )
      goto LABEL_15;
  }
LABEL_2:
  if ( !v8 )
    v7 = (unsigned __int16)v6 | 0x80070000;
LABEL_22:
  LocalFree(v5);
  LocalFree(v4);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012bec  mov     [rsp-38h+arg_0], rbx
0x180012bf1  push    rbp
0x180012bf2  push    rsi
0x180012bf3  push    rdi
0x180012bf4  push    r12
0x180012bf6  push    r13
0x180012bf8  push    r14
0x180012bfa  push    r15
0x180012bfc  mov     rbp, rsp
0x180012bff  sub     rsp, 80h
0x180012c06  xor     r13d, r13d
0x180012c09  lea     rax, [rbp+hKey]
0x180012c0d  mov     [rdx], r13
0x180012c10  mov     r15, rdx
0x180012c13  mov     r12d, ecx
0x180012c16  mov     [rbp+hKey], r13
0x180012c1a  mov     edi, 20019h
0x180012c1f  mov     [rbp+var_8], r13
0x180012c23  lea     rdx, ?c_szAppRegistrationByGenId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x180012c2a  mov     [rbp+cSubKeys], r13d
0x180012c2e  mov     r9d, edi; samDesired
0x180012c31  mov     [rbp+cbMaxSubKeyLen], r13d
0x180012c35  xor     r8d, r8d; ulOptions
0x180012c38  mov     [rbp+cchName], r13d
0x180012c3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012c43  mov     [rbp+var_10], r13
0x180012c47  mov     esi, r13d
0x180012c4a  mov     [rbp+var_20], r13d
0x180012c4e  mov     r14d, r13d
0x180012c51  mov     [rsp+80h+phkResult], rax; phkResult
0x180012c56  call    cs:__imp_RegOpenKeyExW
0x180012c5c  mov     ebx, eax
0x180012c5e  test    eax, eax
0x180012c60  jz      short loc_180012C76
0x180012c62  jle     loc_180012DD1
0x180012c68  movzx   ebx, ax
0x180012c6b  or      ebx, 80070000h
0x180012c71  jmp     loc_180012DD1
0x180012c76  mov     rdx, cs:?c_szAppRegistrationByGenIdStateSep@@3QEAGEA; lpSubKey
0x180012c7d  lea     rax, [rbp+var_8]
0x180012c81  mov     r9d, edi; samDesired
0x180012c84  mov     [rsp+80h+phkResult], rax; phkResult
0x180012c89  xor     r8d, r8d; ulOptions
0x180012c8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012c93  call    cs:__imp_RegOpenKeyExW
0x180012c99  mov     ebx, eax
0x180012c9b  test    eax, eax
0x180012c9d  jnz     short loc_180012C62
0x180012c9f  mov     rcx, [rbp+hKey]; hKey
0x180012ca3  lea     rax, [rbp+cbMaxSubKeyLen]
0x180012ca7  mov     [rsp+80h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180012cac  xor     r9d, r9d; lpReserved
0x180012caf  mov     [rsp+80h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180012cb4  xor     r8d, r8d; lpcchClass
0x180012cb7  mov     [rsp+80h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180012cbc  xor     edx, edx; lpClass
0x180012cbe  mov     [rsp+80h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180012cc3  mov     [rsp+80h+lpcValues], r13; lpcValues
0x180012cc8  mov     [rsp+80h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180012ccd  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180012cd2  lea     rax, [rbp+cSubKeys]
0x180012cd6  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x180012cdb  call    cs:__imp_RegQueryInfoKeyW
0x180012ce1  mov     ebx, eax
0x180012ce3  test    eax, eax
0x180012ce5  jnz     loc_180012C62
0x180012ceb  mov     eax, [rbp+cbMaxSubKeyLen]
0x180012cee  lea     ecx, [rax+1]
0x180012cf1  cmp     ecx, eax
0x180012cf3  jb      loc_180012DC5
0x180012cf9  mov     [rbp+cbMaxSubKeyLen], ecx
0x180012cfc  test    ecx, ecx
0x180012cfe  js      loc_180012DCC
0x180012d04  lea     edx, [rcx+rcx]; uBytes
0x180012d07  xor     ecx, ecx; uFlags
0x180012d09  call    cs:__imp_LocalAlloc
0x180012d0f  mov     rsi, rax
0x180012d12  test    rax, rax
0x180012d15  jnz     short loc_180012D21
0x180012d17  mov     ebx, 8007000Eh
0x180012d1c  jmp     loc_180012DD1
0x180012d21  mov     edi, r13d
0x180012d24  cmp     [rbp+cSubKeys], r13d
0x180012d28  jbe     short loc_180012D8A
0x180012d2a  mov     eax, [rbp+cbMaxSubKeyLen]
0x180012d2d  lea     r9, [rbp+cchName]; lpcchName
0x180012d31  mov     rcx, [rbp+hKey]; hKey
0x180012d35  mov     r8, rsi; lpName
0x180012d38  mov     [rsp+80h+lpcValues], r13; lpftLastWriteTime
0x180012d3d  mov     edx, edi; dwIndex
0x180012d3f  mov     [rsp+80h+lpcbMaxClassLen], r13; lpcchClass
0x180012d44  mov     [rsp+80h+lpcbMaxSubKeyLen], r13; lpClass
0x180012d49  mov     [rsp+80h+phkResult], r13; lpReserved
0x180012d4e  mov     [rbp+cchName], eax
0x180012d51  call    cs:__imp_RegEnumKeyExW
0x180012d57  mov     ebx, eax
0x180012d59  test    eax, eax
0x180012d5b  jnz     loc_180012C62
0x180012d61  mov     rcx, [rbp+var_8]
0x180012d65  lea     r9, [rbp+var_20]
0x180012d69  lea     r8, ?c_szQueueId@@3QBGB; "QueueId"
0x180012d70  mov     rdx, rsi
0x180012d73  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180012d79  test    eax, eax
0x180012d7b  js      short loc_180012D83
0x180012d7d  cmp     [rbp+var_20], r12d
0x180012d81  jz      short loc_180012D99
0x180012d83  inc     edi
0x180012d85  cmp     edi, [rbp+cSubKeys]
0x180012d88  jb      short loc_180012D2A
0x180012d8a  mov     ebx, r13d
0x180012d8d  cmp     [r15], r13
0x180012d90  jnz     short loc_180012DD1
0x180012d92  mov     ebx, 80070490h
0x180012d97  jmp     short loc_180012DD1
0x180012d99  mov     rcx, [rbp+hKey]; HKEY
0x180012d9d  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180012da1  lea     r8, ?c_szGenId@@3QBGB; "GenId"
0x180012da8  mov     rdx, rsi; unsigned __int16 *
0x180012dab  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180012db0  mov     ebx, eax
0x180012db2  test    eax, eax
0x180012db4  js      short loc_180012DBF
0x180012db6  mov     rax, [rbp+var_10]
0x180012dba  mov     [r15], rax
0x180012dbd  jmp     short loc_180012D8A
0x180012dbf  mov     r14, [rbp+var_10]
0x180012dc3  jmp     short loc_180012DD1
0x180012dc5  mov     [rbp+cbMaxSubKeyLen], 0FFFFFFFFh
0x180012dcc  mov     ebx, 80070216h
0x180012dd1  mov     rcx, r14; hMem
0x180012dd4  call    cs:__imp_LocalFree
0x180012dda  mov     rcx, rsi; hMem
0x180012ddd  call    cs:__imp_LocalFree
0x180012de3  mov     rcx, [rbp+hKey]; hKey
0x180012de7  test    rcx, rcx
0x180012dea  jz      short loc_180012DF2
0x180012dec  call    cs:__imp_RegCloseKey
0x180012df2  mov     rcx, [rbp+var_8]; hKey
0x180012df6  test    rcx, rcx
0x180012df9  jz      short loc_180012E01
0x180012dfb  call    cs:__imp_RegCloseKey
0x180012e01  mov     eax, ebx
0x180012e03  mov     rbx, [rsp+80h+arg_0]
0x180012e0b  add     rsp, 80h
0x180012e12  pop     r15
0x180012e14  pop     r14
0x180012e16  pop     r13
0x180012e18  pop     r12
0x180012e1a  pop     rdi
0x180012e1b  pop     rsi
0x180012e1c  pop     rbp
0x180012e1d  retn
```
