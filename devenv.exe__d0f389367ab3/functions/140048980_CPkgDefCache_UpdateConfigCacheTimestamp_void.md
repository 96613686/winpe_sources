# CPkgDefCache::UpdateConfigCacheTimestamp(void)

- ea: `0x140048980`
- end: `0x140048b47`
- name: `?UpdateConfigCacheTimestamp@CPkgDefCache@@UEAAJXZ`
- size: `455`
- prototype: `__int64 __fastcall(CPkgDefCache *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x140001020`
- `0x140003160`
- `0x1400095f4`
- `0x140047554`
- `0x140048980`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140048b16`
- `ADVAPI32!RegCloseKey` at `0x140048b16`
- `ADVAPI32!RegCreateKeyExW` at `0x140048a49`
- `ADVAPI32!RegCreateKeyExW` at `0x140048a49`
- `ADVAPI32!RegSetValueExW` at `0x140048ad1`
- `ADVAPI32!RegSetValueExW` at `0x140048ad1`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400489e3`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1400489e3`
- `ADVAPI32!RevertToSelf` at `0x140048b07`
- `ADVAPI32!RevertToSelf` at `0x140048b07`

## string_xrefs

- `0x140048a80`: `ConfigPkgDefCacheTimestamp`
- `0x1400489b5`: `Saving pkgdef cache time stamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPkgDefCache::UpdateConfigCacheTimestamp(HANDLE *this)
{
  HKEY v2; // r14
  bool v3; // bl
  const WCHAR *v4; // rsi
  HKEY v5; // rdi
  DWORD dwOptions; // eax
  LSTATUS v7; // eax
  signed int v8; // edi
  LSTATUS v9; // eax
  _QWORD *v10; // rdx
  DWORD dwDisposition[2]; // [rsp+60h] [rbp+Fh] BYREF
  __int128 v13; // [rsp+68h] [rbp+17h]
  __int64 v14; // [rsp+78h] [rbp+27h]
  HKEY phkResult; // [rsp+88h] [rbp+37h] BYREF

  CLogger::LogInfo(L"Saving pkgdef cache time stamp", 0, 0);
  v14 = 0;
  v2 = 0;
  v13 = 0u;
  v3 = ImpersonateLoggedOnUser(this[28]);
  v4 = (const WCHAR *)this[23];
  v5 = hKey;
  if ( this[29] )
    v5 = (HKEY)this[29];
  dwOptions = (*((__int64 (__fastcall **)(HANDLE *))*this + 4))(this);
  phkResult = 0;
  v7 = RegCreateKeyExW(v5, v4, 0, 0, dwOptions, 0x2001Fu, 0, &phkResult, dwDisposition);
  if ( !v7 )
  {
    v2 = phkResult;
    *(_QWORD *)&v13 = phkResult;
    DWORD2(v13) = 0;
  }
  v8 = (unsigned __int16)(v7 != 0 ? v7 : 0) | 0x80070000;
  if ( (v7 != 0 ? v7 : 0) <= 0 )
    v8 = v7 != 0 ? v7 : 0;
  if ( v8 >= 0 )
  {
    _mm_lfence();
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      dwDisposition,
      L"ConfigPkgDefCacheTimestamp");
    phkResult = **(HKEY **)&CPkgDefCache::ComputeConfigCacheTimestamp((CPkgDefCache *)this);
    v9 = RegSetValueExW(v2, *(LPCWSTR *)dwDisposition, 0, 0xBu, (const BYTE *)&phkResult, 8u);
    v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v8 = v9;
    v10 = (_QWORD *)(*(_QWORD *)dwDisposition - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)dwDisposition - 24LL + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    }
  }
  if ( v3 )
    RevertToSelf();
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140048980  mov     rax, rsp
0x140048983  mov     [rax+10h], rbx
0x140048987  mov     [rax+18h], rsi
0x14004898b  mov     [rax+20h], rdi
0x14004898f  push    rbp
0x140048990  push    r14
0x140048992  push    r15
0x140048994  lea     rbp, [rax-5Fh]
0x140048998  sub     rsp, 90h
0x14004899f  mov     rax, cs:__security_cookie
0x1400489a6  xor     rax, rsp
0x1400489a9  mov     [rbp+57h+var_18], rax
0x1400489ad  mov     r15, rcx
0x1400489b0  xor     r8d, r8d; unsigned __int16 *
0x1400489b3  xor     edx, edx; int
0x1400489b5  lea     rcx, aSavingPkgdefCa_0; "Saving pkgdef cache time stamp"
0x1400489bc  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400489c1  xorps   xmm0, xmm0
0x1400489c4  xor     eax, eax
0x1400489c6  movups  [rbp+57h+var_40], xmm0
0x1400489ca  mov     [rbp+57h+var_30], rax
0x1400489ce  xor     r14d, r14d
0x1400489d1  mov     qword ptr [rbp+57h+var_40], r14
0x1400489d5  and     dword ptr [rbp+57h+var_40+8], eax
0x1400489d8  and     [rbp+57h+var_30], rax
0x1400489dc  mov     rcx, [r15+0E0h]; hToken
0x1400489e3  call    cs:__imp_ImpersonateLoggedOnUser
0x1400489e9  test    eax, eax
0x1400489eb  setnz   bl
0x1400489ee  mov     [rbp+57h+var_50], bl
0x1400489f1  mov     rsi, [r15+0B8h]
0x1400489f8  mov     rax, [r15+0E8h]
0x1400489ff  mov     rdi, cs:hKey
0x140048a06  test    rax, rax
0x140048a09  cmovnz  rdi, rax
0x140048a0d  mov     rax, [r15]
0x140048a10  mov     rcx, r15
0x140048a13  call    qword ptr [rax+20h]
0x140048a16  and     [rbp+57h+var_20], r14
0x140048a1a  lea     rcx, [rbp+57h+dwDisposition]
0x140048a1e  mov     [rsp+0A0h+lpdwDisposition], rcx; lpdwDisposition
0x140048a23  lea     rcx, [rbp+57h+var_20]
0x140048a27  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x140048a2c  and     [rsp+0A0h+var_70], r14
0x140048a31  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x140048a39  mov     [rsp+0A0h+dwOptions], eax; dwOptions
0x140048a3d  xor     r9d, r9d; lpClass
0x140048a40  xor     r8d, r8d; Reserved
0x140048a43  mov     rdx, rsi; lpSubKey
0x140048a46  mov     rcx, rdi; hKey
0x140048a49  call    cs:__imp_RegCreateKeyExW
0x140048a4f  test    eax, eax
0x140048a51  jnz     short loc_140048A5E
0x140048a53  mov     r14, [rbp+57h+var_20]
0x140048a57  mov     qword ptr [rbp+57h+var_40], r14
0x140048a5b  and     dword ptr [rbp+57h+var_40+8], eax
0x140048a5e  mov     ecx, eax
0x140048a60  neg     ecx
0x140048a62  sbb     edx, edx
0x140048a64  and     edx, eax
0x140048a66  movzx   edi, dx
0x140048a69  mov     esi, 80070000h
0x140048a6e  or      edi, esi
0x140048a70  test    edx, edx
0x140048a72  cmovle  edi, edx
0x140048a75  test    edi, edi
0x140048a77  js      loc_140048B03
0x140048a7d  lfence
0x140048a80  lea     rdx, aConfigpkgdefca; "ConfigPkgDefCacheTimestamp"
0x140048a87  lea     rcx, [rbp+57h+dwDisposition]
0x140048a8b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140048a90  nop
0x140048a91  lea     rdx, [rbp+57h+var_28]
0x140048a95  mov     rcx, r15; this
0x140048a98  call    ?ComputeConfigCacheTimestamp@CPkgDefCache@@IEAA?AU_FILETIME@@XZ; CPkgDefCache::ComputeConfigCacheTimestamp(void)
0x140048a9d  mov     ecx, [rax]
0x140048a9f  mov     dword ptr [rbp+57h+var_20], ecx
0x140048aa2  mov     eax, [rax+4]
0x140048aa5  mov     dword ptr [rbp+57h+var_20+4], eax
0x140048aa8  mov     rax, [rbp+57h+var_20]
0x140048aac  mov     [rbp+57h+var_20], rax
0x140048ab0  mov     [rsp+0A0h+samDesired], 8; cbData
0x140048ab8  lea     rax, [rbp+57h+var_20]
0x140048abc  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x140048ac1  mov     r9d, 0Bh; dwType
0x140048ac7  xor     r8d, r8d; Reserved
0x140048aca  mov     rdx, qword ptr [rbp+57h+dwDisposition]; lpValueName
0x140048ace  mov     rcx, r14; hKey
0x140048ad1  call    cs:__imp_RegSetValueExW
0x140048ad7  movzx   edi, ax
0x140048ada  or      edi, esi
0x140048adc  test    eax, eax
0x140048ade  cmovle  edi, eax
0x140048ae1  mov     rdx, qword ptr [rbp+57h+dwDisposition]
0x140048ae5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140048ae9  or      eax, 0FFFFFFFFh
0x140048aec  lock xadd [rdx+10h], eax
0x140048af1  sub     eax, 1
0x140048af4  jg      short loc_140048B03
0x140048af6  lfence
0x140048af9  mov     rcx, [rdx]
0x140048afc  mov     rax, [rcx]
0x140048aff  call    qword ptr [rax+8]
0x140048b02  nop
0x140048b03  test    bl, bl
0x140048b05  jz      short loc_140048B0E
0x140048b07  call    cs:__imp_RevertToSelf
0x140048b0d  nop
0x140048b0e  test    r14, r14
0x140048b11  jz      short loc_140048B1C
0x140048b13  mov     rcx, r14; hKey
0x140048b16  call    cs:__imp_RegCloseKey
0x140048b1c  mov     eax, edi
0x140048b1e  mov     rcx, [rbp+57h+var_18]
0x140048b22  xor     rcx, rsp; StackCookie
0x140048b25  call    __security_check_cookie
0x140048b2a  lea     r11, [rsp+0A0h+var_10]
0x140048b32  mov     rbx, [r11+28h]
0x140048b36  mov     rsi, [r11+30h]
0x140048b3a  mov     rdi, [r11+38h]
0x140048b3e  mov     rsp, r11
0x140048b41  pop     r15
0x140048b43  pop     r14
0x140048b45  pop     rbp
0x140048b46  retn
```
