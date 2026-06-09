# CPkgDefCache::GetConfigurationTimestamp(void)

- ea: `0x140008770`
- end: `0x1400088d5`
- name: `?GetConfigurationTimestamp@CPkgDefCache@@UEBA?AU_FILETIME@@XZ`
- size: `357`
- prototype: `struct _FILETIME __fastcall(CPkgDefCache *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140003160`
- `0x140008770`
- `0x1400088d8`
- `0x1400464b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400088ac`
- `ADVAPI32!RegCloseKey` at `0x1400088ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1400087f1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400087f1`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140008797`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140008797`
- `ADVAPI32!RevertToSelf` at `0x1400088b7`
- `ADVAPI32!RevertToSelf` at `0x1400088b7`

## string_xrefs

- `0x140008839`: `ConfigPkgDefCacheTimestamp`
- `0x140008823`: `No previous pkgdef cache data`
- `0x140008889`: `Previous pkgdef cache timestamp is not valid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _FILETIME __fastcall CPkgDefCache::GetConfigurationTimestamp(CPkgDefCache *this, __int64 a2)
{
  bool v4; // bl
  HKEY v5; // rsi
  HKEY v6; // rcx
  LSTATUS v7; // eax
  HKEY v8; // rdi
  signed int v9; // edx
  HKEY v10; // rcx
  int RegistryValue; // edi
  HKEY v12; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h]
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF

  *(_QWORD *)a2 = 0;
  v4 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  v15 = 0;
  v5 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v6 = ::hKey;
  if ( *((_QWORD *)this + 29) )
    v6 = (HKEY)*((_QWORD *)this + 29);
  phkResult = 0;
  v7 = RegOpenKeyExW(v6, *((LPCWSTR *)this + 23), 0, 0x2001Fu, &phkResult);
  v8 = 0;
  if ( !v7 )
  {
    v5 = phkResult;
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
    v8 = phkResult;
  }
  v9 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v9 = v7;
  if ( v9 < 0 )
  {
    _mm_lfence();
    CLogger::LogWarn(L"No previous pkgdef cache data", v9, 0);
    if ( !v8 )
      goto LABEL_16;
    v10 = v5;
    goto LABEL_15;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    L"ConfigPkgDefCacheTimestamp");
  RegistryValue = GetRegistryValue(hKey, &phkResult, a2);
  v12 = phkResult - 6;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  }
  _mm_lfence();
  if ( RegistryValue < 0 )
  {
    CLogger::LogWarn(L"Previous pkgdef cache timestamp is not valid", RegistryValue, 0);
    *(_DWORD *)a2 = 0;
    *(_DWORD *)(a2 + 4) = 0;
  }
  v10 = hKey[0];
  if ( hKey[0] )
LABEL_15:
    RegCloseKey(v10);
LABEL_16:
  if ( v4 )
    RevertToSelf();
  return (struct _FILETIME)a2;
}

```

## disassembly

```asm
0x140008770  mov     [rsp-18h+arg_8], rbx
0x140008775  mov     [rsp-18h+arg_18], rsi
0x14000877a  push    rbp
0x14000877b  push    rdi
0x14000877c  push    r14
0x14000877e  mov     rbp, rsp
0x140008781  sub     rsp, 50h
0x140008785  mov     r14, rdx
0x140008788  mov     rdi, rcx
0x14000878b  xor     eax, eax
0x14000878d  mov     [rdx], rax
0x140008790  mov     rcx, [rcx+0E0h]; hToken
0x140008797  call    cs:__imp_ImpersonateLoggedOnUser
0x14000879d  test    eax, eax
0x14000879f  setnz   bl
0x1400087a2  mov     [rbp+arg_0], bl
0x1400087a5  xorps   xmm0, xmm0
0x1400087a8  xor     eax, eax
0x1400087aa  movups  xmmword ptr [rbp+hKey], xmm0
0x1400087ae  mov     [rbp+var_10], rax
0x1400087b2  xor     esi, esi
0x1400087b4  mov     [rbp+hKey], rsi
0x1400087b8  and     dword ptr [rbp+hKey+8], eax
0x1400087bb  and     [rbp+var_10], rax
0x1400087bf  mov     rax, [rdi+0E8h]
0x1400087c6  mov     rcx, cs:hKey
0x1400087cd  test    rax, rax
0x1400087d0  cmovnz  rcx, rax; hKey
0x1400087d4  and     [rbp+arg_10], rsi
0x1400087d8  lea     rax, [rbp+arg_10]
0x1400087dc  mov     [rsp+50h+phkResult], rax; phkResult
0x1400087e1  mov     r9d, 2001Fh; samDesired
0x1400087e7  xor     r8d, r8d; ulOptions
0x1400087ea  mov     rdx, [rdi+0B8h]; lpSubKey
0x1400087f1  call    cs:__imp_RegOpenKeyExW
0x1400087f7  xor     edi, edi
0x1400087f9  test    eax, eax
0x1400087fb  jnz     short loc_14000880B
0x1400087fd  mov     rsi, [rbp+arg_10]
0x140008801  mov     [rbp+hKey], rsi
0x140008805  and     dword ptr [rbp+hKey+8], eax
0x140008808  mov     rdi, rsi
0x14000880b  movzx   edx, ax
0x14000880e  or      edx, 80070000h
0x140008814  test    eax, eax
0x140008816  cmovle  edx, eax; int
0x140008819  test    edx, edx
0x14000881b  jns     short loc_140008839
0x14000881d  lfence
0x140008820  xor     r8d, r8d; unsigned __int16 *
0x140008823  lea     rcx, aNoPreviousPkgd; "No previous pkgdef cache data"
0x14000882a  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14000882f  test    rdi, rdi
0x140008832  jz      short loc_1400088B3
0x140008834  mov     rcx, rsi
0x140008837  jmp     short loc_1400088AC
0x140008839  lea     rdx, aConfigpkgdefca; "ConfigPkgDefCacheTimestamp"
0x140008840  lea     rcx, [rbp+arg_10]
0x140008844  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140008849  mov     r8, r14
0x14000884c  lea     rdx, [rbp+arg_10]
0x140008850  lea     rcx, [rbp+hKey]
0x140008854  call    ?GetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAU_FILETIME@@@Z; GetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_FILETIME &)
0x140008859  mov     edi, eax
0x14000885b  mov     rdx, [rbp+arg_10]
0x14000885f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140008863  or      ecx, 0FFFFFFFFh
0x140008866  lock xadd [rdx+10h], ecx
0x14000886b  sub     ecx, 1
0x14000886e  jg      short loc_14000887D
0x140008870  lfence
0x140008873  mov     rcx, [rdx]
0x140008876  mov     r8, [rcx]
0x140008879  call    qword ptr [r8+8]
0x14000887d  test    edi, edi
0x14000887f  jns     short loc_1400088A0
0x140008881  lfence
0x140008884  xor     r8d, r8d; unsigned __int16 *
0x140008887  mov     edx, edi; int
0x140008889  lea     rcx, aPreviousPkgdef; "Previous pkgdef cache timestamp is not "...
0x140008890  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140008895  and     dword ptr [r14], 0
0x140008899  and     dword ptr [r14+4], 0
0x14000889e  jmp     short loc_1400088A3
0x1400088a0  lfence
0x1400088a3  mov     rcx, [rbp+hKey]; hKey
0x1400088a7  test    rcx, rcx
0x1400088aa  jz      short loc_1400088B3
0x1400088ac  call    cs:__imp_RegCloseKey
0x1400088b2  nop
0x1400088b3  test    bl, bl
0x1400088b5  jz      short loc_1400088BD
0x1400088b7  call    cs:__imp_RevertToSelf
0x1400088bd  mov     rax, r14
0x1400088c0  lea     r11, [rsp+50h+var_s0]
0x1400088c5  mov     rbx, [r11+28h]
0x1400088c9  mov     rsi, [r11+38h]
0x1400088cd  mov     rsp, r11
0x1400088d0  pop     r14
0x1400088d2  pop     rdi
0x1400088d3  pop     rbp
0x1400088d4  retn
```
