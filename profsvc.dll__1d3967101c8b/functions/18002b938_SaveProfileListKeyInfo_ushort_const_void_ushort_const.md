# _SaveProfileListKeyInfo(ushort const *,void *,ushort const *)

- ea: `0x18002b938`
- end: `0x18002bb4f`
- name: `?_SaveProfileListKeyInfo@@YAJPEBGPEAX0@Z`
- size: `535`
- prototype: `__int64 __fastcall(LPCWCH lpString1, BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ed00`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x18001f060`
- `0x18001fb70`
- `0x18002b938`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002f738`
- `0x18003fd14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ba3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ba3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bae8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bae8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ba0c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ba0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bac5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002bac5`

## string_xrefs

- `0x18002ba4c`: `ProfileImagePath`
- `0x18002b9a4`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18002ba1f`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18002ba6a`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

## pseudocode

```c
__int64 __fastcall _SaveProfileListKeyInfo(LPCWCH lpString1, BYTE *lpData, const unsigned __int16 *a3)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  DWORD LengthSid; // eax
  int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  __int64 v20; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v22; // [rsp+A8h] [rbp+38h] BYREF

  v22 = 0;
  lpSubKey = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v19 = -1;
  v20 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, &v22);
  v7 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      dwOptions);
    goto LABEL_23;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v8 )
  {
    v10 = 71;
LABEL_5:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
           (const char *)v8,
           dwOptionsa);
    goto LABEL_6;
  }
  v11 = SHRegSetExpandString(hKey, v9, L"ProfileImagePath", a3);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = 73;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)v11,
      dwOptionsa);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_23;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"Flags", 0);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = 74;
    goto LABEL_10;
  }
  v11 = SHRegSetDWORD(hKey, 0, L"State", 4u);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = 75;
    goto LABEL_10;
  }
  LengthSid = GetLengthSid(lpData);
  v8 = RegSetValueExW(hKey, L"Sid", 0, 3u, lpData, LengthSid);
  if ( v8 )
  {
    v10 = 76;
    goto LABEL_5;
  }
  if ( v22 )
  {
    v11 = CopyRedirectedProfileListKeyForSid(hKey, lpString1);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = 80;
      goto LABEL_10;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  v7 = 0;
LABEL_23:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x18002b938  mov     [rsp-18h+arg_0], rbx
0x18002b93d  mov     [rsp-18h+arg_8], rsi
0x18002b942  push    rbp
0x18002b943  push    rdi
0x18002b944  push    r14
0x18002b946  mov     rbp, rsp
0x18002b949  sub     rsp, 70h
0x18002b94d  mov     rdi, rcx
0x18002b950  mov     [rbp+arg_18], 0
0x18002b957  lea     rcx, [rbp+lpSubKey]
0x18002b95b  mov     [rbp+lpSubKey], 0
0x18002b963  mov     rsi, r8
0x18002b966  mov     [rbp+var_10], 0
0x18002b96e  mov     r14, rdx
0x18002b971  mov     [rbp+var_8], 0
0x18002b979  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002b97e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b982  lea     r8, [rbp+arg_18]; int *
0x18002b986  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18002b98a  mov     [rbp+var_10], rax
0x18002b98e  mov     rcx, rdi; lpString1
0x18002b991  mov     [rbp+var_8], rax
0x18002b995  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002b99a  mov     ebx, eax
0x18002b99c  test    eax, eax
0x18002b99e  jns     short loc_18002B9BD
0x18002b9a0  mov     rcx, [rbp+18h]; this
0x18002b9a4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002b9ab  mov     r9d, eax; char *
0x18002b9ae  mov     edx, 3Ch ; '<'; void *
0x18002b9b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b9b8  jmp     loc_18002BB2F
0x18002b9bd  xor     edx, edx
0x18002b9bf  mov     [rbp+hKey], 0
0x18002b9c7  lea     rcx, [rbp+hKey]
0x18002b9cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b9d0  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002b9d4  lea     rax, [rbp+hKey]
0x18002b9d8  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18002b9e1  xor     r9d, r9d; lpClass
0x18002b9e4  mov     [rsp+70h+phkResult], rax; phkResult
0x18002b9e9  xor     r8d, r8d; Reserved
0x18002b9ec  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002b9f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b9fc  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18002ba04  mov     [rsp+70h+dwOptions], 0; int
0x18002ba0c  call    cs:__imp_RegCreateKeyExW
0x18002ba12  test    eax, eax
0x18002ba14  jz      short loc_18002BA48
0x18002ba16  mov     edx, 47h ; 'G'; void *
0x18002ba1b  mov     rcx, [rbp+18h]; this
0x18002ba1f  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ba26  mov     r9d, eax; char *
0x18002ba29  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ba2e  mov     ebx, eax
0x18002ba30  mov     rcx, [rbp+hKey]; hKey
0x18002ba34  test    rcx, rcx
0x18002ba37  jz      loc_18002BB2F
0x18002ba3d  call    cs:__imp_RegCloseKey
0x18002ba43  jmp     loc_18002BB2F
0x18002ba48  mov     rcx, [rbp+hKey]; HKEY
0x18002ba4c  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18002ba53  mov     r9, rsi; unsigned __int16 *
0x18002ba56  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002ba5b  mov     ebx, eax
0x18002ba5d  test    eax, eax
0x18002ba5f  jns     short loc_18002BA7B
0x18002ba61  mov     edx, 49h ; 'I'; void *
0x18002ba66  mov     rcx, [rbp+18h]; this
0x18002ba6a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ba71  mov     r9d, eax; char *
0x18002ba74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba79  jmp     short loc_18002BA30
0x18002ba7b  mov     rcx, [rbp+hKey]; HKEY
0x18002ba7f  lea     r8, aFlags; "Flags"
0x18002ba86  xor     r9d, r9d; unsigned int
0x18002ba89  xor     edx, edx; unsigned __int16 *
0x18002ba8b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002ba90  mov     ebx, eax
0x18002ba92  test    eax, eax
0x18002ba94  jns     short loc_18002BA9D
0x18002ba96  mov     edx, 4Ah ; 'J'
0x18002ba9b  jmp     short loc_18002BA66
0x18002ba9d  mov     rcx, [rbp+hKey]; HKEY
0x18002baa1  lea     r8, aState; "State"
0x18002baa8  mov     r9d, 4; unsigned int
0x18002baae  xor     edx, edx; unsigned __int16 *
0x18002bab0  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002bab5  mov     ebx, eax
0x18002bab7  test    eax, eax
0x18002bab9  jns     short loc_18002BAC2
0x18002babb  mov     edx, 4Bh ; 'K'
0x18002bac0  jmp     short loc_18002BA66
0x18002bac2  mov     rcx, r14; pSid
0x18002bac5  call    cs:__imp_GetLengthSid
0x18002bacb  mov     rcx, [rbp+hKey]; hKey
0x18002bacf  lea     rdx, aSid; "Sid"
0x18002bad6  mov     [rsp+70h+samDesired], eax; cbData
0x18002bada  mov     r9d, 3; dwType
0x18002bae0  xor     r8d, r8d; Reserved
0x18002bae3  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x18002bae8  call    cs:__imp_RegSetValueExW
0x18002baee  test    eax, eax
0x18002baf0  jz      short loc_18002BAFC
0x18002baf2  mov     edx, 4Ch ; 'L'
0x18002baf7  jmp     loc_18002BA1B
0x18002bafc  cmp     [rbp+arg_18], 0
0x18002bb00  jz      short loc_18002BB1E
0x18002bb02  mov     rcx, [rbp+hKey]; hKeySrc
0x18002bb06  mov     rdx, rdi; unsigned __int16 *
0x18002bb09  call    ?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z; CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)
0x18002bb0e  mov     ebx, eax
0x18002bb10  test    eax, eax
0x18002bb12  jns     short loc_18002BB1E
0x18002bb14  mov     edx, 50h ; 'P'
0x18002bb19  jmp     loc_18002BA66
0x18002bb1e  mov     rcx, [rbp+hKey]; hKey
0x18002bb22  test    rcx, rcx
0x18002bb25  jz      short loc_18002BB2D
0x18002bb27  call    cs:__imp_RegCloseKey
0x18002bb2d  xor     ebx, ebx
0x18002bb2f  lea     rcx, [rbp+lpSubKey]
0x18002bb33  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002bb38  lea     r11, [rsp+70h+var_s0]
0x18002bb3d  mov     eax, ebx
0x18002bb3f  mov     rbx, [r11+20h]
0x18002bb43  mov     rsi, [r11+28h]
0x18002bb47  mov     rsp, r11
0x18002bb4a  pop     r14
0x18002bb4c  pop     rdi
0x18002bb4d  pop     rbp
0x18002bb4e  retn
```
