# CPkgDefCacheNonVolatileBase::SaveConfigCacheMetaData(CFileDiscovery const &)

- ea: `0x140052440`
- end: `0x140052655`
- name: `?SaveConfigCacheMetaData@CPkgDefCacheNonVolatileBase@@MEAAJAEBVCFileDiscovery@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(CPkgDefCacheNonVolatileBase *__hidden this, const struct CFileDiscovery *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140001020`
- `0x140002190`
- `0x140003160`
- `0x1400095f4`
- `0x140046e88`
- `0x140052440`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140052600`
- `ADVAPI32!RegCloseKey` at `0x14005261e`
- `ADVAPI32!RegCloseKey` at `0x140052600`
- `ADVAPI32!RegCloseKey` at `0x14005261e`
- `ADVAPI32!RegCreateKeyExW` at `0x14005251a`
- `ADVAPI32!RegCreateKeyExW` at `0x14005251a`
- `ADVAPI32!RegSetValueExW` at `0x1400525a5`
- `ADVAPI32!RegSetValueExW` at `0x1400525a5`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400524b2`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400524b2`
- `ADVAPI32!RevertToSelf` at `0x1400525f1`
- `ADVAPI32!RevertToSelf` at `0x14005260f`
- `ADVAPI32!RevertToSelf` at `0x1400525f1`
- `ADVAPI32!RevertToSelf` at `0x14005260f`

## string_xrefs

- `0x14005254d`: `ConfigPkgDefCacheMetaData`
- `0x140052484`: `Saving pkgdef cache meta data`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPkgDefCacheNonVolatileBase::SaveConfigCacheMetaData(
        CPkgDefCacheNonVolatileBase *this,
        const struct CFileDiscovery *a2)
{
  HKEY v4; // r14
  bool v5; // di
  const WCHAR *v6; // rsi
  HKEY v7; // rbx
  DWORD dwOptions; // eax
  LSTATUS v9; // eax
  signed int v10; // esi
  const struct std::nothrow_t *v11; // rdx
  HKEY v12; // rbx
  LSTATUS v13; // eax
  const struct std::nothrow_t *v14; // rdx
  LPCWSTR v15; // rdx
  DWORD dwDisposition; // [rsp+54h] [rbp-5h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-1h] BYREF
  __int128 v19; // [rsp+60h] [rbp+7h]
  __int64 v20; // [rsp+70h] [rbp+17h]
  HKEY phkResult; // [rsp+78h] [rbp+1Fh] BYREF

  if ( *((_BYTE *)this + 288) )
    return (*(__int64 (__fastcall **)(CPkgDefCacheNonVolatileBase *))(*(_QWORD *)this + 64LL))(this);
  CLogger::LogInfo(L"Saving pkgdef cache meta data", 0, 0);
  v20 = 0;
  v4 = 0;
  v19 = 0u;
  v5 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  v6 = (const WCHAR *)*((_QWORD *)this + 23);
  v7 = hKey;
  if ( *((_QWORD *)this + 29) )
    v7 = (HKEY)*((_QWORD *)this + 29);
  dwOptions = (*(__int64 (__fastcall **)(CPkgDefCacheNonVolatileBase *))(*(_QWORD *)this + 32LL))(this);
  phkResult = 0;
  v9 = RegCreateKeyExW(v7, v6, 0, 0, dwOptions, 0x2001Fu, 0, &phkResult, &dwDisposition);
  if ( !v9 )
  {
    v4 = phkResult;
    *(_QWORD *)&v19 = phkResult;
    DWORD2(v19) = 0;
  }
  v10 = (unsigned __int16)(v9 != 0 ? v9 : 0) | 0x80070000;
  if ( (v9 != 0 ? v9 : 0) <= 0 )
    v10 = v9 != 0 ? v9 : 0;
  if ( v10 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &lpValueName,
      L"ConfigPkgDefCacheMetaData");
    phkResult = 0;
    v10 = ConvertFileDiscoveryListToBinaryBlob((char *)a2 + 32, &phkResult, &dwDisposition);
    if ( v10 >= 0 )
    {
      v12 = phkResult;
      v13 = RegSetValueExW(v4, lpValueName, 0, 3u, (const BYTE *)phkResult, dwDisposition);
      v10 = (unsigned __int16)v13 | 0x80070000;
      if ( v13 <= 0 )
        v10 = v13;
      operator delete(v12, v14);
      if ( v10 >= 0 )
        v10 = 0;
    }
    else
    {
      operator delete(phkResult, v11);
    }
    v15 = lpValueName - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpValueName - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
    }
    if ( v10 >= 0 )
    {
      if ( v5 )
        RevertToSelf();
      if ( v4 )
        RegCloseKey(v4);
      return (*(__int64 (__fastcall **)(CPkgDefCacheNonVolatileBase *))(*(_QWORD *)this + 64LL))(this);
    }
  }
  if ( v5 )
    RevertToSelf();
  if ( v4 )
    RegCloseKey(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140052440  mov     [rsp-8+arg_10], rbx
0x140052445  mov     [rsp-8+arg_18], rsi
0x14005244a  push    rbp
0x14005244b  push    rdi
0x14005244c  push    r13
0x14005244e  push    r14
0x140052450  push    r15
0x140052452  lea     rbp, [rsp-37h]
0x140052457  sub     rsp, 90h
0x14005245e  mov     rax, cs:__security_cookie
0x140052465  xor     rax, rsp
0x140052468  mov     [rbp+57h+var_30], rax
0x14005246c  mov     r13, rdx
0x14005246f  mov     r15, rcx
0x140052472  cmp     byte ptr [rcx+120h], 0
0x140052479  jnz     loc_140052624
0x14005247f  xor     r8d, r8d; unsigned __int16 *
0x140052482  xor     edx, edx; int
0x140052484  lea     rcx, aSavingPkgdefCa
0x14005248b  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z
0x140052490  xorps   xmm0, xmm0
0x140052493  xor     eax, eax
0x140052495  movups  [rbp+57h+var_50], xmm0
0x140052499  mov     [rbp+57h+var_40], rax
0x14005249d  xor     r14d, r14d
0x1400524a0  mov     qword ptr [rbp+57h+var_50], r14
0x1400524a4  and     dword ptr [rbp+57h+var_50+8], eax
0x1400524a7  and     [rbp+57h+var_40], rax
0x1400524ab  mov     rcx, [r15+0E0h]; hToken
0x1400524b2  call    cs:__imp_ImpersonateLoggedOnUser
0x1400524b8  test    eax, eax
0x1400524ba  setnz   dil
0x1400524be  mov     [rbp+57h+var_60], dil
0x1400524c2  mov     rsi, [r15+0B8h]
0x1400524c9  mov     rax, [r15+0E8h]
0x1400524d0  mov     rbx, cs:hKey
0x1400524d7  test    rax, rax
0x1400524da  cmovnz  rbx, rax
0x1400524de  mov     rax, [r15]
0x1400524e1  mov     rcx, r15
0x1400524e4  call    qword ptr [rax+20h]
0x1400524e7  and     [rbp+57h+var_38], r14
0x1400524eb  lea     rcx, [rbp+57h+dwDisposition]
0x1400524ef  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x1400524f4  lea     rcx, [rbp+57h+var_38]
0x1400524f8  mov     [rsp+0B0h+phkResult], rcx; phkResult
0x1400524fd  and     [rsp+0B0h+var_80], r14
0x140052502  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x14005250a  mov     [rsp+0B0h+dwOptions], eax; dwOptions
0x14005250e  xor     r9d, r9d; lpClass
0x140052511  xor     r8d, r8d; Reserved
0x140052514  mov     rdx, rsi; lpSubKey
0x140052517  mov     rcx, rbx; hKey
0x14005251a  call    cs:__imp_RegCreateKeyExW
0x140052520  test    eax, eax
0x140052522  jnz     short loc_14005252F
0x140052524  mov     r14, [rbp+57h+var_38]
0x140052528  mov     qword ptr [rbp+57h+var_50], r14
0x14005252c  and     dword ptr [rbp+57h+var_50+8], eax
0x14005252f  mov     ecx, eax
0x140052531  neg     ecx
0x140052533  sbb     edx, edx
0x140052535  and     edx, eax
0x140052537  movzx   esi, dx
0x14005253a  or      esi, 80070000h
0x140052540  test    edx, edx
0x140052542  cmovle  esi, edx
0x140052545  test    esi, esi
0x140052547  js      loc_1400525EC
0x14005254d  lea     rdx, aConfigpkgdefca_0
0x140052554  lea     rcx, [rbp+57h+lpValueName]
0x140052558  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z
0x14005255d  nop
0x14005255e  and     [rbp+57h+var_38], 0
0x140052563  lea     rcx, [r13+20h]
0x140052567  lea     r8, [rbp+57h+dwDisposition]
0x14005256b  lea     rdx, [rbp+57h+var_38]
0x14005256f  call    ?ConvertFileDiscoveryListToBinaryBlob@@YAJAEBV?$CAtlList@UDiscoveredFile@@V?$CElementTraits@UDiscoveredFile@@@ATL@@@ATL@@AEAV?$CAutoVectorPtr@E@2@AEAK@Z
0x140052574  mov     esi, eax
0x140052576  test    eax, eax
0x140052578  jns     short loc_140052585
0x14005257a  mov     rcx, [rbp+57h+var_38]; void *
0x14005257e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x140052583  jmp     short loc_1400525C7
0x140052585  mov     eax, [rbp+57h+dwDisposition]
0x140052588  mov     [rsp+0B0h+samDesired], eax; cbData
0x14005258c  mov     rbx, [rbp+57h+var_38]
0x140052590  mov     qword ptr [rsp+0B0h+dwOptions], rbx; lpData
0x140052595  mov     r9d, 3; dwType
0x14005259b  xor     r8d, r8d; Reserved
0x14005259e  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x1400525a2  mov     rcx, r14; hKey
0x1400525a5  call    cs:__imp_RegSetValueExW
0x1400525ab  movzx   esi, ax
0x1400525ae  or      esi, 80070000h
0x1400525b4  test    eax, eax
0x1400525b6  cmovle  esi, eax
0x1400525b9  mov     rcx, rbx; void *
0x1400525bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1400525c1  test    esi, esi
0x1400525c3  js      short loc_1400525C7
0x1400525c5  xor     esi, esi
0x1400525c7  mov     rdx, [rbp+57h+lpValueName]
0x1400525cb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400525cf  or      eax, 0FFFFFFFFh
0x1400525d2  lock xadd [rdx+10h], eax
0x1400525d7  sub     eax, 1
0x1400525da  jg      short loc_1400525E8
0x1400525dc  lfence
0x1400525df  mov     rcx, [rdx]
0x1400525e2  mov     rax, [rcx]
0x1400525e5  call    qword ptr [rax+8]
0x1400525e8  test    esi, esi
0x1400525ea  jns     short loc_14005260A
0x1400525ec  test    dil, dil
0x1400525ef  jz      short loc_1400525F8
0x1400525f1  call    cs:__imp_RevertToSelf
0x1400525f7  nop
0x1400525f8  test    r14, r14
0x1400525fb  jz      short loc_140052606
0x1400525fd  mov     rcx, r14; hKey
0x140052600  call    cs:__imp_RegCloseKey
0x140052606  mov     eax, esi
0x140052608  jmp     short loc_14005262D
0x14005260a  test    dil, dil
0x14005260d  jz      short loc_140052616
0x14005260f  call    cs:__imp_RevertToSelf
0x140052615  nop
0x140052616  test    r14, r14
0x140052619  jz      short loc_140052624
0x14005261b  mov     rcx, r14; hKey
0x14005261e  call    cs:__imp_RegCloseKey
0x140052624  mov     rax, [r15]
0x140052627  mov     rcx, r15
0x14005262a  call    qword ptr [rax+40h]
0x14005262d  mov     rcx, [rbp+57h+var_30]
0x140052631  xor     rcx, rsp; StackCookie
0x140052634  call    __security_check_cookie
0x140052639  lea     r11, [rsp+0B0h+var_20]
0x140052641  mov     rbx, [r11+40h]
0x140052645  mov     rsi, [r11+48h]
0x140052649  mov     rsp, r11
0x14005264c  pop     r15
0x14005264e  pop     r14
0x140052650  pop     r13
0x140052652  pop     rdi
0x140052653  pop     rbp
0x140052654  retn
```
