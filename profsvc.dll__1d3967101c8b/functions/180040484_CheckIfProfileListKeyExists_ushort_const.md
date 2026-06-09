# _CheckIfProfileListKeyExists(ushort const *)

- ea: `0x180040484`
- end: `0x180040666`
- name: `?_CheckIfProfileListKeyExists@@YAJPEBG@Z`
- size: `482`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ed00`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x180016680`
- `0x18001f060`
- `0x18002d2d8`
- `0x180040484`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040648`

## string_xrefs

- `0x18004054f`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x1800405af`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180040622`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

## pseudocode

```c
__int64 __fastcall _CheckIfProfileListKeyExists(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  HKEY v17; // [rsp+70h] [rbp+20h] BYREF

  lpSubKey = 0;
  v13 = 0;
  v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v13 = -1;
  v14 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    v4 = 13;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
    goto LABEL_32;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v3 = v5;
  if ( !v5 )
  {
    v6 = hKey;
LABEL_5:
    if ( v6 )
      RegCloseKey(v6);
    v3 = -2147024713;
    goto LABEL_32;
  }
  if ( v5 != 2 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v3,
        phkResult);
    v7 = hKey;
LABEL_14:
    if ( v7 )
      RegCloseKey(v7);
    goto LABEL_32;
  }
  if ( hKey )
    RegCloseKey(hKey);
  ProfileListKeyNameFromSid = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                &lpSubKey,
                                L".bak",
                                4);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    v4 = 23;
    goto LABEL_20;
  }
  v17 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v17,
    0);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &v17);
  v3 = v8;
  if ( !v8 )
  {
    v6 = v17;
    goto LABEL_5;
  }
  if ( v8 != 2 )
  {
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    if ( v3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
        (const char *)(unsigned int)v3,
        phkResulta);
    v7 = v17;
    goto LABEL_14;
  }
  if ( v17 )
    RegCloseKey(v17);
  v3 = 0;
LABEL_32:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180040484  mov     [rsp-8+arg_0], rbx
0x180040489  push    rbp
0x18004048a  mov     rbp, rsp
0x18004048d  sub     rsp, 50h
0x180040491  mov     rbx, rcx
0x180040494  mov     [rbp+lpSubKey], 0
0x18004049c  lea     rcx, [rbp+lpSubKey]
0x1800404a0  mov     [rbp+var_18], 0
0x1800404a8  mov     [rbp+var_10], 0
0x1800404b0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800404b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800404b9  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x1800404bd  xor     r8d, r8d; int *
0x1800404c0  mov     [rbp+var_18], rax
0x1800404c4  mov     rcx, rbx; lpString1
0x1800404c7  mov     [rbp+var_10], rax
0x1800404cb  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800404d0  mov     ebx, eax
0x1800404d2  test    eax, eax
0x1800404d4  jns     short loc_1800404E0
0x1800404d6  mov     edx, 0Dh
0x1800404db  jmp     loc_1800405AB
0x1800404e0  xor     edx, edx
0x1800404e2  mov     [rbp+hKey], 0
0x1800404ea  lea     rcx, [rbp+hKey]
0x1800404ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800404f3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800404f7  lea     rax, [rbp+hKey]
0x1800404fb  mov     r9d, 20019h; samDesired
0x180040501  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180040506  xor     r8d, r8d; ulOptions
0x180040509  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040510  call    cs:__imp_RegOpenKeyExW
0x180040516  mov     ebx, eax
0x180040518  test    eax, eax
0x18004051a  jnz     short loc_180040535
0x18004051c  mov     rcx, [rbp+hKey]; hKey
0x180040520  test    rcx, rcx
0x180040523  jz      short loc_18004052B
0x180040525  call    cs:__imp_RegCloseKey
0x18004052b  mov     ebx, 800700B7h
0x180040530  jmp     loc_180040650
0x180040535  cmp     eax, 2
0x180040538  jz      short loc_18004057B
0x18004053a  test    eax, eax
0x18004053c  jle     short loc_180040547
0x18004053e  movzx   ebx, ax
0x180040541  or      ebx, 80070000h
0x180040547  test    ebx, ebx
0x180040549  jns     short loc_180040563
0x18004054b  mov     rcx, [rbp+8]; this
0x18004054f  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180040556  mov     r9d, ebx; char *
0x180040559  mov     edx, 13h; void *
0x18004055e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040563  mov     rcx, [rbp+hKey]; hKey
0x180040567  test    rcx, rcx
0x18004056a  jz      loc_180040650
0x180040570  call    cs:__imp_RegCloseKey
0x180040576  jmp     loc_180040650
0x18004057b  mov     rcx, [rbp+hKey]; hKey
0x18004057f  test    rcx, rcx
0x180040582  jz      short loc_18004058A
0x180040584  call    cs:__imp_RegCloseKey
0x18004058a  mov     r8d, 4
0x180040590  lea     rdx, ?c_szBAK@@3QBGB; ".bak"
0x180040597  lea     rcx, [rbp+lpSubKey]
0x18004059b  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800405a0  mov     ebx, eax
0x1800405a2  test    eax, eax
0x1800405a4  jns     short loc_1800405C3
0x1800405a6  mov     edx, 17h; void *
0x1800405ab  mov     rcx, [rbp+8]; this
0x1800405af  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800405b6  mov     r9d, eax; char *
0x1800405b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800405be  jmp     loc_180040650
0x1800405c3  xor     edx, edx
0x1800405c5  mov     [rbp+arg_10], 0
0x1800405cd  lea     rcx, [rbp+arg_10]
0x1800405d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800405d6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800405da  lea     rax, [rbp+arg_10]
0x1800405de  mov     r9d, 20019h; samDesired
0x1800405e4  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800405e9  xor     r8d, r8d; ulOptions
0x1800405ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800405f3  call    cs:__imp_RegOpenKeyExW
0x1800405f9  mov     ebx, eax
0x1800405fb  test    eax, eax
0x1800405fd  jnz     short loc_180040608
0x1800405ff  mov     rcx, [rbp+arg_10]
0x180040603  jmp     loc_180040520
0x180040608  cmp     eax, 2
0x18004060b  jz      short loc_18004063F
0x18004060d  test    eax, eax
0x18004060f  jle     short loc_18004061A
0x180040611  movzx   ebx, ax
0x180040614  or      ebx, 80070000h
0x18004061a  test    ebx, ebx
0x18004061c  jns     short loc_180040636
0x18004061e  mov     rcx, [rbp+8]; this
0x180040622  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180040629  mov     r9d, ebx; char *
0x18004062c  mov     edx, 1Dh; void *
0x180040631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040636  mov     rcx, [rbp+arg_10]
0x18004063a  jmp     loc_180040567
0x18004063f  mov     rcx, [rbp+arg_10]; hKey
0x180040643  test    rcx, rcx
0x180040646  jz      short loc_18004064E
0x180040648  call    cs:__imp_RegCloseKey
0x18004064e  xor     ebx, ebx
0x180040650  lea     rcx, [rbp+lpSubKey]
0x180040654  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180040659  mov     eax, ebx
0x18004065b  mov     rbx, [rsp+50h+arg_0]
0x180040660  add     rsp, 50h
0x180040664  pop     rbp
0x180040665  retn
```
