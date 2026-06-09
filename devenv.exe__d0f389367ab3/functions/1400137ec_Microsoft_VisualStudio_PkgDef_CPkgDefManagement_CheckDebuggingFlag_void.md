# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::CheckDebuggingFlag(void)

- ea: `0x1400137ec`
- end: `0x140013989`
- name: `?CheckDebuggingFlag@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAXXZ`
- size: `413`
- prototype: `void __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001d17c`

## callees

- `0x140001020`
- `0x140003160`
- `0x14000a670`
- `0x1400137ec`
- `0x14001c380`
- `0x1400464b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140013962`
- `ADVAPI32!RegCloseKey` at `0x140013962`
- `ADVAPI32!RegOpenKeyExW` at `0x140013862`
- `ADVAPI32!RegOpenKeyExW` at `0x140013862`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140013833`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140013833`
- `ADVAPI32!RevertToSelf` at `0x140013953`
- `ADVAPI32!RevertToSelf` at `0x140013953`
- `KERNEL32!GetCurrentThreadId` at `0x140013942`
- `KERNEL32!GetCurrentThreadId` at `0x140013942`

## string_xrefs

- `0x140013894`: `DisableCacheCheck`
- `0x1400138f6`: `DisableCacheCheck`
- `0x140013910`: `Turning off cache check based on HKLM registry setting`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::CheckDebuggingFlag(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  HKEY v2; // rdi
  bool v3; // bl
  int RegistryValue; // eax
  signed int v6; // edi
  bool v7; // di
  _QWORD *v8; // rdx
  const unsigned __int16 **v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // [rsp+38h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+50h] [rbp-20h]
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF

  v13 = 0;
  v2 = 0;
  v12 = 0u;
  v3 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 14), 0, 0x20019u, &phkResult) )
  {
    *(_QWORD *)&v12 = phkResult;
    DWORD2(v12) = 0;
    LODWORD(phkResult) = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v11,
      L"DisableCacheCheck");
    RegistryValue = GetRegistryValue(&v12, &v11, &phkResult);
    v6 = (unsigned __int16)RegistryValue | 0x80070000;
    if ( RegistryValue <= 0 )
      v6 = RegistryValue;
    v7 = v6 >= 0;
    v8 = (_QWORD *)(v11 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    }
    if ( v7 && (_DWORD)phkResult )
    {
      v9 = (const unsigned __int16 **)ATL::operator+(&v11, (char *)this + 112, L"DisableCacheCheck");
      CLogger::LogWarn(L"Turning off cache check based on HKLM registry setting", 0, *v9);
      v10 = (_QWORD *)(v11 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
      }
      *((_DWORD *)this + 15) |= 4u;
      *((_DWORD *)this + 16) = GetCurrentThreadId();
    }
    v2 = (HKEY)v12;
  }
  if ( v3 )
    RevertToSelf();
  if ( v2 )
    RegCloseKey(v2);
}

```

## disassembly

```asm
0x1400137ec  mov     [rsp-18h+arg_8], rbx
0x1400137f1  mov     [rsp-18h+arg_10], rsi
0x1400137f6  push    rbp
0x1400137f7  push    rdi
0x1400137f8  push    r14
0x1400137fa  mov     rbp, rsp
0x1400137fd  sub     rsp, 70h
0x140013801  mov     rax, cs:__security_cookie
0x140013808  xor     rax, rsp
0x14001380b  mov     [rbp+var_10], rax
0x14001380f  mov     rsi, rcx
0x140013812  xorps   xmm0, xmm0
0x140013815  xor     eax, eax
0x140013817  movups  [rbp+var_30], xmm0
0x14001381b  mov     [rbp+var_20], rax
0x14001381f  xor     edi, edi
0x140013821  mov     qword ptr [rbp+var_30], rdi
0x140013825  and     dword ptr [rbp+var_30+8], eax
0x140013828  and     [rbp+var_20], rax
0x14001382c  mov     rcx, [rcx+0C0h]; hToken
0x140013833  call    cs:__imp_ImpersonateLoggedOnUser
0x140013839  test    eax, eax
0x14001383b  setnz   bl
0x14001383e  mov     [rbp+var_40], bl
0x140013841  and     [rbp+var_18], rdi
0x140013845  lea     rax, [rbp+var_18]
0x140013849  mov     [rsp+70h+phkResult], rax; phkResult
0x14001384e  mov     r9d, 20019h; samDesired
0x140013854  xor     r8d, r8d; ulOptions
0x140013857  mov     rdx, [rsi+70h]; lpSubKey
0x14001385b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140013862  call    cs:__imp_RegOpenKeyExW
0x140013868  mov     ecx, eax
0x14001386a  test    eax, eax
0x14001386c  jnz     short loc_14001387B
0x14001386e  mov     rax, [rbp+var_18]
0x140013872  mov     qword ptr [rbp+var_30], rax
0x140013876  and     dword ptr [rbp+var_30+8], ecx
0x140013879  jmp     short loc_140013890
0x14001387b  movzx   eax, cx
0x14001387e  or      eax, 80070000h
0x140013883  test    ecx, ecx
0x140013885  cmovle  eax, ecx
0x140013888  test    eax, eax
0x14001388a  js      loc_14001394F
0x140013890  and     dword ptr [rbp+var_18], 0
0x140013894  lea     rdx, aDisablecachech; "DisableCacheCheck"
0x14001389b  lea     rcx, [rbp+var_38]
0x14001389f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400138a4  lea     r8, [rbp+var_18]
0x1400138a8  lea     rdx, [rbp+var_38]
0x1400138ac  lea     rcx, [rbp+var_30]
0x1400138b0  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x1400138b5  movzx   edi, ax
0x1400138b8  or      edi, 80070000h
0x1400138be  test    eax, eax
0x1400138c0  cmovle  edi, eax
0x1400138c3  shr     edi, 1Fh
0x1400138c6  xor     dil, 1
0x1400138ca  mov     rdx, [rbp+var_38]
0x1400138ce  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400138d2  or      eax, 0FFFFFFFFh
0x1400138d5  lock xadd [rdx+10h], eax
0x1400138da  sub     eax, 1
0x1400138dd  jg      short loc_1400138EB
0x1400138df  lfence
0x1400138e2  mov     rcx, [rdx]
0x1400138e5  mov     rax, [rcx]
0x1400138e8  call    qword ptr [rax+8]
0x1400138eb  test    dil, dil
0x1400138ee  jz      short loc_14001394B
0x1400138f0  cmp     dword ptr [rbp+var_18], 0
0x1400138f4  jz      short loc_14001394B
0x1400138f6  lea     r8, aDisablecachech; "DisableCacheCheck"
0x1400138fd  lea     rdx, [rsi+70h]
0x140013901  lea     rcx, [rbp+var_38]
0x140013905  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001390a  nop
0x14001390b  mov     r8, [rax]; unsigned __int16 *
0x14001390e  xor     edx, edx; int
0x140013910  lea     rcx, aTurningOffCach; "Turning off cache check based on HKLM r"...
0x140013917  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14001391c  nop
0x14001391d  mov     rdx, [rbp+var_38]
0x140013921  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140013925  or      eax, 0FFFFFFFFh
0x140013928  lock xadd [rdx+10h], eax
0x14001392d  sub     eax, 1
0x140013930  jg      short loc_14001393E
0x140013932  lfence
0x140013935  mov     rcx, [rdx]
0x140013938  mov     rax, [rcx]
0x14001393b  call    qword ptr [rax+8]
0x14001393e  or      dword ptr [rsi+3Ch], 4
0x140013942  call    cs:__imp_GetCurrentThreadId
0x140013948  mov     [rsi+40h], eax
0x14001394b  mov     rdi, qword ptr [rbp+var_30]
0x14001394f  test    bl, bl
0x140013951  jz      short loc_14001395A
0x140013953  call    cs:__imp_RevertToSelf
0x140013959  nop
0x14001395a  test    rdi, rdi
0x14001395d  jz      short loc_140013968
0x14001395f  mov     rcx, rdi; hKey
0x140013962  call    cs:__imp_RegCloseKey
0x140013968  mov     rcx, [rbp+var_10]
0x14001396c  xor     rcx, rsp; StackCookie
0x14001396f  call    __security_check_cookie
0x140013974  lea     r11, [rsp+70h+var_s0]
0x140013979  mov     rbx, [r11+28h]
0x14001397d  mov     rsi, [r11+30h]
0x140013981  mov     rsp, r11
0x140013984  pop     r14
0x140013986  pop     rdi
0x140013987  pop     rbp
0x140013988  retn
```
