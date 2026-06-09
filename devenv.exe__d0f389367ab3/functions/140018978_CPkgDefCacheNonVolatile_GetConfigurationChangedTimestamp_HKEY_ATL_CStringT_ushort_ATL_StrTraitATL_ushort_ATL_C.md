# CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140018978`
- end: `0x140018adc`
- name: `?GetConfigurationChangedTimestamp@CPkgDefCacheNonVolatile@@IEBA?AU_FILETIME@@PEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001875c`

## callees

- `0x1400088d8`
- `0x1400095f4`
- `0x14000bfa8`
- `0x140018978`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140018abf`
- `ADVAPI32!RegCloseKey` at `0x140018abf`
- `ADVAPI32!RegOpenKeyExW` at `0x1400189e3`
- `ADVAPI32!RegOpenKeyExW` at `0x1400189e3`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400189b9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400189b9`
- `ADVAPI32!RevertToSelf` at `0x140018a2a`
- `ADVAPI32!RevertToSelf` at `0x140018aaf`
- `ADVAPI32!RevertToSelf` at `0x140018a2a`
- `ADVAPI32!RevertToSelf` at `0x140018aaf`

## string_xrefs

- `0x140018a41`: `ConfigurationChanged`
- `0x140018a91`: `Could not find ConfigurationChanged timestamp.`
- `0x140018a1a`: `Could not open key to check ConfigurationChanged timestamp.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(
        __int64 a1,
        __int64 a2,
        HKEY a3,
        LPCWSTR *a4)
{
  HKEY v7; // r14
  bool v8; // bl
  LSTATUS v9; // eax
  HKEY v10; // rdi
  HKEY v11; // rsi
  signed int v12; // edx
  HKEY v13; // rcx
  int RegistryValue; // edi
  HKEY v15; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  HKEY phkResult; // [rsp+98h] [rbp+48h] BYREF

  *(_QWORD *)a2 = 0;
  v18 = 0;
  v7 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v8 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 224));
  phkResult = 0;
  v9 = RegOpenKeyExW(a3, *a4, 0, 0x20019u, &phkResult);
  v10 = 0;
  v11 = 0;
  if ( !v9 )
  {
    v7 = phkResult;
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
    v10 = phkResult;
    v11 = phkResult;
  }
  v12 = (unsigned __int16)v9 | 0x80070000;
  if ( v9 <= 0 )
    v12 = v9;
  if ( v12 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      "ConfigurationChanged");
    RegistryValue = GetRegistryValue(hKey, &phkResult, a2);
    v15 = phkResult - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
    }
    _mm_lfence();
    if ( RegistryValue < 0 )
    {
      CLogger::LogInfo(L"Could not find ConfigurationChanged timestamp.", RegistryValue, 0);
      *(_DWORD *)a2 = 0;
      *(_DWORD *)(a2 + 4) = 0;
    }
    if ( v8 )
      RevertToSelf();
    v13 = hKey[0];
    if ( hKey[0] )
      goto LABEL_17;
  }
  else
  {
    _mm_lfence();
    CLogger::LogInfo(L"Could not open key to check ConfigurationChanged timestamp.", v12, 0);
    if ( v8 )
    {
      RevertToSelf();
      v10 = v11;
    }
    if ( v10 )
    {
      v13 = v7;
LABEL_17:
      RegCloseKey(v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140018978  mov     [rsp-28h+arg_8], rbx
0x14001897d  push    rbp
0x14001897e  push    rsi
0x14001897f  push    rdi
0x140018980  push    r14
0x140018982  push    r15
0x140018984  mov     rbp, rsp
0x140018987  sub     rsp, 50h
0x14001898b  mov     rdi, r9
0x14001898e  mov     rsi, r8
0x140018991  mov     r15, rdx
0x140018994  xor     eax, eax
0x140018996  mov     [rdx], rax
0x140018999  xorps   xmm0, xmm0
0x14001899c  movups  xmmword ptr [rbp+hKey], xmm0
0x1400189a0  mov     [rbp+var_10], rax
0x1400189a4  xor     r14d, r14d
0x1400189a7  mov     [rbp+hKey], r14
0x1400189ab  and     dword ptr [rbp+hKey+8], eax
0x1400189ae  and     [rbp+var_10], rax
0x1400189b2  mov     rcx, [rcx+0E0h]; hToken
0x1400189b9  call    cs:__imp_ImpersonateLoggedOnUser
0x1400189bf  test    eax, eax
0x1400189c1  setnz   bl
0x1400189c4  mov     [rbp+arg_0], bl
0x1400189c7  and     [rbp+arg_18], r14
0x1400189cb  lea     rax, [rbp+arg_18]
0x1400189cf  mov     [rsp+50h+phkResult], rax; phkResult
0x1400189d4  mov     r9d, 20019h; samDesired
0x1400189da  xor     r8d, r8d; ulOptions
0x1400189dd  mov     rdx, [rdi]; lpSubKey
0x1400189e0  mov     rcx, rsi; hKey
0x1400189e3  call    cs:__imp_RegOpenKeyExW
0x1400189e9  xor     edi, edi
0x1400189eb  xor     esi, esi
0x1400189ed  test    eax, eax
0x1400189ef  jnz     short loc_140018A02
0x1400189f1  mov     r14, [rbp+arg_18]
0x1400189f5  mov     [rbp+hKey], r14
0x1400189f9  and     dword ptr [rbp+hKey+8], eax
0x1400189fc  mov     rdi, r14
0x1400189ff  mov     rsi, r14
0x140018a02  movzx   edx, ax
0x140018a05  or      edx, 80070000h
0x140018a0b  test    eax, eax
0x140018a0d  cmovle  edx, eax; int
0x140018a10  test    edx, edx
0x140018a12  jns     short loc_140018A41
0x140018a14  lfence
0x140018a17  xor     r8d, r8d; unsigned __int16 *
0x140018a1a  lea     rcx, aCouldNotOpenKe; "Could not open key to check Configurati"...
0x140018a21  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140018a26  test    bl, bl
0x140018a28  jz      short loc_140018A33
0x140018a2a  call    cs:__imp_RevertToSelf
0x140018a30  mov     rdi, rsi
0x140018a33  test    rdi, rdi
0x140018a36  jz      loc_140018AC5
0x140018a3c  mov     rcx, r14
0x140018a3f  jmp     short loc_140018ABF
0x140018a41  lea     rdx, aConfigurationc; "ConfigurationChanged"
0x140018a48  lea     rcx, [rbp+arg_18]
0x140018a4c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x140018a51  mov     r8, r15
0x140018a54  lea     rdx, [rbp+arg_18]
0x140018a58  lea     rcx, [rbp+hKey]
0x140018a5c  call    ?GetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAU_FILETIME@@@Z; GetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_FILETIME &)
0x140018a61  mov     edi, eax
0x140018a63  mov     rdx, [rbp+arg_18]
0x140018a67  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140018a6b  or      ecx, 0FFFFFFFFh
0x140018a6e  lock xadd [rdx+10h], ecx
0x140018a73  sub     ecx, 1
0x140018a76  jg      short loc_140018A85
0x140018a78  lfence
0x140018a7b  mov     rcx, [rdx]
0x140018a7e  mov     r8, [rcx]
0x140018a81  call    qword ptr [r8+8]
0x140018a85  test    edi, edi
0x140018a87  jns     short loc_140018AA8
0x140018a89  lfence
0x140018a8c  xor     r8d, r8d; unsigned __int16 *
0x140018a8f  mov     edx, edi; int
0x140018a91  lea     rcx, aCouldNotFindCo; "Could not find ConfigurationChanged tim"...
0x140018a98  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140018a9d  and     dword ptr [r15], 0
0x140018aa1  and     dword ptr [r15+4], 0
0x140018aa6  jmp     short loc_140018AAB
0x140018aa8  lfence
0x140018aab  test    bl, bl
0x140018aad  jz      short loc_140018AB6
0x140018aaf  call    cs:__imp_RevertToSelf
0x140018ab5  nop
0x140018ab6  mov     rcx, [rbp+hKey]; hKey
0x140018aba  test    rcx, rcx
0x140018abd  jz      short loc_140018AC5
0x140018abf  call    cs:__imp_RegCloseKey
0x140018ac5  mov     rax, r15
0x140018ac8  mov     rbx, [rsp+50h+arg_8]
0x140018ad0  add     rsp, 50h
0x140018ad4  pop     r15
0x140018ad6  pop     r14
0x140018ad8  pop     rdi
0x140018ad9  pop     rsi
0x140018ada  pop     rbp
0x140018adb  retn
```
