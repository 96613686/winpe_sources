# AddPostBootReminder(void *,uint)

- ea: `0x1800393f8`
- end: `0x18003974c`
- name: `?AddPostBootReminder@@YAJPEAXI@Z`
- size: `852`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bdd8`

## callees

- `0x1800053c0`
- `0x180005dd0`
- `0x180007b58`
- `0x1800130d0`
- `0x180013770`
- `0x180014b4c`
- `0x180026e5c`
- `0x180030ad0`
- `0x180031060`
- `0x1800393f8`
- `0x180039754`
- `0x180040bcc`
- `0x1800506b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800394e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800394e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180039464`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180039464`

## string_xrefs

- `0x18003943a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003947b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800394f7`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180039551`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800395bd`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800396ce`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800396e2`: `TempProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AddPostBootReminder(void *a1, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-29h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-29h]
  __int64 v17; // [rsp+50h] [rbp+7h] BYREF
  char v18; // [rsp+58h] [rbp+Fh]
  unsigned __int16 *v19[3]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v20[5]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  HKEY hKey; // [rsp+B0h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp+77h] BYREF

  v17 = 0;
  v18 = 0;
  phkResult = 0;
  if ( !a1 )
    goto LABEL_6;
  v3 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v17, a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v5 = RegOpenCurrentUser(0x20006u, &phkResult);
    if ( v5 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4A5,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
             (const char *)v5,
             dwOptions);
      goto LABEL_40;
    }
LABEL_6:
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = HKEY_CURRENT_USER;
    if ( phkResult )
      v6 = phkResult;
    v7 = RegCreateKeyExW(
           v6,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PostBootReminders\\ProfileError",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v7 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4AA,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
             (const char *)v7,
             dwOptionsa);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_40;
    }
    memset(v19, 0, sizeof(v19));
    v8 = 100;
    if ( a2 != 102 )
      v8 = 300;
    v9 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(
           v19,
           g_hDllInstance,
           v8);
    v4 = v9;
    if ( v9 >= 0 )
    {
      v9 = SHRegSetString(hKey, 0, L"Title", v19[0]);
      v4 = v9;
      if ( v9 >= 0 )
      {
        memset(v20, 0, 24);
        v11 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Initialize(
                v20,
                g_hDllInstance,
                a2);
        v4 = v11;
        if ( v11 >= 0 )
        {
          v11 = SHRegSetString(hKey, 0, L"Text", v20[0]);
          v4 = v11;
          if ( v11 >= 0 )
          {
            v11 = SHRegSetString(hKey, 0, L"IconResource", v20[0]);
            v4 = v11;
            if ( v11 >= 0 )
            {
              v11 = SHRegSetDWORD(hKey, 0, L"ShowTime", 0xEA60u);
              v4 = v11;
              if ( v11 >= 0 )
              {
                v11 = SHRegSetDWORD(hKey, 0, L"RetryInterval", 0);
                v4 = v11;
                if ( v11 >= 0 )
                {
                  v11 = SHRegSetDWORD(hKey, 0, L"RetryCount", 0);
                  v4 = v11;
                  if ( v11 >= 0 )
                  {
                    v11 = SHRegSetDWORD(hKey, 0, L"TypeFlags", 0);
                    v4 = v11;
                    if ( v11 >= 0 )
                    {
                      if ( a2 != 102 )
                        goto LABEL_39;
                      v13 = LogHiveListInfo();
                      if ( v13 < 0 )
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x4C0,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                          (const char *)(unsigned int)v13,
                          dwOptionsa);
                      v11 = SHRegSetDWORD(hKey, 0, L"TempProfile", 0);
                      v4 = v11;
                      if ( v11 >= 0 )
                      {
LABEL_39:
                        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v20);
                        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v19);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        v4 = 0;
                        goto LABEL_40;
                      }
                      v12 = 1217;
                    }
                    else
                    {
                      v12 = 1212;
                    }
                  }
                  else
                  {
                    v12 = 1211;
                  }
                }
                else
                {
                  v12 = 1210;
                }
              }
              else
              {
                v12 = 1207;
              }
            }
            else
            {
              v12 = 1205;
            }
          }
          else
          {
            v12 = 1202;
          }
        }
        else
        {
          v12 = 1201;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v11,
          dwOptionsa);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v20);
        goto LABEL_16;
      }
      v10 = 1198;
    }
    else
    {
      v10 = 1197;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v9,
      dwOptionsa);
LABEL_16:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(v19);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A3,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v3,
    dwOptions);
LABEL_40:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v17);
  return v4;
}

```

## disassembly

```asm
0x1800393f8  mov     [rsp-8+arg_8], rbx
0x1800393fd  push    rbp
0x1800393fe  push    rsi
0x1800393ff  push    rdi
0x180039400  lea     rbp, [rsp-47h]
0x180039405  sub     rsp, 90h
0x18003940c  mov     edi, edx
0x18003940e  xor     esi, esi
0x180039410  mov     [rbp+57h+var_50], rsi
0x180039414  mov     [rbp+57h+var_48], sil
0x180039418  mov     [rbp+57h+phkResult], rsi
0x18003941c  test    rcx, rcx
0x18003941f  jz      short loc_180039493
0x180039421  mov     rdx, rcx; void *
0x180039424  lea     rcx, [rbp+57h+var_50]; this
0x180039428  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18003942d  mov     ebx, eax
0x18003942f  test    eax, eax
0x180039431  jns     short loc_180039450
0x180039433  mov     rcx, [rbp+5Fh]; this
0x180039437  mov     r9d, eax; char *
0x18003943a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039441  mov     edx, 4A3h; void *
0x180039446  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003944b  jmp     loc_180039723
0x180039450  xor     edx, edx
0x180039452  lea     rcx, [rbp+57h+phkResult]
0x180039456  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003945b  lea     rdx, [rbp+57h+phkResult]; phkResult
0x18003945f  mov     ecx, 20006h; samDesired
0x180039464  call    cs:__imp_RegOpenCurrentUser
0x18003946b  nop     dword ptr [rax+rax+00h]
0x180039470  test    eax, eax
0x180039472  jz      short loc_180039493
0x180039474  mov     rcx, [rbp+5Fh]; this
0x180039478  mov     r9d, eax; char *
0x18003947b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039482  mov     edx, 4A5h; void *
0x180039487  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003948c  mov     ebx, eax
0x18003948e  jmp     loc_180039723
0x180039493  mov     [rbp+57h+hKey], rsi
0x180039497  xor     edx, edx
0x180039499  lea     rcx, [rbp+57h+hKey]
0x18003949d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800394a2  mov     rcx, 0FFFFFFFF80000001h
0x1800394a9  mov     rax, [rbp+57h+phkResult]
0x1800394ad  test    rax, rax
0x1800394b0  cmovnz  rcx, rax; hKey
0x1800394b4  mov     [rsp+0A0h+lpdwDisposition], rsi; lpdwDisposition
0x1800394b9  lea     rax, [rbp+57h+hKey]
0x1800394bd  mov     [rsp+0A0h+var_68], rax; phkResult
0x1800394c2  mov     [rsp+0A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800394c7  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x1800394cf  mov     [rsp+0A0h+dwOptions], esi; int
0x1800394d3  xor     r9d, r9d; lpClass
0x1800394d6  xor     r8d, r8d; Reserved
0x1800394d9  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800394e0  call    cs:__imp_RegCreateKeyExW
0x1800394e7  nop     dword ptr [rax+rax+00h]
0x1800394ec  test    eax, eax
0x1800394ee  jz      short loc_180039518
0x1800394f0  mov     rcx, [rbp+5Fh]; this
0x1800394f4  mov     r9d, eax; char *
0x1800394f7  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800394fe  mov     edx, 4AAh; void *
0x180039503  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180039508  mov     ebx, eax
0x18003950a  lea     rcx, [rbp+57h+hKey]
0x18003950e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039513  jmp     loc_180039723
0x180039518  mov     [rbp+57h+var_40], rsi
0x18003951c  mov     [rbp+57h+var_38], rsi
0x180039520  mov     [rbp+57h+var_30], rsi
0x180039524  mov     eax, 12Ch
0x180039529  mov     r8d, 64h ; 'd'
0x18003952f  cmp     edi, 66h ; 'f'
0x180039532  cmovnz  r8d, eax
0x180039536  mov     rdx, cs:?g_hDllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hDllInstance
0x18003953d  lea     rcx, [rbp+57h+var_40]
0x180039541  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x180039546  mov     ebx, eax
0x180039548  test    eax, eax
0x18003954a  jns     short loc_180039570
0x18003954c  mov     edx, 4ADh; void *
0x180039551  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180039558  mov     r9d, eax; char *
0x18003955b  mov     rcx, [rbp+5Fh]; this
0x18003955f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039564  nop
0x180039565  lea     rcx, [rbp+57h+var_40]
0x180039569  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003956e  jmp     short loc_18003950A
0x180039570  mov     r9, [rbp+57h+var_40]; unsigned __int16 *
0x180039574  lea     r8, aTitle; "Title"
0x18003957b  xor     edx, edx; unsigned __int16 *
0x18003957d  mov     rcx, [rbp+57h+hKey]; hKey
0x180039581  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039586  mov     ebx, eax
0x180039588  test    eax, eax
0x18003958a  jns     short loc_180039593
0x18003958c  mov     edx, 4AEh
0x180039591  jmp     short loc_180039551
0x180039593  mov     [rbp+57h+var_28], rsi
0x180039597  mov     [rbp+57h+var_20], rsi
0x18003959b  mov     [rbp+57h+var_18], rsi
0x18003959f  mov     r8d, edi
0x1800395a2  mov     rdx, cs:?g_hDllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hDllInstance
0x1800395a9  lea     rcx, [rbp+57h+var_28]
0x1800395ad  call    ?Initialize@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x1800395b2  mov     ebx, eax
0x1800395b4  test    eax, eax
0x1800395b6  jns     short loc_1800395DC
0x1800395b8  mov     edx, 4B1h; void *
0x1800395bd  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800395c4  mov     r9d, eax; char *
0x1800395c7  mov     rcx, [rbp+5Fh]; this
0x1800395cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800395d0  nop
0x1800395d1  lea     rcx, [rbp+57h+var_28]
0x1800395d5  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x1800395da  jmp     short loc_180039565
0x1800395dc  mov     r9, [rbp+57h+var_28]; unsigned __int16 *
0x1800395e0  lea     r8, aText; "Text"
0x1800395e7  xor     edx, edx; unsigned __int16 *
0x1800395e9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800395ed  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800395f2  mov     ebx, eax
0x1800395f4  test    eax, eax
0x1800395f6  jns     short loc_1800395FF
0x1800395f8  mov     edx, 4B2h
0x1800395fd  jmp     short loc_1800395BD
0x1800395ff  mov     r9, [rbp+57h+var_28]; unsigned __int16 *
0x180039603  lea     r8, aIconresource; "IconResource"
0x18003960a  xor     edx, edx; unsigned __int16 *
0x18003960c  mov     rcx, [rbp+57h+hKey]; hKey
0x180039610  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039615  mov     ebx, eax
0x180039617  test    eax, eax
0x180039619  jns     short loc_180039622
0x18003961b  mov     edx, 4B5h
0x180039620  jmp     short loc_1800395BD
0x180039622  mov     r9d, 0EA60h; unsigned int
0x180039628  lea     r8, aShowtime; "ShowTime"
0x18003962f  xor     edx, edx; unsigned __int16 *
0x180039631  mov     rcx, [rbp+57h+hKey]; HKEY
0x180039635  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18003963a  mov     ebx, eax
0x18003963c  test    eax, eax
0x18003963e  jns     short loc_18003964A
0x180039640  mov     edx, 4B7h
0x180039645  jmp     loc_1800395BD
0x18003964a  xor     r9d, r9d; unsigned int
0x18003964d  lea     r8, aRetryinterval; "RetryInterval"
0x180039654  xor     edx, edx; unsigned __int16 *
0x180039656  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003965a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18003965f  mov     ebx, eax
0x180039661  test    eax, eax
0x180039663  jns     short loc_18003966F
0x180039665  mov     edx, 4BAh
0x18003966a  jmp     loc_1800395BD
0x18003966f  xor     r9d, r9d; unsigned int
0x180039672  lea     r8, aRetrycount; "RetryCount"
0x180039679  xor     edx, edx; unsigned __int16 *
0x18003967b  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003967f  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180039684  mov     ebx, eax
0x180039686  test    eax, eax
0x180039688  jns     short loc_180039694
0x18003968a  mov     edx, 4BBh
0x18003968f  jmp     loc_1800395BD
0x180039694  xor     r9d, r9d; unsigned int
0x180039697  lea     r8, aTypeflags; "TypeFlags"
0x18003969e  xor     edx, edx; unsigned __int16 *
0x1800396a0  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800396a4  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800396a9  mov     ebx, eax
0x1800396ab  test    eax, eax
0x1800396ad  jns     short loc_1800396B9
0x1800396af  mov     edx, 4BCh
0x1800396b4  jmp     loc_1800395BD
0x1800396b9  cmp     edi, 66h ; 'f'
0x1800396bc  jnz     short loc_180039704
0x1800396be  call    ?LogHiveListInfo@@YAJXZ; LogHiveListInfo(void)
0x1800396c3  mov     rcx, [rbp+5Fh]; this
0x1800396c7  test    eax, eax
0x1800396c9  jns     short loc_1800396DF
0x1800396cb  mov     r9d, eax; char *
0x1800396ce  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800396d5  mov     edx, 4C0h; void *
0x1800396da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800396df  xor     r9d, r9d; unsigned int
0x1800396e2  lea     r8, aTempprofile; "TempProfile"
0x1800396e9  xor     edx, edx; unsigned __int16 *
0x1800396eb  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800396ef  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800396f4  mov     ebx, eax
0x1800396f6  test    eax, eax
0x1800396f8  jns     short loc_180039704
0x1800396fa  mov     edx, 4C1h
0x1800396ff  jmp     loc_1800395BD
0x180039704  lea     rcx, [rbp+57h+var_28]
0x180039708  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x18003970d  nop
0x18003970e  lea     rcx, [rbp+57h+var_40]
0x180039712  call    ??1?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::~NativeString<Windows::Internal::LocalMemPolicy<ushort>>(void)
0x180039717  nop
0x180039718  lea     rcx, [rbp+57h+hKey]
0x18003971c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039721  mov     ebx, esi
0x180039723  lea     rcx, [rbp+57h+phkResult]
0x180039727  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003972c  nop
0x18003972d  lea     rcx, [rbp+57h+var_50]; this
0x180039731  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180039736  mov     eax, ebx
0x180039738  mov     rbx, [rsp+0A0h+arg_8]
0x180039740  add     rsp, 90h
0x180039747  pop     rdi
0x180039748  pop     rsi
0x180039749  pop     rbp
0x18003974a  retn
```
