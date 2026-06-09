# PushMsgAuthModule::LoadProgIDs(void)

- ea: `0x18001b700`
- end: `0x18001ba34`
- name: `?LoadProgIDs@PushMsgAuthModule@@AEAAJXZ`
- size: `820`
- prototype: `__int64 __fastcall(PushMsgAuthModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014dcc`

## callees

- `0x1800060b4`
- `0x18001b700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b7e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001b848`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001b848`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b784`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b784`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001b94a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001b94a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b7cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b7d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b7cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b7d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b8d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b8f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b8d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b8f6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001b7c1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001b7c1`
- `DMCmnUtils!CopyString` at `0x18001b976`
- `DMCmnUtils!CopyString` at `0x18001b994`
- `DMCmnUtils!CopyString` at `0x18001b976`
- `DMCmnUtils!CopyString` at `0x18001b994`
- `DMCmnUtils!InvStrCmpW` at `0x18001b9d0`
- `DMCmnUtils!InvStrCmpW` at `0x18001b9d0`

## string_xrefs

- `0x18001b728`: `Software\Microsoft\Pushrouter\Security`
- `0x18001b7b3`: `Software\Microsoft\Pushrouter\Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PushMsgAuthModule::LoadProgIDs(PushMsgAuthModule *this)
{
  BYTE *v2; // r12
  LSTATUS v3; // eax
  signed int v4; // ebx
  LPWSTR v5; // r14
  DWORD v7; // eax
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  void *v10; // rax
  unsigned __int64 v11; // rax
  void *v12; // rax
  SIZE_T v13; // rdx
  DWORD v14; // esi
  LSTATUS v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // rsi
  unsigned int v19; // ecx
  __int64 v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  DWORD cValues; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-1h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp+7h] BYREF
  LPWSTR lpValueName; // [rsp+78h] [rbp+Fh]
  HKEY hKey; // [rsp+80h] [rbp+17h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwDisposition; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  cSubKeys = 0;
  cValues = 0;
  v2 = 0;
  dwDisposition = 0;
  Type = 0;
  cchValueName = 0;
  cbMaxValueNameLen = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Pushrouter\\Security",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         &dwDisposition);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
    {
LABEL_4:
      v5 = 0;
      goto LABEL_8;
    }
LABEL_3:
    v4 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_4;
  }
  v4 = 0;
  if ( dwDisposition == 1 )
  {
    RegCloseKey(hKey);
    hKey = 0;
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Pushrouter\\Security");
LABEL_7:
    v5 = 0;
    goto LABEL_8;
  }
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v3 )
  {
    if ( v3 <= 0 )
    {
      v4 = v3;
      goto LABEL_4;
    }
    goto LABEL_3;
  }
  v7 = cValues;
  if ( !cValues )
    goto LABEL_7;
  *(_DWORD *)this = cValues;
  v9 = v7;
  v8 = 8LL * v7;
  if ( !is_mul_ok(v9, 8u) )
    v8 = -1;
  v10 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 1) = v10;
  if ( !v10 )
    goto LABEL_18;
  v11 = 8LL * *(unsigned int *)this;
  if ( !is_mul_ok(*(unsigned int *)this, 8u) )
    v11 = -1;
  v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 2) = v12;
  if ( !v12 )
  {
LABEL_18:
    v4 = -2147024882;
    goto LABEL_4;
  }
  v13 = 2LL * ++cbMaxValueNameLen;
  lpValueName = (LPWSTR)LocalAlloc(0, v13);
  v5 = lpValueName;
  if ( lpValueName && (v2 = (BYTE *)LocalAlloc(0, cbMaxValueLen)) != 0 )
  {
    v14 = 0;
    if ( *(_DWORD *)this )
    {
      while ( 1 )
      {
        cchValueName = cbMaxValueNameLen;
        cbData = cbMaxValueLen;
        v15 = RegEnumValueW(hKey, v14, lpValueName, &cchValueName, 0, &Type, v2, &cbData);
        v4 = v15;
        if ( v15 )
          break;
        if ( Type != 1 )
        {
          v4 = -2147024809;
          goto LABEL_41;
        }
        v4 = CopyString(lpValueName, 0xFFFFFFFF, (unsigned __int16 **)(*((_QWORD *)this + 1) + 8LL * v14));
        if ( v4 < 0 )
          goto LABEL_41;
        v4 = CopyString(
               (const unsigned __int16 *)v2,
               0xFFFFFFFF,
               (unsigned __int16 **)(*((_QWORD *)this + 2) + 8LL * v14));
        if ( v4 < 0 )
          goto LABEL_41;
        v16 = *(_DWORD *)this;
        if ( ++v14 >= *(_DWORD *)this )
        {
          if ( v16 )
          {
            v17 = 0;
            do
            {
              v18 = v17 + 1;
              v19 = v17;
              v17 = v18;
              if ( (unsigned int)v18 >= v16 )
                break;
              v20 = v19;
              do
              {
                if ( (int)InvStrCmpW(
                            *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8 * v20),
                            *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 8 * v18)) > 0 )
                {
                  v21 = *((_QWORD *)this + 1);
                  v22 = *(_QWORD *)(v21 + 8 * v20);
                  *(_QWORD *)(v21 + 8 * v20) = *(_QWORD *)(v21 + 8 * v18);
                  *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v18) = v22;
                  v23 = *((_QWORD *)this + 2);
                  v24 = *(_QWORD *)(v23 + 8 * v20);
                  *(_QWORD *)(v23 + 8 * v20) = *(_QWORD *)(v23 + 8 * v18);
                  *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v18) = v24;
                }
                v16 = *(_DWORD *)this;
                v18 = (unsigned int)(v18 + 1);
              }
              while ( (unsigned int)v18 < *(_DWORD *)this );
            }
            while ( v17 < v16 );
          }
          goto LABEL_41;
        }
      }
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
LABEL_41:
      v5 = lpValueName;
    }
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  LocalFree(v5);
  LocalFree(v2);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b700  mov     [rsp-8+arg_0], rbx
0x18001b705  push    rbp
0x18001b706  push    rsi
0x18001b707  push    rdi
0x18001b708  push    r12
0x18001b70a  push    r13
0x18001b70c  push    r14
0x18001b70e  push    r15
0x18001b710  lea     rbp, [rsp-27h]
0x18001b715  sub     rsp, 90h
0x18001b71c  xor     r15d, r15d
0x18001b71f  lea     rax, [rbp+57h+dwDisposition]
0x18001b723  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18001b728  lea     rdx, ?sc_szAuthProvRegistrations@PushMsgAuthModule@@0QBGB; "Software\\Microsoft\\Pushrouter\\Securi"...
0x18001b72f  lea     rax, [rbp+57h+hKey]
0x18001b733  mov     [rbp+57h+hKey], r15
0x18001b737  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001b73c  mov     rdi, rcx
0x18001b73f  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001b744  mov     rsi, 0FFFFFFFF80000002h
0x18001b74b  mov     [rsp+0C0h+samDesired], 20019h; samDesired
0x18001b753  xor     r9d, r9d; lpClass
0x18001b756  xor     r8d, r8d; Reserved
0x18001b759  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x18001b75e  mov     rcx, rsi; hKey
0x18001b761  mov     [rbp+57h+cSubKeys], r15d
0x18001b765  mov     [rbp+57h+cValues], r15d
0x18001b769  mov     r12d, r15d
0x18001b76c  mov     [rbp+57h+dwDisposition], r15d
0x18001b770  mov     [rbp+57h+Type], r15d
0x18001b774  mov     [rbp+57h+cchValueName], r15d
0x18001b778  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18001b77c  mov     [rbp+57h+cbData], r15d
0x18001b780  mov     [rbp+57h+cbMaxValueLen], r15d
0x18001b784  call    cs:__imp_RegCreateKeyExW
0x18001b78a  mov     ebx, eax
0x18001b78c  test    eax, eax
0x18001b78e  jz      short loc_18001B7A0
0x18001b790  jle     short loc_18001B79B
0x18001b792  movzx   ebx, ax
0x18001b795  or      ebx, 80070000h
0x18001b79b  mov     r14, r12
0x18001b79e  jmp     short loc_18001B7CA
0x18001b7a0  cmp     [rbp+57h+dwDisposition], 1
0x18001b7a4  mov     ebx, r15d
0x18001b7a7  mov     rcx, [rbp+57h+hKey]; hKey
0x18001b7ab  jnz     short loc_18001B808
0x18001b7ad  call    cs:__imp_RegCloseKey
0x18001b7b3  lea     rdx, ?sc_szAuthProvRegistrations@PushMsgAuthModule@@0QBGB; "Software\\Microsoft\\Pushrouter\\Securi"...
0x18001b7ba  mov     [rbp+57h+hKey], r15
0x18001b7be  mov     rcx, rsi; hKey
0x18001b7c1  call    cs:__imp_RegDeleteKeyW
0x18001b7c7  mov     r14, rbx
0x18001b7ca  mov     rcx, r14; hMem
0x18001b7cd  call    cs:__imp_LocalFree
0x18001b7d3  mov     rcx, r12; hMem
0x18001b7d6  call    cs:__imp_LocalFree
0x18001b7dc  mov     rcx, [rbp+57h+hKey]; hKey
0x18001b7e0  test    rcx, rcx
0x18001b7e3  jz      short loc_18001B7EB
0x18001b7e5  call    cs:__imp_RegCloseKey
0x18001b7eb  mov     eax, ebx
0x18001b7ed  mov     rbx, [rsp+0C0h+arg_0]
0x18001b7f5  add     rsp, 90h
0x18001b7fc  pop     r15
0x18001b7fe  pop     r14
0x18001b800  pop     r13
0x18001b802  pop     r12
0x18001b804  pop     rdi
0x18001b805  pop     rsi
0x18001b806  pop     rbp
0x18001b807  retn
0x18001b808  mov     [rsp+0C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001b80d  lea     rax, [rbp+57h+cbMaxValueLen]
0x18001b811  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001b816  xor     r9d, r9d; lpReserved
0x18001b819  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001b81e  xor     r8d, r8d; lpcchClass
0x18001b821  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18001b825  xor     edx, edx; lpClass
0x18001b827  mov     [rsp+0C0h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x18001b82c  lea     rax, [rbp+57h+cValues]
0x18001b830  mov     [rsp+0C0h+phkResult], rax; lpcValues
0x18001b835  lea     rax, [rbp+57h+cSubKeys]
0x18001b839  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x18001b83e  mov     qword ptr [rsp+0C0h+samDesired], r15; lpcbMaxSubKeyLen
0x18001b843  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpcSubKeys
0x18001b848  call    cs:__imp_RegQueryInfoKeyW
0x18001b84e  test    eax, eax
0x18001b850  jz      short loc_18001B85F
0x18001b852  jg      loc_18001B792
0x18001b858  mov     ebx, eax
0x18001b85a  jmp     loc_18001B79B
0x18001b85f  mov     eax, [rbp+57h+cValues]
0x18001b862  test    eax, eax
0x18001b864  jz      loc_18001B7C7
0x18001b86a  mov     ecx, eax
0x18001b86c  mov     esi, 8
0x18001b871  mov     [rdi], ecx
0x18001b873  mov     eax, esi
0x18001b875  mul     rcx
0x18001b878  lea     r14, [rsi-9]
0x18001b87c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b883  cmovb   rax, r14
0x18001b887  mov     rcx, rax; unsigned __int64
0x18001b88a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b88f  mov     [rdi+8], rax
0x18001b893  test    rax, rax
0x18001b896  jnz     short loc_18001B8A2
0x18001b898  mov     ebx, 8007000Eh
0x18001b89d  jmp     loc_18001B79B
0x18001b8a2  mov     ecx, [rdi]
0x18001b8a4  mov     rax, rsi
0x18001b8a7  mul     rcx
0x18001b8aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b8b1  cmovb   rax, r14
0x18001b8b5  mov     rcx, rax; unsigned __int64
0x18001b8b8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b8bd  mov     [rdi+10h], rax
0x18001b8c1  test    rax, rax
0x18001b8c4  jz      short loc_18001B898
0x18001b8c6  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001b8c9  xor     ecx, ecx; uFlags
0x18001b8cb  inc     eax
0x18001b8cd  mov     edx, eax
0x18001b8cf  add     rdx, rdx; uBytes
0x18001b8d2  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18001b8d5  call    cs:__imp_LocalAlloc
0x18001b8db  mov     [rbp+57h+lpValueName], rax
0x18001b8df  mov     r14, rax
0x18001b8e2  test    rax, rax
0x18001b8e5  jnz     short loc_18001B8F1
0x18001b8e7  mov     ebx, 8007000Eh
0x18001b8ec  jmp     loc_18001B7CA
0x18001b8f1  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x18001b8f4  xor     ecx, ecx; uFlags
0x18001b8f6  call    cs:__imp_LocalAlloc
0x18001b8fc  mov     r12, rax
0x18001b8ff  test    rax, rax
0x18001b902  jz      short loc_18001B8E7
0x18001b904  mov     esi, r15d
0x18001b907  cmp     [rdi], r15d
0x18001b90a  jbe     loc_18001B7CA
0x18001b910  or      r13d, 0FFFFFFFFh
0x18001b914  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001b917  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18001b91b  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x18001b91f  mov     edx, esi; dwIndex
0x18001b921  mov     rcx, [rbp+57h+hKey]; hKey
0x18001b925  mov     [rbp+57h+cchValueName], eax
0x18001b928  mov     eax, [rbp+57h+cbMaxValueLen]
0x18001b92b  mov     [rbp+57h+cbData], eax
0x18001b92e  lea     rax, [rbp+57h+cbData]
0x18001b932  mov     [rsp+0C0h+phkResult], rax; lpcbData
0x18001b937  lea     rax, [rbp+57h+Type]
0x18001b93b  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpData
0x18001b940  mov     qword ptr [rsp+0C0h+samDesired], rax; lpType
0x18001b945  mov     qword ptr [rsp+0C0h+dwOptions], r15; lpReserved
0x18001b94a  call    cs:__imp_RegEnumValueW
0x18001b950  mov     ebx, eax
0x18001b952  test    eax, eax
0x18001b954  jnz     loc_18001BA27
0x18001b95a  cmp     [rbp+57h+Type], 1
0x18001b95e  jnz     loc_18001BA19
0x18001b964  mov     rax, [rdi+8]
0x18001b968  mov     edx, r13d
0x18001b96b  mov     rcx, [rbp+57h+lpValueName]
0x18001b96f  mov     r14d, esi
0x18001b972  lea     r8, [rax+r14*8]
0x18001b976  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001b97c  mov     ebx, eax
0x18001b97e  test    eax, eax
0x18001b980  js      loc_18001BA1E
0x18001b986  mov     rax, [rdi+10h]
0x18001b98a  mov     edx, r13d
0x18001b98d  mov     rcx, r12
0x18001b990  lea     r8, [rax+r14*8]
0x18001b994  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001b99a  mov     ebx, eax
0x18001b99c  test    eax, eax
0x18001b99e  js      short loc_18001BA1E
0x18001b9a0  mov     eax, [rdi]
0x18001b9a2  inc     esi
0x18001b9a4  cmp     esi, eax
0x18001b9a6  jb      loc_18001B914
0x18001b9ac  test    eax, eax
0x18001b9ae  jz      short loc_18001BA1E
0x18001b9b0  mov     r14d, r15d
0x18001b9b3  lea     esi, [r14+1]
0x18001b9b7  mov     ecx, r14d
0x18001b9ba  mov     r14d, esi
0x18001b9bd  cmp     esi, eax
0x18001b9bf  jnb     short loc_18001BA1E
0x18001b9c1  mov     r15d, ecx
0x18001b9c4  mov     rcx, [rdi+8]
0x18001b9c8  mov     rdx, [rcx+rsi*8]
0x18001b9cc  mov     rcx, [rcx+r15*8]
0x18001b9d0  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x18001b9d6  test    eax, eax
0x18001b9d8  jle     short loc_18001BA0A
0x18001b9da  mov     rcx, [rdi+8]
0x18001b9de  mov     rax, [rcx+rsi*8]
0x18001b9e2  mov     rdx, [rcx+r15*8]
0x18001b9e6  mov     [rcx+r15*8], rax
0x18001b9ea  mov     rax, [rdi+8]
0x18001b9ee  mov     [rax+rsi*8], rdx
0x18001b9f2  mov     rcx, [rdi+10h]
0x18001b9f6  mov     rax, [rcx+rsi*8]
0x18001b9fa  mov     rdx, [rcx+r15*8]
0x18001b9fe  mov     [rcx+r15*8], rax
0x18001ba02  mov     rax, [rdi+10h]
0x18001ba06  mov     [rax+rsi*8], rdx
0x18001ba0a  mov     eax, [rdi]
0x18001ba0c  inc     esi
0x18001ba0e  cmp     esi, eax
0x18001ba10  jb      short loc_18001B9C4
0x18001ba12  cmp     r14d, eax
0x18001ba15  jb      short loc_18001B9B3
0x18001ba17  jmp     short loc_18001BA1E
0x18001ba19  mov     ebx, 80070057h
0x18001ba1e  mov     r14, [rbp+57h+lpValueName]
0x18001ba22  jmp     loc_18001B7CA
0x18001ba27  jle     short loc_18001BA1E
0x18001ba29  movzx   ebx, ax
0x18001ba2c  or      ebx, 80070000h
0x18001ba32  jmp     short loc_18001BA1E
```
