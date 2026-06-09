# _anonymous_namespace_::EnsureUserPemissionForPrivateRegistryHive

- ea: `0x1400249e0`
- end: `0x140024c30`
- name: `_anonymous_namespace_::EnsureUserPemissionForPrivateRegistryHive`
- size: `592`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002ae80`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140003160`
- `0x140004950`
- `0x140009b10`
- `0x1400249e0`
- `0x140024c30`
- `0x140024e44`
- `0x140033ab0`
- `0x140061988`
- `0x140061b94`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140024b9e`
- `ADVAPI32!RegCloseKey` at `0x140024b9e`
- `ADVAPI32!RegCreateKeyExW` at `0x140024afd`
- `ADVAPI32!RegCreateKeyExW` at `0x140024afd`
- `ADVAPI32!RegDeleteTreeW` at `0x140024baf`
- `ADVAPI32!RegDeleteTreeW` at `0x140024baf`
- `ADVAPI32!RegSaveKeyW` at `0x140024b73`
- `ADVAPI32!RegSaveKeyW` at `0x140024b73`
- `ole32!StringFromCLSID` at `0x140024aa3`
- `ole32!StringFromCLSID` at `0x140024aa3`
- `ole32!CoTaskMemFree` at `0x140024ac4`
- `ole32!CoTaskMemFree` at `0x140024ac4`
- `ole32!CoCreateGuid` at `0x140024a8b`
- `ole32!CoCreateGuid` at `0x140024a8b`
- `SHLWAPI!PathFileExistsW` at `0x140024a57`
- `SHLWAPI!PathFileExistsW` at `0x140024a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::EnsureUserPemissionForPrivateRegistryHive(LPCWSTR lpPathName)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  int v3; // ebx
  LSTATUS v4; // eax
  int v5; // eax
  HKEY v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  __int64 v10; // rcx
  LPCWSTR v11; // rdx
  _QWORD *v12; // rdx
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+17h] BYREF
  __int64 v15; // [rsp+58h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+60h] [rbp+27h] BYREF
  LPOLESTR lpsz; // [rsp+68h] [rbp+2Fh] BYREF
  GUID pguid; // [rsp+70h] [rbp+37h] BYREF

  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v15 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v3 = anonymous_namespace_::ComputePrivateRegistryFilePath(lpPathName);
  if ( v3 >= 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpFile, &v15);
    if ( PathFileExistsW(lpFile) || IsWindows8OrGreater() )
    {
      v3 = 0;
      goto LABEL_24;
    }
    lpSubKey = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &lpSubKey,
      L"Software");
    v3 = CoCreateGuid(&pguid);
    if ( v3 < 0 )
      goto LABEL_22;
    v3 = StringFromCLSID(&pguid, &lpsz);
    if ( v3 < 0 )
      goto LABEL_22;
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
      &lpSubKey,
      lpsz);
    CoTaskMemFree(lpsz);
    v4 = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v4 )
    {
      v3 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        v3 = v4;
      goto LABEL_22;
    }
    v5 = anonymous_namespace_::SaveInMemoryHiveToPrivateHive(hKey);
    v3 = v5;
    if ( v5 < 0 )
    {
      _mm_lfence();
      dword_14009D440 = v5;
      v3 = anonymous_namespace_::ComputePrivateRegistryFilePath(lpPathName);
      if ( v3 < 0 )
        goto LABEL_22;
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpFile, &v15);
      v6 = hKey;
      LOBYTE(v7) = 1;
      if ( (unsigned __int8)anonymous_namespace_::SetCurrentProcessPrivilege(v8, v7) )
      {
        v9 = RegSaveKeyW(v6, lpFile, 0);
        if ( v9 )
        {
          v3 = (unsigned __int16)v9 | 0x80070000;
          if ( v9 <= 0 )
            v3 = v9;
          goto LABEL_22;
        }
        anonymous_namespace_::SetCurrentProcessPrivilege(v10, 0);
      }
      v3 = 0;
    }
    RegCloseKey(hKey);
    RegDeleteTreeW(HKEY_CURRENT_USER, lpSubKey);
LABEL_22:
    v11 = lpSubKey - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    }
  }
LABEL_24:
  v12 = (_QWORD *)(v15 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400249e0  mov     [rsp-8+arg_8], rbx
0x1400249e5  mov     [rsp-8+arg_10], rdi
0x1400249ea  push    rbp
0x1400249eb  lea     rbp, [rsp-57h]
0x1400249f0  sub     rsp, 90h
0x1400249f7  mov     rax, cs:__security_cookie
0x1400249fe  xor     rax, rsp
0x140024a01  mov     [rbp+57h+var_10], rax
0x140024a05  mov     rdi, rcx
0x140024a08  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140024a0d  mov     rcx, rax
0x140024a10  test    rax, rax
0x140024a13  jz      loc_140024C25
0x140024a19  mov     rax, [rax]
0x140024a1c  call    qword ptr [rax+18h]
0x140024a1f  add     rax, 18h
0x140024a23  mov     [rbp+57h+var_38], rax
0x140024a27  xor     r8d, r8d
0x140024a2a  lea     rdx, [rbp+57h+var_38]
0x140024a2e  mov     rcx, rdi; lpPathName
0x140024a31  call    _anonymous_namespace___ComputePrivateRegistryFilePath
0x140024a36  mov     ebx, eax
0x140024a38  test    eax, eax
0x140024a3a  js      loc_140024BE0
0x140024a40  lea     rdx, [rbp+57h+var_38]
0x140024a44  lea     rcx, lpFile
0x140024a4b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140024a50  mov     rcx, cs:lpFile; pszPath
0x140024a57  call    cs:__imp_PathFileExistsW
0x140024a5d  test    eax, eax
0x140024a5f  jnz     short loc_140024A6A
0x140024a61  call    ?IsWindows8OrGreater@@YA_NXZ; IsWindows8OrGreater(void)
0x140024a66  test    al, al
0x140024a68  jz      short loc_140024A71
0x140024a6a  xor     ebx, ebx
0x140024a6c  jmp     loc_140024BE0
0x140024a71  and     [rbp+57h+lpSubKey], 0
0x140024a76  lea     rdx, aSoftware_0; "Software"
0x140024a7d  lea     rcx, [rbp+57h+lpSubKey]
0x140024a81  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024a86  nop
0x140024a87  lea     rcx, [rbp+57h+pguid]; pguid
0x140024a8b  call    cs:__imp_CoCreateGuid
0x140024a91  mov     ebx, eax
0x140024a93  test    eax, eax
0x140024a95  js      loc_140024BB6
0x140024a9b  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x140024a9f  lea     rcx, [rbp+57h+pguid]; rclsid
0x140024aa3  call    cs:__imp_StringFromCLSID
0x140024aa9  mov     ebx, eax
0x140024aab  test    eax, eax
0x140024aad  js      loc_140024BB6
0x140024ab3  mov     rdx, [rbp+57h+lpsz]
0x140024ab7  lea     rcx, [rbp+57h+lpSubKey]
0x140024abb  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140024ac0  mov     rcx, [rbp+57h+lpsz]; pv
0x140024ac4  call    cs:__imp_CoTaskMemFree
0x140024aca  and     [rsp+90h+var_50], 0
0x140024ad0  lea     rax, [rbp+57h+hKey]
0x140024ad4  mov     [rsp+90h+phkResult], rax; phkResult
0x140024ad9  and     [rsp+90h+var_60], 0
0x140024adf  mov     [rsp+90h+samDesired], 0F003Fh; samDesired
0x140024ae7  and     [rsp+90h+var_70], 0
0x140024aec  xor     r9d, r9d; lpClass
0x140024aef  xor     r8d, r8d; Reserved
0x140024af2  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140024af6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140024afd  call    cs:__imp_RegCreateKeyExW
0x140024b03  test    eax, eax
0x140024b05  jz      short loc_140024B1A
0x140024b07  movzx   ebx, ax
0x140024b0a  or      ebx, 80070000h
0x140024b10  test    eax, eax
0x140024b12  cmovle  ebx, eax
0x140024b15  jmp     loc_140024BB6
0x140024b1a  mov     rcx, [rbp+57h+hKey]; hKey
0x140024b1e  call    _anonymous_namespace___SaveInMemoryHiveToPrivateHive
0x140024b23  mov     ebx, eax
0x140024b25  test    eax, eax
0x140024b27  jns     short loc_140024B9A
0x140024b29  lfence
0x140024b2c  mov     cs:dword_14009D440, eax
0x140024b32  mov     r8b, 1
0x140024b35  lea     rdx, [rbp+57h+var_38]
0x140024b39  mov     rcx, rdi; lpPathName
0x140024b3c  call    _anonymous_namespace___ComputePrivateRegistryFilePath
0x140024b41  mov     ebx, eax
0x140024b43  test    eax, eax
0x140024b45  js      short loc_140024BB6
0x140024b47  lea     rdx, [rbp+57h+var_38]
0x140024b4b  lea     rcx, lpFile
0x140024b52  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140024b57  mov     rbx, [rbp+57h+hKey]
0x140024b5b  mov     dl, 1
0x140024b5d  call    _anonymous_namespace___SetCurrentProcessPrivilege
0x140024b62  test    al, al
0x140024b64  jz      short loc_140024B98
0x140024b66  xor     r8d, r8d; lpSecurityAttributes
0x140024b69  mov     rdx, cs:lpFile; lpFile
0x140024b70  mov     rcx, rbx; hKey
0x140024b73  call    cs:__imp_RegSaveKeyW
0x140024b79  test    eax, eax
0x140024b7b  jz      short loc_140024B91
0x140024b7d  movzx   ebx, ax
0x140024b80  or      ebx, 80070000h
0x140024b86  test    eax, eax
0x140024b88  cmovle  ebx, eax
0x140024b8b  test    ebx, ebx
0x140024b8d  jns     short loc_140024B9A
0x140024b8f  jmp     short loc_140024BB6
0x140024b91  xor     edx, edx
0x140024b93  call    _anonymous_namespace___SetCurrentProcessPrivilege
0x140024b98  xor     ebx, ebx
0x140024b9a  mov     rcx, [rbp+57h+hKey]; hKey
0x140024b9e  call    cs:__imp_RegCloseKey
0x140024ba4  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140024ba8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140024baf  call    cs:__imp_RegDeleteTreeW
0x140024bb5  nop
0x140024bb6  mov     rdx, [rbp+57h+lpSubKey]
0x140024bba  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024bbe  or      eax, 0FFFFFFFFh
0x140024bc1  lock xadd [rdx+10h], eax
0x140024bc6  sub     eax, 1
0x140024bc9  jg      short loc_140024BE0
0x140024bcb  lfence
0x140024bce  mov     rcx, [rdx]
0x140024bd1  mov     rax, [rcx]
0x140024bd4  call    qword ptr [rax+8]
0x140024bd7  nop
0x140024bd8  nop     dword ptr [rax+rax+00000000h]
0x140024be0  mov     rdx, [rbp+57h+var_38]
0x140024be4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024be8  or      ecx, 0FFFFFFFFh
0x140024beb  lock xadd [rdx+10h], ecx
0x140024bf0  sub     ecx, 1
0x140024bf3  jg      short loc_140024C02
0x140024bf5  lfence
0x140024bf8  mov     rcx, [rdx]
0x140024bfb  mov     r8, [rcx]
0x140024bfe  call    qword ptr [r8+8]
0x140024c02  mov     eax, ebx
0x140024c04  mov     rcx, [rbp+57h+var_10]
0x140024c08  xor     rcx, rsp; StackCookie
0x140024c0b  call    __security_check_cookie
0x140024c10  lea     r11, [rsp+90h+var_s0]
0x140024c18  mov     rbx, [r11+18h]
0x140024c1c  mov     rdi, [r11+20h]
0x140024c20  mov     rsp, r11
0x140024c23  pop     rbp
0x140024c24  retn
0x140024c25  mov     ecx, 80004005h; int
0x140024c2a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
