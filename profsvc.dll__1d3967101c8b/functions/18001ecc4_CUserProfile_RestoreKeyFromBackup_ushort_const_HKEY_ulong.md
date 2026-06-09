# CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)

- ea: `0x18001ecc4`
- end: `0x18001f053`
- name: `?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `911`
- prototype: `int(CUserProfile *__hidden this, const unsigned __int16 *, HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ea8c`
- `0x18002b2a0`

## callees

- `0x1800053a0`
- `0x18000f1b0`
- `0x1800111a0`
- `0x180016680`
- `0x18001ecc4`
- `0x18001f060`
- `0x18001fb70`
- `0x18002444c`
- `0x18002d2d8`
- `0x18002e648`
- `0x180034794`
- `0x18003f42c`
- `0x180042a78`
- `0x180043b40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ed57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ed57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001edf9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001edf9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001eec9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001eec9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001efc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ee28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001efc7`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18001efa4`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18001efa4`

## string_xrefs

- `0x18001ed1b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001ed5d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::RestoreKeyFromBackup(
        DWORD **this,
        const unsigned __int16 *a2,
        HKEY *a3,
        unsigned int *a4)
{
  HKEY v4; // rbx
  int ProfileListKeyNameFromSid; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  const WCHAR *v11; // r14
  unsigned int v12; // eax
  LSTATUS ValueW; // eax
  bool v14; // sf
  HKEY v15; // rcx
  unsigned int v16; // ebx
  int v17; // eax
  LSTATUS v18; // eax
  CUserProfile *v19; // rcx
  int v20; // eax
  HKEY v21; // rcx
  unsigned int v22; // eax
  int v24; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  HKEY v26; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int pvData; // [rsp+C0h] [rbp+50h] BYREF
  const WCHAR *pcbData; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  lpSubKey[0] = 0;
  lpSubKey[1] = (LPCWSTR)-1LL;
  lpSubKey[2] = (LPCWSTR)-1LL;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a2, (unsigned __int16 **)lpSubKey, 0);
  v9 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    v10 = 2752;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
LABEL_45:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    return v9;
  }
  v11 = lpSubKey[0];
  v26 = 0;
  pvData = 0;
  hKey = 0;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &hKey);
  if ( v12 == 2 )
    goto LABEL_16;
  if ( !v12 )
  {
    LODWORD(pcbData) = 4;
    ValueW = RegGetValueW(hKey, 0, L"State", 0x10u, 0, &pvData, (LPDWORD)&pcbData);
    v14 = ValueW < 0;
    if ( ValueW > 0 )
      v14 = 1;
    if ( !v14 )
    {
      v4 = hKey;
      v15 = 0;
      hKey = 0;
      v26 = v4;
      goto LABEL_17;
    }
LABEL_16:
    v15 = hKey;
LABEL_17:
    if ( v15 )
      RegCloseKey(v15);
    goto LABEL_19;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xB1F,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
         (const char *)v12,
         phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)v9,
      phkResult);
    if ( v11 )
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v11);
    return v9;
  }
LABEL_19:
  LODWORD(pcbData) = 0;
  if ( (pvData & 0x880) != 0 && (unsigned int)GetMachineRole((int *)&pcbData) && (_DWORD)pcbData )
  {
    v16 = pvData;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v17 = CUserProfile::CleanupProfileFromKey(this, a2, &v26, v16);
    if ( v17 >= 0 )
    {
      v4 = v26;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xACE,
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v17);
      v4 = v26;
      if ( v26 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v26,
          0);
        v4 = v26;
        pvData = 0;
      }
      v18 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0);
      v9 = v18;
      if ( (v18 & 0xFFFFFFFD) != 0 )
      {
        if ( v18 > 0 )
          v9 = (unsigned __int16)v18 | 0x80070000;
        if ( (v9 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xADB,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v9,
            phkResult);
        if ( !v4 )
          goto LABEL_45;
        goto LABEL_43;
      }
    }
  }
  if ( !v4 )
  {
    ProfileListKeyNameFromSid = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                  lpSubKey,
                                  L".bak",
                                  4);
    v9 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      v10 = 2786;
      goto LABEL_36;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v26,
      0);
    v11 = lpSubKey[0];
    v20 = CUserProfile::OpenProfileListKey(v19, lpSubKey[0], &v26, &pvData);
    v9 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v20,
        phkResult);
      v21 = v26;
      if ( !v26 )
        goto LABEL_45;
      goto LABEL_44;
    }
    v4 = v26;
    if ( v26 )
    {
      v22 = RegRenameKey(v26, 0, a2);
      if ( v22 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xAEA,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
               (const char *)v22,
               phkResult);
LABEL_43:
        v21 = v4;
LABEL_44:
        RegCloseKey(v21);
        goto LABEL_45;
      }
      pcbData = v11;
      ProfileTelemetry::ProfileListBackupKeyRestored<unsigned short const *>(&pcbData);
      pvData &= ~0x8000u;
      v24 = SHRegSetDWORD(v4, 0, L"State", pvData);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF0,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v24);
    }
  }
  *a3 = v4;
  if ( a4 )
    *a4 = pvData;
  if ( v11 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v11);
  return 0;
}

```

## disassembly

```asm
0x18001ecc4  mov     [rsp-38h+arg_8], rbx
0x18001ecc9  mov     [rsp-38h+arg_0], rcx
0x18001ecce  push    rbp
0x18001eccf  push    rsi
0x18001ecd0  push    rdi
0x18001ecd1  push    r12
0x18001ecd3  push    r13
0x18001ecd5  push    r14
0x18001ecd7  push    r15
0x18001ecd9  mov     rbp, rsp
0x18001ecdc  sub     rsp, 70h
0x18001ece0  xor     ebx, ebx
0x18001ece2  mov     r15, r9
0x18001ece5  mov     [r8], rbx
0x18001ece8  mov     r13, r8
0x18001eceb  mov     r12, rdx
0x18001ecee  test    r9, r9
0x18001ecf1  jz      short loc_18001ECF6
0x18001ecf3  mov     [r9], ebx
0x18001ecf6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ecfa  mov     [rbp+lpSubKey], rbx
0x18001ecfe  xor     r8d, r8d; int *
0x18001ed01  mov     [rbp+var_18], rax
0x18001ed05  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18001ed09  mov     [rbp+var_10], rax
0x18001ed0d  mov     rcx, r12; lpString1
0x18001ed10  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18001ed15  mov     edi, eax
0x18001ed17  test    eax, eax
0x18001ed19  jns     short loc_18001ED2C
0x18001ed1b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ed22  mov     edx, 0AC0h
0x18001ed27  jmp     loc_18001EF3A
0x18001ed2c  mov     r14, [rbp+lpSubKey]
0x18001ed30  lea     rax, [rbp+hKey]
0x18001ed34  mov     rdx, r14; lpSubKey
0x18001ed37  mov     [rbp+var_30], rbx
0x18001ed3b  mov     r9d, 0F003Fh; samDesired
0x18001ed41  mov     [rbp+arg_10], ebx
0x18001ed44  xor     r8d, r8d; ulOptions
0x18001ed47  mov     [rbp+hKey], rbx
0x18001ed4b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ed52  mov     [rsp+70h+phkResult], rax; int
0x18001ed57  call    cs:__imp_RegOpenKeyExW
0x18001ed5d  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ed64  cmp     eax, 2
0x18001ed67  jz      loc_18001EE1F
0x18001ed6d  test    eax, eax
0x18001ed6f  jz      short loc_18001EDC8
0x18001ed71  mov     rcx, [rbp+38h]; this
0x18001ed75  mov     r9d, eax; char *
0x18001ed78  mov     r8, rsi; unsigned int
0x18001ed7b  mov     edx, 0B1Fh; void *
0x18001ed80  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ed85  mov     rcx, [rbp+hKey]; hKey
0x18001ed89  mov     edi, eax
0x18001ed8b  test    rcx, rcx
0x18001ed8e  jz      short loc_18001ED96
0x18001ed90  call    cs:__imp_RegCloseKey
0x18001ed96  test    edi, edi
0x18001ed98  jns     loc_18001EE2E
0x18001ed9e  mov     rcx, [rbp+38h]; this
0x18001eda2  mov     r9d, edi; char *
0x18001eda5  mov     r8, rsi; unsigned int
0x18001eda8  mov     edx, 0AC4h; void *
0x18001edad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001edb2  test    r14, r14
0x18001edb5  jz      loc_18001EFD6
0x18001edbb  mov     rcx, r14
0x18001edbe  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001edc3  jmp     loc_18001EFD6
0x18001edc8  mov     rcx, [rbp+hKey]; hkey
0x18001edcc  lea     rax, [rbp+arg_18]
0x18001edd0  mov     [rsp+70h+pcbData], rax; pcbData
0x18001edd5  lea     r8, aState; "State"
0x18001eddc  lea     rax, [rbp+arg_10]
0x18001ede0  mov     dword ptr [rbp+arg_18], 4
0x18001ede7  mov     [rsp+70h+pvData], rax; pvData
0x18001edec  mov     r9d, 10h; dwFlags
0x18001edf2  xor     edx, edx; lpSubKey
0x18001edf4  mov     [rsp+70h+phkResult], rbx; pdwType
0x18001edf9  call    cs:__imp_RegGetValueW
0x18001edff  test    eax, eax
0x18001ee01  jle     short loc_18001EE0D
0x18001ee03  movzx   eax, ax
0x18001ee06  or      eax, 80070000h
0x18001ee0b  test    eax, eax
0x18001ee0d  js      short loc_18001EE1F
0x18001ee0f  mov     rbx, [rbp+hKey]
0x18001ee13  xor     ecx, ecx
0x18001ee15  mov     [rbp+hKey], rcx
0x18001ee19  mov     [rbp+var_30], rbx
0x18001ee1d  jmp     short loc_18001EE23
0x18001ee1f  mov     rcx, [rbp+hKey]; hKey
0x18001ee23  test    rcx, rcx
0x18001ee26  jz      short loc_18001EE2E
0x18001ee28  call    cs:__imp_RegCloseKey
0x18001ee2e  test    [rbp+arg_10], 880h
0x18001ee35  mov     dword ptr [rbp+arg_18], 0
0x18001ee3c  jz      loc_18001EF0F
0x18001ee42  lea     rcx, [rbp+arg_18]; int *
0x18001ee46  call    ?GetMachineRole@@YAHPEAH@Z; GetMachineRole(int *)
0x18001ee4b  test    eax, eax
0x18001ee4d  jz      loc_18001EF0F
0x18001ee53  cmp     dword ptr [rbp+arg_18], 0
0x18001ee57  jz      loc_18001EF0F
0x18001ee5d  mov     ebx, [rbp+arg_10]
0x18001ee60  lea     rcx, [rbp+var_30]
0x18001ee64  xor     edx, edx
0x18001ee66  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ee6b  mov     rcx, [rbp+arg_0]; this
0x18001ee6f  lea     r8, [rbp+var_30]; HKEY *
0x18001ee73  mov     r9d, ebx; unsigned int
0x18001ee76  mov     rdx, r12; unsigned __int16 *
0x18001ee79  call    ?CleanupProfileFromKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@K@Z; CUserProfile::CleanupProfileFromKey(ushort const *,HKEY__ * *,ulong)
0x18001ee7e  test    eax, eax
0x18001ee80  jns     loc_18001EF0B
0x18001ee86  mov     rcx, [rbp+38h]; this
0x18001ee8a  mov     r9d, eax; char *
0x18001ee8d  mov     r8, rsi; unsigned int
0x18001ee90  mov     edx, 0ACEh; void *
0x18001ee95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ee9a  mov     rbx, [rbp+var_30]
0x18001ee9e  test    rbx, rbx
0x18001eea1  jz      short loc_18001EEB9
0x18001eea3  xor     edx, edx
0x18001eea5  lea     rcx, [rbp+var_30]
0x18001eea9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001eeae  mov     rbx, [rbp+var_30]
0x18001eeb2  mov     [rbp+arg_10], 0
0x18001eeb9  xor     r9d, r9d; Reserved
0x18001eebc  xor     r8d, r8d; samDesired
0x18001eebf  mov     rdx, r14; lpSubKey
0x18001eec2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eec9  call    cs:__imp_RegDeleteKeyExW
0x18001eecf  mov     edi, eax
0x18001eed1  test    eax, 0FFFFFFFDh
0x18001eed6  jz      short loc_18001EF0F
0x18001eed8  test    eax, eax
0x18001eeda  jle     short loc_18001EEE5
0x18001eedc  movzx   edi, ax
0x18001eedf  or      edi, 80070000h
0x18001eee5  test    edi, edi
0x18001eee7  jns     short loc_18001EEFD
0x18001eee9  mov     rcx, [rbp+38h]; this
0x18001eeed  mov     r9d, edi; char *
0x18001eef0  mov     r8, rsi; unsigned int
0x18001eef3  mov     edx, 0ADBh; void *
0x18001eef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eefd  test    rbx, rbx
0x18001ef00  jnz     loc_18001EFC4
0x18001ef06  jmp     loc_18001EFCD
0x18001ef0b  mov     rbx, [rbp+var_30]
0x18001ef0f  test    rbx, rbx
0x18001ef12  jnz     loc_18001F01D
0x18001ef18  lea     r8d, [rbx+4]
0x18001ef1c  lea     rdx, ?c_szBAK@@3QBGB; ".bak"
0x18001ef23  lea     rcx, [rbp+lpSubKey]
0x18001ef27  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001ef2c  mov     edi, eax
0x18001ef2e  test    eax, eax
0x18001ef30  jns     short loc_18001EF4B
0x18001ef32  mov     r8, rsi; unsigned int
0x18001ef35  mov     edx, 0AE2h; void *
0x18001ef3a  mov     rcx, [rbp+38h]; this
0x18001ef3e  mov     r9d, eax; char *
0x18001ef41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef46  jmp     loc_18001EFCD
0x18001ef4b  xor     edx, edx
0x18001ef4d  lea     rcx, [rbp+var_30]
0x18001ef51  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ef56  mov     r14, [rbp+lpSubKey]
0x18001ef5a  lea     r9, [rbp+arg_10]; unsigned int *
0x18001ef5e  mov     rdx, r14; unsigned __int16 *
0x18001ef61  lea     r8, [rbp+var_30]; HKEY *
0x18001ef65  call    ?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)
0x18001ef6a  mov     edi, eax
0x18001ef6c  test    eax, eax
0x18001ef6e  jns     short loc_18001EF8F
0x18001ef70  mov     rcx, [rbp+38h]; this
0x18001ef74  mov     r9d, eax; char *
0x18001ef77  mov     r8, rsi; unsigned int
0x18001ef7a  mov     edx, 0AE4h; void *
0x18001ef7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef84  mov     rcx, [rbp+var_30]
0x18001ef88  test    rcx, rcx
0x18001ef8b  jnz     short loc_18001EFC7
0x18001ef8d  jmp     short loc_18001EFCD
0x18001ef8f  mov     rbx, [rbp+var_30]
0x18001ef93  test    rbx, rbx
0x18001ef96  jz      loc_18001F01D
0x18001ef9c  mov     r8, r12; lpNewKeyName
0x18001ef9f  xor     edx, edx; lpSubKeyName
0x18001efa1  mov     rcx, rbx; hKey
0x18001efa4  call    cs:__imp_RegRenameKey
0x18001efaa  test    eax, eax
0x18001efac  jz      short loc_18001EFDA
0x18001efae  mov     rcx, [rbp+38h]; this
0x18001efb2  mov     r9d, eax; char *
0x18001efb5  mov     r8, rsi; unsigned int
0x18001efb8  mov     edx, 0AEAh; void *
0x18001efbd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001efc2  mov     edi, eax
0x18001efc4  mov     rcx, rbx; hKey
0x18001efc7  call    cs:__imp_RegCloseKey
0x18001efcd  lea     rcx, [rbp+lpSubKey]
0x18001efd1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001efd6  mov     eax, edi
0x18001efd8  jmp     short loc_18001F03B
0x18001efda  lea     rcx, [rbp+arg_18]
0x18001efde  mov     [rbp+arg_18], r14
0x18001efe2  call    ??$ProfileListBackupKeyRestored@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::ProfileListBackupKeyRestored<ushort const *>(ushort const * &&)
0x18001efe7  mov     r9d, [rbp+arg_10]
0x18001efeb  lea     r8, aState; "State"
0x18001eff2  btr     r9d, 0Fh; unsigned int
0x18001eff7  xor     edx, edx; unsigned __int16 *
0x18001eff9  mov     rcx, rbx; HKEY
0x18001effc  mov     [rbp+arg_10], r9d
0x18001f000  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001f005  test    eax, eax
0x18001f007  jns     short loc_18001F01D
0x18001f009  mov     rcx, [rbp+38h]; this
0x18001f00d  mov     r9d, eax; char *
0x18001f010  mov     r8, rsi; unsigned int
0x18001f013  mov     edx, 0AF0h; void *
0x18001f018  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f01d  mov     [r13+0], rbx
0x18001f021  test    r15, r15
0x18001f024  jz      short loc_18001F02C
0x18001f026  mov     eax, [rbp+arg_10]
0x18001f029  mov     [r15], eax
0x18001f02c  test    r14, r14
0x18001f02f  jz      short loc_18001F039
0x18001f031  mov     rcx, r14
0x18001f034  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001f039  xor     eax, eax
0x18001f03b  mov     rbx, [rsp+70h+arg_8]
0x18001f043  add     rsp, 70h
0x18001f047  pop     r15
0x18001f049  pop     r14
0x18001f04b  pop     r13
0x18001f04d  pop     r12
0x18001f04f  pop     rdi
0x18001f050  pop     rsi
0x18001f051  pop     rbp
0x18001f052  retn
```
