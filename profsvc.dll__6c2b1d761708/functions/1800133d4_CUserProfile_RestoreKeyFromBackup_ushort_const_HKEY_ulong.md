# CUserProfile::RestoreKeyFromBackup(ushort const *,HKEY__ * *,ulong *)

- ea: `0x1800133d4`
- end: `0x180013769`
- name: `?RestoreKeyFromBackup@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `917`
- prototype: `int(CUserProfile *__hidden this, const unsigned __int16 *, HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180013838`
- `0x180037544`

## callees

- `0x18000b060`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x1800133d4`
- `0x180013770`
- `0x180014b4c`
- `0x180017520`
- `0x180026d30`
- `0x180030ad0`
- `0x180031060`
- `0x180034e10`
- `0x180040bcc`
- `0x180044588`
- `0x180045614`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013479`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001350c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001350c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800135ed`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800135ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013541`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x1800136b3`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x1800136b3`

## string_xrefs

- `0x180013432`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180013485`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::RestoreKeyFromBackup(
        CUserProfile *this,
        const unsigned __int16 *a2,
        HKEY *a3,
        unsigned int *a4)
{
  CUserProfile *v7; // rdi
  int ProfileListKeyNameFromSid; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // r14
  HKEY v11; // rbx
  unsigned int v12; // eax
  signed int v13; // edi
  LSTATUS ValueW; // eax
  bool v15; // sf
  HKEY v16; // rcx
  unsigned int v17; // ebx
  int v18; // eax
  LSTATUS v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  CUserProfile *v22; // rcx
  unsigned int v23; // eax
  int v25; // eax
  int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int pvData; // [rsp+C0h] [rbp+50h] BYREF
  const WCHAR *pcbData; // [rsp+C8h] [rbp+58h] BYREF

  *a3 = 0;
  v7 = this;
  if ( a4 )
    *a4 = 0;
  lpSubKey[0] = 0;
  lpSubKey[1] = (LPCWSTR)-1LL;
  lpSubKey[2] = (LPCWSTR)-1LL;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a2, (unsigned __int16 **)lpSubKey, 0);
  v9 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC0,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    return v9;
  }
  v10 = lpSubKey[0];
  v11 = 0;
  pvData = 0;
  hKey = 0;
  hkey = 0;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &hkey);
  if ( v12 == 2 )
    goto LABEL_14;
  if ( !v12 )
  {
    LODWORD(pcbData) = 4;
    ValueW = RegGetValueW(hkey, 0, L"State", 0x10u, 0, &pvData, (LPDWORD)&pcbData);
    v15 = ValueW < 0;
    if ( ValueW > 0 )
      v15 = 1;
    if ( !v15 )
    {
      v11 = hkey;
      v16 = 0;
      hkey = 0;
      hKey = v11;
      goto LABEL_15;
    }
LABEL_14:
    v16 = hkey;
LABEL_15:
    if ( v16 )
      RegCloseKey(v16);
    goto LABEL_18;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xB1F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v12,
          phkResulta);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v13,
      phkResulta);
LABEL_9:
    v9 = v13;
    goto LABEL_41;
  }
  v7 = this;
LABEL_18:
  LODWORD(pcbData) = 0;
  if ( (pvData & 0x880) != 0 && (unsigned int)GetMachineRole((int *)&pcbData) && (_DWORD)pcbData )
  {
    v17 = pvData;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v18 = CUserProfile::CleanupProfileFromKey(v7, a2, &hKey, v17);
    if ( v18 >= 0 )
    {
      v11 = hKey;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xACE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v18,
        phkResulta);
      v11 = hKey;
      if ( hKey )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v11 = hKey;
        pvData = 0;
      }
      v19 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0);
      v13 = v19;
      if ( (v19 & 0xFFFFFFFD) != 0 )
      {
        if ( v19 > 0 )
          v13 = (unsigned __int16)v19 | 0x80070000;
        if ( v13 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xADB,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v13,
            phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_9;
      }
    }
  }
  if ( !v11 )
  {
    v20 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
            lpSubKey,
            L".bak",
            4);
    v9 = v20;
    if ( v20 < 0 )
    {
      v21 = 2786;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v20,
        phkResulta);
LABEL_40:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_41;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = lpSubKey[0];
    v20 = CUserProfile::OpenProfileListKey(v22, lpSubKey[0], &hKey, &pvData);
    v9 = v20;
    if ( v20 < 0 )
    {
      v21 = 2788;
      goto LABEL_34;
    }
    v11 = hKey;
    if ( hKey )
    {
      v23 = RegRenameKey(hKey, 0, a2);
      if ( v23 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xAEA,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
               (const char *)v23,
               phkResulta);
        goto LABEL_40;
      }
      pcbData = v10;
      ProfileTelemetry::ProfileListBackupKeyRestored<unsigned short const *>(&pcbData);
      pvData &= ~0x8000u;
      v25 = SHRegSetDWORD(v11, 0, L"State", pvData);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF0,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v25,
          phkResulta);
    }
  }
  *a3 = v11;
  if ( a4 )
    *a4 = pvData;
  if ( v10 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v10);
  return 0;
}

```

## disassembly

```asm
0x1800133d4  mov     [rsp-38h+arg_8], rbx
0x1800133d9  mov     [rsp-38h+arg_0], rcx
0x1800133de  push    rbp
0x1800133df  push    rsi
0x1800133e0  push    rdi
0x1800133e1  push    r12
0x1800133e3  push    r13
0x1800133e5  push    r14
0x1800133e7  push    r15
0x1800133e9  mov     rbp, rsp
0x1800133ec  sub     rsp, 70h
0x1800133f0  xor     esi, esi
0x1800133f2  mov     r15, r9
0x1800133f5  mov     [r8], rsi
0x1800133f8  mov     r13, r8
0x1800133fb  mov     r12, rdx
0x1800133fe  mov     rdi, rcx
0x180013401  test    r9, r9
0x180013404  jz      short loc_180013409
0x180013406  mov     [r9], esi
0x180013409  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001340d  mov     [rbp+lpSubKey], rsi
0x180013411  xor     r8d, r8d; int *
0x180013414  mov     [rbp+var_18], rax
0x180013418  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18001341c  mov     [rbp+var_10], rax
0x180013420  mov     rcx, r12; lpString1
0x180013423  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180013428  mov     ebx, eax
0x18001342a  test    eax, eax
0x18001342c  jns     short loc_18001344B
0x18001342e  mov     rcx, [rbp+38h]; this
0x180013432  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013439  mov     r9d, eax; char *
0x18001343c  mov     edx, 0AC0h; void *
0x180013441  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013446  jmp     loc_1800136E2
0x18001344b  mov     r14, [rbp+lpSubKey]
0x18001344f  lea     rax, [rbp+hkey]
0x180013453  mov     rbx, rsi
0x180013456  mov     [rbp+arg_10], esi
0x180013459  mov     rdx, r14; lpSubKey
0x18001345c  mov     [rbp+hKey], rbx
0x180013460  mov     r9d, 0F003Fh; samDesired
0x180013466  mov     [rbp+hkey], rsi
0x18001346a  xor     r8d, r8d; ulOptions
0x18001346d  mov     [rsp+70h+phkResult], rax; int
0x180013472  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013479  call    cs:__imp_RegOpenKeyExW
0x180013480  nop     dword ptr [rax+rax+00h]
0x180013485  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001348c  cmp     eax, 2
0x18001348f  jz      loc_180013538
0x180013495  test    eax, eax
0x180013497  jz      short loc_1800134DB
0x180013499  mov     rcx, [rbp+38h]; this
0x18001349d  mov     r9d, eax; char *
0x1800134a0  mov     r8, rsi; unsigned int
0x1800134a3  mov     edx, 0B1Fh; void *
0x1800134a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800134ad  lea     rcx, [rbp+hkey]
0x1800134b1  mov     edi, eax
0x1800134b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800134b8  test    edi, edi
0x1800134ba  jns     loc_18001354F
0x1800134c0  mov     rcx, [rbp+38h]; this
0x1800134c4  mov     r9d, edi; char *
0x1800134c7  mov     r8, rsi; unsigned int
0x1800134ca  mov     edx, 0AC4h; void *
0x1800134cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134d4  mov     ebx, edi
0x1800134d6  jmp     loc_1800136E2
0x1800134db  mov     rcx, [rbp+hkey]; hkey
0x1800134df  lea     rax, [rbp+arg_18]
0x1800134e3  mov     [rsp+70h+pcbData], rax; pcbData
0x1800134e8  lea     r8, aState; "State"
0x1800134ef  lea     rax, [rbp+arg_10]
0x1800134f3  mov     dword ptr [rbp+arg_18], 4
0x1800134fa  mov     [rsp+70h+pvData], rax; pvData
0x1800134ff  mov     r9d, 10h; dwFlags
0x180013505  xor     edx, edx; lpSubKey
0x180013507  mov     [rsp+70h+phkResult], rbx; pdwType
0x18001350c  call    cs:__imp_RegGetValueW
0x180013513  nop     dword ptr [rax+rax+00h]
0x180013518  test    eax, eax
0x18001351a  jle     short loc_180013526
0x18001351c  movzx   eax, ax
0x18001351f  or      eax, 80070000h
0x180013524  test    eax, eax
0x180013526  js      short loc_180013538
0x180013528  mov     rbx, [rbp+hkey]
0x18001352c  xor     ecx, ecx
0x18001352e  mov     [rbp+hkey], rcx
0x180013532  mov     [rbp+hKey], rbx
0x180013536  jmp     short loc_18001353C
0x180013538  mov     rcx, [rbp+hkey]; hKey
0x18001353c  test    rcx, rcx
0x18001353f  jz      short loc_180013553
0x180013541  call    cs:__imp_RegCloseKey
0x180013548  nop     dword ptr [rax+rax+00h]
0x18001354d  jmp     short loc_180013553
0x18001354f  mov     rdi, [rbp+arg_0]
0x180013553  test    [rbp+arg_10], 880h
0x18001355a  mov     dword ptr [rbp+arg_18], 0
0x180013561  jz      loc_180013639
0x180013567  lea     rcx, [rbp+arg_18]; int *
0x18001356b  call    ?GetMachineRole@@YAHPEAH@Z; GetMachineRole(int *)
0x180013570  test    eax, eax
0x180013572  jz      loc_180013639
0x180013578  cmp     dword ptr [rbp+arg_18], 0
0x18001357c  jz      loc_180013639
0x180013582  mov     ebx, [rbp+arg_10]
0x180013585  lea     rcx, [rbp+hKey]
0x180013589  xor     edx, edx
0x18001358b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013590  mov     r9d, ebx; unsigned int
0x180013593  lea     r8, [rbp+hKey]; HKEY *
0x180013597  mov     rdx, r12; unsigned __int16 *
0x18001359a  mov     rcx, rdi; this
0x18001359d  call    ?CleanupProfileFromKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@K@Z; CUserProfile::CleanupProfileFromKey(ushort const *,HKEY__ * *,ulong)
0x1800135a2  test    eax, eax
0x1800135a4  jns     loc_180013635
0x1800135aa  mov     rcx, [rbp+38h]; this
0x1800135ae  mov     r9d, eax; char *
0x1800135b1  mov     r8, rsi; unsigned int
0x1800135b4  mov     edx, 0ACEh; void *
0x1800135b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800135be  mov     rbx, [rbp+hKey]
0x1800135c2  test    rbx, rbx
0x1800135c5  jz      short loc_1800135DD
0x1800135c7  xor     edx, edx
0x1800135c9  lea     rcx, [rbp+hKey]
0x1800135cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800135d2  mov     rbx, [rbp+hKey]
0x1800135d6  mov     [rbp+arg_10], 0
0x1800135dd  xor     r9d, r9d; Reserved
0x1800135e0  xor     r8d, r8d; samDesired
0x1800135e3  mov     rdx, r14; lpSubKey
0x1800135e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800135ed  call    cs:__imp_RegDeleteKeyExW
0x1800135f4  nop     dword ptr [rax+rax+00h]
0x1800135f9  mov     edi, eax
0x1800135fb  test    eax, 0FFFFFFFDh
0x180013600  jz      short loc_180013639
0x180013602  test    eax, eax
0x180013604  jle     short loc_18001360F
0x180013606  movzx   edi, ax
0x180013609  or      edi, 80070000h
0x18001360f  test    edi, edi
0x180013611  jns     short loc_180013627
0x180013613  mov     rcx, [rbp+38h]; this
0x180013617  mov     r9d, edi; char *
0x18001361a  mov     r8, rsi; unsigned int
0x18001361d  mov     edx, 0ADBh; void *
0x180013622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013627  lea     rcx, [rbp+hKey]
0x18001362b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013630  jmp     loc_1800134D4
0x180013635  mov     rbx, [rbp+hKey]
0x180013639  test    rbx, rbx
0x18001363c  jnz     loc_180013732
0x180013642  lea     r8d, [rbx+4]
0x180013646  lea     rdx, ?c_szBAK@@3QBGB; ".bak"
0x18001364d  lea     rcx, [rbp+lpSubKey]
0x180013651  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180013656  mov     ebx, eax
0x180013658  test    eax, eax
0x18001365a  jns     short loc_180013672
0x18001365c  mov     edx, 0AE2h; void *
0x180013661  mov     rcx, [rbp+38h]; this
0x180013665  mov     r8, rsi; unsigned int
0x180013668  mov     r9d, eax; char *
0x18001366b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013670  jmp     short loc_1800136D9
0x180013672  xor     edx, edx
0x180013674  lea     rcx, [rbp+hKey]
0x180013678  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001367d  mov     r14, [rbp+lpSubKey]
0x180013681  lea     r9, [rbp+arg_10]; unsigned int *
0x180013685  mov     rdx, r14; unsigned __int16 *
0x180013688  lea     r8, [rbp+hKey]; HKEY *
0x18001368c  call    ?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z; CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)
0x180013691  mov     ebx, eax
0x180013693  test    eax, eax
0x180013695  jns     short loc_18001369E
0x180013697  mov     edx, 0AE4h
0x18001369c  jmp     short loc_180013661
0x18001369e  mov     rbx, [rbp+hKey]
0x1800136a2  test    rbx, rbx
0x1800136a5  jz      loc_180013732
0x1800136ab  mov     r8, r12; lpNewKeyName
0x1800136ae  xor     edx, edx; lpSubKeyName
0x1800136b0  mov     rcx, rbx; hKey
0x1800136b3  call    cs:__imp_RegRenameKey
0x1800136ba  nop     dword ptr [rax+rax+00h]
0x1800136bf  test    eax, eax
0x1800136c1  jz      short loc_1800136EF
0x1800136c3  mov     rcx, [rbp+38h]; this
0x1800136c7  mov     r9d, eax; char *
0x1800136ca  mov     r8, rsi; unsigned int
0x1800136cd  mov     edx, 0AEAh; void *
0x1800136d2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800136d7  mov     ebx, eax
0x1800136d9  lea     rcx, [rbp+hKey]
0x1800136dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800136e2  lea     rcx, [rbp+lpSubKey]
0x1800136e6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800136eb  mov     eax, ebx
0x1800136ed  jmp     short loc_180013750
0x1800136ef  lea     rcx, [rbp+arg_18]
0x1800136f3  mov     [rbp+arg_18], r14
0x1800136f7  call    ??$ProfileListBackupKeyRestored@PEBG@ProfileTelemetry@@SAX$$QEAPEBG@Z; ProfileTelemetry::ProfileListBackupKeyRestored<ushort const *>(ushort const * &&)
0x1800136fc  mov     r9d, [rbp+arg_10]
0x180013700  lea     r8, aState; "State"
0x180013707  btr     r9d, 0Fh; unsigned int
0x18001370c  xor     edx, edx; unsigned __int16 *
0x18001370e  mov     rcx, rbx; HKEY
0x180013711  mov     [rbp+arg_10], r9d
0x180013715  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001371a  test    eax, eax
0x18001371c  jns     short loc_180013732
0x18001371e  mov     rcx, [rbp+38h]; this
0x180013722  mov     r9d, eax; char *
0x180013725  mov     r8, rsi; unsigned int
0x180013728  mov     edx, 0AF0h; void *
0x18001372d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013732  mov     [r13+0], rbx
0x180013736  test    r15, r15
0x180013739  jz      short loc_180013741
0x18001373b  mov     eax, [rbp+arg_10]
0x18001373e  mov     [r15], eax
0x180013741  test    r14, r14
0x180013744  jz      short loc_18001374E
0x180013746  mov     rcx, r14
0x180013749  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001374e  xor     eax, eax
0x180013750  mov     rbx, [rsp+70h+arg_8]
0x180013758  add     rsp, 70h
0x18001375c  pop     r15
0x18001375e  pop     r14
0x180013760  pop     r13
0x180013762  pop     r12
0x180013764  pop     rdi
0x180013765  pop     rsi
0x180013766  pop     rbp
0x180013767  retn
```
