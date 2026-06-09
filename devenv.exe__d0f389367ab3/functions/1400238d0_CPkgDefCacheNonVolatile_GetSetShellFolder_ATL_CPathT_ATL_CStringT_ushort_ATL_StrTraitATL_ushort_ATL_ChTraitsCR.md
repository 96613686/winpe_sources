# CPkgDefCacheNonVolatile::GetSetShellFolder(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)

- ea: `0x1400238d0`
- end: `0x140023b75`
- name: `?GetSetShellFolder@CPkgDefCacheNonVolatile@@UEAAAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@AEBV23@@Z`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x14001c8f8`
- `0x140022d80`
- `0x1400238d0`
- `0x140023b80`
- `0x14002a644`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140023b44`
- `ADVAPI32!RegCloseKey` at `0x140023b44`
- `ADVAPI32!RegOpenKeyExW` at `0x140023981`
- `ADVAPI32!RegOpenKeyExW` at `0x140023981`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14002394c`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14002394c`
- `ADVAPI32!RevertToSelf` at `0x140023af3`
- `ADVAPI32!RevertToSelf` at `0x140023af3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140023a1d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140023a1d`

## string_xrefs

- `0x14002399f`: `InstallDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPkgDefCacheNonVolatile::GetSetShellFolder(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r14
  struct ATL::IAtlStringMgr *Instance; // rax
  wchar_t *v6; // rbx
  wchar_t *v7; // rdi
  bool v8; // si
  LSTATUS v9; // eax
  int RegistryValue; // ebx
  HKEY v11; // rdx
  int v12; // ebx
  HKEY v13; // rdx
  int CanonicalName; // eax
  HKEY v15; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+48h] [rbp-8h]
  wchar_t *String2; // [rsp+A0h] [rbp+50h] BYREF
  wchar_t *String1; // [rsp+A8h] [rbp+58h] BYREF

  v4 = a1 + 112;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 112) - 16LL) )
    return v4;
  *(_OWORD *)hKey = 0;
  v19 = 0;
  hKey[0] = 0;
  LODWORD(hKey[1]) = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v6 = (wchar_t *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  String2 = v6;
  v7 = (wchar_t *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 24LL) + 24);
  String1 = v7;
  v8 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 224));
  phkResult = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a1 + 136), 0, 0x20019u, &phkResult);
  if ( v9 )
  {
    if ( v9 < 0 )
      goto LABEL_20;
  }
  else
  {
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    L"InstallDir");
  RegistryValue = GetRegistryValue(hKey, &phkResult, &String2);
  v11 = phkResult - 6;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
  if ( RegistryValue < 0 || (int)GetCanonicalName(&String2) < 0 )
    goto LABEL_19;
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddBackslash(&String1);
  v6 = String2;
  if ( !String2 )
    ATL::AtlThrowImpl(-2147467259);
  v7 = String1;
  if ( _wcsicmp(String1, String2) )
    goto LABEL_20;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    L"ShellFolder");
  v12 = GetRegistryValue(hKey, &phkResult, &String2);
  v13 = phkResult - 6;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  }
  if ( v12 < 0 )
  {
LABEL_19:
    v6 = String2;
  }
  else
  {
    v6 = String2;
    if ( *((_DWORD *)String2 - 4) )
    {
      CanonicalName = GetCanonicalName(&String2);
      v6 = String2;
      if ( CanonicalName >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &phkResult,
          String2);
        ATL::CSimpleStringT<unsigned short,0>::operator=(v4, &phkResult);
        v15 = phkResult - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
        }
        goto LABEL_21;
      }
    }
  }
LABEL_20:
  CPkgDefCache::GetSetShellFolder(a1, a2);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddBackslash(v4);
LABEL_21:
  if ( v8 )
    RevertToSelf();
  if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v6 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v4;
}

```

## disassembly

```asm
0x1400238d0  push    rbp
0x1400238d2  push    rbx
0x1400238d3  push    rsi
0x1400238d4  push    rdi
0x1400238d5  push    r12
0x1400238d7  push    r14
0x1400238d9  push    r15
0x1400238db  mov     rbp, rsp
0x1400238de  sub     rsp, 50h
0x1400238e2  mov     r12, rdx
0x1400238e5  mov     r15, rcx
0x1400238e8  lea     r14, [rcx+70h]
0x1400238ec  mov     rax, [r14]
0x1400238ef  cmp     dword ptr [rax-10h], 0
0x1400238f3  jnz     loc_140023B4A
0x1400238f9  xorps   xmm0, xmm0
0x1400238fc  xor     eax, eax
0x1400238fe  movups  xmmword ptr [rbp+hKey], xmm0
0x140023902  mov     [rbp+var_8], rax
0x140023906  and     [rbp+hKey], rax
0x14002390a  and     dword ptr [rbp+hKey+8], eax
0x14002390d  and     [rbp+var_8], rax
0x140023911  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140023916  mov     rcx, rax
0x140023919  test    rax, rax
0x14002391c  jz      loc_140023B6A
0x140023922  mov     rax, [rax]
0x140023925  call    qword ptr [rax+18h]
0x140023928  lea     rbx, [rax+18h]
0x14002392c  mov     [rbp+String2], rbx
0x140023930  mov     rcx, [r12]
0x140023934  sub     rcx, 18h
0x140023938  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14002393d  lea     rdi, [rax+18h]
0x140023941  mov     [rbp+String1], rdi
0x140023945  mov     rcx, [r15+0E0h]; hToken
0x14002394c  call    cs:__imp_ImpersonateLoggedOnUser
0x140023952  test    eax, eax
0x140023954  setnz   sil
0x140023958  mov     [rbp+arg_0], sil
0x14002395c  and     [rbp+var_20], 0
0x140023961  lea     rax, [rbp+var_20]
0x140023965  mov     [rsp+50h+phkResult], rax; phkResult
0x14002396a  mov     r9d, 20019h; samDesired
0x140023970  xor     r8d, r8d; ulOptions
0x140023973  mov     rdx, [r15+88h]; lpSubKey
0x14002397a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023981  call    cs:__imp_RegOpenKeyExW
0x140023987  test    eax, eax
0x140023989  jnz     short loc_140023999
0x14002398b  mov     rax, [rbp+var_20]
0x14002398f  mov     [rbp+hKey], rax
0x140023993  and     dword ptr [rbp+hKey+8], 0
0x140023997  jmp     short loc_14002399F
0x140023999  js      loc_140023AD7
0x14002399f  lea     rdx, aInstalldir; "InstallDir"
0x1400239a6  lea     rcx, [rbp+var_20]
0x1400239aa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400239af  lea     r8, [rbp+String2]
0x1400239b3  lea     rdx, [rbp+var_20]
0x1400239b7  lea     rcx, [rbp+hKey]
0x1400239bb  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400239c0  mov     ebx, eax
0x1400239c2  mov     rdx, [rbp+var_20]
0x1400239c6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400239ca  or      ecx, 0FFFFFFFFh
0x1400239cd  lock xadd [rdx+10h], ecx
0x1400239d2  sub     ecx, 1
0x1400239d5  jg      short loc_1400239E4
0x1400239d7  lfence
0x1400239da  mov     rcx, [rdx]
0x1400239dd  mov     r8, [rcx]
0x1400239e0  call    qword ptr [r8+8]
0x1400239e4  test    ebx, ebx
0x1400239e6  js      loc_140023AD3
0x1400239ec  lea     rcx, [rbp+String2]
0x1400239f0  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400239f5  test    eax, eax
0x1400239f7  js      loc_140023AD3
0x1400239fd  lea     rcx, [rbp+String1]
0x140023a01  call    ?AddBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddBackslash(void)
0x140023a06  mov     rbx, [rbp+String2]
0x140023a0a  test    rbx, rbx
0x140023a0d  jz      loc_140023B5C
0x140023a13  mov     rdx, rbx; String2
0x140023a16  mov     rdi, [rbp+String1]
0x140023a1a  mov     rcx, rdi; String1
0x140023a1d  call    cs:__imp__wcsicmp
0x140023a23  test    eax, eax
0x140023a25  jnz     loc_140023AD7
0x140023a2b  lea     rdx, aShellfolder; "ShellFolder"
0x140023a32  lea     rcx, [rbp+var_20]
0x140023a36  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140023a3b  nop
0x140023a3c  lea     r8, [rbp+String2]
0x140023a40  lea     rdx, [rbp+var_20]
0x140023a44  lea     rcx, [rbp+hKey]
0x140023a48  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140023a4d  mov     ebx, eax
0x140023a4f  mov     rdx, [rbp+var_20]
0x140023a53  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140023a57  or      ecx, 0FFFFFFFFh
0x140023a5a  lock xadd [rdx+10h], ecx
0x140023a5f  sub     ecx, 1
0x140023a62  jg      short loc_140023A71
0x140023a64  lfence
0x140023a67  mov     rcx, [rdx]
0x140023a6a  mov     r8, [rcx]
0x140023a6d  call    qword ptr [r8+8]
0x140023a71  test    ebx, ebx
0x140023a73  js      short loc_140023AD3
0x140023a75  mov     rbx, [rbp+String2]
0x140023a79  cmp     dword ptr [rbx-10h], 0
0x140023a7d  jz      short loc_140023AD7
0x140023a7f  lea     rcx, [rbp+String2]
0x140023a83  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x140023a88  mov     rbx, [rbp+String2]
0x140023a8c  test    eax, eax
0x140023a8e  js      short loc_140023AD7
0x140023a90  mov     rdx, rbx
0x140023a93  lea     rcx, [rbp+var_20]
0x140023a97  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140023a9c  nop
0x140023a9d  lea     rdx, [rbp+var_20]
0x140023aa1  mov     rcx, r14
0x140023aa4  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140023aa9  nop
0x140023aaa  mov     rdx, [rbp+var_20]
0x140023aae  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140023ab2  or      r15d, 0FFFFFFFFh
0x140023ab6  mov     eax, r15d
0x140023ab9  lock xadd [rdx+10h], eax
0x140023abe  add     eax, r15d
0x140023ac1  test    eax, eax
0x140023ac3  jg      short loc_140023AEE
0x140023ac5  lfence
0x140023ac8  mov     rcx, [rdx]
0x140023acb  mov     rax, [rcx]
0x140023ace  call    qword ptr [rax+8]
0x140023ad1  jmp     short loc_140023AEE
0x140023ad3  mov     rbx, [rbp+String2]
0x140023ad7  mov     rdx, r12
0x140023ada  mov     rcx, r15
0x140023add  call    ?GetSetShellFolder@CPkgDefCache@@UEAAAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@AEBV23@@Z; CPkgDefCache::GetSetShellFolder(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)
0x140023ae2  mov     rcx, r14
0x140023ae5  call    ?AddBackslash@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddBackslash(void)
0x140023aea  or      r15d, 0FFFFFFFFh
0x140023aee  test    sil, sil
0x140023af1  jz      short loc_140023AFA
0x140023af3  call    cs:__imp_RevertToSelf
0x140023af9  nop
0x140023afa  lea     rdx, [rdi-18h]
0x140023afe  mov     eax, r15d
0x140023b01  lock xadd [rdx+10h], eax
0x140023b06  add     eax, r15d
0x140023b09  test    eax, eax
0x140023b0b  jg      short loc_140023B1A
0x140023b0d  lfence
0x140023b10  mov     rcx, [rdx]
0x140023b13  mov     rax, [rcx]
0x140023b16  call    qword ptr [rax+8]
0x140023b19  nop
0x140023b1a  lea     rdx, [rbx-18h]
0x140023b1e  mov     eax, r15d
0x140023b21  lock xadd [rdx+10h], eax
0x140023b26  add     eax, r15d
0x140023b29  test    eax, eax
0x140023b2b  jg      short loc_140023B3B
0x140023b2d  lfence
0x140023b30  mov     rcx, [rdx]
0x140023b33  mov     r8, [rcx]
0x140023b36  call    qword ptr [r8+8]
0x140023b3a  nop
0x140023b3b  mov     rcx, [rbp+hKey]; hKey
0x140023b3f  test    rcx, rcx
0x140023b42  jz      short loc_140023B4A
0x140023b44  call    cs:__imp_RegCloseKey
0x140023b4a  mov     rax, r14
0x140023b4d  add     rsp, 50h
0x140023b51  pop     r15
0x140023b53  pop     r14
0x140023b55  pop     r12
0x140023b57  pop     rdi
0x140023b58  pop     rsi
0x140023b59  pop     rbx
0x140023b5a  pop     rbp
0x140023b5b  retn
0x140023b5c  mov     ecx, 80004005h; int
0x140023b61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140023b67  jmp     short $+2
0x140023b69  nop
0x140023b6a  mov     ecx, 80004005h; int
0x140023b6f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
