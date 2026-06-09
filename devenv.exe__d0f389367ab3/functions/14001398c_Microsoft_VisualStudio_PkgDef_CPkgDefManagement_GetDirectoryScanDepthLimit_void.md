# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetDirectoryScanDepthLimit(void)

- ea: `0x14001398c`
- end: `0x140013ad7`
- name: `?GetDirectoryScanDepthLimit@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAHXZ`
- size: `331`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140017580`

## callees

- `0x140001020`
- `0x140003160`
- `0x14000a670`
- `0x14001398c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140013aad`
- `ADVAPI32!RegCloseKey` at `0x140013aad`
- `ADVAPI32!RegOpenKeyExW` at `0x140013a04`
- `ADVAPI32!RegOpenKeyExW` at `0x140013a04`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400139d5`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400139d5`
- `ADVAPI32!RevertToSelf` at `0x140013a9e`
- `ADVAPI32!RevertToSelf` at `0x140013a9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetDirectoryScanDepthLimit(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  HKEY v2; // rsi
  bool v3; // bl
  LSTATUS v4; // ecx
  signed int v5; // eax
  int RegistryValue; // eax
  signed int v7; // edi
  bool v8; // di
  _QWORD *v9; // rdx
  bool v10; // zf
  unsigned int v11; // edi
  HKEY hKey[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF

  v14 = 0;
  v2 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v3 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  phkResult = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 14), 0, 0x20019u, &phkResult);
  if ( v4 )
  {
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    if ( v5 < 0 )
      goto LABEL_11;
  }
  else
  {
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
  }
  LODWORD(phkResult) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v15,
    L"AssetScanDepth");
  RegistryValue = GetRegistryValue(hKey, &v15, &phkResult);
  v7 = (unsigned __int16)RegistryValue | 0x80070000;
  if ( RegistryValue <= 0 )
    v7 = RegistryValue;
  v8 = v7 >= 0;
  v9 = (_QWORD *)(v15 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  }
  v2 = hKey[0];
  v10 = !v8;
  v11 = (unsigned int)phkResult;
  if ( v10 )
LABEL_11:
    v11 = 4;
  if ( v3 )
    RevertToSelf();
  if ( v2 )
    RegCloseKey(v2);
  return v11;
}

```

## disassembly

```asm
0x14001398c  mov     [rsp-8+arg_8], rbx
0x140013991  mov     [rsp-8+arg_10], rsi
0x140013996  mov     [rsp-8+arg_18], rdi
0x14001399b  push    rbp
0x14001399c  mov     rbp, rsp
0x14001399f  sub     rsp, 70h
0x1400139a3  mov     rax, cs:__security_cookie
0x1400139aa  xor     rax, rsp
0x1400139ad  mov     [rbp+var_10], rax
0x1400139b1  mov     rdi, rcx
0x1400139b4  xorps   xmm0, xmm0
0x1400139b7  xor     eax, eax
0x1400139b9  movups  xmmword ptr [rbp+hKey], xmm0
0x1400139bd  mov     [rbp+var_28], rax
0x1400139c1  xor     esi, esi
0x1400139c3  mov     [rbp+hKey], rsi
0x1400139c7  and     dword ptr [rbp+hKey+8], eax
0x1400139ca  and     [rbp+var_28], rax
0x1400139ce  mov     rcx, [rcx+0C0h]; hToken
0x1400139d5  call    cs:__imp_ImpersonateLoggedOnUser
0x1400139db  test    eax, eax
0x1400139dd  setnz   bl
0x1400139e0  mov     [rbp+var_40], bl
0x1400139e3  and     [rbp+var_18], rsi
0x1400139e7  lea     rax, [rbp+var_18]
0x1400139eb  mov     [rsp+70h+phkResult], rax; phkResult
0x1400139f0  mov     r9d, 20019h; samDesired
0x1400139f6  xor     r8d, r8d; ulOptions
0x1400139f9  mov     rdx, [rdi+70h]; lpSubKey
0x1400139fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140013a04  call    cs:__imp_RegOpenKeyExW
0x140013a0a  mov     ecx, eax
0x140013a0c  test    eax, eax
0x140013a0e  jnz     short loc_140013A1D
0x140013a10  mov     rax, [rbp+var_18]
0x140013a14  mov     [rbp+hKey], rax
0x140013a18  and     dword ptr [rbp+hKey+8], ecx
0x140013a1b  jmp     short loc_140013A2E
0x140013a1d  movzx   eax, cx
0x140013a20  or      eax, 80070000h
0x140013a25  test    ecx, ecx
0x140013a27  cmovle  eax, ecx
0x140013a2a  test    eax, eax
0x140013a2c  js      short loc_140013A95
0x140013a2e  and     dword ptr [rbp+var_18], 0
0x140013a32  lea     rdx, aAssetscandepth; "AssetScanDepth"
0x140013a39  lea     rcx, [rbp+var_20]
0x140013a3d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140013a42  lea     r8, [rbp+var_18]
0x140013a46  lea     rdx, [rbp+var_20]
0x140013a4a  lea     rcx, [rbp+hKey]
0x140013a4e  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x140013a53  movzx   edi, ax
0x140013a56  or      edi, 80070000h
0x140013a5c  test    eax, eax
0x140013a5e  cmovle  edi, eax
0x140013a61  shr     edi, 1Fh
0x140013a64  xor     dil, 1
0x140013a68  mov     rdx, [rbp+var_20]
0x140013a6c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140013a70  or      eax, 0FFFFFFFFh
0x140013a73  lock xadd [rdx+10h], eax
0x140013a78  sub     eax, 1
0x140013a7b  jg      short loc_140013A89
0x140013a7d  lfence
0x140013a80  mov     rcx, [rdx]
0x140013a83  mov     rax, [rcx]
0x140013a86  call    qword ptr [rax+8]
0x140013a89  mov     rsi, [rbp+hKey]
0x140013a8d  test    dil, dil
0x140013a90  mov     edi, dword ptr [rbp+var_18]
0x140013a93  jnz     short loc_140013A9A
0x140013a95  mov     edi, 4
0x140013a9a  test    bl, bl
0x140013a9c  jz      short loc_140013AA5
0x140013a9e  call    cs:__imp_RevertToSelf
0x140013aa4  nop
0x140013aa5  test    rsi, rsi
0x140013aa8  jz      short loc_140013AB3
0x140013aaa  mov     rcx, rsi; hKey
0x140013aad  call    cs:__imp_RegCloseKey
0x140013ab3  mov     eax, edi
0x140013ab5  mov     rcx, [rbp+var_10]
0x140013ab9  xor     rcx, rsp; StackCookie
0x140013abc  call    __security_check_cookie
0x140013ac1  lea     r11, [rsp+70h+var_s0]
0x140013ac6  mov     rbx, [r11+18h]
0x140013aca  mov     rsi, [r11+20h]
0x140013ace  mov     rdi, [r11+28h]
0x140013ad2  mov     rsp, r11
0x140013ad5  pop     rbp
0x140013ad6  retn
```
