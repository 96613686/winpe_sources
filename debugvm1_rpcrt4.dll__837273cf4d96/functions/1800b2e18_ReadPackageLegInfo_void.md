# ReadPackageLegInfo(void)

- ea: `0x1800b2e18`
- end: `0x1800b30fa`
- name: `?ReadPackageLegInfo@@YAHXZ`
- size: `738`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009d3ec`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18005ceb0`
- `0x1800a5004`
- `0x1800a6a40`
- `0x1800b2e18`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!wcstoul` at `0x1800b3096`
- `ntdll!wcstoul` at `0x1800b3096`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b2e87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b2e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3004`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2ec1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2ff8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2ec1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2ff8`

## string_xrefs

- `0x1800b2e79`: `Software\Microsoft\Rpc\SecurityService`

## pseudocode

```c
__int64 ReadPackageLegInfo(void)
{
  unsigned int v1; // ebx
  char *pvData; // rdi
  LSTATUS ValueW; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  char *v13; // rax
  LSTATUS v14; // esi
  int v15; // esi
  char *v16; // rcx
  char *v17; // rdx
  int v18; // eax
  _DWORD *v19; // r15
  int v20; // r14d
  const wchar_t *i; // rcx
  wchar_t *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp+0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp+8h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp+10h] BYREF
  struct MUTEX *v28; // [rsp+58h] [rbp+18h] BYREF

  pcbData = 0;
  hkey = 0;
  v28 = 0;
  if ( FourLeggedPackages )
    return 1;
  InsureSecuritySupportLoaded(&v28);
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc\\SecurityService", 0, 0x20019u, &hkey) )
  {
    pvData = 0;
    ValueW = RegGetValueW(hkey, 0, L"Four-legged packages", 0x20u, 0, 0, &pcbData);
    if ( ValueW == 2 )
    {
LABEL_6:
      v1 = 1;
LABEL_7:
      FourLeggedPackages = &NullPackageList;
      goto LABEL_8;
    }
    if ( ValueW )
      goto LABEL_15;
    if ( pcbData > 0xFA0 )
      goto LABEL_6;
    v7 = pcbData;
    if ( !pcbData )
      goto LABEL_49;
    if ( pcbData > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_49;
    v8 = pcbData + g_ulAdditionalProbeSize + 8;
    if ( v8 < pcbData || !(unsigned int)VerifyStackAvailable(v8, v4, v5, v6) )
      goto LABEL_49;
    v9 = v7 + 23;
    if ( v7 + 23 <= v7 + 8 )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
    v11 = alloca(v10);
    v12 = alloca(v10);
    pvData = (char *)&pcbData;
    if ( &v24 == (__int64 *)-64LL || (pcbData = 1801679955, (pvData = (char *)&hkey) == 0) )
    {
LABEL_49:
      if ( v7 + 8 >= v7 )
      {
        v13 = (char *)((__int64 (*)(void))g_pfnAllocate)();
        pvData = v13;
        if ( v13 )
        {
          *(_DWORD *)v13 = 1885431112;
          pvData = v13 + 8;
        }
      }
    }
    if ( !pvData )
      goto LABEL_15;
    v14 = RegGetValueW(hkey, 0, L"Four-legged packages", 0x20u, 0, pvData, &pcbData);
    RegCloseKey(hkey);
    hkey = 0;
    v1 = 1;
    if ( (unsigned int)(v14 - 1011) <= 1 )
      goto LABEL_7;
    if ( v14 )
    {
      v1 = 0;
LABEL_11:
      if ( *((_DWORD *)pvData - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return v1;
    }
    v15 = 0;
    v16 = pvData;
    v17 = &pvData[2 * pcbData];
    if ( pvData < v17 )
    {
      do
      {
        v18 = v15 + 1;
        if ( *(_WORD *)v16 )
          v18 = v15;
        v16 += 2;
        v15 = v18;
      }
      while ( v16 < v17 );
    }
    v19 = AllocWrapper(saturated_mul(v15, 4u));
    if ( v19 )
    {
      EndPtr = 0;
      v20 = 0;
      for ( i = (const wchar_t *)pvData; v20 < v15; i = v22 + 1 )
      {
        v19[v20] = wcstoul(i, &EndPtr, 10);
        v22 = EndPtr;
        if ( *EndPtr )
        {
          --v20;
          v23 = -1;
          do
            ++v23;
          while ( EndPtr[v23] );
          v22 = &EndPtr[v23];
          EndPtr = v22;
        }
        ++v20;
      }
      if ( FourLeggedPackages && FourLeggedPackages != &NullPackageList )
        FreeWrapper(FourLeggedPackages);
      FourLeggedPackages = v19;
    }
    else
    {
LABEL_15:
      v1 = 0;
    }
LABEL_8:
    if ( hkey )
      RegCloseKey(hkey);
    if ( !pvData )
      return v1;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b2e18  push    rbp
0x1800b2e1a  push    rbx
0x1800b2e1b  push    rsi
0x1800b2e1c  push    rdi
0x1800b2e1d  push    r12
0x1800b2e1f  push    r13
0x1800b2e21  push    r14
0x1800b2e23  push    r15
0x1800b2e25  sub     rsp, 78h
0x1800b2e29  lea     rbp, [rsp+40h]
0x1800b2e2e  mov     rax, cs:__security_cookie
0x1800b2e35  xor     rax, rbp
0x1800b2e38  mov     [rbp+70h+var_50], rax
0x1800b2e3c  xor     r12d, r12d
0x1800b2e3f  cmp     cs:?FourLeggedPackages@@3PEAKEA, r12; ulong * FourLeggedPackages
0x1800b2e46  mov     [rbp+70h+var_70], r12d
0x1800b2e4a  mov     [rbp+70h+hkey], r12
0x1800b2e4e  mov     [rbp+70h+var_58], r12
0x1800b2e52  jz      short loc_1800B2E5E
0x1800b2e54  lea     eax, [r12+1]
0x1800b2e59  jmp     loc_1800B2F0D
0x1800b2e5e  lea     rcx, [rbp+70h+var_58]; struct MUTEX **
0x1800b2e62  call    ?InsureSecuritySupportLoaded@@YAJPEAPEAVMUTEX@@@Z; InsureSecuritySupportLoaded(MUTEX * *)
0x1800b2e67  lea     rax, [rbp+70h+hkey]
0x1800b2e6b  mov     r9d, 20019h; samDesired
0x1800b2e71  xor     r8d, r8d; ulOptions
0x1800b2e74  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800b2e79  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x1800b2e80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b2e87  call    cs:__imp_RegOpenKeyExA
0x1800b2e8d  test    eax, eax
0x1800b2e8f  jz      short loc_1800B2E96
0x1800b2e91  mov     ebx, r12d
0x1800b2e94  jmp     short loc_1800B2F0B
0x1800b2e96  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b2e9a  lea     rax, [rbp+70h+var_70]
0x1800b2e9e  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b2ea3  lea     r8, aFourLeggedPack; "Four-legged packages"
0x1800b2eaa  mov     esi, 20h ; ' '
0x1800b2eaf  mov     [rsp+0B0h+pvData], r12; pvData
0x1800b2eb4  mov     r9d, esi; dwFlags
0x1800b2eb7  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b2ebc  xor     edx, edx; lpSubKey
0x1800b2ebe  mov     rdi, r12
0x1800b2ec1  call    cs:__imp_RegGetValueW
0x1800b2ec7  cmp     eax, 2
0x1800b2eca  jnz     short loc_1800B2F2A
0x1800b2ecc  mov     ebx, 1
0x1800b2ed1  lea     rax, ?NullPackageList@@3PAKA; ulong near * NullPackageList
0x1800b2ed8  mov     cs:?FourLeggedPackages@@3PEAKEA, rax; ulong * FourLeggedPackages
0x1800b2edf  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b2ee3  test    rcx, rcx
0x1800b2ee6  jz      short loc_1800B2EEE
0x1800b2ee8  call    cs:__imp_RegCloseKey
0x1800b2eee  test    rdi, rdi
0x1800b2ef1  jz      short loc_1800B2F0B
0x1800b2ef3  lea     rcx, [rdi-8]
0x1800b2ef7  cmp     dword ptr [rcx], 70616548h
0x1800b2efd  jnz     short loc_1800B2F0B
0x1800b2eff  mov     rax, cs:g_pfnFree
0x1800b2f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f0b  mov     eax, ebx
0x1800b2f0d  mov     rcx, [rbp+70h+var_50]
0x1800b2f11  xor     rcx, rbp; StackCookie
0x1800b2f14  call    __security_check_cookie
0x1800b2f19  lea     rsp, [rbp+38h]
0x1800b2f1d  pop     r15
0x1800b2f1f  pop     r14
0x1800b2f21  pop     r13
0x1800b2f23  pop     r12
0x1800b2f25  pop     rdi
0x1800b2f26  pop     rsi
0x1800b2f27  pop     rbx
0x1800b2f28  pop     rbp
0x1800b2f29  retn
0x1800b2f2a  test    eax, eax
0x1800b2f2c  jz      short loc_1800B2F33
0x1800b2f2e  mov     ebx, r12d
0x1800b2f31  jmp     short loc_1800B2EDF
0x1800b2f33  cmp     [rbp+70h+var_70], 0FA0h
0x1800b2f3a  ja      short loc_1800B2ECC
0x1800b2f3c  mov     ebx, [rbp+70h+var_70]
0x1800b2f3f  test    rbx, rbx
0x1800b2f42  jz      short loc_1800B2FA5
0x1800b2f44  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800b2f4b  ja      short loc_1800B2FA5
0x1800b2f4d  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b2f54  add     rcx, 8
0x1800b2f58  add     rcx, rbx
0x1800b2f5b  cmp     rcx, rbx
0x1800b2f5e  jb      short loc_1800B2FA5
0x1800b2f60  call    VerifyStackAvailable
0x1800b2f65  test    eax, eax
0x1800b2f67  jz      short loc_1800B2FA5
0x1800b2f69  lea     rax, [rbx+8]
0x1800b2f6d  lea     rcx, [rax+0Fh]
0x1800b2f71  cmp     rcx, rax
0x1800b2f74  ja      short loc_1800B2F80
0x1800b2f76  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b2f80  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b2f84  mov     rax, rcx
0x1800b2f87  call    __chkstk_0
0x1800b2f8c  sub     rsp, rcx
0x1800b2f8f  lea     rdi, [rsp+0B0h+var_70]
0x1800b2f94  test    rdi, rdi
0x1800b2f97  jz      short loc_1800B2FA5
0x1800b2f99  mov     dword ptr [rdi], 6B637453h
0x1800b2f9f  add     rdi, 8
0x1800b2fa3  jnz     short loc_1800B2FCC
0x1800b2fa5  lea     rcx, [rbx+8]
0x1800b2fa9  cmp     rcx, rbx
0x1800b2fac  jb      short loc_1800B2FCC
0x1800b2fae  mov     rax, cs:g_pfnAllocate
0x1800b2fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2fba  mov     rdi, rax
0x1800b2fbd  test    rax, rax
0x1800b2fc0  jz      short loc_1800B2FCC
0x1800b2fc2  mov     dword ptr [rax], 70616548h
0x1800b2fc8  add     rdi, 8
0x1800b2fcc  test    rdi, rdi
0x1800b2fcf  jz      loc_1800B2F2E
0x1800b2fd5  mov     rcx, [rbp+70h+hkey]; hkey
0x1800b2fd9  lea     rax, [rbp+70h+var_70]
0x1800b2fdd  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800b2fe2  lea     r8, aFourLeggedPack; "Four-legged packages"
0x1800b2fe9  mov     [rsp+0B0h+pvData], rdi; pvData
0x1800b2fee  mov     r9d, esi; dwFlags
0x1800b2ff1  xor     edx, edx; lpSubKey
0x1800b2ff3  mov     [rsp+0B0h+phkResult], r12; pdwType
0x1800b2ff8  call    cs:__imp_RegGetValueW
0x1800b2ffe  mov     rcx, [rbp+70h+hkey]; hKey
0x1800b3002  mov     esi, eax
0x1800b3004  call    cs:__imp_RegCloseKey
0x1800b300a  lea     ecx, [rsi-3F3h]
0x1800b3010  mov     [rbp+70h+hkey], r12
0x1800b3014  mov     ebx, 1
0x1800b3019  cmp     ecx, ebx
0x1800b301b  jbe     loc_1800B2ED1
0x1800b3021  test    esi, esi
0x1800b3023  jz      short loc_1800B302D
0x1800b3025  mov     ebx, r12d
0x1800b3028  jmp     loc_1800B2EF3
0x1800b302d  mov     eax, [rbp+70h+var_70]
0x1800b3030  mov     esi, r12d
0x1800b3033  mov     rcx, rdi
0x1800b3036  lea     rdx, [rdi+rax*2]
0x1800b303a  cmp     rdi, rdx
0x1800b303d  jnb     short loc_1800B3054
0x1800b303f  cmp     [rcx], r12w
0x1800b3043  lea     eax, [rsi+1]
0x1800b3046  cmovnz  eax, esi
0x1800b3049  add     rcx, 2
0x1800b304d  mov     esi, eax
0x1800b304f  cmp     rcx, rdx
0x1800b3052  jb      short loc_1800B303F
0x1800b3054  movsxd  rcx, esi
0x1800b3057  mov     eax, 4
0x1800b305c  mul     rcx
0x1800b305f  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800b3066  cmovb   rax, r13
0x1800b306a  mov     rcx, rax; dwBytes
0x1800b306d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b3072  mov     r15, rax
0x1800b3075  test    rax, rax
0x1800b3078  jz      loc_1800B2F2E
0x1800b307e  mov     [rbp+70h+EndPtr], r12
0x1800b3082  mov     r14d, r12d
0x1800b3085  mov     rcx, rdi; String
0x1800b3088  test    esi, esi
0x1800b308a  jle     short loc_1800B30D1
0x1800b308c  mov     r8d, 0Ah; Radix
0x1800b3092  lea     rdx, [rbp+70h+EndPtr]; EndPtr
0x1800b3096  call    cs:__imp_wcstoul
0x1800b309c  movsxd  rcx, r14d
0x1800b309f  mov     [r15+rcx*4], eax
0x1800b30a3  mov     rax, [rbp+70h+EndPtr]
0x1800b30a7  cmp     [rax], r12w
0x1800b30ab  jz      short loc_1800B30C5
0x1800b30ad  sub     r14d, ebx
0x1800b30b0  mov     rcx, r13
0x1800b30b3  inc     rcx
0x1800b30b6  cmp     [rax+rcx*2], r12w
0x1800b30bb  jnz     short loc_1800B30B3
0x1800b30bd  lea     rax, [rax+rcx*2]
0x1800b30c1  mov     [rbp+70h+EndPtr], rax
0x1800b30c5  add     r14d, ebx
0x1800b30c8  lea     rcx, [rax+2]
0x1800b30cc  cmp     r14d, esi
0x1800b30cf  jl      short loc_1800B308C
0x1800b30d1  mov     rcx, cs:?FourLeggedPackages@@3PEAKEA; lpMem
0x1800b30d8  test    rcx, rcx
0x1800b30db  jz      short loc_1800B30EE
0x1800b30dd  lea     rax, ?NullPackageList@@3PAKA; ulong near * NullPackageList
0x1800b30e4  cmp     rcx, rax
0x1800b30e7  jz      short loc_1800B30EE
0x1800b30e9  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b30ee  mov     cs:?FourLeggedPackages@@3PEAKEA, r15; ulong * FourLeggedPackages
0x1800b30f5  jmp     loc_1800B2EDF
```
