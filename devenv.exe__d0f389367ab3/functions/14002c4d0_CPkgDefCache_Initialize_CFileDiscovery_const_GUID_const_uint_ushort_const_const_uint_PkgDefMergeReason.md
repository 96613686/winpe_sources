# CPkgDefCache::Initialize(CFileDiscovery const &,_GUID const *,uint,ushort const * const *,uint,PkgDefMergeReason *)

- ea: `0x14002c4d0`
- end: `0x14002c661`
- name: `?Initialize@CPkgDefCache@@UEAAJAEBVCFileDiscovery@@PEBU_GUID@@IPEBQEBGIPEAW4PkgDefMergeReason@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(CPkgDefCache *__hidden this, const struct CFileDiscovery *, const struct _GUID *, unsigned int, HKEY hKey, DWORD dwDisposition, enum PkgDefMergeReason *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14002c310`
- `0x14004c560`

## callees

- `0x140003160`
- `0x140004950`
- `0x14002c4d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002c623`
- `ADVAPI32!RegCloseKey` at `0x14002c634`
- `ADVAPI32!RegCloseKey` at `0x14002c623`
- `ADVAPI32!RegCloseKey` at `0x14002c634`
- `ADVAPI32!RegCreateKeyExW` at `0x14002c60d`
- `ADVAPI32!RegCreateKeyExW` at `0x14002c60d`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14002c5a1`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14002c5a1`
- `ADVAPI32!RevertToSelf` at `0x14002c63f`
- `ADVAPI32!RevertToSelf` at `0x14002c63f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPkgDefCache::Initialize(
        CPkgDefCache *this,
        const struct CFileDiscovery *a2,
        const struct _GUID *a3,
        int a4,
        HKEY hKey,
        DWORD dwDisposition)
{
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rdx
  HKEY v12; // rsi
  bool v13; // bl
  HKEY v14; // r15
  const WCHAR *v15; // rdi
  DWORD dwOptions; // eax
  __int64 v18; // [rsp+90h] [rbp+20h] BYREF

  if ( !*(_DWORD *)(*((_QWORD *)this + 14) - 16LL) )
  {
    v9 = (*(__int64 (__fastcall **)(CPkgDefCache *, char *))(*(_QWORD *)this + 48LL))(this, (char *)this + 64);
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 112, v9);
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 13) - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v18,
      &WindowName);
    v10 = (*(__int64 (__fastcall **)(CPkgDefCache *, __int64 *, char *))(*(_QWORD *)this + 40LL))(
            this,
            &v18,
            (char *)this + 64);
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 104, v10);
    v11 = (_QWORD *)(v18 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    }
  }
  *((_QWORD *)this + 2) = a3;
  *((_DWORD *)this + 6) = a4;
  *((_QWORD *)this + 4) = hKey;
  *((_DWORD *)this + 10) = dwDisposition;
  v12 = ::hKey;
  if ( *((_QWORD *)this + 29) )
    v12 = (HKEY)*((_QWORD *)this + 29);
  v13 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  LOBYTE(dwDisposition) = v13;
  v14 = 0;
  v15 = (const WCHAR *)*((_QWORD *)this + 18);
  dwOptions = (*(__int64 (__fastcall **)(CPkgDefCache *))(*(_QWORD *)this + 32LL))(this);
  hKey = 0;
  if ( !RegCreateKeyExW(v12, v15, 0, 0, dwOptions, 0x20006u, 0, &hKey, &dwDisposition) )
  {
    v14 = hKey;
    if ( hKey )
    {
      RegCloseKey(hKey);
      v14 = 0;
    }
  }
  if ( v14 )
    RegCloseKey(v14);
  if ( v13 )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x14002c4d0  mov     [rsp-18h+arg_8], rbx
0x14002c4d5  mov     [rsp-18h+arg_10], rsi
0x14002c4da  mov     [rsp-18h+arg_18], rdi
0x14002c4df  push    rbp
0x14002c4e0  push    r14
0x14002c4e2  push    r15
0x14002c4e4  mov     rbp, rsp
0x14002c4e7  sub     rsp, 70h
0x14002c4eb  mov     esi, r9d
0x14002c4ee  mov     r15, r8
0x14002c4f1  mov     r14, rcx
0x14002c4f4  mov     rax, [rcx+70h]
0x14002c4f8  cmp     dword ptr [rax-10h], 0
0x14002c4fc  jnz     short loc_14002C514
0x14002c4fe  mov     rax, [rcx]
0x14002c501  lea     rdx, [rcx+40h]
0x14002c505  call    qword ptr [rax+30h]
0x14002c508  mov     rdx, rax
0x14002c50b  lea     rcx, [r14+70h]
0x14002c50f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002c514  mov     rax, [r14+68h]
0x14002c518  cmp     dword ptr [rax-10h], 0
0x14002c51c  jnz     short loc_14002C56E
0x14002c51e  lea     rdx, WindowName
0x14002c525  lea     rcx, [rbp+arg_0]
0x14002c529  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002c52e  nop
0x14002c52f  mov     rax, [r14]
0x14002c532  lea     r8, [r14+40h]
0x14002c536  lea     rdx, [rbp+arg_0]
0x14002c53a  mov     rcx, r14
0x14002c53d  call    qword ptr [rax+28h]
0x14002c540  mov     rdx, rax
0x14002c543  lea     rcx, [r14+68h]
0x14002c547  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002c54c  nop
0x14002c54d  mov     rdx, [rbp+arg_0]
0x14002c551  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002c555  or      eax, 0FFFFFFFFh
0x14002c558  lock xadd [rdx+10h], eax
0x14002c55d  sub     eax, 1
0x14002c560  jg      short loc_14002C56E
0x14002c562  lfence
0x14002c565  mov     rcx, [rdx]
0x14002c568  mov     rax, [rcx]
0x14002c56b  call    qword ptr [rax+8]
0x14002c56e  mov     [r14+10h], r15
0x14002c572  mov     [r14+18h], esi
0x14002c576  mov     rax, [rbp+hKey]
0x14002c57a  mov     [r14+20h], rax
0x14002c57e  mov     eax, [rbp+dwDisposition]
0x14002c581  mov     [r14+28h], eax
0x14002c585  mov     rax, [r14+0E8h]
0x14002c58c  mov     rsi, cs:hKey
0x14002c593  test    rax, rax
0x14002c596  cmovnz  rsi, rax
0x14002c59a  mov     rcx, [r14+0E0h]; hToken
0x14002c5a1  call    cs:__imp_ImpersonateLoggedOnUser
0x14002c5a7  test    eax, eax
0x14002c5a9  setnz   bl
0x14002c5ac  mov     byte ptr [rbp+dwDisposition], bl
0x14002c5af  xorps   xmm0, xmm0
0x14002c5b2  xor     eax, eax
0x14002c5b4  movups  [rbp+var_20], xmm0
0x14002c5b8  mov     [rbp+var_10], rax
0x14002c5bc  xor     r15d, r15d
0x14002c5bf  mov     qword ptr [rbp+var_20], r15
0x14002c5c3  and     dword ptr [rbp+var_20+8], eax
0x14002c5c6  and     [rbp+var_10], rax
0x14002c5ca  mov     rdi, [r14+90h]
0x14002c5d1  mov     rax, [r14]
0x14002c5d4  mov     rcx, r14
0x14002c5d7  call    qword ptr [rax+20h]
0x14002c5da  and     [rbp+hKey], r15
0x14002c5de  lea     rcx, [rbp+dwDisposition]
0x14002c5e2  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x14002c5e7  lea     rcx, [rbp+hKey]
0x14002c5eb  mov     [rsp+70h+phkResult], rcx; phkResult
0x14002c5f0  and     [rsp+70h+var_40], r15
0x14002c5f5  mov     [rsp+70h+samDesired], 20006h; samDesired
0x14002c5fd  mov     [rsp+70h+dwOptions], eax; dwOptions
0x14002c601  xor     r9d, r9d; lpClass
0x14002c604  xor     r8d, r8d; Reserved
0x14002c607  mov     rdx, rdi; lpSubKey
0x14002c60a  mov     rcx, rsi; hKey
0x14002c60d  call    cs:__imp_RegCreateKeyExW
0x14002c613  test    eax, eax
0x14002c615  jnz     short loc_14002C62C
0x14002c617  mov     r15, [rbp+hKey]
0x14002c61b  test    r15, r15
0x14002c61e  jz      short loc_14002C62C
0x14002c620  mov     rcx, r15; hKey
0x14002c623  call    cs:__imp_RegCloseKey
0x14002c629  xor     r15d, r15d
0x14002c62c  test    r15, r15
0x14002c62f  jz      short loc_14002C63B
0x14002c631  mov     rcx, r15; hKey
0x14002c634  call    cs:__imp_RegCloseKey
0x14002c63a  nop
0x14002c63b  test    bl, bl
0x14002c63d  jz      short loc_14002C645
0x14002c63f  call    cs:__imp_RevertToSelf
0x14002c645  xor     eax, eax
0x14002c647  lea     r11, [rsp+70h+var_s0]
0x14002c64c  mov     rbx, [r11+28h]
0x14002c650  mov     rsi, [r11+30h]
0x14002c654  mov     rdi, [r11+38h]
0x14002c658  mov     rsp, r11
0x14002c65b  pop     r15
0x14002c65d  pop     r14
0x14002c65f  pop     rbp
0x14002c660  retn
```
