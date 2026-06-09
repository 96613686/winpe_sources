# LoadTransports

- ea: `0x180022be8`
- end: `0x180022f26`
- name: `LoadTransports`
- size: `830`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800274d0`
- `0x180027da0`
- `0x1800281c0`
- `0x180028430`

## callees

- `0x180017700`
- `0x180018470`
- `0x180022be8`
- `0x1800291b4`
- `0x18002998c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022dfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022dfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ead`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022cdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022e0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022cdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022e0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ebb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022e96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022de1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022e96`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180022c91`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180022c91`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022d39`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022d39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022d61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022d61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022d9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022d9c`

## string_xrefs

- `0x180022d95`: `ProtocolId`

## pseudocode

```c
LSTATUS __fastcall LoadTransports(__int64 a1)
{
  _QWORD *v1; // rax
  _QWORD **v2; // rsi
  DWORD v3; // r12d
  HKEY *v5; // r14
  LSTATUS result; // eax
  LSTATUS v7; // edi
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // r13
  HKEY v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rdi
  unsigned int v14; // eax
  bool v15; // zf
  HKEY v16; // rcx
  HANDLE v17; // rax
  _OWORD *v18; // rax
  _QWORD *v19; // rdi
  PWSTR v20; // rax
  HANDLE v21; // rax
  _QWORD *v22; // rcx
  HANDLE v23; // rax
  _QWORD *i; // rbx
  _QWORD *v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  DWORD Type; // [rsp+60h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+C8h] [rbp+50h] BYREF
  DWORD cSubKeys; // [rsp+D0h] [rbp+58h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+60h] BYREF

  v1 = *(_QWORD **)(a1 + 80);
  v2 = (_QWORD **)(a1 + 80);
  v3 = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  Data = 0;
  Type = 0;
  cchName = 0;
  while ( v1 != v2 )
  {
    *((_DWORD *)v1 - 2) = 1;
    v1 = (_QWORD *)*v1;
  }
  v5 = (HKEY *)(a1 + 40);
  if ( !*(_QWORD *)(a1 + 40) && (unsigned int)AccessRouterSubkey(*(HKEY *)(a1 + 16), L"RouterManagers", 0, v5) )
    return 0;
  result = RegQueryInfoKeyW(*v5, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v7 = result;
  if ( result )
    return result;
  if ( !cSubKeys )
    return 0;
  if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen || 2 * (unsigned __int64)(cbMaxSubKeyLen + 1) > 0xFFFFFFFF )
    return 534;
  v8 = 2 * (cbMaxSubKeyLen + 1);
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v8);
  if ( !v10 )
    return 8;
  if ( cSubKeys )
  {
    while ( 1 )
    {
      v11 = *v5;
      cchName = cbMaxSubKeyLen + 1;
      v7 = RegEnumKeyExW(v11, v3, v10, &cchName, 0, 0, 0, 0);
      if ( v7 )
        goto LABEL_36;
      v7 = RegOpenKeyExW(*v5, v10, 0, 0x3001Fu, &phkResult);
      if ( !v7 )
        break;
LABEL_35:
      if ( ++v3 >= cSubKeys )
        goto LABEL_36;
    }
    cchName = 4;
    if ( !RegQueryValueExW(phkResult, L"ProtocolId", 0, &Type, (LPBYTE)&Data, &cchName) )
    {
      v12 = *(_QWORD **)(a1 + 80);
      v2 = (_QWORD **)(a1 + 80);
      if ( v12 != (_QWORD *)(a1 + 80) )
      {
        while ( 1 )
        {
          v13 = v12 - 4;
          v14 = *((_DWORD *)v12 - 8);
          v15 = v14 == Data;
          if ( v14 >= Data )
            break;
          v12 = (_QWORD *)*v12;
          if ( v12 == v2 )
          {
            v15 = v14 == Data;
            break;
          }
        }
        if ( v15 )
        {
          v16 = (HKEY)v13[2];
          *((_DWORD *)v13 + 6) = 0;
          if ( v16 )
            RegCloseKey(v16);
          v13[2] = phkResult;
          v7 = 0;
          phkResult = 0;
          goto LABEL_35;
        }
      }
      v17 = GetProcessHeap();
      v18 = HeapAlloc(v17, 0, 0x30u);
      v19 = v18;
      if ( !v18 )
        goto LABEL_26;
      *v18 = 0;
      v18[1] = 0;
      v18[2] = 0;
      v20 = StrDupW(v10);
      v19[1] = v20;
      if ( !v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v19);
LABEL_26:
        v7 = 8;
        goto LABEL_32;
      }
      *(_DWORD *)v19 = Data;
      v19[2] = phkResult;
      phkResult = 0;
      v22 = (_QWORD *)v12[1];
      if ( (_QWORD *)*v22 != v12 )
LABEL_44:
        __fastfail(3u);
      v19[4] = v12;
      v19[5] = v22;
      *v22 = v19 + 4;
      v12[1] = v19 + 4;
    }
    v7 = 0;
LABEL_32:
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v7 )
      goto LABEL_36;
    goto LABEL_35;
  }
LABEL_36:
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v10);
  for ( i = *v2; i != v2; i = (_QWORD *)*i )
  {
    v25 = i - 4;
    if ( *((_DWORD *)i - 2) )
    {
      v26 = (_QWORD *)*i;
      if ( *(_QWORD **)(*i + 8LL) != i )
        goto LABEL_44;
      v27 = (_QWORD *)i[1];
      if ( (_QWORD *)*v27 != i )
        goto LABEL_44;
      *v27 = v26;
      i = v27;
      v26[1] = v27;
      FreeTransport(v25);
    }
  }
  UpdateTimeStamp(*v5, (PFILETIME)(a1 + 48));
  return v7;
}

```

## disassembly

```asm
0x180022be8  push    rbp
0x180022bea  push    rbx
0x180022beb  push    rsi
0x180022bec  push    rdi
0x180022bed  push    r12
0x180022bef  push    r13
0x180022bf1  push    r14
0x180022bf3  push    r15
0x180022bf5  mov     rbp, rsp
0x180022bf8  sub     rsp, 78h
0x180022bfc  mov     rax, [rcx+50h]
0x180022c00  lea     rsi, [rcx+50h]
0x180022c04  xor     r12d, r12d
0x180022c07  mov     r15, rcx
0x180022c0a  mov     [rbp+phkResult], r12
0x180022c0e  mov     [rbp+cSubKeys], r12d
0x180022c12  mov     [rbp+cbMaxSubKeyLen], r12d
0x180022c16  mov     [rbp+Data], r12d
0x180022c1a  mov     [rbp+Type], r12d
0x180022c1e  mov     [rbp+cchName], r12d
0x180022c22  jmp     short loc_180022C2E
0x180022c24  mov     dword ptr [rax-8], 1
0x180022c2b  mov     rax, [rax]
0x180022c2e  cmp     rax, rsi
0x180022c31  jnz     short loc_180022C24
0x180022c33  lea     r14, [rcx+28h]
0x180022c37  cmp     [r14], r12
0x180022c3a  jnz     short loc_180022C56
0x180022c3c  mov     rcx, [rcx+10h]; hKey
0x180022c40  lea     rdx, c_szRouterManagers; "RouterManagers"
0x180022c47  mov     r9, r14
0x180022c4a  xor     r8d, r8d
0x180022c4d  call    AccessRouterSubkey
0x180022c52  test    eax, eax
0x180022c54  jnz     short loc_180022CA7
0x180022c56  mov     rcx, [r14]; hKey
0x180022c59  lea     rax, [rbp+cbMaxSubKeyLen]
0x180022c5d  mov     [rsp+78h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180022c62  xor     r9d, r9d; lpReserved
0x180022c65  mov     [rsp+78h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180022c6a  xor     r8d, r8d; lpcchClass
0x180022c6d  mov     [rsp+78h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180022c72  xor     edx, edx; lpClass
0x180022c74  mov     [rsp+78h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180022c79  mov     [rsp+78h+lpcValues], r12; lpcValues
0x180022c7e  mov     [rsp+78h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180022c83  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180022c88  lea     rax, [rbp+cSubKeys]
0x180022c8c  mov     [rsp+78h+lpcSubKeys], rax; lpcSubKeys
0x180022c91  call    cs:__imp_RegQueryInfoKeyW
0x180022c97  mov     edi, eax
0x180022c99  test    eax, eax
0x180022c9b  jnz     loc_180022F15
0x180022ca1  cmp     [rbp+cSubKeys], r12d
0x180022ca5  jnz     short loc_180022CAE
0x180022ca7  xor     eax, eax
0x180022ca9  jmp     loc_180022F15
0x180022cae  mov     eax, [rbp+cbMaxSubKeyLen]
0x180022cb1  lea     ecx, [rax+1]
0x180022cb4  cmp     ecx, eax
0x180022cb6  jb      loc_180022F10
0x180022cbc  mov     eax, ecx
0x180022cbe  mov     ecx, 0FFFFFFFFh
0x180022cc3  add     rax, rax
0x180022cc6  cmp     rax, rcx
0x180022cc9  ja      loc_180022F10
0x180022ccf  mov     ebx, eax
0x180022cd1  call    cs:__imp_GetProcessHeap
0x180022cd7  mov     r8d, ebx; dwBytes
0x180022cda  xor     edx, edx; dwFlags
0x180022cdc  mov     rcx, rax; hHeap
0x180022cdf  call    cs:__imp_HeapAlloc
0x180022ce5  mov     r13, rax
0x180022ce8  test    rax, rax
0x180022ceb  jnz     short loc_180022CF6
0x180022ced  lea     eax, [r13+8]
0x180022cf1  jmp     loc_180022F15
0x180022cf6  cmp     [rbp+cSubKeys], r12d
0x180022cfa  jbe     loc_180022EAD
0x180022d00  mov     eax, [rbp+cbMaxSubKeyLen]
0x180022d03  lea     r9, [rbp+cchName]; lpcchName
0x180022d07  mov     rcx, [r14]; hKey
0x180022d0a  inc     eax
0x180022d0c  mov     [rsp+78h+lpcValues], 0; lpftLastWriteTime
0x180022d15  mov     r8, r13; lpName
0x180022d18  mov     [rsp+78h+lpcbMaxClassLen], 0; lpcchClass
0x180022d21  mov     edx, r12d; dwIndex
0x180022d24  mov     [rsp+78h+lpcbMaxSubKeyLen], 0; lpClass
0x180022d2d  mov     [rbp+cchName], eax
0x180022d30  mov     [rsp+78h+lpcSubKeys], 0; lpReserved
0x180022d39  call    cs:__imp_RegEnumKeyExW
0x180022d3f  mov     edi, eax
0x180022d41  test    eax, eax
0x180022d43  jnz     loc_180022EAD
0x180022d49  mov     rcx, [r14]; hKey
0x180022d4c  lea     rax, [rbp+phkResult]
0x180022d50  mov     r9d, 3001Fh; samDesired
0x180022d56  mov     [rsp+78h+lpcSubKeys], rax; phkResult
0x180022d5b  xor     r8d, r8d; ulOptions
0x180022d5e  mov     rdx, r13; lpSubKey
0x180022d61  call    cs:__imp_RegOpenKeyExW
0x180022d67  mov     edi, eax
0x180022d69  test    eax, eax
0x180022d6b  jnz     loc_180022EA0
0x180022d71  mov     rcx, [rbp+phkResult]; hKey
0x180022d75  lea     rax, [rbp+cchName]
0x180022d79  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180022d7e  lea     r9, [rbp+Type]; lpType
0x180022d82  lea     rax, [rbp+Data]
0x180022d86  mov     [rbp+cchName], 4
0x180022d8d  xor     r8d, r8d; lpReserved
0x180022d90  mov     [rsp+78h+lpcSubKeys], rax; lpData
0x180022d95  lea     rdx, c_szProtocolId; "ProtocolId"
0x180022d9c  call    cs:__imp_RegQueryValueExW
0x180022da2  test    eax, eax
0x180022da4  jnz     loc_180022E8B
0x180022daa  lea     rax, [r15+50h]
0x180022dae  mov     rbx, [rax]
0x180022db1  mov     rsi, rax
0x180022db4  cmp     rbx, rax
0x180022db7  jz      short loc_180022DFE
0x180022db9  lea     rdi, [rbx-20h]
0x180022dbd  mov     eax, [rdi]
0x180022dbf  cmp     eax, [rbp+Data]
0x180022dc2  jnb     short loc_180022DCF
0x180022dc4  mov     rbx, [rbx]
0x180022dc7  cmp     rbx, rsi
0x180022dca  jnz     short loc_180022DB9
0x180022dcc  cmp     eax, [rbp+Data]
0x180022dcf  jnz     short loc_180022DFE
0x180022dd1  mov     rcx, [rdi+10h]; hKey
0x180022dd5  mov     dword ptr [rdi+18h], 0
0x180022ddc  test    rcx, rcx
0x180022ddf  jz      short loc_180022DE7
0x180022de1  call    cs:__imp_RegCloseKey
0x180022de7  mov     rax, [rbp+phkResult]
0x180022deb  mov     [rdi+10h], rax
0x180022def  xor     edi, edi
0x180022df1  mov     [rbp+phkResult], 0
0x180022df9  jmp     loc_180022EA0
0x180022dfe  call    cs:__imp_GetProcessHeap
0x180022e04  xor     edx, edx; dwFlags
0x180022e06  mov     rcx, rax; hHeap
0x180022e09  lea     r8d, [rdx+30h]; dwBytes
0x180022e0d  call    cs:__imp_HeapAlloc
0x180022e13  mov     rdi, rax
0x180022e16  test    rax, rax
0x180022e19  jnz     short loc_180022E22
0x180022e1b  mov     edi, 8
0x180022e20  jmp     short loc_180022E8D
0x180022e22  xorps   xmm0, xmm0
0x180022e25  mov     rcx, r13; pszSrch
0x180022e28  movups  xmmword ptr [rax], xmm0
0x180022e2b  movups  xmmword ptr [rax+10h], xmm0
0x180022e2f  movups  xmmword ptr [rax+20h], xmm0
0x180022e33  call    StrDupW
0x180022e38  mov     [rdi+8], rax
0x180022e3c  test    rax, rax
0x180022e3f  jnz     short loc_180022E57
0x180022e41  call    cs:__imp_GetProcessHeap
0x180022e47  mov     r8, rdi; lpMem
0x180022e4a  xor     edx, edx; dwFlags
0x180022e4c  mov     rcx, rax; hHeap
0x180022e4f  call    cs:__imp_HeapFree
0x180022e55  jmp     short loc_180022E1B
0x180022e57  mov     eax, [rbp+Data]
0x180022e5a  mov     [rdi], eax
0x180022e5c  mov     rax, [rbp+phkResult]
0x180022e60  mov     [rdi+10h], rax
0x180022e64  mov     [rbp+phkResult], 0
0x180022e6c  mov     rcx, [rbx+8]
0x180022e70  cmp     [rcx], rbx
0x180022e73  jnz     loc_180022F09
0x180022e79  lea     rax, [rdi+20h]
0x180022e7d  mov     [rax], rbx
0x180022e80  mov     [rax+8], rcx
0x180022e84  mov     [rcx], rax
0x180022e87  mov     [rbx+8], rax
0x180022e8b  xor     edi, edi
0x180022e8d  mov     rcx, [rbp+phkResult]; hKey
0x180022e91  test    rcx, rcx
0x180022e94  jz      short loc_180022E9C
0x180022e96  call    cs:__imp_RegCloseKey
0x180022e9c  test    edi, edi
0x180022e9e  jnz     short loc_180022EAD
0x180022ea0  inc     r12d
0x180022ea3  cmp     r12d, [rbp+cSubKeys]
0x180022ea7  jb      loc_180022D00
0x180022ead  call    cs:__imp_GetProcessHeap
0x180022eb3  mov     r8, r13; lpMem
0x180022eb6  xor     edx, edx; dwFlags
0x180022eb8  mov     rcx, rax; hHeap
0x180022ebb  call    cs:__imp_HeapFree
0x180022ec1  mov     rbx, [rsi]
0x180022ec4  jmp     short loc_180022EF4
0x180022ec6  lea     rcx, [rbx-20h]
0x180022eca  cmp     dword ptr [rcx+18h], 0
0x180022ece  jz      short loc_180022EF1
0x180022ed0  mov     rdx, [rbx]
0x180022ed3  cmp     [rdx+8], rbx
0x180022ed7  jnz     short loc_180022F09
0x180022ed9  mov     rax, [rbx+8]
0x180022edd  cmp     [rax], rbx
0x180022ee0  jnz     short loc_180022F09
0x180022ee2  mov     [rax], rdx
0x180022ee5  mov     rbx, rax
0x180022ee8  mov     [rdx+8], rax
0x180022eec  call    FreeTransport
0x180022ef1  mov     rbx, [rbx]
0x180022ef4  cmp     rbx, rsi
0x180022ef7  jnz     short loc_180022EC6
0x180022ef9  mov     rcx, [r14]; hKey
0x180022efc  lea     rdx, [r15+30h]; lpftLastWriteTime
0x180022f00  call    UpdateTimeStamp
0x180022f05  mov     eax, edi
0x180022f07  jmp     short loc_180022F15
0x180022f09  mov     ecx, 3
0x180022f0e  int     29h; Win8: RtlFailFast(ecx)
0x180022f10  mov     eax, 216h
0x180022f15  add     rsp, 78h
0x180022f19  pop     r15
0x180022f1b  pop     r14
0x180022f1d  pop     r13
0x180022f1f  pop     r12
0x180022f21  pop     rdi
0x180022f22  pop     rsi
0x180022f23  pop     rbx
0x180022f24  pop     rbp
0x180022f25  retn
```
