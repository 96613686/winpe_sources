# CPkgDefCache::CheckRegistryScanOverrides(void)

- ea: `0x1400473a0`
- end: `0x140047551`
- name: `?CheckRegistryScanOverrides@CPkgDefCache@@IEAAXXZ`
- size: `433`
- prototype: `void __fastcall(CPkgDefCache *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140047554`
- `0x14004bd64`

## callees

- `0x140001020`
- `0x140003160`
- `0x14000a670`
- `0x1400473a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004751f`
- `ADVAPI32!RegCloseKey` at `0x14004751f`
- `ADVAPI32!RegOpenKeyExW` at `0x14004743a`
- `ADVAPI32!RegOpenKeyExW` at `0x14004743a`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400473e0`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400473e0`
- `ADVAPI32!RevertToSelf` at `0x14004752a`
- `ADVAPI32!RevertToSelf` at `0x14004752a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPkgDefCache::CheckRegistryScanOverrides(CPkgDefCache *this)
{
  _DWORD *v2; // rdi
  bool v3; // bl
  HKEY v4; // rsi
  HKEY v5; // rcx
  bool v7; // si
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // [rsp+38h] [rbp-38h] BYREF
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h]
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF

  v2 = (_DWORD *)((char *)this + 48);
  if ( !*((_DWORD *)this + 12) )
  {
    *v2 = 3;
    v3 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
    v12 = 0;
    v4 = 0;
    v11 = 0u;
    v5 = hKey;
    if ( *((_QWORD *)this + 29) )
      v5 = (HKEY)*((_QWORD *)this + 29);
    phkResult = 0;
    if ( !RegOpenKeyExW(v5, *((LPCWSTR *)this + 23), 0, 0x20019u, &phkResult) )
    {
      *(_QWORD *)&v11 = phkResult;
      DWORD2(v11) = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v10,
        L"RegScanLevel");
      v7 = (int)GetRegistryValue(&v11, &v10, v2) < 0 || *v2 < 3u;
      v8 = (_QWORD *)(v10 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
      }
      if ( v7 )
        *v2 = 3;
      LODWORD(phkResult) = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v10,
        L"RegScanLargeNodes");
      GetRegistryValue(&v11, &v10, &phkResult);
      v9 = (_QWORD *)(v10 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
      }
      v4 = (HKEY)v11;
    }
    if ( v4 )
      RegCloseKey(v4);
    if ( v3 )
      RevertToSelf();
  }
}

```

## disassembly

```asm
0x1400473a0  mov     [rsp-18h+arg_8], rbx
0x1400473a5  mov     [rsp-18h+arg_10], rsi
0x1400473aa  push    rbp
0x1400473ab  push    rdi
0x1400473ac  push    r14
0x1400473ae  mov     rbp, rsp
0x1400473b1  sub     rsp, 70h
0x1400473b5  mov     rax, cs:__security_cookie
0x1400473bc  xor     rax, rsp
0x1400473bf  mov     [rbp+var_10], rax
0x1400473c3  mov     r14, rcx
0x1400473c6  lea     rdi, [rcx+30h]
0x1400473ca  cmp     dword ptr [rdi], 0
0x1400473cd  ja      loc_140047530
0x1400473d3  mov     dword ptr [rdi], 3
0x1400473d9  mov     rcx, [rcx+0E0h]; hToken
0x1400473e0  call    cs:__imp_ImpersonateLoggedOnUser
0x1400473e6  test    eax, eax
0x1400473e8  setnz   bl
0x1400473eb  mov     [rbp+var_40], bl
0x1400473ee  xorps   xmm0, xmm0
0x1400473f1  xor     eax, eax
0x1400473f3  movups  [rbp+var_30], xmm0
0x1400473f7  mov     [rbp+var_20], rax
0x1400473fb  xor     esi, esi
0x1400473fd  mov     qword ptr [rbp+var_30], rsi
0x140047401  and     dword ptr [rbp+var_30+8], eax
0x140047404  and     [rbp+var_20], rax
0x140047408  mov     rax, [r14+0E8h]
0x14004740f  mov     rcx, cs:hKey
0x140047416  test    rax, rax
0x140047419  cmovnz  rcx, rax; hKey
0x14004741d  and     [rbp+var_18], rsi
0x140047421  lea     rax, [rbp+var_18]
0x140047425  mov     [rsp+70h+phkResult], rax; phkResult
0x14004742a  mov     r9d, 20019h; samDesired
0x140047430  xor     r8d, r8d; ulOptions
0x140047433  mov     rdx, [r14+0B8h]; lpSubKey
0x14004743a  call    cs:__imp_RegOpenKeyExW
0x140047440  mov     ecx, eax
0x140047442  test    eax, eax
0x140047444  jnz     short loc_140047453
0x140047446  mov     rax, [rbp+var_18]
0x14004744a  mov     qword ptr [rbp+var_30], rax
0x14004744e  and     dword ptr [rbp+var_30+8], ecx
0x140047451  jmp     short loc_140047468
0x140047453  movzx   eax, cx
0x140047456  or      eax, 80070000h
0x14004745b  test    ecx, ecx
0x14004745d  cmovle  eax, ecx
0x140047460  test    eax, eax
0x140047462  js      loc_140047517
0x140047468  lea     rdx, aRegscanlevel; "RegScanLevel"
0x14004746f  lea     rcx, [rbp+var_38]
0x140047473  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140047478  mov     r8, rdi
0x14004747b  lea     rdx, [rbp+var_38]
0x14004747f  lea     rcx, [rbp+var_30]
0x140047483  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x140047488  test    eax, eax
0x14004748a  js      short loc_140047496
0x14004748c  cmp     dword ptr [rdi], 3
0x14004748f  jb      short loc_140047496
0x140047491  xor     sil, sil
0x140047494  jmp     short loc_140047499
0x140047496  mov     sil, 1
0x140047499  mov     rdx, [rbp+var_38]
0x14004749d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400474a1  or      r14d, 0FFFFFFFFh
0x1400474a5  mov     eax, r14d
0x1400474a8  lock xadd [rdx+10h], eax
0x1400474ad  add     eax, r14d
0x1400474b0  test    eax, eax
0x1400474b2  jg      short loc_1400474C0
0x1400474b4  lfence
0x1400474b7  mov     rcx, [rdx]
0x1400474ba  mov     rax, [rcx]
0x1400474bd  call    qword ptr [rax+8]
0x1400474c0  test    sil, sil
0x1400474c3  jz      short loc_1400474CB
0x1400474c5  mov     dword ptr [rdi], 3
0x1400474cb  and     dword ptr [rbp+var_18], 0
0x1400474cf  lea     rdx, aRegscanlargeno; "RegScanLargeNodes"
0x1400474d6  lea     rcx, [rbp+var_38]
0x1400474da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400474df  lea     r8, [rbp+var_18]
0x1400474e3  lea     rdx, [rbp+var_38]
0x1400474e7  lea     rcx, [rbp+var_30]
0x1400474eb  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x1400474f0  mov     rdx, [rbp+var_38]
0x1400474f4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400474f8  mov     eax, r14d
0x1400474fb  lock xadd [rdx+10h], eax
0x140047500  add     eax, r14d
0x140047503  test    eax, eax
0x140047505  jg      short loc_140047513
0x140047507  lfence
0x14004750a  mov     rcx, [rdx]
0x14004750d  mov     rax, [rcx]
0x140047510  call    qword ptr [rax+8]
0x140047513  mov     rsi, qword ptr [rbp+var_30]
0x140047517  test    rsi, rsi
0x14004751a  jz      short loc_140047526
0x14004751c  mov     rcx, rsi; hKey
0x14004751f  call    cs:__imp_RegCloseKey
0x140047525  nop
0x140047526  test    bl, bl
0x140047528  jz      short loc_140047530
0x14004752a  call    cs:__imp_RevertToSelf
0x140047530  mov     rcx, [rbp+var_10]
0x140047534  xor     rcx, rsp; StackCookie
0x140047537  call    __security_check_cookie
0x14004753c  lea     r11, [rsp+70h+var_s0]
0x140047541  mov     rbx, [r11+28h]
0x140047545  mov     rsi, [r11+30h]
0x140047549  mov     rsp, r11
0x14004754c  pop     r14
0x14004754e  pop     rdi
0x14004754f  pop     rbp
0x140047550  retn
```
