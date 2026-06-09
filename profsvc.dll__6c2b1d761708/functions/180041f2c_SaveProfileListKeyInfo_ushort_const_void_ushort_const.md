# _SaveProfileListKeyInfo(ushort const *,void *,ushort const *)

- ea: `0x180041f2c`
- end: `0x180042146`
- name: `?_SaveProfileListKeyInfo@@YAJPEBGPEAX0@Z`
- size: `538`
- prototype: `__int64 __fastcall(LPCWCH lpString1, BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180030050`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180014b4c`
- `0x180030ad0`
- `0x180031060`
- `0x180041504`
- `0x180041f2c`
- `0x180051554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042000`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042000`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800420b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800420b5`

## string_xrefs

- `0x18004203c`: `ProfileImagePath`
- `0x180041f98`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180042019`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18004205a`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v19 = -1;
  v20 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, &v22);
  v7 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
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
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_20;
    }
    v11 = SHRegSetExpandString(hKey, v9, L"ProfileImagePath", a3);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v11 = SHRegSetDWORD(hKey, 0, L"Flags", 0);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v11 = SHRegSetDWORD(hKey, 0, L"State", 4u);
        v7 = v11;
        if ( v11 >= 0 )
        {
          LengthSid = GetLengthSid(lpData);
          v8 = RegSetValueExW(hKey, L"Sid", 0, 3u, lpData, LengthSid);
          if ( v8 )
          {
            v10 = 76;
            goto LABEL_5;
          }
          if ( !v22 || (v11 = CopyRedirectedProfileListKeyForSid(hKey, lpString1), v7 = v11, v11 >= 0) )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            v7 = 0;
            goto LABEL_20;
          }
          v12 = 80;
        }
        else
        {
          v12 = 75;
        }
      }
      else
      {
        v12 = 74;
      }
    }
    else
    {
      v12 = 73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)v11,
      dwOptionsa);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3C,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    dwOptions);
LABEL_20:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x180041f2c  mov     [rsp-18h+arg_0], rbx
0x180041f31  mov     [rsp-18h+arg_8], rsi
0x180041f36  push    rbp
0x180041f37  push    rdi
0x180041f38  push    r14
0x180041f3a  mov     rbp, rsp
0x180041f3d  sub     rsp, 70h
0x180041f41  mov     rdi, rcx
0x180041f44  mov     [rbp+arg_18], 0
0x180041f4b  lea     rcx, [rbp+lpSubKey]
0x180041f4f  mov     [rbp+lpSubKey], 0
0x180041f57  mov     rsi, r8
0x180041f5a  mov     [rbp+var_10], 0
0x180041f62  mov     r14, rdx
0x180041f65  mov     [rbp+var_8], 0
0x180041f6d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180041f72  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041f76  lea     r8, [rbp+arg_18]; int *
0x180041f7a  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180041f7e  mov     [rbp+var_10], rax
0x180041f82  mov     rcx, rdi; lpString1
0x180041f85  mov     [rbp+var_8], rax
0x180041f89  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180041f8e  mov     ebx, eax
0x180041f90  test    eax, eax
0x180041f92  jns     short loc_180041FB1
0x180041f94  mov     rcx, [rbp+18h]; this
0x180041f98  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041f9f  mov     r9d, eax; char *
0x180041fa2  mov     edx, 3Ch ; '<'; void *
0x180041fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041fac  jmp     loc_180042125
0x180041fb1  xor     edx, edx
0x180041fb3  mov     [rbp+hKey], 0
0x180041fbb  lea     rcx, [rbp+hKey]
0x180041fbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041fc4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180041fc8  lea     rax, [rbp+hKey]
0x180041fcc  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180041fd5  xor     r9d, r9d; lpClass
0x180041fd8  mov     [rsp+70h+phkResult], rax; phkResult
0x180041fdd  xor     r8d, r8d; Reserved
0x180041fe0  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180041fe9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041ff0  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180041ff8  mov     [rsp+70h+dwOptions], 0; int
0x180042000  call    cs:__imp_RegCreateKeyExW
0x180042007  nop     dword ptr [rax+rax+00h]
0x18004200c  test    eax, eax
0x18004200e  jz      short loc_180042038
0x180042010  mov     edx, 47h ; 'G'; void *
0x180042015  mov     rcx, [rbp+18h]; this
0x180042019  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180042020  mov     r9d, eax; char *
0x180042023  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042028  mov     ebx, eax
0x18004202a  lea     rcx, [rbp+hKey]
0x18004202e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042033  jmp     loc_180042125
0x180042038  mov     rcx, [rbp+hKey]; HKEY
0x18004203c  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180042043  mov     r9, rsi; unsigned __int16 *
0x180042046  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004204b  mov     ebx, eax
0x18004204d  test    eax, eax
0x18004204f  jns     short loc_18004206B
0x180042051  mov     edx, 49h ; 'I'; void *
0x180042056  mov     rcx, [rbp+18h]; this
0x18004205a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180042061  mov     r9d, eax; char *
0x180042064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042069  jmp     short loc_18004202A
0x18004206b  mov     rcx, [rbp+hKey]; HKEY
0x18004206f  lea     r8, Value; "Flags"
0x180042076  xor     r9d, r9d; unsigned int
0x180042079  xor     edx, edx; unsigned __int16 *
0x18004207b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180042080  mov     ebx, eax
0x180042082  test    eax, eax
0x180042084  jns     short loc_18004208D
0x180042086  mov     edx, 4Ah ; 'J'
0x18004208b  jmp     short loc_180042056
0x18004208d  mov     rcx, [rbp+hKey]; HKEY
0x180042091  lea     r8, aState; "State"
0x180042098  mov     r9d, 4; unsigned int
0x18004209e  xor     edx, edx; unsigned __int16 *
0x1800420a0  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800420a5  mov     ebx, eax
0x1800420a7  test    eax, eax
0x1800420a9  jns     short loc_1800420B2
0x1800420ab  mov     edx, 4Bh ; 'K'
0x1800420b0  jmp     short loc_180042056
0x1800420b2  mov     rcx, r14; pSid
0x1800420b5  call    cs:__imp_GetLengthSid
0x1800420bc  nop     dword ptr [rax+rax+00h]
0x1800420c1  mov     rcx, [rbp+hKey]; hKey
0x1800420c5  lea     rdx, aSid; "Sid"
0x1800420cc  mov     [rsp+70h+samDesired], eax; cbData
0x1800420d0  mov     r9d, 3; dwType
0x1800420d6  xor     r8d, r8d; Reserved
0x1800420d9  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1800420de  call    cs:__imp_RegSetValueExW
0x1800420e5  nop     dword ptr [rax+rax+00h]
0x1800420ea  test    eax, eax
0x1800420ec  jz      short loc_1800420F8
0x1800420ee  mov     edx, 4Ch ; 'L'
0x1800420f3  jmp     loc_180042015
0x1800420f8  cmp     [rbp+arg_18], 0
0x1800420fc  jz      short loc_18004211A
0x1800420fe  mov     rcx, [rbp+hKey]; hKeySrc
0x180042102  mov     rdx, rdi; unsigned __int16 *
0x180042105  call    ?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z; CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)
0x18004210a  mov     ebx, eax
0x18004210c  test    eax, eax
0x18004210e  jns     short loc_18004211A
0x180042110  mov     edx, 50h ; 'P'
0x180042115  jmp     loc_180042056
0x18004211a  lea     rcx, [rbp+hKey]
0x18004211e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042123  xor     ebx, ebx
0x180042125  lea     rcx, [rbp+lpSubKey]
0x180042129  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004212e  lea     r11, [rsp+70h+var_s0]
0x180042133  mov     eax, ebx
0x180042135  mov     rbx, [r11+20h]
0x180042139  mov     rsi, [r11+28h]
0x18004213d  mov     rsp, r11
0x180042140  pop     r14
0x180042142  pop     rdi
0x180042143  pop     rbp
0x180042144  retn
```
