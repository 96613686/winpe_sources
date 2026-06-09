# CUserProfile::CheckProfileListKey(HKEY__ * *,ulong *,int *)

- ea: `0x18001ea8c`
- end: `0x18001ecbe`
- name: `?CheckProfileListKey@CUserProfile@@IEAAJPEAPEAUHKEY__@@PEAKPEAH@Z`
- size: `562`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, HKEY *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b6b8`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x18001ea8c`
- `0x18001ecc4`
- `0x18001f060`
- `0x18002b2a0`
- `0x18002d2d8`
- `0x18002e648`
- `0x18003f42c`
- `0x1800439c0`
- `0x18004e5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eafb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ec27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eafb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ec27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ebf1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ebf1`

## string_xrefs

- `0x18001eadf`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001eb96`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001ec02`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001ec59`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001ec82`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfile::CheckProfileListKey(CUserProfile *this, HKEY *a2, unsigned int *a3, int *a4)
{
  int OldKeyFromGuid; // edi
  __int64 v9; // rdx
  int v11; // esi
  HKEY v12; // rdx
  int ProfileListKeyNameFromSid; // eax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  const unsigned __int16 *v17; // r8
  int v18; // eax
  int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h]
  __int64 v23; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int v25; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v25 = 0;
  hKey = 0;
  OldKeyFromGuid = CUserProfile::RestoreKeyFromBackup(this, *((const unsigned __int16 **)this + 6), &hKey, &v25);
  if ( OldKeyFromGuid < 0 )
  {
    v9 = 1097;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)OldKeyFromGuid,
      dwOptions);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)OldKeyFromGuid;
  }
  v11 = 0;
  if ( hKey )
  {
LABEL_22:
    *a2 = hKey;
    *a3 = v25;
    *a4 = v11;
    return 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  OldKeyFromGuid = CUserProfile::GetOldKeyFromGuid(this, *((HANDLE *)this + 3), *((LPCWCH *)this + 6), &hKey, &v25);
  if ( OldKeyFromGuid < 0 )
  {
    v9 = 1104;
    goto LABEL_3;
  }
  v12 = hKey;
  if ( hKey )
  {
LABEL_18:
    v16 = CUserProfile::CheckUserPrefrenceKey(this, v12, v11);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x465,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v16);
    v18 = SetOldSidString(*((HANDLE *)this + 3), *((const unsigned __int16 **)this + 6), v17);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x468,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v18);
    goto LABEL_22;
  }
  lpSubKey = 0;
  v22 = 0;
  v23 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v22 = -1;
  v23 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(
                                *((LPCWCH *)this + 6),
                                (unsigned __int16 **)&lpSubKey,
                                (int *)this + 10);
  OldKeyFromGuid = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      dwOptions);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    goto LABEL_4;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( !v14 )
  {
    v11 = 1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
    v12 = hKey;
    goto LABEL_18;
  }
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x460,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v14,
          dwOptionsa);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return v15;
}

```

## disassembly

```asm
0x18001ea8c  mov     [rsp-38h+arg_10], rbx
0x18001ea91  push    rbp
0x18001ea92  push    rsi
0x18001ea93  push    rdi
0x18001ea94  push    r12
0x18001ea96  push    r13
0x18001ea98  push    r14
0x18001ea9a  push    r15
0x18001ea9c  mov     rbp, rsp
0x18001ea9f  sub     rsp, 70h
0x18001eaa3  mov     r14, r9
0x18001eaa6  mov     r15, r8
0x18001eaa9  mov     r12, rdx
0x18001eaac  mov     rbx, rcx
0x18001eaaf  xor     r13d, r13d
0x18001eab2  mov     [rdx], r13
0x18001eab5  mov     [r8], r13d
0x18001eab8  mov     [r9], r13d
0x18001eabb  mov     [rbp+arg_0], r13d
0x18001eabf  mov     [rbp+hKey], r13
0x18001eac3  lea     r9, [rbp+arg_0]; unsigned int *
0x18001eac7  lea     r8, [rbp+hKey]; HKEY *
0x18001eacb  mov     rdx, [rcx+30h]; unsigned __int16 *
0x18001eacf  call    ?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)
0x18001ead4  mov     edi, eax
0x18001ead6  test    eax, eax
0x18001ead8  jns     short loc_18001EB08
0x18001eada  mov     edx, 449h; void *
0x18001eadf  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001eae6  mov     r9d, edi; char *
0x18001eae9  mov     rcx, [rbp+38h]; this
0x18001eaed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eaf2  mov     rcx, [rbp+hKey]; hKey
0x18001eaf6  test    rcx, rcx
0x18001eaf9  jz      short loc_18001EB01
0x18001eafb  call    cs:__imp_RegCloseKey
0x18001eb01  mov     eax, edi
0x18001eb03  jmp     loc_18001ECA6
0x18001eb08  mov     esi, r13d
0x18001eb0b  cmp     [rbp+hKey], r13
0x18001eb0f  jnz     loc_18001EC93
0x18001eb15  xor     edx, edx
0x18001eb17  lea     rcx, [rbp+hKey]
0x18001eb1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001eb20  lea     rax, [rbp+arg_0]
0x18001eb24  mov     qword ptr [rsp+70h+dwOptions], rax; int
0x18001eb29  lea     r9, [rbp+hKey]; HKEY *
0x18001eb2d  mov     r8, [rbx+30h]; lpString1
0x18001eb31  mov     rdx, [rbx+18h]; TokenHandle
0x18001eb35  mov     rcx, rbx; this
0x18001eb38  call    ?GetOldKeyFromGuid@CUserProfile@@IEAAJPEAXPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::GetOldKeyFromGuid(void *,ushort const *,HKEY__ * *,ulong *)
0x18001eb3d  mov     edi, eax
0x18001eb3f  test    eax, eax
0x18001eb41  jns     short loc_18001EB4A
0x18001eb43  mov     edx, 450h
0x18001eb48  jmp     short loc_18001EADF
0x18001eb4a  mov     rdx, [rbp+hKey]
0x18001eb4e  test    rdx, rdx
0x18001eb51  jnz     loc_18001EC43
0x18001eb57  mov     [rbp+lpSubKey], r13
0x18001eb5b  mov     [rbp+var_18], r13
0x18001eb5f  mov     [rbp+var_10], r13
0x18001eb63  lea     rcx, [rbp+lpSubKey]
0x18001eb67  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001eb6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb70  mov     [rbp+var_18], rax
0x18001eb74  mov     [rbp+var_10], rax
0x18001eb78  lea     r8, [rbx+28h]; int *
0x18001eb7c  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18001eb80  mov     rcx, [rbx+30h]; lpString1
0x18001eb84  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18001eb89  mov     edi, eax
0x18001eb8b  test    eax, eax
0x18001eb8d  jns     short loc_18001EBB5
0x18001eb8f  mov     rcx, [rbp+38h]; this
0x18001eb93  mov     r9d, eax; char *
0x18001eb96  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001eb9d  mov     edx, 457h; void *
0x18001eba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eba7  lea     rcx, [rbp+lpSubKey]
0x18001ebab  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001ebb0  jmp     loc_18001EAF2
0x18001ebb5  xor     edx, edx
0x18001ebb7  lea     rcx, [rbp+hKey]
0x18001ebbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ebc0  mov     [rsp+70h+lpdwDisposition], r13; lpdwDisposition
0x18001ebc5  lea     rax, [rbp+hKey]
0x18001ebc9  mov     [rsp+70h+phkResult], rax; phkResult
0x18001ebce  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18001ebd3  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18001ebdb  mov     [rsp+70h+dwOptions], r13d; int
0x18001ebe0  xor     r9d, r9d; lpClass
0x18001ebe3  xor     r8d, r8d; Reserved
0x18001ebe6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001ebea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ebf1  call    cs:__imp_RegCreateKeyExW
0x18001ebf7  test    eax, eax
0x18001ebf9  jz      short loc_18001EC31
0x18001ebfb  mov     rcx, [rbp+38h]; this
0x18001ebff  mov     r9d, eax; char *
0x18001ec02  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ec09  mov     edx, 460h; void *
0x18001ec0e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ec13  mov     ebx, eax
0x18001ec15  lea     rcx, [rbp+lpSubKey]
0x18001ec19  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001ec1e  mov     rcx, [rbp+hKey]; hKey
0x18001ec22  test    rcx, rcx
0x18001ec25  jz      short loc_18001EC2D
0x18001ec27  call    cs:__imp_RegCloseKey
0x18001ec2d  mov     eax, ebx
0x18001ec2f  jmp     short loc_18001ECA6
0x18001ec31  mov     esi, 1
0x18001ec36  lea     rcx, [rbp+lpSubKey]
0x18001ec3a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001ec3f  mov     rdx, [rbp+hKey]; HKEY
0x18001ec43  mov     r8d, esi; int
0x18001ec46  mov     rcx, rbx; this
0x18001ec49  call    ?CheckUserPrefrenceKey@CUserProfile@@IEAAJPEAUHKEY__@@H@Z; CUserProfile::CheckUserPrefrenceKey(HKEY__ *,int)
0x18001ec4e  test    eax, eax
0x18001ec50  jns     short loc_18001EC6A
0x18001ec52  mov     rcx, [rbp+38h]; this
0x18001ec56  mov     r9d, eax; char *
0x18001ec59  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ec60  mov     edx, 465h; void *
0x18001ec65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ec6a  mov     rdx, [rbx+30h]; unsigned __int16 *
0x18001ec6e  mov     rcx, [rbx+18h]; TokenHandle
0x18001ec72  call    ?SetOldSidString@@YAJPEAXPEBG1@Z; SetOldSidString(void *,ushort const *,ushort const *)
0x18001ec77  test    eax, eax
0x18001ec79  jns     short loc_18001EC93
0x18001ec7b  mov     rcx, [rbp+38h]; this
0x18001ec7f  mov     r9d, eax; char *
0x18001ec82  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ec89  mov     edx, 468h; void *
0x18001ec8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ec93  mov     rax, [rbp+hKey]
0x18001ec97  mov     [r12], rax
0x18001ec9b  mov     eax, [rbp+arg_0]
0x18001ec9e  mov     [r15], eax
0x18001eca1  mov     [r14], esi
0x18001eca4  xor     eax, eax
0x18001eca6  mov     rbx, [rsp+70h+arg_10]
0x18001ecae  add     rsp, 70h
0x18001ecb2  pop     r15
0x18001ecb4  pop     r14
0x18001ecb6  pop     r13
0x18001ecb8  pop     r12
0x18001ecba  pop     rdi
0x18001ecbb  pop     rsi
0x18001ecbc  pop     rbp
0x18001ecbd  retn
```
