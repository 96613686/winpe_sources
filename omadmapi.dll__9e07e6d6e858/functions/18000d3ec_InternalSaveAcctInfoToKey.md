# InternalSaveAcctInfoToKey

- ea: `0x18000d3ec`
- end: `0x18000db89`
- name: `InternalSaveAcctInfoToKey`
- size: `1949`
- prototype: `__int64 __fastcall(HKEY hKey, struct tagOMADMACCTINFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001268c`
- `0x18001a690`

## callees

- `0x1800031b0`
- `0x180008600`
- `0x180009bf4`
- `0x18000c718`
- `0x18000d3ec`
- `0x18000fae0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dad5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dad5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000da8b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000da8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d95e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d95e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d4ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d5b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d636`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d762`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d83e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d89e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d9f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d4ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d5b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d636`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d762`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d83e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d89e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d9f5`

## pseudocode

```c
__int64 __fastcall InternalSaveAcctInfoToKey(HKEY hKey, struct tagOMADMACCTINFO *a2)
{
  int v4; // r14d
  signed int IndexedString; // ebx
  int v6; // r12d
  HKEY *phkResult; // rax
  LSTATUS v8; // eax
  bool v9; // cc
  HKEY *v10; // rax
  unsigned int v11; // esi
  HKEY *v12; // rax
  LSTATUS v13; // eax
  int v14; // eax
  HKEY v15; // rcx
  HKEY *v16; // rax
  unsigned int i; // esi
  HKEY *v18; // rax
  HKEY *v19; // rax
  HKEY *v20; // rax
  const BYTE *v21; // rdi
  LSTATUS v22; // eax
  HKEY v23; // rcx
  __int64 v24; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-69h] BYREF
  int HasProtectedMembers; // [rsp+54h] [rbp-65h]
  HKEY v28; // [rsp+58h] [rbp-61h] BYREF
  HKEY v29; // [rsp+60h] [rbp-59h] BYREF
  HKEY v30; // [rsp+68h] [rbp-51h] BYREF
  HKEY v31[2]; // [rsp+70h] [rbp-49h] BYREF
  HKEY v32; // [rsp+80h] [rbp-39h] BYREF
  HKEY hKeya; // [rsp+88h] [rbp-31h] BYREF
  HKEY v34; // [rsp+90h] [rbp-29h] BYREF
  __int128 v35; // [rsp+98h] [rbp-21h]
  __int128 v36; // [rsp+A8h] [rbp-11h]
  WCHAR SubKey[8]; // [rsp+B8h] [rbp-1h] BYREF
  int v38; // [rsp+C8h] [rbp+Fh]

  dwDisposition = 0;
  *(_OWORD *)SubKey = 0;
  v38 = 0;
  HasProtectedMembers = OmaDmHasProtectedMembers(a2);
  v4 = HasProtectedMembers;
  v28 = 0;
  v34 = 0;
  hKeya = 0;
  v32 = 0;
  v30 = 0;
  v29 = 0;
  if ( !hKey || !a2 )
    return (unsigned int)-2147024809;
  v6 = 0;
  if ( HasProtectedMembers )
  {
    phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
    v8 = RegCreateKeyExW(hKey, L"Protected", 0, 0, 0, 0x20106u, 0, phkResult, &dwDisposition);
    IndexedString = v8;
    v9 = v8 <= 0;
    if ( v8 )
      goto LABEL_23;
    IndexedString = SaveStructInRegistry(v28, 19, (__int64)a2, 512, (unsigned __int8 *)&qword_18002A538, 0x10u);
    if ( IndexedString < 0 )
      goto LABEL_63;
    v6 = 1;
  }
  IndexedString = SaveStructInRegistry(hKey, 9, (__int64)a2, 512, (unsigned __int8 *)&qword_18002A538, 0x10u);
  if ( IndexedString < 0 )
    goto LABEL_63;
  if ( (*((_DWORD *)a2 + 1) & 0x8000000) == 0 || !*((_DWORD *)a2 + 124) )
    goto LABEL_20;
  v10 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKeya);
  v8 = RegCreateKeyExW(hKey, L"UserInfo", 0, 0, 0, 0x20106u, 0, v10, &dwDisposition);
  IndexedString = v8;
  v9 = v8 <= 0;
  if ( v8 )
    goto LABEL_23;
  v11 = 0;
  if ( !*((_DWORD *)a2 + 124) )
  {
LABEL_20:
    if ( *((_DWORD *)a2 + 34) )
    {
      if ( !v4 )
      {
LABEL_22:
        IndexedString = -2147418113;
        goto LABEL_63;
      }
      if ( v6 )
      {
        v16 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v34);
        v8 = RegCreateKeyExW(v28, L"AddrInfo", 0, 0, 0, 0x20106u, 0, v16, &dwDisposition);
        IndexedString = v8;
        v9 = v8 <= 0;
        if ( v8 )
          goto LABEL_23;
        IndexedString = SaveStructInRegistry(v34, 6, (__int64)a2 + 136, 56, (unsigned __int8 *)&qword_18002A538, 0x10u);
        if ( IndexedString < 0 )
          goto LABEL_63;
      }
    }
    for ( i = 0; i < 2; ++i )
    {
      if ( *((_DWORD *)a2 + 18 * i + 48) )
      {
        IndexedString = GenerateIndexedString(L"AuthInfo", i, SubKey, 0xAu);
        if ( IndexedString < 0 )
          goto LABEL_63;
        v18 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
        v8 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20106u, 0, v18, &dwDisposition);
        IndexedString = v8;
        v9 = v8 <= 0;
        if ( v8 )
          goto LABEL_23;
        if ( HasProtectedMembers && v6 )
        {
          v19 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v30);
          v8 = RegCreateKeyExW(v28, SubKey, 0, 0, 0, 0x20106u, 0, v19, &dwDisposition);
          IndexedString = v8;
          v9 = v8 <= 0;
          if ( v8 )
            goto LABEL_23;
          IndexedString = SaveStructInRegistry(
                            v30,
                            5,
                            (__int64)a2 + 72 * i + 192,
                            72,
                            (unsigned __int8 *)&qword_18002A538,
                            0x10u);
          if ( IndexedString < 0 )
            goto LABEL_63;
        }
        IndexedString = SaveStructInRegistry(
                          v29,
                          2,
                          (__int64)a2 + 72 * i + 192,
                          72,
                          (unsigned __int8 *)&qword_18002A538,
                          0x10u);
        if ( IndexedString < 0 )
          goto LABEL_63;
        if ( v30 )
        {
          RegCloseKey(v30);
          v30 = 0;
        }
        if ( v29 )
        {
          RegCloseKey(v29);
          v29 = 0;
        }
      }
    }
    if ( !*((_DWORD *)a2 + 89) )
      goto LABEL_52;
    if ( !HasProtectedMembers )
      goto LABEL_22;
    if ( !v6 )
    {
LABEL_52:
      v35 = 0;
      *(_OWORD *)v31 = 0;
      v36 = 0;
      v21 = (const BYTE *)a2 + 128;
      if ( v21 )
      {
        v22 = RegSetValueExW(hKey, L"RoamingCount", 0, 4u, v21, 4u);
        IndexedString = v22;
        if ( v22 )
        {
          if ( v22 > 0 )
            IndexedString = (unsigned __int16)v22 | 0x80070000;
        }
        else
        {
          IndexedString = 0;
        }
      }
      else
      {
        IndexedString = -2147024809;
      }
      v23 = v31[1];
      if ( v31[1] )
      {
        v24 = LODWORD(v31[0]);
        if ( LODWORD(v31[0]) )
        {
          do
          {
            *(_BYTE *)v23 = 0;
            v23 = (HKEY)((char *)v23 + 1);
            --v24;
          }
          while ( v24 );
          v23 = v31[1];
        }
        LocalFree(v23);
      }
      goto LABEL_63;
    }
    v20 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v32);
    v8 = RegCreateKeyExW(v28, L"ConnInfo", 0, 0, 0, 0x20106u, 0, v20, &dwDisposition);
    IndexedString = v8;
    v9 = v8 <= 0;
    if ( !v8 )
    {
      IndexedString = SaveStructInRegistry(v32, 16, (__int64)a2 + 336, 96, (unsigned __int8 *)&qword_18002A538, 0x10u);
      if ( IndexedString < 0 )
        goto LABEL_63;
      goto LABEL_52;
    }
LABEL_23:
    if ( !v9 )
      IndexedString = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_63;
  }
  while ( 1 )
  {
    if ( !*(_DWORD *)(*((_QWORD *)a2 + 63) + 24LL * v11) )
      goto LABEL_18;
    v31[0] = 0;
    v12 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v31);
    v13 = RegCreateKeyExW(
            hKeya,
            *(LPCWSTR *)(*((_QWORD *)a2 + 63) + 24LL * v11 + 16),
            0,
            0,
            0,
            0x20106u,
            0,
            v12,
            &dwDisposition);
    IndexedString = v13;
    if ( v13 )
      break;
    v14 = SaveStructInRegistry(
            v31[0],
            2,
            *((_QWORD *)a2 + 63) + 24LL * v11,
            24,
            (unsigned __int8 *)&qword_18002A538,
            0x10u);
    v15 = v31[0];
    IndexedString = v14;
    if ( v14 < 0 )
      goto LABEL_28;
    if ( v31[0] )
      RegCloseKey(v31[0]);
LABEL_18:
    if ( ++v11 >= *((_DWORD *)a2 + 124) )
    {
      v4 = HasProtectedMembers;
      goto LABEL_20;
    }
  }
  if ( v13 > 0 )
    IndexedString = (unsigned __int16)v13 | 0x80070000;
  v15 = v31[0];
LABEL_28:
  if ( v15 )
    RegCloseKey(v15);
LABEL_63:
  if ( v29 )
    RegCloseKey(v29);
  if ( v30 )
    RegCloseKey(v30);
  if ( v32 )
    RegCloseKey(v32);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v34 )
    RegCloseKey(v34);
  if ( v28 )
    RegCloseKey(v28);
  return (unsigned int)IndexedString;
}

```

## disassembly

```asm
0x18000d3ec  mov     [rsp-8+arg_10], rbx
0x18000d3f1  push    rbp
0x18000d3f2  push    rsi
0x18000d3f3  push    rdi
0x18000d3f4  push    r12
0x18000d3f6  push    r13
0x18000d3f8  push    r14
0x18000d3fa  push    r15
0x18000d3fc  lea     rbp, [rsp-27h]
0x18000d401  sub     rsp, 0E0h
0x18000d408  mov     rax, cs:__security_cookie
0x18000d40f  xor     rax, rsp
0x18000d412  mov     [rbp+57h+var_40], rax
0x18000d416  mov     r13, rcx
0x18000d419  xorps   xmm0, xmm0
0x18000d41c  xor     eax, eax
0x18000d41e  xor     r15d, r15d
0x18000d421  mov     rcx, rdx; struct tagOMADMACCTINFO *
0x18000d424  mov     [rbp+57h+dwDisposition], r15d
0x18000d428  movups  xmmword ptr [rbp+57h+SubKey], xmm0
0x18000d42c  mov     [rbp+57h+var_48], eax
0x18000d42f  mov     rdi, rdx
0x18000d432  call    ?OmaDmHasProtectedMembers@@YAHPEAUtagOMADMACCTINFO@@@Z; OmaDmHasProtectedMembers(tagOMADMACCTINFO *)
0x18000d437  mov     [rbp+57h+var_BC], eax
0x18000d43a  mov     r14d, eax
0x18000d43d  mov     [rbp+57h+var_B8], r15
0x18000d441  mov     [rbp+57h+var_80], r15
0x18000d445  mov     [rbp+57h+hKey], r15
0x18000d449  mov     [rbp+57h+var_90], r15
0x18000d44d  mov     [rbp+57h+var_A8], r15
0x18000d451  mov     [rbp+57h+var_B0], r15
0x18000d455  test    r13, r13
0x18000d458  jnz     short loc_18000D464
0x18000d45a  mov     ebx, 80070057h
0x18000d45f  jmp     loc_18000DB5F
0x18000d464  test    rdi, rdi
0x18000d467  jz      short loc_18000D45A
0x18000d469  lea     rax, qword_18002A538
0x18000d470  mov     r12d, r15d
0x18000d473  mov     esi, 200h
0x18000d478  test    r14d, r14d
0x18000d47b  jz      loc_18000D523
0x18000d481  lea     rcx, [rbp+57h+var_B8]
0x18000d485  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d48a  lea     rcx, [rbp+57h+dwDisposition]
0x18000d48e  xor     r9d, r9d; lpClass
0x18000d491  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d496  lea     rdx, aProtected; "Protected"
0x18000d49d  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d4a2  xor     r8d, r8d; Reserved
0x18000d4a5  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000d4aa  mov     rcx, r13; hKey
0x18000d4ad  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d4b5  mov     [rsp+110h+dwOptions], r15d; dwOptions
0x18000d4ba  call    cs:__imp_RegCreateKeyExW
0x18000d4c1  nop     dword ptr [rax+rax+00h]
0x18000d4c6  mov     ebx, eax
0x18000d4c8  test    eax, eax
0x18000d4ca  jnz     loc_18000D6E2
0x18000d4d0  mov     r8d, [rdi+4]
0x18000d4d4  lea     rcx, qword_18002A538
0x18000d4db  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d4e3  lea     r9, off_180026360; "AcctRootName"
0x18000d4ea  mov     [rsp+110h+phkResult], rcx; unsigned __int8 *
0x18000d4ef  lea     edx, [rax+1]
0x18000d4f2  mov     rcx, [rbp+57h+var_B8]; hKey
0x18000d4f6  mov     dword ptr [rsp+110h+lpSecurityAttributes], esi; int
0x18000d4fa  mov     qword ptr [rsp+110h+samDesired], rdi; __int64
0x18000d4ff  mov     [rsp+110h+dwOptions], 13h; int
0x18000d507  call    SaveStructInRegistry
0x18000d50c  mov     ebx, eax
0x18000d50e  test    eax, eax
0x18000d510  js      loc_18000DAE1
0x18000d516  mov     r12d, 1
0x18000d51c  lea     rax, qword_18002A538
0x18000d523  mov     r8d, [rdi+4]
0x18000d527  lea     r9, off_1800265C0; "SecondaryServerNonce"
0x18000d52e  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d536  mov     edx, 1
0x18000d53b  mov     [rsp+110h+phkResult], rax; unsigned __int8 *
0x18000d540  mov     rcx, r13; hKey
0x18000d543  mov     dword ptr [rsp+110h+lpSecurityAttributes], esi; int
0x18000d547  mov     qword ptr [rsp+110h+samDesired], rdi; __int64
0x18000d54c  mov     [rsp+110h+dwOptions], 9; int
0x18000d554  call    SaveStructInRegistry
0x18000d559  mov     ebx, eax
0x18000d55b  test    eax, eax
0x18000d55d  js      loc_18000DAE1
0x18000d563  test    dword ptr [rdi+4], 8000000h
0x18000d56a  jz      loc_18000D6C3
0x18000d570  cmp     [rdi+1F0h], r15d
0x18000d577  jz      loc_18000D6C3
0x18000d57d  lea     rcx, [rbp+57h+hKey]
0x18000d581  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d586  lea     rcx, [rbp+57h+dwDisposition]
0x18000d58a  xor     r9d, r9d; lpClass
0x18000d58d  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d592  lea     rdx, aUserinfo; "UserInfo"
0x18000d599  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d59e  xor     r8d, r8d; Reserved
0x18000d5a1  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000d5a6  mov     rcx, r13; hKey
0x18000d5a9  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d5b1  mov     [rsp+110h+dwOptions], r15d; dwOptions
0x18000d5b6  call    cs:__imp_RegCreateKeyExW
0x18000d5bd  nop     dword ptr [rax+rax+00h]
0x18000d5c2  mov     ebx, eax
0x18000d5c4  test    eax, eax
0x18000d5c6  jnz     loc_18000D6E2
0x18000d5cc  mov     esi, r15d
0x18000d5cf  cmp     [rdi+1F0h], r15d
0x18000d5d6  jbe     loc_18000D6C3
0x18000d5dc  mov     eax, esi
0x18000d5de  lea     r14, [rax+rax*2]
0x18000d5e2  mov     rax, [rdi+1F8h]
0x18000d5e9  cmp     [rax+r14*8], r15d
0x18000d5ed  jz      loc_18000D6B1
0x18000d5f3  lea     rcx, [rbp+57h+var_A0]
0x18000d5f7  mov     [rbp+57h+var_A0], r15
0x18000d5fb  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d600  mov     rdx, [rdi+1F8h]
0x18000d607  lea     rcx, [rbp+57h+dwDisposition]
0x18000d60b  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d610  xor     r9d, r9d; lpClass
0x18000d613  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d617  xor     r8d, r8d; Reserved
0x18000d61a  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d61f  mov     rdx, [rdx+r14*8+10h]; lpSubKey
0x18000d624  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000d629  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d631  mov     [rsp+110h+dwOptions], r15d; dwOptions
0x18000d636  call    cs:__imp_RegCreateKeyExW
0x18000d63d  nop     dword ptr [rax+rax+00h]
0x18000d642  mov     ebx, eax
0x18000d644  test    eax, eax
0x18000d646  jnz     loc_18000D6F6
0x18000d64c  mov     rax, [rdi+1F8h]
0x18000d653  lea     r9, off_180025C60; "AADTokenNeedsUserInteraction"
0x18000d65a  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000d65e  lea     edx, [rbx+1]
0x18000d661  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d669  lea     r8, [rax+r14*8]
0x18000d66d  lea     rax, qword_18002A538
0x18000d674  mov     [rsp+110h+phkResult], rax; unsigned __int8 *
0x18000d679  mov     dword ptr [rsp+110h+lpSecurityAttributes], 18h; int
0x18000d681  mov     qword ptr [rsp+110h+samDesired], r8; __int64
0x18000d686  mov     r8d, [r8]
0x18000d689  mov     [rsp+110h+dwOptions], 2; int
0x18000d691  call    SaveStructInRegistry
0x18000d696  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000d69a  mov     ebx, eax
0x18000d69c  test    eax, eax
0x18000d69e  js      short loc_18000D705
0x18000d6a0  test    rcx, rcx
0x18000d6a3  jz      short loc_18000D6B1
0x18000d6a5  call    cs:__imp_RegCloseKey
0x18000d6ac  nop     dword ptr [rax+rax+00h]
0x18000d6b1  inc     esi
0x18000d6b3  cmp     esi, [rdi+1F0h]
0x18000d6b9  jb      loc_18000D5DC
0x18000d6bf  mov     r14d, [rbp+57h+var_BC]
0x18000d6c3  lea     rsi, [rdi+88h]
0x18000d6ca  cmp     [rsi], r15d
0x18000d6cd  jz      loc_18000D7C1
0x18000d6d3  test    r14d, r14d
0x18000d6d6  jnz     short loc_18000D71F
0x18000d6d8  mov     ebx, 8000FFFFh
0x18000d6dd  jmp     loc_18000DAE1
0x18000d6e2  jle     loc_18000DAE1
0x18000d6e8  movzx   ebx, ax
0x18000d6eb  or      ebx, 80070000h
0x18000d6f1  jmp     loc_18000DAE1
0x18000d6f6  jle     short loc_18000D701
0x18000d6f8  movzx   ebx, ax
0x18000d6fb  or      ebx, 80070000h
0x18000d701  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000d705  test    rcx, rcx
0x18000d708  jz      loc_18000DAE1
0x18000d70e  call    cs:__imp_RegCloseKey
0x18000d715  nop     dword ptr [rax+rax+00h]
0x18000d71a  jmp     loc_18000DAE1
0x18000d71f  test    r12d, r12d
0x18000d722  jz      loc_18000D7C1
0x18000d728  lea     rcx, [rbp+57h+var_80]
0x18000d72c  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d731  lea     rcx, [rbp+57h+dwDisposition]
0x18000d735  xor     r9d, r9d; lpClass
0x18000d738  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d73d  lea     rdx, aAddrinfo; "AddrInfo"
0x18000d744  mov     rcx, [rbp+57h+var_B8]; hKey
0x18000d748  xor     r8d, r8d; Reserved
0x18000d74b  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d750  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000d755  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d75d  mov     [rsp+110h+dwOptions], r15d; dwOptions
0x18000d762  call    cs:__imp_RegCreateKeyExW
0x18000d769  nop     dword ptr [rax+rax+00h]
0x18000d76e  mov     ebx, eax
0x18000d770  test    eax, eax
0x18000d772  jnz     loc_18000D6E2
0x18000d778  mov     r8d, [rsi]
0x18000d77b  lea     rax, qword_18002A538
0x18000d782  mov     rcx, [rbp+57h+var_80]; hKey
0x18000d786  lea     r9, off_1800262A0; "AddrRootName"
0x18000d78d  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d795  lea     edx, [rbx+1]
0x18000d798  mov     [rsp+110h+phkResult], rax; unsigned __int8 *
0x18000d79d  mov     dword ptr [rsp+110h+lpSecurityAttributes], 38h ; '8'; int
0x18000d7a5  mov     qword ptr [rsp+110h+samDesired], rsi; __int64
0x18000d7aa  mov     [rsp+110h+dwOptions], 6; int
0x18000d7b2  call    SaveStructInRegistry
0x18000d7b7  mov     ebx, eax
0x18000d7b9  test    eax, eax
0x18000d7bb  js      loc_18000DAE1
0x18000d7c1  mov     esi, r15d
0x18000d7c4  mov     eax, esi
0x18000d7c6  lea     r15, [rdi+0C0h]
0x18000d7cd  lea     r14, [rax+rax*8]
0x18000d7d1  lea     r15, [r15+r14*8]
0x18000d7d5  cmp     dword ptr [r15], 0
0x18000d7d9  jz      loc_18000D989
0x18000d7df  mov     r9d, 0Ah; unsigned int
0x18000d7e5  lea     r8, [rbp+57h+SubKey]; unsigned __int16 *
0x18000d7e9  mov     edx, esi; unsigned int
0x18000d7eb  lea     rcx, aAuthinfo; "AuthInfo"
0x18000d7f2  call    ?GenerateIndexedString@@YAJPEBGKPEAGK@Z; GenerateIndexedString(ushort const *,ulong,ushort *,ulong)
0x18000d7f7  mov     ebx, eax
0x18000d7f9  test    eax, eax
0x18000d7fb  js      loc_18000DAE1
0x18000d801  lea     rcx, [rbp+57h+var_B0]
0x18000d805  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d80a  lea     rcx, [rbp+57h+dwDisposition]
0x18000d80e  xor     r9d, r9d; lpClass
0x18000d811  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d816  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000d81a  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d81f  xor     r8d, r8d; Reserved
0x18000d822  mov     [rsp+110h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000d82b  mov     rcx, r13; hKey
0x18000d82e  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d836  mov     [rsp+110h+dwOptions], 0; dwOptions
0x18000d83e  call    cs:__imp_RegCreateKeyExW
0x18000d845  nop     dword ptr [rax+rax+00h]
0x18000d84a  mov     ebx, eax
0x18000d84c  test    eax, eax
0x18000d84e  jnz     loc_18000D6E2
0x18000d854  xor     ebx, ebx
0x18000d856  cmp     [rbp+57h+var_BC], ebx
0x18000d859  jz      loc_18000D902
0x18000d85f  test    r12d, r12d
0x18000d862  jz      loc_18000D902
0x18000d868  lea     rcx, [rbp+57h+var_A8]
0x18000d86c  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000d871  lea     rcx, [rbp+57h+dwDisposition]
0x18000d875  xor     r9d, r9d; lpClass
0x18000d878  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18000d87d  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18000d881  mov     rcx, [rbp+57h+var_B8]; hKey
0x18000d885  xor     r8d, r8d; Reserved
0x18000d888  mov     [rsp+110h+phkResult], rax; phkResult
0x18000d88d  mov     [rsp+110h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000d892  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18000d89a  mov     [rsp+110h+dwOptions], ebx; dwOptions
0x18000d89e  call    cs:__imp_RegCreateKeyExW
0x18000d8a5  nop     dword ptr [rax+rax+00h]
0x18000d8aa  mov     ebx, eax
0x18000d8ac  test    eax, eax
0x18000d8ae  jnz     loc_18000D6E2
0x18000d8b4  mov     r8d, [rdi+r14*8+0C0h]
0x18000d8bc  lea     rax, qword_18002A538
0x18000d8c3  mov     rcx, [rbp+57h+var_A8]; hKey
0x18000d8c7  lea     r9, off_1800261C0; "AuthRootName"
0x18000d8ce  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d8d6  lea     edx, [rbx+1]
0x18000d8d9  mov     [rsp+110h+phkResult], rax; unsigned __int8 *
0x18000d8de  mov     dword ptr [rsp+110h+lpSecurityAttributes], 48h ; 'H'; int
0x18000d8e6  mov     qword ptr [rsp+110h+samDesired], r15; __int64
0x18000d8eb  mov     [rsp+110h+dwOptions], 5; int
0x18000d8f3  call    SaveStructInRegistry
0x18000d8f8  mov     ebx, eax
0x18000d8fa  test    eax, eax
0x18000d8fc  js      loc_18000DAE1
0x18000d902  mov     r8d, [rdi+r14*8+0C0h]
0x18000d90a  lea     rax, qword_18002A538
0x18000d911  mov     rcx, [rbp+57h+var_B0]; hKey
0x18000d915  lea     r9, off_180026260; "AuthData"
0x18000d91c  mov     dword ptr [rsp+110h+lpdwDisposition], 10h; unsigned int
0x18000d924  mov     edx, 1
0x18000d929  mov     [rsp+110h+phkResult], rax; unsigned __int8 *
0x18000d92e  mov     dword ptr [rsp+110h+lpSecurityAttributes], 48h ; 'H'; int
0x18000d936  mov     qword ptr [rsp+110h+samDesired], r15; __int64
0x18000d93b  mov     [rsp+110h+dwOptions], 2; int
0x18000d943  call    SaveStructInRegistry
0x18000d948  xor     r15d, r15d
0x18000d94b  mov     ebx, eax
0x18000d94d  test    eax, eax
0x18000d94f  js      loc_18000DAE1
0x18000d955  mov     rcx, [rbp+57h+var_A8]; hKey
0x18000d959  test    rcx, rcx
0x18000d95c  jz      short loc_18000D96E
  ... truncated ...
```
