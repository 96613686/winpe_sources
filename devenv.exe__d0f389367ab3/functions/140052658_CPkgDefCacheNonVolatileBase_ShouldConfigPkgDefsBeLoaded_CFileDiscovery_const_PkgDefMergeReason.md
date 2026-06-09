# CPkgDefCacheNonVolatileBase::ShouldConfigPkgDefsBeLoaded(CFileDiscovery const &,PkgDefMergeReason *)

- ea: `0x140052658`
- end: `0x14005289a`
- name: `?ShouldConfigPkgDefsBeLoaded@CPkgDefCacheNonVolatileBase@@IEAA_NAEBVCFileDiscovery@@PEAW4PkgDefMergeReason@@@Z`
- size: `578`
- prototype: `bool __fastcall(CPkgDefCacheNonVolatileBase *__hidden this, const struct CFileDiscovery *, enum PkgDefMergeReason *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1400147e0`
- `0x140052280`

## callees

- `0x140001020`
- `0x140002190`
- `0x140003160`
- `0x1400095f4`
- `0x140014564`
- `0x140046e88`
- `0x1400522ac`
- `0x140052658`
- `0x14006b58c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140052799`
- `ADVAPI32!RegCloseKey` at `0x140052799`
- `ADVAPI32!RegOpenKeyExW` at `0x1400526f7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400526f7`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400526b6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400526b6`
- `ADVAPI32!RevertToSelf` at `0x140052777`
- `ADVAPI32!RevertToSelf` at `0x140052777`

## string_xrefs

- `0x140052712`: `ConfigPkgDefCacheMetaData`
- `0x140052880`: `Forcing cache refresh based on flag`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall CPkgDefCacheNonVolatileBase::ShouldConfigPkgDefsBeLoaded(
        CPkgDefCacheNonVolatileBase *this,
        const struct CFileDiscovery *a2,
        enum PkgDefMergeReason *a3)
{
  bool v6; // bl
  HKEY v7; // rcx
  const struct std::nothrow_t *v8; // rdx
  int RegistryValue; // r14d
  char v11; // di
  const struct std::nothrow_t *v12; // rdx
  HKEY phkResult; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h]
  void *Buf2; // [rsp+58h] [rbp-28h] BYREF
  void *Buf1; // [rsp+60h] [rbp-20h] BYREF
  int v19; // [rsp+68h] [rbp-18h] BYREF

  *(_OWORD *)hKey = 0;
  v16 = 0;
  hKey[0] = 0;
  LODWORD(hKey[1]) = 0;
  if ( a3 )
    *(_DWORD *)a3 = 0;
  Buf1 = 0;
  Buf2 = 0;
  v6 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  v7 = ::hKey;
  if ( *((_QWORD *)this + 29) )
    v7 = (HKEY)*((_QWORD *)this + 29);
  phkResult = 0;
  if ( RegOpenKeyExW(v7, *((LPCWSTR *)this + 23), 0, 0x2001Fu, &phkResult) )
  {
    if ( a3 )
      *(_DWORD *)a3 = 16;
    goto LABEL_11;
  }
  hKey[0] = phkResult;
  LODWORD(hKey[1]) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    L"ConfigPkgDefCacheMetaData");
  RegistryValue = GetRegistryValue(hKey, &phkResult, &Buf1, &v19);
  v8 = (const struct std::nothrow_t *)(phkResult - 6);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  }
  if ( RegistryValue < 0 )
  {
    if ( a3 )
      *(_DWORD *)a3 = 13;
    goto LABEL_11;
  }
  if ( (int)ConvertFileDiscoveryListToBinaryBlob((char *)a2 + 32, &Buf2, &phkResult) < 0 )
  {
    if ( a3 )
      *(_DWORD *)a3 = 17;
    goto LABEL_11;
  }
  if ( (_DWORD)phkResult != v19 )
  {
    if ( a3 )
      *(_DWORD *)a3 = 14;
    goto LABEL_11;
  }
  if ( memcmp_0(Buf1, Buf2, (unsigned int)phkResult) )
  {
    if ( a3 )
      *(_DWORD *)a3 = 15;
    goto LABEL_11;
  }
  if ( !CPkgDefCacheNonVolatileBase::IsConfigCacheValid(this, a3) )
  {
LABEL_11:
    v11 = 1;
    goto LABEL_12;
  }
  if ( (*((_DWORD *)this + 2) & 0x100) != 0 )
  {
    if ( a3 )
      *(_DWORD *)a3 = 6;
    CLogger::LogInfo(L"Forcing cache refresh based on flag", 0, 0);
    goto LABEL_11;
  }
  v11 = 0;
LABEL_12:
  if ( v6 )
    RevertToSelf();
  operator delete(Buf2, v8);
  operator delete(Buf1, v12);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v11;
}

```

## disassembly

```asm
0x140052658  mov     [rsp-28h+arg_18], rbx
0x14005265d  push    rbp
0x14005265e  push    rsi
0x14005265f  push    rdi
0x140052660  push    r14
0x140052662  push    r15
0x140052664  mov     rbp, rsp
0x140052667  sub     rsp, 80h
0x14005266e  mov     rax, cs:__security_cookie
0x140052675  xor     rax, rsp
0x140052678  mov     [rbp+var_10], rax
0x14005267c  mov     rdi, r8
0x14005267f  mov     r15, rdx
0x140052682  mov     rsi, rcx
0x140052685  xorps   xmm0, xmm0
0x140052688  xor     eax, eax
0x14005268a  movups  xmmword ptr [rbp+hKey], xmm0
0x14005268e  mov     [rbp+var_30], rax
0x140052692  and     [rbp+hKey], rax
0x140052696  and     dword ptr [rbp+hKey+8], eax
0x140052699  and     [rbp+var_30], rax
0x14005269d  test    r8, r8
0x1400526a0  jz      short loc_1400526A5
0x1400526a2  and     [r8], eax
0x1400526a5  and     [rbp+Buf1], 0
0x1400526aa  and     [rbp+Buf2], 0
0x1400526af  mov     rcx, [rcx+0E0h]; hToken
0x1400526b6  call    cs:__imp_ImpersonateLoggedOnUser
0x1400526bc  test    eax, eax
0x1400526be  setnz   bl
0x1400526c1  mov     [rbp+var_50], bl
0x1400526c4  mov     rax, [rsi+0E8h]
0x1400526cb  mov     rcx, cs:hKey
0x1400526d2  test    rax, rax
0x1400526d5  cmovnz  rcx, rax; hKey
0x1400526d9  and     [rbp+var_48], 0
0x1400526de  lea     rax, [rbp+var_48]
0x1400526e2  mov     [rsp+80h+phkResult], rax; phkResult
0x1400526e7  mov     r9d, 2001Fh; samDesired
0x1400526ed  xor     r8d, r8d; ulOptions
0x1400526f0  mov     rdx, [rsi+0B8h]; lpSubKey
0x1400526f7  call    cs:__imp_RegOpenKeyExW
0x1400526fd  mov     ecx, eax
0x1400526ff  test    eax, eax
0x140052701  jnz     loc_1400527C5
0x140052707  mov     rax, [rbp+var_48]
0x14005270b  mov     [rbp+hKey], rax
0x14005270f  and     dword ptr [rbp+hKey+8], ecx
0x140052712  lea     rdx, aConfigpkgdefca_0
0x140052719  lea     rcx, [rbp+var_48]
0x14005271d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z
0x140052722  lea     r9, [rbp+var_18]
0x140052726  lea     r8, [rbp+Buf1]
0x14005272a  lea     rdx, [rbp+var_48]
0x14005272e  lea     rcx, [rbp+hKey]
0x140052732  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV?$CAutoVectorPtr@E@2@AEAK@Z
0x140052737  mov     r14d, eax
0x14005273a  mov     rdx, [rbp+var_48]
0x14005273e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140052742  or      ecx, 0FFFFFFFFh
0x140052745  lock xadd [rdx+10h], ecx
0x14005274a  sub     ecx, 1
0x14005274d  jg      short loc_14005275C
0x14005274f  lfence
0x140052752  mov     rcx, [rdx]
0x140052755  mov     r8, [rcx]
0x140052758  call    qword ptr [r8+8]
0x14005275c  test    r14d, r14d
0x14005275f  jns     loc_1400527E7
0x140052765  test    rdi, rdi
0x140052768  jz      short loc_140052770
0x14005276a  mov     dword ptr [rdi], 0Dh
0x140052770  mov     dil, 1
0x140052773  test    bl, bl
0x140052775  jz      short loc_14005277E
0x140052777  call    cs:__imp_RevertToSelf
0x14005277d  nop
0x14005277e  mov     rcx, [rbp+Buf2]; void *
0x140052782  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x140052787  mov     rcx, [rbp+Buf1]; void *
0x14005278b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x140052790  mov     rcx, [rbp+hKey]; hKey
0x140052794  test    rcx, rcx
0x140052797  jz      short loc_14005279F
0x140052799  call    cs:__imp_RegCloseKey
0x14005279f  mov     al, dil
0x1400527a2  mov     rcx, [rbp+var_10]
0x1400527a6  xor     rcx, rsp; StackCookie
0x1400527a9  call    __security_check_cookie
0x1400527ae  mov     rbx, [rsp+80h+arg_18]
0x1400527b6  add     rsp, 80h
0x1400527bd  pop     r15
0x1400527bf  pop     r14
0x1400527c1  pop     rdi
0x1400527c2  pop     rsi
0x1400527c3  pop     rbp
0x1400527c4  retn
0x1400527c5  movzx   eax, cx
0x1400527c8  or      eax, 80070000h
0x1400527cd  test    ecx, ecx
0x1400527cf  cmovle  eax, ecx
0x1400527d2  test    eax, eax
0x1400527d4  jns     loc_140052712
0x1400527da  test    rdi, rdi
0x1400527dd  jz      short loc_140052770
0x1400527df  mov     dword ptr [rdi], 10h
0x1400527e5  jmp     short loc_140052770
0x1400527e7  lea     rcx, [r15+20h]
0x1400527eb  lea     r8, [rbp+var_48]
0x1400527ef  lea     rdx, [rbp+Buf2]
0x1400527f3  call    ?ConvertFileDiscoveryListToBinaryBlob@@YAJAEBV?$CAtlList@UDiscoveredFile@@V?$CElementTraits@UDiscoveredFile@@@ATL@@@ATL@@AEAV?$CAutoVectorPtr@E@2@AEAK@Z
0x1400527f8  test    eax, eax
0x1400527fa  jns     short loc_140052810
0x1400527fc  test    rdi, rdi
0x1400527ff  jz      loc_140052770
0x140052805  mov     dword ptr [rdi], 11h
0x14005280b  jmp     loc_140052770
0x140052810  mov     eax, dword ptr [rbp+var_48]
0x140052813  cmp     eax, [rbp+var_18]
0x140052816  jz      short loc_14005282C
0x140052818  test    rdi, rdi
0x14005281b  jz      loc_140052770
0x140052821  mov     dword ptr [rdi], 0Eh
0x140052827  jmp     loc_140052770
0x14005282c  mov     r8, rax; Size
0x14005282f  mov     rdx, [rbp+Buf2]; Buf2
0x140052833  mov     rcx, [rbp+Buf1]; Buf1
0x140052837  call    memcmp_0
0x14005283c  test    eax, eax
0x14005283e  jz      short loc_140052854
0x140052840  test    rdi, rdi
0x140052843  jz      loc_140052770
0x140052849  mov     dword ptr [rdi], 0Fh
0x14005284f  jmp     loc_140052770
0x140052854  mov     rdx, rdi; enum PkgDefMergeReason *
0x140052857  mov     rcx, rsi; this
0x14005285a  call    ?IsConfigCacheValid@CPkgDefCacheNonVolatileBase@@IEAA_NPEAW4PkgDefMergeReason@@@Z
0x14005285f  test    al, al
0x140052861  jz      loc_140052770
0x140052867  test    dword ptr [rsi+8], 100h
0x14005286e  jz      short loc_140052891
0x140052870  test    rdi, rdi
0x140052873  jz      short loc_14005287B
0x140052875  mov     dword ptr [rdi], 6
0x14005287b  xor     r8d, r8d; unsigned __int16 *
0x14005287e  xor     edx, edx; int
0x140052880  lea     rcx, aForcingCacheRe
0x140052887  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z
0x14005288c  jmp     loc_140052770
0x140052891  xor     dil, dil
0x140052894  jmp     loc_140052773
```
