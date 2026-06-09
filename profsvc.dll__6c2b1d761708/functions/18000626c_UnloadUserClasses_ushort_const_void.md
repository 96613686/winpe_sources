# UnloadUserClasses(ushort const *,void * *)

- ea: `0x18000626c`
- end: `0x180006492`
- name: `?UnloadUserClasses@@YAJPEBGPEAPEAX@Z`
- size: `550`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800066cc`
- `0x18002f844`
- `0x180030050`
- `0x180040ce0`

## callees

- `0x18000626c`
- `0x180006498`
- `0x18000a6e0`
- `0x18000b060`
- `0x18000d030`
- `0x18000e1a0`
- `0x180013770`
- `0x180030ad0`
- `0x180031060`
- `0x180040bcc`
- `0x180043800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800062dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006315`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006315`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800062f4`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800062f4`
- `OLEAUT32!__imp_VariantClear` at `0x18000637d`
- `OLEAUT32!__imp_VariantClear` at `0x1800063e9`
- `OLEAUT32!__imp_VariantClear` at `0x18000637d`
- `OLEAUT32!__imp_VariantClear` at `0x1800063e9`

## string_xrefs

- `0x180006400`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180006427`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180006441`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180006462`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18000647b`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnloadUserClasses(const unsigned __int16 *a1, void **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPCWSTR v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // eax
  int UserStateSetting; // edi
  BOOL v9; // esi
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  int phkResult; // [rsp+20h] [rbp-58h]
  unsigned int phkResulta; // [rsp+20h] [rbp-58h]
  int phkResultb; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+28h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  HKEY hKey; // [rsp+C0h] [rbp+48h] BYREF

  memset(lpSubKey, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s_Classes",
         a1);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
    goto LABEL_21;
  }
  hKey = 0;
  v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x21D,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
           (const char *)v6,
           phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_21;
  }
  v7 = RegFlushKey(hKey);
  if ( v7 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)v7,
      phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  UserStateSetting = GetUserStateSetting(2u, (__int64)qword_18007FC90, 0x22u, 8, &pvarg, v17, 0, 0);
  if ( UserStateSetting >= 0 )
  {
    v9 = pvarg.iVal == 0xFFFF;
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    UserStateSetting = 0;
  }
  else
  {
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    v9 = 0;
  }
  v10 = retaddr;
  if ( UserStateSetting < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)UserStateSetting,
      phkResultb);
  v11 = UnmountRegHive(v10, v5, v9, a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v11,
      phkResultb);
    v4 = v12;
LABEL_21:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    return v4;
  }
  if ( v5 )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v5);
  return 0;
}

```

## disassembly

```asm
0x18000626c  push    rbp
0x18000626e  push    rbx
0x18000626f  push    rsi
0x180006270  push    rdi
0x180006271  push    r12
0x180006273  push    r14
0x180006275  mov     rbp, rsp
0x180006278  sub     rsp, 78h
0x18000627c  mov     r14, rdx
0x18000627f  mov     [rbp+lpSubKey], 0
0x180006287  mov     [rbp+var_18], 0
0x18000628f  mov     [rbp+var_10], 0
0x180006297  mov     r8, rcx
0x18000629a  lea     rdx, aSClasses; "%s_Classes"
0x1800062a1  lea     rcx, [rbp+lpSubKey]
0x1800062a5  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800062aa  mov     ebx, eax
0x1800062ac  test    eax, eax
0x1800062ae  js      loc_180006420
0x1800062b4  mov     [rbp+hKey], 0
0x1800062bc  lea     rax, [rbp+hKey]
0x1800062c0  mov     [rsp+78h+phkResult], rax; unsigned int
0x1800062c5  mov     r9d, 20019h; samDesired
0x1800062cb  xor     r8d, r8d; ulOptions
0x1800062ce  mov     rbx, [rbp+lpSubKey]
0x1800062d2  mov     rdx, rbx; lpSubKey
0x1800062d5  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800062dc  call    cs:__imp_RegOpenKeyExW
0x1800062e3  nop     dword ptr [rax+rax+00h]
0x1800062e8  test    eax, eax
0x1800062ea  jnz     loc_18000643A
0x1800062f0  mov     rcx, [rbp+hKey]; hKey
0x1800062f4  call    cs:__imp_RegFlushKey
0x1800062fb  nop     dword ptr [rax+rax+00h]
0x180006300  mov     rcx, [rbp+30h]; this
0x180006304  test    eax, eax
0x180006306  jnz     loc_18000645F
0x18000630c  mov     rcx, [rbp+hKey]; hKey
0x180006310  test    rcx, rcx
0x180006313  jz      short loc_180006321
0x180006315  call    cs:__imp_RegCloseKey
0x18000631c  nop     dword ptr [rax+rax+00h]
0x180006321  xorps   xmm0, xmm0
0x180006324  xor     eax, eax
0x180006326  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000632a  mov     qword ptr [rbp+pvarg+10h], rax
0x18000632e  mov     word ptr [rbp+pvarg], ax
0x180006332  mov     [rsp+78h+var_40], rax
0x180006337  mov     [rsp+78h+var_48], eax
0x18000633b  lea     rax, [rbp+pvarg]
0x18000633f  mov     [rsp+78h+phkResult], rax; int
0x180006344  mov     r12d, 8
0x18000634a  mov     r9d, r12d
0x18000634d  lea     r8d, [r12+1Ah]
0x180006352  lea     rdx, qword_18007FC90
0x180006359  lea     ecx, [r12-6]
0x18000635e  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180006363  mov     edi, eax
0x180006365  test    eax, eax
0x180006367  jns     short loc_1800063C8
0x180006369  mov     eax, 0FFFh
0x18000636e  cmp     word ptr [rbp+pvarg], ax
0x180006372  jnz     short loc_180006379
0x180006374  mov     word ptr [rbp+pvarg], r12w
0x180006379  lea     rcx, [rbp+pvarg]; pvarg
0x18000637d  call    cs:__imp_VariantClear
0x180006384  nop     dword ptr [rax+rax+00h]
0x180006389  xor     esi, esi
0x18000638b  mov     rcx, [rbp+30h]; this
0x18000638f  test    edi, edi
0x180006391  js      loc_180006478
0x180006397  mov     r9, r14
0x18000639a  mov     r8d, esi
0x18000639d  mov     rdx, rbx
0x1800063a0  call    ?UnmountRegHive@@YAJPEAUHKEY__@@PEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHive(HKEY__ *,ushort const *,UnloadFlags,void * *)
0x1800063a5  mov     edi, eax
0x1800063a7  test    eax, eax
0x1800063a9  js      short loc_1800063F9
0x1800063ab  test    rbx, rbx
0x1800063ae  jz      short loc_1800063B8
0x1800063b0  mov     rcx, rbx
0x1800063b3  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800063b8  xor     eax, eax
0x1800063ba  add     rsp, 78h
0x1800063be  pop     r14
0x1800063c0  pop     r12
0x1800063c2  pop     rdi
0x1800063c3  pop     rsi
0x1800063c4  pop     rbx
0x1800063c5  pop     rbp
0x1800063c6  retn
0x1800063c8  xor     esi, esi
0x1800063ca  or      eax, 0FFFFFFFFh
0x1800063cd  cmp     ax, word ptr [rbp+pvarg+8]
0x1800063d1  setz    sil
0x1800063d5  mov     eax, 0FFFh
0x1800063da  cmp     word ptr [rbp+pvarg], ax
0x1800063de  jnz     short loc_1800063E5
0x1800063e0  mov     word ptr [rbp+pvarg], r12w
0x1800063e5  lea     rcx, [rbp+pvarg]; pvarg
0x1800063e9  call    cs:__imp_VariantClear
0x1800063f0  nop     dword ptr [rax+rax+00h]
0x1800063f5  xor     edi, edi
0x1800063f7  jmp     short loc_18000638B
0x1800063f9  mov     rcx, [rbp+30h]; this
0x1800063fd  mov     r9d, edi; char *
0x180006400  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006407  mov     edx, 22Ch; void *
0x18000640c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006411  mov     ebx, edi
0x180006413  lea     rcx, [rbp+lpSubKey]
0x180006417  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000641c  mov     eax, ebx
0x18000641e  jmp     short loc_1800063BA
0x180006420  mov     rcx, [rbp+30h]; this
0x180006424  mov     r9d, eax; char *
0x180006427  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000642e  mov     edx, 217h; void *
0x180006433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006438  jmp     short loc_180006413
0x18000643a  mov     rcx, [rbp+30h]; this
0x18000643e  mov     r9d, eax; char *
0x180006441  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006448  mov     edx, 21Dh; void *
0x18000644d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006452  mov     ebx, eax
0x180006454  lea     rcx, [rbp+hKey]
0x180006458  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000645d  jmp     short loc_180006413
0x18000645f  mov     r9d, eax; char *
0x180006462  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006469  mov     edx, 21Fh; void *
0x18000646e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180006473  jmp     loc_18000630C
0x180006478  mov     r9d, edi; char *
0x18000647b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006482  mov     edx, 224h; void *
0x180006487  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000648c  jmp     loc_180006397
```
