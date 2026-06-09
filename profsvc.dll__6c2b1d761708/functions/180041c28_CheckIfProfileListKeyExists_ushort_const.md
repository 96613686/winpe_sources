# _CheckIfProfileListKeyExists(ushort const *)

- ea: `0x180041c28`
- end: `0x180041dfb`
- name: `?_CheckIfProfileListKeyExists@@YAJPEBG@Z`
- size: `467`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180030050`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180017520`
- `0x180030ad0`
- `0x180041c28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041d87`

## string_xrefs

- `0x180041cf3`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180041d43`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180041dbc`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

## pseudocode

```c
__int64 __fastcall _CheckIfProfileListKeyExists(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  LSTATUS v5; // eax
  HKEY *v6; // rcx
  HKEY *v7; // rcx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY v16; // [rsp+68h] [rbp+18h] BYREF
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
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
    goto LABEL_25;
  }
  v16 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v16,
    0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &v16);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
      ProfileListKeyNameFromSid = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                    &lpSubKey,
                                    L".bak",
                                    4);
      v3 = ProfileListKeyNameFromSid;
      if ( ProfileListKeyNameFromSid < 0 )
      {
        v4 = 23;
        goto LABEL_15;
      }
      v17 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v17,
        0);
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &v17);
      v3 = v8;
      if ( !v8 )
      {
        v6 = &v17;
        goto LABEL_5;
      }
      if ( v8 == 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
        v3 = 0;
        goto LABEL_25;
      }
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( v3 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
          (const char *)(unsigned int)v3,
          phkResulta);
      v7 = &v17;
    }
    else
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
      v7 = &v16;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v7);
    goto LABEL_25;
  }
  v6 = &v16;
LABEL_5:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v6);
  v3 = -2147024713;
LABEL_25:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180041c28  mov     [rsp-8+arg_0], rbx
0x180041c2d  push    rbp
0x180041c2e  mov     rbp, rsp
0x180041c31  sub     rsp, 50h
0x180041c35  mov     rbx, rcx
0x180041c38  mov     [rbp+lpSubKey], 0
0x180041c40  lea     rcx, [rbp+lpSubKey]
0x180041c44  mov     [rbp+var_18], 0
0x180041c4c  mov     [rbp+var_10], 0
0x180041c54  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180041c59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041c5d  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180041c61  xor     r8d, r8d; int *
0x180041c64  mov     [rbp+var_18], rax
0x180041c68  mov     rcx, rbx; lpString1
0x180041c6b  mov     [rbp+var_10], rax
0x180041c6f  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180041c74  mov     ebx, eax
0x180041c76  test    eax, eax
0x180041c78  jns     short loc_180041C84
0x180041c7a  mov     edx, 0Dh
0x180041c7f  jmp     loc_180041D3F
0x180041c84  xor     edx, edx
0x180041c86  mov     [rbp+arg_8], 0
0x180041c8e  lea     rcx, [rbp+arg_8]
0x180041c92  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041c97  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180041c9b  lea     rax, [rbp+arg_8]
0x180041c9f  mov     r9d, 20019h; samDesired
0x180041ca5  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180041caa  xor     r8d, r8d; ulOptions
0x180041cad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041cb4  call    cs:__imp_RegOpenKeyExW
0x180041cbb  nop     dword ptr [rax+rax+00h]
0x180041cc0  mov     ebx, eax
0x180041cc2  test    eax, eax
0x180041cc4  jnz     short loc_180041CD9
0x180041cc6  lea     rcx, [rbp+arg_8]
0x180041cca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041ccf  mov     ebx, 800700B7h
0x180041cd4  jmp     loc_180041DE4
0x180041cd9  cmp     eax, 2
0x180041cdc  jz      short loc_180041D15
0x180041cde  test    eax, eax
0x180041ce0  jle     short loc_180041CEB
0x180041ce2  movzx   ebx, ax
0x180041ce5  or      ebx, 80070000h
0x180041ceb  test    ebx, ebx
0x180041ced  jns     short loc_180041D07
0x180041cef  mov     rcx, [rbp+8]; this
0x180041cf3  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041cfa  mov     r9d, ebx; char *
0x180041cfd  mov     edx, 13h; void *
0x180041d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041d07  lea     rcx, [rbp+arg_8]
0x180041d0b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041d10  jmp     loc_180041DE4
0x180041d15  lea     rcx, [rbp+arg_8]
0x180041d19  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041d1e  mov     r8d, 4
0x180041d24  lea     rdx, ?c_szBAK@@3QBGB; ".bak"
0x180041d2b  lea     rcx, [rbp+lpSubKey]
0x180041d2f  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180041d34  mov     ebx, eax
0x180041d36  test    eax, eax
0x180041d38  jns     short loc_180041D57
0x180041d3a  mov     edx, 17h; void *
0x180041d3f  mov     rcx, [rbp+8]; this
0x180041d43  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041d4a  mov     r9d, eax; char *
0x180041d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041d52  jmp     loc_180041DE4
0x180041d57  xor     edx, edx
0x180041d59  mov     [rbp+arg_10], 0
0x180041d61  lea     rcx, [rbp+arg_10]
0x180041d65  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041d6a  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180041d6e  lea     rax, [rbp+arg_10]
0x180041d72  mov     r9d, 20019h; samDesired
0x180041d78  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180041d7d  xor     r8d, r8d; ulOptions
0x180041d80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041d87  call    cs:__imp_RegOpenKeyExW
0x180041d8e  nop     dword ptr [rax+rax+00h]
0x180041d93  mov     ebx, eax
0x180041d95  test    eax, eax
0x180041d97  jnz     short loc_180041DA2
0x180041d99  lea     rcx, [rbp+arg_10]
0x180041d9d  jmp     loc_180041CCA
0x180041da2  cmp     eax, 2
0x180041da5  jz      short loc_180041DD9
0x180041da7  test    eax, eax
0x180041da9  jle     short loc_180041DB4
0x180041dab  movzx   ebx, ax
0x180041dae  or      ebx, 80070000h
0x180041db4  test    ebx, ebx
0x180041db6  jns     short loc_180041DD0
0x180041db8  mov     rcx, [rbp+8]; this
0x180041dbc  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041dc3  mov     r9d, ebx; char *
0x180041dc6  mov     edx, 1Dh; void *
0x180041dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041dd0  lea     rcx, [rbp+arg_10]
0x180041dd4  jmp     loc_180041D0B
0x180041dd9  lea     rcx, [rbp+arg_10]
0x180041ddd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041de2  xor     ebx, ebx
0x180041de4  lea     rcx, [rbp+lpSubKey]
0x180041de8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180041ded  mov     eax, ebx
0x180041def  mov     rbx, [rsp+50h+arg_0]
0x180041df4  add     rsp, 50h
0x180041df8  pop     rbp
0x180041df9  retn
```
