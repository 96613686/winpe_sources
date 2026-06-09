# LocalAccountManager::RemoveNonRetailDemoAccounts(void)

- ea: `0x180030860`
- end: `0x180030bc0`
- name: `?RemoveNonRetailDemoAccounts@LocalAccountManager@@UEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(LocalAccountManager *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007bbc`
- `0x180008544`
- `0x18001e9a4`
- `0x180023574`
- `0x18002f39c`
- `0x180030860`
- `0x180031194`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a79`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a79`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030b8b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030b8b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800309ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800309ff`
- `OLEAUT32!__imp_VariantClear` at `0x180030aed`
- `OLEAUT32!__imp_VariantClear` at `0x180030b29`
- `OLEAUT32!__imp_VariantClear` at `0x180030aed`
- `OLEAUT32!__imp_VariantClear` at `0x180030b29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003092d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003092d`

## string_xrefs

- `0x18003089e`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x1800308df`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x18003093e`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180030b13`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180030b3d`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180030b61`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LocalAccountManager::RemoveNonRetailDemoAccounts(LocalAccountManager *this)
{
  LocalAccountManager *v1; // rcx
  int RetailDemoUserName; // eax
  unsigned int v3; // ebx
  LocalAccountManager *v4; // rcx
  int v5; // eax
  HRESULT v6; // eax
  __int64 v7; // rdx
  char v8; // r14
  int v9; // esi
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD); // rbx
  int v12; // eax
  BSTR v13; // rax
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-79h]
  int ppva; // [rsp+20h] [rbp-79h]
  LPCWCH v18; // [rsp+30h] [rbp-69h] BYREF
  __int64 v19; // [rsp+38h] [rbp-61h] BYREF
  LPCWCH lpString2[2]; // [rsp+40h] [rbp-59h] BYREF
  __int16 v21; // [rsp+50h] [rbp-49h] BYREF
  int v22; // [rsp+52h] [rbp-47h]
  __int16 v23; // [rsp+56h] [rbp-43h]
  int v24; // [rsp+58h] [rbp-41h]
  __int64 v25; // [rsp+5Ch] [rbp-3Dh]
  int v26; // [rsp+64h] [rbp-35h]
  BSTR v27; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v28[22]; // [rsp+7Ah] [rbp-1Fh]
  VARIANTARG pvarg; // [rsp+90h] [rbp-9h] BYREF
  __int16 v30; // [rsp+B0h] [rbp+17h] BYREF
  _OWORD v31[3]; // [rsp+B2h] [rbp+19h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  __int16 v33; // [rsp+108h] [rbp+6Fh] BYREF
  int v34; // [rsp+110h] [rbp+77h] BYREF
  LPVOID v35; // [rsp+118h] [rbp+7Fh] BYREF

  lpString2[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpString2,
    0);
  RetailDemoUserName = LocalAccountManager::_GetRetailDemoUserName(v1, 0, (unsigned __int16 **)lpString2);
  v3 = RetailDemoUserName;
  if ( RetailDemoUserName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)RetailDemoUserName,
      ppv);
    goto LABEL_29;
  }
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  v5 = LocalAccountManager::_GetRetailDemoUserName(v4, 1, (unsigned __int16 **)&v18);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v5,
      ppv);
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
    goto LABEL_29;
  }
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v6 = CoCreateInstance(&CLSID_ShellLogonEnumUsers, 0, 1u, &GUID_3ee328ab_8f69_420a_9b86_7080f22af38b, &v35);
  v3 = v6;
  if ( v6 < 0 )
  {
    v7 = 174;
    goto LABEL_8;
  }
  v34 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v35 + 24LL))(v35, &v34);
  v3 = v6;
  if ( v6 < 0 )
  {
    v7 = 176;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
      (const char *)(unsigned int)v6,
      ppva);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    goto LABEL_5;
  }
  v8 = 0;
  v9 = v34;
  while ( --v9 >= 0 )
  {
    v19 = 0;
    v10 = v35;
    v11 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    v21 = 3;
    v22 = *(_DWORD *)v28;
    v23 = *(_WORD *)&v28[4];
    v24 = v9;
    v25 = *(_QWORD *)&v28[10];
    v26 = *(_DWORD *)&v28[18];
    v12 = v11(v10, &v21, &v19);
    v3 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v12,
        ppva);
      goto LABEL_25;
    }
    v13 = SysAllocString(L"LoginName");
    v27 = v13;
    if ( !v13 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)0x8007000ELL,
        ppva);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      goto LABEL_9;
    }
    pvarg.vt = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v19 + 24LL))(v19, v13, &pvarg);
    v3 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
        (const char *)(unsigned int)v14,
        ppva);
      VariantClear(&pvarg);
      goto LABEL_23;
    }
    if ( CompareStringOrdinal(pvarg.bstrVal, -1, lpString2[0], -1, 1) != 2
      && CompareStringOrdinal(pvarg.bstrVal, -1, v18, -1, 1) != 2 )
    {
      v33 = 0;
      v30 = 0;
      v31[0] = *(_OWORD *)v28;
      *(_QWORD *)((char *)v31 + 14) = *(_QWORD *)&v28[14];
      v21 = 3;
      v22 = *(_DWORD *)v28;
      v23 = *(_WORD *)&v28[4];
      v24 = v9;
      v25 = *(_QWORD *)&v28[10];
      v26 = *(_DWORD *)&v28[18];
      (*(void (__fastcall **)(LPVOID, __int16 *, __int16 *, __int16 *))(*(_QWORD *)v35 + 64LL))(v35, &v21, &v30, &v33);
      v8 = 1;
    }
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  if ( v8 )
    Sleep(0x7530u);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  v3 = 0;
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpString2);
  return v3;
}

```

## disassembly

```asm
0x180030860  push    rbp
0x180030862  push    rbx
0x180030863  push    rsi
0x180030864  push    rdi
0x180030865  push    r14
0x180030867  lea     rbp, [rsp-37h]
0x18003086c  sub     rsp, 0D0h
0x180030873  mov     [rbp+57h+lpString2], 0
0x18003087b  xor     edx, edx
0x18003087d  lea     rcx, [rbp+57h+lpString2]
0x180030881  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180030886  lea     r8, [rbp+57h+lpString2]; unsigned __int16 **
0x18003088a  xor     edx, edx; bool
0x18003088c  call    ?_GetRetailDemoUserName@LocalAccountManager@@AEAAJ_NPEAPEAG@Z; LocalAccountManager::_GetRetailDemoUserName(bool,ushort * *)
0x180030891  mov     ebx, eax
0x180030893  test    eax, eax
0x180030895  jns     short loc_1800308B4
0x180030897  mov     rcx, [rbp+5Fh]; this
0x18003089b  mov     r9d, eax; char *
0x18003089e  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800308a5  mov     edx, 0A7h; void *
0x1800308aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800308af  jmp     loc_180030BA7
0x1800308b4  mov     [rbp+57h+var_C0], 0
0x1800308bc  xor     edx, edx
0x1800308be  lea     rcx, [rbp+57h+var_C0]
0x1800308c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800308c7  lea     r8, [rbp+57h+var_C0]; unsigned __int16 **
0x1800308cb  mov     dl, 1; bool
0x1800308cd  call    ?_GetRetailDemoUserName@LocalAccountManager@@AEAAJ_NPEAPEAG@Z; LocalAccountManager::_GetRetailDemoUserName(bool,ushort * *)
0x1800308d2  mov     ebx, eax
0x1800308d4  test    eax, eax
0x1800308d6  jns     short loc_1800308FF
0x1800308d8  mov     rcx, [rbp+5Fh]; this
0x1800308dc  mov     r9d, eax; char *
0x1800308df  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800308e6  mov     edx, 0A9h; void *
0x1800308eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800308f0  nop
0x1800308f1  lea     rcx, [rbp+57h+var_C0]
0x1800308f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800308fa  jmp     loc_180030BA7
0x1800308ff  mov     [rbp+57h+arg_18], 0
0x180030907  lea     rcx, [rbp+57h+arg_18]
0x18003090b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030910  lea     rax, [rbp+57h+arg_18]
0x180030914  mov     qword ptr [rsp+0F0h+ppv], rax; int
0x180030919  lea     r9, _GUID_3ee328ab_8f69_420a_9b86_7080f22af38b; riid
0x180030920  xor     edx, edx; pUnkOuter
0x180030922  lea     r8d, [rdx+1]; dwClsContext
0x180030926  lea     rcx, CLSID_ShellLogonEnumUsers; rclsid
0x18003092d  call    cs:__imp_CoCreateInstance
0x180030933  mov     ebx, eax
0x180030935  test    eax, eax
0x180030937  jns     short loc_18003095D
0x180030939  mov     edx, 0AEh; void *
0x18003093e  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x180030945  mov     r9d, eax; char *
0x180030948  mov     rcx, [rbp+5Fh]; this
0x18003094c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030951  nop
0x180030952  lea     rcx, [rbp+57h+arg_18]
0x180030956  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003095b  jmp     short loc_1800308F1
0x18003095d  mov     [rbp+57h+arg_10], 0
0x180030964  mov     rcx, [rbp+57h+arg_18]
0x180030968  mov     rax, [rcx]
0x18003096b  lea     rdx, [rbp+57h+arg_10]
0x18003096f  mov     rax, [rax+18h]
0x180030973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030978  mov     ebx, eax
0x18003097a  test    eax, eax
0x18003097c  jns     short loc_180030985
0x18003097e  mov     edx, 0B0h
0x180030983  jmp     short loc_18003093E
0x180030985  xor     r14b, r14b
0x180030988  mov     esi, [rbp+57h+arg_10]
0x18003098b  dec     esi
0x18003098d  test    esi, esi
0x18003098f  js      loc_180030B81
0x180030995  mov     [rbp+57h+var_B8], 0
0x18003099d  mov     rdi, [rbp+57h+arg_18]
0x1800309a1  mov     rax, [rdi]
0x1800309a4  mov     rbx, [rax+30h]
0x1800309a8  lea     rcx, [rbp+57h+var_B8]
0x1800309ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800309b1  mov     eax, 3
0x1800309b6  mov     [rbp+57h+var_A0], ax
0x1800309ba  mov     edx, dword ptr [rbp+57h+var_76]
0x1800309bd  mov     [rbp+57h+var_9E], edx
0x1800309c0  movzx   edx, word ptr [rbp+57h+var_76+4]
0x1800309c4  mov     [rbp+57h+var_9A], dx
0x1800309c8  mov     [rbp+57h+var_98], esi
0x1800309cb  movsd   xmm0, qword ptr [rbp+57h+var_76+0Ah]
0x1800309d0  movsd   [rbp+57h+var_94], xmm0
0x1800309d5  mov     edx, [rbp+57h+var_64]
0x1800309d8  mov     [rbp+57h+var_8C], edx
0x1800309db  lea     r8, [rbp+57h+var_B8]
0x1800309df  lea     rdx, [rbp+57h+var_A0]
0x1800309e3  mov     rcx, rdi
0x1800309e6  mov     rax, rbx
0x1800309e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309ee  mov     ebx, eax
0x1800309f0  test    eax, eax
0x1800309f2  js      loc_180030B5A
0x1800309f8  lea     rcx, aLoginname; "LoginName"
0x1800309ff  call    cs:__imp_SysAllocString
0x180030a05  mov     [rbp+57h+var_80], rax
0x180030a09  test    rax, rax
0x180030a0c  jz      loc_180030B31
0x180030a12  xor     ecx, ecx
0x180030a14  mov     word ptr [rbp+57h+pvarg], cx
0x180030a18  mov     rcx, [rbp+57h+var_B8]
0x180030a1c  mov     rdx, [rcx]
0x180030a1f  mov     r9, [rdx+18h]
0x180030a23  lea     r8, [rbp+57h+pvarg]
0x180030a27  mov     rdx, rax
0x180030a2a  mov     rax, r9
0x180030a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a32  mov     ebx, eax
0x180030a34  test    eax, eax
0x180030a36  js      loc_180030B0C
0x180030a3c  mov     [rsp+0F0h+ppv], 1; bIgnoreCase
0x180030a44  or      r9d, 0FFFFFFFFh; cchCount2
0x180030a48  mov     r8, [rbp+57h+lpString2]; lpString2
0x180030a4c  or      edx, r9d; cchCount1
0x180030a4f  mov     rcx, qword ptr [rbp+57h+pvarg+8]; lpString1
0x180030a53  call    cs:__imp_CompareStringOrdinal
0x180030a59  cmp     eax, 2
0x180030a5c  jz      loc_180030AE9
0x180030a62  mov     [rsp+0F0h+ppv], 1; bIgnoreCase
0x180030a6a  or      r9d, 0FFFFFFFFh; cchCount2
0x180030a6e  mov     r8, [rbp+57h+var_C0]; lpString2
0x180030a72  or      edx, r9d; cchCount1
0x180030a75  mov     rcx, qword ptr [rbp+57h+pvarg+8]; lpString1
0x180030a79  call    cs:__imp_CompareStringOrdinal
0x180030a7f  cmp     eax, 2
0x180030a82  jz      short loc_180030AE9
0x180030a84  xor     eax, eax
0x180030a86  mov     [rbp+57h+arg_8], ax
0x180030a8a  mov     rcx, [rbp+57h+arg_18]
0x180030a8e  mov     [rbp+57h+var_40], ax
0x180030a92  movups  xmm0, [rbp+57h+var_76]
0x180030a96  movups  [rbp+57h+var_3E], xmm0
0x180030a9a  movsd   xmm1, qword ptr [rbp+57h+var_76+0Eh]
0x180030a9f  movsd   qword ptr [rbp+57h+var_3E+0Eh], xmm1
0x180030aa4  mov     eax, 3
0x180030aa9  mov     [rbp+57h+var_A0], ax
0x180030aad  mov     eax, dword ptr [rbp+57h+var_76]
0x180030ab0  mov     [rbp+57h+var_9E], eax
0x180030ab3  movzx   eax, word ptr [rbp+57h+var_76+4]
0x180030ab7  mov     [rbp+57h+var_9A], ax
0x180030abb  mov     [rbp+57h+var_98], esi
0x180030abe  movsd   xmm0, qword ptr [rbp+57h+var_76+0Ah]
0x180030ac3  movsd   [rbp+57h+var_94], xmm0
0x180030ac8  mov     eax, [rbp+57h+var_64]
0x180030acb  mov     [rbp+57h+var_8C], eax
0x180030ace  mov     rax, [rcx]
0x180030ad1  lea     r9, [rbp+57h+arg_8]
0x180030ad5  lea     r8, [rbp+57h+var_40]
0x180030ad9  lea     rdx, [rbp+57h+var_A0]
0x180030add  mov     rax, [rax+40h]
0x180030ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ae6  mov     r14b, 1
0x180030ae9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180030aed  call    cs:__imp_VariantClear
0x180030af3  nop
0x180030af4  lea     rcx, [rbp+57h+var_80]
0x180030af8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180030afd  nop
0x180030afe  lea     rcx, [rbp+57h+var_B8]
0x180030b02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b07  jmp     loc_18003098B
0x180030b0c  mov     rcx, [rbp+5Fh]; this
0x180030b10  mov     r9d, eax; char *
0x180030b13  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x180030b1a  mov     edx, 0B8h; void *
0x180030b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b24  nop
0x180030b25  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180030b29  call    cs:__imp_VariantClear
0x180030b2f  jmp     short loc_180030B4F
0x180030b31  mov     rcx, [rbp+5Fh]; this
0x180030b35  mov     ebx, 8007000Eh
0x180030b3a  mov     r9d, ebx; char *
0x180030b3d  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x180030b44  mov     edx, 0B6h; void *
0x180030b49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b4e  nop
0x180030b4f  lea     rcx, [rbp+57h+var_80]
0x180030b53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180030b58  jmp     short loc_180030B73
0x180030b5a  mov     rcx, [rbp+5Fh]; this
0x180030b5e  mov     r9d, eax; char *
0x180030b61  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x180030b68  mov     edx, 0B4h; void *
0x180030b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b72  nop
0x180030b73  lea     rcx, [rbp+57h+var_B8]
0x180030b77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b7c  jmp     loc_180030952
0x180030b81  test    r14b, r14b
0x180030b84  jz      short loc_180030B92
0x180030b86  mov     ecx, 7530h; dwMilliseconds
0x180030b8b  call    cs:__imp_Sleep
0x180030b91  nop
0x180030b92  lea     rcx, [rbp+57h+arg_18]
0x180030b96  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b9b  nop
0x180030b9c  lea     rcx, [rbp+57h+var_C0]
0x180030ba0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030ba5  xor     ebx, ebx
0x180030ba7  lea     rcx, [rbp+57h+lpString2]
0x180030bab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030bb0  mov     eax, ebx
0x180030bb2  add     rsp, 0D0h
0x180030bb9  pop     r14
0x180030bbb  pop     rdi
0x180030bbc  pop     rsi
0x180030bbd  pop     rbx
0x180030bbe  pop     rbp
0x180030bbf  retn
```
